# IumpUnprotectCredential(_MSV1_0_SECRETS_WRAPPER *)

- ea: `0x140036330`
- end: `0x140036445`
- name: `?IumpUnprotectCredential@@YAJPEAU_MSV1_0_SECRETS_WRAPPER@@@Z`
- size: `277`
- prototype: `__int64 __fastcall(struct _MSV1_0_SECRETS_WRAPPER *)`
- caller_count: `11`
- callee_count: `6`
- tags: ``

## callers

- `0x140034180`
- `0x140034270`
- `0x140034360`
- `0x140034450`
- `0x140034c60`
- `0x1400350e0`
- `0x1400352c0`
- `0x1400353e0`
- `0x140035980`
- `0x140035ad0`
- `0x140035c80`

## callees

- `0x140003ad6`
- `0x140006720`
- `0x140036038`
- `0x140036080`
- `0x140036330`
- `0x14003a010`

## pseudocode

```c
__int64 __fastcall IumpUnprotectCredential(struct _MSV1_0_SECRETS_WRAPPER *a1)
{
  bool v1; // zf
  int v4; // eax
  const char *v5; // r8
  unsigned int v6; // edi
  __int64 v7; // rax
  _BYTE *v8; // rcx
  size_t Size; // [rsp+60h] [rbp+8h] BYREF
  void *Src; // [rsp+68h] [rbp+10h] BYREF

  v1 = *((_BYTE *)a1 + 8) == 0;
  Src = 0;
  LODWORD(Size) = 0;
  if ( v1 )
    return 3221225485LL;
  v4 = (*(&IumpLsaIsoFunctions + 1))(
         "NtlmHash",
         (char *)a1 + 38,
         *((unsigned __int16 *)a1 + 8),
         MIDL_user_allocate,
         SafeAllocaFreeToHeap,
         &Src,
         &Size,
         0,
         0);
  v6 = v4;
  if ( v4 < 0 )
  {
    NtlmTraceErrorWithStatusViaWpp("IumpUnprotectCredential", 104, "NtlmFailure", v4);
  }
  else
  {
    if ( (unsigned int)Size <= 0x34 )
    {
      memcpy_0((char *)a1 + 38, Src, (unsigned int)Size);
      *((_BYTE *)a1 + 8) = 0;
      *((_WORD *)a1 + 8) = 0;
    }
    NtlmTraceInfoViaWpp("IumpUnprotectCredential", 104, v5);
  }
  v7 = (unsigned int)Size;
  v8 = Src;
  if ( (_DWORD)Size )
  {
    do
    {
      *v8++ = 0;
      --v7;
    }
    while ( v7 );
    v8 = Src;
  }
  SafeAllocaFreeToHeap(v8);
  return v6;
}

```

## disassembly

```asm
0x140036330  mov     rax, rsp
0x140036333  mov     [rax+18h], rbx
0x140036337  mov     [rax+20h], rsi
0x14003633b  push    rdi
0x14003633c  sub     rsp, 50h
0x140036340  cmp     byte ptr [rcx+8], 0
0x140036344  mov     rbx, rcx
0x140036347  mov     qword ptr [rax+10h], 0
0x14003634f  mov     dword ptr [rax+8], 0
0x140036356  jnz     short loc_140036362
0x140036358  mov     eax, 0C000000Dh
0x14003635d  jmp     loc_140036435
0x140036362  movzx   r8d, word ptr [rcx+10h]
0x140036367  lea     rax, [rsp+58h+Size]
0x14003636c  mov     [rsp+58h+var_18], 0
0x140036375  lea     rdx, [rcx+26h]
0x140036379  mov     [rsp+58h+var_20], 0
0x140036382  lea     r9, MIDL_user_allocate
0x140036389  mov     [rsp+58h+var_28], rax
0x14003638e  lea     rcx, aNtlmhash; "NtlmHash"
0x140036395  lea     rax, [rsp+58h+Src]
0x14003639a  mov     [rsp+58h+var_30], rax
0x14003639f  lea     rax, SafeAllocaFreeToHeap
0x1400363a6  mov     [rsp+58h+var_38], rax
0x1400363ab  mov     rax, qword ptr cs:?IumpLsaIsoFunctions@@3U_LsaIsoSupportFunctions@@A+8; _LsaIsoSupportFunctions IumpLsaIsoFunctions
0x1400363b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400363b7  mov     edi, eax
0x1400363b9  test    eax, eax
0x1400363bb  js      short loc_1400363F4
0x1400363bd  cmp     dword ptr [rsp+58h+Size], 34h ; '4'
0x1400363c2  ja      short loc_1400363E1
0x1400363c4  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x1400363c9  lea     rcx, [rbx+26h]; void *
0x1400363cd  mov     rdx, [rsp+58h+Src]; Src
0x1400363d2  call    memcpy_0
0x1400363d7  xor     ecx, ecx
0x1400363d9  mov     byte ptr [rbx+8], 0
0x1400363dd  mov     [rbx+10h], cx
0x1400363e1  mov     edx, 68h ; 'h'; unsigned int
0x1400363e6  lea     rcx, aIumpunprotectc; "IumpUnprotectCredential"
0x1400363ed  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x1400363f2  jmp     short loc_14003640F
0x1400363f4  mov     r9d, edi; int
0x1400363f7  lea     r8, aNtlmfailure; "NtlmFailure"
0x1400363fe  mov     edx, 68h ; 'h'; unsigned int
0x140036403  lea     rcx, aIumpunprotectc; "IumpUnprotectCredential"
0x14003640a  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x14003640f  mov     eax, dword ptr [rsp+58h+Size]
0x140036413  mov     rcx, [rsp+58h+Src]
0x140036418  test    rax, rax
0x14003641b  jz      short loc_14003642E
0x14003641d  mov     byte ptr [rcx], 0
0x140036420  inc     rcx
0x140036423  sub     rax, 1
0x140036427  jnz     short loc_14003641D
0x140036429  mov     rcx, [rsp+58h+Src]; void *
0x14003642e  call    SafeAllocaFreeToHeap
0x140036433  mov     eax, edi
0x140036435  mov     rbx, [rsp+58h+arg_10]
0x14003643a  mov     rsi, [rsp+58h+arg_18]
0x14003643f  add     rsp, 50h
0x140036443  pop     rdi
0x140036444  retn
```

# ConstructStatics

- ea: `0x140006b74`
- end: `0x140006c8e`
- name: `ConstructStatics`
- size: `282`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007330`

## callees

- `0x140001008`
- `0x140006b74`
- `0x140008010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140006be2`
- `ntdll!RtlAllocateHeap` at `0x140006be2`

## string_xrefs

- `0x140006c25`: `onecore\xbox\gameinput\common\Crt.cpp`

## pseudocode

```c
__int64 ConstructStatics()
{
  unsigned __int64 v0; // rcx
  void (**v1)(void); // rbx
  __int64 (__fastcall **v2)(); // rax
  SIZE_T v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  int v7; // [rsp+50h] [rbp+8h] BYREF
  int v8; // [rsp+58h] [rbp+10h] BYREF
  const char *v9; // [rsp+60h] [rbp+18h] BYREF

  v0 = qword_14000E6A0;
  v1 = (void (**)(void))off_140010008;
  v2 = off_140010008;
  if ( off_140010008 < (__int64 (__fastcall **)())qword_140010018 )
  {
    do
    {
      if ( *v2 )
        ++v0;
      ++v2;
    }
    while ( v2 < (__int64 (__fastcall **)())qword_140010018 );
    qword_14000E6A0 = v0;
  }
  if ( !v0 )
    return 0;
  v3 = 8 * v0;
  if ( !is_mul_ok(v0, 8u) )
    v3 = -1;
  P = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  if ( P )
  {
    while ( v1 < (void (**)(void))qword_140010018 )
    {
      if ( *v1 )
        (*v1)();
      ++v1;
    }
    return 0;
  }
  if ( (unsigned int)dword_14000E000 > 2 && (qword_14000E010 & 2) != 0 && (qword_14000E018 & 2) == qword_14000E018 )
  {
    v7 = -2147024882;
    v9 = "onecore\\xbox\\gameinput\\common\\Crt.cpp";
    v8 = 208;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&v9,
      (int)&dword_14000B8DC,
      v4,
      v5,
      (__int64 **)&v9,
      (__int64)&v8,
      (__int64)&v7);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x140006b74  mov     [rsp+arg_18], rbx
0x140006b79  push    rdi
0x140006b7a  sub     rsp, 40h
0x140006b7e  mov     rcx, cs:qword_14000E6A0
0x140006b85  lea     rbx, off_140010008
0x140006b8c  lea     rdi, qword_140010018
0x140006b93  mov     rax, rbx
0x140006b96  cmp     rbx, rdi
0x140006b99  jnb     short loc_140006BB4
0x140006b9b  cmp     qword ptr [rax], 0
0x140006b9f  jz      short loc_140006BA4
0x140006ba1  inc     rcx
0x140006ba4  add     rax, 8
0x140006ba8  cmp     rax, rdi
0x140006bab  jb      short loc_140006B9B
0x140006bad  mov     cs:qword_14000E6A0, rcx
0x140006bb4  test    rcx, rcx
0x140006bb7  jz      loc_140006C81
0x140006bbd  mov     eax, 8
0x140006bc2  mul     rcx
0x140006bc5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140006bcc  cmovb   rax, rcx
0x140006bd0  mov     rcx, gs:60h
0x140006bd9  mov     r8, rax; Size
0x140006bdc  xor     edx, edx; Flags
0x140006bde  mov     rcx, [rcx+30h]; HeapHandle
0x140006be2  call    cs:__imp_RtlAllocateHeap
0x140006be8  mov     cs:P, rax
0x140006bef  test    rax, rax
0x140006bf2  jnz     loc_140006C7C
0x140006bf8  mov     eax, cs:dword_14000E000
0x140006bfe  mov     ebx, 8007000Eh
0x140006c03  cmp     eax, 2
0x140006c06  jbe     short loc_140006C67
0x140006c08  mov     rcx, cs:qword_14000E018
0x140006c0f  mov     rax, cs:qword_14000E010
0x140006c16  test    al, 2
0x140006c18  jz      short loc_140006C67
0x140006c1a  mov     rax, rcx
0x140006c1d  and     eax, 2
0x140006c20  cmp     rax, rcx
0x140006c23  jnz     short loc_140006C67
0x140006c25  lea     rcx, aOnecoreXboxGam; "onecore\\xbox\\gameinput\\common\\Crt.c"...
0x140006c2c  mov     [rsp+48h+arg_0], ebx
0x140006c30  mov     [rsp+48h+arg_10], rcx
0x140006c35  lea     rdx, dword_14000B8DC
0x140006c3c  lea     rcx, [rsp+48h+arg_0]
0x140006c41  mov     [rsp+48h+arg_8], 0D0h
0x140006c49  mov     [rsp+48h+var_18], rcx
0x140006c4e  lea     rcx, [rsp+48h+arg_8]
0x140006c53  mov     [rsp+48h+var_20], rcx
0x140006c58  lea     rcx, [rsp+48h+arg_10]
0x140006c5d  mov     [rsp+48h+var_28], rcx
0x140006c62  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140006c67  mov     eax, ebx
0x140006c69  jmp     short loc_140006C83
0x140006c6b  mov     rax, [rbx]
0x140006c6e  test    rax, rax
0x140006c71  jz      short loc_140006C78
0x140006c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c78  add     rbx, 8
0x140006c7c  cmp     rbx, rdi
0x140006c7f  jb      short loc_140006C6B
0x140006c81  xor     eax, eax
0x140006c83  mov     rbx, [rsp+48h+arg_18]
0x140006c88  add     rsp, 40h
0x140006c8c  pop     rdi
0x140006c8d  retn
```

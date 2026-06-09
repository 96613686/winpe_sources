# NtlmIumComparePasswordToProtectedPassword

- ea: `0x140034700`
- end: `0x14003488e`
- name: `NtlmIumComparePasswordToProtectedPassword`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140006720`
- `0x140034700`
- `0x140036038`
- `0x140036080`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140034720`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140034720`

## string_xrefs

- `0x140034839`: `NtlmIumComparePasswordToProtectedPassword`
- `0x140034872`: `NtlmIumComparePasswordToProtectedPassword`

## pseudocode

```c
__int64 __fastcall NtlmIumComparePasswordToProtectedPassword(__int64 a1, unsigned __int16 *a2, __int64 a3, int *a4)
{
  int v7; // eax
  const char *v8; // r8
  _BYTE *v9; // rdx
  int v10; // esi
  __int64 v11; // r10
  char v12; // r9
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  void *v16[2]; // [rsp+40h] [rbp-38h] BYREF
  int v17; // [rsp+80h] [rbp+8h] BYREF

  if ( qword_140052C50 != a1 )
  {
    Sleep(5u);
    return 3221225506LL;
  }
  v17 = 0;
  *(_OWORD *)v16 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    NtlmTraceErrorWithStatusViaWpp("NtlmIumComparePasswordToProtectedPassword", 0x728u, "NtlmFailure", -1073741811);
    return 3221225485LL;
  }
  *a4 = 0;
  v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD, void *(__stdcall *)(size_t), void (*)(void *), int *, void **))qword_140052F08)(
         *(_QWORD *)(a3 + 8),
         *(unsigned __int16 *)(a3 + 2),
         MIDL_user_allocate,
         SafeAllocaFreeToHeap,
         &v17,
         v16);
  v9 = v16[1];
  v10 = v7;
  if ( v7 >= 0 )
  {
    if ( *a2 == LOWORD(v16[0]) && (v11 = *((_QWORD *)a2 + 1)) != 0 && v16[1] )
    {
      v12 = 0;
      v8 = 0;
      if ( !*a2 )
        goto LABEL_13;
      do
      {
        v13 = (unsigned int)v8;
        v8 = (const char *)(unsigned int)((_DWORD)v8 + 1);
        v12 |= *(_BYTE *)(v13 + v11) ^ *((_BYTE *)v16[1] + v13);
      }
      while ( (unsigned int)v8 < *a2 );
      v9 = v16[1];
      v14 = 0;
      if ( !v12 )
LABEL_13:
        v14 = 1;
      *a4 = v14;
    }
    else if ( !*a2 && !LOWORD(v16[0]) && !*((_QWORD *)a2 + 1) )
    {
      if ( v16[1] )
      {
LABEL_21:
        v15 = WORD1(v16[0]);
        if ( WORD1(v16[0]) )
        {
          do
          {
            *v9++ = 0;
            --v15;
          }
          while ( v15 );
          v9 = v16[1];
        }
        SafeAllocaFreeToHeap(v9);
        goto LABEL_25;
      }
      *a4 = 1;
    }
  }
  if ( v9 )
    goto LABEL_21;
LABEL_25:
  if ( v10 < 0 )
    NtlmTraceErrorWithStatusViaWpp("NtlmIumComparePasswordToProtectedPassword", 0x74Du, "NtlmFailure", v10);
  else
    NtlmTraceInfoViaWpp("NtlmIumComparePasswordToProtectedPassword", 0x74Du, v8);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140034700  push    rbx
0x140034702  push    rbp
0x140034703  push    rsi
0x140034704  push    rdi
0x140034705  sub     rsp, 58h
0x140034709  cmp     cs:qword_140052C50, rcx
0x140034710  mov     rdi, r9
0x140034713  mov     rax, r8
0x140034716  mov     rbx, rdx
0x140034719  jz      short loc_140034730
0x14003471b  mov     ecx, 5; dwMilliseconds
0x140034720  call    cs:__imp_Sleep
0x140034726  mov     eax, 0C0000022h
0x14003472b  jmp     loc_140034885
0x140034730  xor     ebp, ebp
0x140034732  xorps   xmm0, xmm0
0x140034735  mov     [rsp+78h+arg_0], ebp
0x14003473c  movups  xmmword ptr [rsp+78h+var_38], xmm0
0x140034741  test    rbx, rbx
0x140034744  jz      loc_140034863
0x14003474a  test    rax, rax
0x14003474d  jz      loc_140034863
0x140034753  test    rdi, rdi
0x140034756  jz      loc_140034863
0x14003475c  mov     [r9], ebp
0x14003475f  lea     rcx, [rsp+78h+var_38]
0x140034764  movzx   edx, word ptr [r8+2]
0x140034769  lea     r9, SafeAllocaFreeToHeap
0x140034770  mov     [rsp+78h+var_50], rcx
0x140034775  lea     r8, MIDL_user_allocate
0x14003477c  lea     rcx, [rsp+78h+arg_0]
0x140034784  mov     [rsp+78h+var_58], rcx
0x140034789  mov     rcx, [rax+8]
0x14003478d  mov     rax, cs:qword_140052F08
0x140034794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034799  mov     rdx, [rsp+78h+var_38+8]
0x14003479e  mov     esi, eax
0x1400347a0  test    eax, eax
0x1400347a2  js      short loc_140034811
0x1400347a4  movzx   eax, word ptr [rsp+78h+var_38]
0x1400347a9  cmp     [rbx], ax
0x1400347ac  jnz     short loc_1400347F6
0x1400347ae  mov     r10, [rbx+8]
0x1400347b2  test    r10, r10
0x1400347b5  jz      short loc_1400347F6
0x1400347b7  test    rdx, rdx
0x1400347ba  jz      short loc_1400347F6
0x1400347bc  mov     r9b, bpl
0x1400347bf  mov     r8d, ebp
0x1400347c2  cmp     bp, [rbx]
0x1400347c5  jnb     short loc_1400347ED
0x1400347c7  mov     eax, r8d
0x1400347ca  inc     r8d
0x1400347cd  mov     cl, [rax+rdx]
0x1400347d0  mov     al, [rax+r10]
0x1400347d4  xor     cl, al
0x1400347d6  movzx   eax, word ptr [rbx]
0x1400347d9  or      r9b, cl
0x1400347dc  cmp     r8d, eax
0x1400347df  jb      short loc_1400347C7
0x1400347e1  mov     rdx, [rsp+78h+var_38+8]
0x1400347e6  mov     eax, ebp
0x1400347e8  test    r9b, r9b
0x1400347eb  jnz     short loc_1400347F2
0x1400347ed  mov     eax, 1
0x1400347f2  mov     [rdi], eax
0x1400347f4  jmp     short loc_140034811
0x1400347f6  cmp     [rbx], bp
0x1400347f9  jnz     short loc_140034811
0x1400347fb  test    ax, ax
0x1400347fe  jnz     short loc_140034811
0x140034800  cmp     [rbx+8], rbp
0x140034804  jnz     short loc_140034811
0x140034806  test    rdx, rdx
0x140034809  jnz     short loc_140034816
0x14003480b  mov     dword ptr [rdi], 1
0x140034811  test    rdx, rdx
0x140034814  jz      short loc_140034839
0x140034816  movzx   eax, word ptr [rsp+78h+var_38+2]
0x14003481b  test    rax, rax
0x14003481e  jz      short loc_140034831
0x140034820  mov     [rdx], bpl
0x140034823  inc     rdx
0x140034826  sub     rax, 1
0x14003482a  jnz     short loc_140034820
0x14003482c  mov     rdx, [rsp+78h+var_38+8]
0x140034831  mov     rcx, rdx; void *
0x140034834  call    SafeAllocaFreeToHeap
0x140034839  lea     rcx, aNtlmiumcompare; "NtlmIumComparePasswordToProtectedPasswo"...
0x140034840  mov     edx, 74Dh; unsigned int
0x140034845  test    esi, esi
0x140034847  js      short loc_140034850
0x140034849  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x14003484e  jmp     short loc_14003485F
0x140034850  mov     r9d, esi; int
0x140034853  lea     r8, aNtlmfailure; "NtlmFailure"
0x14003485a  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x14003485f  mov     eax, esi
0x140034861  jmp     short loc_140034885
0x140034863  mov     ebx, 0C000000Dh
0x140034868  lea     r8, aNtlmfailure; "NtlmFailure"
0x14003486f  mov     r9d, ebx; int
0x140034872  lea     rcx, aNtlmiumcompare; "NtlmIumComparePasswordToProtectedPasswo"...
0x140034879  mov     edx, 728h; unsigned int
0x14003487e  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x140034883  mov     eax, ebx
0x140034885  add     rsp, 58h
0x140034889  pop     rdi
0x14003488a  pop     rsi
0x14003488b  pop     rbp
0x14003488c  pop     rbx
0x14003488d  retn
```

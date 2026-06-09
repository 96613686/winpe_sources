# MSCryptDestroyKeyPair

- ea: `0x180021490`
- end: `0x1800215dc`
- name: `MSCryptDestroyKeyPair`
- size: `332`
- prototype: `__int64 __fastcall(_QWORD *P, __int64, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004a060`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180021490`
- `0x1800215e4`
- `0x1800593e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180021508`
- `ntdll!RtlFreeHeap` at `0x180021579`
- `ntdll!RtlFreeHeap` at `0x180021508`
- `ntdll!RtlFreeHeap` at `0x180021579`

## string_xrefs

- `0x180021592`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x1800215c5`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`

## pseudocode

```c
__int64 __fastcall MSCryptDestroyKeyPair(_QWORD *P, __int64 a2, int a3)
{
  __int64 v5; // rbx
  void *v6; // rbx
  unsigned int v7; // edx
  _BYTE *v8; // rax
  __int64 v9; // rcx
  __int64 i; // rcx
  int v11; // eax

  if ( (!P || *((_DWORD *)P + 1) == 1297306187) && P )
  {
    v5 = P[4];
    if ( v5 )
    {
      SymCryptWipeAsm(P[4], *(unsigned int *)(v5 + 4));
      v6 = (void *)(v5 - *(unsigned int *)(v5 - 4));
      if ( v6 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      P[4] = 0;
    }
    v7 = *(_DWORD *)P;
    v8 = P;
    v9 = *(unsigned int *)P;
    if ( *(_DWORD *)P )
    {
      do
      {
        *v8++ = 0;
        --v9;
      }
      while ( v9 );
    }
    for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
    {
      if ( *((_BYTE *)P + i) )
      {
        v11 = MSCryptAuditPrimitiveFailure(i, L"RSA", 2438, 0);
        if ( v11 < 0 )
          DebugTraceError((unsigned int)v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c", 491);
        break;
      }
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        60);
    return 3221225480LL;
  }
}

```

## disassembly

```asm
0x180021490  push    rdi
0x180021492  sub     rsp, 40h
0x180021496  mov     rdi, rcx
0x180021499  test    rcx, rcx
0x18002149c  jz      short loc_1800214D0
0x18002149e  cmp     dword ptr [rcx+4], 4D53524Bh
0x1800214a5  jz      short loc_1800214D0
0x1800214a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214ae  lea     rax, WPP_GLOBAL_Control
0x1800214b5  cmp     rcx, rax
0x1800214b8  jz      short loc_1800214C4
0x1800214ba  test    byte ptr [rcx+1Ch], 1
0x1800214be  jnz     loc_18002158E
0x1800214c4  mov     eax, 0C0000008h
0x1800214c9  add     rsp, 40h
0x1800214cd  pop     rdi
0x1800214ce  retn
0x1800214d0  test    rdi, rdi
0x1800214d3  jz      short loc_1800214A7
0x1800214d5  mov     [rsp+48h+arg_0], rbx
0x1800214da  mov     rbx, [rcx+20h]
0x1800214de  test    rbx, rbx
0x1800214e1  jz      short loc_18002151C
0x1800214e3  mov     edx, [rbx+4]
0x1800214e6  mov     rcx, rbx
0x1800214e9  call    SymCryptWipeAsm
0x1800214ee  mov     eax, [rbx-4]
0x1800214f1  sub     rbx, rax
0x1800214f4  jz      short loc_180021514
0x1800214f6  mov     rcx, gs:60h
0x1800214ff  mov     r8, rbx; P
0x180021502  xor     edx, edx; Flags
0x180021504  mov     rcx, [rcx+30h]; HeapHandle
0x180021508  call    cs:__imp_RtlFreeHeap
0x18002150f  nop     dword ptr [rax+rax+00h]
0x180021514  mov     qword ptr [rdi+20h], 0
0x18002151c  mov     edx, [rdi]
0x18002151e  mov     rax, rdi
0x180021521  mov     rbx, [rsp+48h+arg_0]
0x180021526  mov     ecx, edx
0x180021528  test    edx, edx
0x18002152a  jz      short loc_18002153D
0x18002152c  nop     dword ptr [rax+00h]
0x180021530  mov     byte ptr [rax], 0
0x180021533  lea     rax, [rax+1]
0x180021537  sub     rcx, 1
0x18002153b  jnz     short loc_180021530
0x18002153d  xor     ecx, ecx
0x18002153f  nop
0x180021540  cmp     ecx, edx
0x180021542  jnb     short loc_180021567
0x180021544  cmp     byte ptr [rcx+rdi], 0
0x180021548  jnz     short loc_18002154E
0x18002154a  inc     ecx
0x18002154c  jmp     short loc_180021540
0x18002154e  xor     r9d, r9d
0x180021551  lea     rdx, aRsa; "RSA"
0x180021558  mov     r8d, 986h
0x18002155e  call    MSCryptAuditPrimitiveFailure
0x180021563  test    eax, eax
0x180021565  js      short loc_1800215BF
0x180021567  mov     rcx, gs:60h
0x180021570  mov     r8, rdi; P
0x180021573  xor     edx, edx; Flags
0x180021575  mov     rcx, [rcx+30h]; HeapHandle
0x180021579  call    cs:__imp_RtlFreeHeap
0x180021580  nop     dword ptr [rax+rax+00h]
0x180021585  xor     eax, eax
0x180021587  add     rsp, 40h
0x18002158b  pop     rdi
0x18002158c  retn
0x18002158e  mov     rcx, [rcx+10h]
0x180021592  lea     rdx, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021599  mov     [rsp+48h+var_18], 43Ch
0x1800215a1  lea     r9, aStatus; "Status"
0x1800215a8  mov     [rsp+48h+var_20], rdx
0x1800215ad  mov     [rsp+48h+var_28], 0C0000008h
0x1800215b5  call    WPP_SF_sDsd
0x1800215ba  jmp     loc_1800214C4
0x1800215bf  mov     r9d, 1EBh
0x1800215c5  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800215cc  lea     rdx, aStatus; "Status"
0x1800215d3  mov     ecx, eax
0x1800215d5  call    DebugTraceError
0x1800215da  jmp     short loc_180021567
```

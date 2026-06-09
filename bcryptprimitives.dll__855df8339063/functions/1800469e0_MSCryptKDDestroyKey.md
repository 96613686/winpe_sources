# MSCryptKDDestroyKey

- ea: `0x1800469e0`
- end: `0x180046b5c`
- name: `MSCryptKDDestroyKey`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010ee0`
- `0x180053750`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800469e0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180046a1e`
- `ntdll!RtlFreeHeap` at `0x180046a80`
- `ntdll!RtlFreeHeap` at `0x180046a1e`
- `ntdll!RtlFreeHeap` at `0x180046a80`

## string_xrefs

- `0x180046ab7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180046b01`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180046b2f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDDestroyKey(__int64 a1, int a2, int a3)
{
  void *v4; // r8
  __int64 v5; // rcx
  _BYTE *v6; // rax
  _BYTE *v7; // rax
  __int64 v8; // rcx

  if ( !a1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        75);
    goto LABEL_14;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        84);
LABEL_14:
    DebugTraceError(
      3221225480LL,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      1551);
    return 3221225480LL;
  }
  v4 = *(void **)(a1 + 56);
  if ( v4 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    v5 = 592;
    *(_QWORD *)(a1 + 56) = 0;
    v6 = (_BYTE *)(a1 + 48);
    do
    {
      *v6++ = 0;
      --v5;
    }
    while ( v5 );
  }
  v7 = *(_BYTE **)(a1 + 24);
  if ( v7 )
  {
    v8 = *(unsigned int *)(a1 + 16);
    if ( *(_DWORD *)(a1 + 16) )
    {
      do
      {
        *v7++ = 0;
        --v8;
      }
      while ( v8 );
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)(a1 + 24));
    *(_QWORD *)(a1 + 24) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800469e0  push    rbx
0x1800469e2  sub     rsp, 40h
0x1800469e6  mov     rbx, rcx
0x1800469e9  test    rcx, rcx
0x1800469ec  jz      loc_180046AE4
0x1800469f2  cmp     dword ptr [rcx+4], 4D534B59h
0x1800469f9  jnz     loc_180046A9E
0x1800469ff  mov     r8, [rcx+38h]; P
0x180046a03  mov     [rsp+48h+arg_0], rdi
0x180046a08  xor     edi, edi
0x180046a0a  test    r8, r8
0x180046a0d  jz      short loc_180046A4D
0x180046a0f  mov     rcx, gs:60h
0x180046a18  xor     edx, edx; Flags
0x180046a1a  mov     rcx, [rcx+30h]; HeapHandle
0x180046a1e  call    cs:__imp_RtlFreeHeap
0x180046a25  nop     dword ptr [rax+rax+00h]
0x180046a2a  mov     ecx, 250h
0x180046a2f  mov     [rbx+38h], rdi
0x180046a33  lea     rax, [rbx+30h]
0x180046a37  nop     word ptr [rax+rax+00000000h]
0x180046a40  mov     [rax], dil
0x180046a43  lea     rax, [rax+1]
0x180046a47  sub     rcx, 1
0x180046a4b  jnz     short loc_180046A40
0x180046a4d  mov     rax, [rbx+18h]
0x180046a51  test    rax, rax
0x180046a54  jz      short loc_180046A90
0x180046a56  mov     ecx, [rbx+10h]
0x180046a59  test    rcx, rcx
0x180046a5c  jz      short loc_180046A6D
0x180046a5e  xchg    ax, ax
0x180046a60  mov     [rax], dil
0x180046a63  lea     rax, [rax+1]
0x180046a67  sub     rcx, 1
0x180046a6b  jnz     short loc_180046A60
0x180046a6d  mov     rcx, gs:60h
0x180046a76  xor     edx, edx; Flags
0x180046a78  mov     r8, [rbx+18h]; P
0x180046a7c  mov     rcx, [rcx+30h]; HeapHandle
0x180046a80  call    cs:__imp_RtlFreeHeap
0x180046a87  nop     dword ptr [rax+rax+00h]
0x180046a8c  mov     [rbx+18h], rdi
0x180046a90  mov     eax, edi
0x180046a92  mov     rdi, [rsp+48h+arg_0]
0x180046a97  add     rsp, 40h
0x180046a9b  pop     rbx
0x180046a9c  retn
0x180046a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180046aa5  lea     rax, WPP_GLOBAL_Control
0x180046aac  cmp     rcx, rax
0x180046aaf  jz      short loc_180046AB7
0x180046ab1  test    byte ptr [rcx+1Ch], 1
0x180046ab5  jnz     short loc_180046B2B
0x180046ab7  lea     rbx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046abe  mov     r9d, 60Fh
0x180046ac4  lea     rdx, aStatus; "Status"
0x180046acb  mov     r8, rbx
0x180046ace  mov     ecx, 0C0000008h
0x180046ad3  call    DebugTraceError
0x180046ad8  mov     eax, 0C0000008h
0x180046add  add     rsp, 40h
0x180046ae1  pop     rbx
0x180046ae2  retn
0x180046ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x180046aeb  lea     rax, WPP_GLOBAL_Control
0x180046af2  cmp     rcx, rax
0x180046af5  jz      short loc_180046AB7
0x180046af7  test    byte ptr [rcx+1Ch], 1
0x180046afb  jz      short loc_180046AB7
0x180046afd  mov     rcx, [rcx+10h]
0x180046b01  lea     rbx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046b08  mov     [rsp+48h+var_18], 14Bh
0x180046b10  lea     r9, aStatus; "Status"
0x180046b17  mov     [rsp+48h+var_20], rbx
0x180046b1c  mov     [rsp+48h+var_28], 0C0000008h
0x180046b24  call    WPP_SF_sDsd
0x180046b29  jmp     short loc_180046ABE
0x180046b2b  mov     rcx, [rcx+10h]
0x180046b2f  lea     rbx, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180046b36  mov     [rsp+48h+var_18], 154h
0x180046b3e  lea     r9, aStatus; "Status"
0x180046b45  mov     [rsp+48h+var_20], rbx
0x180046b4a  mov     [rsp+48h+var_28], 0C0000008h
0x180046b52  call    WPP_SF_sDsd
0x180046b57  jmp     loc_180046ABE
```

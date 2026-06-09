# BfsFindEntry

- ea: `0x1400116a0`
- end: `0x14001179e`
- name: `BfsFindEntry`
- size: `254`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140006e14`
- `0x14001033c`
- `0x14001079c`
- `0x140010ffc`
- `0x140012478`

## callees

- `0x1400116a0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140011745`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140011745`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400116e6`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400116e6`
- `ntoskrnl!RtlFindSetBits` at `0x1400116fe`
- `ntoskrnl!RtlFindSetBits` at `0x14001176b`
- `ntoskrnl!RtlFindSetBits` at `0x1400116fe`
- `ntoskrnl!RtlFindSetBits` at `0x14001176b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001172e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001172e`

## pseudocode

```c
__int64 __fastcall BfsFindEntry(__int64 a1, const UNICODE_STRING *a2)
{
  _QWORD *v4; // rsi
  __int64 v5; // r14
  ULONG SetBits; // edi
  __int64 v7; // rbx
  ULONG v8; // ebx
  struct _RTL_BITMAP BitMapHeader; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF

  LODWORD(BitMapHeader.Buffer) = 0;
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
  v4 = **(_QWORD ***)(a1 + 16);
LABEL_2:
  if ( v4 == *(_QWORD **)(a1 + 16) )
    return 0;
  v5 = v4[2];
  RtlInitializeBitMap(&BitMapHeader, (PULONG)(v5 + 15968), 0x1Eu);
  SetBits = RtlFindSetBits(&BitMapHeader, 1u, 0);
  while ( 1 )
  {
    if ( SetBits == -1 )
    {
LABEL_8:
      v4 = (_QWORD *)*v4;
      goto LABEL_2;
    }
    v7 = 532LL * SetBits;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, (PCWSTR)(v5 + v7 + 28));
    if ( RtlEqualUnicodeString(&DestinationString, a2, 1u) )
      return v7 + v5 + 8;
    if ( SetBits + 1 < 0x1E )
    {
      v8 = SetBits;
      SetBits = RtlFindSetBits(&BitMapHeader, 1u, SetBits + 1);
      if ( SetBits > v8 )
        continue;
    }
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x1400116a0  push    rbx
0x1400116a2  push    rbp
0x1400116a3  push    rsi
0x1400116a4  push    rdi
0x1400116a5  push    r14
0x1400116a7  push    r15
0x1400116a9  sub     rsp, 48h
0x1400116ad  xor     eax, eax
0x1400116af  mov     r15, rdx
0x1400116b2  mov     qword ptr [rsp+78h+BitMapHeader+4], rax
0x1400116b7  mov     rbp, rcx
0x1400116ba  mov     [rsp+20h], rax
0x1400116bf  mov     rax, [rcx+10h]
0x1400116c3  mov     rsi, [rax]
0x1400116c6  cmp     rsi, [rbp+10h]
0x1400116ca  jz      loc_14001178E
0x1400116d0  mov     r14, [rsi+10h]
0x1400116d4  lea     rcx, [rsp+78h+BitMapHeader]; BitMapHeader
0x1400116d9  mov     r8d, 1Eh; SizeOfBitMap
0x1400116df  lea     rdx, [r14+3E60h]; BitMapBuffer
0x1400116e6  call    cs:__imp_RtlInitializeBitMap
0x1400116ed  nop     dword ptr [rax+rax+00h]
0x1400116f2  xor     r8d, r8d; HintIndex
0x1400116f5  lea     rcx, [rsp+78h+BitMapHeader]; BitMapHeader
0x1400116fa  lea     edx, [r8+1]; NumberToFind
0x1400116fe  call    cs:__imp_RtlFindSetBits
0x140011705  nop     dword ptr [rax+rax+00h]
0x14001170a  mov     edi, eax
0x14001170c  cmp     edi, 0FFFFFFFFh
0x14001170f  jz      short loc_14001177D
0x140011711  mov     ecx, edi
0x140011713  xorps   xmm0, xmm0
0x140011716  imul    rbx, rcx, 214h
0x14001171d  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140011722  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140011727  lea     rdx, [rbx+1Ch]
0x14001172b  add     rdx, r14; SourceString
0x14001172e  call    cs:__imp_RtlInitUnicodeString
0x140011735  nop     dword ptr [rax+rax+00h]
0x14001173a  mov     r8b, 1; CaseInSensitive
0x14001173d  lea     rcx, [rsp+78h+DestinationString]; String1
0x140011742  mov     rdx, r15; String2
0x140011745  call    cs:__imp_RtlEqualUnicodeString
0x14001174c  nop     dword ptr [rax+rax+00h]
0x140011751  test    al, al
0x140011753  jnz     short loc_140011785
0x140011755  lea     r8d, [rdi+1]; HintIndex
0x140011759  cmp     r8d, 1Eh
0x14001175d  jnb     short loc_14001177D
0x14001175f  mov     edx, 1; NumberToFind
0x140011764  lea     rcx, [rsp+78h+BitMapHeader]; BitMapHeader
0x140011769  mov     ebx, edi
0x14001176b  call    cs:__imp_RtlFindSetBits
0x140011772  nop     dword ptr [rax+rax+00h]
0x140011777  mov     edi, eax
0x140011779  cmp     eax, ebx
0x14001177b  ja      short loc_14001170C
0x14001177d  mov     rsi, [rsi]
0x140011780  jmp     loc_1400116C6
0x140011785  lea     rax, [r14+8]
0x140011789  add     rax, rbx
0x14001178c  jmp     short loc_140011790
0x14001178e  xor     eax, eax
0x140011790  add     rsp, 48h
0x140011794  pop     r15
0x140011796  pop     r14
0x140011798  pop     rdi
0x140011799  pop     rsi
0x14001179a  pop     rbp
0x14001179b  pop     rbx
0x14001179c  retn
```

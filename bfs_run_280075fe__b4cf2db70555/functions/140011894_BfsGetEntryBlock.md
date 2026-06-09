# BfsGetEntryBlock

- ea: `0x140011894`
- end: `0x140011985`
- name: `BfsGetEntryBlock`
- size: `241`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001033c`
- `0x140010ffc`
- `0x140012478`

## callees

- `0x140011894`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x1400118f7`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400118f7`
- `ntoskrnl!RtlFindSetBits` at `0x14001190f`
- `ntoskrnl!RtlFindSetBits` at `0x14001194b`
- `ntoskrnl!RtlFindSetBits` at `0x14001190f`
- `ntoskrnl!RtlFindSetBits` at `0x14001194b`

## pseudocode

```c
__int64 __fastcall BfsGetEntryBlock(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  __int64 **v4; // rax
  __int64 *i; // rdi
  __int64 v10; // rsi
  ULONG SetBits; // eax
  ULONG v12; // ebx
  __int64 result; // rax
  struct _RTL_BITMAP BitMapHeader; // [rsp+20h] [rbp-48h] BYREF

  v4 = *(__int64 ***)(a1 + 16);
  *a3 = 0;
  *a4 = 0;
  for ( i = *v4; i != *(__int64 **)(a1 + 16); i = (__int64 *)*i )
  {
    v10 = i[2];
    if ( v10 )
    {
      LODWORD(BitMapHeader.Buffer) = 0;
      *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
      RtlInitializeBitMap(&BitMapHeader, (PULONG)(v10 + 15968), 0x1Eu);
      SetBits = RtlFindSetBits(&BitMapHeader, 1u, 0);
      while ( SetBits != -1 )
      {
        if ( a2 == v10 + 532LL * SetBits + 8 )
        {
          *a4 = *((_DWORD *)i + 6);
          result = 0;
          *a3 = v10;
          return result;
        }
        if ( SetBits + 1 < 0x1E )
        {
          v12 = SetBits;
          SetBits = RtlFindSetBits(&BitMapHeader, 1u, SetBits + 1);
          if ( SetBits > v12 )
            continue;
        }
        break;
      }
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x140011894  push    rbx
0x140011896  push    rbp
0x140011897  push    rsi
0x140011898  push    rdi
0x140011899  push    r12
0x14001189b  push    r14
0x14001189d  push    r15
0x14001189f  sub     rsp, 30h
0x1400118a3  mov     rax, [rcx+10h]
0x1400118a7  mov     r14, r9
0x1400118aa  mov     r15, r8
0x1400118ad  mov     qword ptr [r8], 0
0x1400118b4  mov     r12, rdx
0x1400118b7  mov     dword ptr [r9], 0
0x1400118be  mov     rbp, rcx
0x1400118c1  mov     rdi, [rax]
0x1400118c4  cmp     rdi, [rbp+10h]
0x1400118c8  jz      loc_140011970
0x1400118ce  mov     rsi, [rdi+10h]
0x1400118d2  test    rsi, rsi
0x1400118d5  jz      loc_14001195B
0x1400118db  xor     eax, eax
0x1400118dd  lea     rdx, [rsi+3E60h]; BitMapBuffer
0x1400118e4  mov     qword ptr [rsp+68h+BitMapHeader+4], rax
0x1400118e9  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x1400118ee  mov     qword ptr [rsp+68h+BitMapHeader.SizeOfBitMap], rax
0x1400118f3  lea     r8d, [rax+1Eh]; SizeOfBitMap
0x1400118f7  call    cs:__imp_RtlInitializeBitMap
0x1400118fe  nop     dword ptr [rax+rax+00h]
0x140011903  xor     r8d, r8d; HintIndex
0x140011906  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x14001190b  lea     edx, [r8+1]; NumberToFind
0x14001190f  call    cs:__imp_RtlFindSetBits
0x140011916  nop     dword ptr [rax+rax+00h]
0x14001191b  cmp     eax, 0FFFFFFFFh
0x14001191e  jz      short loc_14001195B
0x140011920  mov     ecx, eax
0x140011922  imul    rcx, 214h
0x140011929  add     rcx, 8
0x14001192d  add     rcx, rsi
0x140011930  cmp     r12, rcx
0x140011933  jz      short loc_140011963
0x140011935  lea     r8d, [rax+1]; HintIndex
0x140011939  cmp     r8d, 1Eh
0x14001193d  jnb     short loc_14001195B
0x14001193f  mov     edx, 1; NumberToFind
0x140011944  lea     rcx, [rsp+68h+BitMapHeader]; BitMapHeader
0x140011949  mov     ebx, eax
0x14001194b  call    cs:__imp_RtlFindSetBits
0x140011952  nop     dword ptr [rax+rax+00h]
0x140011957  cmp     eax, ebx
0x140011959  ja      short loc_14001191B
0x14001195b  mov     rdi, [rdi]
0x14001195e  jmp     loc_1400118C4
0x140011963  mov     eax, [rdi+18h]
0x140011966  mov     [r14], eax
0x140011969  xor     eax, eax
0x14001196b  mov     [r15], rsi
0x14001196e  jmp     short loc_140011975
0x140011970  mov     eax, 0C0000225h
0x140011975  add     rsp, 30h
0x140011979  pop     r15
0x14001197b  pop     r14
0x14001197d  pop     r12
0x14001197f  pop     rdi
0x140011980  pop     rsi
0x140011981  pop     rbp
0x140011982  pop     rbx
0x140011983  retn
```

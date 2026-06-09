# AhcApiLookupCdb

- ea: `0x140049bfc`
- end: `0x140049e02`
- name: `AhcApiLookupCdb`
- size: `518`
- prototype: `__int64 __fastcall(__int64, __m128i *, _DWORD *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400497bc`

## callees

- `0x14002726c`
- `0x1400273f4`
- `0x14003e364`
- `0x140049520`
- `0x140049bfc`
- `0x14004b2b0`
- `0x14004ba84`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140049d2e`
- `ntoskrnl!ProbeForWrite` at `0x140049d2e`
- `ntoskrnl!MmIsUserAddress` at `0x140049c74`
- `ntoskrnl!MmIsUserAddress` at `0x140049d3d`
- `ntoskrnl!MmIsUserAddress` at `0x140049c74`
- `ntoskrnl!MmIsUserAddress` at `0x140049d3d`
- `ntoskrnl!ProbeForRead` at `0x140049c56`
- `ntoskrnl!ProbeForRead` at `0x140049c56`

## pseudocode

```c
__int64 __fastcall AhcApiLookupCdb(__int64 a1, __m128i *a2, _DWORD *a3, int a4)
{
  __int16 v6; // bx
  __int16 UShortFromUser; // ax
  int v8; // ebx
  int v9; // eax
  __m128i v11; // [rsp+38h] [rbp-50h] BYREF
  _OWORD v12[4]; // [rsp+48h] [rbp-40h] BYREF
  int Src; // [rsp+A0h] [rbp+18h] BYREF

  v11 = 0;
  v12[0] = 0;
  Src = 0;
  if ( a3 && (v6 = 0, a4 == 4) )
  {
    v11 = *a2;
    ProbeForRead((volatile void *)_mm_srli_si128(v11, 8).m128i_i64[0], (unsigned __int16)_mm_cvtsi128_si32(v11), 1u);
    if ( v11.m128i_i64[1] && v11.m128i_i16[0] )
    {
      if ( (unsigned __int8)MmIsUserAddress(v11.m128i_i64[1]) )
        UShortFromUser = RtlReadUShortFromUser(v11.m128i_i64[1]);
      else
        UShortFromUser = *(_WORD *)v11.m128i_i64[1];
      v6 = UShortFromUser;
    }
    if ( v6 )
    {
      v9 = AslUnicodeStringDuplicate(v12, &v11);
      v8 = v9;
      if ( v9 < 0 )
        AslLogCallPrintf(1, "AhcApiLookupCdb", 704, "Failed to duplicate cdb name [%x]", v9);
    }
    else
    {
      v8 = -1073741811;
    }
    if ( v8 >= 0 )
    {
      if ( (int)AhcCdbLookup(&Src, a1, v12) < 0 )
        Src = 0;
      ProbeForWrite(a3, 4u, 4u);
      if ( (unsigned __int8)MmIsUserAddress(a3) )
        RtlCopyToUser(a3, &Src, 4u);
      else
        *a3 = Src;
      v8 = 0;
    }
  }
  else
  {
    v8 = -1073741811;
    AslLogCallPrintf(1, "AhcApiLookupCdb", 675, "LookupCdb bad parameters [%x]", -1073741811);
  }
  AslAnsiStringFree(v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140049bfc  mov     rax, rsp
0x140049bff  push    rbx
0x140049c00  push    rsi
0x140049c01  push    r14
0x140049c03  push    r15
0x140049c05  sub     rsp, 68h
0x140049c09  mov     rsi, r8
0x140049c0c  mov     r14, rcx
0x140049c0f  xorps   xmm0, xmm0
0x140049c12  movups  xmmword ptr [rax-50h], xmm0
0x140049c16  xorps   xmm1, xmm1
0x140049c19  movups  xmmword ptr [rax-40h], xmm1
0x140049c1d  xor     r15d, r15d
0x140049c20  mov     [rax+18h], r15d
0x140049c24  test    r8, r8
0x140049c27  jz      loc_140049DC3
0x140049c2d  mov     ebx, r15d
0x140049c30  cmp     r9d, 4
0x140049c34  jnz     loc_140049DC3
0x140049c3a  movups  xmm0, xmmword ptr [rdx]
0x140049c3d  movups  xmmword ptr [rax-50h], xmm0
0x140049c41  movd    eax, xmm0
0x140049c45  movzx   edx, ax; Length
0x140049c48  lea     r8d, [r15+1]; Alignment
0x140049c4c  psrldq  xmm0, 8
0x140049c51  movq    rcx, xmm0; Address
0x140049c56  call    cs:__imp_ProbeForRead
0x140049c5d  nop     dword ptr [rax+rax+00h]
0x140049c62  mov     rcx, [rsp+88h+var_48]
0x140049c67  test    rcx, rcx
0x140049c6a  jz      short loc_140049CAE
0x140049c6c  cmp     [rsp+88h+var_50], r15w
0x140049c72  jz      short loc_140049CAE
0x140049c74  call    cs:__imp_MmIsUserAddress
0x140049c7b  nop     dword ptr [rax+rax+00h]
0x140049c80  test    al, al
0x140049c82  jz      short loc_140049C90
0x140049c84  mov     [rsp+88h+var_54], 1
0x140049c8c  mov     al, 1
0x140049c8e  jmp     short loc_140049C98
0x140049c90  mov     [rsp+88h+var_54], r15d
0x140049c95  mov     al, r15b
0x140049c98  mov     rcx, [rsp+88h+var_48]
0x140049c9d  test    al, al
0x140049c9f  jz      short loc_140049CA8
0x140049ca1  call    RtlReadUShortFromUser
0x140049ca6  jmp     short loc_140049CAB
0x140049ca8  movzx   eax, word ptr [rcx]
0x140049cab  movzx   ebx, ax
0x140049cae  test    bx, bx
0x140049cb1  jnz     short loc_140049CBE
0x140049cb3  mov     ebx, 0C000000Dh
0x140049cb8  mov     [rsp+88h+var_58], ebx
0x140049cbc  jmp     short loc_140049CFA
0x140049cbe  lea     rdx, [rsp+88h+var_50]
0x140049cc3  lea     rcx, [rsp+88h+var_40]
0x140049cc8  call    AslUnicodeStringDuplicate
0x140049ccd  mov     ebx, eax
0x140049ccf  mov     [rsp+88h+var_58], eax
0x140049cd3  test    eax, eax
0x140049cd5  jns     short loc_140049CFA
0x140049cd7  mov     [rsp+88h+var_68], eax
0x140049cdb  lea     r9, aFailedToDuplic_2; "Failed to duplicate cdb name [%x]"
0x140049ce2  mov     r8d, 2C0h
0x140049ce8  lea     rdx, aAhcapilookupcd; "AhcApiLookupCdb"
0x140049cef  mov     ecx, 1
0x140049cf4  call    AslLogCallPrintf
0x140049cf9  nop
0x140049cfa  test    ebx, ebx
0x140049cfc  js      loc_140049DEA
0x140049d02  lea     r8, [rsp+88h+var_40]
0x140049d07  mov     rdx, r14
0x140049d0a  lea     rcx, [rsp+88h+Src]
0x140049d12  call    AhcCdbLookup
0x140049d17  test    eax, eax
0x140049d19  jns     short loc_140049D23
0x140049d1b  mov     [rsp+88h+Src], r15d
0x140049d23  mov     edx, 4; Length
0x140049d28  mov     r8d, edx; Alignment
0x140049d2b  mov     rcx, rsi; Address
0x140049d2e  call    cs:__imp_ProbeForWrite
0x140049d35  nop     dword ptr [rax+rax+00h]
0x140049d3a  mov     rcx, rsi
0x140049d3d  call    cs:__imp_MmIsUserAddress
0x140049d44  nop     dword ptr [rax+rax+00h]
0x140049d49  test    al, al
0x140049d4b  jz      short loc_140049D65
0x140049d4d  mov     r8d, 4; Size
0x140049d53  lea     rdx, [rsp+88h+Src]; Src
0x140049d5b  mov     rcx, rsi; void *
0x140049d5e  call    RtlCopyToUser
0x140049d63  jmp     short loc_140049D6E
0x140049d65  mov     eax, [rsp+88h+Src]
0x140049d6c  mov     [rsi], eax
0x140049d6e  mov     ebx, r15d
0x140049d71  jmp     short loc_140049DEA
0x140049d73  mov     ebx, eax
0x140049d75  mov     [rsp+88h+var_68], eax
0x140049d79  lea     r9, aLookupcdbExcep; "LookupCdb exception [%x]"
0x140049d80  mov     r8d, 2EEh
0x140049d86  lea     rdx, aAhcapilookupcd; "AhcApiLookupCdb"
0x140049d8d  mov     ecx, 1
0x140049d92  call    AslLogCallPrintf
0x140049d97  jmp     short loc_140049DEA
0x140049d99  mov     ebx, eax
0x140049d9b  mov     [rsp+88h+var_58], eax
0x140049d9f  mov     [rsp+88h+var_68], eax
0x140049da3  lea     r9, aLookupcdbExcep; "LookupCdb exception [%x]"
0x140049daa  mov     r8d, 2C5h
0x140049db0  lea     rdx, aAhcapilookupcd; "AhcApiLookupCdb"
0x140049db7  mov     ecx, 1
0x140049dbc  call    AslLogCallPrintf
0x140049dc1  jmp     short loc_140049DEA
0x140049dc3  mov     ebx, 0C000000Dh
0x140049dc8  mov     [rsp+88h+var_68], ebx
0x140049dcc  lea     r9, aLookupcdbBadPa; "LookupCdb bad parameters [%x]"
0x140049dd3  mov     r8d, 2A3h
0x140049dd9  lea     rdx, aAhcapilookupcd; "AhcApiLookupCdb"
0x140049de0  mov     ecx, 1
0x140049de5  call    AslLogCallPrintf
0x140049dea  lea     rcx, [rsp+88h+var_40]
0x140049def  call    AslAnsiStringFree
0x140049df4  mov     eax, ebx
0x140049df6  add     rsp, 68h
0x140049dfa  pop     r15
0x140049dfc  pop     r14
0x140049dfe  pop     rsi
0x140049dff  pop     rbx
0x140049e00  retn
```

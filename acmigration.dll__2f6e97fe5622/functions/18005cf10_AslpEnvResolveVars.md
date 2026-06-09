# AslpEnvResolveVars

- ea: `0x18005cf10`
- end: `0x18005d251`
- name: `AslpEnvResolveVars`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005c7c4`

## callees

- `0x1800027a8`
- `0x180052784`
- `0x1800533c0`
- `0x1800543c0`
- `0x18005cf10`

## string_xrefs

- `0x18005d1b3`: `RtlStringCchCopyW failed [%x]`
- `0x18005d1c6`: `RtlStringCchCopyW failed [%x]`
- `0x18005d21f`: `RtlStringCchCopyW failed [%x]`
- `0x18005d1da`: `ResolvedPath is NULL or zero size [%#x]`
- `0x18005d0a4`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

## pseudocode

```c
__int64 __fastcall AslpEnvResolveVars(
        const wchar_t *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned int *a7)
{
  int v7; // ebx
  unsigned __int64 v8; // r14
  int v9; // r13d
  unsigned int v10; // esi
  unsigned __int16 *v11; // rdi
  __int64 v12; // r12
  unsigned __int64 v14; // r15
  unsigned int v15; // eax
  unsigned __int16 v16; // cx
  unsigned __int64 i; // rdi
  unsigned __int16 v18; // ax
  int v19; // eax
  __int64 v20; // r11
  unsigned int v21; // ebx
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v28; // [rsp+20h] [rbp-48h]
  const wchar_t *v29; // [rsp+70h] [rbp+8h]

  v29 = a1;
  v7 = 0;
  v8 = a4;
  v9 = 0;
  v10 = 0;
  v11 = a3;
  v12 = 0;
  while ( !v7 )
  {
    v14 = 24 * v12;
    v15 = *((_DWORD *)&unk_180096A40 + 6 * v12);
    if ( a2 > v15 )
    {
      if ( !wcsnicmp(a1, off_180096A30[v14 / 8], v15) )
      {
        v10 = a2 + *(_DWORD *)((char *)&unk_180096A44 + v14) - *(_DWORD *)((char *)&unk_180096A40 + v14);
        if ( v10 > (unsigned int)v8 )
        {
          v21 = -1073741789;
          goto LABEL_39;
        }
        if ( !v11 || !(_DWORD)v8 )
        {
          v21 = -1073741811;
          LODWORD(v28) = -1073741811;
          AslLogCallPrintf(1, "AslpEnvResolveVars", 1035, "ResolvedPath is NULL or zero size [%#x]", v28);
          return v21;
        }
        if ( v12 )
        {
          if ( !v9 )
          {
LABEL_20:
            v24 = RtlStringCchCopyW(v11, v8, (&off_180096A38)[v14 / 8]);
            v21 = v24;
            if ( v24 < 0 )
            {
              LODWORD(v28) = v24;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1091, "RtlStringCchCopyW failed [%x]", v28);
              return v21;
            }
            v25 = RtlStringCchCatW(v11, v8, &v29[*(unsigned int *)((char *)&unk_180096A40 + v14)]);
            v21 = v25;
            if ( v25 < 0 )
            {
              LODWORD(v28) = v25;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1097, "RtlStringCchCatW failed [%x]", v28);
              return v21;
            }
          }
        }
        else
        {
          v16 = a5;
          for ( i = 0; i < 8; ++i )
          {
            v18 = a6;
            if ( word_1800969B0[8 * i] == v16 && word_1800969B2[8 * i] == a6 )
            {
              v19 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              v21 = v19;
              if ( v19 < 0 )
              {
                LODWORD(v28) = v19;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1051, "RtlStringCchCopyW failed [%x]", v28);
                return v21;
              }
              v22 = RtlStringCchCatW(a3, v8, (&off_1800969B8)[v20]);
              v21 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v28) = v22;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1057, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v23 = RtlStringCchCatW(a3, v8, &v29[*(unsigned int *)((char *)&unk_180096A40 + v14)]);
              v21 = v23;
              if ( v23 < 0 )
              {
                LODWORD(v28) = v23;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1063, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v18 = a6;
              v16 = a5;
              v9 = 1;
            }
          }
          if ( !v9 )
          {
            AslLogCallPrintf(
              1,
              "AslpEnvResolveVars",
              1074,
              "Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4",
              v16,
              v18);
            v11 = a3;
            goto LABEL_20;
          }
          v11 = a3;
        }
        v7 = 1;
      }
      a1 = v29;
    }
    if ( (unsigned __int64)++v12 >= 4 )
    {
      if ( !v7 )
      {
        if ( a2 > (unsigned int)v8 )
        {
          v21 = -1073741789;
          *a7 = a2;
          return v21;
        }
        v10 = a2;
        v26 = RtlStringCchCopyW(v11, v8, a1);
        v21 = v26;
        if ( v26 < 0 )
        {
          LODWORD(v28) = v26;
          AslLogCallPrintf(1, "AslpEnvResolveVars", 1129, "RtlStringCchCopyW failed [%x]", v28);
          return v21;
        }
      }
      break;
    }
  }
  v21 = 0;
LABEL_39:
  *a7 = v10;
  return v21;
}

```

## disassembly

```asm
0x18005cf10  mov     [rsp+arg_8], rbx
0x18005cf15  mov     [rsp+arg_10], r8
0x18005cf1a  mov     [rsp+arg_0], rcx
0x18005cf1f  push    rbp
0x18005cf20  push    rsi
0x18005cf21  push    rdi
0x18005cf22  push    r12
0x18005cf24  push    r13
0x18005cf26  push    r14
0x18005cf28  push    r15
0x18005cf2a  sub     rsp, 30h
0x18005cf2e  xor     ebx, ebx
0x18005cf30  mov     r14d, r9d
0x18005cf33  xor     r13d, r13d
0x18005cf36  lea     r11, cs:180000000h
0x18005cf3d  xor     esi, esi
0x18005cf3f  mov     rdi, r8
0x18005cf42  xor     r12d, r12d
0x18005cf45  mov     ebp, edx
0x18005cf47  test    ebx, ebx
0x18005cf49  jnz     loc_18005D22E
0x18005cf4f  lea     r15, [r12+r12*2]
0x18005cf53  shl     r15, 3
0x18005cf57  mov     eax, [r15+r11+96A40h]
0x18005cf5f  cmp     ebp, eax
0x18005cf61  jbe     loc_18005D157
0x18005cf67  mov     rdx, [r15+r11+96A30h]; String2
0x18005cf6f  mov     r8d, eax; MaxCount
0x18005cf72  call    _wcsnicmp
0x18005cf77  lea     r11, cs:180000000h
0x18005cf7e  test    eax, eax
0x18005cf80  jnz     loc_18005D152
0x18005cf86  mov     esi, [r15+r11+96A44h]
0x18005cf8e  sub     esi, [r15+r11+96A40h]
0x18005cf96  add     esi, ebp
0x18005cf98  cmp     esi, r14d
0x18005cf9b  ja      loc_18005D1FE
0x18005cfa1  test    rdi, rdi
0x18005cfa4  jz      loc_18005D1D5
0x18005cfaa  test    r14d, r14d
0x18005cfad  jz      loc_18005D1D5
0x18005cfb3  test    r12, r12
0x18005cfb6  jnz     loc_18005D0D6
0x18005cfbc  movzx   ecx, [rsp+68h+arg_20]
0x18005cfc4  lea     rdx, cs:180000000h
0x18005cfcb  xor     edi, edi
0x18005cfcd  movzx   eax, [rsp+68h+arg_28]
0x18005cfd5  mov     r11, rdi
0x18005cfd8  add     r11, r11
0x18005cfdb  cmp     rva word_1800969B0[rdx+r11*8], cx
0x18005cfe4  jnz     loc_18005D08B
0x18005cfea  cmp     rva word_1800969B2[rdx+r11*8], ax
0x18005cff3  jnz     loc_18005D08B
0x18005cff9  mov     r13, [rsp+68h+arg_10]
0x18005d001  lea     r8, aSystemroot; "%systemroot%"
0x18005d008  mov     rcx, r13
0x18005d00b  mov     rdx, r14
0x18005d00e  call    RtlStringCchCopyW
0x18005d013  mov     ebx, eax
0x18005d015  test    eax, eax
0x18005d017  js      loc_18005D1AF
0x18005d01d  lea     r8, cs:180000000h
0x18005d024  mov     rdx, r14; unsigned __int64
0x18005d027  mov     r8, rva off_1800969B8[r8+r11*8]; unsigned __int16 *
0x18005d02f  mov     rcx, r13; unsigned __int16 *
0x18005d032  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005d037  mov     ebx, eax
0x18005d039  test    eax, eax
0x18005d03b  js      loc_18005D19C
0x18005d041  mov     rcx, [rsp+68h+arg_0]
0x18005d046  lea     rax, cs:180000000h
0x18005d04d  mov     eax, [r15+rax+96A40h]
0x18005d055  mov     rdx, r14; unsigned __int64
0x18005d058  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x18005d05c  mov     rcx, r13; unsigned __int16 *
0x18005d05f  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005d064  mov     ebx, eax
0x18005d066  test    eax, eax
0x18005d068  js      loc_18005D189
0x18005d06e  movzx   eax, [rsp+68h+arg_28]
0x18005d076  lea     rdx, cs:180000000h
0x18005d07d  movzx   ecx, [rsp+68h+arg_20]
0x18005d085  mov     r13d, 1
0x18005d08b  inc     rdi
0x18005d08e  cmp     rdi, 8
0x18005d092  jb      loc_18005CFCD
0x18005d098  test    r13d, r13d
0x18005d09b  jnz     loc_18005D13E
0x18005d0a1  movzx   ecx, cx
0x18005d0a4  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x18005d0ab  movzx   eax, ax
0x18005d0ae  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x18005d0b5  mov     [rsp+68h+var_40], eax
0x18005d0b9  mov     r8d, 432h
0x18005d0bf  mov     dword ptr [rsp+68h+var_48], ecx
0x18005d0c3  lea     ecx, [r13+1]
0x18005d0c7  call    AslLogCallPrintf
0x18005d0cc  mov     rdi, [rsp+68h+arg_10]
0x18005d0d4  jmp     short loc_18005D0DB
0x18005d0d6  test    r13d, r13d
0x18005d0d9  jnz     short loc_18005D14D
0x18005d0db  lea     rax, cs:180000000h
0x18005d0e2  mov     rdx, r14
0x18005d0e5  mov     r8, [r15+rax+96A38h]
0x18005d0ed  mov     rcx, rdi
0x18005d0f0  call    RtlStringCchCopyW
0x18005d0f5  mov     ebx, eax
0x18005d0f7  test    eax, eax
0x18005d0f9  js      loc_18005D1C2
0x18005d0ff  mov     rcx, [rsp+68h+arg_0]
0x18005d104  lea     rax, cs:180000000h
0x18005d10b  mov     eax, [r15+rax+96A40h]
0x18005d113  mov     rdx, r14; unsigned __int64
0x18005d116  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x18005d11a  mov     rcx, rdi; unsigned __int16 *
0x18005d11d  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005d122  mov     ebx, eax
0x18005d124  test    eax, eax
0x18005d126  jns     short loc_18005D146
0x18005d128  mov     dword ptr [rsp+68h+var_48], eax
0x18005d12c  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18005d133  mov     r8d, 449h
0x18005d139  jmp     loc_18005D1EB
0x18005d13e  mov     rdi, [rsp+68h+arg_10]
0x18005d146  lea     r11, cs:180000000h
0x18005d14d  mov     ebx, 1
0x18005d152  mov     rcx, [rsp+68h+arg_0]
0x18005d157  inc     r12
0x18005d15a  cmp     r12, 4
0x18005d15e  jb      loc_18005CF47
0x18005d164  test    ebx, ebx
0x18005d166  jnz     loc_18005D22E
0x18005d16c  cmp     ebp, r14d
0x18005d16f  jbe     loc_18005D205
0x18005d175  mov     rax, [rsp+68h+arg_30]
0x18005d17d  mov     ebx, 0C0000023h
0x18005d182  mov     [rax], ebp
0x18005d184  jmp     loc_18005D23A
0x18005d189  mov     dword ptr [rsp+68h+var_48], eax
0x18005d18d  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18005d194  mov     r8d, 427h
0x18005d19a  jmp     short loc_18005D1EB
0x18005d19c  mov     dword ptr [rsp+68h+var_48], eax
0x18005d1a0  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18005d1a7  mov     r8d, 421h
0x18005d1ad  jmp     short loc_18005D1EB
0x18005d1af  mov     dword ptr [rsp+68h+var_48], eax
0x18005d1b3  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x18005d1ba  mov     r8d, 41Bh
0x18005d1c0  jmp     short loc_18005D1EB
0x18005d1c2  mov     dword ptr [rsp+68h+var_48], eax
0x18005d1c6  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x18005d1cd  mov     r8d, 443h
0x18005d1d3  jmp     short loc_18005D1EB
0x18005d1d5  mov     ebx, 0C000000Dh
0x18005d1da  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x18005d1e1  mov     dword ptr [rsp+68h+var_48], ebx
0x18005d1e5  mov     r8d, 40Bh
0x18005d1eb  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x18005d1f2  mov     ecx, 1
0x18005d1f7  call    AslLogCallPrintf
0x18005d1fc  jmp     short loc_18005D23A
0x18005d1fe  mov     ebx, 0C0000023h
0x18005d203  jmp     short loc_18005D230
0x18005d205  mov     r8, rcx
0x18005d208  mov     rdx, r14
0x18005d20b  mov     rcx, rdi
0x18005d20e  mov     esi, ebp
0x18005d210  call    RtlStringCchCopyW
0x18005d215  mov     ebx, eax
0x18005d217  test    eax, eax
0x18005d219  jns     short loc_18005D22E
0x18005d21b  mov     dword ptr [rsp+68h+var_48], eax
0x18005d21f  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x18005d226  mov     r8d, 469h
0x18005d22c  jmp     short loc_18005D1EB
0x18005d22e  xor     ebx, ebx
0x18005d230  mov     rax, [rsp+68h+arg_30]
0x18005d238  mov     [rax], esi
0x18005d23a  mov     eax, ebx
0x18005d23c  mov     rbx, [rsp+68h+arg_8]
0x18005d241  add     rsp, 30h
0x18005d245  pop     r15
0x18005d247  pop     r14
0x18005d249  pop     r13
0x18005d24b  pop     r12
0x18005d24d  pop     rdi
0x18005d24e  pop     rsi
0x18005d24f  pop     rbp
0x18005d250  retn
```

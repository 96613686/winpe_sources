# AslpEnvResolveVars

- ea: `0x18004d17c`
- end: `0x18004d4bd`
- name: `AslpEnvResolveVars`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18004a7a8`

## callees

- `0x18000589c`
- `0x1800466f8`
- `0x18004c020`
- `0x18004d17c`
- `0x180051ce4`

## string_xrefs

- `0x18004d41f`: `RtlStringCchCopyW failed [%x]`
- `0x18004d432`: `RtlStringCchCopyW failed [%x]`
- `0x18004d48b`: `RtlStringCchCopyW failed [%x]`
- `0x18004d446`: `ResolvedPath is NULL or zero size [%#x]`
- `0x18004d310`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

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
  __int64 v14; // r15
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
    v14 = 3 * v12;
    v15 = qword_180119660[3 * v12];
    if ( a2 > v15 )
    {
      if ( !wcsnicmp(a1, off_180119650[v14], v15) )
      {
        v10 = a2 + HIDWORD(qword_180119660[v14]) - LODWORD(qword_180119660[v14]);
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
            v24 = RtlStringCchCopyW(v11, v8, (&off_180119658)[v14]);
            v21 = v24;
            if ( v24 < 0 )
            {
              LODWORD(v28) = v24;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1091, "RtlStringCchCopyW failed [%x]", v28);
              return v21;
            }
            v25 = RtlStringCchCatW(v11, v8, &v29[LODWORD(qword_180119660[v14])]);
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
            if ( word_1801195D0[8 * i] == v16 && word_1801195D2[8 * i] == a6 )
            {
              v19 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              v21 = v19;
              if ( v19 < 0 )
              {
                LODWORD(v28) = v19;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1051, "RtlStringCchCopyW failed [%x]", v28);
                return v21;
              }
              v22 = RtlStringCchCatW(a3, v8, (&off_1801195D8)[v20]);
              v21 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v28) = v22;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1057, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v23 = RtlStringCchCatW(a3, v8, &v29[LODWORD(qword_180119660[v14])]);
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
0x18004d17c  mov     [rsp+arg_8], rbx
0x18004d181  mov     [rsp+arg_10], r8
0x18004d186  mov     [rsp+arg_0], rcx
0x18004d18b  push    rbp
0x18004d18c  push    rsi
0x18004d18d  push    rdi
0x18004d18e  push    r12
0x18004d190  push    r13
0x18004d192  push    r14
0x18004d194  push    r15
0x18004d196  sub     rsp, 30h
0x18004d19a  xor     ebx, ebx
0x18004d19c  mov     r14d, r9d
0x18004d19f  xor     r13d, r13d
0x18004d1a2  lea     r11, cs:180000000h
0x18004d1a9  xor     esi, esi
0x18004d1ab  mov     rdi, r8
0x18004d1ae  xor     r12d, r12d
0x18004d1b1  mov     ebp, edx
0x18004d1b3  test    ebx, ebx
0x18004d1b5  jnz     loc_18004D49A
0x18004d1bb  lea     r15, [r12+r12*2]
0x18004d1bf  shl     r15, 3
0x18004d1c3  mov     eax, [r15+r11+119660h]
0x18004d1cb  cmp     ebp, eax
0x18004d1cd  jbe     loc_18004D3C3
0x18004d1d3  mov     rdx, [r15+r11+119650h]; String2
0x18004d1db  mov     r8d, eax; MaxCount
0x18004d1de  call    _wcsnicmp
0x18004d1e3  lea     r11, cs:180000000h
0x18004d1ea  test    eax, eax
0x18004d1ec  jnz     loc_18004D3BE
0x18004d1f2  mov     esi, [r15+r11+119664h]
0x18004d1fa  sub     esi, [r15+r11+119660h]
0x18004d202  add     esi, ebp
0x18004d204  cmp     esi, r14d
0x18004d207  ja      loc_18004D46A
0x18004d20d  test    rdi, rdi
0x18004d210  jz      loc_18004D441
0x18004d216  test    r14d, r14d
0x18004d219  jz      loc_18004D441
0x18004d21f  test    r12, r12
0x18004d222  jnz     loc_18004D342
0x18004d228  movzx   ecx, [rsp+68h+arg_20]
0x18004d230  lea     rdx, cs:180000000h
0x18004d237  xor     edi, edi
0x18004d239  movzx   eax, [rsp+68h+arg_28]
0x18004d241  mov     r11, rdi
0x18004d244  add     r11, r11
0x18004d247  cmp     rva word_1801195D0[rdx+r11*8], cx
0x18004d250  jnz     loc_18004D2F7
0x18004d256  cmp     rva word_1801195D2[rdx+r11*8], ax
0x18004d25f  jnz     loc_18004D2F7
0x18004d265  mov     r13, [rsp+68h+arg_10]
0x18004d26d  lea     r8, aSystemroot; "%systemroot%"
0x18004d274  mov     rcx, r13
0x18004d277  mov     rdx, r14
0x18004d27a  call    RtlStringCchCopyW
0x18004d27f  mov     ebx, eax
0x18004d281  test    eax, eax
0x18004d283  js      loc_18004D41B
0x18004d289  lea     r8, cs:180000000h
0x18004d290  mov     rdx, r14; unsigned __int64
0x18004d293  mov     r8, rva off_1801195D8[r8+r11*8]; unsigned __int16 *
0x18004d29b  mov     rcx, r13; unsigned __int16 *
0x18004d29e  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004d2a3  mov     ebx, eax
0x18004d2a5  test    eax, eax
0x18004d2a7  js      loc_18004D408
0x18004d2ad  mov     rcx, [rsp+68h+arg_0]
0x18004d2b2  lea     rax, cs:180000000h
0x18004d2b9  mov     eax, [r15+rax+119660h]
0x18004d2c1  mov     rdx, r14; unsigned __int64
0x18004d2c4  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x18004d2c8  mov     rcx, r13; unsigned __int16 *
0x18004d2cb  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004d2d0  mov     ebx, eax
0x18004d2d2  test    eax, eax
0x18004d2d4  js      loc_18004D3F5
0x18004d2da  movzx   eax, [rsp+68h+arg_28]
0x18004d2e2  lea     rdx, cs:180000000h
0x18004d2e9  movzx   ecx, [rsp+68h+arg_20]
0x18004d2f1  mov     r13d, 1
0x18004d2f7  inc     rdi
0x18004d2fa  cmp     rdi, 8
0x18004d2fe  jb      loc_18004D239
0x18004d304  test    r13d, r13d
0x18004d307  jnz     loc_18004D3AA
0x18004d30d  movzx   ecx, cx
0x18004d310  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x18004d317  movzx   eax, ax
0x18004d31a  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x18004d321  mov     [rsp+68h+var_40], eax
0x18004d325  mov     r8d, 432h
0x18004d32b  mov     dword ptr [rsp+68h+var_48], ecx
0x18004d32f  lea     ecx, [r13+1]
0x18004d333  call    AslLogCallPrintf
0x18004d338  mov     rdi, [rsp+68h+arg_10]
0x18004d340  jmp     short loc_18004D347
0x18004d342  test    r13d, r13d
0x18004d345  jnz     short loc_18004D3B9
0x18004d347  lea     rax, cs:180000000h
0x18004d34e  mov     rdx, r14
0x18004d351  mov     r8, [r15+rax+119658h]
0x18004d359  mov     rcx, rdi
0x18004d35c  call    RtlStringCchCopyW
0x18004d361  mov     ebx, eax
0x18004d363  test    eax, eax
0x18004d365  js      loc_18004D42E
0x18004d36b  mov     rcx, [rsp+68h+arg_0]
0x18004d370  lea     rax, cs:180000000h
0x18004d377  mov     eax, [r15+rax+119660h]
0x18004d37f  mov     rdx, r14; unsigned __int64
0x18004d382  lea     r8, [rcx+rax*2]; unsigned __int16 *
0x18004d386  mov     rcx, rdi; unsigned __int16 *
0x18004d389  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004d38e  mov     ebx, eax
0x18004d390  test    eax, eax
0x18004d392  jns     short loc_18004D3B2
0x18004d394  mov     dword ptr [rsp+68h+var_48], eax
0x18004d398  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18004d39f  mov     r8d, 449h
0x18004d3a5  jmp     loc_18004D457
0x18004d3aa  mov     rdi, [rsp+68h+arg_10]
0x18004d3b2  lea     r11, cs:180000000h
0x18004d3b9  mov     ebx, 1
0x18004d3be  mov     rcx, [rsp+68h+arg_0]
0x18004d3c3  inc     r12
0x18004d3c6  cmp     r12, 4
0x18004d3ca  jb      loc_18004D1B3
0x18004d3d0  test    ebx, ebx
0x18004d3d2  jnz     loc_18004D49A
0x18004d3d8  cmp     ebp, r14d
0x18004d3db  jbe     loc_18004D471
0x18004d3e1  mov     rax, [rsp+68h+arg_30]
0x18004d3e9  mov     ebx, 0C0000023h
0x18004d3ee  mov     [rax], ebp
0x18004d3f0  jmp     loc_18004D4A6
0x18004d3f5  mov     dword ptr [rsp+68h+var_48], eax
0x18004d3f9  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18004d400  mov     r8d, 427h
0x18004d406  jmp     short loc_18004D457
0x18004d408  mov     dword ptr [rsp+68h+var_48], eax
0x18004d40c  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x18004d413  mov     r8d, 421h
0x18004d419  jmp     short loc_18004D457
0x18004d41b  mov     dword ptr [rsp+68h+var_48], eax
0x18004d41f  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18004d426  mov     r8d, 41Bh
0x18004d42c  jmp     short loc_18004D457
0x18004d42e  mov     dword ptr [rsp+68h+var_48], eax
0x18004d432  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18004d439  mov     r8d, 443h
0x18004d43f  jmp     short loc_18004D457
0x18004d441  mov     ebx, 0C000000Dh
0x18004d446  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x18004d44d  mov     dword ptr [rsp+68h+var_48], ebx
0x18004d451  mov     r8d, 40Bh
0x18004d457  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x18004d45e  mov     ecx, 1
0x18004d463  call    AslLogCallPrintf
0x18004d468  jmp     short loc_18004D4A6
0x18004d46a  mov     ebx, 0C0000023h
0x18004d46f  jmp     short loc_18004D49C
0x18004d471  mov     r8, rcx
0x18004d474  mov     rdx, r14
0x18004d477  mov     rcx, rdi
0x18004d47a  mov     esi, ebp
0x18004d47c  call    RtlStringCchCopyW
0x18004d481  mov     ebx, eax
0x18004d483  test    eax, eax
0x18004d485  jns     short loc_18004D49A
0x18004d487  mov     dword ptr [rsp+68h+var_48], eax
0x18004d48b  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18004d492  mov     r8d, 469h
0x18004d498  jmp     short loc_18004D457
0x18004d49a  xor     ebx, ebx
0x18004d49c  mov     rax, [rsp+68h+arg_30]
0x18004d4a4  mov     [rax], esi
0x18004d4a6  mov     eax, ebx
0x18004d4a8  mov     rbx, [rsp+68h+arg_8]
0x18004d4ad  add     rsp, 30h
0x18004d4b1  pop     r15
0x18004d4b3  pop     r14
0x18004d4b5  pop     r13
0x18004d4b7  pop     r12
0x18004d4b9  pop     rdi
0x18004d4ba  pop     rsi
0x18004d4bb  pop     rbp
0x18004d4bc  retn
```

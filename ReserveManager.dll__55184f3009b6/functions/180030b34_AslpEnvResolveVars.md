# AslpEnvResolveVars

- ea: `0x180030b34`
- end: `0x180030e75`
- name: `AslpEnvResolveVars`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180030668`

## callees

- `0x18000427c`
- `0x180030b34`
- `0x180030e7c`
- `0x180030f40`
- `0x180031a3c`

## string_xrefs

- `0x180030dfe`: `ResolvedPath is NULL or zero size [%#x]`
- `0x180030dd7`: `RtlStringCchCopyW failed [%x]`
- `0x180030dea`: `RtlStringCchCopyW failed [%x]`
- `0x180030e43`: `RtlStringCchCopyW failed [%x]`
- `0x180030cc8`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

## pseudocode

```c
__int64 __fastcall AslpEnvResolveVars(
        const wchar_t *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned int *a7)
{
  int v7; // ebx
  __int64 v8; // r14
  int v9; // r13d
  unsigned int v10; // esi
  __int64 v11; // rdi
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
    v15 = qword_18004C100[3 * v12];
    if ( a2 > v15 )
    {
      if ( !wcsnicmp(a1, off_18004C0F0[v14], v15) )
      {
        v10 = a2 + HIDWORD(qword_18004C100[v14]) - LODWORD(qword_18004C100[v14]);
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
            v24 = RtlStringCchCopyW(v11, v8, (&off_18004C0F8)[v14]);
            v21 = v24;
            if ( v24 < 0 )
            {
              LODWORD(v28) = v24;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1091, "RtlStringCchCopyW failed [%x]", v28);
              return v21;
            }
            v25 = RtlStringCchCatW(v11, v8, &v29[LODWORD(qword_18004C100[v14])]);
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
            if ( word_18004C070[8 * i] == v16 && word_18004C072[8 * i] == a6 )
            {
              v19 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              v21 = v19;
              if ( v19 < 0 )
              {
                LODWORD(v28) = v19;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1051, "RtlStringCchCopyW failed [%x]", v28);
                return v21;
              }
              v22 = RtlStringCchCatW(a3, v8, (&off_18004C078)[v20]);
              v21 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v28) = v22;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1057, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v23 = RtlStringCchCatW(a3, v8, &v29[LODWORD(qword_18004C100[v14])]);
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
0x180030b34  mov     [rsp+arg_8], rbx
0x180030b39  mov     [rsp+arg_10], r8
0x180030b3e  mov     [rsp+arg_0], rcx
0x180030b43  push    rbp
0x180030b44  push    rsi
0x180030b45  push    rdi
0x180030b46  push    r12
0x180030b48  push    r13
0x180030b4a  push    r14
0x180030b4c  push    r15
0x180030b4e  sub     rsp, 30h
0x180030b52  xor     ebx, ebx
0x180030b54  mov     r14d, r9d
0x180030b57  xor     r13d, r13d
0x180030b5a  lea     r11, cs:180000000h
0x180030b61  xor     esi, esi
0x180030b63  mov     rdi, r8
0x180030b66  xor     r12d, r12d
0x180030b69  mov     ebp, edx
0x180030b6b  test    ebx, ebx
0x180030b6d  jnz     loc_180030E52
0x180030b73  lea     r15, [r12+r12*2]
0x180030b77  shl     r15, 3
0x180030b7b  mov     eax, [r15+r11+4C100h]
0x180030b83  cmp     ebp, eax
0x180030b85  jbe     loc_180030D7B
0x180030b8b  mov     rdx, [r15+r11+4C0F0h]; String2
0x180030b93  mov     r8d, eax; MaxCount
0x180030b96  call    _wcsnicmp
0x180030b9b  lea     r11, cs:180000000h
0x180030ba2  test    eax, eax
0x180030ba4  jnz     loc_180030D76
0x180030baa  mov     esi, [r15+r11+4C104h]
0x180030bb2  sub     esi, [r15+r11+4C100h]
0x180030bba  add     esi, ebp
0x180030bbc  cmp     esi, r14d
0x180030bbf  ja      loc_180030E22
0x180030bc5  test    rdi, rdi
0x180030bc8  jz      loc_180030DF9
0x180030bce  test    r14d, r14d
0x180030bd1  jz      loc_180030DF9
0x180030bd7  test    r12, r12
0x180030bda  jnz     loc_180030CFA
0x180030be0  movzx   ecx, [rsp+68h+arg_20]
0x180030be8  lea     rdx, cs:180000000h
0x180030bef  xor     edi, edi
0x180030bf1  movzx   eax, [rsp+68h+arg_28]
0x180030bf9  mov     r11, rdi
0x180030bfc  add     r11, r11
0x180030bff  cmp     rva word_18004C070[rdx+r11*8], cx
0x180030c08  jnz     loc_180030CAF
0x180030c0e  cmp     rva word_18004C072[rdx+r11*8], ax
0x180030c17  jnz     loc_180030CAF
0x180030c1d  mov     r13, [rsp+68h+arg_10]
0x180030c25  lea     r8, aSystemroot; "%systemroot%"
0x180030c2c  mov     rcx, r13
0x180030c2f  mov     rdx, r14
0x180030c32  call    RtlStringCchCopyW
0x180030c37  mov     ebx, eax
0x180030c39  test    eax, eax
0x180030c3b  js      loc_180030DD3
0x180030c41  lea     r8, cs:180000000h
0x180030c48  mov     rdx, r14
0x180030c4b  mov     r8, rva off_18004C078[r8+r11*8]; "\\System32" ...
0x180030c53  mov     rcx, r13
0x180030c56  call    RtlStringCchCatW
0x180030c5b  mov     ebx, eax
0x180030c5d  test    eax, eax
0x180030c5f  js      loc_180030DC0
0x180030c65  mov     rcx, [rsp+68h+arg_0]
0x180030c6a  lea     rax, cs:180000000h
0x180030c71  mov     eax, [r15+rax+4C100h]
0x180030c79  mov     rdx, r14
0x180030c7c  lea     r8, [rcx+rax*2]
0x180030c80  mov     rcx, r13
0x180030c83  call    RtlStringCchCatW
0x180030c88  mov     ebx, eax
0x180030c8a  test    eax, eax
0x180030c8c  js      loc_180030DAD
0x180030c92  movzx   eax, [rsp+68h+arg_28]
0x180030c9a  lea     rdx, cs:180000000h
0x180030ca1  movzx   ecx, [rsp+68h+arg_20]
0x180030ca9  mov     r13d, 1
0x180030caf  inc     rdi
0x180030cb2  cmp     rdi, 8
0x180030cb6  jb      loc_180030BF1
0x180030cbc  test    r13d, r13d
0x180030cbf  jnz     loc_180030D62
0x180030cc5  movzx   ecx, cx
0x180030cc8  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x180030ccf  movzx   eax, ax
0x180030cd2  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x180030cd9  mov     [rsp+68h+var_40], eax
0x180030cdd  mov     r8d, 432h
0x180030ce3  mov     dword ptr [rsp+68h+var_48], ecx
0x180030ce7  lea     ecx, [r13+1]
0x180030ceb  call    AslLogCallPrintf
0x180030cf0  mov     rdi, [rsp+68h+arg_10]
0x180030cf8  jmp     short loc_180030CFF
0x180030cfa  test    r13d, r13d
0x180030cfd  jnz     short loc_180030D71
0x180030cff  lea     rax, cs:180000000h
0x180030d06  mov     rdx, r14
0x180030d09  mov     r8, [r15+rax+4C0F8h]
0x180030d11  mov     rcx, rdi
0x180030d14  call    RtlStringCchCopyW
0x180030d19  mov     ebx, eax
0x180030d1b  test    eax, eax
0x180030d1d  js      loc_180030DE6
0x180030d23  mov     rcx, [rsp+68h+arg_0]
0x180030d28  lea     rax, cs:180000000h
0x180030d2f  mov     eax, [r15+rax+4C100h]
0x180030d37  mov     rdx, r14
0x180030d3a  lea     r8, [rcx+rax*2]
0x180030d3e  mov     rcx, rdi
0x180030d41  call    RtlStringCchCatW
0x180030d46  mov     ebx, eax
0x180030d48  test    eax, eax
0x180030d4a  jns     short loc_180030D6A
0x180030d4c  mov     dword ptr [rsp+68h+var_48], eax
0x180030d50  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x180030d57  mov     r8d, 449h
0x180030d5d  jmp     loc_180030E0F
0x180030d62  mov     rdi, [rsp+68h+arg_10]
0x180030d6a  lea     r11, cs:180000000h
0x180030d71  mov     ebx, 1
0x180030d76  mov     rcx, [rsp+68h+arg_0]
0x180030d7b  inc     r12
0x180030d7e  cmp     r12, 4
0x180030d82  jb      loc_180030B6B
0x180030d88  test    ebx, ebx
0x180030d8a  jnz     loc_180030E52
0x180030d90  cmp     ebp, r14d
0x180030d93  jbe     loc_180030E29
0x180030d99  mov     rax, [rsp+68h+arg_30]
0x180030da1  mov     ebx, 0C0000023h
0x180030da6  mov     [rax], ebp
0x180030da8  jmp     loc_180030E5E
0x180030dad  mov     dword ptr [rsp+68h+var_48], eax
0x180030db1  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x180030db8  mov     r8d, 427h
0x180030dbe  jmp     short loc_180030E0F
0x180030dc0  mov     dword ptr [rsp+68h+var_48], eax
0x180030dc4  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x180030dcb  mov     r8d, 421h
0x180030dd1  jmp     short loc_180030E0F
0x180030dd3  mov     dword ptr [rsp+68h+var_48], eax
0x180030dd7  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x180030dde  mov     r8d, 41Bh
0x180030de4  jmp     short loc_180030E0F
0x180030de6  mov     dword ptr [rsp+68h+var_48], eax
0x180030dea  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x180030df1  mov     r8d, 443h
0x180030df7  jmp     short loc_180030E0F
0x180030df9  mov     ebx, 0C000000Dh
0x180030dfe  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x180030e05  mov     dword ptr [rsp+68h+var_48], ebx
0x180030e09  mov     r8d, 40Bh
0x180030e0f  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x180030e16  mov     ecx, 1
0x180030e1b  call    AslLogCallPrintf
0x180030e20  jmp     short loc_180030E5E
0x180030e22  mov     ebx, 0C0000023h
0x180030e27  jmp     short loc_180030E54
0x180030e29  mov     r8, rcx
0x180030e2c  mov     rdx, r14
0x180030e2f  mov     rcx, rdi
0x180030e32  mov     esi, ebp
0x180030e34  call    RtlStringCchCopyW
0x180030e39  mov     ebx, eax
0x180030e3b  test    eax, eax
0x180030e3d  jns     short loc_180030E52
0x180030e3f  mov     dword ptr [rsp+68h+var_48], eax
0x180030e43  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x180030e4a  mov     r8d, 469h
0x180030e50  jmp     short loc_180030E0F
0x180030e52  xor     ebx, ebx
0x180030e54  mov     rax, [rsp+68h+arg_30]
0x180030e5c  mov     [rax], esi
0x180030e5e  mov     eax, ebx
0x180030e60  mov     rbx, [rsp+68h+arg_8]
0x180030e65  add     rsp, 30h
0x180030e69  pop     r15
0x180030e6b  pop     r14
0x180030e6d  pop     r13
0x180030e6f  pop     r12
0x180030e71  pop     rdi
0x180030e72  pop     rsi
0x180030e73  pop     rbp
0x180030e74  retn
```

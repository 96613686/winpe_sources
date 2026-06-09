# AslpEnvResolveVars

- ea: `0x14005a8d4`
- end: `0x14005ac0f`
- name: `AslpEnvResolveVars`
- size: `827`
- prototype: `__int64 __fastcall(NTSTRSAFE_PCWSTR pszSrc, unsigned int, wchar_t *, unsigned int, unsigned __int16, unsigned __int16, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400327e0`

## callees

- `0x1400012f0`
- `0x1400013d0`
- `0x14000448d`
- `0x14003e364`
- `0x14005a8d4`

## string_xrefs

- `0x14005ab70`: `RtlStringCchCopyW failed [%x]`
- `0x14005ab83`: `RtlStringCchCopyW failed [%x]`
- `0x14005abdc`: `RtlStringCchCopyW failed [%x]`
- `0x14005ab97`: `ResolvedPath is NULL or zero size [%#x]`
- `0x14005aa68`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

## pseudocode

```c
__int64 __fastcall AslpEnvResolveVars(
        NTSTRSAFE_PCWSTR pszSrc,
        unsigned int a2,
        wchar_t *a3,
        unsigned int a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned int *a7)
{
  int v7; // ebx
  size_t v8; // r14
  int v9; // r13d
  unsigned int v10; // esi
  wchar_t *v11; // rdi
  __int64 v12; // r12
  __int64 v14; // r15
  unsigned int v15; // eax
  unsigned __int16 v16; // cx
  unsigned __int64 i; // rdi
  unsigned __int16 v18; // ax
  NTSTATUS v19; // eax
  __int64 v20; // r10
  unsigned int v21; // ebx
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  __int64 v25; // r11
  NTSTATUS v26; // eax
  NTSTATUS v27; // eax
  __int64 v29; // [rsp+20h] [rbp-48h]
  const wchar_t *v30; // [rsp+70h] [rbp+8h]

  v30 = pszSrc;
  v7 = 0;
  v8 = a4;
  v9 = 0;
  v10 = 0;
  v11 = a3;
  v12 = 0;
  while ( !v7 )
  {
    v14 = 3 * v12;
    v15 = qword_14001E120[3 * v12];
    if ( a2 > v15 )
    {
      if ( !wcsnicmp_0(pszSrc, off_14001E110[v14], v15) )
      {
        v10 = a2 + HIDWORD(qword_14001E120[v14]) - LODWORD(qword_14001E120[v14]);
        if ( v10 > (unsigned int)v8 )
        {
          v21 = -1073741789;
          goto LABEL_40;
        }
        if ( !v11 || !(_DWORD)v8 )
        {
          v21 = -1073741811;
          LODWORD(v29) = -1073741811;
          AslLogCallPrintf(1, "AslpEnvResolveVars", 1035, "ResolvedPath is NULL or zero size [%#x]", v29);
          return v21;
        }
        if ( v12 )
        {
          if ( !v9 )
          {
LABEL_20:
            v24 = RtlStringCchCopyW(v11, v8, (&off_14001E118)[v14]);
            v21 = v24;
            if ( v24 < 0 )
            {
              LODWORD(v29) = v24;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1091, "RtlStringCchCopyW failed [%x]", v29);
              return v21;
            }
            v26 = RtlStringCchCatW(v11, v8, &v30[*(unsigned int *)(v14 * 8 + v25 + 123168)]);
            v21 = v26;
            if ( v26 < 0 )
            {
              LODWORD(v29) = v26;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1097, "RtlStringCchCatW failed [%x]", v29);
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
            if ( word_14001E090[8 * i] == v16 && word_14001E092[8 * i] == a6 )
            {
              v19 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              v21 = v19;
              if ( v19 < 0 )
              {
                LODWORD(v29) = v19;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1051, "RtlStringCchCopyW failed [%x]", v29);
                return v21;
              }
              v22 = RtlStringCchCatW(a3, v8, (&off_14001E098)[v20]);
              v21 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v29) = v22;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1057, "RtlStringCchCatW failed [%x]", v29);
                return v21;
              }
              v23 = RtlStringCchCatW(a3, v8, &v30[LODWORD(qword_14001E120[v14])]);
              v21 = v23;
              if ( v23 < 0 )
              {
                LODWORD(v29) = v23;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1063, "RtlStringCchCatW failed [%x]", v29);
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
      pszSrc = v30;
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
        v27 = RtlStringCchCopyW(v11, v8, pszSrc);
        v21 = v27;
        if ( v27 < 0 )
        {
          LODWORD(v29) = v27;
          AslLogCallPrintf(1, "AslpEnvResolveVars", 1129, "RtlStringCchCopyW failed [%x]", v29);
          return v21;
        }
      }
      break;
    }
  }
  v21 = 0;
LABEL_40:
  *a7 = v10;
  return v21;
}

```

## disassembly

```asm
0x14005a8d4  mov     [rsp+arg_8], rbx
0x14005a8d9  mov     [rsp+pszDest], r8
0x14005a8de  mov     [rsp+arg_0], rcx
0x14005a8e3  push    rbp
0x14005a8e4  push    rsi
0x14005a8e5  push    rdi
0x14005a8e6  push    r12
0x14005a8e8  push    r13
0x14005a8ea  push    r14
0x14005a8ec  push    r15
0x14005a8ee  sub     rsp, 30h
0x14005a8f2  xor     ebx, ebx
0x14005a8f4  mov     r14d, r9d
0x14005a8f7  xor     r13d, r13d
0x14005a8fa  lea     r10, cs:140000000h
0x14005a901  xor     esi, esi
0x14005a903  mov     rdi, r8
0x14005a906  xor     r12d, r12d
0x14005a909  mov     ebp, edx
0x14005a90b  test    ebx, ebx
0x14005a90d  jnz     loc_14005ABEB
0x14005a913  lea     r15, [r12+r12*2]
0x14005a917  shl     r15, 3
0x14005a91b  mov     eax, [r15+r10+1E120h]
0x14005a923  cmp     ebp, eax
0x14005a925  jbe     loc_14005AB14
0x14005a92b  mov     rdx, [r15+r10+1E110h]; Str2
0x14005a933  mov     r8d, eax; MaxCount
0x14005a936  call    _wcsnicmp_0
0x14005a93b  lea     r10, cs:140000000h
0x14005a942  test    eax, eax
0x14005a944  jnz     loc_14005AB0F
0x14005a94a  mov     esi, [r15+r10+1E124h]
0x14005a952  sub     esi, [r15+r10+1E120h]
0x14005a95a  add     esi, ebp
0x14005a95c  cmp     esi, r14d
0x14005a95f  ja      loc_14005ABBB
0x14005a965  test    rdi, rdi
0x14005a968  jz      loc_14005AB92
0x14005a96e  test    r14d, r14d
0x14005a971  jz      loc_14005AB92
0x14005a977  test    r12, r12
0x14005a97a  jnz     loc_14005AA9A
0x14005a980  movzx   ecx, [rsp+68h+arg_20]
0x14005a988  lea     rdx, cs:140000000h
0x14005a98f  xor     edi, edi
0x14005a991  movzx   eax, [rsp+68h+arg_28]
0x14005a999  mov     r10, rdi
0x14005a99c  add     r10, r10
0x14005a99f  cmp     rva word_14001E090[rdx+r10*8], cx
0x14005a9a8  jnz     loc_14005AA4F
0x14005a9ae  cmp     rva word_14001E092[rdx+r10*8], ax
0x14005a9b7  jnz     loc_14005AA4F
0x14005a9bd  mov     r13, [rsp+68h+pszDest]
0x14005a9c5  lea     r8, aSystemroot_0; "%systemroot%"
0x14005a9cc  mov     rcx, r13; pszDest
0x14005a9cf  mov     rdx, r14; cchDest
0x14005a9d2  call    RtlStringCchCopyW
0x14005a9d7  mov     ebx, eax
0x14005a9d9  test    eax, eax
0x14005a9db  js      loc_14005AB6C
0x14005a9e1  lea     r8, cs:140000000h
0x14005a9e8  mov     rdx, r14; cchDest
0x14005a9eb  mov     r8, rva off_14001E098[r8+r10*8]; pszSrc
0x14005a9f3  mov     rcx, r13; pszDest
0x14005a9f6  call    RtlStringCchCatW
0x14005a9fb  mov     ebx, eax
0x14005a9fd  test    eax, eax
0x14005a9ff  js      loc_14005AB59
0x14005aa05  mov     rcx, [rsp+68h+arg_0]
0x14005aa0a  lea     rax, cs:140000000h
0x14005aa11  mov     eax, [r15+rax+1E120h]
0x14005aa19  mov     rdx, r14; cchDest
0x14005aa1c  lea     r8, [rcx+rax*2]; pszSrc
0x14005aa20  mov     rcx, r13; pszDest
0x14005aa23  call    RtlStringCchCatW
0x14005aa28  mov     ebx, eax
0x14005aa2a  test    eax, eax
0x14005aa2c  js      loc_14005AB46
0x14005aa32  movzx   eax, [rsp+68h+arg_28]
0x14005aa3a  lea     rdx, cs:140000000h
0x14005aa41  movzx   ecx, [rsp+68h+arg_20]
0x14005aa49  mov     r13d, 1
0x14005aa4f  inc     rdi
0x14005aa52  cmp     rdi, 8
0x14005aa56  jb      loc_14005A991
0x14005aa5c  test    r13d, r13d
0x14005aa5f  jnz     loc_14005AAFB
0x14005aa65  movzx   ecx, cx
0x14005aa68  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x14005aa6f  movzx   eax, ax
0x14005aa72  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x14005aa79  mov     [rsp+68h+var_40], eax
0x14005aa7d  mov     r8d, 432h
0x14005aa83  mov     dword ptr [rsp+68h+var_48], ecx
0x14005aa87  lea     ecx, [r13+1]
0x14005aa8b  call    AslLogCallPrintf
0x14005aa90  mov     rdi, [rsp+68h+pszDest]
0x14005aa98  jmp     short loc_14005AA9F
0x14005aa9a  test    r13d, r13d
0x14005aa9d  jnz     short loc_14005AB0A
0x14005aa9f  lea     r11, cs:140000000h
0x14005aaa6  mov     rdx, r14; cchDest
0x14005aaa9  mov     r8, [r15+r11+1E118h]; pszSrc
0x14005aab1  mov     rcx, rdi; pszDest
0x14005aab4  call    RtlStringCchCopyW
0x14005aab9  mov     ebx, eax
0x14005aabb  test    eax, eax
0x14005aabd  js      loc_14005AB7F
0x14005aac3  mov     eax, [r15+r11+1E120h]
0x14005aacb  mov     rdx, r14; cchDest
0x14005aace  mov     rcx, [rsp+68h+arg_0]
0x14005aad3  lea     r8, [rcx+rax*2]; pszSrc
0x14005aad7  mov     rcx, rdi; pszDest
0x14005aada  call    RtlStringCchCatW
0x14005aadf  mov     ebx, eax
0x14005aae1  test    eax, eax
0x14005aae3  jns     short loc_14005AB03
0x14005aae5  mov     dword ptr [rsp+68h+var_48], eax
0x14005aae9  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14005aaf0  mov     r8d, 449h
0x14005aaf6  jmp     loc_14005ABA8
0x14005aafb  mov     rdi, [rsp+68h+pszDest]
0x14005ab03  lea     r10, cs:140000000h
0x14005ab0a  mov     ebx, 1
0x14005ab0f  mov     rcx, [rsp+68h+arg_0]
0x14005ab14  inc     r12
0x14005ab17  cmp     r12, 4
0x14005ab1b  jb      loc_14005A90B
0x14005ab21  test    ebx, ebx
0x14005ab23  jnz     loc_14005ABEB
0x14005ab29  cmp     ebp, r14d
0x14005ab2c  jbe     loc_14005ABC2
0x14005ab32  mov     rax, [rsp+68h+arg_30]
0x14005ab3a  mov     ebx, 0C0000023h
0x14005ab3f  mov     [rax], ebp
0x14005ab41  jmp     loc_14005ABF7
0x14005ab46  mov     dword ptr [rsp+68h+var_48], eax
0x14005ab4a  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14005ab51  mov     r8d, 427h
0x14005ab57  jmp     short loc_14005ABA8
0x14005ab59  mov     dword ptr [rsp+68h+var_48], eax
0x14005ab5d  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x14005ab64  mov     r8d, 421h
0x14005ab6a  jmp     short loc_14005ABA8
0x14005ab6c  mov     dword ptr [rsp+68h+var_48], eax
0x14005ab70  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14005ab77  mov     r8d, 41Bh
0x14005ab7d  jmp     short loc_14005ABA8
0x14005ab7f  mov     dword ptr [rsp+68h+var_48], eax
0x14005ab83  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14005ab8a  mov     r8d, 443h
0x14005ab90  jmp     short loc_14005ABA8
0x14005ab92  mov     ebx, 0C000000Dh
0x14005ab97  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x14005ab9e  mov     dword ptr [rsp+68h+var_48], ebx
0x14005aba2  mov     r8d, 40Bh
0x14005aba8  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x14005abaf  mov     ecx, 1
0x14005abb4  call    AslLogCallPrintf
0x14005abb9  jmp     short loc_14005ABF7
0x14005abbb  mov     ebx, 0C0000023h
0x14005abc0  jmp     short loc_14005ABED
0x14005abc2  mov     r8, rcx; pszSrc
0x14005abc5  mov     rdx, r14; cchDest
0x14005abc8  mov     rcx, rdi; pszDest
0x14005abcb  mov     esi, ebp
0x14005abcd  call    RtlStringCchCopyW
0x14005abd2  mov     ebx, eax
0x14005abd4  test    eax, eax
0x14005abd6  jns     short loc_14005ABEB
0x14005abd8  mov     dword ptr [rsp+68h+var_48], eax
0x14005abdc  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14005abe3  mov     r8d, 469h
0x14005abe9  jmp     short loc_14005ABA8
0x14005abeb  xor     ebx, ebx
0x14005abed  mov     rax, [rsp+68h+arg_30]
0x14005abf5  mov     [rax], esi
0x14005abf7  mov     eax, ebx
0x14005abf9  mov     rbx, [rsp+68h+arg_8]
0x14005abfe  add     rsp, 30h
0x14005ac02  pop     r15
0x14005ac04  pop     r14
0x14005ac06  pop     r13
0x14005ac08  pop     r12
0x14005ac0a  pop     rdi
0x14005ac0b  pop     rsi
0x14005ac0c  pop     rbp
0x14005ac0d  retn
```

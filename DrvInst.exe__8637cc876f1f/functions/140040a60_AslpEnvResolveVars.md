# AslpEnvResolveVars

- ea: `0x140040a60`
- end: `0x140040da2`
- name: `AslpEnvResolveVars`
- size: `834`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, __int64, unsigned int, unsigned __int16, unsigned __int16, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140040298`

## callees

- `0x14002fdc0`
- `0x14002fea8`
- `0x14003bf18`
- `0x140040a60`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140040ac2`
- `msvcrt!_wcsnicmp` at `0x140040ac2`

## string_xrefs

- `0x140040d04`: `RtlStringCchCopyW failed [%x]`
- `0x140040d17`: `RtlStringCchCopyW failed [%x]`
- `0x140040d70`: `RtlStringCchCopyW failed [%x]`
- `0x140040d2b`: `ResolvedPath is NULL or zero size [%#x]`
- `0x140040bf5`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

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
    v15 = qword_1400631A0[3 * v12];
    if ( a2 > v15 )
    {
      if ( !_wcsnicmp(a1, off_140063190[v14], v15) )
      {
        v10 = a2 + HIDWORD(qword_1400631A0[v14]) - LODWORD(qword_1400631A0[v14]);
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
            v24 = RtlStringCchCopyW(v11, v8, (&off_140063198)[v14]);
            v21 = v24;
            if ( v24 < 0 )
            {
              LODWORD(v28) = v24;
              AslLogCallPrintf(1, "AslpEnvResolveVars", 1091, "RtlStringCchCopyW failed [%x]", v28);
              return v21;
            }
            v25 = RtlStringCchCatW(v11, v8, &v29[LODWORD(qword_1400631A0[v14])]);
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
            if ( word_140063110[8 * i] == v16 && word_140063112[8 * i] == a6 )
            {
              v19 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
              v21 = v19;
              if ( v19 < 0 )
              {
                LODWORD(v28) = v19;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1051, "RtlStringCchCopyW failed [%x]", v28);
                return v21;
              }
              v22 = RtlStringCchCatW(a3, v8, (&off_140063118)[v20]);
              v21 = v22;
              if ( v22 < 0 )
              {
                LODWORD(v28) = v22;
                AslLogCallPrintf(1, "AslpEnvResolveVars", 1057, "RtlStringCchCatW failed [%x]", v28);
                return v21;
              }
              v23 = RtlStringCchCatW(a3, v8, &v29[LODWORD(qword_1400631A0[v14])]);
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
0x140040a60  mov     [rsp+arg_8], rbx
0x140040a65  mov     [rsp+arg_10], r8
0x140040a6a  mov     [rsp+arg_0], rcx
0x140040a6f  push    rbp
0x140040a70  push    rsi
0x140040a71  push    rdi
0x140040a72  push    r12
0x140040a74  push    r13
0x140040a76  push    r14
0x140040a78  push    r15
0x140040a7a  sub     rsp, 30h
0x140040a7e  xor     ebx, ebx
0x140040a80  mov     r14d, r9d
0x140040a83  xor     r13d, r13d
0x140040a86  lea     r11, __ImageBase
0x140040a8d  xor     esi, esi
0x140040a8f  mov     rdi, r8
0x140040a92  xor     r12d, r12d
0x140040a95  mov     ebp, edx
0x140040a97  test    ebx, ebx
0x140040a99  jnz     loc_140040D7F
0x140040a9f  lea     r15, [r12+r12*2]
0x140040aa3  shl     r15, 3
0x140040aa7  mov     eax, [r15+r11+631A0h]
0x140040aaf  cmp     ebp, eax
0x140040ab1  jbe     loc_140040CA8
0x140040ab7  mov     rdx, [r15+r11+63190h]; String2
0x140040abf  mov     r8d, eax; MaxCount
0x140040ac2  call    cs:__imp__wcsnicmp
0x140040ac8  lea     r11, __ImageBase
0x140040acf  test    eax, eax
0x140040ad1  jnz     loc_140040CA3
0x140040ad7  mov     esi, [r15+r11+631A4h]
0x140040adf  sub     esi, [r15+r11+631A0h]
0x140040ae7  add     esi, ebp
0x140040ae9  cmp     esi, r14d
0x140040aec  ja      loc_140040D4F
0x140040af2  test    rdi, rdi
0x140040af5  jz      loc_140040D26
0x140040afb  test    r14d, r14d
0x140040afe  jz      loc_140040D26
0x140040b04  test    r12, r12
0x140040b07  jnz     loc_140040C27
0x140040b0d  movzx   ecx, [rsp+68h+arg_20]
0x140040b15  lea     rdx, __ImageBase
0x140040b1c  xor     edi, edi
0x140040b1e  movzx   eax, [rsp+68h+arg_28]
0x140040b26  mov     r11, rdi
0x140040b29  add     r11, r11
0x140040b2c  cmp     rva word_140063110[rdx+r11*8], cx
0x140040b35  jnz     loc_140040BDC
0x140040b3b  cmp     rva word_140063112[rdx+r11*8], ax
0x140040b44  jnz     loc_140040BDC
0x140040b4a  mov     r13, [rsp+68h+arg_10]
0x140040b52  lea     r8, aSystemroot; "%systemroot%"
0x140040b59  mov     rcx, r13
0x140040b5c  mov     rdx, r14
0x140040b5f  call    RtlStringCchCopyW
0x140040b64  mov     ebx, eax
0x140040b66  test    eax, eax
0x140040b68  js      loc_140040D00
0x140040b6e  lea     r8, __ImageBase
0x140040b75  mov     rdx, r14
0x140040b78  mov     r8, rva off_140063118[r8+r11*8]; "\\System32" ...
0x140040b80  mov     rcx, r13
0x140040b83  call    RtlStringCchCatW
0x140040b88  mov     ebx, eax
0x140040b8a  test    eax, eax
0x140040b8c  js      loc_140040CED
0x140040b92  mov     rcx, [rsp+68h+arg_0]
0x140040b97  lea     rax, __ImageBase
0x140040b9e  mov     eax, [r15+rax+631A0h]
0x140040ba6  mov     rdx, r14
0x140040ba9  lea     r8, [rcx+rax*2]
0x140040bad  mov     rcx, r13
0x140040bb0  call    RtlStringCchCatW
0x140040bb5  mov     ebx, eax
0x140040bb7  test    eax, eax
0x140040bb9  js      loc_140040CDA
0x140040bbf  movzx   eax, [rsp+68h+arg_28]
0x140040bc7  lea     rdx, __ImageBase
0x140040bce  movzx   ecx, [rsp+68h+arg_20]
0x140040bd6  mov     r13d, 1
0x140040bdc  inc     rdi
0x140040bdf  cmp     rdi, 8
0x140040be3  jb      loc_140040B1E
0x140040be9  test    r13d, r13d
0x140040bec  jnz     loc_140040C8F
0x140040bf2  movzx   ecx, cx
0x140040bf5  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x140040bfc  movzx   eax, ax
0x140040bff  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x140040c06  mov     [rsp+68h+var_40], eax
0x140040c0a  mov     r8d, 432h
0x140040c10  mov     dword ptr [rsp+68h+var_48], ecx
0x140040c14  lea     ecx, [r13+1]
0x140040c18  call    AslLogCallPrintf
0x140040c1d  mov     rdi, [rsp+68h+arg_10]
0x140040c25  jmp     short loc_140040C2C
0x140040c27  test    r13d, r13d
0x140040c2a  jnz     short loc_140040C9E
0x140040c2c  lea     rax, __ImageBase
0x140040c33  mov     rdx, r14
0x140040c36  mov     r8, [r15+rax+63198h]
0x140040c3e  mov     rcx, rdi
0x140040c41  call    RtlStringCchCopyW
0x140040c46  mov     ebx, eax
0x140040c48  test    eax, eax
0x140040c4a  js      loc_140040D13
0x140040c50  mov     rcx, [rsp+68h+arg_0]
0x140040c55  lea     rax, __ImageBase
0x140040c5c  mov     eax, [r15+rax+631A0h]
0x140040c64  mov     rdx, r14
0x140040c67  lea     r8, [rcx+rax*2]
0x140040c6b  mov     rcx, rdi
0x140040c6e  call    RtlStringCchCatW
0x140040c73  mov     ebx, eax
0x140040c75  test    eax, eax
0x140040c77  jns     short loc_140040C97
0x140040c79  mov     dword ptr [rsp+68h+var_48], eax
0x140040c7d  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x140040c84  mov     r8d, 449h
0x140040c8a  jmp     loc_140040D3C
0x140040c8f  mov     rdi, [rsp+68h+arg_10]
0x140040c97  lea     r11, __ImageBase
0x140040c9e  mov     ebx, 1
0x140040ca3  mov     rcx, [rsp+68h+arg_0]
0x140040ca8  inc     r12
0x140040cab  cmp     r12, 4
0x140040caf  jb      loc_140040A97
0x140040cb5  test    ebx, ebx
0x140040cb7  jnz     loc_140040D7F
0x140040cbd  cmp     ebp, r14d
0x140040cc0  jbe     loc_140040D56
0x140040cc6  mov     rax, [rsp+68h+arg_30]
0x140040cce  mov     ebx, 0C0000023h
0x140040cd3  mov     [rax], ebp
0x140040cd5  jmp     loc_140040D8B
0x140040cda  mov     dword ptr [rsp+68h+var_48], eax
0x140040cde  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x140040ce5  mov     r8d, 427h
0x140040ceb  jmp     short loc_140040D3C
0x140040ced  mov     dword ptr [rsp+68h+var_48], eax
0x140040cf1  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x140040cf8  mov     r8d, 421h
0x140040cfe  jmp     short loc_140040D3C
0x140040d00  mov     dword ptr [rsp+68h+var_48], eax
0x140040d04  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140040d0b  mov     r8d, 41Bh
0x140040d11  jmp     short loc_140040D3C
0x140040d13  mov     dword ptr [rsp+68h+var_48], eax
0x140040d17  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140040d1e  mov     r8d, 443h
0x140040d24  jmp     short loc_140040D3C
0x140040d26  mov     ebx, 0C000000Dh
0x140040d2b  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x140040d32  mov     dword ptr [rsp+68h+var_48], ebx
0x140040d36  mov     r8d, 40Bh
0x140040d3c  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x140040d43  mov     ecx, 1
0x140040d48  call    AslLogCallPrintf
0x140040d4d  jmp     short loc_140040D8B
0x140040d4f  mov     ebx, 0C0000023h
0x140040d54  jmp     short loc_140040D81
0x140040d56  mov     r8, rcx
0x140040d59  mov     rdx, r14
0x140040d5c  mov     rcx, rdi
0x140040d5f  mov     esi, ebp
0x140040d61  call    RtlStringCchCopyW
0x140040d66  mov     ebx, eax
0x140040d68  test    eax, eax
0x140040d6a  jns     short loc_140040D7F
0x140040d6c  mov     dword ptr [rsp+68h+var_48], eax
0x140040d70  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x140040d77  mov     r8d, 469h
0x140040d7d  jmp     short loc_140040D3C
0x140040d7f  xor     ebx, ebx
0x140040d81  mov     rax, [rsp+68h+arg_30]
0x140040d89  mov     [rax], esi
0x140040d8b  mov     eax, ebx
0x140040d8d  mov     rbx, [rsp+68h+arg_8]
0x140040d92  add     rsp, 30h
0x140040d96  pop     r15
0x140040d98  pop     r14
0x140040d9a  pop     r13
0x140040d9c  pop     r12
0x140040d9e  pop     rdi
0x140040d9f  pop     rsi
0x140040da0  pop     rbp
0x140040da1  retn
```

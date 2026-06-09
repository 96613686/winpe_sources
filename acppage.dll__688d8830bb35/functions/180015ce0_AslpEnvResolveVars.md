# AslpEnvResolveVars

- ea: `0x180015ce0`
- end: `0x180016021`
- name: `AslpEnvResolveVars`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014d54`

## callees

- `0x180001f7e`
- `0x180015220`
- `0x180015ce0`
- `0x180016028`
- `0x1800160ec`

## string_xrefs

- `0x180015f83`: `RtlStringCchCopyW failed [%x]`
- `0x180015f96`: `RtlStringCchCopyW failed [%x]`
- `0x180015fef`: `RtlStringCchCopyW failed [%x]`
- `0x180015faa`: `ResolvedPath is NULL or zero size [%#x]`
- `0x180015e74`: `Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4`

## pseudocode

```c
__int64 __fastcall AslpEnvResolveVars(
        const wchar_t *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int16 a5,
        __int16 a6,
        unsigned int *a7)
{
  int v7; // ebx
  __int64 v8; // r14
  int v9; // r13d
  unsigned int v10; // esi
  __int64 v11; // rdi
  unsigned __int64 i; // r12
  __int64 v14; // r15
  unsigned int v15; // eax
  __int16 v16; // cx
  unsigned __int64 j; // rdi
  int v18; // ebx
  __int64 v19; // r11
  const char *v20; // r9
  __int64 v21; // r8
  const wchar_t *v23; // [rsp+70h] [rbp+8h]

  v23 = a1;
  v7 = 0;
  v8 = a4;
  v9 = 0;
  v10 = 0;
  v11 = a3;
  for ( i = 0; i < 4; ++i )
  {
    if ( v7 )
      goto LABEL_39;
    v14 = 3 * i;
    v15 = qword_180020160[3 * i];
    if ( a2 > v15 )
    {
      if ( wcsnicmp_0(a1, off_180020150[v14], v15) )
      {
LABEL_25:
        a1 = v23;
        continue;
      }
      v10 = a2 + HIDWORD(qword_180020160[v14]) - LODWORD(qword_180020160[v14]);
      if ( v10 > (unsigned int)v8 )
      {
        v18 = -1073741789;
        goto LABEL_40;
      }
      if ( !v11 || !(_DWORD)v8 )
      {
        v18 = -1073741811;
        v20 = "ResolvedPath is NULL or zero size [%#x]";
        v21 = 1035;
        goto LABEL_35;
      }
      if ( !i )
      {
        v16 = a5;
        for ( j = 0; j < 8; ++j )
        {
          if ( word_1800200D0[8 * j] == v16 && word_1800200D2[8 * j] == a6 )
          {
            v18 = RtlStringCchCopyW(a3, v8, L"%systemroot%");
            if ( v18 < 0 )
            {
              v20 = "RtlStringCchCopyW failed [%x]";
              v21 = 1051;
              goto LABEL_35;
            }
            v18 = RtlStringCchCatW(a3, v8, (&off_1800200D8)[v19]);
            if ( v18 < 0 )
            {
              v20 = "RtlStringCchCatW failed [%x]";
              v21 = 1057;
              goto LABEL_35;
            }
            v18 = RtlStringCchCatW(a3, v8, &v23[LODWORD(qword_180020160[v14])]);
            if ( v18 < 0 )
            {
              v20 = "RtlStringCchCatW failed [%x]";
              v21 = 1063;
              goto LABEL_35;
            }
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
            "Invalid combination of Host/Current processor architectures passed to AslpEnvResolveVars Host: %x4 Current: %x4");
          v11 = a3;
          goto LABEL_20;
        }
        v11 = a3;
        goto LABEL_24;
      }
      if ( !v9 )
      {
LABEL_20:
        v18 = RtlStringCchCopyW(v11, v8, (&off_180020158)[v14]);
        if ( v18 < 0 )
        {
          v20 = "RtlStringCchCopyW failed [%x]";
          v21 = 1091;
          goto LABEL_35;
        }
        v18 = RtlStringCchCatW(v11, v8, &v23[LODWORD(qword_180020160[v14])]);
        if ( v18 < 0 )
        {
          v20 = "RtlStringCchCatW failed [%x]";
          v21 = 1097;
LABEL_35:
          AslLogCallPrintf(1, "AslpEnvResolveVars", v21, v20);
          return (unsigned int)v18;
        }
      }
LABEL_24:
      v7 = 1;
      goto LABEL_25;
    }
  }
  if ( !v7 )
  {
    if ( a2 > (unsigned int)v8 )
    {
      v18 = -1073741789;
      *a7 = a2;
      return (unsigned int)v18;
    }
    v10 = a2;
    v18 = RtlStringCchCopyW(v11, v8, a1);
    if ( v18 < 0 )
    {
      v20 = "RtlStringCchCopyW failed [%x]";
      v21 = 1129;
      goto LABEL_35;
    }
  }
LABEL_39:
  v18 = 0;
LABEL_40:
  *a7 = v10;
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180015ce0  mov     [rsp+arg_8], rbx
0x180015ce5  mov     [rsp+arg_10], r8
0x180015cea  mov     [rsp+arg_0], rcx
0x180015cef  push    rbp
0x180015cf0  push    rsi
0x180015cf1  push    rdi
0x180015cf2  push    r12
0x180015cf4  push    r13
0x180015cf6  push    r14
0x180015cf8  push    r15
0x180015cfa  sub     rsp, 30h
0x180015cfe  xor     ebx, ebx
0x180015d00  mov     r14d, r9d
0x180015d03  xor     r13d, r13d
0x180015d06  lea     r11, __ImageBase
0x180015d0d  xor     esi, esi
0x180015d0f  mov     rdi, r8
0x180015d12  xor     r12d, r12d
0x180015d15  mov     ebp, edx
0x180015d17  test    ebx, ebx
0x180015d19  jnz     loc_180015FFE
0x180015d1f  lea     r15, [r12+r12*2]
0x180015d23  shl     r15, 3
0x180015d27  mov     eax, [r15+r11+20160h]
0x180015d2f  cmp     ebp, eax
0x180015d31  jbe     loc_180015F27
0x180015d37  mov     rdx, [r15+r11+20150h]; String2
0x180015d3f  mov     r8d, eax; MaxCount
0x180015d42  call    _wcsnicmp_0
0x180015d47  lea     r11, __ImageBase
0x180015d4e  test    eax, eax
0x180015d50  jnz     loc_180015F22
0x180015d56  mov     esi, [r15+r11+20164h]
0x180015d5e  sub     esi, [r15+r11+20160h]
0x180015d66  add     esi, ebp
0x180015d68  cmp     esi, r14d
0x180015d6b  ja      loc_180015FCE
0x180015d71  test    rdi, rdi
0x180015d74  jz      loc_180015FA5
0x180015d7a  test    r14d, r14d
0x180015d7d  jz      loc_180015FA5
0x180015d83  test    r12, r12
0x180015d86  jnz     loc_180015EA6
0x180015d8c  movzx   ecx, [rsp+68h+arg_20]
0x180015d94  lea     rdx, __ImageBase
0x180015d9b  xor     edi, edi
0x180015d9d  movzx   eax, [rsp+68h+arg_28]
0x180015da5  mov     r11, rdi
0x180015da8  add     r11, r11
0x180015dab  cmp     rva word_1800200D0[rdx+r11*8], cx
0x180015db4  jnz     loc_180015E5B
0x180015dba  cmp     rva word_1800200D2[rdx+r11*8], ax
0x180015dc3  jnz     loc_180015E5B
0x180015dc9  mov     r13, [rsp+68h+arg_10]
0x180015dd1  lea     r8, aSystemroot; "%systemroot%"
0x180015dd8  mov     rcx, r13
0x180015ddb  mov     rdx, r14
0x180015dde  call    RtlStringCchCopyW
0x180015de3  mov     ebx, eax
0x180015de5  test    eax, eax
0x180015de7  js      loc_180015F7F
0x180015ded  lea     r8, __ImageBase
0x180015df4  mov     rdx, r14
0x180015df7  mov     r8, rva off_1800200D8[r8+r11*8]; "\\System32" ...
0x180015dff  mov     rcx, r13
0x180015e02  call    RtlStringCchCatW
0x180015e07  mov     ebx, eax
0x180015e09  test    eax, eax
0x180015e0b  js      loc_180015F6C
0x180015e11  mov     rcx, [rsp+68h+arg_0]
0x180015e16  lea     rax, __ImageBase
0x180015e1d  mov     eax, [r15+rax+20160h]
0x180015e25  mov     rdx, r14
0x180015e28  lea     r8, [rcx+rax*2]
0x180015e2c  mov     rcx, r13
0x180015e2f  call    RtlStringCchCatW
0x180015e34  mov     ebx, eax
0x180015e36  test    eax, eax
0x180015e38  js      loc_180015F59
0x180015e3e  movzx   eax, [rsp+68h+arg_28]
0x180015e46  lea     rdx, __ImageBase
0x180015e4d  movzx   ecx, [rsp+68h+arg_20]
0x180015e55  mov     r13d, 1
0x180015e5b  inc     rdi
0x180015e5e  cmp     rdi, 8
0x180015e62  jb      loc_180015D9D
0x180015e68  test    r13d, r13d
0x180015e6b  jnz     loc_180015F0E
0x180015e71  movzx   ecx, cx
0x180015e74  lea     r9, aInvalidCombina; "Invalid combination of Host/Current pro"...
0x180015e7b  movzx   eax, ax
0x180015e7e  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x180015e85  mov     [rsp+68h+var_40], eax
0x180015e89  mov     r8d, 432h
0x180015e8f  mov     [rsp+68h+var_48], ecx
0x180015e93  lea     ecx, [r13+1]
0x180015e97  call    AslLogCallPrintf
0x180015e9c  mov     rdi, [rsp+68h+arg_10]
0x180015ea4  jmp     short loc_180015EAB
0x180015ea6  test    r13d, r13d
0x180015ea9  jnz     short loc_180015F1D
0x180015eab  lea     rax, __ImageBase
0x180015eb2  mov     rdx, r14
0x180015eb5  mov     r8, [r15+rax+20158h]
0x180015ebd  mov     rcx, rdi
0x180015ec0  call    RtlStringCchCopyW
0x180015ec5  mov     ebx, eax
0x180015ec7  test    eax, eax
0x180015ec9  js      loc_180015F92
0x180015ecf  mov     rcx, [rsp+68h+arg_0]
0x180015ed4  lea     rax, __ImageBase
0x180015edb  mov     eax, [r15+rax+20160h]
0x180015ee3  mov     rdx, r14
0x180015ee6  lea     r8, [rcx+rax*2]
0x180015eea  mov     rcx, rdi
0x180015eed  call    RtlStringCchCatW
0x180015ef2  mov     ebx, eax
0x180015ef4  test    eax, eax
0x180015ef6  jns     short loc_180015F16
0x180015ef8  mov     [rsp+68h+var_48], eax
0x180015efc  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x180015f03  mov     r8d, 449h
0x180015f09  jmp     loc_180015FBB
0x180015f0e  mov     rdi, [rsp+68h+arg_10]
0x180015f16  lea     r11, __ImageBase
0x180015f1d  mov     ebx, 1
0x180015f22  mov     rcx, [rsp+68h+arg_0]
0x180015f27  inc     r12
0x180015f2a  cmp     r12, 4
0x180015f2e  jb      loc_180015D17
0x180015f34  test    ebx, ebx
0x180015f36  jnz     loc_180015FFE
0x180015f3c  cmp     ebp, r14d
0x180015f3f  jbe     loc_180015FD5
0x180015f45  mov     rax, [rsp+68h+arg_30]
0x180015f4d  mov     ebx, 0C0000023h
0x180015f52  mov     [rax], ebp
0x180015f54  jmp     loc_18001600A
0x180015f59  mov     [rsp+68h+var_48], eax
0x180015f5d  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x180015f64  mov     r8d, 427h
0x180015f6a  jmp     short loc_180015FBB
0x180015f6c  mov     [rsp+68h+var_48], eax
0x180015f70  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x180015f77  mov     r8d, 421h
0x180015f7d  jmp     short loc_180015FBB
0x180015f7f  mov     [rsp+68h+var_48], eax
0x180015f83  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x180015f8a  mov     r8d, 41Bh
0x180015f90  jmp     short loc_180015FBB
0x180015f92  mov     [rsp+68h+var_48], eax
0x180015f96  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x180015f9d  mov     r8d, 443h
0x180015fa3  jmp     short loc_180015FBB
0x180015fa5  mov     ebx, 0C000000Dh
0x180015faa  lea     r9, aResolvedpathIs; "ResolvedPath is NULL or zero size [%#x]"
0x180015fb1  mov     [rsp+68h+var_48], ebx
0x180015fb5  mov     r8d, 40Bh
0x180015fbb  lea     rdx, aAslpenvresolve; "AslpEnvResolveVars"
0x180015fc2  mov     ecx, 1
0x180015fc7  call    AslLogCallPrintf
0x180015fcc  jmp     short loc_18001600A
0x180015fce  mov     ebx, 0C0000023h
0x180015fd3  jmp     short loc_180016000
0x180015fd5  mov     r8, rcx
0x180015fd8  mov     rdx, r14
0x180015fdb  mov     rcx, rdi
0x180015fde  mov     esi, ebp
0x180015fe0  call    RtlStringCchCopyW
0x180015fe5  mov     ebx, eax
0x180015fe7  test    eax, eax
0x180015fe9  jns     short loc_180015FFE
0x180015feb  mov     [rsp+68h+var_48], eax
0x180015fef  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x180015ff6  mov     r8d, 469h
0x180015ffc  jmp     short loc_180015FBB
0x180015ffe  xor     ebx, ebx
0x180016000  mov     rax, [rsp+68h+arg_30]
0x180016008  mov     [rax], esi
0x18001600a  mov     eax, ebx
0x18001600c  mov     rbx, [rsp+68h+arg_8]
0x180016011  add     rsp, 30h
0x180016015  pop     r15
0x180016017  pop     r14
0x180016019  pop     r13
0x18001601b  pop     r12
0x18001601d  pop     rdi
0x18001601e  pop     rsi
0x18001601f  pop     rbp
0x180016020  retn
```

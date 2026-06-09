# ReadField(HKEY__ *,tagFieldInfo const &,tagPROPVARIANT &)

- ea: `0x180008ab0`
- end: `0x180008fb4`
- name: `?ReadField@@YAJPEAUHKEY__@@AEBUtagFieldInfo@@AEAUtagPROPVARIANT@@@Z`
- size: `1284`
- prototype: `__int64 __fastcall(HKEY hKey, const struct tagFieldInfo *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008a30`

## callees

- `0x180008ab0`
- `0x180008fbc`
- `0x1800434ba`
- `0x1800434c6`
- `0x180043510`
- `0x1800435a0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008b10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008daa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008b10`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008daa`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008c57`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008df8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008c57`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180008df8`
- `OLEAUT32!__imp_SysAllocString` at `0x180008be4`
- `OLEAUT32!__imp_SysAllocString` at `0x180008e63`
- `OLEAUT32!__imp_SysAllocString` at `0x180008be4`
- `OLEAUT32!__imp_SysAllocString` at `0x180008e63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008ed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008ed2`

## pseudocode

```c
__int64 __fastcall ReadField(HKEY hKey, LPCWSTR *a2, LARGE_INTEGER *a3)
{
  BYTE *lpData; // rsi
  int v7; // ebx
  unsigned __int64 v9; // rbx
  BYTE *v10; // rax
  BSTR v11; // rax
  int v12; // eax
  LONG v13; // edx
  DWORD v14; // r15d
  unsigned __int64 v15; // rbx
  DWORD *p_cbData; // rdi
  size_t v17; // r13
  unsigned __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  _DWORD *v22; // rax
  __int64 v23; // rcx
  unsigned __int64 v24; // rcx
  void *v25; // rsp
  void *v26; // rsp
  BSTR v27; // rax
  int v28; // edx
  SIZE_T v29; // rcx
  BYTE *v30; // rax
  LARGE_INTEGER *v31; // rcx
  size_t v32; // r8
  __int64 v33; // [rsp+0h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+30h] [rbp+0h] BYREF
  DWORD Type; // [rsp+34h] [rbp+4h] BYREF
  __int64 v36; // [rsp+38h] [rbp+8h] BYREF

  Type = 0;
  cbData = 0;
  *(_OWORD *)&a3->LowPart = 0;
  a3[2].QuadPart = 0;
  lpData = 0;
  v7 = RegQueryValueExW(hKey, *a2, 0, &Type, 0, &cbData);
  if ( v7 )
    goto LABEL_2;
  v9 = cbData;
  if ( !cbData
    || cbData > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)cbData + g_ulAdditionalProbeSize + 8 < cbData
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_85;
  }
  v23 = v9 + 23;
  if ( v9 + 23 <= v9 + 8 )
    v23 = 0xFFFFFFFFFFFFFF0LL;
  v24 = v23 & 0xFFFFFFFFFFFFFFF0uLL;
  v25 = alloca(v24);
  v26 = alloca(v24);
  lpData = (BYTE *)&cbData;
  if ( &v33 == (__int64 *)-48LL || (cbData = 1801679955, (lpData = (BYTE *)&v36) == 0) )
  {
LABEL_85:
    if ( v9 + 8 >= v9 )
    {
      v10 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
      lpData = v10;
      if ( v10 )
      {
        *(_DWORD *)v10 = 1885431112;
        lpData = v10 + 8;
      }
    }
  }
  if ( !lpData )
  {
    v7 = -2147024882;
    goto LABEL_5;
  }
  v7 = RegQueryValueExW(hKey, *a2, 0, &Type, lpData, &cbData);
  if ( v7 )
  {
LABEL_2:
    if ( v7 == 2 )
    {
      if ( (*((_BYTE *)a2 + 12) & 4) != 0 )
        v7 = -2147160063;
      else
        v7 = 1;
    }
    else if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
    }
LABEL_5:
    if ( !lpData )
      return (unsigned int)v7;
LABEL_18:
    if ( *((_DWORD *)lpData - 2) == 1885431112 )
      ((void (__fastcall *)(BYTE *))g_pfnFree)(lpData - 8);
    return (unsigned int)v7;
  }
  v7 = 0;
  switch ( Type )
  {
    case 1u:
      if ( ((*((_WORD *)a2 + 4) - 8) & 0xFFBF) != 0 )
      {
        v7 = -2147418113;
      }
      else
      {
        LOWORD(a3->LowPart) = 8;
        v11 = SysAllocString((const OLECHAR *)lpData);
        a3[1].QuadPart = (LONGLONG)v11;
        if ( !v11 )
          v7 = -2147024882;
      }
      goto LABEL_18;
    case 2u:
      if ( *((_WORD *)a2 + 4) != 8 )
      {
        v7 = -2147418113;
        goto LABEL_18;
      }
      v14 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
      if ( !v14 )
      {
        v7 = -2147418113;
        goto LABEL_18;
      }
      v15 = 2LL * v14;
      if ( v15 > 0xFFFFFFFF )
      {
        v7 = -2147024362;
        goto LABEL_18;
      }
      p_cbData = 0;
      if ( (_DWORD)v15 )
      {
        v17 = (unsigned int)v15;
        if ( (unsigned int)v15 <= (unsigned __int64)g_ulMaxStackAllocSize
          && (unsigned __int64)(unsigned int)v15 + g_ulAdditionalProbeSize + 8 >= (unsigned int)v15
          && (unsigned int)VerifyStackAvailable() )
        {
          v18 = (unsigned int)v15 + 23LL;
          if ( v18 <= (unsigned __int64)(unsigned int)v15 + 8 )
            v18 = 0xFFFFFFFFFFFFFF0LL;
          v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
          v20 = alloca(v19);
          v21 = alloca(v19);
          p_cbData = &cbData;
          if ( &cbData )
          {
            cbData = 1801679955;
            p_cbData = (DWORD *)&v36;
            if ( &v36 )
            {
LABEL_51:
              memset_0(p_cbData, 0, v17);
              if ( ExpandEnvironmentStringsW((LPCWSTR)lpData, (LPWSTR)p_cbData, v14) )
              {
                LOWORD(a3->LowPart) = 8;
                v27 = SysAllocString((const OLECHAR *)p_cbData);
                v7 = -2147024882;
                a3[1].QuadPart = (LONGLONG)v27;
                if ( v27 )
                  v7 = 0;
              }
              else
              {
                v7 = -2147418113;
              }
              if ( p_cbData && *(p_cbData - 2) == 1885431112 )
                ((void (__fastcall *)(DWORD *))g_pfnFree)(p_cbData - 2);
              goto LABEL_18;
            }
          }
        }
      }
      v17 = (unsigned int)v15;
      if ( (unsigned __int64)(unsigned int)v15 + 8 >= (unsigned int)v15 )
      {
        v22 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        if ( !v22 )
          goto LABEL_38;
        *v22 = 1885431112;
        p_cbData = v22 + 2;
      }
      if ( p_cbData )
        goto LABEL_51;
LABEL_38:
      v7 = -2147024882;
      goto LABEL_18;
    case 4u:
      v12 = *((unsigned __int16 *)a2 + 4);
      v13 = *(_DWORD *)lpData;
      LOWORD(a3->LowPart) = v12;
      switch ( v12 )
      {
        case 2:
        case 11:
        case 18:
          LOWORD(a3[1].LowPart) = v13;
          break;
        case 3:
        case 10:
        case 19:
        case 22:
        case 23:
          a3[1].LowPart = v13;
          break;
        case 16:
        case 17:
          LOBYTE(a3[1].LowPart) = v13;
          break;
        default:
          goto LABEL_23;
      }
      goto LABEL_18;
  }
  if ( Type != 3 )
  {
LABEL_23:
    v7 = -2147467259;
    goto LABEL_18;
  }
  v28 = *((unsigned __int16 *)a2 + 4);
  if ( (_WORD)v28 == 4113 )
  {
    LOWORD(a3->LowPart) = 4113;
    v29 = cbData;
    a3[1].LowPart = cbData;
    v30 = (BYTE *)CoTaskMemAlloc(v29);
    a3[2].QuadPart = (LONGLONG)v30;
    if ( v30 )
      memcpy_0(v30, lpData, cbData);
    else
      v7 = -2147024882;
    goto LABEL_18;
  }
  switch ( v28 )
  {
    case 4:
      v32 = 4;
      goto LABEL_80;
    case 5:
    case 6:
    case 7:
      v32 = 8;
LABEL_80:
      v31 = a3 + 1;
      goto LABEL_81;
    case 14:
      v31 = a3;
      v32 = 16;
LABEL_81:
      LOWORD(a3->LowPart) = v28;
      memcpy_0(v31, lpData, v32);
      goto LABEL_18;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180008ab0  push    rbp
0x180008ab2  push    rbx
0x180008ab3  push    rsi
0x180008ab4  push    rdi
0x180008ab5  push    r12
0x180008ab7  push    r13
0x180008ab9  push    r14
0x180008abb  push    r15
0x180008abd  sub     rsp, 58h
0x180008ac1  lea     rbp, [rsp+30h]
0x180008ac6  mov     rax, cs:__security_cookie
0x180008acd  xor     rax, rbp
0x180008ad0  mov     [rbp+60h+var_50], rax
0x180008ad4  xor     r13d, r13d
0x180008ad7  lea     r9, [rbp+60h+Type]; lpType
0x180008adb  xor     eax, eax
0x180008add  mov     [rbp+60h+Type], r13d
0x180008ae1  xorps   xmm0, xmm0
0x180008ae4  mov     [rbp+60h+cbData], r13d
0x180008ae8  movups  xmmword ptr [r8], xmm0
0x180008aec  mov     [r8+10h], rax
0x180008af0  mov     r14, r8
0x180008af3  lea     rax, [rbp+60h+cbData]
0x180008af7  mov     rdi, rdx
0x180008afa  mov     rdx, [rdx]; lpValueName
0x180008afd  xor     r8d, r8d; lpReserved
0x180008b00  mov     [rsp+90h+lpcbData], rax; lpcbData
0x180008b05  mov     r15, rcx
0x180008b08  mov     [rsp+90h+lpData], r13; lpData
0x180008b0d  mov     esi, r13d
0x180008b10  call    cs:__imp_RegQueryValueExW
0x180008b16  mov     ebx, eax
0x180008b18  test    eax, eax
0x180008b1a  jz      short loc_180008B67
0x180008b1c  cmp     ebx, 2
0x180008b1f  jnz     short loc_180008B58
0x180008b21  test    byte ptr [rdi+0Ch], 4
0x180008b25  jnz     loc_180008F52
0x180008b2b  mov     ebx, 1
0x180008b30  test    rsi, rsi
0x180008b33  jnz     loc_180008BF7
0x180008b39  mov     eax, ebx
0x180008b3b  mov     rcx, [rbp+60h+var_50]
0x180008b3f  xor     rcx, rbp; StackCookie
0x180008b42  call    __security_check_cookie
0x180008b47  lea     rsp, [rbp+28h]
0x180008b4b  pop     r15
0x180008b4d  pop     r14
0x180008b4f  pop     r13
0x180008b51  pop     r12
0x180008b53  pop     rdi
0x180008b54  pop     rsi
0x180008b55  pop     rbx
0x180008b56  pop     rbp
0x180008b57  retn
0x180008b58  test    ebx, ebx
0x180008b5a  jle     short loc_180008B30
0x180008b5c  movzx   ebx, bx
0x180008b5f  or      ebx, 80070000h
0x180008b65  jmp     short loc_180008B30
0x180008b67  mov     ebx, [rbp+60h+cbData]
0x180008b6a  test    rbx, rbx
0x180008b6d  jz      short loc_180008B7C
0x180008b6f  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180008b76  jbe     loc_180008D1F
0x180008b7c  mov     r12, 0FFFFFFFFFFFFFF0h
0x180008b86  lea     rcx, [rbx+8]
0x180008b8a  cmp     rcx, rbx
0x180008b8d  jb      loc_180008D8A
0x180008b93  mov     rax, cs:g_pfnAllocate
0x180008b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9f  mov     rsi, rax
0x180008ba2  test    rax, rax
0x180008ba5  jz      loc_180008D8A
0x180008bab  mov     dword ptr [rax], 70616548h
0x180008bb1  add     rsi, 8
0x180008bb5  jmp     loc_180008D8A
0x180008bba  mov     eax, [rbp+60h+Type]
0x180008bbd  mov     ebx, r13d
0x180008bc0  cmp     eax, 1
0x180008bc3  jnz     short loc_180008C19
0x180008bc5  movzx   eax, word ptr [rdi+8]
0x180008bc9  mov     ecx, 0FFBFh
0x180008bce  sub     ax, 8
0x180008bd2  test    cx, ax
0x180008bd5  jnz     loc_180008E32
0x180008bdb  mov     rcx, rsi; psz
0x180008bde  mov     word ptr [r14], 8
0x180008be4  call    cs:__imp_SysAllocString
0x180008bea  mov     [r14+8], rax
0x180008bee  test    rax, rax
0x180008bf1  jz      loc_180008E3C
0x180008bf7  cmp     dword ptr [rsi-8], 70616548h
0x180008bfe  lea     rcx, [rsi-8]
0x180008c02  jnz     loc_180008B39
0x180008c08  mov     rax, cs:g_pfnFree
0x180008c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c14  jmp     loc_180008B39
0x180008c19  cmp     eax, 2
0x180008c1c  jz      short loc_180008C44
0x180008c1e  cmp     eax, 4
0x180008c21  jnz     loc_180008EAE
0x180008c27  movzx   eax, word ptr [rdi+8]
0x180008c2b  mov     edx, [rsi]
0x180008c2d  mov     [r14], ax
0x180008c31  add     eax, 0FFFFFFFEh; switch 22 cases
0x180008c34  cmp     eax, 15h
0x180008c37  jbe     loc_180008E7C
0x180008c3d  mov     ebx, 80004005h; jumptable 0000000180008E90 default case, cases 4-9,12-15,20,21
0x180008c42  jmp     short loc_180008BF7
0x180008c44  cmp     word ptr [rdi+8], 8
0x180008c49  jnz     loc_180008E46
0x180008c4f  xor     r8d, r8d; nSize
0x180008c52  xor     edx, edx; lpDst
0x180008c54  mov     rcx, rsi; lpSrc
0x180008c57  call    cs:__imp_ExpandEnvironmentStringsW
0x180008c5d  mov     r15d, eax
0x180008c60  test    eax, eax
0x180008c62  jz      loc_180008E50
0x180008c68  mov     ebx, r15d
0x180008c6b  mov     eax, 0FFFFFFFFh
0x180008c70  add     rbx, rbx
0x180008c73  cmp     rbx, rax
0x180008c76  ja      loc_180008D15
0x180008c7c  mov     rdi, r13
0x180008c7f  test    ebx, ebx
0x180008c81  jz      short loc_180008CD8
0x180008c83  mov     r13d, ebx
0x180008c86  cmp     r13, cs:g_ulMaxStackAllocSize
0x180008c8d  ja      short loc_180008CD8
0x180008c8f  mov     rcx, cs:g_ulAdditionalProbeSize
0x180008c96  add     rcx, 8
0x180008c9a  add     rcx, r13
0x180008c9d  cmp     rcx, r13
0x180008ca0  jb      short loc_180008CD8
0x180008ca2  call    VerifyStackAvailable
0x180008ca7  test    eax, eax
0x180008ca9  jz      short loc_180008CD8
0x180008cab  lea     rax, [r13+8]
0x180008caf  lea     rcx, [rax+0Fh]
0x180008cb3  cmp     rcx, rax
0x180008cb6  ja      short loc_180008CBB
0x180008cb8  mov     rcx, r12
0x180008cbb  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008cbf  mov     rax, rcx
0x180008cc2  call    _alloca_probe
0x180008cc7  sub     rsp, rcx
0x180008cca  lea     rdi, [rsp+90h+cbData]
0x180008ccf  test    rdi, rdi
0x180008cd2  jnz     loc_180008DD2
0x180008cd8  mov     r13d, ebx
0x180008cdb  lea     rcx, [r13+8]
0x180008cdf  cmp     rcx, r13
0x180008ce2  jb      short loc_180008D02
0x180008ce4  mov     rax, cs:g_pfnAllocate
0x180008ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cf0  mov     rdi, rax
0x180008cf3  test    rax, rax
0x180008cf6  jz      short loc_180008D0B
0x180008cf8  mov     dword ptr [rax], 70616548h
0x180008cfe  add     rdi, 8
0x180008d02  test    rdi, rdi
0x180008d05  jnz     loc_180008DE2
0x180008d0b  mov     ebx, 8007000Eh
0x180008d10  jmp     loc_180008BF7
0x180008d15  mov     ebx, 80070216h
0x180008d1a  jmp     loc_180008BF7
0x180008d1f  mov     rcx, cs:g_ulAdditionalProbeSize
0x180008d26  add     rcx, 8
0x180008d2a  add     rcx, rbx
0x180008d2d  cmp     rcx, rbx
0x180008d30  jb      loc_180008B7C
0x180008d36  call    VerifyStackAvailable
0x180008d3b  test    eax, eax
0x180008d3d  jz      loc_180008B7C
0x180008d43  lea     rax, [rbx+8]
0x180008d47  mov     r12, 0FFFFFFFFFFFFFF0h
0x180008d51  lea     rcx, [rax+0Fh]
0x180008d55  cmp     rcx, rax
0x180008d58  ja      short loc_180008D5D
0x180008d5a  mov     rcx, r12
0x180008d5d  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180008d61  mov     rax, rcx
0x180008d64  call    _alloca_probe
0x180008d69  sub     rsp, rcx
0x180008d6c  lea     rsi, [rsp+90h+cbData]
0x180008d71  test    rsi, rsi
0x180008d74  jz      loc_180008B86
0x180008d7a  mov     dword ptr [rsi], 6B637453h
0x180008d80  add     rsi, 8
0x180008d84  jz      loc_180008B86
0x180008d8a  test    rsi, rsi
0x180008d8d  jz      short loc_180008DBF
0x180008d8f  mov     rdx, [rdi]; lpValueName
0x180008d92  lea     rax, [rbp+60h+cbData]
0x180008d96  mov     [rsp+90h+lpcbData], rax; lpcbData
0x180008d9b  lea     r9, [rbp+60h+Type]; lpType
0x180008d9f  xor     r8d, r8d; lpReserved
0x180008da2  mov     [rsp+90h+lpData], rsi; lpData
0x180008da7  mov     rcx, r15; hKey
0x180008daa  call    cs:__imp_RegQueryValueExW
0x180008db0  mov     ebx, eax
0x180008db2  test    eax, eax
0x180008db4  jnz     loc_180008B1C
0x180008dba  jmp     loc_180008BBA
0x180008dbf  mov     ebx, 0Eh
0x180008dc4  movzx   ebx, bx
0x180008dc7  or      ebx, 80070000h
0x180008dcd  jmp     loc_180008B30
0x180008dd2  mov     dword ptr [rdi], 6B637453h
0x180008dd8  add     rdi, 8
0x180008ddc  jz      loc_180008CD8
0x180008de2  mov     r8, r13; Size
0x180008de5  xor     edx, edx; Val
0x180008de7  mov     rcx, rdi; void *
0x180008dea  call    memset_0
0x180008def  mov     r8d, r15d; nSize
0x180008df2  mov     rdx, rdi; lpDst
0x180008df5  mov     rcx, rsi; lpSrc
0x180008df8  call    cs:__imp_ExpandEnvironmentStringsW
0x180008dfe  test    eax, eax
0x180008e00  jnz     short loc_180008E5A
0x180008e02  mov     ebx, 8000FFFFh
0x180008e07  test    rdi, rdi
0x180008e0a  jz      loc_180008BF7
0x180008e10  cmp     dword ptr [rdi-8], 70616548h
0x180008e17  lea     rcx, [rdi-8]
0x180008e1b  jnz     loc_180008BF7
0x180008e21  mov     rax, cs:g_pfnFree
0x180008e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e2d  jmp     loc_180008BF7
0x180008e32  mov     ebx, 8000FFFFh
0x180008e37  jmp     loc_180008BF7
0x180008e3c  mov     ebx, 8007000Eh
0x180008e41  jmp     loc_180008BF7
0x180008e46  mov     ebx, 8000FFFFh
0x180008e4b  jmp     loc_180008BF7
0x180008e50  mov     ebx, 8000FFFFh
0x180008e55  jmp     loc_180008BF7
0x180008e5a  mov     rcx, rdi; psz
0x180008e5d  mov     word ptr [r14], 8
0x180008e63  call    cs:__imp_SysAllocString
0x180008e69  xor     ecx, ecx
0x180008e6b  mov     ebx, 8007000Eh
0x180008e70  test    rax, rax
0x180008e73  mov     [r14+8], rax
0x180008e77  cmovnz  ebx, ecx
0x180008e7a  jmp     short loc_180008E07
0x180008e7c  lea     r8, __ImageBase
0x180008e83  cdqe
0x180008e85  mov     ecx, ds:(jpt_180008E90 - 180000000h)[r8+rax*4]
0x180008e8d  add     rcx, r8
0x180008e90  jmp     rcx; switch jump
0x180008e92  mov     [r14+8], dl; jumptable 0000000180008E90 cases 16,17
0x180008e96  jmp     loc_180008BF7
0x180008e9b  mov     [r14+8], dx; jumptable 0000000180008E90 cases 2,11,18
0x180008ea0  jmp     loc_180008BF7
0x180008ea5  mov     [r14+8], edx; jumptable 0000000180008E90 cases 3,10,19,22,23
0x180008ea9  jmp     loc_180008BF7
0x180008eae  cmp     eax, 3
0x180008eb1  jnz     def_180008E90; jumptable 0000000180008E90 default case, cases 4-9,12-15,20,21
0x180008eb7  movzx   edx, word ptr [rdi+8]
0x180008ebb  mov     eax, 1011h
0x180008ec0  cmp     dx, ax
0x180008ec3  jnz     short loc_180008EFF
0x180008ec5  mov     [r14], ax
0x180008ec9  mov     eax, [rbp+60h+cbData]
0x180008ecc  mov     ecx, eax; cb
0x180008ece  mov     [r14+8], eax
0x180008ed2  call    cs:__imp_CoTaskMemAlloc
0x180008ed8  mov     [r14+10h], rax
0x180008edc  test    rax, rax
0x180008edf  jnz     short loc_180008EEB
0x180008ee1  mov     ebx, 8007000Eh
0x180008ee6  jmp     loc_180008BF7
0x180008eeb  mov     r8d, [rbp+60h+cbData]; Size
0x180008eef  mov     rdx, rsi; Src
0x180008ef2  mov     rcx, rax; void *
0x180008ef5  call    memcpy_0
0x180008efa  jmp     loc_180008BF7
0x180008eff  mov     ecx, edx
0x180008f01  sub     ecx, 4
0x180008f04  jz      short loc_180008F37
0x180008f06  sub     ecx, 1
0x180008f09  jz      short loc_180008F2F
0x180008f0b  sub     ecx, 1
0x180008f0e  jz      short loc_180008F2F
0x180008f10  sub     ecx, 1
0x180008f13  jz      short loc_180008F2F
0x180008f15  cmp     ecx, 7
0x180008f18  jz      short loc_180008F24
0x180008f1a  mov     eax, 80004005h
0x180008f1f  jmp     loc_180008B3B
0x180008f24  mov     rcx, r14
0x180008f27  mov     r8d, 10h
0x180008f2d  jmp     short loc_180008F41
0x180008f2f  mov     r8d, 8
0x180008f35  jmp     short loc_180008F3D
0x180008f37  mov     r8d, 4; Size
0x180008f3d  lea     rcx, [r14+8]; void *
  ... truncated ...
```

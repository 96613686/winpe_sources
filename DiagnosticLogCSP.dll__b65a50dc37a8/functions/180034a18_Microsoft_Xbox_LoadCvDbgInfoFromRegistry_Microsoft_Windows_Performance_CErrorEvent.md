# Microsoft::Xbox::LoadCvDbgInfoFromRegistry(Microsoft::Windows::Performance::CErrorEvent *)

- ea: `0x180034a18`
- end: `0x180035047`
- name: `?LoadCvDbgInfoFromRegistry@Xbox@Microsoft@@YAJPEAVCErrorEvent@Performance@Windows@2@@Z`
- size: `1583`
- prototype: `__int64 __fastcall(Microsoft::Xbox *__hidden this, struct Microsoft::Windows::Performance::CErrorEvent *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021250`

## callees

- `0x180001b90`
- `0x180001bb4`
- `0x18000265c`
- `0x180002d25`
- `0x18000c07c`
- `0x180031a88`
- `0x180031cac`
- `0x180033900`
- `0x18003403c`
- `0x1800343b0`
- `0x180034a18`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180034b0c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180034b0c`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180034e8f`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180034e8f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180034e2b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180034e2b`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034cea`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034d38`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034dcf`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034cea`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034d38`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034dcf`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180034ed8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180034ed8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034b4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034c43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034b4e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034c43`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180034ac3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180034ac3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035004`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035004`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034a6f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034a6f`

## string_xrefs

- `0x180034a81`: `Unable to open RegKey HKLM\System\Software\Microsoft (%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Microsoft::Xbox::LoadCvDbgInfoFromRegistry(
        Microsoft::Xbox *this,
        struct Microsoft::Windows::Performance::CErrorEvent *a2)
{
  int v3; // edi
  const wchar_t *v4; // rdx
  DWORD i; // ebx
  unsigned __int64 v6; // rax
  LSTATUS v7; // ebx
  size_t v8; // r15
  BYTE *v9; // rax
  void *v10; // rax
  void *v11; // rcx
  BYTE *v12; // rbx
  LSTATUS v13; // ebx
  unsigned __int64 v14; // r15
  LPBYTE v15; // r12
  __int64 v16; // rbx
  DWORD v17; // ecx
  const wchar_t *v18; // r12
  wchar_t *v19; // rax
  wchar_t *v20; // rax
  wchar_t *v21; // r13
  __int64 v22; // rcx
  __int64 v23; // r9
  DWORD cbData; // [rsp+40h] [rbp-AB8h] BYREF
  DWORD cchValueName[2]; // [rsp+48h] [rbp-AB0h] BYREF
  char v27; // [rsp+50h] [rbp-AA8h]
  HKEY hKey; // [rsp+58h] [rbp-AA0h] BYREF
  LPBYTE v29[2]; // [rsp+60h] [rbp-A98h] BYREF
  BYTE *v30; // [rsp+70h] [rbp-A88h]
  DWORD Type; // [rsp+78h] [rbp-A80h] BYREF
  wchar_t *v32; // [rsp+80h] [rbp-A78h]
  wchar_t *v33; // [rsp+88h] [rbp-A70h]
  _BYTE Src[520]; // [rsp+90h] [rbp-A68h] BYREF
  int v35; // [rsp+298h] [rbp-860h]
  _BYTE v36[16]; // [rsp+29Ch] [rbp-85Ch] BYREF
  int v37; // [rsp+2ACh] [rbp-84Ch]
  CHAR MultiByteStr[1552]; // [rsp+2B0h] [rbp-848h] BYREF
  WCHAR ValueName[256]; // [rsp+8C0h] [rbp-238h] BYREF

  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Software\\Microsoft", 0, 0x20019u, &hKey);
  if ( v3 )
  {
    v4 = L"Unable to open RegKey HKLM\\System\\Software\\Microsoft (%x)";
LABEL_53:
    (*(void (__fastcall **)(Microsoft::Xbox *, const wchar_t *, _QWORD))(*(_QWORD *)this + 8LL))(
      this,
      v4,
      (unsigned int)v3);
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3;
LABEL_55:
      v3 |= 0x80070000;
    }
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      cchValueName[0] = 256;
      v3 = RegEnumValueW(hKey, i, ValueName, cchValueName, 0, 0, 0, 0);
      if ( v3 )
      {
        v4 = L"Unable to enum reg values (%x)";
        goto LABEL_53;
      }
      v6 = -1;
      do
        ++v6;
      while ( ValueName[v6] );
      if ( v6 >= 4 && !(unsigned int)_o__wcsnicmp(&MultiByteStr[2 * v6 + 1544], L"_vbi", 4) )
        break;
    }
    v3 = 0;
    Type = 0;
    cbData = 0;
    v7 = RegQueryValueExW(hKey, ValueName, 0, &Type, 0, &cbData);
    if ( v7 )
    {
      (*(void (__fastcall **)(Microsoft::Xbox *, const wchar_t *, _QWORD))(*(_QWORD *)this + 8LL))(
        this,
        L"unable to query vbi reg value for size",
        (unsigned int)v7);
      if ( v7 <= 0 )
      {
        v3 = v7;
        goto LABEL_56;
      }
      v3 = (unsigned __int16)v7;
      goto LABEL_55;
    }
    *(_OWORD *)v29 = 0;
    v30 = 0;
    if ( cbData )
    {
      v8 = 2LL * cbData;
      if ( v8 )
      {
        if ( v8 < 0x1000 )
        {
          v9 = (BYTE *)operator new(v8);
        }
        else
        {
          if ( v8 + 39 < v8 )
            __scrt_throw_std_bad_array_new_length();
          v10 = operator new(v8 + 39);
          v11 = v10;
          if ( !v10 )
            __fastfail(5u);
          v9 = (BYTE *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v9 - 1) = v11;
        }
      }
      else
      {
        v9 = 0;
      }
      v29[0] = v9;
      v12 = &v9[v8];
      v30 = &v9[v8];
      memset_0(v9, 0, v8);
      v29[1] = v12;
      *(_QWORD *)cchValueName = 0;
      std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(cchValueName);
    }
    v13 = RegQueryValueExW(hKey, ValueName, 0, 0, v29[0], &cbData);
    if ( v13 )
    {
      (*(void (__fastcall **)(Microsoft::Xbox *, const wchar_t *, _QWORD))(*(_QWORD *)this + 8LL))(
        this,
        L"unable to query vbi reg value for data",
        (unsigned int)v13);
      if ( v13 > 0 )
        v3 = (unsigned __int16)v13 | 0x80070000;
      else
        v3 = v13;
      std::vector<unsigned short>::~vector<unsigned short>(v29);
    }
    else
    {
      v14 = 0;
      v15 = v29[0];
      v16 = -1;
      do
        ++v16;
      while ( *(_WORD *)&v29[0][2 * v16] );
      v17 = cbData;
      while ( v16 && v14 < v17 )
      {
        memset_0(Src, 0, 0x830u);
        v35 = 1396986706;
        v18 = (const wchar_t *)&v15[2 * v14];
        v19 = wcsstr(v18, L"@");
        *(_QWORD *)cchValueName = v19;
        if ( !v19 )
          goto LABEL_38;
        v20 = wcsstr(v19, L"}");
        v21 = v20;
        if ( !v20
          || v20 + 1 >= &v18[v16 - 1]
          || (v32 = v20 + 2, (v33 = wcsstr(v20 + 2, L" ")) == 0)
          || (**(_WORD **)cchValueName = 0,
              _o_wcscpy_s(Src, 260, v18),
              *v21 = 0,
              *(_QWORD *)cchValueName += 4LL,
              !tlx::string_to_guid<unsigned short *>(v36, cchValueName))
          || (v37 = _o__wtoi(v32), WideCharToMultiByte(0, 0, v33 + 1, -1, MultiByteStr, 780, 0, 0) <= 0) )
        {
LABEL_38:
          (*(void (**)(Microsoft::Xbox *, const wchar_t *, ...))(*(_QWORD *)this + 8LL))(
            this,
            L"malformed VBI Dbg Id entry: %s",
            v18);
          v3 = -2147467259;
          std::vector<unsigned short>::~vector<unsigned short>(v29);
          goto LABEL_56;
        }
        if ( qword_18004D700 == (void *)qword_18004D708 )
        {
          std::vector<Microsoft::Xbox::PdbInfoRecord>::_Emplace_reallocate<Microsoft::Xbox::PdbInfoRecord const &>(
            v22,
            qword_18004D700,
            Src);
        }
        else
        {
          memcpy_0(qword_18004D700, Src, 0x830u);
          qword_18004D700 = (char *)qword_18004D700 + 2096;
        }
        v14 += v16 + 1;
        v15 = v29[0];
        if ( !*(_WORD *)&v29[0][2 * v14] )
          ++v14;
        v17 = cbData;
        if ( v14 < cbData )
        {
          v16 = -1;
          do
            ++v16;
          while ( *(_WORD *)&v29[0][2 * v14 + 2 * v16] );
        }
      }
      std::vector<unsigned short>::~vector<unsigned short>(v29);
      LOBYTE(v23) = v27;
      std::_Sort_unchecked_Microsoft::Xbox::PdbInfoRecord____lambda_f7a8b1b861ea55e52666277e77b7ead8___(
        Microsoft::Xbox::pdbRecords,
        qword_18004D700,
        0x3E88CB3C9484E2BLL * (((_BYTE *)qword_18004D700 - (_BYTE *)Microsoft::Xbox::pdbRecords) >> 4),
        v23);
    }
  }
LABEL_56:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180034a18  mov     [rsp+arg_8], rbx
0x180034a1d  mov     [rsp+arg_10], rsi
0x180034a22  push    rdi
0x180034a23  push    r12
0x180034a25  push    r13
0x180034a27  push    r14
0x180034a29  push    r15
0x180034a2b  sub     rsp, 0AD0h
0x180034a32  mov     rax, cs:__security_cookie
0x180034a39  xor     rax, rsp
0x180034a3c  mov     [rsp+0AF8h+var_38], rax
0x180034a44  mov     r14, rcx
0x180034a47  xor     esi, esi
0x180034a49  mov     [rsp+0AF8h+hKey], rsi
0x180034a4e  lea     rax, [rsp+0AF8h+hKey]
0x180034a53  mov     [rsp+0AF8h+phkResult], rax; phkResult
0x180034a58  mov     r9d, 20019h; samDesired
0x180034a5e  xor     r8d, r8d; ulOptions
0x180034a61  lea     rdx, aSystemSoftware; "System\\Software\\Microsoft"
0x180034a68  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034a6f  call    cs:__imp_RegOpenKeyExW
0x180034a76  nop     dword ptr [rax+rax+00h]
0x180034a7b  mov     edi, eax
0x180034a7d  test    eax, eax
0x180034a7f  jz      short loc_180034A8D
0x180034a81  lea     rdx, aUnableToOpenRe; "Unable to open RegKey HKLM\\System\\Sof"...
0x180034a88  jmp     loc_180034FDB
0x180034a8d  mov     ebx, esi
0x180034a8f  or      r13, 0FFFFFFFFFFFFFFFFh
0x180034a93  mov     [rsp+0AF8h+cchValueName], 100h
0x180034a9b  mov     [rsp+0AF8h+lpcbData], rsi; lpcbData
0x180034aa0  mov     [rsp+0AF8h+lpData], rsi; lpData
0x180034aa5  mov     [rsp+0AF8h+lpType], rsi; lpType
0x180034aaa  mov     [rsp+0AF8h+phkResult], rsi; lpReserved
0x180034aaf  lea     r9, [rsp+0AF8h+cchValueName]; lpcchValueName
0x180034ab4  lea     r8, [rsp+0AF8h+ValueName]; lpValueName
0x180034abc  mov     edx, ebx; dwIndex
0x180034abe  mov     rcx, [rsp+0AF8h+hKey]; hKey
0x180034ac3  call    cs:__imp_RegEnumValueW
0x180034aca  nop     dword ptr [rax+rax+00h]
0x180034acf  mov     edi, eax
0x180034ad1  test    eax, eax
0x180034ad3  jnz     loc_180034FD4
0x180034ad9  lea     rcx, [rsp+0AF8h+ValueName]
0x180034ae1  mov     rax, r13
0x180034ae4  inc     rax
0x180034ae7  cmp     [rcx+rax*2], si
0x180034aeb  jnz     short loc_180034AE4
0x180034aed  cmp     rax, 4
0x180034af1  jb      loc_180034FCD
0x180034af7  lea     rcx, [rsp+rax*2+0AF8h+var_240]
0x180034aff  mov     r8d, 4
0x180034b05  lea     rdx, aVbi; "_vbi"
0x180034b0c  call    cs:__imp__o__wcsnicmp
0x180034b13  nop     dword ptr [rax+rax+00h]
0x180034b18  test    eax, eax
0x180034b1a  jnz     loc_180034FCD
0x180034b20  mov     edi, esi
0x180034b22  mov     [rsp+0AF8h+Type], esi
0x180034b26  mov     [rsp+0AF8h+cbData], esi
0x180034b2a  lea     rax, [rsp+0AF8h+cbData]
0x180034b2f  mov     [rsp+0AF8h+lpType], rax; lpcbData
0x180034b34  mov     [rsp+0AF8h+phkResult], rsi; lpData
0x180034b39  lea     r9, [rsp+0AF8h+Type]; lpType
0x180034b3e  xor     r8d, r8d; lpReserved
0x180034b41  lea     rdx, [rsp+0AF8h+ValueName]; lpValueName
0x180034b49  mov     rcx, [rsp+0AF8h+hKey]; hKey
0x180034b4e  call    cs:__imp_RegQueryValueExW
0x180034b55  nop     dword ptr [rax+rax+00h]
0x180034b5a  mov     ebx, eax
0x180034b5c  test    eax, eax
0x180034b5e  jz      short loc_180034B8C
0x180034b60  mov     rcx, [r14]
0x180034b63  mov     rax, [rcx+8]
0x180034b67  mov     r8d, ebx
0x180034b6a  lea     rdx, aUnableToQueryV; "unable to query vbi reg value for size"
0x180034b71  mov     rcx, r14
0x180034b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b79  test    ebx, ebx
0x180034b7b  jg      short loc_180034B84
0x180034b7d  mov     edi, ebx
0x180034b7f  jmp     loc_180034FFA
0x180034b84  movzx   edi, bx
0x180034b87  jmp     loc_180034FF4
0x180034b8c  mov     r15d, [rsp+0AF8h+cbData]
0x180034b91  xorps   xmm0, xmm0
0x180034b94  movdqu  xmmword ptr [rsp+0AF8h+var_A98], xmm0
0x180034b9a  mov     [rsp+0AF8h+var_A88], rsi
0x180034b9f  test    r15, r15
0x180034ba2  jz      short loc_180034C1C
0x180034ba4  add     r15, r15
0x180034ba7  jnz     short loc_180034BAE
0x180034ba9  mov     rax, rsi
0x180034bac  jmp     short loc_180034BEC
0x180034bae  cmp     r15, 1000h
0x180034bb5  jb      short loc_180034BE4
0x180034bb7  lea     rcx, [r15+27h]; Size
0x180034bbb  cmp     rcx, r15
0x180034bbe  jbe     loc_180035040
0x180034bc4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034bc9  mov     rcx, rax
0x180034bcc  test    rax, rax
0x180034bcf  jnz     short loc_180034BD6
0x180034bd1  lea     ecx, [rax+5]
0x180034bd4  int     29h; Win8: RtlFailFast(ecx)
0x180034bd6  add     rax, 27h ; '''
0x180034bda  and     rax, 0FFFFFFFFFFFFFFE0h
0x180034bde  mov     [rax-8], rcx
0x180034be2  jmp     short loc_180034BEC
0x180034be4  mov     rcx, r15; Size
0x180034be7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034bec  mov     [rsp+0AF8h+var_A98], rax
0x180034bf1  lea     rbx, [rax+r15]
0x180034bf5  mov     [rsp+0AF8h+var_A88], rbx
0x180034bfa  mov     r8, r15; Size
0x180034bfd  xor     edx, edx; Val
0x180034bff  mov     rcx, rax; void *
0x180034c02  call    memset_0
0x180034c07  mov     [rsp+0AF8h+var_A98+8], rbx
0x180034c0c  mov     qword ptr [rsp+0AF8h+cchValueName], rsi
0x180034c11  lea     rcx, [rsp+0AF8h+cchValueName]
0x180034c16  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x180034c1b  nop
0x180034c1c  mov     rax, [rsp+0AF8h+var_A98]
0x180034c21  lea     rcx, [rsp+0AF8h+cbData]
0x180034c26  mov     [rsp+0AF8h+lpType], rcx; lpcbData
0x180034c2b  mov     [rsp+0AF8h+phkResult], rax; lpData
0x180034c30  xor     r9d, r9d; lpType
0x180034c33  xor     r8d, r8d; lpReserved
0x180034c36  lea     rdx, [rsp+0AF8h+ValueName]; lpValueName
0x180034c3e  mov     rcx, [rsp+0AF8h+hKey]; hKey
0x180034c43  call    cs:__imp_RegQueryValueExW
0x180034c4a  nop     dword ptr [rax+rax+00h]
0x180034c4f  mov     ebx, eax
0x180034c51  test    eax, eax
0x180034c53  jz      short loc_180034C8F
0x180034c55  mov     rcx, [r14]
0x180034c58  mov     rax, [rcx+8]
0x180034c5c  mov     r8d, ebx
0x180034c5f  lea     rdx, aUnableToQueryV_0; "unable to query vbi reg value for data"
0x180034c66  mov     rcx, r14
0x180034c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c6e  test    ebx, ebx
0x180034c70  jg      short loc_180034C76
0x180034c72  mov     edi, ebx
0x180034c74  jmp     short loc_180034C7F
0x180034c76  movzx   edi, bx
0x180034c79  or      edi, 80070000h
0x180034c7f  lea     rcx, [rsp+0AF8h+var_A98]
0x180034c84  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180034c89  nop
0x180034c8a  jmp     loc_180034FFA
0x180034c8f  mov     r15, rsi
0x180034c92  mov     r12, [rsp+0AF8h+var_A98]
0x180034c97  mov     rbx, r13
0x180034c9a  inc     rbx
0x180034c9d  cmp     [r12+rbx*2], si
0x180034ca2  jnz     short loc_180034C9A
0x180034ca4  mov     ecx, [rsp+0AF8h+cbData]
0x180034ca8  test    rbx, rbx
0x180034cab  jz      loc_180034F8A
0x180034cb1  mov     eax, ecx
0x180034cb3  cmp     r15, rax
0x180034cb6  jnb     loc_180034F8A
0x180034cbc  xor     edx, edx; Val
0x180034cbe  mov     r8d, 830h; Size
0x180034cc4  lea     rcx, [rsp+0AF8h+Src]; void *
0x180034ccc  call    memset_0
0x180034cd1  mov     [rsp+0AF8h+var_860], 53445352h
0x180034cdc  lea     r12, [r12+r15*2]
0x180034ce0  lea     rdx, asc_18003FBD0; "@"
0x180034ce7  mov     rcx, r12; Str
0x180034cea  call    cs:__imp_wcsstr
0x180034cf1  nop     dword ptr [rax+rax+00h]
0x180034cf6  mov     qword ptr [rsp+0AF8h+cchValueName], rax
0x180034cfb  test    rax, rax
0x180034cfe  jnz     short loc_180034D2E
0x180034d00  mov     rax, [r14]
0x180034d03  mov     r8, r12
0x180034d06  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x180034d0d  mov     rcx, r14
0x180034d10  mov     rax, [rax+8]
0x180034d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d19  mov     edi, 80004005h
0x180034d1e  lea     rcx, [rsp+0AF8h+var_A98]
0x180034d23  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180034d28  nop
0x180034d29  jmp     loc_180034FFA
0x180034d2e  lea     rdx, asc_18003FC18; "}"
0x180034d35  mov     rcx, rax; Str
0x180034d38  call    cs:__imp_wcsstr
0x180034d3f  nop     dword ptr [rax+rax+00h]
0x180034d44  mov     r13, rax
0x180034d47  test    rax, rax
0x180034d4a  jnz     short loc_180034D7A
0x180034d4c  mov     rax, [r14]
0x180034d4f  mov     r8, r12
0x180034d52  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x180034d59  mov     rcx, r14
0x180034d5c  mov     rax, [rax+8]
0x180034d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d65  mov     edi, 80004005h
0x180034d6a  lea     rcx, [rsp+0AF8h+var_A98]
0x180034d6f  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180034d74  nop
0x180034d75  jmp     loc_180034FFA
0x180034d7a  lea     rcx, [rax+2]
0x180034d7e  lea     rax, [rbx-1]
0x180034d82  lea     rax, [r12+rax*2]
0x180034d86  cmp     rcx, rax
0x180034d89  jb      short loc_180034DB9
0x180034d8b  mov     rax, [r14]
0x180034d8e  mov     r8, r12
0x180034d91  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x180034d98  mov     rcx, r14
0x180034d9b  mov     rax, [rax+8]
0x180034d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034da4  mov     edi, 80004005h
0x180034da9  lea     rcx, [rsp+0AF8h+var_A98]
0x180034dae  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180034db3  nop
0x180034db4  jmp     loc_180034FFA
0x180034db9  lea     rax, [rcx+2]
0x180034dbd  mov     [rsp+0AF8h+var_A78], rax
0x180034dc5  lea     rdx, asc_18003FC1C; " "
0x180034dcc  mov     rcx, rax; Str
0x180034dcf  call    cs:__imp_wcsstr
0x180034dd6  nop     dword ptr [rax+rax+00h]
0x180034ddb  mov     [rsp+0AF8h+var_A70], rax
0x180034de3  mov     r8, r12
0x180034de6  test    rax, rax
0x180034de9  jnz     short loc_180034E16
0x180034deb  mov     rax, [r14]
0x180034dee  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x180034df5  mov     rcx, r14
0x180034df8  mov     rax, [rax+8]
0x180034dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e01  mov     edi, 80004005h
0x180034e06  lea     rcx, [rsp+0AF8h+var_A98]
0x180034e0b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180034e10  nop
0x180034e11  jmp     loc_180034FFA
0x180034e16  mov     rax, qword ptr [rsp+0AF8h+cchValueName]
0x180034e1b  mov     [rax], si
0x180034e1e  mov     edx, 104h
0x180034e23  lea     rcx, [rsp+0AF8h+Src]
0x180034e2b  call    cs:__imp__o_wcscpy_s
0x180034e32  nop     dword ptr [rax+rax+00h]
0x180034e37  mov     [r13+0], si
0x180034e3c  add     qword ptr [rsp+0AF8h+cchValueName], 4
0x180034e42  lea     rdx, [rsp+0AF8h+cchValueName]
0x180034e47  lea     rcx, [rsp+0AF8h+var_85C]
0x180034e4f  call    ??$string_to_guid@PEAG@tlx@@YAPEAGPEAU_GUID@@AEBQEAG@Z; tlx::string_to_guid<ushort *>(_GUID *,ushort * const &)
0x180034e54  test    rax, rax
0x180034e57  jnz     short loc_180034E87
0x180034e59  mov     rax, [r14]
0x180034e5c  mov     r8, r12
0x180034e5f  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x180034e66  mov     rcx, r14
0x180034e69  mov     rax, [rax+8]
0x180034e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e72  mov     edi, 80004005h
0x180034e77  lea     rcx, [rsp+0AF8h+var_A98]
0x180034e7c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180034e81  nop
0x180034e82  jmp     loc_180034FFA
0x180034e87  mov     rcx, [rsp+0AF8h+var_A78]
0x180034e8f  call    cs:__imp__o__wtoi
0x180034e96  nop     dword ptr [rax+rax+00h]
0x180034e9b  mov     [rsp+0AF8h+var_84C], eax
0x180034ea2  mov     r8, [rsp+0AF8h+var_A70]
0x180034eaa  add     r8, 2; lpWideCharStr
0x180034eae  mov     [rsp+0AF8h+lpcbData], rsi; lpUsedDefaultChar
0x180034eb3  mov     [rsp+0AF8h+lpData], rsi; lpDefaultChar
0x180034eb8  mov     dword ptr [rsp+0AF8h+lpType], 30Ch; cbMultiByte
0x180034ec0  lea     rax, [rsp+0AF8h+MultiByteStr]
0x180034ec8  mov     [rsp+0AF8h+phkResult], rax; lpMultiByteStr
0x180034ecd  or      r13, 0FFFFFFFFFFFFFFFFh
0x180034ed1  mov     r9d, r13d; cchWideChar
0x180034ed4  xor     edx, edx; dwFlags
0x180034ed6  xor     ecx, ecx; CodePage
0x180034ed8  call    cs:__imp_WideCharToMultiByte
0x180034edf  nop     dword ptr [rax+rax+00h]
0x180034ee4  test    eax, eax
0x180034ee6  jle     short loc_180034F5F
0x180034ee8  mov     rdx, cs:qword_18004D700
0x180034eef  cmp     rdx, cs:qword_18004D708
0x180034ef6  jz      short loc_180034F1B
0x180034ef8  mov     rcx, rdx; void *
0x180034efb  lea     rdx, [rsp+0AF8h+Src]; Src
0x180034f03  mov     r8d, 830h; Size
0x180034f09  call    memcpy_0
0x180034f0e  add     cs:qword_18004D700, 830h
0x180034f19  jmp     short loc_180034F28
0x180034f1b  lea     r8, [rsp+0AF8h+Src]
0x180034f23  call    ??$_Emplace_reallocate@AEBUPdbInfoRecord@Xbox@Microsoft@@@?$vector@UPdbInfoRecord@Xbox@Microsoft@@V?$allocator@UPdbInfoRecord@Xbox@Microsoft@@@std@@@std@@AEAAPEAUPdbInfoRecord@Xbox@Microsoft@@QEAU234@AEBU234@@Z; std::vector<Microsoft::Xbox::PdbInfoRecord>::_Emplace_reallocate<Microsoft::Xbox::PdbInfoRecord const &>(Microsoft::Xbox::PdbInfoRecord * const,Microsoft::Xbox::PdbInfoRecord const &)
0x180034f28  inc     r15
0x180034f2b  add     r15, rbx
0x180034f2e  mov     r12, [rsp+0AF8h+var_A98]
0x180034f33  cmp     [r12+r15*2], si
  ... truncated ...
```

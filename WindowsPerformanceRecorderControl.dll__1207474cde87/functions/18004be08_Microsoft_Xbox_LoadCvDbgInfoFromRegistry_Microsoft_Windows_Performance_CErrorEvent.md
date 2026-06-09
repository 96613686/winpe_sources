# Microsoft::Xbox::LoadCvDbgInfoFromRegistry(Microsoft::Windows::Performance::CErrorEvent *)

- ea: `0x18004be08`
- end: `0x18004c35b`
- name: `?LoadCvDbgInfoFromRegistry@Xbox@Microsoft@@YAJPEAVCErrorEvent@Performance@Windows@2@@Z`
- size: `1363`
- prototype: `__int64 __fastcall(Microsoft::Xbox *__hidden this, struct Microsoft::Windows::Performance::CErrorEvent *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027e60`

## callees

- `0x18004be08`
- `0x18004c648`
- `0x18004ece0`
- `0x18004f964`
- `0x18008135c`
- `0x1800813c0`
- `0x180081e08`
- `0x180081f08`
- `0x180082268`
- `0x180082d3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18004c1c5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18004c1c5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004c167`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18004c167`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c038`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c080`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c111`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c038`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c080`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18004c111`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004c205`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004c205`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004be6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004be6b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004beb7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18004beb7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bf12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bf92`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bf12`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004bf92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c326`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c326`

## string_xrefs

- `0x18004be77`: `Unable to open RegKey HKLM\System\Software\Microsoft (%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Microsoft::Xbox::LoadCvDbgInfoFromRegistry(
        Microsoft::Xbox *this,
        struct Microsoft::Windows::Performance::CErrorEvent *a2)
{
  int v3; // ebx
  const wchar_t *v4; // rdx
  DWORD i; // r14d
  const unsigned __int16 *v6; // r8
  LSTATUS v7; // r14d
  LSTATUS v8; // r14d
  unsigned __int64 v9; // r15
  LPBYTE v10; // r12
  __int64 v11; // r14
  DWORD v12; // ecx
  const wchar_t *v13; // r12
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // r13
  __int64 v17; // rcx
  __int64 v18; // r9
  DWORD cbData; // [rsp+40h] [rbp-AC8h] BYREF
  DWORD cchValueName[2]; // [rsp+48h] [rbp-AC0h] BYREF
  char v22; // [rsp+50h] [rbp-AB8h]
  HKEY hKey; // [rsp+58h] [rbp-AB0h] BYREF
  LPBYTE v24[2]; // [rsp+60h] [rbp-AA8h] BYREF
  __int64 v25; // [rsp+70h] [rbp-A98h]
  DWORD Type; // [rsp+78h] [rbp-A90h] BYREF
  wchar_t *v27; // [rsp+80h] [rbp-A88h]
  wchar_t *v28; // [rsp+88h] [rbp-A80h]
  __int64 v29; // [rsp+90h] [rbp-A78h]
  _BYTE Src[520]; // [rsp+A0h] [rbp-A68h] BYREF
  int v31; // [rsp+2A8h] [rbp-860h]
  _BYTE v32[16]; // [rsp+2ACh] [rbp-85Ch] BYREF
  int v33; // [rsp+2BCh] [rbp-84Ch]
  CHAR MultiByteStr[1552]; // [rsp+2C0h] [rbp-848h] BYREF
  WCHAR ValueName[256]; // [rsp+8D0h] [rbp-238h] BYREF

  v29 = -2;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Software\\Microsoft", 0, 0x20019u, &hKey);
  if ( v3 )
  {
    v4 = L"Unable to open RegKey HKLM\\System\\Software\\Microsoft (%x)";
LABEL_40:
    (*(void (__fastcall **)(Microsoft::Xbox *, const wchar_t *, _QWORD))(*(_QWORD *)this + 8LL))(
      this,
      v4,
      (unsigned int)v3);
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3;
LABEL_42:
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
        goto LABEL_40;
      }
      if ( (unsigned int)Microsoft::Xbox::StringEndsWithW((Microsoft::Xbox *)ValueName, L"_vbi", v6) )
        break;
    }
    Type = 0;
    cbData = 0;
    v3 = 0;
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
        goto LABEL_43;
      }
      v3 = (unsigned __int16)v7;
      goto LABEL_42;
    }
    *(_OWORD *)v24 = 0;
    v25 = 0;
    std::vector<unsigned short>::_Construct_n<>(v24, cbData);
    v8 = RegQueryValueExW(hKey, ValueName, 0, 0, v24[0], &cbData);
    if ( v8 )
    {
      (*(void (__fastcall **)(Microsoft::Xbox *, const wchar_t *, _QWORD))(*(_QWORD *)this + 8LL))(
        this,
        L"unable to query vbi reg value for data",
        (unsigned int)v8);
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      else
        v3 = v8;
      std::vector<unsigned short>::_Tidy(v24);
    }
    else
    {
      v9 = 0;
      v10 = v24[0];
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&v24[0][2 * v11] );
      v12 = cbData;
      while ( v11 && v9 < v12 )
      {
        memset_0(Src, 0, 0x830u);
        v31 = 1396986706;
        v13 = (const wchar_t *)&v10[2 * v9];
        v14 = wcsstr(v13, L"@");
        *(_QWORD *)cchValueName = v14;
        if ( !v14 )
          goto LABEL_26;
        v15 = wcsstr(v14, L"}");
        v16 = v15;
        if ( !v15
          || v15 + 1 >= &v13[v11 - 1]
          || (v27 = v15 + 2, (v28 = wcsstr(v15 + 2, L" ")) == 0)
          || (**(_WORD **)cchValueName = 0,
              _o_wcscpy_s(Src, 260, v13),
              *v16 = 0,
              *(_QWORD *)cchValueName += 4LL,
              !tlx::string_to_guid<unsigned short *>(v32, cchValueName))
          || (v33 = _o__wtoi(v27), WideCharToMultiByte(0, 0, v28 + 1, -1, MultiByteStr, 780, 0, 0) <= 0) )
        {
LABEL_26:
          (*(void (**)(Microsoft::Xbox *, const wchar_t *, ...))(*(_QWORD *)this + 8LL))(
            this,
            L"malformed VBI Dbg Id entry: %s",
            v13);
          v3 = -2147467259;
          std::vector<unsigned short>::_Tidy(v24);
          goto LABEL_43;
        }
        if ( *(&Microsoft::Xbox::pdbRecords + 1) == (void *)qword_1800BE970 )
        {
          std::vector<Microsoft::Xbox::PdbInfoRecord>::_Emplace_reallocate<Microsoft::Xbox::PdbInfoRecord const &>(
            v17,
            *(&Microsoft::Xbox::pdbRecords + 1),
            Src);
        }
        else
        {
          memcpy_0(*(&Microsoft::Xbox::pdbRecords + 1), Src, 0x830u);
          *(&Microsoft::Xbox::pdbRecords + 1) = (char *)*(&Microsoft::Xbox::pdbRecords + 1) + 2096;
        }
        v9 += v11 + 1;
        v10 = v24[0];
        if ( !*(_WORD *)&v24[0][2 * v9] )
          ++v9;
        v12 = cbData;
        if ( v9 < cbData )
        {
          v11 = -1;
          do
            ++v11;
          while ( *(_WORD *)&v24[0][2 * v9 + 2 * v11] );
        }
      }
      std::vector<unsigned short>::_Tidy(v24);
      LOBYTE(v18) = v22;
      std::_Sort_unchecked_Microsoft::Xbox::PdbInfoRecord____lambda_f7a8b1b861ea55e52666277e77b7ead8___(
        Microsoft::Xbox::pdbRecords,
        *(&Microsoft::Xbox::pdbRecords + 1),
        0x3E88CB3C9484E2BLL
      * (((_BYTE *)*(&Microsoft::Xbox::pdbRecords + 1) - (_BYTE *)Microsoft::Xbox::pdbRecords) >> 4),
        v18);
    }
  }
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004be08  mov     rax, rsp
0x18004be0b  push    rdi
0x18004be0c  push    r12
0x18004be0e  push    r13
0x18004be10  push    r14
0x18004be12  push    r15
0x18004be14  sub     rsp, 0AE0h
0x18004be1b  mov     qword ptr [rax-0A78h], 0FFFFFFFFFFFFFFFEh
0x18004be26  mov     [rax+10h], rbx
0x18004be2a  mov     [rax+18h], rsi
0x18004be2e  mov     rax, cs:__security_cookie
0x18004be35  xor     rax, rsp
0x18004be38  mov     [rsp+0B08h+var_38], rax
0x18004be40  mov     rsi, rcx
0x18004be43  xor     edi, edi
0x18004be45  mov     [rsp+0B08h+hKey], rdi
0x18004be4a  lea     rax, [rsp+0B08h+hKey]
0x18004be4f  mov     [rsp+0B08h+phkResult], rax; phkResult
0x18004be54  mov     r9d, 20019h; samDesired
0x18004be5a  xor     r8d, r8d; ulOptions
0x18004be5d  lea     rdx, aSystemSoftware; "System\\Software\\Microsoft"
0x18004be64  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004be6b  call    cs:__imp_RegOpenKeyExW
0x18004be71  mov     ebx, eax
0x18004be73  test    eax, eax
0x18004be75  jz      short loc_18004BE83
0x18004be77  lea     rdx, aUnableToOpenRe; "Unable to open RegKey HKLM\\System\\Sof"...
0x18004be7e  jmp     loc_18004C2FD
0x18004be83  mov     r14d, edi
0x18004be86  mov     [rsp+0B08h+cchValueName], 100h
0x18004be8e  mov     [rsp+0B08h+lpcbData], rdi; lpcbData
0x18004be93  mov     [rsp+0B08h+lpData], rdi; lpData
0x18004be98  mov     [rsp+0B08h+lpType], rdi; lpType
0x18004be9d  mov     [rsp+0B08h+phkResult], rdi; lpReserved
0x18004bea2  lea     r9, [rsp+0B08h+cchValueName]; lpcchValueName
0x18004bea7  lea     r8, [rsp+0B08h+ValueName]; lpValueName
0x18004beaf  mov     edx, r14d; dwIndex
0x18004beb2  mov     rcx, [rsp+0B08h+hKey]; hKey
0x18004beb7  call    cs:__imp_RegEnumValueW
0x18004bebd  mov     ebx, eax
0x18004bebf  test    eax, eax
0x18004bec1  jnz     loc_18004C2F6
0x18004bec7  lea     rdx, aVbi; "_vbi"
0x18004bece  lea     rcx, [rsp+0B08h+ValueName]; this
0x18004bed6  call    ?StringEndsWithW@Xbox@Microsoft@@YAHPEBG0@Z; Microsoft::Xbox::StringEndsWithW(ushort const *,ushort const *)
0x18004bedb  test    eax, eax
0x18004bedd  jnz     short loc_18004BEE4
0x18004bedf  inc     r14d
0x18004bee2  jmp     short loc_18004BE86
0x18004bee4  mov     [rsp+0B08h+Type], edi
0x18004bee8  mov     [rsp+0B08h+cbData], edi
0x18004beec  mov     ebx, edi
0x18004beee  lea     rax, [rsp+0B08h+cbData]
0x18004bef3  mov     [rsp+0B08h+lpType], rax; lpcbData
0x18004bef8  mov     [rsp+0B08h+phkResult], rdi; lpData
0x18004befd  lea     r9, [rsp+0B08h+Type]; lpType
0x18004bf02  xor     r8d, r8d; lpReserved
0x18004bf05  lea     rdx, [rsp+0B08h+ValueName]; lpValueName
0x18004bf0d  mov     rcx, [rsp+0B08h+hKey]; hKey
0x18004bf12  call    cs:__imp_RegQueryValueExW
0x18004bf18  mov     r14d, eax
0x18004bf1b  test    eax, eax
0x18004bf1d  jz      short loc_18004BF4E
0x18004bf1f  mov     rcx, [rsi]
0x18004bf22  mov     rax, [rcx+8]
0x18004bf26  mov     r8d, r14d
0x18004bf29  lea     rdx, aUnableToQueryV; "unable to query vbi reg value for size"
0x18004bf30  mov     rcx, rsi
0x18004bf33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bf38  test    r14d, r14d
0x18004bf3b  jg      short loc_18004BF45
0x18004bf3d  mov     ebx, r14d
0x18004bf40  jmp     loc_18004C31C
0x18004bf45  movzx   ebx, r14w
0x18004bf49  jmp     loc_18004C316
0x18004bf4e  xorps   xmm0, xmm0
0x18004bf51  movdqu  xmmword ptr [rsp+0B08h+var_AA8], xmm0
0x18004bf57  mov     [rsp+0B08h+var_A98], rdi
0x18004bf5c  mov     edx, [rsp+0B08h+cbData]
0x18004bf60  lea     rcx, [rsp+0B08h+var_AA8]
0x18004bf65  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x18004bf6a  nop
0x18004bf6b  mov     rax, [rsp+0B08h+var_AA8]
0x18004bf70  lea     rcx, [rsp+0B08h+cbData]
0x18004bf75  mov     [rsp+0B08h+lpType], rcx; lpcbData
0x18004bf7a  mov     [rsp+0B08h+phkResult], rax; lpData
0x18004bf7f  xor     r9d, r9d; lpType
0x18004bf82  xor     r8d, r8d; lpReserved
0x18004bf85  lea     rdx, [rsp+0B08h+ValueName]; lpValueName
0x18004bf8d  mov     rcx, [rsp+0B08h+hKey]; hKey
0x18004bf92  call    cs:__imp_RegQueryValueExW
0x18004bf98  mov     r14d, eax
0x18004bf9b  test    eax, eax
0x18004bf9d  jz      short loc_18004BFDC
0x18004bf9f  mov     rcx, [rsi]
0x18004bfa2  mov     rax, [rcx+8]
0x18004bfa6  mov     r8d, r14d
0x18004bfa9  lea     rdx, aUnableToQueryV_0; "unable to query vbi reg value for data"
0x18004bfb0  mov     rcx, rsi
0x18004bfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfb8  test    r14d, r14d
0x18004bfbb  jg      short loc_18004BFC2
0x18004bfbd  mov     ebx, r14d
0x18004bfc0  jmp     short loc_18004BFCC
0x18004bfc2  movzx   ebx, r14w
0x18004bfc6  or      ebx, 80070000h
0x18004bfcc  lea     rcx, [rsp+0B08h+var_AA8]
0x18004bfd1  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004bfd6  nop
0x18004bfd7  jmp     loc_18004C31C
0x18004bfdc  mov     r15, rdi
0x18004bfdf  mov     r12, [rsp+0B08h+var_AA8]
0x18004bfe4  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004bfe8  inc     r14
0x18004bfeb  cmp     [r12+r14*2], di
0x18004bff0  jnz     short loc_18004BFE8
0x18004bff2  mov     ecx, [rsp+0B08h+cbData]
0x18004bff6  test    r14, r14
0x18004bff9  jz      loc_18004C2B3
0x18004bfff  mov     eax, ecx
0x18004c001  cmp     r15, rax
0x18004c004  jnb     loc_18004C2B3
0x18004c00a  xor     edx, edx; Val
0x18004c00c  mov     r8d, 830h; Size
0x18004c012  lea     rcx, [rsp+0B08h+Src]; void *
0x18004c01a  call    memset_0
0x18004c01f  mov     [rsp+0B08h+var_860], 53445352h
0x18004c02a  lea     r12, [r12+r15*2]
0x18004c02e  lea     rdx, SubStr; "@"
0x18004c035  mov     rcx, r12; Str
0x18004c038  call    cs:__imp_wcsstr
0x18004c03e  mov     qword ptr [rsp+0B08h+cchValueName], rax
0x18004c043  test    rax, rax
0x18004c046  jnz     short loc_18004C076
0x18004c048  mov     rax, [rsi]
0x18004c04b  mov     r8, r12
0x18004c04e  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x18004c055  mov     rcx, rsi
0x18004c058  mov     rax, [rax+8]
0x18004c05c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c061  mov     ebx, 80004005h
0x18004c066  lea     rcx, [rsp+0B08h+var_AA8]
0x18004c06b  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004c070  nop
0x18004c071  jmp     loc_18004C31C
0x18004c076  lea     rdx, asc_180094A9C; "}"
0x18004c07d  mov     rcx, rax; Str
0x18004c080  call    cs:__imp_wcsstr
0x18004c086  mov     r13, rax
0x18004c089  test    rax, rax
0x18004c08c  jnz     short loc_18004C0BC
0x18004c08e  mov     rax, [rsi]
0x18004c091  mov     r8, r12
0x18004c094  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x18004c09b  mov     rcx, rsi
0x18004c09e  mov     rax, [rax+8]
0x18004c0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0a7  mov     ebx, 80004005h
0x18004c0ac  lea     rcx, [rsp+0B08h+var_AA8]
0x18004c0b1  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004c0b6  nop
0x18004c0b7  jmp     loc_18004C31C
0x18004c0bc  lea     rcx, [rax+2]
0x18004c0c0  lea     rax, [r14-1]
0x18004c0c4  lea     rax, [r12+rax*2]
0x18004c0c8  cmp     rcx, rax
0x18004c0cb  jb      short loc_18004C0FB
0x18004c0cd  mov     rax, [rsi]
0x18004c0d0  mov     r8, r12
0x18004c0d3  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x18004c0da  mov     rcx, rsi
0x18004c0dd  mov     rax, [rax+8]
0x18004c0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0e6  mov     ebx, 80004005h
0x18004c0eb  lea     rcx, [rsp+0B08h+var_AA8]
0x18004c0f0  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004c0f5  nop
0x18004c0f6  jmp     loc_18004C31C
0x18004c0fb  lea     rax, [rcx+2]
0x18004c0ff  mov     [rsp+0B08h+var_A88], rax
0x18004c107  lea     rdx, asc_18009E148; " "
0x18004c10e  mov     rcx, rax; Str
0x18004c111  call    cs:__imp_wcsstr
0x18004c117  mov     [rsp+0B08h+var_A80], rax
0x18004c11f  mov     r8, r12
0x18004c122  test    rax, rax
0x18004c125  jnz     short loc_18004C152
0x18004c127  mov     rax, [rsi]
0x18004c12a  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x18004c131  mov     rcx, rsi
0x18004c134  mov     rax, [rax+8]
0x18004c138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c13d  mov     ebx, 80004005h
0x18004c142  lea     rcx, [rsp+0B08h+var_AA8]
0x18004c147  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004c14c  nop
0x18004c14d  jmp     loc_18004C31C
0x18004c152  mov     rax, qword ptr [rsp+0B08h+cchValueName]
0x18004c157  mov     [rax], di
0x18004c15a  mov     edx, 104h
0x18004c15f  lea     rcx, [rsp+0B08h+Src]
0x18004c167  call    cs:__imp__o_wcscpy_s
0x18004c16d  mov     [r13+0], di
0x18004c172  add     qword ptr [rsp+0B08h+cchValueName], 4
0x18004c178  lea     rdx, [rsp+0B08h+cchValueName]
0x18004c17d  lea     rcx, [rsp+0B08h+var_85C]
0x18004c185  call    ??$string_to_guid@PEAG@tlx@@YAPEAGPEAU_GUID@@AEBQEAG@Z; tlx::string_to_guid<ushort *>(_GUID *,ushort * const &)
0x18004c18a  test    rax, rax
0x18004c18d  jnz     short loc_18004C1BD
0x18004c18f  mov     rax, [rsi]
0x18004c192  mov     r8, r12
0x18004c195  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x18004c19c  mov     rcx, rsi
0x18004c19f  mov     rax, [rax+8]
0x18004c1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c1a8  mov     ebx, 80004005h
0x18004c1ad  lea     rcx, [rsp+0B08h+var_AA8]
0x18004c1b2  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004c1b7  nop
0x18004c1b8  jmp     loc_18004C31C
0x18004c1bd  mov     rcx, [rsp+0B08h+var_A88]
0x18004c1c5  call    cs:__imp__o__wtoi
0x18004c1cb  mov     [rsp+0B08h+var_84C], eax
0x18004c1d2  mov     r8, [rsp+0B08h+var_A80]
0x18004c1da  add     r8, 2; lpWideCharStr
0x18004c1de  mov     [rsp+0B08h+lpcbData], rdi; lpUsedDefaultChar
0x18004c1e3  mov     [rsp+0B08h+lpData], rdi; lpDefaultChar
0x18004c1e8  mov     dword ptr [rsp+0B08h+lpType], 30Ch; cbMultiByte
0x18004c1f0  lea     rax, [rsp+0B08h+MultiByteStr]
0x18004c1f8  mov     [rsp+0B08h+phkResult], rax; lpMultiByteStr
0x18004c1fd  or      r9d, 0FFFFFFFFh; cchWideChar
0x18004c201  xor     edx, edx; dwFlags
0x18004c203  xor     ecx, ecx; CodePage
0x18004c205  call    cs:__imp_WideCharToMultiByte
0x18004c20b  test    eax, eax
0x18004c20d  jle     short loc_18004C288
0x18004c20f  mov     rdx, qword ptr cs:?pdbRecords@Xbox@Microsoft@@3V?$vector@UPdbInfoRecord@Xbox@Microsoft@@V?$allocator@UPdbInfoRecord@Xbox@Microsoft@@@std@@@std@@A+8; std::vector<Microsoft::Xbox::PdbInfoRecord> Microsoft::Xbox::pdbRecords
0x18004c216  cmp     rdx, cs:qword_1800BE970
0x18004c21d  jz      short loc_18004C242
0x18004c21f  mov     rcx, rdx; void *
0x18004c222  lea     rdx, [rsp+0B08h+Src]; Src
0x18004c22a  mov     r8d, 830h; Size
0x18004c230  call    memcpy_0
0x18004c235  add     qword ptr cs:?pdbRecords@Xbox@Microsoft@@3V?$vector@UPdbInfoRecord@Xbox@Microsoft@@V?$allocator@UPdbInfoRecord@Xbox@Microsoft@@@std@@@std@@A+8, 830h; std::vector<Microsoft::Xbox::PdbInfoRecord> Microsoft::Xbox::pdbRecords
0x18004c240  jmp     short loc_18004C24F
0x18004c242  lea     r8, [rsp+0B08h+Src]
0x18004c24a  call    ??$_Emplace_reallocate@AEBUPdbInfoRecord@Xbox@Microsoft@@@?$vector@UPdbInfoRecord@Xbox@Microsoft@@V?$allocator@UPdbInfoRecord@Xbox@Microsoft@@@std@@@std@@AEAAPEAUPdbInfoRecord@Xbox@Microsoft@@QEAU234@AEBU234@@Z; std::vector<Microsoft::Xbox::PdbInfoRecord>::_Emplace_reallocate<Microsoft::Xbox::PdbInfoRecord const &>(Microsoft::Xbox::PdbInfoRecord * const,Microsoft::Xbox::PdbInfoRecord const &)
0x18004c24f  inc     r15
0x18004c252  add     r15, r14
0x18004c255  mov     r12, [rsp+0B08h+var_AA8]
0x18004c25a  cmp     [r12+r15*2], di
0x18004c25f  jnz     short loc_18004C264
0x18004c261  inc     r15
0x18004c264  mov     ecx, [rsp+0B08h+cbData]
0x18004c268  cmp     r15, rcx
0x18004c26b  jnb     loc_18004BFF6
0x18004c271  lea     rax, [r12+r15*2]
0x18004c275  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004c279  inc     r14
0x18004c27c  cmp     [rax+r14*2], di
0x18004c281  jnz     short loc_18004C279
0x18004c283  jmp     loc_18004BFF6
0x18004c288  mov     rax, [rsi]
0x18004c28b  mov     r8, r12
0x18004c28e  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x18004c295  mov     rcx, rsi
0x18004c298  mov     rax, [rax+8]
0x18004c29c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2a1  mov     ebx, 80004005h
0x18004c2a6  lea     rcx, [rsp+0B08h+var_AA8]
0x18004c2ab  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004c2b0  nop
0x18004c2b1  jmp     short loc_18004C31C
0x18004c2b3  lea     rcx, [rsp+0B08h+var_AA8]
0x18004c2b8  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18004c2bd  nop
0x18004c2be  jmp     short loc_18004C2C4
0x18004c2c0  mov     ebx, [rsp+0B08h+cchValueName]
0x18004c2c4  mov     rdx, qword ptr cs:?pdbRecords@Xbox@Microsoft@@3V?$vector@UPdbInfoRecord@Xbox@Microsoft@@V?$allocator@UPdbInfoRecord@Xbox@Microsoft@@@std@@@std@@A+8; std::vector<Microsoft::Xbox::PdbInfoRecord> Microsoft::Xbox::pdbRecords
0x18004c2cb  mov     rcx, qword ptr cs:?pdbRecords@Xbox@Microsoft@@3V?$vector@UPdbInfoRecord@Xbox@Microsoft@@V?$allocator@UPdbInfoRecord@Xbox@Microsoft@@@std@@@std@@A; std::vector<Microsoft::Xbox::PdbInfoRecord> Microsoft::Xbox::pdbRecords
0x18004c2d2  mov     r8, rdx
0x18004c2d5  sub     r8, rcx
0x18004c2d8  sar     r8, 4
0x18004c2dc  mov     rax, 3E88CB3C9484E2Bh
0x18004c2e6  imul    r8, rax
0x18004c2ea  mov     r9b, [rsp+0B08h+var_AB8]
0x18004c2ef  call    std___Sort_unchecked_Microsoft__Xbox__PdbInfoRecord____lambda_f7a8b1b861ea55e52666277e77b7ead8___
0x18004c2f4  jmp     short loc_18004C31C
0x18004c2f6  lea     rdx, aUnableToEnumRe; "Unable to enum reg values (%x)"
0x18004c2fd  mov     rax, [rsi]
0x18004c300  mov     r8d, ebx
0x18004c303  mov     rcx, rsi
0x18004c306  mov     rax, [rax+8]
0x18004c30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c30f  test    ebx, ebx
0x18004c311  jle     short loc_18004C31C
0x18004c313  movzx   ebx, bx
0x18004c316  or      ebx, 80070000h
0x18004c31c  mov     rcx, [rsp+0B08h+hKey]; hKey
0x18004c321  test    rcx, rcx
  ... truncated ...
```

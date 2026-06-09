# Microsoft::Xbox::LoadCvDbgInfoFromRegistry(Microsoft::Windows::Performance::CErrorEvent *)

- ea: `0x180025ee4`
- end: `0x1800264ca`
- name: `?LoadCvDbgInfoFromRegistry@Xbox@Microsoft@@YAJPEAVCErrorEvent@Performance@Windows@2@@Z`
- size: `1510`
- prototype: `__int64 __fastcall(Microsoft::Xbox *__hidden this, struct Microsoft::Windows::Performance::CErrorEvent *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f5dc`

## callees

- `0x180001870`
- `0x1800018a0`
- `0x180002420`
- `0x1800027b1`
- `0x18000be50`
- `0x180022f78`
- `0x18002319c`
- `0x180024dcc`
- `0x180025508`
- `0x18002587c`
- `0x180025ee4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180025fcc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180025fcc`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180026325`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180026325`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800262c7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800262c7`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180026198`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800261e0`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180026271`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180026198`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800261e0`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180026271`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026368`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180026368`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180025f89`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180025f89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026008`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800260f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026008`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800260f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002648e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002648e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025f3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025f3b`

## string_xrefs

- `0x180025f47`: `Unable to open RegKey HKLM\System\Software\Microsoft (%x)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        if ( qword_180036EB0 == (void *)qword_180036EB8 )
        {
          std::vector<Microsoft::Xbox::PdbInfoRecord>::_Emplace_reallocate<Microsoft::Xbox::PdbInfoRecord const &>(
            v22,
            qword_180036EB0,
            Src);
        }
        else
        {
          memcpy_0(qword_180036EB0, Src, 0x830u);
          qword_180036EB0 = (char *)qword_180036EB0 + 2096;
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
        qword_180036EB0,
        0x3E88CB3C9484E2BLL * (((_BYTE *)qword_180036EB0 - (_BYTE *)Microsoft::Xbox::pdbRecords) >> 4),
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
0x180025ee4  mov     [rsp+arg_8], rbx
0x180025ee9  mov     [rsp+arg_10], rsi
0x180025eee  push    rdi
0x180025eef  push    r12
0x180025ef1  push    r13
0x180025ef3  push    r14
0x180025ef5  push    r15
0x180025ef7  sub     rsp, 0AD0h
0x180025efe  mov     rax, cs:__security_cookie
0x180025f05  xor     rax, rsp
0x180025f08  mov     [rsp+0AF8h+var_38], rax
0x180025f10  mov     r14, rcx
0x180025f13  xor     esi, esi
0x180025f15  mov     [rsp+0AF8h+hKey], rsi
0x180025f1a  lea     rax, [rsp+0AF8h+hKey]
0x180025f1f  mov     [rsp+0AF8h+phkResult], rax; phkResult
0x180025f24  mov     r9d, 20019h; samDesired
0x180025f2a  xor     r8d, r8d; ulOptions
0x180025f2d  lea     rdx, aSystemSoftware; "System\\Software\\Microsoft"
0x180025f34  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025f3b  call    cs:__imp_RegOpenKeyExW
0x180025f41  mov     edi, eax
0x180025f43  test    eax, eax
0x180025f45  jz      short loc_180025F53
0x180025f47  lea     rdx, aUnableToOpenRe; "Unable to open RegKey HKLM\\System\\Sof"...
0x180025f4e  jmp     loc_180026465
0x180025f53  mov     ebx, esi
0x180025f55  or      r13, 0FFFFFFFFFFFFFFFFh
0x180025f59  mov     [rsp+0AF8h+cchValueName], 100h
0x180025f61  mov     [rsp+0AF8h+lpcbData], rsi; lpcbData
0x180025f66  mov     [rsp+0AF8h+lpData], rsi; lpData
0x180025f6b  mov     [rsp+0AF8h+lpType], rsi; lpType
0x180025f70  mov     [rsp+0AF8h+phkResult], rsi; lpReserved
0x180025f75  lea     r9, [rsp+0AF8h+cchValueName]; lpcchValueName
0x180025f7a  lea     r8, [rsp+0AF8h+ValueName]; lpValueName
0x180025f82  mov     edx, ebx; dwIndex
0x180025f84  mov     rcx, [rsp+0AF8h+hKey]; hKey
0x180025f89  call    cs:__imp_RegEnumValueW
0x180025f8f  mov     edi, eax
0x180025f91  test    eax, eax
0x180025f93  jnz     loc_18002645E
0x180025f99  lea     rcx, [rsp+0AF8h+ValueName]
0x180025fa1  mov     rax, r13
0x180025fa4  inc     rax
0x180025fa7  cmp     [rcx+rax*2], si
0x180025fab  jnz     short loc_180025FA4
0x180025fad  cmp     rax, 4
0x180025fb1  jb      loc_180026457
0x180025fb7  lea     rcx, [rsp+rax*2+0AF8h+var_240]
0x180025fbf  mov     r8d, 4
0x180025fc5  lea     rdx, aVbi; "_vbi"
0x180025fcc  call    cs:__imp__o__wcsnicmp
0x180025fd2  test    eax, eax
0x180025fd4  jnz     loc_180026457
0x180025fda  mov     edi, esi
0x180025fdc  mov     [rsp+0AF8h+Type], esi
0x180025fe0  mov     [rsp+0AF8h+cbData], esi
0x180025fe4  lea     rax, [rsp+0AF8h+cbData]
0x180025fe9  mov     [rsp+0AF8h+lpType], rax; lpcbData
0x180025fee  mov     [rsp+0AF8h+phkResult], rsi; lpData
0x180025ff3  lea     r9, [rsp+0AF8h+Type]; lpType
0x180025ff8  xor     r8d, r8d; lpReserved
0x180025ffb  lea     rdx, [rsp+0AF8h+ValueName]; lpValueName
0x180026003  mov     rcx, [rsp+0AF8h+hKey]; hKey
0x180026008  call    cs:__imp_RegQueryValueExW
0x18002600e  mov     ebx, eax
0x180026010  test    eax, eax
0x180026012  jz      short loc_180026040
0x180026014  mov     rcx, [r14]
0x180026017  mov     rax, [rcx+8]
0x18002601b  mov     r8d, ebx
0x18002601e  lea     rdx, aUnableToQueryV; "unable to query vbi reg value for size"
0x180026025  mov     rcx, r14
0x180026028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002602d  test    ebx, ebx
0x18002602f  jg      short loc_180026038
0x180026031  mov     edi, ebx
0x180026033  jmp     loc_180026484
0x180026038  movzx   edi, bx
0x18002603b  jmp     loc_18002647E
0x180026040  mov     r15d, [rsp+0AF8h+cbData]
0x180026045  xorps   xmm0, xmm0
0x180026048  movdqu  xmmword ptr [rsp+0AF8h+var_A98], xmm0
0x18002604e  mov     [rsp+0AF8h+var_A88], rsi
0x180026053  test    r15, r15
0x180026056  jz      short loc_1800260D0
0x180026058  add     r15, r15
0x18002605b  jnz     short loc_180026062
0x18002605d  mov     rax, rsi
0x180026060  jmp     short loc_1800260A0
0x180026062  cmp     r15, 1000h
0x180026069  jb      short loc_180026098
0x18002606b  lea     rcx, [r15+27h]; Size
0x18002606f  cmp     rcx, r15
0x180026072  jbe     loc_1800264C3
0x180026078  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002607d  mov     rcx, rax
0x180026080  test    rax, rax
0x180026083  jnz     short loc_18002608A
0x180026085  lea     ecx, [rax+5]
0x180026088  int     29h; Win8: RtlFailFast(ecx)
0x18002608a  add     rax, 27h ; '''
0x18002608e  and     rax, 0FFFFFFFFFFFFFFE0h
0x180026092  mov     [rax-8], rcx
0x180026096  jmp     short loc_1800260A0
0x180026098  mov     rcx, r15; Size
0x18002609b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800260a0  mov     [rsp+0AF8h+var_A98], rax
0x1800260a5  lea     rbx, [rax+r15]
0x1800260a9  mov     [rsp+0AF8h+var_A88], rbx
0x1800260ae  mov     r8, r15; Size
0x1800260b1  xor     edx, edx; Val
0x1800260b3  mov     rcx, rax; void *
0x1800260b6  call    memset_0
0x1800260bb  mov     [rsp+0AF8h+var_A98+8], rbx
0x1800260c0  mov     qword ptr [rsp+0AF8h+cchValueName], rsi
0x1800260c5  lea     rcx, [rsp+0AF8h+cchValueName]
0x1800260ca  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x1800260cf  nop
0x1800260d0  mov     rax, [rsp+0AF8h+var_A98]
0x1800260d5  lea     rcx, [rsp+0AF8h+cbData]
0x1800260da  mov     [rsp+0AF8h+lpType], rcx; lpcbData
0x1800260df  mov     [rsp+0AF8h+phkResult], rax; lpData
0x1800260e4  xor     r9d, r9d; lpType
0x1800260e7  xor     r8d, r8d; lpReserved
0x1800260ea  lea     rdx, [rsp+0AF8h+ValueName]; lpValueName
0x1800260f2  mov     rcx, [rsp+0AF8h+hKey]; hKey
0x1800260f7  call    cs:__imp_RegQueryValueExW
0x1800260fd  mov     ebx, eax
0x1800260ff  test    eax, eax
0x180026101  jz      short loc_18002613D
0x180026103  mov     rcx, [r14]
0x180026106  mov     rax, [rcx+8]
0x18002610a  mov     r8d, ebx
0x18002610d  lea     rdx, aUnableToQueryV_0; "unable to query vbi reg value for data"
0x180026114  mov     rcx, r14
0x180026117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002611c  test    ebx, ebx
0x18002611e  jg      short loc_180026124
0x180026120  mov     edi, ebx
0x180026122  jmp     short loc_18002612D
0x180026124  movzx   edi, bx
0x180026127  or      edi, 80070000h
0x18002612d  lea     rcx, [rsp+0AF8h+var_A98]
0x180026132  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180026137  nop
0x180026138  jmp     loc_180026484
0x18002613d  mov     r15, rsi
0x180026140  mov     r12, [rsp+0AF8h+var_A98]
0x180026145  mov     rbx, r13
0x180026148  inc     rbx
0x18002614b  cmp     [r12+rbx*2], si
0x180026150  jnz     short loc_180026148
0x180026152  mov     ecx, [rsp+0AF8h+cbData]
0x180026156  test    rbx, rbx
0x180026159  jz      loc_180026414
0x18002615f  mov     eax, ecx
0x180026161  cmp     r15, rax
0x180026164  jnb     loc_180026414
0x18002616a  xor     edx, edx; Val
0x18002616c  mov     r8d, 830h; Size
0x180026172  lea     rcx, [rsp+0AF8h+Src]; void *
0x18002617a  call    memset_0
0x18002617f  mov     [rsp+0AF8h+var_860], 53445352h
0x18002618a  lea     r12, [r12+r15*2]
0x18002618e  lea     rdx, asc_18002EF00; "@"
0x180026195  mov     rcx, r12; Str
0x180026198  call    cs:__imp_wcsstr
0x18002619e  mov     qword ptr [rsp+0AF8h+cchValueName], rax
0x1800261a3  test    rax, rax
0x1800261a6  jnz     short loc_1800261D6
0x1800261a8  mov     rax, [r14]
0x1800261ab  mov     r8, r12
0x1800261ae  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x1800261b5  mov     rcx, r14
0x1800261b8  mov     rax, [rax+8]
0x1800261bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261c1  mov     edi, 80004005h
0x1800261c6  lea     rcx, [rsp+0AF8h+var_A98]
0x1800261cb  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800261d0  nop
0x1800261d1  jmp     loc_180026484
0x1800261d6  lea     rdx, asc_18002EF48; "}"
0x1800261dd  mov     rcx, rax; Str
0x1800261e0  call    cs:__imp_wcsstr
0x1800261e6  mov     r13, rax
0x1800261e9  test    rax, rax
0x1800261ec  jnz     short loc_18002621C
0x1800261ee  mov     rax, [r14]
0x1800261f1  mov     r8, r12
0x1800261f4  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x1800261fb  mov     rcx, r14
0x1800261fe  mov     rax, [rax+8]
0x180026202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026207  mov     edi, 80004005h
0x18002620c  lea     rcx, [rsp+0AF8h+var_A98]
0x180026211  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180026216  nop
0x180026217  jmp     loc_180026484
0x18002621c  lea     rcx, [rax+2]
0x180026220  lea     rax, [rbx-1]
0x180026224  lea     rax, [r12+rax*2]
0x180026228  cmp     rcx, rax
0x18002622b  jb      short loc_18002625B
0x18002622d  mov     rax, [r14]
0x180026230  mov     r8, r12
0x180026233  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x18002623a  mov     rcx, r14
0x18002623d  mov     rax, [rax+8]
0x180026241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026246  mov     edi, 80004005h
0x18002624b  lea     rcx, [rsp+0AF8h+var_A98]
0x180026250  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180026255  nop
0x180026256  jmp     loc_180026484
0x18002625b  lea     rax, [rcx+2]
0x18002625f  mov     [rsp+0AF8h+var_A78], rax
0x180026267  lea     rdx, asc_18002EF4C; " "
0x18002626e  mov     rcx, rax; Str
0x180026271  call    cs:__imp_wcsstr
0x180026277  mov     [rsp+0AF8h+var_A70], rax
0x18002627f  mov     r8, r12
0x180026282  test    rax, rax
0x180026285  jnz     short loc_1800262B2
0x180026287  mov     rax, [r14]
0x18002628a  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x180026291  mov     rcx, r14
0x180026294  mov     rax, [rax+8]
0x180026298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002629d  mov     edi, 80004005h
0x1800262a2  lea     rcx, [rsp+0AF8h+var_A98]
0x1800262a7  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800262ac  nop
0x1800262ad  jmp     loc_180026484
0x1800262b2  mov     rax, qword ptr [rsp+0AF8h+cchValueName]
0x1800262b7  mov     [rax], si
0x1800262ba  mov     edx, 104h
0x1800262bf  lea     rcx, [rsp+0AF8h+Src]
0x1800262c7  call    cs:__imp__o_wcscpy_s
0x1800262cd  mov     [r13+0], si
0x1800262d2  add     qword ptr [rsp+0AF8h+cchValueName], 4
0x1800262d8  lea     rdx, [rsp+0AF8h+cchValueName]
0x1800262dd  lea     rcx, [rsp+0AF8h+var_85C]
0x1800262e5  call    ??$string_to_guid@PEAG@tlx@@YAPEAGPEAU_GUID@@AEBQEAG@Z; tlx::string_to_guid<ushort *>(_GUID *,ushort * const &)
0x1800262ea  test    rax, rax
0x1800262ed  jnz     short loc_18002631D
0x1800262ef  mov     rax, [r14]
0x1800262f2  mov     r8, r12
0x1800262f5  lea     rdx, aMalformedVbiDb; "malformed VBI Dbg Id entry: %s"
0x1800262fc  mov     rcx, r14
0x1800262ff  mov     rax, [rax+8]
0x180026303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026308  mov     edi, 80004005h
0x18002630d  lea     rcx, [rsp+0AF8h+var_A98]
0x180026312  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180026317  nop
0x180026318  jmp     loc_180026484
0x18002631d  mov     rcx, [rsp+0AF8h+var_A78]
0x180026325  call    cs:__imp__o__wtoi
0x18002632b  mov     [rsp+0AF8h+var_84C], eax
0x180026332  mov     r8, [rsp+0AF8h+var_A70]
0x18002633a  add     r8, 2; lpWideCharStr
0x18002633e  mov     [rsp+0AF8h+lpcbData], rsi; lpUsedDefaultChar
0x180026343  mov     [rsp+0AF8h+lpData], rsi; lpDefaultChar
0x180026348  mov     dword ptr [rsp+0AF8h+lpType], 30Ch; cbMultiByte
0x180026350  lea     rax, [rsp+0AF8h+MultiByteStr]
0x180026358  mov     [rsp+0AF8h+phkResult], rax; lpMultiByteStr
0x18002635d  or      r13, 0FFFFFFFFFFFFFFFFh
0x180026361  mov     r9d, r13d; cchWideChar
0x180026364  xor     edx, edx; dwFlags
0x180026366  xor     ecx, ecx; CodePage
0x180026368  call    cs:__imp_WideCharToMultiByte
0x18002636e  test    eax, eax
0x180026370  jle     short loc_1800263E9
0x180026372  mov     rdx, cs:qword_180036EB0
0x180026379  cmp     rdx, cs:qword_180036EB8
0x180026380  jz      short loc_1800263A5
0x180026382  mov     rcx, rdx; void *
0x180026385  lea     rdx, [rsp+0AF8h+Src]; Src
0x18002638d  mov     r8d, 830h; Size
0x180026393  call    memcpy_0
0x180026398  add     cs:qword_180036EB0, 830h
0x1800263a3  jmp     short loc_1800263B2
0x1800263a5  lea     r8, [rsp+0AF8h+Src]
0x1800263ad  call    ??$_Emplace_reallocate@AEBUPdbInfoRecord@Xbox@Microsoft@@@?$vector@UPdbInfoRecord@Xbox@Microsoft@@V?$allocator@UPdbInfoRecord@Xbox@Microsoft@@@std@@@std@@AEAAPEAUPdbInfoRecord@Xbox@Microsoft@@QEAU234@AEBU234@@Z; std::vector<Microsoft::Xbox::PdbInfoRecord>::_Emplace_reallocate<Microsoft::Xbox::PdbInfoRecord const &>(Microsoft::Xbox::PdbInfoRecord * const,Microsoft::Xbox::PdbInfoRecord const &)
0x1800263b2  inc     r15
0x1800263b5  add     r15, rbx
0x1800263b8  mov     r12, [rsp+0AF8h+var_A98]
0x1800263bd  cmp     [r12+r15*2], si
0x1800263c2  jnz     short loc_1800263C7
0x1800263c4  inc     r15
0x1800263c7  mov     ecx, [rsp+0AF8h+cbData]
0x1800263cb  cmp     r15, rcx
0x1800263ce  jnb     loc_180026156
0x1800263d4  lea     rax, [r12+r15*2]
0x1800263d8  mov     rbx, r13
0x1800263db  inc     rbx
0x1800263de  cmp     [rax+rbx*2], si
0x1800263e2  jnz     short loc_1800263DB
0x1800263e4  jmp     loc_180026156
  ... truncated ...
```

# CMFSourceFilter::_CheckBytes(HKEY__ *,ushort const *,_GUID &)

- ea: `0x180024f00`
- end: `0x1800253ec`
- name: `?_CheckBytes@CMFSourceFilter@@QEAAHPEAUHKEY__@@PEBGAEAU_GUID@@@Z`
- size: `1260`
- prototype: `int(CMFSourceFilter *__hidden this, HKEY, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180024bcc`

## callees

- `0x180002820`
- `0x1800140b0`
- `0x180024f00`
- `0x1800253f4`
- `0x1800256c0`
- `0x1800256fc`
- `0x180025750`
- `0x180073d4c`
- `0x180073d58`
- `0x180074160`
- `0x18007c8e8`
- `0x180092a00`
- `0x1800c9010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180025392`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180025392`
- `OLEAUT32!__imp_SysFreeString` at `0x180025074`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252e7`
- `OLEAUT32!__imp_SysFreeString` at `0x180025074`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252e7`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180025265`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180025265`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002510e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002510e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024f71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180024f71`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180024fdd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180024fdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002505b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800252c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002537b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002505b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800252c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002537b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002524a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002524a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002514a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002514a`

## pseudocode

```c
__int64 __fastcall CMFSourceFilter::_CheckBytes(
        CMFSourceFilter *this,
        HKEY a2,
        const unsigned __int16 *a3,
        struct _GUID *a4)
{
  int v6; // ebx
  DWORD v8; // ecx
  const char *v9; // rdx
  __int64 v10; // r8
  CallStackTracing *v11; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  unsigned int v15; // edx
  void *v16; // rcx
  BOOL v17; // ebx
  unsigned int v18; // edi
  void *v19; // rax
  void *v20; // rsi
  void *v21; // rbx
  void *v22; // r14
  unsigned int i; // edx
  _BYTE v24[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+64h] [rbp-9Ch] BYREF
  void *v26[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v27; // [rsp+78h] [rbp-88h]
  unsigned int v28; // [rsp+7Ch] [rbp-84h]
  void *v29; // [rsp+80h] [rbp-80h]
  struct _FILETIME ftLastWriteTime; // [rsp+88h] [rbp-78h] BYREF
  void **v31; // [rsp+90h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  DWORD dwIndex; // [rsp+A0h] [rbp-60h]
  _BYTE v34[60]; // [rsp+A4h] [rbp-5Ch] BYREF
  BSTR bstrString; // [rsp+E0h] [rbp-20h]
  DWORD cSubKeys; // [rsp+E8h] [rbp-18h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+ECh] [rbp-14h] BYREF
  DWORD cValues; // [rsp+F0h] [rbp-10h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+F4h] [rbp-Ch] BYREF
  DWORD cbMaxValueLen; // [rsp+F8h] [rbp-8h] BYREF
  DWORD Type; // [rsp+100h] [rbp+0h] BYREF
  DWORD cbData; // [rsp+104h] [rbp+4h] BYREF
  void *Block; // [rsp+108h] [rbp+8h]
  _BYTE v44[32]; // [rsp+110h] [rbp+10h] BYREF

  v31 = &CKey::`vftable';
  hKey = 0;
  dwIndex = 0;
  cSubKeys = 0;
  bstrString = (BSTR)v34;
  cValues = 0;
  v6 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey);
  if ( !v6 )
  {
    cbSecurityDescriptor = 0;
    ftLastWriteTime = 0;
    v6 = RegQueryInfoKeyW(
           hKey,
           0,
           0,
           0,
           &cSubKeys,
           &cbMaxSubKeyLen,
           0,
           &cValues,
           &cbMaxValueNameLen,
           &cbMaxValueLen,
           &cbSecurityDescriptor,
           &ftLastWriteTime);
    if ( v6 )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
  }
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  cbData = 0;
  v31 = &CEnumValue::`vftable';
  Block = v44;
  if ( v6 < 0 )
    goto LABEL_10;
  if ( cbMaxValueNameLen + 1 > 0x1E )
  {
    bstrString = SysAllocStringLen(0, cbMaxValueNameLen);
    if ( !bstrString )
      v6 = -2147024882;
  }
  if ( (cbMaxValueLen <= 0x1E || (Block = operator new[](cbMaxValueLen)) != 0) && v6 >= 0 )
  {
    do
    {
LABEL_20:
      v8 = dwIndex;
      do
      {
        if ( v8 >= cValues
          || (cbSecurityDescriptor = cbMaxValueNameLen + 1,
              cbData = cbMaxValueLen,
              RegEnumValueW(hKey, v8, bstrString, &cbSecurityDescriptor, 0, &Type, (LPBYTE)Block, &cbData)) )
        {
          CEnumValue::~CEnumValue((CEnumValue *)&v31);
          return 0;
        }
        v8 = ++dwIndex;
      }
      while ( Type != 1 );
    }
    while ( CompareStringOrdinal(bstrString, -1, L"Source Filter", 13, 1) == 2 );
    v11 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v11 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v11);
      v13 = *((unsigned int *)ThreadRelativeContext + 497);
      if ( (unsigned int)v13 < *((_DWORD *)ThreadRelativeContext + 498) )
      {
        v14 = 2 * v13;
        v9 = "CMFSourceFilter::_CheckBytes";
        *((_QWORD *)ThreadRelativeContext + v14) = "CMFSourceFilter::_CheckBytes";
        *((_DWORD *)ThreadRelativeContext + 2 * v14 + 2) = 6059;
      }
      ++*((_DWORD *)ThreadRelativeContext + 497);
    }
    if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 17), v9, v10, bstrString);
    *(_OWORD *)v26 = 0;
    v29 = Block;
    while ( (unsigned int)CExtractQuadruplets::Next((CExtractQuadruplets *)v26) )
    {
      v18 = v27;
      v19 = operator new[](v27);
      v20 = v26[1];
      v21 = v19;
      v22 = v26[0];
      if ( !v19 )
        goto LABEL_54;
      if ( (*(unsigned int (__fastcall **)(char *, _QWORD, _QWORD, void *))(*((_QWORD *)this + 32) + 56LL))(
             (char *)this + 256,
             v28,
             v18,
             v19) )
      {
LABEL_53:
        operator delete(v21);
LABEL_54:
        operator delete(v22);
        operator delete(v20);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
        goto LABEL_20;
      }
      for ( i = 0; i < v18; ++i )
      {
        if ( ((unsigned __int8)(*((_BYTE *)v20 + i) ^ *((_BYTE *)v21 + i)) & *((_BYTE *)v22 + i)) != 0 )
          goto LABEL_53;
      }
      operator delete(v21);
    }
    dwIndex = 0;
    do
    {
      if ( !(unsigned int)CEnumValue::Next((CEnumValue *)&v31, v15) )
      {
        v16 = v26[0];
        *a4 = GUID_00000000_0000_0000_0000_000000000000;
        operator delete(v16);
        operator delete(v26[1]);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
        v31 = &CEnumValue::`vftable';
        if ( Block != v44 )
          operator delete(Block);
        CKey::~CKey((CKey *)&v31);
        return 1;
      }
    }
    while ( lstrcmpiW(L"Source Filter", bstrString) );
    v17 = IIDFromString((LPCOLESTR)Block, a4) >= 0;
    operator delete(v26[0]);
    operator delete(v26[1]);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v24);
    v31 = &CEnumValue::`vftable';
    if ( Block != v44 )
      operator delete(Block);
    v31 = &CKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    if ( bstrString != (BSTR)v34 )
      SysFreeString(bstrString);
    return v17;
  }
  else
  {
LABEL_10:
    v31 = &CEnumValue::`vftable';
    if ( Block != v44 )
      operator delete(Block);
    v31 = &CKey::`vftable';
    if ( hKey )
      RegCloseKey(hKey);
    if ( bstrString != (BSTR)v34 )
      SysFreeString(bstrString);
    return 0;
  }
}

```

## disassembly

```asm
0x180024f00  push    rbp
0x180024f02  push    rbx
0x180024f03  push    rsi
0x180024f04  push    rdi
0x180024f05  push    r12
0x180024f07  push    r13
0x180024f09  push    r14
0x180024f0b  push    r15
0x180024f0d  lea     rbp, [rsp-48h]
0x180024f12  sub     rsp, 148h
0x180024f19  mov     rax, cs:__security_cookie
0x180024f20  xor     rax, rsp
0x180024f23  mov     [rbp+80h+var_50], rax
0x180024f27  mov     r13, rcx
0x180024f2a  lea     rsi, ??_7CKey@@6B@; const CKey::`vftable'
0x180024f31  xor     r12d, r12d
0x180024f34  mov     [rbp+80h+var_F0], rsi
0x180024f38  mov     r10, r8
0x180024f3b  mov     [rbp+80h+hKey], r12
0x180024f3f  mov     rax, rdx
0x180024f42  mov     [rbp+80h+dwIndex], r12d
0x180024f46  lea     rcx, [rbp+80h+var_DC]
0x180024f4a  mov     [rbp+80h+cSubKeys], r12d
0x180024f4e  mov     [rbp+80h+bstrString], rcx
0x180024f52  mov     r15, r9
0x180024f55  lea     rcx, [rbp+80h+hKey]
0x180024f59  mov     [rbp+80h+cValues], r12d
0x180024f5d  mov     [rsp+180h+phkResult], rcx; phkResult
0x180024f62  mov     r9d, 20019h; samDesired
0x180024f68  mov     rcx, rax; hKey
0x180024f6b  xor     r8d, r8d; ulOptions
0x180024f6e  mov     rdx, r10; lpSubKey
0x180024f71  call    cs:__imp_RegOpenKeyExW
0x180024f78  nop     dword ptr [rax+rax+00h]
0x180024f7d  mov     ebx, eax
0x180024f7f  test    eax, eax
0x180024f81  jnz     short loc_180024FF3
0x180024f83  mov     rcx, [rbp+80h+hKey]; hKey
0x180024f87  lea     rax, [rbp+80h+ftLastWriteTime]
0x180024f8b  mov     [rsp+180h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180024f90  xor     r9d, r9d; lpReserved
0x180024f93  lea     rax, [rsp+180h+cbSecurityDescriptor]
0x180024f98  mov     [rsp+180h+cbSecurityDescriptor], r12d
0x180024f9d  mov     [rsp+180h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x180024fa2  xor     r8d, r8d; lpcchClass
0x180024fa5  lea     rax, [rbp+80h+cbMaxValueLen]
0x180024fa9  mov     qword ptr [rbp+80h+ftLastWriteTime.dwLowDateTime], r12
0x180024fad  mov     [rsp+180h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180024fb2  xor     edx, edx; lpClass
0x180024fb4  lea     rax, [rbp+80h+cbMaxValueNameLen]
0x180024fb8  mov     [rsp+180h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180024fbd  lea     rax, [rbp+80h+cValues]
0x180024fc1  mov     [rsp+180h+lpcValues], rax; lpcValues
0x180024fc6  lea     rax, [rbp+80h+cbMaxSubKeyLen]
0x180024fca  mov     [rsp+180h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180024fcf  mov     [rsp+180h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180024fd4  lea     rax, [rbp+80h+cSubKeys]
0x180024fd8  mov     [rsp+180h+phkResult], rax; lpcSubKeys
0x180024fdd  call    cs:__imp_RegQueryInfoKeyW
0x180024fe4  nop     dword ptr [rax+rax+00h]
0x180024fe9  mov     ebx, eax
0x180024feb  test    eax, eax
0x180024fed  jnz     loc_180025377
0x180024ff3  test    ebx, ebx
0x180024ff5  jle     short loc_180025000
0x180024ff7  movzx   ebx, bx
0x180024ffa  or      ebx, 80070000h
0x180025000  mov     [rbp+80h+cbData], r12d
0x180025004  lea     rdi, ??_7CEnumValue@@6B@; const CEnumValue::`vftable'
0x18002500b  mov     [rbp+80h+var_F0], rdi
0x18002500f  lea     rax, [rbp+80h+var_70]
0x180025013  mov     [rbp+80h+Block], rax
0x180025017  test    ebx, ebx
0x180025019  js      short loc_180025038
0x18002501b  mov     edx, [rbp+80h+cbMaxValueNameLen]; ui
0x18002501e  lea     eax, [rdx+1]
0x180025021  cmp     eax, 1Eh
0x180025024  ja      loc_180025390
0x18002502a  cmp     [rbp+80h+cbMaxValueLen], 1Eh
0x18002502e  ja      short loc_1800250AE
0x180025030  test    ebx, ebx
0x180025032  jns     loc_1800250C8
0x180025038  mov     rcx, [rbp+80h+Block]; Block
0x18002503c  lea     rax, [rbp+80h+var_70]
0x180025040  mov     [rbp+80h+var_F0], rdi
0x180025044  cmp     rcx, rax
0x180025047  jz      short loc_18002504E
0x180025049  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002504e  mov     rcx, [rbp+80h+hKey]; hKey
0x180025052  mov     [rbp+80h+var_F0], rsi
0x180025056  test    rcx, rcx
0x180025059  jz      short loc_180025067
0x18002505b  call    cs:__imp_RegCloseKey
0x180025062  nop     dword ptr [rax+rax+00h]
0x180025067  mov     rcx, [rbp+80h+bstrString]; bstrString
0x18002506b  lea     rax, [rbp+80h+var_DC]
0x18002506f  cmp     rcx, rax
0x180025072  jz      short loc_18002508B
0x180025074  call    cs:__imp_SysFreeString
0x18002507b  nop     dword ptr [rax+rax+00h]
0x180025080  jmp     short loc_18002508B
0x180025082  lea     rcx, [rbp+80h+var_F0]; this
0x180025086  call    ??1CEnumValue@@QEAA@XZ; CEnumValue::~CEnumValue(void)
0x18002508b  xor     eax, eax
0x18002508d  mov     rcx, [rbp+80h+var_50]
0x180025091  xor     rcx, rsp; StackCookie
0x180025094  call    __security_check_cookie
0x180025099  add     rsp, 148h
0x1800250a0  pop     r15
0x1800250a2  pop     r14
0x1800250a4  pop     r13
0x1800250a6  pop     r12
0x1800250a8  pop     rdi
0x1800250a9  pop     rsi
0x1800250aa  pop     rbx
0x1800250ab  pop     rbp
0x1800250ac  retn
0x1800250ae  mov     ecx, [rbp+80h+cbMaxValueLen]; unsigned __int64
0x1800250b1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800250b6  mov     [rbp+80h+Block], rax
0x1800250ba  test    rax, rax
0x1800250bd  jnz     loc_180025030
0x1800250c3  jmp     loc_180025038
0x1800250c8  mov     ecx, [rbp+80h+dwIndex]
0x1800250cb  cmp     ecx, [rbp+80h+cValues]
0x1800250ce  jnb     short loc_180025082
0x1800250d0  mov     eax, [rbp+80h+cbMaxValueNameLen]
0x1800250d3  lea     r9, [rsp+180h+cbSecurityDescriptor]; lpcchValueName
0x1800250d8  mov     r8, [rbp+80h+bstrString]; lpValueName
0x1800250dc  inc     eax
0x1800250de  mov     [rsp+180h+cbSecurityDescriptor], eax
0x1800250e2  mov     edx, ecx; dwIndex
0x1800250e4  mov     eax, [rbp+80h+cbMaxValueLen]
0x1800250e7  mov     rcx, [rbp+80h+hKey]; hKey
0x1800250eb  mov     [rbp+80h+cbData], eax
0x1800250ee  lea     rax, [rbp+80h+cbData]
0x1800250f2  mov     [rsp+180h+lpcValues], rax; lpcbData
0x1800250f7  mov     rax, [rbp+80h+Block]
0x1800250fb  mov     [rsp+180h+lpcbMaxClassLen], rax; lpData
0x180025100  lea     rax, [rbp+80h+Type]
0x180025104  mov     [rsp+180h+lpcbMaxSubKeyLen], rax; lpType
0x180025109  mov     [rsp+180h+phkResult], r12; lpReserved
0x18002510e  call    cs:__imp_RegEnumValueW
0x180025115  nop     dword ptr [rax+rax+00h]
0x18002511a  test    eax, eax
0x18002511c  jnz     loc_180025082
0x180025122  mov     ecx, [rbp+80h+dwIndex]
0x180025125  inc     ecx
0x180025127  cmp     [rbp+80h+Type], 1
0x18002512b  mov     [rbp+80h+dwIndex], ecx
0x18002512e  jnz     short loc_1800250CB
0x180025130  mov     rcx, [rbp+80h+bstrString]; lpString1
0x180025134  lea     r9d, [rax+0Dh]; cchCount2
0x180025138  lea     r8, String1; "Source Filter"
0x18002513f  mov     dword ptr [rsp+180h+phkResult], 1; bIgnoreCase
0x180025147  or      edx, 0FFFFFFFFh; cchCount1
0x18002514a  call    cs:__imp_CompareStringOrdinal
0x180025151  nop     dword ptr [rax+rax+00h]
0x180025156  cmp     eax, 2
0x180025159  jz      loc_1800250C8
0x18002515f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180025166  test    rcx, rcx
0x180025169  jz      loc_1800253B2
0x18002516f  cmp     [rcx+8], r12b
0x180025173  jz      short loc_1800251A4
0x180025175  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002517a  mov     ecx, [rax+7C4h]
0x180025180  cmp     ecx, [rax+7C8h]
0x180025186  jnb     short loc_18002519E
0x180025188  add     rcx, rcx
0x18002518b  lea     rdx, aCmfsourcefilte; "CMFSourceFilter::_CheckBytes"
0x180025192  mov     [rax+rcx*8], rdx
0x180025196  mov     dword ptr [rax+rcx*8+8], 17ABh
0x18002519e  inc     dword ptr [rax+7C4h]
0x1800251a4  cmp     cs:byte_1800EACCB, 20h ; ' '
0x1800251ab  jnb     loc_1800253C3
0x1800251b1  mov     rax, [rbp+80h+Block]
0x1800251b5  xorps   xmm0, xmm0
0x1800251b8  movdqu  xmmword ptr [rsp+180h+var_118], xmm0
0x1800251be  mov     [rbp+80h+var_100], rax
0x1800251c2  lea     rcx, [rsp+180h+var_118]; this
0x1800251c7  call    ?Next@CExtractQuadruplets@@QEAAHXZ; CExtractQuadruplets::Next(void)
0x1800251cc  test    eax, eax
0x1800251ce  jnz     loc_1800252F5
0x1800251d4  mov     [rbp+80h+dwIndex], r12d
0x1800251d8  lea     rcx, [rbp+80h+var_F0]; this
0x1800251dc  call    ?Next@CEnumValue@@QEAAHK@Z; CEnumValue::Next(ulong)
0x1800251e1  test    eax, eax
0x1800251e3  jnz     short loc_18002523F
0x1800251e5  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800251ec  mov     rcx, [rsp+180h+var_118]; Block
0x1800251f1  movdqu  xmmword ptr [r15], xmm0
0x1800251f6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800251fb  mov     rcx, [rsp+180h+var_118+8]; Block
0x180025200  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025205  lea     rcx, [rsp+180h+var_120]; this
0x18002520a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002520f  mov     rcx, [rbp+80h+Block]; Block
0x180025213  lea     rdx, [rbp+80h+var_70]
0x180025217  lea     rax, ??_7CEnumValue@@6B@; const CEnumValue::`vftable'
0x18002521e  mov     [rbp+80h+var_F0], rax
0x180025222  cmp     rcx, rdx
0x180025225  jz      short loc_18002522C
0x180025227  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002522c  lea     rcx, [rbp+80h+var_F0]; this
0x180025230  call    ??1CKey@@QEAA@XZ; CKey::~CKey(void)
0x180025235  mov     eax, 1
0x18002523a  jmp     loc_18002508D
0x18002523f  mov     rdx, [rbp+80h+bstrString]; lpString2
0x180025243  lea     rcx, String1; "Source Filter"
0x18002524a  call    cs:__imp_lstrcmpiW
0x180025251  nop     dword ptr [rax+rax+00h]
0x180025256  test    eax, eax
0x180025258  jnz     loc_1800251D8
0x18002525e  mov     rcx, [rbp+80h+Block]; lpsz
0x180025262  mov     rdx, r15; lpiid
0x180025265  call    cs:__imp_IIDFromString
0x18002526c  nop     dword ptr [rax+rax+00h]
0x180025271  mov     rcx, [rsp+180h+var_118]; Block
0x180025276  mov     ebx, eax
0x180025278  not     ebx
0x18002527a  shr     ebx, 1Fh
0x18002527d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025282  mov     rcx, [rsp+180h+var_118+8]; Block
0x180025287  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002528c  lea     rcx, [rsp+180h+var_120]; this
0x180025291  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180025296  mov     rcx, [rbp+80h+Block]; Block
0x18002529a  lea     rax, ??_7CEnumValue@@6B@; const CEnumValue::`vftable'
0x1800252a1  mov     [rbp+80h+var_F0], rax
0x1800252a5  lea     rax, [rbp+80h+var_70]
0x1800252a9  cmp     rcx, rax
0x1800252ac  jz      short loc_1800252B3
0x1800252ae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800252b3  mov     rcx, [rbp+80h+hKey]; hKey
0x1800252b7  lea     rax, ??_7CKey@@6B@; const CKey::`vftable'
0x1800252be  mov     [rbp+80h+var_F0], rax
0x1800252c2  test    rcx, rcx
0x1800252c5  jz      short loc_1800252D3
0x1800252c7  call    cs:__imp_RegCloseKey
0x1800252ce  nop     dword ptr [rax+rax+00h]
0x1800252d3  mov     rcx, [rbp+80h+bstrString]; bstrString
0x1800252d7  lea     rax, [rbp+80h+var_DC]
0x1800252db  cmp     rcx, rax
0x1800252de  jnz     short loc_1800252E7
0x1800252e0  mov     eax, ebx
0x1800252e2  jmp     loc_18002508D
0x1800252e7  call    cs:__imp_SysFreeString
0x1800252ee  nop     dword ptr [rax+rax+00h]
0x1800252f3  jmp     short loc_1800252E0
0x1800252f5  mov     edi, dword ptr [rsp+180h+var_108]
0x1800252f9  mov     ecx, edi; unsigned __int64
0x1800252fb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180025300  mov     rsi, [rsp+180h+var_118+8]
0x180025305  mov     rbx, rax
0x180025308  mov     r14, [rsp+180h+var_118]
0x18002530d  test    rax, rax
0x180025310  jz      short loc_180025354
0x180025312  mov     edx, dword ptr [rsp+180h+var_108+4]
0x180025316  lea     rcx, [r13+100h]
0x18002531d  mov     r8, [rcx]
0x180025320  mov     r9, rbx
0x180025323  mov     rax, [r8+38h]
0x180025327  mov     r8d, edi
0x18002532a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002532f  test    eax, eax
0x180025331  jnz     short loc_18002534C
0x180025333  mov     edx, r12d
0x180025336  cmp     edx, edi
0x180025338  jnb     loc_1800253DF
0x18002533e  mov     ecx, edx
0x180025340  mov     al, [rcx+rbx]
0x180025343  xor     al, [rcx+rsi]
0x180025346  test    [rcx+r14], al
0x18002534a  jz      short loc_180025373
0x18002534c  mov     rcx, rbx; Block
0x18002534f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025354  mov     rcx, r14; Block
0x180025357  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002535c  mov     rcx, rsi; Block
0x18002535f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180025364  lea     rcx, [rsp+180h+var_120]; this
0x180025369  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002536e  jmp     loc_1800250C8
0x180025373  inc     edx
0x180025375  jmp     short loc_180025336
0x180025377  mov     rcx, [rbp+80h+hKey]; hKey
0x18002537b  call    cs:__imp_RegCloseKey
0x180025382  nop     dword ptr [rax+rax+00h]
0x180025387  mov     [rbp+80h+hKey], r12
0x18002538b  jmp     loc_180024FF3
0x180025390  xor     ecx, ecx; strIn
0x180025392  call    cs:__imp_SysAllocStringLen
0x180025399  nop     dword ptr [rax+rax+00h]
0x18002539e  test    rax, rax
0x1800253a1  mov     [rbp+80h+bstrString], rax
0x1800253a5  mov     ecx, 8007000Eh
0x1800253aa  cmovz   ebx, ecx
0x1800253ad  jmp     loc_18002502A
0x1800253b2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
  ... truncated ...
```

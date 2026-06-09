# EnrollmentInfoEnumerator::GetAllEnrollmentIDsFiltered(ulong *,ushort * * *,EnrollmentStateTag,EnrollmentStateTag,unsigned __int64,ushort const *,int,int)

- ea: `0x180019044`
- end: `0x18001950b`
- name: `?GetAllEnrollmentIDsFiltered@EnrollmentInfoEnumerator@@AEAAJPEAKPEAPEAPEAGW4EnrollmentStateTag@@2_KPEBGHH@Z`
- size: `1223`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019514`

## callees

- `0x180001c60`
- `0x1800026d8`
- `0x1800051d8`
- `0x180006574`
- `0x1800075e8`
- `0x18000c5dc`
- `0x180011828`
- `0x1800188f8`
- `0x180018bf0`
- `0x180018c14`
- `0x180018f30`
- `0x180019044`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800193c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800193c9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800193e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800193e8`
- `OLEAUT32!__imp_SysAllocString` at `0x180019400`
- `OLEAUT32!__imp_SysAllocString` at `0x180019400`
- `OLEAUT32!__imp_SysFreeString` at `0x180019476`
- `OLEAUT32!__imp_SysFreeString` at `0x180019476`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800192df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001932a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800192df`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001932a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180019133`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180019133`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180019238`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180019238`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800194a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800194b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800194a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800194b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001917b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800191df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001917b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800191df`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EnrollmentInfoEnumerator::GetAllEnrollmentIDsFiltered(
        unsigned int a1,
        DWORD *a2,
        _QWORD *a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9)
{
  DWORD v11; // esi
  int v12; // eax
  signed int v13; // ebx
  LSTATUS InfoKeyW; // eax
  size_t v15; // rbx
  _QWORD *v16; // rax
  _QWORD *v17; // r14
  WCHAR *v18; // rdi
  __int64 v19; // rcx
  DWORD v20; // r12d
  LSTATUS v21; // eax
  const unsigned __int16 *EnrollmentsRootKey; // rax
  unsigned int v23; // edx
  unsigned __int16 *v24; // rcx
  __int64 v25; // r9
  const WCHAR *v26; // rdx
  unsigned __int8 v27; // si
  int v29; // eax
  __int64 v30; // r8
  BSTR v31; // rax
  OLECHAR *v32; // rcx
  SIZE_T cb; // [rsp+60h] [rbp-A0h] BYREF
  SIZE_T pvData; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v36; // [rsp+70h] [rbp-90h] BYREF
  HKEY hkey; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v38; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchName; // [rsp+90h] [rbp-70h] BYREF
  DWORD pcbData; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD v42; // [rsp+98h] [rbp-68h] BYREF
  int v43; // [rsp+9Ch] [rbp-64h]
  HKEY v44; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h]
  _QWORD v46[2]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  v43 = a4;
  v45 = a7;
  v11 = 0;
  cb = 0;
  pvData = 0;
  hKey = 0;
  v44 = 0;
  v46[0] = 0;
  hkey = 0;
  SubKey[0] = 0;
  if ( !a2 || !a3 )
  {
    v13 = -2147024809;
    goto LABEL_57;
  }
  *a2 = 0;
  *a3 = 0;
  v12 = EEDBManager::OpenEnrollmentsHKEY(a1, &v44);
  v13 = v12;
  if ( v12 == -2147024894 )
  {
    v13 = 0;
    goto LABEL_57;
  }
  if ( v12 < 0 )
    goto LABEL_57;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    v44);
  InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, (LPDWORD)&pvData + 1, (LPDWORD)&cb + 1, 0, 0, 0, 0, 0, 0);
  v13 = InfoKeyW;
  if ( InfoKeyW )
  {
    if ( InfoKeyW > 0 )
      v13 = (unsigned __int16)InfoKeyW | 0x80070000;
    goto LABEL_57;
  }
  v13 = ULongLongToULong(8LL * HIDWORD(pvData), (unsigned int *)&cb);
  if ( v13 < 0 )
    goto LABEL_57;
  v15 = (unsigned int)cb;
  v16 = CoTaskMemAlloc((unsigned int)cb);
  v17 = v16;
  if ( !v16 )
  {
    v13 = -2147024882;
    goto LABEL_57;
  }
  v18 = 0;
  memset_0(v16, 0, v15);
  v19 = (unsigned int)(HIDWORD(cb) + 1);
  if ( (unsigned int)v19 < HIDWORD(cb) )
  {
    HIDWORD(cb) = -1;
    v13 = -2147024362;
  }
  else
  {
    v20 = 0;
    ++HIDWORD(cb);
    v13 = ULongLongToULong(2 * v19, (unsigned int *)&pvData);
    if ( v13 >= 0 )
    {
      v18 = (WCHAR *)CoTaskMemAlloc((unsigned int)pvData);
      if ( !v18 )
      {
        v13 = -2147024882;
        goto LABEL_54;
      }
      while ( 1 )
      {
        LODWORD(cb) = v11;
        if ( v11 >= HIDWORD(pvData) )
        {
          *a2 = v20;
          *a3 = v17;
          goto LABEL_55;
        }
        cchName = HIDWORD(cb);
        *v18 = 0;
        v21 = RegEnumKeyExW(hKey, v11, v18, &cchName, 0, 0, 0, 0);
        v13 = v21;
        if ( v21 )
          break;
        EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
        v13 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", EnrollmentsRootKey, v18);
        if ( v13 < 0 )
        {
          v11 = 0;
          goto LABEL_48;
        }
        v13 = EEDBManager::OpenHKEY(SubKey, v23, &hkey);
        if ( v13 >= 0 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            v46,
            hkey);
          LODWORD(pvData) = 0;
          pcbData = 4;
          if ( !RegGetValueW(hkey, 0, L"EnrollmentState", 0x18u, 0, &pvData, &pcbData) )
          {
            v36 = 0;
            v42 = 4;
            RegGetValueW(hkey, 0, L"EnrollmentType", 0x18u, 0, &v36, &v42);
            v24 = 0;
            v38 = 0;
            v25 = v45;
            if ( v45 )
            {
              v26 = L"PartnerOpaqueID";
              if ( !a8 )
                v26 = L"AADOpaqueID";
              AllocAndGetEnrollmentString(hkey, v26, &v38);
              v24 = v38;
              v25 = v45;
            }
            if ( (_DWORD)pvData != 63 )
            {
              v27 = 0;
              if ( (_DWORD)pvData != a5 )
              {
                v27 = _bittest64(&a6, v36);
                if ( (_DWORD)pvData == v43 )
                  v27 = 1;
              }
              if ( v25 && v24 )
              {
                if ( a9 )
                {
                  v30 = -1;
                  do
                    ++v30;
                  while ( *(_WORD *)(v25 + 2 * v30) );
                  v29 = _o__wcsnicmp(v24, v25);
                }
                else
                {
                  v29 = _o__wcsicmp(v24, v25);
                }
                if ( !v29 )
                  goto LABEL_38;
              }
              if ( v27 )
              {
LABEL_38:
                v31 = SysAllocString(v18);
                v17[v20] = v31;
                v11 = 0;
                if ( !v31 )
                {
                  v13 = -2147024882;
                  CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v38);
                  goto LABEL_48;
                }
                ++v20;
              }
              v11 = cb;
            }
            CTSmartObj<unsigned short *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(&v38);
          }
        }
        ++v11;
      }
      v11 = 0;
      if ( v21 > 0 )
        v13 = (unsigned __int16)v21 | 0x80070000;
    }
LABEL_48:
    if ( v20 )
    {
      do
      {
        v32 = (OLECHAR *)v17[v11];
        if ( v32 )
        {
          SysFreeString(v32);
          v17[v11] = 0;
        }
        ++v11;
      }
      while ( v11 < v20 );
    }
  }
LABEL_54:
  CoTaskMemFree(v17);
  if ( v18 )
LABEL_55:
    CoTaskMemFree(v18);
LABEL_57:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v46);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180019044  mov     [rsp-8+arg_0], rbx
0x180019049  push    rbp
0x18001904a  push    rsi
0x18001904b  push    rdi
0x18001904c  push    r12
0x18001904e  push    r13
0x180019050  push    r14
0x180019052  push    r15
0x180019054  lea     rbp, [rsp-1E0h]
0x18001905c  sub     rsp, 2E0h
0x180019063  mov     rax, cs:__security_cookie
0x18001906a  xor     rax, rsp
0x18001906d  mov     [rbp+210h+var_40], rax
0x180019074  mov     [rbp+210h+var_274], r9d
0x180019078  mov     r15, r8
0x18001907b  mov     r13, rdx
0x18001907e  mov     rax, [rbp+210h+arg_30]
0x180019085  mov     [rbp+210h+var_268], rax
0x180019089  xor     esi, esi
0x18001908b  mov     dword ptr [rsp+310h+pvData+4], esi
0x18001908f  mov     dword ptr [rsp+310h+cb+4], esi
0x180019093  mov     dword ptr [rsp+310h+cb], esi
0x180019097  mov     dword ptr [rsp+310h+pvData], esi
0x18001909b  mov     [rbp+210h+hKey], rsi
0x18001909f  mov     [rbp+210h+var_270], rsi
0x1800190a3  mov     [rbp+210h+var_260], rsi
0x1800190a7  mov     [rsp+310h+hkey], rsi
0x1800190ac  mov     [rbp+210h+SubKey], si
0x1800190b0  test    rdx, rdx
0x1800190b3  jz      loc_1800194C6
0x1800190b9  test    r8, r8
0x1800190bc  jz      loc_1800194C6
0x1800190c2  mov     [rdx], esi
0x1800190c4  mov     [r8], rsi
0x1800190c7  lea     rdx, [rbp+210h+var_270]; HKEY *
0x1800190cb  call    ?OpenEnrollmentsHKEY@EEDBManager@@SAJKPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentsHKEY(ulong,HKEY__ * *)
0x1800190d0  mov     ebx, eax
0x1800190d2  cmp     eax, 80070002h
0x1800190d7  jnz     short loc_1800190E0
0x1800190d9  mov     ebx, esi
0x1800190db  jmp     loc_1800194CB
0x1800190e0  test    eax, eax
0x1800190e2  js      loc_1800194CB
0x1800190e8  mov     rdx, [rbp+210h+var_270]
0x1800190ec  lea     rcx, [rbp+210h+hKey]
0x1800190f0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800190f5  mov     [rsp+310h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800190fa  mov     [rsp+310h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800190ff  mov     [rsp+310h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180019104  mov     [rsp+310h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180019109  mov     [rsp+310h+lpcValues], rsi; lpcValues
0x18001910e  mov     [rsp+310h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180019113  lea     rax, [rsp+310h+cb+4]
0x180019118  mov     [rsp+310h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001911d  lea     rax, [rsp+310h+pvData+4]
0x180019122  mov     [rsp+310h+lpcSubKeys], rax; lpcSubKeys
0x180019127  xor     r9d, r9d; lpReserved
0x18001912a  xor     r8d, r8d; lpcchClass
0x18001912d  xor     edx, edx; lpClass
0x18001912f  mov     rcx, [rbp+210h+hKey]; hKey
0x180019133  call    cs:__imp_RegQueryInfoKeyW
0x18001913a  nop     dword ptr [rax+rax+00h]
0x18001913f  mov     ebx, eax
0x180019141  test    eax, eax
0x180019143  jz      short loc_180019159
0x180019145  jle     loc_1800194CB
0x18001914b  movzx   ebx, ax
0x18001914e  or      ebx, 80070000h
0x180019154  jmp     loc_1800194CB
0x180019159  mov     ecx, dword ptr [rsp+310h+pvData+4]
0x18001915d  shl     rcx, 3; unsigned __int64
0x180019161  lea     rdx, [rsp+310h+cb]; unsigned int *
0x180019166  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001916b  mov     ebx, eax
0x18001916d  test    eax, eax
0x18001916f  js      loc_1800194CB
0x180019175  mov     ebx, dword ptr [rsp+310h+cb]
0x180019179  mov     ecx, ebx; cb
0x18001917b  call    cs:__imp_CoTaskMemAlloc
0x180019182  nop     dword ptr [rax+rax+00h]
0x180019187  mov     r14, rax
0x18001918a  test    rax, rax
0x18001918d  jnz     short loc_180019199
0x18001918f  mov     ebx, 8007000Eh
0x180019194  jmp     loc_1800194CB
0x180019199  mov     rdi, rsi
0x18001919c  mov     r8, rbx; Size
0x18001919f  xor     edx, edx; Val
0x1800191a1  mov     rcx, r14; void *
0x1800191a4  call    memset_0
0x1800191a9  mov     eax, dword ptr [rsp+310h+cb+4]
0x1800191ad  lea     ecx, [rax+1]
0x1800191b0  cmp     ecx, eax
0x1800191b2  jb      loc_180019494
0x1800191b8  mov     r12d, esi
0x1800191bb  mov     dword ptr [rsp+310h+cb+4], ecx
0x1800191bf  add     rcx, rcx; unsigned __int64
0x1800191c2  lea     rdx, [rsp+310h+pvData]; unsigned int *
0x1800191c7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800191cc  mov     ebx, eax
0x1800191ce  mov     eax, 1
0x1800191d3  test    ebx, ebx
0x1800191d5  js      loc_180019462
0x1800191db  mov     ecx, dword ptr [rsp+310h+pvData]; cb
0x1800191df  call    cs:__imp_CoTaskMemAlloc
0x1800191e6  nop     dword ptr [rax+rax+00h]
0x1800191eb  mov     rdi, rax
0x1800191ee  test    rax, rax
0x1800191f1  jnz     short loc_1800191FD
0x1800191f3  mov     ebx, 8007000Eh
0x1800191f8  jmp     loc_1800194A1
0x1800191fd  mov     dword ptr [rsp+310h+cb], esi
0x180019201  cmp     esi, dword ptr [rsp+310h+pvData+4]
0x180019205  jnb     loc_180019452
0x18001920b  mov     eax, dword ptr [rsp+310h+cb+4]
0x18001920f  mov     [rbp+210h+cchName], eax
0x180019212  xor     ecx, ecx
0x180019214  mov     [rdi], cx
0x180019217  mov     [rsp+310h+lpcValues], rcx; lpftLastWriteTime
0x18001921c  mov     [rsp+310h+lpcbMaxClassLen], rcx; lpcchClass
0x180019221  mov     [rsp+310h+lpcbMaxSubKeyLen], rcx; lpClass
0x180019226  mov     [rsp+310h+lpcSubKeys], rcx; lpReserved
0x18001922b  lea     r9, [rbp+210h+cchName]; lpcchName
0x18001922f  mov     r8, rdi; lpName
0x180019232  mov     edx, esi; dwIndex
0x180019234  mov     rcx, [rbp+210h+hKey]; hKey
0x180019238  call    cs:__imp_RegEnumKeyExW
0x18001923f  nop     dword ptr [rax+rax+00h]
0x180019244  mov     ebx, eax
0x180019246  test    eax, eax
0x180019248  jnz     loc_180019441
0x18001924e  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x180019253  mov     r9, rax
0x180019256  mov     [rsp+310h+lpcSubKeys], rdi
0x18001925b  lea     r8, aSS; "%s\\%s"
0x180019262  mov     edx, 104h; unsigned __int64
0x180019267  lea     rcx, [rbp+210h+SubKey]; unsigned __int16 *
0x18001926b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180019270  mov     ebx, eax
0x180019272  test    eax, eax
0x180019274  js      loc_18001945B
0x18001927a  lea     r8, [rsp+310h+hkey]; HKEY *
0x18001927f  lea     rcx, [rbp+210h+SubKey]; lpSubKey
0x180019283  call    ?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z; EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)
0x180019288  mov     ebx, eax
0x18001928a  test    eax, eax
0x18001928c  js      loc_18001942A
0x180019292  mov     rdx, [rsp+310h+hkey]
0x180019297  lea     rcx, [rbp+210h+var_260]
0x18001929b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800192a0  mov     dword ptr [rsp+310h+pvData], 0
0x1800192a8  mov     [rbp+210h+pcbData], 4
0x1800192af  lea     rax, [rbp+210h+pcbData]
0x1800192b3  mov     [rsp+310h+lpcbMaxClassLen], rax; pcbData
0x1800192b8  lea     rax, [rsp+310h+pvData]
0x1800192bd  mov     [rsp+310h+lpcbMaxSubKeyLen], rax; pvData
0x1800192c2  mov     [rsp+310h+lpcSubKeys], 0; pdwType
0x1800192cb  mov     r9d, 18h; dwFlags
0x1800192d1  lea     r8, aEnrollmentstat; "EnrollmentState"
0x1800192d8  xor     edx, edx; lpSubKey
0x1800192da  mov     rcx, [rsp+310h+hkey]; hkey
0x1800192df  call    cs:__imp_RegGetValueW
0x1800192e6  nop     dword ptr [rax+rax+00h]
0x1800192eb  xor     ecx, ecx
0x1800192ed  test    eax, eax
0x1800192ef  jnz     loc_18001942A
0x1800192f5  mov     [rsp+310h+var_2A0], ecx
0x1800192f9  mov     [rbp+210h+var_278], 4
0x180019300  lea     rax, [rbp+210h+var_278]
0x180019304  mov     [rsp+310h+lpcbMaxClassLen], rax; pcbData
0x180019309  lea     rax, [rsp+310h+var_2A0]
0x18001930e  mov     [rsp+310h+lpcbMaxSubKeyLen], rax; pvData
0x180019313  mov     [rsp+310h+lpcSubKeys], rcx; pdwType
0x180019318  lea     r9d, [rcx+18h]; dwFlags
0x18001931c  lea     r8, aEnrollmenttype; "EnrollmentType"
0x180019323  xor     edx, edx; lpSubKey
0x180019325  mov     rcx, [rsp+310h+hkey]; hkey
0x18001932a  call    cs:__imp_RegGetValueW
0x180019331  nop     dword ptr [rax+rax+00h]
0x180019336  xor     r10d, r10d
0x180019339  mov     ecx, r10d
0x18001933c  mov     [rbp+210h+var_290], rcx
0x180019340  mov     r9, [rbp+210h+var_268]
0x180019344  test    r9, r9
0x180019347  jz      short loc_18001937B
0x180019349  lea     rax, aAadopaqueid; "AADOpaqueID"
0x180019350  lea     rdx, aPartneropaquei; "PartnerOpaqueID"
0x180019357  cmp     [rbp+210h+arg_38], r10d
0x18001935e  cmovz   rdx, rax; lpValue
0x180019362  lea     r8, [rbp+210h+var_290]; unsigned __int16 **
0x180019366  mov     rcx, [rsp+310h+hkey]; hkey
0x18001936b  call    ?AllocAndGetEnrollmentString@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; AllocAndGetEnrollmentString(HKEY__ *,ushort const *,ushort * *)
0x180019370  mov     rcx, [rbp+210h+var_290]
0x180019374  mov     r9, [rbp+210h+var_268]
0x180019378  xor     r10d, r10d
0x18001937b  mov     edx, dword ptr [rsp+310h+pvData]
0x18001937f  cmp     edx, 3Fh ; '?'
0x180019382  jz      loc_180019421
0x180019388  mov     sil, r10b
0x18001938b  cmp     edx, [rbp+210h+arg_20]
0x180019391  jz      short loc_1800193B3
0x180019393  mov     eax, [rsp+310h+var_2A0]
0x180019397  mov     r8, [rbp+210h+arg_28]
0x18001939e  bt      r8, rax
0x1800193a2  setb    al
0x1800193a5  movzx   esi, al
0x1800193a8  cmp     edx, [rbp+210h+var_274]
0x1800193ab  mov     eax, 1
0x1800193b0  cmovz   esi, eax
0x1800193b3  test    r9, r9
0x1800193b6  jz      short loc_1800193F8
0x1800193b8  test    rcx, rcx
0x1800193bb  jz      short loc_1800193F8
0x1800193bd  cmp     [rbp+210h+arg_40], r10d
0x1800193c4  jnz     short loc_1800193D7
0x1800193c6  mov     rdx, r9
0x1800193c9  call    cs:__imp__o__wcsicmp
0x1800193d0  nop     dword ptr [rax+rax+00h]
0x1800193d5  jmp     short loc_1800193F4
0x1800193d7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800193db  inc     r8
0x1800193de  cmp     [r9+r8*2], r10w
0x1800193e3  jnz     short loc_1800193DB
0x1800193e5  mov     rdx, r9
0x1800193e8  call    cs:__imp__o__wcsnicmp
0x1800193ef  nop     dword ptr [rax+rax+00h]
0x1800193f4  test    eax, eax
0x1800193f6  jz      short loc_1800193FD
0x1800193f8  test    sil, sil
0x1800193fb  jz      short loc_18001941D
0x1800193fd  mov     rcx, rdi; psz
0x180019400  call    cs:__imp_SysAllocString
0x180019407  nop     dword ptr [rax+rax+00h]
0x18001940c  mov     ecx, r12d
0x18001940f  mov     [r14+rcx*8], rax
0x180019413  xor     esi, esi
0x180019415  test    rax, rax
0x180019418  jz      short loc_180019431
0x18001941a  inc     r12d
0x18001941d  mov     esi, dword ptr [rsp+310h+cb]
0x180019421  lea     rcx, [rbp+210h+var_290]
0x180019425  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18001942a  inc     esi
0x18001942c  jmp     loc_1800191FD
0x180019431  mov     ebx, 8007000Eh
0x180019436  lea     rcx, [rbp+210h+var_290]
0x18001943a  call    ?Release@?$CTSmartObj@PEAGV?$CTSmartPtr_PolicyComplete@VCTContainer_PolicyHeapMem@@@@@@QEAAXXZ; CTSmartObj<ushort *,CTSmartPtr_PolicyComplete<CTContainer_PolicyHeapMem>>::Release(void)
0x18001943f  jmp     short loc_18001945D
0x180019441  xor     esi, esi
0x180019443  test    eax, eax
0x180019445  jle     short loc_18001945D
0x180019447  movzx   ebx, ax
0x18001944a  or      ebx, 80070000h
0x180019450  jmp     short loc_18001945D
0x180019452  mov     [r13+0], r12d
0x180019456  mov     [r15], r14
0x180019459  jmp     short loc_1800194B5
0x18001945b  xor     esi, esi
0x18001945d  mov     eax, 1
0x180019462  xor     r13d, r13d
0x180019465  test    r12d, r12d
0x180019468  jz      short loc_1800194A1
0x18001946a  mov     r15d, esi
0x18001946d  mov     rcx, [r14+r15*8]; bstrString
0x180019471  test    rcx, rcx
0x180019474  jz      short loc_18001948B
0x180019476  call    cs:__imp_SysFreeString
0x18001947d  nop     dword ptr [rax+rax+00h]
0x180019482  mov     [r14+r15*8], r13
0x180019486  mov     eax, 1
0x18001948b  add     esi, eax
0x18001948d  cmp     esi, r12d
0x180019490  jb      short loc_18001946A
0x180019492  jmp     short loc_1800194A1
0x180019494  mov     dword ptr [rsp+310h+cb+4], 0FFFFFFFFh
0x18001949c  mov     ebx, 80070216h
0x1800194a1  mov     rcx, r14; pv
0x1800194a4  call    cs:__imp_CoTaskMemFree
0x1800194ab  nop     dword ptr [rax+rax+00h]
0x1800194b0  test    rdi, rdi
0x1800194b3  jz      short loc_1800194CB
0x1800194b5  mov     rcx, rdi; pv
0x1800194b8  call    cs:__imp_CoTaskMemFree
0x1800194bf  nop     dword ptr [rax+rax+00h]
0x1800194c4  jmp     short loc_1800194CB
0x1800194c6  mov     ebx, 80070057h
0x1800194cb  lea     rcx, [rbp+210h+var_260]
0x1800194cf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800194d4  nop
0x1800194d5  lea     rcx, [rbp+210h+hKey]
0x1800194d9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800194de  mov     eax, ebx
0x1800194e0  mov     rcx, [rbp+210h+var_40]
0x1800194e7  xor     rcx, rsp; StackCookie
0x1800194ea  call    __security_check_cookie
0x1800194ef  mov     rbx, [rsp+310h+arg_0]
0x1800194f7  add     rsp, 2E0h
0x1800194fe  pop     r15
0x180019500  pop     r14
0x180019502  pop     r13
  ... truncated ...
```

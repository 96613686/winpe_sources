# DmFindMdmEnrollmentWithLinkedEnrollment(ushort const *,ushort *)

- ea: `0x1800b22a0`
- end: `0x1800b261a`
- name: `?DmFindMdmEnrollmentWithLinkedEnrollment@@YAJPEBGPEAG@Z`
- size: `890`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180077c20`

## callees

- `0x180007270`
- `0x180053c78`
- `0x18005427c`
- `0x180057c6c`
- `0x1800583e8`
- `0x180058420`
- `0x18005b638`
- `0x18005b914`
- `0x180062704`
- `0x180064a44`
- `0x1800b22a0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b25b8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b25b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2496`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b254b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2496`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b254b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800b2305`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800b2305`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b23f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b23f5`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800b2325`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800b2325`

## string_xrefs

- `0x1800b2311`: `Software\Microsoft\Enrollments\%s\LinkedEnrollment`
- `0x1800b2318`: `OSData\Software\Microsoft\Enrollments\%s\LinkedEnrollment`
- `0x1800b2483`: `LinkedEnrollmentId`
- `0x1800b2538`: `LinkedEnrollmentId`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DmFindMdmEnrollmentWithLinkedEnrollment(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // r12
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v6)(__int64, __int64, __int64 *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  unsigned __int64 v12; // r9
  __int64 (__fastcall *v13)(__int64, BSTR *); // r15
  LSTATUS ValueW; // eax
  PVOID v15; // rbx
  LSTATUS v16; // eax
  signed int v17; // edi
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  PVOID pvData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( a1 && a2 )
  {
    v26 = 0;
    v25 = 0;
    bstrString = 0;
    v4 = L"OSData\\Software\\Microsoft\\Enrollments\\%s\\LinkedEnrollment";
    if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
      v4 = L"Software\\Microsoft\\Enrollments\\%s\\LinkedEnrollment";
    DatabaseManagerInstance = GetDatabaseManagerInstance();
    v6 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    v7 = v6(DatabaseManagerInstance, 8289, &v26);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v10 = v26;
      v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
      v7 = v11(v10, &v25);
      v8 = v7;
      if ( v7 >= 0 )
      {
        if ( !v25 )
        {
          v8 = -2147467259;
          goto LABEL_30;
        }
        v24 = 1;
        pcbData = 0;
        v13 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v25 + 32LL);
        bstrString = 0;
        v7 = v13(v25, &bstrString);
        v8 = v7;
        if ( v7 >= 0 )
        {
          v7 = StringCchPrintfW(SubKey, 0x104u, v4, bstrString);
          v8 = v7;
          if ( v7 >= 0 )
          {
            ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"LinkedEnrollmentId", 2u, &v24, 0, &pcbData);
            v8 = ValueW;
            if ( ValueW > 0 )
              v8 = (unsigned __int16)ValueW | 0x80070000;
            if ( (v8 & 0x80000000) == 0 )
            {
              if ( pcbData <= 0x104 )
              {
                wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &pvData,
                  0,
                  pcbData);
                v15 = pvData;
                if ( pvData )
                {
                  v16 = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"LinkedEnrollmentId", 2u, &v24, pvData, &pcbData);
                  v17 = v16;
                  if ( v16 > 0 )
                    v17 = (unsigned __int16)v16 | 0x80070000;
                  if ( v17 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x1BE,
                      (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\enrollmentutils\\enrollmentutils.cpp",
                      (const char *)(unsigned int)v17,
                      pdwTypea);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pvData);
                    v8 = v17;
                    goto LABEL_30;
                  }
                  if ( (unsigned int)_o__wcsicmp(v15, a1) )
                    v8 = -2147024894;
                  else
                    v8 = StringCchCopyW(a2, 0x27u, bstrString);
                }
                else
                {
                  v8 = -2147024882;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1B3,
                    (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\enrollmentutils\\enrollmentutils.cpp",
                    (const char *)0x8007000ELL,
                    pdwType);
                }
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pvData);
              }
              else
              {
                v8 = -2147024809;
              }
LABEL_30:
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrString);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
              return v8;
            }
            v12 = v8;
            v9 = 426;
LABEL_10:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v9,
              (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\enrollmentutils\\enrollmentutils.cpp",
              (const char *)v12,
              pdwType);
            goto LABEL_30;
          }
          v9 = 412;
        }
        else
        {
          v9 = 409;
        }
      }
      else
      {
        v9 = 402;
      }
    }
    else
    {
      v9 = 401;
    }
    v12 = (unsigned int)v7;
    goto LABEL_10;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800b22a0  mov     [rsp-8+arg_10], rbx
0x1800b22a5  mov     [rsp-8+arg_18], rsi
0x1800b22aa  push    rbp
0x1800b22ab  push    rdi
0x1800b22ac  push    r12
0x1800b22ae  push    r14
0x1800b22b0  push    r15
0x1800b22b2  lea     rbp, [rsp-190h]
0x1800b22ba  sub     rsp, 290h
0x1800b22c1  mov     rax, cs:__security_cookie
0x1800b22c8  xor     rax, rsp
0x1800b22cb  mov     [rbp+1B0h+var_30], rax
0x1800b22d2  mov     rsi, rdx
0x1800b22d5  mov     r14, rcx
0x1800b22d8  test    rcx, rcx
0x1800b22db  jz      loc_1800B25E9
0x1800b22e1  test    rdx, rdx
0x1800b22e4  jz      loc_1800B25E9
0x1800b22ea  mov     [rsp+2B0h+var_248], 0
0x1800b22f3  mov     [rsp+2B0h+var_250], 0
0x1800b22fc  mov     [rsp+2B0h+bstrString], 0
0x1800b2305  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800b230c  nop     dword ptr [rax+rax+00h]
0x1800b2311  lea     rcx, aSoftwareMicros_0; "Software\\Microsoft\\Enrollments\\%s\\L"...
0x1800b2318  lea     r12, aOsdataSoftware_3; "OSData\\Software\\Microsoft\\Enrollment"...
0x1800b231f  test    al, al
0x1800b2321  cmovz   r12, rcx
0x1800b2325  call    cs:__imp_GetDatabaseManagerInstance
0x1800b232c  nop     dword ptr [rax+rax+00h]
0x1800b2331  mov     rdi, rax
0x1800b2334  mov     rcx, [rax]
0x1800b2337  mov     rbx, [rcx+20h]
0x1800b233b  lea     rcx, [rsp+2B0h+var_248]
0x1800b2340  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b2345  lea     r8, [rsp+2B0h+var_248]
0x1800b234a  mov     edx, 2061h
0x1800b234f  mov     rcx, rdi
0x1800b2352  mov     rax, rbx
0x1800b2355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b235a  mov     ebx, eax
0x1800b235c  test    eax, eax
0x1800b235e  jns     short loc_1800B2367
0x1800b2360  mov     edx, 191h
0x1800b2365  jmp     short loc_1800B2398
0x1800b2367  mov     rdi, [rsp+2B0h+var_248]
0x1800b236c  mov     rax, [rdi]
0x1800b236f  mov     rbx, [rax+18h]
0x1800b2373  lea     rcx, [rsp+2B0h+var_250]
0x1800b2378  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b237d  lea     rdx, [rsp+2B0h+var_250]
0x1800b2382  mov     rcx, rdi
0x1800b2385  mov     rax, rbx
0x1800b2388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b238d  mov     ebx, eax
0x1800b238f  test    eax, eax
0x1800b2391  jns     short loc_1800B23B3
0x1800b2393  mov     edx, 192h; void *
0x1800b2398  mov     r9d, eax; char *
0x1800b239b  mov     rcx, [rbp+1B8h]; this
0x1800b23a2  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\dm\\dmcmnutils\\enro"...
0x1800b23a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b23ae  jmp     loc_1800B258E
0x1800b23b3  mov     rbx, [rsp+2B0h+var_250]
0x1800b23b8  test    rbx, rbx
0x1800b23bb  jnz     short loc_1800B23C7
0x1800b23bd  mov     ebx, 80004005h
0x1800b23c2  jmp     loc_1800B258E
0x1800b23c7  mov     [rsp+2B0h+var_258], 1
0x1800b23cf  mov     [rsp+2B0h+var_270], 0
0x1800b23d7  mov     rax, [rbx]
0x1800b23da  mov     r15, [rax+20h]
0x1800b23de  mov     rdi, [rsp+2B0h+bstrString]
0x1800b23e3  test    rdi, rdi
0x1800b23e6  jz      short loc_1800B240B
0x1800b23e8  lea     rcx, [rsp+2B0h+var_260]; this
0x1800b23ed  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800b23f2  mov     rcx, rdi; bstrString
0x1800b23f5  call    cs:__imp_SysFreeString
0x1800b23fc  nop     dword ptr [rax+rax+00h]
0x1800b2401  lea     rcx, [rsp+2B0h+var_260]; this
0x1800b2406  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800b240b  mov     [rsp+2B0h+bstrString], 0
0x1800b2414  lea     rdx, [rsp+2B0h+bstrString]
0x1800b2419  mov     rcx, rbx
0x1800b241c  mov     rax, r15
0x1800b241f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2424  mov     ebx, eax
0x1800b2426  test    eax, eax
0x1800b2428  jns     short loc_1800B2434
0x1800b242a  mov     edx, 199h
0x1800b242f  jmp     loc_1800B2398
0x1800b2434  mov     r9, [rsp+2B0h+bstrString]
0x1800b2439  mov     r8, r12; unsigned __int16 *
0x1800b243c  mov     edi, 104h
0x1800b2441  mov     edx, edi; unsigned __int64
0x1800b2443  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x1800b2448  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b244d  mov     ebx, eax
0x1800b244f  test    eax, eax
0x1800b2451  jns     short loc_1800B245D
0x1800b2453  mov     edx, 19Ch
0x1800b2458  jmp     loc_1800B2398
0x1800b245d  lea     rax, [rsp+2B0h+var_270]
0x1800b2462  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800b2467  mov     [rsp+2B0h+pvData], 0; pvData
0x1800b2470  lea     rax, [rsp+2B0h+var_258]
0x1800b2475  mov     [rsp+2B0h+pdwType], rax; int
0x1800b247a  mov     r12d, 2
0x1800b2480  mov     r9d, r12d; dwFlags
0x1800b2483  lea     r8, aLinkedenrollme; "LinkedEnrollmentId"
0x1800b248a  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1800b248f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800b2496  call    cs:__imp_RegGetValueW
0x1800b249d  nop     dword ptr [rax+rax+00h]
0x1800b24a2  mov     ebx, eax
0x1800b24a4  mov     r15d, 80070000h
0x1800b24aa  test    eax, eax
0x1800b24ac  jle     short loc_1800B24B4
0x1800b24ae  movzx   ebx, ax
0x1800b24b1  or      ebx, r15d
0x1800b24b4  test    ebx, ebx
0x1800b24b6  jns     short loc_1800B24C5
0x1800b24b8  mov     r9d, ebx
0x1800b24bb  mov     edx, 1AAh
0x1800b24c0  jmp     loc_1800B239B
0x1800b24c5  cmp     [rsp+2B0h+var_270], edi
0x1800b24c9  jbe     short loc_1800B24D5
0x1800b24cb  mov     ebx, 80070057h
0x1800b24d0  jmp     loc_1800B258E
0x1800b24d5  mov     r8d, [rsp+2B0h+var_270]
0x1800b24da  xor     edx, edx
0x1800b24dc  lea     rcx, [rsp+2B0h+var_260]
0x1800b24e1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800b24e6  mov     rbx, [rsp+2B0h+var_260]
0x1800b24eb  test    rbx, rbx
0x1800b24ee  jnz     short loc_1800B251C
0x1800b24f0  mov     rcx, [rbp+1B8h]; this
0x1800b24f7  mov     ebx, 8007000Eh
0x1800b24fc  mov     r9d, ebx; char *
0x1800b24ff  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\dm\\dmcmnutils\\enro"...
0x1800b2506  mov     edx, 1B3h; void *
0x1800b250b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2510  lea     rcx, [rsp+2B0h+var_260]
0x1800b2515  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b251a  jmp     short loc_1800B258E
0x1800b251c  lea     rax, [rsp+2B0h+var_270]
0x1800b2521  mov     [rsp+2B0h+pcbData], rax; pcbData
0x1800b2526  mov     [rsp+2B0h+pvData], rbx; pvData
0x1800b252b  lea     rax, [rsp+2B0h+var_258]
0x1800b2530  mov     [rsp+2B0h+pdwType], rax; int
0x1800b2535  mov     r9d, r12d; dwFlags
0x1800b2538  lea     r8, aLinkedenrollme; "LinkedEnrollmentId"
0x1800b253f  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x1800b2544  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800b254b  call    cs:__imp_RegGetValueW
0x1800b2552  nop     dword ptr [rax+rax+00h]
0x1800b2557  mov     edi, eax
0x1800b2559  test    eax, eax
0x1800b255b  jle     short loc_1800B2563
0x1800b255d  movzx   edi, ax
0x1800b2560  or      edi, r15d
0x1800b2563  test    edi, edi
0x1800b2565  jns     short loc_1800B25B2
0x1800b2567  mov     rcx, [rbp+1B8h]; this
0x1800b256e  mov     r9d, edi; char *
0x1800b2571  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\dm\\dmcmnutils\\enro"...
0x1800b2578  mov     edx, 1BEh; void *
0x1800b257d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2582  lea     rcx, [rsp+2B0h+var_260]
0x1800b2587  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b258c  mov     ebx, edi
0x1800b258e  lea     rcx, [rsp+2B0h+bstrString]
0x1800b2593  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b2598  nop
0x1800b2599  lea     rcx, [rsp+2B0h+var_250]
0x1800b259e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b25a3  nop
0x1800b25a4  lea     rcx, [rsp+2B0h+var_248]
0x1800b25a9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b25ae  mov     eax, ebx
0x1800b25b0  jmp     short loc_1800B25EE
0x1800b25b2  mov     rdx, r14
0x1800b25b5  mov     rcx, rbx
0x1800b25b8  call    cs:__imp__o__wcsicmp
0x1800b25bf  nop     dword ptr [rax+rax+00h]
0x1800b25c4  test    eax, eax
0x1800b25c6  jnz     short loc_1800B25DF
0x1800b25c8  mov     r8, [rsp+2B0h+bstrString]; unsigned __int16 *
0x1800b25cd  lea     edx, [rax+27h]; unsigned __int64
0x1800b25d0  mov     rcx, rsi; unsigned __int16 *
0x1800b25d3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b25d8  mov     ebx, eax
0x1800b25da  jmp     loc_1800B2510
0x1800b25df  mov     ebx, 80070002h
0x1800b25e4  jmp     loc_1800B2510
0x1800b25e9  mov     eax, 80070057h
0x1800b25ee  mov     rcx, [rbp+1B0h+var_30]
0x1800b25f5  xor     rcx, rsp; StackCookie
0x1800b25f8  call    __security_check_cookie
0x1800b25fd  lea     r11, [rsp+2B0h+var_20]
0x1800b2605  mov     rbx, [r11+40h]
0x1800b2609  mov     rsi, [r11+48h]
0x1800b260d  mov     rsp, r11
0x1800b2610  pop     r15
0x1800b2612  pop     r14
0x1800b2614  pop     r12
0x1800b2616  pop     rdi
0x1800b2617  pop     rbp
0x1800b2618  retn
```

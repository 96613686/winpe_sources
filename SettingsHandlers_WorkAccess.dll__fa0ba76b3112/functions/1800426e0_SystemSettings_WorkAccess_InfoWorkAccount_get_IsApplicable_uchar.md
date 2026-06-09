# SystemSettings::WorkAccess::InfoWorkAccount::get_IsApplicable(uchar *)

- ea: `0x1800426e0`
- end: `0x180042b17`
- name: `?get_IsApplicable@InfoWorkAccount@WorkAccess@SystemSettings@@UEAAJPEAE@Z`
- size: `1079`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::InfoWorkAccount *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x1800236d8`
- `0x1800236fc`
- `0x1800257a4`
- `0x180029708`
- `0x180029764`
- `0x180042600`
- `0x1800426e0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004299c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800429d0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004299c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800429d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800429b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800429b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800428f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800429f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800428f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800429f5`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180042717`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180042717`

## string_xrefs

- `0x18004286b`: `shellcommon\shell\settingshandlers\workaccess\lib\infoworkaccount.cpp`
- `0x1800428c1`: `shellcommon\shell\settingshandlers\workaccess\lib\infoworkaccount.cpp`
- `0x18004291e`: `shellcommon\shell\settingshandlers\workaccess\lib\infoworkaccount.cpp`
- `0x18004296b`: `shellcommon\shell\settingshandlers\workaccess\lib\infoworkaccount.cpp`
- `0x180042a77`: `shellcommon\shell\settingshandlers\workaccess\lib\infoworkaccount.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::WorkAccess::InfoWorkAccount::get_IsApplicable(
        SystemSettings::WorkAccess::InfoWorkAccount *this,
        unsigned __int8 *a2)
{
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  int (__fastcall *v10)(__int64, __int64 *); // rbx
  unsigned __int8 v11; // si
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, LPCWCH *); // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, LPCWCH *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  int CurrentUserSidString; // eax
  const WCHAR *StringRawBuffer; // rax
  __int64 v24; // rdi
  int (__fastcall *v25)(__int64, _QWORD *); // rbx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-40h]
  __int64 v28; // [rsp+30h] [rbp-30h] BYREF
  LPCWCH v29; // [rsp+38h] [rbp-28h] BYREF
  __int64 v30; // [rsp+40h] [rbp-20h] BYREF
  LPCWCH lpString2; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v34; // [rsp+A0h] [rbp+40h] BYREF
  int v35; // [rsp+A8h] [rbp+48h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+50h] BYREF
  LPCWCH lpString1; // [rsp+B8h] [rbp+58h] BYREF

  *a2 = 0;
  if ( *((_DWORD *)this + 56) == 4 )
    return 0;
  v30 = 0;
  v28 = 0;
  v32[0] = 0;
  DatabaseManagerInstance = GetDatabaseManagerInstance();
  v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v6 = v5(DatabaseManagerInstance, 222306401, &v30);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 72;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\infoworkaccount.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
    goto LABEL_36;
  }
  v9 = v30;
  v10 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  if ( v10(v9, &v28) >= 0 && v28 )
  {
    v34 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 48LL))(v28, &v34);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 79;
      goto LABEL_35;
    }
    v11 = 1;
    if ( ((v34 - 24) & 0xFFFFFFFD) != 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 48LL))(v28, &v34);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 106;
        goto LABEL_35;
      }
      if ( ((1LL << v34) & 0x4000040) == 0 || (unsigned int)(*((_DWORD *)this + 56) - 1) > 2 )
      {
        if ( v34 <= 0x18 )
        {
          v12 = 16785440;
          if ( _bittest(&v12, v34) )
          {
            if ( !*((_DWORD *)this + 56) )
            {
              lpString1 = 0;
              v13 = v28;
              v14 = *(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v28 + 112LL);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &lpString1,
                0);
              v15 = v14(v13, &lpString1);
              v7 = v15;
              if ( v15 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x73,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\infoworkaccount.cpp",
                  (const char *)(unsigned int)v15,
                  bIgnoreCase);
LABEL_18:
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
LABEL_36:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v32);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
                return v7;
              }
              v29 = 0;
              v16 = v28;
              v17 = *(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v28 + 104LL);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &v29,
                0);
              v18 = v17(v16, &v29);
              v7 = v18;
              if ( v18 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x76,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\infoworkaccount.cpp",
                  (const char *)(unsigned int)v18,
                  bIgnoreCase);
LABEL_21:
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
                goto LABEL_18;
              }
              string = 0;
              v19 = *((_QWORD *)this + 27);
              v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 56LL);
              WindowsDeleteString(0);
              string = 0;
              v21 = v20(v19, &string);
              v7 = v21;
              if ( v21 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x79,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\infoworkaccount.cpp",
                  (const char *)(unsigned int)v21,
                  bIgnoreCase);
LABEL_24:
                WindowsDeleteString(string);
                string = 0;
                goto LABEL_21;
              }
              lpString2 = 0;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &lpString2,
                0);
              CurrentUserSidString = GetCurrentUserSidString((LPWSTR *)&lpString2);
              v7 = CurrentUserSidString;
              if ( CurrentUserSidString < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x7C,
                  (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\infoworkaccount.cpp",
                  (const char *)(unsigned int)CurrentUserSidString,
                  bIgnoreCase);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString2);
                goto LABEL_24;
              }
              if ( CompareStringOrdinal(lpString1, -1, lpString2, -1, 0) != 2
                || (StringRawBuffer = WindowsGetStringRawBuffer(string, 0),
                    CompareStringOrdinal(v29, -1, StringRawBuffer, -1, 0) != 2) )
              {
                v11 = 0;
              }
              *a2 = v11;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString2);
              WindowsDeleteString(string);
              string = 0;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
            }
          }
        }
        goto LABEL_45;
      }
    }
    else
    {
      v24 = v30;
      v25 = *(int (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v30 + 24LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v32);
      if ( v25(v24, v32) < 0 || !v32[0] )
        goto LABEL_45;
      v35 = 0;
      v6 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v32[0] + 48LL))(v32[0], &v35);
      v7 = v6;
      if ( v6 < 0 )
      {
        v8 = 85;
        goto LABEL_35;
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::GetImpl'::`2'::impl) )
      {
        if ( v35 != 13 && v35 != 6 || *((_DWORD *)this + 56) > 3u )
          goto LABEL_45;
      }
      else if ( v35 != 6 || (unsigned int)(*((_DWORD *)this + 56) - 1) > 2 )
      {
        goto LABEL_45;
      }
    }
    *a2 = 1;
  }
LABEL_45:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  return 0;
}

```

## disassembly

```asm
0x1800426e0  push    rbp
0x1800426e2  push    rbx
0x1800426e3  push    rsi
0x1800426e4  push    rdi
0x1800426e5  push    r12
0x1800426e7  push    r14
0x1800426e9  push    r15
0x1800426eb  mov     rbp, rsp
0x1800426ee  sub     rsp, 60h
0x1800426f2  mov     r15, rdx
0x1800426f5  mov     r14, rcx
0x1800426f8  xor     r12d, r12d
0x1800426fb  mov     [rdx], r12b
0x1800426fe  cmp     dword ptr [rcx+0E0h], 4
0x180042705  jz      loc_180042B05
0x18004270b  mov     [rbp+var_20], r12
0x18004270f  mov     [rbp+var_30], r12
0x180042713  mov     [rbp+var_10], r12
0x180042717  call    cs:__imp_GetDatabaseManagerInstance
0x18004271e  nop     dword ptr [rax+rax+00h]
0x180042723  mov     rdi, rax
0x180042726  mov     rcx, [rax]
0x180042729  mov     rbx, [rcx+20h]
0x18004272d  lea     rcx, [rbp+var_20]
0x180042731  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042736  lea     r8, [rbp+var_20]
0x18004273a  mov     edx, 0D402061h
0x18004273f  mov     rcx, rdi
0x180042742  mov     rax, rbx
0x180042745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004274a  mov     ebx, eax
0x18004274c  test    eax, eax
0x18004274e  jns     short loc_18004275A
0x180042750  lea     edx, [r12+48h]
0x180042755  jmp     loc_180042A74
0x18004275a  mov     rdi, [rbp+var_20]
0x18004275e  mov     rax, [rdi]
0x180042761  mov     rbx, [rax+18h]
0x180042765  lea     rcx, [rbp+var_30]
0x180042769  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004276e  lea     rdx, [rbp+var_30]
0x180042772  mov     rcx, rdi
0x180042775  mov     rax, rbx
0x180042778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004277d  test    eax, eax
0x18004277f  js      loc_180042AE8
0x180042785  mov     rcx, [rbp+var_30]
0x180042789  test    rcx, rcx
0x18004278c  jz      loc_180042AE8
0x180042792  mov     [rbp+arg_0], r12d
0x180042796  mov     rax, [rcx]
0x180042799  lea     rdx, [rbp+arg_0]
0x18004279d  mov     rax, [rax+30h]
0x1800427a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427a6  mov     ebx, eax
0x1800427a8  test    eax, eax
0x1800427aa  jns     short loc_1800427B6
0x1800427ac  mov     edx, 4Fh ; 'O'
0x1800427b1  jmp     loc_180042A74
0x1800427b6  mov     eax, [rbp+arg_0]
0x1800427b9  add     eax, 0FFFFFFE8h
0x1800427bc  mov     esi, 1
0x1800427c1  test    eax, 0FFFFFFFDh
0x1800427c6  jz      loc_180042A1D
0x1800427cc  mov     rcx, [rbp+var_30]
0x1800427d0  mov     rax, [rcx]
0x1800427d3  lea     rdx, [rbp+arg_0]
0x1800427d7  mov     rax, [rax+30h]
0x1800427db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427e0  mov     ebx, eax
0x1800427e2  test    eax, eax
0x1800427e4  jns     short loc_1800427EE
0x1800427e6  lea     edx, [rsi+69h]
0x1800427e9  jmp     loc_180042A74
0x1800427ee  mov     ecx, [rbp+arg_0]
0x1800427f1  mov     rax, rsi
0x1800427f4  shl     rax, cl
0x1800427f7  test    rax, 4000040h
0x1800427fd  jz      short loc_180042811
0x1800427ff  mov     eax, [r14+0E0h]
0x180042806  sub     eax, esi
0x180042808  cmp     eax, 2
0x18004280b  jbe     loc_180042AE5
0x180042811  cmp     ecx, 18h
0x180042814  ja      loc_180042AE8
0x18004281a  mov     eax, 1002020h
0x18004281f  bt      eax, ecx
0x180042822  jnb     loc_180042AE8
0x180042828  cmp     [r14+0E0h], r12d
0x18004282f  jnz     loc_180042AE8
0x180042835  mov     [rbp+lpString1], r12
0x180042839  mov     rdi, [rbp+var_30]
0x18004283d  mov     rax, [rdi]
0x180042840  mov     rbx, [rax+70h]
0x180042844  xor     edx, edx
0x180042846  lea     rcx, [rbp+lpString1]
0x18004284a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18004284f  lea     rdx, [rbp+lpString1]
0x180042853  mov     rcx, rdi
0x180042856  mov     rax, rbx
0x180042859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004285e  mov     ebx, eax
0x180042860  test    eax, eax
0x180042862  jns     short loc_18004288B
0x180042864  mov     rcx, [rbp+38h]; this
0x180042868  mov     r9d, eax; char *
0x18004286b  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\settingshandlers\\w"...
0x180042872  mov     edx, 73h ; 's'; void *
0x180042877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004287c  nop
0x18004287d  lea     rcx, [rbp+lpString1]
0x180042881  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180042886  jmp     loc_180042A88
0x18004288b  mov     [rbp+var_28], r12
0x18004288f  mov     rdi, [rbp+var_30]
0x180042893  mov     rax, [rdi]
0x180042896  mov     rbx, [rax+68h]
0x18004289a  xor     edx, edx
0x18004289c  lea     rcx, [rbp+var_28]
0x1800428a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800428a5  lea     rdx, [rbp+var_28]
0x1800428a9  mov     rcx, rdi
0x1800428ac  mov     rax, rbx
0x1800428af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800428b4  mov     ebx, eax
0x1800428b6  test    eax, eax
0x1800428b8  jns     short loc_1800428DE
0x1800428ba  mov     rcx, [rbp+38h]; this
0x1800428be  mov     r9d, eax; char *
0x1800428c1  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\settingshandlers\\w"...
0x1800428c8  mov     edx, 76h ; 'v'; void *
0x1800428cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800428d2  nop
0x1800428d3  lea     rcx, [rbp+var_28]
0x1800428d7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800428dc  jmp     short loc_18004287D
0x1800428de  mov     [rbp+string], r12
0x1800428e2  mov     rdi, [r14+0D8h]
0x1800428e9  mov     rax, [rdi]
0x1800428ec  mov     rbx, [rax+38h]
0x1800428f0  xor     ecx, ecx; string
0x1800428f2  call    cs:__imp_WindowsDeleteString
0x1800428f9  nop     dword ptr [rax+rax+00h]
0x1800428fe  mov     [rbp+string], r12
0x180042902  lea     rdx, [rbp+string]
0x180042906  mov     rcx, rdi
0x180042909  mov     rax, rbx
0x18004290c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042911  mov     ebx, eax
0x180042913  test    eax, eax
0x180042915  jns     short loc_180042946
0x180042917  mov     rcx, [rbp+38h]; this
0x18004291b  mov     r9d, eax; char *
0x18004291e  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\settingshandlers\\w"...
0x180042925  mov     edx, 79h ; 'y'; void *
0x18004292a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004292f  nop
0x180042930  mov     rcx, [rbp+string]; string
0x180042934  call    cs:__imp_WindowsDeleteString
0x18004293b  nop     dword ptr [rax+rax+00h]
0x180042940  mov     [rbp+string], r12
0x180042944  jmp     short loc_1800428D3
0x180042946  mov     [rbp+lpString2], r12
0x18004294a  xor     edx, edx
0x18004294c  lea     rcx, [rbp+lpString2]
0x180042950  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180042955  lea     rcx, [rbp+lpString2]; StringSid
0x180042959  call    ?GetCurrentUserSidString@@YAJPEAPEAG@Z; GetCurrentUserSidString(ushort * *)
0x18004295e  mov     ebx, eax
0x180042960  test    eax, eax
0x180042962  jns     short loc_180042987
0x180042964  mov     rcx, [rbp+38h]; this
0x180042968  mov     r9d, eax; char *
0x18004296b  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\settingshandlers\\w"...
0x180042972  mov     edx, 7Ch ; '|'; void *
0x180042977  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004297c  lea     rcx, [rbp+lpString2]
0x180042980  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180042985  jmp     short loc_180042930
0x180042987  mov     [rsp+60h+bIgnoreCase], r12d; bIgnoreCase
0x18004298c  or      ebx, 0FFFFFFFFh
0x18004298f  mov     r9d, ebx; cchCount2
0x180042992  mov     r8, [rbp+lpString2]; lpString2
0x180042996  mov     edx, ebx; cchCount1
0x180042998  mov     rcx, [rbp+lpString1]; lpString1
0x18004299c  call    cs:__imp_CompareStringOrdinal
0x1800429a3  nop     dword ptr [rax+rax+00h]
0x1800429a8  cmp     eax, 2
0x1800429ab  jnz     short loc_1800429E1
0x1800429ad  xor     edx, edx; length
0x1800429af  mov     rcx, [rbp+string]; string
0x1800429b3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800429ba  nop     dword ptr [rax+rax+00h]
0x1800429bf  mov     [rsp+60h+bIgnoreCase], r12d; bIgnoreCase
0x1800429c4  mov     r9d, ebx; cchCount2
0x1800429c7  mov     r8, rax; lpString2
0x1800429ca  mov     edx, ebx; cchCount1
0x1800429cc  mov     rcx, [rbp+var_28]; lpString1
0x1800429d0  call    cs:__imp_CompareStringOrdinal
0x1800429d7  nop     dword ptr [rax+rax+00h]
0x1800429dc  cmp     eax, 2
0x1800429df  jz      short loc_1800429E4
0x1800429e1  mov     sil, r12b
0x1800429e4  mov     [r15], sil
0x1800429e7  lea     rcx, [rbp+lpString2]
0x1800429eb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800429f0  nop
0x1800429f1  mov     rcx, [rbp+string]; string
0x1800429f5  call    cs:__imp_WindowsDeleteString
0x1800429fc  nop     dword ptr [rax+rax+00h]
0x180042a01  mov     [rbp+string], r12
0x180042a05  lea     rcx, [rbp+var_28]
0x180042a09  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180042a0e  nop
0x180042a0f  lea     rcx, [rbp+lpString1]
0x180042a13  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180042a18  jmp     loc_180042AE8
0x180042a1d  mov     rdi, [rbp+var_20]
0x180042a21  mov     rax, [rdi]
0x180042a24  mov     rbx, [rax+18h]
0x180042a28  lea     rcx, [rbp+var_10]
0x180042a2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042a31  lea     rdx, [rbp+var_10]
0x180042a35  mov     rcx, rdi
0x180042a38  mov     rax, rbx
0x180042a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a40  test    eax, eax
0x180042a42  js      loc_180042AE8
0x180042a48  mov     rcx, [rbp+var_10]
0x180042a4c  test    rcx, rcx
0x180042a4f  jz      loc_180042AE8
0x180042a55  mov     [rbp+arg_8], r12d
0x180042a59  mov     rax, [rcx]
0x180042a5c  lea     rdx, [rbp+arg_8]
0x180042a60  mov     rax, [rax+30h]
0x180042a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042a69  mov     ebx, eax
0x180042a6b  test    eax, eax
0x180042a6d  jns     short loc_180042AA9
0x180042a6f  mov     edx, 55h ; 'U'; void *
0x180042a74  mov     r9d, eax; char *
0x180042a77  lea     r8, aShellcommonShe_3; "shellcommon\\shell\\settingshandlers\\w"...
0x180042a7e  mov     rcx, [rbp+38h]; this
0x180042a82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042a87  nop
0x180042a88  lea     rcx, [rbp+var_10]
0x180042a8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042a91  nop
0x180042a92  lea     rcx, [rbp+var_30]
0x180042a96  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042a9b  nop
0x180042a9c  lea     rcx, [rbp+var_20]
0x180042aa0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042aa5  mov     eax, ebx
0x180042aa7  jmp     short loc_180042B07
0x180042aa9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment> `wil::Feature<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::GetImpl(void)'::`2'::impl
0x180042ab0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WorkplaceJoin_DualEnrollment>::__private_IsEnabled(void)
0x180042ab5  test    al, al
0x180042ab7  jz      short loc_180042AD1
0x180042ab9  cmp     [rbp+arg_8], 0Dh
0x180042abd  jz      short loc_180042AC5
0x180042abf  cmp     [rbp+arg_8], 6
0x180042ac3  jnz     short loc_180042AE8
0x180042ac5  cmp     dword ptr [r14+0E0h], 3
0x180042acd  jbe     short loc_180042AE5
0x180042acf  jmp     short loc_180042AE8
0x180042ad1  cmp     [rbp+arg_8], 6
0x180042ad5  jnz     short loc_180042AE8
0x180042ad7  mov     eax, [r14+0E0h]
0x180042ade  sub     eax, esi
0x180042ae0  cmp     eax, 2
0x180042ae3  ja      short loc_180042AE8
0x180042ae5  mov     [r15], sil
0x180042ae8  lea     rcx, [rbp+var_10]
0x180042aec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042af1  nop
0x180042af2  lea     rcx, [rbp+var_30]
0x180042af6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042afb  nop
0x180042afc  lea     rcx, [rbp+var_20]
0x180042b00  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180042b05  xor     eax, eax
0x180042b07  add     rsp, 60h
0x180042b0b  pop     r15
0x180042b0d  pop     r14
0x180042b0f  pop     r12
0x180042b11  pop     rdi
0x180042b12  pop     rsi
0x180042b13  pop     rbx
0x180042b14  pop     rbp
0x180042b15  retn
```

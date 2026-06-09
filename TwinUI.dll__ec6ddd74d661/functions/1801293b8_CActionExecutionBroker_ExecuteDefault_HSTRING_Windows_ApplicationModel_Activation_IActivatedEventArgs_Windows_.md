# CActionExecutionBroker::_ExecuteDefault(HSTRING__ *,Windows::ApplicationModel::Activation::IActivatedEventArgs *,Windows::ApplicationModel::Actions::IActionActivationInfo *,HSTRING__ *)

- ea: `0x1801293b8`
- end: `0x18012983b`
- name: `?_ExecuteDefault@CActionExecutionBroker@@AEAAJPEAUHSTRING__@@PEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIActionActivationInfo@Actions@56@0@Z`
- size: `1155`
- prototype: `__int64 __fastcall(CActionExecutionBroker *this, HSTRING, struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, IUnknown *, HSTRING)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18012919c`

## callees

- `0x180041f54`
- `0x1801293b8`
- `0x180129844`
- `0x180156e50`
- `0x180156f28`
- `0x180157024`
- `0x180157134`
- `0x180376a68`
- `0x180376f3c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180129458`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180129458`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180129514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012955d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180129661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801297c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012980b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180129514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012955d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180129661`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801297c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012980b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012941d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801296a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012941d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801296a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801294f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801295f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012975b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801294f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801295f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012975b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x1801293f4`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!IUnknown_GetWindow` at `0x1801293f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CActionExecutionBroker::_ExecuteDefault(
        CActionExecutionBroker *this,
        HSTRING a2,
        struct Windows::ApplicationModel::Activation::IActivatedEventArgs *a3,
        IUnknown *a4,
        HSTRING a5)
{
  CActionExecutionBroker *v6; // rsi
  struct Windows::ApplicationModel::Activation::IActivatedEventArgs *v8; // r12
  int Window; // ebx
  const WCHAR *StringRawBuffer; // r14
  wchar_t **i; // rdi
  wchar_t *v12; // rcx
  void *v13; // rsi
  __int64 v14; // rdx
  unsigned __int16 *v15; // rbx
  const unsigned __int16 *v16; // rcx
  wchar_t *v17; // rcx
  void *v18; // rsi
  __int64 v19; // rdx
  unsigned __int16 *v20; // r12
  wchar_t *v21; // rcx
  int v22; // eax
  ImmersiveAssociationHelpers *v23; // rax
  unsigned __int16 **v24; // r9
  CActionExecutionBroker *v25; // rcx
  int v26; // eax
  void *v27; // rdi
  __int64 v28; // rdx
  unsigned __int16 *v29; // rsi
  int v30; // eax
  HSTRING string; // [rsp+30h] [rbp-40h] BYREF
  HWND phwnd; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-30h] BYREF
  __int64 v35; // [rsp+48h] [rbp-28h]
  __int64 v36; // [rsp+50h] [rbp-20h]
  unsigned __int16 *v37; // [rsp+58h] [rbp-18h] BYREF
  __int64 v38; // [rsp+60h] [rbp-10h]
  __int64 v39; // [rsp+68h] [rbp-8h]

  phwnd = 0;
  v6 = this;
  v8 = a3;
  Window = IUnknown_GetWindow(a4, &phwnd);
  if ( Window >= 0 )
  {
    pv = 0;
    v35 = 0;
    v36 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    for ( i = off_1804C0000; i != (wchar_t **)&g_appCrashUIRegisterProc; i += 4 )
    {
      if ( CompareStringOrdinal(*i, -1, StringRawBuffer, -1, 1) == 2 )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        v35 = -1;
        v36 = -1;
        if ( (int)CActionExecutionBroker::s_GetProgIdFromRegistration(StringRawBuffer, (unsigned __int16 **)&pv) >= 0 )
        {
          v37 = 0;
          v38 = 0;
          v39 = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
          v12 = i[1];
          v38 = -1;
          v39 = -1;
          v13 = pv;
          Window = CActionExecutionBroker::s_EnsureUserChosenAssociation(v12, v14, pv);
          if ( Window >= 0 )
          {
            v15 = v37;
            v37 = 0;
            v39 = 0;
            v38 = 0;
            if ( v13 )
              CoTaskMemFree(v13);
            pv = v15;
            v36 = -1;
            v35 = -1;
            WindowsDeleteString(0);
            string = 0;
            Window = GetAppIdFromProgId(v15, (HSTRING)&string);
            if ( Window >= 0 )
              Window = CActionExecutionBroker::_ExecuteAction(this, a2, string, v8, a4, a5);
            WindowsDeleteString(string);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
          goto LABEL_39;
        }
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
        v16 = i[1];
        v35 = -1;
        v36 = -1;
        if ( (int)CActionExecutionBroker::s_GetProgIdFromAssoc(v16, (unsigned __int16 **)&pv) < 0 )
        {
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
          v21 = i[1];
          v35 = -1;
          v36 = -1;
          v22 = CActionExecutionBroker::s_ShowOpenWith(v21, phwnd, 12, &pv);
          v18 = pv;
          Window = v22;
        }
        else
        {
          v37 = 0;
          v38 = 0;
          v39 = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
          v17 = i[1];
          v38 = -1;
          v39 = -1;
          v18 = pv;
          Window = CActionExecutionBroker::s_EnsureUserChosenAssociation(v17, v19, pv);
          if ( Window >= 0 )
          {
            v20 = v37;
            v37 = 0;
            v39 = 0;
            v38 = 0;
            if ( v18 )
              CoTaskMemFree(v18);
            pv = v20;
            v18 = v20;
            v36 = -1;
            v8 = a3;
            v35 = -1;
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
        }
        if ( Window >= 0 )
        {
          WindowsDeleteString(0);
          string = 0;
          if ( (int)GetAppIdFromProgId((unsigned __int16 *)v18, (HSTRING)&string) >= 0 )
          {
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
            v35 = -1;
            v36 = -1;
            v23 = (ImmersiveAssociationHelpers *)WindowsGetStringRawBuffer(string, 0);
            if ( (int)ImmersiveAssociationHelpers::GetAppProgIdForProtocol(v23, StringRawBuffer, &pv, v24) >= 0 )
            {
              v25 = this;
              goto LABEL_36;
            }
          }
          v26 = ((__int64 (__fastcall *)(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, IUnknown *))i[3])(
                  v8,
                  a4);
LABEL_37:
          Window = v26;
          goto LABEL_38;
        }
        goto LABEL_39;
      }
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
    v35 = -1;
    v36 = -1;
    if ( (int)CActionExecutionBroker::s_GetProgIdFromAssoc(StringRawBuffer, (unsigned __int16 **)&pv) < 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
      v35 = -1;
      v36 = -1;
      v30 = CActionExecutionBroker::s_ShowOpenWith(StringRawBuffer, phwnd, 140, &pv);
      v27 = pv;
      Window = v30;
    }
    else
    {
      v37 = 0;
      v38 = 0;
      v39 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
      v38 = -1;
      v39 = -1;
      v27 = pv;
      Window = CActionExecutionBroker::s_EnsureUserChosenAssociation(StringRawBuffer, v28, pv);
      if ( Window >= 0 )
      {
        v29 = v37;
        v37 = 0;
        v39 = 0;
        v38 = 0;
        if ( v27 )
          CoTaskMemFree(v27);
        pv = v29;
        v27 = v29;
        v36 = -1;
        v6 = this;
        v35 = -1;
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v37);
    }
    if ( Window >= 0 )
    {
      WindowsDeleteString(0);
      string = 0;
      Window = GetAppIdFromProgId((unsigned __int16 *)v27, (HSTRING)&string);
      if ( Window >= 0 )
      {
        v25 = v6;
LABEL_36:
        v26 = CActionExecutionBroker::_ExecuteAction(v25, a2, string, v8, a4, a5);
        goto LABEL_37;
      }
LABEL_38:
      WindowsDeleteString(string);
    }
LABEL_39:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pv);
  }
  return (unsigned int)Window;
}

```

## disassembly

```asm
0x1801293b8  mov     [rsp-38h+arg_8], rbx
0x1801293bd  mov     [rsp-38h+arg_10], r8
0x1801293c2  mov     [rsp-38h+arg_0], rcx
0x1801293c7  push    rbp
0x1801293c8  push    rsi
0x1801293c9  push    rdi
0x1801293ca  push    r12
0x1801293cc  push    r13
0x1801293ce  push    r14
0x1801293d0  push    r15
0x1801293d2  mov     rbp, rsp
0x1801293d5  sub     rsp, 70h
0x1801293d9  mov     r13, rdx
0x1801293dc  mov     [rbp+phwnd], 0
0x1801293e4  mov     rsi, rcx
0x1801293e7  lea     rdx, [rbp+phwnd]; phwnd
0x1801293eb  mov     rcx, r9; punk
0x1801293ee  mov     r15, r9
0x1801293f1  mov     r12, r8
0x1801293f4  call    cs:__imp_IUnknown_GetWindow
0x1801293fb  nop     dword ptr [rax+rax+00h]
0x180129400  mov     ebx, eax
0x180129402  test    eax, eax
0x180129404  js      loc_180129820
0x18012940a  xor     ebx, ebx
0x18012940c  xor     edx, edx; length
0x18012940e  mov     rcx, r13; string
0x180129411  mov     [rbp+pv], rbx
0x180129415  mov     [rbp+var_28], rbx
0x180129419  mov     [rbp+var_20], rbx
0x18012941d  call    cs:__imp_WindowsGetStringRawBuffer
0x180129424  nop     dword ptr [rax+rax+00h]
0x180129429  mov     r14, rax
0x18012942c  lea     rdi, off_1804C0000; "Windows.Contact.Call+telephone"
0x180129433  lea     rax, ?g_appCrashUIRegisterProc@@3PAP6AJXZA; long (*near * g_appCrashUIRegisterProc)(void)
0x18012943a  cmp     rdi, rax
0x18012943d  jz      loc_1801296DC
0x180129443  mov     rcx, [rdi]; lpString1
0x180129446  or      r9d, 0FFFFFFFFh; cchCount2
0x18012944a  or      edx, r9d; cchCount1
0x18012944d  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x180129455  mov     r8, r14; lpString2
0x180129458  call    cs:__imp_CompareStringOrdinal
0x18012945f  nop     dword ptr [rax+rax+00h]
0x180129464  cmp     eax, 2
0x180129467  jz      short loc_18012946F
0x180129469  add     rdi, 20h ; ' '
0x18012946d  jmp     short loc_180129433
0x18012946f  lea     rcx, [rbp+pv]
0x180129473  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180129478  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18012947c  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180129480  mov     rcx, r14; lpString2
0x180129483  mov     [rbp+var_28], rsi
0x180129487  mov     [rbp+var_20], rsi
0x18012948b  call    ?s_GetProgIdFromRegistration@CActionExecutionBroker@@CAJPEBGPEAPEAG@Z; CActionExecutionBroker::s_GetProgIdFromRegistration(ushort const *,ushort * *)
0x180129490  test    eax, eax
0x180129492  js      loc_180129577
0x180129498  lea     rcx, [rbp+var_18]
0x18012949c  mov     [rbp+var_18], rbx
0x1801294a0  mov     [rbp+var_10], rbx
0x1801294a4  mov     [rbp+var_8], rbx
0x1801294a8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801294ad  mov     rcx, [rdi+8]
0x1801294b1  lea     rax, [rbp+var_18]
0x1801294b5  mov     [rbp+var_10], rsi
0x1801294b9  mov     [rbp+var_8], rsi
0x1801294bd  mov     rsi, [rbp+pv]
0x1801294c1  mov     r8, rsi
0x1801294c4  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x1801294c9  call    ?s_EnsureUserChosenAssociation@CActionExecutionBroker@@CAJPEBGPEAUHWND__@@0W4IMMERSIVE_OPENWITH_FLAGS@@PEAPEAG@Z; CActionExecutionBroker::s_EnsureUserChosenAssociation(ushort const *,HWND__ *,ushort const *,IMMERSIVE_OPENWITH_FLAGS,ushort * *)
0x1801294ce  xor     edi, edi
0x1801294d0  mov     ebx, eax
0x1801294d2  test    eax, eax
0x1801294d4  js      loc_180129569
0x1801294da  mov     rbx, [rbp+var_18]
0x1801294de  mov     [rbp+var_18], rdi
0x1801294e2  mov     [rbp+var_8], rdi
0x1801294e6  mov     [rbp+var_10], rdi
0x1801294ea  test    rsi, rsi
0x1801294ed  jz      short loc_1801294FE
0x1801294ef  mov     rcx, rsi; pv
0x1801294f2  call    cs:__imp_CoTaskMemFree
0x1801294f9  nop     dword ptr [rax+rax+00h]
0x1801294fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180129502  mov     [rbp+pv], rbx
0x180129506  xor     ecx, ecx; string
0x180129508  mov     [rbp+var_20], rax
0x18012950c  mov     [rbp+var_28], rax
0x180129510  mov     [rbp+string], rdi
0x180129514  call    cs:__imp_WindowsDeleteString
0x18012951b  nop     dword ptr [rax+rax+00h]
0x180129520  lea     rdx, [rbp+string]; HSTRING
0x180129524  mov     [rbp+string], rdi
0x180129528  mov     rcx, rbx; unsigned __int16 *
0x18012952b  call    GetAppIdFromProgId
0x180129530  mov     ebx, eax
0x180129532  test    eax, eax
0x180129534  js      short loc_180129559
0x180129536  mov     rax, [rbp+arg_20]
0x18012953a  mov     r9, r12; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x18012953d  mov     r8, [rbp+string]; HSTRING
0x180129541  mov     rdx, r13; HSTRING
0x180129544  mov     rcx, [rbp+arg_0]; this
0x180129548  mov     [rsp+70h+var_48], rax; HSTRING
0x18012954d  mov     qword ptr [rsp+70h+bIgnoreCase], r15; struct Windows::ApplicationModel::Actions::IActionActivationInfo *
0x180129552  call    ?_ExecuteAction@CActionExecutionBroker@@AEAAJPEAUHSTRING__@@0PEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIActionActivationInfo@Actions@56@0@Z; CActionExecutionBroker::_ExecuteAction(HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Activation::IActivatedEventArgs *,Windows::ApplicationModel::Actions::IActionActivationInfo *,HSTRING__ *)
0x180129557  mov     ebx, eax
0x180129559  mov     rcx, [rbp+string]; string
0x18012955d  call    cs:__imp_WindowsDeleteString
0x180129564  nop     dword ptr [rax+rax+00h]
0x180129569  lea     rcx, [rbp+var_18]
0x18012956d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180129572  jmp     loc_180129817
0x180129577  lea     rcx, [rbp+pv]
0x18012957b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180129580  mov     rcx, [rdi+8]; unsigned __int16 *
0x180129584  lea     rdx, [rbp+pv]; unsigned __int16 **
0x180129588  mov     [rbp+var_28], rsi
0x18012958c  mov     [rbp+var_20], rsi
0x180129590  call    ?s_GetProgIdFromAssoc@CActionExecutionBroker@@CAJPEBGPEAPEAG@Z; CActionExecutionBroker::s_GetProgIdFromAssoc(ushort const *,ushort * *)
0x180129595  test    eax, eax
0x180129597  js      loc_180129621
0x18012959d  lea     rcx, [rbp+var_18]
0x1801295a1  mov     [rbp+var_18], rbx
0x1801295a5  mov     [rbp+var_10], rbx
0x1801295a9  mov     [rbp+var_8], rbx
0x1801295ad  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801295b2  mov     rcx, [rdi+8]
0x1801295b6  lea     rax, [rbp+var_18]
0x1801295ba  mov     [rbp+var_10], rsi
0x1801295be  mov     [rbp+var_8], rsi
0x1801295c2  mov     rsi, [rbp+pv]
0x1801295c6  mov     r8, rsi
0x1801295c9  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x1801295ce  call    ?s_EnsureUserChosenAssociation@CActionExecutionBroker@@CAJPEBGPEAUHWND__@@0W4IMMERSIVE_OPENWITH_FLAGS@@PEAPEAG@Z; CActionExecutionBroker::s_EnsureUserChosenAssociation(ushort const *,HWND__ *,ushort const *,IMMERSIVE_OPENWITH_FLAGS,ushort * *)
0x1801295d3  mov     ebx, eax
0x1801295d5  xor     eax, eax
0x1801295d7  test    ebx, ebx
0x1801295d9  js      short loc_180129616
0x1801295db  mov     r12, [rbp+var_18]
0x1801295df  mov     [rbp+var_18], rax
0x1801295e3  mov     [rbp+var_8], rax
0x1801295e7  mov     [rbp+var_10], rax
0x1801295eb  test    rsi, rsi
0x1801295ee  jz      short loc_1801295FF
0x1801295f0  mov     rcx, rsi; pv
0x1801295f3  call    cs:__imp_CoTaskMemFree
0x1801295fa  nop     dword ptr [rax+rax+00h]
0x1801295ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180129603  mov     [rbp+pv], r12
0x180129607  mov     rsi, r12
0x18012960a  mov     [rbp+var_20], rax
0x18012960e  mov     r12, [rbp+arg_10]
0x180129612  mov     [rbp+var_28], rax
0x180129616  lea     rcx, [rbp+var_18]
0x18012961a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18012961f  jmp     short loc_18012964F
0x180129621  lea     rcx, [rbp+pv]
0x180129625  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18012962a  mov     rdx, [rbp+phwnd]
0x18012962e  lea     r9, [rbp+pv]
0x180129632  mov     rcx, [rdi+8]
0x180129636  mov     r8d, 0Ch
0x18012963c  mov     [rbp+var_28], rsi
0x180129640  mov     [rbp+var_20], rsi
0x180129644  call    ?s_ShowOpenWith@CActionExecutionBroker@@CAJPEBGPEAUHWND__@@W4IMMERSIVE_OPENWITH_FLAGS@@PEAPEAG@Z; CActionExecutionBroker::s_ShowOpenWith(ushort const *,HWND__ *,IMMERSIVE_OPENWITH_FLAGS,ushort * *)
0x180129649  mov     rsi, [rbp+pv]
0x18012964d  mov     ebx, eax
0x18012964f  test    ebx, ebx
0x180129651  js      loc_180129817
0x180129657  xor     ecx, ecx; string
0x180129659  mov     [rbp+string], 0
0x180129661  call    cs:__imp_WindowsDeleteString
0x180129668  nop     dword ptr [rax+rax+00h]
0x18012966d  lea     rdx, [rbp+string]; HSTRING
0x180129671  mov     [rbp+string], 0
0x180129679  mov     rcx, rsi; unsigned __int16 *
0x18012967c  call    GetAppIdFromProgId
0x180129681  test    eax, eax
0x180129683  js      short loc_1801296C8
0x180129685  lea     rcx, [rbp+pv]
0x180129689  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18012968e  mov     rcx, [rbp+string]; string
0x180129692  or      rax, 0FFFFFFFFFFFFFFFFh
0x180129696  xor     edx, edx; length
0x180129698  mov     [rbp+var_28], rax
0x18012969c  mov     [rbp+var_20], rax
0x1801296a0  call    cs:__imp_WindowsGetStringRawBuffer
0x1801296a7  nop     dword ptr [rax+rax+00h]
0x1801296ac  lea     r8, [rbp+pv]; void **
0x1801296b0  mov     rdx, r14; unsigned __int16 *
0x1801296b3  mov     rcx, rax; this
0x1801296b6  call    ?GetAppProgIdForProtocol@ImmersiveAssociationHelpers@@YAJPEBG0PEAPEAG@Z; ImmersiveAssociationHelpers::GetAppProgIdForProtocol(ushort const *,ushort const *,ushort * *)
0x1801296bb  test    eax, eax
0x1801296bd  js      short loc_1801296C8
0x1801296bf  mov     rcx, [rbp+arg_0]
0x1801296c3  jmp     loc_1801297E8
0x1801296c8  mov     rax, [rdi+18h]
0x1801296cc  mov     rdx, r15
0x1801296cf  mov     rcx, r12
0x1801296d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801296d7  jmp     loc_180129805
0x1801296dc  lea     rcx, [rbp+pv]
0x1801296e0  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1801296e5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801296e9  lea     rdx, [rbp+pv]; unsigned __int16 **
0x1801296ed  mov     rcx, r14; unsigned __int16 *
0x1801296f0  mov     [rbp+var_28], rdi
0x1801296f4  mov     [rbp+var_20], rdi
0x1801296f8  call    ?s_GetProgIdFromAssoc@CActionExecutionBroker@@CAJPEBGPEAPEAG@Z; CActionExecutionBroker::s_GetProgIdFromAssoc(ushort const *,ushort * *)
0x1801296fd  test    eax, eax
0x1801296ff  js      loc_180129789
0x180129705  lea     rcx, [rbp+var_18]
0x180129709  mov     [rbp+var_18], rbx
0x18012970d  mov     [rbp+var_10], rbx
0x180129711  mov     [rbp+var_8], rbx
0x180129715  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18012971a  mov     [rbp+var_10], rdi
0x18012971e  lea     rax, [rbp+var_18]
0x180129722  mov     [rbp+var_8], rdi
0x180129726  mov     rcx, r14
0x180129729  mov     rdi, [rbp+pv]
0x18012972d  mov     r8, rdi
0x180129730  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x180129735  call    ?s_EnsureUserChosenAssociation@CActionExecutionBroker@@CAJPEBGPEAUHWND__@@0W4IMMERSIVE_OPENWITH_FLAGS@@PEAPEAG@Z; CActionExecutionBroker::s_EnsureUserChosenAssociation(ushort const *,HWND__ *,ushort const *,IMMERSIVE_OPENWITH_FLAGS,ushort * *)
0x18012973a  xor     r14d, r14d
0x18012973d  mov     ebx, eax
0x18012973f  test    eax, eax
0x180129741  js      short loc_18012977E
0x180129743  mov     rsi, [rbp+var_18]
0x180129747  mov     [rbp+var_18], r14
0x18012974b  mov     [rbp+var_8], r14
0x18012974f  mov     [rbp+var_10], r14
0x180129753  test    rdi, rdi
0x180129756  jz      short loc_180129767
0x180129758  mov     rcx, rdi; pv
0x18012975b  call    cs:__imp_CoTaskMemFree
0x180129762  nop     dword ptr [rax+rax+00h]
0x180129767  or      rax, 0FFFFFFFFFFFFFFFFh
0x18012976b  mov     [rbp+pv], rsi
0x18012976f  mov     rdi, rsi
0x180129772  mov     [rbp+var_20], rax
0x180129776  mov     rsi, [rbp+arg_0]
0x18012977a  mov     [rbp+var_28], rax
0x18012977e  lea     rcx, [rbp+var_18]
0x180129782  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180129787  jmp     short loc_1801297B9
0x180129789  lea     rcx, [rbp+pv]
0x18012978d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180129792  mov     rdx, [rbp+phwnd]
0x180129796  lea     r9, [rbp+pv]
0x18012979a  mov     r8d, 8Ch
0x1801297a0  mov     [rbp+var_28], rdi
0x1801297a4  mov     rcx, r14
0x1801297a7  mov     [rbp+var_20], rdi
0x1801297ab  call    ?s_ShowOpenWith@CActionExecutionBroker@@CAJPEBGPEAUHWND__@@W4IMMERSIVE_OPENWITH_FLAGS@@PEAPEAG@Z; CActionExecutionBroker::s_ShowOpenWith(ushort const *,HWND__ *,IMMERSIVE_OPENWITH_FLAGS,ushort * *)
0x1801297b0  mov     rdi, [rbp+pv]
0x1801297b4  mov     ebx, eax
0x1801297b6  xor     r14d, r14d
0x1801297b9  test    ebx, ebx
0x1801297bb  js      short loc_180129817
0x1801297bd  xor     ecx, ecx; string
0x1801297bf  mov     [rbp+string], r14
0x1801297c3  call    cs:__imp_WindowsDeleteString
0x1801297ca  nop     dword ptr [rax+rax+00h]
0x1801297cf  lea     rdx, [rbp+string]; HSTRING
0x1801297d3  mov     [rbp+string], r14
0x1801297d7  mov     rcx, rdi; unsigned __int16 *
0x1801297da  call    GetAppIdFromProgId
0x1801297df  mov     ebx, eax
0x1801297e1  test    eax, eax
0x1801297e3  js      short loc_180129807
0x1801297e5  mov     rcx, rsi; this
0x1801297e8  mov     rax, [rbp+arg_20]
0x1801297ec  mov     r9, r12; struct Windows::ApplicationModel::Activation::IActivatedEventArgs *
0x1801297ef  mov     r8, [rbp+string]; HSTRING
0x1801297f3  mov     rdx, r13; HSTRING
0x1801297f6  mov     [rsp+70h+var_48], rax; HSTRING
0x1801297fb  mov     qword ptr [rsp+70h+bIgnoreCase], r15; struct Windows::ApplicationModel::Actions::IActionActivationInfo *
0x180129800  call    ?_ExecuteAction@CActionExecutionBroker@@AEAAJPEAUHSTRING__@@0PEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIActionActivationInfo@Actions@56@0@Z; CActionExecutionBroker::_ExecuteAction(HSTRING__ *,HSTRING__ *,Windows::ApplicationModel::Activation::IActivatedEventArgs *,Windows::ApplicationModel::Actions::IActionActivationInfo *,HSTRING__ *)
0x180129805  mov     ebx, eax
0x180129807  mov     rcx, [rbp+string]; string
0x18012980b  call    cs:__imp_WindowsDeleteString
0x180129812  nop     dword ptr [rax+rax+00h]
0x180129817  lea     rcx, [rbp+pv]
0x18012981b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180129820  mov     eax, ebx
0x180129822  mov     rbx, [rsp+70h+arg_8]
0x18012982a  add     rsp, 70h
0x18012982e  pop     r15
0x180129830  pop     r14
0x180129832  pop     r13
0x180129834  pop     r12
0x180129836  pop     rdi
0x180129837  pop     rsi
0x180129838  pop     rbp
0x180129839  retn
```

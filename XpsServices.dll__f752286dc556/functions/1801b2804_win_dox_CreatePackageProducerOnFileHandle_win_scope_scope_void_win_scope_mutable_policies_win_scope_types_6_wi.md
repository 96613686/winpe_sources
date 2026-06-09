# win_dox::CreatePackageProducerOnFileHandle(win_scope::scope<void *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>,bool,win_dox::PackageSettings &,win_dox::OpcPackageContent &)

- ea: `0x1801b2804`
- end: `0x1801b294f`
- name: `?CreatePackageProducerOnFileHandle@win_dox@@YAXV?$scope@PEAXU?$mutable_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@_NAEAVPackageSettings@1@AEAVOpcPackageContent@1@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18011faf0`

## callees

- `0x1800041b0`
- `0x180012450`
- `0x18011b44c`
- `0x180134b70`
- `0x1801355e4`
- `0x1801359ce`
- `0x1801b2804`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b28aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b28aa`
- `OpcServices!__imp_CreatePackageProducerOnFileHandle` at `0x1801b286b`
- `OpcServices!__imp_CreatePackageProducerOnFileHandle` at `0x1801b286b`

## string_xrefs

- `0x1801b28f3`: `Call to ::CreatePackageProducerOnFileHandle failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall win_dox::CreatePackageProducerOnFileHandle(HANDLE *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rdi
  __int64 v7; // r14
  HANDLE v8; // rcx
  int result; // eax
  int v10; // ebx
  __int64 v11; // [rsp+40h] [rbp-4E8h] BYREF
  _QWORD v12[3]; // [rsp+48h] [rbp-4E0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-4C8h] BYREF
  wchar_t v14[512]; // [rsp+100h] [rbp-428h] BYREF

  v12[1] = a1;
  win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(
    &v11,
    a4);
  v6 = v11;
  win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(
    v12,
    a3);
  v7 = v12[0];
  v8 = *a1;
  *a1 = (HANDLE)-1LL;
  result = CreatePackageProducerOnFileHandle(v8, 1, v7, v6);
  v10 = result;
  if ( v7 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v6 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v10 < 0 )
  {
    memset_0(v14, 0, sizeof(v14));
    StringCchPrintfW(
      v14,
      0x200u,
      L"Call to ::CreatePackageProducerOnFileHandle failed with HResult 0x%X.",
      (unsigned int)v10);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x51u,
      v10,
      (__int64)v14);
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *a1 != (HANDLE)-1LL )
  {
    result = CloseHandle(*a1);
    *a1 = (HANDLE)-1LL;
  }
  return result;
}

```

## disassembly

```asm
0x1801b2804  mov     [rsp+arg_8], rbx
0x1801b2809  push    rsi
0x1801b280a  push    rdi
0x1801b280b  push    r14
0x1801b280d  sub     rsp, 510h
0x1801b2814  mov     rax, cs:__security_cookie
0x1801b281b  xor     rax, rsp
0x1801b281e  mov     [rsp+528h+var_28], rax
0x1801b2826  mov     rbx, r8
0x1801b2829  mov     rsi, rcx
0x1801b282c  mov     [rsp+528h+var_4D8], rcx
0x1801b2831  mov     rdx, r9
0x1801b2834  lea     rcx, [rsp+528h+var_4E8]
0x1801b2839  call    ??0?$scope@PEAUIXpsOMCanvas@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1801b283e  nop
0x1801b283f  mov     rdi, [rsp+528h+var_4E8]
0x1801b2844  mov     rdx, rbx
0x1801b2847  lea     rcx, [rsp+528h+var_4E0]
0x1801b284c  call    ??0?$scope@PEAUIXpsOMCanvas@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1801b2851  mov     r14, [rsp+528h+var_4E0]
0x1801b2856  mov     rcx, [rsi]
0x1801b2859  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1801b2860  mov     r9, rdi
0x1801b2863  mov     r8, r14
0x1801b2866  mov     edx, 1
0x1801b286b  call    cs:__imp_CreatePackageProducerOnFileHandle
0x1801b2871  mov     ebx, eax
0x1801b2873  test    r14, r14
0x1801b2876  jz      short loc_1801B2888
0x1801b2878  mov     rdx, [r14]
0x1801b287b  mov     rcx, r14
0x1801b287e  mov     rax, [rdx+10h]
0x1801b2882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2887  nop
0x1801b2888  test    rdi, rdi
0x1801b288b  jz      short loc_1801B289D
0x1801b288d  mov     rax, [rdi]
0x1801b2890  mov     rcx, rdi
0x1801b2893  mov     rax, [rax+10h]
0x1801b2897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b289c  nop
0x1801b289d  test    ebx, ebx
0x1801b289f  js      short loc_1801B28DB
0x1801b28a1  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1801b28a5  jz      short loc_1801B28B7
0x1801b28a7  mov     rcx, [rsi]; hObject
0x1801b28aa  call    cs:__imp_CloseHandle
0x1801b28b0  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1801b28b7  mov     rcx, [rsp+528h+var_28]
0x1801b28bf  xor     rcx, rsp; StackCookie
0x1801b28c2  call    __security_check_cookie
0x1801b28c7  mov     rbx, [rsp+528h+arg_8]
0x1801b28cf  add     rsp, 510h
0x1801b28d6  pop     r14
0x1801b28d8  pop     rdi
0x1801b28d9  pop     rsi
0x1801b28da  retn
0x1801b28db  xor     edx, edx; Val
0x1801b28dd  mov     r8d, 400h; Size
0x1801b28e3  lea     rcx, [rsp+528h+var_428]; void *
0x1801b28eb  call    memset_0
0x1801b28f0  mov     r9d, ebx
0x1801b28f3  lea     r8, aCallToCreatepa_1; "Call to ::CreatePackageProducerOnFileHa"...
0x1801b28fa  mov     edx, 200h; unsigned __int64
0x1801b28ff  lea     rcx, [rsp+528h+var_428]; wchar_t *
0x1801b2907  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801b290c  lea     rax, [rsp+528h+var_428]
0x1801b2914  mov     [rsp+528h+var_4F8], rax; __int64
0x1801b2919  mov     [rsp+528h+var_500], ebx; int
0x1801b291d  mov     [rsp+528h+var_508], 51h ; 'Q'; unsigned int
0x1801b2925  lea     r9, Src
0x1801b292c  lea     r8, aNoFilename; "(no filename)"
0x1801b2933  lea     rcx, [rsp+528h+pExceptionObject]; this
0x1801b2938  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801b293d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801b2944  lea     rcx, [rsp+528h+pExceptionObject]; pExceptionObject
0x1801b2949  call    _CxxThrowException_0
```

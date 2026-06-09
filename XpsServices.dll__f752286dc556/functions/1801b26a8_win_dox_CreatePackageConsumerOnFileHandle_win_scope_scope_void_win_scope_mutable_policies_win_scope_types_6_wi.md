# win_dox::CreatePackageConsumerOnFileHandle(win_scope::scope<void *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<int (*)(void *),&CloseHandle(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::invalid_handle_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>,bool,bool)

- ea: `0x1801b26a8`
- end: `0x1801b27fd`
- name: `?CreatePackageConsumerOnFileHandle@win_dox@@YA?AVOpcPackageContent@1@V?$scope@PEAXU?$mutable_policies@U?$types_6@U?$close_function@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Uinvalid_handle_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@_N1@Z`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18011ff54`

## callees

- `0x1800041b0`
- `0x180005664`
- `0x180012450`
- `0x1800c5ac8`
- `0x18011b44c`
- `0x180134b70`
- `0x1801355e4`
- `0x1801359ce`
- `0x1801b26a8`
- `0x1801c7010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b2768`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b2768`
- `OpcServices!__imp_CreatePackageConsumerOnFileHandle` at `0x1801b2719`
- `OpcServices!__imp_CreatePackageConsumerOnFileHandle` at `0x1801b2719`

## string_xrefs

- `0x1801b27a9`: `Call to ::CreatePackageConsumerOnFileHandle failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall win_dox::CreatePackageConsumerOnFileHandle(
        __int64 a1,
        HANDLE *a2,
        unsigned __int8 a3,
        unsigned __int8 a4)
{
  unsigned int v4; // edi
  unsigned int v5; // ebx
  HANDLE v8; // rcx
  int v9; // ebx
  _QWORD *v10; // rax
  __int64 v12; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v15[512]; // [rsp+100h] [rbp+0h] BYREF

  v4 = a4;
  v5 = a3;
  v13[0] = a1;
  v13[2] = a2;
  v12 = 0;
  win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(
    &v12,
    0);
  v12 = 0;
  v8 = *a2;
  *a2 = (HANDLE)-1LL;
  v9 = CreatePackageConsumerOnFileHandle(v8, v5, v4, &v12);
  if ( v9 < 0 )
  {
    memset_0(v15, 0, sizeof(v15));
    StringCchPrintfW(
      v15,
      0x200u,
      L"Call to ::CreatePackageConsumerOnFileHandle failed with HResult 0x%X.",
      (unsigned int)v9);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::THResultException *)pExceptionObject,
      0x25u,
      v9,
      (__int64)v15);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v10 = (_QWORD *)win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(
                    v13,
                    &v12);
  win_dox::OpcPackageContent::OpcPackageContent(a1, v10);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( *a2 != (HANDLE)-1LL )
  {
    CloseHandle(*a2);
    *a2 = (HANDLE)-1LL;
  }
  return a1;
}

```

## disassembly

```asm
0x1801b26a8  push    rbp
0x1801b26aa  push    rbx
0x1801b26ab  push    rsi
0x1801b26ac  push    rdi
0x1801b26ad  push    r14
0x1801b26af  lea     rbp, [rsp-410h]
0x1801b26b7  sub     rsp, 510h
0x1801b26be  mov     rax, cs:__security_cookie
0x1801b26c5  xor     rax, rsp
0x1801b26c8  mov     [rbp+430h+var_30], rax
0x1801b26cf  movzx   edi, r9b
0x1801b26d3  movzx   ebx, r8b
0x1801b26d7  mov     rsi, rdx
0x1801b26da  mov     r14, rcx
0x1801b26dd  mov     [rsp+530h+var_4E8], rcx
0x1801b26e2  mov     [rsp+530h+var_4D8], rdx
0x1801b26e7  mov     [rsp+530h+var_4F0], 0
0x1801b26f0  xor     edx, edx
0x1801b26f2  lea     rcx, [rsp+530h+var_4F0]
0x1801b26f7  call    ?reset@?$scope_helper@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@detail@win_scope@@SAXAEAV?$scope@PEAUIXpsPageRelationshipCollection@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@3@PEAUIXpsPageRelationshipCollection@@@Z; win_scope::detail::scope_helper<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>>::reset(win_scope::scope<IXpsPageRelationshipCollection *,win_scope::const_policies<win_scope::com_policies>> &,IXpsPageRelationshipCollection *)
0x1801b26fc  mov     [rsp+530h+var_4F0], 0
0x1801b2705  mov     rcx, [rsi]
0x1801b2708  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1801b270f  mov     r8d, edi
0x1801b2712  mov     edx, ebx
0x1801b2714  lea     r9, [rsp+530h+var_4F0]
0x1801b2719  call    cs:__imp_CreatePackageConsumerOnFileHandle
0x1801b271f  mov     ebx, eax
0x1801b2721  test    eax, eax
0x1801b2723  js      short loc_1801B2795
0x1801b2725  lea     rdx, [rsp+530h+var_4F0]
0x1801b272a  lea     rcx, [rsp+530h+var_4E8]
0x1801b272f  call    ??0?$scope@PEAUIXpsOMCanvas@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<IXpsOMCanvas *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1801b2734  mov     rdx, rax
0x1801b2737  mov     rcx, r14
0x1801b273a  call    ??$?0V?$scope@PEAUIOpcPackageContent@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@OpcPackageContent@win_dox@@QEAA@V?$scope@PEAUIOpcPackageContent@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@@Z; win_dox::OpcPackageContent::OpcPackageContent(win_scope::scope<IOpcPackageContent *,win_scope::const_policies<win_scope::com_policies>>)
0x1801b273f  nop
0x1801b2740  mov     rcx, [rsp+530h+var_4F0]
0x1801b2745  test    rcx, rcx
0x1801b2748  jz      short loc_1801B275F
0x1801b274a  mov     rax, [rcx]
0x1801b274d  mov     rax, [rax+10h]
0x1801b2751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b2756  mov     [rsp+530h+var_4F0], 0
0x1801b275f  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1801b2763  jz      short loc_1801B2775
0x1801b2765  mov     rcx, [rsi]; hObject
0x1801b2768  call    cs:__imp_CloseHandle
0x1801b276e  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x1801b2775  mov     rax, r14
0x1801b2778  mov     rcx, [rbp+430h+var_30]
0x1801b277f  xor     rcx, rsp; StackCookie
0x1801b2782  call    __security_check_cookie
0x1801b2787  add     rsp, 510h
0x1801b278e  pop     r14
0x1801b2790  pop     rdi
0x1801b2791  pop     rsi
0x1801b2792  pop     rbx
0x1801b2793  pop     rbp
0x1801b2794  retn
0x1801b2795  xor     edx, edx; Val
0x1801b2797  mov     r8d, 400h; Size
0x1801b279d  lea     rcx, [rbp+430h+var_430]; void *
0x1801b27a1  call    memset_0
0x1801b27a6  mov     r9d, ebx
0x1801b27a9  lea     r8, aCallToCreatepa_5; "Call to ::CreatePackageConsumerOnFileHa"...
0x1801b27b0  mov     edx, 200h; unsigned __int64
0x1801b27b5  lea     rcx, [rbp+430h+var_430]; wchar_t *
0x1801b27b9  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801b27be  lea     rax, [rbp+430h+var_430]
0x1801b27c2  mov     [rsp+530h+var_500], rax; __int64
0x1801b27c7  mov     [rsp+530h+var_508], ebx; int
0x1801b27cb  mov     [rsp+530h+var_510], 25h ; '%'; unsigned int
0x1801b27d3  lea     r9, Src
0x1801b27da  lea     r8, aNoFilename; "(no filename)"
0x1801b27e1  lea     rcx, [rsp+530h+pExceptionObject]; this
0x1801b27e6  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1801b27eb  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1801b27f2  lea     rcx, [rsp+530h+pExceptionObject]; pExceptionObject
0x1801b27f7  call    _CxxThrowException_0
```

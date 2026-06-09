# OOBEOneDriveOptin::GetFolderMoveStatusesForAccount(ushort const *,ushort const *,ushort const *,uint *,OneDriveKnownFolderMoveStatusEntry * *)

- ea: `0x18001a3a0`
- end: `0x18001a815`
- name: `?GetFolderMoveStatusesForAccount@OOBEOneDriveOptin@@UEAAJPEBG00PEAIPEAPEAUOneDriveKnownFolderMoveStatusEntry@@@Z`
- size: `1141`
- prototype: `__int64 __fastcall(OOBEOneDriveOptin *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, struct OneDriveKnownFolderMoveStatusEntry **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800032b0`
- `0x180007134`
- `0x180009f90`
- `0x18001136c`
- `0x180017d18`
- `0x180018554`
- `0x180018c78`
- `0x18001a3a0`
- `0x18001cf00`
- `0x18001d1d8`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a6dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a6dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a40a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a40a`

## string_xrefs

- `0x18001a4b8`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001a530`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001a670`: `shell\oobe\user\dll\oobesyncengineapi.cpp`
- `0x18001a6f7`: `shell\oobe\user\dll\oobesyncengineapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall OOBEOneDriveOptin::GetFolderMoveStatusesForAccount(
        OOBEOneDriveOptin *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        struct OneDriveKnownFolderMoveStatusEntry **a6)
{
  LPVOID v9; // rsi
  __int64 (__fastcall *v10)(LPVOID, _QWORD, __int64, __int64); // r15
  __int64 v11; // rdi
  __int64 v12; // rbx
  _QWORD *bstr; // rax
  int v14; // ebx
  int v16[2]; // [rsp+50h] [rbp-49h] BYREF
  int v17; // [rsp+58h] [rbp-41h] BYREF
  __int64 v18; // [rsp+60h] [rbp-39h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v20[8]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  *a5 = 0;
  *a6 = 0;
  *(_QWORD *)v16 = 0;
  ppv = 0;
  if ( CoCreateInstance(
         &GUID_07ca83f0_df06_4e67_89dd_e80924a49512,
         0,
         4u,
         &GUID_ee6a6d4e_1a56_48e1_8aff_268072b66738,
         &ppv) < 0 )
    goto LABEL_4;
  v9 = ppv;
  v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int64))(*(_QWORD *)ppv + 24LL);
  *(_QWORD *)v16 = 0;
  v11 = *(_QWORD *)wil::make_bstr(v20, a4);
  v12 = *(_QWORD *)wil::make_bstr(&v17, a3);
  bstr = (_QWORD *)wil::make_bstr(&v18, a2);
  v14 = v10(v9, *bstr, v12, v11);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v20);
  if ( v14 >= 0 )
  {
LABEL_4:
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&ppv);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v16);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"shell\\oobe\\user\\dll\\oobesyncengineapi.cpp",
      (const char *)(unsigned int)v14,
      (int)v16);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(&ppv);
    wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(v16);
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x18001a3a0  mov     [rsp-8+arg_0], rbx
0x18001a3a5  push    rbp
0x18001a3a6  push    rsi
0x18001a3a7  push    rdi
0x18001a3a8  push    r12
0x18001a3aa  push    r13
0x18001a3ac  push    r14
0x18001a3ae  push    r15
0x18001a3b0  lea     rbp, [rsp-17h]
0x18001a3b5  sub     rsp, 0B0h
0x18001a3bc  mov     rax, cs:__security_cookie
0x18001a3c3  xor     rax, rsp
0x18001a3c6  mov     [rbp+47h+var_40], rax
0x18001a3ca  mov     rdi, r9
0x18001a3cd  mov     rbx, r8
0x18001a3d0  mov     r14, rdx
0x18001a3d3  mov     r12, [rbp+47h+arg_20]
0x18001a3d7  mov     r13, [rbp+47h+arg_28]
0x18001a3db  xor     esi, esi
0x18001a3dd  mov     [r12], esi
0x18001a3e1  mov     [r13+0], rsi
0x18001a3e5  mov     qword ptr [rbp+47h+var_90], rsi
0x18001a3e9  mov     [rbp+47h+var_78], rsi
0x18001a3ed  lea     rax, [rbp+47h+var_78]
0x18001a3f1  mov     [rsp+0E0h+ppv], rax; ppv
0x18001a3f6  lea     r9, _GUID_ee6a6d4e_1a56_48e1_8aff_268072b66738; riid
0x18001a3fd  xor     edx, edx; pUnkOuter
0x18001a3ff  lea     r8d, [rsi+4]; dwClsContext
0x18001a403  lea     rcx, _GUID_07ca83f0_df06_4e67_89dd_e80924a49512; rclsid
0x18001a40a  call    cs:__imp_CoCreateInstance
0x18001a410  test    eax, eax
0x18001a412  js      loc_18001A7D9
0x18001a418  mov     rsi, [rbp+47h+var_78]
0x18001a41c  mov     rax, [rsi]
0x18001a41f  mov     r15, [rax+18h]
0x18001a423  mov     rcx, qword ptr [rbp+47h+var_90]
0x18001a427  mov     qword ptr [rbp+47h+var_90], 0
0x18001a42f  test    rcx, rcx
0x18001a432  jz      short loc_18001A441
0x18001a434  mov     rax, [rcx]
0x18001a437  mov     rax, [rax+10h]
0x18001a43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a440  nop
0x18001a441  mov     rdx, rdi
0x18001a444  lea     rcx, [rbp+47h+var_60]
0x18001a448  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18001a44d  nop
0x18001a44e  mov     rdi, [rax]
0x18001a451  mov     rdx, rbx
0x18001a454  lea     rcx, [rbp+47h+var_88]
0x18001a458  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18001a45d  nop
0x18001a45e  mov     rbx, [rax]
0x18001a461  mov     rdx, r14
0x18001a464  lea     rcx, [rbp+47h+var_80]
0x18001a468  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18001a46d  nop
0x18001a46e  lea     rcx, [rbp+47h+var_90]
0x18001a472  mov     [rsp+0E0h+ppv], rcx; int
0x18001a477  mov     r9, rdi
0x18001a47a  mov     r8, rbx
0x18001a47d  mov     rdx, [rax]
0x18001a480  mov     rcx, rsi
0x18001a483  mov     rax, r15
0x18001a486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a48b  mov     ebx, eax
0x18001a48d  lea     rcx, [rbp+47h+var_80]
0x18001a491  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a496  nop
0x18001a497  lea     rcx, [rbp+47h+var_88]
0x18001a49b  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a4a0  nop
0x18001a4a1  lea     rcx, [rbp+47h+var_60]
0x18001a4a5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a4aa  xor     r15d, r15d
0x18001a4ad  test    ebx, ebx
0x18001a4af  jns     short loc_18001A4CE
0x18001a4b1  mov     rcx, [rbp+4Fh]; this
0x18001a4b5  mov     r9d, ebx; char *
0x18001a4b8  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001a4bf  mov     edx, 22Ah; void *
0x18001a4c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a4c9  jmp     loc_18001A744
0x18001a4ce  mov     rbx, qword ptr [rbp+47h+var_90]
0x18001a4d2  test    rbx, rbx
0x18001a4d5  jz      loc_18001A7D9
0x18001a4db  mov     [rbp+47h+var_98], r15d
0x18001a4df  mov     [rbp+47h+var_70], r15
0x18001a4e3  mov     [rbp+47h+var_68], r15
0x18001a4e7  mov     rax, [rbx]
0x18001a4ea  mov     rdi, [rax+38h]
0x18001a4ee  lea     rcx, [rbp+47h+var_70]
0x18001a4f2  call    ?reset@?$unique_any_array_ptr@PEAUIKFMEnrollmentStatus@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<IKFMEnrollmentStatus *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(void)
0x18001a4f7  mov     rdx, r14
0x18001a4fa  lea     rcx, [rbp+47h+var_60]
0x18001a4fe  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18001a503  nop
0x18001a504  lea     r9, [rbp+47h+var_70]
0x18001a508  lea     r8, [rbp+47h+var_98]
0x18001a50c  mov     rdx, [rax]
0x18001a50f  mov     rcx, rbx
0x18001a512  mov     rax, rdi
0x18001a515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a51a  mov     ebx, eax
0x18001a51c  lea     rcx, [rbp+47h+var_60]
0x18001a520  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a525  test    ebx, ebx
0x18001a527  jns     short loc_18001A546
0x18001a529  mov     rcx, [rbp+4Fh]; this
0x18001a52d  mov     r9d, ebx; char *
0x18001a530  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001a537  mov     edx, 234h; void *
0x18001a53c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a541  jmp     loc_18001A73A
0x18001a546  mov     ecx, [rbp+47h+var_98]
0x18001a549  test    ecx, ecx
0x18001a54b  jz      loc_18001A7CF
0x18001a551  xorps   xmm0, xmm0
0x18001a554  movdqu  [rbp+47h+var_B0], xmm0
0x18001a559  mov     rax, r15
0x18001a55c  mov     [rbp+47h+var_A0], rax
0x18001a560  mov     ebx, r15d
0x18001a563  mov     eax, ebx
0x18001a565  mov     rdx, [rbp+47h+var_70]
0x18001a569  mov     rdx, [rdx+rax*8]
0x18001a56d  lea     rcx, [rbp+47h+var_80]
0x18001a571  call    ??0?$com_ptr_t@UIKFMEnrollmentStatus@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIKFMEnrollmentStatus@@@Z; wil::com_ptr_t<IKFMEnrollmentStatus,wil::err_exception_policy>::com_ptr_t<IKFMEnrollmentStatus,wil::err_exception_policy>(IKFMEnrollmentStatus *)
0x18001a576  nop
0x18001a577  mov     [rbp+47h+var_88], r15d
0x18001a57b  mov     rdi, [rbp+47h+var_80]
0x18001a57f  mov     rax, [rdi]
0x18001a582  lea     rdx, [rbp+47h+var_88]
0x18001a586  mov     rcx, rdi
0x18001a589  mov     rax, [rax+18h]
0x18001a58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a592  mov     esi, eax
0x18001a594  test    eax, eax
0x18001a596  js      loc_18001A668
0x18001a59c  cmp     [rbp+47h+var_88], r15d
0x18001a5a0  jz      short loc_18001A613
0x18001a5a2  xorps   xmm0, xmm0
0x18001a5a5  xor     eax, eax
0x18001a5a7  movups  [rbp+47h+var_58], xmm0
0x18001a5ab  mov     [rbp+47h+var_48], eax
0x18001a5ae  mov     rax, [rdi]
0x18001a5b1  lea     rdx, [rbp+47h+var_58]
0x18001a5b5  mov     rcx, rdi
0x18001a5b8  mov     rax, [rax+20h]
0x18001a5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5c1  mov     esi, eax
0x18001a5c3  test    eax, eax
0x18001a5c5  js      loc_18001A661
0x18001a5cb  cmp     [rbp+47h+var_88], 3
0x18001a5cf  jnz     short loc_18001A5DA
0x18001a5d1  mov     [rbp+47h+var_48], 2
0x18001a5d8  jmp     short loc_18001A5E7
0x18001a5da  mov     eax, r15d
0x18001a5dd  cmp     [rbp+47h+var_88], 2
0x18001a5e1  setz    al
0x18001a5e4  mov     [rbp+47h+var_48], eax
0x18001a5e7  mov     rdx, qword ptr [rbp+47h+var_B0+8]
0x18001a5eb  cmp     rdx, [rbp+47h+var_A0]
0x18001a5ef  jz      short loc_18001A605
0x18001a5f1  movups  xmm0, [rbp+47h+var_58]
0x18001a5f5  movups  xmmword ptr [rdx], xmm0
0x18001a5f8  mov     eax, [rbp+47h+var_48]
0x18001a5fb  mov     [rdx+10h], eax
0x18001a5fe  add     qword ptr [rbp+47h+var_B0+8], 14h
0x18001a603  jmp     short loc_18001A613
0x18001a605  lea     r8, [rbp+47h+var_58]
0x18001a609  lea     rcx, [rbp+47h+var_B0]
0x18001a60d  call    ??$_Emplace_reallocate@AEBUOneDriveKnownFolderMoveStatusEntry@@@?$vector@UOneDriveKnownFolderMoveStatusEntry@@V?$allocator@UOneDriveKnownFolderMoveStatusEntry@@@std@@@std@@AEAAPEAUOneDriveKnownFolderMoveStatusEntry@@QEAU2@AEBU2@@Z; std::vector<OneDriveKnownFolderMoveStatusEntry>::_Emplace_reallocate<OneDriveKnownFolderMoveStatusEntry const &>(OneDriveKnownFolderMoveStatusEntry * const,OneDriveKnownFolderMoveStatusEntry const &)
0x18001a612  nop
0x18001a613  lea     rcx, [rbp+47h+var_80]
0x18001a617  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001a61c  inc     ebx
0x18001a61e  cmp     ebx, [rbp+47h+var_98]
0x18001a621  jb      loc_18001A563
0x18001a627  mov     rax, [rbp+47h+var_A0]
0x18001a62b  mov     rcx, qword ptr [rbp+47h+var_B0]
0x18001a62f  mov     rbx, qword ptr [rbp+47h+var_B0+8]
0x18001a633  sub     rbx, rcx
0x18001a636  sar     rbx, 2
0x18001a63a  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x18001a644  imul    rbx, rdi
0x18001a648  test    ebx, ebx
0x18001a64a  jnz     loc_18001A6D3
0x18001a650  test    rcx, rcx
0x18001a653  jz      loc_18001A7CF
0x18001a659  sub     rax, rcx
0x18001a65c  jmp     loc_18001A7AE
0x18001a661  mov     edx, 247h
0x18001a666  jmp     short loc_18001A66D
0x18001a668  mov     edx, 243h; void *
0x18001a66d  mov     r9d, esi; char *
0x18001a670  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001a677  mov     rcx, [rbp+4Fh]; this
0x18001a67b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a680  nop
0x18001a681  lea     rcx, [rbp+47h+var_80]
0x18001a685  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001a68a  nop
0x18001a68b  mov     rcx, qword ptr [rbp+47h+var_B0]
0x18001a68f  test    rcx, rcx
0x18001a692  jz      short loc_18001A6C6
0x18001a694  mov     rax, [rbp+47h+var_A0]
0x18001a698  sub     rax, rcx
0x18001a69b  sar     rax, 2
0x18001a69f  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x18001a6a9  imul    rax, rdi
0x18001a6ad  lea     rdx, [rax+rax*4]
0x18001a6b1  shl     rdx, 2
0x18001a6b5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001a6ba  xorps   xmm0, xmm0
0x18001a6bd  movdqu  [rbp+47h+var_B0], xmm0
0x18001a6c2  mov     [rbp+47h+var_A0], r15
0x18001a6c6  lea     rcx, [rbp+47h+var_70]
0x18001a6ca  call    ?reset@?$unique_any_array_ptr@PEAUIKFMEnrollmentStatus@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<IKFMEnrollmentStatus *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(void)
0x18001a6cf  mov     ebx, esi
0x18001a6d1  jmp     short loc_18001A744
0x18001a6d3  mov     eax, ebx
0x18001a6d5  lea     rcx, [rax+rax*4]
0x18001a6d9  shl     rcx, 2; cb
0x18001a6dd  call    cs:__imp_CoTaskMemAlloc
0x18001a6e3  mov     r9, rax
0x18001a6e6  test    rax, rax
0x18001a6e9  jnz     short loc_18001A75E
0x18001a6eb  mov     rcx, [rbp+4Fh]; this
0x18001a6ef  mov     ebx, 8007000Eh
0x18001a6f4  mov     r9d, ebx; char *
0x18001a6f7  lea     r8, aShellOobeUserD_8; "shell\\oobe\\user\\dll\\oobesyncenginea"...
0x18001a6fe  mov     edx, 256h; void *
0x18001a703  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a708  nop
0x18001a709  mov     rcx, qword ptr [rbp+47h+var_B0]
0x18001a70d  test    rcx, rcx
0x18001a710  jz      short loc_18001A73A
0x18001a712  mov     rax, [rbp+47h+var_A0]
0x18001a716  sub     rax, rcx
0x18001a719  sar     rax, 2
0x18001a71d  imul    rax, rdi
0x18001a721  lea     rdx, [rax+rax*4]
0x18001a725  shl     rdx, 2
0x18001a729  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001a72e  xorps   xmm0, xmm0
0x18001a731  movdqu  [rbp+47h+var_B0], xmm0
0x18001a736  mov     [rbp+47h+var_A0], r15
0x18001a73a  lea     rcx, [rbp+47h+var_70]
0x18001a73e  call    ?reset@?$unique_any_array_ptr@PEAUIKFMEnrollmentStatus@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<IKFMEnrollmentStatus *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(void)
0x18001a743  nop
0x18001a744  lea     rcx, [rbp+47h+var_78]
0x18001a748  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001a74d  nop
0x18001a74e  lea     rcx, [rbp+47h+var_90]
0x18001a752  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001a757  mov     eax, ebx
0x18001a759  jmp     loc_18001A7EE
0x18001a75e  mov     r10d, r15d
0x18001a761  mov     r8, qword ptr [rbp+47h+var_B0]
0x18001a765  mov     r11, qword ptr [rbp+47h+var_B0+8]
0x18001a769  cmp     r8, r11
0x18001a76c  jz      short loc_18001A797
0x18001a76e  movups  xmm0, xmmword ptr [r8]
0x18001a772  mov     edx, [r8+10h]
0x18001a776  mov     eax, r10d
0x18001a779  lea     rcx, [rax+rax*4]
0x18001a77d  movups  xmmword ptr [r9+rcx*4], xmm0
0x18001a782  mov     [r9+rcx*4+10h], edx
0x18001a787  inc     r10d
0x18001a78a  add     r8, 14h
0x18001a78e  cmp     r8, r11
0x18001a791  jnz     short loc_18001A76E
0x18001a793  mov     r8, qword ptr [rbp+47h+var_B0]
0x18001a797  mov     [r12], ebx
0x18001a79b  mov     [r13+0], r9
0x18001a79f  test    r8, r8
0x18001a7a2  jz      short loc_18001A7CF
0x18001a7a4  mov     rax, [rbp+47h+var_A0]
0x18001a7a8  sub     rax, r8
0x18001a7ab  mov     rcx, r8
0x18001a7ae  sar     rax, 2
0x18001a7b2  imul    rax, rdi
0x18001a7b6  lea     rdx, [rax+rax*4]
0x18001a7ba  shl     rdx, 2
0x18001a7be  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001a7c3  xorps   xmm0, xmm0
0x18001a7c6  mov     [rbp+47h+var_A0], r15
0x18001a7ca  movdqu  [rbp+47h+var_B0], xmm0
0x18001a7cf  lea     rcx, [rbp+47h+var_70]
0x18001a7d3  call    ?reset@?$unique_any_array_ptr@PEAUIKFMEnrollmentStatus@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Ucom_unknown_deleter@details@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<IKFMEnrollmentStatus *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(void)
0x18001a7d8  nop
0x18001a7d9  lea     rcx, [rbp+47h+var_78]
0x18001a7dd  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001a7e2  nop
0x18001a7e3  lea     rcx, [rbp+47h+var_90]
0x18001a7e7  call    ??1?$com_ptr_t@UIPinnedList2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPinnedList2,wil::err_exception_policy>::~com_ptr_t<IPinnedList2,wil::err_exception_policy>(void)
0x18001a7ec  xor     eax, eax
0x18001a7ee  mov     rcx, [rbp+47h+var_40]
0x18001a7f2  xor     rcx, rsp; StackCookie
0x18001a7f5  call    __security_check_cookie
  ... truncated ...
```

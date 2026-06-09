# ScheduledTask::_GetTrigger(ushort *)

- ea: `0x180010a80`
- end: `0x180010c3b`
- name: `?_GetTrigger@ScheduledTask@@AEAA?AV?$ComPtr@UITrigger@@@WRL@Microsoft@@PEAG@Z`
- size: `443`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000f39c`
- `0x18000f4f8`
- `0x18000fd38`
- `0x18000fe94`

## callees

- `0x18000556c`
- `0x18000760c`
- `0x18000d63c`
- `0x180010150`
- `0x180010170`
- `0x180010a80`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010b69`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180010b69`

## string_xrefs

- `0x180010bb6`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x180010bea`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x180010bff`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x180010c14`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x180010c29`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 **__fastcall ScheduledTask::_GetTrigger(__int64 a1, __int64 **a2, const char *a3)
{
  unsigned int v5; // esi
  int v6; // eax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // esi
  int v10; // eax
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v15; // eax
  int bIgnoreCase; // [rsp+20h] [rbp-20h]
  LPCWCH lpString1; // [rsp+30h] [rbp-10h] BYREF
  __int64 v18; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v20; // [rsp+70h] [rbp+30h] BYREF
  __int64 **v21; // [rsp+78h] [rbp+38h]
  int v22; // [rsp+88h] [rbp+48h]

  v21 = a2;
  v5 = 1;
  v22 = 1;
  v18 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 40) + 72LL))(*(_QWORD *)(a1 + 40), &v18);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  v20 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v20);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
  v8 = 1;
  if ( v20 < 1 )
  {
LABEL_11:
    v15 = wil::verify_hresult<long>(2147943568LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x120,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)v15,
      (int)"Cannot Find Trigger : %ws",
      a3);
  }
  while ( 1 )
  {
    *a2 = 0;
    v9 = v5 | 1;
    v22 = v9;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v18 + 64LL))(v18, v8, a2);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
        (const char *)(unsigned int)v10,
        bIgnoreCase);
    lpString1 = 0;
    v11 = *a2;
    v12 = **a2;
    lpString1 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, LPCWCH *))(v12 + 64))(v11, &lpString1);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
    if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)a3, -1, 1) == 2 )
      break;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
    v5 = v9 & 0xFFFFFFFE;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
    if ( (int)++v8 > v20 )
      goto LABEL_11;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpString1);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  return a2;
}

```

## disassembly

```asm
0x180010a80  mov     [rsp-28h+arg_8], rdx
0x180010a85  push    rbp
0x180010a86  push    rbx
0x180010a87  push    rsi
0x180010a88  push    rdi
0x180010a89  push    r14
0x180010a8b  mov     rbp, rsp
0x180010a8e  sub     rsp, 40h
0x180010a92  mov     r14, r8
0x180010a95  mov     rdi, rdx
0x180010a98  mov     esi, 1
0x180010a9d  mov     [rbp+arg_18], esi
0x180010aa0  mov     [rbp+var_8], 0
0x180010aa8  mov     rcx, [rcx+28h]
0x180010aac  mov     rax, [rcx]
0x180010aaf  lea     rdx, [rbp+var_8]
0x180010ab3  mov     rax, [rax+48h]
0x180010ab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010abc  mov     rcx, [rbp+28h]; this
0x180010ac0  test    eax, eax
0x180010ac2  js      loc_180010C11
0x180010ac8  mov     [rbp+arg_0], 0
0x180010acf  mov     rcx, [rbp+var_8]
0x180010ad3  mov     rax, [rcx]
0x180010ad6  lea     rdx, [rbp+arg_0]
0x180010ada  mov     rax, [rax+38h]
0x180010ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ae3  mov     rcx, [rbp+28h]; this
0x180010ae7  test    eax, eax
0x180010ae9  js      loc_180010C26
0x180010aef  mov     ebx, esi
0x180010af1  cmp     [rbp+arg_0], ebx
0x180010af4  jl      loc_180010BC8
0x180010afa  mov     qword ptr [rdi], 0
0x180010b01  or      esi, 1
0x180010b04  mov     [rbp+arg_18], esi
0x180010b07  mov     rcx, [rbp+var_8]
0x180010b0b  mov     rax, [rcx]
0x180010b0e  mov     r8, rdi
0x180010b11  mov     edx, ebx
0x180010b13  mov     rax, [rax+40h]
0x180010b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b1c  mov     rcx, [rbp+28h]; this
0x180010b20  test    eax, eax
0x180010b22  js      loc_180010BFC
0x180010b28  mov     [rbp+lpString1], 0
0x180010b30  mov     rcx, [rdi]
0x180010b33  mov     rax, [rcx]
0x180010b36  mov     [rbp+lpString1], 0
0x180010b3e  lea     rdx, [rbp+lpString1]
0x180010b42  mov     rax, [rax+40h]
0x180010b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b4b  mov     rcx, [rbp+28h]; this
0x180010b4f  test    eax, eax
0x180010b51  js      short loc_180010BB3
0x180010b53  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x180010b5b  or      r9d, 0FFFFFFFFh; cchCount2
0x180010b5f  mov     r8, r14; lpString2
0x180010b62  or      edx, r9d; cchCount1
0x180010b65  mov     rcx, [rbp+lpString1]; lpString1
0x180010b69  call    cs:__imp_CompareStringOrdinal
0x180010b6f  nop
0x180010b70  lea     rcx, [rbp+lpString1]
0x180010b74  cmp     eax, 2
0x180010b77  jz      short loc_180010B96
0x180010b79  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010b7e  nop
0x180010b7f  and     esi, 0FFFFFFFEh
0x180010b82  mov     rcx, rdi
0x180010b85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010b8a  inc     ebx
0x180010b8c  cmp     ebx, [rbp+arg_0]
0x180010b8f  jg      short loc_180010BC8
0x180010b91  jmp     loc_180010AFA
0x180010b96  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180010b9b  nop
0x180010b9c  lea     rcx, [rbp+var_8]
0x180010ba0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010ba5  mov     rax, rdi
0x180010ba8  add     rsp, 40h
0x180010bac  pop     r14
0x180010bae  pop     rdi
0x180010baf  pop     rsi
0x180010bb0  pop     rbx
0x180010bb1  pop     rbp
0x180010bb2  retn
0x180010bb3  mov     r9d, eax; char *
0x180010bb6  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x180010bbd  mov     edx, 11Ah; void *
0x180010bc2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010bc8  mov     ecx, 80070490h
0x180010bcd  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180010bd2  mov     r9d, eax; char *
0x180010bd5  mov     rcx, [rbp+28h]; this
0x180010bd9  mov     [rsp+40h+var_18], r14; char *
0x180010bde  lea     rax, aCannotFindTrig; "Cannot Find Trigger : %ws"
0x180010be5  mov     qword ptr [rsp+40h+bIgnoreCase], rax; int
0x180010bea  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x180010bf1  mov     edx, 120h; void *
0x180010bf6  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180010bfc  mov     r9d, eax; char *
0x180010bff  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x180010c06  mov     edx, 118h; void *
0x180010c0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010c11  mov     r9d, eax; char *
0x180010c14  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x180010c1b  mov     edx, 111h; void *
0x180010c20  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180010c26  mov     r9d, eax; char *
0x180010c29  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x180010c30  mov     edx, 114h; void *
0x180010c35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

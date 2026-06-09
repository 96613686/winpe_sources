# ScheduledTask::AddDailyTrigger(std::chrono::duration<__int64,std::ratio<1,10000000>>,short)

- ea: `0x18001c23c`
- end: `0x18001c434`
- name: `?AddDailyTrigger@ScheduledTask@@QEAAXV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@F@Z`
- size: `504`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d4e0`

## callees

- `0x180003450`
- `0x18000760c`
- `0x18000d370`
- `0x18000d63c`
- `0x180010150`
- `0x180011284`
- `0x180019c78`
- `0x18001c23c`
- `0x18001cbe0`
- `0x180046010`

## string_xrefs

- `0x18001c2aa`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18001c2f7`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18001c329`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18001c35e`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18001c3ae`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18001c3ea`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ScheduledTask::AddDailyTrigger(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD); // rbx
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD); // rbx
  wchar_t *v13; // rax
  _QWORD *bstr; // rax
  int v15; // eax
  int v16; // eax
  __int64 v18; // [rsp+20h] [rbp-39h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64); // [rsp+28h] [rbp-31h] BYREF
  __int64 v20; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-21h] BYREF
  __int64 v22; // [rsp+40h] [rbp-19h] BYREF
  wchar_t Buffer[28]; // [rsp+48h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v22 = a2 + *(_QWORD *)GetTimeAtMidnightToday();
  v20 = 0;
  v3 = *(_QWORD *)(a1 + 40);
  v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  v5 = v4(v3, &v20);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v5,
      v18);
  v19 = 0;
  v6 = v20;
  v7 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v20 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v8 = v7(v6, 2, &v19);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v8,
      v18);
  v18 = 0;
  v9 = Microsoft::WRL::ComPtr<ITrigger>::As<IDailyTrigger>(&v19, (__int64)&v18);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v9,
      v18);
  v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 168LL))(v18, 1);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v10,
      v18);
  v11 = v18;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v18 + 120LL);
  v13 = time_point_iso8601::time_point_iso8601(Buffer, (__int64)&v22);
  bstr = (_QWORD *)wil::make_bstr(v21, v13);
  v15 = v12(v11, *bstr);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v15,
      v18);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v21);
  v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 152LL))(v18, 0xFFFFFFFFLL);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      (const char *)(unsigned int)v16,
      v18);
  *(_BYTE *)a1 = 1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
}

```

## disassembly

```asm
0x18001c23c  push    rbp
0x18001c23e  push    rbx
0x18001c23f  push    rsi
0x18001c240  push    rdi
0x18001c241  lea     rbp, [rsp-3Fh]
0x18001c246  sub     rsp, 98h
0x18001c24d  mov     rax, cs:__security_cookie
0x18001c254  xor     rax, rsp
0x18001c257  mov     [rbp+57h+var_30], rax
0x18001c25b  mov     rbx, rdx
0x18001c25e  mov     rsi, rcx
0x18001c261  lea     rcx, [rbp+57h+var_78]
0x18001c265  call    ?GetTimeAtMidnightToday@@YA@XZ; GetTimeAtMidnightToday(void)
0x18001c26a  mov     rax, [rax]
0x18001c26d  add     rax, rbx
0x18001c270  mov     [rbp+57h+var_70], rax
0x18001c274  mov     [rbp+57h+var_80], 0
0x18001c27c  mov     rdi, [rsi+28h]
0x18001c280  mov     rax, [rdi]
0x18001c283  mov     rbx, [rax+48h]
0x18001c287  lea     rcx, [rbp+57h+var_80]
0x18001c28b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c290  lea     rdx, [rbp+57h+var_80]
0x18001c294  mov     rcx, rdi
0x18001c297  mov     rax, rbx
0x18001c29a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c29f  mov     rcx, [rbp+5Fh]; this
0x18001c2a3  test    eax, eax
0x18001c2a5  jns     short loc_18001C2BC
0x18001c2a7  mov     r9d, eax; char *
0x18001c2aa  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c2b1  mov     edx, 46h ; 'F'; void *
0x18001c2b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c2bc  mov     [rbp+57h+var_88], 0
0x18001c2c4  mov     rdi, [rbp+57h+var_80]
0x18001c2c8  mov     rax, [rdi]
0x18001c2cb  mov     rbx, [rax+50h]
0x18001c2cf  lea     rcx, [rbp+57h+var_88]
0x18001c2d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c2d8  lea     r8, [rbp+57h+var_88]
0x18001c2dc  mov     edx, 2
0x18001c2e1  mov     rcx, rdi
0x18001c2e4  mov     rax, rbx
0x18001c2e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2ec  mov     rcx, [rbp+5Fh]; this
0x18001c2f0  test    eax, eax
0x18001c2f2  jns     short loc_18001C309
0x18001c2f4  mov     r9d, eax; char *
0x18001c2f7  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c2fe  mov     edx, 48h ; 'H'; void *
0x18001c303  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c309  mov     [rbp+57h+var_90], 0
0x18001c311  lea     rdx, [rbp+57h+var_90]
0x18001c315  lea     rcx, [rbp+57h+var_88]
0x18001c319  call    ??$As@UIDailyTrigger@@@?$ComPtr@UITrigger@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDailyTrigger@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ITrigger>::As<IDailyTrigger>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDailyTrigger>>)
0x18001c31e  mov     rcx, [rbp+5Fh]; this
0x18001c322  test    eax, eax
0x18001c324  jns     short loc_18001C33B
0x18001c326  mov     r9d, eax; char *
0x18001c329  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c330  mov     edx, 4Ah ; 'J'; void *
0x18001c335  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c33b  mov     rcx, [rbp+57h+var_90]
0x18001c33f  mov     rax, [rcx]
0x18001c342  mov     edx, 1
0x18001c347  mov     rax, [rax+0A8h]
0x18001c34e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c353  mov     rcx, [rbp+5Fh]; this
0x18001c357  test    eax, eax
0x18001c359  jns     short loc_18001C370
0x18001c35b  mov     r9d, eax; char *
0x18001c35e  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c365  mov     edx, 4Bh ; 'K'; void *
0x18001c36a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c370  mov     rdi, [rbp+57h+var_90]
0x18001c374  mov     rax, [rdi]
0x18001c377  mov     rbx, [rax+78h]
0x18001c37b  lea     rdx, [rbp+57h+var_70]
0x18001c37f  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18001c383  call    ??0time_point_iso8601@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; time_point_iso8601::time_point_iso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x18001c388  mov     rdx, rax
0x18001c38b  lea     rcx, [rbp+57h+var_78]
0x18001c38f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18001c394  nop
0x18001c395  mov     rdx, [rax]
0x18001c398  mov     rcx, rdi
0x18001c39b  mov     rax, rbx
0x18001c39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3a3  mov     rcx, [rbp+5Fh]; this
0x18001c3a7  test    eax, eax
0x18001c3a9  jns     short loc_18001C3C0
0x18001c3ab  mov     r9d, eax; char *
0x18001c3ae  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c3b5  mov     edx, 4Ch ; 'L'; void *
0x18001c3ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c3c0  lea     rcx, [rbp+57h+var_78]
0x18001c3c4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001c3c9  mov     rcx, [rbp+57h+var_90]
0x18001c3cd  mov     rax, [rcx]
0x18001c3d0  or      edx, 0FFFFFFFFh
0x18001c3d3  mov     rax, [rax+98h]
0x18001c3da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3df  mov     rcx, [rbp+5Fh]; this
0x18001c3e3  test    eax, eax
0x18001c3e5  jns     short loc_18001C3FC
0x18001c3e7  mov     r9d, eax; char *
0x18001c3ea  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18001c3f1  mov     edx, 4Dh ; 'M'; void *
0x18001c3f6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001c3fc  mov     byte ptr [rsi], 1
0x18001c3ff  lea     rcx, [rbp+57h+var_90]
0x18001c403  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c408  nop
0x18001c409  lea     rcx, [rbp+57h+var_88]
0x18001c40d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c412  nop
0x18001c413  lea     rcx, [rbp+57h+var_80]
0x18001c417  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c41c  mov     rcx, [rbp+57h+var_30]
0x18001c420  xor     rcx, rsp; StackCookie
0x18001c423  call    __security_check_cookie
0x18001c428  add     rsp, 98h
0x18001c42f  pop     rdi
0x18001c430  pop     rsi
0x18001c431  pop     rbx
0x18001c432  pop     rbp
0x18001c433  retn
```

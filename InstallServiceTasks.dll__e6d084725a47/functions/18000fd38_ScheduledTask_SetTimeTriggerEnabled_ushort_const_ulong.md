# ScheduledTask::SetTimeTriggerEnabled(ushort const *,ulong)

- ea: `0x18000fd38`
- end: `0x18000fe8e`
- name: `?SetTimeTriggerEnabled@ScheduledTask@@QEAAXPEBGK@Z`
- size: `342`
- prototype: `void __fastcall(ScheduledTask *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010d74`

## callees

- `0x180003450`
- `0x18000760c`
- `0x18000b464`
- `0x18000d370`
- `0x18000d63c`
- `0x18000fd38`
- `0x18000fe94`
- `0x180010150`
- `0x180010a80`
- `0x180011284`
- `0x180046010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18000fdd5`
- `msvcp_win!_Xtime_get_ticks` at `0x18000fdd5`

## string_xrefs

- `0x18000fd9b`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000fe40`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ScheduledTask::SetTimeTriggerEnabled(ScheduledTask *this, const unsigned __int16 *a2)
{
  int v3; // eax
  const char *v4; // r9
  __int64 ticks; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rdi
  __int64 (__fastcall *v9)(__int64 *, _QWORD); // rsi
  wchar_t *v10; // rax
  _QWORD *bstr; // rax
  int v12; // eax
  int v13; // [rsp+20h] [rbp-68h] BYREF
  __int64 *v14; // [rsp+28h] [rbp-60h] BYREF
  int v15; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+38h] [rbp-50h] BYREF
  wchar_t Buffer[28]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    ScheduledTask::_GetTrigger((__int64)this, &v14, (const char *)L"NetworkDebounce");
    v13 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v14 + 56))(v14, &v13);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
        (const char *)(unsigned int)v3,
        v13);
    if ( v13 == 1 )
    {
      ScheduledTask::SetTriggerEnabled(this, L"NetworkDebounce", 1);
      ticks = _Xtime_get_ticks();
      v15 = 5;
      std::chrono::duration<__int64,std::ratio<1,10000000>>::duration<__int64,std::ratio<1,10000000>>(
        &v16,
        &v15,
        v6,
        ticks);
      v16 += v7;
      v8 = v14;
      v9 = *(__int64 (__fastcall **)(__int64 *, _QWORD))(*v14 + 120);
      v10 = time_point_iso8601::time_point_iso8601(Buffer, (__int64)&v16);
      bstr = (_QWORD *)wil::make_bstr(&v15, v10);
      v12 = v9(v8, *bstr);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
          (const char *)(unsigned int)v12,
          v13);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v15);
      *(_BYTE *)this = 1;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      v4);
  }
}

```

## disassembly

```asm
0x18000fd38  mov     [rsp+arg_8], rbx
0x18000fd3d  mov     [rsp+arg_10], rsi
0x18000fd42  push    rdi
0x18000fd43  sub     rsp, 80h
0x18000fd4a  mov     rax, cs:__security_cookie
0x18000fd51  xor     rax, rsp
0x18000fd54  mov     [rsp+88h+var_10], rax
0x18000fd59  mov     rbx, rcx
0x18000fd5c  lea     r8, aNetworkdebounc_0; "NetworkDebounce"
0x18000fd63  lea     rdx, [rsp+88h+var_60]
0x18000fd68  call    ?_GetTrigger@ScheduledTask@@AEAA?AV?$ComPtr@UITrigger@@@WRL@Microsoft@@PEAG@Z; ScheduledTask::_GetTrigger(ushort *)
0x18000fd6d  nop
0x18000fd6e  mov     [rsp+88h+var_68], 0; int
0x18000fd76  mov     rcx, [rsp+88h+var_60]
0x18000fd7b  mov     rax, [rcx]
0x18000fd7e  lea     rdx, [rsp+88h+var_68]
0x18000fd83  mov     rax, [rax+38h]
0x18000fd87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8c  mov     rcx, [rsp+88h]; this
0x18000fd94  test    eax, eax
0x18000fd96  jns     short loc_18000FDAC
0x18000fd98  mov     r9d, eax; char *
0x18000fd9b  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000fda2  mov     edx, 56h ; 'V'; void *
0x18000fda7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000fdac  cmp     [rsp+88h+var_68], 1
0x18000fdb1  jz      short loc_18000FDC3
0x18000fdb3  lea     rcx, [rsp+88h+var_60]
0x18000fdb8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fdbd  nop
0x18000fdbe  jmp     loc_18000FE6C
0x18000fdc3  mov     r8b, 1; bool
0x18000fdc6  lea     rdx, aNetworkdebounc_0; "NetworkDebounce"
0x18000fdcd  mov     rcx, rbx; this
0x18000fdd0  call    ?SetTriggerEnabled@ScheduledTask@@QEAAXPEBG_N@Z; ScheduledTask::SetTriggerEnabled(ushort const *,bool)
0x18000fdd5  call    cs:__imp__Xtime_get_ticks
0x18000fddb  mov     r9, rax
0x18000fdde  mov     [rsp+88h+var_58], 5
0x18000fde6  lea     rdx, [rsp+88h+var_58]
0x18000fdeb  lea     rcx, [rsp+88h+var_50]
0x18000fdf0  call    ??$?0HU?$ratio@$0DM@$00@std@@$0A@@?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@QEAA@AEBV?$duration@HU?$ratio@$0DM@$00@std@@@12@@Z; std::chrono::duration<__int64,std::ratio<1,10000000>>::duration<__int64,std::ratio<1,10000000>>(std::chrono::duration<int,std::ratio<60,1>> const &)
0x18000fdf5  add     [rsp+88h+var_50], r9
0x18000fdfa  mov     rdi, [rsp+88h+var_60]
0x18000fdff  mov     rax, [rdi]
0x18000fe02  mov     rsi, [rax+78h]
0x18000fe06  lea     rdx, [rsp+88h+var_50]
0x18000fe0b  lea     rcx, [rsp+88h+Buffer]; Buffer
0x18000fe10  call    ??0time_point_iso8601@@QEAA@AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; time_point_iso8601::time_point_iso8601(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x18000fe15  mov     rdx, rax
0x18000fe18  lea     rcx, [rsp+88h+var_58]
0x18000fe1d  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18000fe22  nop
0x18000fe23  mov     rdx, [rax]
0x18000fe26  mov     rcx, rdi
0x18000fe29  mov     rax, rsi
0x18000fe2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe31  mov     rcx, [rsp+88h]; this
0x18000fe39  test    eax, eax
0x18000fe3b  jns     short loc_18000FE52
0x18000fe3d  mov     r9d, eax; char *
0x18000fe40  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000fe47  mov     edx, 63h ; 'c'; void *
0x18000fe4c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000fe52  lea     rcx, [rsp+88h+var_58]
0x18000fe57  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000fe5c  mov     byte ptr [rbx], 1
0x18000fe5f  lea     rcx, [rsp+88h+var_60]
0x18000fe64  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000fe69  nop
0x18000fe6a  jmp     short $+2
0x18000fe6c  mov     rcx, [rsp+88h+var_10]
0x18000fe71  xor     rcx, rsp; StackCookie
0x18000fe74  call    __security_check_cookie
0x18000fe79  lea     r11, [rsp+88h+var_8]
0x18000fe81  mov     rbx, [r11+18h]
0x18000fe85  mov     rsi, [r11+20h]
0x18000fe89  mov     rsp, r11
0x18000fe8c  pop     rdi
0x18000fe8d  retn
```

# ScheduledTask::GetTimeTriggerState(ushort const *)

- ea: `0x18000f39c`
- end: `0x18000f4f2`
- name: `?GetTimeTriggerState@ScheduledTask@@QEAA?AW4TimeTriggerState@@PEBG@Z`
- size: `342`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18000f0e0`
- `0x180010230`
- `0x180010d74`

## callees

- `0x18000760c`
- `0x18000f39c`
- `0x180010150`
- `0x180010a80`
- `0x180011544`
- `0x180046010`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18000f488`
- `msvcp_win!_Xtime_get_ticks` at `0x18000f488`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f49b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f49b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4b3`

## string_xrefs

- `0x18000f3d8`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000f420`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`
- `0x18000f468`: `onecoreuap\enduser\winstore\installservice\lib\TaskHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ScheduledTask::GetTimeTriggerState(__int64 a1, const char *a2)
{
  int v2; // eax
  int v3; // eax
  int v4; // eax
  const char *v5; // r9
  __int64 result; // rax
  __int64 *v7; // [rsp+20h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-20h] BYREF
  __int64 v9[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int16 v11; // [rsp+60h] [rbp+18h] BYREF
  int v12; // [rsp+68h] [rbp+20h] BYREF

  try
  {
    ScheduledTask::_GetTrigger(a1, &v7, a2);
    v12 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v7 + 56))(v7, &v12);
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
        (const char *)(unsigned int)v2,
        (int)v7);
    if ( v12 != 1 )
      goto LABEL_14;
    v11 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v7 + 144))(v7, &v11);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
        (const char *)(unsigned int)v3,
        (int)v7);
    if ( v11 == -1 )
    {
      try
      {
        bstrString = 0;
        v4 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v7 + 112))(v7, &bstrString);
        if ( v4 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x74,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
            (const char *)(unsigned int)v4,
            (int)v7);
        time_point_iso8601::parse(v9, bstrString);
        if ( v9[0] >= _Xtime_get_ticks() )
        {
          SysFreeString(bstrString);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
          result = 1;
        }
        else
        {
          SysFreeString(bstrString);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
          result = 2;
        }
      }
      catch ( ... )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
        result = 1;
      }
    }
    else
    {
LABEL_14:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
      result = 0;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\TaskHelpers.h",
      v5);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f39c  sub     rsp, 48h
0x18000f3a0  mov     r8, rdx
0x18000f3a3  lea     rdx, [rsp+48h+var_28]
0x18000f3a8  call    ?_GetTrigger@ScheduledTask@@AEAA?AV?$ComPtr@UITrigger@@@WRL@Microsoft@@PEAG@Z; ScheduledTask::_GetTrigger(ushort *)
0x18000f3ad  nop
0x18000f3ae  mov     [rsp+48h+arg_18], 0
0x18000f3b6  mov     rcx, [rsp+48h+var_28]
0x18000f3bb  mov     rax, [rcx]
0x18000f3be  lea     rdx, [rsp+48h+arg_18]
0x18000f3c3  mov     rax, [rax+38h]
0x18000f3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3cc  mov     rcx, [rsp+48h]; this
0x18000f3d1  test    eax, eax
0x18000f3d3  jns     short loc_18000F3E9
0x18000f3d5  mov     r9d, eax; char *
0x18000f3d8  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000f3df  mov     edx, 6Ch ; 'l'; void *
0x18000f3e4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f3e9  cmp     [rsp+48h+arg_18], 1
0x18000f3ee  jnz     loc_18000F4DC
0x18000f3f4  xor     eax, eax
0x18000f3f6  mov     [rsp+48h+arg_10], ax
0x18000f3fb  mov     rcx, [rsp+48h+var_28]
0x18000f400  mov     rax, [rcx]
0x18000f403  lea     rdx, [rsp+48h+arg_10]
0x18000f408  mov     rax, [rax+90h]
0x18000f40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f414  mov     rcx, [rsp+48h]; this
0x18000f419  test    eax, eax
0x18000f41b  jns     short loc_18000F431
0x18000f41d  mov     r9d, eax; char *
0x18000f420  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000f427  mov     edx, 70h ; 'p'; void *
0x18000f42c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f431  cmp     [rsp+48h+arg_10], 0FFFFh
0x18000f437  jnz     loc_18000F4DC
0x18000f43d  mov     [rsp+48h+bstrString], 0
0x18000f446  mov     rcx, [rsp+48h+var_28]
0x18000f44b  mov     rax, [rcx]
0x18000f44e  lea     rdx, [rsp+48h+bstrString]
0x18000f453  mov     rax, [rax+70h]
0x18000f457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f45c  mov     rcx, [rsp+48h]; this
0x18000f461  test    eax, eax
0x18000f463  jns     short loc_18000F479
0x18000f465  mov     r9d, eax; char *
0x18000f468  lea     r8, aOnecoreuapEndu_8; "onecoreuap\\enduser\\winstore\\installs"...
0x18000f46f  mov     edx, 74h ; 't'; void *
0x18000f474  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f479  mov     rdx, [rsp+48h+bstrString]
0x18000f47e  lea     rcx, [rsp+48h+var_18]
0x18000f483  call    ?parse@time_point_iso8601@@SA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@PEBG@Z; time_point_iso8601::parse(ushort const *)
0x18000f488  call    cs:__imp__Xtime_get_ticks
0x18000f48e  nop
0x18000f48f  mov     rcx, [rsp+48h+bstrString]; bstrString
0x18000f494  cmp     [rsp+48h+var_18], rax
0x18000f499  jge     short loc_18000F4B3
0x18000f49b  call    cs:__imp_SysFreeString
0x18000f4a1  nop
0x18000f4a2  lea     rcx, [rsp+48h+var_28]
0x18000f4a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f4ac  mov     eax, 2
0x18000f4b1  jmp     short loc_18000F4EC
0x18000f4b3  call    cs:__imp_SysFreeString
0x18000f4b9  nop
0x18000f4ba  lea     rcx, [rsp+48h+var_28]
0x18000f4bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f4c4  mov     eax, 1
0x18000f4c9  jmp     short loc_18000F4EC
0x18000f4cb  lea     rcx, [rsp+48h+var_28]
0x18000f4d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f4d5  mov     eax, 1
0x18000f4da  jmp     short loc_18000F4EC
0x18000f4dc  lea     rcx, [rsp+48h+var_28]
0x18000f4e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f4e6  xor     eax, eax
0x18000f4e8  jmp     short loc_18000F4EC
0x18000f4ea  xor     eax, eax
0x18000f4ec  add     rsp, 48h
0x18000f4f0  retn
```

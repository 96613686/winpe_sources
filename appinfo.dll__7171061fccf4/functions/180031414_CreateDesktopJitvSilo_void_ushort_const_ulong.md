# CreateDesktopJitvSilo(void *,ushort const *,ulong *)

- ea: `0x180031414`
- end: `0x180031506`
- name: `?CreateDesktopJitvSilo@@YAJPEAXPEBGPEAK@Z`
- size: `242`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003cbe0`

## callees

- `0x18000720c`
- `0x180009d50`
- `0x18000bd90`
- `0x18000c410`
- `0x180018dbc`
- `0x18002afa0`
- `0x18002b044`
- `0x180031414`

## import_xrefs

- `ext-ms-win-desktopappx-l1-2-0!CreateJitvSilo` at `0x1800314c1`
- `ext-ms-win-desktopappx-l1-2-0!CreateJitvSilo` at `0x1800314c1`

## string_xrefs

- `0x180031493`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800314d1`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall CreateDesktopJitvSilo(void *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int ClientInformation; // ebx
  unsigned int v6; // ebx
  __int64 v7; // r8
  int JitvSilo; // eax
  unsigned int v10; // [rsp+20h] [rbp-58h]
  __int64 v11; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v12; // [rsp+38h] [rbp-40h] BYREF
  void *v13; // [rsp+40h] [rbp-38h] BYREF
  char v14; // [rsp+48h] [rbp-30h]
  __int64 *v15; // [rsp+50h] [rbp-28h] BYREF
  void *v16; // [rsp+58h] [rbp-20h] BYREF
  char v17; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]
  __int64 v19; // [rsp+B8h] [rbp+40h] BYREF

  v19 = 0;
  v15 = &v11;
  v11 = 0;
  v12 = &v19;
  v16 = 0;
  v17 = 1;
  v13 = 0;
  v14 = 1;
  ClientInformation = AiGetClientInformation(a1, &v13, &v16, 0, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v12);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v15);
  if ( ClientInformation )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1DB2,
           (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
           (const char *)ClientInformation,
           v10);
  }
  else
  {
    v7 = v19;
    v19 = 0;
    JitvSilo = CreateJitvSilo(v11, a2, v7, a3);
    v6 = JitvSilo;
    if ( JitvSilo >= 0 )
      v6 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DB4,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
        (const char *)(unsigned int)JitvSilo,
        v10);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
  wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
  return v6;
}

```

## disassembly

```asm
0x180031414  push    rbp
0x180031416  push    rbx
0x180031417  push    rsi
0x180031418  push    rdi
0x180031419  mov     rbp, rsp
0x18003141c  sub     rsp, 78h
0x180031420  lea     rax, [rbp+var_48]
0x180031424  mov     [rbp+arg_18], 0
0x18003142c  mov     [rbp+var_28], rax
0x180031430  mov     rdi, r8
0x180031433  lea     rax, [rbp+arg_18]
0x180031437  mov     [rbp+var_48], 0
0x18003143f  mov     rsi, rdx
0x180031442  mov     [rbp+var_40], rax
0x180031446  xor     r9d, r9d; unsigned int *
0x180031449  mov     [rbp+var_20], 0
0x180031451  lea     r8, [rbp+var_20]; void **
0x180031455  mov     [rbp+var_18], 1
0x180031459  lea     rdx, [rbp+var_38]; void **
0x18003145d  mov     [rbp+var_38], 0
0x180031465  mov     [rbp+var_30], 1
0x180031469  mov     qword ptr [rsp+78h+var_58], 0; int
0x180031472  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180031477  lea     rcx, [rbp+var_40]
0x18003147b  mov     ebx, eax
0x18003147d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180031482  lea     rcx, [rbp+var_28]
0x180031486  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18003148b  test    ebx, ebx
0x18003148d  jz      short loc_1800314AB
0x18003148f  mov     rcx, [rbp+20h]; this
0x180031493  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18003149a  mov     r9d, ebx; char *
0x18003149d  mov     edx, 1DB2h; void *
0x1800314a2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800314a7  mov     ebx, eax
0x1800314a9  jmp     short loc_1800314E9
0x1800314ab  mov     r8, [rbp+arg_18]
0x1800314af  mov     r9, rdi
0x1800314b2  mov     rcx, [rbp+var_48]
0x1800314b6  mov     rdx, rsi
0x1800314b9  mov     [rbp+arg_18], 0
0x1800314c1  call    cs:__imp_CreateJitvSilo
0x1800314c7  mov     ebx, eax
0x1800314c9  test    eax, eax
0x1800314cb  jns     short loc_1800314E7
0x1800314cd  mov     rcx, [rbp+20h]; this
0x1800314d1  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x1800314d8  mov     r9d, eax; char *
0x1800314db  mov     edx, 1DB4h; void *
0x1800314e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800314e5  jmp     short loc_1800314E9
0x1800314e7  xor     ebx, ebx
0x1800314e9  lea     rcx, [rbp+var_48]
0x1800314ed  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800314f2  lea     rcx, [rbp+arg_18]
0x1800314f6  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800314fb  mov     eax, ebx
0x1800314fd  add     rsp, 78h
0x180031501  pop     rdi
0x180031502  pop     rsi
0x180031503  pop     rbx
0x180031504  pop     rbp
0x180031505  retn
```

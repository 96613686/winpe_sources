# CreateDesktopJitvSilo(void *,ushort const *,ulong *)

- ea: `0x18002e278`
- end: `0x18002e376`
- name: `?CreateDesktopJitvSilo@@YAJPEAXPEBGPEAK@Z`
- size: `254`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180039890`

## callees

- `0x180007c78`
- `0x18000a230`
- `0x18000c4c0`
- `0x18000f8b0`
- `0x180018280`
- `0x180028730`
- `0x1800287d8`
- `0x18002e278`

## import_xrefs

- `ext-ms-win-desktopappx-l1-2-0!CreateJitvSilo` at `0x18002e31d`
- `ext-ms-win-desktopappx-l1-2-0!CreateJitvSilo` at `0x18002e31d`

## string_xrefs

- `0x18002e2f2`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002e333`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall CreateDesktopJitvSilo(void *a1, const unsigned __int16 *a2, unsigned int *a3)
{
  unsigned int ClientInformation; // ebx
  unsigned int v6; // ebx
  __int64 v7; // r8
  int JitvSilo; // eax
  unsigned int v10; // [rsp+20h] [rbp-50h]
  __int64 v11; // [rsp+30h] [rbp-40h] BYREF
  __int64 *v12; // [rsp+38h] [rbp-38h] BYREF
  void *v13; // [rsp+40h] [rbp-30h] BYREF
  char v14; // [rsp+48h] [rbp-28h]
  __int64 *v15; // [rsp+50h] [rbp-20h] BYREF
  void *v16; // [rsp+58h] [rbp-18h] BYREF
  char v17; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  __int64 v19; // [rsp+98h] [rbp+28h] BYREF

  v19 = 0;
  v11 = 0;
  v16 = 0;
  v13 = 0;
  v15 = &v11;
  v17 = 1;
  v12 = &v19;
  v14 = 1;
  ClientInformation = AiGetClientInformation(a1, &v13, &v16, 0, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v12);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v15);
  if ( ClientInformation )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1A67,
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
        (void *)0x1A69,
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
0x18002e278  mov     r11, rsp
0x18002e27b  mov     [r11+8], rbx
0x18002e27f  mov     [r11+10h], rsi
0x18002e283  mov     [r11+18h], rdi
0x18002e287  push    rbp
0x18002e288  mov     rbp, rsp
0x18002e28b  sub     rsp, 70h
0x18002e28f  and     [rbp+arg_18], 0
0x18002e294  lea     rax, [rbp+var_40]
0x18002e298  and     [rbp+var_40], 0
0x18002e29d  mov     rdi, r8
0x18002e2a0  and     [rbp+var_18], 0
0x18002e2a5  lea     r8, [rbp+var_18]; void **
0x18002e2a9  and     [rbp+var_30], 0
0x18002e2ae  mov     rsi, rdx
0x18002e2b1  and     qword ptr [r11-58h], 0
0x18002e2b6  lea     rdx, [rbp+var_30]; void **
0x18002e2ba  mov     [rbp+var_20], rax
0x18002e2be  xor     r9d, r9d; unsigned int *
0x18002e2c1  lea     rax, [rbp+arg_18]
0x18002e2c5  mov     [rbp+var_10], 1
0x18002e2c9  mov     [rbp+var_38], rax
0x18002e2cd  mov     [rbp+var_28], 1
0x18002e2d1  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18002e2d6  lea     rcx, [rbp+var_38]
0x18002e2da  mov     ebx, eax
0x18002e2dc  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002e2e1  lea     rcx, [rbp+var_20]
0x18002e2e5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002e2ea  test    ebx, ebx
0x18002e2ec  jz      short loc_18002E30A
0x18002e2ee  mov     rcx, [rbp+8]; this
0x18002e2f2  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002e2f9  mov     r9d, ebx; char *
0x18002e2fc  mov     edx, 1A67h; void *
0x18002e301  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002e306  mov     ebx, eax
0x18002e308  jmp     short loc_18002E34B
0x18002e30a  mov     r8, [rbp+arg_18]
0x18002e30e  mov     r9, rdi
0x18002e311  mov     rcx, [rbp+var_40]
0x18002e315  mov     rdx, rsi
0x18002e318  and     [rbp+arg_18], 0
0x18002e31d  call    cs:__imp_CreateJitvSilo
0x18002e324  nop     dword ptr [rax+rax+00h]
0x18002e329  mov     ebx, eax
0x18002e32b  test    eax, eax
0x18002e32d  jns     short loc_18002E349
0x18002e32f  mov     rcx, [rbp+8]; this
0x18002e333  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18002e33a  mov     r9d, eax; char *
0x18002e33d  mov     edx, 1A69h; void *
0x18002e342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e347  jmp     short loc_18002E34B
0x18002e349  xor     ebx, ebx
0x18002e34b  lea     rcx, [rbp+var_40]
0x18002e34f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002e354  lea     rcx, [rbp+arg_18]
0x18002e358  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002e35d  lea     r11, [rsp+70h+var_s0]
0x18002e362  mov     eax, ebx
0x18002e364  mov     rbx, [r11+10h]
0x18002e368  mov     rsi, [r11+18h]
0x18002e36c  mov     rdi, [r11+20h]
0x18002e370  mov     rsp, r11
0x18002e373  pop     rbp
0x18002e374  retn
```

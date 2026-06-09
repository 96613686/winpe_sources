# CreateDesktopJitvSilo(void *,ushort const *,ulong *)

- ea: `0x18002cd28`
- end: `0x18002ce26`
- name: `?CreateDesktopJitvSilo@@YAJPEAXPEBGPEAK@Z`
- size: `254`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003a810`

## callees

- `0x180007c78`
- `0x18000a230`
- `0x18000c4c0`
- `0x18000f9e0`
- `0x180018530`
- `0x1800271c0`
- `0x180027268`
- `0x18002cd28`

## import_xrefs

- `ext-ms-win-desktopappx-l1-2-0!CreateJitvSilo` at `0x18002cdcd`
- `ext-ms-win-desktopappx-l1-2-0!CreateJitvSilo` at `0x18002cdcd`

## string_xrefs

- `0x18002cda2`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002cde3`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
           (void *)0x1B6B,
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
        (void *)0x1B6D,
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
0x18002cd28  mov     r11, rsp
0x18002cd2b  mov     [r11+8], rbx
0x18002cd2f  mov     [r11+10h], rsi
0x18002cd33  mov     [r11+18h], rdi
0x18002cd37  push    rbp
0x18002cd38  mov     rbp, rsp
0x18002cd3b  sub     rsp, 70h
0x18002cd3f  and     [rbp+arg_18], 0
0x18002cd44  lea     rax, [rbp+var_40]
0x18002cd48  and     [rbp+var_40], 0
0x18002cd4d  mov     rdi, r8
0x18002cd50  and     [rbp+var_18], 0
0x18002cd55  lea     r8, [rbp+var_18]; void **
0x18002cd59  and     [rbp+var_30], 0
0x18002cd5e  mov     rsi, rdx
0x18002cd61  and     qword ptr [r11-58h], 0
0x18002cd66  lea     rdx, [rbp+var_30]; void **
0x18002cd6a  mov     [rbp+var_20], rax
0x18002cd6e  xor     r9d, r9d; unsigned int *
0x18002cd71  lea     rax, [rbp+arg_18]
0x18002cd75  mov     [rbp+var_10], 1
0x18002cd79  mov     [rbp+var_38], rax
0x18002cd7d  mov     [rbp+var_28], 1
0x18002cd81  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18002cd86  lea     rcx, [rbp+var_38]
0x18002cd8a  mov     ebx, eax
0x18002cd8c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002cd91  lea     rcx, [rbp+var_20]
0x18002cd95  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002cd9a  test    ebx, ebx
0x18002cd9c  jz      short loc_18002CDBA
0x18002cd9e  mov     rcx, [rbp+8]; this
0x18002cda2  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002cda9  mov     r9d, ebx; char *
0x18002cdac  mov     edx, 1B6Bh; void *
0x18002cdb1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002cdb6  mov     ebx, eax
0x18002cdb8  jmp     short loc_18002CDFB
0x18002cdba  mov     r8, [rbp+arg_18]
0x18002cdbe  mov     r9, rdi
0x18002cdc1  mov     rcx, [rbp+var_40]
0x18002cdc5  mov     rdx, rsi
0x18002cdc8  and     [rbp+arg_18], 0
0x18002cdcd  call    cs:__imp_CreateJitvSilo
0x18002cdd4  nop     dword ptr [rax+rax+00h]
0x18002cdd9  mov     ebx, eax
0x18002cddb  test    eax, eax
0x18002cddd  jns     short loc_18002CDF9
0x18002cddf  mov     rcx, [rbp+8]; this
0x18002cde3  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002cdea  mov     r9d, eax; char *
0x18002cded  mov     edx, 1B6Dh; void *
0x18002cdf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cdf7  jmp     short loc_18002CDFB
0x18002cdf9  xor     ebx, ebx
0x18002cdfb  lea     rcx, [rbp+var_40]
0x18002cdff  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002ce04  lea     rcx, [rbp+arg_18]
0x18002ce08  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002ce0d  lea     r11, [rsp+70h+var_s0]
0x18002ce12  mov     eax, ebx
0x18002ce14  mov     rbx, [r11+10h]
0x18002ce18  mov     rsi, [r11+18h]
0x18002ce1c  mov     rdi, [r11+20h]
0x18002ce20  mov     rsp, r11
0x18002ce23  pop     rbp
0x18002ce24  retn
```

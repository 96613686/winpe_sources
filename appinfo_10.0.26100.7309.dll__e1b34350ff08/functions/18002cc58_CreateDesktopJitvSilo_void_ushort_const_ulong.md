# CreateDesktopJitvSilo(void *,ushort const *,ulong *)

- ea: `0x18002cc58`
- end: `0x18002cd56`
- name: `?CreateDesktopJitvSilo@@YAJPEAXPEBGPEAK@Z`
- size: `254`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003a490`

## callees

- `0x180007c78`
- `0x18000a230`
- `0x18000c4c0`
- `0x18000f9e0`
- `0x180018530`
- `0x1800270f0`
- `0x180027198`
- `0x18002cc58`

## import_xrefs

- `ext-ms-win-desktopappx-l1-2-0!CreateJitvSilo` at `0x18002ccfd`
- `ext-ms-win-desktopappx-l1-2-0!CreateJitvSilo` at `0x18002ccfd`

## string_xrefs

- `0x18002ccd2`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18002cd13`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
           (void *)0x1B34,
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
        (void *)0x1B36,
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
0x18002cc58  mov     r11, rsp
0x18002cc5b  mov     [r11+8], rbx
0x18002cc5f  mov     [r11+10h], rsi
0x18002cc63  mov     [r11+18h], rdi
0x18002cc67  push    rbp
0x18002cc68  mov     rbp, rsp
0x18002cc6b  sub     rsp, 70h
0x18002cc6f  and     [rbp+arg_18], 0
0x18002cc74  lea     rax, [rbp+var_40]
0x18002cc78  and     [rbp+var_40], 0
0x18002cc7d  mov     rdi, r8
0x18002cc80  and     [rbp+var_18], 0
0x18002cc85  lea     r8, [rbp+var_18]; void **
0x18002cc89  and     [rbp+var_30], 0
0x18002cc8e  mov     rsi, rdx
0x18002cc91  and     qword ptr [r11-58h], 0
0x18002cc96  lea     rdx, [rbp+var_30]; void **
0x18002cc9a  mov     [rbp+var_20], rax
0x18002cc9e  xor     r9d, r9d; unsigned int *
0x18002cca1  lea     rax, [rbp+arg_18]
0x18002cca5  mov     [rbp+var_10], 1
0x18002cca9  mov     [rbp+var_38], rax
0x18002ccad  mov     [rbp+var_28], 1
0x18002ccb1  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18002ccb6  lea     rcx, [rbp+var_38]
0x18002ccba  mov     ebx, eax
0x18002ccbc  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002ccc1  lea     rcx, [rbp+var_20]
0x18002ccc5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18002ccca  test    ebx, ebx
0x18002cccc  jz      short loc_18002CCEA
0x18002ccce  mov     rcx, [rbp+8]; this
0x18002ccd2  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002ccd9  mov     r9d, ebx; char *
0x18002ccdc  mov     edx, 1B34h; void *
0x18002cce1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002cce6  mov     ebx, eax
0x18002cce8  jmp     short loc_18002CD2B
0x18002ccea  mov     r8, [rbp+arg_18]
0x18002ccee  mov     r9, rdi
0x18002ccf1  mov     rcx, [rbp+var_40]
0x18002ccf5  mov     rdx, rsi
0x18002ccf8  and     [rbp+arg_18], 0
0x18002ccfd  call    cs:__imp_CreateJitvSilo
0x18002cd04  nop     dword ptr [rax+rax+00h]
0x18002cd09  mov     ebx, eax
0x18002cd0b  test    eax, eax
0x18002cd0d  jns     short loc_18002CD29
0x18002cd0f  mov     rcx, [rbp+8]; this
0x18002cd13  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x18002cd1a  mov     r9d, eax; char *
0x18002cd1d  mov     edx, 1B36h; void *
0x18002cd22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cd27  jmp     short loc_18002CD2B
0x18002cd29  xor     ebx, ebx
0x18002cd2b  lea     rcx, [rbp+var_40]
0x18002cd2f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002cd34  lea     rcx, [rbp+arg_18]
0x18002cd38  call    ??1?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002cd3d  lea     r11, [rsp+70h+var_s0]
0x18002cd42  mov     eax, ebx
0x18002cd44  mov     rbx, [r11+10h]
0x18002cd48  mov     rsi, [r11+18h]
0x18002cd4c  mov     rdi, [r11+20h]
0x18002cd50  mov     rsp, r11
0x18002cd53  pop     rbp
0x18002cd54  retn
```

# BackgroundTaskHandler::InitOdbBrokerClient(void)

- ea: `0x18004e7e8`
- end: `0x18004e8fe`
- name: `?InitOdbBrokerClient@BackgroundTaskHandler@@QEAAXXZ`
- size: `278`
- prototype: `void __fastcall(BackgroundTaskHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004ddc0`

## callees

- `0x180003ca0`
- `0x1800127a4`
- `0x1800147fc`
- `0x180031228`
- `0x18003787c`
- `0x18004e7e8`
- `0x18005e010`

## import_xrefs

- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x18004e82b`
- `OnDemandBrokerClient!CreateOnDemandBrokerClient` at `0x18004e82b`

## string_xrefs

- `0x18004e8d7`: `onecoreuap\printscan\print\workflow\broker\psa_lib\backgroundtaskhandler.cpp`
- `0x18004e8ec`: `onecoreuap\printscan\print\workflow\broker\psa_lib\backgroundtaskhandler.cpp`
- `0x18004e824`: `PsaBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall BackgroundTaskHandler::InitOdbBrokerClient(BackgroundTaskHandler *this)
{
  __int64 *v2; // rdi
  int v3; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, _QWORD, char *); // rbx
  _QWORD *v6; // rax
  int v7; // eax
  int v8; // [rsp+20h] [rbp-78h]
  _QWORD v9[2]; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v10[8]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v2 = (__int64 *)((char *)this + 64);
  if ( *((_QWORD *)this + 8) )
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref((char *)this + 64);
  v3 = CreateOnDemandBrokerClient(L"PsaBroker", v2);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\backgroundtaskhandler.cpp",
      (const char *)(unsigned int)v3,
      v8);
  v10[0] = off_180063428;
  v10[7] = v10;
  v4 = *v2;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, char *))(*(_QWORD *)v4 + 32LL);
  v6 = (_QWORD *)winrt::make<OnDemandBrokerCallBack,std::function<void (enum BackgroundTaskExitReason)> &>(v9, v10);
  v7 = v5(v4, *((unsigned int *)this + 14), *v6, (char *)this + 72);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\backgroundtaskhandler.cpp",
      (const char *)(unsigned int)v7,
      v8);
  if ( v9[0] )
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(v9);
  std::function<std::pair<winrt::hstring,unsigned int> (winrt::Windows::Data::Json::JsonObject const &)>::~function<std::pair<winrt::hstring,unsigned int> (winrt::Windows::Data::Json::JsonObject const &)>(v10);
}

```

## disassembly

```asm
0x18004e7e8  mov     [rsp+arg_8], rbx
0x18004e7ed  mov     [rsp+arg_10], rsi
0x18004e7f2  push    rdi
0x18004e7f3  sub     rsp, 90h
0x18004e7fa  mov     rax, cs:__security_cookie
0x18004e801  xor     rax, rsp
0x18004e804  mov     [rsp+98h+var_18], rax
0x18004e80c  mov     rsi, rcx
0x18004e80f  lea     rdi, [rcx+40h]
0x18004e813  cmp     qword ptr [rdi], 0
0x18004e817  jz      short loc_18004E821
0x18004e819  mov     rcx, rdi
0x18004e81c  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18004e821  mov     rdx, rdi
0x18004e824  lea     rcx, aPsabroker; "PsaBroker"
0x18004e82b  call    cs:__imp_CreateOnDemandBrokerClient
0x18004e831  mov     rcx, [rsp+98h]; this
0x18004e839  test    eax, eax
0x18004e83b  js      loc_18004E8E9
0x18004e841  lea     rax, off_180063428
0x18004e848  mov     [rsp+98h+var_58], rax
0x18004e84d  lea     rax, [rsp+98h+var_58]
0x18004e852  mov     [rsp+98h+var_20], rax
0x18004e857  mov     rdi, [rdi]
0x18004e85a  mov     rax, [rdi]
0x18004e85d  mov     rbx, [rax+20h]
0x18004e861  lea     rdx, [rsp+98h+var_58]
0x18004e866  lea     rcx, [rsp+98h+var_68]
0x18004e86b  call    ??$make@UOnDemandBrokerCallBack@@AEAV?$function@$$A6AXW4BackgroundTaskExitReason@@@Z@std@@@winrt@@YA?A_PAEAV?$function@$$A6AXW4BackgroundTaskExitReason@@@Z@std@@@Z
0x18004e870  nop
0x18004e871  lea     r9, [rsi+48h]
0x18004e875  mov     r8, [rax]
0x18004e878  mov     edx, [rsi+38h]
0x18004e87b  mov     rcx, rdi
0x18004e87e  mov     rax, rbx
0x18004e881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e886  mov     rcx, [rsp+98h]; this
0x18004e88e  test    eax, eax
0x18004e890  js      short loc_18004E8D4
0x18004e892  cmp     [rsp+98h+var_68], 0
0x18004e898  jz      short loc_18004E8A5
0x18004e89a  lea     rcx, [rsp+98h+var_68]
0x18004e89f  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18004e8a4  nop
0x18004e8a5  lea     rcx, [rsp+98h+var_58]
0x18004e8aa  call    ??1?$function@$$A6A?AU?$pair@Uhstring@winrt@@I@std@@AEBUJsonObject@Json@Data@Windows@winrt@@@Z@std@@QEAA@XZ; std::function<std::pair<winrt::hstring,uint> (winrt::Windows::Data::Json::JsonObject const &)>::~function<std::pair<winrt::hstring,uint> (winrt::Windows::Data::Json::JsonObject const &)>(void)
0x18004e8af  mov     rcx, [rsp+98h+var_18]
0x18004e8b7  xor     rcx, rsp; StackCookie
0x18004e8ba  call    __security_check_cookie
0x18004e8bf  lea     r11, [rsp+98h+var_8]
0x18004e8c7  mov     rbx, [r11+18h]
0x18004e8cb  mov     rsi, [r11+20h]
0x18004e8cf  mov     rsp, r11
0x18004e8d2  pop     rdi
0x18004e8d3  retn
0x18004e8d4  mov     r9d, eax; char *
0x18004e8d7  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\workflow"...
0x18004e8de  mov     edx, 23h ; '#'; void *
0x18004e8e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004e8e9  mov     r9d, eax; char *
0x18004e8ec  lea     r8, aOnecoreuapPrin; "onecoreuap\\printscan\\print\\workflow"...
0x18004e8f3  mov     edx, 1Fh; void *
0x18004e8f8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

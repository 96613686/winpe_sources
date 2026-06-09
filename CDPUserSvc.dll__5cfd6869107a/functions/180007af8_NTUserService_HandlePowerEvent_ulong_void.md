# NTUserService::HandlePowerEvent(ulong,void *)

- ea: `0x180007af8`
- end: `0x180007c52`
- name: `?HandlePowerEvent@NTUserService@@AEAAXKPEAX@Z`
- size: `346`
- prototype: `void __fastcall(NTUserService *__hidden this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180015100`

## callees

- `0x180004a58`
- `0x180004a98`
- `0x180006494`
- `0x180007af8`
- `0x180007c58`
- `0x18000eb48`
- `0x18002c570`
- `0x18003e1cc`
- `0x180064010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180007b8b`
- `msvcp_win!_Mtx_unlock` at `0x180007b8b`

## string_xrefs

- `0x180007b26`: `NTUserService received notification for SERVICE_CONTROL_POWEREVENT, eventType = %u`
- `0x180007bab`: `NTUserService entering low power mode`
- `0x180007c3a`: `NTUserService exiting low power mode`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NTUserService::HandlePowerEvent(NTUserService *this, int a2, _QWORD *a3)
{
  __int64 v6; // r14
  void (__fastcall *v7)(__int64, __int64, _QWORD *); // rbx
  char v8; // al
  _QWORD *v9; // r8
  __int64 v10; // rcx
  int v11; // edi
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // edi
  __int64 v16; // rax
  int v17; // [rsp+20h] [rbp-68h] BYREF
  void *v18; // [rsp+28h] [rbp-60h]
  _QWORD v19[4]; // [rsp+30h] [rbp-58h] BYREF

  v17 = a2;
  cdp::detail::StringFormat(
    v19,
    "NTUserService received notification for SERVICE_CONTROL_POWEREVENT, eventType = %u",
    a2);
  v18 = &g_loggerMutex;
  std::_Mutex_base::lock((std::_Mutex_base *)&g_loggerMutex);
  v6 = g_logger;
  if ( g_logger )
  {
    v7 = *(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)g_logger + 24LL);
    v8 = std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(v19);
    v9 = v19;
    if ( v8 )
      v9 = (_QWORD *)v19[0];
    v7(v6, 3, v9);
  }
  _Mtx_unlock((_Mtx_t)&g_loggerMutex);
  std::string::_Tidy_deallocate(v19);
  v11 = a2 - 4;
  if ( !v11 )
    goto LABEL_7;
  v12 = v11 - 1;
  if ( !v12 )
    goto LABEL_7;
  v13 = v12 - 2;
  if ( !v13 || (v14 = v13 - 1) == 0 || (v15 = v14 - 10) == 0 )
  {
LABEL_17:
    Log<unsigned long &>(v10, "NTUserService exiting low power mode", &v17);
    (*(void (__fastcall **)(NTUserService *))(*(_QWORD *)this + 24LL))(this);
    return;
  }
  if ( v15 == 32769 )
  {
    Log<>(3u, "Checking if power setting is for GUID_LOW_POWER_EPOCH");
    v16 = *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1 - *a3;
    if ( *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1 == *a3 )
      v16 = *(_QWORD *)GUID_LOW_POWER_EPOCH.Data4 - a3[1];
    if ( !v16 )
    {
      if ( *((_DWORD *)a3 + 5) )
      {
LABEL_7:
        Log<unsigned long &>(v10, "NTUserService entering low power mode", &v17);
        (*(void (__fastcall **)(NTUserService *))(*(_QWORD *)this + 16LL))(this);
        return;
      }
      goto LABEL_17;
    }
  }
}

```

## disassembly

```asm
0x180007af8  mov     [rsp+arg_10], rbx
0x180007afd  push    rbp
0x180007afe  push    rsi
0x180007aff  push    rdi
0x180007b00  push    r14
0x180007b02  push    r15
0x180007b04  sub     rsp, 60h
0x180007b08  mov     rax, cs:__security_cookie
0x180007b0f  xor     rax, rsp
0x180007b12  mov     [rsp+88h+var_38], rax
0x180007b17  mov     rbp, r8
0x180007b1a  mov     edi, edx
0x180007b1c  mov     rsi, rcx
0x180007b1f  mov     [rsp+88h+var_68], edx
0x180007b23  mov     r8d, edx
0x180007b26  lea     rdx, aNtuserserviceR; "NTUserService received notification for"...
0x180007b2d  lea     rcx, [rsp+88h+var_58]
0x180007b32  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x180007b37  nop
0x180007b38  lea     r15, ?g_loggerMutex@@3Vmutex@std@@A; std::mutex g_loggerMutex
0x180007b3f  mov     [rsp+88h+var_60], r15
0x180007b44  mov     rcx, r15; this
0x180007b47  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180007b4c  nop
0x180007b4d  mov     r14, cs:?g_logger@@3V?$shared_ptr@VICDPLogger@@@std@@A; std::shared_ptr<ICDPLogger> g_logger
0x180007b54  test    r14, r14
0x180007b57  jz      short loc_180007B88
0x180007b59  mov     rax, [r14]
0x180007b5c  mov     rbx, [rax+18h]
0x180007b60  lea     rcx, [rsp+88h+var_58]
0x180007b65  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x180007b6a  lea     r8, [rsp+88h+var_58]
0x180007b6f  test    al, al
0x180007b71  cmovnz  r8, [rsp+88h+var_58]
0x180007b77  mov     edx, 3
0x180007b7c  mov     rcx, r14
0x180007b7f  mov     rax, rbx
0x180007b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b87  nop
0x180007b88  mov     rcx, r15; _Mtx_t
0x180007b8b  call    cs:__imp__Mtx_unlock
0x180007b91  nop
0x180007b92  lea     rcx, [rsp+88h+var_58]
0x180007b97  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180007b9c  sub     edi, 4
0x180007b9f  jz      short loc_180007BA6
0x180007ba1  sub     edi, 1
0x180007ba4  jnz     short loc_180007BE7
0x180007ba6  lea     r8, [rsp+88h+var_68]
0x180007bab  lea     rdx, aNtuserserviceE_0; "NTUserService entering low power mode"
0x180007bb2  call    ??$Log@AEAK@@YAXW4CDPLogLevel@@PEBDAEAK@Z; Log<ulong &>(CDPLogLevel,char const *,ulong &)
0x180007bb7  mov     rax, [rsi]
0x180007bba  mov     rax, [rax+10h]
0x180007bbe  mov     rcx, rsi
0x180007bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bc6  mov     rcx, [rsp+88h+var_38]
0x180007bcb  xor     rcx, rsp; StackCookie
0x180007bce  call    __security_check_cookie
0x180007bd3  mov     rbx, [rsp+88h+arg_10]
0x180007bdb  add     rsp, 60h
0x180007bdf  pop     r15
0x180007be1  pop     r14
0x180007be3  pop     rdi
0x180007be4  pop     rsi
0x180007be5  pop     rbp
0x180007be6  retn
0x180007be7  sub     edi, 2
0x180007bea  jz      short loc_180007C35
0x180007bec  sub     edi, 1
0x180007bef  jz      short loc_180007C35
0x180007bf1  sub     edi, 0Ah
0x180007bf4  jz      short loc_180007C35
0x180007bf6  cmp     edi, 8001h
0x180007bfc  jnz     short loc_180007BC6
0x180007bfe  lea     rdx, aCheckingIfPowe; "Checking if power setting is for GUID_L"...
0x180007c05  mov     ecx, 3
0x180007c0a  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180007c0f  mov     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x180007c16  sub     rax, [rbp+0]
0x180007c1a  jnz     short loc_180007C27
0x180007c1c  mov     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data4
0x180007c23  sub     rax, [rbp+8]
0x180007c27  test    rax, rax
0x180007c2a  jnz     short loc_180007BC6
0x180007c2c  cmp     [rbp+14h], eax
0x180007c2f  jnz     loc_180007BA6
0x180007c35  lea     r8, [rsp+88h+var_68]
0x180007c3a  lea     rdx, aNtuserserviceE; "NTUserService exiting low power mode"
0x180007c41  call    ??$Log@AEAK@@YAXW4CDPLogLevel@@PEBDAEAK@Z; Log<ulong &>(CDPLogLevel,char const *,ulong &)
0x180007c46  mov     rax, [rsi]
0x180007c49  mov     rax, [rax+18h]
0x180007c4d  jmp     loc_180007BBE
```

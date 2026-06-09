# WpnService::RevokeClassFactoryCallback(tagComCallData *)

- ea: `0x18002a2b0`
- end: `0x18002a393`
- name: `?RevokeClassFactoryCallback@WpnService@@SAJPEAUtagComCallData@@@Z`
- size: `227`
- prototype: `static int(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800202bc`
- `0x180028218`
- `0x180028368`
- `0x18002a2b0`
- `0x18002a73c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18002a31d`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x18002a31d`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x18002a36b`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x18002a36b`

## string_xrefs

- `0x18002a2d3`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`
- `0x18002a32e`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\systemservice\dll\wpnservice.cpp`

## pseudocode

```c
__int64 __fastcall WpnService::RevokeClassFactoryCallback(
        struct tagComCallData *a1,
        struct Microsoft::WRL::Details::ModuleBase *a2,
        const unsigned __int16 *a3)
{
  HRESULT v3; // ebx
  __int64 v4; // rdx
  DWORD **pUserDefined; // rdi
  HRESULT v7; // eax
  unsigned int v8; // esi
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  DWORD *v11; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 )
  {
    v3 = -2147024809;
    v4 = 321;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
      (const char *)(unsigned int)v3,
      v9);
    return (unsigned int)v3;
  }
  pUserDefined = (DWORD **)a1->pUserDefined;
  Microsoft::WRL::Details::UnregisterObjects(module, a2, a3);
  if ( **pUserDefined )
  {
    v11 = pUserDefined[1] + 2;
    ServiceHostTelemetry::RevokingClassObject<unsigned short const *>((__int64 *)&v11);
    v7 = CoRevokeClassObject(**pUserDefined);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\systemservice\\dll\\wpnservice.cpp",
        (const char *)(unsigned int)v7,
        v9);
      return v8;
    }
    **pUserDefined = 0;
  }
  v11 = pUserDefined[1] + 2;
  ServiceHostTelemetry::DisconnectingContext<unsigned short const *>((__int64 *)&v11);
  v3 = CoDisconnectContext(0x1388u);
  if ( v3 < 0 )
  {
    v4 = 341;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18002a2b0  mov     [rsp+arg_8], rbx
0x18002a2b5  mov     [rsp+arg_10], rsi
0x18002a2ba  push    rdi; int
0x18002a2bb  sub     rsp, 20h
0x18002a2bf  test    rcx, rcx
0x18002a2c2  jnz     short loc_18002A2E9
0x18002a2c4  mov     ebx, 80070057h
0x18002a2c9  mov     edx, 141h; void *
0x18002a2ce  mov     rcx, [rsp+28h]; this
0x18002a2d3  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002a2da  mov     r9d, ebx; char *
0x18002a2dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a2e2  mov     eax, ebx
0x18002a2e4  jmp     loc_18002A383
0x18002a2e9  mov     rdi, [rcx+8]
0x18002a2ed  mov     rcx, cs:?module@@3AEAVWpnServiceModule@@EA; this
0x18002a2f4  call    ?UnregisterObjects@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEBG@Z; Microsoft::WRL::Details::UnregisterObjects(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x18002a2f9  mov     rax, [rdi]
0x18002a2fc  cmp     dword ptr [rax], 0
0x18002a2ff  jz      short loc_18002A34F
0x18002a301  mov     rax, [rdi+8]
0x18002a305  lea     rcx, [rsp+28h+arg_0]
0x18002a30a  add     rax, 8
0x18002a30e  mov     [rsp+28h+arg_0], rax
0x18002a313  call    ??$RevokingClassObject@PEBG@ServiceHostTelemetry@@SAX$$QEAPEBG@Z; ServiceHostTelemetry::RevokingClassObject<ushort const *>(ushort const * &&)
0x18002a318  mov     rcx, [rdi]
0x18002a31b  mov     ecx, [rcx]; dwRegister
0x18002a31d  call    cs:__imp_CoRevokeClassObject
0x18002a323  mov     esi, eax
0x18002a325  test    eax, eax
0x18002a327  jns     short loc_18002A346
0x18002a329  mov     rcx, [rsp+28h]; this
0x18002a32e  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18002a335  mov     r9d, eax; char *
0x18002a338  mov     edx, 14Dh; void *
0x18002a33d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a342  mov     eax, esi
0x18002a344  jmp     short loc_18002A383
0x18002a346  mov     rax, [rdi]
0x18002a349  mov     dword ptr [rax], 0
0x18002a34f  mov     rax, [rdi+8]
0x18002a353  lea     rcx, [rsp+28h+arg_0]
0x18002a358  add     rax, 8
0x18002a35c  mov     [rsp+28h+arg_0], rax
0x18002a361  call    ??$DisconnectingContext@PEBG@ServiceHostTelemetry@@SAX$$QEAPEBG@Z; ServiceHostTelemetry::DisconnectingContext<ushort const *>(ushort const * &&)
0x18002a366  mov     ecx, 1388h; dwTimeout
0x18002a36b  call    cs:__imp_CoDisconnectContext
0x18002a371  mov     ebx, eax
0x18002a373  test    eax, eax
0x18002a375  jns     short loc_18002A381
0x18002a377  mov     edx, 155h
0x18002a37c  jmp     loc_18002A2CE
0x18002a381  xor     eax, eax
0x18002a383  mov     rbx, [rsp+28h+arg_8]
0x18002a388  mov     rsi, [rsp+28h+arg_10]
0x18002a38d  add     rsp, 20h
0x18002a391  pop     rdi
0x18002a392  retn
```

# DllGetClassObject

- ea: `0x180003750`
- end: `0x180003894`
- name: `DllGetClassObject`
- size: `324`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003750`
- `0x18000d68c`
- `0x180014e3c`
- `0x18002c6fc`
- `0x18004d010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x18000386e`
- `RPCRT4!NdrDllGetClassObject` at `0x18000386e`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT result; // eax

  result = GameInputModule::LoadModule((__int64)rclsid, (__int64)riid, (const WCHAR *)ppv);
  if ( !result )
    return (*((__int64 (__fastcall **)(const IID *const, const IID *const, LPVOID *))&xmmword_1800698C0 + 1))(
             rclsid,
             riid,
             ppv);
  if ( result != 1 )
  {
    *ppv = 0;
    return result;
  }
  if ( *(_QWORD *)&rclsid->Data1 == 0x46B0C7A8FF66E172LL
    && *(_QWORD *)rclsid->Data4 == 0xDECAF68EF771BE9AuLL
    && *(_QWORD *)&riid->Data1 == *(_QWORD *)&GUID_ff03efb3_9964_4a77_bbf0_2a387f32c83c.Data1
    && *(_QWORD *)riid->Data4 == *(_QWORD *)GUID_ff03efb3_9964_4a77_bbf0_2a387f32c83c.Data4 )
  {
    if ( _InterlockedExchangeAdd(&dword_180069040, 1u) == -1 )
    {
      GameInputFailFast(2147500036LL, 28);
      JUMPOUT(0x180003893LL);
    }
    *ppv = &g_serverFactory;
    return 0;
  }
  if ( *(_QWORD *)&rclsid->Data1 == 0x4AD834D9A059B652LL
    && *(_QWORD *)rclsid->Data4 == 0xADC8E93AE18D76ADuLL
    && GetHidForceFeedbackBrokerFactory((const struct _GUID *)1, riid, ppv) >= 0 )
  {
    return 0;
  }
  return NdrDllGetClassObject(
           rclsid,
           riid,
           ppv,
           (const ProxyFileInfo **)&aProxyFileList,
           &CLSID_PSFactoryBuffer,
           &gPFactory);
}

```

## disassembly

```asm
0x180003750  push    rbp
0x180003752  push    rbx
0x180003753  push    rsi
0x180003754  push    rdi
0x180003755  mov     rbp, rsp
0x180003758  sub     rsp, 48h
0x18000375c  mov     rdi, r8
0x18000375f  mov     rsi, rdx
0x180003762  mov     rbx, rcx
0x180003765  call    ?LoadModule@GameInputModule@@AEAAJW4ModuleKind@1@AEBUGameInputVersion@@@Z; GameInputModule::LoadModule(GameInputModule::ModuleKind,GameInputVersion const &)
0x18000376a  test    eax, eax
0x18000376c  jnz     short loc_180003788
0x18000376e  mov     rax, qword ptr cs:xmmword_1800698C0+8
0x180003775  mov     r8, rdi
0x180003778  mov     rdx, rsi
0x18000377b  mov     rcx, rbx
0x18000377e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003783  jmp     loc_18000387A
0x180003788  mov     ecx, 1; struct _GUID *
0x18000378d  cmp     eax, ecx
0x18000378f  jz      short loc_18000379D
0x180003791  mov     qword ptr [rdi], 0
0x180003798  jmp     loc_18000387A
0x18000379d  mov     rax, [rbx]
0x1800037a0  mov     dword ptr [rbp+var_18], 0FF66E172h
0x1800037a7  mov     dword ptr [rbp+var_18+4], 46B0C7A8h
0x1800037ae  mov     dword ptr [rbp+var_10], 0F771BE9Ah
0x1800037b5  mov     dword ptr [rbp+var_10+4], 0DECAF68Eh
0x1800037bc  cmp     rax, [rbp+var_18]
0x1800037c0  jnz     short loc_180003808
0x1800037c2  mov     rax, [rbx+8]
0x1800037c6  cmp     rax, [rbp+var_10]
0x1800037ca  jnz     short loc_180003808
0x1800037cc  mov     rax, [rsi]
0x1800037cf  cmp     rax, qword ptr cs:_GUID_ff03efb3_9964_4a77_bbf0_2a387f32c83c.Data1
0x1800037d6  jnz     short loc_180003808
0x1800037d8  mov     rax, [rsi+8]
0x1800037dc  cmp     rax, qword ptr cs:_GUID_ff03efb3_9964_4a77_bbf0_2a387f32c83c.Data4
0x1800037e3  jnz     short loc_180003808
0x1800037e5  nop
0x1800037e6  lock xadd cs:dword_180069040, ecx
0x1800037ee  lea     eax, [rcx+1]
0x1800037f1  nop
0x1800037f2  test    eax, eax
0x1800037f4  jz      loc_180003884
0x1800037fa  lea     rax, ?g_serverFactory@@3VServerFactory@@A; ServerFactory g_serverFactory
0x180003801  mov     [rdi], rax
0x180003804  xor     eax, eax
0x180003806  jmp     short loc_18000387A
0x180003808  mov     rax, [rbx]
0x18000380b  mov     dword ptr [rbp+var_18], 0A059B652h
0x180003812  mov     dword ptr [rbp+var_18+4], 4AD834D9h
0x180003819  mov     dword ptr [rbp+var_10], 0E18D76ADh
0x180003820  mov     dword ptr [rbp+var_10+4], 0ADC8E93Ah
0x180003827  cmp     rax, [rbp+var_18]
0x18000382b  jnz     short loc_180003846
0x18000382d  mov     rax, [rbx+8]
0x180003831  cmp     rax, [rbp+var_10]
0x180003835  jnz     short loc_180003846
0x180003837  mov     r8, rdi; void **
0x18000383a  mov     rdx, rsi; struct _GUID *
0x18000383d  call    ?GetHidForceFeedbackBrokerFactory@@YAJAEBU_GUID@@0PEAPEAX@Z; GetHidForceFeedbackBrokerFactory(_GUID const &,_GUID const &,void * *)
0x180003842  test    eax, eax
0x180003844  jns     short loc_180003804
0x180003846  lea     rax, gPFactory
0x18000384d  mov     r8, rdi; ppv
0x180003850  mov     [rsp+48h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180003855  lea     r9, aProxyFileList; pProxyFileList
0x18000385c  lea     rax, CLSID_PSFactoryBuffer
0x180003863  mov     rdx, rsi; riid
0x180003866  mov     rcx, rbx; rclsid
0x180003869  mov     [rsp+48h+pclsid], rax; pclsid
0x18000386e  call    cs:__imp_NdrDllGetClassObject
0x180003875  nop     dword ptr [rax+rax+00h]
0x18000387a  add     rsp, 48h
0x18000387e  pop     rdi
0x18000387f  pop     rsi
0x180003880  pop     rbx
0x180003881  pop     rbp
0x180003882  retn
0x180003884  mov     edx, 1Ch
0x180003889  mov     ecx, 80004004h
0x18000388e  call    GameInputFailFast
```

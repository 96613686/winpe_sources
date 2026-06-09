# FreeAuthBrokerClientContext(_AUTH_BROKER_CLIENT_CONTEXT *)

- ea: `0x180003330`
- end: `0x1800033ae`
- name: `?FreeAuthBrokerClientContext@@YAXPEAU_AUTH_BROKER_CLIENT_CONTEXT@@@Z`
- size: `126`
- prototype: `void __fastcall(_AUTH_BROKER_CLIENT_CONTEXT *clientContext, __int64, const _GUID *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002a70`
- `0x180002b20`
- `0x180011630`
- `0x180017150`
- `0x180017770`
- `0x180019030`

## callees

- `0x180003330`
- `0x180012128`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003399`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003399`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000338a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000338a`

## pseudocode

```c
void __fastcall FreeAuthBrokerClientContext(_AUTH_BROKER_CLIENT_CONTEXT *clientContext, __int64 a2, const _GUID *a3)
{
  wchar_t *dialogTitle; // rcx
  void *tokenHandle; // rcx

  if ( clientContext )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 5u )
    {
      WPP_SF_qd(WPP_GLOBAL_Control[1].Control.Logger, 0x5Fu, a3, clientContext, clientContext->refCount);
    }
    if ( _InterlockedExchangeAdd(&clientContext->refCount, 0xFFFFFFFF) == 1 )
    {
      dialogTitle = clientContext->dialogTitle;
      if ( dialogTitle )
        CoTaskMemFree(dialogTitle);
      tokenHandle = clientContext->tokenHandle;
      if ( tokenHandle )
        CloseHandle(tokenHandle);
      LocalFree(clientContext);
    }
  }
}

```

## disassembly

```asm
0x180003330  test    clientContext, clientContext
0x180003333  jz      short locret_1800033AD
0x180003335  push    rbx
0x180003336  sub     rsp, 30h
0x18000333a  mov     rbx, clientContext
0x18000333d  mov     clientContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180003344  lea     rax, WPP_GLOBAL_Control
0x18000334b  cmp     clientContext, rax
0x18000334e  jz      short loc_180003373
0x180003350  test    byte ptr [clientContext+44h], 10h
0x180003354  jz      short loc_180003373
0x180003356  cmp     byte ptr [clientContext+41h], 5
0x18000335a  jb      short loc_180003373
0x18000335c  mov     eax, [rbx]
0x18000335e  mov     edx, 5Fh ; '_'; id
0x180003363  mov     clientContext, [clientContext+38h]; Logger
0x180003367  mov     r9, rbx; _a2
0x18000336a  mov     [rsp+38h+Logger], eax; Logger
0x18000336e  call    WPP_SF_qd
0x180003373  mov     eax, 0FFFFFFFFh
0x180003378  lock xadd [rbx], eax
0x18000337c  cmp     eax, 1
0x18000337f  jnz     short loc_1800033A8
0x180003381  mov     clientContext, [rbx+10h]; pv
0x180003385  test    clientContext, clientContext
0x180003388  jz      short loc_180003390
0x18000338a  call    cs:__imp_CoTaskMemFree
0x180003390  mov     clientContext, [rbx+20h]; hObject
0x180003394  test    clientContext, clientContext
0x180003397  jz      short loc_18000339F
0x180003399  call    cs:__imp_CloseHandle
0x18000339f  mov     clientContext, rbx; hMem
0x1800033a2  call    cs:__imp_LocalFree
0x1800033a8  add     rsp, 30h
0x1800033ac  pop     rbx
0x1800033ad  retn
```

# ConnectCallback

- ea: `0x140006700`
- end: `0x14000676c`
- name: `ConnectCallback`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140006700`
- `0x14000e328`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000672a`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x14000672a`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000673f`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x14000673f`

## string_xrefs

- `0x14000674b`: `Unable to resume suspended COM objects.`

## pseudocode

```c
__int64 ConnectCallback()
{
  HRESULT v0; // eax
  unsigned int v1; // ebx
  HRESULT v2; // eax

  v0 = CoRegisterClassObject(&CLSID_CbsWorker, vpWorkerFactory, 4u, 5u, &dwRegisteredWorkerFactoryID);
  v1 = v0;
  if ( v0 >= 0 )
  {
    v2 = CoResumeClassObjects();
    v1 = v2;
    if ( v2 < 0 )
      CBSWdsLog(0x4000000u, v2, (size_t *)1, "Unable to resume suspended COM objects.");
  }
  else
  {
    CBSWdsLog(0x4000000u, v0, (size_t *)1, "Failed to register worker factory");
  }
  return v1;
}

```

## disassembly

```asm
0x140006700  push    rbx
0x140006702  sub     rsp, 30h
0x140006706  mov     rdx, cs:?vpWorkerFactory@@3PEAUIClassFactory@@EA; pUnk
0x14000670d  lea     rax, ?dwRegisteredWorkerFactoryID@@3KA; ulong dwRegisteredWorkerFactoryID
0x140006714  mov     r9d, 5; flags
0x14000671a  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x14000671f  lea     rcx, CLSID_CbsWorker; rclsid
0x140006726  lea     r8d, [r9-1]; dwClsContext
0x14000672a  call    cs:__imp_CoRegisterClassObject
0x140006730  mov     ebx, eax
0x140006732  test    eax, eax
0x140006734  jns     short loc_14000673F
0x140006736  lea     r9, aFailedToRegist; "Failed to register worker factory"
0x14000673d  jmp     short loc_140006752
0x14000673f  call    cs:__imp_CoResumeClassObjects
0x140006745  mov     ebx, eax
0x140006747  test    eax, eax
0x140006749  jns     short loc_140006764
0x14000674b  lea     r9, aUnableToResume; "Unable to resume suspended COM objects."
0x140006752  mov     r8d, 1
0x140006758  mov     edx, eax
0x14000675a  mov     ecx, 4000000h
0x14000675f  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140006764  mov     eax, ebx
0x140006766  add     rsp, 30h
0x14000676a  pop     rbx
0x14000676b  retn
```

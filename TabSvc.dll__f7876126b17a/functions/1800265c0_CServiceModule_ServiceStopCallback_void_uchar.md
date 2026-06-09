# CServiceModule::ServiceStopCallback(void *,uchar)

- ea: `0x1800265c0`
- end: `0x180026640`
- name: `?ServiceStopCallback@CServiceModule@@SAXPEAXE@Z`
- size: `128`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18001fcbc`
- `0x18002638c`
- `0x1800265c0`
- `0x180027420`
- `0x18002b3a8`
- `0x18002b710`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800265fb`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x1800265fb`

## string_xrefs

- `0x180026622`: `PENSERVICE_CServiceModule::ServiceStopCallback`

## pseudocode

```c
void __fastcall CServiceModule::ServiceStopCallback(void *a1)
{
  HANDLE v1; // rbx
  unsigned int v2; // edx

  v1 = WaitHandle;
  CServiceModule::ServiceMainEnd((CServiceModule *)&_Module);
  CServiceModule::Stop((CServiceModule *)&_Module, v2);
  CServiceModule::Destroy((CServiceModule *)&_Module);
  WppCleanupUm();
  if ( !UnregisterWaitEx(v1, 0)
    && WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      136,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::ServiceStopCallback");
  }
}

```

## disassembly

```asm
0x1800265c0  push    rbx
0x1800265c2  sub     rsp, 20h
0x1800265c6  mov     rbx, cs:WaitHandle
0x1800265cd  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x1800265d4  call    ?ServiceMainEnd@CServiceModule@@QEAAXXZ; CServiceModule::ServiceMainEnd(void)
0x1800265d9  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x1800265e0  call    ?Stop@CServiceModule@@QEAAXXZ; CServiceModule::Stop(void)
0x1800265e5  lea     rcx, ?_Module@@3VCServiceModule@@A; this
0x1800265ec  call    ?Destroy@CServiceModule@@QEAAXXZ; CServiceModule::Destroy(void)
0x1800265f1  call    WppCleanupUm
0x1800265f6  xor     edx, edx; CompletionEvent
0x1800265f8  mov     rcx, rbx; WaitHandle
0x1800265fb  call    cs:__imp_UnregisterWaitEx
0x180026601  test    eax, eax
0x180026603  jnz     short loc_18002663A
0x180026605  mov     rcx, cs:WPP_GLOBAL_Control
0x18002660c  lea     rax, WPP_GLOBAL_Control
0x180026613  cmp     rcx, rax
0x180026616  jz      short loc_18002663A
0x180026618  test    byte ptr [rcx+1Ch], 4
0x18002661c  jz      short loc_18002663A
0x18002661e  mov     rcx, [rcx+10h]
0x180026622  lea     r9, aPenserviceCser; "PENSERVICE_CServiceModule::ServiceStopC"...
0x180026629  mov     edx, 88h
0x18002662e  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180026635  call    WPP_SF_s
0x18002663a  add     rsp, 20h
0x18002663e  pop     rbx
0x18002663f  retn
```

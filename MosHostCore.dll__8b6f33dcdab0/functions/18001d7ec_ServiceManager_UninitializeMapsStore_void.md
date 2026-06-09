# ServiceManager::UninitializeMapsStore(void)

- ea: `0x18001d7ec`
- end: `0x18001d86a`
- name: `?UninitializeMapsStore@ServiceManager@@AEAAJXZ`
- size: `126`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001d7c4`

## callees

- `0x18001d7ec`
- `0x18001e454`

## import_xrefs

- `MapsStore!MapsStore_UnInitialize` at `0x18001d81a`
- `MapsStore!MapsStore_UnInitialize` at `0x18001d81a`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001d814`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001d814`
- `ZTrace_Maps!ZTraceHelper` at `0x18001d857`
- `ZTrace_Maps!ZTraceHelper` at `0x18001d857`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001d836`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001d836`

## string_xrefs

- `0x18001d805`: `ServiceManager::UninitializeMapsStore`
- `0x18001d823`: `ServiceManager::UninitializeMapsStore`
- `0x18001d842`: `[MosHost] Service - Shutdown - MapsStore uninitialized`

## pseudocode

```c
__int64 __fastcall ServiceManager::UninitializeMapsStore(ServiceManager *this)
{
  int v2; // eax
  int v3; // eax
  unsigned int v4; // edi

  v2 = ServiceManager::WaitForMOSAndBingInit(this);
  if ( v2 < 0 )
    ZTraceReportIgnore(v2, "ServiceManager::UninitializeMapsStore", 2777, this);
  v3 = MapsStore_UnInitialize();
  if ( v3 >= 0 )
  {
    v4 = 0;
    ZTraceHelper(
      5,
      "ServiceManager::UninitializeMapsStore",
      2781,
      this,
      "[MosHost] Service - Shutdown - MapsStore uninitialized");
  }
  else
  {
    return (unsigned int)ZTraceReportOrigination(v3, "ServiceManager::UninitializeMapsStore", 2779, this);
  }
  return v4;
}

```

## disassembly

```asm
0x18001d7ec  mov     [rsp+arg_0], rbx
0x18001d7f1  push    rdi
0x18001d7f2  sub     rsp, 30h
0x18001d7f6  mov     rbx, rcx
0x18001d7f9  call    ?WaitForMOSAndBingInit@ServiceManager@@AEAAJXZ; ServiceManager::WaitForMOSAndBingInit(void)
0x18001d7fe  test    eax, eax
0x18001d800  jns     short loc_18001D81A
0x18001d802  mov     r9, rbx
0x18001d805  lea     rdx, aServicemanager_86; "ServiceManager::UninitializeMapsStore"
0x18001d80c  mov     r8d, 0AD9h
0x18001d812  mov     ecx, eax
0x18001d814  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001d81a  call    cs:__imp_?MapsStore_UnInitialize@@YAJXZ; MapsStore_UnInitialize(void)
0x18001d820  mov     r9, rbx
0x18001d823  lea     rdx, aServicemanager_86; "ServiceManager::UninitializeMapsStore"
0x18001d82a  test    eax, eax
0x18001d82c  jns     short loc_18001D840
0x18001d82e  mov     r8d, 0ADBh
0x18001d834  mov     ecx, eax
0x18001d836  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001d83c  mov     edi, eax
0x18001d83e  jmp     short loc_18001D85D
0x18001d840  xor     edi, edi
0x18001d842  lea     rax, aMoshostService_3; "[MosHost] Service - Shutdown - MapsStor"...
0x18001d849  mov     r8d, 0ADDh
0x18001d84f  mov     [rsp+38h+var_18], rax
0x18001d854  lea     ecx, [rdi+5]
0x18001d857  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001d85d  mov     rbx, [rsp+38h+arg_0]
0x18001d862  mov     eax, edi
0x18001d864  add     rsp, 30h
0x18001d868  pop     rdi
0x18001d869  retn
```

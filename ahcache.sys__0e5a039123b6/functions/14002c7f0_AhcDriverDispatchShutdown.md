# AhcDriverDispatchShutdown

- ea: `0x14002c7f0`
- end: `0x14002c88a`
- name: `AhcDriverDispatchShutdown`
- size: `154`
- prototype: `__int64 __fastcall(__int64, IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14002a6b4`
- `0x14002c7f0`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!PsGetPermanentSiloContext` at `0x14002c822`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14002c822`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14002c80c`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14002c80c`
- `ntoskrnl!IofCompleteRequest` at `0x14002c870`
- `ntoskrnl!IofCompleteRequest` at `0x14002c870`

## string_xrefs

- `0x14002c842`: `Failed to save cache data to registry [%x]`

## pseudocode

```c
__int64 __fastcall AhcDriverDispatchShutdown(__int64 a1, IRP *a2)
{
  unsigned int v2; // ebx
  __int64 CurrentServerSilo; // rax
  int v5; // eax
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  v2 = g_AhcacheSiloContextSlot;
  v7 = 0;
  CurrentServerSilo = PsGetCurrentServerSilo();
  PsGetPermanentSiloContext(CurrentServerSilo, v2, &v7);
  if ( *(_DWORD *)(v7 + 96) )
  {
    v5 = AhcPersist();
    if ( v5 < 0 )
      AslLogCallPrintf(1, "AhcDriverDispatchShutdown", 525, "Failed to save cache data to registry [%x]", v5);
  }
  a2->IoStatus.Status = 0;
  IofCompleteRequest(a2, 0);
  return 0;
}

```

## disassembly

```asm
0x14002c7f0  mov     [rsp+arg_0], rbx
0x14002c7f5  push    rdi
0x14002c7f6  sub     rsp, 30h
0x14002c7fa  mov     ebx, cs:g_AhcacheSiloContextSlot
0x14002c800  mov     rdi, rdx
0x14002c803  mov     [rsp+38h+arg_8], 0
0x14002c80c  call    cs:__imp_PsGetCurrentServerSilo
0x14002c813  nop     dword ptr [rax+rax+00h]
0x14002c818  lea     r8, [rsp+38h+arg_8]
0x14002c81d  mov     edx, ebx
0x14002c81f  mov     rcx, rax
0x14002c822  call    cs:__imp_PsGetPermanentSiloContext
0x14002c829  nop     dword ptr [rax+rax+00h]
0x14002c82e  mov     rcx, [rsp+38h+arg_8]
0x14002c833  cmp     dword ptr [rcx+60h], 0
0x14002c837  jz      short loc_14002C864
0x14002c839  call    AhcPersist
0x14002c83e  test    eax, eax
0x14002c840  jns     short loc_14002C864
0x14002c842  lea     r9, aFailedToSaveCa; "Failed to save cache data to registry ["...
0x14002c849  mov     [rsp+38h+var_18], eax
0x14002c84d  mov     r8d, 20Dh
0x14002c853  lea     rdx, aAhcdriverdispa; "AhcDriverDispatchShutdown"
0x14002c85a  mov     ecx, 1
0x14002c85f  call    AslLogCallPrintf
0x14002c864  xor     edx, edx; PriorityBoost
0x14002c866  mov     dword ptr [rdi+30h], 0
0x14002c86d  mov     rcx, rdi; Irp
0x14002c870  call    cs:__imp_IofCompleteRequest
0x14002c877  nop     dword ptr [rax+rax+00h]
0x14002c87c  mov     rbx, [rsp+38h+arg_0]
0x14002c881  xor     eax, eax
0x14002c883  add     rsp, 30h
0x14002c887  pop     rdi
0x14002c888  retn
```

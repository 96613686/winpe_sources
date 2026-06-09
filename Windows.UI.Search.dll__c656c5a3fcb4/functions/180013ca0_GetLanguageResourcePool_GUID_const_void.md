# _GetLanguageResourcePool(_GUID const &,void * *)

- ea: `0x180013ca0`
- end: `0x180013dad`
- name: `?_GetLanguageResourcePool@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `269`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012930`
- `0x180045be0`

## callees

- `0x180013060`
- `0x1800130f8`
- `0x1800133b0`
- `0x180013ca0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013d1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013d1d`

## string_xrefs

- `0x180013cbc`: `WBCache`

## pseudocode

```c
__int64 __fastcall _GetLanguageResourcePool(const struct _GUID *a1, void **a2)
{
  HRESULT v4; // ebx
  int v6; // [rsp+58h] [rbp+28h] BYREF
  struct IUnknown *v7; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  DelayAllocateTLS(&g_tlsWBCache, L"WBCache");
  v6 = 0;
  v4 = CachedSTAObject_QueryInterface(g_tlsWBCache, &v6, a1, a2);
  if ( v4 == 1 )
  {
    ppv = 0;
    v4 = CoCreateInstance(
           &GUID_934d4698_6a59_48f8_9f29_9fb30670320e,
           0,
           1u,
           &GUID_b3ddac23_10ba_4407_98de_f5fef5db4629,
           &ppv);
    if ( v4 >= 0 )
    {
      v7 = 0;
      v4 = (*(__int64 (__fastcall **)(LPVOID, GUID *, struct IUnknown **))(*(_QWORD *)ppv + 80LL))(
             ppv,
             &GUID_7b732139_70db_4196_a7ae_5406ed4457c5,
             &v7);
      if ( v4 >= 0 )
      {
        if ( v6 )
          CachedSTAObject_SetObject(g_tlsWBCache, v7);
        v4 = ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, void **))v7->lpVtbl->QueryInterface)(
               v7,
               a1,
               a2);
        ((void (__fastcall *)(struct IUnknown *))v7->lpVtbl->Release)(v7);
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180013ca0  mov     [rsp-18h+arg_0], rbx
0x180013ca5  push    rbp
0x180013ca6  push    rsi
0x180013ca7  push    rdi
0x180013ca8  mov     rbp, rsp
0x180013cab  sub     rsp, 30h
0x180013caf  mov     rdi, rdx
0x180013cb2  mov     qword ptr [rdx], 0
0x180013cb9  mov     rsi, rcx
0x180013cbc  lea     rdx, aWbcache; "WBCache"
0x180013cc3  lea     rcx, ?g_tlsWBCache@@3KA; unsigned int *
0x180013cca  call    ?DelayAllocateTLS@@YAJPEAKPEBG@Z; DelayAllocateTLS(ulong *,ushort const *)
0x180013ccf  mov     ecx, cs:?g_tlsWBCache@@3KA; unsigned int
0x180013cd5  lea     rdx, [rbp+arg_8]; int *
0x180013cd9  mov     r9, rdi; void **
0x180013cdc  mov     [rbp+arg_8], 0
0x180013ce3  mov     r8, rsi; struct _GUID *
0x180013ce6  call    ?CachedSTAObject_QueryInterface@@YAJKPEAHAEBU_GUID@@PEAPEAX@Z; CachedSTAObject_QueryInterface(ulong,int *,_GUID const &,void * *)
0x180013ceb  mov     r8d, 1; dwClsContext
0x180013cf1  mov     ebx, eax
0x180013cf3  cmp     eax, r8d
0x180013cf6  jnz     loc_180013D9E
0x180013cfc  lea     rax, [rbp+arg_18]
0x180013d00  mov     [rbp+arg_18], 0
0x180013d08  lea     r9, _GUID_b3ddac23_10ba_4407_98de_f5fef5db4629; riid
0x180013d0f  mov     [rsp+30h+ppv], rax; ppv
0x180013d14  xor     edx, edx; pUnkOuter
0x180013d16  lea     rcx, _GUID_934d4698_6a59_48f8_9f29_9fb30670320e; rclsid
0x180013d1d  call    cs:__imp_CoCreateInstance
0x180013d23  mov     ebx, eax
0x180013d25  test    eax, eax
0x180013d27  js      short loc_180013D9E
0x180013d29  mov     rcx, [rbp+arg_18]
0x180013d2d  lea     r8, [rbp+arg_10]
0x180013d31  mov     [rbp+arg_10], 0
0x180013d39  lea     rdx, _GUID_7b732139_70db_4196_a7ae_5406ed4457c5
0x180013d40  mov     rax, [rcx]
0x180013d43  mov     rax, [rax+50h]
0x180013d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d4c  mov     ebx, eax
0x180013d4e  test    eax, eax
0x180013d50  js      short loc_180013D8E
0x180013d52  cmp     [rbp+arg_8], 0
0x180013d56  jz      short loc_180013D67
0x180013d58  mov     rdx, [rbp+arg_10]; struct IUnknown *
0x180013d5c  mov     ecx, cs:?g_tlsWBCache@@3KA; unsigned int
0x180013d62  call    ?CachedSTAObject_SetObject@@YAJKPEAUIUnknown@@@Z; CachedSTAObject_SetObject(ulong,IUnknown *)
0x180013d67  mov     rcx, [rbp+arg_10]
0x180013d6b  mov     r8, rdi
0x180013d6e  mov     rdx, rsi
0x180013d71  mov     rax, [rcx]
0x180013d74  mov     rax, [rax]
0x180013d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d7c  mov     rcx, [rbp+arg_10]
0x180013d80  mov     ebx, eax
0x180013d82  mov     rax, [rcx]
0x180013d85  mov     rax, [rax+10h]
0x180013d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d8e  mov     rcx, [rbp+arg_18]
0x180013d92  mov     rax, [rcx]
0x180013d95  mov     rax, [rax+10h]
0x180013d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d9e  mov     eax, ebx
0x180013da0  mov     rbx, [rsp+30h+arg_0]
0x180013da5  add     rsp, 30h
0x180013da9  pop     rdi
0x180013daa  pop     rsi
0x180013dab  pop     rbp
0x180013dac  retn
```

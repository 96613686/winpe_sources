# CConflictPropertyStore::s_GetSyncHandlerID(ISyncMgrConflict *,ushort * *)

- ea: `0x18003840c`
- end: `0x180038496`
- name: `?s_GetSyncHandlerID@CConflictPropertyStore@@SAJPEAUISyncMgrConflict@@PEAPEAG@Z`
- size: `138`
- prototype: `static int(struct ISyncMgrConflict *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180033a80`
- `0x180036e94`

## callees

- `0x18003840c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038470`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003847e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003847e`
- `PROPSYS!PropVariantToStringAlloc` at `0x180038457`
- `PROPSYS!PropVariantToStringAlloc` at `0x180038457`

## pseudocode

```c
__int64 __fastcall CConflictPropertyStore::s_GetSyncHandlerID(struct ISyncMgrConflict *a1, unsigned __int16 **a2)
{
  HRESULT v3; // ebx
  PROPVARIANT propvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+30h] [rbp-18h]

  *(_OWORD *)propvar = 0;
  v6 = 0;
  *a2 = 0;
  v3 = ((__int64 (__fastcall *)(struct ISyncMgrConflict *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetProperty)(
         a1,
         &PKEY_Sync_HandlerID,
         propvar);
  if ( v3 >= 0 )
  {
    v3 = PropVariantToStringAlloc(propvar, a2);
    if ( v3 >= 0 && !**a2 )
    {
      v3 = -2147467259;
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
    PropVariantClear(propvar);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003840c  mov     r11, rsp
0x18003840f  mov     [r11+8], rbx
0x180038413  mov     [r11+10h], rsi
0x180038417  push    rdi
0x180038418  sub     rsp, 40h
0x18003841c  xor     eax, eax
0x18003841e  lea     r8, [r11-28h]
0x180038422  xorps   xmm0, xmm0
0x180038425  mov     rdi, rdx
0x180038428  movups  xmmword ptr [rsp+48h+propvar], xmm0
0x18003842d  mov     [r11-18h], rax
0x180038431  xor     esi, esi
0x180038433  mov     [rdx], rsi
0x180038436  lea     rdx, PKEY_Sync_HandlerID
0x18003843d  mov     rax, [rcx]
0x180038440  mov     rax, [rax+18h]
0x180038444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038449  mov     ebx, eax
0x18003844b  test    eax, eax
0x18003844d  js      short loc_180038484
0x18003844f  mov     rdx, rdi; ppszOut
0x180038452  lea     rcx, [rsp+48h+propvar]; propvar
0x180038457  call    cs:__imp_PropVariantToStringAlloc
0x18003845d  mov     ebx, eax
0x18003845f  test    eax, eax
0x180038461  js      short loc_180038479
0x180038463  mov     rcx, [rdi]; pv
0x180038466  cmp     [rcx], si
0x180038469  jnz     short loc_180038479
0x18003846b  mov     ebx, 80004005h
0x180038470  call    cs:__imp_CoTaskMemFree
0x180038476  mov     [rdi], rsi
0x180038479  lea     rcx, [rsp+48h+propvar]; pvar
0x18003847e  call    cs:__imp_PropVariantClear
0x180038484  mov     rsi, [rsp+48h+arg_8]
0x180038489  mov     eax, ebx
0x18003848b  mov     rbx, [rsp+48h+arg_0]
0x180038490  add     rsp, 40h
0x180038494  pop     rdi
0x180038495  retn
```

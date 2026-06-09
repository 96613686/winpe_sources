# CConflictPropertyStore::s_GetSyncItemID(ISyncMgrConflict *,ushort * *)

- ea: `0x18003849c`
- end: `0x180038526`
- name: `?s_GetSyncItemID@CConflictPropertyStore@@SAJPEAUISyncMgrConflict@@PEAPEAG@Z`
- size: `138`
- prototype: `static int(struct ISyncMgrConflict *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003625c`
- `0x180036e94`

## callees

- `0x18003849c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038500`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038500`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003850e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003850e`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800384e7`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800384e7`

## pseudocode

```c
__int64 __fastcall CConflictPropertyStore::s_GetSyncItemID(struct ISyncMgrConflict *a1, unsigned __int16 **a2)
{
  HRESULT v3; // ebx
  PROPVARIANT propvar[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+30h] [rbp-18h]

  *(_OWORD *)propvar = 0;
  v6 = 0;
  *a2 = 0;
  v3 = ((__int64 (__fastcall *)(struct ISyncMgrConflict *, const PROPERTYKEY *, PROPVARIANT *))a1->lpVtbl->GetProperty)(
         a1,
         &PKEY_Sync_ItemID,
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
0x18003849c  mov     r11, rsp
0x18003849f  mov     [r11+8], rbx
0x1800384a3  mov     [r11+10h], rsi
0x1800384a7  push    rdi
0x1800384a8  sub     rsp, 40h
0x1800384ac  xor     eax, eax
0x1800384ae  lea     r8, [r11-28h]
0x1800384b2  xorps   xmm0, xmm0
0x1800384b5  mov     rdi, rdx
0x1800384b8  movups  xmmword ptr [rsp+48h+propvar], xmm0
0x1800384bd  mov     [r11-18h], rax
0x1800384c1  xor     esi, esi
0x1800384c3  mov     [rdx], rsi
0x1800384c6  lea     rdx, PKEY_Sync_ItemID
0x1800384cd  mov     rax, [rcx]
0x1800384d0  mov     rax, [rax+18h]
0x1800384d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384d9  mov     ebx, eax
0x1800384db  test    eax, eax
0x1800384dd  js      short loc_180038514
0x1800384df  mov     rdx, rdi; ppszOut
0x1800384e2  lea     rcx, [rsp+48h+propvar]; propvar
0x1800384e7  call    cs:__imp_PropVariantToStringAlloc
0x1800384ed  mov     ebx, eax
0x1800384ef  test    eax, eax
0x1800384f1  js      short loc_180038509
0x1800384f3  mov     rcx, [rdi]; pv
0x1800384f6  cmp     [rcx], si
0x1800384f9  jnz     short loc_180038509
0x1800384fb  mov     ebx, 80004005h
0x180038500  call    cs:__imp_CoTaskMemFree
0x180038506  mov     [rdi], rsi
0x180038509  lea     rcx, [rsp+48h+propvar]; pvar
0x18003850e  call    cs:__imp_PropVariantClear
0x180038514  mov     rsi, [rsp+48h+arg_8]
0x180038519  mov     eax, ebx
0x18003851b  mov     rbx, [rsp+48h+arg_0]
0x180038520  add     rsp, 40h
0x180038524  pop     rdi
0x180038525  retn
```

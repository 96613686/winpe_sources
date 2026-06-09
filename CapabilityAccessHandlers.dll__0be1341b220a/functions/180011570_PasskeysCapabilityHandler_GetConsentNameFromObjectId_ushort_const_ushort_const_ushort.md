# PasskeysCapabilityHandler::GetConsentNameFromObjectId(ushort const *,ushort const *,ushort * *)

- ea: `0x180011570`
- end: `0x1800115ed`
- name: `?GetConsentNameFromObjectId@PasskeysCapabilityHandler@@UEAAJPEBG0PEAPEAG@Z`
- size: `125`
- prototype: `__int64 __fastcall(PasskeysCapabilityHandler *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180011450`
- `0x1800114e0`
- `0x180011570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800115d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800115d4`

## pseudocode

```c
__int64 __fastcall PasskeysCapabilityHandler::GetConsentNameFromObjectId(
        PasskeysCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  int ConsentIdFromObjectId; // edi
  LPVOID pv; // [rsp+58h] [rbp+10h] BYREF

  pv = 0;
  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  *a4 = 0;
  ConsentIdFromObjectId = PasskeysCapabilityHandler::GetConsentIdFromObjectId(this, a2, a3, (unsigned __int16 **)&pv);
  if ( ConsentIdFromObjectId >= 0 )
    ConsentIdFromObjectId = PasskeysCapabilityHandler::GetConsentNameFromConsentId(
                              this,
                              a2,
                              (const unsigned __int16 *)pv,
                              a4);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)ConsentIdFromObjectId;
}

```

## disassembly

```asm
0x180011570  push    rbp
0x180011572  push    rsi
0x180011573  push    rdi
0x180011574  push    r14
0x180011576  sub     rsp, 28h
0x18001157a  mov     [rsp+48h+pv], 0
0x180011583  mov     rsi, r9
0x180011586  mov     rbp, rdx
0x180011589  mov     r14, rcx
0x18001158c  test    rdx, rdx
0x18001158f  jz      short loc_1800115DE
0x180011591  test    r8, r8
0x180011594  jz      short loc_1800115DE
0x180011596  test    r9, r9
0x180011599  jz      short loc_1800115DE
0x18001159b  mov     qword ptr [r9], 0
0x1800115a2  lea     r9, [rsp+48h+pv]; unsigned __int16 **
0x1800115a7  call    ?GetConsentIdFromObjectId@PasskeysCapabilityHandler@@UEAAJPEBG0PEAPEAG@Z; PasskeysCapabilityHandler::GetConsentIdFromObjectId(ushort const *,ushort const *,ushort * *)
0x1800115ac  mov     edi, eax
0x1800115ae  test    eax, eax
0x1800115b0  js      short loc_1800115C7
0x1800115b2  mov     r8, [rsp+48h+pv]; unsigned __int16 *
0x1800115b7  mov     r9, rsi; unsigned __int16 **
0x1800115ba  mov     rdx, rbp; unsigned __int16 *
0x1800115bd  mov     rcx, r14; this
0x1800115c0  call    ?GetConsentNameFromConsentId@PasskeysCapabilityHandler@@UEAAJPEBG0PEAPEAG@Z; PasskeysCapabilityHandler::GetConsentNameFromConsentId(ushort const *,ushort const *,ushort * *)
0x1800115c5  mov     edi, eax
0x1800115c7  cmp     [rsp+48h+pv], 0
0x1800115cd  jz      short loc_1800115DA
0x1800115cf  mov     rcx, [rsp+48h+pv]; pv
0x1800115d4  call    cs:__imp_CoTaskMemFree
0x1800115da  mov     eax, edi
0x1800115dc  jmp     short loc_1800115E3
0x1800115de  mov     eax, 80070057h
0x1800115e3  add     rsp, 28h
0x1800115e7  pop     r14
0x1800115e9  pop     rdi
0x1800115ea  pop     rsi
0x1800115eb  pop     rbp
0x1800115ec  retn
```

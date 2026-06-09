# IsWABSavedCredential(_VAULT_ITEM *)

- ea: `0x18001cf28`
- end: `0x18001cf54`
- name: `?IsWABSavedCredential@@YAEPEAU_VAULT_ITEM@@@Z`
- size: `44`
- prototype: `unsigned __int8 __fastcall(_VAULT_ITEM *pItem)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001c2f4`
- `0x18001c980`

## callees

- `0x18001cf28`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x18001cf40`
- `ntdll!RtlEqualSid` at `0x18001cf40`

## pseudocode

```c
bool __fastcall IsWABSavedCredential(_VAULT_ITEM *pItem)
{
  _VAULT_ITEM_ELEMENT *pPackageSid; // rcx

  pPackageSid = pItem->pPackageSid;
  return pPackageSid && RtlEqualSid(pPackageSid->ItemValue.String, &gWABPackageSidBuffer) != 0;
}

```

## disassembly

```asm
0x18001cf28  sub     rsp, 28h
0x18001cf2c  mov     pItem, [pItem+30h]
0x18001cf30  test    pItem, pItem
0x18001cf33  jz      short loc_18001CF4D
0x18001cf35  mov     pItem, [pItem+10h]; Sid1
0x18001cf39  lea     rdx, ?gWABPackageSidBuffer@@3U_SID_BUFFER@@A; Sid2
0x18001cf40  call    cs:__imp_RtlEqualSid
0x18001cf46  test    al, al
0x18001cf48  setnz   al
0x18001cf4b  jmp     short loc_18001CF4F
0x18001cf4d  xor     al, al
0x18001cf4f  add     rsp, 28h
0x18001cf53  retn
```

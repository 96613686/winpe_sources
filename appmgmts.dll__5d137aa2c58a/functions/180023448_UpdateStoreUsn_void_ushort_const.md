# UpdateStoreUsn(void *,ushort const *)

- ea: `0x180023448`
- end: `0x1800234aa`
- name: `?UpdateStoreUsn@@YAJPEAXPEBG@Z`
- size: `98`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001f0b0`
- `0x18001f570`
- `0x18001fa10`
- `0x1800205f4`
- `0x1800208c4`
- `0x180022e00`
- `0x180023050`

## callees

- `0x18002435c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002349c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002349c`
- `adsldpc!ADSISetObjectAttributes` at `0x18002348f`
- `adsldpc!ADSISetObjectAttributes` at `0x18002348f`

## string_xrefs

- `0x18002346c`: `lastUpdateSequence`

## pseudocode

```c
__int64 __fastcall UpdateStoreUsn(void *a1, unsigned __int16 *a2)
{
  struct _ads_attr_info v4; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 *v6; // [rsp+60h] [rbp+18h] BYREF

  v6 = a2;
  v5 = 0;
  PackStrArrToAttr(&v4, (WCHAR *)L"lastUpdateSequence", &v6, a2 != 0);
  LODWORD(a1) = ADSISetObjectAttributes(a1, &v4, 1, &v5);
  LocalFree(v4.pADsValues);
  return (unsigned int)a1;
}

```

## disassembly

```asm
0x180023448  mov     rax, rsp
0x18002344b  push    rbx
0x18002344c  sub     rsp, 40h
0x180023450  xor     r9d, r9d
0x180023453  mov     [rax+18h], rdx
0x180023457  test    rdx, rdx
0x18002345a  mov     dword ptr [rax+10h], 0
0x180023461  mov     rbx, rcx
0x180023464  lea     r8, [rax+18h]; unsigned __int16 **
0x180023468  setnz   r9b; unsigned int
0x18002346c  lea     rdx, aLastupdatesequ; "lastUpdateSequence"
0x180023473  lea     rcx, [rax-28h]; struct _ads_attr_info *
0x180023477  call    ?PackStrArrToAttr@@YAXPEAU_ads_attr_info@@PEBGPEAPEAGK@Z; PackStrArrToAttr(_ads_attr_info *,ushort const *,ushort * *,ulong)
0x18002347c  lea     r9, [rsp+48h+arg_8]
0x180023481  mov     r8d, 1
0x180023487  lea     rdx, [rsp+48h+var_28]
0x18002348c  mov     rcx, rbx
0x18002348f  call    cs:__imp_ADSISetObjectAttributes
0x180023495  mov     rcx, [rsp+48h+hMem]; hMem
0x18002349a  mov     ebx, eax
0x18002349c  call    cs:__imp_LocalFree
0x1800234a2  mov     eax, ebx
0x1800234a4  add     rsp, 40h
0x1800234a8  pop     rbx
0x1800234a9  retn
```

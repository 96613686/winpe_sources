# CStringHashTable<JET_COLUMNDEF,CEcsColumnNameHashPolicy,CStringCompare>::AddItem(ushort const * const &,JET_COLUMNDEF const &)

- ea: `0x1800df6d8`
- end: `0x1800df73f`
- name: `?AddItem@?$CStringHashTable@UJET_COLUMNDEF@@VCEcsColumnNameHashPolicy@@VCStringCompare@@@@QEAAJAEBQEBGAEBUJET_COLUMNDEF@@@Z`
- size: `103`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800e047c`
- `0x1800e6a50`
- `0x1800e7b64`
- `0x1800eccb0`
- `0x1800ed570`
- `0x1800eed90`

## callees

- `0x1800df6d8`
- `0x1800e11f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df727`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800df727`
- `SHLWAPI!SHStrDupW` at `0x1800df700`
- `SHLWAPI!SHStrDupW` at `0x1800df700`

## pseudocode

```c
__int64 __fastcall CStringHashTable<JET_COLUMNDEF,CEcsColumnNameHashPolicy,CStringCompare>::AddItem(
        __int64 a1,
        LPCWSTR *a2,
        __int64 a3)
{
  __int64 v5; // rdx
  HRESULT updated; // ebx
  LPVOID pv; // [rsp+58h] [rbp+20h] BYREF

  pv = 0;
  updated = SHStrDupW(*a2, (LPWSTR *)&pv);
  if ( updated >= 0 )
  {
    updated = CSimpleHashTable<unsigned short const *,JET_COLUMNDEF,CEcsColumnNameHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(
                a1,
                v5,
                &pv,
                a3);
    if ( updated < 0 )
      CoTaskMemFree(pv);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800df6d8  mov     r11, rsp
0x1800df6db  mov     [r11+8], rbx
0x1800df6df  mov     [r11+10h], rsi
0x1800df6e3  push    rdi
0x1800df6e4  sub     rsp, 30h
0x1800df6e8  mov     rax, rdx
0x1800df6eb  mov     qword ptr [r11+20h], 0
0x1800df6f3  mov     rsi, rcx
0x1800df6f6  lea     rdx, [r11+20h]; ppwsz
0x1800df6fa  mov     rdi, r8
0x1800df6fd  mov     rcx, [rax]; psz
0x1800df700  call    cs:__imp_SHStrDupW
0x1800df706  mov     ebx, eax
0x1800df708  test    eax, eax
0x1800df70a  js      short loc_1800DF72D
0x1800df70c  mov     r9, rdi
0x1800df70f  lea     r8, [rsp+38h+pv]
0x1800df714  mov     rcx, rsi
0x1800df717  call    ?_AddUpdateItem@?$CSimpleHashTable@PEBGUJET_COLUMNDEF@@VCEcsColumnNameHashPolicy@@VCStringCompare@@VCDefaultResizePolicy@@VCDefaultRehashPolicy@@@@AEAAJHAEBQEBGAEBUJET_COLUMNDEF@@PEAU2@@Z; CSimpleHashTable<ushort const *,JET_COLUMNDEF,CEcsColumnNameHashPolicy,CStringCompare,CDefaultResizePolicy,CDefaultRehashPolicy>::_AddUpdateItem(int,ushort const * const &,JET_COLUMNDEF const &,JET_COLUMNDEF *)
0x1800df71c  mov     ebx, eax
0x1800df71e  test    eax, eax
0x1800df720  jns     short loc_1800DF72D
0x1800df722  mov     rcx, [rsp+38h+pv]; pv
0x1800df727  call    cs:__imp_CoTaskMemFree
0x1800df72d  mov     rsi, [rsp+38h+arg_8]
0x1800df732  mov     eax, ebx
0x1800df734  mov     rbx, [rsp+38h+arg_0]
0x1800df739  add     rsp, 30h
0x1800df73d  pop     rdi
0x1800df73e  retn
```

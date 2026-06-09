# _MapsStoreManager::IsMapFullyInstalled_::_1_::catch$0

- ea: `0x18008e099`
- end: `0x18008e0d8`
- name: `_MapsStoreManager::IsMapFullyInstalled_::_1_::catch$0`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001ab70`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x18008e0be`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18008e0be`

## string_xrefs

- `0x18008e0b5`: `MapsStoreManager::IsMapFullyInstalled`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::IsMapFullyInstalled_::_1_::catch_0(wil *a1, __int64 a2)
{
  int v3; // eax

  v3 = wil::ResultFromCaughtException(a1);
  *(_DWORD *)(a2 + 64) = ZTraceReportOrigination(
                           v3,
                           "MapsStoreManager::IsMapFullyInstalled",
                           567,
                           *(const void **)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x18008e099  mov     [rsp+arg_8], rdx
0x18008e09e  push    rbp
0x18008e09f  sub     rsp, 20h
0x18008e0a3  mov     rbp, rdx
0x18008e0a6  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18008e0ab  mov     r9, [rbp+30h]
0x18008e0af  mov     r8d, 237h
0x18008e0b5  lea     rdx, aMapsstoremanag_7; "MapsStoreManager::IsMapFullyInstalled"
0x18008e0bc  mov     ecx, eax
0x18008e0be  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18008e0c4  mov     [rbp+40h], eax
0x18008e0c7  mov     rax, 0
0x18008e0d1  add     rsp, 20h
0x18008e0d5  pop     rbp
0x18008e0d6  retn
```

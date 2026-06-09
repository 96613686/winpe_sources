# _MapsStoreManager::CheckUpdateAsync_::_1_::catch$0

- ea: `0x18008dc61`
- end: `0x18008dca0`
- name: `_MapsStoreManager::CheckUpdateAsync_::_1_::catch$0`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001ab70`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x18008dc86`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18008dc86`

## string_xrefs

- `0x18008dc7d`: `MapsStoreManager::CheckUpdateAsync`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::CheckUpdateAsync_::_1_::catch_0(wil *a1, __int64 a2)
{
  int v3; // eax

  v3 = wil::ResultFromCaughtException(a1);
  *(_DWORD *)(a2 + 56) = ZTraceReportOrigination(
                           v3,
                           "MapsStoreManager::CheckUpdateAsync",
                           545,
                           *(const void **)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x18008dc61  mov     [rsp+arg_8], rdx
0x18008dc66  push    rbp
0x18008dc67  sub     rsp, 20h
0x18008dc6b  mov     rbp, rdx
0x18008dc6e  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18008dc73  mov     r9, [rbp+30h]
0x18008dc77  mov     r8d, 221h
0x18008dc7d  lea     rdx, aMapsstoremanag_12; "MapsStoreManager::CheckUpdateAsync"
0x18008dc84  mov     ecx, eax
0x18008dc86  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18008dc8c  mov     [rbp+38h], eax
0x18008dc8f  mov     rax, 0
0x18008dc99  add     rsp, 20h
0x18008dc9d  pop     rbp
0x18008dc9e  retn
```

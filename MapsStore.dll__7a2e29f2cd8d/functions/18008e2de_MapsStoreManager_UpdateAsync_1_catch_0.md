# _MapsStoreManager::UpdateAsync_::_1_::catch$0

- ea: `0x18008e2de`
- end: `0x18008e31d`
- name: `_MapsStoreManager::UpdateAsync_::_1_::catch$0`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001ab70`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x18008e303`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18008e303`

## string_xrefs

- `0x18008e2fa`: `MapsStoreManager::UpdateAsync`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::UpdateAsync_::_1_::catch_0(wil *a1, __int64 a2)
{
  int v3; // eax

  v3 = wil::ResultFromCaughtException(a1);
  *(_DWORD *)(a2 + 56) = ZTraceReportOrigination(v3, "MapsStoreManager::UpdateAsync", 524, *(const void **)(a2 + 48));
  return 0;
}

```

## disassembly

```asm
0x18008e2de  mov     [rsp+arg_8], rdx
0x18008e2e3  push    rbp
0x18008e2e4  sub     rsp, 20h
0x18008e2e8  mov     rbp, rdx
0x18008e2eb  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18008e2f0  mov     r9, [rbp+30h]
0x18008e2f4  mov     r8d, 20Ch
0x18008e2fa  lea     rdx, aMapsstoremanag_5; "MapsStoreManager::UpdateAsync"
0x18008e301  mov     ecx, eax
0x18008e303  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18008e309  mov     [rbp+38h], eax
0x18008e30c  mov     rax, 0
0x18008e316  add     rsp, 20h
0x18008e31a  pop     rbp
0x18008e31b  retn
```

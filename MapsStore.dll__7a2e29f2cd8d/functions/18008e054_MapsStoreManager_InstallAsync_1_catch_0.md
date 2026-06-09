# _MapsStoreManager::InstallAsync_::_1_::catch$0

- ea: `0x18008e054`
- end: `0x18008e093`
- name: `_MapsStoreManager::InstallAsync_::_1_::catch$0`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18001ab70`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOrigination` at `0x18008e079`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18008e079`

## string_xrefs

- `0x18008e070`: `MapsStoreManager::InstallAsync`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::InstallAsync_::_1_::catch_0(wil *a1, __int64 a2)
{
  int v3; // eax

  v3 = wil::ResultFromCaughtException(a1);
  *(_DWORD *)(a2 + 32) = ZTraceReportOrigination(v3, "MapsStoreManager::InstallAsync", 499, *(const void **)(a2 + 112));
  return 0;
}

```

## disassembly

```asm
0x18008e054  mov     [rsp+arg_8], rdx
0x18008e059  push    rbp
0x18008e05a  sub     rsp, 20h
0x18008e05e  mov     rbp, rdx
0x18008e061  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18008e066  mov     r9, [rbp+70h]
0x18008e06a  mov     r8d, 1F3h
0x18008e070  lea     rdx, aMapsstoremanag_13; "MapsStoreManager::InstallAsync"
0x18008e077  mov     ecx, eax
0x18008e079  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18008e07f  mov     [rbp+20h], eax
0x18008e082  mov     rax, 0
0x18008e08c  add     rsp, 20h
0x18008e090  pop     rbp
0x18008e091  retn
```

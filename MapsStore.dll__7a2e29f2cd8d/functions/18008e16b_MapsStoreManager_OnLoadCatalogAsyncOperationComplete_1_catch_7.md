# _MapsStoreManager::OnLoadCatalogAsyncOperationComplete_::_1_::catch$7

- ea: `0x18008e16b`
- end: `0x18008e1cc`
- name: `_MapsStoreManager::OnLoadCatalogAsyncOperationComplete_::_1_::catch$7`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800185b0`
- `0x18001ab70`
- `0x18008e16b`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x18008e19e`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18008e19e`

## string_xrefs

- `0x18008e195`: `MapsStoreManager::OnLoadCatalogAsyncOperationComplete`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::OnLoadCatalogAsyncOperationComplete_::_1_::catch_7(wil *a1, __int64 a2)
{
  int v3; // eax
  int v4; // edi
  MapsStoreManager *v5; // rbx

  v3 = wil::ResultFromCaughtException(a1);
  v4 = v3;
  v5 = *(MapsStoreManager **)(a2 + 144);
  if ( v3 < 0 )
    ZTraceReportIgnore(v3, "MapsStoreManager::OnLoadCatalogAsyncOperationComplete", 724, *(const void **)(a2 + 144));
  if ( *((_QWORD *)v5 + 48) )
    MapsStoreManager::CompleteStoreOperation(v5, v4);
  return 0;
}

```

## disassembly

```asm
0x18008e16b  mov     [rsp+arg_8], rdx
0x18008e170  push    rbx
0x18008e171  push    rbp
0x18008e172  push    rdi
0x18008e173  sub     rsp, 30h
0x18008e177  mov     rbp, rdx
0x18008e17a  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18008e17f  mov     edi, eax
0x18008e181  mov     rbx, [rbp+90h]
0x18008e188  test    eax, eax
0x18008e18a  jns     short loc_18008E1A4
0x18008e18c  mov     r9, rbx
0x18008e18f  mov     r8d, 2D4h
0x18008e195  lea     rdx, aMapsstoremanag_2; "MapsStoreManager::OnLoadCatalogAsyncOpe"...
0x18008e19c  mov     ecx, eax
0x18008e19e  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18008e1a4  cmp     qword ptr [rbx+180h], 0
0x18008e1ac  jz      short loc_18008E1B9
0x18008e1ae  mov     edx, edi; int
0x18008e1b0  mov     rcx, rbx; this
0x18008e1b3  call    ?CompleteStoreOperation@MapsStoreManager@@AEAAXJ@Z; MapsStoreManager::CompleteStoreOperation(long)
0x18008e1b8  nop
0x18008e1b9  mov     rax, 0
0x18008e1c3  add     rsp, 30h
0x18008e1c7  pop     rdi
0x18008e1c8  pop     rbp
0x18008e1c9  pop     rbx
0x18008e1ca  retn
```

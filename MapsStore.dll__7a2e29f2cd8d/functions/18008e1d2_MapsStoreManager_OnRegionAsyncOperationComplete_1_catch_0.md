# _MapsStoreManager::OnRegionAsyncOperationComplete_::_1_::catch$0

- ea: `0x18008e1d2`
- end: `0x18008e230`
- name: `_MapsStoreManager::OnRegionAsyncOperationComplete_::_1_::catch$0`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800185b0`
- `0x18001ab70`
- `0x18008e1d2`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x18008e202`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18008e202`

## string_xrefs

- `0x18008e1f9`: `MapsStoreManager::OnRegionAsyncOperationComplete`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::OnRegionAsyncOperationComplete_::_1_::catch_0(wil *a1, __int64 a2)
{
  int v3; // eax
  int v4; // edi
  MapsStoreManager *v5; // rbx

  v3 = wil::ResultFromCaughtException(a1);
  v4 = v3;
  v5 = *(MapsStoreManager **)(a2 + 48);
  if ( v3 < 0 )
    ZTraceReportIgnore(v3, "MapsStoreManager::OnRegionAsyncOperationComplete", 755, *(const void **)(a2 + 48));
  if ( *((_QWORD *)v5 + 50) )
    MapsStoreManager::CompleteStoreOperation(v5, v4);
  return 0;
}

```

## disassembly

```asm
0x18008e1d2  mov     [rsp+arg_8], rdx
0x18008e1d7  push    rbx
0x18008e1d8  push    rbp
0x18008e1d9  push    rdi
0x18008e1da  sub     rsp, 20h
0x18008e1de  mov     rbp, rdx
0x18008e1e1  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18008e1e6  mov     edi, eax
0x18008e1e8  mov     rbx, [rbp+30h]
0x18008e1ec  test    eax, eax
0x18008e1ee  jns     short loc_18008E208
0x18008e1f0  mov     r9, rbx
0x18008e1f3  mov     r8d, 2F3h
0x18008e1f9  lea     rdx, aMapsstoremanag_9; "MapsStoreManager::OnRegionAsyncOperatio"...
0x18008e200  mov     ecx, eax
0x18008e202  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18008e208  cmp     qword ptr [rbx+190h], 0
0x18008e210  jz      short loc_18008E21D
0x18008e212  mov     edx, edi; int
0x18008e214  mov     rcx, rbx; this
0x18008e217  call    ?CompleteStoreOperation@MapsStoreManager@@AEAAXJ@Z; MapsStoreManager::CompleteStoreOperation(long)
0x18008e21c  nop
0x18008e21d  mov     rax, 0
0x18008e227  add     rsp, 20h
0x18008e22b  pop     rdi
0x18008e22c  pop     rbp
0x18008e22d  pop     rbx
0x18008e22e  retn
```

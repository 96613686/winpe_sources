# _MapsStoreManager::OnUpdateCheckAsyncOperationComplete_::_1_::catch$0

- ea: `0x18008e236`
- end: `0x18008e294`
- name: `_MapsStoreManager::OnUpdateCheckAsyncOperationComplete_::_1_::catch$0`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800185b0`
- `0x18001ab70`
- `0x18008e236`

## import_xrefs

- `ZTrace_Maps!ZTraceReportIgnore` at `0x18008e266`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18008e266`

## string_xrefs

- `0x18008e25d`: `MapsStoreManager::OnUpdateCheckAsyncOperationComplete`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::OnUpdateCheckAsyncOperationComplete_::_1_::catch_0(wil *a1, __int64 a2)
{
  int v3; // eax
  int v4; // edi
  MapsStoreManager *v5; // rbx

  v3 = wil::ResultFromCaughtException(a1);
  v4 = v3;
  v5 = *(MapsStoreManager **)(a2 + 48);
  if ( v3 < 0 )
    ZTraceReportIgnore(v3, "MapsStoreManager::OnUpdateCheckAsyncOperationComplete", 786, *(const void **)(a2 + 48));
  if ( *((_QWORD *)v5 + 52) )
    MapsStoreManager::CompleteStoreOperation(v5, v4);
  return 0;
}

```

## disassembly

```asm
0x18008e236  mov     [rsp+arg_8], rdx
0x18008e23b  push    rbx
0x18008e23c  push    rbp
0x18008e23d  push    rdi
0x18008e23e  sub     rsp, 20h
0x18008e242  mov     rbp, rdx
0x18008e245  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18008e24a  mov     edi, eax
0x18008e24c  mov     rbx, [rbp+30h]
0x18008e250  test    eax, eax
0x18008e252  jns     short loc_18008E26C
0x18008e254  mov     r9, rbx
0x18008e257  mov     r8d, 312h
0x18008e25d  lea     rdx, aMapsstoremanag_6; "MapsStoreManager::OnUpdateCheckAsyncOpe"...
0x18008e264  mov     ecx, eax
0x18008e266  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18008e26c  cmp     qword ptr [rbx+1A0h], 0
0x18008e274  jz      short loc_18008E281
0x18008e276  mov     edx, edi; int
0x18008e278  mov     rcx, rbx; this
0x18008e27b  call    ?CompleteStoreOperation@MapsStoreManager@@AEAAXJ@Z; MapsStoreManager::CompleteStoreOperation(long)
0x18008e280  nop
0x18008e281  mov     rax, 0
0x18008e28b  add     rsp, 20h
0x18008e28f  pop     rdi
0x18008e290  pop     rbp
0x18008e291  pop     rbx
0x18008e292  retn
```

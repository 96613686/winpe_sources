# POOMIndexing::UnifiedStoreAggregateDataSource::PreWork(void)

- ea: `0x18001b4f0`
- end: `0x18001b5a3`
- name: `?PreWork@UnifiedStoreAggregateDataSource@POOMIndexing@@UEAAJXZ`
- size: `179`
- prototype: `__int64 __fastcall(POOMIndexing::UnifiedStoreAggregateDataSource *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800067c0`
- `0x18000c5b8`
- `0x18001b4f0`

## import_xrefs

- `PIMSTORE!GetAggregateCache` at `0x18001b53c`
- `PIMSTORE!GetAggregateCache` at `0x18001b53c`

## pseudocode

```c
__int64 __fastcall POOMIndexing::UnifiedStoreAggregateDataSource::PreWork(
        POOMIndexing::UnifiedStoreAggregateDataSource *this)
{
  void *v2; // rax
  void *v3; // rax
  __int64 v4; // r9
  int *p_AggregateCache; // r8
  int AggregateCache; // [rsp+40h] [rbp+8h] BYREF

  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
  {
    v2 = _t_address();
    EtwTraceMessage(&ETWMESSAGE, v2, 0, -1, 0, -1);
  }
  AggregateCache = GetAggregateCache(0, *((_QWORD *)this + 5));
  if ( AggregateCache >= 0 )
  {
    if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
    {
      v3 = _t_address();
      p_AggregateCache = 0;
      v4 = -1;
      goto LABEL_8;
    }
  }
  else if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 4) != 0 )
  {
    v3 = _t_address();
    v4 = 4;
    p_AggregateCache = &AggregateCache;
LABEL_8:
    EtwTraceMessage(&ETWMESSAGE, v3, p_AggregateCache, v4, 0, -1);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b4f0  mov     [rsp+arg_8], rbx
0x18001b4f5  push    rsi
0x18001b4f6  sub     rsp, 30h
0x18001b4fa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001b4fe  mov     rbx, rcx
0x18001b501  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18001b508  jz      short loc_18001B532
0x18001b50a  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18001b50f  mov     rdx, rax; void *
0x18001b512  mov     [rsp+38h+var_10], rsi
0x18001b517  mov     r9, rsi
0x18001b51a  mov     [rsp+38h+var_18], 0
0x18001b523  xor     r8d, r8d
0x18001b526  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18001b52d  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18001b532  mov     rdx, [rbx+28h]
0x18001b536  lea     r8, [rbx+30h]
0x18001b53a  xor     ecx, ecx
0x18001b53c  call    cs:__imp_GetAggregateCache
0x18001b542  mov     [rsp+38h+arg_0], eax
0x18001b546  test    eax, eax
0x18001b548  jns     short loc_18001B565
0x18001b54a  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18001b551  jz      short loc_18001B596
0x18001b553  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18001b558  mov     r9d, 4
0x18001b55e  lea     r8, [rsp+38h+arg_0]
0x18001b563  jmp     short loc_18001B579
0x18001b565  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 4
0x18001b56c  jz      short loc_18001B596
0x18001b56e  call    ?_t_address@@YAPEAXXZ; _t_address(void)
0x18001b573  xor     r8d, r8d
0x18001b576  mov     r9, rsi
0x18001b579  mov     [rsp+38h+var_10], rsi
0x18001b57e  lea     rcx, _ETWMESSAGE; EventDescriptor
0x18001b585  mov     rdx, rax; void *
0x18001b588  mov     [rsp+38h+var_18], 0
0x18001b591  call    ?EtwTraceMessage@@YAXPEBU_EVENT_DESCRIPTOR@@PEAXZZ; EtwTraceMessage(_EVENT_DESCRIPTOR const *,void *,...)
0x18001b596  mov     rbx, [rsp+38h+arg_8]
0x18001b59b  xor     eax, eax
0x18001b59d  add     rsp, 30h
0x18001b5a1  pop     rsi
0x18001b5a2  retn
```

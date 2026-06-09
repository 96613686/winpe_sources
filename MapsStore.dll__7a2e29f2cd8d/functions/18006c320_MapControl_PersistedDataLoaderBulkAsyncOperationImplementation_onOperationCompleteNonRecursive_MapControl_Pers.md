# MapControl::PersistedDataLoaderBulkAsyncOperationImplementation::onOperationCompleteNonRecursive(MapControl::PersistedDataLoaderAsyncOperation const &)

- ea: `0x18006c320`
- end: `0x18006c42c`
- name: `?onOperationCompleteNonRecursive@PersistedDataLoaderBulkAsyncOperationImplementation@MapControl@@AEAAXAEBVPersistedDataLoaderAsyncOperation@2@@Z`
- size: `268`
- prototype: `void __fastcall(MapControl::PersistedDataLoaderBulkAsyncOperationImplementation *__hidden this, const struct MapControl::PersistedDataLoaderAsyncOperation *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18006c2f0`

## callees

- `0x18000d090`
- `0x180016cbc`
- `0x180017cf4`
- `0x18002e4a0`
- `0x18002f420`
- `0x18003b20c`
- `0x18006c07c`
- `0x18006c1c0`
- `0x18006c320`
- `0x180074b28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c3af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c3af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c3e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c3e4`

## string_xrefs

- `0x18006c371`: `Failed to delete chunk`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall MapControl::PersistedDataLoaderBulkAsyncOperationImplementation::onOperationCompleteNonRecursive(
        MapControl::PersistedDataLoaderBulkAsyncOperationImplementation *this,
        const struct MapControl::PersistedDataLoaderAsyncOperation *a2)
{
  _BYTE *v3; // rdi
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  _BYTE v5[56]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v6; // [rsp+68h] [rbp-20h]

  v3 = (char *)a2 + 150;
  if ( *((_DWORD *)this + 66) != 2 || *v3 )
  {
    v6 = 0;
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 344);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 344));
    --*((_DWORD *)this + 120);
    ++*((_QWORD *)this + 74);
    if ( !*v3 )
      _InterlockedIncrement((volatile signed __int32 *)this + 150);
    std::function<void (Pal::AsyncOperation<MapControl::BulkChunkIdResult> &)>::operator=(v5, (char *)this + 608);
    LeaveCriticalSection(v4);
    if ( v6 )
      std::_Func_class<void,>::operator()(v5, this);
    std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<unsigned char> const>> &>::_Tidy(v5);
  }
  else
  {
    MapControl::PersistedDataLoaderBulkAsyncOperationImplementation::cancelOperations(this);
    Pal::UntypedAsyncOperationCancelList::cancelAll((LPCRITICAL_SECTION)((char *)this + 488));
    Utility::MaybeConstStringImpl<char>::operator=((char *)this + 184, "Failed to delete chunk");
    MapControl::TracedUntypedAsyncOperation::endTrace(this, 0);
    Pal::UntypedAsyncOperation::setFailed(this, 8388610);
  }
}

```

## disassembly

```asm
0x18006c320  mov     [rsp+arg_8], rbx
0x18006c325  mov     [rsp+arg_10], rsi
0x18006c32a  push    rdi
0x18006c32b  sub     rsp, 80h
0x18006c332  mov     rax, cs:__security_cookie
0x18006c339  xor     rax, rsp
0x18006c33c  mov     [rsp+88h+var_18], rax
0x18006c341  mov     rbx, rcx
0x18006c344  lea     rdi, [rdx+96h]
0x18006c34b  cmp     dword ptr [rcx+108h], 2
0x18006c352  jnz     short loc_18006C397
0x18006c354  cmp     byte ptr [rdi], 0
0x18006c357  jnz     short loc_18006C397
0x18006c359  call    ?cancelOperations@PersistedDataLoaderBulkAsyncOperationImplementation@MapControl@@AEAAXXZ; MapControl::PersistedDataLoaderBulkAsyncOperationImplementation::cancelOperations(void)
0x18006c35e  lea     rcx, [rbx+1E8h]; lpCriticalSection
0x18006c365  call    ?cancelAll@UntypedAsyncOperationCancelList@Pal@@QEAAXXZ; Pal::UntypedAsyncOperationCancelList::cancelAll(void)
0x18006c36a  lea     rcx, [rbx+0B8h]
0x18006c371  lea     rdx, aFailedToDelete; "Failed to delete chunk"
0x18006c378  call    ??4?$MaybeConstStringImpl@D@Utility@@QEAAAEAV01@PEBD@Z; Utility::MaybeConstStringImpl<char>::operator=(char const *)
0x18006c37d  xor     edx, edx; bool
0x18006c37f  mov     rcx, rbx; this
0x18006c382  call    ?endTrace@TracedUntypedAsyncOperation@MapControl@@AEAAX_N@Z; MapControl::TracedUntypedAsyncOperation::endTrace(bool)
0x18006c387  mov     edx, cs:dword_1800A4920
0x18006c38d  mov     rcx, rbx
0x18006c390  call    ?setFailed@UntypedAsyncOperation@Pal@@IEAA_NVStatusCode@Core@@@Z; Pal::UntypedAsyncOperation::setFailed(Core::StatusCode)
0x18006c395  jmp     short loc_18006C40A
0x18006c397  mov     [rsp+88h+var_20], 0
0x18006c3a0  lea     rsi, [rcx+158h]
0x18006c3a7  mov     [rsp+88h+var_68], rsi
0x18006c3ac  mov     rcx, rsi; lpCriticalSection
0x18006c3af  call    cs:__imp_EnterCriticalSection
0x18006c3b5  nop
0x18006c3b6  dec     dword ptr [rbx+1E0h]
0x18006c3bc  inc     qword ptr [rbx+250h]
0x18006c3c3  cmp     byte ptr [rdi], 0
0x18006c3c6  jnz     short loc_18006C3CF
0x18006c3c8  lock inc dword ptr [rbx+258h]
0x18006c3cf  lea     rdx, [rbx+260h]
0x18006c3d6  lea     rcx, [rsp+88h+var_58]
0x18006c3db  call    ??4?$function@$$A6AXAEAV?$AsyncOperation@UBulkChunkIdResult@MapControl@@@Pal@@@Z@std@@QEAAAEAV01@AEBV01@@Z; std::function<void (Pal::AsyncOperation<MapControl::BulkChunkIdResult> &)>::operator=(std::function<void (Pal::AsyncOperation<MapControl::BulkChunkIdResult> &)> const &)
0x18006c3e0  nop
0x18006c3e1  mov     rcx, rsi; lpCriticalSection
0x18006c3e4  call    cs:__imp_LeaveCriticalSection
0x18006c3ea  cmp     [rsp+88h+var_20], 0
0x18006c3f0  jz      short loc_18006C400
0x18006c3f2  mov     rdx, rbx
0x18006c3f5  lea     rcx, [rsp+88h+var_58]
0x18006c3fa  call    ??R?$_Func_class@X$$V@std@@QEBAXXZ; std::_Func_class<void,>::operator()(void)
0x18006c3ff  nop
0x18006c400  lea     rcx, [rsp+88h+var_58]
0x18006c405  call    ?_Tidy@?$_Func_class@XAEAV?$AsyncOperation@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Pal@@@std@@IEAAXXZ; std::_Func_class<void,Pal::AsyncOperation<std::shared_ptr<std::vector<uchar> const>> &>::_Tidy(void)
0x18006c40a  mov     rcx, [rsp+88h+var_18]
0x18006c40f  xor     rcx, rsp; StackCookie
0x18006c412  call    __security_check_cookie
0x18006c417  lea     r11, [rsp+88h+var_8]
0x18006c41f  mov     rbx, [r11+18h]
0x18006c423  mov     rsi, [r11+20h]
0x18006c427  mov     rsp, r11
0x18006c42a  pop     rdi
0x18006c42b  retn
```

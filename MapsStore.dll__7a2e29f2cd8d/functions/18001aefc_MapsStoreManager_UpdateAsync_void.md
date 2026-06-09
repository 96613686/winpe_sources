# MapsStoreManager::UpdateAsync(void)

- ea: `0x18001aefc`
- end: `0x18001af78`
- name: `?UpdateAsync@MapsStoreManager@@QEAAJXZ`
- size: `124`
- prototype: `__int64 __fastcall(MapsStoreManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180011b20`

## callees

- `0x1800182cc`
- `0x1800188dc`
- `0x18001abe8`
- `0x18001aefc`
- `0x1800363cc`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001af63`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001af63`

## string_xrefs

- `0x18001af5a`: `MapsStoreManager::UpdateAsync`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::UpdateAsync(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // eax
  int v3; // r8d
  unsigned int v4; // edi
  wil *v5; // rcx
  int v7; // eax

  v2 = MapsStoreManager::EnsureReadyForOperation(this);
  if ( v2 < 0 )
  {
    v3 = 510;
    return (unsigned int)ZTraceReportPropagation(v2, "MapsStoreManager::UpdateAsync", v3, this);
  }
  v2 = Pal::MapsbtsvcProxy::ensureJob((__int64)&Pal::MapsbtsvcProxy::smInstance, (__int64)&this[1].LockCount);
  if ( v2 < 0 )
  {
    v3 = 512;
    return (unsigned int)ZTraceReportPropagation(v2, "MapsStoreManager::UpdateAsync", v3, this);
  }
  v4 = 0;
  try
  {
    MapsStoreManager::CancelGridRequestsAndWait((MapsStoreManager *)this);
    MapsStoreManager::StartNonInstallOperation(this, 3);
  }
  catch ( ... )
  {
    v7 = wil::ResultFromCaughtException(v5);
    return (unsigned int)ZTraceReportOrigination(v7, "MapsStoreManager::UpdateAsync", 524, this);
  }
  return v4;
}

```

## disassembly

```asm
0x18001aefc  mov     [rsp+arg_10], rbx
0x18001af01  mov     [rsp+arg_0], rcx
0x18001af06  push    rdi
0x18001af07  sub     rsp, 20h
0x18001af0b  mov     rbx, rcx
0x18001af0e  call    ?EnsureReadyForOperation@MapsStoreManager@@AEAAJXZ; MapsStoreManager::EnsureReadyForOperation(void)
0x18001af13  test    eax, eax
0x18001af15  jns     short loc_18001AF1F
0x18001af17  mov     r8d, 1FEh
0x18001af1d  jmp     short loc_18001AF57
0x18001af1f  lea     rdx, [rbx+30h]
0x18001af23  lea     rcx, ?smInstance@MapsbtsvcProxy@Pal@@0V12@A; Pal::MapsbtsvcProxy Pal::MapsbtsvcProxy::smInstance
0x18001af2a  call    ?ensureJob@MapsbtsvcProxy@Pal@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::MapsbtsvcProxy::ensureJob(std::wstring const &)
0x18001af2f  test    eax, eax
0x18001af31  js      short loc_18001AF51
0x18001af33  xor     edi, edi
0x18001af35  mov     rcx, rbx; this
0x18001af38  call    ?CancelGridRequestsAndWait@MapsStoreManager@@AEAAXXZ; MapsStoreManager::CancelGridRequestsAndWait(void)
0x18001af3d  lea     edx, [rdi+3]
0x18001af40  mov     rcx, rbx
0x18001af43  call    ?StartNonInstallOperation@MapsStoreManager@@AEAAXW4OperationType@1@@Z; MapsStoreManager::StartNonInstallOperation(MapsStoreManager::OperationType)
0x18001af48  nop
0x18001af49  jmp     short loc_18001AF6B
0x18001af4b  mov     edi, [rsp+28h+arg_8]
0x18001af4f  jmp     short loc_18001AF6B
0x18001af51  mov     r8d, 200h
0x18001af57  mov     r9, rbx
0x18001af5a  lea     rdx, aMapsstoremanag_5; "MapsStoreManager::UpdateAsync"
0x18001af61  mov     ecx, eax
0x18001af63  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001af69  mov     edi, eax
0x18001af6b  mov     eax, edi
0x18001af6d  mov     rbx, [rsp+28h+arg_10]
0x18001af72  add     rsp, 20h
0x18001af76  pop     rdi
0x18001af77  retn
```

# MapsStoreManager::CheckUpdateAsync(void)

- ea: `0x180018534`
- end: `0x1800185a8`
- name: `?CheckUpdateAsync@MapsStoreManager@@QEAAJXZ`
- size: `116`
- prototype: `__int64 __fastcall(MapsStoreManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180011900`

## callees

- `0x180018534`
- `0x1800188dc`
- `0x18001abe8`
- `0x1800363cc`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x180018593`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180018593`

## string_xrefs

- `0x18001858a`: `MapsStoreManager::CheckUpdateAsync`

## pseudocode

```c
__int64 __fastcall MapsStoreManager::CheckUpdateAsync(struct _RTL_CRITICAL_SECTION *this)
{
  int v2; // eax
  int v3; // r8d
  unsigned int v4; // edi
  wil *v5; // rcx
  int v7; // eax

  v2 = MapsStoreManager::EnsureReadyForOperation(this);
  if ( v2 < 0 )
  {
    v3 = 535;
    return (unsigned int)ZTraceReportPropagation(v2, "MapsStoreManager::CheckUpdateAsync", v3, this);
  }
  v2 = Pal::MapsbtsvcProxy::ensureJob((__int64)&Pal::MapsbtsvcProxy::smInstance, (__int64)&this[1].LockCount);
  if ( v2 < 0 )
  {
    v3 = 537;
    return (unsigned int)ZTraceReportPropagation(v2, "MapsStoreManager::CheckUpdateAsync", v3, this);
  }
  v4 = 0;
  try
  {
    MapsStoreManager::StartNonInstallOperation(this, 5);
  }
  catch ( ... )
  {
    v7 = wil::ResultFromCaughtException(v5);
    return (unsigned int)ZTraceReportOrigination(v7, "MapsStoreManager::CheckUpdateAsync", 545, this);
  }
  return v4;
}

```

## disassembly

```asm
0x180018534  mov     [rsp+arg_10], rbx
0x180018539  mov     [rsp+arg_0], rcx
0x18001853e  push    rdi
0x18001853f  sub     rsp, 20h
0x180018543  mov     rbx, rcx
0x180018546  call    ?EnsureReadyForOperation@MapsStoreManager@@AEAAJXZ; MapsStoreManager::EnsureReadyForOperation(void)
0x18001854b  test    eax, eax
0x18001854d  jns     short loc_180018557
0x18001854f  mov     r8d, 217h
0x180018555  jmp     short loc_180018587
0x180018557  lea     rdx, [rbx+30h]
0x18001855b  lea     rcx, ?smInstance@MapsbtsvcProxy@Pal@@0V12@A; Pal::MapsbtsvcProxy Pal::MapsbtsvcProxy::smInstance
0x180018562  call    ?ensureJob@MapsbtsvcProxy@Pal@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::MapsbtsvcProxy::ensureJob(std::wstring const &)
0x180018567  test    eax, eax
0x180018569  js      short loc_180018581
0x18001856b  xor     edi, edi
0x18001856d  lea     edx, [rdi+5]
0x180018570  mov     rcx, rbx
0x180018573  call    ?StartNonInstallOperation@MapsStoreManager@@AEAAXW4OperationType@1@@Z; MapsStoreManager::StartNonInstallOperation(MapsStoreManager::OperationType)
0x180018578  nop
0x180018579  jmp     short loc_18001859B
0x18001857b  mov     edi, [rsp+28h+arg_8]
0x18001857f  jmp     short loc_18001859B
0x180018581  mov     r8d, 219h
0x180018587  mov     r9, rbx
0x18001858a  lea     rdx, aMapsstoremanag_12; "MapsStoreManager::CheckUpdateAsync"
0x180018591  mov     ecx, eax
0x180018593  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180018599  mov     edi, eax
0x18001859b  mov     eax, edi
0x18001859d  mov     rbx, [rsp+28h+arg_10]
0x1800185a2  add     rsp, 20h
0x1800185a6  pop     rdi
0x1800185a7  retn
```

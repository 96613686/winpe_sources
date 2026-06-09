# DeviceCastle::Library::Internal::DeviceCastleDatabase::~DeviceCastleDatabase(void)

- ea: `0x1800445dc`
- end: `0x180044641`
- name: `??1DeviceCastleDatabase@Internal@Library@DeviceCastle@@UEAA@XZ`
- size: `101`
- prototype: `void __fastcall(DeviceCastle::Library::Internal::DeviceCastleDatabase *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800448d0`
- `0x180049b24`
- `0x180099309`

## callees

- `0x1800106ac`
- `0x180013274`
- `0x1800445dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004463a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004460f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004460f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180044600`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180044600`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180044619`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180044619`

## pseudocode

```c
void __fastcall DeviceCastle::Library::Internal::DeviceCastleDatabase::~DeviceCastleDatabase(
        DeviceCastle::Library::Internal::DeviceCastleDatabase *this)
{
  struct _TP_TIMER *v2; // rcx

  *(_QWORD *)this = &DeviceCastle::Library::Internal::DeviceCastleDatabase::`vftable';
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 14);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 14), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 14));
  }
  std::wstring::~wstring((char *)this + 80);
  std::vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>>::~vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>>((char *)this + 56);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x1800445dc  push    rbx
0x1800445de  sub     rsp, 20h
0x1800445e2  lea     rax, ??_7DeviceCastleDatabase@Internal@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Internal::DeviceCastleDatabase::`vftable'
0x1800445e9  mov     rbx, rcx
0x1800445ec  mov     [rcx], rax
0x1800445ef  mov     rcx, [rcx+70h]; pti
0x1800445f3  test    rcx, rcx
0x1800445f6  jz      short loc_18004461F
0x1800445f8  xor     r9d, r9d; msWindowLength
0x1800445fb  xor     r8d, r8d; msPeriod
0x1800445fe  xor     edx, edx; pftDueTime
0x180044600  call    cs:__imp_SetThreadpoolTimer
0x180044606  mov     rcx, [rbx+70h]; pti
0x18004460a  mov     edx, 1; fCancelPendingCallbacks
0x18004460f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180044615  mov     rcx, [rbx+70h]; pti
0x180044619  call    cs:__imp_CloseThreadpoolTimer
0x18004461f  lea     rcx, [rbx+50h]
0x180044623  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044628  lea     rcx, [rbx+38h]
0x18004462c  call    ??1?$vector@V?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@V?$allocator@V?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>>::~vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>>(void)
0x180044631  lea     rcx, [rbx+10h]
0x180044635  add     rsp, 20h
0x180044639  pop     rbx
0x18004463a  jmp     cs:__imp_DeleteCriticalSection
```

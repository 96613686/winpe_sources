# MapsStoreManager::MapsStoreManager(void)

- ea: `0x18001685c`
- end: `0x180016a1c`
- name: `??0MapsStoreManager@@AEAA@XZ`
- size: `448`
- prototype: `MapsStoreManager *__fastcall(MapsStoreManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800038a0`

## callees

- `0x1800114f4`
- `0x1800163fc`
- `0x180016548`
- `0x180016700`
- `0x1800167d0`
- `0x180016800`
- `0x18001685c`
- `0x18001ac9c`
- `0x18002e05c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016948`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180016948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001695a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001695a`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
MapsStoreManager *__fastcall MapsStoreManager::MapsStoreManager(MapsStoreManager *this)
{
  void *v1; // rdx
  HANDLE Event; // rbx
  unsigned int v3; // r8d
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Pal::Mutex::Mutex((Pal::Mutex *)MapsStoreManager::sm_mapsStoremgr);
  word_1800F18E8 = 0;
  std::wstring::wstring(qword_1800F18F0);
  std::wstring::wstring(qword_1800F1910);
  qword_1800F1930 = 0;
  qword_1800F1938 = 0;
  xmmword_1800F1940 = 0;
  qword_1800F1950 = 0;
  Pal::Mutex::Mutex((Pal::Mutex *)qword_1800F1958);
  std::unordered_map<void *,MapsStoreManager::GridRequestValue>::unordered_map<void *,MapsStoreManager::GridRequestValue>(qword_1800F1980);
  std::unordered_set<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>::unordered_set<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>(qword_1800F19C0);
  xmmword_1800F1A00 = 0;
  xmmword_1800F1A10 = 0;
  xmmword_1800F1A20 = 0;
  xmmword_1800F1A30 = 0;
  xmmword_1800F1A40 = 0;
  xmmword_1800F1A50 = 0;
  xmmword_1800F1A60 = 0;
  qword_1800F1A70 = 0;
  Event = CreateEventExW(0, 0, 3u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v1, v3, v4);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &qword_1800F1A70,
    Event);
  qword_1800F1A78 = 0;
  qword_1800F1A80 = 0;
  qword_1800F1A88 = 0;
  qword_1800F1A90 = 0;
  qword_1800F1A98 = 0;
  std::atomic<bool>::atomic<bool>(byte_1800F1AA0);
  dword_1800F1AA4 = 0;
  std::list<unsigned int>::list<unsigned int>(qword_1800F1AA8);
  std::list<unsigned int>::list<unsigned int>(qword_1800F1AB8);
  qword_1800F1AC8 = MapControl::RegionId::kUndefined;
  byte_1800F1AD0 = 0;
  std::wstring::wstring(qword_1800F1AD8);
  qword_1800F1AF8 = 0;
  xmmword_1800F1B00 = 0;
  std::wstring::wstring(qword_1800F1B10);
  xmmword_1800F1B30 = 0;
  return (MapsStoreManager *)MapsStoreManager::sm_mapsStoremgr;
}

```

## disassembly

```asm
0x18001685c  mov     [rsp+arg_10], rbx
0x180016861  mov     [rsp+arg_0], rcx
0x180016866  push    rbp
0x180016867  push    rsi
0x180016868  push    rdi
0x180016869  sub     rsp, 20h
0x18001686d  lea     rsi, ?sm_mapsStoremgr@MapsStoreManager@@0V1@A; MapsStoreManager MapsStoreManager::sm_mapsStoremgr
0x180016874  mov     [rsp+38h+arg_0], rsi
0x180016879  mov     rcx, rsi; this
0x18001687c  call    ??0Mutex@Pal@@QEAA@XZ; Pal::Mutex::Mutex(void)
0x180016881  nop
0x180016882  xor     edi, edi
0x180016884  mov     cs:word_1800F18E8, di
0x18001688b  lea     rcx, qword_1800F18F0
0x180016892  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180016897  nop
0x180016898  lea     rcx, qword_1800F1910
0x18001689f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800168a4  nop
0x1800168a5  mov     cs:qword_1800F1930, rdi
0x1800168ac  mov     cs:qword_1800F1938, rdi
0x1800168b3  xorps   xmm0, xmm0
0x1800168b6  movdqa  cs:xmmword_1800F1940, xmm0
0x1800168be  mov     cs:qword_1800F1950, rdi
0x1800168c5  lea     rcx, qword_1800F1958; this
0x1800168cc  call    ??0Mutex@Pal@@QEAA@XZ; Pal::Mutex::Mutex(void)
0x1800168d1  nop
0x1800168d2  lea     rcx, qword_1800F1980
0x1800168d9  call    ??0?$unordered_map@PEAXUGridRequestValue@MapsStoreManager@@U?$hash@PEAX@std@@U?$equal_to@PEAX@4@V?$allocator@U?$pair@QEAXUGridRequestValue@MapsStoreManager@@@std@@@4@@std@@QEAA@XZ; std::unordered_map<void *,MapsStoreManager::GridRequestValue>::unordered_map<void *,MapsStoreManager::GridRequestValue>(void)
0x1800168de  nop
0x1800168df  lea     rcx, qword_1800F19C0
0x1800168e6  call    ??0?$unordered_set@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@U?$hash@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@@2@U?$equal_to@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@@2@V?$allocator@V?$shared_ptr@VPersistedDataLoaderAsyncOperation@MapControl@@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>::unordered_set<std::shared_ptr<MapControl::PersistedDataLoaderAsyncOperation>>(void)
0x1800168eb  nop
0x1800168ec  xorps   xmm0, xmm0
0x1800168ef  movdqa  cs:xmmword_1800F1A00, xmm0
0x1800168f7  movdqa  cs:xmmword_1800F1A10, xmm0
0x1800168ff  movdqa  cs:xmmword_1800F1A20, xmm0
0x180016907  movdqa  cs:xmmword_1800F1A30, xmm0
0x18001690f  movdqa  cs:xmmword_1800F1A40, xmm0
0x180016917  movdqa  cs:xmmword_1800F1A50, xmm0
0x18001691f  movdqa  cs:xmmword_1800F1A60, xmm0
0x180016927  lea     rbp, qword_1800F1A70
0x18001692e  mov     [rsp+38h+arg_8], rbp
0x180016933  mov     cs:qword_1800F1A70, rdi
0x18001693a  xor     edx, edx; lpName
0x18001693c  xor     ecx, ecx; lpEventAttributes
0x18001693e  mov     r9d, 1F0003h; dwDesiredAccess
0x180016944  lea     r8d, [rdi+3]; dwFlags
0x180016948  call    cs:__imp_CreateEventExW
0x18001694e  mov     rbx, rax
0x180016951  test    rax, rax
0x180016954  jz      loc_180016A11
0x18001695a  call    cs:__imp_GetLastError
0x180016960  mov     rdx, rbx
0x180016963  mov     rcx, rbp
0x180016966  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18001696b  nop
0x18001696c  mov     cs:qword_1800F1A78, rdi
0x180016973  mov     cs:qword_1800F1A80, rdi
0x18001697a  mov     cs:qword_1800F1A88, rdi
0x180016981  mov     cs:qword_1800F1A90, rdi
0x180016988  mov     cs:qword_1800F1A98, rdi
0x18001698f  lea     rcx, byte_1800F1AA0
0x180016996  call    ??0?$atomic@_N@std@@QEAA@_N@Z; std::atomic<bool>::atomic<bool>(bool)
0x18001699b  mov     cs:dword_1800F1AA4, edi
0x1800169a1  lea     rcx, qword_1800F1AA8
0x1800169a8  call    ??0?$list@IV?$allocator@I@std@@@std@@QEAA@XZ; std::list<uint>::list<uint>(void)
0x1800169ad  nop
0x1800169ae  lea     rcx, qword_1800F1AB8
0x1800169b5  call    ??0?$list@IV?$allocator@I@std@@@std@@QEAA@XZ; std::list<uint>::list<uint>(void)
0x1800169ba  mov     rcx, cs:?kUndefined@RegionId@MapControl@@2V12@B; MapControl::RegionId const MapControl::RegionId::kUndefined
0x1800169c1  mov     cs:qword_1800F1AC8, rcx
0x1800169c8  mov     cs:byte_1800F1AD0, dil
0x1800169cf  lea     rcx, qword_1800F1AD8
0x1800169d6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800169db  mov     cs:qword_1800F1AF8, rdi
0x1800169e2  xorps   xmm1, xmm1
0x1800169e5  movdqa  cs:xmmword_1800F1B00, xmm1
0x1800169ed  lea     rcx, qword_1800F1B10
0x1800169f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800169f9  movdqa  cs:xmmword_1800F1B30, xmm1
0x180016a01  mov     rax, rsi
0x180016a04  mov     rbx, [rsp+38h+arg_10]
0x180016a09  add     rsp, 20h
0x180016a0d  pop     rdi
0x180016a0e  pop     rsi
0x180016a0f  pop     rbp
0x180016a10  retn
0x180016a11  mov     rcx, [rsp+38h]; this
0x180016a16  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

# wil::details_abi::SubscriptionList::~SubscriptionList(void)

- ea: `0x180065ccc`
- end: `0x180065cfc`
- name: `??1SubscriptionList@details_abi@wil@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180065bb8`
- `0x180065bf8`
- `0x1800ad571`
- `0x1800ad5cc`
- `0x1800ad5fb`
- `0x1800ad8cf`
- `0x1800ad92a`
- `0x1800ad959`

## callees

- `0x1800658f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180065cef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180065cef`

## pseudocode

```c
void __fastcall wil::details_abi::SubscriptionList::~SubscriptionList(LPCRITICAL_SECTION lpCriticalSection)
{
  wil::details_abi::heap_vector<wil::details::EnabledStateManager::CachedFeaturePropertyData>::~heap_vector<wil::details::EnabledStateManager::CachedFeaturePropertyData>((wil::details_abi::heap_buffer *)&lpCriticalSection[1]);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180065ccc  mov     [rsp+arg_0], rcx
0x180065cd1  push    rbx
0x180065cd2  sub     rsp, 30h
0x180065cd6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180065cdf  mov     rbx, rcx
0x180065ce2  add     rcx, 28h ; '('
0x180065ce6  call    ??1?$heap_vector@UCachedFeaturePropertyData@EnabledStateManager@details@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::heap_vector<wil::details::EnabledStateManager::CachedFeaturePropertyData>::~heap_vector<wil::details::EnabledStateManager::CachedFeaturePropertyData>(void)
0x180065ceb  nop
0x180065cec  mov     rcx, rbx; lpCriticalSection
0x180065cef  call    cs:__imp_DeleteCriticalSection
0x180065cf5  nop
0x180065cf6  add     rsp, 30h
0x180065cfa  pop     rbx
0x180065cfb  retn
```

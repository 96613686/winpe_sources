# winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CancelPolicyUpdateTimer(void)

- ea: `0x1800083b0`
- end: `0x18000841d`
- name: `?CancelPolicyUpdateTimer@ModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@AEAAXXZ`
- size: `109`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180005550`
- `0x180007ef0`

## callees

- `0x1800083b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800083e9`
- `KERNEL32!GetLastError` at `0x1800083e9`
- `KERNEL32!SetThreadpoolTimer` at `0x1800083d2`
- `KERNEL32!SetThreadpoolTimer` at `0x1800083d2`
- `KERNEL32!SetLastError` at `0x1800083fc`
- `KERNEL32!SetLastError` at `0x1800083fc`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800083f4`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800083f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager::CancelPolicyUpdateTimer(
        winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager *this)
{
  struct _TP_TIMER *v2; // rcx
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // ebx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 32);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    v3 = (struct _TP_TIMER *)*((_QWORD *)this + 32);
    if ( v3 )
    {
      LastError = GetLastError();
      CloseThreadpoolTimer(v3);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 32) = 0;
  }
}

```

## disassembly

```asm
0x1800083b0  push    rdi
0x1800083b2  sub     rsp, 20h
0x1800083b6  mov     rdi, rcx
0x1800083b9  mov     rcx, [rcx+100h]; pti
0x1800083c0  test    rcx, rcx
0x1800083c3  jz      short loc_180008417
0x1800083c5  xor     r9d, r9d; msWindowLength
0x1800083c8  mov     [rsp+28h+arg_8], rsi
0x1800083cd  xor     r8d, r8d; msPeriod
0x1800083d0  xor     edx, edx; pftDueTime
0x1800083d2  call    cs:__imp_SetThreadpoolTimer
0x1800083d8  mov     rsi, [rdi+100h]
0x1800083df  test    rsi, rsi
0x1800083e2  jz      short loc_180008407
0x1800083e4  mov     [rsp+28h+arg_0], rbx
0x1800083e9  call    cs:__imp_GetLastError
0x1800083ef  mov     rcx, rsi; pti
0x1800083f2  mov     ebx, eax
0x1800083f4  call    cs:__imp_CloseThreadpoolTimer
0x1800083fa  mov     ecx, ebx; dwErrCode
0x1800083fc  call    cs:__imp_SetLastError
0x180008402  mov     rbx, [rsp+28h+arg_0]
0x180008407  mov     rsi, [rsp+28h+arg_8]
0x18000840c  mov     qword ptr [rdi+100h], 0
0x180008417  add     rsp, 20h
0x18000841b  pop     rdi
0x18000841c  retn
```

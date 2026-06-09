# MapsStoreManager::GetCopyright(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,uint *)

- ea: `0x180018bf4`
- end: `0x180018cb4`
- name: `?GetCopyright@MapsStoreManager@@QEAAJPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAI@Z`
- size: `192`
- prototype: `__int64 __fastcall(MapsStoreManager *this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011960`

## callees

- `0x1800179e8`
- `0x180018968`
- `0x180018bf4`
- `0x180019f68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018c60`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018c60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018c99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018c99`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180018c29`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180018c29`

## string_xrefs

- `0x180018c1f`: `MapsStoreManager::GetCopyright`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MapsStoreManager::GetCopyright(struct _RTL_CRITICAL_SECTION *this, __int64 a2, _DWORD *a3)
{
  int v6; // r8d
  int v7; // ecx
  unsigned int v8; // edi
  struct _RTL_CRITICAL_SECTION *LockSemaphore; // rbx
  _DWORD *v10; // rdx

  if ( !a2 )
  {
    v6 = 584;
    v7 = -2147467261;
    return (unsigned int)ZTraceReportOrigination(v7, "MapsStoreManager::GetCopyright", v6, this);
  }
  if ( !MapControl::RegionSet::getIsLoaded(this) )
  {
    v6 = 585;
    v7 = -2147024875;
    return (unsigned int)ZTraceReportOrigination(v7, "MapsStoreManager::GetCopyright", v6, this);
  }
  MapsStoreManager::FetchCopyrightAsync((MapsStoreManager *)this);
  LockSemaphore = (struct _RTL_CRITICAL_SECTION *)this[15].LockSemaphore;
  EnterCriticalSection(LockSemaphore);
  v10 = this[15].LockSemaphore;
  if ( v10[19] == 2 )
  {
    v8 = 0;
    std::wstring::operator=(a2, v10 + 10);
    *a3 = *((_DWORD *)this[15].LockSemaphore + 18);
  }
  else
  {
    v8 = -2147024875;
  }
  LeaveCriticalSection(LockSemaphore);
  return v8;
}

```

## disassembly

```asm
0x180018bf4  mov     [rsp+arg_0], rbx
0x180018bf9  mov     [rsp+arg_10], rbp
0x180018bfe  push    rsi
0x180018bff  push    rdi
0x180018c00  push    r14
0x180018c02  sub     rsp, 20h
0x180018c06  mov     r14, r8
0x180018c09  mov     rbp, rdx
0x180018c0c  mov     rsi, rcx
0x180018c0f  test    rdx, rdx
0x180018c12  jnz     short loc_180018C33
0x180018c14  mov     r8d, 248h
0x180018c1a  mov     ecx, 80004003h
0x180018c1f  lea     rdx, aMapsstoremanag_3; "MapsStoreManager::GetCopyright"
0x180018c26  mov     r9, rsi
0x180018c29  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180018c2f  mov     edi, eax
0x180018c31  jmp     short loc_180018C9F
0x180018c33  call    ?getIsLoaded@RegionSet@MapControl@@QEAA_NXZ; MapControl::RegionSet::getIsLoaded(void)
0x180018c38  test    al, al
0x180018c3a  jnz     short loc_180018C49
0x180018c3c  mov     r8d, 249h
0x180018c42  mov     ecx, 80070015h
0x180018c47  jmp     short loc_180018C1F
0x180018c49  mov     rcx, rsi; this
0x180018c4c  call    ?FetchCopyrightAsync@MapsStoreManager@@AEAAXXZ; MapsStoreManager::FetchCopyrightAsync(void)
0x180018c51  mov     rbx, [rsi+270h]
0x180018c58  mov     [rsp+38h+arg_8], rbx
0x180018c5d  mov     rcx, rbx; lpCriticalSection
0x180018c60  call    cs:__imp_EnterCriticalSection
0x180018c66  nop
0x180018c67  mov     rdx, [rsi+270h]
0x180018c6e  cmp     dword ptr [rdx+4Ch], 2
0x180018c72  jz      short loc_180018C7B
0x180018c74  mov     edi, 80070015h
0x180018c79  jmp     short loc_180018C96
0x180018c7b  xor     edi, edi
0x180018c7d  add     rdx, 28h ; '('
0x180018c81  mov     rcx, rbp
0x180018c84  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180018c89  mov     rax, [rsi+270h]
0x180018c90  mov     ecx, [rax+48h]
0x180018c93  mov     [r14], ecx
0x180018c96  mov     rcx, rbx; lpCriticalSection
0x180018c99  call    cs:__imp_LeaveCriticalSection
0x180018c9f  mov     eax, edi
0x180018ca1  mov     rbx, [rsp+38h+arg_0]
0x180018ca6  mov     rbp, [rsp+38h+arg_10]
0x180018cab  add     rsp, 20h
0x180018caf  pop     r14
0x180018cb1  pop     rdi
0x180018cb2  pop     rsi
0x180018cb3  retn
```

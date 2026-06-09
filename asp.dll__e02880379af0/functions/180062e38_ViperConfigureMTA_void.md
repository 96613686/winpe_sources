# ViperConfigureMTA(void)

- ea: `0x180062e38`
- end: `0x180062f85`
- name: `?ViperConfigureMTA@@YAJXZ`
- size: `333`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000268c`

## callees

- `0x180062e38`
- `0x180064010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180062e8d`
- `ole32!CoCreateInstance` at `0x180062e8d`
- `KERNEL32!GetSystemInfo` at `0x180062ef2`
- `KERNEL32!GetSystemInfo` at `0x180062ef2`
- `KERNEL32!LeaveCriticalSection` at `0x180062f6f`
- `KERNEL32!LeaveCriticalSection` at `0x180062f6f`
- `KERNEL32!EnterCriticalSection` at `0x180062e5e`
- `KERNEL32!EnterCriticalSection` at `0x180062e5e`

## pseudocode

```c
__int64 ViperConfigureMTA(void)
{
  HRESULT v0; // ebx
  unsigned int v1; // r8d
  __int64 v2; // rdx
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-30h] BYREF
  __int64 v5; // [rsp+70h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+18h] BYREF

  v0 = 0;
  ppv = 0;
  if ( g_fFirstMTAHit )
  {
    EnterCriticalSection(&g_csFirstMTAHitLock);
    if ( g_fFirstMTAHit )
    {
      v0 = CoCreateInstance(&CLSID_MTSPackage, 0, 1u, &IID_IMTSPackage, &ppv);
      if ( v0 >= 0 )
      {
        if ( ppv )
        {
          v5 = 0;
          v0 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IComMtaThreadPoolKnobs, &v5);
          if ( v0 >= 0 && v5 )
          {
            memset(&SystemInfo, 0, sizeof(SystemInfo));
            GetSystemInfo(&SystemInfo);
            v1 = 100;
            if ( (g_AspRegistryParams & 0x1000) != 0 )
              v1 = *(_DWORD *)&dword_18007D864;
            v2 = dword_180079FA8 * SystemInfo.dwNumberOfProcessors;
            if ( v1 <= (unsigned int)v2 )
              v2 = v1;
            v0 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, v2);
            if ( v0 >= 0 )
              v0 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 40LL))(v5, 8);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
          }
        }
        else
        {
          v0 = -2147467259;
        }
      }
      g_fFirstMTAHit = 0;
    }
    LeaveCriticalSection(&g_csFirstMTAHitLock);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180062e38  mov     [rsp-8+arg_10], rbx
0x180062e3d  push    rbp
0x180062e3e  mov     rbp, rsp
0x180062e41  sub     rsp, 60h
0x180062e45  xor     ebx, ebx
0x180062e47  cmp     cs:?g_fFirstMTAHit@@3HA, ebx; int g_fFirstMTAHit
0x180062e4d  mov     [rbp+arg_8], rbx
0x180062e51  jz      loc_180062F75
0x180062e57  lea     rcx, ?g_csFirstMTAHitLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180062e5e  call    cs:__imp_EnterCriticalSection
0x180062e64  cmp     cs:?g_fFirstMTAHit@@3HA, ebx; int g_fFirstMTAHit
0x180062e6a  jz      loc_180062F68
0x180062e70  lea     rax, [rbp+arg_8]
0x180062e74  xor     edx, edx; pUnkOuter
0x180062e76  lea     r9, IID_IMTSPackage; riid
0x180062e7d  mov     [rsp+60h+ppv], rax; ppv
0x180062e82  lea     r8d, [rbx+1]; dwClsContext
0x180062e86  lea     rcx, CLSID_MTSPackage; rclsid
0x180062e8d  call    cs:__imp_CoCreateInstance
0x180062e93  mov     ebx, eax
0x180062e95  test    eax, eax
0x180062e97  js      loc_180062F5E
0x180062e9d  mov     rcx, [rbp+arg_8]
0x180062ea1  test    rcx, rcx
0x180062ea4  jnz     short loc_180062EB0
0x180062ea6  mov     ebx, 80004005h
0x180062eab  jmp     loc_180062F5E
0x180062eb0  mov     [rbp+arg_0], 0
0x180062eb8  lea     r8, [rbp+arg_0]
0x180062ebc  mov     rax, [rcx]
0x180062ebf  lea     rdx, IID_IComMtaThreadPoolKnobs
0x180062ec6  mov     rax, [rax]
0x180062ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062ece  mov     ebx, eax
0x180062ed0  test    eax, eax
0x180062ed2  js      loc_180062F5E
0x180062ed8  cmp     [rbp+arg_0], 0
0x180062edd  jz      short loc_180062F5E
0x180062edf  xorps   xmm0, xmm0
0x180062ee2  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180062ee6  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180062eea  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180062eee  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180062ef2  call    cs:__imp_GetSystemInfo
0x180062ef8  test    cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, 1000h; CAspRegistryParams g_AspRegistryParams
0x180062f02  mov     r8d, 64h ; 'd'
0x180062f08  mov     edx, [rbp+SystemInfo.dwNumberOfProcessors]
0x180062f0b  cmovnz  r8d, cs:dword_18007D864
0x180062f13  imul    edx, cs:dword_180079FA8
0x180062f1a  mov     rcx, [rbp+arg_0]
0x180062f1e  mov     rax, [rcx]
0x180062f21  cmp     r8d, edx
0x180062f24  cmovbe  edx, r8d
0x180062f28  mov     rax, [rax+18h]
0x180062f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f31  mov     ebx, eax
0x180062f33  test    eax, eax
0x180062f35  js      short loc_180062F4E
0x180062f37  mov     rcx, [rbp+arg_0]
0x180062f3b  mov     edx, 8
0x180062f40  mov     rax, [rcx]
0x180062f43  mov     rax, [rax+28h]
0x180062f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f4c  mov     ebx, eax
0x180062f4e  mov     rcx, [rbp+arg_0]
0x180062f52  mov     rax, [rcx]
0x180062f55  mov     rax, [rax+10h]
0x180062f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f5e  mov     cs:?g_fFirstMTAHit@@3HA, 0; int g_fFirstMTAHit
0x180062f68  lea     rcx, ?g_csFirstMTAHitLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180062f6f  call    cs:__imp_LeaveCriticalSection
0x180062f75  mov     eax, ebx
0x180062f77  mov     rbx, [rsp+60h+arg_10]
0x180062f7f  add     rsp, 60h
0x180062f83  pop     rbp
0x180062f84  retn
```

# ViperConfigureSTA(void)

- ea: `0x180002488`
- end: `0x180002685`
- name: `?ViperConfigureSTA@@YAJXZ`
- size: `509`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000268c`

## callees

- `0x180002488`
- `0x180064010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800024dd`
- `ole32!CoCreateInstance` at `0x1800024dd`
- `KERNEL32!GetSystemInfo` at `0x180002540`
- `KERNEL32!GetSystemInfo` at `0x180002540`
- `KERNEL32!LeaveCriticalSection` at `0x18000266f`
- `KERNEL32!LeaveCriticalSection` at `0x18000266f`
- `KERNEL32!EnterCriticalSection` at `0x1800024ae`
- `KERNEL32!EnterCriticalSection` at `0x1800024ae`

## pseudocode

```c
__int64 ViperConfigureSTA(void)
{
  HRESULT v0; // ebx
  DWORD v1; // eax
  DWORD dwNumberOfProcessors; // ebx
  DWORD v3; // r8d
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int16 v6; // ax
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-30h] BYREF
  __int64 v9; // [rsp+70h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+18h] BYREF

  v0 = 0;
  ppv = 0;
  if ( g_fFirstSTAHit )
  {
    EnterCriticalSection(&g_csFirstSTAHitLock);
    if ( g_fFirstSTAHit )
    {
      v0 = CoCreateInstance(&CLSID_MTSPackage, 0, 1u, &IID_IMTSPackage, &ppv);
      if ( v0 >= 0 )
      {
        if ( ppv )
        {
          v9 = 0;
          v0 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IComStaThreadPoolKnobs, &v9);
          if ( v0 >= 0 )
          {
            if ( v9 )
            {
              memset(&SystemInfo, 0, sizeof(SystemInfo));
              GetSystemInfo(&SystemInfo);
              v1 = 100;
              dwNumberOfProcessors = 4;
              if ( (g_AspRegistryParams & 0x1000) != 0 )
                v1 = *(_DWORD *)&dword_18007D864;
              v3 = dword_180079FA8 * SystemInfo.dwNumberOfProcessors;
              if ( v1 <= dword_180079FA8 * SystemInfo.dwNumberOfProcessors )
                v3 = v1;
              if ( SystemInfo.dwNumberOfProcessors > 4 )
                dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
              v4 = dwNumberOfProcessors;
              if ( v3 >= dwNumberOfProcessors )
                v4 = v3;
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 40LL))(v9, v4);
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, dwNumberOfProcessors);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 104LL))(v9, 30000);
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 56LL))(v9, 1);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
            }
            v9 = 0;
            v0 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IComStaThreadPoolKnobs2, &v9);
            if ( v0 >= 0 && v9 )
            {
              v5 = *(unsigned int *)&dword_18007D858;
              if ( (g_AspRegistryParams & 0x200) == 0 )
                v5 = 100;
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 120LL))(v9, v5);
              v6 = g_AspRegistryParams;
              if ( (g_AspRegistryParams & 0x100) != 0 )
              {
                (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 168LL))(v9, *(unsigned int *)&dword_18007D854);
                v6 = g_AspRegistryParams;
              }
              if ( (v6 & 0x2000) != 0 )
                (*(void (__fastcall **)(__int64, bool))(*(_QWORD *)v9 + 136LL))(v9, *(_DWORD *)&dword_18007D868 == 0);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
            }
          }
        }
        else
        {
          v0 = -2147467259;
        }
      }
      g_fFirstSTAHit = 0;
    }
    LeaveCriticalSection(&g_csFirstSTAHitLock);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x180002488  mov     [rsp-8+arg_10], rbx
0x18000248d  push    rbp
0x18000248e  mov     rbp, rsp
0x180002491  sub     rsp, 60h
0x180002495  xor     ebx, ebx
0x180002497  cmp     cs:?g_fFirstSTAHit@@3HA, ebx; int g_fFirstSTAHit
0x18000249d  mov     [rbp+arg_8], rbx
0x1800024a1  jz      loc_180002675
0x1800024a7  lea     rcx, ?g_csFirstSTAHitLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800024ae  call    cs:__imp_EnterCriticalSection
0x1800024b4  cmp     cs:?g_fFirstSTAHit@@3HA, ebx; int g_fFirstSTAHit
0x1800024ba  jz      loc_180002668
0x1800024c0  lea     rax, [rbp+arg_8]
0x1800024c4  xor     edx, edx; pUnkOuter
0x1800024c6  lea     r9, IID_IMTSPackage; riid
0x1800024cd  mov     [rsp+60h+ppv], rax; ppv
0x1800024d2  lea     r8d, [rbx+1]; dwClsContext
0x1800024d6  lea     rcx, CLSID_MTSPackage; rclsid
0x1800024dd  call    cs:__imp_CoCreateInstance
0x1800024e3  mov     ebx, eax
0x1800024e5  test    eax, eax
0x1800024e7  js      loc_18000265E
0x1800024ed  mov     rcx, [rbp+arg_8]
0x1800024f1  test    rcx, rcx
0x1800024f4  jz      loc_180024C74
0x1800024fa  mov     [rbp+arg_0], 0
0x180002502  lea     r8, [rbp+arg_0]
0x180002506  mov     rax, [rcx]
0x180002509  lea     rdx, IID_IComStaThreadPoolKnobs
0x180002510  mov     rax, [rax]
0x180002513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002518  mov     ebx, eax
0x18000251a  test    eax, eax
0x18000251c  js      loc_18000265E
0x180002522  cmp     [rbp+arg_0], 0
0x180002527  jz      loc_1800025E0
0x18000252d  xorps   xmm0, xmm0
0x180002530  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x180002534  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180002538  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18000253c  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180002540  call    cs:__imp_GetSystemInfo
0x180002546  test    cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, 1000h; CAspRegistryParams g_AspRegistryParams
0x180002550  mov     eax, 64h ; 'd'
0x180002555  mov     ecx, [rbp+SystemInfo.dwNumberOfProcessors]
0x180002558  mov     ebx, 4
0x18000255d  cmovnz  eax, cs:dword_18007D864
0x180002564  mov     r8d, ecx
0x180002567  imul    r8d, cs:dword_180079FA8
0x18000256f  cmp     eax, r8d
0x180002572  cmovbe  r8d, eax
0x180002576  cmp     ecx, ebx
0x180002578  cmova   ebx, ecx
0x18000257b  mov     rcx, [rbp+arg_0]
0x18000257f  cmp     r8d, ebx
0x180002582  mov     edx, ebx
0x180002584  cmovnb  edx, r8d
0x180002588  mov     rax, [rcx]
0x18000258b  mov     rax, [rax+28h]
0x18000258f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002594  mov     rcx, [rbp+arg_0]
0x180002598  mov     edx, ebx
0x18000259a  mov     rax, [rcx]
0x18000259d  mov     rax, [rax+18h]
0x1800025a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025a6  mov     rcx, [rbp+arg_0]
0x1800025aa  mov     edx, 7530h
0x1800025af  mov     rax, [rcx]
0x1800025b2  mov     rax, [rax+68h]
0x1800025b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025bb  mov     rcx, [rbp+arg_0]
0x1800025bf  mov     edx, 1
0x1800025c4  mov     rax, [rcx]
0x1800025c7  mov     rax, [rax+38h]
0x1800025cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025d0  mov     rcx, [rbp+arg_0]
0x1800025d4  mov     rax, [rcx]
0x1800025d7  mov     rax, [rax+10h]
0x1800025db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e0  mov     rcx, [rbp+arg_8]
0x1800025e4  lea     r8, [rbp+arg_0]
0x1800025e8  mov     [rbp+arg_0], 0
0x1800025f0  lea     rdx, IID_IComStaThreadPoolKnobs2
0x1800025f7  mov     rax, [rcx]
0x1800025fa  mov     rax, [rax]
0x1800025fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002602  mov     ebx, eax
0x180002604  test    eax, eax
0x180002606  js      short loc_18000265E
0x180002608  mov     rcx, [rbp+arg_0]
0x18000260c  test    rcx, rcx
0x18000260f  jz      short loc_18000265E
0x180002611  test    cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A, 200h; CAspRegistryParams g_AspRegistryParams
0x18000261b  mov     rax, [rcx]
0x18000261e  mov     edx, cs:dword_18007D858
0x180002624  mov     rax, [rax+78h]
0x180002628  jnz     short loc_18000262F
0x18000262a  mov     edx, 64h ; 'd'
0x18000262f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002634  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x18000263a  bt      eax, 8
0x18000263e  jb      loc_180024C7E
0x180002644  bt      eax, 0Dh
0x180002648  jb      loc_180024CA2
0x18000264e  mov     rcx, [rbp+arg_0]
0x180002652  mov     rax, [rcx]
0x180002655  mov     rax, [rax+10h]
0x180002659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000265e  mov     cs:?g_fFirstSTAHit@@3HA, 0; int g_fFirstSTAHit
0x180002668  lea     rcx, ?g_csFirstSTAHitLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000266f  call    cs:__imp_LeaveCriticalSection
0x180002675  mov     eax, ebx
0x180002677  mov     rbx, [rsp+60h+arg_10]
0x18000267f  add     rsp, 60h
0x180002683  pop     rbp
0x180002684  retn
0x180024c74  mov     ebx, 80004005h
0x180024c79  jmp     loc_18000265E
0x180024c7e  mov     rcx, [rbp+arg_0]
0x180024c82  mov     edx, cs:dword_18007D854
0x180024c88  mov     rax, [rcx]
0x180024c8b  mov     rax, [rax+0A8h]
0x180024c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c97  mov     eax, cs:?g_AspRegistryParams@@3VCAspRegistryParams@@A; CAspRegistryParams g_AspRegistryParams
0x180024c9d  jmp     loc_180002644
0x180024ca2  mov     rcx, [rbp+arg_0]
0x180024ca6  xor     edx, edx
0x180024ca8  cmp     cs:dword_18007D868, edx
0x180024cae  setz    dl
0x180024cb1  mov     rax, [rcx]
0x180024cb4  mov     rax, [rax+88h]
0x180024cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cc0  nop
0x180024cc1  jmp     loc_18000264E
```

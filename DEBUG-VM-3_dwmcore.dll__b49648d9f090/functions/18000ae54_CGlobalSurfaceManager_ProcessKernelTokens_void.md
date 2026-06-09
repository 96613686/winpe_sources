# CGlobalSurfaceManager::ProcessKernelTokens(void)

- ea: `0x18000ae54`
- end: `0x18000afcf`
- name: `?ProcessKernelTokens@CGlobalSurfaceManager@@AEAAJXZ`
- size: `379`
- prototype: `__int64 __fastcall(CGlobalSurfaceManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180233a00`

## callees

- `0x18000ae54`
- `0x18000afd8`
- `0x18000b07c`
- `0x18000b380`
- `0x180042de0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ae94`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000ae94`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000af4c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000af4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae9e`
- `win32u!NtTokenManagerThread` at `0x18000af8b`
- `win32u!NtTokenManagerThread` at `0x18000af8b`

## pseudocode

```c
__int64 __fastcall CGlobalSurfaceManager::ProcessKernelTokens(CGlobalSurfaceManager *this)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  __int128 v9; // [rsp+38h] [rbp-20h]

  v8 = *((_QWORD *)this + 16);
  v9 = 0;
  v2 = 0;
  while ( !*((_BYTE *)this + 144) )
  {
    SetLastError(0);
    if ( !ResetEvent(*((HANDLE *)this + 16)) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( (v2 & 0x80000000) == 0 )
        v2 = -2003304445;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v2, 0x183u, 0);
      return v2;
    }
    if ( *((_BYTE *)this + 144) )
      return v2;
    CMmcssTask::Clone((LPCRITICAL_SECTION)((char *)g_pComposition + 728), (LPCRITICAL_SECTION)((char *)this + 408));
    v5 = CGlobalSurfaceManager::EnsureAdapterInfo(this);
    v2 = v5;
    if ( v5 >= 0 )
    {
      v6 = *((_QWORD *)this + 64) - *((_QWORD *)this + 63);
      *(_QWORD *)&v9 = *((_QWORD *)this + 63);
      DWORD2(v9) = -1431655765 * (v6 >> 3);
      v7 = NtTokenManagerThread(&v8);
      if ( v7 < 0 )
      {
        v2 = v7 | 0x10000000;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v7 | 0x10000000, 0x1A3u, 0);
      }
      std::vector<CGlobalSurfaceManager::AdapterInfo>::clear((char *)this + 504);
    }
    else
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v5, 0x194u, 0);
      WaitForSingleObject(*((HANDLE *)this + 16), 0xFFFFFFFF);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000ae54  mov     [rsp+arg_0], rbx
0x18000ae59  mov     [rsp+arg_8], rsi
0x18000ae5e  push    rdi
0x18000ae5f  sub     rsp, 50h
0x18000ae63  mov     rax, [rcx+80h]
0x18000ae6a  xorps   xmm0, xmm0
0x18000ae6d  mov     [rsp+58h+var_28], rax
0x18000ae72  mov     rdi, rcx
0x18000ae75  movups  [rsp+58h+var_20], xmm0
0x18000ae7a  xor     ebx, ebx
0x18000ae7c  cmp     byte ptr [rdi+90h], 0
0x18000ae83  jnz     short loc_18000AEDE
0x18000ae85  xor     ecx, ecx; dwErrCode
0x18000ae87  call    cs:__imp_SetLastError
0x18000ae8d  mov     rcx, [rdi+80h]; hEvent
0x18000ae94  call    cs:__imp_ResetEvent
0x18000ae9a  test    eax, eax
0x18000ae9c  jnz     short loc_18000AEF0
0x18000ae9e  call    cs:__imp_GetLastError
0x18000aea4  mov     ebx, eax
0x18000aea6  test    eax, eax
0x18000aea8  jle     short loc_18000AEB3
0x18000aeaa  movzx   ebx, ax
0x18000aead  or      ebx, 80070000h
0x18000aeb3  test    ebx, ebx
0x18000aeb5  mov     [rsp+58h+var_30], 0; void *
0x18000aebe  mov     eax, 88980003h
0x18000aec3  mov     [rsp+58h+var_38], 183h; unsigned int
0x18000aecb  cmovns  ebx, eax
0x18000aece  xor     edx, edx; int *
0x18000aed0  mov     r9d, ebx; int
0x18000aed3  xor     r8d, r8d; unsigned int
0x18000aed6  lea     ecx, [rdx+14h]; unsigned int
0x18000aed9  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000aede  mov     rsi, [rsp+58h+arg_8]
0x18000aee3  mov     eax, ebx
0x18000aee5  mov     rbx, [rsp+58h+arg_0]
0x18000aeea  add     rsp, 50h
0x18000aeee  pop     rdi
0x18000aeef  retn
0x18000aef0  cmp     byte ptr [rdi+90h], 0
0x18000aef7  jnz     short loc_18000AEDE
0x18000aef9  mov     rcx, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x18000af00  lea     rdx, [rdi+198h]; LPCRITICAL_SECTION
0x18000af07  add     rcx, 2D8h; lpCriticalSection
0x18000af0e  call    ?Clone@CMmcssTask@@QEBAJPEAV1@@Z; CMmcssTask::Clone(CMmcssTask *)
0x18000af13  mov     rcx, rdi; this
0x18000af16  call    ?EnsureAdapterInfo@CGlobalSurfaceManager@@AEAAJXZ; CGlobalSurfaceManager::EnsureAdapterInfo(void)
0x18000af1b  mov     ebx, eax
0x18000af1d  test    eax, eax
0x18000af1f  jns     short loc_18000AF57
0x18000af21  xor     edx, edx; int *
0x18000af23  mov     [rsp+58h+var_30], 0; void *
0x18000af2c  mov     r9d, eax; int
0x18000af2f  mov     [rsp+58h+var_38], 194h; unsigned int
0x18000af37  xor     r8d, r8d; unsigned int
0x18000af3a  lea     ecx, [rdx+14h]; unsigned int
0x18000af3d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000af42  mov     rcx, [rdi+80h]; hHandle
0x18000af49  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000af4c  call    cs:__imp_WaitForSingleObject
0x18000af52  jmp     loc_18000AE7C
0x18000af57  mov     rcx, [rdi+200h]
0x18000af5e  lea     rsi, [rdi+1F8h]
0x18000af65  mov     rax, [rsi]
0x18000af68  sub     rcx, rax
0x18000af6b  mov     qword ptr [rsp+58h+var_20], rax
0x18000af70  sar     rcx, 3
0x18000af74  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000af7e  imul    rcx, rax
0x18000af82  mov     dword ptr [rsp+58h+var_20+8], ecx
0x18000af86  lea     rcx, [rsp+58h+var_28]
0x18000af8b  call    cs:__imp_NtTokenManagerThread
0x18000af91  test    eax, eax
0x18000af93  js      short loc_18000AFA2
0x18000af95  mov     rcx, rsi
0x18000af98  call    ?clear@?$vector@VAdapterInfo@CGlobalSurfaceManager@@V?$allocator@VAdapterInfo@CGlobalSurfaceManager@@@std@@@std@@QEAAXXZ; std::vector<CGlobalSurfaceManager::AdapterInfo>::clear(void)
0x18000af9d  jmp     loc_18000AE7C
0x18000afa2  mov     ebx, eax
0x18000afa4  or      ebx, 10000000h
0x18000afaa  jge     short loc_18000AF95
0x18000afac  xor     edx, edx; int *
0x18000afae  mov     [rsp+58h+var_30], 0; void *
0x18000afb7  mov     r9d, ebx; int
0x18000afba  mov     [rsp+58h+var_38], 1A3h; unsigned int
0x18000afc2  xor     r8d, r8d; unsigned int
0x18000afc5  lea     ecx, [rdx+14h]; unsigned int
0x18000afc8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000afcd  jmp     short loc_18000AF95
```

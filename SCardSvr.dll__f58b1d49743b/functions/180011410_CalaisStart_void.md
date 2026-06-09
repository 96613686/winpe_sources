# CalaisStart(void)

- ea: `0x180011410`
- end: `0x180011ab3`
- name: `?CalaisStart@@YAKXZ`
- size: `1699`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010f50`

## callees

- `0x1800022b0`
- `0x1800075d0`
- `0x18000fc40`
- `0x180011410`
- `0x180011abc`
- `0x180012380`
- `0x180017b44`
- `0x180017f44`
- `0x180018278`
- `0x180019220`
- `0x180019b40`
- `0x180019bc4`
- `0x18001c330`
- `0x180023168`
- `0x18002438c`
- `0x180028b78`
- `0x18002ac04`
- `0x180032258`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011596`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180011596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011640`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011640`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800116cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800117bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011905`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800116cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800117bc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011905`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a3d`

## pseudocode

```c
__int64 CalaisStart(void)
{
  __int64 v0; // rbx
  CCriticalSectionObject *v1; // rax
  unsigned int v2; // edx
  struct CCriticalSectionObject *v3; // rcx
  unsigned int v4; // edx
  CCriticalSectionObject *v5; // rcx
  CCriticalSectionObject *v6; // rcx
  struct CCriticalSectionObject *v8; // rbx
  CMultiEvent *v9; // rax
  const unsigned __int16 *v10; // r9
  CMultiEvent *v11; // rcx
  const unsigned __int8 *v12; // rcx
  const unsigned __int16 *v13; // r9
  unsigned int v14; // edx
  DWORD LastError; // ebx
  const unsigned __int8 *v16; // rcx
  LSTATUS v17; // eax
  LSTATUS v18; // eax
  unsigned int v19; // eax
  LSTATUS v20; // eax
  unsigned int v21; // eax
  int v22; // r9d
  LSTATUS v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // eax
  int v26; // r9d
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-B8h]
  struct CCriticalSectionObject *v28; // [rsp+30h] [rbp-A8h] BYREF
  ulong pExceptionObject; // [rsp+38h] [rbp-A0h] BYREF
  LSTATUS v30; // [rsp+3Ch] [rbp-9Ch] BYREF
  LSTATUS v31; // [rsp+40h] [rbp-98h] BYREF
  ulong v32; // [rsp+44h] [rbp-94h] BYREF
  ulong v33; // [rsp+48h] [rbp-90h] BYREF
  LSTATUS v34; // [rsp+4Ch] [rbp-8Ch] BYREF
  ulong v35; // [rsp+50h] [rbp-88h] BYREF
  ulong v36; // [rsp+54h] [rbp-84h] BYREF
  LSTATUS v37; // [rsp+58h] [rbp-80h] BYREF
  ulong v38; // [rsp+5Ch] [rbp-7Ch] BYREF
  void **v39; // [rsp+60h] [rbp-78h]
  __int64 v40; // [rsp+68h] [rbp-70h]
  __int64 v41; // [rsp+70h] [rbp-68h]
  HKEY hKey; // [rsp+78h] [rbp-60h] BYREF
  int v43; // [rsp+80h] [rbp-58h]
  void **v44; // [rsp+88h] [rbp-50h]
  void *Block; // [rsp+90h] [rbp-48h]
  int v46; // [rsp+98h] [rbp-40h]
  int v47; // [rsp+9Ch] [rbp-3Ch]
  ulong v48; // [rsp+A0h] [rbp-38h]
  ulong v49[11]; // [rsp+ACh] [rbp-2Ch] BYREF
  CCriticalSectionObject *Data; // [rsp+E0h] [rbp+8h] BYREF
  unsigned int v51; // [rsp+E8h] [rbp+10h]
  DWORD Type; // [rsp+F0h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+F8h] [rbp+20h] BYREF

  v51 = 0;
  if ( dword_18004BF6C )
    return v51;
  _InterlockedExchange((volatile __int32 *)&g_fBlockServiceHandler, 0);
  LODWORD(v0) = 0;
  while ( (unsigned int)v0 < 4 )
  {
    v1 = (CCriticalSectionObject *)operator new(0x38u);
    Data = v1;
    if ( v1 )
      v3 = CCriticalSectionObject::CCriticalSectionObject(v1, v2);
    else
      v3 = 0;
    *(&g_pcsControlLocks + (unsigned int)v0) = v3;
    if ( !v3 )
      return 2148532230LL;
    if ( (*(unsigned int (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v3 + 16LL))(v3) )
    {
      v5 = *(&g_pcsControlLocks + (unsigned int)v0);
      if ( v5 )
        CCriticalSectionObject::`scalar deleting destructor'(v5, v4);
      *(&g_pcsControlLocks + (unsigned int)v0) = 0;
      do
      {
        v0 = (unsigned int)(v0 - 1);
        v6 = *(&g_pcsControlLocks + v0);
        if ( v6 )
          CCriticalSectionObject::`scalar deleting destructor'(v6, v4);
        *(&g_pcsControlLocks + v0) = 0;
      }
      while ( (_DWORD)v0 );
      return 2148532230LL;
    }
    LODWORD(v0) = v0 + 1;
  }
  v8 = g_pcsControlLocks;
  v28 = g_pcsControlLocks;
  (**(void (__fastcall ***)(struct CCriticalSectionObject *, _QWORD, _QWORD))g_pcsControlLocks)(g_pcsControlLocks, 0, 0);
  dword_18004BF6C = 1;
  v9 = (CMultiEvent *)operator new(0x60u);
  Data = v9;
  if ( v9 )
    v11 = CMultiEvent::CMultiEvent(v9);
  else
    v11 = 0;
  g_phReaderChangeEvent = v11;
  if ( !v11 )
  {
    CalaisError(0, 0xCEu, 0, v10, phkResult);
    COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v28);
    return 2148532230LL;
  }
  if ( !(*(unsigned int (__fastcall **)(CMultiEvent *))(*(_QWORD *)v11 + 16LL))(v11) )
  {
    g_hCalaisShutdown = CreateEventW(0, 1, 0, 0);
    if ( !g_hCalaisShutdown )
    {
      LastError = GetLastError();
      CalaisError(v16, 0xCCu, LastError, 0, 0, 0);
      pExceptionObject = LastError;
      throw &pExceptionObject;
    }
    CalaisInitializeAsyncReaderHandling();
    CPowerSupport::Initialize();
    if ( __eh34_try(0, 1) )
    {
      __eh34_scope_strut(1);
      v44 = &CBuffer::`vftable';
      Block = 0;
      v47 = 0;
      hKey = 0;
      v48 = 1010;
      v46 = 0;
      v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Cryptography\\Calais", 0, 0x20019u, &hKey);
      v48 = v17;
      v43 = 2;
      if ( v17 )
      {
        v30 = v17;
        throw (ulong *)&v30;
      }
      LODWORD(Data) = 0;
      Type = 0;
      v39 = &CBuffer::`vftable';
      v40 = 0;
      v41 = 0;
      cbData = 4;
      v18 = RegQueryValueExW(hKey, L"MaxDefaultBuffer", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( __eh34_try(1, 2) )
      {
        __eh34_scope_strut(2);
        if ( v18 )
        {
          v31 = v18;
          throw (ulong *)&v31;
        }
        if ( Type == 4 )
        {
          v19 = (unsigned int)Data;
        }
        else
        {
          if ( Type != 5 )
          {
            v32 = 11;
            throw &v32;
          }
          v19 = HTONL((unsigned int)Data);
        }
        g_dwDefaultIOMax = v19;
      }
      if ( __eh34_catch(2) )
      {
        if ( __eh34_catch_type(2, &unsigned long `RTTI Type Descriptor', 0) )
        {
          v8 = v28;
          __eh34_try_continuation(2, &unsigned long `RTTI Type Descriptor', &loc_180011731);
        }
      }
      if ( __eh34_try(1, 4) )
      {
        __eh34_scope_strut(4);
        LODWORD(Data) = 0;
        Type = 0;
        v39 = &CBuffer::`vftable';
        v40 = 0;
        v41 = 0;
        if ( v48 )
        {
          v33 = v48;
          throw &v33;
        }
        cbData = 4;
        v20 = RegQueryValueExW(hKey, L"CardDisconnectPowerDownDelay", 0, &Type, (LPBYTE)&Data, &cbData);
        if ( v20 )
        {
          v34 = v20;
          throw (ulong *)&v34;
        }
        if ( Type == 4 )
        {
          v21 = (unsigned int)Data;
        }
        else
        {
          if ( Type != 5 )
          {
            v35 = 11;
            throw &v35;
          }
          v21 = HTONL((unsigned int)Data);
        }
        g_dwCardDisconnectPowerDownDelay = v21;
        if ( v21 > 0xE10 )
          g_dwCardDisconnectPowerDownDelay = 3600;
      }
      if ( __eh34_catch(4) )
      {
        if ( __eh34_catch_type(4, &unsigned long `RTTI Type Descriptor', 0) )
        {
          v8 = v28;
          __eh34_try_continuation(4, &unsigned long `RTTI Type Descriptor', &loc_180011831);
        }
      }
      if ( __eh34_try(1, 6) )
      {
        __eh34_scope_strut(6);
        WppTraceIndent(3600, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            (int)WPP_f3ba224ca5d536188ece76512abbdd99_Traceguids,
            v22,
            g_dwCardDisconnectPowerDownDelay);
        }
        LODWORD(Data) = 0;
        Type = 0;
        v39 = &CBuffer::`vftable';
        v40 = 0;
        v41 = 0;
        if ( v48 )
        {
          v36 = v48;
          throw &v36;
        }
        cbData = 4;
        v23 = RegQueryValueExW(hKey, L"TransactionTimeoutDelay", 0, &Type, (LPBYTE)&Data, &cbData);
        if ( v23 )
        {
          v37 = v23;
          throw (ulong *)&v37;
        }
        if ( Type == 4 )
        {
          v25 = (unsigned int)Data;
        }
        else
        {
          if ( Type != 5 )
          {
            v38 = 11;
            throw &v38;
          }
          v25 = HTONL((unsigned int)Data);
        }
        g_dwTransactionTimeoutDelay = v25;
        if ( v25 )
        {
          if ( v25 >= 5 )
          {
            if ( v25 > 0x3C )
              g_dwTransactionTimeoutDelay = 60;
          }
          else
          {
            g_dwTransactionTimeoutDelay = 5;
          }
        }
        else
        {
          g_fDisableTransactionTimeoutDelay = 1;
        }
      }
      if ( __eh34_catch(6) )
      {
        if ( __eh34_catch_type(6, &unsigned long `RTTI Type Descriptor', 0) )
        {
          v8 = v28;
          __eh34_try_continuation(6, &unsigned long `RTTI Type Descriptor', &loc_180011998);
        }
      }
    }
    if ( __eh34_catch(1) )
    {
      if ( __eh34_catch_type(1, &unsigned long `RTTI Type Descriptor', v49) )
        throw;
    }
    if ( g_fDisableTransactionTimeoutDelay )
    {
      WppTraceIndent(v24, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_f3ba224ca5d536188ece76512abbdd99_Traceguids,
          WPP_pszIndent);
      }
    }
    else
    {
      WppTraceIndent(v24, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (int)WPP_f3ba224ca5d536188ece76512abbdd99_Traceguids,
          v26,
          g_dwTransactionTimeoutDelay);
      }
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v48 = 1010;
    v46 = 0;
    v44 = &CBuffer::`vftable';
    if ( Block )
      operator delete[](Block);
    dword_18004BF68 = 1;
    AddAllPnPDrivers();
    AddAllNgcReaders();
    (*(void (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v8 + 8LL))(v8);
    return v51;
  }
  CalaisError(v12, 0xCFu, 0, v13, phkResult);
  if ( g_phReaderChangeEvent )
    CMultiEvent::`scalar deleting destructor'(g_phReaderChangeEvent, v14);
  g_phReaderChangeEvent = 0;
  COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v28);
  return 2148532230LL;
}

```

## disassembly

```asm
0x180011410  push    rbx
0x180011412  push    rsi
0x180011413  push    rdi
0x180011414  push    r14
0x180011416  sub     rsp, 0B8h
0x18001141d  xor     edi, edi
0x18001141f  mov     [rsp+0D8h+arg_8], edi
0x180011426  cmp     cs:dword_18004BF6C, edi
0x18001142c  jnz     loc_180011A9E
0x180011432  mov     eax, edi
0x180011434  xchg    eax, cs:?g_fBlockServiceHandler@@3KA; ulong g_fBlockServiceHandler
0x18001143a  mov     ebx, edi
0x18001143c  lea     r14, ?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; CCriticalSectionObject * near * g_pcsControlLocks
0x180011443  cmp     ebx, 4
0x180011446  jnb     short loc_1800114C2
0x180011448  mov     ecx, 38h ; '8'; Size
0x18001144d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011452  mov     [rsp+0D8h+Data], rax
0x18001145a  test    rax, rax
0x18001145d  jz      short loc_18001146C
0x18001145f  mov     rcx, rax; this
0x180011462  call    ??0CCriticalSectionObject@@QEAA@K@Z; CCriticalSectionObject::CCriticalSectionObject(ulong)
0x180011467  mov     rcx, rax
0x18001146a  jmp     short loc_18001146F
0x18001146c  mov     rcx, rdi
0x18001146f  mov     esi, ebx
0x180011471  mov     [r14+rsi*8], rcx
0x180011475  test    rcx, rcx
0x180011478  jz      short loc_1800114B8
0x18001147a  mov     rax, [rcx]
0x18001147d  mov     rax, [rax+10h]
0x180011481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011486  test    eax, eax
0x180011488  jnz     short loc_18001148E
0x18001148a  inc     ebx
0x18001148c  jmp     short loc_180011443
0x18001148e  mov     rcx, [r14+rsi*8]; this
0x180011492  test    rcx, rcx
0x180011495  jz      short loc_18001149C
0x180011497  call    ??_GCCriticalSectionObject@@QEAAPEAXI@Z; CCriticalSectionObject::`scalar deleting destructor'(uint)
0x18001149c  mov     [r14+rsi*8], rdi
0x1800114a0  dec     ebx
0x1800114a2  mov     rcx, [r14+rbx*8]; this
0x1800114a6  test    rcx, rcx
0x1800114a9  jz      short loc_1800114B0
0x1800114ab  call    ??_GCCriticalSectionObject@@QEAAPEAXI@Z; CCriticalSectionObject::`scalar deleting destructor'(uint)
0x1800114b0  mov     [r14+rbx*8], rdi
0x1800114b4  test    ebx, ebx
0x1800114b6  jnz     short loc_1800114A0
0x1800114b8  mov     eax, 80100006h
0x1800114bd  jmp     loc_180011AA5
0x1800114c2  mov     rbx, cs:?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; CCriticalSectionObject * near * g_pcsControlLocks
0x1800114c9  mov     [rsp+0D8h+var_A8], rbx
0x1800114ce  mov     rax, [rbx]
0x1800114d1  xor     r8d, r8d
0x1800114d4  xor     edx, edx
0x1800114d6  mov     rcx, rbx
0x1800114d9  mov     rax, [rax]
0x1800114dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114e1  nop
0x1800114e2  mov     cs:dword_18004BF6C, 1
0x1800114ec  mov     ecx, 60h ; '`'; Size
0x1800114f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800114f6  mov     [rsp+0D8h+Data], rax
0x1800114fe  test    rax, rax
0x180011501  jz      short loc_180011510
0x180011503  mov     rcx, rax; this
0x180011506  call    ??0CMultiEvent@@QEAA@XZ; CMultiEvent::CMultiEvent(void)
0x18001150b  mov     rcx, rax
0x18001150e  jmp     short loc_180011513
0x180011510  mov     rcx, rdi; unsigned __int8 *
0x180011513  mov     cs:?g_phReaderChangeEvent@@3PEAVCMultiEvent@@EA, rcx; CMultiEvent * g_phReaderChangeEvent
0x18001151a  test    rcx, rcx
0x18001151d  jnz     short loc_180011541
0x18001151f  xor     r8d, r8d; unsigned __int16 *
0x180011522  mov     edx, 0CEh; unsigned int
0x180011527  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18001152c  nop
0x18001152d  lea     rcx, [rsp+0D8h+var_A8]; this
0x180011532  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x180011537  mov     eax, 80100006h
0x18001153c  jmp     loc_180011AA5
0x180011541  mov     rax, [rcx]
0x180011544  mov     rax, [rax+10h]
0x180011548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001154d  test    eax, eax
0x18001154f  jz      short loc_18001158A
0x180011551  xor     r8d, r8d; unsigned __int16 *
0x180011554  mov     edx, 0CFh; unsigned int
0x180011559  call    ?CalaisError@@YAXPEBEKPEBG11@Z; CalaisError(uchar const *,ulong,ushort const *,ushort const *,ushort const *)
0x18001155e  mov     rcx, cs:?g_phReaderChangeEvent@@3PEAVCMultiEvent@@EA; this
0x180011565  test    rcx, rcx
0x180011568  jz      short loc_18001156F
0x18001156a  call    ??_GCMultiEvent@@QEAAPEAXI@Z; CMultiEvent::`scalar deleting destructor'(uint)
0x18001156f  mov     cs:?g_phReaderChangeEvent@@3PEAVCMultiEvent@@EA, rdi; CMultiEvent * g_phReaderChangeEvent
0x180011576  lea     rcx, [rsp+0D8h+var_A8]; this
0x18001157b  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x180011580  mov     eax, 80100006h
0x180011585  jmp     loc_180011AA5
0x18001158a  xor     r9d, r9d; lpName
0x18001158d  xor     r8d, r8d; bInitialState
0x180011590  lea     edx, [r9+1]; bManualReset
0x180011594  xor     ecx, ecx; lpEventAttributes
0x180011596  call    cs:__imp_CreateEventW
0x18001159c  mov     cs:?g_hCalaisShutdown@@3PEAXEA, rax; void * g_hCalaisShutdown
0x1800115a3  test    rax, rax
0x1800115a6  jnz     short loc_1800115DF
0x1800115a8  call    cs:__imp_GetLastError
0x1800115ae  mov     ebx, eax
0x1800115b0  mov     [rsp+0D8h+lpcbData], rdi; unsigned __int16 *
0x1800115b5  mov     [rsp+0D8h+phkResult], rdi; unsigned __int16 *
0x1800115ba  xor     r9d, r9d; unsigned __int16 *
0x1800115bd  mov     r8d, eax; unsigned int
0x1800115c0  mov     edx, 0CCh; unsigned int
0x1800115c5  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x1800115ca  mov     [rsp+0D8h+pExceptionObject], ebx
0x1800115ce  lea     rdx, _TI1K; pThrowInfo
0x1800115d5  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x1800115da  call    _CxxThrowException_0
0x1800115df  call    ?CalaisInitializeAsyncReaderHandling@@YAXXZ; CalaisInitializeAsyncReaderHandling(void)
0x1800115e4  call    ?Initialize@CPowerSupport@@SAKXZ; CPowerSupport::Initialize(void)
0x1800115e9  nop
0x1800115ea  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x1800115f1  mov     [rsp+0D8h+var_50], rsi
0x1800115f9  mov     [rsp+0D8h+Block], rdi
0x180011601  mov     [rsp+0D8h+var_3C], edi
0x180011608  mov     [rsp+0D8h+hKey], rdi
0x18001160d  mov     [rsp+0D8h+var_38], 3F2h
0x180011618  mov     [rsp+0D8h+var_40], edi
0x18001161f  lea     rax, [rsp+0D8h+hKey]
0x180011624  mov     [rsp+0D8h+phkResult], rax; phkResult
0x180011629  mov     r9d, 20019h; samDesired
0x18001162f  xor     r8d, r8d; ulOptions
0x180011632  mov     rdx, cs:lpSubKey; lpSubKey
0x180011639  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180011640  call    cs:__imp_RegOpenKeyExW
0x180011646  mov     [rsp+0D8h+var_38], eax
0x18001164d  mov     [rsp+0D8h+var_58], 2
0x180011658  test    eax, eax
0x18001165a  jz      short loc_180011672
0x18001165c  mov     [rsp+0D8h+var_9C], eax
0x180011660  lea     rdx, _TI1K; pThrowInfo
0x180011667  lea     rcx, [rsp+0D8h+var_9C]; pExceptionObject
0x18001166c  call    _CxxThrowException_0
0x180011672  mov     dword ptr [rsp+0D8h+Data], edi
0x180011679  mov     [rsp+0D8h+Type], edi
0x180011680  mov     [rsp+0D8h+var_78], rsi
0x180011685  mov     [rsp+0D8h+var_70], rdi
0x18001168a  mov     [rsp+0D8h+var_68], rdi
0x18001168f  mov     [rsp+0D8h+cbData], 4
0x18001169a  lea     rax, [rsp+0D8h+cbData]
0x1800116a2  mov     [rsp+0D8h+lpcbData], rax; lpcbData
0x1800116a7  lea     rax, [rsp+0D8h+Data]
0x1800116af  mov     [rsp+0D8h+phkResult], rax; lpData
0x1800116b4  lea     r9, [rsp+0D8h+Type]; lpType
0x1800116bc  xor     r8d, r8d; lpReserved
0x1800116bf  mov     rdx, cs:lpValueName; lpValueName
0x1800116c6  mov     rcx, [rsp+0D8h+hKey]; hKey
0x1800116cb  call    cs:__imp_RegQueryValueExW
0x1800116d1  test    eax, eax
0x1800116d3  jz      short loc_1800116EA
0x1800116d5  mov     [rsp+0D8h+var_98], eax
0x1800116d9  lea     rdx, _TI1K; pThrowInfo
0x1800116e0  lea     rcx, [rsp+0D8h+var_98]; pExceptionObject
0x1800116e5  call    _CxxThrowException_0
0x1800116ea  mov     eax, [rsp+0D8h+Type]
0x1800116f1  sub     eax, 4
0x1800116f4  jz      short loc_180011722
0x1800116f6  cmp     eax, 1
0x1800116f9  jz      short loc_180011714
0x1800116fb  mov     [rsp+0D8h+var_94], 0Bh
0x180011703  lea     rdx, _TI1K; pThrowInfo
0x18001170a  lea     rcx, [rsp+0D8h+var_94]; pExceptionObject
0x18001170f  call    _CxxThrowException_0
0x180011714  mov     ecx, dword ptr [rsp+0D8h+Data]
0x18001171b  call    HTONL
0x180011720  jmp     short loc_180011729
0x180011722  mov     eax, dword ptr [rsp+0D8h+Data]
0x180011729  mov     cs:?g_dwDefaultIOMax@@3KA, eax; ulong g_dwDefaultIOMax
0x18001172f  jmp     short loc_18001173F
0x180011731  xor     edi, edi
0x180011733  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001173a  mov     rbx, [rsp+0D8h+var_A8]
0x18001173f  mov     dword ptr [rsp+0D8h+Data], edi
0x180011746  mov     [rsp+0D8h+Type], edi
0x18001174d  mov     [rsp+0D8h+var_78], rsi
0x180011752  mov     [rsp+0D8h+var_70], rdi
0x180011757  mov     [rsp+0D8h+var_68], 0
0x180011760  mov     eax, [rsp+0D8h+var_38]
0x180011767  test    eax, eax
0x180011769  jz      short loc_180011780
0x18001176b  mov     [rsp+0D8h+var_90], eax
0x18001176f  lea     rdx, _TI1K; pThrowInfo
0x180011776  lea     rcx, [rsp+0D8h+var_90]; pExceptionObject
0x18001177b  call    _CxxThrowException_0
0x180011780  mov     [rsp+0D8h+cbData], 4
0x18001178b  lea     rax, [rsp+0D8h+cbData]
0x180011793  mov     [rsp+0D8h+lpcbData], rax; lpcbData
0x180011798  lea     rax, [rsp+0D8h+Data]
0x1800117a0  mov     [rsp+0D8h+phkResult], rax; lpData
0x1800117a5  lea     r9, [rsp+0D8h+Type]; lpType
0x1800117ad  xor     r8d, r8d; lpReserved
0x1800117b0  mov     rdx, cs:off_1800380F8; lpValueName
0x1800117b7  mov     rcx, [rsp+0D8h+hKey]; hKey
0x1800117bc  call    cs:__imp_RegQueryValueExW
0x1800117c2  test    eax, eax
0x1800117c4  jz      short loc_1800117DB
0x1800117c6  mov     [rsp+0D8h+var_8C], eax
0x1800117ca  lea     rdx, _TI1K; pThrowInfo
0x1800117d1  lea     rcx, [rsp+0D8h+var_8C]; pExceptionObject
0x1800117d6  call    _CxxThrowException_0
0x1800117db  mov     eax, [rsp+0D8h+Type]
0x1800117e2  sub     eax, 4
0x1800117e5  jz      short loc_180011813
0x1800117e7  cmp     eax, 1
0x1800117ea  jz      short loc_180011805
0x1800117ec  mov     [rsp+0D8h+var_88], 0Bh
0x1800117f4  lea     rdx, _TI1K; pThrowInfo
0x1800117fb  lea     rcx, [rsp+0D8h+var_88]; pExceptionObject
0x180011800  call    _CxxThrowException_0
0x180011805  mov     ecx, dword ptr [rsp+0D8h+Data]
0x18001180c  call    HTONL
0x180011811  jmp     short loc_18001181A
0x180011813  mov     eax, dword ptr [rsp+0D8h+Data]
0x18001181a  mov     cs:?g_dwCardDisconnectPowerDownDelay@@3KA, eax; ulong g_dwCardDisconnectPowerDownDelay
0x180011820  mov     ecx, 0E10h
0x180011825  cmp     eax, ecx
0x180011827  jbe     short loc_18001182F
0x180011829  mov     cs:?g_dwCardDisconnectPowerDownDelay@@3KA, ecx; ulong g_dwCardDisconnectPowerDownDelay
0x18001182f  jmp     short loc_18001183F
0x180011831  xor     edi, edi
0x180011833  lea     rsi, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18001183a  mov     rbx, [rsp+0D8h+var_A8]
0x18001183f  mov     edx, 2
0x180011844  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180011849  lea     r14, WPP_GLOBAL_Control
0x180011850  mov     rcx, cs:WPP_GLOBAL_Control
0x180011857  cmp     rcx, r14
0x18001185a  jz      short loc_180011888
0x18001185c  test    byte ptr [rcx+1Ch], 1
0x180011860  jz      short loc_180011888
0x180011862  cmp     byte ptr [rcx+19h], 4
0x180011866  jb      short loc_180011888
0x180011868  mov     edx, 0Ah
0x18001186d  mov     eax, cs:?g_dwCardDisconnectPowerDownDelay@@3KA; ulong g_dwCardDisconnectPowerDownDelay
0x180011873  mov     dword ptr [rsp+0D8h+phkResult], eax
0x180011877  lea     r8, WPP_f3ba224ca5d536188ece76512abbdd99_Traceguids
0x18001187e  mov     rcx, [rcx+10h]
0x180011882  call    WPP_SF_sd
0x180011887  nop
0x180011888  mov     dword ptr [rsp+0D8h+Data], edi
0x18001188f  mov     [rsp+0D8h+Type], edi
0x180011896  mov     [rsp+0D8h+var_78], rsi
0x18001189b  mov     [rsp+0D8h+var_70], rdi
0x1800118a0  mov     [rsp+0D8h+var_68], 0
0x1800118a9  mov     eax, [rsp+0D8h+var_38]
0x1800118b0  test    eax, eax
0x1800118b2  jz      short loc_1800118C9
0x1800118b4  mov     [rsp+0D8h+var_84], eax
0x1800118b8  lea     rdx, _TI1K; pThrowInfo
0x1800118bf  lea     rcx, [rsp+0D8h+var_84]; pExceptionObject
0x1800118c4  call    _CxxThrowException_0
0x1800118c9  mov     [rsp+0D8h+cbData], 4
0x1800118d4  lea     rax, [rsp+0D8h+cbData]
0x1800118dc  mov     [rsp+0D8h+lpcbData], rax; lpcbData
0x1800118e1  lea     rax, [rsp+0D8h+Data]
0x1800118e9  mov     [rsp+0D8h+phkResult], rax; lpData
0x1800118ee  lea     r9, [rsp+0D8h+Type]; lpType
0x1800118f6  xor     r8d, r8d; lpReserved
0x1800118f9  mov     rdx, cs:off_180038100; lpValueName
0x180011900  mov     rcx, [rsp+0D8h+hKey]; hKey
0x180011905  call    cs:__imp_RegQueryValueExW
0x18001190b  test    eax, eax
0x18001190d  jz      short loc_180011924
0x18001190f  mov     [rsp+0D8h+var_80], eax
0x180011913  lea     rdx, _TI1K; pThrowInfo
0x18001191a  lea     rcx, [rsp+0D8h+var_80]; pExceptionObject
0x18001191f  call    _CxxThrowException_0
0x180011924  mov     eax, [rsp+0D8h+Type]
0x18001192b  sub     eax, 4
0x18001192e  jz      short loc_18001195C
0x180011930  cmp     eax, 1
0x180011933  jz      short loc_18001194E
0x180011935  mov     [rsp+0D8h+var_7C], 0Bh
0x18001193d  lea     rdx, _TI1K; pThrowInfo
0x180011944  lea     rcx, [rsp+0D8h+var_7C]; pExceptionObject
0x180011949  call    _CxxThrowException_0
0x18001194e  mov     ecx, dword ptr [rsp+0D8h+Data]
0x180011955  call    HTONL
0x18001195a  jmp     short loc_180011963
0x18001195c  mov     eax, dword ptr [rsp+0D8h+Data]
0x180011963  mov     cs:?g_dwTransactionTimeoutDelay@@3KA, eax; ulong g_dwTransactionTimeoutDelay
0x180011969  test    eax, eax
0x18001196b  jnz     short loc_180011976
0x18001196d  mov     cs:?g_fDisableTransactionTimeoutDelay@@3_NA, 1; bool g_fDisableTransactionTimeoutDelay
0x180011974  jmp     short loc_180011996
0x180011976  cmp     eax, 5
0x180011979  jnb     short loc_180011987
0x18001197b  mov     cs:?g_dwTransactionTimeoutDelay@@3KA, 5; ulong g_dwTransactionTimeoutDelay
0x180011985  jmp     short loc_180011996
  ... truncated ...
```

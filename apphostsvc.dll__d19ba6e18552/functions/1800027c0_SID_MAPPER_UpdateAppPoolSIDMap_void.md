# SID_MAPPER::UpdateAppPoolSIDMap(void)

- ea: `0x1800027c0`
- end: `0x180002b45`
- name: `?UpdateAppPoolSIDMap@SID_MAPPER@@AEAAJXZ`
- size: `901`
- prototype: `__int64 __fastcall(SID_MAPPER *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180002600`

## callees

- `0x180002348`
- `0x1800024ac`
- `0x1800027c0`
- `0x180007878`
- `0x18000821c`
- `0x180008314`
- `0x180008c50`
- `0x18000a010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180002b1d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002b1d`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002827`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180002827`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002ac6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002ac6`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800029bf`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180002b12`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800029bf`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180002b12`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002816`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180002816`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x18000283e`
- `nativerd!GetDefaultNativeConfigurationSystem` at `0x18000283e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SID_MAPPER::UpdateAppPoolSIDMap(SID_MAPPER *this)
{
  unsigned int v2; // r15d
  signed int DefaultNativeConfigurationSystem; // ebx
  int v4; // edi
  BOOL v5; // r14d
  int v6; // eax
  unsigned int v7; // edx
  unsigned int v9; // [rsp+30h] [rbp-69h] BYREF
  __int64 v10; // [rsp+38h] [rbp-61h] BYREF
  __int64 v11; // [rsp+40h] [rbp-59h] BYREF
  __int64 v12; // [rsp+48h] [rbp-51h] BYREF
  __int64 v13; // [rsp+50h] [rbp-49h] BYREF
  struct INativeConfigurationSystem *v14; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 *v15; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int16 *v16; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v17[32]; // [rsp+70h] [rbp-29h] BYREF
  _WORD *v18; // [rsp+90h] [rbp-9h]
  int v19; // [rsp+A0h] [rbp+7h]

  v2 = 0;
  DefaultNativeConfigurationSystem = 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  v11 = 0;
  v10 = 0;
  v9 = 0;
  v4 = 0;
  v5 = 0;
  v15 = 0;
  STRU::STRU((STRU *)v17);
  CReaderWriterLock3::WriteLock((SID_MAPPER *)((char *)this + 184));
  if ( *((_DWORD *)this + 48) != 1 )
  {
    DefaultNativeConfigurationSystem = GetDefaultNativeConfigurationSystem(&v14);
    if ( DefaultNativeConfigurationSystem < 0 )
      goto LABEL_3;
    DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, const wchar_t *, __int64 *, _QWORD))(*(_QWORD *)v14 + 88LL))(
                                         v14,
                                         L"MACHINE/WEBROOT/APPHOST",
                                         &v13,
                                         0);
    if ( DefaultNativeConfigurationSystem < 0 )
      goto LABEL_3;
    DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, _QWORD))(*(_QWORD *)v13 + 64LL))(
                                         v13,
                                         L"system.applicationHost/applicationPools",
                                         L"MACHINE/WEBROOT/APPHOST",
                                         &v12,
                                         0);
    if ( DefaultNativeConfigurationSystem < 0 )
      goto LABEL_3;
    DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 40LL))(
                                         v12,
                                         &v11);
    if ( DefaultNativeConfigurationSystem < 0 )
      goto LABEL_3;
    DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v11 + 24LL))(
                                         v11,
                                         &v9);
    if ( DefaultNativeConfigurationSystem < 0 )
      goto LABEL_3;
    if ( !v9 )
      goto LABEL_26;
    DefaultNativeConfigurationSystem = APP_POOL_HASH_MAPPER::SetAllAppPoolsForDeletion((SID_MAPPER *)((char *)this + 32));
    if ( DefaultNativeConfigurationSystem < 0 )
    {
LABEL_3:
      v4 = 1;
      goto LABEL_26;
    }
    if ( v9 )
    {
      while ( 1 )
      {
        DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v11 + 32LL))(
                                             v11,
                                             v2,
                                             &v10);
        if ( DefaultNativeConfigurationSystem < 0 )
          break;
        DefaultNativeConfigurationSystem = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v10 + 64LL))(
                                             v10,
                                             L"name",
                                             &v15,
                                             0,
                                             0);
        if ( DefaultNativeConfigurationSystem < 0 )
          break;
        *v18 = 0;
        v19 = 0;
        DefaultNativeConfigurationSystem = APP_POOL_HASH_MAPPER::CheckAndAddAppPool(
                                             (SID_MAPPER *)((char *)this + 32),
                                             v15,
                                             (struct STRU *)v17);
        if ( (int)(DefaultNativeConfigurationSystem + 0x80000000) >= 0
          && DefaultNativeConfigurationSystem != -2147024844 )
        {
          if ( DefaultNativeConfigurationSystem != -2147022882 )
          {
            v5 = 1;
            goto LABEL_26;
          }
          v16 = v15;
          EVENT_LOG::LogEvent(
            (APP_HOST_SERVICE *)((char *)g_pAppHostService + 136),
            0xC0002329,
            1u,
            (const unsigned __int16 **const)&v16,
            0x800707DE);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        v10 = 0;
        if ( ++v2 >= v9 )
          goto LABEL_18;
      }
      v4 = 1;
    }
    else
    {
LABEL_18:
      v6 = SID_MAPPER::DoDeleteMappings(this);
      DefaultNativeConfigurationSystem = v6;
      if ( v6 < 0 || (v6 = SID_MAPPER::DoAddMappings(this), DefaultNativeConfigurationSystem = v6, v6 < 0) )
      {
        v5 = v6 != -2147467259;
      }
      else
      {
        DefaultNativeConfigurationSystem = APP_POOL_HASH_MAPPER::ResetStateFlags((SID_MAPPER *)((char *)this + 32));
        if ( DefaultNativeConfigurationSystem >= 0 )
          *((_DWORD *)this + 49) = 0;
        else
          v5 = 1;
      }
    }
  }
LABEL_26:
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v10 = 0;
  }
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  CReaderWriterLock3::WriteUnlock((SID_MAPPER *)((char *)this + 184));
  if ( DefaultNativeConfigurationSystem < 0 && !*((_DWORD *)this + 49) )
  {
    *((_DWORD *)this + 49) = 1;
    if ( v4 == 1 )
    {
      v7 = -1073732824;
LABEL_42:
      EVENT_LOG::LogEvent(
        (APP_HOST_SERVICE *)((char *)g_pAppHostService + 136),
        v7,
        0,
        0,
        DefaultNativeConfigurationSystem);
      goto LABEL_43;
    }
    if ( v5 )
    {
      v7 = -1073732822;
      goto LABEL_42;
    }
  }
LABEL_43:
  STRU::~STRU((STRU *)v17);
  return (unsigned int)DefaultNativeConfigurationSystem;
}

```

## disassembly

```asm
0x1800027c0  push    rbp
0x1800027c2  push    rbx
0x1800027c3  push    rsi
0x1800027c4  push    rdi
0x1800027c5  push    r12
0x1800027c7  push    r13
0x1800027c9  push    r14
0x1800027cb  push    r15
0x1800027cd  lea     rbp, [rsp-1Fh]
0x1800027d2  sub     rsp, 0B8h
0x1800027d9  mov     rax, cs:__security_cookie
0x1800027e0  xor     rax, rsp
0x1800027e3  mov     [rbp+57h+var_48], rax
0x1800027e7  mov     rsi, rcx
0x1800027ea  xor     r15d, r15d
0x1800027ed  mov     ebx, r15d
0x1800027f0  mov     [rbp+57h+var_98], r15
0x1800027f4  mov     [rbp+57h+var_A0], r15
0x1800027f8  mov     [rbp+57h+var_A8], r15
0x1800027fc  mov     [rbp+57h+var_B0], r15
0x180002800  mov     [rbp+57h+var_B8], r15
0x180002804  mov     [rbp+57h+var_C0], r15d
0x180002808  mov     edi, r15d
0x18000280b  mov     r14d, r15d
0x18000280e  mov     [rbp+57h+var_90], r15
0x180002812  lea     rcx, [rbp+57h+var_80]
0x180002816  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000281c  nop
0x18000281d  lea     r13, [rsi+0B8h]
0x180002824  mov     rcx, r13
0x180002827  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000282d  cmp     dword ptr [rsi+0C0h], 1
0x180002834  jz      loc_180002A46
0x18000283a  lea     rcx, [rbp+57h+var_98]
0x18000283e  call    cs:__imp_?GetDefaultNativeConfigurationSystem@@YAJPEAPEAVINativeConfigurationSystem@@@Z; GetDefaultNativeConfigurationSystem(INativeConfigurationSystem * *)
0x180002844  mov     ebx, eax
0x180002846  test    eax, eax
0x180002848  jns     short loc_180002854
0x18000284a  mov     edi, 1
0x18000284f  jmp     loc_180002A46
0x180002854  mov     rcx, [rbp+57h+var_98]
0x180002858  mov     rax, [rcx]
0x18000285b  xor     r9d, r9d
0x18000285e  lea     r8, [rbp+57h+var_A0]
0x180002862  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180002869  mov     rax, [rax+58h]
0x18000286d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002872  mov     ebx, eax
0x180002874  test    eax, eax
0x180002876  js      short loc_18000284A
0x180002878  mov     rcx, [rbp+57h+var_A0]
0x18000287c  mov     rax, [rcx]
0x18000287f  mov     [rsp+0F0h+var_D0], r15
0x180002884  lea     r9, [rbp+57h+var_A8]
0x180002888  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000288f  lea     rdx, aSystemApplicat_0; "system.applicationHost/applicationPools"
0x180002896  mov     rax, [rax+40h]
0x18000289a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000289f  mov     ebx, eax
0x1800028a1  test    eax, eax
0x1800028a3  js      short loc_18000284A
0x1800028a5  mov     rcx, [rbp+57h+var_A8]
0x1800028a9  mov     rax, [rcx]
0x1800028ac  lea     rdx, [rbp+57h+var_B0]
0x1800028b0  mov     rax, [rax+28h]
0x1800028b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028b9  mov     ebx, eax
0x1800028bb  test    eax, eax
0x1800028bd  js      short loc_18000284A
0x1800028bf  mov     rcx, [rbp+57h+var_B0]
0x1800028c3  mov     rax, [rcx]
0x1800028c6  lea     rdx, [rbp+57h+var_C0]
0x1800028ca  mov     rax, [rax+18h]
0x1800028ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d3  mov     ebx, eax
0x1800028d5  test    eax, eax
0x1800028d7  js      loc_18000284A
0x1800028dd  cmp     [rbp+57h+var_C0], r15d
0x1800028e1  jz      loc_180002A46
0x1800028e7  lea     r12, [rsi+20h]
0x1800028eb  mov     rcx, r12; this
0x1800028ee  call    ?SetAllAppPoolsForDeletion@APP_POOL_HASH_MAPPER@@QEAAJXZ; APP_POOL_HASH_MAPPER::SetAllAppPoolsForDeletion(void)
0x1800028f3  mov     ebx, eax
0x1800028f5  test    eax, eax
0x1800028f7  js      loc_18000284A
0x1800028fd  cmp     [rbp+57h+var_C0], 0
0x180002901  jbe     loc_1800029EA
0x180002907  mov     rcx, [rbp+57h+var_B0]
0x18000290b  mov     rax, [rcx]
0x18000290e  lea     r8, [rbp+57h+var_B8]
0x180002912  mov     edx, r15d
0x180002915  mov     rax, [rax+20h]
0x180002919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000291e  mov     ebx, eax
0x180002920  test    eax, eax
0x180002922  js      loc_180002A11
0x180002928  mov     rcx, [rbp+57h+var_B8]
0x18000292c  mov     rax, [rcx]
0x18000292f  mov     [rsp+0F0h+var_D0], 0
0x180002938  xor     r9d, r9d
0x18000293b  lea     r8, [rbp+57h+var_90]
0x18000293f  lea     rdx, aName; "name"
0x180002946  mov     rax, [rax+40h]
0x18000294a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000294f  mov     ebx, eax
0x180002951  test    eax, eax
0x180002953  js      loc_180002A11
0x180002959  xor     ecx, ecx
0x18000295b  mov     rax, [rbp+57h+var_60]
0x18000295f  mov     [rax], cx
0x180002962  mov     [rbp+57h+var_50], ecx
0x180002965  lea     r8, [rbp+57h+var_80]; struct STRU *
0x180002969  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x18000296d  mov     rcx, r12; this
0x180002970  call    ?CheckAndAddAppPool@APP_POOL_HASH_MAPPER@@QEAAJPEBGPEAVSTRU@@@Z; APP_POOL_HASH_MAPPER::CheckAndAddAppPool(ushort const *,STRU *)
0x180002975  mov     ebx, eax
0x180002977  mov     ecx, 80000000h
0x18000297c  add     eax, ecx
0x18000297e  test    ecx, eax
0x180002980  jnz     short loc_1800029C5
0x180002982  cmp     ebx, 80070034h
0x180002988  jz      short loc_1800029C5
0x18000298a  cmp     ebx, 800707DEh
0x180002990  jnz     short loc_180002A09
0x180002992  mov     rax, [rbp+57h+var_90]
0x180002996  mov     [rbp+57h+var_88], rax
0x18000299a  mov     r8d, 1
0x1800029a0  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x1800029a7  add     rcx, 88h
0x1800029ae  mov     dword ptr [rsp+0F0h+var_D0], 800707DEh
0x1800029b6  lea     r9, [rbp+57h+var_88]
0x1800029ba  mov     edx, 0C0002329h
0x1800029bf  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800029c5  mov     rcx, [rbp+57h+var_B8]
0x1800029c9  mov     rax, [rcx]
0x1800029cc  mov     rax, [rax+10h]
0x1800029d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d5  mov     [rbp+57h+var_B8], 0
0x1800029dd  inc     r15d
0x1800029e0  cmp     r15d, [rbp+57h+var_C0]
0x1800029e4  jb      loc_180002907
0x1800029ea  mov     rcx, rsi; this
0x1800029ed  call    ?DoDeleteMappings@SID_MAPPER@@AEAAJXZ; SID_MAPPER::DoDeleteMappings(void)
0x1800029f2  mov     ebx, eax
0x1800029f4  xor     r15d, r15d
0x1800029f7  test    eax, eax
0x1800029f9  jns     short loc_180002A1B
0x1800029fb  mov     r14d, r15d
0x1800029fe  cmp     eax, 80004005h
0x180002a03  setnz   r14b
0x180002a07  jmp     short loc_180002A46
0x180002a09  mov     r14d, 1
0x180002a0f  jmp     short loc_180002A16
0x180002a11  mov     edi, 1
0x180002a16  xor     r15d, r15d
0x180002a19  jmp     short loc_180002A46
0x180002a1b  mov     rcx, rsi; this
0x180002a1e  call    ?DoAddMappings@SID_MAPPER@@AEAAJXZ; SID_MAPPER::DoAddMappings(void)
0x180002a23  mov     ebx, eax
0x180002a25  test    eax, eax
0x180002a27  js      short loc_1800029FB
0x180002a29  mov     rcx, r12; this
0x180002a2c  call    ?ResetStateFlags@APP_POOL_HASH_MAPPER@@QEAAJXZ; APP_POOL_HASH_MAPPER::ResetStateFlags(void)
0x180002a31  mov     ebx, eax
0x180002a33  test    eax, eax
0x180002a35  jns     short loc_180002A3F
0x180002a37  mov     r14d, 1
0x180002a3d  jmp     short loc_180002A46
0x180002a3f  mov     [rsi+0C4h], r15d
0x180002a46  mov     rcx, [rbp+57h+var_B8]
0x180002a4a  test    rcx, rcx
0x180002a4d  jz      short loc_180002A5F
0x180002a4f  mov     rax, [rcx]
0x180002a52  mov     rax, [rax+10h]
0x180002a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a5b  mov     [rbp+57h+var_B8], r15
0x180002a5f  mov     rcx, [rbp+57h+var_B0]
0x180002a63  test    rcx, rcx
0x180002a66  jz      short loc_180002A78
0x180002a68  mov     rax, [rcx]
0x180002a6b  mov     rax, [rax+10h]
0x180002a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a74  mov     [rbp+57h+var_B0], r15
0x180002a78  mov     rcx, [rbp+57h+var_A8]
0x180002a7c  test    rcx, rcx
0x180002a7f  jz      short loc_180002A91
0x180002a81  mov     rax, [rcx]
0x180002a84  mov     rax, [rax+10h]
0x180002a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a8d  mov     [rbp+57h+var_A8], r15
0x180002a91  mov     rcx, [rbp+57h+var_A0]
0x180002a95  test    rcx, rcx
0x180002a98  jz      short loc_180002AAA
0x180002a9a  mov     rax, [rcx]
0x180002a9d  mov     rax, [rax+10h]
0x180002aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa6  mov     [rbp+57h+var_A0], r15
0x180002aaa  mov     rcx, [rbp+57h+var_98]
0x180002aae  test    rcx, rcx
0x180002ab1  jz      short loc_180002AC3
0x180002ab3  mov     rax, [rcx]
0x180002ab6  mov     rax, [rax+10h]
0x180002aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002abf  mov     [rbp+57h+var_98], r15
0x180002ac3  mov     rcx, r13
0x180002ac6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180002acc  test    ebx, ebx
0x180002ace  jns     short loc_180002B19
0x180002ad0  cmp     [rsi+0C4h], r15d
0x180002ad7  jnz     short loc_180002B19
0x180002ad9  mov     dword ptr [rsi+0C4h], 1
0x180002ae3  cmp     edi, 1
0x180002ae6  jnz     short loc_180002AEF
0x180002ae8  mov     edx, 0C0002328h
0x180002aed  jmp     short loc_180002AFA
0x180002aef  cmp     r14d, 1
0x180002af3  jnz     short loc_180002B19
0x180002af5  mov     edx, 0C000232Ah
0x180002afa  mov     rcx, cs:?g_pAppHostService@@3PEAVAPP_HOST_SERVICE@@EA; APP_HOST_SERVICE * g_pAppHostService
0x180002b01  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x180002b05  xor     r9d, r9d
0x180002b08  xor     r8d, r8d
0x180002b0b  add     rcx, 88h
0x180002b12  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180002b18  nop
0x180002b19  lea     rcx, [rbp+57h+var_80]
0x180002b1d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002b23  mov     eax, ebx
0x180002b25  mov     rcx, [rbp+57h+var_48]
0x180002b29  xor     rcx, rsp; StackCookie
0x180002b2c  call    __security_check_cookie
0x180002b31  add     rsp, 0B8h
0x180002b38  pop     r15
0x180002b3a  pop     r14
0x180002b3c  pop     r13
0x180002b3e  pop     r12
0x180002b40  pop     rdi
0x180002b41  pop     rsi
0x180002b42  pop     rbx
0x180002b43  pop     rbp
0x180002b44  retn
```

# CInterceptor_IWbemSyncProvider::TrackingOperation(unsigned __int64 &,ushort *)

- ea: `0x14000d9e4`
- end: `0x14000de83`
- name: `?TrackingOperation@CInterceptor_IWbemSyncProvider@@QEAAHAEA_KPEAG@Z`
- size: `1183`
- prototype: `_BOOL8 __fastcall(CInterceptor_IWbemSyncProvider *this, unsigned __int64 *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000c850`
- `0x14000d5fc`
- `0x14000d780`
- `0x14000e738`

## callees

- `0x14000212c`
- `0x14000a414`
- `0x14000a530`
- `0x14000d9e4`
- `0x14000f600`
- `0x140020820`
- `0x1400209a0`
- `0x140022508`
- `0x140029d34`
- `0x14002a55c`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x14000da2c`
- `msvcrt!_ui64tow_s` at `0x14000dcff`
- `msvcrt!_ui64tow_s` at `0x14000da2c`
- `msvcrt!_ui64tow_s` at `0x14000dcff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000db8f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000dbdd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000dc30`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000dc64`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000dcd7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000db8f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000dbdd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000dc30`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000dc64`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14000dcd7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000dd2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000dd2c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x14000de07`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x14000de24`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x14000de07`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongLongCounterValue` at `0x14000de24`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14000ddd1`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14000ddec`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14000ddd1`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetULongCounterValue` at `0x14000ddec`
- `OLEAUT32!__imp_SysStringLen` at `0x14000dd0a`
- `OLEAUT32!__imp_SysStringLen` at `0x14000dd0a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14000dd5a`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14000dd5a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14000dd65`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14000dd65`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14000db48`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14000dc96`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14000db48`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x14000dc96`

## pseudocode

```c
_BOOL8 __fastcall CInterceptor_IWbemSyncProvider::TrackingOperation(
        CInterceptor_IWbemSyncProvider *this,
        unsigned __int64 *a2,
        unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r14
  _bstr_t::Data_t *v6; // rax
  _bstr_t::Data_t *v7; // rax
  HKEY v8; // rbx
  LSTATUS v9; // edi
  unsigned int v10; // edx
  unsigned int v11; // edx
  _bstr_t::Data_t *v12; // rcx
  BOOL v13; // r13d
  int v14; // r14d
  HKEY v15; // rbx
  const WCHAR **v16; // rax
  const WCHAR *v17; // rdx
  HKEY v18; // rbx
  LSTATUS ValueW; // eax
  UINT v20; // eax
  _QWORD *v21; // r14
  _bstr_t::Data_t *v22; // rbx
  UINT v23; // eax
  BSTR v24; // rax
  DWORD pdwType; // [rsp+40h] [rbp-59h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-51h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-49h] BYREF
  _bstr_t::Data_t *v29; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 *v30; // [rsp+60h] [rbp-39h] BYREF
  HKEY v31; // [rsp+68h] [rbp-31h] BYREF
  wchar_t Buffer[32]; // [rsp+70h] [rbp-29h] BYREF

  v3 = a3;
  v30 = a3;
  _ui64tow_s(*a2, Buffer, 0x1Eu, 10);
  v6 = (_bstr_t::Data_t *)operator new(0x18u);
  v29 = v6;
  if ( v6 )
    v6 = (_bstr_t::Data_t *)_bstr_t::Data_t::Data_t(v6, Buffer);
  v29 = v6;
  if ( !v6 )
    _com_issue_error(-2147024882);
  v7 = (_bstr_t::Data_t *)operator new(0x18u);
  phkResult = (HKEY)v7;
  if ( v7 )
    v8 = (HKEY)_bstr_t::Data_t::Data_t(v7, L": ");
  else
    v8 = 0;
  phkResult = v8;
  if ( !v8 )
LABEL_40:
    _com_issue_error(-2147024882);
  v9 = 0;
  _bstr_t::operator+=(&v29, &phkResult);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 4, 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'((_bstr_t::Data_t *)v8, v10);
  _bstr_t::_bstr_t((_bstr_t *)&phkResult, v3);
  _bstr_t::operator+=(&v29, &phkResult);
  v12 = (_bstr_t::Data_t *)phkResult;
  if ( phkResult && _InterlockedExchangeAdd((volatile signed __int32 *)phkResult + 4, 0xFFFFFFFF) == 1 && v12 )
    _bstr_t::Data_t::`scalar deleting destructor'(v12, v11);
  v13 = 0;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 29) + 48LL))((char *)this + 232);
  if ( *((_DWORD *)this + 145) )
  {
    phkResult = 0;
    pdwType = 0;
    pcbData = 4;
    if ( !RegOpenKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WBEM\\Tracing\\Providers", &phkResult) )
    {
      v14 = *((_DWORD *)this + 147);
      v15 = phkResult;
      v31 = phkResult;
      RegGetValueW(phkResult, 0, L"PerfLibEnabled", 0x10u, &pdwType, (char *)this + 588, &pcbData);
      v13 = !*((_DWORD *)this + 147) && v14;
      if ( !RegGetValueW(phkResult, 0, L"PerfLibInterval_ms", 0x10u, &pdwType, &qword_140060940, &pcbData) )
        qword_140060940 *= 10000;
      if ( *((_DWORD *)this + 145) )
      {
        RegGetValueW(phkResult, 0, L"IsToCleanupTraces", 0x10u, &pdwType, (char *)this + 576, &pcbData);
        RegGetValueW(phkResult, 0, L"IsTrackingOperationOnly", 0x10u, &pdwType, (char *)this + 584, &pcbData);
      }
      DLRegCloseKey(v15);
      v3 = v30;
    }
    v16 = (const WCHAR **)*((_QWORD *)this + 71);
    if ( v16 )
      v17 = *v16;
    else
      v17 = 0;
    v9 = RegOpenKeyW(HKEY_LOCAL_MACHINE, v17, &phkResult);
    v18 = phkResult;
    v31 = phkResult;
    while ( !v9 )
    {
      ValueW = RegGetValueW(phkResult, 0, Buffer, 2u, 0, 0, 0);
      v9 = ValueW;
      if ( ValueW == 2 )
      {
        v20 = SysStringLen(v3);
        v9 = RegSetValueExW(phkResult, Buffer, 0, 1u, (const BYTE *)v3, 2 * v20);
        break;
      }
      if ( !ValueW )
        _ui64tow_s(_InterlockedIncrement64((volatile signed __int64 *)a2), Buffer, 0x1Eu, 10);
    }
    DLRegCloseKey(v18);
  }
  v21 = (_QWORD *)*((_QWORD *)this + 69);
  v22 = v29;
  if ( v21 )
  {
    if ( v29 && *(_QWORD *)v29 )
    {
      v23 = SysStringByteLen(*(BSTR *)v29);
      v24 = SysAllocStringByteLen(*(LPCSTR *)v22, v23);
      if ( !v24 )
        goto LABEL_40;
    }
    else
    {
      v24 = 0;
    }
    v30 = v24;
    if ( *v21 )
      WmiBasicTree<unsigned __int64,unsigned short *>::Insert(*v21 + 24LL * (*(_DWORD *)a2 & 3), a2, &v30, &v31);
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 29) + 56LL))((char *)this + 232);
  if ( v13 )
  {
    PerfSetULongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 2u, 0);
    PerfSetULongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 3u, 0);
    PerfSetULongLongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 4u, 0);
  }
  PerfSetULongLongCounterValue(WmiprvSePerfCounter, *((PPERF_COUNTERSET_INSTANCE *)this + 68), 0xBu, *a2);
  CInterceptor_IWbemSyncProvider::RefreshCPURawData(this);
  if ( v22 && _InterlockedExchangeAdd((volatile signed __int32 *)v22 + 4, 0xFFFFFFFF) == 1 )
    _bstr_t::Data_t::`scalar deleting destructor'(v22, 1u);
  return v9 == 0;
}

```

## disassembly

```asm
0x14000d9e4  mov     [rsp-8+arg_18], rbx
0x14000d9e9  push    rbp
0x14000d9ea  push    rsi
0x14000d9eb  push    rdi
0x14000d9ec  push    r12
0x14000d9ee  push    r13
0x14000d9f0  push    r14
0x14000d9f2  push    r15
0x14000d9f4  lea     rbp, [rsp-27h]
0x14000d9f9  sub     rsp, 0C0h
0x14000da00  mov     rax, cs:__security_cookie
0x14000da07  xor     rax, rsp
0x14000da0a  mov     [rbp+57h+var_40], rax
0x14000da0e  mov     r14, r8
0x14000da11  mov     [rbp+57h+var_90], r8
0x14000da15  mov     r15, rdx
0x14000da18  mov     rsi, rcx
0x14000da1b  mov     r9d, 0Ah; Radix
0x14000da21  lea     r8d, [r9+14h]; BufferCount
0x14000da25  lea     rdx, [rbp+57h+Buffer]; Buffer
0x14000da29  mov     rcx, [r15]; Value
0x14000da2c  call    cs:__imp__ui64tow_s
0x14000da32  mov     ebx, 18h
0x14000da37  mov     ecx, ebx; dwBytes
0x14000da39  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000da3e  mov     [rbp+57h+var_98], rax
0x14000da42  test    rax, rax
0x14000da45  jz      short loc_14000DA54
0x14000da47  lea     rdx, [rbp+57h+Buffer]; unsigned __int16 *
0x14000da4b  mov     rcx, rax; this
0x14000da4e  call    ??0Data_t@_bstr_t@@QEAA@PEBG@Z; _bstr_t::Data_t::Data_t(ushort const *)
0x14000da53  nop
0x14000da54  mov     [rbp+57h+var_98], rax
0x14000da58  test    rax, rax
0x14000da5b  jnz     short loc_14000DA68
0x14000da5d  mov     ecx, 8007000Eh; int
0x14000da62  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000da68  mov     rcx, rbx; dwBytes
0x14000da6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000da70  mov     [rbp+57h+phkResult], rax
0x14000da74  test    rax, rax
0x14000da77  jz      short loc_14000DA8D
0x14000da79  lea     rdx, asc_140052E88; ": "
0x14000da80  mov     rcx, rax; this
0x14000da83  call    ??0Data_t@_bstr_t@@QEAA@PEBG@Z; _bstr_t::Data_t::Data_t(ushort const *)
0x14000da88  mov     rbx, rax
0x14000da8b  jmp     short loc_14000DA8F
0x14000da8d  xor     ebx, ebx
0x14000da8f  mov     [rbp+57h+phkResult], rbx
0x14000da93  test    rbx, rbx
0x14000da96  jz      loc_14000DD70
0x14000da9c  xor     edi, edi
0x14000da9e  lea     rdx, [rbp+57h+phkResult]
0x14000daa2  lea     rcx, [rbp+57h+var_98]
0x14000daa6  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x14000daab  nop
0x14000daac  or      r12d, 0FFFFFFFFh
0x14000dab0  mov     eax, r12d
0x14000dab3  lock xadd [rbx+10h], eax
0x14000dab8  add     eax, r12d
0x14000dabb  jnz     short loc_14000DAC5
0x14000dabd  mov     rcx, rbx; this
0x14000dac0  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x14000dac5  mov     rdx, r14; unsigned __int16 *
0x14000dac8  lea     rcx, [rbp+57h+phkResult]; this
0x14000dacc  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x14000dad1  nop
0x14000dad2  lea     rdx, [rbp+57h+phkResult]
0x14000dad6  lea     rcx, [rbp+57h+var_98]
0x14000dada  call    ??Y_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator+=(_bstr_t const &)
0x14000dadf  nop
0x14000dae0  mov     rcx, [rbp+57h+phkResult]; this
0x14000dae4  test    rcx, rcx
0x14000dae7  jz      short loc_14000DB00
0x14000dae9  mov     eax, r12d
0x14000daec  lock xadd [rcx+10h], eax
0x14000daf1  add     eax, r12d
0x14000daf4  jnz     short loc_14000DB00
0x14000daf6  test    rcx, rcx
0x14000daf9  jz      short loc_14000DB00
0x14000dafb  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x14000db00  xor     r13d, r13d
0x14000db03  lea     r12, [rsi+0E8h]
0x14000db0a  mov     rax, [r12]
0x14000db0e  mov     rcx, r12
0x14000db11  mov     rax, [rax+30h]
0x14000db15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db1a  cmp     [rsi+244h], r13d
0x14000db21  jz      loc_14000DD3D
0x14000db27  mov     [rbp+57h+phkResult], r13
0x14000db2b  mov     [rbp+57h+var_B0], r13d
0x14000db2f  mov     [rbp+57h+var_A0], 4
0x14000db36  lea     r8, [rbp+57h+phkResult]; phkResult
0x14000db3a  lea     rdx, SubKey; "Software\\Microsoft\\WBEM\\Tracing\\Pro"...
0x14000db41  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000db48  call    cs:__imp_RegOpenKeyW
0x14000db4e  test    eax, eax
0x14000db50  jnz     loc_14000DC78
0x14000db56  lea     rdi, [rsi+24Ch]
0x14000db5d  mov     r14d, [rdi]
0x14000db60  mov     rbx, [rbp+57h+phkResult]
0x14000db64  mov     [rbp+57h+var_88], rbx
0x14000db68  lea     rax, [rbp+57h+var_A0]
0x14000db6c  mov     [rsp+0F0h+pcbData], rax; pcbData
0x14000db71  mov     [rsp+0F0h+pvData], rdi; pvData
0x14000db76  lea     rax, [rbp+57h+var_B0]
0x14000db7a  mov     [rsp+0F0h+pdwType], rax; pdwType
0x14000db7f  lea     r9d, [r13+10h]; dwFlags
0x14000db83  lea     r8, Value; "PerfLibEnabled"
0x14000db8a  xor     edx, edx; lpSubKey
0x14000db8c  mov     rcx, rbx; hkey
0x14000db8f  call    cs:__imp_RegGetValueW
0x14000db95  cmp     [rdi], r13d
0x14000db98  jnz     short loc_14000DBA7
0x14000db9a  test    r14d, r14d
0x14000db9d  jz      short loc_14000DBA7
0x14000db9f  mov     r13d, 1
0x14000dba5  jmp     short loc_14000DBAA
0x14000dba7  xor     r13d, r13d
0x14000dbaa  lea     rax, [rbp+57h+var_A0]
0x14000dbae  mov     [rsp+0F0h+pcbData], rax; pcbData
0x14000dbb3  lea     rax, qword_140060940
0x14000dbba  mov     [rsp+0F0h+pvData], rax; pvData
0x14000dbbf  lea     rax, [rbp+57h+var_B0]
0x14000dbc3  mov     [rsp+0F0h+pdwType], rax; pdwType
0x14000dbc8  mov     edi, 10h
0x14000dbcd  mov     r9d, edi; dwFlags
0x14000dbd0  lea     r8, aPerflibinterva; "PerfLibInterval_ms"
0x14000dbd7  xor     edx, edx; lpSubKey
0x14000dbd9  mov     rcx, [rbp+57h+phkResult]; hkey
0x14000dbdd  call    cs:__imp_RegGetValueW
0x14000dbe3  test    eax, eax
0x14000dbe5  jnz     short loc_14000DBF9
0x14000dbe7  imul    rax, cs:qword_140060940, 2710h
0x14000dbf2  mov     cs:qword_140060940, rax
0x14000dbf9  cmp     dword ptr [rsi+244h], 0
0x14000dc00  jz      short loc_14000DC6B
0x14000dc02  lea     rax, [rsi+240h]
0x14000dc09  lea     rcx, [rbp+57h+var_A0]
0x14000dc0d  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x14000dc12  mov     [rsp+0F0h+pvData], rax; pvData
0x14000dc17  lea     rax, [rbp+57h+var_B0]
0x14000dc1b  mov     [rsp+0F0h+pdwType], rax; pdwType
0x14000dc20  mov     r9d, edi; dwFlags
0x14000dc23  lea     r8, aIstocleanuptra; "IsToCleanupTraces"
0x14000dc2a  xor     edx, edx; lpSubKey
0x14000dc2c  mov     rcx, [rbp+57h+phkResult]; hkey
0x14000dc30  call    cs:__imp_RegGetValueW
0x14000dc36  lea     rax, [rsi+248h]
0x14000dc3d  lea     rcx, [rbp+57h+var_A0]
0x14000dc41  mov     [rsp+0F0h+pcbData], rcx; pcbData
0x14000dc46  mov     [rsp+0F0h+pvData], rax; pvData
0x14000dc4b  lea     rax, [rbp+57h+var_B0]
0x14000dc4f  mov     [rsp+0F0h+pdwType], rax; pdwType
0x14000dc54  mov     r9d, edi; dwFlags
0x14000dc57  lea     r8, aIstrackingoper; "IsTrackingOperationOnly"
0x14000dc5e  xor     edx, edx; lpSubKey
0x14000dc60  mov     rcx, [rbp+57h+phkResult]; hkey
0x14000dc64  call    cs:__imp_RegGetValueW
0x14000dc6a  nop
0x14000dc6b  mov     rcx, rbx
0x14000dc6e  call    DLRegCloseKey
0x14000dc73  nop
0x14000dc74  mov     r14, [rbp+57h+var_90]
0x14000dc78  mov     rax, [rsi+238h]
0x14000dc7f  test    rax, rax
0x14000dc82  jz      short loc_14000DC89
0x14000dc84  mov     rdx, [rax]
0x14000dc87  jmp     short loc_14000DC8B
0x14000dc89  xor     edx, edx; lpSubKey
0x14000dc8b  lea     r8, [rbp+57h+phkResult]; phkResult
0x14000dc8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000dc96  call    cs:__imp_RegOpenKeyW
0x14000dc9c  mov     edi, eax
0x14000dc9e  mov     rbx, [rbp+57h+phkResult]
0x14000dca2  mov     [rbp+57h+var_88], rbx
0x14000dca6  test    edi, edi
0x14000dca8  jnz     loc_14000DD34
0x14000dcae  mov     [rsp+0F0h+pcbData], 0; pcbData
0x14000dcb7  mov     [rsp+0F0h+pvData], 0; pvData
0x14000dcc0  mov     [rsp+0F0h+pdwType], 0; pdwType
0x14000dcc9  lea     r9d, [rdi+2]; dwFlags
0x14000dccd  lea     r8, [rbp+57h+Buffer]; lpValue
0x14000dcd1  xor     edx, edx; lpSubKey
0x14000dcd3  mov     rcx, [rbp+57h+phkResult]; hkey
0x14000dcd7  call    cs:__imp_RegGetValueW
0x14000dcdd  mov     edi, eax
0x14000dcdf  cmp     eax, 2
0x14000dce2  jz      short loc_14000DD07
0x14000dce4  test    eax, eax
0x14000dce6  jnz     short loc_14000DCA6
0x14000dce8  lea     ecx, [rax+1]
0x14000dceb  lock xadd [r15], rcx
0x14000dcf0  inc     rcx; Value
0x14000dcf3  lea     r9d, [rax+0Ah]; Radix
0x14000dcf7  lea     r8d, [rax+1Eh]; BufferCount
0x14000dcfb  lea     rdx, [rbp+57h+Buffer]; Buffer
0x14000dcff  call    cs:__imp__ui64tow_s
0x14000dd05  jmp     short loc_14000DCA6
0x14000dd07  mov     rcx, r14; pbstr
0x14000dd0a  call    cs:__imp_SysStringLen
0x14000dd10  add     eax, eax
0x14000dd12  mov     dword ptr [rsp+0F0h+pvData], eax; cbData
0x14000dd16  mov     [rsp+0F0h+pdwType], r14; lpData
0x14000dd1b  mov     r9d, 1; dwType
0x14000dd21  xor     r8d, r8d; Reserved
0x14000dd24  lea     rdx, [rbp+57h+Buffer]; lpValueName
0x14000dd28  mov     rcx, [rbp+57h+phkResult]; hKey
0x14000dd2c  call    cs:__imp_RegSetValueExW
0x14000dd32  mov     edi, eax
0x14000dd34  mov     rcx, rbx
0x14000dd37  call    DLRegCloseKey
0x14000dd3c  nop
0x14000dd3d  mov     r14, [rsi+228h]
0x14000dd44  mov     rbx, [rbp+57h+var_98]
0x14000dd48  test    r14, r14
0x14000dd4b  jz      short loc_14000DDA7
0x14000dd4d  test    rbx, rbx
0x14000dd50  jz      short loc_14000DD7B
0x14000dd52  mov     rcx, [rbx]; bstr
0x14000dd55  test    rcx, rcx
0x14000dd58  jz      short loc_14000DD7B
0x14000dd5a  call    cs:__imp_SysStringByteLen
0x14000dd60  mov     edx, eax; len
0x14000dd62  mov     rcx, [rbx]; psz
0x14000dd65  call    cs:__imp_SysAllocStringByteLen
0x14000dd6b  test    rax, rax
0x14000dd6e  jnz     short loc_14000DD7D
0x14000dd70  mov     ecx, 8007000Eh; int
0x14000dd75  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x14000dd7b  xor     eax, eax
0x14000dd7d  mov     [rbp+57h+var_90], rax
0x14000dd81  mov     rcx, [r14]
0x14000dd84  test    rcx, rcx
0x14000dd87  jz      short loc_14000DDA7
0x14000dd89  mov     eax, [r15]
0x14000dd8c  and     eax, 3
0x14000dd8f  lea     rax, [rax+rax*2]
0x14000dd93  lea     rcx, [rcx+rax*8]
0x14000dd97  lea     r9, [rbp+57h+var_88]
0x14000dd9b  lea     r8, [rbp+57h+var_90]
0x14000dd9f  mov     rdx, r15
0x14000dda2  call    ?Insert@?$WmiBasicTree@_KPEAG@@QEAA?AW4WmiStatusCode@@AEB_KAEBQEAGAEAVIterator@1@@Z; WmiBasicTree<unsigned __int64,ushort *>::Insert(unsigned __int64 const &,ushort * const &,WmiBasicTree<unsigned __int64,ushort *>::Iterator &)
0x14000dda7  mov     rax, [r12]
0x14000ddab  mov     rcx, r12
0x14000ddae  mov     rax, [rax+38h]
0x14000ddb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ddb7  test    r13d, r13d
0x14000ddba  jz      short loc_14000DE0D
0x14000ddbc  xor     r9d, r9d; Value
0x14000ddbf  lea     r8d, [r9+2]; CounterId
0x14000ddc3  mov     rdx, [rsi+220h]; Instance
0x14000ddca  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14000ddd1  call    cs:__imp_PerfSetULongCounterValue
0x14000ddd7  xor     r9d, r9d; Value
0x14000ddda  lea     r8d, [r9+3]; CounterId
0x14000ddde  mov     rdx, [rsi+220h]; Instance
0x14000dde5  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14000ddec  call    cs:__imp_PerfSetULongCounterValue
0x14000ddf2  xor     r9d, r9d; Value
0x14000ddf5  lea     r8d, [r9+4]; CounterId
0x14000ddf9  mov     rdx, [rsi+220h]; Instance
0x14000de00  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14000de07  call    cs:__imp_PerfSetULongLongCounterValue
0x14000de0d  mov     r9, [r15]; Value
0x14000de10  mov     r8d, 0Bh; CounterId
0x14000de16  mov     rdx, [rsi+220h]; Instance
0x14000de1d  mov     rcx, cs:WmiprvSePerfCounter; Provider
0x14000de24  call    cs:__imp_PerfSetULongLongCounterValue
0x14000de2a  mov     rcx, rsi; this
0x14000de2d  call    ?RefreshCPURawData@CInterceptor_IWbemSyncProvider@@QEAAJXZ; CInterceptor_IWbemSyncProvider::RefreshCPURawData(void)
0x14000de32  nop
0x14000de33  xor     esi, esi
0x14000de35  test    edi, edi
0x14000de37  setz    sil
0x14000de3b  test    rbx, rbx
0x14000de3e  jz      short loc_14000DE5A
0x14000de40  or      edx, 0FFFFFFFFh
0x14000de43  lock xadd [rbx+10h], edx; unsigned int
0x14000de48  cmp     edx, 1
0x14000de4b  jnz     short loc_14000DE5A
0x14000de4d  test    rbx, rbx
0x14000de50  jz      short loc_14000DE5A
0x14000de52  mov     rcx, rbx; this
0x14000de55  call    ??_GData_t@_bstr_t@@AEAAPEAXI@Z; _bstr_t::Data_t::`scalar deleting destructor'(uint)
0x14000de5a  mov     eax, esi
0x14000de5c  mov     rcx, [rbp+57h+var_40]
0x14000de60  xor     rcx, rsp; StackCookie
0x14000de63  call    __security_check_cookie
0x14000de68  mov     rbx, [rsp+0F0h+arg_18]
0x14000de70  add     rsp, 0C0h
0x14000de77  pop     r15
0x14000de79  pop     r14
0x14000de7b  pop     r13
0x14000de7d  pop     r12
0x14000de7f  pop     rdi
0x14000de80  pop     rsi
0x14000de81  pop     rbp
0x14000de82  retn
```

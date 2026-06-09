# WaasMedic::RegGetPersistedRootPath(ushort *,ulong,ushort *,ulong *)

- ea: `0x14001002c`
- end: `0x1400102ea`
- name: `?RegGetPersistedRootPath@WaasMedic@@YAJPEAGK0PEAK@Z`
- size: `702`
- prototype: `__int64 __fastcall(WaasMedic *this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1400102f0`

## callees

- `0x140001ee8`
- `0x140002a30`
- `0x140006e60`
- `0x14000885c`
- `0x14000b470`
- `0x14001002c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400101a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400101a3`
- `ntdll!RtlGetPersistedStateLocation` at `0x14001010b`
- `ntdll!RtlGetPersistedStateLocation` at `0x14001010b`
- `ntdll!RtlNtStatusToDosError` at `0x140010146`
- `ntdll!RtlNtStatusToDosError` at `0x140010146`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400100ce`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1400100ce`

## string_xrefs

- `0x14001011b`: `RegUtil: RtlGetPersistedStateLocation returned: path=%ws, cbRequired=%d, hr=0x%08X`
- `0x14001016b`: `RegUtil: Buffer too small for root path: expecting %d, hr=0x%08X`
- `0x140010188`: `RegUtil: Error retrieving persisted registry key path. hr=0x%08X`
- `0x1400101bb`: `RegUtil: Unexpected root path returned from state separation api: %ws`
- `0x14001026d`: `RegUtil: Failed to generate state separated root key path! hr = 0x%08x`
- `0x1400102ac`: `RegUtil: Failed to generate non-state separated root key path! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegGetPersistedRootPath(
        WaasMedic *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v6; // rcx
  const wchar_t *v7; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebx
  NTSTATUS PersistedStateLocation; // eax
  NTSTATUS v11; // r14d
  signed int v12; // eax
  const wchar_t *v13; // rbx
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // r9
  int v16; // eax
  int v17; // eax
  __int64 v19; // [rsp+20h] [rbp-E0h]
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  const unsigned __int16 *v21; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 near **v22; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v24[528]; // [rsp+60h] [rbp-A0h] BYREF

  v20 = 0;
  if ( a4 )
    *(_DWORD *)a4 = 0;
  if ( a3 )
  {
    v6 = 0x7FFFFFFF;
    v7 = L"WaaSMedic";
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v6;
    }
    while ( v6 );
    v8 = (0x7FFFFFFF - v6) & -(__int64)(v6 != 0);
    if ( v6 )
    {
      if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
      {
        PersistedStateLocation = RtlGetPersistedStateLocation(L"WaaS", 0, L"SYSTEM\\WaaS", 0, v24, 520, &v20);
        LODWORD(v19) = 0;
        v11 = PersistedStateLocation;
        LogLevelW(
          5u,
          L"RegUtil: RtlGetPersistedStateLocation returned: path=%ws, cbRequired=%d, hr=0x%08X",
          v24,
          v20,
          v19);
        if ( a4 )
          *(_DWORD *)a4 = v8 + (v20 >> 1);
        v12 = RtlNtStatusToDosError(v11);
        v9 = v12;
        if ( v12 > 0 )
          v9 = (unsigned __int16)v12 | 0x80070000;
        if ( v9 == -2147024662 )
        {
          LogLevelW(3u, L"RegUtil: Buffer too small for root path: expecting %d, hr=0x%08X", v20);
        }
        else if ( (v9 & 0x80000000) == 0 )
        {
          v13 = L"OSDATA\\SYSTEM\\WaaS";
          if ( (unsigned int)_o__wcsicmp(v24, L"OSDATA\\SYSTEM\\WaaS") )
          {
            LogLevelW(2u, L"RegUtil: Unexpected root path returned from state separation api: %ws", v24);
            v14 = WaasMedic::TelemetryProvider::Provider();
            if ( *(_DWORD *)v14 > 5u
              && (*((_QWORD *)v14 + 2) & 0x400000000000LL) != 0
              && (*((_QWORD *)v14 + 3) & 0x400000000000LL) == *((_QWORD *)v14 + 3) )
            {
              v23 = 0x1000000;
              v21 = (const unsigned __int16 *)v24;
              v22 = &gc_pszVersionString;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                (__int64)v14,
                (__int64)byte_14001A245,
                0x400000000000LL,
                v15,
                (__int64)&v23,
                (const unsigned __int16 **)&v22,
                &v21);
            }
          }
          else
          {
            v13 = (const wchar_t *)v24;
          }
          v16 = StringCchPrintfW(a3, 0x104u, L"%s\\%s", v13, L"WaaSMedic");
          v9 = v16;
          if ( v16 < 0 )
            LogLevelW(2u, L"RegUtil: Failed to generate state separated root key path! hr = 0x%08x", (unsigned int)v16);
        }
        else
        {
          LogLevelW(2u, L"RegUtil: Error retrieving persisted registry key path. hr=0x%08X", v9);
        }
      }
      else
      {
        if ( a4 )
          *(_DWORD *)a4 = v8 + 12;
        v17 = StringCchPrintfW(a3, 0x104u, L"%s\\%s", L"SYSTEM\\WaaS", L"WaaSMedic");
        v9 = v17;
        if ( v17 < 0 )
          LogLevelW(
            2u,
            L"RegUtil: Failed to generate non-state separated root key path! hr = 0x%08x",
            (unsigned int)v17);
      }
    }
    else
    {
      v9 = 0;
      LogLevelW(2u, L"RegUtil: Error calculating the length of root key name. hr=0x%08X", 0);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v9;
}

```

## disassembly

```asm
0x14001002c  mov     [rsp-8+arg_0], rbx
0x140010031  mov     [rsp-8+arg_8], rsi
0x140010036  push    rbp
0x140010037  push    rdi
0x140010038  push    r13
0x14001003a  push    r14
0x14001003c  push    r15
0x14001003e  lea     rbp, [rsp-180h]
0x140010046  sub     rsp, 280h
0x14001004d  mov     rax, cs:__security_cookie
0x140010054  xor     rax, rsp
0x140010057  mov     [rbp+1A0h+var_30], rax
0x14001005e  xor     r15d, r15d
0x140010061  mov     rbx, r9
0x140010064  mov     [rsp+2A0h+var_260], r15d
0x140010069  mov     rsi, r8
0x14001006c  test    r9, r9
0x14001006f  jz      short loc_140010074
0x140010071  mov     [r9], r15d
0x140010074  test    rsi, rsi
0x140010077  jz      loc_1400102B8
0x14001007d  mov     edx, 7FFFFFFFh
0x140010082  lea     r13, aWaasmedic; "WaaSMedic"
0x140010089  mov     ecx, edx
0x14001008b  mov     rax, r13
0x14001008e  cmp     [rax], r15w
0x140010092  jz      short loc_14001009E
0x140010094  add     rax, 2
0x140010098  sub     rcx, 1
0x14001009c  jnz     short loc_14001008E
0x14001009e  sub     rdx, rcx
0x1400100a1  mov     rax, rcx
0x1400100a4  neg     rax
0x1400100a7  sbb     rdi, rdi
0x1400100aa  and     rdi, rdx
0x1400100ad  test    rcx, rcx
0x1400100b0  jnz     short loc_1400100CE
0x1400100b2  mov     ebx, r15d
0x1400100b5  lea     rdx, aRegutilErrorCa_0; "RegUtil: Error calculating the length o"...
0x1400100bc  xor     r8d, r8d
0x1400100bf  mov     ecx, 2; unsigned __int8
0x1400100c4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1400100c9  jmp     loc_1400102BD
0x1400100ce  call    cs:__imp_RtlIsStateSeparationEnabled
0x1400100d4  test    al, al
0x1400100d6  jz      loc_140010279
0x1400100dc  lea     rax, [rsp+2A0h+var_260]
0x1400100e1  xor     r9d, r9d
0x1400100e4  mov     [rsp+2A0h+var_270], rax
0x1400100e9  lea     r8, aSystemWaas; "SYSTEM\\WaaS"
0x1400100f0  lea     rax, [rsp+2A0h+var_240]
0x1400100f5  mov     dword ptr [rsp+2A0h+var_278], 208h
0x1400100fd  xor     edx, edx
0x1400100ff  mov     [rsp+2A0h+var_280], rax
0x140010104  lea     rcx, aWaas; "WaaS"
0x14001010b  call    cs:__imp_RtlGetPersistedStateLocation
0x140010111  mov     r9d, [rsp+2A0h+var_260]
0x140010116  lea     r8, [rsp+2A0h+var_240]
0x14001011b  lea     rdx, aRegutilRtlgetp; "RegUtil: RtlGetPersistedStateLocation r"...
0x140010122  mov     dword ptr [rsp+2A0h+var_280], r15d
0x140010127  mov     ecx, 5; unsigned __int8
0x14001012c  mov     r14d, eax
0x14001012f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140010134  test    rbx, rbx
0x140010137  jz      short loc_140010143
0x140010139  mov     ecx, [rsp+2A0h+var_260]
0x14001013d  shr     ecx, 1
0x14001013f  add     ecx, edi
0x140010141  mov     [rbx], ecx
0x140010143  mov     ecx, r14d; Status
0x140010146  call    cs:__imp_RtlNtStatusToDosError
0x14001014c  mov     ebx, eax
0x14001014e  test    eax, eax
0x140010150  jle     short loc_14001015B
0x140010152  movzx   ebx, ax
0x140010155  or      ebx, 80070000h
0x14001015b  mov     r9d, 800700EAh
0x140010161  cmp     ebx, r9d
0x140010164  jnz     short loc_140010181
0x140010166  mov     r8d, [rsp+2A0h+var_260]
0x14001016b  lea     rdx, aRegutilBufferT; "RegUtil: Buffer too small for root path"...
0x140010172  mov     ecx, 3; unsigned __int8
0x140010177  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14001017c  jmp     loc_1400102BD
0x140010181  test    ebx, ebx
0x140010183  jns     short loc_140010194
0x140010185  mov     r8d, ebx
0x140010188  lea     rdx, aRegutilErrorRe; "RegUtil: Error retrieving persisted reg"...
0x14001018f  jmp     loc_1400100BF
0x140010194  lea     rbx, aOsdataSystemWa; "OSDATA\\SYSTEM\\WaaS"
0x14001019b  mov     rdx, rbx
0x14001019e  lea     rcx, [rsp+2A0h+var_240]
0x1400101a3  call    cs:__imp__o__wcsicmp
0x1400101a9  test    eax, eax
0x1400101ab  jz      loc_140010243
0x1400101b1  lea     r8, [rsp+2A0h+var_240]
0x1400101b6  mov     ecx, 2; unsigned __int8
0x1400101bb  lea     rdx, aRegutilUnexpec; "RegUtil: Unexpected root path returned "...
0x1400101c2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1400101c7  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x1400101cc  mov     ecx, [rax]
0x1400101ce  cmp     ecx, 5
0x1400101d1  jbe     short loc_140010248
0x1400101d3  mov     rdx, [rax+18h]
0x1400101d7  mov     r8, 400000000000h
0x1400101e1  mov     rcx, [rax+10h]
0x1400101e5  test    r8, rcx
0x1400101e8  jz      short loc_140010248
0x1400101ea  mov     rcx, rdx
0x1400101ed  and     rcx, r8
0x1400101f0  cmp     rcx, rdx
0x1400101f3  jnz     short loc_140010248
0x1400101f5  lea     rcx, [rsp+2A0h+var_240]
0x1400101fa  mov     [rsp+2A0h+var_248], 1000000h
0x140010203  mov     [rsp+2A0h+var_258], rcx
0x140010208  lea     rdx, byte_14001A245
0x14001020f  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x140010216  mov     [rsp+2A0h+var_250], rcx
0x14001021b  lea     rcx, [rsp+2A0h+var_258]
0x140010220  mov     [rsp+2A0h+var_270], rcx
0x140010225  lea     rcx, [rsp+2A0h+var_250]
0x14001022a  mov     [rsp+2A0h+var_278], rcx
0x14001022f  lea     rcx, [rsp+2A0h+var_248]
0x140010234  mov     [rsp+2A0h+var_280], rcx
0x140010239  mov     rcx, rax
0x14001023c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140010241  jmp     short loc_140010248
0x140010243  lea     rbx, [rsp+2A0h+var_240]
0x140010248  mov     r9, rbx
0x14001024b  mov     [rsp+2A0h+var_280], r13
0x140010250  lea     r8, aSS; "%s\\%s"
0x140010257  mov     edx, 104h; unsigned __int64
0x14001025c  mov     rcx, rsi; unsigned __int16 *
0x14001025f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140010264  mov     ebx, eax
0x140010266  test    eax, eax
0x140010268  jns     short loc_1400102BD
0x14001026a  mov     r8d, eax
0x14001026d  lea     rdx, aRegutilFailedT; "RegUtil: Failed to generate state separ"...
0x140010274  jmp     loc_1400100BF
0x140010279  test    rbx, rbx
0x14001027c  jz      short loc_140010283
0x14001027e  lea     eax, [rdi+0Ch]
0x140010281  mov     [rbx], eax
0x140010283  lea     r9, aSystemWaas; "SYSTEM\\WaaS"
0x14001028a  mov     [rsp+2A0h+var_280], r13
0x14001028f  lea     r8, aSS; "%s\\%s"
0x140010296  mov     edx, 104h; unsigned __int64
0x14001029b  mov     rcx, rsi; unsigned __int16 *
0x14001029e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400102a3  mov     ebx, eax
0x1400102a5  test    eax, eax
0x1400102a7  jns     short loc_1400102BD
0x1400102a9  mov     r8d, eax
0x1400102ac  lea     rdx, aRegutilFailedT_0; "RegUtil: Failed to generate non-state s"...
0x1400102b3  jmp     loc_1400100BF
0x1400102b8  mov     ebx, 80004003h
0x1400102bd  mov     eax, ebx
0x1400102bf  mov     rcx, [rbp+1A0h+var_30]
0x1400102c6  xor     rcx, rsp; StackCookie
0x1400102c9  call    __security_check_cookie
0x1400102ce  lea     r11, [rsp+2A0h+var_20]
0x1400102d6  mov     rbx, [r11+30h]
0x1400102da  mov     rsi, [r11+38h]
0x1400102de  mov     rsp, r11
0x1400102e1  pop     r15
0x1400102e3  pop     r14
0x1400102e5  pop     r13
0x1400102e7  pop     rdi
0x1400102e8  pop     rbp
0x1400102e9  retn
```

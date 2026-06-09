# WaasMedic::RegGetPersistedRootPath(ushort *,ulong,ushort *,ulong *)

- ea: `0x180027df8`
- end: `0x1800280b6`
- name: `?RegGetPersistedRootPath@WaasMedic@@YAJPEAGK0PEAK@Z`
- size: `702`
- prototype: `int(WaasMedic *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180021060`
- `0x1800280bc`

## callees

- `0x180002058`
- `0x180003bb0`
- `0x18000a5d0`
- `0x180016c9c`
- `0x18002543c`
- `0x180027df8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027f6f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027f6f`
- `ntdll!RtlNtStatusToDosError` at `0x180027f12`
- `ntdll!RtlNtStatusToDosError` at `0x180027f12`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027e9a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180027e9a`
- `ntdll!RtlGetPersistedStateLocation` at `0x180027ed7`
- `ntdll!RtlGetPersistedStateLocation` at `0x180027ed7`

## string_xrefs

- `0x180027f37`: `RegUtil: Buffer too small for root path: expecting %d, hr=0x%08X`
- `0x180027ee7`: `RegUtil: RtlGetPersistedStateLocation returned: path=%ws, cbRequired=%d, hr=0x%08X`
- `0x180027f54`: `RegUtil: Error retrieving persisted registry key path. hr=0x%08X`
- `0x180028039`: `RegUtil: Failed to generate state separated root key path! hr = 0x%08x`
- `0x180027f87`: `RegUtil: Unexpected root path returned from state separation api: %ws`
- `0x180028078`: `RegUtil: Failed to generate non-state separated root key path! hr = 0x%08x`

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
  int v15; // r9d
  int v16; // eax
  int v17; // eax
  __int64 v19; // [rsp+20h] [rbp-E0h]
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v21; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v22; // [rsp+50h] [rbp-B0h] BYREF
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
              v21 = v24;
              v22 = &gc_pszVersionString;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                (_DWORD)v14,
                (unsigned int)&word_1800890A6,
                0,
                v15,
                (__int64)&v23,
                (__int64)&v22,
                (__int64)&v21);
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
0x180027df8  mov     [rsp-8+arg_0], rbx
0x180027dfd  mov     [rsp-8+arg_8], rsi
0x180027e02  push    rbp
0x180027e03  push    rdi
0x180027e04  push    r13
0x180027e06  push    r14
0x180027e08  push    r15
0x180027e0a  lea     rbp, [rsp-180h]
0x180027e12  sub     rsp, 280h
0x180027e19  mov     rax, cs:__security_cookie
0x180027e20  xor     rax, rsp
0x180027e23  mov     [rbp+1A0h+var_30], rax
0x180027e2a  xor     r15d, r15d
0x180027e2d  mov     rbx, r9
0x180027e30  mov     [rsp+2A0h+var_260], r15d
0x180027e35  mov     rsi, r8
0x180027e38  test    r9, r9
0x180027e3b  jz      short loc_180027E40
0x180027e3d  mov     [r9], r15d
0x180027e40  test    rsi, rsi
0x180027e43  jz      loc_180028084
0x180027e49  mov     edx, 7FFFFFFFh
0x180027e4e  lea     r13, aWaasmedic_1; "WaaSMedic"
0x180027e55  mov     ecx, edx
0x180027e57  mov     rax, r13
0x180027e5a  cmp     [rax], r15w
0x180027e5e  jz      short loc_180027E6A
0x180027e60  add     rax, 2
0x180027e64  sub     rcx, 1
0x180027e68  jnz     short loc_180027E5A
0x180027e6a  sub     rdx, rcx
0x180027e6d  mov     rax, rcx
0x180027e70  neg     rax
0x180027e73  sbb     rdi, rdi
0x180027e76  and     rdi, rdx
0x180027e79  test    rcx, rcx
0x180027e7c  jnz     short loc_180027E9A
0x180027e7e  mov     ebx, r15d
0x180027e81  lea     rdx, aRegutilErrorCa_0; "RegUtil: Error calculating the length o"...
0x180027e88  xor     r8d, r8d
0x180027e8b  mov     ecx, 2; unsigned __int8
0x180027e90  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027e95  jmp     loc_180028089
0x180027e9a  call    cs:__imp_RtlIsStateSeparationEnabled
0x180027ea0  test    al, al
0x180027ea2  jz      loc_180028045
0x180027ea8  lea     rax, [rsp+2A0h+var_260]
0x180027ead  xor     r9d, r9d
0x180027eb0  mov     [rsp+2A0h+var_270], rax
0x180027eb5  lea     r8, aSystemWaas; "SYSTEM\\WaaS"
0x180027ebc  lea     rax, [rsp+2A0h+var_240]
0x180027ec1  mov     dword ptr [rsp+2A0h+var_278], 208h
0x180027ec9  xor     edx, edx
0x180027ecb  mov     [rsp+2A0h+var_280], rax
0x180027ed0  lea     rcx, aWaas; "WaaS"
0x180027ed7  call    cs:__imp_RtlGetPersistedStateLocation
0x180027edd  mov     r9d, [rsp+2A0h+var_260]
0x180027ee2  lea     r8, [rsp+2A0h+var_240]
0x180027ee7  lea     rdx, aRegutilRtlgetp; "RegUtil: RtlGetPersistedStateLocation r"...
0x180027eee  mov     dword ptr [rsp+2A0h+var_280], r15d
0x180027ef3  mov     ecx, 5; unsigned __int8
0x180027ef8  mov     r14d, eax
0x180027efb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027f00  test    rbx, rbx
0x180027f03  jz      short loc_180027F0F
0x180027f05  mov     ecx, [rsp+2A0h+var_260]
0x180027f09  shr     ecx, 1
0x180027f0b  add     ecx, edi
0x180027f0d  mov     [rbx], ecx
0x180027f0f  mov     ecx, r14d; Status
0x180027f12  call    cs:__imp_RtlNtStatusToDosError
0x180027f18  mov     ebx, eax
0x180027f1a  test    eax, eax
0x180027f1c  jle     short loc_180027F27
0x180027f1e  movzx   ebx, ax
0x180027f21  or      ebx, 80070000h
0x180027f27  mov     r9d, 800700EAh
0x180027f2d  cmp     ebx, r9d
0x180027f30  jnz     short loc_180027F4D
0x180027f32  mov     r8d, [rsp+2A0h+var_260]
0x180027f37  lea     rdx, aRegutilBufferT; "RegUtil: Buffer too small for root path"...
0x180027f3e  mov     ecx, 3; unsigned __int8
0x180027f43  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027f48  jmp     loc_180028089
0x180027f4d  test    ebx, ebx
0x180027f4f  jns     short loc_180027F60
0x180027f51  mov     r8d, ebx
0x180027f54  lea     rdx, aRegutilErrorRe; "RegUtil: Error retrieving persisted reg"...
0x180027f5b  jmp     loc_180027E8B
0x180027f60  lea     rbx, aOsdataSystemWa; "OSDATA\\SYSTEM\\WaaS"
0x180027f67  mov     rdx, rbx
0x180027f6a  lea     rcx, [rsp+2A0h+var_240]
0x180027f6f  call    cs:__imp__o__wcsicmp
0x180027f75  test    eax, eax
0x180027f77  jz      loc_18002800F
0x180027f7d  lea     r8, [rsp+2A0h+var_240]
0x180027f82  mov     ecx, 2; unsigned __int8
0x180027f87  lea     rdx, aRegutilUnexpec; "RegUtil: Unexpected root path returned "...
0x180027f8e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180027f93  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180027f98  mov     ecx, [rax]
0x180027f9a  cmp     ecx, 5
0x180027f9d  jbe     short loc_180028014
0x180027f9f  mov     rdx, [rax+18h]
0x180027fa3  mov     r8, 400000000000h
0x180027fad  mov     rcx, [rax+10h]
0x180027fb1  test    r8, rcx
0x180027fb4  jz      short loc_180028014
0x180027fb6  mov     rcx, rdx
0x180027fb9  and     rcx, r8
0x180027fbc  cmp     rcx, rdx
0x180027fbf  jnz     short loc_180028014
0x180027fc1  lea     rcx, [rsp+2A0h+var_240]
0x180027fc6  mov     [rsp+2A0h+var_248], 1000000h
0x180027fcf  mov     [rsp+2A0h+var_258], rcx
0x180027fd4  lea     rdx, word_1800890A6
0x180027fdb  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180027fe2  mov     [rsp+2A0h+var_250], rcx
0x180027fe7  lea     rcx, [rsp+2A0h+var_258]
0x180027fec  mov     [rsp+2A0h+var_270], rcx
0x180027ff1  lea     rcx, [rsp+2A0h+var_250]
0x180027ff6  mov     [rsp+2A0h+var_278], rcx
0x180027ffb  lea     rcx, [rsp+2A0h+var_248]
0x180028000  mov     [rsp+2A0h+var_280], rcx
0x180028005  mov     rcx, rax
0x180028008  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002800d  jmp     short loc_180028014
0x18002800f  lea     rbx, [rsp+2A0h+var_240]
0x180028014  mov     r9, rbx
0x180028017  mov     [rsp+2A0h+var_280], r13
0x18002801c  lea     r8, aSS; "%s\\%s"
0x180028023  mov     edx, 104h; unsigned __int64
0x180028028  mov     rcx, rsi; unsigned __int16 *
0x18002802b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028030  mov     ebx, eax
0x180028032  test    eax, eax
0x180028034  jns     short loc_180028089
0x180028036  mov     r8d, eax
0x180028039  lea     rdx, aRegutilFailedT; "RegUtil: Failed to generate state separ"...
0x180028040  jmp     loc_180027E8B
0x180028045  test    rbx, rbx
0x180028048  jz      short loc_18002804F
0x18002804a  lea     eax, [rdi+0Ch]
0x18002804d  mov     [rbx], eax
0x18002804f  lea     r9, aSystemWaas; "SYSTEM\\WaaS"
0x180028056  mov     [rsp+2A0h+var_280], r13
0x18002805b  lea     r8, aSS; "%s\\%s"
0x180028062  mov     edx, 104h; unsigned __int64
0x180028067  mov     rcx, rsi; unsigned __int16 *
0x18002806a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002806f  mov     ebx, eax
0x180028071  test    eax, eax
0x180028073  jns     short loc_180028089
0x180028075  mov     r8d, eax
0x180028078  lea     rdx, aRegutilFailedT_0; "RegUtil: Failed to generate non-state s"...
0x18002807f  jmp     loc_180027E8B
0x180028084  mov     ebx, 80004003h
0x180028089  mov     eax, ebx
0x18002808b  mov     rcx, [rbp+1A0h+var_30]
0x180028092  xor     rcx, rsp; StackCookie
0x180028095  call    __security_check_cookie
0x18002809a  lea     r11, [rsp+2A0h+var_20]
0x1800280a2  mov     rbx, [r11+30h]
0x1800280a6  mov     rsi, [r11+38h]
0x1800280aa  mov     rsp, r11
0x1800280ad  pop     r15
0x1800280af  pop     r14
0x1800280b1  pop     r13
0x1800280b3  pop     rdi
0x1800280b4  pop     rbp
0x1800280b5  retn
```

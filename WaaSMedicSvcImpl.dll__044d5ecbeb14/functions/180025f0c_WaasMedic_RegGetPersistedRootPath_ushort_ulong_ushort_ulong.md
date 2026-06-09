# WaasMedic::RegGetPersistedRootPath(ushort *,ulong,ushort *,ulong *)

- ea: `0x180025f0c`
- end: `0x1800261c1`
- name: `?RegGetPersistedRootPath@WaasMedic@@YAJPEAGK0PEAK@Z`
- size: `693`
- prototype: `int(WaasMedic *__hidden this, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `8`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180017a60`
- `0x180022d30`
- `0x1800261c8`
- `0x18004ef58`
- `0x18004ff6c`
- `0x1800524b0`
- `0x1800525b0`
- `0x180068100`

## callees

- `0x1800022e4`
- `0x1800050a0`
- `0x18000c638`
- `0x18000d04c`
- `0x180025f0c`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026083`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026083`
- `ntdll!RtlNtStatusToDosError` at `0x180026026`
- `ntdll!RtlNtStatusToDosError` at `0x180026026`
- `ntdll!RtlGetPersistedStateLocation` at `0x180025feb`
- `ntdll!RtlGetPersistedStateLocation` at `0x180025feb`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180025fae`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180025fae`

## string_xrefs

- `0x180025ffb`: `RegUtil: RtlGetPersistedStateLocation returned: path=%ws, cbRequired=%d, hr=0x%08X`
- `0x180026068`: `RegUtil: Error retrieving persisted registry key path. hr=0x%08X`
- `0x18002604b`: `RegUtil: Buffer too small for root path: expecting %d, hr=0x%08X`
- `0x18002609b`: `RegUtil: Unexpected root path returned from state separation api: %ws`
- `0x18002618d`: `RegUtil: Failed to generate non-state separated root key path! hr = 0x%08x`
- `0x18002614e`: `RegUtil: Failed to generate state separated root key path! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegGetPersistedRootPath(
        WaasMedic *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  WaasMedic *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdi
  unsigned int v10; // ebx
  NTSTATUS PersistedStateLocation; // eax
  NTSTATUS v12; // r15d
  signed int v13; // eax
  const wchar_t *v14; // rbx
  __int64 v15; // rcx
  int v16; // r9d
  int v17; // eax
  int v18; // eax
  __int64 v20; // [rsp+20h] [rbp-E0h]
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v22; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v23; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v25[528]; // [rsp+60h] [rbp-A0h] BYREF

  v21 = 0;
  if ( a4 )
    *(_DWORD *)a4 = 0;
  if ( this && a3 )
  {
    v7 = this;
    v8 = 0x7FFFFFFF;
    do
    {
      if ( !*(_WORD *)v7 )
        break;
      v7 = (WaasMedic *)((char *)v7 + 2);
      --v8;
    }
    while ( v8 );
    v9 = (0x7FFFFFFF - v8) & -(__int64)(v8 != 0);
    if ( v8 )
    {
      if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
      {
        PersistedStateLocation = RtlGetPersistedStateLocation(L"WaaS", 0, L"SYSTEM\\WaaS", 0, v25, 520, &v21);
        LODWORD(v20) = 0;
        v12 = PersistedStateLocation;
        LogLevelW(
          5u,
          L"RegUtil: RtlGetPersistedStateLocation returned: path=%ws, cbRequired=%d, hr=0x%08X",
          v25,
          v21,
          v20);
        if ( a4 )
          *(_DWORD *)a4 = v9 + (v21 >> 1);
        v13 = RtlNtStatusToDosError(v12);
        v10 = v13;
        if ( v13 > 0 )
          v10 = (unsigned __int16)v13 | 0x80070000;
        if ( v10 == -2147024662 )
        {
          LogLevelW(3u, L"RegUtil: Buffer too small for root path: expecting %d, hr=0x%08X", v21);
        }
        else if ( (v10 & 0x80000000) == 0 )
        {
          v14 = L"OSDATA\\SYSTEM\\WaaS";
          if ( (unsigned int)_o__wcsicmp(v25, L"OSDATA\\SYSTEM\\WaaS") )
          {
            LogLevelW(2u, L"RegUtil: Unexpected root path returned from state separation api: %ws", v25);
            v15 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
            if ( *(_DWORD *)v15 > 5u
              && (*(_QWORD *)(v15 + 16) & 0x400000000000LL) != 0
              && (*(_QWORD *)(v15 + 24) & 0x400000000000LL) == *(_QWORD *)(v15 + 24) )
            {
              v24 = 0x1000000;
              v22 = v25;
              v23 = &gc_pszVersionString;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                v15,
                (unsigned int)byte_180092BB9,
                0,
                v16,
                (__int64)&v24,
                (__int64)&v23,
                (__int64)&v22);
            }
          }
          else
          {
            v14 = (const wchar_t *)v25;
          }
          v17 = StringCchPrintfW(a3, 0x104u, L"%s\\%s", v14, this);
          v10 = v17;
          if ( v17 < 0 )
            LogLevelW(2u, L"RegUtil: Failed to generate state separated root key path! hr = 0x%08x", (unsigned int)v17);
        }
        else
        {
          LogLevelW(2u, L"RegUtil: Error retrieving persisted registry key path. hr=0x%08X", v10);
        }
      }
      else
      {
        if ( a4 )
          *(_DWORD *)a4 = v9 + 12;
        v18 = StringCchPrintfW(a3, 0x104u, L"%s\\%s", L"SYSTEM\\WaaS", this);
        v10 = v18;
        if ( v18 < 0 )
          LogLevelW(
            2u,
            L"RegUtil: Failed to generate non-state separated root key path! hr = 0x%08x",
            (unsigned int)v18);
      }
    }
    else
    {
      v10 = 0;
      LogLevelW(2u, L"RegUtil: Error calculating the length of root key name. hr=0x%08X", 0);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v10;
}

```

## disassembly

```asm
0x180025f0c  push    rbp
0x180025f0e  push    rbx
0x180025f0f  push    rsi
0x180025f10  push    rdi
0x180025f11  push    r12
0x180025f13  push    r14
0x180025f15  push    r15
0x180025f17  lea     rbp, [rsp-180h]
0x180025f1f  sub     rsp, 280h
0x180025f26  mov     rax, cs:__security_cookie
0x180025f2d  xor     rax, rsp
0x180025f30  mov     [rbp+1B0h+var_40], rax
0x180025f37  xor     r12d, r12d
0x180025f3a  mov     rbx, r9
0x180025f3d  mov     [rsp+2B0h+var_270], r12d
0x180025f42  mov     r14, r8
0x180025f45  mov     rsi, rcx
0x180025f48  test    r9, r9
0x180025f4b  jz      short loc_180025F50
0x180025f4d  mov     [r9], r12d
0x180025f50  test    rsi, rsi
0x180025f53  jz      loc_180026199
0x180025f59  test    r14, r14
0x180025f5c  jz      loc_180026199
0x180025f62  mov     r8d, 7FFFFFFFh
0x180025f68  mov     rax, rsi
0x180025f6b  mov     edx, r8d
0x180025f6e  cmp     [rax], r12w
0x180025f72  jz      short loc_180025F7E
0x180025f74  add     rax, 2
0x180025f78  sub     rdx, 1
0x180025f7c  jnz     short loc_180025F6E
0x180025f7e  sub     r8, rdx
0x180025f81  mov     rax, rdx
0x180025f84  neg     rax
0x180025f87  sbb     rdi, rdi
0x180025f8a  and     rdi, r8
0x180025f8d  test    rdx, rdx
0x180025f90  jnz     short loc_180025FAE
0x180025f92  mov     ebx, r12d
0x180025f95  lea     rdx, aRegutilErrorCa_0; "RegUtil: Error calculating the length o"...
0x180025f9c  xor     r8d, r8d
0x180025f9f  mov     ecx, 2; unsigned __int8
0x180025fa4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180025fa9  jmp     loc_18002619E
0x180025fae  call    cs:__imp_RtlIsStateSeparationEnabled
0x180025fb4  test    al, al
0x180025fb6  jz      loc_18002615A
0x180025fbc  lea     rax, [rsp+2B0h+var_270]
0x180025fc1  xor     r9d, r9d
0x180025fc4  mov     [rsp+2B0h+var_280], rax
0x180025fc9  lea     r8, aSystemWaas; "SYSTEM\\WaaS"
0x180025fd0  lea     rax, [rsp+2B0h+var_250]
0x180025fd5  mov     dword ptr [rsp+2B0h+var_288], 208h
0x180025fdd  xor     edx, edx
0x180025fdf  mov     [rsp+2B0h+var_290], rax
0x180025fe4  lea     rcx, aWaas; "WaaS"
0x180025feb  call    cs:__imp_RtlGetPersistedStateLocation
0x180025ff1  mov     r9d, [rsp+2B0h+var_270]
0x180025ff6  lea     r8, [rsp+2B0h+var_250]
0x180025ffb  lea     rdx, aRegutilRtlgetp; "RegUtil: RtlGetPersistedStateLocation r"...
0x180026002  mov     dword ptr [rsp+2B0h+var_290], r12d
0x180026007  mov     ecx, 5; unsigned __int8
0x18002600c  mov     r15d, eax
0x18002600f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180026014  test    rbx, rbx
0x180026017  jz      short loc_180026023
0x180026019  mov     ecx, [rsp+2B0h+var_270]
0x18002601d  shr     ecx, 1
0x18002601f  add     ecx, edi
0x180026021  mov     [rbx], ecx
0x180026023  mov     ecx, r15d; Status
0x180026026  call    cs:__imp_RtlNtStatusToDosError
0x18002602c  mov     ebx, eax
0x18002602e  test    eax, eax
0x180026030  jle     short loc_18002603B
0x180026032  movzx   ebx, ax
0x180026035  or      ebx, 80070000h
0x18002603b  mov     r9d, 800700EAh
0x180026041  cmp     ebx, r9d
0x180026044  jnz     short loc_180026061
0x180026046  mov     r8d, [rsp+2B0h+var_270]
0x18002604b  lea     rdx, aRegutilBufferT; "RegUtil: Buffer too small for root path"...
0x180026052  mov     ecx, 3; unsigned __int8
0x180026057  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002605c  jmp     loc_18002619E
0x180026061  test    ebx, ebx
0x180026063  jns     short loc_180026074
0x180026065  mov     r8d, ebx
0x180026068  lea     rdx, aRegutilErrorRe; "RegUtil: Error retrieving persisted reg"...
0x18002606f  jmp     loc_180025F9F
0x180026074  lea     rbx, aOsdataSystemWa_2; "OSDATA\\SYSTEM\\WaaS"
0x18002607b  mov     rdx, rbx
0x18002607e  lea     rcx, [rsp+2B0h+var_250]
0x180026083  call    cs:__imp__o__wcsicmp
0x180026089  test    eax, eax
0x18002608b  jz      loc_180026124
0x180026091  lea     r8, [rsp+2B0h+var_250]
0x180026096  mov     ecx, 2; unsigned __int8
0x18002609b  lea     rdx, aRegutilUnexpec; "RegUtil: Unexpected root path returned "...
0x1800260a2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800260a7  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x1800260ac  mov     rcx, [rax+8]
0x1800260b0  mov     eax, [rcx]
0x1800260b2  cmp     eax, 5
0x1800260b5  jbe     short loc_180026129
0x1800260b7  mov     rdx, [rcx+18h]
0x1800260bb  mov     r8, 400000000000h
0x1800260c5  mov     rax, [rcx+10h]
0x1800260c9  test    r8, rax
0x1800260cc  jz      short loc_180026129
0x1800260ce  mov     rax, rdx
0x1800260d1  and     rax, r8
0x1800260d4  cmp     rax, rdx
0x1800260d7  jnz     short loc_180026129
0x1800260d9  lea     rax, [rsp+2B0h+var_250]
0x1800260de  mov     [rsp+2B0h+var_258], 1000000h
0x1800260e7  mov     [rsp+2B0h+var_268], rax
0x1800260ec  lea     rdx, byte_180092BB9
0x1800260f3  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800260fa  mov     [rsp+2B0h+var_260], rax
0x1800260ff  lea     rax, [rsp+2B0h+var_268]
0x180026104  mov     [rsp+2B0h+var_280], rax
0x180026109  lea     rax, [rsp+2B0h+var_260]
0x18002610e  mov     [rsp+2B0h+var_288], rax
0x180026113  lea     rax, [rsp+2B0h+var_258]
0x180026118  mov     [rsp+2B0h+var_290], rax
0x18002611d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180026122  jmp     short loc_180026129
0x180026124  lea     rbx, [rsp+2B0h+var_250]
0x180026129  mov     r9, rbx
0x18002612c  mov     [rsp+2B0h+var_290], rsi
0x180026131  lea     r8, aSS; "%s\\%s"
0x180026138  mov     edx, 104h; unsigned __int64
0x18002613d  mov     rcx, r14; unsigned __int16 *
0x180026140  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026145  mov     ebx, eax
0x180026147  test    eax, eax
0x180026149  jns     short loc_18002619E
0x18002614b  mov     r8d, eax
0x18002614e  lea     rdx, aRegutilFailedT; "RegUtil: Failed to generate state separ"...
0x180026155  jmp     loc_180025F9F
0x18002615a  test    rbx, rbx
0x18002615d  jz      short loc_180026164
0x18002615f  lea     eax, [rdi+0Ch]
0x180026162  mov     [rbx], eax
0x180026164  lea     r9, aSystemWaas; "SYSTEM\\WaaS"
0x18002616b  mov     [rsp+2B0h+var_290], rsi
0x180026170  lea     r8, aSS; "%s\\%s"
0x180026177  mov     edx, 104h; unsigned __int64
0x18002617c  mov     rcx, r14; unsigned __int16 *
0x18002617f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180026184  mov     ebx, eax
0x180026186  test    eax, eax
0x180026188  jns     short loc_18002619E
0x18002618a  mov     r8d, eax
0x18002618d  lea     rdx, aRegutilFailedT_0; "RegUtil: Failed to generate non-state s"...
0x180026194  jmp     loc_180025F9F
0x180026199  mov     ebx, 80004003h
0x18002619e  mov     eax, ebx
0x1800261a0  mov     rcx, [rbp+1B0h+var_40]
0x1800261a7  xor     rcx, rsp; StackCookie
0x1800261aa  call    __security_check_cookie
0x1800261af  add     rsp, 280h
0x1800261b6  pop     r15
0x1800261b8  pop     r14
0x1800261ba  pop     r12
0x1800261bc  pop     rdi
0x1800261bd  pop     rsi
0x1800261be  pop     rbx
0x1800261bf  pop     rbp
0x1800261c0  retn
```

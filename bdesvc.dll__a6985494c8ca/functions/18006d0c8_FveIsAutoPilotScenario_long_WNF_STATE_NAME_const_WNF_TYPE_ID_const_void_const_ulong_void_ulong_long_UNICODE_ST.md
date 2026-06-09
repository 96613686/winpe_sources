# FveIsAutoPilotScenario(long (*)(_WNF_STATE_NAME const *,_WNF_TYPE_ID const *,void const *,ulong *,void *,ulong *),long (*)(_UNICODE_STRING *,ulong *,void *,ulong,ulong *),bool *,bool *,unsigned __int64 *)

- ea: `0x18006d0c8`
- end: `0x18006d727`
- name: `?FveIsAutoPilotScenario@@YAJP6AJPEBU_WNF_STATE_NAME@@PEBU_WNF_TYPE_ID@@PEBXPEAKPEAX3@ZP6AJPEAU_UNICODE_STRING@@34K3@ZPEA_N8PEA_K@Z`
- size: `1631`
- prototype: `__int64 __fastcall(int (*)(const struct _WNF_STATE_NAME *, const struct _WNF_TYPE_ID *, const void *, unsigned int *, void *, unsigned int *), int (*)(struct _UNICODE_STRING *, unsigned int *, void *, unsigned int, unsigned int *), bool *, bool *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006c39c`

## callees

- `0x180001fe8`
- `0x18000356c`
- `0x180009f30`
- `0x180009f60`
- `0x180025ed4`
- `0x18002f28c`
- `0x18006d0c8`
- `0x18007e010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18006d12d`
- `ntdll!RtlInitUnicodeString` at `0x18006d12d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006d1a4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006d1a4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d6fb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006d6fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006d298`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006d298`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d1bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d2ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d1bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d2ac`

## string_xrefs

- `0x18006d197`: `autopilot.dll`
- `0x18006d0fe`: `WorkstationService-DomainJoinEnabled`

## pseudocode

```c
__int64 __fastcall FveIsAutoPilotScenario(
        int (*a1)(const struct _WNF_STATE_NAME *, const struct _WNF_TYPE_ID *, const void *, unsigned int *, void *, unsigned int *),
        __int64 (__fastcall *a2)(struct _UNICODE_STRING *, int *, int *, __int64, int *),
        bool *a3,
        bool *a4,
        unsigned __int64 *a5)
{
  char v5; // r13
  int v9; // eax
  __int64 v10; // rdi
  HMODULE Library; // rax
  HMODULE v12; // r15
  signed int LastError; // eax
  unsigned int v14; // ebx
  __int64 v15; // rax
  FARPROC ProcAddress; // rbx
  signed int v17; // eax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rdi
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  bool v24; // r14
  int v25; // eax
  __int64 v26; // rax
  bool *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  int v32; // [rsp+40h] [rbp-31h] BYREF
  unsigned int v33; // [rsp+44h] [rbp-2Dh] BYREF
  int v34; // [rsp+48h] [rbp-29h] BYREF
  int v35; // [rsp+4Ch] [rbp-25h] BYREF
  int v36; // [rsp+50h] [rbp-21h] BYREF
  int v37; // [rsp+54h] [rbp-1Dh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-19h] BYREF
  PSRWLOCK v39[11]; // [rsp+68h] [rbp-9h] BYREF
  unsigned int v41; // [rsp+D8h] [rbp+67h] BYREF
  int v42; // [rsp+E0h] [rbp+6Fh] BYREF
  bool *v43; // [rsp+E8h] [rbp+77h] BYREF

  v43 = a4;
  v5 = 0;
  v33 = 0;
  v34 = 0;
  v32 = 0;
  v37 = 0;
  v42 = 4;
  v36 = 0;
  DestinationString = 0;
  v35 = 0;
  *a3 = 0;
  *a4 = 0;
  RtlInitUnicodeString(&DestinationString, L"WorkstationService-DomainJoinEnabled");
  v9 = a2(&DestinationString, &v37, &v35, 4, &v36);
  if ( v9 >= 0 )
  {
    v10 = 0;
    if ( (v35 & 2) == 0 )
    {
      v12 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      v10 = 0x20000000;
      goto LABEL_87;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)v9);
    v10 = 0x10000000;
  }
  Library = LoadLibraryExW(L"autopilot.dll", 0, 0x800u);
  v12 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v14 = LastError;
    if ( LastError > 0 )
      v14 = (unsigned __int16)LastError | 0x80070000;
    if ( v14 == -2147024894 )
    {
      v14 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      v15 = 0x40000000;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v14);
      v15 = 0x80000000LL;
    }
LABEL_23:
    v10 |= v15;
    goto LABEL_88;
  }
  ProcAddress = GetProcAddress(Library, "AutoPilotIsLocalProfileAvailable");
  if ( !ProcAddress )
  {
    v17 = GetLastError();
    v14 = v17;
    if ( v17 > 0 )
      v14 = (unsigned __int16)v17 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v14);
    v15 = 0x100000000LL;
    goto LABEL_23;
  }
  LOBYTE(v41) = 0;
  v32 = 0;
  v42 = 4;
  v18 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, int *))a1)(
          &WNF_PROV_AUTOPILOT_PROFILE_AVAILABLE,
          0,
          0,
          &v34,
          &v32,
          &v42);
  if ( v18 >= 0 )
  {
    if ( v42 == 4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      LOBYTE(v41) = 1;
      v19 = 0x400000000LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      v19 = 0x800000000LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)v18);
    v19 = 0x200000000LL;
  }
  v20 = v19 | v10;
  v32 = 0;
  v42 = 4;
  v21 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, int *))a1)(
          &WNF_PROV_AUTOPILOT_DEVICE_NOT_MANAGED,
          0,
          0,
          &v34,
          &v32,
          &v42);
  if ( v21 >= 0 )
  {
    if ( v42 == 4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      v5 = 1;
      v22 = 0x2000000000LL;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
      v22 = 0x4000000000LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)v21);
    v22 = 0x1000000000LL;
  }
  v10 = v22 | v20;
  v23 = ((__int64 (__fastcall *)(unsigned int *))ProcAddress)(&v33);
  v14 = v23;
  if ( v23 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)v23);
    v15 = 0x8000000000LL;
    goto LABEL_23;
  }
  v24 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v33);
  v32 = 0;
  v42 = 4;
  v25 = ((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, int *, int *))a1)(
          &WNF_PROV_DEVICE_BOOTSTRAP_COMPLETE,
          0,
          0,
          &v34,
          &v32,
          &v42);
  if ( v25 >= 0 )
  {
    if ( v42 == 4 )
    {
      v24 = v32 == 1;
      goto LABEL_79;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
    v26 = 0x20000000000LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids,
        (unsigned int)v25);
    v26 = 0x10000000000LL;
  }
  v10 |= v26;
LABEL_79:
  if ( v33 )
  {
    v27 = v43;
    *a3 = 1;
    *v27 = v24;
LABEL_87:
    v14 = 0;
    goto LABEL_88;
  }
  v14 = -2147024875;
  if ( v5 )
  {
    *a3 = 0;
    v14 = 0;
  }
  if ( (_BYTE)v41 )
  {
    *a3 = 0;
    v14 = 0;
  }
  if ( v24 )
  {
    *a3 = 0;
    goto LABEL_87;
  }
LABEL_88:
  if ( a5 )
    *a5 |= v10;
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v39,
    &g_hBitLockerDelayProvider,
    &g_bitLockerDelayProviderInitLock,
    &g_bitLockerDelayProviderRefCount);
  if ( (unsigned int)dword_18009A4D8 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A4D8, 0x400000000000LL) )
  {
    LODWORD(a5) = v33;
    LOBYTE(v43) = *a3;
    v41 = v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      v28,
      (int)byte_18008E913,
      v29,
      v30,
      (__int64)&v41,
      (__int64)&v43,
      (__int64)&a5);
  }
  if ( v12 )
    FreeLibrary(v12);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar(v39);
  return v14;
}

```

## disassembly

```asm
0x18006d0c8  mov     [rsp-8+arg_18], r9
0x18006d0cd  mov     [rsp-8+arg_0], rcx
0x18006d0d2  push    rbp
0x18006d0d3  push    rbx
0x18006d0d4  push    rsi
0x18006d0d5  push    rdi
0x18006d0d6  push    r12
0x18006d0d8  push    r13
0x18006d0da  push    r14
0x18006d0dc  push    r15
0x18006d0de  lea     rbp, [rsp-17h]
0x18006d0e3  sub     rsp, 88h
0x18006d0ea  xor     r13d, r13d
0x18006d0ed  mov     rbx, rdx
0x18006d0f0  mov     r14, rcx
0x18006d0f3  mov     [rbp+4Fh+var_7C], r13d
0x18006d0f7  xorps   xmm0, xmm0
0x18006d0fa  mov     [rbp+4Fh+var_78], r13d
0x18006d0fe  lea     rdx, aWorkstationser; "WorkstationService-DomainJoinEnabled"
0x18006d105  mov     [rbp+4Fh+var_80], r13d
0x18006d109  lea     edi, [r13+4]
0x18006d10d  mov     [rbp+4Fh+var_6C], r13d
0x18006d111  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18006d115  mov     [rbp+4Fh+arg_10], edi
0x18006d118  mov     r12, r8
0x18006d11b  mov     [rbp+4Fh+var_70], r13d
0x18006d11f  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18006d123  mov     [rbp+4Fh+var_74], r13d
0x18006d127  mov     [r8], r13b
0x18006d12a  mov     [r9], r13b
0x18006d12d  call    cs:__imp_RtlInitUnicodeString
0x18006d134  nop     dword ptr [rax+rax+00h]
0x18006d139  lea     rax, [rbp+4Fh+var_70]
0x18006d13d  mov     r9d, edi
0x18006d140  mov     [rsp+0C0h+var_A0], rax
0x18006d145  lea     r8, [rbp+4Fh+var_74]
0x18006d149  mov     rax, rbx
0x18006d14c  lea     rdx, [rbp+4Fh+var_6C]
0x18006d150  lea     rcx, [rbp+4Fh+DestinationString]
0x18006d154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d159  lea     rsi, WPP_GLOBAL_Control
0x18006d160  test    eax, eax
0x18006d162  jns     loc_18006D213
0x18006d168  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d16f  cmp     rcx, rsi
0x18006d172  jz      short loc_18006D190
0x18006d174  test    [rcx+1Ch], dil
0x18006d178  jz      short loc_18006D190
0x18006d17a  mov     rcx, [rcx+10h]
0x18006d17e  lea     edx, [rdi+6]
0x18006d181  mov     r9d, eax
0x18006d184  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d18b  call    WPP_SF_d
0x18006d190  mov     edi, 10000000h
0x18006d195  xor     edx, edx; hFile
0x18006d197  lea     rcx, aAutopilotDll; "autopilot.dll"
0x18006d19e  mov     r8d, 800h; dwFlags
0x18006d1a4  call    cs:__imp_LoadLibraryExW
0x18006d1ab  nop     dword ptr [rax+rax+00h]
0x18006d1b0  mov     r15, rax
0x18006d1b3  test    rax, rax
0x18006d1b6  jnz     loc_18006D28E
0x18006d1bc  call    cs:__imp_GetLastError
0x18006d1c3  nop     dword ptr [rax+rax+00h]
0x18006d1c8  mov     ebx, eax
0x18006d1ca  test    eax, eax
0x18006d1cc  jle     short loc_18006D1D7
0x18006d1ce  movzx   ebx, ax
0x18006d1d1  or      ebx, 80070000h
0x18006d1d7  cmp     ebx, 80070002h
0x18006d1dd  jnz     short loc_18006D257
0x18006d1df  mov     ebx, r13d
0x18006d1e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d1e9  cmp     rcx, rsi
0x18006d1ec  jz      short loc_18006D20C
0x18006d1ee  mov     sil, 8
0x18006d1f1  test    [rcx+1Ch], sil
0x18006d1f5  jz      short loc_18006D20C
0x18006d1f7  mov     rcx, [rcx+10h]
0x18006d1fb  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d202  mov     edx, 0Ch
0x18006d207  call    WPP_SF_
0x18006d20c  mov     eax, 40000000h
0x18006d211  jmp     short loc_18006D286
0x18006d213  test    byte ptr [rbp+4Fh+var_74], 2
0x18006d217  mov     rdi, r13
0x18006d21a  jnz     loc_18006D195
0x18006d220  mov     r15, r13
0x18006d223  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d22a  cmp     rcx, rsi
0x18006d22d  jz      short loc_18006D24D
0x18006d22f  mov     sil, 8
0x18006d232  test    [rcx+1Ch], sil
0x18006d236  jz      short loc_18006D24D
0x18006d238  mov     rcx, [rcx+10h]
0x18006d23c  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d243  mov     edx, 0Bh
0x18006d248  call    WPP_SF_
0x18006d24d  mov     edi, 20000000h
0x18006d252  jmp     loc_18006D66A
0x18006d257  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d25e  cmp     rcx, rsi
0x18006d261  jz      short loc_18006D281
0x18006d263  test    byte ptr [rcx+1Ch], 2
0x18006d267  jz      short loc_18006D281
0x18006d269  mov     rcx, [rcx+10h]
0x18006d26d  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d274  mov     edx, 0Dh
0x18006d279  mov     r9d, ebx
0x18006d27c  call    WPP_SF_d
0x18006d281  mov     eax, 80000000h
0x18006d286  or      rdi, rax
0x18006d289  jmp     loc_18006D66D
0x18006d28e  lea     rdx, aAutopilotisloc; "AutoPilotIsLocalProfileAvailable"
0x18006d295  mov     rcx, rax; hModule
0x18006d298  call    cs:__imp_GetProcAddress
0x18006d29f  nop     dword ptr [rax+rax+00h]
0x18006d2a4  mov     rbx, rax
0x18006d2a7  test    rax, rax
0x18006d2aa  jnz     short loc_18006D2FD
0x18006d2ac  call    cs:__imp_GetLastError
0x18006d2b3  nop     dword ptr [rax+rax+00h]
0x18006d2b8  mov     ebx, eax
0x18006d2ba  test    eax, eax
0x18006d2bc  jle     short loc_18006D2C7
0x18006d2be  movzx   ebx, ax
0x18006d2c1  or      ebx, 80070000h
0x18006d2c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d2ce  cmp     rcx, rsi
0x18006d2d1  jz      short loc_18006D2F1
0x18006d2d3  test    byte ptr [rcx+1Ch], 2
0x18006d2d7  jz      short loc_18006D2F1
0x18006d2d9  mov     rcx, [rcx+10h]
0x18006d2dd  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d2e4  mov     edx, 0Eh
0x18006d2e9  mov     r9d, ebx
0x18006d2ec  call    WPP_SF_d
0x18006d2f1  mov     rax, 100000000h
0x18006d2fb  jmp     short loc_18006D286
0x18006d2fd  lea     rax, [rbp+4Fh+arg_10]
0x18006d301  mov     byte ptr [rbp+4Fh+arg_8], r13b
0x18006d305  mov     [rsp+0C0h+var_98], rax
0x18006d30a  lea     r9, [rbp+4Fh+var_78]
0x18006d30e  lea     rax, [rbp+4Fh+var_80]
0x18006d312  mov     [rbp+4Fh+var_80], r13d
0x18006d316  mov     [rsp+0C0h+var_A0], rax
0x18006d31b  lea     rcx, WNF_PROV_AUTOPILOT_PROFILE_AVAILABLE
0x18006d322  mov     rax, r14
0x18006d325  mov     [rbp+4Fh+arg_10], 4
0x18006d32c  xor     r8d, r8d
0x18006d32f  xor     edx, edx
0x18006d331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d336  mov     sil, 8
0x18006d339  test    eax, eax
0x18006d33b  jns     short loc_18006D37A
0x18006d33d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d344  lea     rdx, WPP_GLOBAL_Control
0x18006d34b  cmp     rcx, rdx
0x18006d34e  jz      short loc_18006D36E
0x18006d350  test    byte ptr [rcx+1Ch], 2
0x18006d354  jz      short loc_18006D36E
0x18006d356  mov     rcx, [rcx+10h]
0x18006d35a  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d361  mov     edx, 0Fh
0x18006d366  mov     r9d, eax
0x18006d369  call    WPP_SF_d
0x18006d36e  mov     rax, 200000000h
0x18006d378  jmp     short loc_18006D3F6
0x18006d37a  cmp     [rbp+4Fh+arg_10], 4
0x18006d37e  jnz     short loc_18006D3BE
0x18006d380  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d387  lea     rdx, WPP_GLOBAL_Control
0x18006d38e  cmp     rcx, rdx
0x18006d391  jz      short loc_18006D3AE
0x18006d393  test    [rcx+1Ch], sil
0x18006d397  jz      short loc_18006D3AE
0x18006d399  mov     rcx, [rcx+10h]
0x18006d39d  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d3a4  mov     edx, 10h
0x18006d3a9  call    WPP_SF_
0x18006d3ae  mov     byte ptr [rbp+4Fh+arg_8], 1
0x18006d3b2  mov     rax, 400000000h
0x18006d3bc  jmp     short loc_18006D3F6
0x18006d3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d3c5  lea     rdx, WPP_GLOBAL_Control
0x18006d3cc  cmp     rcx, rdx
0x18006d3cf  jz      short loc_18006D3EC
0x18006d3d1  test    [rcx+1Ch], sil
0x18006d3d5  jz      short loc_18006D3EC
0x18006d3d7  mov     rcx, [rcx+10h]
0x18006d3db  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d3e2  mov     edx, 11h
0x18006d3e7  call    WPP_SF_
0x18006d3ec  mov     rax, 800000000h
0x18006d3f6  or      rdi, rax
0x18006d3f9  mov     [rbp+4Fh+var_80], r13d
0x18006d3fd  lea     rax, [rbp+4Fh+arg_10]
0x18006d401  mov     [rbp+4Fh+arg_10], 4
0x18006d408  mov     [rsp+0C0h+var_98], rax
0x18006d40d  lea     r9, [rbp+4Fh+var_78]
0x18006d411  lea     rax, [rbp+4Fh+var_80]
0x18006d415  xor     r8d, r8d
0x18006d418  mov     [rsp+0C0h+var_A0], rax
0x18006d41d  lea     rcx, WNF_PROV_AUTOPILOT_DEVICE_NOT_MANAGED
0x18006d424  mov     rax, r14
0x18006d427  xor     edx, edx
0x18006d429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d42e  test    eax, eax
0x18006d430  jns     short loc_18006D46F
0x18006d432  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d439  lea     r14, WPP_GLOBAL_Control
0x18006d440  cmp     rcx, r14
0x18006d443  jz      short loc_18006D463
0x18006d445  test    byte ptr [rcx+1Ch], 2
0x18006d449  jz      short loc_18006D463
0x18006d44b  mov     rcx, [rcx+10h]
0x18006d44f  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d456  mov     edx, 12h
0x18006d45b  mov     r9d, eax
0x18006d45e  call    WPP_SF_d
0x18006d463  mov     rax, 1000000000h
0x18006d46d  jmp     short loc_18006D4EA
0x18006d46f  cmp     [rbp+4Fh+arg_10], 4
0x18006d473  jnz     short loc_18006D4B2
0x18006d475  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d47c  lea     r14, WPP_GLOBAL_Control
0x18006d483  cmp     rcx, r14
0x18006d486  jz      short loc_18006D4A3
0x18006d488  test    [rcx+1Ch], sil
0x18006d48c  jz      short loc_18006D4A3
0x18006d48e  mov     rcx, [rcx+10h]
0x18006d492  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d499  mov     edx, 13h
0x18006d49e  call    WPP_SF_
0x18006d4a3  mov     r13b, 1
0x18006d4a6  mov     rax, 2000000000h
0x18006d4b0  jmp     short loc_18006D4EA
0x18006d4b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d4b9  lea     r14, WPP_GLOBAL_Control
0x18006d4c0  cmp     rcx, r14
0x18006d4c3  jz      short loc_18006D4E0
0x18006d4c5  test    [rcx+1Ch], sil
0x18006d4c9  jz      short loc_18006D4E0
0x18006d4cb  mov     rcx, [rcx+10h]
0x18006d4cf  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d4d6  mov     edx, 14h
0x18006d4db  call    WPP_SF_
0x18006d4e0  mov     rax, 4000000000h
0x18006d4ea  or      rdi, rax
0x18006d4ed  lea     rcx, [rbp+4Fh+var_7C]
0x18006d4f1  mov     rax, rbx
0x18006d4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d4f9  mov     ebx, eax
0x18006d4fb  test    eax, eax
0x18006d4fd  jns     short loc_18006D538
0x18006d4ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d506  cmp     rcx, r14
0x18006d509  jz      short loc_18006D529
0x18006d50b  test    byte ptr [rcx+1Ch], 2
0x18006d50f  jz      short loc_18006D529
0x18006d511  mov     rcx, [rcx+10h]
0x18006d515  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d51c  mov     edx, 15h
0x18006d521  mov     r9d, eax
0x18006d524  call    WPP_SF_d
0x18006d529  mov     rax, 8000000000h
0x18006d533  jmp     loc_18006D286
0x18006d538  xor     r14b, r14b
0x18006d53b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d542  lea     rbx, WPP_GLOBAL_Control
0x18006d549  cmp     rcx, rbx
0x18006d54c  jz      short loc_18006D56D
0x18006d54e  test    [rcx+1Ch], sil
0x18006d552  jz      short loc_18006D56D
0x18006d554  mov     r9d, [rbp+4Fh+var_7C]
0x18006d558  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18006d55f  mov     rcx, [rcx+10h]
0x18006d563  mov     edx, 16h
0x18006d568  call    WPP_SF_d
0x18006d56d  lea     rax, [rbp+4Fh+arg_10]
0x18006d571  mov     [rbp+4Fh+var_80], 0
0x18006d578  mov     [rsp+0C0h+var_98], rax
0x18006d57d  lea     r9, [rbp+4Fh+var_78]
0x18006d581  lea     rax, [rbp+4Fh+var_80]
0x18006d585  mov     [rbp+4Fh+arg_10], 4
0x18006d58c  mov     [rsp+0C0h+var_A0], rax
0x18006d591  lea     rcx, WNF_PROV_DEVICE_BOOTSTRAP_COMPLETE
0x18006d598  mov     rax, [rbp+4Fh+arg_0]
0x18006d59c  xor     r8d, r8d
0x18006d59f  xor     edx, edx
0x18006d5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d5a6  test    eax, eax
0x18006d5a8  jns     short loc_18006D5E0
0x18006d5aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d5b1  cmp     rcx, rbx
0x18006d5b4  jz      short loc_18006D5D4
0x18006d5b6  test    byte ptr [rcx+1Ch], 2
0x18006d5ba  jz      short loc_18006D5D4
0x18006d5bc  mov     rcx, [rcx+10h]
0x18006d5c0  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
  ... truncated ...
```

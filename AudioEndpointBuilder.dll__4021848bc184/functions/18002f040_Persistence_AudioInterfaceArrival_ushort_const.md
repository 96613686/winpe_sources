# Persistence_AudioInterfaceArrival(ushort const *)

- ea: `0x18002f040`
- end: `0x18002f6ea`
- name: `?Persistence_AudioInterfaceArrival@@YAJPEBG@Z`
- size: `1706`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180029780`
- `0x18002fecc`

## callees

- `0x180010da8`
- `0x18001707c`
- `0x18001d560`
- `0x18001f374`
- `0x18001ff7c`
- `0x18002f040`
- `0x1800301b8`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f16d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f1fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f2a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f34d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f4c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f5b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f623`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f683`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f16d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f1fe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f2a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f34d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f4c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f5b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f623`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002f683`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f07f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002f07f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f551`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002f551`
- `ntdll!EtwEventWriteTransfer` at `0x18002f163`
- `ntdll!EtwEventWriteTransfer` at `0x18002f163`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f434`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f45a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f434`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f45a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f4bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f5a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f679`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f4bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f5a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f679`

## string_xrefs

- `0x18002f1e9`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002f292`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002f338`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002f3cf`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002f408`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002f4a0`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`
- `0x18002f5fe`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall Persistence_AudioInterfaceArrival(const unsigned __int16 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  int v4; // ebx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, const unsigned __int16 *, __int64 *); // rsi
  __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  struct IMMDeviceVtbl *lpVtbl; // rax
  int v16; // eax
  int v17; // eax
  struct IMMDeviceVtbl *v18; // rax
  int v19; // eax
  unsigned int v20; // ebx
  _QWORD *i; // rax
  _QWORD *v22; // rdi
  __int64 v23; // rsi
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  int v27; // eax
  unsigned int v28; // ebx
  int lpString2; // [rsp+20h] [rbp-59h]
  struct IMMDevice *v30; // [rsp+30h] [rbp-49h] BYREF
  __int64 v31; // [rsp+38h] [rbp-41h] BYREF
  __int64 v32; // [rsp+40h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v34; // [rsp+50h] [rbp-29h] BYREF
  _QWORD v35[2]; // [rsp+58h] [rbp-21h] BYREF
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-11h] BYREF
  char *v37; // [rsp+78h] [rbp-1h]
  int v38; // [rsp+80h] [rbp+7h]
  int v39; // [rsp+84h] [rbp+Bh]
  const unsigned __int16 *v40; // [rsp+88h] [rbp+Fh]
  int v41; // [rsp+90h] [rbp+17h]
  int v42; // [rsp+94h] [rbp+1Bh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v32 = 0;
  v30 = 0;
  v31 = 0;
  EnterCriticalSection(&g_PersistedControlListLock);
  v35[0] = &g_PersistedControlListLock;
  if ( !g_PersistenceInitialized )
  {
    v2 = *((_QWORD *)AudioEndpointBuilderTelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v2 > 4u )
    {
      if ( a1 )
      {
        v3 = -1;
        do
          ++v3;
        while ( a1[v3] );
        v4 = 2 * v3 + 2;
      }
      else
      {
        a1 = &LocaleName;
        v4 = 2;
      }
      v40 = a1;
      v41 = v4;
      v42 = 0;
      v35[0] = 0x40B000000LL;
      v35[1] = 0;
      pvar[0] = *(PROPVARIANT *)(v2 + 8);
      pvar[1] = (PROPVARIANT)(*(unsigned __int16 *)pvar[0] | 0x200000000LL);
      v37 = byte_180077A4D;
      v38 = 84;
      v39 = 1;
      v34 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(*(_QWORD *)(v2 + 32), v35, 0, 0);
    }
    LeaveCriticalSection(&g_PersistedControlListLock);
LABEL_83:
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    return 0;
  }
  v31 = 0;
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))g_DeviceEnumerator->lpVtbl->QueryInterface)(
         g_DeviceEnumerator,
         &GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0,
         &v31);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    LeaveCriticalSection(&g_PersistedControlListLock);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    return v6;
  }
  v8 = v31;
  v9 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 *))(*(_QWORD *)v31 + 40LL);
  v10 = v32;
  v32 = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = v9(v8, a1, &v32);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v11,
      lpString2);
    LeaveCriticalSection(&g_PersistedControlListLock);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    return v12;
  }
  v30 = 0;
  v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IMMDevice **))v32)(
          v32,
          &GUID_d666063f_1587_4e43_81f1_b948e807363f,
          &v30);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v13,
      lpString2);
    LeaveCriticalSection(&g_PersistedControlListLock);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v30 )
      ((void (__fastcall *)(struct IMMDevice *))v30->lpVtbl->Release)(v30);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    return v14;
  }
  *(_OWORD *)pvar = 0;
  v37 = 0;
  lpVtbl = v30->lpVtbl;
  pv = 0;
  v16 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, LPVOID *))lpVtbl->OpenPropertyStore)(v30, 0, &pv);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x39A,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v16,
      lpString2);
    goto LABEL_39;
  }
  v17 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, PROPVARIANT *))(*(_QWORD *)pv + 40LL))(
          pv,
          PKEY_AudioDevice_DontPersistControls,
          pvar);
  if ( v17 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x39E,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v17,
      lpString2);
    goto LABEL_39;
  }
  if ( LOWORD(pvar[0]) && (LOWORD(pvar[0]) != 19 || LODWORD(pvar[1])) )
  {
LABEL_39:
    PropVariantClear(pvar);
    if ( pv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
LABEL_79:
    LeaveCriticalSection(&g_PersistedControlListLock);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v30 )
      ((void (__fastcall *)(struct IMMDevice *))v30->lpVtbl->Release)(v30);
    goto LABEL_83;
  }
  PropVariantClear(pvar);
  if ( pv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
  pv = 0;
  v18 = v30->lpVtbl;
  pv = 0;
  v19 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))v18->GetId)(v30, &pv);
  v20 = v19;
  if ( v19 >= 0 )
  {
    for ( i = g_PersistedControlList; i; i = v22 )
    {
      v22 = (_QWORD *)*i;
      v23 = i[2];
      if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v23 + 72), -1, (PCNZWCH)pv, -1) == 2 )
      {
        v24 = AudioEndpointBuilderTelemetryProvider::Provider();
        if ( *(_DWORD *)v24 > 4u )
        {
          v34 = *(_DWORD *)(v23 + 64);
          v35[0] = *(_QWORD *)(v23 + 72);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (_DWORD)v24,
            (unsigned int)byte_1800779E1,
            v25,
            v26,
            (__int64)v35,
            (__int64)&v34);
        }
        if ( pv )
          CoTaskMemFree(pv);
        LeaveCriticalSection(&g_PersistedControlListLock);
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v30 )
          ((void (__fastcall *)(struct IMMDevice *))v30->lpVtbl->Release)(v30);
        goto LABEL_83;
      }
    }
    v27 = ProcessNewDevicePersistenceState(v30);
    v28 = v27;
    if ( v27 >= 0 )
    {
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_79;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v27,
      lpString2);
    if ( pv )
      CoTaskMemFree(pv);
    LeaveCriticalSection(&g_PersistedControlListLock);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v30 )
      ((void (__fastcall *)(struct IMMDevice *))v30->lpVtbl->Release)(v30);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    return v28;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
      (const char *)(unsigned int)v19,
      lpString2);
    if ( pv )
      CoTaskMemFree(pv);
    LeaveCriticalSection(&g_PersistedControlListLock);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v30 )
      ((void (__fastcall *)(struct IMMDevice *))v30->lpVtbl->Release)(v30);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    return v20;
  }
}

```

## disassembly

```asm
0x18002f040  push    rbp
0x18002f042  push    rbx
0x18002f043  push    rsi
0x18002f044  push    rdi
0x18002f045  push    r14
0x18002f047  push    r15
0x18002f049  lea     rbp, [rsp-2Fh]
0x18002f04e  sub     rsp, 0A8h
0x18002f055  mov     rax, cs:__security_cookie
0x18002f05c  xor     rax, rsp
0x18002f05f  mov     [rbp+57h+var_38], rax
0x18002f063  mov     rdi, rcx
0x18002f066  xor     r14d, r14d
0x18002f069  mov     [rbp+57h+var_90], r14
0x18002f06d  mov     [rbp+57h+var_A0], r14
0x18002f071  mov     [rbp+57h+var_98], r14
0x18002f075  lea     r15, ?g_PersistedControlListLock@@3Vcritical_section@wil@@A; wil::critical_section g_PersistedControlListLock
0x18002f07c  mov     rcx, r15; lpCriticalSection
0x18002f07f  call    cs:__imp_EnterCriticalSection
0x18002f085  mov     [rbp+57h+var_78], r15
0x18002f089  cmp     cs:?g_PersistenceInitialized@@3_NA, r14b; bool g_PersistenceInitialized
0x18002f090  jnz     loc_18002F1A5
0x18002f096  call    ?Instance@AudioEndpointBuilderTelemetryProvider@@KAPEAV1@XZ; AudioEndpointBuilderTelemetryProvider::Instance(void)
0x18002f09b  mov     rcx, [rax+8]
0x18002f09f  mov     eax, [rcx]
0x18002f0a1  cmp     eax, 4
0x18002f0a4  jbe     loc_18002F16A
0x18002f0aa  test    rdi, rdi
0x18002f0ad  jz      short loc_18002F0D4
0x18002f0af  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002f0b6  nop     word ptr [rax+rax+00000000h]
0x18002f0c0  lea     rbx, [rbx+1]
0x18002f0c4  cmp     word ptr [rdi+rbx*2], 0
0x18002f0c9  jnz     short loc_18002F0C0
0x18002f0cb  lea     ebx, ds:2[rbx*2]
0x18002f0d2  jmp     short loc_18002F0E0
0x18002f0d4  lea     rdi, LocaleName
0x18002f0db  mov     ebx, 2
0x18002f0e0  mov     [rbp+57h+var_48], rdi
0x18002f0e4  mov     [rbp+57h+var_40], ebx
0x18002f0e7  mov     [rbp+57h+var_3C], r14d
0x18002f0eb  mov     dword ptr [rbp+57h+var_78], 0B000000h
0x18002f0f2  movzx   eax, cs:word_180077A43
0x18002f0f9  mov     dword ptr [rbp+57h+var_78+4], eax
0x18002f0fc  mov     [rbp+57h+var_70], r14
0x18002f100  mov     rax, [rcx+8]
0x18002f104  mov     [rbp+57h+pvar], rax
0x18002f108  movzx   eax, word ptr [rax]
0x18002f10b  mov     dword ptr [rbp+57h+pvar+8], eax
0x18002f10e  mov     dword ptr [rbp+57h+pvar+0Ch], 2
0x18002f115  lea     rax, byte_180077A4D
0x18002f11c  mov     [rbp+57h+var_58], rax
0x18002f120  mov     [rbp+57h+var_50], 54h ; 'T'
0x18002f127  mov     [rbp+57h+var_4C], 1
0x18002f12e  lea     rax, _TraceLoggingMetadataEnd
0x18002f135  lea     rdx, _TraceLoggingMetadata
0x18002f13c  sub     eax, edx
0x18002f13e  mov     [rbp+57h+var_80], eax
0x18002f141  mov     eax, [rbp+57h+var_80]
0x18002f144  lea     rax, [rbp+57h+pvar]
0x18002f148  mov     qword ptr [rsp+0D0h+cchCount2], rax
0x18002f14d  mov     dword ptr [rsp+0D0h+lpString2], 3
0x18002f155  xor     r9d, r9d
0x18002f158  xor     r8d, r8d
0x18002f15b  lea     rdx, [rbp+57h+var_78]
0x18002f15f  mov     rcx, [rcx+20h]
0x18002f163  call    cs:__imp_EtwEventWriteTransfer
0x18002f169  nop
0x18002f16a  mov     rcx, r15; lpCriticalSection
0x18002f16d  call    cs:__imp_LeaveCriticalSection
0x18002f173  nop
0x18002f174  mov     rcx, [rbp+57h+var_98]
0x18002f178  test    rcx, rcx
0x18002f17b  jz      short loc_18002F18A
0x18002f17d  mov     rax, [rcx]
0x18002f180  mov     rax, [rax+10h]
0x18002f184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f189  nop
0x18002f18a  mov     rcx, [rbp+57h+var_A0]
0x18002f18e  test    rcx, rcx
0x18002f191  jz      short loc_18002F1A0
0x18002f193  mov     rax, [rcx]
0x18002f196  mov     rax, [rax+10h]
0x18002f19a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f19f  nop
0x18002f1a0  jmp     loc_18002F6B6
0x18002f1a5  mov     rcx, [rbp+57h+var_98]
0x18002f1a9  mov     [rbp+57h+var_98], r14
0x18002f1ad  test    rcx, rcx
0x18002f1b0  jz      short loc_18002F1BF
0x18002f1b2  mov     rax, [rcx]
0x18002f1b5  mov     rax, [rax+10h]
0x18002f1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1be  nop
0x18002f1bf  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18002f1c6  mov     rax, [rcx]
0x18002f1c9  lea     r8, [rbp+57h+var_98]
0x18002f1cd  lea     rdx, _GUID_3e52272f_3c89_45f8_be26_cb3b91ab42a0
0x18002f1d4  mov     rax, [rax]
0x18002f1d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1dc  mov     ebx, eax
0x18002f1de  test    eax, eax
0x18002f1e0  jns     short loc_18002F24E
0x18002f1e2  mov     rcx, [rbp+5Fh]; this
0x18002f1e6  mov     r9d, eax; char *
0x18002f1e9  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18002f1f0  mov     edx, 53h ; 'S'; void *
0x18002f1f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f1fa  nop
0x18002f1fb  mov     rcx, r15; lpCriticalSection
0x18002f1fe  call    cs:__imp_LeaveCriticalSection
0x18002f204  nop
0x18002f205  mov     rcx, [rbp+57h+var_98]
0x18002f209  test    rcx, rcx
0x18002f20c  jz      short loc_18002F21B
0x18002f20e  mov     rax, [rcx]
0x18002f211  mov     rax, [rax+10h]
0x18002f215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f21a  nop
0x18002f21b  mov     rcx, [rbp+57h+var_A0]
0x18002f21f  test    rcx, rcx
0x18002f222  jz      short loc_18002F231
0x18002f224  mov     rax, [rcx]
0x18002f227  mov     rax, [rax+10h]
0x18002f22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f230  nop
0x18002f231  mov     rcx, [rbp+57h+var_90]
0x18002f235  test    rcx, rcx
0x18002f238  jz      short loc_18002F247
0x18002f23a  mov     rax, [rcx]
0x18002f23d  mov     rax, [rax+10h]
0x18002f241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f246  nop
0x18002f247  mov     eax, ebx
0x18002f249  jmp     loc_18002F6CE
0x18002f24e  mov     rbx, [rbp+57h+var_98]
0x18002f252  mov     rax, [rbx]
0x18002f255  mov     rsi, [rax+28h]
0x18002f259  mov     rcx, [rbp+57h+var_90]
0x18002f25d  mov     [rbp+57h+var_90], r14
0x18002f261  test    rcx, rcx
0x18002f264  jz      short loc_18002F273
0x18002f266  mov     r8, [rcx]
0x18002f269  mov     rax, [r8+10h]
0x18002f26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f272  nop
0x18002f273  lea     r8, [rbp+57h+var_90]
0x18002f277  mov     rdx, rdi
0x18002f27a  mov     rcx, rbx
0x18002f27d  mov     rax, rsi
0x18002f280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f285  mov     ebx, eax
0x18002f287  test    eax, eax
0x18002f289  jns     short loc_18002F2F7
0x18002f28b  mov     rcx, [rbp+5Fh]; this
0x18002f28f  mov     r9d, eax; char *
0x18002f292  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18002f299  mov     edx, 54h ; 'T'; void *
0x18002f29e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f2a3  nop
0x18002f2a4  mov     rcx, r15; lpCriticalSection
0x18002f2a7  call    cs:__imp_LeaveCriticalSection
0x18002f2ad  nop
0x18002f2ae  mov     rcx, [rbp+57h+var_98]
0x18002f2b2  test    rcx, rcx
0x18002f2b5  jz      short loc_18002F2C4
0x18002f2b7  mov     rax, [rcx]
0x18002f2ba  mov     rax, [rax+10h]
0x18002f2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2c3  nop
0x18002f2c4  mov     rcx, [rbp+57h+var_A0]
0x18002f2c8  test    rcx, rcx
0x18002f2cb  jz      short loc_18002F2DA
0x18002f2cd  mov     rax, [rcx]
0x18002f2d0  mov     rax, [rax+10h]
0x18002f2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2d9  nop
0x18002f2da  mov     rcx, [rbp+57h+var_90]
0x18002f2de  test    rcx, rcx
0x18002f2e1  jz      short loc_18002F2F0
0x18002f2e3  mov     rax, [rcx]
0x18002f2e6  mov     rax, [rax+10h]
0x18002f2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2ef  nop
0x18002f2f0  mov     eax, ebx
0x18002f2f2  jmp     loc_18002F6CE
0x18002f2f7  mov     rcx, [rbp+57h+var_A0]
0x18002f2fb  mov     [rbp+57h+var_A0], r14
0x18002f2ff  test    rcx, rcx
0x18002f302  jz      short loc_18002F311
0x18002f304  mov     rax, [rcx]
0x18002f307  mov     rax, [rax+10h]
0x18002f30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f310  nop
0x18002f311  mov     rcx, [rbp+57h+var_90]
0x18002f315  mov     rax, [rcx]
0x18002f318  lea     r8, [rbp+57h+var_A0]
0x18002f31c  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x18002f323  mov     rax, [rax]
0x18002f326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f32b  mov     ebx, eax
0x18002f32d  test    eax, eax
0x18002f32f  jns     short loc_18002F39D
0x18002f331  mov     rcx, [rbp+5Fh]; this
0x18002f335  mov     r9d, eax; char *
0x18002f338  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18002f33f  mov     edx, 55h ; 'U'; void *
0x18002f344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f349  nop
0x18002f34a  mov     rcx, r15; lpCriticalSection
0x18002f34d  call    cs:__imp_LeaveCriticalSection
0x18002f353  nop
0x18002f354  mov     rcx, [rbp+57h+var_98]
0x18002f358  test    rcx, rcx
0x18002f35b  jz      short loc_18002F36A
0x18002f35d  mov     rax, [rcx]
0x18002f360  mov     rax, [rax+10h]
0x18002f364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f369  nop
0x18002f36a  mov     rcx, [rbp+57h+var_A0]
0x18002f36e  test    rcx, rcx
0x18002f371  jz      short loc_18002F380
0x18002f373  mov     rax, [rcx]
0x18002f376  mov     rax, [rax+10h]
0x18002f37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f37f  nop
0x18002f380  mov     rcx, [rbp+57h+var_90]
0x18002f384  test    rcx, rcx
0x18002f387  jz      short loc_18002F396
0x18002f389  mov     rax, [rcx]
0x18002f38c  mov     rax, [rax+10h]
0x18002f390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f395  nop
0x18002f396  mov     eax, ebx
0x18002f398  jmp     loc_18002F6CE
0x18002f39d  mov     rcx, [rbp+57h+var_A0]
0x18002f3a1  xorps   xmm0, xmm0
0x18002f3a4  xor     eax, eax
0x18002f3a6  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18002f3aa  mov     [rbp+57h+var_58], rax
0x18002f3ae  mov     rax, [rcx]
0x18002f3b1  mov     [rbp+57h+pv], r14
0x18002f3b5  lea     r8, [rbp+57h+pv]
0x18002f3b9  xor     edx, edx
0x18002f3bb  mov     rax, [rax+20h]
0x18002f3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3c4  mov     rcx, [rbp+5Fh]; this
0x18002f3c8  test    eax, eax
0x18002f3ca  jns     short loc_18002F3E2
0x18002f3cc  mov     r9d, eax; char *
0x18002f3cf  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18002f3d6  mov     edx, 39Ah; void *
0x18002f3db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f3e0  jmp     short loc_18002F430
0x18002f3e2  mov     rcx, [rbp+57h+pv]
0x18002f3e6  mov     rax, [rcx]
0x18002f3e9  lea     r8, [rbp+57h+pvar]
0x18002f3ed  lea     rdx, PKEY_AudioDevice_DontPersistControls
0x18002f3f4  mov     rax, [rax+28h]
0x18002f3f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3fd  mov     rcx, [rbp+5Fh]; this
0x18002f401  test    eax, eax
0x18002f403  jns     short loc_18002F41B
0x18002f405  mov     r9d, eax; char *
0x18002f408  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x18002f40f  mov     edx, 39Eh; void *
0x18002f414  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f419  jmp     short loc_18002F430
0x18002f41b  movzx   eax, word ptr [rbp+57h+pvar]
0x18002f41f  test    ax, ax
0x18002f422  jz      short loc_18002F456
0x18002f424  cmp     ax, 13h
0x18002f428  jnz     short loc_18002F430
0x18002f42a  cmp     dword ptr [rbp+57h+pvar+8], 0
0x18002f42e  jz      short loc_18002F456
0x18002f430  lea     rcx, [rbp+57h+pvar]; pvar
0x18002f434  call    cs:__imp_PropVariantClear
0x18002f43a  nop
0x18002f43b  mov     rcx, [rbp+57h+pv]
0x18002f43f  test    rcx, rcx
0x18002f442  jz      short loc_18002F451
0x18002f444  mov     rax, [rcx]
0x18002f447  mov     rax, [rax+10h]
0x18002f44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f450  nop
0x18002f451  jmp     loc_18002F680
0x18002f456  lea     rcx, [rbp+57h+pvar]; pvar
0x18002f45a  call    cs:__imp_PropVariantClear
0x18002f460  nop
0x18002f461  mov     rcx, [rbp+57h+pv]
0x18002f465  test    rcx, rcx
0x18002f468  jz      short loc_18002F477
0x18002f46a  mov     rax, [rcx]
0x18002f46d  mov     rax, [rax+10h]
0x18002f471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f476  nop
0x18002f477  mov     [rbp+57h+pv], r14
0x18002f47b  mov     rcx, [rbp+57h+var_A0]
0x18002f47f  mov     rax, [rcx]
0x18002f482  mov     [rbp+57h+pv], r14
  ... truncated ...
```

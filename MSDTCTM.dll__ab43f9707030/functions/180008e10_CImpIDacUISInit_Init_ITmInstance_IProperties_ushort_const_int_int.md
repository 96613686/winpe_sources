# CImpIDacUISInit::Init(ITmInstance *,IProperties *,ushort const *,int,int)

- ea: `0x180008e10`
- end: `0x18000936a`
- name: `?Init@CImpIDacUISInit@@UEAAJPEAUITmInstance@@PEAUIProperties@@PEBGHH@Z`
- size: `1370`
- prototype: `__int64 __fastcall(CImpIDacUISInit *__hidden this, struct ITmInstance *, struct IProperties *, const unsigned __int16 *, int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800063b0`
- `0x180008a50`
- `0x180008e10`
- `0x180013e24`
- `0x180015230`
- `0x1800240b0`
- `0x1800ab05c`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800092bb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800092bb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000922c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000925e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000922c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000925e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180008e8a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180008e8a`
- `MSDTCPRX!__imp_DllGetDTCConnectionManager` at `0x180008f3e`
- `MSDTCPRX!__imp_DllGetDTCConnectionManager` at `0x180008f3e`
- `MSDTCPRX!__imp_?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z` at `0x180008eb6`
- `MSDTCPRX!__imp_?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z` at `0x180008eb6`
- `CLUSAPI!GetNodeClusterState` at `0x180008fa8`
- `CLUSAPI!GetNodeClusterState` at `0x180008fa8`

## string_xrefs

- `0x180008e83`: `COMRES.DLL`
- `0x180008fe9`: `com\complus\dtc\shared\util\clusterutilbasic.cpp`
- `0x18000920b`: `UpdateLimit`
- `0x18000932c`: `com\complus\dtc\dtc\dtcuis\src\uisimp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CImpIDacUISInit::Init(
        CImpIDacUISInit *this,
        struct ITmInstance *a2,
        struct IProperties *a3,
        const unsigned __int16 *a4,
        int a5,
        int a6)
{
  __int64 v9; // rdi
  HMODULE Library; // rax
  __int64 result; // rax
  struct INameObject *v12; // rax
  struct INameObject *v13; // r14
  int DTCConnectionManager; // edi
  __int64 (__fastcall ***v15)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall ***v16)(_QWORD, GUID *, _QWORD *); // rdi
  signed int NodeClusterState; // eax
  unsigned int v18; // r15d
  void *v19; // r9
  CUisImpIConnectionNotify *v20; // rax
  CUisImpIConnectionNotify *v21; // rsi
  unsigned int v22; // r15d
  unsigned int v23; // esi
  __int64 v24; // rax
  _QWORD *v25; // r9
  __int64 v26; // rcx
  int v27; // eax
  LPDWORD lpThreadId; // [rsp+28h] [rbp-71h]
  LPDWORD lpThreadIda; // [rsp+28h] [rbp-71h]
  __int64 (__fastcall ***v30)(_QWORD, GUID *, _QWORD *); // [rsp+50h] [rbp-49h] BYREF
  struct ITmInstance *v31; // [rsp+58h] [rbp-41h] BYREF
  DWORD pdwClusterState[2]; // [rsp+60h] [rbp-39h] BYREF
  DWORD ThreadId; // [rsp+68h] [rbp-31h] BYREF
  __int64 v34; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *v35[2]; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int16 v36[16]; // [rsp+88h] [rbp-11h] BYREF

  v30 = 0;
  ThreadId = 0;
  v34 = 0;
  if ( !a2 || !a3 )
    return 2147942487LL;
  *((_QWORD *)this + 4) = a2;
  (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)a2 + 8LL))(a2);
  *(_QWORD *)(*((_QWORD *)this + 1) + 16LL) = a3;
  v9 = *((_QWORD *)this + 1);
  Library = LoadLibraryExA("COMRES.DLL", 0, 0);
  *(_QWORD *)(v9 + 392) = Library;
  if ( !Library )
    return 2147500037LL;
  *(_DWORD *)(*((_QWORD *)this + 1) + 536LL) = a5;
  v12 = ContactToNameObject(a3);
  v13 = v12;
  if ( !v12 )
    return 2147942414LL;
  DTCConnectionManager = (*(__int64 (__fastcall **)(struct INameObject *, const unsigned __int16 *))(*(_QWORD *)v12 + 104LL))(
                           v12,
                           a4);
  if ( DTCConnectionManager < 0 )
  {
LABEL_7:
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v13 + 16LL))(v13);
    return (unsigned int)DTCConnectionManager;
  }
  if ( (**(int (__fastcall ***)(struct IProperties *, GUID *, __int64))a3)(
         a3,
         &IID_ICustomProperties,
         *((_QWORD *)this + 1) + 24LL) < 0 )
  {
LABEL_9:
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v13 + 16LL))(v13);
    return 2147942414LL;
  }
  DTCConnectionManager = DllGetDTCConnectionManager(&CLSID_DTCCM, &IID_IConnectionManager, &v30);
  if ( DTCConnectionManager )
    goto LABEL_7;
  v15 = v30;
  *((_QWORD *)this + 3) = v30;
  DTCConnectionManager = (**v15)(v15, &IID_IConnectionManagerConfig, &v30);
  if ( DTCConnectionManager )
    goto LABEL_7;
  v16 = v30;
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64))(*v30)[5])(v30, 1);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64))(*v16)[9])(v16, 1);
  pdwClusterState[0] = 0;
  NodeClusterState = GetNodeClusterState(0, pdwClusterState);
  v18 = NodeClusterState;
  if ( NodeClusterState )
  {
    if ( NodeClusterState > 0 )
      v18 = (unsigned __int16)NodeClusterState | 0x80070000;
    LODWORD(lpThreadId) = v18;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\clusterutilbasic.cpp",
      101,
      L"MtxCluIsClusterPresentNonAdmin",
      lpThreadId,
      L"GetNodeClusterState failed");
    memset(v36, 0, 30);
    StringCchPrintfW(v36, 0xFu, L"0x%08X", v18);
    v35[0] = 0;
    v35[1] = v36;
    LODWORD(lpThreadIda) = 0;
    DtcWriteToEventLoggerExW(1u, 0xEu, 0x40001008u, v19, 2u, (size_t)lpThreadIda, (const unsigned __int16 **)v35, 0, 1);
LABEL_18:
    if ( !a6 )
    {
      result = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *), __int64))(*v16)[15])(
                 v16,
                 32);
      if ( (_DWORD)result )
        return result;
    }
    goto LABEL_20;
  }
  if ( pdwClusterState[0] <= 1 )
    goto LABEL_18;
LABEL_20:
  v31 = 0;
  if ( (*(int (__fastcall **)(struct IProperties *, struct ITmInstance **))(*(_QWORD *)a3 + 176LL))(a3, &v31) < 0 )
    goto LABEL_9;
  v20 = (CUisImpIConnectionNotify *)operator new(0x48u);
  *(_QWORD *)pdwClusterState = v20;
  v21 = v20 ? CUisImpIConnectionNotify::CUisImpIConnectionNotify(v20, *((struct CUISCore **)this + 1), v31) : 0LL;
  (*(void (__fastcall **)(struct ITmInstance *))(*(_QWORD *)v31 + 16LL))(v31);
  if ( !v21 )
    goto LABEL_9;
  (*(void (__fastcall **)(CUisImpIConnectionNotify *))(*(_QWORD *)v21 + 8LL))(v21);
  v22 = (*(__int64 (__fastcall **)(_QWORD, struct INameObject *, CUisImpIConnectionNotify *, _QWORD))(**((_QWORD **)this + 3) + 24LL))(
          *((_QWORD *)this + 3),
          v13,
          v21,
          0);
  if ( v22 )
  {
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v13 + 16LL))(v13);
    return v22;
  }
  (*(void (__fastcall **)(CUisImpIConnectionNotify *))(*(_QWORD *)v21 + 16LL))(v21);
  v23 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3));
  if ( v23 )
  {
    (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v13 + 16LL))(v13);
    return v23;
  }
  v23 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[3])(v16);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v16)[2])(v16);
  (*(void (__fastcall **)(struct INameObject *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v23 )
    return v23;
  (*(void (__fastcall **)(_QWORD, const char *, const char *, __int64))(**(_QWORD **)(*((_QWORD *)this + 1) + 24LL)
                                                                      + 56LL))(
    *(_QWORD *)(*((_QWORD *)this + 1) + 24LL),
    "DAC",
    "TraceLimit",
    *((_QWORD *)this + 1) + 12LL);
  (*(void (__fastcall **)(_QWORD, const char *, const char *, unsigned int *))(**(_QWORD **)(*((_QWORD *)this + 1) + 24LL)
                                                                             + 56LL))(
    *(_QWORD *)(*((_QWORD *)this + 1) + 24LL),
    "DAC",
    "ShowLimit",
    &z_dwShowLimit);
  (*(void (__fastcall **)(_QWORD, const char *, const char *, unsigned int *))(**(_QWORD **)(*((_QWORD *)this + 1) + 24LL)
                                                                             + 56LL))(
    *(_QWORD *)(*((_QWORD *)this + 1) + 24LL),
    "DAC",
    "UpdateLimit",
    &z_dwUpdateLimit);
  *(_QWORD *)(*((_QWORD *)this + 1) + 520LL) = CreateEventA(0, 0, 0, 0);
  if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 520LL) )
    v23 = -2147024882;
  *(_QWORD *)(*((_QWORD *)this + 1) + 544LL) = CreateEventA(0, 1, 0, 0);
  v24 = *((_QWORD *)this + 1);
  if ( !*(_QWORD *)(v24 + 544) )
    v23 = -2147024882;
  *(_DWORD *)(v24 + 528) = 1;
  if ( !v23 )
  {
    v25 = (_QWORD *)*((_QWORD *)this + 1);
    if ( !v25[18] )
    {
      *(_QWORD *)(*((_QWORD *)this + 1) + 144LL) = CreateThread(0, 0, UIServerThread, v25, 0, &ThreadId);
      v26 = *((_QWORD *)this + 1);
      if ( !*(_QWORD *)(v26 + 144) )
      {
        (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v26)(v26, &IID_IDtcTrace, &v34);
        v27 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)v34 + 24LL))(
                v34,
                1,
                1,
                0,
                -2147024882,
                0,
                0,
                0);
        if ( v27 < 0 )
          TraceFile(v27, "pTrace->Trace", "com\\complus\\dtc\\dtc\\dtcuis\\src\\uisimp.cpp", 0x8AFu);
        return (unsigned int)-2147024882;
      }
    }
  }
  return v23;
}

```

## disassembly

```asm
0x180008e10  push    rbp
0x180008e12  push    rbx
0x180008e13  push    rsi
0x180008e14  push    rdi
0x180008e15  push    r12
0x180008e17  push    r14
0x180008e19  push    r15
0x180008e1b  lea     rbp, [rsp-17h]
0x180008e20  sub     rsp, 0B0h
0x180008e27  mov     rax, cs:__security_cookie
0x180008e2e  xor     rax, rsp
0x180008e31  mov     [rbp+47h+var_38], rax
0x180008e35  mov     r15, r9
0x180008e38  mov     rsi, r8
0x180008e3b  mov     rbx, rcx
0x180008e3e  xor     r12d, r12d
0x180008e41  mov     [rbp+47h+var_90], r12
0x180008e45  mov     [rbp+47h+ThreadId], r12d
0x180008e49  mov     [rbp+47h+var_70], r12
0x180008e4d  test    rdx, rdx
0x180008e50  jz      loc_180009347
0x180008e56  test    r8, r8
0x180008e59  jz      loc_180009347
0x180008e5f  mov     [rcx+20h], rdx
0x180008e63  mov     rax, [rdx]
0x180008e66  mov     rcx, rdx
0x180008e69  mov     rax, [rax+8]
0x180008e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e72  mov     rax, [rbx+8]
0x180008e76  mov     [rax+10h], rsi
0x180008e7a  mov     rdi, [rbx+8]
0x180008e7e  xor     r8d, r8d; dwFlags
0x180008e81  xor     edx, edx; hFile
0x180008e83  lea     rcx, LibFileName; "COMRES.DLL"
0x180008e8a  call    cs:__imp_LoadLibraryExA
0x180008e90  mov     [rdi+188h], rax
0x180008e97  test    rax, rax
0x180008e9a  jnz     short loc_180008EA6
0x180008e9c  mov     eax, 80004005h
0x180008ea1  jmp     loc_18000934C
0x180008ea6  mov     rcx, [rbx+8]
0x180008eaa  mov     eax, [rbp+47h+arg_20]
0x180008ead  mov     [rcx+218h], eax
0x180008eb3  mov     rcx, rsi
0x180008eb6  call    cs:__imp_?ContactToNameObject@@YAPEAUINameObject@@PEAUIProperties@@@Z; ContactToNameObject(IProperties *)
0x180008ebc  mov     r14, rax
0x180008ebf  test    rax, rax
0x180008ec2  jz      short loc_180008F22
0x180008ec4  mov     rax, [rax]
0x180008ec7  mov     rdx, r15
0x180008eca  mov     rcx, r14
0x180008ecd  mov     rax, [rax+68h]
0x180008ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ed6  mov     edi, eax
0x180008ed8  test    eax, eax
0x180008eda  jns     short loc_180008EF2
0x180008edc  mov     rcx, [r14]
0x180008edf  mov     rax, [rcx+10h]
0x180008ee3  mov     rcx, r14
0x180008ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eeb  mov     eax, edi
0x180008eed  jmp     loc_18000934C
0x180008ef2  mov     rax, [rsi]
0x180008ef5  mov     r8, [rbx+8]
0x180008ef9  add     r8, 18h
0x180008efd  lea     rdx, IID_ICustomProperties
0x180008f04  mov     rcx, rsi
0x180008f07  mov     rax, [rax]
0x180008f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f0f  test    eax, eax
0x180008f11  jns     short loc_180008F2C
0x180008f13  mov     rax, [r14]
0x180008f16  mov     rcx, r14
0x180008f19  mov     rax, [rax+10h]
0x180008f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f22  mov     eax, 8007000Eh
0x180008f27  jmp     loc_18000934C
0x180008f2c  lea     r8, [rbp+47h+var_90]
0x180008f30  lea     rdx, IID_IConnectionManager
0x180008f37  lea     rcx, CLSID_DTCCM
0x180008f3e  call    cs:__imp_DllGetDTCConnectionManager
0x180008f44  mov     edi, eax
0x180008f46  test    eax, eax
0x180008f48  jnz     short loc_180008EDC
0x180008f4a  mov     rcx, [rbp+47h+var_90]
0x180008f4e  mov     [rbx+18h], rcx
0x180008f52  mov     rax, [rcx]
0x180008f55  lea     r8, [rbp+47h+var_90]
0x180008f59  lea     rdx, IID_IConnectionManagerConfig
0x180008f60  mov     rax, [rax]
0x180008f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f68  mov     edi, eax
0x180008f6a  test    eax, eax
0x180008f6c  jnz     loc_180008EDC
0x180008f72  mov     rdi, [rbp+47h+var_90]
0x180008f76  mov     rax, [rdi]
0x180008f79  mov     edx, 1
0x180008f7e  mov     rcx, rdi
0x180008f81  mov     rax, [rax+28h]
0x180008f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f8a  mov     rax, [rdi]
0x180008f8d  mov     edx, 1
0x180008f92  mov     rcx, rdi
0x180008f95  mov     rax, [rax+48h]
0x180008f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f9e  mov     [rbp+47h+pdwClusterState], r12d
0x180008fa2  lea     rdx, [rbp+47h+pdwClusterState]; pdwClusterState
0x180008fa6  xor     ecx, ecx; lpszNodeName
0x180008fa8  call    cs:__imp_GetNodeClusterState
0x180008fae  mov     r15d, eax
0x180008fb1  test    eax, eax
0x180008fb3  jz      loc_180009068
0x180008fb9  jle     short loc_180008FC6
0x180008fbb  movzx   r15d, ax
0x180008fbf  or      r15d, 80070000h
0x180008fc6  lea     rax, aGetnodecluster; "GetNodeClusterState failed"
0x180008fcd  mov     [rsp+0E0h+var_B0], rax
0x180008fd2  mov     dword ptr [rsp+0E0h+lpThreadId], r15d
0x180008fd7  lea     rax, aMtxcluiscluste; "MtxCluIsClusterPresentNonAdmin"
0x180008fde  mov     qword ptr [rsp+0E0h+dwCreationFlags], rax
0x180008fe3  mov     r9d, 65h ; 'e'
0x180008fe9  lea     r8, aComComplusDtcS_4; "com\\complus\\dtc\\shared\\util\\cluste"...
0x180008ff0  mov     edx, 1
0x180008ff5  mov     ecx, 7
0x180008ffa  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180008fff  mov     [rbp+47h+var_58], r12w
0x180009004  xorps   xmm0, xmm0
0x180009007  movups  xmmword ptr [rbp+47h+var_56], xmm0
0x18000900b  movups  xmmword ptr [rbp+47h+var_56+0Ch], xmm0
0x18000900f  mov     r9d, r15d
0x180009012  lea     r8, a0x08x; "0x%08X"
0x180009019  mov     edx, 0Fh; unsigned __int64
0x18000901e  lea     rcx, [rbp+47h+var_58]; unsigned __int16 *
0x180009022  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009027  mov     [rbp+47h+var_68], r12
0x18000902b  lea     rax, [rbp+47h+var_58]
0x18000902f  mov     [rbp+47h+var_60], rax
0x180009033  mov     edx, 0Eh; unsigned __int16
0x180009038  mov     ecx, 1; unsigned __int16
0x18000903d  mov     [rsp+0E0h+var_A0], ecx; int
0x180009041  mov     [rsp+0E0h+Src], r12; Src
0x180009046  lea     rax, [rbp+47h+var_68]
0x18000904a  mov     [rsp+0E0h+var_B0], rax; unsigned __int16 **
0x18000904f  mov     dword ptr [rsp+0E0h+lpThreadId], r12d; Size
0x180009054  mov     word ptr [rsp+0E0h+dwCreationFlags], 2; unsigned __int16
0x18000905b  mov     r8d, 40001008h; unsigned int
0x180009061  call    ?DtcWriteToEventLoggerExW@@YAJGGKPEAXGKPEAPEBG0H@Z; DtcWriteToEventLoggerExW(ushort,ushort,ulong,void *,ushort,ulong,ushort const * *,void *,int)
0x180009066  jmp     short loc_18000906E
0x180009068  cmp     [rbp+47h+pdwClusterState], 1
0x18000906c  ja      short loc_180009090
0x18000906e  cmp     [rbp+47h+arg_28], r12d
0x180009072  jnz     short loc_180009090
0x180009074  mov     rax, [rdi]
0x180009077  mov     edx, 20h ; ' '
0x18000907c  mov     rcx, rdi
0x18000907f  mov     rax, [rax+78h]
0x180009083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009088  test    eax, eax
0x18000908a  jnz     loc_18000934C
0x180009090  mov     [rbp+47h+var_88], r12
0x180009094  mov     rax, [rsi]
0x180009097  lea     rdx, [rbp+47h+var_88]
0x18000909b  mov     rcx, rsi
0x18000909e  mov     rax, [rax+0B0h]
0x1800090a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090aa  test    eax, eax
0x1800090ac  js      loc_180008F13
0x1800090b2  mov     ecx, 48h ; 'H'; Size
0x1800090b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800090bc  mov     qword ptr [rbp+47h+pdwClusterState], rax
0x1800090c0  test    rax, rax
0x1800090c3  jz      short loc_1800090DA
0x1800090c5  mov     r8, [rbp+47h+var_88]; struct ITmInstance *
0x1800090c9  mov     rdx, [rbx+8]; struct CUISCore *
0x1800090cd  mov     rcx, rax; this
0x1800090d0  call    ??0CUisImpIConnectionNotify@@QEAA@PEAVCUISCore@@PEAUITmInstance@@@Z; CUisImpIConnectionNotify::CUisImpIConnectionNotify(CUISCore *,ITmInstance *)
0x1800090d5  mov     rsi, rax
0x1800090d8  jmp     short loc_1800090DD
0x1800090da  mov     rsi, r12
0x1800090dd  mov     rcx, [rbp+47h+var_88]
0x1800090e1  mov     rax, [rcx]
0x1800090e4  mov     rax, [rax+10h]
0x1800090e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090ed  test    rsi, rsi
0x1800090f0  jz      loc_180008F13
0x1800090f6  mov     rax, [rsi]
0x1800090f9  mov     rcx, rsi
0x1800090fc  mov     rax, [rax+8]
0x180009100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009105  mov     rcx, [rbx+18h]
0x180009109  mov     rax, [rcx]
0x18000910c  xor     r9d, r9d
0x18000910f  mov     r8, rsi
0x180009112  mov     rdx, r14
0x180009115  mov     rax, [rax+18h]
0x180009119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000911e  mov     r15d, eax
0x180009121  test    eax, eax
0x180009123  jz      short loc_18000913C
0x180009125  mov     rcx, [r14]
0x180009128  mov     rax, [rcx+10h]
0x18000912c  mov     rcx, r14
0x18000912f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009134  mov     eax, r15d
0x180009137  jmp     loc_18000934C
0x18000913c  mov     rax, [rsi]
0x18000913f  mov     rcx, rsi
0x180009142  mov     rax, [rax+10h]
0x180009146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000914b  mov     rcx, [rbx+18h]
0x18000914f  mov     rax, [rcx]
0x180009152  mov     rax, [rax+20h]
0x180009156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000915b  mov     esi, eax
0x18000915d  test    eax, eax
0x18000915f  jz      short loc_180009177
0x180009161  mov     rcx, [r14]
0x180009164  mov     rax, [rcx+10h]
0x180009168  mov     rcx, r14
0x18000916b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009170  mov     eax, esi
0x180009172  jmp     loc_18000934C
0x180009177  mov     rax, [rdi]
0x18000917a  mov     rcx, rdi
0x18000917d  mov     rax, [rax+18h]
0x180009181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009186  mov     esi, eax
0x180009188  mov     rax, [rdi]
0x18000918b  mov     rcx, rdi
0x18000918e  mov     rax, [rax+10h]
0x180009192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009197  mov     rax, [r14]
0x18000919a  mov     rax, [rax+10h]
0x18000919e  mov     rcx, r14
0x1800091a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091a6  test    esi, esi
0x1800091a8  jnz     short loc_180009170
0x1800091aa  mov     r9, [rbx+8]
0x1800091ae  mov     rcx, [r9+18h]
0x1800091b2  mov     rax, [rcx]
0x1800091b5  add     r9, 0Ch
0x1800091b9  lea     r8, aTracelimit; "TraceLimit"
0x1800091c0  lea     rdx, aDac; "DAC"
0x1800091c7  mov     rax, [rax+38h]
0x1800091cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091d0  mov     rax, [rbx+8]
0x1800091d4  mov     rcx, [rax+18h]
0x1800091d8  mov     rax, [rcx]
0x1800091db  lea     r9, ?z_dwShowLimit@@3KA; ulong z_dwShowLimit
0x1800091e2  lea     r8, aShowlimit; "ShowLimit"
0x1800091e9  lea     rdx, aDac; "DAC"
0x1800091f0  mov     rax, [rax+38h]
0x1800091f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f9  mov     rax, [rbx+8]
0x1800091fd  mov     rcx, [rax+18h]
0x180009201  mov     rax, [rcx]
0x180009204  lea     r9, ?z_dwUpdateLimit@@3KA; ulong z_dwUpdateLimit
0x18000920b  lea     r8, aUpdatelimit; "UpdateLimit"
0x180009212  lea     rdx, aDac; "DAC"
0x180009219  mov     rax, [rax+38h]
0x18000921d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009222  xor     r9d, r9d; lpName
0x180009225  xor     r8d, r8d; bInitialState
0x180009228  xor     edx, edx; bManualReset
0x18000922a  xor     ecx, ecx; lpEventAttributes
0x18000922c  call    cs:__imp_CreateEventA
0x180009232  mov     rcx, [rbx+8]
0x180009236  mov     [rcx+208h], rax
0x18000923d  mov     rax, [rbx+8]
0x180009241  mov     edi, 8007000Eh
0x180009246  cmp     qword ptr [rax+208h], 0
0x18000924e  cmovz   esi, edi
0x180009251  xor     r9d, r9d; lpName
0x180009254  xor     r8d, r8d; bInitialState
0x180009257  mov     edx, 1; bManualReset
0x18000925c  xor     ecx, ecx; lpEventAttributes
0x18000925e  call    cs:__imp_CreateEventA
0x180009264  mov     rcx, [rbx+8]
0x180009268  mov     [rcx+220h], rax
0x18000926f  mov     rax, [rbx+8]
0x180009273  cmp     qword ptr [rax+220h], 0
0x18000927b  cmovz   esi, edi
0x18000927e  mov     dword ptr [rax+210h], 1
0x180009288  test    esi, esi
0x18000928a  jnz     loc_180009343
0x180009290  mov     r9, [rbx+8]; lpParameter
0x180009294  cmp     qword ptr [r9+90h], 0
0x18000929c  jnz     loc_180009343
0x1800092a2  lea     rax, [rbp+47h+ThreadId]
0x1800092a6  mov     [rsp+0E0h+lpThreadId], rax; lpThreadId
0x1800092ab  mov     [rsp+0E0h+dwCreationFlags], r12d; dwCreationFlags
0x1800092b0  lea     r8, ?UIServerThread@@YAKPEAK@Z; lpStartAddress
0x1800092b7  xor     edx, edx; dwStackSize
0x1800092b9  xor     ecx, ecx; lpThreadAttributes
0x1800092bb  call    cs:__imp_CreateThread
0x1800092c1  mov     rcx, [rbx+8]
0x1800092c5  mov     [rcx+90h], rax
0x1800092cc  mov     rcx, [rbx+8]
0x1800092d0  cmp     qword ptr [rcx+90h], 0
0x1800092d8  jnz     short loc_180009343
  ... truncated ...
```

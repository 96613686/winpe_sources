# WindowsPerformanceRecorder::CControlManager::ConfigSnapshotByPIDEx(__MIDL_ISnapshotManager_0001,ulong *,long *,ulong,short)

- ea: `0x180062240`
- end: `0x180062479`
- name: `?ConfigSnapshotByPIDEx@CControlManager@WindowsPerformanceRecorder@@UEAAJW4__MIDL_ISnapshotManager_0001@@PEAKPEAJKF@Z`
- size: `569`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18001e6e0`
- `0x180037634`
- `0x18004a170`
- `0x18004b494`
- `0x180062240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062310`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062310`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800622fe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800622fe`
- `ntdll!RtlQueryHeapInformation` at `0x18006235f`
- `ntdll!RtlQueryHeapInformation` at `0x18006235f`
- `ntdll!RtlSetHeapInformation` at `0x1800623ba`
- `ntdll!RtlSetHeapInformation` at `0x1800623ba`

## string_xrefs

- `0x180062288`: `COMGUARD`
- `0x18006229c`: `ConfigSnapshotByPIDEx`
- `0x18006237e`: `ConfigSnapshotByPIDEx`
- `0x180062448`: `ConfigSnapshotByPIDEx`
- `0x180062433`: `HeapStackDatabase already enabled`
- `0x18006246a`: `HeapStackDatabase already disabled`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::ConfigSnapshotByPIDEx(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int16 a6)
{
  unsigned int v7; // ebx
  int v8; // r14d
  int v9; // esi
  __int16 v10; // r15
  unsigned int v11; // edi
  DWORD v12; // r8d
  HANDLE v13; // rbx
  int LastError; // eax
  NTSTATUS v15; // eax
  char *v17; // rax
  __int64 v18; // r8
  const char *v19; // [rsp+30h] [rbp-41h]
  HANDLE v20; // [rsp+38h] [rbp-39h] BYREF
  __int128 v21; // [rsp+40h] [rbp-31h] BYREF
  _BYTE v22[8]; // [rsp+50h] [rbp-21h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-19h]
  __int128 HeapInformation; // [rsp+68h] [rbp-9h] BYREF
  __int128 v25; // [rsp+78h] [rbp+7h]
  __int64 v26; // [rsp+88h] [rbp+17h]

  WindowsPerformanceRecorder::Impl::CAutoPrivilege::CAutoPrivilege(
    (WindowsPerformanceRecorder::Impl::CAutoPrivilege *)v22,
    20,
    1u);
  v7 = v23;
  if ( v23 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"ConfigSnapshotByPIDEx",
      (const char *)0x7D,
      v23,
      "COMGUARD",
      v19);
    goto LABEL_19;
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( a2 == 1 )
    v10 = a6 != 0;
  v11 = 0;
  if ( !a5 )
  {
LABEL_17:
    v8 = -984068078;
    goto LABEL_18;
  }
  do
  {
    v26 = 0;
    HeapInformation = 0;
    v25 = 0;
    v12 = *(_DWORD *)(a3 + 4LL * v11);
    v21 = 0;
    v20 = OpenProcess(0x10067Au, 0, v12);
    v13 = v20;
    if ( !v20 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_9:
      v8 = 1;
      goto LABEL_15;
    }
    v26 = 1;
    *(_QWORD *)&HeapInformation = 2;
    *((_QWORD *)&HeapInformation + 1) = v20;
    v25 = 0;
    v15 = RtlQueryHeapInformation(0, (HEAP_INFORMATION_CLASS)5, &HeapInformation, 0x28u, 0);
    if ( v15 >= 0 )
    {
      if ( a6 )
      {
        if ( BYTE1(v26) != 1 )
          goto LABEL_12;
        v17 = "HeapStackDatabase already enabled";
        v18 = 178;
      }
      else
      {
        if ( BYTE1(v26) == 1 )
          goto LABEL_12;
        v17 = "HeapStackDatabase already disabled";
        v18 = 186;
      }
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)4,
        (unsigned __int8)"ConfigSnapshotByPIDEx",
        (const char *)v18,
        0,
        v17,
        v19);
      ++v9;
      goto LABEL_14;
    }
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)3,
      (unsigned __int8)"ConfigSnapshotByPIDEx",
      (const char *)0xAC,
      v15,
      "HeapStackDatabase Query Error",
      v19);
LABEL_12:
    DWORD1(v21) = 0;
    LOWORD(v21) = 1;
    *((_QWORD *)&v21 + 1) = v13;
    WORD1(v21) = v10;
    LastError = RtlSetHeapInformation(0, (HEAP_INFORMATION_CLASS)5, &v21, 0x10u);
    if ( LastError < 0 )
      goto LABEL_9;
    ++v9;
LABEL_14:
    LastError = 0;
LABEL_15:
    *(_DWORD *)(a4 + 4LL * v11) = LastError;
    ATL::CHandle::~CHandle((ATL::CHandle *)&v20);
    ++v11;
  }
  while ( v11 < a5 );
  if ( !v9 )
    goto LABEL_17;
LABEL_18:
  v7 = v8;
LABEL_19:
  WindowsPerformanceRecorder::Impl::CAutoPrivilege::~CAutoPrivilege((WindowsPerformanceRecorder::Impl::CAutoPrivilege *)v22);
  return v7;
}

```

## disassembly

```asm
0x180062240  mov     rax, rsp
0x180062243  mov     [rax+8], rbx
0x180062247  mov     [rax+10h], rsi
0x18006224b  mov     [rax+20h], r9
0x18006224f  mov     [rax+18h], r8
0x180062253  push    rbp
0x180062254  push    rdi
0x180062255  push    r12
0x180062257  push    r14
0x180062259  push    r15
0x18006225b  lea     rbp, [rax-4Fh]
0x18006225f  sub     rsp, 90h
0x180062266  mov     r12d, 1
0x18006226c  lea     rcx, [rbp+47h+var_68]; this
0x180062270  mov     edi, edx
0x180062272  mov     r8b, r12b; unsigned __int8
0x180062275  lea     edx, [r12+13h]; unsigned int
0x18006227a  call    ??0CAutoPrivilege@Impl@WindowsPerformanceRecorder@@QEAA@KE@Z; WindowsPerformanceRecorder::Impl::CAutoPrivilege::CAutoPrivilege(ulong,uchar)
0x18006227f  mov     ebx, [rbp+47h+var_60]
0x180062282  xor     ecx, ecx
0x180062284  test    ebx, ebx
0x180062286  jz      short loc_1800622B2
0x180062288  lea     rax, aComguard; "COMGUARD"
0x18006228f  mov     r9d, ebx; unsigned int
0x180062292  lea     r8d, [r12+7Ch]; char *
0x180062297  mov     [rsp+0B0h+ReturnLength], rax; Format
0x18006229c  lea     rdx, aConfigsnapshot_0; "ConfigSnapshotByPIDEx"
0x1800622a3  lea     ecx, [r12+1]; this
0x1800622a8  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800622ad  jmp     loc_1800623F8
0x1800622b2  mov     r14d, ecx
0x1800622b5  mov     esi, ecx
0x1800622b7  mov     r15d, ecx
0x1800622ba  cmp     edi, r12d
0x1800622bd  jnz     short loc_1800622C9
0x1800622bf  cmp     [rbp+47h+arg_28], cx
0x1800622c3  jz      short loc_1800622C9
0x1800622c5  movzx   r15d, r12w
0x1800622c9  mov     r12d, [rbp+47h+arg_20]
0x1800622cd  mov     edi, ecx
0x1800622cf  test    r12d, r12d
0x1800622d2  jz      loc_1800623EF
0x1800622d8  mov     rcx, [rbp+47h+arg_10]
0x1800622dc  xorps   xmm0, xmm0
0x1800622df  xor     eax, eax
0x1800622e1  xor     edx, edx; bInheritHandle
0x1800622e3  mov     [rbp+47h+var_30], rax
0x1800622e7  mov     eax, edi
0x1800622e9  movups  [rbp+47h+HeapInformation], xmm0
0x1800622ed  movups  [rbp+47h+var_40], xmm0
0x1800622f1  mov     r8d, [rcx+rax*4]; dwProcessId
0x1800622f5  mov     ecx, 10067Ah; dwDesiredAccess
0x1800622fa  movups  [rbp+47h+var_78], xmm0
0x1800622fe  call    cs:__imp_OpenProcess
0x180062304  mov     [rbp+47h+var_80], rax
0x180062308  mov     rbx, rax
0x18006230b  test    rax, rax
0x18006230e  jnz     short loc_18006232D
0x180062310  call    cs:__imp_GetLastError
0x180062316  test    eax, eax
0x180062318  jle     short loc_180062322
0x18006231a  movzx   eax, ax
0x18006231d  or      eax, 80070000h
0x180062322  mov     r14d, 1
0x180062328  jmp     loc_1800623CE
0x18006232d  xor     eax, eax
0x18006232f  lea     r8, [rbp+47h+HeapInformation]; HeapInformation
0x180062333  xorps   xmm0, xmm0
0x180062336  mov     [rbp+47h+var_30], rax
0x18006233a  movups  [rbp+47h+HeapInformation], xmm0
0x18006233e  xor     ecx, ecx; HeapHandle
0x180062340  mov     dword ptr [rbp+47h+HeapInformation], 2
0x180062347  lea     r9d, [rax+28h]; HeapInformationLength
0x18006234b  mov     qword ptr [rbp+47h+HeapInformation+8], rbx
0x18006234f  lea     edx, [rax+5]; HeapInformationClass
0x180062352  mov     byte ptr [rbp+47h+var_30], 1
0x180062356  movups  [rbp+47h+var_40], xmm0
0x18006235a  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x18006235f  call    cs:__imp_RtlQueryHeapInformation
0x180062365  xor     ecx, ecx
0x180062367  test    eax, eax
0x180062369  jns     loc_18006241F
0x18006236f  lea     rcx, aHeapstackdatab; "HeapStackDatabase Query Error"
0x180062376  mov     r9d, eax; unsigned int
0x180062379  mov     [rsp+0B0h+ReturnLength], rcx; Format
0x18006237e  lea     rdx, aConfigsnapshot_0; "ConfigSnapshotByPIDEx"
0x180062385  mov     ecx, 3; this
0x18006238a  mov     r8d, 0ACh; char *
0x180062390  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180062395  xor     ecx, ecx
0x180062397  lea     edx, [rcx+1]
0x18006239a  mov     r9d, 10h; HeapInformationLength
0x1800623a0  mov     dword ptr [rbp+47h+var_78+4], ecx
0x1800623a3  mov     word ptr [rbp+47h+var_78], dx
0x1800623a7  lea     r8, [rbp+47h+var_78]; HeapInformation
0x1800623ab  xor     ecx, ecx; HeapHandle
0x1800623ad  mov     qword ptr [rbp+47h+var_78+8], rbx
0x1800623b1  mov     word ptr [rbp+47h+var_78+2], r15w
0x1800623b6  lea     edx, [r9-0Bh]; HeapInformationClass
0x1800623ba  call    cs:__imp_RtlSetHeapInformation
0x1800623c0  xor     ebx, ebx
0x1800623c2  test    eax, eax
0x1800623c4  js      loc_180062322
0x1800623ca  inc     esi
0x1800623cc  mov     eax, ebx
0x1800623ce  mov     rdx, [rbp+47h+arg_18]
0x1800623d2  mov     ecx, edi
0x1800623d4  mov     [rdx+rcx*4], eax
0x1800623d7  lea     rcx, [rbp+47h+var_80]; this
0x1800623db  call    ??1CHandle@ATL@@QEAA@XZ; ATL::CHandle::~CHandle(void)
0x1800623e0  inc     edi
0x1800623e2  cmp     edi, r12d
0x1800623e5  jb      loc_1800622D8
0x1800623eb  test    esi, esi
0x1800623ed  jnz     short loc_1800623F5
0x1800623ef  mov     r14d, 0C5585012h
0x1800623f5  mov     ebx, r14d
0x1800623f8  lea     rcx, [rbp+47h+var_68]; this
0x1800623fc  call    ??1CAutoPrivilege@Impl@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::Impl::CAutoPrivilege::~CAutoPrivilege(void)
0x180062401  lea     r11, [rsp+0B0h+var_20]
0x180062409  mov     eax, ebx
0x18006240b  mov     rbx, [r11+30h]
0x18006240f  mov     rsi, [r11+38h]
0x180062413  mov     rsp, r11
0x180062416  pop     r15
0x180062418  pop     r14
0x18006241a  pop     r12
0x18006241c  pop     rdi
0x18006241d  pop     rbp
0x18006241e  retn
0x18006241f  mov     edx, 1
0x180062424  cmp     [rbp+47h+arg_28], cx
0x180062428  jz      short loc_180062461
0x18006242a  cmp     byte ptr [rbp+47h+var_30+1], dl
0x18006242d  jnz     loc_18006239A
0x180062433  lea     rax, aHeapstackdatab_0; "HeapStackDatabase already enabled"
0x18006243a  mov     r8d, 0B2h; char *
0x180062440  xor     r9d, r9d; unsigned int
0x180062443  mov     [rsp+0B0h+ReturnLength], rax; Format
0x180062448  lea     rdx, aConfigsnapshot_0; "ConfigSnapshotByPIDEx"
0x18006244f  lea     ecx, [r9+4]; this
0x180062453  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180062458  inc     esi
0x18006245a  xor     ebx, ebx
0x18006245c  jmp     loc_1800623CC
0x180062461  cmp     byte ptr [rbp+47h+var_30+1], dl
0x180062464  jz      loc_18006239A
0x18006246a  lea     rax, aHeapstackdatab_1; "HeapStackDatabase already disabled"
0x180062471  mov     r8d, 0BAh
0x180062477  jmp     short loc_180062440
```

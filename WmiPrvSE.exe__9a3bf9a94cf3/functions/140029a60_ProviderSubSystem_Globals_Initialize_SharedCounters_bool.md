# ProviderSubSystem_Globals::Initialize_SharedCounters(bool)

- ea: `0x140029a60`
- end: `0x140029c40`
- name: `?Initialize_SharedCounters@ProviderSubSystem_Globals@@SAJ_N@Z`
- size: `480`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14002d070`

## callees

- `0x14000a0f0`
- `0x1400234b8`
- `0x140029a60`
- `0x14002f430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029a9b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029b49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140029b49`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140029bd2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x140029bd2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x140029bbc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfSetCounterSetInfo` at `0x140029bbc`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProviderEx` at `0x140029b9e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStartProviderEx` at `0x140029b9e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140029b33`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x140029b33`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140029b00`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140029b00`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140029a83`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x140029a83`
- `wbemcomn!GetMemLogObject` at `0x140029be7`
- `wbemcomn!GetMemLogObject` at `0x140029be7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140029bf2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140029bf2`

## pseudocode

```c
__int64 __fastcall ProviderSubSystem_Globals::Initialize_SharedCounters()
{
  int SecurityDescriptor; // ebx
  HANDLE FileMappingW; // rdi
  const void *v2; // rax
  CMemoryLog *MemLogObject; // rax
  struct _PROVIDER_CONTEXT FileMappingAttributes; // [rsp+30h] [rbp-50h] BYREF
  _SECURITY_DESCRIPTOR v6; // [rsp+58h] [rbp-28h] BYREF

  SecurityDescriptor = 0;
  FileMappingW = OpenFileMappingW(6u, 0, L"Global\\Wmi Provider Sub System Counters");
  if ( FileMappingW )
    goto LABEL_7;
  if ( GetLastError() != 2 )
  {
    SecurityDescriptor = -2147217405;
    goto LABEL_13;
  }
  memset(&v6, 0, sizeof(v6));
  SecurityDescriptor = GetSecurityDescriptor(&v6);
  if ( SecurityDescriptor < 0 )
    goto LABEL_13;
  FileMappingAttributes.ControlCallback = (PERFLIBREQUEST)&v6;
  *(_QWORD *)&FileMappingAttributes.ContextSize = 24;
  FileMappingAttributes.MemAllocRoutine = 0;
  FileMappingW = CreateFileMappingW(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   (LPSECURITY_ATTRIBUTES)&FileMappingAttributes,
                   0x8000004u,
                   0,
                   0x148u,
                   L"Global\\Wmi Provider Sub System Counters");
  if ( !FileMappingW )
    SecurityDescriptor = -2147217405;
  operator delete(v6.Dacl);
  if ( SecurityDescriptor >= 0 )
  {
LABEL_7:
    v2 = MapViewOfFile(FileMappingW, 6u, 0, 0, 0x148u);
    if ( v2 )
    {
      ProviderSubSystem_Globals::s_FileMapping = FileMappingW;
      ProviderSubSystem_Globals::s_SharedCounters = v2;
      goto LABEL_13;
    }
    SecurityDescriptor = -2147217405;
  }
  if ( FileMappingW )
    CloseHandle(FileMappingW);
LABEL_13:
  *(_QWORD *)&FileMappingAttributes.ContextSize = 40;
  memset(&FileMappingAttributes.ControlCallback, 0, 32);
  if ( PerfStartProviderEx(&WmiprvSePerfCounterGuid, &FileMappingAttributes, &WmiprvSePerfCounter) )
  {
LABEL_17:
    WmiprvSePerfCounter = 0;
    goto LABEL_18;
  }
  if ( PerfSetCounterSetInfo(WmiprvSePerfCounter, &WMI_PROVIDERHOST_HEALTHInfo, 0xE8u) && WmiprvSePerfCounter )
  {
    PerfStopProvider(WmiprvSePerfCounter);
    goto LABEL_17;
  }
LABEL_18:
  if ( SecurityDescriptor < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, SecurityDescriptor);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_3058338b7eb536807a3546f9e85809ac_Traceguids,
      (unsigned int)SecurityDescriptor);
  }
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x140029a60  push    rbp
0x140029a62  push    rbx
0x140029a63  push    rdi
0x140029a64  push    r12
0x140029a66  push    r14
0x140029a68  mov     rbp, rsp
0x140029a6b  sub     rsp, 80h
0x140029a72  xor     ebx, ebx
0x140029a74  lea     r12, Name; "Global\\Wmi Provider Sub System Counter"...
0x140029a7b  mov     r8, r12; lpName
0x140029a7e  xor     edx, edx; bInheritHandle
0x140029a80  lea     ecx, [rbx+6]; dwDesiredAccess
0x140029a83  call    cs:__imp_OpenFileMappingW
0x140029a89  mov     rdi, rax
0x140029a8c  mov     r14d, 80041003h
0x140029a92  test    rax, rax
0x140029a95  jnz     loc_140029B1D
0x140029a9b  call    cs:__imp_GetLastError
0x140029aa1  cmp     eax, 2
0x140029aa4  jnz     loc_140029B51
0x140029aaa  xorps   xmm0, xmm0
0x140029aad  lea     rcx, [rbp+var_28]; struct _SECURITY_DESCRIPTOR *
0x140029ab1  xor     eax, eax
0x140029ab3  movups  xmmword ptr [rbp+var_28.Revision], xmm0
0x140029ab7  mov     [rbp+var_28.Dacl], rax
0x140029abb  movups  xmmword ptr [rbp+var_28.Group], xmm0
0x140029abf  call    ?GetSecurityDescriptor@@YAJAEAU_SECURITY_DESCRIPTOR@@K@Z; GetSecurityDescriptor(_SECURITY_DESCRIPTOR &,ulong)
0x140029ac4  mov     ebx, eax
0x140029ac6  test    eax, eax
0x140029ac8  js      loc_140029B64
0x140029ace  lea     rax, [rbp+var_28]
0x140029ad2  mov     [rsp+80h+lpName], r12; lpName
0x140029ad7  xor     r9d, r9d; dwMaximumSizeHigh
0x140029ada  mov     [rbp+FileMappingAttributes.lpSecurityDescriptor], rax
0x140029ade  mov     r8d, 8000004h; flProtect
0x140029ae4  mov     qword ptr [rbp+FileMappingAttributes.nLength], 18h
0x140029aec  lea     rdx, [rbp+FileMappingAttributes]; lpFileMappingAttributes
0x140029af0  mov     qword ptr [rbp+FileMappingAttributes.bInheritHandle], rdi
0x140029af4  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x140029af8  mov     [rsp+80h+dwMaximumSizeLow], 148h; dwMaximumSizeLow
0x140029b00  call    cs:__imp_CreateFileMappingW
0x140029b06  mov     rcx, [rbp+var_28.Dacl]; lpMem
0x140029b0a  test    rax, rax
0x140029b0d  mov     rdi, rax
0x140029b10  cmovz   ebx, r14d
0x140029b14  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140029b19  test    ebx, ebx
0x140029b1b  js      short loc_140029B41
0x140029b1d  xor     r9d, r9d; dwFileOffsetLow
0x140029b20  mov     qword ptr [rsp+80h+dwMaximumSizeLow], 148h; dwNumberOfBytesToMap
0x140029b29  xor     r8d, r8d; dwFileOffsetHigh
0x140029b2c  mov     rcx, rdi; hFileMappingObject
0x140029b2f  lea     edx, [r9+6]; dwDesiredAccess
0x140029b33  call    cs:__imp_MapViewOfFile
0x140029b39  test    rax, rax
0x140029b3c  jnz     short loc_140029B56
0x140029b3e  mov     ebx, r14d
0x140029b41  test    rdi, rdi
0x140029b44  jz      short loc_140029B64
0x140029b46  mov     rcx, rdi; hObject
0x140029b49  call    cs:__imp_CloseHandle
0x140029b4f  jmp     short loc_140029B64
0x140029b51  mov     ebx, r14d
0x140029b54  jmp     short loc_140029B64
0x140029b56  mov     cs:?s_FileMapping@ProviderSubSystem_Globals@@2PEAXEA, rdi; void * ProviderSubSystem_Globals::s_FileMapping
0x140029b5d  mov     cs:?s_SharedCounters@ProviderSubSystem_Globals@@2PEAVCServerObject_ProviderSubsystem_Counters@@EA, rax; CServerObject_ProviderSubsystem_Counters * ProviderSubSystem_Globals::s_SharedCounters
0x140029b64  lea     r8, WmiprvSePerfCounter; Provider
0x140029b6b  mov     qword ptr [rbp+FileMappingAttributes.nLength], 28h ; '('
0x140029b73  lea     rdx, [rbp+FileMappingAttributes]; ProviderContext
0x140029b77  mov     [rbp+FileMappingAttributes.lpSecurityDescriptor], 0
0x140029b7f  lea     rcx, WmiprvSePerfCounterGuid; ProviderGuid
0x140029b86  mov     qword ptr [rbp+FileMappingAttributes.bInheritHandle], 0
0x140029b8e  mov     [rbp+var_38], 0
0x140029b96  mov     [rbp+var_30], 0
0x140029b9e  call    cs:__imp_PerfStartProviderEx
0x140029ba4  test    eax, eax
0x140029ba6  jnz     short loc_140029BD8
0x140029ba8  mov     rcx, cs:WmiprvSePerfCounter; ProviderHandle
0x140029baf  lea     rdx, WMI_PROVIDERHOST_HEALTHInfo; Template
0x140029bb6  mov     r8d, 0E8h; TemplateSize
0x140029bbc  call    cs:__imp_PerfSetCounterSetInfo
0x140029bc2  test    eax, eax
0x140029bc4  jz      short loc_140029BE3
0x140029bc6  mov     rcx, cs:WmiprvSePerfCounter; ProviderHandle
0x140029bcd  test    rcx, rcx
0x140029bd0  jz      short loc_140029BE3
0x140029bd2  call    cs:__imp_PerfStopProvider
0x140029bd8  mov     cs:WmiprvSePerfCounter, 0
0x140029be3  test    ebx, ebx
0x140029be5  jns     short loc_140029BF8
0x140029be7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140029bed  mov     rcx, rax
0x140029bf0  mov     edx, ebx
0x140029bf2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140029bf8  mov     rcx, cs:WPP_GLOBAL_Control
0x140029bff  lea     rax, WPP_GLOBAL_Control
0x140029c06  cmp     rcx, rax
0x140029c09  jz      short loc_140029C2F
0x140029c0b  test    byte ptr [rcx+1Ch], 4
0x140029c0f  jz      short loc_140029C2F
0x140029c11  cmp     byte ptr [rcx+19h], 2
0x140029c15  jb      short loc_140029C2F
0x140029c17  mov     rcx, [rcx+10h]
0x140029c1b  lea     r8, WPP_3058338b7eb536807a3546f9e85809ac_Traceguids
0x140029c22  mov     edx, 0Dh
0x140029c27  mov     r9d, ebx
0x140029c2a  call    WPP_SF_d
0x140029c2f  mov     eax, ebx
0x140029c31  add     rsp, 80h
0x140029c38  pop     r14
0x140029c3a  pop     r12
0x140029c3c  pop     rdi
0x140029c3d  pop     rbx
0x140029c3e  pop     rbp
0x140029c3f  retn
```

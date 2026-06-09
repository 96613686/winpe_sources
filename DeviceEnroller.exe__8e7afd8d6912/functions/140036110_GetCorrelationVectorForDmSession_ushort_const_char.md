# GetCorrelationVectorForDmSession(ushort const *,char *)

- ea: `0x140036110`
- end: `0x14003626f`
- name: `?GetCorrelationVectorForDmSession@@YAJPEBGPEAD@Z`
- size: `351`
- prototype: `int(const unsigned __int16 *, char *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400359e4`
- `0x140039f28`
- `0x14004c794`

## callees

- `0x1400042f0`
- `0x140004314`
- `0x1400045a8`
- `0x140034754`
- `0x1400353e4`
- `0x140035f78`
- `0x140036110`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x14003613b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14003613b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003616e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14003616e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003622f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140036262`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003622f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140036262`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400361a6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1400361a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetCorrelationVectorForDmSession(const unsigned __int16 *a1, char *a2)
{
  char IsStateSeparationEnabled; // al
  int ComponentCVForEnrollmentId; // eax
  bool v5; // cc
  const unsigned __int16 *v6; // rcx
  void *v7; // rax
  volatile signed __int64 *v8; // rbx
  HKEY hKey; // [rsp+30h] [rbp-78h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int16 Data[40]; // [rsp+40h] [rbp-68h] BYREF

  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(a1, a2);
  ComponentCVForEnrollmentId = RegOpenKeyExW(
                                 HKEY_LOCAL_MACHINE,
                                 *(wchar_t **)((char *)`DMGetKnownRegPath'::`2'::Paths
                                             + (IsStateSeparationEnabled != 0 ? 8 : 0)),
                                 0,
                                 0x20019u,
                                 &hKey);
  v5 = ComponentCVForEnrollmentId <= 0;
  if ( ComponentCVForEnrollmentId
    || (cbData[0] = 78,
        ComponentCVForEnrollmentId = RegQueryValueExW(hKey, L"CurrentEnrollmentId", 0, 0, (LPBYTE)Data, cbData),
        v5 = ComponentCVForEnrollmentId <= 0,
        ComponentCVForEnrollmentId) )
  {
    if ( !v5 )
      ComponentCVForEnrollmentId = (unsigned __int16)ComponentCVForEnrollmentId | 0x80070000;
  }
  else
  {
    ComponentCVForEnrollmentId = GetComponentCVForEnrollmentId(v6, Data, a2, hKey);
  }
  if ( ComponentCVForEnrollmentId >= 0 )
    goto LABEL_12;
  v7 = operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)cbData = v7;
  if ( v7 )
    v8 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((__int64)v7);
  else
    v8 = 0;
  if ( v8 )
  {
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v8,
      _InterlockedExchangeAdd64(v8 + 17, 0),
      a2);
    operator delete((void *)v8);
LABEL_12:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140036110  mov     [rsp+arg_0], rbx
0x140036115  push    rdi
0x140036116  sub     rsp, 0A0h
0x14003611d  mov     rax, cs:__security_cookie
0x140036124  xor     rax, rsp
0x140036127  mov     [rsp+0A8h+var_18], rax
0x14003612f  mov     rdi, rdx
0x140036132  mov     [rsp+0A8h+hKey], 0
0x14003613b  call    cs:__imp_RtlIsStateSeparationEnabled
0x140036141  neg     al
0x140036143  sbb     rdx, rdx
0x140036146  and     edx, 8
0x140036149  lea     rcx, ?Paths@?1??DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z@4QAY01QEBGA; ushort const * (near * `DMGetKnownRegPath(REFKNOWNREGID)'::`2'::Paths)[2]
0x140036150  lea     rax, [rsp+0A8h+hKey]
0x140036155  mov     [rsp+0A8h+phkResult], rax; phkResult
0x14003615a  mov     r9d, 20019h; samDesired
0x140036160  xor     r8d, r8d; ulOptions
0x140036163  mov     rdx, [rdx+rcx]; lpSubKey
0x140036167  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003616e  call    cs:__imp_RegOpenKeyExW
0x140036174  test    eax, eax
0x140036176  jnz     short loc_1400361C4
0x140036178  mov     [rsp+0A8h+cbData], 4Eh ; 'N'
0x140036180  lea     rax, [rsp+0A8h+cbData]
0x140036185  mov     [rsp+0A8h+lpcbData], rax; lpcbData
0x14003618a  lea     rax, [rsp+0A8h+Data]
0x14003618f  mov     [rsp+0A8h+phkResult], rax; lpData
0x140036194  xor     r9d, r9d; lpType
0x140036197  xor     r8d, r8d; lpReserved
0x14003619a  lea     rdx, c_szCurrentCorreleationEnrollmentIdValueName; "CurrentEnrollmentId"
0x1400361a1  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1400361a6  call    cs:__imp_RegQueryValueExW
0x1400361ac  test    eax, eax
0x1400361ae  jnz     short loc_1400361C4
0x1400361b0  mov     r9, [rsp+0A8h+hKey]; HKEY
0x1400361b5  mov     r8, rdi; char *
0x1400361b8  lea     rdx, [rsp+0A8h+Data]; unsigned __int16 *
0x1400361bd  call    ?GetComponentCVForEnrollmentId@@YAJPEBG0PEADPEAUHKEY__@@@Z; GetComponentCVForEnrollmentId(ushort const *,ushort const *,char *,HKEY__ *)
0x1400361c2  jmp     short loc_1400361CE
0x1400361c4  jle     short loc_1400361CE
0x1400361c6  movzx   eax, ax
0x1400361c9  or      eax, 80070000h
0x1400361ce  test    eax, eax
0x1400361d0  jns     short loc_140036225
0x1400361d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400361d9  mov     ecx, 90h; unsigned __int64
0x1400361de  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400361e3  mov     qword ptr [rsp+0A8h+cbData], rax
0x1400361e8  test    rax, rax
0x1400361eb  jz      short loc_1400361FA
0x1400361ed  mov     rcx, rax
0x1400361f0  call    ??0TraceLoggingCorrelationVector@@QEAA@UTraceLoggingCorrelationVectorV2_t@@@Z; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(TraceLoggingCorrelationVectorV2_t)
0x1400361f5  mov     rbx, rax
0x1400361f8  jmp     short loc_1400361FC
0x1400361fa  xor     ebx, ebx
0x1400361fc  test    rbx, rbx
0x1400361ff  jz      short loc_140036258
0x140036201  xor     edx, edx
0x140036203  lock xadd [rbx+88h], rdx; unsigned __int64
0x14003620c  mov     r8, rdi; char *
0x14003620f  mov     rcx, rbx; this
0x140036212  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x140036217  mov     edx, 90h
0x14003621c  mov     rcx, rbx; Block
0x14003621f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140036224  nop
0x140036225  mov     rcx, [rsp+0A8h+hKey]; hKey
0x14003622a  test    rcx, rcx
0x14003622d  jz      short loc_140036235
0x14003622f  call    cs:__imp_RegCloseKey
0x140036235  xor     eax, eax
0x140036237  mov     rcx, [rsp+0A8h+var_18]
0x14003623f  xor     rcx, rsp; StackCookie
0x140036242  call    __security_check_cookie
0x140036247  mov     rbx, [rsp+0A8h+arg_0]
0x14003624f  add     rsp, 0A0h
0x140036256  pop     rdi
0x140036257  retn
0x140036258  mov     rcx, [rsp+0A8h+hKey]; hKey
0x14003625d  test    rcx, rcx
0x140036260  jz      short loc_140036268
0x140036262  call    cs:__imp_RegCloseKey
0x140036268  mov     eax, 8007000Eh
0x14003626d  jmp     short loc_140036237
```

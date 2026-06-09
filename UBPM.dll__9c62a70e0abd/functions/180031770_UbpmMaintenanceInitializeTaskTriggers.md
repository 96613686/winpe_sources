# UbpmMaintenanceInitializeTaskTriggers

- ea: `0x180031770`
- end: `0x180031932`
- name: `UbpmMaintenanceInitializeTaskTriggers`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180030390`

## callees

- `0x18002b5bc`
- `0x180031770`
- `0x18004022e`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x18003185a`
- `ntdll!NtCreateWnfStateName` at `0x18003185a`
- `ntdll!RtlNtStatusToDosError` at `0x1800318bd`
- `ntdll!RtlNtStatusToDosError` at `0x1800318bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800317db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800317c8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800317c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800318d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800318d4`
- `CSystemEventsBrokerClient!CSebCreatePrivateEvent` at `0x18003188f`
- `CSystemEventsBrokerClient!CSebCreatePrivateEvent` at `0x18003188f`

## pseudocode

```c
__int64 UbpmMaintenanceInitializeTaskTriggers()
{
  int v0; // edi
  ULONG LastError; // eax
  int v2; // r8d
  int v3; // r9d
  unsigned int v4; // ebx
  struct _MAINTENANCE_TRIGGER near **v5; // rdi
  NTSTATUS WnfStateName; // eax
  int v7; // eax
  ULONG v8; // ebx
  int v9; // ecx
  __int128 v11; // [rsp+48h] [rbp-79h]
  __m256i v12; // [rsp+58h] [rbp-69h] BYREF
  __int128 v13; // [rsp+88h] [rbp-39h] BYREF
  __m256i v14; // [rsp+98h] [rbp-29h]
  __int64 v15; // [rsp+B8h] [rbp-9h]
  ULONG SecurityDescriptorSize; // [rsp+128h] [rbp+67h] BYREF
  int v17; // [rsp+130h] [rbp+6Fh] BYREF
  ULONG v18; // [rsp+138h] [rbp+77h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+140h] [rbp+7Fh] BYREF

  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  memset_0(&g_MaintenanceTriggers, 0, 0x50u);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GA;;;SY)",
         1u,
         &SecurityDescriptor,
         &SecurityDescriptorSize) )
  {
    v4 = 0;
    v12.m256i_i64[0] = 1;
    memset(&v12.m256i_u64[1], 0, 24);
    *((_QWORD *)&v11 + 1) = 4124;
    while ( 1 )
    {
      v5 = &g_MaintenanceTriggers + 2 * v4;
      WnfStateName = NtCreateWnfStateName(v5, 3, 0, 0, 0, 4096, SecurityDescriptor);
      if ( WnfStateName < 0 )
        break;
      *(_QWORD *)&v11 = *v5;
      v14 = v12;
      v13 = v11;
      v15 = 0;
      v7 = CSebCreatePrivateEvent(&v13, v5 + 1);
      if ( v7 < 0 )
      {
        v0 = 30;
        v8 = (unsigned __int16)v7;
        goto LABEL_11;
      }
      if ( ++v4 >= 5 )
      {
        v0 = 0;
        v8 = 0;
        goto LABEL_11;
      }
    }
    v0 = 20;
    LastError = RtlNtStatusToDosError(WnfStateName);
  }
  else
  {
    v0 = 10;
    LastError = GetLastError();
  }
  v8 = LastError;
LABEL_11:
  v9 = (int)SecurityDescriptor;
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( (unsigned int)dword_18004F0F0 > 4 )
  {
    v17 = v0;
    v18 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v9,
      (unsigned int)byte_180047421,
      v2,
      v3,
      (__int64)&v18,
      (__int64)&v17);
  }
  return v8;
}

```

## disassembly

```asm
0x180031770  mov     rax, rsp
0x180031773  push    rbp
0x180031774  push    rbx
0x180031775  push    rdi
0x180031776  push    r15
0x180031778  lea     rbp, [rax-5Fh]
0x18003177c  sub     rsp, 0F8h
0x180031783  movaps  xmmword ptr [rax-38h], xmm6
0x180031787  lea     r15, ?g_MaintenanceTriggers@@3PAU_MAINTENANCE_TRIGGER@@A; _MAINTENANCE_TRIGGER near * g_MaintenanceTriggers
0x18003178e  xor     edx, edx; Val
0x180031790  movaps  xmmword ptr [rax-48h], xmm7
0x180031794  mov     rcx, r15; void *
0x180031797  movaps  xmmword ptr [rax-58h], xmm8
0x18003179c  mov     [rbp+57h+SecurityDescriptor], 0
0x1800317a4  mov     [rbp+57h+SecurityDescriptorSize], 0
0x1800317ab  lea     r8d, [rdx+50h]; Size
0x1800317af  call    memset_0
0x1800317b4  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800317b8  mov     edx, 1; StringSDRevision
0x1800317bd  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800317c1  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x1800317c8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800317cf  nop     dword ptr [rax+rax+00h]
0x1800317d4  test    eax, eax
0x1800317d6  jnz     short loc_1800317EC
0x1800317d8  lea     edi, [rax+0Ah]
0x1800317db  call    cs:__imp_GetLastError
0x1800317e2  nop     dword ptr [rax+rax+00h]
0x1800317e7  jmp     loc_1800318C9
0x1800317ec  mov     [rbp+57h+var_A4], 0
0x1800317f4  xorps   xmm0, xmm0
0x1800317f7  movdqu  [rbp+57h+var_C0+0Ch], xmm0
0x1800317fc  mov     [rbp+57h+var_9C], 0
0x180031803  xor     ebx, ebx
0x180031805  movups  xmm7, xmmword ptr [rbp-59h]
0x180031809  mov     qword ptr [rbp+57h+var_C0], 1
0x180031811  movsd   xmm6, [rbp+57h+var_A4+4]
0x180031816  mov     dword ptr [rbp+57h+var_C0+8], 0
0x18003181d  movups  xmm8, [rbp+57h+var_C0]
0x180031822  mov     qword ptr [rbp+57h+var_D0+8], 101Ch
0x18003182a  mov     rax, [rbp+57h+SecurityDescriptor]
0x18003182e  xor     r9d, r9d
0x180031831  mov     [rsp+110h+var_E0], rax
0x180031836  xor     r8d, r8d
0x180031839  mov     edi, ebx
0x18003183b  shl     rdi, 4
0x18003183f  add     rdi, r15
0x180031842  mov     dword ptr [rsp+110h+var_E8], 1000h
0x18003184a  mov     rcx, rdi
0x18003184d  mov     [rsp+110h+var_F0], 0
0x180031856  lea     edx, [r9+3]
0x18003185a  call    cs:__imp_NtCreateWnfStateName
0x180031861  nop     dword ptr [rax+rax+00h]
0x180031866  test    eax, eax
0x180031868  js      short loc_1800318B6
0x18003186a  mov     rax, [rdi]
0x18003186d  lea     rdx, [rdi+8]
0x180031871  mov     qword ptr [rbp+57h+var_D0], rax
0x180031875  lea     rcx, [rbp+57h+var_90]
0x180031879  movups  xmm0, [rbp+57h+var_D0]
0x18003187d  movaps  [rbp+57h+var_80], xmm8
0x180031882  movaps  [rbp+57h+var_90], xmm0
0x180031886  movaps  [rbp+57h+var_70], xmm7
0x18003188a  movsd   [rbp+57h+var_60], xmm6
0x18003188f  call    cs:__imp_CSebCreatePrivateEvent
0x180031896  nop     dword ptr [rax+rax+00h]
0x18003189b  test    eax, eax
0x18003189d  js      short loc_1800318AC
0x18003189f  inc     ebx
0x1800318a1  cmp     ebx, 5
0x1800318a4  jb      short loc_18003182A
0x1800318a6  xor     edi, edi
0x1800318a8  xor     ebx, ebx
0x1800318aa  jmp     short loc_1800318CB
0x1800318ac  mov     edi, 1Eh
0x1800318b1  movzx   ebx, ax
0x1800318b4  jmp     short loc_1800318CB
0x1800318b6  mov     ecx, eax; Status
0x1800318b8  mov     edi, 14h
0x1800318bd  call    cs:__imp_RtlNtStatusToDosError
0x1800318c4  nop     dword ptr [rax+rax+00h]
0x1800318c9  mov     ebx, eax
0x1800318cb  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800318cf  test    rcx, rcx
0x1800318d2  jz      short loc_1800318E0
0x1800318d4  call    cs:__imp_LocalFree
0x1800318db  nop     dword ptr [rax+rax+00h]
0x1800318e0  mov     eax, cs:dword_18004F0F0
0x1800318e6  cmp     eax, 4
0x1800318e9  jbe     short loc_18003190F
0x1800318eb  lea     rax, [rbp+57h+arg_8]
0x1800318ef  mov     [rbp+57h+arg_8], edi
0x1800318f2  mov     [rsp+110h+var_E8], rax
0x1800318f7  lea     rdx, byte_180047421
0x1800318fe  lea     rax, [rbp+57h+arg_10]
0x180031902  mov     [rbp+57h+arg_10], ebx
0x180031905  mov     [rsp+110h+var_F0], rax
0x18003190a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003190f  lea     r11, [rsp+110h+var_18]
0x180031917  mov     eax, ebx
0x180031919  movaps  xmm6, xmmword ptr [r11-18h]
0x18003191e  movaps  xmm7, xmmword ptr [r11-28h]
0x180031923  movaps  xmm8, xmmword ptr [r11-38h]
0x180031928  mov     rsp, r11
0x18003192b  pop     r15
0x18003192d  pop     rdi
0x18003192e  pop     rbx
0x18003192f  pop     rbp
0x180031930  retn
```

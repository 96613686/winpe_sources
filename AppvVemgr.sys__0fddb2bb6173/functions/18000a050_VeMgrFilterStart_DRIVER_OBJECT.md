# VeMgrFilterStart(_DRIVER_OBJECT *)

- ea: `0x18000a050`
- end: `0x18000a1c3`
- name: `?VeMgrFilterStart@@YAJPEAU_DRIVER_OBJECT@@@Z`
- size: `371`
- prototype: `NTSTATUS __fastcall(PDRIVER_OBJECT Driver)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015fa4`

## callees

- `0x180005388`
- `0x18000a050`
- `0x18000ade8`
- `0x18000b09c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000a071`
- `ntoskrnl!ExAllocatePool2` at `0x18000a071`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a0f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a0f0`
- `FLTMGR!FltStartFiltering` at `0x18000a194`
- `FLTMGR!FltStartFiltering` at `0x18000a194`
- `FLTMGR!FltRegisterFilter` at `0x18000a0c1`
- `FLTMGR!FltRegisterFilter` at `0x18000a0c1`

## string_xrefs

- `0x18000a108`: `\VeMgrFltCommunicationClientServerPort`
- `0x18000a14f`: `\VeMgrFltCommunicationServerClientPort`

## pseudocode

```c
NTSTATUS __fastcall VeMgrFilterStart(PDRIVER_OBJECT Driver)
{
  _QWORD *Pool2; // rax
  NTSTATUS v3; // edi
  PVOID v4; // rbx
  NTSTATUS result; // eax
  _QWORD v6[2]; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v7[2]; // [rsp+40h] [rbp-10h] BYREF
  char v8; // [rsp+78h] [rbp+28h] BYREF
  int v9; // [rsp+80h] [rbp+30h] BYREF

  Pool2 = (_QWORD *)ExAllocatePool2(64, 40, 1733125462);
  if ( !Pool2 )
  {
    v3 = -1073741670;
LABEL_9:
    g_VeMgrFltData = 0;
    return v3;
  }
  *Pool2 = 0;
  Pool2[1] = 0;
  Pool2[2] = 0;
  Pool2[3] = 0;
  Pool2[4] = 0;
  g_VeMgrFltData = Pool2;
  v3 = FltRegisterFilter(Driver, &Registration, (PFLT_FILTER *)Pool2);
  if ( v3 < 0 )
  {
    v4 = g_VeMgrFltData;
    if ( g_VeMgrFltData )
    {
      VeMgrFilterData::~VeMgrFilterData((VeMgrFilterData *)g_VeMgrFltData);
      ExFreePoolWithTag(v4, 0);
    }
    goto LABEL_9;
  }
  v6[1] = L"\\VeMgrFltCommunicationClientServerPort";
  v6[0] = 5111884;
  v8 = 1;
  v9 = 2031617;
  result = appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::create_connection(
             (int)g_VeMgrFltData + 24,
             *(_QWORD *)g_VeMgrFltData,
             (unsigned int)v6,
             (unsigned int)&v8,
             (__int64)&v9);
  if ( result >= 0 )
  {
    v7[1] = L"\\VeMgrFltCommunicationServerClientPort";
    v7[0] = 5111884;
    v9 = 2031617;
    v8 = 0;
    result = appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>::create_connection(
               (int)g_VeMgrFltData + 8,
               *(_QWORD *)g_VeMgrFltData,
               (unsigned int)v7,
               (unsigned int)&v8,
               (__int64)&v9);
    if ( result >= 0 )
      return FltStartFiltering(*(PFLT_FILTER *)g_VeMgrFltData);
  }
  return result;
}

```

## disassembly

```asm
0x18000a050  mov     [rsp-18h+arg_0], rbx
0x18000a055  push    rbp
0x18000a056  push    rdi
0x18000a057  push    r14
0x18000a059  mov     rbp, rsp
0x18000a05c  sub     rsp, 50h
0x18000a060  mov     edx, 28h ; '('
0x18000a065  mov     rbx, rcx
0x18000a068  mov     r8d, 674D6556h
0x18000a06e  lea     ecx, [rdx+18h]
0x18000a071  call    cs:__imp_ExAllocatePool2
0x18000a078  nop     dword ptr [rax+rax+00h]
0x18000a07d  test    rax, rax
0x18000a080  jz      loc_18000A1A2
0x18000a086  mov     r8, rax; RetFilter
0x18000a089  mov     qword ptr [rax], 0
0x18000a090  lea     rdx, Registration; Registration
0x18000a097  mov     qword ptr [rax+8], 0
0x18000a09f  mov     rcx, rbx; Driver
0x18000a0a2  mov     qword ptr [rax+10h], 0
0x18000a0aa  mov     qword ptr [rax+18h], 0
0x18000a0b2  mov     qword ptr [rax+20h], 0
0x18000a0ba  mov     cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA, rax; VeMgrFilterData * g_VeMgrFltData
0x18000a0c1  call    cs:__imp_FltRegisterFilter
0x18000a0c8  nop     dword ptr [rax+rax+00h]
0x18000a0cd  mov     edi, eax
0x18000a0cf  test    eax, eax
0x18000a0d1  jns     short loc_18000A101
0x18000a0d3  mov     rbx, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x18000a0da  test    rbx, rbx
0x18000a0dd  jz      loc_18000A1A7
0x18000a0e3  mov     rcx, rbx; this
0x18000a0e6  call    ??1VeMgrFilterData@@QEAA@XZ; VeMgrFilterData::~VeMgrFilterData(void)
0x18000a0eb  xor     edx, edx; Tag
0x18000a0ed  mov     rcx, rbx; P
0x18000a0f0  call    cs:__imp_ExFreePoolWithTag
0x18000a0f7  nop     dword ptr [rax+rax+00h]
0x18000a0fc  jmp     loc_18000A1A7
0x18000a101  mov     rdx, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x18000a108  lea     rax, aVemgrfltcommun_0; "\\VeMgrFltCommunicationClientServerPort"
0x18000a10f  mov     [rbp+var_18], rax
0x18000a113  lea     r9, [rbp+arg_8]
0x18000a117  mov     [rbp+var_20], 4E004Ch
0x18000a11f  lea     rax, [rbp+arg_10]
0x18000a123  mov     ebx, 1F0001h
0x18000a128  mov     [rbp+arg_8], 1
0x18000a12c  lea     rcx, [rdx+18h]
0x18000a130  mov     [rbp+arg_10], ebx
0x18000a133  mov     rdx, [rdx]
0x18000a136  lea     r8, [rbp+var_20]
0x18000a13a  mov     [rsp+50h+var_30], rax
0x18000a13f  call    ?create_connection@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@SAJAEAV?$shared_ptr@V?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel_std@@PEAU_FLT_FILTER@@AEAU_UNICODE_STRING@@AEB_NAEBK@Z; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::create_connection(kernel_std::shared_ptr<appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>> &,_FLT_FILTER *,_UNICODE_STRING &,bool const &,ulong const &)
0x18000a144  test    eax, eax
0x18000a146  js      short loc_18000A1B4
0x18000a148  mov     rdx, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x18000a14f  lea     rax, aVemgrfltcommun; "\\VeMgrFltCommunicationServerClientPort"
0x18000a156  mov     [rbp+var_8], rax
0x18000a15a  lea     r9, [rbp+arg_8]
0x18000a15e  mov     [rbp+var_10], 4E004Ch
0x18000a166  lea     rax, [rbp+arg_10]
0x18000a16a  lea     r8, [rbp+var_10]
0x18000a16e  mov     [rbp+arg_10], ebx
0x18000a171  lea     rcx, [rdx+8]
0x18000a175  mov     [rbp+arg_8], 0
0x18000a179  mov     rdx, [rdx]
0x18000a17c  mov     [rsp+50h+var_30], rax
0x18000a181  call    ?create_connection@?$flt_connection@Vdefault_flt_connection_manager@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@SAJAEAV?$shared_ptr@V?$flt_connection@Vdefault_flt_connection_manager@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel_std@@PEAU_FLT_FILTER@@AEAU_UNICODE_STRING@@AEB_NAEBK@Z; appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>::create_connection(kernel_std::shared_ptr<appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>> &,_FLT_FILTER *,_UNICODE_STRING &,bool const &,ulong const &)
0x18000a186  test    eax, eax
0x18000a188  js      short loc_18000A1B4
0x18000a18a  mov     rcx, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x18000a191  mov     rcx, [rcx]; Filter
0x18000a194  call    cs:__imp_FltStartFiltering
0x18000a19b  nop     dword ptr [rax+rax+00h]
0x18000a1a0  jmp     short loc_18000A1B4
0x18000a1a2  mov     edi, 0C000009Ah
0x18000a1a7  mov     cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA, 0; VeMgrFilterData * g_VeMgrFltData
0x18000a1b2  mov     eax, edi
0x18000a1b4  mov     rbx, [rsp+50h+arg_0]
0x18000a1b9  add     rsp, 50h
0x18000a1bd  pop     r14
0x18000a1bf  pop     rdi
0x18000a1c0  pop     rbp
0x18000a1c1  retn
```

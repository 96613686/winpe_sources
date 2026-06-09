# FwppCommonInit

- ea: `0x18001bdd0`
- end: `0x18001bfaf`
- name: `FwppCommonInit`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000faf0`

## callees

- `0x18000891c`
- `0x18000c9b4`
- `0x18000ce38`
- `0x18000dffc`
- `0x18001bdd0`
- `0x18001bfb8`
- `0x18001f130`
- `0x18001f610`

## import_xrefs

- `ntoskrnl!MmIsVerifierEnabled` at `0x18001bf79`
- `ntoskrnl!MmIsVerifierEnabled` at `0x18001bf79`
- `ntoskrnl!KeInitializeSpinLock` at `0x18001bf64`
- `ntoskrnl!KeInitializeSpinLock` at `0x18001bf64`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x18001bec6`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x18001befc`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x18001bf30`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x18001bec6`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x18001befc`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x18001bf30`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001be06`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001be39`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001be6c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001beb5`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001be06`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001be39`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001be6c`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18001beb5`

## string_xrefs

- `0x18001bf91`: `FwppCommonInit`

## pseudocode

```c
__int64 FwppCommonInit()
{
  __int64 v0; // rdi
  ULONG MaximumProcessorCount; // eax
  __int64 i; // rbx
  __int64 v3; // rdx
  _QWORD *v4; // rdx
  int IsEnabledDeviceUsageNoInline; // eax

  ExInitializeNPagedLookasideList(&gFwpNblInfo, 0, 0, 0x200u, 0x178u, 0x6E707746u, 0);
  ExInitializeNPagedLookasideList(&stru_180048500, 0, 0, 0x200u, 0x20u, 0x69707746u, 0);
  ExInitializeNPagedLookasideList(&stru_180048580, 0, 0, 0x200u, 0xC0u, 0x78707746u, 0);
  v0 = WfpObjectManagerInitialize(&unk_180048680);
  if ( v0
    || (ExInitializeNPagedLookasideList(&Lookaside, 0, 0, 0x200u, 0xA0u, 0x64707746u, 0),
        MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu),
        (v0 = WfpPoolAllocNonPaged(24 * MaximumProcessorCount, 1886418758, &gPerProcessorContext)) != 0) )
  {
    FwppCommonShutdown();
    WfpReportError(v0, (int)"FwppCommonInit");
  }
  else
  {
    for ( i = 0; (unsigned int)i < KeQueryMaximumProcessorCountEx(0xFFFFu); *v4 = v4 )
    {
      v3 = i + 2 * i + 1;
      i = (unsigned int)(i + 1);
      v4 = (_QWORD *)(gPerProcessorContext + 8 * v3);
      v4[1] = v4;
    }
    if ( ((__int64)WPP_MAIN_CB.Dpc.DeferredContext & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = (__int64)WPP_MAIN_CB.Dpc.DeferredContext & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline();
    if ( IsEnabledDeviceUsageNoInline )
    {
      InitializeWfpVerifierSettings();
      KeInitializeSpinLock(&gSpecialPoolData);
    }
    else
    {
      MmIsVerifierEnabled(&gVerifierFlags);
      IsWfpNblVerifierEnabledInit();
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18001bdd0  mov     [rsp+arg_0], rbx
0x18001bdd5  push    rdi
0x18001bdd6  sub     rsp, 40h
0x18001bdda  xor     eax, eax
0x18001bddc  lea     rcx, gFwpNblInfo; Lookaside
0x18001bde3  mov     [rsp+48h+Depth], ax; Depth
0x18001bde8  mov     ebx, 200h
0x18001bded  mov     [rsp+48h+Tag], 6E707746h; Tag
0x18001bdf5  mov     r9d, ebx; Flags
0x18001bdf8  xor     r8d, r8d; Free
0x18001bdfb  mov     [rsp+48h+Size], 178h; Size
0x18001be04  xor     edx, edx; Allocate
0x18001be06  call    cs:__imp_ExInitializeNPagedLookasideList
0x18001be0d  nop     dword ptr [rax+rax+00h]
0x18001be12  xor     eax, eax
0x18001be14  lea     rcx, stru_180048500; Lookaside
0x18001be1b  mov     [rsp+48h+Depth], ax; Depth
0x18001be20  mov     r9d, ebx; Flags
0x18001be23  mov     [rsp+48h+Tag], 69707746h; Tag
0x18001be2b  xor     r8d, r8d; Free
0x18001be2e  xor     edx, edx; Allocate
0x18001be30  mov     [rsp+48h+Size], 20h ; ' '; Size
0x18001be39  call    cs:__imp_ExInitializeNPagedLookasideList
0x18001be40  nop     dword ptr [rax+rax+00h]
0x18001be45  xor     eax, eax
0x18001be47  lea     rcx, stru_180048580; Lookaside
0x18001be4e  mov     [rsp+48h+Depth], ax; Depth
0x18001be53  mov     r9d, ebx; Flags
0x18001be56  mov     [rsp+48h+Tag], 78707746h; Tag
0x18001be5e  xor     r8d, r8d; Free
0x18001be61  xor     edx, edx; Allocate
0x18001be63  mov     [rsp+48h+Size], 0C0h; Size
0x18001be6c  call    cs:__imp_ExInitializeNPagedLookasideList
0x18001be73  nop     dword ptr [rax+rax+00h]
0x18001be78  lea     rcx, unk_180048680; void *
0x18001be7f  call    WfpObjectManagerInitialize
0x18001be84  mov     rdi, rax
0x18001be87  test    rax, rax
0x18001be8a  jnz     loc_18001BF8C
0x18001be90  mov     [rsp+48h+Depth], ax; Depth
0x18001be95  lea     rcx, Lookaside; Lookaside
0x18001be9c  mov     [rsp+48h+Tag], 64707746h; Tag
0x18001bea4  mov     r9d, ebx; Flags
0x18001bea7  xor     r8d, r8d; Free
0x18001beaa  mov     [rsp+48h+Size], 0A0h; Size
0x18001beb3  xor     edx, edx; Allocate
0x18001beb5  call    cs:__imp_ExInitializeNPagedLookasideList
0x18001bebc  nop     dword ptr [rax+rax+00h]
0x18001bec1  mov     ecx, 0FFFFh; GroupNumber
0x18001bec6  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x18001becd  nop     dword ptr [rax+rax+00h]
0x18001bed2  lea     r8, gPerProcessorContext
0x18001bed9  mov     edx, 70707746h
0x18001bede  lea     ecx, [rax+rax*2]
0x18001bee1  shl     ecx, 3
0x18001bee4  call    WfpPoolAllocNonPaged
0x18001bee9  mov     rdi, rax
0x18001beec  test    rax, rax
0x18001beef  jnz     loc_18001BF8C
0x18001bef5  mov     ecx, 0FFFFh; GroupNumber
0x18001befa  xor     ebx, ebx
0x18001befc  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x18001bf03  nop     dword ptr [rax+rax+00h]
0x18001bf08  test    eax, eax
0x18001bf0a  jz      short loc_18001BF40
0x18001bf0c  mov     rax, cs:gPerProcessorContext
0x18001bf13  lea     rdx, ds:1[rbx*2]
0x18001bf1b  add     rdx, rbx
0x18001bf1e  mov     ecx, 0FFFFh; GroupNumber
0x18001bf23  inc     ebx
0x18001bf25  lea     rdx, [rax+rdx*8]
0x18001bf29  mov     [rdx+8], rdx
0x18001bf2d  mov     [rdx], rdx
0x18001bf30  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x18001bf37  nop     dword ptr [rax+rax+00h]
0x18001bf3c  cmp     ebx, eax
0x18001bf3e  jb      short loc_18001BF0C
0x18001bf40  mov     eax, dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext
0x18001bf46  test    al, 10h
0x18001bf48  jz      short loc_18001BF4F
0x18001bf4a  and     eax, 1
0x18001bf4d  jmp     short loc_18001BF54
0x18001bf4f  call    Feature_Firewall_042024__private_IsEnabledDeviceUsageNoInline
0x18001bf54  test    eax, eax
0x18001bf56  jz      short loc_18001BF72
0x18001bf58  call    InitializeWfpVerifierSettings
0x18001bf5d  lea     rcx, gSpecialPoolData; SpinLock
0x18001bf64  call    cs:__imp_KeInitializeSpinLock
0x18001bf6b  nop     dword ptr [rax+rax+00h]
0x18001bf70  jmp     short loc_18001BFA0
0x18001bf72  lea     rcx, gVerifierFlags; VerifierFlags
0x18001bf79  call    cs:__imp_MmIsVerifierEnabled
0x18001bf80  nop     dword ptr [rax+rax+00h]
0x18001bf85  call    IsWfpNblVerifierEnabledInit
0x18001bf8a  jmp     short loc_18001BFA0
0x18001bf8c  call    FwppCommonShutdown
0x18001bf91  lea     rdx, aFwppcommoninit; "FwppCommonInit"
0x18001bf98  mov     rcx, rdi
0x18001bf9b  call    WfpReportError
0x18001bfa0  mov     rbx, [rsp+48h+arg_0]
0x18001bfa5  mov     rax, rdi
0x18001bfa8  add     rsp, 40h
0x18001bfac  pop     rdi
0x18001bfad  retn
```

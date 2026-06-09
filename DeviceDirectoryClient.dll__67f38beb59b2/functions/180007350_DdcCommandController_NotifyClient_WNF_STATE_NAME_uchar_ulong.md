# DdcCommandController::NotifyClient(_WNF_STATE_NAME,uchar *,ulong)

- ea: `0x180007350`
- end: `0x1800073af`
- name: `?NotifyClient@DdcCommandController@@SAJU_WNF_STATE_NAME@@PEAEK@Z`
- size: `95`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006230`
- `0x18000921c`

## callees

- `0x1800050b8`
- `0x180007350`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180007367`
- `ntdll!RtlPublishWnfStateData` at `0x180007367`

## string_xrefs

- `0x18000738f`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`

## pseudocode

```c
__int64 __fastcall DdcCommandController::NotifyClient(struct _WNF_STATE_NAME a1, unsigned __int8 *a2, unsigned int a3)
{
  int v3; // edx
  int v4; // ecx
  int v5; // ebx
  unsigned int v6; // ebx

  v5 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))RtlPublishWnfStateData)(a1, 0, a2, a3, 0);
  if ( v5 )
  {
    v6 = v5 | 0x10000000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        v3,
        v6,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        23,
        "CBR(((NTSTATUS)0x00000000L) == ntStatus)");
  }
  else
  {
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180007350  push    rbx
0x180007352  sub     rsp, 30h
0x180007356  mov     r9d, r8d
0x180007359  mov     [rsp+38h+var_18], 0
0x180007362  mov     r8, rdx
0x180007365  xor     edx, edx
0x180007367  call    cs:__imp_RtlPublishWnfStateData
0x18000736d  mov     ebx, eax
0x18000736f  test    eax, eax
0x180007371  jz      short loc_1800073A5
0x180007373  bts     ebx, 1Ch
0x180007377  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000737e  jz      short loc_1800073A7
0x180007380  lea     rax, aCbrNtstatus0x0; "CBR(((NTSTATUS)0x00000000L) == ntStatus"...
0x180007387  mov     r8d, ebx
0x18000738a  mov     [rsp+38h+var_10], rax
0x18000738f  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180007396  mov     dword ptr [rsp+38h+var_18], 117h
0x18000739e  call    McTemplateU0dsqs_EventWriteTransfer
0x1800073a3  jmp     short loc_1800073A7
0x1800073a5  xor     ebx, ebx
0x1800073a7  mov     eax, ebx
0x1800073a9  add     rsp, 30h
0x1800073ad  pop     rbx
0x1800073ae  retn
```

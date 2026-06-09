# DdcProtectionStateHelper::GetAssessmentFieldNames(_tagHealthAdvisorAssessment,ushort const * *,ushort const * *)

- ea: `0x18001dc38`
- end: `0x18001dcf6`
- name: `?GetAssessmentFieldNames@DdcProtectionStateHelper@@CAJW4_tagHealthAdvisorAssessment@@PEAPEBG1@Z`
- size: `190`
- prototype: `__int64 __fastcall(int, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dcfc`

## callees

- `0x1800050b8`
- `0x18001dc38`

## string_xrefs

- `0x18001dc6d`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001dc59`: `CPR(ppwszJsonHealth)`
- `0x18001dc92`: `CPR(ppwszJsonStatus)`

## pseudocode

```c
__int64 __fastcall DdcProtectionStateHelper::GetAssessmentFieldNames(int a1, _QWORD *a2, _QWORD *a3)
{
  unsigned int v3; // ebx

  if ( a2 )
  {
    if ( a3 )
    {
      if ( a1 == 256 )
      {
        v3 = 0;
        *a2 = L"StorageHealthEvalAssessmentHealth";
        *a3 = L"StorageHealthEvalAssessmentStatus";
      }
      else
      {
        v3 = -2147024809;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            a1,
            (_DWORD)a2,
            -2147024809,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
            117,
            "CHR(((HRESULT)0x80070057L))");
      }
    }
    else
    {
      v3 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          a1,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
          107,
          "CPR(ppwszJsonStatus)");
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
        106,
        "CPR(ppwszJsonHealth)");
  }
  return v3;
}

```

## disassembly

```asm
0x18001dc38  push    rbx
0x18001dc3a  sub     rsp, 30h
0x18001dc3e  test    rdx, rdx
0x18001dc41  jnz     short loc_18001DC7B
0x18001dc43  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001dc4a  mov     r8d, 80070057h
0x18001dc50  mov     ebx, r8d
0x18001dc53  jz      loc_18001DCEE
0x18001dc59  lea     rax, aCprPpwszjsonhe; "CPR(ppwszJsonHealth)"
0x18001dc60  mov     [rsp+38h+var_10], rax
0x18001dc65  mov     [rsp+38h+var_18], 46Ah
0x18001dc6d  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001dc74  call    McTemplateU0dsqs_EventWriteTransfer
0x18001dc79  jmp     short loc_18001DCEE
0x18001dc7b  test    r8, r8
0x18001dc7e  jnz     short loc_18001DCA8
0x18001dc80  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001dc87  mov     r8d, 80070057h
0x18001dc8d  mov     ebx, r8d
0x18001dc90  jz      short loc_18001DCEE
0x18001dc92  lea     rax, aCprPpwszjsonst; "CPR(ppwszJsonStatus)"
0x18001dc99  mov     [rsp+38h+var_10], rax
0x18001dc9e  mov     [rsp+38h+var_18], 46Bh
0x18001dca6  jmp     short loc_18001DC6D
0x18001dca8  cmp     ecx, 100h
0x18001dcae  jz      short loc_18001DCD8
0x18001dcb0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001dcb7  mov     r8d, 80070057h
0x18001dcbd  mov     ebx, r8d
0x18001dcc0  jz      short loc_18001DCEE
0x18001dcc2  lea     rax, aChrHresult0x80; "CHR(((HRESULT)0x80070057L))"
0x18001dcc9  mov     [rsp+38h+var_10], rax
0x18001dcce  mov     [rsp+38h+var_18], 475h
0x18001dcd6  jmp     short loc_18001DC6D
0x18001dcd8  lea     rax, aStoragehealthe; "StorageHealthEvalAssessmentHealth"
0x18001dcdf  xor     ebx, ebx
0x18001dce1  mov     [rdx], rax
0x18001dce4  lea     rax, aStoragehealthe_0; "StorageHealthEvalAssessmentStatus"
0x18001dceb  mov     [r8], rax
0x18001dcee  mov     eax, ebx
0x18001dcf0  add     rsp, 30h
0x18001dcf4  pop     rbx
0x18001dcf5  retn
```

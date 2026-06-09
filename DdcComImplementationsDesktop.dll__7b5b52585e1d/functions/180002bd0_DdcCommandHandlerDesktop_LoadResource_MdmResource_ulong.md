# DdcCommandHandlerDesktop::LoadResource(MdmResource,ulong *)

- ea: `0x180002bd0`
- end: `0x180002c48`
- name: `?LoadResource@DdcCommandHandlerDesktop@@UEAAJW4MdmResource@@PEAK@Z`
- size: `120`
- prototype: `__int64 __fastcall(int, int, _DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026ac`
- `0x180002bd0`

## string_xrefs

- `0x180002bfd`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddccommandhandlerdesktop.cpp`

## pseudocode

```c
__int64 __fastcall DdcCommandHandlerDesktop::LoadResource(int a1, int a2, _DWORD *a3)
{
  unsigned int v3; // ebx

  if ( a3 )
  {
    if ( a2 == 1 )
    {
      v3 = 0;
      *a3 = 607;
    }
    else
    {
      v3 = -2147467263;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          a1,
          a2,
          -2147467263,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomm"
                        "andhandlerdesktop.cpp",
          37,
          (__int64)"CHR(((HRESULT)0x80004001L))");
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomman"
                      "dhandlerdesktop.cpp",
        29,
        (__int64)"CPR(pResourceId)");
  }
  return v3;
}

```

## disassembly

```asm
0x180002bd0  push    rbx
0x180002bd2  sub     rsp, 30h
0x180002bd6  test    r8, r8
0x180002bd9  jnz     short loc_180002C0E
0x180002bdb  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002be2  mov     ebx, 80070057h
0x180002be7  jz      short loc_180002C40
0x180002be9  lea     rax, aCprPresourceid; "CPR(pResourceId)"
0x180002bf0  mov     [rsp+38h+var_10], rax
0x180002bf5  mov     [rsp+38h+var_18], 11Dh
0x180002bfd  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180002c04  mov     r8d, ebx
0x180002c07  call    McTemplateU0dsqs_EventWriteTransfer
0x180002c0c  jmp     short loc_180002C40
0x180002c0e  cmp     edx, 1
0x180002c11  jz      short loc_180002C37
0x180002c13  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002c1a  mov     ebx, 80004001h
0x180002c1f  jz      short loc_180002C40
0x180002c21  lea     rax, aChrHresult0x80_0; "CHR(((HRESULT)0x80004001L))"
0x180002c28  mov     [rsp+38h+var_10], rax
0x180002c2d  mov     [rsp+38h+var_18], 125h
0x180002c35  jmp     short loc_180002BFD
0x180002c37  xor     ebx, ebx
0x180002c39  mov     dword ptr [r8], 25Fh
0x180002c40  mov     eax, ebx
0x180002c42  add     rsp, 30h
0x180002c46  pop     rbx
0x180002c47  retn
```

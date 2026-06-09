# DdcWnsListener::RegisterChannel(FILETIMEEX *,ushort *,ulong *)

- ea: `0x180024d0c`
- end: `0x180024d93`
- name: `?RegisterChannel@DdcWnsListener@@CAJPEATFILETIMEEX@@PEAGPEAK@Z`
- size: `135`
- prototype: `__int64 __fastcall(union FILETIMEEX *, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024d9c`

## callees

- `0x1800050b8`
- `0x180024ae0`
- `0x180024d0c`
- `0x180024fb8`

## string_xrefs

- `0x180024d79`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcwnslistener.cpp`
- `0x180024d65`: `CHR(RegisterWnsChannel(pftExpiration, pwszChannelUri, pcchChannelUri))`

## pseudocode

```c
__int64 __fastcall DdcWnsListener::RegisterChannel(union FILETIMEEX *a1, unsigned __int16 *a2, unsigned int *a3)
{
  int v6; // edx
  int v7; // ecx
  int v8; // ebx
  int v9; // edx
  int v10; // ecx

  v8 = DdcWnsListener::RegisterApplication();
  if ( v8 >= 0 )
  {
    v8 = DdcWnsListener::RegisterWnsChannel(a1, a2, a3);
    if ( v8 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        v9,
        v8,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
        137,
        "CHR(RegisterWnsChannel(pftExpiration, pwszChannelUri, pcchChannelUri))");
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      v6,
      v8,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
      136,
      "CHR(RegisterApplication())");
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180024d0c  push    rbx
0x180024d0e  push    rbp
0x180024d0f  push    rsi
0x180024d10  push    rdi
0x180024d11  sub     rsp, 38h
0x180024d15  mov     rdi, r8
0x180024d18  mov     rsi, rdx
0x180024d1b  mov     rbp, rcx
0x180024d1e  call    ?RegisterApplication@DdcWnsListener@@CAJXZ; DdcWnsListener::RegisterApplication(void)
0x180024d23  mov     ebx, eax
0x180024d25  test    eax, eax
0x180024d27  jns     short loc_180024D48
0x180024d29  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024d30  jz      short loc_180024D88
0x180024d32  lea     rax, aChrRegisterapp; "CHR(RegisterApplication())"
0x180024d39  mov     [rsp+58h+var_30], rax
0x180024d3e  mov     [rsp+58h+var_38], 88h
0x180024d46  jmp     short loc_180024D79
0x180024d48  mov     r8, rdi; unsigned int *
0x180024d4b  mov     rdx, rsi; unsigned __int16 *
0x180024d4e  mov     rcx, rbp; union FILETIMEEX *
0x180024d51  call    ?RegisterWnsChannel@DdcWnsListener@@CAJPEATFILETIMEEX@@PEAGPEAK@Z; DdcWnsListener::RegisterWnsChannel(FILETIMEEX *,ushort *,ulong *)
0x180024d56  mov     ebx, eax
0x180024d58  test    eax, eax
0x180024d5a  jns     short loc_180024D88
0x180024d5c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024d63  jz      short loc_180024D88
0x180024d65  lea     rax, aChrRegisterwns; "CHR(RegisterWnsChannel(pftExpiration, p"...
0x180024d6c  mov     [rsp+58h+var_30], rax
0x180024d71  mov     [rsp+58h+var_38], 89h
0x180024d79  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180024d80  mov     r8d, ebx
0x180024d83  call    McTemplateU0dsqs_EventWriteTransfer
0x180024d88  mov     eax, ebx
0x180024d8a  add     rsp, 38h
0x180024d8e  pop     rdi
0x180024d8f  pop     rsi
0x180024d90  pop     rbp
0x180024d91  pop     rbx
0x180024d92  retn
```

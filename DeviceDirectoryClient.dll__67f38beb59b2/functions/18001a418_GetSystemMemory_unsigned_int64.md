# GetSystemMemory(unsigned __int64 *)

- ea: `0x18001a418`
- end: `0x18001a50c`
- name: `?GetSystemMemory@@YAJPEA_K@Z`
- size: `244`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019400`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800050b8`
- `0x18001a418`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18001a495`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18001a495`

## string_xrefs

- `0x18001a47c`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcdeviceinfohelper.cpp`

## pseudocode

```c
__int64 __fastcall GetSystemMemory(unsigned __int64 *a1)
{
  int v2; // edx
  int v3; // ecx
  unsigned int v4; // ebx
  int v5; // edx
  int v6; // ecx
  _MEMORYSTATUSEX Buffer; // [rsp+30h] [rbp-58h] BYREF

  memset_0(&Buffer, 0, sizeof(Buffer));
  Buffer.dwLength = 64;
  v4 = 0;
  if ( a1 )
  {
    *a1 = 0;
    if ( GlobalMemoryStatusEx(&Buffer) )
    {
      *a1 = 107374182 * (Buffer.ullTotalPhys / 0x6666666);
    }
    else
    {
      v4 = -2147467259;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v6,
          v5,
          -2147467259,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
          99,
          "CBR(GlobalMemoryStatusEx(&ms))",
          *(_QWORD *)&Buffer.dwLength);
    }
  }
  else
  {
    v4 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcdeviceinfohelper.cpp",
        96,
        "CPR(pUllBytes)",
        *(_QWORD *)&Buffer.dwLength);
  }
  return v4;
}

```

## disassembly

```asm
0x18001a418  mov     [rsp+arg_8], rbx
0x18001a41d  push    rdi
0x18001a41e  sub     rsp, 80h
0x18001a425  mov     rax, cs:__security_cookie
0x18001a42c  xor     rax, rsp
0x18001a42f  mov     [rsp+88h+var_18], rax
0x18001a434  mov     rdi, rcx
0x18001a437  mov     ebx, 40h ; '@'
0x18001a43c  mov     r8d, ebx; Size
0x18001a43f  lea     rcx, [rsp+88h+Buffer]; void *
0x18001a444  xor     edx, edx; Val
0x18001a446  call    memset_0
0x18001a44b  mov     [rsp+88h+Buffer.dwLength], ebx
0x18001a44f  xor     ebx, ebx
0x18001a451  test    rdi, rdi
0x18001a454  jnz     short loc_18001A48D
0x18001a456  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a45d  mov     ebx, 80070057h
0x18001a462  jz      loc_18001A4EC
0x18001a468  lea     rax, aCprPullbytes; "CPR(pUllBytes)"
0x18001a46f  mov     [rsp+88h+var_60], rax
0x18001a474  mov     [rsp+88h+var_68], 560h
0x18001a47c  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001a483  mov     r8d, ebx
0x18001a486  call    McTemplateU0dsqs_EventWriteTransfer
0x18001a48b  jmp     short loc_18001A4EC
0x18001a48d  lea     rcx, [rsp+88h+Buffer]; lpBuffer
0x18001a492  mov     [rdi], rbx
0x18001a495  call    cs:__imp_GlobalMemoryStatusEx
0x18001a49b  test    eax, eax
0x18001a49d  jnz     short loc_18001A4C3
0x18001a49f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001a4a6  mov     ebx, 80004005h
0x18001a4ab  jz      short loc_18001A4EC
0x18001a4ad  lea     rax, aCbrGlobalmemor; "CBR(GlobalMemoryStatusEx(&ms))"
0x18001a4b4  mov     [rsp+88h+var_60], rax
0x18001a4b9  mov     [rsp+88h+var_68], 563h
0x18001a4c1  jmp     short loc_18001A47C
0x18001a4c3  mov     rcx, [rsp+88h+Buffer.ullTotalPhys]
0x18001a4c8  mov     rax, 4000001400000141h
0x18001a4d2  mul     rcx
0x18001a4d5  sub     rcx, rdx
0x18001a4d8  shr     rcx, 1
0x18001a4db  add     rcx, rdx
0x18001a4de  shr     rcx, 1Ah
0x18001a4e2  imul    rcx, 6666666h
0x18001a4e9  mov     [rdi], rcx
0x18001a4ec  mov     eax, ebx
0x18001a4ee  mov     rcx, [rsp+88h+var_18]
0x18001a4f3  xor     rcx, rsp; StackCookie
0x18001a4f6  call    __security_check_cookie
0x18001a4fb  mov     rbx, [rsp+88h+arg_8]
0x18001a503  add     rsp, 80h
0x18001a50a  pop     rdi
0x18001a50b  retn
```

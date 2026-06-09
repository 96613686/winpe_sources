# IsTooSoonForUserRegistration(int *)

- ea: `0x18000a7b8`
- end: `0x18000a89b`
- name: `?IsTooSoonForUserRegistration@@YAJPEAH@Z`
- size: `227`
- prototype: `__int64 __fastcall(unsigned int *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ca4c`

## callees

- `0x1800050b8`
- `0x18000a7b8`
- `0x18001b844`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a86d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a86d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a87d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000a87d`

## string_xrefs

- `0x18000a83d`: `SOFTWARE\Microsoft\DeviceDirectory`
- `0x18000a804`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistrationcontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall IsTooSoonForUserRegistration(unsigned int *a1, int a2)
{
  unsigned int v3; // ebx
  unsigned int ByteValue; // eax
  unsigned int v5; // eax
  unsigned int v7; // [rsp+40h] [rbp+8h] BYREF
  FILETIME FileTime2; // [rsp+48h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp+18h] BYREF

  FileTime2 = 0;
  SystemTimeAsFileTime = 0;
  v7 = 8;
  if ( a1 )
  {
    *a1 = 1;
    ByteValue = DdcRegistry::GetByteValue(
                  HKEY_CURRENT_USER,
                  L"SOFTWARE\\Microsoft\\DeviceDirectory",
                  L"LastUserRegistrationTimestamp",
                  (unsigned __int8 *const)&FileTime2,
                  &v7);
    v3 = ByteValue;
    if ( ByteValue == -2147023728 || ByteValue == -2147024894 )
    {
      v3 = 0;
      v5 = 0;
    }
    else
    {
      *(_QWORD *)&FileTime2 += 25920000000000LL;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v5 = (unsigned int)CompareFileTime(&SystemTimeAsFileTime, &FileTime2) >> 31;
    }
    *a1 = v5;
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistrationcontroller.cpp",
        177,
        "CPR(pfTooSoonForUserRegistration)");
  }
  return v3;
}

```

## disassembly

```asm
0x18000a7b8  mov     rax, rsp
0x18000a7bb  mov     [rax+20h], rbx
0x18000a7bf  push    rdi
0x18000a7c0  sub     rsp, 30h
0x18000a7c4  mov     qword ptr [rax+10h], 0
0x18000a7cc  mov     rdi, rcx
0x18000a7cf  mov     qword ptr [rax+18h], 0
0x18000a7d7  mov     dword ptr [rax+8], 8
0x18000a7de  test    rcx, rcx
0x18000a7e1  jnz     short loc_18000A81A
0x18000a7e3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000a7ea  mov     ebx, 80070057h
0x18000a7ef  jz      loc_18000A88E
0x18000a7f5  lea     rax, aCprPftoosoonfo; "CPR(pfTooSoonForUserRegistration)"
0x18000a7fc  mov     r8d, ebx
0x18000a7ff  mov     [rsp+38h+var_10], rax
0x18000a804  lea     r9, aOnecoreuapShel_4; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000a80b  mov     dword ptr [rsp+38h+var_18], 0B1h
0x18000a813  call    McTemplateU0dsqs_EventWriteTransfer
0x18000a818  jmp     short loc_18000A88E
0x18000a81a  mov     dword ptr [rcx], 1
0x18000a820  lea     rax, [rsp+38h+arg_0]
0x18000a825  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x18000a82c  mov     [rsp+38h+var_18], rax; unsigned int *
0x18000a831  lea     r9, [rsp+38h+FileTime2]; unsigned __int8 *
0x18000a836  lea     r8, aLastuserregist; "LastUserRegistrationTimestamp"
0x18000a83d  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\DeviceDirectory"
0x18000a844  call    ?GetByteValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1QEAEAEAK@Z; DdcRegistry::GetByteValue(HKEY__ *,ushort const *,ushort const *,uchar * const,ulong &)
0x18000a849  mov     ebx, eax
0x18000a84b  cmp     eax, 80070490h
0x18000a850  jz      short loc_18000A888
0x18000a852  cmp     eax, 80070002h
0x18000a857  jz      short loc_18000A888
0x18000a859  mov     rax, 1792F8648000h
0x18000a863  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000a868  add     qword ptr [rsp+38h+FileTime2.dwLowDateTime], rax
0x18000a86d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000a873  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x18000a878  lea     rcx, [rsp+38h+SystemTimeAsFileTime]; lpFileTime1
0x18000a87d  call    cs:__imp_CompareFileTime
0x18000a883  shr     eax, 1Fh
0x18000a886  jmp     short loc_18000A88C
0x18000a888  xor     ebx, ebx
0x18000a88a  xor     eax, eax
0x18000a88c  mov     [rdi], eax
0x18000a88e  mov     eax, ebx
0x18000a890  mov     rbx, [rsp+38h+arg_18]
0x18000a895  add     rsp, 30h
0x18000a899  pop     rdi
0x18000a89a  retn
```

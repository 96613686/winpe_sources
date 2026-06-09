# DdcRegistry::DeleteKey(HKEY__ *,ushort const *)

- ea: `0x1800040b8`
- end: `0x180004120`
- name: `?DeleteKey@DdcRegistry@@SAJPEAUHKEY__@@PEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004218`

## callees

- `0x1800026ac`
- `0x1800040b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800040cc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800040cc`

## string_xrefs

- `0x1800040be`: `SYSTEM\CurrentControlSet\Control\Lsa\LockedDownSIDs`
- `0x180004100`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
__int64 __fastcall DdcRegistry::DeleteKey(HKEY a1, const unsigned __int16 *a2)
{
  LSTATUS v2; // eax
  int v3; // edx
  int v4; // ecx
  unsigned int v5; // ebx

  v2 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Lsa\\LockedDownSIDs");
  v5 = v2;
  if ( (v2 & 0xFFFFFFFD) != 0 )
  {
    if ( v2 > 0 )
      v5 = (unsigned __int16)v2 | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        v3,
        v5,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
        233,
        (__int64)"CBR(dwResult == 0L)");
  }
  else
  {
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800040b8  push    rbx
0x1800040ba  sub     rsp, 30h
0x1800040be  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Lsa"...
0x1800040c5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800040cc  call    cs:__imp_RegDeleteTreeW
0x1800040d2  mov     ebx, eax
0x1800040d4  test    eax, 0FFFFFFFDh
0x1800040d9  jz      short loc_180004116
0x1800040db  test    eax, eax
0x1800040dd  jle     short loc_1800040E8
0x1800040df  movzx   ebx, ax
0x1800040e2  or      ebx, 80070000h
0x1800040e8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800040ef  jz      short loc_180004118
0x1800040f1  lea     rax, aCbrDwresult0l; "CBR(dwResult == 0L)"
0x1800040f8  mov     r8d, ebx
0x1800040fb  mov     [rsp+38h+var_10], rax
0x180004100  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180004107  mov     [rsp+38h+var_18], 2E9h
0x18000410f  call    McTemplateU0dsqs_EventWriteTransfer
0x180004114  jmp     short loc_180004118
0x180004116  xor     ebx, ebx
0x180004118  mov     eax, ebx
0x18000411a  add     rsp, 30h
0x18000411e  pop     rbx
0x18000411f  retn
```

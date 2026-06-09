# DeviceConnected(int *)

- ea: `0x18001263c`
- end: `0x1800126ef`
- name: `?DeviceConnected@@YAJPEAH@Z`
- size: `179`
- prototype: `__int64 __fastcall(int *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013004`
- `0x1800132e4`

## callees

- `0x1800050b8`
- `0x18001263c`

## import_xrefs

- `ntdll!NtQueryWnfStateData` at `0x1800126c1`
- `ntdll!NtQueryWnfStateData` at `0x1800126c1`

## string_xrefs

- `0x180012682`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`

## pseudocode

```c
__int64 __fastcall DeviceConnected(int *a1, int a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  int v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+48h] [rbp+10h] BYREF
  int v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  v7 = 0;
  v6 = 4;
  if ( a1 )
  {
    v3 = 0;
    *a1 = 0;
    if ( (unsigned int)NtQueryWnfStateData(&WNF_NLM_INTERNET_PRESENT, 0, 0, &v8, &v7, &v6) || !v6 )
      v4 = 0;
    else
      v4 = v7;
    *a1 = v4 != 0;
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        19,
        "CPR(pfConnected)");
  }
  return v3;
}

```

## disassembly

```asm
0x18001263c  mov     rax, rsp
0x18001263f  mov     [rax+20h], rbx
0x180012643  push    rdi
0x180012644  sub     rsp, 30h
0x180012648  mov     dword ptr [rax+18h], 0
0x18001264f  mov     rdi, rcx
0x180012652  mov     dword ptr [rax+10h], 0
0x180012659  mov     dword ptr [rax+8], 4
0x180012660  test    rcx, rcx
0x180012663  jnz     short loc_180012698
0x180012665  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001266c  mov     ebx, 80070057h
0x180012671  jz      short loc_1800126E2
0x180012673  lea     rax, aCprPfconnected; "CPR(pfConnected)"
0x18001267a  mov     r8d, ebx
0x18001267d  mov     [rsp+38h+var_10], rax
0x180012682  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180012689  mov     dword ptr [rsp+38h+var_18], 113h
0x180012691  call    McTemplateU0dsqs_EventWriteTransfer
0x180012696  jmp     short loc_1800126E2
0x180012698  lea     rax, [rsp+38h+arg_0]
0x18001269d  xor     ebx, ebx
0x18001269f  mov     [rsp+38h+var_10], rax
0x1800126a4  lea     r9, [rsp+38h+arg_10]
0x1800126a9  lea     rax, [rsp+38h+arg_8]
0x1800126ae  mov     [rcx], ebx
0x1800126b0  xor     r8d, r8d
0x1800126b3  mov     [rsp+38h+var_18], rax
0x1800126b8  xor     edx, edx
0x1800126ba  lea     rcx, WNF_NLM_INTERNET_PRESENT
0x1800126c1  call    cs:__imp_NtQueryWnfStateData
0x1800126c7  test    eax, eax
0x1800126c9  jnz     short loc_1800126D7
0x1800126cb  cmp     [rsp+38h+arg_0], ebx
0x1800126cf  jz      short loc_1800126D7
0x1800126d1  mov     eax, [rsp+38h+arg_8]
0x1800126d5  jmp     short loc_1800126D9
0x1800126d7  xor     eax, eax
0x1800126d9  xor     ecx, ecx
0x1800126db  test    eax, eax
0x1800126dd  setnz   cl
0x1800126e0  mov     [rdi], ecx
0x1800126e2  mov     eax, ebx
0x1800126e4  mov     rbx, [rsp+38h+arg_18]
0x1800126e9  add     rsp, 30h
0x1800126ed  pop     rdi
0x1800126ee  retn
```

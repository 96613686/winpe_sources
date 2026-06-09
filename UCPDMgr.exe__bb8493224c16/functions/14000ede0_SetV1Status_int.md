# SetV1Status(int)

- ea: `0x14000ede0`
- end: `0x14000eec2`
- name: `?SetV1Status@@YAXH@Z`
- size: `226`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14000e590`

## callees

- `0x14000ede0`
- `0x14000eed0`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x14000eea3`
- `ADVAPI32!CloseServiceHandle` at `0x14000eeac`
- `ADVAPI32!CloseServiceHandle` at `0x14000eea3`
- `ADVAPI32!CloseServiceHandle` at `0x14000eeac`
- `ADVAPI32!OpenSCManagerA` at `0x14000edfb`
- `ADVAPI32!OpenSCManagerA` at `0x14000edfb`
- `ADVAPI32!OpenServiceA` at `0x14000ee1d`
- `ADVAPI32!OpenServiceA` at `0x14000ee1d`
- `ADVAPI32!ChangeServiceConfigA` at `0x14000ee9a`
- `ADVAPI32!ChangeServiceConfigA` at `0x14000ee9a`

## pseudocode

```c
void __fastcall SetV1Status(int a1)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rbx
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rdi
  unsigned int ServiceStartType; // eax
  bool v7; // zf

  v2 = OpenSCManagerA(0, 0, 0xF003Fu);
  v3 = v2;
  if ( v2 )
  {
    v4 = OpenServiceA(v2, "UCPD", 3u);
    v5 = v4;
    if ( v4 )
    {
      ServiceStartType = GetServiceStartType(v4);
      if ( ServiceStartType != -1 )
      {
        if ( a1 )
          v7 = ServiceStartType == 1;
        else
          v7 = ServiceStartType == 4;
        if ( !v7 )
          ChangeServiceConfigA(v5, 0xFFFFFFFF, a1 != 0 ? 1 : 4, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0);
      }
      CloseServiceHandle(v5);
    }
    CloseServiceHandle(v3);
  }
}

```

## disassembly

```asm
0x14000ede0  mov     [rsp+arg_0], rbx
0x14000ede5  mov     [rsp+arg_8], rsi
0x14000edea  push    rdi
0x14000edeb  sub     rsp, 60h
0x14000edef  mov     esi, ecx
0x14000edf1  xor     edx, edx; lpDatabaseName
0x14000edf3  xor     ecx, ecx; lpMachineName
0x14000edf5  mov     r8d, 0F003Fh; dwDesiredAccess
0x14000edfb  call    cs:__imp_OpenSCManagerA
0x14000ee01  mov     rbx, rax
0x14000ee04  test    rax, rax
0x14000ee07  jz      loc_14000EEB2
0x14000ee0d  mov     r8d, 3; dwDesiredAccess
0x14000ee13  lea     rdx, ServiceName; "UCPD"
0x14000ee1a  mov     rcx, rax; hSCManager
0x14000ee1d  call    cs:__imp_OpenServiceA
0x14000ee23  mov     rdi, rax
0x14000ee26  test    rax, rax
0x14000ee29  jz      short loc_14000EEA9
0x14000ee2b  mov     rcx, rax; hService
0x14000ee2e  call    ?GetServiceStartType@@YAKPEAUSC_HANDLE__@@@Z; GetServiceStartType(SC_HANDLE__ *)
0x14000ee33  or      edx, 0FFFFFFFFh; dwServiceType
0x14000ee36  cmp     eax, edx
0x14000ee38  jz      short loc_14000EEA0
0x14000ee3a  test    esi, esi
0x14000ee3c  jz      short loc_14000EE43
0x14000ee3e  cmp     eax, 1
0x14000ee41  jmp     short loc_14000EE46
0x14000ee43  cmp     eax, 4
0x14000ee46  jz      short loc_14000EEA0
0x14000ee48  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x14000ee51  neg     esi
0x14000ee53  mov     [rsp+68h+lpPassword], 0; lpPassword
0x14000ee5c  mov     r9d, edx; dwErrorControl
0x14000ee5f  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x14000ee68  sbb     r8d, r8d
0x14000ee6b  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x14000ee74  and     r8d, 0FFFFFFFDh
0x14000ee78  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x14000ee81  add     r8d, 4; dwStartType
0x14000ee85  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x14000ee8e  mov     rcx, rdi; hService
0x14000ee91  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x14000ee9a  call    cs:__imp_ChangeServiceConfigA
0x14000eea0  mov     rcx, rdi; hSCObject
0x14000eea3  call    cs:__imp_CloseServiceHandle
0x14000eea9  mov     rcx, rbx; hSCObject
0x14000eeac  call    cs:__imp_CloseServiceHandle
0x14000eeb2  mov     rbx, [rsp+68h+arg_0]
0x14000eeb7  mov     rsi, [rsp+68h+arg_8]
0x14000eebc  add     rsp, 60h
0x14000eec0  pop     rdi
0x14000eec1  retn
```

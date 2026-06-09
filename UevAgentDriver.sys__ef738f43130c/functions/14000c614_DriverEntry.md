# DriverEntry

- ea: `0x14000c614`
- end: `0x14000c76e`
- name: `DriverEntry`
- size: `346`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c010`

## callees

- `0x140001118`
- `0x140001298`
- `0x140001488`
- `0x1400014c8`
- `0x140001500`
- `0x14000a120`
- `0x14000a284`
- `0x14000ac48`
- `0x14000b614`
- `0x14000b734`
- `0x14000c55c`
- `0x14000c614`

## import_xrefs

- `FLTMGR!FltRegisterFilter` at `0x14000c68a`
- `FLTMGR!FltRegisterFilter` at `0x14000c68a`

## string_xrefs

- `0x14000c654`: `UevFilter.DriverEntry: ComPort initialization failed, status = 0x%X\n`
- `0x14000c6d0`: `UevFilter.DriverEntry: Communication Port creation failed, status = 0x%X\n`
- `0x14000c713`: `UevFilter.DriverEntry: Failed to create process event port. status = 0x%X\n`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 v2; // r8
  __int64 v4; // rcx
  __int64 v5; // rcx
  int v6; // eax
  NTSTATUS v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // r8
  NTSTATUS v10; // eax
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx

  DbgTrace(1, "UevFilter.DriverEntry: Entry\n", v2);
  McGenEventRegister_EtwRegister(v4);
  GetDebugLevel(v5);
  v6 = ComPortInit();
  v7 = v6;
  if ( v6 >= 0 )
  {
    comPortInitialized = 1;
    g_pFilter = 0;
    v10 = FltRegisterFilter(DriverObject, &FilterRegistration, &g_pFilter);
    v7 = v10;
    if ( v10 >= 0 || v10 == -1071906799 && g_pFilter )
    {
      filterRegistered = 1;
      v11 = ComPortCreate();
      v7 = v11;
      if ( v11 >= 0 )
      {
        portCreated = 1;
        LOBYTE(v12) = 1;
        v13 = HookProcessNotify(v12);
        v7 = v13;
        if ( v13 >= 0 )
        {
          processNotifyHooked = 1;
          v15 = ProcessEventInitialize(v14);
          v7 = v15;
          if ( v15 >= 0 )
          {
            processEventPortCreated = 1;
            if ( (Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits & 0x10) != 0 )
              McTemplateK0_EtwWriteTransfer(v8, DriverLoaded);
          }
          else
          {
            DbgTraceFrmtErr(
              "UevFilter.DriverEntry: Failed to create process event port. status = 0x%X\n",
              (unsigned int)v15);
          }
        }
        else
        {
          DbgTraceFrmtErr("UevFilter.DriverEntry: Hook process notify failed, status = 0x%X\n", (unsigned int)v13);
        }
      }
      else
      {
        DbgTraceFrmtErr("UevFilter.DriverEntry: Communication Port creation failed, status = 0x%X\n", (unsigned int)v11);
      }
    }
    else
    {
      DbgTraceFrmtErr("UevFilter.DriverEntry: Filter registration failed, status = 0x%X\n", (unsigned int)v10);
    }
  }
  else
  {
    DbgTraceFrmtErr("UevFilter.DriverEntry: ComPort initialization failed, status = 0x%X\n", (unsigned int)v6);
  }
  if ( v7 < 0 )
    UnInitializeDriver(v8);
  DbgTrace(1, "UevFilter.DriverEntry: Exit\n", v9);
  if ( v7 < 0 )
    McGenEventUnregister_EtwUnregister(v16);
  return v7;
}

```

## disassembly

```asm
0x14000c614  mov     [rsp+arg_0], rbx
0x14000c619  push    rdi
0x14000c61a  sub     rsp, 30h
0x14000c61e  mov     rdi, rcx
0x14000c621  mov     [rsp+38h+var_18], 0C0000001h
0x14000c629  lea     rdx, aUevfilterDrive; "UevFilter.DriverEntry: Entry\n"
0x14000c630  mov     ecx, 1
0x14000c635  call    DbgTrace
0x14000c63a  call    McGenEventRegister_EtwRegister
0x14000c63f  nop
0x14000c640  call    GetDebugLevel
0x14000c645  call    ComPortInit
0x14000c64a  mov     ebx, eax
0x14000c64c  mov     [rsp+38h+var_18], eax
0x14000c650  test    eax, eax
0x14000c652  jns     short loc_14000C667
0x14000c654  lea     rcx, aUevfilterDrive_2; "UevFilter.DriverEntry: ComPort initiali"...
0x14000c65b  mov     edx, eax
0x14000c65d  call    DbgTraceFrmtErr
0x14000c662  jmp     loc_14000C73D
0x14000c667  mov     cs:comPortInitialized, 1
0x14000c66e  mov     cs:g_pFilter, 0
0x14000c679  lea     r8, g_pFilter; RetFilter
0x14000c680  lea     rdx, FilterRegistration; Registration
0x14000c687  mov     rcx, rdi; Driver
0x14000c68a  call    cs:__imp_FltRegisterFilter
0x14000c691  nop     dword ptr [rax+rax+00h]
0x14000c696  mov     ebx, eax
0x14000c698  mov     [rsp+38h+var_18], eax
0x14000c69c  test    eax, eax
0x14000c69e  jns     short loc_14000C6BA
0x14000c6a0  cmp     eax, 0C01C0011h
0x14000c6a5  jnz     short loc_14000C6B1
0x14000c6a7  cmp     cs:g_pFilter, 0
0x14000c6af  jnz     short loc_14000C6BA
0x14000c6b1  lea     rcx, aUevfilterDrive_7; "UevFilter.DriverEntry: Filter registrat"...
0x14000c6b8  jmp     short loc_14000C65B
0x14000c6ba  mov     cs:filterRegistered, 1
0x14000c6c1  call    ComPortCreate
0x14000c6c6  mov     ebx, eax
0x14000c6c8  mov     [rsp+38h+var_18], eax
0x14000c6cc  test    eax, eax
0x14000c6ce  jns     short loc_14000C6D9
0x14000c6d0  lea     rcx, aUevfilterDrive_6; "UevFilter.DriverEntry: Communication Po"...
0x14000c6d7  jmp     short loc_14000C65B
0x14000c6d9  mov     cs:portCreated, 1
0x14000c6e0  mov     cl, 1
0x14000c6e2  call    HookProcessNotify
0x14000c6e7  mov     ebx, eax
0x14000c6e9  mov     [rsp+38h+var_18], eax
0x14000c6ed  test    eax, eax
0x14000c6ef  jns     short loc_14000C6FD
0x14000c6f1  lea     rcx, aUevfilterDrive_0; "UevFilter.DriverEntry: Hook process not"...
0x14000c6f8  jmp     loc_14000C65B
0x14000c6fd  mov     cs:processNotifyHooked, 1
0x14000c704  call    ProcessEventInitialize
0x14000c709  mov     ebx, eax
0x14000c70b  mov     [rsp+38h+var_18], eax
0x14000c70f  test    eax, eax
0x14000c711  jns     short loc_14000C71F
0x14000c713  lea     rcx, aUevfilterDrive_1; "UevFilter.DriverEntry: Failed to create"...
0x14000c71a  jmp     loc_14000C65B
0x14000c71f  mov     cs:processEventPortCreated, 1
0x14000c726  mov     al, cs:Microsoft_User_Experience_Virtualization_Agent_DriverEnableBits
0x14000c72c  test    al, 10h
0x14000c72e  jz      short loc_14000C73D
0x14000c730  lea     rdx, DriverLoaded
0x14000c737  call    McTemplateK0_EtwWriteTransfer
0x14000c73c  nop
0x14000c73d  test    ebx, ebx
0x14000c73f  jns     short loc_14000C746
0x14000c741  call    UnInitializeDriver
0x14000c746  lea     rdx, aUevfilterDrive_4; "UevFilter.DriverEntry: Exit\n"
0x14000c74d  mov     ecx, 1
0x14000c752  call    DbgTrace
0x14000c757  test    ebx, ebx
0x14000c759  jns     short loc_14000C760
0x14000c75b  call    McGenEventUnregister_EtwUnregister
0x14000c760  mov     eax, ebx
0x14000c762  mov     rbx, [rsp+38h+arg_0]
0x14000c767  add     rsp, 30h
0x14000c76b  pop     rdi
0x14000c76c  retn
0x14000c774  push    rbp
0x14000c776  sub     rsp, 20h
0x14000c77a  mov     rbp, rdx
0x14000c77d  cmp     dword ptr [rbp+20h], 0
0x14000c781  jge     short loc_14000C789
0x14000c783  call    UnInitializeDriver
0x14000c788  nop
0x14000c789  add     rsp, 20h
0x14000c78d  pop     rbp
0x14000c78e  retn
```

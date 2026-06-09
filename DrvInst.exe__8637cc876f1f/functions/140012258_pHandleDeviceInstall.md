# pHandleDeviceInstall

- ea: `0x140012258`
- end: `0x14001233d`
- name: `pHandleDeviceInstall`
- size: `229`
- prototype: `__int64 __fastcall(int, __int64, wchar_t *, __int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140008e80`

## callees

- `0x140010e20`
- `0x14001170c`
- `0x14001190c`
- `0x140011a78`
- `0x140012258`
- `0x140020f3c`
- `0x140027864`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x1400122ab`
- `ntdll!DbgPrintEx` at `0x1400122ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012328`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012328`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x14001227a`
- `DEVRTL!DevRtlSetThreadLogToken` at `0x14001227a`

## string_xrefs

- `0x14001228c`: `DebugInstall`
- `0x14001229f`: `\nDRVINST.EXE: Entering debugger during PnP device installation.\nDevice instance = "%ls" ...\n\n`

## pseudocode

```c
__int64 __fastcall pHandleDeviceInstall(
        int a1,
        __int64 a2,
        wchar_t *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int a7)
{
  unsigned int v11; // esi
  void *DeviceManagerSyncEvent; // rbp
  int v13; // ebx
  int v14; // ebx
  unsigned int v15; // eax

  v11 = 0;
  DevRtlSetThreadLogToken(a6);
  if ( !(unsigned int)DevUtilsIsVolumeSnapshotDevice(a3) && (unsigned int)DoDebugBreak(L"DebugInstall") )
  {
    DbgPrintEx(
      0x23u,
      0,
      "\nDRVINST.EXE: Entering debugger during PnP device installation.\nDevice instance = \"%ls\" ...\n\n",
      a3);
    __debugbreak();
  }
  DeviceManagerSyncEvent = (void *)CreateDeviceManagerSyncEvent(a3);
  v13 = a1 - 1;
  if ( v13 )
  {
    v14 = v13 - 1;
    if ( v14 )
    {
      if ( v14 != 1 )
        goto LABEL_11;
      v15 = InstallNullDriver(a2, (_DWORD)a3, a7);
    }
    else
    {
      v15 = InstallSpecificDriver(a2, 0, a3, a4, a5, a7);
    }
  }
  else
  {
    v15 = InstallBestDriver(a2, a3, a7);
  }
  v11 = v15;
LABEL_11:
  if ( DeviceManagerSyncEvent )
    CloseHandle(DeviceManagerSyncEvent);
  return v11;
}

```

## disassembly

```asm
0x140012258  push    rbx
0x14001225a  push    rbp
0x14001225b  push    rsi
0x14001225c  push    rdi
0x14001225d  push    r14
0x14001225f  push    r15
0x140012261  sub     rsp, 38h
0x140012265  mov     ebx, ecx
0x140012267  mov     r15, r9
0x14001226a  mov     rcx, [rsp+68h+arg_28]
0x140012272  mov     rdi, r8
0x140012275  mov     r14, rdx
0x140012278  xor     esi, esi
0x14001227a  call    cs:__imp_DevRtlSetThreadLogToken
0x140012280  mov     rcx, rdi
0x140012283  call    DevUtilsIsVolumeSnapshotDevice
0x140012288  test    eax, eax
0x14001228a  jnz     short loc_1400122B2
0x14001228c  lea     rcx, aDebuginstall; "DebugInstall"
0x140012293  call    DoDebugBreak
0x140012298  test    eax, eax
0x14001229a  jz      short loc_1400122B2
0x14001229c  mov     r9, rdi
0x14001229f  lea     r8, aDrvinstExeEnte_1; "\nDRVINST.EXE: Entering debugger during"...
0x1400122a6  xor     edx, edx; Level
0x1400122a8  lea     ecx, [rsi+23h]; ComponentId
0x1400122ab  call    cs:__imp_DbgPrintEx
0x1400122b1  int     3; Trap to Debugger
0x1400122b2  mov     rcx, rdi; unsigned __int16 *
0x1400122b5  call    CreateDeviceManagerSyncEvent
0x1400122ba  mov     rbp, rax
0x1400122bd  sub     ebx, 1
0x1400122c0  jz      short loc_14001230B
0x1400122c2  sub     ebx, 1
0x1400122c5  jz      short loc_1400122E1
0x1400122c7  cmp     ebx, 1
0x1400122ca  jnz     short loc_140012320
0x1400122cc  mov     r8d, [rsp+68h+arg_30]
0x1400122d4  mov     rdx, rdi
0x1400122d7  mov     rcx, r14
0x1400122da  call    InstallNullDriver
0x1400122df  jmp     short loc_14001231E
0x1400122e1  mov     eax, [rsp+68h+arg_30]
0x1400122e8  mov     r9, r15
0x1400122eb  mov     [rsp+68h+var_40], eax
0x1400122ef  mov     r8, rdi
0x1400122f2  mov     rax, [rsp+68h+arg_20]
0x1400122fa  xor     edx, edx
0x1400122fc  mov     rcx, r14
0x1400122ff  mov     [rsp+68h+var_48], rax
0x140012304  call    InstallSpecificDriver
0x140012309  jmp     short loc_14001231E
0x14001230b  mov     r8d, [rsp+68h+arg_30]
0x140012313  mov     rdx, rdi
0x140012316  mov     rcx, r14
0x140012319  call    InstallBestDriver
0x14001231e  mov     esi, eax
0x140012320  test    rbp, rbp
0x140012323  jz      short loc_14001232E
0x140012325  mov     rcx, rbp; hObject
0x140012328  call    cs:__imp_CloseHandle
0x14001232e  mov     eax, esi
0x140012330  add     rsp, 38h
0x140012334  pop     r15
0x140012336  pop     r14
0x140012338  pop     rdi
0x140012339  pop     rsi
0x14001233a  pop     rbp
0x14001233b  pop     rbx
0x14001233c  retn
```

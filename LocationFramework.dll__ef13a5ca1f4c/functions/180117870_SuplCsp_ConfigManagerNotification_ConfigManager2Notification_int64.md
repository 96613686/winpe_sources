# SuplCsp::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x180117870`
- end: `0x1801178b2`
- name: `?ConfigManagerNotification@SuplCsp@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180117870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18011788a`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18011788a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18011789b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18011789b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801178a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801178a4`

## string_xrefs

- `0x180117880`: `SuplCspUpdatedEvent3`

## pseudocode

```c
__int64 __fastcall SuplCsp::ConfigManagerNotification(__int64 a1, int a2)
{
  HANDLE v2; // rax
  void *v3; // rbx

  if ( a2 == 6 )
  {
    v2 = OpenEventW(2u, 1, L"SuplCspUpdatedEvent3");
    v3 = v2;
    if ( v2 )
    {
      SetEvent(v2);
      CloseHandle(v3);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180117870  push    rbx
0x180117872  sub     rsp, 20h
0x180117876  cmp     edx, 6
0x180117879  jnz     short loc_1801178AA
0x18011787b  mov     edx, 1; bInheritHandle
0x180117880  lea     r8, Name; "SuplCspUpdatedEvent3"
0x180117887  lea     ecx, [rdx+1]; dwDesiredAccess
0x18011788a  call    cs:__imp_OpenEventW
0x180117890  mov     rbx, rax
0x180117893  test    rax, rax
0x180117896  jz      short loc_1801178AA
0x180117898  mov     rcx, rax; hEvent
0x18011789b  call    cs:__imp_SetEvent
0x1801178a1  mov     rcx, rbx; hObject
0x1801178a4  call    cs:__imp_CloseHandle
0x1801178aa  xor     eax, eax
0x1801178ac  add     rsp, 20h
0x1801178b0  pop     rbx
0x1801178b1  retn
```

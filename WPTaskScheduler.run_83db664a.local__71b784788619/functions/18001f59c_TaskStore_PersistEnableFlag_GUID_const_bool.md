# TaskStore::PersistEnableFlag(_GUID const &,bool)

- ea: `0x18001f59c`
- end: `0x18001f655`
- name: `?PersistEnableFlag@TaskStore@@QEAAJAEBU_GUID@@_N@Z`
- size: `185`
- prototype: `__int64 __fastcall(TaskStore *__hidden this, const struct _GUID *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180018bc4`

## callees

- `0x18000ea40`
- `0x18001f2b0`
- `0x18001f59c`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f5f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f5f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f63a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f63a`

## pseudocode

```c
__int64 __fastcall TaskStore::PersistEnableFlag(TaskStore *this, struct _GUID *a2, unsigned __int8 a3)
{
  int v3; // eax
  HKEY v4; // rcx
  int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // r8
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-28h] BYREF

  *(_DWORD *)Data = a3;
  hKey = 0;
  v3 = TaskStore::OpenKey((__int64)this, (GUIDParser *)a2, (__int64)&hKey);
  v4 = hKey;
  v5 = v3;
  if ( v3 >= 0 )
  {
    v5 = RegSetValueExW(hKey, L"Enabled", 0, 4u, Data, 4u);
    if ( (byte_180030D06 & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v6, (const EVENT_DESCRIPTOR *)RegistryWrite, v7, 1u, &v11);
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v4 = hKey;
  }
  if ( v4 )
    RegCloseKey(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001f59c  push    rbx
0x18001f59e  sub     rsp, 60h
0x18001f5a2  mov     rax, cs:__security_cookie
0x18001f5a9  xor     rax, rsp
0x18001f5ac  mov     [rsp+68h+var_18], rax
0x18001f5b1  movzx   eax, r8b
0x18001f5b5  lea     r8, [rsp+68h+hKey]
0x18001f5ba  mov     dword ptr [rsp+68h+Data], eax
0x18001f5be  mov     [rsp+68h+hKey], 0
0x18001f5c7  call    ?OpenKey@TaskStore@@AEAAJAEBU_GUID@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@Z; TaskStore::OpenKey(_GUID const &,tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f5cc  mov     rcx, [rsp+68h+hKey]; hKey
0x18001f5d1  mov     ebx, eax
0x18001f5d3  test    eax, eax
0x18001f5d5  js      short loc_18001F635
0x18001f5d7  mov     r9d, 4; dwType
0x18001f5dd  lea     rax, [rsp+68h+Data]
0x18001f5e2  mov     [rsp+68h+cbData], r9d; cbData
0x18001f5e7  lea     rdx, aEnabled; "Enabled"
0x18001f5ee  xor     r8d, r8d; Reserved
0x18001f5f1  mov     [rsp+68h+lpData], rax; lpData
0x18001f5f6  call    cs:__imp_RegSetValueExW
0x18001f5fc  test    cs:byte_180030D06, 2
0x18001f603  mov     ebx, eax
0x18001f605  jz      short loc_18001F623
0x18001f607  lea     rax, [rsp+68h+var_28]
0x18001f60c  mov     r9d, 1
0x18001f612  lea     rdx, RegistryWrite
0x18001f619  mov     [rsp+68h+lpData], rax
0x18001f61e  call    McGenEventWrite_EventWriteTransfer
0x18001f623  test    ebx, ebx
0x18001f625  jle     short loc_18001F630
0x18001f627  movzx   ebx, bx
0x18001f62a  or      ebx, 80070000h
0x18001f630  mov     rcx, [rsp+68h+hKey]; hKey
0x18001f635  test    rcx, rcx
0x18001f638  jz      short loc_18001F640
0x18001f63a  call    cs:__imp_RegCloseKey
0x18001f640  mov     eax, ebx
0x18001f642  mov     rcx, [rsp+68h+var_18]
0x18001f647  xor     rcx, rsp; StackCookie
0x18001f64a  call    __security_check_cookie
0x18001f64f  add     rsp, 60h
0x18001f653  pop     rbx
0x18001f654  retn
```

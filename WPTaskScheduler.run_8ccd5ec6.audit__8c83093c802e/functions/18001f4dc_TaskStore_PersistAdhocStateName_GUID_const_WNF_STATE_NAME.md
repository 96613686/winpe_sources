# TaskStore::PersistAdhocStateName(_GUID const &,_WNF_STATE_NAME)

- ea: `0x18001f4dc`
- end: `0x18001f595`
- name: `?PersistAdhocStateName@TaskStore@@QEAAJAEBU_GUID@@U_WNF_STATE_NAME@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(TaskStore *__hidden this, const struct _GUID *, struct _WNF_STATE_NAME)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18001af50`

## callees

- `0x18000ea40`
- `0x18001f2b0`
- `0x18001f4dc`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f536`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001f536`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f57a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f57a`

## pseudocode

```c
__int64 __fastcall TaskStore::PersistAdhocStateName(TaskStore *this, struct _GUID *a2, struct _WNF_STATE_NAME a3)
{
  int v3; // eax
  HKEY v4; // rcx
  int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // r8
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-30h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-28h] BYREF

  *(struct _WNF_STATE_NAME *)Data = a3;
  hKey = 0;
  v3 = TaskStore::OpenKey((__int64)this, (GUIDParser *)a2, (__int64)&hKey);
  v4 = hKey;
  v5 = v3;
  if ( v3 >= 0 )
  {
    v5 = RegSetValueExW(hKey, L"AdhocState", 0, 3u, Data, 8u);
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
0x18001f4dc  push    rbx
0x18001f4de  sub     rsp, 60h
0x18001f4e2  mov     rax, cs:__security_cookie
0x18001f4e9  xor     rax, rsp
0x18001f4ec  mov     [rsp+68h+var_18], rax
0x18001f4f1  mov     qword ptr [rsp+68h+Data], r8
0x18001f4f6  lea     r8, [rsp+68h+hKey]
0x18001f4fb  mov     [rsp+68h+hKey], 0
0x18001f504  call    ?OpenKey@TaskStore@@AEAAJAEBU_GUID@@AEAV?$auto_xxx@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@Z; TaskStore::OpenKey(_GUID const &,tlx::auto_xxx<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0> &)
0x18001f509  mov     rcx, [rsp+68h+hKey]; hKey
0x18001f50e  mov     ebx, eax
0x18001f510  test    eax, eax
0x18001f512  js      short loc_18001F575
0x18001f514  lea     rax, [rsp+68h+Data]
0x18001f519  mov     [rsp+68h+cbData], 8; cbData
0x18001f521  mov     r9d, 3; dwType
0x18001f527  mov     [rsp+68h+lpData], rax; lpData
0x18001f52c  xor     r8d, r8d; Reserved
0x18001f52f  lea     rdx, aAdhocstate; "AdhocState"
0x18001f536  call    cs:__imp_RegSetValueExW
0x18001f53c  test    cs:byte_180030D06, 2
0x18001f543  mov     ebx, eax
0x18001f545  jz      short loc_18001F563
0x18001f547  lea     rax, [rsp+68h+var_28]
0x18001f54c  mov     r9d, 1
0x18001f552  lea     rdx, RegistryWrite
0x18001f559  mov     [rsp+68h+lpData], rax
0x18001f55e  call    McGenEventWrite_EventWriteTransfer
0x18001f563  test    ebx, ebx
0x18001f565  jle     short loc_18001F570
0x18001f567  movzx   ebx, bx
0x18001f56a  or      ebx, 80070000h
0x18001f570  mov     rcx, [rsp+68h+hKey]; hKey
0x18001f575  test    rcx, rcx
0x18001f578  jz      short loc_18001F580
0x18001f57a  call    cs:__imp_RegCloseKey
0x18001f580  mov     eax, ebx
0x18001f582  mov     rcx, [rsp+68h+var_18]
0x18001f587  xor     rcx, rsp; StackCookie
0x18001f58a  call    __security_check_cookie
0x18001f58f  add     rsp, 60h
0x18001f593  pop     rbx
0x18001f594  retn
```

# CRegistryWatcher::Cleanup(void)

- ea: `0x180074ef4`
- end: `0x180074f54`
- name: `?Cleanup@CRegistryWatcher@@AEAAXXZ`
- size: `96`
- prototype: `void __fastcall(CRegistryWatcher *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800c334c`
- `0x18015497c`

## callees

- `0x180074ef4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180074f13`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180074f13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180074f0a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180074f0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074f40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074f40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074f29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074f29`

## pseudocode

```c
void __fastcall CRegistryWatcher::Cleanup(PTP_WAIT *this)
{
  struct _TP_WAIT *v2; // rcx
  HKEY v3; // rcx
  PTP_WAIT v4; // rcx

  v2 = *this;
  if ( v2 )
  {
    WaitForThreadpoolWaitCallbacks(v2, 1);
    CloseThreadpoolWait(*this);
    *this = 0;
  }
  v3 = (HKEY)this[3];
  if ( v3 )
  {
    RegCloseKey(v3);
    this[3] = 0;
  }
  v4 = this[4];
  if ( v4 )
  {
    CloseHandle(v4);
    this[4] = 0;
  }
}

```

## disassembly

```asm
0x180074ef4  push    rbx
0x180074ef6  sub     rsp, 20h
0x180074efa  mov     rbx, rcx
0x180074efd  mov     rcx, [rcx]; pwa
0x180074f00  test    rcx, rcx
0x180074f03  jz      short loc_180074F20
0x180074f05  mov     edx, 1; fCancelPendingCallbacks
0x180074f0a  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180074f10  mov     rcx, [rbx]; pwa
0x180074f13  call    cs:__imp_CloseThreadpoolWait
0x180074f19  mov     qword ptr [rbx], 0
0x180074f20  mov     rcx, [rbx+18h]; hKey
0x180074f24  test    rcx, rcx
0x180074f27  jz      short loc_180074F37
0x180074f29  call    cs:__imp_RegCloseKey
0x180074f2f  mov     qword ptr [rbx+18h], 0
0x180074f37  mov     rcx, [rbx+20h]; hObject
0x180074f3b  test    rcx, rcx
0x180074f3e  jz      short loc_180074F4E
0x180074f40  call    cs:__imp_CloseHandle
0x180074f46  mov     qword ptr [rbx+20h], 0
0x180074f4e  add     rsp, 20h
0x180074f52  pop     rbx
0x180074f53  retn
```

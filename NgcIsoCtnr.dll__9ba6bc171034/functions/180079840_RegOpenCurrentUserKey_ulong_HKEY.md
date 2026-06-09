# RegOpenCurrentUserKey(ulong,HKEY__ * *)

- ea: `0x180079840`
- end: `0x18007989a`
- name: `?RegOpenCurrentUserKey@@YAKKPEAPEAUHKEY__@@@Z`
- size: `90`
- prototype: `unsigned int __fastcall(unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180080fec`
- `0x18008194c`

## callees

- `0x180079840`
- `0x18007d1b8`
- `0x18007d37c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180079853`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180079853`

## string_xrefs

- `0x180079881`: `%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.`
- `0x180079868`: `RegOpenCurrentUser`
- `0x180079877`: `RegOpenCurrentUserKey`

## pseudocode

```c
__int64 __fastcall RegOpenCurrentUserKey(REGSAM a1, HKEY *a2)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx

  *a2 = 0;
  v3 = RegOpenCurrentUser(a1, a2);
  v4 = v3;
  if ( v3 )
  {
    Logger::WriteRegistryFailureEvent(v3, L"RegOpenCurrentUser", L"HKEY_CURRENT_USER");
    Logger::TraceError(
      L"%s: RegOpenCurrentUser failed with win32 error code: 0x%08x. samDesired = %lu.",
      L"RegOpenCurrentUserKey",
      v4,
      a1);
  }
  return v4;
}

```

## disassembly

```asm
0x180079840  mov     [rsp+arg_0], rbx
0x180079845  push    rdi
0x180079846  sub     rsp, 20h
0x18007984a  mov     edi, ecx
0x18007984c  mov     qword ptr [rdx], 0
0x180079853  call    cs:__imp_RegOpenCurrentUser
0x180079859  mov     ebx, eax
0x18007985b  test    eax, eax
0x18007985d  jz      short loc_18007988D
0x18007985f  lea     r8, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180079866  mov     ecx, eax; unsigned int
0x180079868  lea     rdx, aRegopencurrent; "RegOpenCurrentUser"
0x18007986f  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180079874  mov     r9d, edi
0x180079877  lea     rdx, aRegopencurrent_0; "RegOpenCurrentUserKey"
0x18007987e  mov     r8d, ebx
0x180079881  lea     rcx, aSRegopencurren; "%s: RegOpenCurrentUser failed with win3"...
0x180079888  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007988d  mov     eax, ebx
0x18007988f  mov     rbx, [rsp+28h+arg_0]
0x180079894  add     rsp, 20h
0x180079898  pop     rdi
0x180079899  retn
```

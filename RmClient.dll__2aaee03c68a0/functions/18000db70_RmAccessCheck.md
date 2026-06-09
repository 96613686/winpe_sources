# RmAccessCheck

- ea: `0x18000db70`
- end: `0x18000dbf9`
- name: `RmAccessCheck`
- size: `137`
- prototype: `__int64 __fastcall(unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000db70`
- `0x18000dc00`
- `0x180013314`

## import_xrefs

- `ntdll!RtlEnterCriticalSection` at `0x18000db8a`
- `ntdll!RtlEnterCriticalSection` at `0x18000db8a`
- `ntdll!RtlLeaveCriticalSection` at `0x18000dba3`
- `ntdll!RtlLeaveCriticalSection` at `0x18000dbd8`
- `ntdll!RtlLeaveCriticalSection` at `0x18000dba3`
- `ntdll!RtlLeaveCriticalSection` at `0x18000dbd8`

## pseudocode

```c
__int64 __fastcall RmAccessCheck(unsigned int a1, unsigned int a2)
{
  __int64 v4; // rbx
  int ResourceManagerProxy; // ebx

  RtlEnterCriticalSection(&s_csProxy);
  v4 = qword_18002ED78;
  if ( qword_18002ED78 )
    goto LABEL_2;
  ResourceManagerProxy = CreateResourceManagerProxy();
  if ( ResourceManagerProxy >= 0 )
  {
    v4 = qword_18002ED78;
LABEL_2:
    RtlLeaveCriticalSection(&s_csProxy);
    return ResourceManagerProxy::RmAccessCheck(v4, a1, a2);
  }
  RtlLeaveCriticalSection(&s_csProxy);
  return (unsigned int)ResourceManagerProxy;
}

```

## disassembly

```asm
0x18000db70  mov     [rsp+arg_0], rbx
0x18000db75  mov     [rsp+arg_8], rsi
0x18000db7a  push    rdi
0x18000db7b  sub     rsp, 20h
0x18000db7f  mov     esi, ecx
0x18000db81  mov     edi, edx
0x18000db83  lea     rcx, ?s_csProxy@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000db8a  call    cs:__imp_RtlEnterCriticalSection
0x18000db90  mov     rbx, cs:qword_18002ED78
0x18000db97  test    rbx, rbx
0x18000db9a  jz      short loc_18000DBC6
0x18000db9c  lea     rcx, ?s_csProxy@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000dba3  call    cs:__imp_RtlLeaveCriticalSection
0x18000dba9  mov     r8d, edi
0x18000dbac  mov     edx, esi
0x18000dbae  mov     rcx, rbx
0x18000dbb1  call    ?RmAccessCheck@ResourceManagerProxy@@QEAAJW4RmResourceType@@K@Z; ResourceManagerProxy::RmAccessCheck(RmResourceType,ulong)
0x18000dbb6  mov     rbx, [rsp+28h+arg_0]
0x18000dbbb  mov     rsi, [rsp+28h+arg_8]
0x18000dbc0  add     rsp, 20h
0x18000dbc4  pop     rdi
0x18000dbc5  retn
0x18000dbc6  call    CreateResourceManagerProxy
0x18000dbcb  mov     ebx, eax
0x18000dbcd  test    eax, eax
0x18000dbcf  jns     short loc_18000DBF0
0x18000dbd1  lea     rcx, ?s_csProxy@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000dbd8  call    cs:__imp_RtlLeaveCriticalSection
0x18000dbde  mov     rsi, [rsp+28h+arg_8]
0x18000dbe3  mov     eax, ebx
0x18000dbe5  mov     rbx, [rsp+28h+arg_0]
0x18000dbea  add     rsp, 20h
0x18000dbee  pop     rdi
0x18000dbef  retn
0x18000dbf0  mov     rbx, cs:qword_18002ED78
0x18000dbf7  jmp     short loc_18000DB9C
```

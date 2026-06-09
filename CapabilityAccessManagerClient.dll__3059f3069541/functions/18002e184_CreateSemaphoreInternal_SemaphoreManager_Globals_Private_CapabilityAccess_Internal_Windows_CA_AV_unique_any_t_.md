# ?CreateSemaphoreInternal@SemaphoreManager@Globals@Private@CapabilityAccess@Internal@Windows@@CA?AV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@I@Z

- ea: `0x18002e184`
- end: `0x18002e1c3`
- name: `?CreateSemaphoreInternal@SemaphoreManager@Globals@Private@CapabilityAccess@Internal@Windows@@CA?AV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@I@Z`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002eb34`

## callees

- `0x180023690`
- `0x18002e184`

## import_xrefs

- `api-ms-win-core-synch-ansi-l1-1-0!CreateSemaphoreA` at `0x18002e195`
- `api-ms-win-core-synch-ansi-l1-1-0!CreateSemaphoreA` at `0x18002e195`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::Globals::SemaphoreManager::CreateSemaphoreInternal(
        _QWORD *a1,
        LONG a2)
{
  HANDLE SemaphoreA; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  SemaphoreA = CreateSemaphoreA(0, a2, a2, 0);
  if ( !SemaphoreA )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      v4);
  *a1 = SemaphoreA;
  return a1;
}

```

## disassembly

```asm
0x18002e184  push    rbx
0x18002e186  sub     rsp, 30h
0x18002e18a  mov     rbx, rcx
0x18002e18d  xor     r9d, r9d; lpName
0x18002e190  xor     ecx, ecx; lpSemaphoreAttributes
0x18002e192  mov     r8d, edx; lMaximumCount
0x18002e195  call    cs:__imp_CreateSemaphoreA
0x18002e19b  test    rax, rax
0x18002e19e  jz      short loc_18002E1AC
0x18002e1a0  mov     [rbx], rax
0x18002e1a3  mov     rax, rbx
0x18002e1a6  add     rsp, 30h
0x18002e1aa  pop     rbx
0x18002e1ab  retn
0x18002e1ac  mov     rcx, [rsp+38h]; this
0x18002e1b1  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\core\\sync"...
0x18002e1b8  mov     edx, 1F8h; void *
0x18002e1bd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

# wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&AppXFreeMemory(void *)>>::~unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&AppXFreeMemory(void *)>>(void)

- ea: `0x14000a0ec`
- end: `0x14000a10d`
- name: `??1?$unique_ptr@$$BY0A@U_SID_AND_ATTRIBUTES@@U?$function_deleter@P6AXPEAX@Z$1?AppXFreeMemory@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140011543`

## callees

- `0x14000a0ec`

## import_xrefs

- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x14000a102`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x14000a102`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>::~unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>(
        __int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  *a1 = 0;
  if ( result )
    return AppXFreeMemory(result);
  return result;
}

```

## disassembly

```asm
0x14000a0ec  sub     rsp, 28h
0x14000a0f0  mov     rax, [rcx]
0x14000a0f3  mov     qword ptr [rcx], 0
0x14000a0fa  test    rax, rax
0x14000a0fd  jz      short loc_14000A108
0x14000a0ff  mov     rcx, rax
0x14000a102  call    cs:__imp_AppXFreeMemory
0x14000a108  add     rsp, 28h
0x14000a10c  retn
```

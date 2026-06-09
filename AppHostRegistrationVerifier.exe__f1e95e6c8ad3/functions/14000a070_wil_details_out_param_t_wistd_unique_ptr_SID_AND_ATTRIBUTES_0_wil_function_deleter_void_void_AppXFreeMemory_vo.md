# wil::details::out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&AppXFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&AppXFreeMemory(void *)>>>(void)

- ea: `0x14000a070`
- end: `0x14000a09a`
- name: `??1?$out_param_t@V?$unique_ptr@$$BY0A@U_SID_AND_ATTRIBUTES@@U?$function_deleter@P6AXPEAX@Z$1?AppXFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `__int64 __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000afec`

## callees

- `0x14000a070`

## import_xrefs

- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x14000a08f`
- `api-ms-win-appmodel-identity-l1-2-0!AppXFreeMemory` at `0x14000a08f`

## pseudocode

```c
__int64 __fastcall wil::details::out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_SID_AND_ATTRIBUTES [0],wil::function_deleter<void (*)(void *),&void AppXFreeMemory(void *)>>>(
        __int64 **a1)
{
  __int64 result; // rax
  __int64 v2; // r8

  if ( *((_BYTE *)a1 + 16) )
  {
    result = (__int64)a1[1];
    v2 = **a1;
    **a1 = result;
    if ( v2 )
      return AppXFreeMemory(v2);
  }
  return result;
}

```

## disassembly

```asm
0x14000a070  sub     rsp, 28h
0x14000a074  cmp     byte ptr [rcx+10h], 0
0x14000a078  jz      short loc_14000A095
0x14000a07a  mov     rdx, [rcx]
0x14000a07d  mov     rax, [rcx+8]
0x14000a081  mov     r8, [rdx]
0x14000a084  mov     [rdx], rax
0x14000a087  test    r8, r8
0x14000a08a  jz      short loc_14000A095
0x14000a08c  mov     rcx, r8
0x14000a08f  call    cs:__imp_AppXFreeMemory
0x14000a095  add     rsp, 28h
0x14000a099  retn
```

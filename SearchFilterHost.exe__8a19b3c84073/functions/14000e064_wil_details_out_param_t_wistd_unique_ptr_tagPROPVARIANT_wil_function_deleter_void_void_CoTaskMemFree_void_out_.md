# wil::details::out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)

- ea: `0x14000e064`
- end: `0x14000e08e`
- name: `??1?$out_param_t@V?$unique_ptr@UtagPROPVARIANT@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000e7ec`
- `0x14001e68c`
- `0x14004b992`
- `0x14004bf8f`

## callees

- `0x14000e064`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000e083`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000e083`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<tagPROPVARIANT,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        __int64 a1)
{
  void *v1; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
      CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x14000e064  sub     rsp, 28h
0x14000e068  cmp     byte ptr [rcx+10h], 0
0x14000e06c  jz      short loc_14000E089
0x14000e06e  mov     rdx, [rcx]
0x14000e071  mov     rax, [rcx+8]
0x14000e075  mov     r8, [rdx]
0x14000e078  mov     [rdx], rax
0x14000e07b  test    r8, r8
0x14000e07e  jz      short loc_14000E089
0x14000e080  mov     rcx, r8; pv
0x14000e083  call    cs:__imp_CoTaskMemFree
0x14000e089  add     rsp, 28h
0x14000e08d  retn
```

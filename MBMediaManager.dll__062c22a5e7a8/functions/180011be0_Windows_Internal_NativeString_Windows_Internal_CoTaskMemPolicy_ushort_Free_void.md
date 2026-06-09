# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x180011be0`
- end: `0x180011c0e`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `46`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e538`
- `0x1800116e0`
- `0x18001d918`
- `0x18001dc70`
- `0x180020ec0`
- `0x1800244b0`
- `0x180026380`
- `0x18004c768`

## callees

- `0x180011be0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011bf1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011bf1`

## pseudocode

```c
__int64 __fastcall Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(
        __int64 a1)
{
  void *v2; // rcx
  __int64 result; // rax

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    result = 0;
    *(_QWORD *)a1 = 0;
  }
  else
  {
    result = 0;
  }
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x180011be0  push    rbx
0x180011be2  sub     rsp, 20h
0x180011be6  mov     rbx, rcx
0x180011be9  mov     rcx, [rcx]; pv
0x180011bec  test    rcx, rcx
0x180011bef  jz      short loc_180011C0A
0x180011bf1  call    cs:__imp_CoTaskMemFree
0x180011bf7  xor     eax, eax
0x180011bf9  mov     [rbx], rax
0x180011bfc  mov     [rbx+10h], rax
0x180011c00  mov     [rbx+8], rax
0x180011c04  add     rsp, 20h
0x180011c08  pop     rbx
0x180011c09  retn
0x180011c0a  xor     eax, eax
0x180011c0c  jmp     short loc_180011BFC
```

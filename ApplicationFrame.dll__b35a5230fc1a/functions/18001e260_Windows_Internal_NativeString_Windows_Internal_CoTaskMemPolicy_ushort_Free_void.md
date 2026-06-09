# Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)

- ea: `0x18001e260`
- end: `0x18001e28e`
- name: `?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ`
- size: `46`
- prototype: ``
- caller_count: `29`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004c4c`
- `0x18000e1d0`
- `0x1800111d0`
- `0x18001dddc`
- `0x18001df90`
- `0x18001e204`
- `0x18001e5d0`
- `0x1800206e8`
- `0x1800243a4`
- `0x1800249d8`
- `0x180031080`
- `0x180037680`
- `0x180039990`
- `0x18003e5fc`
- `0x18003fd44`
- `0x1800419f8`
- `0x18005e99c`
- `0x18005ef4c`
- `0x180060560`
- `0x180062af4`
- `0x180063684`
- `0x180068c24`
- `0x180069364`
- `0x18006b3f8`
- `0x18006b984`
- `0x18006ba70`
- `0x18006bd5c`
- `0x18006bfec`
- `0x18006c268`

## callees

- `0x18001e260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e271`

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
0x18001e260  push    rbx
0x18001e262  sub     rsp, 20h
0x18001e266  mov     rbx, rcx
0x18001e269  mov     rcx, [rcx]; pv
0x18001e26c  test    rcx, rcx
0x18001e26f  jz      short loc_18001E28A
0x18001e271  call    cs:__imp_CoTaskMemFree
0x18001e277  xor     eax, eax
0x18001e279  mov     [rbx], rax
0x18001e27c  mov     [rbx+10h], rax
0x18001e280  mov     [rbx+8], rax
0x18001e284  add     rsp, 20h
0x18001e288  pop     rbx
0x18001e289  retn
0x18001e28a  xor     eax, eax
0x18001e28c  jmp     short loc_18001E27C
```

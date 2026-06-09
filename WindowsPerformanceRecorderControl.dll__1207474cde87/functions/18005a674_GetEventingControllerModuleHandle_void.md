# GetEventingControllerModuleHandle(void)

- ea: `0x18005a674`
- end: `0x18005a69d`
- name: `?GetEventingControllerModuleHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `41`
- prototype: `HINSTANCE(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016f08`
- `0x18005aaf8`

## callees

- `0x18005a674`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18005a68b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18005a68b`

## string_xrefs

- `0x18005a684`: `api-ms-win-eventing-controller-l1-1-0.dll`

## pseudocode

```c
HINSTANCE GetEventingControllerModuleHandle(void)
{
  HINSTANCE result; // rax

  result = (HINSTANCE)qword_1800BE6C8;
  if ( !qword_1800BE6C8 )
  {
    result = GetModuleHandleW(L"api-ms-win-eventing-controller-l1-1-0.dll");
    qword_1800BE6C8 = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x18005a674  sub     rsp, 28h
0x18005a678  mov     rax, cs:qword_1800BE6C8
0x18005a67f  test    rax, rax
0x18005a682  jnz     short loc_18005A698
0x18005a684  lea     rcx, aApiMsWinEventi_4; "api-ms-win-eventing-controller-l1-1-0.d"...
0x18005a68b  call    cs:__imp_GetModuleHandleW
0x18005a691  mov     cs:qword_1800BE6C8, rax
0x18005a698  add     rsp, 28h
0x18005a69c  retn
```

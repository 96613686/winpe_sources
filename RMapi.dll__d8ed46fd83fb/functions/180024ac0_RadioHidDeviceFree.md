# RadioHidDeviceFree

- ea: `0x180024ac0`
- end: `0x180024af8`
- name: `RadioHidDeviceFree`
- size: `56`
- prototype: `int __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x180009500`
- `0x18000970c`

## callees

- `0x180024ac0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024aec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024aec`
- `HID!HidD_FreePreparsedData` at `0x180024ad9`
- `HID!HidD_FreePreparsedData` at `0x180024ad9`

## pseudocode

```c
int __fastcall RadioHidDeviceFree(__int64 a1)
{
  struct _HIDP_PREPARSED_DATA *v2; // rcx
  unsigned __int64 v3; // rax

  if ( a1 )
  {
    v2 = *(struct _HIDP_PREPARSED_DATA **)(a1 + 528);
    if ( v2 )
      HidD_FreePreparsedData(v2);
    v3 = *(_QWORD *)a1 - 1LL;
    if ( v3 <= 0xFFFFFFFFFFFFFFFDuLL )
      LODWORD(v3) = CloseHandle(*(HANDLE *)a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180024ac0  test    rcx, rcx
0x180024ac3  jz      short locret_180024AF7
0x180024ac5  push    rbx
0x180024ac6  sub     rsp, 20h
0x180024aca  mov     rbx, rcx
0x180024acd  mov     rcx, [rcx+210h]; PreparsedData
0x180024ad4  test    rcx, rcx
0x180024ad7  jz      short loc_180024ADF
0x180024ad9  call    cs:__imp_HidD_FreePreparsedData
0x180024adf  mov     rcx, [rbx]; hObject
0x180024ae2  lea     rax, [rcx-1]
0x180024ae6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024aea  ja      short loc_180024AF2
0x180024aec  call    cs:__imp_CloseHandle
0x180024af2  add     rsp, 20h
0x180024af6  pop     rbx
0x180024af7  retn
```

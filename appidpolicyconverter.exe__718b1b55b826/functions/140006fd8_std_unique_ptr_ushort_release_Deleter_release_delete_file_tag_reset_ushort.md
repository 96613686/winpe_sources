# std::unique_ptr<ushort,release::Deleter<release::delete_file_tag>>::reset(ushort *)

- ea: `0x140006fd8`
- end: `0x140007009`
- name: `?reset@?$unique_ptr@GU?$Deleter@Udelete_file_tag@release@@@release@@@std@@QEAAXPEAG@Z`
- size: `49`
- prototype: `BOOL __fastcall(const WCHAR **, const WCHAR *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140006154`
- `0x1400064f8`

## callees

- `0x140006fd8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140006ff5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140006ff5`

## pseudocode

```c
BOOL __fastcall std::unique_ptr<unsigned short,release::Deleter<release::delete_file_tag>>::reset(
        const WCHAR **a1,
        const WCHAR *a2)
{
  const WCHAR *v4; // rcx
  BOOL result; // eax

  v4 = *a1;
  if ( a2 != v4 )
  {
    if ( v4 )
      result = DeleteFileW(v4);
    *a1 = a2;
  }
  return result;
}

```

## disassembly

```asm
0x140006fd8  mov     [rsp+arg_0], rbx
0x140006fdd  push    rdi
0x140006fde  sub     rsp, 20h
0x140006fe2  mov     rbx, rdx
0x140006fe5  mov     rdi, rcx
0x140006fe8  mov     rcx, [rcx]; lpFileName
0x140006feb  cmp     rdx, rcx
0x140006fee  jz      short loc_140006FFE
0x140006ff0  test    rcx, rcx
0x140006ff3  jz      short loc_140006FFB
0x140006ff5  call    cs:__imp_DeleteFileW
0x140006ffb  mov     [rdi], rbx
0x140006ffe  mov     rbx, [rsp+28h+arg_0]
0x140007003  add     rsp, 20h
0x140007007  pop     rdi
0x140007008  retn
```

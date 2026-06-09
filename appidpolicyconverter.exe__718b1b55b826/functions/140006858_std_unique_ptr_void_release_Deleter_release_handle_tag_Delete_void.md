# std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(void)

- ea: `0x140006858`
- end: `0x140006878`
- name: `?_Delete@?$unique_ptr@PEAXU?$Deleter@Uhandle_tag@release@@@release@@@std@@AEAAXXZ`
- size: `32`
- prototype: `BOOL __fastcall(HANDLE **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400027d8`
- `0x140006154`
- `0x1400064f8`
- `0x140007010`

## callees

- `0x140006858`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000686d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000686d`

## pseudocode

```c
BOOL __fastcall std::unique_ptr<void *,release::Deleter<release::handle_tag>>::_Delete(HANDLE **a1)
{
  HANDLE *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
  {
    if ( *v1 != (HANDLE)-1LL )
      return CloseHandle(*v1);
  }
  return result;
}

```

## disassembly

```asm
0x140006858  sub     rsp, 28h
0x14000685c  mov     rcx, [rcx]
0x14000685f  test    rcx, rcx
0x140006862  jz      short loc_140006873
0x140006864  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x140006868  jz      short loc_140006873
0x14000686a  mov     rcx, [rcx]; hObject
0x14000686d  call    cs:__imp_CloseHandle
0x140006873  add     rsp, 28h
0x140006877  retn
```

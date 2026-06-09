# ??1?$unique_ptr@U_ACL@@U?$generic_delete@U_ACL@@U?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ

- ea: `0x140004a94`
- end: `0x140004aab`
- name: `??1?$unique_ptr@U_ACL@@U?$generic_delete@U_ACL@@U?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14001cca7`

## callees

- `0x140004a94`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004aa0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004aa0`

## pseudocode

```c
HLOCAL __fastcall __1__unique_ptr_U_ACL__U__generic_delete_U_ACL__U__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(
        void **a1)
{
  void *v1; // rcx
  HLOCAL result; // rax

  v1 = *a1;
  if ( v1 )
    return LocalFree(v1);
  return result;
}

```

## disassembly

```asm
0x140004a94  sub     rsp, 28h
0x140004a98  mov     rcx, [rcx]; hMem
0x140004a9b  test    rcx, rcx
0x140004a9e  jz      short loc_140004AA6
0x140004aa0  call    cs:__imp_LocalFree
0x140004aa6  add     rsp, 28h
0x140004aaa  retn
```

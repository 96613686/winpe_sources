# PMSIHANDLE::~PMSIHANDLE(void)

- ea: `0x18004c810`
- end: `0x18004c825`
- name: `??1PMSIHANDLE@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(PMSIHANDLE *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180068e67`
- `0x180068e79`
- `0x180068e8b`

## callees

- `0x18004c810`

## import_xrefs

- `MSI!MsiCloseHandle` at `0x18004c81a`
- `MSI!MsiCloseHandle` at `0x18004c81a`

## pseudocode

```c
void __fastcall PMSIHANDLE::~PMSIHANDLE(MSIHANDLE *this)
{
  MSIHANDLE v1; // ecx

  v1 = *this;
  if ( v1 )
    MsiCloseHandle(v1);
}

```

## disassembly

```asm
0x18004c810  sub     rsp, 28h
0x18004c814  mov     ecx, [rcx]; hAny
0x18004c816  test    ecx, ecx
0x18004c818  jz      short loc_18004C820
0x18004c81a  call    cs:__imp_MsiCloseHandle
0x18004c820  add     rsp, 28h
0x18004c824  retn
```

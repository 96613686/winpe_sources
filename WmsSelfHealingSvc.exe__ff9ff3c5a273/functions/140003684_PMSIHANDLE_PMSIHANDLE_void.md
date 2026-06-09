# PMSIHANDLE::~PMSIHANDLE(void)

- ea: `0x140003684`
- end: `0x140003699`
- name: `??1PMSIHANDLE@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(MSIHANDLE *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000afe7`
- `0x14000aff9`

## callees

- `0x140003684`

## import_xrefs

- `msi!__imp_MsiCloseHandle` at `0x14000368e`
- `msi!__imp_MsiCloseHandle` at `0x14000368e`

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
0x140003684  sub     rsp, 28h
0x140003688  mov     ecx, [rcx]; hAny
0x14000368a  test    ecx, ecx
0x14000368c  jz      short loc_140003694
0x14000368e  call    cs:__imp_MsiCloseHandle
0x140003694  add     rsp, 28h
0x140003698  retn
```

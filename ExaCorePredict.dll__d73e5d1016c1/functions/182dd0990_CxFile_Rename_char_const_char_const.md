# CxFile::Rename(char const *,char const *)

- ea: `0x182dd0990`
- end: `0x182dd09be`
- name: `?Rename@CxFile@@SAXPEBD0@Z`
- size: `46`
- prototype: `void __fastcall(const char *, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x182dce0f0`
- `0x182dd0990`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x182dd09a3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x182dd09a3`
- `api-ms-win-crt-filesystem-l1-1-0!rename` at `0x182dd0999`
- `api-ms-win-crt-filesystem-l1-1-0!rename` at `0x182dd0999`

## pseudocode

```c
void __fastcall CxFile::Rename(const char *a1, const char *a2)
{
  int *v3; // rax

  if ( rename(a1, a2) )
  {
    v3 = _errno();
    CxFileException::ThrowOsError(*v3, a1);
  }
}

```

## disassembly

```asm
0x182dd0990  push    rbx
0x182dd0992  sub     rsp, 20h
0x182dd0996  mov     rbx, rcx
0x182dd0999  call    cs:__imp_rename
0x182dd099f  test    eax, eax
0x182dd09a1  jz      short loc_182DD09B8
0x182dd09a3  call    cs:__imp__errno
0x182dd09a9  mov     rdx, rbx; char *
0x182dd09ac  mov     ecx, [rax]; int
0x182dd09ae  add     rsp, 20h
0x182dd09b2  pop     rbx
0x182dd09b3  jmp     ?ThrowOsError@CxFileException@@SAXJPEBD@Z; CxFileException::ThrowOsError(long,char const *)
0x182dd09b8  add     rsp, 20h
0x182dd09bc  pop     rbx
0x182dd09bd  retn
```

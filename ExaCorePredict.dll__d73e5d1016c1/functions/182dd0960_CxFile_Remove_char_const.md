# CxFile::Remove(char const *)

- ea: `0x182dd0960`
- end: `0x182dd098e`
- name: `?Remove@CxFile@@SAXPEBD@Z`
- size: `46`
- prototype: `void __fastcall(const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x182dce0f0`
- `0x182dd0960`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x182dd0973`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x182dd0973`
- `api-ms-win-crt-filesystem-l1-1-0!remove` at `0x182dd0969`
- `api-ms-win-crt-filesystem-l1-1-0!remove` at `0x182dd0969`

## pseudocode

```c
void __fastcall CxFile::Remove(const char *a1)
{
  int *v2; // rax

  if ( remove(a1) )
  {
    v2 = _errno();
    CxFileException::ThrowOsError(*v2, a1);
  }
}

```

## disassembly

```asm
0x182dd0960  push    rbx
0x182dd0962  sub     rsp, 20h
0x182dd0966  mov     rbx, rcx
0x182dd0969  call    cs:__imp_remove
0x182dd096f  test    eax, eax
0x182dd0971  jz      short loc_182DD0988
0x182dd0973  call    cs:__imp__errno
0x182dd0979  mov     rdx, rbx; char *
0x182dd097c  mov     ecx, [rax]; int
0x182dd097e  add     rsp, 20h
0x182dd0982  pop     rbx
0x182dd0983  jmp     ?ThrowOsError@CxFileException@@SAXJPEBD@Z; CxFileException::ThrowOsError(long,char const *)
0x182dd0988  add     rsp, 20h
0x182dd098c  pop     rbx
0x182dd098d  retn
```

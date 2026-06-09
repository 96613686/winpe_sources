# ResumeImpersonate(void *)

- ea: `0x180011f84`
- end: `0x180011fac`
- name: `?ResumeImpersonate@@YAXPEAX@Z`
- size: `40`
- prototype: `void __fastcall(HANDLE Token)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180011cd4`
- `0x180011d30`
- `0x180012750`
- `0x180014840`
- `0x180058ce8`
- `0x1800862d4`

## callees

- `0x180011f84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011f97`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011f97`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011fa5`

## pseudocode

```c
void __fastcall ResumeImpersonate(HANDLE Token)
{
  if ( Token )
  {
    SetThreadToken(0, Token);
    CloseHandle(Token);
  }
}

```

## disassembly

```asm
0x180011f84  test    rcx, rcx
0x180011f87  jnz     short loc_180011F8A
0x180011f89  retn
0x180011f8a  push    rbx
0x180011f8b  sub     rsp, 20h
0x180011f8f  mov     rbx, rcx
0x180011f92  mov     rdx, rcx; Token
0x180011f95  xor     ecx, ecx; Thread
0x180011f97  call    cs:__imp_SetThreadToken
0x180011f9d  mov     rcx, rbx
0x180011fa0  add     rsp, 20h
0x180011fa4  pop     rbx
0x180011fa5  jmp     cs:__imp_CloseHandle
```

# CreateFileWForAccessFailures

- ea: `0x18004ff64`
- end: `0x180050011`
- name: `CreateFileWForAccessFailures`
- size: `173`
- prototype: `HANDLE __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180037f94`

## callees

- `0x18004ff64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ff9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ff9a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004ffba`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004ffba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ffe7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004ffe7`

## pseudocode

```c
HANDLE __fastcall CreateFileWForAccessFailures(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes)
{
  __int64 v6; // rdi
  HANDLE i; // rax
  HANDLE v12; // rbx

  v6 = 0;
  for ( i = CreateFileW(
              lpFileName,
              dwDesiredAccess,
              dwShareMode,
              lpSecurityAttributes,
              dwCreationDisposition,
              dwFlagsAndAttributes,
              0);
        ;
        i = CreateFileW(
              lpFileName,
              dwDesiredAccess,
              dwShareMode,
              lpSecurityAttributes,
              dwCreationDisposition,
              dwFlagsAndAttributes,
              0) )
  {
    v12 = i;
    if ( i != (HANDLE)-1LL || GetLastError() != 32 || (unsigned int)v6 >= 6 )
      break;
    Sleep(dword_1800DBB78[v6]);
    v6 = (unsigned int)(v6 + 1);
  }
  return v12;
}

```

## disassembly

```asm
0x18004ff64  push    rbx
0x18004ff66  push    rbp
0x18004ff67  push    rsi
0x18004ff68  push    rdi
0x18004ff69  push    r12
0x18004ff6b  push    r13
0x18004ff6d  push    r14
0x18004ff6f  push    r15
0x18004ff71  sub     rsp, 48h
0x18004ff75  mov     r12d, [rsp+88h+arg_28]
0x18004ff7d  xor     edi, edi
0x18004ff7f  mov     r13d, [rsp+88h+arg_20]
0x18004ff87  mov     rsi, r9
0x18004ff8a  mov     [rsp+88h+hTemplateFile], rdi
0x18004ff8f  mov     ebp, r8d
0x18004ff92  mov     r14d, edx
0x18004ff95  mov     r15, rcx
0x18004ff98  jmp     short loc_18004FFDD
0x18004ff9a  call    cs:__imp_GetLastError
0x18004ffa1  nop     dword ptr [rax+rax+00h]
0x18004ffa6  cmp     eax, 20h ; ' '
0x18004ffa9  jnz     short loc_18004FFFC
0x18004ffab  cmp     edi, 6
0x18004ffae  jnb     short loc_18004FFFC
0x18004ffb0  lea     rax, dword_1800DBB78
0x18004ffb7  mov     ecx, [rax+rdi*4]; dwMilliseconds
0x18004ffba  call    cs:__imp_Sleep
0x18004ffc1  nop     dword ptr [rax+rax+00h]
0x18004ffc6  inc     edi
0x18004ffc8  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18004ffd1  mov     r9, rsi; lpSecurityAttributes
0x18004ffd4  mov     r8d, ebp; dwShareMode
0x18004ffd7  mov     edx, r14d; dwDesiredAccess
0x18004ffda  mov     rcx, r15; lpFileName
0x18004ffdd  mov     [rsp+88h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18004ffe2  mov     [rsp+88h+dwCreationDisposition], r13d; dwCreationDisposition
0x18004ffe7  call    cs:__imp_CreateFileW
0x18004ffee  nop     dword ptr [rax+rax+00h]
0x18004fff3  mov     rbx, rax
0x18004fff6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004fffa  jz      short loc_18004FF9A
0x18004fffc  mov     rax, rbx
0x18004ffff  add     rsp, 48h
0x180050003  pop     r15
0x180050005  pop     r14
0x180050007  pop     r13
0x180050009  pop     r12
0x18005000b  pop     rdi
0x18005000c  pop     rsi
0x18005000d  pop     rbp
0x18005000e  pop     rbx
0x18005000f  retn
```

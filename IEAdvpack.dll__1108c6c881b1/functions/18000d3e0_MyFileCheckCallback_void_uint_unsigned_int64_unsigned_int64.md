# MyFileCheckCallback(void *,uint,unsigned __int64,unsigned __int64)

- ea: `0x18000d3e0`
- end: `0x18000d487`
- name: `?MyFileCheckCallback@@YAIPEAXI_K1@Z`
- size: `167`
- prototype: `UINT __fastcall(void *, UINT, UINT_PTR, UINT_PTR)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180001e40`
- `0x18000d3e0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000d457`
- `KERNEL32!CreateFileW` at `0x18000d457`
- `KERNEL32!CloseHandle` at `0x18000d474`
- `KERNEL32!CloseHandle` at `0x18000d474`
- `SETUPAPI!SetupDefaultQueueCallbackW` at `0x18000d3fe`
- `SETUPAPI!SetupDefaultQueueCallbackW` at `0x18000d3fe`
- `SHLWAPI!PathFileExistsW` at `0x18000d428`
- `SHLWAPI!PathFileExistsW` at `0x18000d428`

## pseudocode

```c
UINT __fastcall MyFileCheckCallback(void *a1, UINT a2, UINT_PTR a3, UINT_PTR a4)
{
  LPCWSTR *v5; // rax
  int v6; // ebx
  const WCHAR *v7; // rdi
  HANDLE FileW; // rax

  if ( a2 == 5 || a2 == 8 || a2 == 11 )
  {
    v5 = (LPCWSTR *)(a3 + 8);
    v6 = 2;
    if ( a2 != 8 )
      v5 = (LPCWSTR *)a3;
    v7 = *v5;
    if ( PathFileExistsW(*v5) )
    {
      FileW = CreateFileW(v7, 0x40000000u, 3u, 0, 3u, 0x80u, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        dword_180025CA0 = 0;
        return 0;
      }
      else
      {
        CloseHandle(FileW);
      }
    }
    return v6;
  }
  else if ( a2 == 14 )
  {
    return MyFileQueueCallback2(a1, 0xEu, a3, a4);
  }
  else
  {
    return SetupDefaultQueueCallbackW(a1, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x18000d3e0  mov     [rsp+arg_0], rbx
0x18000d3e5  push    rdi
0x18000d3e6  sub     rsp, 40h
0x18000d3ea  cmp     edx, 5
0x18000d3ed  jz      short loc_18000D412
0x18000d3ef  cmp     edx, 8
0x18000d3f2  jz      short loc_18000D412
0x18000d3f4  cmp     edx, 0Bh
0x18000d3f7  jz      short loc_18000D412
0x18000d3f9  cmp     edx, 0Eh
0x18000d3fc  jz      short loc_18000D406
0x18000d3fe  call    cs:__imp_SetupDefaultQueueCallbackW
0x18000d404  jmp     short loc_18000D47C
0x18000d406  mov     edx, 0Eh; Notification
0x18000d40b  call    ?MyFileQueueCallback2@@YAIPEAXI_K1@Z; MyFileQueueCallback2(void *,uint,unsigned __int64,unsigned __int64)
0x18000d410  jmp     short loc_18000D47C
0x18000d412  cmp     edx, 8
0x18000d415  lea     rax, [r8+8]
0x18000d419  mov     ebx, 2
0x18000d41e  cmovnz  rax, r8
0x18000d422  mov     rdi, [rax]
0x18000d425  mov     rcx, rdi; pszPath
0x18000d428  call    cs:__imp_PathFileExistsW
0x18000d42e  test    eax, eax
0x18000d430  jz      short loc_18000D47A
0x18000d432  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000d43b  lea     r8d, [rbx+1]; dwShareMode
0x18000d43f  mov     [rsp+48h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000d447  xor     r9d, r9d; lpSecurityAttributes
0x18000d44a  mov     edx, 40000000h; dwDesiredAccess
0x18000d44f  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000d454  mov     rcx, rdi; lpFileName
0x18000d457  call    cs:__imp_CreateFileW
0x18000d45d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d461  jnz     short loc_18000D471
0x18000d463  mov     cs:dword_180025CA0, 0
0x18000d46d  xor     ebx, ebx
0x18000d46f  jmp     short loc_18000D47A
0x18000d471  mov     rcx, rax; hObject
0x18000d474  call    cs:__imp_CloseHandle
0x18000d47a  mov     eax, ebx
0x18000d47c  mov     rbx, [rsp+48h+arg_0]
0x18000d481  add     rsp, 40h
0x18000d485  pop     rdi
0x18000d486  retn
```

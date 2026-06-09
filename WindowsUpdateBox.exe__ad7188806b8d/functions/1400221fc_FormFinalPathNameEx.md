# FormFinalPathNameEx

- ea: `0x1400221fc`
- end: `0x1400222e2`
- name: `FormFinalPathNameEx`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, reparse_path`

## callers

- `0x140020498`
- `0x14002066c`
- `0x140026104`

## callees

- `0x1400220d0`
- `0x1400221fc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140022287`
- `KERNEL32!CloseHandle` at `0x140022287`
- `KERNEL32!GetLastError` at `0x140022274`
- `KERNEL32!GetLastError` at `0x140022298`
- `KERNEL32!GetLastError` at `0x140022274`
- `KERNEL32!GetLastError` at `0x140022298`
- `KERNEL32!CreateFileW` at `0x14002224d`
- `KERNEL32!CreateFileW` at `0x14002224d`
- `KERNEL32!SetLastError` at `0x1400222a8`
- `KERNEL32!SetLastError` at `0x1400222be`
- `KERNEL32!SetLastError` at `0x1400222a8`
- `KERNEL32!SetLastError` at `0x1400222be`

## pseudocode

```c
WCHAR *__fastcall FormFinalPathNameEx(const WCHAR *a1, int a2)
{
  WCHAR *v2; // rbx
  char *FileW; // rax
  char *v5; // rsi
  WCHAR *v6; // rbp
  DWORD LastError; // edi

  v2 = 0;
  if ( a1 && *a1 && (a2 & 0xFFFFFFF8) == 0 )
  {
    FileW = (char *)CreateFileW(a1, 0, 7u, 0, 3u, 0x2200000u, 0);
    v5 = FileW;
    if ( FileW == (char *)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      v6 = FormFinalPathNameByHandle(FileW, a2);
      if ( !v6 )
        LODWORD(v2) = GetLastError();
      LastError = (unsigned int)v2;
      CloseHandle(v5);
      v2 = v6;
    }
    SetLastError(LastError);
    return v2;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x1400221fc  mov     rax, rsp
0x1400221ff  mov     [rax+8], rbx
0x140022203  mov     [rax+10h], rbp
0x140022207  mov     [rax+18h], rsi
0x14002220b  push    rdi
0x14002220c  sub     rsp, 40h
0x140022210  xor     ebx, ebx
0x140022212  mov     edi, edx
0x140022214  test    rcx, rcx
0x140022217  jz      loc_1400222B9
0x14002221d  cmp     bx, [rcx]
0x140022220  jz      loc_1400222B9
0x140022226  test    edx, 0FFFFFFF8h
0x14002222c  jnz     loc_1400222B9
0x140022232  mov     [rax-18h], rbx
0x140022236  lea     r8d, [rbx+7]; dwShareMode
0x14002223a  mov     dword ptr [rax-20h], 2200000h
0x140022241  xor     r9d, r9d; lpSecurityAttributes
0x140022244  xor     edx, edx; dwDesiredAccess
0x140022246  mov     dword ptr [rax-28h], 3
0x14002224d  call    cs:__imp_CreateFileW
0x140022254  nop     dword ptr [rax+rax+00h]
0x140022259  mov     rsi, rax
0x14002225c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140022260  jz      short loc_140022298
0x140022262  mov     edx, edi
0x140022264  mov     rcx, rax; hFile
0x140022267  call    FormFinalPathNameByHandle
0x14002226c  mov     rbp, rax
0x14002226f  test    rax, rax
0x140022272  jnz     short loc_140022282
0x140022274  call    cs:__imp_GetLastError
0x14002227b  nop     dword ptr [rax+rax+00h]
0x140022280  mov     ebx, eax
0x140022282  mov     rcx, rsi; hObject
0x140022285  mov     edi, ebx
0x140022287  call    cs:__imp_CloseHandle
0x14002228e  nop     dword ptr [rax+rax+00h]
0x140022293  mov     rbx, rbp
0x140022296  jmp     short loc_1400222A6
0x140022298  call    cs:__imp_GetLastError
0x14002229f  nop     dword ptr [rax+rax+00h]
0x1400222a4  mov     edi, eax
0x1400222a6  mov     ecx, edi; dwErrCode
0x1400222a8  call    cs:__imp_SetLastError
0x1400222af  nop     dword ptr [rax+rax+00h]
0x1400222b4  mov     rax, rbx
0x1400222b7  jmp     short loc_1400222CC
0x1400222b9  mov     ecx, 57h ; 'W'; dwErrCode
0x1400222be  call    cs:__imp_SetLastError
0x1400222c5  nop     dword ptr [rax+rax+00h]
0x1400222ca  xor     eax, eax
0x1400222cc  mov     rbx, [rsp+48h+arg_0]
0x1400222d1  mov     rbp, [rsp+48h+arg_8]
0x1400222d6  mov     rsi, [rsp+48h+arg_10]
0x1400222db  add     rsp, 40h
0x1400222df  pop     rdi
0x1400222e0  retn
```

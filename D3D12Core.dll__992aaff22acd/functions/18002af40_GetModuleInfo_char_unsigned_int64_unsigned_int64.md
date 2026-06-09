# GetModuleInfo(char *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18002af40`
- end: `0x18002b045`
- name: `?GetModuleInfo@@YA_NPEADPEA_K1@Z`
- size: `261`
- prototype: `bool __fastcall(char *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002ae44`

## callees

- `0x18002af40`
- `0x18002b050`
- `0x1800bb480`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18002af76`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18002af76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b030`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002b030`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002b022`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18002b022`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18002afb9`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x18002afb9`

## pseudocode

```c
char __fastcall GetModuleInfo(char *a1, unsigned __int64 *a2, unsigned __int64 *a3)
{
  DWORD ModuleFileNameA; // r14d
  HANDLE FileA; // rax
  void *v8; // rsi
  unsigned __int64 v9; // rcx
  bool v11; // cf
  CHAR Filename[272]; // [rsp+40h] [rbp-148h] BYREF

  ModuleFileNameA = GetModuleFileNameA(0, Filename, 0x104u);
  if ( ModuleFileNameA )
  {
    Filename[260] = 0;
    FileA = CreateFileA(Filename, 0x80000000, 7u, 0, 3u, 0x80u, 0);
    v8 = FileA;
    if ( FileA == (HANDLE)-1LL )
    {
      if ( a3 )
        *a3 = 0;
    }
    else
    {
      if ( a3 )
        *a3 = GetFileSize(FileA, 0);
      CloseHandle(v8);
    }
    if ( !a2 )
      return 1;
    v9 = ModuleFileNameA + 1;
    if ( !a1 )
    {
      *a2 = v9;
      return 1;
    }
    v11 = *a2 < v9;
    *a2 = v9;
    if ( !v11 )
    {
      StringCchCopyA(a1, ModuleFileNameA + 1, Filename);
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002af40  push    rbx
0x18002af42  push    rbp
0x18002af43  push    rsi
0x18002af44  push    rdi
0x18002af45  push    r14
0x18002af47  sub     rsp, 160h
0x18002af4e  mov     rax, cs:__security_cookie
0x18002af55  xor     rax, rsp
0x18002af58  mov     [rsp+188h+var_38], rax
0x18002af60  mov     rdi, r8
0x18002af63  mov     rbx, rdx
0x18002af66  mov     rbp, rcx
0x18002af69  lea     rdx, [rsp+188h+Filename]; lpFilename
0x18002af6e  mov     r8d, 104h; nSize
0x18002af74  xor     ecx, ecx; hModule
0x18002af76  call    cs:__imp_GetModuleFileNameA
0x18002af7c  mov     r14d, eax
0x18002af7f  test    eax, eax
0x18002af81  jz      loc_18002B038
0x18002af87  xor     r9d, r9d; lpSecurityAttributes
0x18002af8a  mov     [rsp+188h+hTemplateFile], 0; hTemplateFile
0x18002af93  mov     [rsp+188h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002af9b  lea     rcx, [rsp+188h+Filename]; lpFileName
0x18002afa0  mov     edx, 80000000h; dwDesiredAccess
0x18002afa5  mov     [rsp+188h+var_44], 0
0x18002afad  mov     [rsp+188h+dwCreationDisposition], 3; dwCreationDisposition
0x18002afb5  lea     r8d, [r9+7]; dwShareMode
0x18002afb9  call    cs:__imp_CreateFileA
0x18002afbf  mov     rsi, rax
0x18002afc2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002afc6  jnz     short loc_18002B018
0x18002afc8  test    rdi, rdi
0x18002afcb  jnz     short loc_18002B03C
0x18002afcd  test    rbx, rbx
0x18002afd0  jz      short loc_18002AFDE
0x18002afd2  lea     ecx, [r14+1]
0x18002afd6  test    rbp, rbp
0x18002afd9  jnz     short loc_18002AFFE
0x18002afdb  mov     [rbx], rcx
0x18002afde  mov     al, 1
0x18002afe0  mov     rcx, [rsp+188h+var_38]
0x18002afe8  xor     rcx, rsp; StackCookie
0x18002afeb  call    __security_check_cookie
0x18002aff0  add     rsp, 160h
0x18002aff7  pop     r14
0x18002aff9  pop     rdi
0x18002affa  pop     rsi
0x18002affb  pop     rbp
0x18002affc  pop     rbx
0x18002affd  retn
0x18002affe  cmp     [rbx], rcx
0x18002b001  mov     [rbx], rcx
0x18002b004  jb      short loc_18002B038
0x18002b006  mov     rdx, rcx; unsigned __int64
0x18002b009  lea     r8, [rsp+188h+Filename]; char *
0x18002b00e  mov     rcx, rbp; char *
0x18002b011  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002b016  jmp     short loc_18002AFDE
0x18002b018  test    rdi, rdi
0x18002b01b  jz      short loc_18002B02D
0x18002b01d  xor     edx, edx; lpFileSizeHigh
0x18002b01f  mov     rcx, rsi; hFile
0x18002b022  call    cs:__imp_GetFileSize
0x18002b028  mov     ecx, eax
0x18002b02a  mov     [rdi], rcx
0x18002b02d  mov     rcx, rsi; hObject
0x18002b030  call    cs:__imp_CloseHandle
0x18002b036  jmp     short loc_18002AFCD
0x18002b038  xor     al, al
0x18002b03a  jmp     short loc_18002AFE0
0x18002b03c  mov     qword ptr [rdi], 0
0x18002b043  jmp     short loc_18002AFCD
```

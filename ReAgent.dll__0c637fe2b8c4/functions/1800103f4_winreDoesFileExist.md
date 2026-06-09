# winreDoesFileExist

- ea: `0x1800103f4`
- end: `0x180010515`
- name: `winreDoesFileExist`
- size: `289`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `16`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x1800109f8`
- `0x180011074`
- `0x180012f58`
- `0x180017960`
- `0x180025a60`
- `0x18002dd30`
- `0x18002eca0`
- `0x18002f860`
- `0x180030770`
- `0x180030c54`
- `0x180032c14`
- `0x180036c38`
- `0x180039b38`
- `0x180039dd4`
- `0x18003a248`
- `0x18003aac0`

## callees

- `0x1800059fc`
- `0x18000fe58`
- `0x1800103f4`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `msvcrt!wcschr` at `0x180010440`
- `msvcrt!wcschr` at `0x180010440`
- `KERNEL32!CreateFileW` at `0x1800104d1`
- `KERNEL32!CreateFileW` at `0x1800104d1`
- `KERNEL32!CloseHandle` at `0x1800104ea`
- `KERNEL32!CloseHandle` at `0x1800104ea`

## string_xrefs

- `0x18001047e`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010492`: `failed to add file to directory path`

## pseudocode

```c
__int64 __fastcall winreDoesFileExist(unsigned __int16 *a1, unsigned __int16 *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rax
  unsigned int v6; // eax
  HANDLE FileW; // rax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-2A0h]
  WCHAR FileName[304]; // [rsp+40h] [rbp-288h] BYREF

  v4 = 0;
  memset_0(FileName, 0, 0x25Cu);
  if ( a2 )
  {
    if ( wcschr(a2, 0x5Cu) )
      goto LABEL_7;
    if ( a1 )
    {
      v5 = -1;
      do
        ++v5;
      while ( a1[v5] );
      if ( v5 )
      {
LABEL_7:
        v6 = winreAddFileToDirPath(a1, a2, FileName);
        if ( v6 )
        {
          dwFlagsAndAttributes = 1399;
          UnattendLogW(
            2,
            L"winreDoesFileExist %s (0x%x) in file %S line %d",
            L"failed to add file to directory path",
            v6,
            "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
            dwFlagsAndAttributes);
        }
        else
        {
          FileW = CreateFileW(FileName, 0x80000000, 7u, 0, 3u, 0, 0);
          if ( FileW != (HANDLE)-1LL )
          {
            v4 = 1;
            if ( FileW )
              CloseHandle(FileW);
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800103f4  mov     [rsp+arg_10], rbx
0x1800103f9  push    rbp
0x1800103fa  push    rsi
0x1800103fb  push    rdi
0x1800103fc  sub     rsp, 2B0h
0x180010403  mov     rax, cs:__security_cookie
0x18001040a  xor     rax, rsp
0x18001040d  mov     [rsp+2C8h+var_28], rax
0x180010415  mov     rsi, rdx
0x180010418  mov     rbx, rcx
0x18001041b  xor     ebp, ebp
0x18001041d  lea     rcx, [rsp+2C8h+FileName]; void *
0x180010422  xor     edx, edx; Val
0x180010424  mov     r8d, 25Ch; Size
0x18001042a  mov     edi, ebp
0x18001042c  call    memset_0
0x180010431  test    rsi, rsi
0x180010434  jz      loc_1800104F0
0x18001043a  lea     edx, [rbp+5Ch]; Ch
0x18001043d  mov     rcx, rsi; Str
0x180010440  call    cs:__imp_wcschr
0x180010446  test    rax, rax
0x180010449  jnz     short loc_18001046A
0x18001044b  test    rbx, rbx
0x18001044e  jz      loc_1800104F0
0x180010454  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010458  inc     rax
0x18001045b  cmp     [rbx+rax*2], bp
0x18001045f  jnz     short loc_180010458
0x180010461  test    rax, rax
0x180010464  jz      loc_1800104F0
0x18001046a  lea     r8, [rsp+2C8h+FileName]; unsigned __int16 *
0x18001046f  mov     rdx, rsi; unsigned __int16 *
0x180010472  mov     rcx, rbx; unsigned __int16 *
0x180010475  call    winreAddFileToDirPath
0x18001047a  test    eax, eax
0x18001047c  jz      short loc_1800104AF
0x18001047e  lea     rcx, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010485  mov     [rsp+2C8h+dwFlagsAndAttributes], 577h
0x18001048d  mov     qword ptr [rsp+2C8h+dwCreationDisposition], rcx
0x180010492  lea     r8, aFailedToAddFil_3; "failed to add file to directory path"
0x180010499  mov     ecx, 2
0x18001049e  lea     rdx, aWinredoesfilee; "winreDoesFileExist %s (0x%x) in file %S"...
0x1800104a5  mov     r9d, eax
0x1800104a8  call    UnattendLogW
0x1800104ad  jmp     short loc_1800104F0
0x1800104af  xor     r9d, r9d; lpSecurityAttributes
0x1800104b2  mov     [rsp+2C8h+hTemplateFile], rbp; hTemplateFile
0x1800104b7  mov     [rsp+2C8h+dwFlagsAndAttributes], ebp; dwFlagsAndAttributes
0x1800104bb  lea     rcx, [rsp+2C8h+FileName]; lpFileName
0x1800104c0  mov     edx, 80000000h; dwDesiredAccess
0x1800104c5  mov     [rsp+2C8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800104cd  lea     r8d, [r9+7]; dwShareMode
0x1800104d1  call    cs:__imp_CreateFileW
0x1800104d7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800104db  jz      short loc_1800104F0
0x1800104dd  mov     edi, 1
0x1800104e2  test    rax, rax
0x1800104e5  jz      short loc_1800104F0
0x1800104e7  mov     rcx, rax; hObject
0x1800104ea  call    cs:__imp_CloseHandle
0x1800104f0  mov     eax, edi
0x1800104f2  mov     rcx, [rsp+2C8h+var_28]
0x1800104fa  xor     rcx, rsp; StackCookie
0x1800104fd  call    __security_check_cookie
0x180010502  mov     rbx, [rsp+2C8h+arg_10]
0x18001050a  add     rsp, 2B0h
0x180010511  pop     rdi
0x180010512  pop     rsi
0x180010513  pop     rbp
0x180010514  retn
```

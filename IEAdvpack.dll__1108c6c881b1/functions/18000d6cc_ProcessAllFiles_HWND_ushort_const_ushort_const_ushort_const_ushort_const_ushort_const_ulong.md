# ProcessAllFiles(HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000d6cc`
- end: `0x18000d7a4`
- name: `?ProcessAllFiles@@YAJPEAUHWND__@@PEBG1111K@Z`
- size: `216`
- prototype: `__int64 __fastcall(HWND hWnd, PCWSTR SectionName, PCWSTR SourceRootPath, LPCWSTR lpDir, LPCWSTR lpBaseName, const unsigned __int16 *, DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e060`
- `0x180010050`

## callees

- `0x180008a6c`
- `0x18000c574`
- `0x18000d6cc`
- `0x18000d90c`
- `0x1800171b0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18000d711`
- `KERNEL32!LocalAlloc` at `0x18000d711`

## string_xrefs

- `0x18000d6dd`: `ProcessAllFiles: Sec=%1, SrcDir=%2, BackupPath=%3\n`

## pseudocode

```c
__int64 __fastcall ProcessAllFiles(
        HWND hWnd,
        PCWSTR SectionName,
        PCWSTR SourceRootPath,
        LPCWSTR lpDir,
        LPCWSTR lpBaseName,
        const unsigned __int16 *a6,
        DWORD dwFlags)
{
  WCHAR *v11; // rdx
  HRESULT v13; // ebx

  AdvWriteToLog(L"ProcessAllFiles: Sec=%1, SrcDir=%2, BackupPath=%3\r\n");
  v11 = 0;
  hMem = 0;
  if ( (dwFlags & 0x100) != 0 )
    goto LABEL_6;
  hMem = (LPWSTR)LocalAlloc(0x40u, 0x5000u);
  qword_180032320 = hMem;
  if ( !hMem )
  {
    MsgBox2Param(hWnd, 0x44Eu, 0, 0, 0x10u, 0);
    return 2147942414LL;
  }
  v13 = ProcessFileSections(SectionName, SourceRootPath, (PSP_FILE_CALLBACK_W)MyFileQueueCallback);
  if ( v13 >= 0 )
  {
    v11 = hMem;
LABEL_6:
    v13 = FileSaveRestoreW(hWnd, v11, lpDir, lpBaseName, dwFlags);
  }
  AdvWriteToLog(L"ProcessAllFiles: End hr=0x%1!x!\r\n", (unsigned int)v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000d6cc  push    rbx
0x18000d6ce  push    rbp
0x18000d6cf  push    rsi
0x18000d6d0  push    rdi
0x18000d6d1  push    r14
0x18000d6d3  sub     rsp, 30h
0x18000d6d7  mov     rdi, rcx
0x18000d6da  mov     rbp, r9
0x18000d6dd  lea     rcx, aProcessallfile; "ProcessAllFiles: Sec=%1, SrcDir=%2, Bac"...
0x18000d6e4  mov     rbx, r8
0x18000d6e7  mov     rsi, rdx
0x18000d6ea  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000d6ef  mov     r14d, [rsp+58h+arg_30]
0x18000d6f7  xor     edx, edx
0x18000d6f9  mov     cs:hMem, rdx
0x18000d700  bt      r14d, 8
0x18000d705  jb      short loc_18000D76F
0x18000d707  mov     edx, 5000h; uBytes
0x18000d70c  mov     ecx, 40h ; '@'; uFlags
0x18000d711  call    cs:__imp_LocalAlloc
0x18000d717  mov     cs:hMem, rax
0x18000d71e  mov     cs:qword_180032320, rax
0x18000d725  test    rax, rax
0x18000d728  jnz     short loc_18000D750
0x18000d72a  mov     [rsp+58h+var_30], eax; unsigned int
0x18000d72e  xor     r9d, r9d; unsigned __int16 *
0x18000d731  xor     r8d, r8d; unsigned __int16 *
0x18000d734  mov     [rsp+58h+dwFlags], 10h; unsigned int
0x18000d73c  mov     edx, 44Eh; uID
0x18000d741  mov     rcx, rdi; hWnd
0x18000d744  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18000d749  mov     eax, 8007000Eh
0x18000d74e  jmp     short loc_18000D799
0x18000d750  lea     r8, ?MyFileQueueCallback@@YAIPEAXI_K1@Z; MsgHandler
0x18000d757  mov     rdx, rbx; SourceRootPath
0x18000d75a  mov     rcx, rsi; SectionName
0x18000d75d  call    ?ProcessFileSections@@YAJPEBG0P6AIPEAXI_K2@Z@Z; ProcessFileSections(ushort const *,ushort const *,uint (*)(void *,uint,unsigned __int64,unsigned __int64))
0x18000d762  mov     ebx, eax
0x18000d764  test    eax, eax
0x18000d766  js      short loc_18000D789
0x18000d768  mov     rdx, cs:hMem; lpFileList
0x18000d76f  mov     r9, [rsp+58h+lpBaseName]; lpBaseName
0x18000d777  mov     r8, rbp; lpDir
0x18000d77a  mov     rcx, rdi; hDlg
0x18000d77d  mov     [rsp+58h+dwFlags], r14d; dwFlags
0x18000d782  call    FileSaveRestoreW
0x18000d787  mov     ebx, eax
0x18000d789  mov     edx, ebx
0x18000d78b  lea     rcx, aProcessallfile_0; "ProcessAllFiles: End hr=0x%1!x!\r\n"
0x18000d792  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000d797  mov     eax, ebx
0x18000d799  add     rsp, 30h
0x18000d79d  pop     r14
0x18000d79f  pop     rdi
0x18000d7a0  pop     rsi
0x18000d7a1  pop     rbp
0x18000d7a2  pop     rbx
0x18000d7a3  retn
```

# CVaultNonTransacted::FileOperationsCreateFile(ushort const *,ulong,eWriteMode,void * *)

- ea: `0x180031640`
- end: `0x1800316ab`
- name: `?FileOperationsCreateFile@CVaultNonTransacted@@UEAAKPEBGKW4eWriteMode@@PEAPEAX@Z`
- size: `107`
- prototype: `DWORD __fastcall(__int64, const WCHAR *, DWORD, int, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180031640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316a4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031685`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031685`

## pseudocode

```c
DWORD __fastcall CVaultNonTransacted::FileOperationsCreateFile(
        __int64 a1,
        const WCHAR *a2,
        DWORD a3,
        int a4,
        _QWORD *a5)
{
  DWORD dwCreationDisposition; // eax
  HANDLE FileW; // rax

  dwCreationDisposition = 2;
  if ( a4 != 1 )
    dwCreationDisposition = 4;
  FileW = CreateFileW(a2, a3, 0, 0, dwCreationDisposition, ((unsigned __int8)(dword_18005F638 & 1) << 31) + 128, 0);
  *a5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  else
    return 0;
}

```

## disassembly

```asm
0x180031640  sub     rsp, 48h
0x180031644  mov     ecx, cs:dword_18005F638
0x18003164a  mov     r11, rdx
0x18003164d  and     ecx, 1
0x180031650  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180031659  shl     ecx, 1Fh
0x18003165c  mov     eax, 2
0x180031661  sub     ecx, 0FFFFFF80h
0x180031664  mov     r10d, r8d
0x180031667  cmp     r9d, 1
0x18003166b  mov     [rsp+48h+dwFlagsAndAttributes], ecx; dwFlagsAndAttributes
0x18003166f  mov     rcx, r11; lpFileName
0x180031672  lea     edx, [rax+2]
0x180031675  cmovnz  eax, edx
0x180031678  xor     r9d, r9d; lpSecurityAttributes
0x18003167b  xor     r8d, r8d; dwShareMode
0x18003167e  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x180031682  mov     edx, r10d; dwDesiredAccess
0x180031685  call    cs:__imp_CreateFileW
0x18003168b  mov     rcx, [rsp+48h+arg_20]
0x180031690  mov     [rcx], rax
0x180031693  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031697  jz      short loc_1800316A0
0x180031699  xor     eax, eax
0x18003169b  add     rsp, 48h
0x18003169f  retn
0x1800316a0  add     rsp, 48h
0x1800316a4  jmp     cs:__imp_GetLastError
```

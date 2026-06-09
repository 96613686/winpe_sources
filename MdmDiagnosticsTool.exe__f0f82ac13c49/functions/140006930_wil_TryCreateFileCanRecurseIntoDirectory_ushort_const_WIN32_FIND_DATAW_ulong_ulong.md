# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x140006930`
- end: `0x140006a13`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `227`
- prototype: `void **__fastcall(void **, const WCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x140005b1c`

## callees

- `0x140003174`
- `0x14000358c`
- `0x140006930`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000696b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000696b`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14000699d`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14000699d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400069ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400069ee`

## pseudocode

```c
void **__fastcall wil::TryCreateFileCanRecurseIntoDirectory(void **a1, const WCHAR *a2, _DWORD *a3)
{
  char *FileW; // rax
  int v6; // ecx
  void *v7; // rdi
  _BYTE v9[24]; // [rsp+40h] [rbp-18h] BYREF
  __int64 FileInformation; // [rsp+60h] [rbp+8h] BYREF

  FileW = (char *)CreateFileW(a2, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
  *a1 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    FileInformation = 0;
    if ( GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u)
      && (FileInformation & 0x10) != 0
      && ((v6 = HIDWORD(FileInformation), (FileInformation & 0x400) == 0)
       || (FileInformation & 0x1000000000000000LL) != 0
       || HIDWORD(FileInformation) == -2147483624) )
    {
      if ( a3 )
      {
        *a3 = FileInformation;
        a3[9] = v6;
      }
    }
    else
    {
      v7 = *a1;
      if ( (char *)*a1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v9);
        CloseHandle(v7);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v9);
      }
      *a1 = (void *)-1LL;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140006930  mov     [rsp+arg_8], rbx
0x140006935  push    rdi
0x140006936  sub     rsp, 50h
0x14000693a  mov     rax, rdx
0x14000693d  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x140006946  xor     r9d, r9d; lpSecurityAttributes
0x140006949  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x140006951  mov     rdi, r8
0x140006954  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x14000695c  mov     rbx, rcx
0x14000695f  mov     edx, 80010000h; dwDesiredAccess
0x140006964  mov     rcx, rax; lpFileName
0x140006967  lea     r8d, [r9+1]; dwShareMode
0x14000696b  call    cs:__imp_CreateFileW
0x140006971  mov     [rbx], rax
0x140006974  lea     rdx, [rax-1]
0x140006978  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000697c  ja      loc_140006A05
0x140006982  mov     r9d, 8; dwBufferSize
0x140006988  mov     [rsp+58h+FileInformation], 0
0x140006991  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x140006996  mov     rcx, rax; hFile
0x140006999  lea     edx, [r9+1]; FileInformationClass
0x14000699d  call    cs:__imp_GetFileInformationByHandleEx
0x1400069a3  test    eax, eax
0x1400069a5  jz      short loc_1400069D4
0x1400069a7  mov     rax, [rsp+58h+FileInformation]
0x1400069ac  test    al, 10h
0x1400069ae  jz      short loc_1400069D4
0x1400069b0  mov     ecx, dword ptr [rsp+58h+FileInformation+4]
0x1400069b4  bt      eax, 0Ah
0x1400069b8  jnb     short loc_1400069C8
0x1400069ba  bt      ecx, 1Ch
0x1400069be  jb      short loc_1400069C8
0x1400069c0  cmp     ecx, 80000018h
0x1400069c6  jnz     short loc_1400069D4
0x1400069c8  test    rdi, rdi
0x1400069cb  jz      short loc_140006A05
0x1400069cd  mov     [rdi], eax
0x1400069cf  mov     [rdi+24h], ecx
0x1400069d2  jmp     short loc_140006A05
0x1400069d4  mov     rdi, [rbx]
0x1400069d7  lea     rax, [rdi-1]
0x1400069db  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400069df  ja      short loc_1400069FE
0x1400069e1  lea     rcx, [rsp+58h+var_18]; this
0x1400069e6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400069eb  mov     rcx, rdi; hObject
0x1400069ee  call    cs:__imp_CloseHandle
0x1400069f4  lea     rcx, [rsp+58h+var_18]; this
0x1400069f9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400069fe  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x140006a05  mov     rax, rbx
0x140006a08  mov     rbx, [rsp+58h+arg_8]
0x140006a0d  add     rsp, 50h
0x140006a11  pop     rdi
0x140006a12  retn
```

# wil::TryCreateFileCanRecurseIntoDirectory(ushort const *,_WIN32_FIND_DATAW *,ulong,ulong)

- ea: `0x1800114fc`
- end: `0x1800115df`
- name: `?TryCreateFileCanRecurseIntoDirectory@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@PEBGPEAU_WIN32_FIND_DATAW@@KK@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800109d4`

## callees

- `0x18000e68c`
- `0x18000e9a4`
- `0x1800114fc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800115ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800115ba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011537`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180011537`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180011569`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180011569`

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
0x1800114fc  mov     [rsp+arg_8], rbx
0x180011501  push    rdi
0x180011502  sub     rsp, 50h
0x180011506  mov     rax, rdx
0x180011509  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180011512  xor     r9d, r9d; lpSecurityAttributes
0x180011515  mov     [rsp+58h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18001151d  mov     rdi, r8
0x180011520  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x180011528  mov     rbx, rcx
0x18001152b  mov     edx, 80010000h; dwDesiredAccess
0x180011530  mov     rcx, rax; lpFileName
0x180011533  lea     r8d, [r9+1]; dwShareMode
0x180011537  call    cs:__imp_CreateFileW
0x18001153d  mov     [rbx], rax
0x180011540  lea     rdx, [rax-1]
0x180011544  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180011548  ja      loc_1800115D1
0x18001154e  mov     r9d, 8; dwBufferSize
0x180011554  mov     [rsp+58h+FileInformation], 0
0x18001155d  lea     r8, [rsp+58h+FileInformation]; lpFileInformation
0x180011562  mov     rcx, rax; hFile
0x180011565  lea     edx, [r9+1]; FileInformationClass
0x180011569  call    cs:__imp_GetFileInformationByHandleEx
0x18001156f  test    eax, eax
0x180011571  jz      short loc_1800115A0
0x180011573  mov     rax, [rsp+58h+FileInformation]
0x180011578  test    al, 10h
0x18001157a  jz      short loc_1800115A0
0x18001157c  mov     ecx, dword ptr [rsp+58h+FileInformation+4]
0x180011580  bt      eax, 0Ah
0x180011584  jnb     short loc_180011594
0x180011586  bt      ecx, 1Ch
0x18001158a  jb      short loc_180011594
0x18001158c  cmp     ecx, 80000018h
0x180011592  jnz     short loc_1800115A0
0x180011594  test    rdi, rdi
0x180011597  jz      short loc_1800115D1
0x180011599  mov     [rdi], eax
0x18001159b  mov     [rdi+24h], ecx
0x18001159e  jmp     short loc_1800115D1
0x1800115a0  mov     rdi, [rbx]
0x1800115a3  lea     rax, [rdi-1]
0x1800115a7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800115ab  ja      short loc_1800115CA
0x1800115ad  lea     rcx, [rsp+58h+var_18]; this
0x1800115b2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800115b7  mov     rcx, rdi; hObject
0x1800115ba  call    cs:__imp_CloseHandle
0x1800115c0  lea     rcx, [rsp+58h+var_18]; this
0x1800115c5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800115ca  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x1800115d1  mov     rax, rbx
0x1800115d4  mov     rbx, [rsp+58h+arg_8]
0x1800115d9  add     rsp, 50h
0x1800115dd  pop     rdi
0x1800115de  retn
```

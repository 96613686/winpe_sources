# SdbOpenApphelpResourceFile

- ea: `0x1400366e8`
- end: `0x1400367a3`
- name: `SdbOpenApphelpResourceFile`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140036f7c`

## callees

- `0x140035658`
- `0x1400366e8`
- `0x14003bf18`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003674e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003674e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003675c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003675c`

## string_xrefs

- `0x140036725`: `SdbGetPathResourceDll failed.`
- `0x140036766`: `Failed to open the Apphelp resource file %ws [Gle=%u]`
- `0x140036732`: `SdbOpenApphelpResourceFile`
- `0x140036778`: `SdbOpenApphelpResourceFile`

## pseudocode

```c
HMODULE SdbOpenApphelpResourceFile()
{
  HMODULE Library; // rbx
  DWORD LastError; // [rsp+28h] [rbp-230h]
  WCHAR LibFileName[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(LibFileName, 0, 0x208u);
  if ( (unsigned int)SdbGetPathResourceDll(LibFileName) )
  {
    Library = LoadLibraryExW(LibFileName, 0, 2u);
    if ( !Library )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        "SdbOpenApphelpResourceFile",
        265,
        "Failed to open the Apphelp resource file %ws [Gle=%u]",
        0,
        LastError);
    }
  }
  else
  {
    Library = 0;
    AslLogCallPrintf(1, "SdbOpenApphelpResourceFile", 254, "SdbGetPathResourceDll failed.");
  }
  return Library;
}

```

## disassembly

```asm
0x1400366e8  push    rbx
0x1400366ea  sub     rsp, 250h
0x1400366f1  mov     rax, cs:__security_cookie
0x1400366f8  xor     rax, rsp
0x1400366fb  mov     [rsp+258h+var_18], rax
0x140036703  xor     edx, edx; Val
0x140036705  lea     rcx, [rsp+258h+LibFileName]; void *
0x14003670a  mov     r8d, 208h; Size
0x140036710  call    memset_0
0x140036715  lea     rcx, [rsp+258h+LibFileName]
0x14003671a  call    SdbGetPathResourceDll
0x14003671f  test    eax, eax
0x140036721  jnz     short loc_140036743
0x140036723  xor     ebx, ebx
0x140036725  lea     r9, aSdbgetpathreso; "SdbGetPathResourceDll failed."
0x14003672c  mov     r8d, 0FEh
0x140036732  lea     rdx, aSdbopenapphelp; "SdbOpenApphelpResourceFile"
0x140036739  lea     ecx, [rax+1]
0x14003673c  call    AslLogCallPrintf
0x140036741  jmp     short loc_140036787
0x140036743  xor     edx, edx; hFile
0x140036745  lea     rcx, [rsp+258h+LibFileName]; lpLibFileName
0x14003674a  lea     r8d, [rdx+2]; dwFlags
0x14003674e  call    cs:__imp_LoadLibraryExW
0x140036754  mov     rbx, rax
0x140036757  test    rax, rax
0x14003675a  jnz     short loc_140036787
0x14003675c  call    cs:__imp_GetLastError
0x140036762  mov     [rsp+258h+var_230], eax
0x140036766  lea     r9, aFailedToOpenTh_0; "Failed to open the Apphelp resource fil"...
0x14003676d  mov     r8d, 109h
0x140036773  mov     [rsp+258h+var_238], rbx
0x140036778  lea     rdx, aSdbopenapphelp; "SdbOpenApphelpResourceFile"
0x14003677f  lea     ecx, [rbx+1]
0x140036782  call    AslLogCallPrintf
0x140036787  mov     rax, rbx
0x14003678a  mov     rcx, [rsp+258h+var_18]
0x140036792  xor     rcx, rsp; StackCookie
0x140036795  call    __security_check_cookie
0x14003679a  add     rsp, 250h
0x1400367a1  pop     rbx
0x1400367a2  retn
```

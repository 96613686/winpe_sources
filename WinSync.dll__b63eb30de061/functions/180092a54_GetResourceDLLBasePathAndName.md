# GetResourceDLLBasePathAndName

- ea: `0x180092a54`
- end: `0x180092b18`
- name: `GetResourceDLLBasePathAndName`
- size: `196`
- prototype: `char __fastcall(HMODULE, __int64, WCHAR *, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180092bc0`

## callees

- `0x1800929fc`
- `0x180092a54`
- `0x180092e78`
- `0x180093270`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180092aae`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180092aae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180092a89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180092a89`

## pseudocode

```c
char __fastcall GetResourceDLLBasePathAndName(HMODULE a1, __int64 a2, WCHAR *a3, __int64 a4, _WORD *a5)
{
  LPWSTR FilePart; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Filename[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !GetModuleFileNameW(a1, Filename, 0x105u) )
    return 0;
  FilePart = 0;
  if ( GetFullPathNameW(Filename, 0x105u, a3, &FilePart) - 1 > 0x104
    || !*a5 && !(unsigned __int8)CopyString(a5, 261, FilePart) )
  {
    return 0;
  }
  *FilePart = 0;
  return PathRenameExtension(a5, 0, L".rll.mui");
}

```

## disassembly

```asm
0x180092a54  mov     [rsp+arg_8], rbx
0x180092a59  push    rdi
0x180092a5a  sub     rsp, 250h
0x180092a61  mov     rax, cs:__security_cookie
0x180092a68  xor     rax, rsp
0x180092a6b  mov     [rsp+258h+var_18], rax
0x180092a73  mov     rbx, [rsp+258h+arg_20]
0x180092a7b  lea     rdx, [rsp+258h+Filename]; lpFilename
0x180092a80  mov     rdi, r8
0x180092a83  mov     r8d, 105h; nSize
0x180092a89  call    cs:__imp_GetModuleFileNameW
0x180092a8f  test    eax, eax
0x180092a91  jz      short loc_180092AF5
0x180092a93  lea     r9, [rsp+258h+FilePart]; lpFilePart
0x180092a98  mov     [rsp+258h+FilePart], 0
0x180092aa1  mov     r8, rdi; lpBuffer
0x180092aa4  lea     rcx, [rsp+258h+Filename]; lpFileName
0x180092aa9  mov     edx, 105h; nBufferLength
0x180092aae  call    cs:__imp_GetFullPathNameW
0x180092ab4  dec     eax
0x180092ab6  cmp     eax, 104h
0x180092abb  ja      short loc_180092AF5
0x180092abd  xor     eax, eax
0x180092abf  cmp     ax, [rbx]
0x180092ac2  jnz     short loc_180092ADA
0x180092ac4  mov     r8, [rsp+258h+FilePart]
0x180092ac9  mov     edx, 105h
0x180092ace  mov     rcx, rbx
0x180092ad1  call    CopyString
0x180092ad6  test    al, al
0x180092ad8  jz      short loc_180092AF5
0x180092ada  mov     rax, [rsp+258h+FilePart]
0x180092adf  lea     r8, aRllMui; ".rll.mui"
0x180092ae6  xor     edx, edx
0x180092ae8  mov     rcx, rbx
0x180092aeb  mov     [rax], dx
0x180092aee  call    PathRenameExtension
0x180092af3  jmp     short loc_180092AF7
0x180092af5  xor     al, al
0x180092af7  mov     rcx, [rsp+258h+var_18]
0x180092aff  xor     rcx, rsp; StackCookie
0x180092b02  call    __security_check_cookie
0x180092b07  mov     rbx, [rsp+258h+arg_8]
0x180092b0f  add     rsp, 250h
0x180092b16  pop     rdi
0x180092b17  retn
```

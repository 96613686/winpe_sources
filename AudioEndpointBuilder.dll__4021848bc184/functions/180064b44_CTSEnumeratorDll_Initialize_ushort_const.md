# CTSEnumeratorDll::Initialize(ushort const *)

- ea: `0x180064b44`
- end: `0x180064b9c`
- name: `?Initialize@CTSEnumeratorDll@@AEAAJPEBG@Z`
- size: `88`
- prototype: `int __fastcall(CTSEnumeratorDll *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180034f98`

## callees

- `0x180064b44`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064b85`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180064b85`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180064b58`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180064b58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064b67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064b67`

## pseudocode

```c
int __fastcall CTSEnumeratorDll::Initialize(CTSEnumeratorDll *this, const unsigned __int16 *a2)
{
  HMODULE Library; // rax
  int result; // eax
  FARPROC ProcAddress; // rax

  Library = LoadLibraryExW(a2, 0, 0);
  *((_QWORD *)this + 3) = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetTSAudioEndpointEnumeratorForSession");
    *((_QWORD *)this + 4) = ProcAddress;
    if ( ProcAddress )
      return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180064b44  push    rbx
0x180064b46  sub     rsp, 20h
0x180064b4a  mov     rax, rdx
0x180064b4d  mov     rbx, rcx
0x180064b50  mov     rcx, rax; lpLibFileName
0x180064b53  xor     r8d, r8d; dwFlags
0x180064b56  xor     edx, edx; hFile
0x180064b58  call    cs:__imp_LoadLibraryExW
0x180064b5e  mov     [rbx+18h], rax
0x180064b62  test    rax, rax
0x180064b65  jnz     short loc_180064B7B
0x180064b67  call    cs:__imp_GetLastError
0x180064b6d  test    eax, eax
0x180064b6f  jle     short loc_180064B96
0x180064b71  movzx   eax, ax
0x180064b74  or      eax, 80070000h
0x180064b79  jmp     short loc_180064B96
0x180064b7b  lea     rdx, aGettsaudioendp; "GetTSAudioEndpointEnumeratorForSession"
0x180064b82  mov     rcx, rax; hModule
0x180064b85  call    cs:__imp_GetProcAddress
0x180064b8b  mov     [rbx+20h], rax
0x180064b8f  test    rax, rax
0x180064b92  jz      short loc_180064B67
0x180064b94  xor     eax, eax
0x180064b96  add     rsp, 20h
0x180064b9a  pop     rbx
0x180064b9b  retn
```

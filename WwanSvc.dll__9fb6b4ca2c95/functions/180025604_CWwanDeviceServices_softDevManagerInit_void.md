# CWwanDeviceServices::softDevManagerInit(void)

- ea: `0x180025604`
- end: `0x1800256be`
- name: `?softDevManagerInit@CWwanDeviceServices@@AEAAKXZ`
- size: `186`
- prototype: `unsigned int __fastcall(CWwanDeviceServices *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180021a6c`

## callees

- `0x180012300`
- `0x180025604`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025625`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180025625`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800256a6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800256a6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180025667`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180025667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025633`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025671`

## string_xrefs

- `0x180025618`: `wwansvc.dll`
- `0x180025639`: `Failed to load wwansvc dll. Error = %d`
- `0x180025645`: `CWwanDeviceServices::softDevManagerInit`
- `0x180025683`: `CWwanDeviceServices::softDevManagerInit`
- `0x180025677`: `Failed to load firmware update device string. Error = %d`

## pseudocode

```c
__int64 __fastcall CWwanDeviceServices::softDevManagerInit(CWwanDeviceServices *this)
{
  HMODULE Library; // rax
  HMODULE v3; // rsi
  __int64 LastError; // rbx

  Library = LoadLibraryExW(L"wwansvc.dll", 0, 0x822u);
  v3 = Library;
  if ( Library )
  {
    if ( LoadStringW(Library, 0x104u, (LPWSTR)this + 76, 260) )
    {
      LODWORD(LastError) = 0;
      *((_BYTE *)this + 136) = 1;
      *((_QWORD *)this + 18) = 0;
    }
    else
    {
      LastError = GetLastError();
      WwanLog::Error(
        "CWwanDeviceServices::softDevManagerInit",
        0,
        L"Failed to load firmware update device string. Error = %d",
        LastError);
    }
    FreeLibrary(v3);
  }
  else
  {
    LastError = GetLastError();
    WwanLog::Error("CWwanDeviceServices::softDevManagerInit", 0, L"Failed to load wwansvc dll. Error = %d", LastError);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180025604  mov     [rsp+arg_0], rbx
0x180025609  mov     [rsp+arg_8], rsi
0x18002560e  push    rdi
0x18002560f  sub     rsp, 20h
0x180025613  mov     rdi, rcx
0x180025616  xor     edx, edx; hFile
0x180025618  lea     rcx, LibFileName; "wwansvc.dll"
0x18002561f  mov     r8d, 822h; dwFlags
0x180025625  call    cs:__imp_LoadLibraryExW
0x18002562b  mov     rsi, rax
0x18002562e  test    rax, rax
0x180025631  jnz     short loc_180025655
0x180025633  call    cs:__imp_GetLastError
0x180025639  lea     r8, aFailedToLoadWw; "Failed to load wwansvc dll. Error = %d"
0x180025640  xor     edx, edx; struct _GUID *
0x180025642  mov     r9d, eax
0x180025645  lea     rcx, aCwwandeviceser_21; "CWwanDeviceServices::softDevManagerInit"
0x18002564c  mov     ebx, eax
0x18002564e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180025653  jmp     short loc_1800256AC
0x180025655  mov     edx, 104h; uID
0x18002565a  lea     r8, [rdi+98h]; lpBuffer
0x180025661  mov     r9d, edx; cchBufferMax
0x180025664  mov     rcx, rsi; hInstance
0x180025667  call    cs:__imp_LoadStringW
0x18002566d  test    eax, eax
0x18002566f  jnz     short loc_180025693
0x180025671  call    cs:__imp_GetLastError
0x180025677  lea     r8, aFailedToLoadFi; "Failed to load firmware update device s"...
0x18002567e  xor     edx, edx; struct _GUID *
0x180025680  mov     r9d, eax
0x180025683  lea     rcx, aCwwandeviceser_21; "CWwanDeviceServices::softDevManagerInit"
0x18002568a  mov     ebx, eax
0x18002568c  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180025691  jmp     short loc_1800256A3
0x180025693  xor     ebx, ebx
0x180025695  mov     byte ptr [rdi+88h], 1
0x18002569c  mov     [rdi+90h], rbx
0x1800256a3  mov     rcx, rsi; hLibModule
0x1800256a6  call    cs:__imp_FreeLibrary
0x1800256ac  mov     rsi, [rsp+28h+arg_8]
0x1800256b1  mov     eax, ebx
0x1800256b3  mov     rbx, [rsp+28h+arg_0]
0x1800256b8  add     rsp, 20h
0x1800256bc  pop     rdi
0x1800256bd  retn
```

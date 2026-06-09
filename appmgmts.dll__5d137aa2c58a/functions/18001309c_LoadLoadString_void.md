# LoadLoadString(void)

- ea: `0x18001309c`
- end: `0x1800130ff`
- name: `?LoadLoadString@@YAHXZ`
- size: `99`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002788`
- `0x18000d2d8`
- `0x18000f634`
- `0x1800116e4`
- `0x18001b1a0`

## callees

- `0x18001309c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800130bb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800130bb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800130ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800130ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800130d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800130d7`

## string_xrefs

- `0x1800130ae`: `user32.dll`

## pseudocode

```c
__int64 LoadLoadString(void)
{
  HMODULE Library; // rax
  HMODULE v1; // rbx

  if ( !pfnLoadStringW )
  {
    Library = LoadLibraryExW(L"user32.dll", 0, 0x800u);
    v1 = Library;
    if ( !Library )
      return 0;
    pfnLoadStringW = (int (*)(HINSTANCE, unsigned int, unsigned __int16 *, int))GetProcAddress(Library, "LoadStringW");
    if ( !pfnLoadStringW )
    {
      FreeLibrary(v1);
      return 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001309c  push    rbx
0x18001309e  sub     rsp, 20h
0x1800130a2  cmp     cs:?pfnLoadStringW@@3P6AHPEAUHINSTANCE__@@IPEAGH@ZEA, 0; int (*pfnLoadStringW)(HINSTANCE__ *,uint,ushort *,int)
0x1800130aa  jnz     short loc_1800130F4
0x1800130ac  xor     edx, edx; hFile
0x1800130ae  lea     rcx, aUser32Dll; "user32.dll"
0x1800130b5  mov     r8d, 800h; dwFlags
0x1800130bb  call    cs:__imp_LoadLibraryExW
0x1800130c1  mov     rbx, rax
0x1800130c4  test    rax, rax
0x1800130c7  jnz     short loc_1800130CD
0x1800130c9  xor     eax, eax
0x1800130cb  jmp     short loc_1800130F9
0x1800130cd  lea     rdx, aLoadstringw; "LoadStringW"
0x1800130d4  mov     rcx, rbx; hModule
0x1800130d7  call    cs:__imp_GetProcAddress
0x1800130dd  mov     cs:?pfnLoadStringW@@3P6AHPEAUHINSTANCE__@@IPEAGH@ZEA, rax; int (*pfnLoadStringW)(HINSTANCE__ *,uint,ushort *,int)
0x1800130e4  test    rax, rax
0x1800130e7  jnz     short loc_1800130F4
0x1800130e9  mov     rcx, rbx; hLibModule
0x1800130ec  call    cs:__imp_FreeLibrary
0x1800130f2  jmp     short loc_1800130C9
0x1800130f4  mov     eax, 1
0x1800130f9  add     rsp, 20h
0x1800130fd  pop     rbx
0x1800130fe  retn
```

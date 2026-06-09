# D3DPresentEngine::InitializeD3D(void)

- ea: `0x1800c0fa8`
- end: `0x1800c1116`
- name: `?InitializeD3D@D3DPresentEngine@@IEAAJXZ`
- size: `366`
- prototype: `__int64 __fastcall(D3DPresentEngine *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800c06a4`

## callees

- `0x1800c0fa8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c108c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c10c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c0fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c1031`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c108c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c10c6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c10fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c10fc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c0fd7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c1078`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c0fd7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c1078`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c101d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c10b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c101d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c10b2`

## string_xrefs

- `0x1800c0fce`: `d3d9.dll`
- `0x1800c1016`: `Direct3DCreate9Ex`
- `0x1800c106f`: `dxva2.dll`
- `0x1800c10a8`: `DXVA2CreateDirect3DDeviceManager9`

## pseudocode

```c
__int64 __fastcall D3DPresentEngine::InitializeD3D(D3DPresentEngine *this)
{
  HMODULE Library; // rax
  signed int LastError; // eax
  signed int v4; // ebx
  FARPROC ProcAddress; // rdi
  signed int v6; // eax
  HMODULE v7; // rdi
  signed int v8; // eax
  FARPROC v9; // rbp
  signed int v10; // eax

  if ( *((_QWORD *)this + 17) )
    goto LABEL_6;
  Library = LoadLibraryExW(L"d3d9.dll", 0, 0x800u);
  *((_QWORD *)this + 17) = Library;
  if ( Library )
    goto LABEL_6;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_6:
    ProcAddress = GetProcAddress(*((HMODULE *)this + 17), "Direct3DCreate9Ex");
    if ( ProcAddress )
      goto LABEL_10;
    v6 = GetLastError();
    v4 = v6;
    if ( v6 > 0 )
      v4 = (unsigned __int16)v6 | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_10:
      v4 = ((__int64 (__fastcall *)(__int64, char *))ProcAddress)(32, (char *)this + 96);
      if ( v4 >= 0 )
      {
        v7 = LoadLibraryExW(L"dxva2.dll", 0, 0x800u);
        if ( v7 )
          goto LABEL_15;
        v8 = GetLastError();
        v4 = v8;
        if ( v8 > 0 )
          v4 = (unsigned __int16)v8 | 0x80070000;
        if ( v4 >= 0 )
        {
LABEL_15:
          v9 = GetProcAddress(v7, "DXVA2CreateDirect3DDeviceManager9");
          if ( v9 )
            goto LABEL_19;
          v10 = GetLastError();
          v4 = v10;
          if ( v10 > 0 )
            v4 = (unsigned __int16)v10 | 0x80070000;
          if ( v4 >= 0 )
LABEL_19:
            v4 = ((__int64 (__fastcall *)(char *, char *))v9)((char *)this + 8, (char *)this + 112);
          if ( v7 )
            FreeLibrary(v7);
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800c0fa8  push    rbx
0x1800c0faa  push    rbp
0x1800c0fab  push    rsi
0x1800c0fac  push    rdi
0x1800c0fad  push    r14
0x1800c0faf  sub     rsp, 20h
0x1800c0fb3  cmp     qword ptr [rcx+88h], 0
0x1800c0fbb  mov     rsi, rcx
0x1800c0fbe  mov     ebp, 800h
0x1800c0fc3  mov     r14d, 80070000h
0x1800c0fc9  jnz     short loc_1800C100F
0x1800c0fcb  mov     r8d, ebp; dwFlags
0x1800c0fce  lea     rcx, aD3d9Dll; "d3d9.dll"
0x1800c0fd5  xor     edx, edx; hFile
0x1800c0fd7  call    cs:__imp_LoadLibraryExW
0x1800c0fde  nop     dword ptr [rax+rax+00h]
0x1800c0fe3  mov     [rsi+88h], rax
0x1800c0fea  test    rax, rax
0x1800c0fed  jnz     short loc_1800C100F
0x1800c0fef  call    cs:__imp_GetLastError
0x1800c0ff6  nop     dword ptr [rax+rax+00h]
0x1800c0ffb  mov     ebx, eax
0x1800c0ffd  test    eax, eax
0x1800c0fff  jle     short loc_1800C1007
0x1800c1001  movzx   ebx, ax
0x1800c1004  or      ebx, r14d
0x1800c1007  test    ebx, ebx
0x1800c1009  js      loc_1800C1108
0x1800c100f  mov     rcx, [rsi+88h]; hModule
0x1800c1016  lea     rdx, aDirect3dcreate; "Direct3DCreate9Ex"
0x1800c101d  call    cs:__imp_GetProcAddress
0x1800c1024  nop     dword ptr [rax+rax+00h]
0x1800c1029  mov     rdi, rax
0x1800c102c  test    rax, rax
0x1800c102f  jnz     short loc_1800C1051
0x1800c1031  call    cs:__imp_GetLastError
0x1800c1038  nop     dword ptr [rax+rax+00h]
0x1800c103d  mov     ebx, eax
0x1800c103f  test    eax, eax
0x1800c1041  jle     short loc_1800C1049
0x1800c1043  movzx   ebx, ax
0x1800c1046  or      ebx, r14d
0x1800c1049  test    ebx, ebx
0x1800c104b  js      loc_1800C1108
0x1800c1051  lea     rdx, [rsi+60h]
0x1800c1055  mov     ecx, 20h ; ' '
0x1800c105a  mov     rax, rdi
0x1800c105d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1062  mov     ebx, eax
0x1800c1064  test    eax, eax
0x1800c1066  js      loc_1800C1108
0x1800c106c  mov     r8d, ebp; dwFlags
0x1800c106f  lea     rcx, aDxva2Dll; "dxva2.dll"
0x1800c1076  xor     edx, edx; hFile
0x1800c1078  call    cs:__imp_LoadLibraryExW
0x1800c107f  nop     dword ptr [rax+rax+00h]
0x1800c1084  mov     rdi, rax
0x1800c1087  test    rax, rax
0x1800c108a  jnz     short loc_1800C10A8
0x1800c108c  call    cs:__imp_GetLastError
0x1800c1093  nop     dword ptr [rax+rax+00h]
0x1800c1098  mov     ebx, eax
0x1800c109a  test    eax, eax
0x1800c109c  jle     short loc_1800C10A4
0x1800c109e  movzx   ebx, ax
0x1800c10a1  or      ebx, r14d
0x1800c10a4  test    ebx, ebx
0x1800c10a6  js      short loc_1800C1108
0x1800c10a8  lea     rdx, aDxva2createdir; "DXVA2CreateDirect3DDeviceManager9"
0x1800c10af  mov     rcx, rdi; hModule
0x1800c10b2  call    cs:__imp_GetProcAddress
0x1800c10b9  nop     dword ptr [rax+rax+00h]
0x1800c10be  mov     rbp, rax
0x1800c10c1  test    rax, rax
0x1800c10c4  jnz     short loc_1800C10E2
0x1800c10c6  call    cs:__imp_GetLastError
0x1800c10cd  nop     dword ptr [rax+rax+00h]
0x1800c10d2  mov     ebx, eax
0x1800c10d4  test    eax, eax
0x1800c10d6  jle     short loc_1800C10DE
0x1800c10d8  movzx   ebx, ax
0x1800c10db  or      ebx, r14d
0x1800c10de  test    ebx, ebx
0x1800c10e0  js      short loc_1800C10F4
0x1800c10e2  lea     rdx, [rsi+70h]
0x1800c10e6  mov     rax, rbp
0x1800c10e9  lea     rcx, [rsi+8]
0x1800c10ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c10f2  mov     ebx, eax
0x1800c10f4  test    rdi, rdi
0x1800c10f7  jz      short loc_1800C1108
0x1800c10f9  mov     rcx, rdi; hLibModule
0x1800c10fc  call    cs:__imp_FreeLibrary
0x1800c1103  nop     dword ptr [rax+rax+00h]
0x1800c1108  mov     eax, ebx
0x1800c110a  add     rsp, 20h
0x1800c110e  pop     r14
0x1800c1110  pop     rdi
0x1800c1111  pop     rsi
0x1800c1112  pop     rbp
0x1800c1113  pop     rbx
0x1800c1114  retn
```

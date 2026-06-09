# DX11Lib::Init(void)

- ea: `0x18001ea44`
- end: `0x18001eafd`
- name: `?Init@DX11Lib@@QEAAHXZ`
- size: `185`
- prototype: `__int64 __fastcall(DX11Lib *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001d18c`

## callees

- `0x1800174c0`
- `0x18001ea44`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ead2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ead2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001eaa5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001eaa5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ea8d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ea8d`

## string_xrefs

- `0x18001ea6a`: `D3D11.DLL`
- `0x18001ea9b`: `D3D11CreateDevice`

## pseudocode

```c
__int64 __fastcall DX11Lib::Init(DX11Lib *this)
{
  __int64 v1; // rbx
  HMODULE Library; // rax
  __int64 v3; // rdi
  FARPROC ProcAddress; // rax
  HMODULE v5; // rdi
  WCHAR LibFileName[12]; // [rsp+20h] [rbp-28h] BYREF

  v1 = qword_18006A3C8;
  if ( !*(_DWORD *)(qword_18006A3C8 + 8) )
  {
    wcscpy(LibFileName, L"D3D11.DLL");
    Library = LoadLibraryExW(LibFileName, 0, 0x800u);
    v3 = (__int64)Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "D3D11CreateDevice");
      if ( ProcAddress )
        _InterlockedExchange64((volatile __int64 *)v1, (__int64)ProcAddress);
      _InterlockedExchange((volatile __int32 *)(v1 + 12), *(_QWORD *)v1 != 0);
      _InterlockedExchange((volatile __int32 *)(v1 + 8), 1);
      v5 = (HMODULE)_InterlockedExchange64((volatile __int64 *)(v1 + 16), v3);
      if ( v5 )
        FreeLibrary(v5);
    }
    else
    {
      _InterlockedExchange((volatile __int32 *)(v1 + 8), 1);
    }
  }
  return *(unsigned int *)(v1 + 12);
}

```

## disassembly

```asm
0x18001ea44  mov     [rsp+arg_0], rbx
0x18001ea49  push    rdi
0x18001ea4a  sub     rsp, 40h
0x18001ea4e  mov     rax, cs:__security_cookie
0x18001ea55  xor     rax, rsp
0x18001ea58  mov     [rsp+48h+var_10], rax
0x18001ea5d  mov     rbx, cs:qword_18006A3C8
0x18001ea64  cmp     dword ptr [rbx+8], 0
0x18001ea68  jnz     short loc_18001EAE2
0x18001ea6a  movups  xmm0, xmmword ptr cs:aD3d11Dll; "D3D11.DLL"
0x18001ea71  mov     eax, dword ptr cs:aD3d11Dll+10h; "L"
0x18001ea77  lea     rcx, [rsp+48h+LibFileName]; lpLibFileName
0x18001ea7c  xor     edx, edx; hFile
0x18001ea7e  mov     [rsp+48h+var_18], eax
0x18001ea82  mov     r8d, 800h; dwFlags
0x18001ea88  movups  xmmword ptr [rsp+48h+LibFileName], xmm0
0x18001ea8d  call    cs:__imp_LoadLibraryExW
0x18001ea93  mov     rdi, rax
0x18001ea96  test    rax, rax
0x18001ea99  jz      short loc_18001EADA
0x18001ea9b  lea     rdx, ProcName; "D3D11CreateDevice"
0x18001eaa2  mov     rcx, rax; hModule
0x18001eaa5  call    cs:__imp_GetProcAddress
0x18001eaab  test    rax, rax
0x18001eaae  jz      short loc_18001EAB3
0x18001eab0  xchg    rax, [rbx]
0x18001eab3  xor     eax, eax
0x18001eab5  mov     edx, 1
0x18001eaba  cmp     [rbx], rax
0x18001eabd  setnz   al
0x18001eac0  xchg    eax, [rbx+0Ch]
0x18001eac3  xchg    edx, [rbx+8]
0x18001eac6  xchg    rdi, [rbx+10h]
0x18001eaca  test    rdi, rdi
0x18001eacd  jz      short loc_18001EAE2
0x18001eacf  mov     rcx, rdi; hLibModule
0x18001ead2  call    cs:__imp_FreeLibrary
0x18001ead8  jmp     short loc_18001EAE2
0x18001eada  mov     edx, 1
0x18001eadf  xchg    edx, [rbx+8]
0x18001eae2  mov     eax, [rbx+0Ch]
0x18001eae5  mov     rcx, [rsp+48h+var_10]
0x18001eaea  xor     rcx, rsp; StackCookie
0x18001eaed  call    __security_check_cookie
0x18001eaf2  mov     rbx, [rsp+48h+arg_0]
0x18001eaf7  add     rsp, 40h
0x18001eafb  pop     rdi
0x18001eafc  retn
```

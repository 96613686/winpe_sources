# LoadLibraryFromSystemDirectory

- ea: `0x180050254`
- end: `0x180050397`
- name: `LoadLibraryFromSystemDirectory`
- size: `323`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800503a0`
- `0x180053fac`

## callees

- `0x180033504`
- `0x18004554c`
- `0x1800487e0`
- `0x1800491dc`
- `0x180050254`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800502b1`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800502b1`
- `KERNEL32!LoadLibraryW` at `0x180050348`
- `KERNEL32!LoadLibraryW` at `0x180050348`
- `KERNEL32!GetSystemDirectoryW` at `0x1800502f9`
- `KERNEL32!GetSystemDirectoryW` at `0x1800502f9`
- `KERNEL32!GetLastError` at `0x180050353`
- `KERNEL32!GetLastError` at `0x180050353`

## pseudocode

```c
__int64 __fastcall LoadLibraryFromSystemDirectory(__int64 a1, HMODULE *a2)
{
  HRESULT v3; // ebx
  wchar_t *v4; // rax
  __int64 SystemDirectoryW; // r9
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  size_t pcchLength[2]; // [rsp+20h] [rbp-238h] BYREF
  wchar_t Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  pcchLength[0] = 0;
  if ( a2 )
  {
    v4 = wcsstr(L"winspool.drv", L"\\");
    *a2 = 0;
    if ( v4 )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      v3 = StringCchLengthW(L"winspool.drv", 0x103u, pcchLength);
      if ( v3 >= 0 )
      {
        SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
        if ( (unsigned __int64)(SystemDirectoryW - 1) > 0x101 || SystemDirectoryW + pcchLength[0] >= 0x103 )
        {
          return (unsigned int)-2147467259;
        }
        else
        {
          Buffer[SystemDirectoryW] = 92;
          v3 = StringCchCatW(Buffer, 0x104u, L"winspool.drv");
          if ( v3 >= 0 )
          {
            LibraryW = LoadLibraryW(Buffer);
            if ( LibraryW )
            {
              *a2 = LibraryW;
            }
            else
            {
              LastError = GetLastError();
              v3 = LastError;
              if ( LastError > 0 )
                return (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
      }
    }
  }
  else
  {
    v3 = -2147024809;
    MEMORY[0] = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180050254  mov     [rsp+arg_0], rbx
0x180050259  push    rdi
0x18005025a  sub     rsp, 250h
0x180050261  mov     rax, cs:__security_cookie
0x180050268  xor     rax, rsp
0x18005026b  mov     [rsp+258h+var_18], rax
0x180050273  mov     rdi, rdx
0x180050276  lea     rcx, [rsp+258h+Buffer]; void *
0x18005027b  xor     edx, edx; Val
0x18005027d  mov     r8d, 208h; Size
0x180050283  call    memset_0
0x180050288  mov     [rsp+258h+pcchLength], 0
0x180050291  test    rdi, rdi
0x180050294  jnz     short loc_1800502A3
0x180050296  mov     ebx, 80070057h
0x18005029b  mov     [rdi], rdi
0x18005029e  jmp     loc_180050374
0x1800502a3  lea     rdx, asc_180080C28; "\\"
0x1800502aa  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x1800502b1  call    cs:__imp_wcsstr
0x1800502b7  mov     qword ptr [rdi], 0
0x1800502be  test    rax, rax
0x1800502c1  jz      short loc_1800502CD
0x1800502c3  mov     ebx, 80070057h
0x1800502c8  jmp     loc_180050374
0x1800502cd  lea     r8, [rsp+258h+pcchLength]; pcchLength
0x1800502d2  mov     edx, 103h; cchMax
0x1800502d7  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x1800502de  call    StringCchLengthW
0x1800502e3  mov     ebx, eax
0x1800502e5  test    eax, eax
0x1800502e7  js      loc_180050374
0x1800502ed  mov     ebx, 104h
0x1800502f2  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x1800502f7  mov     edx, ebx; uSize
0x1800502f9  call    cs:__imp_GetSystemDirectoryW
0x1800502ff  mov     r9d, eax
0x180050302  lea     rax, [r9-1]
0x180050306  cmp     rax, 101h
0x18005030c  ja      short loc_18005036F
0x18005030e  mov     rcx, [rsp+258h+pcchLength]
0x180050313  add     rcx, r9
0x180050316  cmp     rcx, 103h
0x18005031d  jnb     short loc_18005036F
0x18005031f  mov     eax, 5Ch ; '\'
0x180050324  lea     r8, aWinspoolDrv_0; "winspool.drv"
0x18005032b  mov     edx, ebx; cchDest
0x18005032d  mov     [rsp+r9*2+258h+Buffer], ax
0x180050333  lea     rcx, [rsp+258h+Buffer]; pszDest
0x180050338  call    StringCchCatW
0x18005033d  mov     ebx, eax
0x18005033f  test    eax, eax
0x180050341  js      short loc_180050374
0x180050343  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x180050348  call    cs:__imp_LoadLibraryW
0x18005034e  test    rax, rax
0x180050351  jnz     short loc_18005036A
0x180050353  call    cs:__imp_GetLastError
0x180050359  mov     ebx, eax
0x18005035b  test    eax, eax
0x18005035d  jle     short loc_180050374
0x18005035f  movzx   ebx, ax
0x180050362  or      ebx, 80070000h
0x180050368  jmp     short loc_180050374
0x18005036a  mov     [rdi], rax
0x18005036d  jmp     short loc_180050374
0x18005036f  mov     ebx, 80004005h
0x180050374  mov     eax, ebx
0x180050376  mov     rcx, [rsp+258h+var_18]
0x18005037e  xor     rcx, rsp; StackCookie
0x180050381  call    __security_check_cookie
0x180050386  mov     rbx, [rsp+258h+arg_0]
0x18005038e  add     rsp, 250h
0x180050395  pop     rdi
0x180050396  retn
```

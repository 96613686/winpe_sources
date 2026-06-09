# CreateInfFile(HINSTANCE__ *,ushort *,ulong *)

- ea: `0x180002928`
- end: `0x180002acd`
- name: `?CreateInfFile@@YAJPEAUHINSTANCE__@@PEAGPEAK@Z`
- size: `421`
- prototype: `__int64 __fastcall(HINSTANCE hModule, WCHAR *lpFileName, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003be0`

## callees

- `0x180002928`
- `0x180008524`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetTempPath2W` at `0x18000298c`
- `KERNEL32!GetTempPath2W` at `0x18000298c`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800029af`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800029af`
- `KERNEL32!GetTempFileNameW` at `0x1800029c7`
- `KERNEL32!GetTempFileNameW` at `0x1800029c7`
- `KERNEL32!FindResourceW` at `0x1800029e2`
- `KERNEL32!FindResourceW` at `0x1800029e2`
- `KERNEL32!SizeofResource` at `0x1800029fa`
- `KERNEL32!SizeofResource` at `0x1800029fa`
- `KERNEL32!LockResource` at `0x180002a11`
- `KERNEL32!LockResource` at `0x180002a11`
- `KERNEL32!LoadResource` at `0x180002a08`
- `KERNEL32!LoadResource` at `0x180002a08`
- `KERNEL32!WritePrivateProfileStringW` at `0x180002a2d`
- `KERNEL32!WritePrivateProfileStringW` at `0x180002a2d`
- `KERNEL32!CreateFileW` at `0x180002a5a`
- `KERNEL32!CreateFileW` at `0x180002a5a`
- `KERNEL32!WriteFile` at `0x180002a80`
- `KERNEL32!WriteFile` at `0x180002a80`
- `KERNEL32!CloseHandle` at `0x180002a9e`
- `KERNEL32!CloseHandle` at `0x180002a9e`

## pseudocode

```c
__int64 __fastcall CreateInfFile(HINSTANCE hModule, WCHAR *lpFileName, unsigned int *a3)
{
  unsigned int v6; // esi
  HRSRC ResourceW; // rax
  HRSRC v8; // rdi
  DWORD v9; // ebp
  HGLOBAL Resource; // rax
  const void *v11; // r14
  HANDLE FileW; // rax
  void *v13; // rdi
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-258h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-248h] BYREF

  v6 = -2147467259;
  memset_0(Buffer, 0, 0x208u);
  NumberOfBytesWritten = 0;
  if ( a3 )
    *a3 = 0;
  if ( (unsigned int)GetTempPath2W(260, Buffer) <= 0x104 )
  {
    if ( !(unsigned int)IsGoodDir(Buffer) )
      GetWindowsDirectoryW(Buffer, 0x104u);
    if ( GetTempFileNameW(Buffer, L"RGI", 0, lpFileName) )
    {
      ResourceW = FindResourceW(hModule, L"REGINST", L"REGINST");
      v8 = ResourceW;
      if ( ResourceW )
      {
        v9 = SizeofResource(hModule, ResourceW);
        Resource = LoadResource(hModule, v8);
        v11 = LockResource(Resource);
        if ( v11 )
        {
          WritePrivateProfileStringW(0, 0, 0, lpFileName);
          FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
          v13 = FileW;
          if ( FileW != (HANDLE)-1LL )
          {
            if ( WriteFile(FileW, v11, v9, &NumberOfBytesWritten, 0) && NumberOfBytesWritten == v9 )
            {
              if ( a3 )
                *a3 = NumberOfBytesWritten;
              v6 = 0;
            }
            CloseHandle(v13);
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180002928  mov     [rsp+arg_18], rbx
0x18000292d  push    rbp
0x18000292e  push    rsi
0x18000292f  push    rdi
0x180002930  push    r14
0x180002932  push    r15
0x180002934  sub     rsp, 270h
0x18000293b  mov     rax, cs:__security_cookie
0x180002942  xor     rax, rsp
0x180002945  mov     [rsp+298h+var_38], rax
0x18000294d  mov     rbx, r8
0x180002950  mov     r15, rdx
0x180002953  mov     r14, rcx
0x180002956  xor     edx, edx; Val
0x180002958  mov     r8d, 208h; Size
0x18000295e  lea     rcx, [rsp+298h+Buffer]; void *
0x180002963  mov     esi, 80004005h
0x180002968  call    memset_0
0x18000296d  mov     [rsp+298h+NumberOfBytesWritten], 0
0x180002975  test    rbx, rbx
0x180002978  jz      short loc_180002980
0x18000297a  mov     dword ptr [rbx], 0
0x180002980  mov     edi, 104h
0x180002985  lea     rdx, [rsp+298h+Buffer]
0x18000298a  mov     ecx, edi
0x18000298c  call    cs:__imp_GetTempPath2W
0x180002992  cmp     eax, edi
0x180002994  ja      loc_180002AA4
0x18000299a  lea     rcx, [rsp+298h+Buffer]; unsigned __int16 *
0x18000299f  call    ?IsGoodDir@@YAHPEBG@Z; IsGoodDir(ushort const *)
0x1800029a4  test    eax, eax
0x1800029a6  jnz     short loc_1800029B5
0x1800029a8  mov     edx, edi; uSize
0x1800029aa  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x1800029af  call    cs:__imp_GetWindowsDirectoryW
0x1800029b5  mov     r9, r15; lpTempFileName
0x1800029b8  lea     rdx, PrefixString; "RGI"
0x1800029bf  xor     r8d, r8d; uUnique
0x1800029c2  lea     rcx, [rsp+298h+Buffer]; lpPathName
0x1800029c7  call    cs:__imp_GetTempFileNameW
0x1800029cd  test    eax, eax
0x1800029cf  jz      loc_180002AA4
0x1800029d5  lea     rdx, Type; "REGINST"
0x1800029dc  mov     rcx, r14; hModule
0x1800029df  mov     r8, rdx; lpType
0x1800029e2  call    cs:__imp_FindResourceW
0x1800029e8  mov     rdi, rax
0x1800029eb  test    rax, rax
0x1800029ee  jz      loc_180002AA4
0x1800029f4  mov     rdx, rax; hResInfo
0x1800029f7  mov     rcx, r14; hModule
0x1800029fa  call    cs:__imp_SizeofResource
0x180002a00  mov     rdx, rdi; hResInfo
0x180002a03  mov     rcx, r14; hModule
0x180002a06  mov     ebp, eax
0x180002a08  call    cs:__imp_LoadResource
0x180002a0e  mov     rcx, rax; hResData
0x180002a11  call    cs:__imp_LockResource
0x180002a17  mov     r14, rax
0x180002a1a  test    rax, rax
0x180002a1d  jz      loc_180002AA4
0x180002a23  mov     r9, r15; lpFileName
0x180002a26  xor     r8d, r8d; lpString
0x180002a29  xor     edx, edx; lpKeyName
0x180002a2b  xor     ecx, ecx; lpAppName
0x180002a2d  call    cs:__imp_WritePrivateProfileStringW
0x180002a33  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x180002a3c  xor     r9d, r9d; lpSecurityAttributes
0x180002a3f  mov     [rsp+298h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180002a47  xor     r8d, r8d; dwShareMode
0x180002a4a  mov     edx, 40000000h; dwDesiredAccess
0x180002a4f  mov     [rsp+298h+dwCreationDisposition], 2; dwCreationDisposition
0x180002a57  mov     rcx, r15; lpFileName
0x180002a5a  call    cs:__imp_CreateFileW
0x180002a60  mov     rdi, rax
0x180002a63  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002a67  jz      short loc_180002AA4
0x180002a69  lea     r9, [rsp+298h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180002a6e  mov     qword ptr [rsp+298h+dwCreationDisposition], 0; lpOverlapped
0x180002a77  mov     r8d, ebp; nNumberOfBytesToWrite
0x180002a7a  mov     rdx, r14; lpBuffer
0x180002a7d  mov     rcx, rax; hFile
0x180002a80  call    cs:__imp_WriteFile
0x180002a86  test    eax, eax
0x180002a88  jz      short loc_180002A9B
0x180002a8a  mov     ecx, [rsp+298h+NumberOfBytesWritten]
0x180002a8e  cmp     ecx, ebp
0x180002a90  jnz     short loc_180002A9B
0x180002a92  test    rbx, rbx
0x180002a95  jz      short loc_180002A99
0x180002a97  mov     [rbx], ecx
0x180002a99  xor     esi, esi
0x180002a9b  mov     rcx, rdi; hObject
0x180002a9e  call    cs:__imp_CloseHandle
0x180002aa4  mov     eax, esi
0x180002aa6  mov     rcx, [rsp+298h+var_38]
0x180002aae  xor     rcx, rsp; StackCookie
0x180002ab1  call    __security_check_cookie
0x180002ab6  mov     rbx, [rsp+298h+arg_18]
0x180002abe  add     rsp, 270h
0x180002ac5  pop     r15
0x180002ac7  pop     r14
0x180002ac9  pop     rdi
0x180002aca  pop     rsi
0x180002acb  pop     rbp
0x180002acc  retn
```

# CBufferedFile::Open(CBufferedFile::BFILE_OPEN_MODE,CBufferedFile::BFILE_STATUS_FLAGS *)

- ea: `0x18003e850`
- end: `0x18003e99e`
- name: `?Open@CBufferedFile@@UEAAJW4BFILE_OPEN_MODE@1@PEAW4BFILE_STATUS_FLAGS@1@@Z`
- size: `334`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x1800015d0`
- `0x180001ee8`
- `0x18003e850`
- `0x180040010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18003e8dd`
- `KERNEL32!WideCharToMultiByte` at `0x18003e8dd`
- `KERNEL32!CreateFileA` at `0x18003e908`
- `KERNEL32!CreateFileA` at `0x18003e93d`
- `KERNEL32!CreateFileA` at `0x18003e908`
- `KERNEL32!CreateFileA` at `0x18003e93d`

## pseudocode

```c
__int64 __fastcall CBufferedFile::Open(__int64 a1, int a2, _DWORD *a3)
{
  DWORD v3; // ebx
  int v6; // edx
  HANDLE FileA; // rax
  HANDLE v8; // rax
  CHAR MultiByteStr[272]; // [rsp+40h] [rbp-128h] BYREF

  v3 = 0;
  if ( a2 )
  {
    v6 = a2 - 1;
    if ( v6 )
    {
      if ( v6 == 1 )
        v3 = 2;
    }
    else
    {
      v3 = 4;
    }
  }
  else
  {
    v3 = 3;
  }
  memset_0(MultiByteStr, 0, 0x104u);
  WideCharToMultiByte(0, 0, *(LPCWCH *)(a1 + 16), -1, MultiByteStr, 260, 0, 0);
  FileA = CreateFileA(MultiByteStr, 0xC0000000, 0, 0, v3, 0x10000080u, 0);
  *(_QWORD *)(a1 + 8) = FileA;
  if ( FileA != (HANDLE)-1LL )
    return (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a1 + 48LL))(a1, a3);
  v8 = CreateFileA(MultiByteStr, 0x80000000, 0, 0, v3, 0x10000080u, 0);
  *(_QWORD *)(a1 + 8) = v8;
  if ( v8 != (HANDLE)-1LL )
    return (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)a1 + 48LL))(a1, a3);
  *(_QWORD *)(a1 + 8) = 0;
  if ( a3 )
    *a3 = 8;
  return 2147500037LL;
}

```

## disassembly

```asm
0x18003e850  mov     [rsp+arg_8], rbx
0x18003e855  mov     [rsp+arg_18], rsi
0x18003e85a  push    rdi
0x18003e85b  sub     rsp, 160h
0x18003e862  mov     rax, cs:__security_cookie
0x18003e869  xor     rax, rsp
0x18003e86c  mov     [rsp+168h+var_18], rax
0x18003e874  xor     ebx, ebx
0x18003e876  mov     rsi, r8
0x18003e879  mov     rdi, rcx
0x18003e87c  test    edx, edx
0x18003e87e  jz      short loc_18003E896
0x18003e880  sub     edx, 1
0x18003e883  jz      short loc_18003E88F
0x18003e885  cmp     edx, 1
0x18003e888  jnz     short loc_18003E89B
0x18003e88a  lea     ebx, [rdx+1]
0x18003e88d  jmp     short loc_18003E89B
0x18003e88f  mov     ebx, 4
0x18003e894  jmp     short loc_18003E89B
0x18003e896  mov     ebx, 3
0x18003e89b  xor     edx, edx; Val
0x18003e89d  lea     rcx, [rsp+168h+MultiByteStr]; void *
0x18003e8a2  mov     r8d, 104h; Size
0x18003e8a8  call    memset_0
0x18003e8ad  mov     r8, [rdi+10h]; lpWideCharStr
0x18003e8b1  lea     rax, [rsp+168h+MultiByteStr]
0x18003e8b6  mov     [rsp+168h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18003e8bf  or      r9d, 0FFFFFFFFh; cchWideChar
0x18003e8c3  mov     [rsp+168h+lpDefaultChar], 0; lpDefaultChar
0x18003e8cc  xor     edx, edx; dwFlags
0x18003e8ce  mov     [rsp+168h+cbMultiByte], 104h; cbMultiByte
0x18003e8d6  xor     ecx, ecx; CodePage
0x18003e8d8  mov     [rsp+168h+lpMultiByteStr], rax; lpMultiByteStr
0x18003e8dd  call    cs:__imp_WideCharToMultiByte
0x18003e8e3  mov     [rsp+168h+lpDefaultChar], 0; hTemplateFile
0x18003e8ec  lea     rcx, [rsp+168h+MultiByteStr]; lpFileName
0x18003e8f1  mov     [rsp+168h+cbMultiByte], 10000080h; dwFlagsAndAttributes
0x18003e8f9  xor     r9d, r9d; lpSecurityAttributes
0x18003e8fc  xor     r8d, r8d; dwShareMode
0x18003e8ff  mov     dword ptr [rsp+168h+lpMultiByteStr], ebx; dwCreationDisposition
0x18003e903  mov     edx, 0C0000000h; dwDesiredAccess
0x18003e908  call    cs:__imp_CreateFileA
0x18003e90e  mov     [rdi+8], rax
0x18003e912  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e916  jnz     short loc_18003E967
0x18003e918  mov     [rsp+168h+lpDefaultChar], 0; hTemplateFile
0x18003e921  lea     rcx, [rsp+168h+MultiByteStr]; lpFileName
0x18003e926  mov     [rsp+168h+cbMultiByte], 10000080h; dwFlagsAndAttributes
0x18003e92e  xor     r9d, r9d; lpSecurityAttributes
0x18003e931  xor     r8d, r8d; dwShareMode
0x18003e934  mov     dword ptr [rsp+168h+lpMultiByteStr], ebx; dwCreationDisposition
0x18003e938  mov     edx, 80000000h; dwDesiredAccess
0x18003e93d  call    cs:__imp_CreateFileA
0x18003e943  mov     [rdi+8], rax
0x18003e947  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003e94b  jnz     short loc_18003E967
0x18003e94d  mov     qword ptr [rdi+8], 0
0x18003e955  test    rsi, rsi
0x18003e958  jz      short loc_18003E960
0x18003e95a  mov     dword ptr [rsi], 8
0x18003e960  mov     eax, 80004005h
0x18003e965  jmp     short loc_18003E979
0x18003e967  mov     rax, [rdi]
0x18003e96a  mov     rdx, rsi
0x18003e96d  mov     rcx, rdi
0x18003e970  mov     rax, [rax+30h]
0x18003e974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e979  mov     rcx, [rsp+168h+var_18]
0x18003e981  xor     rcx, rsp; StackCookie
0x18003e984  call    __security_check_cookie
0x18003e989  lea     r11, [rsp+168h+var_8]
0x18003e991  mov     rbx, [r11+18h]
0x18003e995  mov     rsi, [r11+28h]
0x18003e999  mov     rsp, r11
0x18003e99c  pop     rdi
0x18003e99d  retn
```

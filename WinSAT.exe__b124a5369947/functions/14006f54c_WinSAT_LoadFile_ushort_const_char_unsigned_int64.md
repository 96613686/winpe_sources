# WinSAT::LoadFile(ushort const *,char * *,unsigned __int64 *)

- ea: `0x14006f54c`
- end: `0x14006f6cd`
- name: `?LoadFile@WinSAT@@YAKPEBGPEAPEADPEA_K@Z`
- size: `385`
- prototype: `unsigned int __fastcall(WinSAT *__hidden this, const unsigned __int16 *, char **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14006f6d4`

## callees

- `0x140001abc`
- `0x140003164`
- `0x140004348`
- `0x1400085b4`
- `0x140017af0`
- `0x14006f54c`

## import_xrefs

- `KERNEL32!ReadFile` at `0x14006f66c`
- `KERNEL32!ReadFile` at `0x14006f66c`
- `KERNEL32!CreateFileW` at `0x14006f59d`
- `KERNEL32!CreateFileW` at `0x14006f59d`
- `KERNEL32!GetFileSizeEx` at `0x14006f5f3`
- `KERNEL32!GetFileSizeEx` at `0x14006f5f3`
- `KERNEL32!CloseHandle` at `0x14006f695`
- `KERNEL32!CloseHandle` at `0x14006f6a2`
- `KERNEL32!CloseHandle` at `0x14006f695`
- `KERNEL32!CloseHandle` at `0x14006f6a2`
- `KERNEL32!GetLastError` at `0x14006f5de`
- `KERNEL32!GetLastError` at `0x14006f5fd`
- `KERNEL32!GetLastError` at `0x14006f682`
- `KERNEL32!GetLastError` at `0x14006f5de`
- `KERNEL32!GetLastError` at `0x14006f5fd`
- `KERNEL32!GetLastError` at `0x14006f682`

## string_xrefs

- `0x14006f5b8`: `Unabled to open file: `

## pseudocode

```c
__int64 __fastcall WinSAT::LoadFile(const WCHAR *this, unsigned __int16 *a2, char **a3, unsigned __int64 *a4)
{
  HANDLE FileW; // rax
  void *v8; // rbp
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  DWORD LastError; // ebx
  char *QuadPart; // rbx
  char *v14; // rdi
  unsigned __int64 i; // rsi
  DWORD v16; // r8d
  __int64 result; // rax
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-38h] BYREF
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+20h] BYREF

  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  FileW = CreateFileW(this, 0x80000000, 1u, 0, 3u, 0, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v9 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v9 + 240, L"Unabled to open file: ");
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v10, this);
    std::endl(v11);
    return GetLastError();
  }
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    LastError = GetLastError();
LABEL_16:
    CloseHandle(v8);
    return LastError;
  }
  QuadPart = (char *)FileSize.QuadPart;
  if ( FileSize.QuadPart == -1 )
  {
    LastError = 223;
    goto LABEL_16;
  }
  v14 = (char *)operator new[](FileSize.QuadPart + 1, (const struct std::nothrow_t *)std::nothrow);
  if ( !v14 )
  {
    LastError = 8;
    goto LABEL_16;
  }
  for ( i = 0; i < (unsigned __int64)QuadPart; i += NumberOfBytesRead )
  {
    v16 = (_DWORD)QuadPart - i;
    if ( (unsigned __int64)&QuadPart[-i] > 0xFFFFFFFF )
      v16 = -1;
    if ( !ReadFile(v8, &v14[i], v16, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      operator delete(v14);
      goto LABEL_16;
    }
  }
  CloseHandle(v8);
  result = 0;
  *(_QWORD *)a2 = v14;
  *a3 = QuadPart;
  v14[(_QWORD)QuadPart] = 0;
  return result;
}

```

## disassembly

```asm
0x14006f54c  mov     rax, rsp
0x14006f54f  mov     [rax+8], rbx
0x14006f553  mov     [rax+10h], rbp
0x14006f557  push    rsi
0x14006f558  push    rdi
0x14006f559  push    r13
0x14006f55b  push    r14
0x14006f55d  push    r15
0x14006f55f  sub     rsp, 50h
0x14006f563  mov     qword ptr [rax-48h], 0
0x14006f56b  xor     r9d, r9d; lpSecurityAttributes
0x14006f56e  mov     r14, r8
0x14006f571  mov     dword ptr [rax-50h], 0
0x14006f578  mov     r15, rdx
0x14006f57b  mov     dword ptr [rax+20h], 0
0x14006f582  mov     edx, 80000000h; dwDesiredAccess
0x14006f587  mov     qword ptr [rax-38h], 0
0x14006f58f  lea     r8d, [r9+1]; dwShareMode
0x14006f593  mov     dword ptr [rax-58h], 3
0x14006f59a  mov     rbx, rcx
0x14006f59d  call    cs:__imp_CreateFileW
0x14006f5a3  mov     rbp, rax
0x14006f5a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14006f5aa  jnz     short loc_14006F5EB
0x14006f5ac  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x14006f5b3  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14006f5b8  lea     rdx, aUnabledToOpenF; "Unabled to open file: "
0x14006f5bf  lea     rcx, [rax+0F0h]
0x14006f5c6  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006f5cb  mov     rcx, rax
0x14006f5ce  mov     rdx, rbx
0x14006f5d1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14006f5d6  mov     rcx, rax
0x14006f5d9  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14006f5de  call    cs:__imp_GetLastError
0x14006f5e4  mov     ebx, eax
0x14006f5e6  jmp     loc_14006F69B
0x14006f5eb  lea     rdx, [rsp+78h+FileSize]; lpFileSize
0x14006f5f0  mov     rcx, rbp; hFile
0x14006f5f3  call    cs:__imp_GetFileSizeEx
0x14006f5f9  test    eax, eax
0x14006f5fb  jnz     short loc_14006F60A
0x14006f5fd  call    cs:__imp_GetLastError
0x14006f603  mov     ebx, eax
0x14006f605  jmp     loc_14006F692
0x14006f60a  mov     rbx, qword ptr [rsp+78h+FileSize]
0x14006f60f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14006f613  jb      short loc_14006F61C
0x14006f615  mov     ebx, 0DFh
0x14006f61a  jmp     short loc_14006F692
0x14006f61c  lea     rcx, [rbx+1]; unsigned __int64
0x14006f620  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14006f627  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14006f62c  mov     rdi, rax
0x14006f62f  test    rax, rax
0x14006f632  jnz     short loc_14006F639
0x14006f634  lea     ebx, [rax+8]
0x14006f637  jmp     short loc_14006F692
0x14006f639  xor     esi, esi
0x14006f63b  mov     r13d, 0FFFFFFFFh
0x14006f641  cmp     rsi, rbx
0x14006f644  jnb     short loc_14006F69F
0x14006f646  mov     r8, rbx
0x14006f649  sub     r8, rsi
0x14006f64c  cmp     r8, r13
0x14006f64f  jbe     short loc_14006F654
0x14006f651  mov     r8d, r13d; nNumberOfBytesToRead
0x14006f654  lea     rdx, [rsi+rdi]; lpBuffer
0x14006f658  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x14006f661  lea     r9, [rsp+78h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14006f669  mov     rcx, rbp; hFile
0x14006f66c  call    cs:__imp_ReadFile
0x14006f672  test    eax, eax
0x14006f674  jz      short loc_14006F682
0x14006f676  mov     eax, [rsp+78h+NumberOfBytesRead]
0x14006f67d  add     rsi, rax
0x14006f680  jmp     short loc_14006F641
0x14006f682  call    cs:__imp_GetLastError
0x14006f688  mov     ebx, eax
0x14006f68a  mov     rcx, rdi; Block
0x14006f68d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006f692  mov     rcx, rbp; hObject
0x14006f695  call    cs:__imp_CloseHandle
0x14006f69b  mov     eax, ebx
0x14006f69d  jmp     short loc_14006F6B4
0x14006f69f  mov     rcx, rbp; hObject
0x14006f6a2  call    cs:__imp_CloseHandle
0x14006f6a8  xor     eax, eax
0x14006f6aa  mov     [r15], rdi
0x14006f6ad  mov     [r14], rbx
0x14006f6b0  mov     byte ptr [rbx+rdi], 0
0x14006f6b4  lea     r11, [rsp+78h+var_28]
0x14006f6b9  mov     rbx, [r11+30h]
0x14006f6bd  mov     rbp, [r11+38h]
0x14006f6c1  mov     rsp, r11
0x14006f6c4  pop     r15
0x14006f6c6  pop     r14
0x14006f6c8  pop     r13
0x14006f6ca  pop     rdi
0x14006f6cb  pop     rsi
0x14006f6cc  retn
```

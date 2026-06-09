# MySmartWrite(ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180002eb0`
- end: `0x18000302d`
- name: `?MySmartWrite@@YAHPEBG000K@Z`
- size: `381`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003978`
- `0x180003a5c`

## callees

- `0x180002eb0`
- `0x180003548`
- `0x18001b980`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180002f85`
- `KERNEL32!LocalFree` at `0x180003004`
- `KERNEL32!LocalFree` at `0x180002f85`
- `KERNEL32!LocalFree` at `0x180003004`
- `KERNEL32!WritePrivateProfileStringW` at `0x180002ef4`
- `KERNEL32!WritePrivateProfileStringW` at `0x180002ef4`
- `KERNEL32!CreateFileW` at `0x180002f70`
- `KERNEL32!CreateFileW` at `0x180002f70`
- `KERNEL32!WriteFile` at `0x180002fea`
- `KERNEL32!WriteFile` at `0x180002fea`
- `KERNEL32!CloseHandle` at `0x180002ffb`
- `KERNEL32!CloseHandle` at `0x180002ffb`
- `KERNEL32!LocalAlloc` at `0x180002f34`
- `KERNEL32!LocalAlloc` at `0x180002f34`
- `KERNEL32!SetFilePointer` at `0x180002f9b`
- `KERNEL32!SetFilePointer` at `0x180002f9b`

## pseudocode

```c
__int64 __fastcall MySmartWrite(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned int v8; // esi
  char *v9; // rbx
  HANDLE FileW; // rax
  __int64 v12; // rdi
  void *v13; // rbp
  const char *v14; // r8
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-58h] BYREF
  char v16[16]; // [rsp+48h] [rbp-50h] BYREF
  __int64 v17; // [rsp+58h] [rbp-40h] BYREF

  NumberOfBytesWritten = 0;
  if ( a5 > 0xFBC1 )
  {
    v17 = 0xA0D53253D5325LL;
    strcpy(v16, "%S=\"%S\"\r\n");
    v9 = (char *)LocalAlloc(0x40u, 0x400u);
    if ( v9 )
    {
      FileW = CreateFileW(a4, 0x40000000u, 0, 0, 4u, 0x80u, 0);
      v12 = -1;
      v13 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        v8 = 0;
        if ( SetFilePointer(FileW, 0, 0, 2u) != -1 )
        {
          v14 = (const char *)&v17;
          if ( *a3 != 34 )
            v14 = v16;
          StringCchPrintfA(v9, 0x400u, v14, a2, a3);
          do
            ++v12;
          while ( v9[v12] );
          WriteFile(v13, v9, v12, &NumberOfBytesWritten, 0);
          LOBYTE(v8) = (_DWORD)v12 == NumberOfBytesWritten;
        }
        CloseHandle(v13);
        LocalFree(v9);
        return v8;
      }
      LocalFree(v9);
    }
    return 0;
  }
  return WritePrivateProfileStringW(L"Strings", a2, a3, a4);
}

```

## disassembly

```asm
0x180002eb0  mov     [rsp+arg_0], rbx
0x180002eb5  push    rbp
0x180002eb6  push    rsi
0x180002eb7  push    rdi
0x180002eb8  push    r14
0x180002eba  push    r15
0x180002ebc  sub     rsp, 70h
0x180002ec0  mov     rax, cs:__security_cookie
0x180002ec7  xor     rax, rsp
0x180002eca  mov     [rsp+98h+var_38], rax
0x180002ecf  cmp     [rsp+98h+arg_20], 0FBC1h
0x180002eda  mov     rdi, r9
0x180002edd  mov     r14, r8
0x180002ee0  mov     [rsp+98h+NumberOfBytesWritten], 0
0x180002ee8  mov     r15, rdx
0x180002eeb  ja      short loc_180002F01
0x180002eed  lea     rcx, AppName; "Strings"
0x180002ef4  call    cs:__imp_WritePrivateProfileStringW
0x180002efa  mov     esi, eax
0x180002efc  jmp     loc_18000300A
0x180002f01  movzx   eax, word ptr cs:aSS+8; "\n"
0x180002f08  mov     edx, 400h; uBytes
0x180002f0d  movsd   xmm0, qword ptr cs:aSS; "%S=\"%S\"\r\n"
0x180002f15  mov     ecx, 40h ; '@'; uFlags
0x180002f1a  mov     word ptr [rsp+98h+var_50+8], ax
0x180002f1f  mov     rax, 0A0D53253D5325h
0x180002f29  mov     [rsp+98h+var_40], rax
0x180002f2e  movsd   qword ptr [rsp+98h+var_50], xmm0
0x180002f34  call    cs:__imp_LocalAlloc
0x180002f3a  mov     rbx, rax
0x180002f3d  test    rax, rax
0x180002f40  jnz     short loc_180002F49
0x180002f42  xor     eax, eax
0x180002f44  jmp     loc_18000300C
0x180002f49  mov     [rsp+98h+hTemplateFile], 0; hTemplateFile
0x180002f52  xor     r9d, r9d; lpSecurityAttributes
0x180002f55  mov     [rsp+98h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180002f5d  xor     r8d, r8d; dwShareMode
0x180002f60  mov     edx, 40000000h; dwDesiredAccess
0x180002f65  mov     [rsp+98h+dwCreationDisposition], 4; dwCreationDisposition
0x180002f6d  mov     rcx, rdi; lpFileName
0x180002f70  call    cs:__imp_CreateFileW
0x180002f76  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002f7a  mov     rbp, rax
0x180002f7d  cmp     rax, rdi
0x180002f80  jnz     short loc_180002F8D
0x180002f82  mov     rcx, rbx; hMem
0x180002f85  call    cs:__imp_LocalFree
0x180002f8b  jmp     short loc_180002F42
0x180002f8d  xor     esi, esi
0x180002f8f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180002f92  xor     edx, edx; lDistanceToMove
0x180002f94  mov     rcx, rbp; hFile
0x180002f97  lea     r9d, [rsi+2]; dwMoveMethod
0x180002f9b  call    cs:__imp_SetFilePointer
0x180002fa1  cmp     eax, 0FFFFFFFFh
0x180002fa4  jz      short loc_180002FF8
0x180002fa6  cmp     word ptr [r14], 22h ; '"'
0x180002fab  lea     rax, [rsp+98h+var_50]
0x180002fb0  lea     r8, [rsp+98h+var_40]
0x180002fb5  mov     qword ptr [rsp+98h+dwCreationDisposition], r14
0x180002fba  cmovnz  r8, rax; char *
0x180002fbe  mov     r9, r15
0x180002fc1  mov     edx, 400h; unsigned __int64
0x180002fc6  mov     rcx, rbx; char *
0x180002fc9  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180002fce  inc     rdi
0x180002fd1  cmp     [rbx+rdi], sil
0x180002fd5  jnz     short loc_180002FCE
0x180002fd7  lea     r9, [rsp+98h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180002fdc  mov     qword ptr [rsp+98h+dwCreationDisposition], rsi; lpOverlapped
0x180002fe1  mov     r8d, edi; nNumberOfBytesToWrite
0x180002fe4  mov     rdx, rbx; lpBuffer
0x180002fe7  mov     rcx, rbp; hFile
0x180002fea  call    cs:__imp_WriteFile
0x180002ff0  cmp     edi, [rsp+98h+NumberOfBytesWritten]
0x180002ff4  setz    sil
0x180002ff8  mov     rcx, rbp; hObject
0x180002ffb  call    cs:__imp_CloseHandle
0x180003001  mov     rcx, rbx; hMem
0x180003004  call    cs:__imp_LocalFree
0x18000300a  mov     eax, esi
0x18000300c  mov     rcx, [rsp+98h+var_38]
0x180003011  xor     rcx, rsp; StackCookie
0x180003014  call    __security_check_cookie
0x180003019  mov     rbx, [rsp+98h+arg_0]
0x180003021  add     rsp, 70h
0x180003025  pop     r15
0x180003027  pop     r14
0x180003029  pop     rdi
0x18000302a  pop     rsi
0x18000302b  pop     rbp
0x18000302c  retn
```

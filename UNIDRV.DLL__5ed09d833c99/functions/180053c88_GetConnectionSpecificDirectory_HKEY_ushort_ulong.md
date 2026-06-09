# GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)

- ea: `0x180053c88`
- end: `0x180053d9e`
- name: `?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z`
- size: `278`
- prototype: `__int64 __fastcall(HKEY hkey, BYTE *pszDest, size_t cchDest)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180048c38`
- `0x1800546f0`

## callees

- `0x180033e78`
- `0x180053c88`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180053d5a`
- `ADVAPI32!RegGetValueW` at `0x180053d5a`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180053cc5`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180053cc5`
- `KERNEL32!GetLastError` at `0x180053cd5`
- `KERNEL32!GetLastError` at `0x180053cd5`

## pseudocode

```c
__int64 __fastcall GetConnectionSpecificDirectory(HKEY hkey, BYTE *pszDest, size_t cchDest)
{
  size_t v3; // rdi
  signed int LastError; // eax
  int v7; // ebx
  __int64 v8; // rax
  LSTATUS ValueW; // eax
  DWORD pdwType; // [rsp+70h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+20h] BYREF

  v3 = (unsigned int)cchDest;
  pdwType = 0;
  if ( GetPrinterDriverDirectoryW(0, 0, 1u, pszDest, 2 * cchDest, &pdwType) )
    goto LABEL_5;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_5:
    v7 = StringCchCatW((STRSAFE_LPWSTR)pszDest, v3, L"\\V4Connections\\");
    if ( v7 >= 0 )
    {
      pdwType = 0;
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&pszDest[2 * v8] );
      pcbData = 2 * (v3 - v8);
      ValueW = RegGetValueW(hkey, 0, L"ConnectionGUID", 2u, &pdwType, &pszDest[2 * v8], &pcbData);
      if ( ValueW )
      {
        if ( ValueW > 0 )
          return (unsigned __int16)ValueW | 0x80070000;
        else
          return (unsigned int)ValueW;
      }
      else if ( pdwType != 1 )
      {
        return (unsigned int)-2147418113;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180053c88  mov     r11, rsp
0x180053c8b  mov     [r11+8], rbx
0x180053c8f  mov     [r11+10h], rbp
0x180053c93  push    rsi
0x180053c94  push    rdi
0x180053c95  push    r14
0x180053c97  sub     rsp, 40h
0x180053c9b  mov     edi, r8d
0x180053c9e  mov     rbp, rcx
0x180053ca1  lea     rcx, [r11+18h]
0x180053ca5  xor     r14d, r14d
0x180053ca8  mov     [r11-30h], rcx
0x180053cac  mov     rsi, rdx
0x180053caf  mov     r9, rdx; pDriverDirectory
0x180053cb2  mov     [r11+18h], r14d
0x180053cb6  lea     eax, [rdi+rdi]
0x180053cb9  xor     edx, edx; pEnvironment
0x180053cbb  xor     ecx, ecx; pName
0x180053cbd  mov     [rsp+58h+cbBuf], eax; cbBuf
0x180053cc1  lea     r8d, [r14+1]; Level
0x180053cc5  call    cs:__imp_GetPrinterDriverDirectoryW
0x180053ccc  nop     dword ptr [rax+rax+00h]
0x180053cd1  test    eax, eax
0x180053cd3  jnz     short loc_180053CF8
0x180053cd5  call    cs:__imp_GetLastError
0x180053cdc  nop     dword ptr [rax+rax+00h]
0x180053ce1  mov     ebx, eax
0x180053ce3  test    eax, eax
0x180053ce5  jle     short loc_180053CF0
0x180053ce7  movzx   ebx, ax
0x180053cea  or      ebx, 80070000h
0x180053cf0  test    ebx, ebx
0x180053cf2  js      loc_180053D88
0x180053cf8  mov     rdx, rdi; cchDest
0x180053cfb  lea     r8, aV4connections; "\\V4Connections\\"
0x180053d02  mov     rcx, rsi; pszDest
0x180053d05  call    StringCchCatW
0x180053d0a  mov     ebx, eax
0x180053d0c  test    eax, eax
0x180053d0e  js      short loc_180053D88
0x180053d10  mov     [rsp+58h+pdwType], r14d
0x180053d15  or      rax, 0FFFFFFFFFFFFFFFFh
0x180053d19  inc     rax
0x180053d1c  cmp     [rsi+rax*2], r14w
0x180053d21  jnz     short loc_180053D19
0x180053d23  sub     edi, eax
0x180053d25  lea     rcx, [rsp+58h+arg_18]
0x180053d2a  mov     [rsp+58h+pcbData], rcx; pcbData
0x180053d2f  lea     rax, [rsi+rax*2]
0x180053d33  mov     [rsp+58h+pvData], rax; pvData
0x180053d38  lea     r8, Value; "ConnectionGUID"
0x180053d3f  lea     rax, [rsp+58h+pdwType]
0x180053d44  add     edi, edi
0x180053d46  mov     r9d, 2; dwFlags
0x180053d4c  mov     qword ptr [rsp+58h+cbBuf], rax; pdwType
0x180053d51  xor     edx, edx; lpSubKey
0x180053d53  mov     [rsp+58h+arg_18], edi
0x180053d57  mov     rcx, rbp; hkey
0x180053d5a  call    cs:__imp_RegGetValueW
0x180053d61  nop     dword ptr [rax+rax+00h]
0x180053d66  test    eax, eax
0x180053d68  jz      short loc_180053D7B
0x180053d6a  jg      short loc_180053D70
0x180053d6c  mov     ebx, eax
0x180053d6e  jmp     short loc_180053D88
0x180053d70  movzx   ebx, ax
0x180053d73  or      ebx, 80070000h
0x180053d79  jmp     short loc_180053D88
0x180053d7b  cmp     [rsp+58h+pdwType], 1
0x180053d80  mov     eax, 8000FFFFh
0x180053d85  cmovnz  ebx, eax
0x180053d88  mov     rbp, [rsp+58h+arg_8]
0x180053d8d  mov     eax, ebx
0x180053d8f  mov     rbx, [rsp+58h+arg_0]
0x180053d94  add     rsp, 40h
0x180053d98  pop     r14
0x180053d9a  pop     rdi
0x180053d9b  pop     rsi
0x180053d9c  retn
```

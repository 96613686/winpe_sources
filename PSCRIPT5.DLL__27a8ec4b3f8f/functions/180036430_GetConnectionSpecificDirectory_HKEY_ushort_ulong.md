# GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)

- ea: `0x180036430`
- end: `0x180036546`
- name: `?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z`
- size: `278`
- prototype: `__int64 __fastcall(HKEY hkey, BYTE *pszDest, size_t cchDest)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180035c30`
- `0x180036f20`

## callees

- `0x180020acc`
- `0x180036430`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180036502`
- `ADVAPI32!RegGetValueW` at `0x180036502`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18003646d`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18003646d`
- `KERNEL32!GetLastError` at `0x18003647d`
- `KERNEL32!GetLastError` at `0x18003647d`

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
0x180036430  mov     r11, rsp
0x180036433  mov     [r11+8], rbx
0x180036437  mov     [r11+10h], rbp
0x18003643b  push    rsi
0x18003643c  push    rdi
0x18003643d  push    r14
0x18003643f  sub     rsp, 40h
0x180036443  mov     edi, r8d
0x180036446  mov     rbp, rcx
0x180036449  lea     rcx, [r11+18h]
0x18003644d  xor     r14d, r14d
0x180036450  mov     [r11-30h], rcx
0x180036454  mov     rsi, rdx
0x180036457  mov     r9, rdx; pDriverDirectory
0x18003645a  mov     [r11+18h], r14d
0x18003645e  lea     eax, [rdi+rdi]
0x180036461  xor     edx, edx; pEnvironment
0x180036463  xor     ecx, ecx; pName
0x180036465  mov     [rsp+58h+cbBuf], eax; cbBuf
0x180036469  lea     r8d, [r14+1]; Level
0x18003646d  call    cs:__imp_GetPrinterDriverDirectoryW
0x180036474  nop     dword ptr [rax+rax+00h]
0x180036479  test    eax, eax
0x18003647b  jnz     short loc_1800364A0
0x18003647d  call    cs:__imp_GetLastError
0x180036484  nop     dword ptr [rax+rax+00h]
0x180036489  mov     ebx, eax
0x18003648b  test    eax, eax
0x18003648d  jle     short loc_180036498
0x18003648f  movzx   ebx, ax
0x180036492  or      ebx, 80070000h
0x180036498  test    ebx, ebx
0x18003649a  js      loc_180036530
0x1800364a0  mov     rdx, rdi; cchDest
0x1800364a3  lea     r8, aV4connections; "\\V4Connections\\"
0x1800364aa  mov     rcx, rsi; pszDest
0x1800364ad  call    StringCchCatW
0x1800364b2  mov     ebx, eax
0x1800364b4  test    eax, eax
0x1800364b6  js      short loc_180036530
0x1800364b8  mov     [rsp+58h+pdwType], r14d
0x1800364bd  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800364c1  inc     rax
0x1800364c4  cmp     [rsi+rax*2], r14w
0x1800364c9  jnz     short loc_1800364C1
0x1800364cb  sub     edi, eax
0x1800364cd  lea     rcx, [rsp+58h+arg_18]
0x1800364d2  mov     [rsp+58h+pcbData], rcx; pcbData
0x1800364d7  lea     rax, [rsi+rax*2]
0x1800364db  mov     [rsp+58h+pvData], rax; pvData
0x1800364e0  lea     r8, Value; "ConnectionGUID"
0x1800364e7  lea     rax, [rsp+58h+pdwType]
0x1800364ec  add     edi, edi
0x1800364ee  mov     r9d, 2; dwFlags
0x1800364f4  mov     qword ptr [rsp+58h+cbBuf], rax; pdwType
0x1800364f9  xor     edx, edx; lpSubKey
0x1800364fb  mov     [rsp+58h+arg_18], edi
0x1800364ff  mov     rcx, rbp; hkey
0x180036502  call    cs:__imp_RegGetValueW
0x180036509  nop     dword ptr [rax+rax+00h]
0x18003650e  test    eax, eax
0x180036510  jz      short loc_180036523
0x180036512  jg      short loc_180036518
0x180036514  mov     ebx, eax
0x180036516  jmp     short loc_180036530
0x180036518  movzx   ebx, ax
0x18003651b  or      ebx, 80070000h
0x180036521  jmp     short loc_180036530
0x180036523  cmp     [rsp+58h+pdwType], 1
0x180036528  mov     eax, 8000FFFFh
0x18003652d  cmovnz  ebx, eax
0x180036530  mov     rbp, [rsp+58h+arg_8]
0x180036535  mov     eax, ebx
0x180036537  mov     rbx, [rsp+58h+arg_0]
0x18003653c  add     rsp, 40h
0x180036540  pop     r14
0x180036542  pop     rdi
0x180036543  pop     rsi
0x180036544  retn
```

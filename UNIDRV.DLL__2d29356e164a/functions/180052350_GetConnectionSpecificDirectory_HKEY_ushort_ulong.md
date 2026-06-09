# GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)

- ea: `0x180052350`
- end: `0x180052453`
- name: `?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z`
- size: `259`
- prototype: `__int64 __fastcall(HKEY hkey, STRSAFE_LPWSTR pszDest, size_t cchDest)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180047790`
- `0x180052d50`

## callees

- `0x180033504`
- `0x180052350`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180052416`
- `ADVAPI32!RegGetValueW` at `0x180052416`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18005238d`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18005238d`
- `KERNEL32!GetLastError` at `0x180052397`
- `KERNEL32!GetLastError` at `0x180052397`

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
0x180052350  mov     r11, rsp
0x180052353  mov     [r11+8], rbx
0x180052357  mov     [r11+10h], rbp
0x18005235b  push    rsi
0x18005235c  push    rdi
0x18005235d  push    r14
0x18005235f  sub     rsp, 40h
0x180052363  mov     edi, r8d
0x180052366  mov     rbp, rcx
0x180052369  lea     rcx, [r11+18h]
0x18005236d  xor     r14d, r14d
0x180052370  mov     [r11-30h], rcx
0x180052374  mov     rsi, rdx
0x180052377  mov     r9, rdx; pDriverDirectory
0x18005237a  mov     [r11+18h], r14d
0x18005237e  lea     eax, [rdi+rdi]
0x180052381  xor     edx, edx; pEnvironment
0x180052383  xor     ecx, ecx; pName
0x180052385  mov     [rsp+58h+cbBuf], eax; cbBuf
0x180052389  lea     r8d, [r14+1]; Level
0x18005238d  call    cs:__imp_GetPrinterDriverDirectoryW
0x180052393  test    eax, eax
0x180052395  jnz     short loc_1800523B4
0x180052397  call    cs:__imp_GetLastError
0x18005239d  mov     ebx, eax
0x18005239f  test    eax, eax
0x1800523a1  jle     short loc_1800523AC
0x1800523a3  movzx   ebx, ax
0x1800523a6  or      ebx, 80070000h
0x1800523ac  test    ebx, ebx
0x1800523ae  js      loc_18005243E
0x1800523b4  mov     rdx, rdi; cchDest
0x1800523b7  lea     r8, aV4connections; "\\V4Connections\\"
0x1800523be  mov     rcx, rsi; pszDest
0x1800523c1  call    StringCchCatW
0x1800523c6  mov     ebx, eax
0x1800523c8  test    eax, eax
0x1800523ca  js      short loc_18005243E
0x1800523cc  mov     [rsp+58h+pdwType], r14d
0x1800523d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800523d5  inc     rax
0x1800523d8  cmp     [rsi+rax*2], r14w
0x1800523dd  jnz     short loc_1800523D5
0x1800523df  sub     edi, eax
0x1800523e1  lea     rcx, [rsp+58h+arg_18]
0x1800523e6  mov     [rsp+58h+pcbData], rcx; pcbData
0x1800523eb  lea     rax, [rsi+rax*2]
0x1800523ef  mov     [rsp+58h+pvData], rax; pvData
0x1800523f4  lea     r8, Value; "ConnectionGUID"
0x1800523fb  lea     rax, [rsp+58h+pdwType]
0x180052400  add     edi, edi
0x180052402  mov     r9d, 2; dwFlags
0x180052408  mov     qword ptr [rsp+58h+cbBuf], rax; pdwType
0x18005240d  xor     edx, edx; lpSubKey
0x18005240f  mov     [rsp+58h+arg_18], edi
0x180052413  mov     rcx, rbp; hkey
0x180052416  call    cs:__imp_RegGetValueW
0x18005241c  test    eax, eax
0x18005241e  jz      short loc_180052431
0x180052420  jg      short loc_180052426
0x180052422  mov     ebx, eax
0x180052424  jmp     short loc_18005243E
0x180052426  movzx   ebx, ax
0x180052429  or      ebx, 80070000h
0x18005242f  jmp     short loc_18005243E
0x180052431  cmp     [rsp+58h+pdwType], 1
0x180052436  mov     eax, 8000FFFFh
0x18005243b  cmovnz  ebx, eax
0x18005243e  mov     rbp, [rsp+58h+arg_8]
0x180052443  mov     eax, ebx
0x180052445  mov     rbx, [rsp+58h+arg_0]
0x18005244a  add     rsp, 40h
0x18005244e  pop     r14
0x180052450  pop     rdi
0x180052451  pop     rsi
0x180052452  retn
```

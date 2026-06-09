# UtsemWin32Error(ushort *,ushort *,ulong)

- ea: `0x18000e6fc`
- end: `0x18000e821`
- name: `?UtsemWin32Error@@YAXPEAG0K@Z`
- size: `293`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001040`
- `0x180005d78`
- `0x180005ff0`
- `0x18000699c`
- `0x1800073b4`
- `0x18000dd90`
- `0x18000e090`

## callees

- `0x18000e6fc`
- `0x18000f654`
- `0x18000f6e4`
- `0x18000f934`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e726`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e726`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e753`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e7e3`

## string_xrefs

- `0x18000e7b5`: `com\complus\src\inc\utsem.h`

## pseudocode

```c
void __fastcall UtsemWin32Error(unsigned __int16 *a1, unsigned __int16 *a2, int a3)
{
  DWORD LastError; // eax
  __int64 v5; // rcx
  const wchar_t *v6; // r8
  __int64 v7; // rdx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rcx
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rcx
  int v12; // r8d
  LPWSTR lpBuffer; // [rsp+20h] [rbp-148h]
  struct _EXCEPTION_POINTERS *nSize; // [rsp+28h] [rbp-140h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-128h] BYREF
  unsigned __int16 v16[128]; // [rsp+50h] [rbp-118h] BYREF

  LastError = GetLastError();
  *(_QWORD *)Buffer = 0;
  FormatMessageW(0x1300u, 0, LastError, 0, Buffer, 0, 0);
  v5 = 2147483646;
  v6 = L"*** Error in %s(%d), %s: %s";
  v7 = 128;
  v8 = v16;
  do
  {
    if ( !v5 )
      break;
    if ( !*v6 )
      break;
    *v8++ = *v6++;
    --v5;
    --v7;
  }
  while ( v7 );
  v9 = v8 - 1;
  if ( v7 )
    v9 = v8;
  *v9 = 0;
  GetFormatString(0x3A6u, v16);
  nSize = *(struct _EXCEPTION_POINTERS **)Buffer;
  LODWORD(lpBuffer) = a3;
  Log(8u, 0xC0021251, v16, L"com\\complus\\src\\inc\\utsem.h", lpBuffer);
  LocalFree(*(HLOCAL *)Buffer);
  FailFastStr(v11, v10, v12, 1, 1, nSize);
}

```

## disassembly

```asm
0x18000e6fc  mov     [rsp+arg_8], rbx
0x18000e701  mov     [rsp+arg_18], rsi
0x18000e706  push    rdi
0x18000e707  sub     rsp, 160h
0x18000e70e  mov     rax, cs:__security_cookie
0x18000e715  xor     rax, rsp
0x18000e718  mov     [rsp+168h+var_18], rax
0x18000e720  mov     edi, r8d
0x18000e723  mov     rbx, rcx
0x18000e726  call    cs:__imp_GetLastError
0x18000e72c  xor     esi, esi
0x18000e72e  lea     rcx, [rsp+168h+Buffer]
0x18000e733  mov     [rsp+168h+Arguments], rsi; Arguments
0x18000e738  xor     r9d, r9d; dwLanguageId
0x18000e73b  mov     [rsp+168h+nSize], esi; nSize
0x18000e73f  mov     r8d, eax; dwMessageId
0x18000e742  mov     [rsp+168h+lpBuffer], rcx; lpBuffer
0x18000e747  xor     edx, edx; lpSource
0x18000e749  mov     ecx, 1300h; dwFlags
0x18000e74e  mov     qword ptr [rsp+168h+Buffer], rsi
0x18000e753  call    cs:__imp_FormatMessageW
0x18000e759  mov     ecx, 7FFFFFFEh
0x18000e75e  lea     r8, aErrorInSDSS; "*** Error in %s(%d), %s: %s"
0x18000e765  mov     edx, 80h
0x18000e76a  lea     rax, [rsp+168h+var_118]
0x18000e76f  test    rcx, rcx
0x18000e772  jz      short loc_18000E793
0x18000e774  movzx   r9d, word ptr [r8]
0x18000e778  test    r9w, r9w
0x18000e77c  jz      short loc_18000E793
0x18000e77e  mov     [rax], r9w
0x18000e782  add     r8, 2
0x18000e786  add     rax, 2
0x18000e78a  dec     rcx
0x18000e78d  sub     rdx, 1
0x18000e791  jnz     short loc_18000E76F
0x18000e793  test    rdx, rdx
0x18000e796  lea     rcx, [rax-2]
0x18000e79a  lea     rdx, [rsp+168h+var_118]; unsigned __int16 *
0x18000e79f  cmovnz  rcx, rax
0x18000e7a3  mov     [rcx], si
0x18000e7a6  mov     ecx, 3A6h; unsigned int
0x18000e7ab  call    ?GetFormatString@@YAXIPEAG@Z; GetFormatString(uint,ushort *)
0x18000e7b0  mov     rax, qword ptr [rsp+168h+Buffer]
0x18000e7b5  lea     r9, aComComplusSrcI; "com\\complus\\src\\inc\\utsem.h"
0x18000e7bc  mov     [rsp+168h+Arguments], rbx
0x18000e7c1  lea     r8, [rsp+168h+var_118]; unsigned __int16 *
0x18000e7c6  mov     qword ptr [rsp+168h+nSize], rax; struct _EXCEPTION_POINTERS *
0x18000e7cb  mov     ecx, 8; unsigned __int16
0x18000e7d0  mov     edx, 0C0021251h; unsigned int
0x18000e7d5  mov     dword ptr [rsp+168h+lpBuffer], edi
0x18000e7d9  call    ?Log@@YAXGKPEBGZZ; Log(ushort,ulong,ushort const *,...)
0x18000e7de  mov     rcx, qword ptr [rsp+168h+Buffer]; hMem
0x18000e7e3  call    cs:__imp_LocalFree
0x18000e7e9  mov     r9d, 1; int
0x18000e7ef  mov     dword ptr [rsp+168h+lpBuffer], 1; int
0x18000e7f7  call    ?FailFastStr@@YAXPEBG0HHHPEAU_EXCEPTION_POINTERS@@@Z; FailFastStr(ushort const *,ushort const *,int,int,int,_EXCEPTION_POINTERS *)
0x18000e7fc  mov     rcx, [rsp+168h+var_18]
0x18000e804  xor     rcx, rsp; StackCookie
0x18000e807  call    __security_check_cookie
0x18000e80c  lea     r11, [rsp+168h+var_8]
0x18000e814  mov     rbx, [r11+18h]
0x18000e818  mov     rsi, [r11+28h]
0x18000e81c  mov     rsp, r11
0x18000e81f  pop     rdi
0x18000e820  retn
```

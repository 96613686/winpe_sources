# DpspRetrieveTokenType

- ea: `0x1800071a4`
- end: `0x18000723f`
- name: `DpspRetrieveTokenType`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800118f0`
- `0x180011c6c`

## callees

- `0x1800071a4`
- `0x180009090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071f7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800071ed`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800071ed`

## string_xrefs

- `0x180007224`: `DpspRetrieveTokenType`

## pseudocode

```c
__int64 __fastcall DpspRetrieveTokenType(void *a1, _DWORD *a2)
{
  signed int v2; // ebx
  signed int LastError; // eax
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF

  ReturnLength = 0;
  if ( a2 )
  {
    v2 = 0;
    *a2 = 2;
    if ( a1 && !GetTokenInformation(a1, TokenType, a2, 4u, &ReturnLength) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 < 0 )
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (int)L"DpspRetrieveTokenType",
          1556,
          (int)L"Error = %d",
          v2);
    }
  }
  else
  {
    v2 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (int)L"DpspRetrieveTokenType",
      1543,
      (int)L"Error = %d",
      87);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800071a4  push    rbx
0x1800071a6  sub     rsp, 30h
0x1800071aa  mov     [rsp+38h+arg_8], 0
0x1800071b2  test    rdx, rdx
0x1800071b5  jnz     short loc_1800071CC
0x1800071b7  mov     ebx, 80070057h
0x1800071bc  mov     dword ptr [rsp+38h+ReturnLength], 57h ; 'W'
0x1800071c4  mov     r8d, 607h
0x1800071ca  jmp     short loc_18000721D
0x1800071cc  xor     ebx, ebx
0x1800071ce  mov     dword ptr [rdx], 2
0x1800071d4  test    rcx, rcx
0x1800071d7  jz      short loc_180007237
0x1800071d9  lea     rax, [rsp+38h+arg_8]
0x1800071de  mov     r8, rdx; TokenInformation
0x1800071e1  lea     edx, [rbx+8]; TokenInformationClass
0x1800071e4  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800071e9  lea     r9d, [rbx+4]; TokenInformationLength
0x1800071ed  call    cs:__imp_GetTokenInformation
0x1800071f3  test    eax, eax
0x1800071f5  jnz     short loc_180007237
0x1800071f7  call    cs:__imp_GetLastError
0x1800071fd  mov     ebx, eax
0x1800071ff  test    eax, eax
0x180007201  jle     short loc_18000720C
0x180007203  movzx   ebx, ax
0x180007206  or      ebx, 80070000h
0x18000720c  test    ebx, ebx
0x18000720e  jns     short loc_180007237
0x180007210  movzx   ecx, bx
0x180007213  mov     r8d, 614h; int
0x180007219  mov     dword ptr [rsp+38h+ReturnLength], ecx; Args
0x18000721d  lea     r9, aErrorD; "Error = %d"
0x180007224  lea     rdx, aDpspretrieveto; "DpspRetrieveTokenType"
0x18000722b  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007232  call    WdipTraceError
0x180007237  mov     eax, ebx
0x180007239  add     rsp, 30h
0x18000723d  pop     rbx
0x18000723e  retn
```

# FormatMessageFromStringAlloc(ushort * *,ushort const *,...)

- ea: `0x18001b430`
- end: `0x18001b528`
- name: `?FormatMessageFromStringAlloc@@YAJPEAPEAGPEBGZZ`
- size: `248`
- prototype: `__int64(LPWSTR lpBuffer, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b1e0`

## callees

- `0x1800050b8`
- `0x18001b430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b4e4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001b4da`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001b4da`

## string_xrefs

- `0x18001b467`: `CPR(pszMessageTemplate)`
- `0x18001b47a`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctoasthelper.cpp`
- `0x18001b502`: `CBR(FormatMessageW( 0x00000400 | 0x00000100 | 0x00002000, pszMessageTemplate, 0, 0, (LPWSTR)ppszMessage, 0, (va_list *)vlArgs) != 0)`

## pseudocode

```c
__int64 FormatMessageFromStringAlloc(LPWSTR lpBuffer, const unsigned __int16 *a2, ...)
{
  unsigned int v2; // ebx
  signed int LastError; // eax
  int v4; // edx
  int v5; // ecx
  va_list va; // [rsp+70h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( a2 )
  {
    if ( lpBuffer )
    {
      if ( FormatMessageW(0x2500u, a2, 0, 0, lpBuffer, 0, (va_list *)va) )
      {
        return 0;
      }
      else
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v5,
            v4,
            v2,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctoasthelper.cpp",
            45,
            "CBR(FormatMessageW( 0x00000400 | 0x00000100 | 0x00002000, pszMessageTemplate, 0, 0, (LPWSTR)ppszMessage, 0, "
            "(va_list *)vlArgs) != 0)");
      }
    }
    else
    {
      v2 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          0,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctoasthelper.cpp",
          33,
          "CPR(ppszMessage)");
    }
  }
  else
  {
    v2 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)lpBuffer,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctoasthelper.cpp",
        32,
        "CPR(pszMessageTemplate)");
  }
  return v2;
}

```

## disassembly

```asm
0x18001b430  mov     r11, rsp
0x18001b433  mov     [r11+10h], rdx
0x18001b437  mov     [r11+18h], r8
0x18001b43b  mov     [r11+20h], r9
0x18001b43f  push    rbx
0x18001b440  sub     rsp, 50h
0x18001b444  mov     qword ptr [r11-18h], 0
0x18001b44c  test    rdx, rdx
0x18001b44f  jnz     short loc_18001B48B
0x18001b451  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b458  mov     r8d, 80070057h
0x18001b45e  mov     ebx, r8d
0x18001b461  jz      loc_18001B520
0x18001b467  lea     rax, aCprPszmessaget; "CPR(pszMessageTemplate)"
0x18001b46e  mov     [r11-30h], rax
0x18001b472  mov     dword ptr [rsp+58h+lpBuffer], 20h ; ' '
0x18001b47a  lea     r9, aOnecoreuapShel_15; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001b481  call    McTemplateU0dsqs_EventWriteTransfer
0x18001b486  jmp     loc_18001B520
0x18001b48b  test    rcx, rcx
0x18001b48e  jnz     short loc_18001B4B8
0x18001b490  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b497  mov     r8d, 80070057h
0x18001b49d  mov     ebx, r8d
0x18001b4a0  jz      short loc_18001B520
0x18001b4a2  lea     rax, aCprPpszmessage; "CPR(ppszMessage)"
0x18001b4a9  mov     qword ptr [rsp+58h+nSize], rax
0x18001b4ae  mov     dword ptr [rsp+58h+lpBuffer], 21h ; '!'
0x18001b4b6  jmp     short loc_18001B47A
0x18001b4b8  lea     rax, [rsp+58h+arg_10]
0x18001b4bd  xor     r9d, r9d; dwLanguageId
0x18001b4c0  mov     [rsp+58h+Arguments], rax; Arguments
0x18001b4c5  xor     r8d, r8d; dwMessageId
0x18001b4c8  mov     [rsp+58h+nSize], 0; nSize
0x18001b4d0  mov     [rsp+58h+lpBuffer], rcx; lpBuffer
0x18001b4d5  mov     ecx, 2500h; dwFlags
0x18001b4da  call    cs:__imp_FormatMessageW
0x18001b4e0  test    eax, eax
0x18001b4e2  jnz     short loc_18001B51E
0x18001b4e4  call    cs:__imp_GetLastError
0x18001b4ea  mov     ebx, eax
0x18001b4ec  test    eax, eax
0x18001b4ee  jle     short loc_18001B4F9
0x18001b4f0  movzx   ebx, ax
0x18001b4f3  or      ebx, 80070000h
0x18001b4f9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001b500  jz      short loc_18001B520
0x18001b502  lea     rax, aCbrFormatmessa; "CBR(FormatMessageW( 0x00000400 | 0x0000"...
0x18001b509  mov     r8d, ebx
0x18001b50c  mov     qword ptr [rsp+58h+nSize], rax
0x18001b511  mov     dword ptr [rsp+58h+lpBuffer], 2Dh ; '-'
0x18001b519  jmp     loc_18001B47A
0x18001b51e  xor     ebx, ebx
0x18001b520  mov     eax, ebx
0x18001b522  add     rsp, 50h
0x18001b526  pop     rbx
0x18001b527  retn
```

# Microsoft::Resources::IProfileHelpers::PathIsInSystemWindowsDirectory(ushort const *)

- ea: `0x18001b738`
- end: `0x18001b82a`
- name: `?PathIsInSystemWindowsDirectory@IProfileHelpers@Resources@Microsoft@@SA_NPEBG@Z`
- size: `242`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a748`
- `0x180026ab4`
- `0x180034c3c`
- `0x1800360b4`
- `0x180056374`
- `0x180073e50`

## callees

- `0x18001b738`
- `0x1800862f0`
- `0x180086f10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b814`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001b76e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001b76e`

## pseudocode

```c
char __fastcall Microsoft::Resources::IProfileHelpers::PathIsInSystemWindowsDirectory(wint_t *a1)
{
  UINT SystemWindowsDirectoryW; // eax
  WCHAR v3; // ax
  WCHAR *i; // r14
  bool v5; // zf
  wint_t v6; // bx
  wint_t v7; // di
  signed int LastError; // eax
  bool v10; // sf
  WCHAR Buffer[264]; // [rsp+20h] [rbp-238h] BYREF

  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  if ( SystemWindowsDirectoryW )
  {
    if ( SystemWindowsDirectoryW <= 0x104 )
      goto LABEL_3;
    return 0;
  }
  LastError = GetLastError();
  v10 = LastError < 0;
  if ( LastError > 0 )
    v10 = 1;
  if ( v10 )
    return 0;
LABEL_3:
  v3 = Buffer[0];
  if ( !Buffer[0] )
    return 1;
  if ( !a1 || !*a1 )
    return 0;
  for ( i = Buffer; ; v3 = *i )
  {
    v5 = v3 == 0;
    if ( !v3 )
      break;
    if ( !*a1 )
      return v3 == 0;
    v6 = *i;
    v7 = towupper(*a1);
    if ( towupper(v6) != v7 )
      return 0;
    ++i;
    ++a1;
  }
  return v5;
}

```

## disassembly

```asm
0x18001b738  mov     [rsp+arg_8], rbx
0x18001b73d  mov     [rsp+arg_10], rbp
0x18001b742  push    rsi
0x18001b743  push    rdi
0x18001b744  push    r14
0x18001b746  sub     rsp, 240h
0x18001b74d  mov     rax, cs:__security_cookie
0x18001b754  xor     rax, rsp
0x18001b757  mov     [rsp+258h+var_28], rax
0x18001b75f  mov     rsi, rcx
0x18001b762  mov     ebx, 104h
0x18001b767  mov     edx, ebx; uSize
0x18001b769  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18001b76e  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001b774  xor     ebp, ebp
0x18001b776  test    eax, eax
0x18001b778  jz      loc_18001B814
0x18001b77e  cmp     eax, ebx
0x18001b780  ja      loc_18001B810
0x18001b786  movzx   eax, [rsp+258h+Buffer]
0x18001b78b  test    ax, ax
0x18001b78e  jz      short loc_18001B806
0x18001b790  test    rsi, rsi
0x18001b793  jz      short loc_18001B7D3
0x18001b795  cmp     [rsi], bp
0x18001b798  jz      short loc_18001B7D3
0x18001b79a  lea     r14, [rsp+258h+Buffer]
0x18001b79f  test    ax, ax
0x18001b7a2  jz      short loc_18001B801
0x18001b7a4  movzx   ecx, word ptr [rsi]; C
0x18001b7a7  test    cx, cx
0x18001b7aa  jz      short loc_18001B7FE
0x18001b7ac  movzx   ebx, word ptr [r14]
0x18001b7b0  call    towupper
0x18001b7b5  movzx   ecx, bx; C
0x18001b7b8  movzx   edi, ax
0x18001b7bb  call    towupper
0x18001b7c0  cmp     ax, di
0x18001b7c3  jnz     short loc_18001B7D3
0x18001b7c5  add     r14, 2
0x18001b7c9  add     rsi, 2
0x18001b7cd  movzx   eax, word ptr [r14]
0x18001b7d1  jmp     short loc_18001B79F
0x18001b7d3  mov     al, bpl
0x18001b7d6  mov     rcx, [rsp+258h+var_28]
0x18001b7de  xor     rcx, rsp; StackCookie
0x18001b7e1  call    __security_check_cookie
0x18001b7e6  lea     r11, [rsp+258h+var_18]
0x18001b7ee  mov     rbx, [r11+28h]
0x18001b7f2  mov     rbp, [r11+30h]
0x18001b7f6  mov     rsp, r11
0x18001b7f9  pop     r14
0x18001b7fb  pop     rdi
0x18001b7fc  pop     rsi
0x18001b7fd  retn
0x18001b7fe  test    ax, ax
0x18001b801  setz    al
0x18001b804  jmp     short loc_18001B7D6
0x18001b806  mov     al, 1
0x18001b808  jmp     short loc_18001B7D6
0x18001b80a  jns     loc_18001B786
0x18001b810  xor     al, al
0x18001b812  jmp     short loc_18001B7D6
0x18001b814  call    cs:__imp_GetLastError
0x18001b81a  test    eax, eax
0x18001b81c  jle     short loc_18001B80A
0x18001b81e  movzx   eax, ax
0x18001b821  or      eax, 80070000h
0x18001b826  test    eax, eax
0x18001b828  jmp     short loc_18001B80A
```

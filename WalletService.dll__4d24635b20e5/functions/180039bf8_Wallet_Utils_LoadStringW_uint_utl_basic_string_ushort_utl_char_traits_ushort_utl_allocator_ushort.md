# Wallet::Utils::LoadStringW(uint,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180039bf8`
- end: `0x180039ce3`
- name: `?LoadStringW@Utils@Wallet@@YAJIAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(UINT uID)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callers

- `0x18001ca18`
- `0x180032cf0`

## callees

- `0x18001400c`
- `0x180039bf8`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039c2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180039c2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180039c59`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180039c59`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039cb7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180039cb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039c63`

## string_xrefs

- `0x180039c26`: `WalletService.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wallet::Utils::LoadStringW(UINT uID, _QWORD *a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rbx
  unsigned int v6; // edi
  signed int LastError; // eax
  __int64 v8; // r8
  WCHAR Buffer[264]; // [rsp+30h] [rbp-238h] BYREF

  Library = LoadLibraryExW(L"WalletService.dll", 0, 0x802u);
  v5 = Library;
  if ( Library )
  {
    if ( LoadStringW(Library, uID, Buffer, 260) )
    {
      v8 = -1;
      do
        ++v8;
      while ( Buffer[v8] );
      v6 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
             a2,
             Buffer,
             v8) == 0
         ? 0x8007000E
         : 0;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v6 = -2143748092;
      }
    }
  }
  else
  {
    v6 = -2147467259;
  }
  if ( v5 )
    FreeLibrary(v5);
  return v6;
}

```

## disassembly

```asm
0x180039bf8  mov     [rsp+arg_10], rbx
0x180039bfd  push    rbp
0x180039bfe  push    rsi
0x180039bff  push    rdi
0x180039c00  sub     rsp, 250h
0x180039c07  mov     rax, cs:__security_cookie
0x180039c0e  xor     rax, rsp
0x180039c11  mov     [rsp+268h+var_28], rax
0x180039c19  mov     rsi, rdx
0x180039c1c  mov     edi, ecx
0x180039c1e  xor     edx, edx; hFile
0x180039c20  mov     r8d, 802h; dwFlags
0x180039c26  lea     rcx, aWalletserviceD_0; "WalletService.dll"
0x180039c2d  call    cs:__imp_LoadLibraryExW
0x180039c33  mov     rbx, rax
0x180039c36  mov     [rsp+268h+var_248], rax
0x180039c3b  xor     ebp, ebp
0x180039c3d  test    rax, rax
0x180039c40  jnz     short loc_180039C49
0x180039c42  mov     edi, 80004005h
0x180039c47  jmp     short loc_180039CAF
0x180039c49  mov     r9d, 104h; cchBufferMax
0x180039c4f  lea     r8, [rsp+268h+Buffer]; lpBuffer
0x180039c54  mov     edx, edi; uID
0x180039c56  mov     rcx, rbx; hInstance
0x180039c59  call    cs:__imp_LoadStringW
0x180039c5f  test    eax, eax
0x180039c61  jnz     short loc_180039C83
0x180039c63  call    cs:__imp_GetLastError
0x180039c69  mov     edi, eax
0x180039c6b  test    eax, eax
0x180039c6d  jz      short loc_180039C7C
0x180039c6f  jle     short loc_180039CAF
0x180039c71  movzx   edi, ax
0x180039c74  or      edi, 80070000h
0x180039c7a  jmp     short loc_180039CAF
0x180039c7c  mov     edi, 80390004h
0x180039c81  jmp     short loc_180039CAF
0x180039c83  lea     rax, [rsp+268h+Buffer]
0x180039c88  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039c8c  inc     r8
0x180039c8f  cmp     [rax+r8*2], bp
0x180039c94  jnz     short loc_180039C8C
0x180039c96  lea     rdx, [rsp+268h+Buffer]
0x180039c9b  mov     rcx, rsi
0x180039c9e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180039ca3  neg     al
0x180039ca5  sbb     edi, edi
0x180039ca7  not     edi
0x180039ca9  and     edi, 8007000Eh
0x180039caf  test    rbx, rbx
0x180039cb2  jz      short loc_180039CBE
0x180039cb4  mov     rcx, rbx; hLibModule
0x180039cb7  call    cs:__imp_FreeLibrary
0x180039cbd  nop
0x180039cbe  mov     eax, edi
0x180039cc0  mov     rcx, [rsp+268h+var_28]
0x180039cc8  xor     rcx, rsp; StackCookie
0x180039ccb  call    __security_check_cookie
0x180039cd0  mov     rbx, [rsp+268h+arg_10]
0x180039cd8  add     rsp, 250h
0x180039cdf  pop     rdi
0x180039ce0  pop     rsi
0x180039ce1  pop     rbp
0x180039ce2  retn
```

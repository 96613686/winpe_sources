# WctLoadUser32(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> *,HWND__ * (**)(ulong))

- ea: `0x18004c9d0`
- end: `0x18004cb07`
- name: `?WctLoadUser32@@YAKPEAV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEAP6APEAUHWND__@@K@Z@Z`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005e2e8`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x1800371c0`
- `0x1800376a8`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004ca7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004ca7f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004ca29`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004ca29`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004ca5e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004ca5e`

## string_xrefs

- `0x18004ca57`: `user32.dll`

## pseudocode

```c
__int64 __fastcall WctLoadUser32(HMODULE *a1, FARPROC *a2)
{
  wchar_t *v4; // rcx
  HMODULE v5; // rcx
  HMODULE LibraryW; // rax
  unsigned int v7; // ebx
  FARPROC ProcAddress; // rsi
  HMODULE v10; // [rsp+50h] [rbp+8h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v5 = *a1;
    *a1 = 0;
    if ( v5 )
      FreeLibrary(v5);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    *a2 = 0;
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 && a2 )
  {
    LibraryW = LoadLibraryW(L"user32.dll");
    v10 = LibraryW;
    if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "GetSendMessageReceiver")) != 0 )
    {
      tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::operator=(
        a1,
        &v10);
      v7 = 0;
      *a2 = ProcAddress;
    }
    else
    {
      v7 = 50;
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v7);
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v10);
  }
  else
  {
    v7 = 87;
    if ( v4 != (wchar_t *)&WPP_GLOBAL_Control && (v4[14] & 4) != 0 )
      WPP_SF_d(*((_QWORD *)v4 + 2), 72, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, 87);
  }
  return v7;
}

```

## disassembly

```asm
0x18004c9d0  push    rbx
0x18004c9d2  push    rsi
0x18004c9d3  push    rdi
0x18004c9d4  push    r14
0x18004c9d6  sub     rsp, 28h
0x18004c9da  mov     rdi, rdx
0x18004c9dd  mov     rbx, rcx
0x18004c9e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c9e7  lea     r14, WPP_GLOBAL_Control
0x18004c9ee  cmp     rcx, r14
0x18004c9f1  jz      short loc_18004CA15
0x18004c9f3  test    byte ptr [rcx+1Ch], 4
0x18004c9f7  jz      short loc_18004CA15
0x18004c9f9  mov     rcx, [rcx+10h]
0x18004c9fd  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18004ca04  mov     edx, 47h ; 'G'
0x18004ca09  call    WPP_SF_
0x18004ca0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca15  test    rbx, rbx
0x18004ca18  jz      short loc_18004CA36
0x18004ca1a  mov     rcx, [rbx]; hLibModule
0x18004ca1d  mov     qword ptr [rbx], 0
0x18004ca24  test    rcx, rcx
0x18004ca27  jz      short loc_18004CA2F
0x18004ca29  call    cs:__imp_FreeLibrary
0x18004ca2f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca36  test    rdi, rdi
0x18004ca39  jz      short loc_18004CA49
0x18004ca3b  mov     qword ptr [rdi], 0
0x18004ca42  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ca49  test    rbx, rbx
0x18004ca4c  jz      loc_18004CAD5
0x18004ca52  test    rdi, rdi
0x18004ca55  jz      short loc_18004CAD5
0x18004ca57  lea     rcx, aUser32Dll; "user32.dll"
0x18004ca5e  call    cs:__imp_LoadLibraryW
0x18004ca64  mov     [rsp+48h+arg_0], rax
0x18004ca69  test    rax, rax
0x18004ca6c  jnz     short loc_18004CA75
0x18004ca6e  mov     ebx, 32h ; '2'
0x18004ca73  jmp     short loc_18004CA9F
0x18004ca75  lea     rdx, aGetsendmessage; "GetSendMessageReceiver"
0x18004ca7c  mov     rcx, rax; hModule
0x18004ca7f  call    cs:__imp_GetProcAddress
0x18004ca85  mov     rsi, rax
0x18004ca88  test    rax, rax
0x18004ca8b  jz      short loc_18004CA6E
0x18004ca8d  lea     rdx, [rsp+48h+arg_0]
0x18004ca92  mov     rcx, rbx
0x18004ca95  call    ??4?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAAAEAV01@$$QEAV01@@Z; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::operator=(tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>> &&)
0x18004ca9a  xor     ebx, ebx
0x18004ca9c  mov     [rdi], rsi
0x18004ca9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004caa6  cmp     rcx, r14
0x18004caa9  jz      short loc_18004CAC9
0x18004caab  test    byte ptr [rcx+1Ch], 4
0x18004caaf  jz      short loc_18004CAC9
0x18004cab1  mov     rcx, [rcx+10h]
0x18004cab5  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18004cabc  mov     edx, 49h ; 'I'
0x18004cac1  mov     r9d, ebx
0x18004cac4  call    WPP_SF_d
0x18004cac9  lea     rcx, [rsp+48h+arg_0]
0x18004cace  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x18004cad3  jmp     short loc_18004CAFB
0x18004cad5  mov     ebx, 57h ; 'W'
0x18004cada  cmp     rcx, r14
0x18004cadd  jz      short loc_18004CAFB
0x18004cadf  test    byte ptr [rcx+1Ch], 4
0x18004cae3  jz      short loc_18004CAFB
0x18004cae5  mov     rcx, [rcx+10h]
0x18004cae9  lea     edx, [rbx-0Fh]
0x18004caec  mov     r9d, ebx
0x18004caef  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18004caf6  call    WPP_SF_d
0x18004cafb  mov     eax, ebx
0x18004cafd  add     rsp, 28h
0x18004cb01  pop     r14
0x18004cb03  pop     rdi
0x18004cb04  pop     rsi
0x18004cb05  pop     rbx
0x18004cb06  retn
```

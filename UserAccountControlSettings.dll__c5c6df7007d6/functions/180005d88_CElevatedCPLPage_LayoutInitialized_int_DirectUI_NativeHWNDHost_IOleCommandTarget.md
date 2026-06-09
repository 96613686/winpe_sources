# CElevatedCPLPage::LayoutInitialized(int,DirectUI::NativeHWNDHost *,IOleCommandTarget *)

- ea: `0x180005d88`
- end: `0x180005e29`
- name: `?LayoutInitialized@CElevatedCPLPage@@QEAAJHPEAVNativeHWNDHost@DirectUI@@PEAUIOleCommandTarget@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(CElevatedCPLPage *__hidden this, int, struct DirectUI::NativeHWNDHost *, struct IOleCommandTarget *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000377c`

## callees

- `0x180001a04`
- `0x180005d88`
- `0x1800071e8`
- `0x1800072c0`
- `0x18000751c`
- `0x18000b710`

## pseudocode

```c
__int64 __fastcall CElevatedCPLPage::LayoutInitialized(
        CElevatedCPLPage *this,
        int a2,
        struct DirectUI::NativeHWNDHost *a3,
        struct IOleCommandTarget *a4)
{
  CUACSettingsPage *v8; // rax
  int v9; // edx
  int v10; // ecx
  int v11; // ebx
  int v12; // r8d
  int v13; // r9d
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+30h] [rbp-38h] BYREF

  v8 = (CUACSettingsPage *)operator new(0xB8u);
  if ( v8 )
    v8 = CUACSettingsPage::CUACSettingsPage(v8, a2);
  *((_QWORD *)this + 25) = v8;
  if ( v8 )
  {
    v11 = CUACSettingsPage::InitializePage(v8, a2, a3, this, a4);
    if ( v11 >= 0 && (Microsoft_Windows_UserAccountControlEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v10, v9, v12, v13, &v15);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005d88  mov     [rsp+arg_8], rbx
0x180005d8d  push    rbp
0x180005d8e  push    rsi
0x180005d8f  push    rdi
0x180005d90  sub     rsp, 50h
0x180005d94  mov     rax, cs:__security_cookie
0x180005d9b  xor     rax, rsp
0x180005d9e  mov     [rsp+68h+var_28], rax
0x180005da3  mov     rbx, rcx
0x180005da6  mov     rbp, r9
0x180005da9  mov     ecx, 0B8h; Size
0x180005dae  mov     rsi, r8
0x180005db1  mov     edi, edx
0x180005db3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005db8  test    rax, rax
0x180005dbb  jz      short loc_180005DC7
0x180005dbd  mov     edx, edi; int
0x180005dbf  mov     rcx, rax; this
0x180005dc2  call    ??0CUACSettingsPage@@QEAA@H@Z; CUACSettingsPage::CUACSettingsPage(int)
0x180005dc7  mov     [rbx+0C8h], rax
0x180005dce  test    rax, rax
0x180005dd1  jz      short loc_180005E08
0x180005dd3  mov     r9, rbx; struct DirectUI::Element *
0x180005dd6  mov     [rsp+68h+var_48], rbp; struct IOleCommandTarget *
0x180005ddb  mov     r8, rsi; struct DirectUI::NativeHWNDHost *
0x180005dde  mov     edx, edi; int
0x180005de0  mov     rcx, rax; this
0x180005de3  call    ?InitializePage@CUACSettingsPage@@QEAAJHPEAVNativeHWNDHost@DirectUI@@PEAVElement@3@PEAUIOleCommandTarget@@@Z; CUACSettingsPage::InitializePage(int,DirectUI::NativeHWNDHost *,DirectUI::Element *,IOleCommandTarget *)
0x180005de8  mov     ebx, eax
0x180005dea  test    eax, eax
0x180005dec  js      short loc_180005E0D
0x180005dee  test    cs:Microsoft_Windows_UserAccountControlEnableBits, 1
0x180005df5  jz      short loc_180005E0D
0x180005df7  lea     rax, [rsp+68h+var_38]
0x180005dfc  mov     [rsp+68h+var_48], rax; PEVENT_DATA_DESCRIPTOR
0x180005e01  call    McGenEventWrite_EventWriteTransfer
0x180005e06  jmp     short loc_180005E0D
0x180005e08  mov     ebx, 8007000Eh
0x180005e0d  mov     eax, ebx
0x180005e0f  mov     rcx, [rsp+68h+var_28]
0x180005e14  xor     rcx, rsp; StackCookie
0x180005e17  call    __security_check_cookie
0x180005e1c  mov     rbx, [rsp+68h+arg_8]
0x180005e21  add     rsp, 50h
0x180005e25  pop     rdi
0x180005e26  pop     rsi
0x180005e27  pop     rbp
0x180005e28  retn
```

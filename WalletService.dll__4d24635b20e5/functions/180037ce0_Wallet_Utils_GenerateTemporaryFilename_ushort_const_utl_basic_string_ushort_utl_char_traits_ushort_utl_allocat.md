# Wallet::Utils::GenerateTemporaryFilename(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180037ce0`
- end: `0x180037e51`
- name: `?GenerateTemporaryFilename@Utils@Wallet@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(Wallet::Utils *, __int64)`
- caller_count: `4`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18001af30`
- `0x18002d3f0`
- `0x18002e5b0`
- `0x180035260`

## callees

- `0x18000acac`
- `0x18001400c`
- `0x18001c638`
- `0x180036948`
- `0x1800376c0`
- `0x180037ce0`
- `0x180039750`
- `0x180043090`

## import_xrefs

- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180037d42`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180037d42`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wallet::Utils::GenerateTemporaryFilename(Wallet::Utils *a1, __int64 a2)
{
  bool IsPhoneOS; // al
  const GUID *v5; // rcx
  unsigned __int16 *v6; // rdx
  HRESULT Guid; // ebx
  unsigned int v8; // r8d
  const unsigned __int16 *v9; // rdx
  __int64 v10; // r8
  PWSTR ppszPath[2]; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v14[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v15[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v16[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  ppszPath[0] = 0;
  IsPhoneOS = Wallet::Utils::IsPhoneOS(a1);
  v5 = (const GUID *)FOLDERID_TempAppData;
  if ( !IsPhoneOS )
    v5 = &FOLDERID_LocalAppData;
  Guid = SHGetKnownFolderPath(v5, 0x8000u, 0, ppszPath);
  if ( Guid >= 0 )
  {
    Guid = Wallet::Utils::CreateGuid(sz, v6, v8);
    if ( Guid >= 0 )
    {
      Guid = StringCchPrintfW(v16, 0x104u, (const unsigned __int16 *)a1, sz);
      if ( Guid >= 0 )
      {
        Guid = StringCchPrintfW(v14, 0x104u, L"%s\\%s", ppszPath[0], L"Wallet");
        if ( Guid >= 0 )
        {
          Guid = Wallet::FileUtils::RecursiveCreateDirectory((Wallet::FileUtils *)v14, v9);
          if ( Guid >= 0 )
          {
            Guid = StringCchPrintfW(v15, 0x104u, L"%s\\%s", v14, v16);
            if ( Guid >= 0 )
            {
              v10 = -1;
              do
                ++v10;
              while ( v15[v10] );
              Guid = (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                        a2,
                                        v15) == 0
                   ? 0x8007000E
                   : 0;
            }
          }
        }
      }
    }
  }
  tlx::unique_any<tlx::handle_traits<unsigned char *,void (*)(void *),&void CoTaskMemFree(void *),0>>::~unique_any<tlx::handle_traits<unsigned char *,void (*)(void *),&void CoTaskMemFree(void *),0>>(ppszPath);
  return (unsigned int)Guid;
}

```

## disassembly

```asm
0x180037ce0  mov     [rsp-8+arg_0], rbx
0x180037ce5  mov     [rsp-8+arg_10], rsi
0x180037cea  push    rbp
0x180037ceb  push    rdi
0x180037cec  push    r14
0x180037cee  lea     rbp, [rsp-5D0h]
0x180037cf6  sub     rsp, 6D0h
0x180037cfd  mov     rax, cs:__security_cookie
0x180037d04  xor     rax, rsp
0x180037d07  mov     [rbp+5E0h+var_20], rax
0x180037d0e  mov     rsi, rdx
0x180037d11  mov     rdi, rcx
0x180037d14  xor     r14d, r14d
0x180037d17  mov     [rsp+6E0h+ppszPath], r14
0x180037d1c  call    ?IsPhoneOS@Utils@Wallet@@YA_NXZ; Wallet::Utils::IsPhoneOS(void)
0x180037d21  lea     rdx, FOLDERID_LocalAppData
0x180037d28  lea     rcx, FOLDERID_TempAppData
0x180037d2f  test    al, al
0x180037d31  cmovz   rcx, rdx; rfid
0x180037d35  lea     r9, [rsp+6E0h+ppszPath]; ppszPath
0x180037d3a  xor     r8d, r8d; hToken
0x180037d3d  mov     edx, 8000h; dwFlags
0x180037d42  call    cs:__imp_SHGetKnownFolderPath
0x180037d48  mov     ebx, eax
0x180037d4a  test    eax, eax
0x180037d4c  js      loc_180037E1E
0x180037d52  lea     rcx, [rsp+6E0h+sz]; lpsz
0x180037d57  call    ?CreateGuid@Utils@Wallet@@YAJPEAGI@Z; Wallet::Utils::CreateGuid(ushort *,uint)
0x180037d5c  mov     ebx, eax
0x180037d5e  test    eax, eax
0x180037d60  js      loc_180037E1E
0x180037d66  lea     r9, [rsp+6E0h+sz]
0x180037d6b  mov     r8, rdi; unsigned __int16 *
0x180037d6e  mov     edi, 104h
0x180037d73  mov     edx, edi; unsigned __int64
0x180037d75  lea     rcx, [rbp+5E0h+var_230]; unsigned __int16 *
0x180037d7c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037d81  mov     ebx, eax
0x180037d83  test    eax, eax
0x180037d85  js      loc_180037E1E
0x180037d8b  lea     rax, aWallet; "Wallet"
0x180037d92  mov     [rsp+6E0h+var_6C0], rax
0x180037d97  mov     r9, [rsp+6E0h+ppszPath]
0x180037d9c  lea     r8, aSS_0; "%s\\%s"
0x180037da3  mov     edx, edi; unsigned __int64
0x180037da5  lea     rcx, [rbp+5E0h+var_650]; unsigned __int16 *
0x180037da9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037dae  mov     ebx, eax
0x180037db0  test    eax, eax
0x180037db2  js      short loc_180037E1E
0x180037db4  lea     rcx, [rbp+5E0h+var_650]; this
0x180037db8  call    ?RecursiveCreateDirectory@FileUtils@Wallet@@YAJPEBG@Z; Wallet::FileUtils::RecursiveCreateDirectory(ushort const *)
0x180037dbd  mov     ebx, eax
0x180037dbf  test    eax, eax
0x180037dc1  js      short loc_180037E1E
0x180037dc3  lea     rax, [rbp+5E0h+var_230]
0x180037dca  mov     [rsp+6E0h+var_6C0], rax
0x180037dcf  lea     r9, [rbp+5E0h+var_650]
0x180037dd3  lea     r8, aSS_0; "%s\\%s"
0x180037dda  mov     edx, edi; unsigned __int64
0x180037ddc  lea     rcx, [rbp+5E0h+var_440]; unsigned __int16 *
0x180037de3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037de8  mov     ebx, eax
0x180037dea  test    eax, eax
0x180037dec  js      short loc_180037E1E
0x180037dee  lea     rax, [rbp+5E0h+var_440]
0x180037df5  or      r8, 0FFFFFFFFFFFFFFFFh
0x180037df9  inc     r8
0x180037dfc  cmp     [rax+r8*2], r14w
0x180037e01  jnz     short loc_180037DF9
0x180037e03  lea     rdx, [rbp+5E0h+var_440]
0x180037e0a  mov     rcx, rsi
0x180037e0d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180037e12  neg     al
0x180037e14  sbb     ebx, ebx
0x180037e16  not     ebx
0x180037e18  and     ebx, 8007000Eh
0x180037e1e  lea     rcx, [rsp+6E0h+ppszPath]
0x180037e23  call    ??1?$unique_any@U?$handle_traits@PEAEP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>::~unique_any<tlx::handle_traits<uchar *,void (*)(void *),&CoTaskMemFree(void *),0>>(void)
0x180037e28  mov     eax, ebx
0x180037e2a  mov     rcx, [rbp+5E0h+var_20]
0x180037e31  xor     rcx, rsp; StackCookie
0x180037e34  call    __security_check_cookie
0x180037e39  lea     r11, [rsp+6E0h+var_10]
0x180037e41  mov     rbx, [r11+20h]
0x180037e45  mov     rsi, [r11+30h]
0x180037e49  mov     rsp, r11
0x180037e4c  pop     r14
0x180037e4e  pop     rdi
0x180037e4f  pop     rbp
0x180037e50  retn
```

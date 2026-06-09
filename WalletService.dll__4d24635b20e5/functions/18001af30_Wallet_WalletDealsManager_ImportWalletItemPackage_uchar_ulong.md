# Wallet::WalletDealsManager::ImportWalletItemPackage(uchar *,ulong)

- ea: `0x18001af30`
- end: `0x18001b1af`
- name: `?ImportWalletItemPackage@WalletDealsManager@Wallet@@UEAAJPEAEK@Z`
- size: `639`
- prototype: `__int64 __fastcall(Wallet::WalletDealsManager *this, unsigned __int8 *, DWORD)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003ae4`
- `0x1800043b8`
- `0x1800056c0`
- `0x18000d8d8`
- `0x180013f78`
- `0x18001aa00`
- `0x18001aa30`
- `0x18001af30`
- `0x180037ce0`
- `0x180039230`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afe5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001afd0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001afd0`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b029`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18001b029`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b0fe`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b0fe`
- `dsclient!DSCreateSharedFileToken` at `0x18001b0c4`
- `dsclient!DSCreateSharedFileToken` at `0x18001b0c4`

## pseudocode

```c
__int64 __fastcall Wallet::WalletDealsManager::ImportWalletItemPackage(
        Wallet::WalletDealsManager *this,
        unsigned __int8 *a2,
        DWORD a3)
{
  signed int TemporaryFilename; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64); // rbx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  HANDLE v21; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  LPCWSTR lpFileName[5]; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v25[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+90h] [rbp-70h]
  const wchar_t *v28; // [rsp+98h] [rbp-68h]
  __int64 v29; // [rsp+A0h] [rbp-60h]
  const wchar_t *v30; // [rsp+A8h] [rbp-58h]
  _BYTE v31[288]; // [rsp+B0h] [rbp-50h] BYREF

  v23 = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  if ( !a2 )
  {
    TemporaryFilename = -2147467261;
    goto LABEL_22;
  }
  TemporaryFilename = Wallet::Utils::GenerateTemporaryFilename(L"Import%s.mswallet");
  if ( TemporaryFilename < 0 )
    goto LABEL_22;
  NumberOfBytesWritten[0] = 0;
  FileW = CreateFileW(lpFileName[0], 0x40000000u, 2u, 0, 1u, 0x10000000u, 0);
  v21 = FileW;
  if ( (unsigned __int64)FileW + 1 > 1 && WriteFile(FileW, a2, a3, NumberOfBytesWritten, 0) )
  {
    if ( NumberOfBytesWritten[0] != a3 )
    {
      TemporaryFilename = -2147418113;
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v21);
LABEL_16:
      DeleteFileW(lpFileName[0]);
      goto LABEL_22;
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v21);
    *(_QWORD *)NumberOfBytesWritten = 0;
    v28 = L"S-1-5-18";
    v30 = L"S-1-5-18";
    v21 = 0;
    v25[0] = 0;
    v25[1] = 1;
    v26 = 2;
    v27 = 0;
    v29 = 0;
    memset_0(v31, 0, sizeof(v31));
    v8 = tlx::replace<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>(&v23);
    TemporaryFilename = DSCreateSharedFileToken(lpFileName[0], v25, 0, 0, v8);
    if ( TemporaryFilename < 0
      || (TemporaryFilename = Wallet::Utils::GetWalletPackageProcessor(NumberOfBytesWritten, v23), TemporaryFilename < 0) )
    {
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v21, v9, v10);
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(
        NumberOfBytesWritten,
        v11,
        v12);
      goto LABEL_16;
    }
    v13 = *(_QWORD *)NumberOfBytesWritten;
    v14 = *(__int64 (__fastcall **)(__int64, __int64))(**(_QWORD **)NumberOfBytesWritten + 32LL);
    v15 = ce::pointerTo<IWalletNotification>(&v21);
    TemporaryFilename = v14(v13, v15);
    if ( TemporaryFilename >= 0 )
    {
      TemporaryFilename = (*(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)v21 + 144LL))(v21);
      if ( TemporaryFilename >= 0 )
      {
        TemporaryFilename = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)NumberOfBytesWritten + 40LL))(*(_QWORD *)NumberOfBytesWritten);
        if ( TemporaryFilename >= 0 )
          TemporaryFilename = 0;
      }
    }
    ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v21, v16, v17);
    ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(NumberOfBytesWritten, v18, v19);
  }
  else
  {
    LastError = GetLastError();
    TemporaryFilename = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        TemporaryFilename = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      TemporaryFilename = -2143748092;
    }
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v21);
  }
LABEL_22:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
  tlx::unique_any<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>::~unique_any<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>(&v23);
  return (unsigned int)TemporaryFilename;
}

```

## disassembly

```asm
0x18001af30  mov     [rsp-8+arg_0], rbx
0x18001af35  push    rbp
0x18001af36  push    rsi
0x18001af37  push    rdi
0x18001af38  lea     rbp, [rsp-0E0h]
0x18001af40  sub     rsp, 1E0h
0x18001af47  mov     rax, cs:__security_cookie
0x18001af4e  xor     rax, rsp
0x18001af51  mov     [rbp+0F0h+var_20], rax
0x18001af58  lea     rcx, [rsp+1F0h+lpFileName]
0x18001af5d  mov     [rsp+1F0h+var_1A0], 0
0x18001af66  mov     edi, r8d
0x18001af69  mov     rsi, rdx
0x18001af6c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001af71  test    rsi, rsi
0x18001af74  jnz     short loc_18001AF80
0x18001af76  mov     ebx, 80004003h
0x18001af7b  jmp     loc_18001B177
0x18001af80  lea     rdx, [rsp+1F0h+lpFileName]
0x18001af85  lea     rcx, aImportSMswalle; "Import%s.mswallet"
0x18001af8c  call    ?GenerateTemporaryFilename@Utils@Wallet@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::GenerateTemporaryFilename(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18001af91  mov     ebx, eax
0x18001af93  test    eax, eax
0x18001af95  js      loc_18001B177
0x18001af9b  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x18001afa0  xor     r9d, r9d; lpSecurityAttributes
0x18001afa3  mov     [rsp+1F0h+hTemplateFile], 0; hTemplateFile
0x18001afac  mov     edx, 40000000h; dwDesiredAccess
0x18001afb1  mov     [rsp+1F0h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x18001afb9  mov     [rsp+1F0h+NumberOfBytesWritten], 0
0x18001afc1  lea     ebx, [r9+2]
0x18001afc5  mov     [rsp+1F0h+dwCreationDisposition], 1; dwCreationDisposition
0x18001afcd  mov     r8d, ebx; dwShareMode
0x18001afd0  call    cs:__imp_CreateFileW
0x18001afd6  mov     [rsp+1F0h+var_1B0], rax
0x18001afdb  lea     rcx, [rax+1]
0x18001afdf  cmp     rcx, 1
0x18001afe3  ja      short loc_18001B012
0x18001afe5  call    cs:__imp_GetLastError
0x18001afeb  mov     ebx, eax
0x18001afed  test    eax, eax
0x18001afef  jz      short loc_18001AFFE
0x18001aff1  jle     short loc_18001B003
0x18001aff3  movzx   ebx, ax
0x18001aff6  or      ebx, 80070000h
0x18001affc  jmp     short loc_18001B003
0x18001affe  mov     ebx, 80390004h
0x18001b003  lea     rcx, [rsp+1F0h+var_1B0]
0x18001b008  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001b00d  jmp     loc_18001B177
0x18001b012  lea     r9, [rsp+1F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001b017  mov     qword ptr [rsp+1F0h+dwCreationDisposition], 0; lpOverlapped
0x18001b020  mov     r8d, edi; nNumberOfBytesToWrite
0x18001b023  mov     rdx, rsi; lpBuffer
0x18001b026  mov     rcx, rax; hFile
0x18001b029  call    cs:__imp_WriteFile
0x18001b02f  test    eax, eax
0x18001b031  jz      short loc_18001AFE5
0x18001b033  lea     rcx, [rsp+1F0h+var_1B0]
0x18001b038  cmp     [rsp+1F0h+NumberOfBytesWritten], edi
0x18001b03c  jz      short loc_18001B04D
0x18001b03e  mov     ebx, 8000FFFFh
0x18001b043  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001b048  jmp     loc_18001B0F9
0x18001b04d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18001b052  lea     rcx, aS1518; "S-1-5-18"
0x18001b059  mov     qword ptr [rsp+1F0h+NumberOfBytesWritten], 0
0x18001b062  mov     [rbp+0F0h+var_158], rcx
0x18001b066  xor     edx, edx; Val
0x18001b068  mov     [rbp+0F0h+var_148], rcx
0x18001b06c  mov     r8d, 120h; Size
0x18001b072  lea     rcx, [rbp+0F0h+var_140]; void *
0x18001b076  mov     [rsp+1F0h+var_1B0], 0
0x18001b07f  mov     [rbp+0F0h+var_170], 0
0x18001b086  mov     [rbp+0F0h+var_16C], 1
0x18001b08d  mov     [rbp+0F0h+var_168], rbx
0x18001b091  mov     [rbp+0F0h+var_160], 0
0x18001b099  mov     [rbp+0F0h+var_150], 0
0x18001b0a1  call    memset_0
0x18001b0a6  lea     rcx, [rsp+1F0h+var_1A0]
0x18001b0ab  call    ??$replace@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAGAEAV?$unique_any@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>(tlx::unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>> &)
0x18001b0b0  mov     rcx, [rsp+1F0h+lpFileName]
0x18001b0b5  lea     rdx, [rbp+0F0h+var_170]
0x18001b0b9  xor     r9d, r9d
0x18001b0bc  mov     qword ptr [rsp+1F0h+dwCreationDisposition], rax
0x18001b0c1  xor     r8d, r8d
0x18001b0c4  call    cs:__imp_DSCreateSharedFileToken
0x18001b0ca  mov     ebx, eax
0x18001b0cc  test    eax, eax
0x18001b0ce  js      short loc_18001B0E5
0x18001b0d0  mov     rdx, [rsp+1F0h+var_1A0]
0x18001b0d5  lea     rcx, [rsp+1F0h+NumberOfBytesWritten]
0x18001b0da  call    ?GetWalletPackageProcessor@Utils@Wallet@@YAJAEAV?$CComPtr@UIWalletPackageProcessor@@@ATL@@PEBG@Z; Wallet::Utils::GetWalletPackageProcessor(ATL::CComPtr<IWalletPackageProcessor> &,ushort const *)
0x18001b0df  mov     ebx, eax
0x18001b0e1  test    eax, eax
0x18001b0e3  jns     short loc_18001B106
0x18001b0e5  lea     rcx, [rsp+1F0h+var_1B0]
0x18001b0ea  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18001b0ef  lea     rcx, [rsp+1F0h+NumberOfBytesWritten]
0x18001b0f4  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18001b0f9  mov     rcx, [rsp+1F0h+lpFileName]; lpFileName
0x18001b0fe  call    cs:__imp_DeleteFileW
0x18001b104  jmp     short loc_18001B177
0x18001b106  mov     rdi, qword ptr [rsp+1F0h+NumberOfBytesWritten]
0x18001b10b  lea     rcx, [rsp+1F0h+var_1B0]
0x18001b110  mov     rax, [rdi]
0x18001b113  mov     rbx, [rax+20h]
0x18001b117  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x18001b11c  mov     rdx, rax
0x18001b11f  mov     rcx, rdi
0x18001b122  mov     rax, rbx
0x18001b125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b12a  mov     ebx, eax
0x18001b12c  test    eax, eax
0x18001b12e  js      short loc_18001B163
0x18001b130  mov     rcx, [rsp+1F0h+var_1B0]
0x18001b135  mov     rax, [rcx]
0x18001b138  mov     rax, [rax+90h]
0x18001b13f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b144  mov     ebx, eax
0x18001b146  test    eax, eax
0x18001b148  js      short loc_18001B163
0x18001b14a  mov     rcx, qword ptr [rsp+1F0h+NumberOfBytesWritten]
0x18001b14f  mov     rax, [rcx]
0x18001b152  mov     rax, [rax+28h]
0x18001b156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b15b  mov     ebx, eax
0x18001b15d  test    eax, eax
0x18001b15f  js      short loc_18001B163
0x18001b161  xor     ebx, ebx
0x18001b163  lea     rcx, [rsp+1F0h+var_1B0]
0x18001b168  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18001b16d  lea     rcx, [rsp+1F0h+NumberOfBytesWritten]
0x18001b172  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18001b177  lea     rcx, [rsp+1F0h+lpFileName]
0x18001b17c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001b181  lea     rcx, [rsp+1F0h+var_1A0]
0x18001b186  call    ??1?$unique_any@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>::~unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>(void)
0x18001b18b  mov     eax, ebx
0x18001b18d  mov     rcx, [rbp+0F0h+var_20]
0x18001b194  xor     rcx, rsp; StackCookie
0x18001b197  call    __security_check_cookie
0x18001b19c  mov     rbx, [rsp+1F0h+arg_0]
0x18001b1a4  add     rsp, 1E0h
0x18001b1ab  pop     rdi
0x18001b1ac  pop     rsi
0x18001b1ad  pop     rbp
0x18001b1ae  retn
```

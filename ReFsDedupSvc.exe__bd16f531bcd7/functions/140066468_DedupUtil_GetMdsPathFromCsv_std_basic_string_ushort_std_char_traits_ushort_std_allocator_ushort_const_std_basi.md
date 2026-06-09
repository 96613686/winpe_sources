# DedupUtil::GetMdsPathFromCsv(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140066468`
- end: `0x1400666f7`
- name: `?GetMdsPathFromCsv@DedupUtil@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `655`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x1400668bc`
- `0x14006f5e0`
- `0x1400793e8`
- `0x14007a6fc`
- `0x14007af84`

## callees

- `0x140004870`
- `0x140004be0`
- `0x140004f20`
- `0x1400057f8`
- `0x1400172f0`
- `0x140019600`
- `0x14001983c`
- `0x14001c194`
- `0x140023d88`
- `0x140063bbc`
- `0x140066468`
- `0x1400667a0`
- `0x1400695d8`
- `0x14006968c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400665d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400665d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140066684`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400664e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400664e7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140066586`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x140066586`

## string_xrefs

- `0x1400666a7`: `Unable to create volume handle for path %s, error = 0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DedupUtil::GetMdsPathFromCsv(__int64 a1, __int64 a2)
{
  unsigned int v4; // r14d
  unsigned int v5; // r15d
  const WCHAR *v6; // rax
  const struct std::nothrow_t *v7; // rdx
  char *FileW; // rbx
  _DWORD *v9; // rdi
  DWORD v10; // esi
  _DWORD *v11; // rax
  DWORD LastError; // eax
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-69h] BYREF
  char *v18; // [rsp+48h] [rbp-61h] BYREF
  __int64 v19; // [rsp+50h] [rbp-59h] BYREF
  __int128 InBuffer; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v21[16]; // [rsp+68h] [rbp-41h] BYREF
  __int64 v22; // [rsp+78h] [rbp-31h]
  _BYTE v23[16]; // [rsp+88h] [rbp-21h] BYREF
  __int64 v24; // [rsp+98h] [rbp-11h]
  _BYTE v25[32]; // [rsp+A8h] [rbp-1h] BYREF

  v4 = 0;
  DedupUtil::GetVolumeGuid((__int64)v21, a1, 0);
  if ( !v22 )
  {
    v5 = 87;
LABEL_20:
    std::wstring::_Tidy_deallocate(v21);
    return v5;
  }
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
  FileW = (char *)CreateFileW(v6, 0x80000000, 3u, 0, 3u, 0, 0);
  v18 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = 0;
    v10 = 272;
    InBuffer = 0;
    v5 = 8;
    LODWORD(InBuffer) = 8;
    while ( 1 )
    {
      BytesReturned = 0;
      if ( v9 )
        operator delete(v9, v7);
      v11 = operator new[](v10, (const struct std::nothrow_t *)std::nothrow);
      v9 = v11;
      if ( !v11 )
        break;
      memset_0(v11, 0, v10);
      if ( DeviceIoControl(FileW, 0x902D4u, &InBuffer, 0x10u, v9, v10, &BytesReturned, 0) )
      {
        if ( *v9 == v9[1] )
        {
          std::wstring::wstring(v23, L"\\??\\GLOBALROOT");
          v13 = std::wstring::wstring(v25, v9 + 3);
          std::wstring::operator=(a2, v13);
          std::wstring::_Tidy_deallocate(v25);
          v14 = v24;
          v15 = std::wstring::find(a2, v23);
          std::wstring::erase(a2, v15, v14);
          std::wstring::_Tidy_deallocate(v23);
        }
        else
        {
          v4 = 5990;
        }
        goto LABEL_18;
      }
      LastError = GetLastError();
      v4 = LastError;
      switch ( LastError )
      {
        case 0x3E5u:
          WaitForSingleObject(FileW, 0xFFFFFFFF);
LABEL_18:
          operator delete(v9, v7);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
          std::wstring::_Tidy_deallocate(v21);
          return v4;
        case 0x7Au:
          v10 *= 2;
          break;
        case 0xEAu:
          v10 = v9[2] + 12;
          break;
        default:
          goto LABEL_18;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
    goto LABEL_20;
  }
  BytesReturned = GetLastError();
  v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  DedupUtil::Print<unsigned short const *,unsigned long &>(
    6,
    L"Unable to create volume handle for path %s, error = 0x%x\n",
    &v19,
    &BytesReturned);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
  std::wstring::_Tidy_deallocate(v21);
  return BytesReturned;
}

```

## disassembly

```asm
0x140066468  mov     [rsp-8+arg_10], rbx
0x14006646d  push    rbp
0x14006646e  push    rsi
0x14006646f  push    rdi
0x140066470  push    r12
0x140066472  push    r13
0x140066474  push    r14
0x140066476  push    r15
0x140066478  lea     rbp, [rsp-27h]
0x14006647d  sub     rsp, 0D0h
0x140066484  mov     rax, cs:__security_cookie
0x14006648b  xor     rax, rsp
0x14006648e  mov     [rbp+57h+var_38], rax
0x140066492  mov     r13, rdx
0x140066495  mov     rdi, rcx
0x140066498  xor     r12d, r12d
0x14006649b  mov     r14d, r12d
0x14006649e  xor     r8d, r8d
0x1400664a1  mov     rdx, rcx
0x1400664a4  lea     rcx, [rbp+57h+var_98]
0x1400664a8  call    ?GetVolumeGuid@DedupUtil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@_N@Z; DedupUtil::GetVolumeGuid(std::wstring const &,bool)
0x1400664ad  nop
0x1400664ae  cmp     [rbp+57h+var_88], r12
0x1400664b2  jnz     short loc_1400664BE
0x1400664b4  lea     r15d, [r12+57h]
0x1400664b9  jmp     loc_140066676
0x1400664be  lea     rcx, [rbp+57h+var_98]
0x1400664c2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1400664c7  mov     rcx, rax; lpFileName
0x1400664ca  mov     [rsp+100h+hTemplateFile], r12; hTemplateFile
0x1400664cf  mov     [rsp+100h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1400664d4  mov     r8d, 3; dwShareMode
0x1400664da  mov     [rsp+100h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400664df  xor     r9d, r9d; lpSecurityAttributes
0x1400664e2  mov     edx, 80000000h; dwDesiredAccess
0x1400664e7  call    cs:__imp_CreateFileW
0x1400664ee  nop     dword ptr [rax+rax+00h]
0x1400664f3  mov     rbx, rax
0x1400664f6  mov     [rbp+57h+var_B8], rax
0x1400664fa  dec     rax
0x1400664fd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140066501  ja      loc_140066684
0x140066507  mov     rdi, r12
0x14006650a  mov     esi, 110h
0x14006650f  xorps   xmm0, xmm0
0x140066512  movups  [rbp+57h+InBuffer], xmm0
0x140066516  mov     r15d, 8
0x14006651c  mov     dword ptr [rbp+57h+InBuffer], r15d
0x140066520  mov     [rbp+57h+BytesReturned], r12d
0x140066524  test    rdi, rdi
0x140066527  jz      short loc_140066531
0x140066529  mov     rcx, rdi; void *
0x14006652c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140066531  mov     r12d, esi
0x140066534  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14006653b  mov     ecx, esi; unsigned __int64
0x14006653d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140066542  mov     rdi, rax
0x140066545  test    rax, rax
0x140066548  jz      loc_14006666C
0x14006654e  mov     r8d, r12d; Size
0x140066551  xor     edx, edx; Val
0x140066553  mov     rcx, rax; void *
0x140066556  call    memset_0
0x14006655b  xor     r12d, r12d
0x14006655e  mov     [rsp+100h+lpOverlapped], r12; lpOverlapped
0x140066563  lea     rax, [rbp+57h+BytesReturned]
0x140066567  mov     [rsp+100h+hTemplateFile], rax; lpBytesReturned
0x14006656c  mov     [rsp+100h+dwFlagsAndAttributes], esi; nOutBufferSize
0x140066570  mov     qword ptr [rsp+100h+dwCreationDisposition], rdi; lpOutBuffer
0x140066575  lea     r9d, [r12+10h]; nInBufferSize
0x14006657a  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x14006657e  mov     edx, 902D4h; dwIoControlCode
0x140066583  mov     rcx, rbx; hDevice
0x140066586  call    cs:__imp_DeviceIoControl
0x14006658d  nop     dword ptr [rax+rax+00h]
0x140066592  test    eax, eax
0x140066594  jnz     short loc_1400665E2
0x140066596  call    cs:__imp_GetLastError
0x14006659d  nop     dword ptr [rax+rax+00h]
0x1400665a2  mov     r14d, eax
0x1400665a5  cmp     eax, 3E5h
0x1400665aa  jz      short loc_1400665CE
0x1400665ac  cmp     eax, 7Ah ; 'z'
0x1400665af  jnz     short loc_1400665B8
0x1400665b1  add     esi, esi
0x1400665b3  jmp     loc_140066520
0x1400665b8  cmp     eax, 0EAh
0x1400665bd  jnz     loc_14006664B
0x1400665c3  mov     esi, [rdi+8]
0x1400665c6  add     esi, 0Ch
0x1400665c9  jmp     loc_140066520
0x1400665ce  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400665d1  mov     rcx, rbx; hHandle
0x1400665d4  call    cs:__imp_WaitForSingleObject
0x1400665db  nop     dword ptr [rax+rax+00h]
0x1400665e0  jmp     short loc_14006664B
0x1400665e2  mov     eax, [rdi+4]
0x1400665e5  cmp     [rdi], eax
0x1400665e7  jz      short loc_1400665F1
0x1400665e9  mov     r14d, 1766h
0x1400665ef  jmp     short loc_14006664B
0x1400665f1  lea     rdx, aGlobalroot_0; "\\??\\GLOBALROOT"
0x1400665f8  lea     rcx, [rbp+57h+var_78]
0x1400665fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140066601  nop
0x140066602  lea     rdx, [rdi+0Ch]
0x140066606  lea     rcx, [rbp+57h+var_58]
0x14006660a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14006660f  mov     rdx, rax
0x140066612  mov     rcx, r13
0x140066615  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14006661a  lea     rcx, [rbp+57h+var_58]
0x14006661e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140066623  mov     rbx, [rbp+57h+var_68]
0x140066627  lea     rdx, [rbp+57h+var_78]
0x14006662b  mov     rcx, r13
0x14006662e  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x140066633  mov     r8, rbx
0x140066636  mov     rdx, rax
0x140066639  mov     rcx, r13
0x14006663c  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x140066641  nop
0x140066642  lea     rcx, [rbp+57h+var_78]
0x140066646  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006664b  mov     rcx, rdi; void *
0x14006664e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140066653  nop
0x140066654  lea     rcx, [rbp+57h+var_B8]
0x140066658  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14006665d  nop
0x14006665e  lea     rcx, [rbp+57h+var_98]
0x140066662  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140066667  mov     eax, r14d
0x14006666a  jmp     short loc_1400666CF
0x14006666c  lea     rcx, [rbp+57h+var_B8]
0x140066670  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140066675  nop
0x140066676  lea     rcx, [rbp+57h+var_98]
0x14006667a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006667f  mov     eax, r15d
0x140066682  jmp     short loc_1400666CF
0x140066684  call    cs:__imp_GetLastError
0x14006668b  nop     dword ptr [rax+rax+00h]
0x140066690  mov     [rbp+57h+BytesReturned], eax
0x140066693  mov     rcx, rdi
0x140066696  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x14006669b  mov     [rbp+57h+var_B0], rax
0x14006669f  lea     r9, [rbp+57h+BytesReturned]
0x1400666a3  lea     r8, [rbp+57h+var_B0]
0x1400666a7  lea     rdx, aUnableToCreate; "Unable to create volume handle for path"...
0x1400666ae  mov     ecx, 6
0x1400666b3  call    ??$Print@PEBGAEAK@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBGAEAK@Z; DedupUtil::Print<ushort const *,ulong &>(DedupUtil::MessageType,ushort const *,ushort const * &&,ulong &)
0x1400666b8  nop
0x1400666b9  lea     rcx, [rbp+57h+var_B8]
0x1400666bd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400666c2  nop
0x1400666c3  lea     rcx, [rbp+57h+var_98]
0x1400666c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400666cc  mov     eax, [rbp+57h+BytesReturned]
0x1400666cf  mov     rcx, [rbp+57h+var_38]
0x1400666d3  xor     rcx, rsp; StackCookie
0x1400666d6  call    __security_check_cookie
0x1400666db  mov     rbx, [rsp+100h+arg_10]
0x1400666e3  add     rsp, 0D0h
0x1400666ea  pop     r15
0x1400666ec  pop     r14
0x1400666ee  pop     r13
0x1400666f0  pop     r12
0x1400666f2  pop     rdi
0x1400666f3  pop     rsi
0x1400666f4  pop     rbp
0x1400666f5  retn
```

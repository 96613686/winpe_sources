# CWinSATResultsInfo::GetDiskStrings(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001ddc4`
- end: `0x18001dfea`
- name: `?GetDiskStrings@CWinSATResultsInfo@@AEAAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180006c00`

## callees

- `0x1800015d0`
- `0x1800020f4`
- `0x18000255c`
- `0x1800035cc`
- `0x180004048`
- `0x180004198`
- `0x180004360`
- `0x180008490`
- `0x18000a104`
- `0x1800114ec`
- `0x18001ddc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de96`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001de86`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18001de86`
- `SHELL32!SHGetFolderPathW` at `0x18001de33`
- `SHELL32!SHGetFolderPathW` at `0x18001de33`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWinSATResultsInfo::GetDiskStrings(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT v5; // ebx
  signed int LastError; // eax
  HINSTANCE v8; // r8
  __int64 v9; // rdx
  HINSTANCE v10; // r8
  __int64 v11; // rax
  _QWORD *v12; // rax
  __int64 v13; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v14; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+40h] [rbp-98h] BYREF
  _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+48h] [rbp-90h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+50h] [rbp-88h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+58h] [rbp-80h] BYREF
  __int64 v19; // [rsp+60h] [rbp-78h]
  _DWORD v20[4]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v21[40]; // [rsp+78h] [rbp-60h] BYREF
  _BYTE v22[48]; // [rsp+A0h] [rbp-38h] BYREF
  __int64 v23; // [rsp+E0h] [rbp+8h] BYREF
  __int64 v24; // [rsp+F8h] [rbp+20h] BYREF

  v23 = a1;
  v19 = -2;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v24,
    260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::reserve(
    &v24,
    260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(&v24);
  v5 = SHGetFolderPathW(0, 38, 0, 0, *(LPWSTR *)(v24 + 24));
  if ( v5 < 0 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(&v24);
LABEL_7:
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
    return (unsigned int)v5;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(&v24);
  FreeBytesAvailableToCaller.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  if ( !GetDiskFreeSpaceExW(
          *(LPCWSTR *)(v24 + 24),
          &FreeBytesAvailableToCaller,
          &TotalNumberOfBytes,
          &TotalNumberOfFreeBytes) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = LastError;
    goto LABEL_7;
  }
  ((void (__fastcall *)(_QWORD, _QWORD))ConvertToBestString)(&v15, (_ULARGE_INTEGER)FreeBytesAvailableToCaller.QuadPart);
  ((void (__fastcall *)(_QWORD, _QWORD))ConvertToBestString)(&v14, (union _ULARGE_INTEGER)TotalNumberOfBytes.QuadPart);
  v9 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v21, 0x2710u, v8);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
    &v13,
    v9);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::reserve(
    a2,
    128);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
    a2,
    *(_QWORD *)(v13 + 24),
    *(_QWORD *)(v15 + 24),
    *(_QWORD *)(v14 + 24));
  try
  {
    v11 = mlib::MUILoader::MUILoader((mlib::MUILoader *)v22, 0x2716u, v10);
    v12 = (_QWORD *)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                      &v23,
                      v11);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::attach_buf(
      a3,
      *v12);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v23);
  }
  catch ( mlib::MSError v20 )
  {
    LODWORD(v23) = v20[0];
    mlib::MSError::~MSError((mlib::MSError *)v20);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v13);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v14);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v15);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
    return (unsigned int)v23;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v13);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v14);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v15);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v24);
  return 0;
}

```

## disassembly

```asm
0x18001ddc4  mov     rax, rsp
0x18001ddc7  mov     [rax+8], rcx
0x18001ddcb  push    rdi
0x18001ddcc  sub     rsp, 0D0h
0x18001ddd3  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x18001dddb  mov     [rax+10h], rbx
0x18001dddf  mov     [rax+18h], rsi
0x18001dde3  mov     rdi, r8
0x18001dde6  mov     rsi, rdx
0x18001dde9  mov     ebx, 104h
0x18001ddee  mov     edx, ebx
0x18001ddf0  lea     rcx, [rax+20h]
0x18001ddf4  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18001ddf9  nop
0x18001ddfa  mov     edx, ebx
0x18001ddfc  lea     rcx, [rsp+0D8h+arg_18]
0x18001de04  call    ?reserve@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::reserve(unsigned __int64)
0x18001de09  lea     rcx, [rsp+0D8h+arg_18]
0x18001de11  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18001de16  mov     rax, [rsp+0D8h+arg_18]
0x18001de1e  mov     rcx, [rax+18h]
0x18001de22  mov     [rsp+0D8h+pszPath], rcx; pszPath
0x18001de27  xor     r9d, r9d; dwFlags
0x18001de2a  xor     r8d, r8d; hToken
0x18001de2d  lea     edx, [r9+26h]; csidl
0x18001de31  xor     ecx, ecx; hwnd
0x18001de33  call    cs:__imp_SHGetFolderPathW
0x18001de3a  nop     dword ptr [rax+rax+00h]
0x18001de3f  mov     ebx, eax
0x18001de41  lea     rcx, [rsp+0D8h+arg_18]
0x18001de49  test    eax, eax
0x18001de4b  jns     short loc_18001DE54
0x18001de4d  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x18001de52  jmp     short loc_18001DEB0
0x18001de54  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(void)
0x18001de59  and     qword ptr [rsp+0D8h+FreeBytesAvailableToCaller], 0
0x18001de5f  and     qword ptr [rsp+0D8h+TotalNumberOfBytes], 0
0x18001de65  and     qword ptr [rsp+0D8h+TotalNumberOfFreeBytes], 0
0x18001de6b  mov     rax, [rsp+0D8h+arg_18]
0x18001de73  lea     r9, [rsp+0D8h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x18001de78  lea     r8, [rsp+0D8h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x18001de7d  lea     rdx, [rsp+0D8h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x18001de82  mov     rcx, [rax+18h]; lpDirectoryName
0x18001de86  call    cs:__imp_GetDiskFreeSpaceExW
0x18001de8d  nop     dword ptr [rax+rax+00h]
0x18001de92  test    eax, eax
0x18001de94  jnz     short loc_18001DEC4
0x18001de96  call    cs:__imp_GetLastError
0x18001de9d  nop     dword ptr [rax+rax+00h]
0x18001dea2  test    eax, eax
0x18001dea4  jle     short loc_18001DEAE
0x18001dea6  movzx   eax, ax
0x18001dea9  or      eax, 80070000h
0x18001deae  mov     ebx, eax
0x18001deb0  lea     rcx, [rsp+0D8h+arg_18]
0x18001deb8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001debd  mov     eax, ebx
0x18001debf  jmp     loc_18001DFD4
0x18001dec4  mov     rdx, qword ptr [rsp+0D8h+FreeBytesAvailableToCaller]
0x18001dec9  lea     rcx, [rsp+0D8h+var_98]
0x18001dece  call    ?ConvertToBestString@@YA?AV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@_K_N@Z; ConvertToBestString(unsigned __int64,bool)
0x18001ded3  nop
0x18001ded4  mov     rdx, qword ptr [rsp+0D8h+TotalNumberOfBytes]
0x18001ded9  lea     rcx, [rsp+0D8h+var_A0]
0x18001dede  call    ?ConvertToBestString@@YA?AV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@_K_N@Z; ConvertToBestString(unsigned __int64,bool)
0x18001dee3  nop
0x18001dee4  mov     edx, 2710h; unsigned __int16
0x18001dee9  lea     rcx, [rsp+0D8h+var_60]; this
0x18001deee  call    ??0MUILoader@mlib@@QEAA@GPEAUHINSTANCE__@@@Z; mlib::MUILoader::MUILoader(ushort,HINSTANCE__ *)
0x18001def3  mov     rdx, rax
0x18001def6  lea     rcx, [rsp+0D8h+var_A8]
0x18001defb  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x18001df00  nop
0x18001df01  mov     edx, 80h
0x18001df06  mov     rcx, rsi
0x18001df09  call    ?reserve@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAX_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::reserve(unsigned __int64)
0x18001df0e  mov     rax, [rsp+0D8h+var_A0]
0x18001df13  mov     r9, [rax+18h]
0x18001df17  mov     rax, [rsp+0D8h+var_98]
0x18001df1c  mov     r8, [rax+18h]
0x18001df20  mov     rax, [rsp+0D8h+var_A8]
0x18001df25  mov     rdx, [rax+18h]
0x18001df29  mov     rcx, rsi
0x18001df2c  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x18001df31  nop
0x18001df32  mov     edx, 2716h; unsigned __int16
0x18001df37  lea     rcx, [rsp+0D8h+var_38]; this
0x18001df3f  call    ??0MUILoader@mlib@@QEAA@GPEAUHINSTANCE__@@@Z; mlib::MUILoader::MUILoader(ushort,HINSTANCE__ *)
0x18001df44  mov     rdx, rax
0x18001df47  lea     rcx, [rsp+0D8h+arg_0]
0x18001df4f  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x18001df54  mov     rdx, [rax]
0x18001df57  mov     rcx, rdi
0x18001df5a  call    ?attach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXPEAV?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@2@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::attach_buf(mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x18001df5f  lea     rcx, [rsp+0D8h+arg_0]
0x18001df67  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001df6c  nop
0x18001df6d  lea     rcx, [rsp+0D8h+var_A8]
0x18001df72  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001df77  nop
0x18001df78  lea     rcx, [rsp+0D8h+var_A0]
0x18001df7d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001df82  nop
0x18001df83  lea     rcx, [rsp+0D8h+var_98]
0x18001df88  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001df8d  nop
0x18001df8e  lea     rcx, [rsp+0D8h+arg_18]
0x18001df96  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001df9b  xor     eax, eax
0x18001df9d  jmp     short loc_18001DFD4
0x18001df9f  lea     rcx, [rsp+0D8h+var_A8]
0x18001dfa4  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001dfa9  nop
0x18001dfaa  lea     rcx, [rsp+0D8h+var_A0]
0x18001dfaf  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001dfb4  nop
0x18001dfb5  lea     rcx, [rsp+0D8h+var_98]
0x18001dfba  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001dfbf  nop
0x18001dfc0  lea     rcx, [rsp+0D8h+arg_18]
0x18001dfc8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001dfcd  mov     eax, dword ptr [rsp+0D8h+arg_0]
0x18001dfd4  lea     r11, [rsp+0D8h+var_8]
0x18001dfdc  mov     rbx, [r11+18h]
0x18001dfe0  mov     rsi, [r11+20h]
0x18001dfe4  mov     rsp, r11
0x18001dfe7  pop     rdi
0x18001dfe8  retn
```

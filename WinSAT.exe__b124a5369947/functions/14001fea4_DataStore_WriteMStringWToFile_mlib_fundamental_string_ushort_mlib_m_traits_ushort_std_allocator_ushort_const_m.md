# DataStore::WriteMStringWToFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14001fea4`
- end: `0x1400200f4`
- name: `?WriteMStringWToFile@DataStore@@SAKAEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z`
- size: `592`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140013170`
- `0x140020374`

## callees

- `0x140004348`
- `0x1400085b4`
- `0x140017af0`
- `0x14001f0cc`
- `0x14001fea4`
- `0x14004fce4`
- `0x1400530a8`
- `0x140056f94`
- `0x140113220`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x1400200b8`
- `KERNEL32!DeleteFileW` at `0x1400200b8`
- `KERNEL32!CloseHandle` at `0x1400200a1`
- `KERNEL32!CloseHandle` at `0x1400200a1`
- `KERNEL32!WriteFile` at `0x14001ffa6`
- `KERNEL32!WriteFile` at `0x140020037`
- `KERNEL32!WriteFile` at `0x14001ffa6`
- `KERNEL32!WriteFile` at `0x140020037`
- `KERNEL32!SetLastError` at `0x1400200c4`
- `KERNEL32!SetLastError` at `0x1400200c4`

## pseudocode

```c
__int64 __fastcall DataStore::WriteMStringWToFile(__int64 a1, __int64 a2)
{
  void **v4; // r9
  __int64 v5; // rbx
  const unsigned __int16 *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // r8d
  __int64 v11; // rdx
  __int64 v12; // rbx
  const unsigned __int16 *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  DWORD v16; // ecx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFile; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[256]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwErrCode; // [rsp+240h] [rbp+140h]
  char v22; // [rsp+244h] [rbp+144h]
  __int64 v23; // [rsp+248h] [rbp+148h]

  hFile = (HANDLE)-1LL;
  NumberOfBytesWritten = 0;
  dwErrCode = 0;
  v22 = 1;
  v23 = 0;
  mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
  if ( mlib::MCreateFile(*(LPCWSTR *)(*(_QWORD *)a2 + 24LL), (const unsigned __int16 *)0x22, (unsigned int)&hFile, v4) )
  {
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::GetLastError(Buffer);
    v5 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw)
       + 240;
    v6 = mlib::MUISpf_(
           (mlib *)"base\\winsat\\exe\\datastore.cpp",
           (const char *)0x2DF,
           10016,
           *(_QWORD *)(*(_QWORD *)a2 + 24LL));
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5, v6);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v7, Buffer);
    std::endl(v8);
    goto LABEL_11;
  }
  if ( !WriteFile(hFile, &qword_1401304B8, 2u, &NumberOfBytesWritten, 0) )
  {
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::GetLastError(Buffer);
    v9 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw);
    v10 = 10019;
    v11 = 749;
LABEL_5:
    v12 = v9 + 240;
    v13 = mlib::MUISpf_(
            (mlib *)"base\\winsat\\exe\\datastore.cpp",
            (const char *)v11,
            v10,
            *(_QWORD *)(*(_QWORD *)a2 + 24LL));
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, v13);
    v15 = std::endl(v14);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v15, Buffer);
    goto LABEL_11;
  }
  if ( NumberOfBytesWritten != 2 )
    goto LABEL_10;
  if ( !WriteFile(hFile, *(LPCVOID *)(*(_QWORD *)a1 + 24LL), 2 * **(_DWORD **)a1, &NumberOfBytesWritten, 0) )
  {
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::GetLastError(Buffer);
    v9 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stderrw);
    v10 = 10020;
    v11 = 768;
    goto LABEL_5;
  }
  if ( NumberOfBytesWritten != 2LL * **(_QWORD **)a1 )
  {
LABEL_10:
    dwErrCode = 29;
    v22 = 1;
    mlib::WinErrorT<unsigned short,std::char_traits<unsigned short>,mlib::m_traits<unsigned short>>::fmt_desc(Buffer);
  }
LABEL_11:
  if ( hFile != (HANDLE)-1LL )
    CloseHandle(hFile);
  v16 = dwErrCode;
  if ( dwErrCode )
  {
    DeleteFileW(*(LPCWSTR *)(*(_QWORD *)a2 + 24LL));
    v16 = dwErrCode;
  }
  SetLastError(v16);
  return dwErrCode;
}

```

## disassembly

```asm
0x14001fea4  mov     [rsp-8+arg_10], rbx
0x14001fea9  mov     [rsp-8+arg_18], rsi
0x14001feae  push    rbp
0x14001feaf  lea     rbp, [rsp-160h]
0x14001feb7  sub     rsp, 260h
0x14001febe  mov     rax, cs:__security_cookie
0x14001fec5  xor     rax, rsp
0x14001fec8  mov     [rbp+160h+var_10], rax
0x14001fecf  mov     rbx, rcx
0x14001fed2  mov     [rsp+260h+hFile], 0FFFFFFFFFFFFFFFFh
0x14001fedb  lea     rcx, [rsp+260h+Buffer]; lpBuffer
0x14001fee0  mov     [rsp+260h+NumberOfBytesWritten], 0
0x14001fee8  mov     rsi, rdx
0x14001feeb  mov     [rbp+160h+dwErrCode], 0
0x14001fef5  mov     [rbp+160h+var_1C], 1
0x14001fefc  mov     [rbp+160h+var_18], 0
0x14001ff07  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x14001ff0c  mov     rcx, [rsi]
0x14001ff0f  lea     r8, [rsp+260h+hFile]; unsigned int
0x14001ff14  mov     edx, 22h ; '"'; unsigned __int16 *
0x14001ff19  mov     rcx, [rcx+18h]; lpFileName
0x14001ff1d  call    ?MCreateFile@mlib@@YAKPEBGKAEAPEAX@Z; mlib::MCreateFile(ushort const *,ulong,void * &)
0x14001ff22  test    eax, eax
0x14001ff24  jz      short loc_14001FF86
0x14001ff26  lea     rcx, [rsp+260h+Buffer]; lpBuffer
0x14001ff2b  call    ?GetLastError@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@QEAAKPEBG@Z; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::GetLastError(ushort const *)
0x14001ff30  lea     rcx, ?stderrw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stderrw
0x14001ff37  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001ff3c  mov     r9, [rsi]
0x14001ff3f  lea     rcx, aBaseWinsatExeD; "base\\winsat\\exe\\datastore.cpp"
0x14001ff46  mov     r8d, 2720h; int
0x14001ff4c  mov     edx, 2DFh; char *
0x14001ff51  lea     rbx, [rax+0F0h]
0x14001ff58  mov     r9, [r9+18h]; unsigned __int16
0x14001ff5c  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x14001ff61  mov     rdx, rax
0x14001ff64  mov     rcx, rbx
0x14001ff67  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14001ff6c  lea     rdx, [rsp+260h+Buffer]
0x14001ff71  mov     rcx, rax
0x14001ff74  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14001ff79  mov     rcx, rax
0x14001ff7c  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14001ff81  jmp     loc_140020094
0x14001ff86  mov     rcx, [rsp+260h+hFile]; hFile
0x14001ff8b  lea     r9, [rsp+260h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001ff90  mov     r8d, 2; nNumberOfBytesToWrite
0x14001ff96  mov     [rsp+260h+lpOverlapped], 0; lpOverlapped
0x14001ff9f  lea     rdx, qword_1401304B8; lpBuffer
0x14001ffa6  call    cs:__imp_WriteFile
0x14001ffac  test    eax, eax
0x14001ffae  jnz     short loc_140020010
0x14001ffb0  lea     rcx, [rsp+260h+Buffer]; lpBuffer
0x14001ffb5  call    ?GetLastError@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@QEAAKPEBG@Z; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::GetLastError(ushort const *)
0x14001ffba  lea     rcx, ?stderrw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stderrw
0x14001ffc1  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x14001ffc6  mov     r8d, 2723h; int
0x14001ffcc  mov     edx, 2EDh; char *
0x14001ffd1  mov     r9, [rsi]
0x14001ffd4  lea     rcx, aBaseWinsatExeD; "base\\winsat\\exe\\datastore.cpp"
0x14001ffdb  lea     rbx, [rax+0F0h]
0x14001ffe2  mov     r9, [r9+18h]; unsigned __int16
0x14001ffe6  call    ?MUISpf_@mlib@@YAPEBGPEBDHGZZ; mlib::MUISpf_(char const *,int,ushort,...)
0x14001ffeb  mov     rdx, rax
0x14001ffee  mov     rcx, rbx
0x14001fff1  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14001fff6  mov     rcx, rax
0x14001fff9  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14001fffe  lea     rdx, [rsp+260h+Buffer]
0x140020003  mov     rcx, rax
0x140020006  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14002000b  jmp     loc_140020094
0x140020010  cmp     [rsp+260h+NumberOfBytesWritten], 2
0x140020015  jnz     short loc_140020079
0x140020017  mov     rdx, [rbx]
0x14002001a  lea     r9, [rsp+260h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002001f  mov     rcx, [rsp+260h+hFile]; hFile
0x140020024  mov     [rsp+260h+lpOverlapped], 0; lpOverlapped
0x14002002d  mov     r8d, [rdx]
0x140020030  mov     rdx, [rdx+18h]; lpBuffer
0x140020034  add     r8d, r8d; nNumberOfBytesToWrite
0x140020037  call    cs:__imp_WriteFile
0x14002003d  test    eax, eax
0x14002003f  jnz     short loc_140020067
0x140020041  lea     rcx, [rsp+260h+Buffer]; lpBuffer
0x140020046  call    ?GetLastError@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@QEAAKPEBG@Z; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::GetLastError(ushort const *)
0x14002004b  lea     rcx, ?stderrw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stderrw
0x140020052  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140020057  mov     r8d, 2724h
0x14002005d  mov     edx, 300h
0x140020062  jmp     loc_14001FFD1
0x140020067  mov     rax, [rbx]
0x14002006a  mov     rdx, [rax]
0x14002006d  mov     eax, [rsp+260h+NumberOfBytesWritten]
0x140020071  add     rdx, rdx
0x140020074  cmp     rax, rdx
0x140020077  jz      short loc_140020094
0x140020079  lea     rcx, [rsp+260h+Buffer]; lpBuffer
0x14002007e  mov     [rbp+160h+dwErrCode], 1Dh
0x140020088  mov     [rbp+160h+var_1C], 1
0x14002008f  call    ?fmt_desc@?$WinErrorT@GU?$char_traits@G@std@@V?$m_traits@G@mlib@@@mlib@@AEAAKXZ; mlib::WinErrorT<ushort,std::char_traits<ushort>,mlib::m_traits<ushort>>::fmt_desc(void)
0x140020094  cmp     [rsp+260h+hFile], 0FFFFFFFFFFFFFFFFh
0x14002009a  jz      short loc_1400200A7
0x14002009c  mov     rcx, [rsp+260h+hFile]; hObject
0x1400200a1  call    cs:__imp_CloseHandle
0x1400200a7  mov     ecx, [rbp+160h+dwErrCode]
0x1400200ad  test    ecx, ecx
0x1400200af  jz      short loc_1400200C4
0x1400200b1  mov     rcx, [rsi]
0x1400200b4  mov     rcx, [rcx+18h]; lpFileName
0x1400200b8  call    cs:__imp_DeleteFileW
0x1400200be  mov     ecx, [rbp+160h+dwErrCode]; dwErrCode
0x1400200c4  call    cs:__imp_SetLastError
0x1400200ca  mov     eax, [rbp+160h+dwErrCode]
0x1400200d0  mov     rcx, [rbp+160h+var_10]
0x1400200d7  xor     rcx, rsp; StackCookie
0x1400200da  call    __security_check_cookie
0x1400200df  lea     r11, [rsp+260h+var_s0]
0x1400200e7  mov     rbx, [r11+20h]
0x1400200eb  mov     rsi, [r11+28h]
0x1400200ef  mov     rsp, r11
0x1400200f2  pop     rbp
0x1400200f3  retn
```

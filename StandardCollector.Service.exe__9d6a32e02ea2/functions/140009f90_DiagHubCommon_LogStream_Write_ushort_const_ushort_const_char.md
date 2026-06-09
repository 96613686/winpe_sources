# DiagHubCommon::LogStream::Write(ushort const *,ushort const *,char *)

- ea: `0x140009f90`
- end: `0x14000a219`
- name: `?Write@LogStream@DiagHubCommon@@QEAAXPEBG0PEAD@Z`
- size: `649`
- prototype: `void __fastcall(DiagHubCommon::LogStream *this, const unsigned __int16 *, const unsigned __int16 *, va_list)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14000a278`

## callees

- `0x140002e64`
- `0x140003010`
- `0x1400043a0`
- `0x140009f90`
- `0x14000b528`
- `0x14000b73c`
- `0x14000ca88`
- `0x14000cd94`
- `0x14000d69c`
- `0x1400137e0`
- `0x14001473e`
- `0x140014c70`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x14000a11e`
- `VCRUNTIME140!wcsrchr` at `0x14000a12f`
- `VCRUNTIME140!wcsrchr` at `0x14000a11e`
- `VCRUNTIME140!wcsrchr` at `0x14000a12f`
- `MSVCP140!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000a1df`
- `MSVCP140!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000a1df`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000a1e9`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x14000a1e9`
- `MSVCP140!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x14000a0c3`
- `MSVCP140!??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x14000a0c3`
- `MSVCP140!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x14000a073`
- `MSVCP140!??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ` at `0x14000a073`
- `MSVCP140!??0?$basic_iostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z` at `0x14000a08f`
- `MSVCP140!??0?$basic_iostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z` at `0x14000a08f`
- `MSVCP140!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000a16c`
- `MSVCP140!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x14000a16c`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x14000a03f`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x14000a03f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DiagHubCommon::LogStream::Write(
        DiagHubCommon::LogStream *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        va_list a4)
{
  const wchar_t *v6; // rdi
  signed __int64 v8; // rbx
  unsigned __int64 *v9; // rax
  _QWORD *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rdi
  _QWORD *i; // rbx
  wchar_t *Buffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h]
  _QWORD v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v20; // [rsp+70h] [rbp-90h] BYREF
  void **v21; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v22[96]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v23; // [rsp+E0h] [rbp-20h]
  int v24; // [rsp+E8h] [rbp-18h]
  _BYTE v25[104]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v26[32]; // [rsp+160h] [rbp+60h] BYREF

  if ( a2 )
  {
    v6 = a2;
    if ( a3 )
    {
      if ( *(_QWORD *)this != *((_QWORD *)this + 1) )
      {
        *(_OWORD *)Buffer = 0;
        v18 = 0;
        std::vector<unsigned short>::resize(Buffer, 0x2000);
        v8 = Buffer[1] - Buffer[0];
        v9 = _local_stdio_printf_options();
        __stdio_common_vsnwprintf_s(*v9, Buffer[0], v8 - 1, 0xFFFFFFFFFFFFFFFFuLL, a3, 0, a4);
        memset_0(v19, 0, 0xF8u);
        v19[0] = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbtable'{for `std::basic_istream<unsigned short>'};
        v20 = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbtable'{for `std::basic_ostream<unsigned short>'};
        std::basic_ios<unsigned short>::basic_ios<unsigned short>(v25);
        std::basic_iostream<unsigned short>::basic_iostream<unsigned short>(v19, &v21, 0);
        *(_QWORD *)((char *)v19 + *(int *)(v19[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
        *(_DWORD *)((char *)&v18 + *(int *)(v19[0] + 4LL) + 4) = *(_DWORD *)(v19[0] + 4LL) - 152;
        std::basic_streambuf<unsigned short>::basic_streambuf<unsigned short>(&v21);
        v21 = &std::basic_stringbuf<unsigned short>::`vftable';
        v23 = 0;
        v24 = 0;
        v10 = (_QWORD *)((char *)this + 24);
        if ( *((_QWORD *)this + 6) > 7u )
          v10 = (_QWORD *)*v10;
        v11 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
                &v20,
                v10,
                *((_QWORD *)this + 5));
        v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L" --- ");
        if ( wcsrchr(v6, 0x5Cu) )
          v6 = wcsrchr(v6, 0x5Cu) + 1;
        v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, v6);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13, L" --- ");
        v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(&v20, Buffer[0]);
        std::basic_ostream<unsigned short>::operator<<(v14, std::endl<unsigned short,std::char_traits<unsigned short>>);
        std::basic_stringbuf<unsigned short>::str(&v21, v26);
        v15 = (_QWORD *)*((_QWORD *)this + 1);
        for ( i = *(_QWORD **)this; i != v15; i += 2 )
          (**(void (__fastcall ***)(_QWORD, _BYTE *))*i)(*i, v26);
        std::wstring::~wstring((__int64)v26);
        *(_QWORD *)((char *)v19 + *(int *)(v19[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
        *(_DWORD *)((char *)&v18 + *(int *)(v19[0] + 4LL) + 4) = *(_DWORD *)(v19[0] + 4LL) - 152;
        std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>((__int64)&v21);
        std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v22);
        std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v25);
        std::vector<unsigned short>::~vector<unsigned short>((__int64)Buffer);
      }
    }
  }
}

```

## disassembly

```asm
0x140009f90  test    rdx, rdx
0x140009f93  jz      locret_14000A218
0x140009f99  push    rbp
0x140009f9a  push    rbx
0x140009f9b  push    rsi
0x140009f9c  push    rdi
0x140009f9d  push    r14
0x140009f9f  push    r15
0x140009fa1  lea     rbp, [rsp-98h]
0x140009fa9  sub     rsp, 198h
0x140009fb0  mov     rax, cs:__security_cookie
0x140009fb7  xor     rax, rsp
0x140009fba  mov     [rbp+0C0h+var_40], rax
0x140009fc1  mov     r15, r9
0x140009fc4  mov     r14, r8
0x140009fc7  mov     rdi, rdx
0x140009fca  mov     rsi, rcx
0x140009fcd  mov     [rsp+1C0h+var_180], 0
0x140009fd5  test    r8, r8
0x140009fd8  jz      loc_14000A1FA
0x140009fde  mov     rax, [rcx+8]
0x140009fe2  cmp     [rcx], rax
0x140009fe5  jz      loc_14000A1FA
0x140009feb  xor     eax, eax
0x140009fed  xorps   xmm1, xmm1
0x140009ff0  movdqu  xmmword ptr [rsp+1C0h+Buffer], xmm1
0x140009ff6  mov     [rsp+1C0h+var_168], rax
0x140009ffb  mov     edx, 2000h
0x14000a000  lea     rcx, [rsp+1C0h+Buffer]
0x14000a005  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x14000a00a  mov     rbx, [rsp+1C0h+Buffer+8]
0x14000a00f  sub     rbx, [rsp+1C0h+Buffer]
0x14000a014  sar     rbx, 1
0x14000a017  call    __local_stdio_printf_options
0x14000a01c  mov     [rsp+1C0h+ArgList], r15; ArgList
0x14000a021  mov     [rsp+1C0h+Locale], 0; Locale
0x14000a02a  mov     [rsp+1C0h+Format], r14; Format
0x14000a02f  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000a033  lea     r8, [rbx-1]; BufferCount
0x14000a037  mov     rdx, [rsp+1C0h+Buffer]; Buffer
0x14000a03c  mov     rcx, [rax]; Options
0x14000a03f  call    cs:__imp___stdio_common_vsnwprintf_s
0x14000a045  xor     edx, edx; Val
0x14000a047  mov     r8d, 0F8h; Size
0x14000a04d  lea     rcx, [rsp+1C0h+var_160]; void *
0x14000a052  call    memset_0
0x14000a057  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_istream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_istream<ushort>'}
0x14000a05e  mov     [rsp+1C0h+var_160], rax
0x14000a063  lea     rax, ??_8?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@7B?$basic_ostream@GU?$char_traits@G@std@@@1@@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbtable'{for `std::basic_ostream<ushort>'}
0x14000a06a  mov     [rsp+1C0h+var_150], rax
0x14000a06f  lea     rcx, [rbp+0C0h+var_C8]
0x14000a073  call    cs:__imp_??0?$basic_ios@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_ios<ushort>::basic_ios<ushort>(void)
0x14000a079  nop
0x14000a07a  mov     [rsp+1C0h+var_180], 1
0x14000a082  xor     r8d, r8d
0x14000a085  lea     rdx, [rsp+1C0h+var_148]
0x14000a08a  lea     rcx, [rsp+1C0h+var_160]
0x14000a08f  call    cs:__imp_??0?$basic_iostream@GU?$char_traits@G@std@@@std@@QEAA@PEAV?$basic_streambuf@GU?$char_traits@G@std@@@1@@Z; std::basic_iostream<ushort>::basic_iostream<ushort>(std::basic_streambuf<ushort> *)
0x14000a095  nop
0x14000a096  mov     rax, [rsp+1C0h+var_160]
0x14000a09b  movsxd  rcx, dword ptr [rax+4]
0x14000a09f  lea     r15, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x14000a0a6  mov     [rsp+rcx+1C0h+var_160], r15
0x14000a0ab  mov     rax, [rsp+1C0h+var_160]
0x14000a0b0  movsxd  rcx, dword ptr [rax+4]
0x14000a0b4  lea     edx, [rcx-98h]
0x14000a0ba  mov     dword ptr [rsp+rcx+1C0h+var_168+4], edx
0x14000a0be  lea     rcx, [rsp+1C0h+var_148]
0x14000a0c3  call    cs:__imp_??0?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAA@XZ; std::basic_streambuf<ushort>::basic_streambuf<ushort>(void)
0x14000a0c9  lea     rax, ??_7?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringbuf<ushort>::`vftable'
0x14000a0d0  mov     [rsp+1C0h+var_148], rax
0x14000a0d5  mov     [rbp+0C0h+var_E0], 0
0x14000a0dd  mov     [rbp+0C0h+var_D8], 0
0x14000a0e4  lea     rdx, [rsi+18h]
0x14000a0e8  mov     r8, [rdx+10h]
0x14000a0ec  cmp     qword ptr [rdx+18h], 7
0x14000a0f1  jbe     short loc_14000A0F6
0x14000a0f3  mov     rdx, [rdx]
0x14000a0f6  lea     rcx, [rsp+1C0h+var_150]
0x14000a0fb  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x14000a100  lea     rdx, asc_14001AE80; " --- "
0x14000a107  mov     rcx, rax
0x14000a10a  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000a10f  mov     rbx, rax
0x14000a112  mov     r14d, 5Ch ; '\'
0x14000a118  mov     edx, r14d; Ch
0x14000a11b  mov     rcx, rdi; Str
0x14000a11e  call    cs:__imp_wcsrchr
0x14000a124  test    rax, rax
0x14000a127  jz      short loc_14000A139
0x14000a129  mov     edx, r14d; Ch
0x14000a12c  mov     rcx, rdi; Str
0x14000a12f  call    cs:__imp_wcsrchr
0x14000a135  lea     rdi, [rax+2]
0x14000a139  mov     rdx, rdi
0x14000a13c  mov     rcx, rbx
0x14000a13f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000a144  mov     rcx, rax
0x14000a147  lea     rdx, asc_14001AE80; " --- "
0x14000a14e  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000a153  mov     rdx, [rsp+1C0h+Buffer]
0x14000a158  lea     rcx, [rsp+1C0h+var_150]
0x14000a15d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x14000a162  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x14000a169  mov     rcx, rax
0x14000a16c  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x14000a172  lea     rdx, [rbp+0C0h+var_60]
0x14000a176  lea     rcx, [rsp+1C0h+var_148]
0x14000a17b  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x14000a180  nop
0x14000a181  mov     rdi, [rsi+8]
0x14000a185  mov     rbx, [rsi]
0x14000a188  jmp     short loc_14000A1A1
0x14000a18a  mov     rcx, [rbx]
0x14000a18d  mov     rax, [rcx]
0x14000a190  lea     rdx, [rbp+0C0h+var_60]
0x14000a194  mov     rax, [rax]
0x14000a197  call    cs:__guard_dispatch_icall_fptr
0x14000a19d  add     rbx, 10h
0x14000a1a1  cmp     rbx, rdi
0x14000a1a4  jnz     short loc_14000A18A
0x14000a1a6  lea     rcx, [rbp+0C0h+var_60]
0x14000a1aa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a1af  nop
0x14000a1b0  mov     rax, [rsp+1C0h+var_160]
0x14000a1b5  movsxd  rcx, dword ptr [rax+4]
0x14000a1b9  mov     [rsp+rcx+1C0h+var_160], r15
0x14000a1be  mov     rax, [rsp+1C0h+var_160]
0x14000a1c3  movsxd  rcx, dword ptr [rax+4]
0x14000a1c7  lea     edx, [rcx-98h]
0x14000a1cd  mov     dword ptr [rsp+rcx+1C0h+var_168+4], edx
0x14000a1d1  lea     rcx, [rsp+1C0h+var_148]
0x14000a1d6  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x14000a1db  lea     rcx, [rbp+0C0h+var_140]
0x14000a1df  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x14000a1e5  lea     rcx, [rbp+0C0h+var_C8]
0x14000a1e9  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x14000a1ef  nop
0x14000a1f0  lea     rcx, [rsp+1C0h+Buffer]
0x14000a1f5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x14000a1fa  mov     rcx, [rbp+0C0h+var_40]
0x14000a201  xor     rcx, rsp; StackCookie
0x14000a204  call    __security_check_cookie
0x14000a209  add     rsp, 198h
0x14000a210  pop     r15
0x14000a212  pop     r14
0x14000a214  pop     rdi
0x14000a215  pop     rsi
0x14000a216  pop     rbx
0x14000a217  pop     rbp
0x14000a218  retn
```

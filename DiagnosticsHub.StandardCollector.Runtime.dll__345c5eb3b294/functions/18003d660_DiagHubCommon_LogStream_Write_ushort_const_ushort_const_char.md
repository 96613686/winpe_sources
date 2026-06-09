# DiagHubCommon::LogStream::Write(ushort const *,ushort const *,char *)

- ea: `0x18003d660`
- end: `0x18003d861`
- name: `?Write@LogStream@DiagHubCommon@@QEAAXPEBG0PEAD@Z`
- size: `513`
- prototype: `void(DiagHubCommon::LogStream *__hidden this, const unsigned __int16 *, const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18003d864`

## callees

- `0x1800023b8`
- `0x18000a078`
- `0x18000a17c`
- `0x1800246f8`
- `0x18002584c`
- `0x180025eac`
- `0x1800267fc`
- `0x180035c60`
- `0x18003d660`
- `0x18003f890`
- `0x180049b50`
- `0x18004ad26`
- `0x18004b640`

## import_xrefs

- `VCRUNTIME140!wcsrchr` at `0x18003d761`
- `VCRUNTIME140!wcsrchr` at `0x18003d772`
- `VCRUNTIME140!wcsrchr` at `0x18003d761`
- `VCRUNTIME140!wcsrchr` at `0x18003d772`
- `MSVCP140!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18003d7ae`
- `MSVCP140!??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z` at `0x18003d7ae`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003d831`
- `MSVCP140!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003d831`
- `MSVCP140!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003d827`
- `MSVCP140!??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18003d827`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x18003d707`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x18003d707`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  wchar_t *Buffer[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+50h] [rbp-B0h]
  _BYTE v19[32]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v20[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v21[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v23[120]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v24[104]; // [rsp+118h] [rbp+18h] BYREF

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
        memset_0(v20, 0, 0xF8u);
        std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v20);
        v10 = (_QWORD *)((char *)this + 24);
        if ( *((_QWORD *)this + 6) > 7u )
          v10 = (_QWORD *)*v10;
        v11 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
                v21,
                v10,
                *((_QWORD *)this + 5));
        v12 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v11, L" --- ");
        if ( wcsrchr(v6, 0x5Cu) )
          v6 = wcsrchr(v6, 0x5Cu) + 1;
        v13 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v12, v6);
        std::operator<<<unsigned short,std::char_traits<unsigned short>>(v13, L" --- ");
        v14 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v21, Buffer[0]);
        std::basic_ostream<unsigned short>::operator<<(v14, std::endl<unsigned short,std::char_traits<unsigned short>>);
        std::basic_stringbuf<unsigned short>::str(v22, v19);
        v15 = (_QWORD *)*((_QWORD *)this + 1);
        for ( i = *(_QWORD **)this; i != v15; i += 2 )
          (**(void (__fastcall ***)(_QWORD, _BYTE *))*i)(*i, v19);
        std::wstring::~wstring(v19);
        *(_QWORD *)((char *)v20 + *(int *)(v20[0] + 4LL)) = &std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vftable';
        *(_DWORD *)&v19[*(int *)(v20[0] + 4LL) + 28] = *(_DWORD *)(v20[0] + 4LL) - 152;
        std::basic_stringbuf<unsigned short>::~basic_stringbuf<unsigned short>(v22);
        std::basic_iostream<unsigned short>::~basic_iostream<unsigned short,std::char_traits<unsigned short>>(v23);
        std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v24);
        std::vector<unsigned short>::~vector<unsigned short>(Buffer);
      }
    }
  }
}

```

## disassembly

```asm
0x18003d660  test    rdx, rdx
0x18003d663  jz      locret_18003D860
0x18003d669  push    rbp
0x18003d66a  push    rbx
0x18003d66b  push    rsi
0x18003d66c  push    rdi
0x18003d66d  push    r14
0x18003d66f  push    r15
0x18003d671  lea     rbp, [rsp-98h]
0x18003d679  sub     rsp, 198h
0x18003d680  mov     rax, cs:__security_cookie
0x18003d687  xor     rax, rsp
0x18003d68a  mov     [rbp+0C0h+var_40], rax
0x18003d691  mov     r15, r9
0x18003d694  mov     r14, r8
0x18003d697  mov     rdi, rdx
0x18003d69a  mov     rsi, rcx
0x18003d69d  test    r8, r8
0x18003d6a0  jz      loc_18003D842
0x18003d6a6  mov     rax, [rcx+8]
0x18003d6aa  cmp     [rcx], rax
0x18003d6ad  jz      loc_18003D842
0x18003d6b3  xor     eax, eax
0x18003d6b5  xorps   xmm1, xmm1
0x18003d6b8  movdqu  xmmword ptr [rsp+1C0h+Buffer], xmm1
0x18003d6be  mov     [rsp+1C0h+var_170], rax
0x18003d6c3  mov     edx, 2000h
0x18003d6c8  lea     rcx, [rsp+1C0h+Buffer]
0x18003d6cd  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003d6d2  mov     rbx, [rsp+1C0h+Buffer+8]
0x18003d6d7  sub     rbx, [rsp+1C0h+Buffer]
0x18003d6dc  sar     rbx, 1
0x18003d6df  call    __local_stdio_printf_options
0x18003d6e4  mov     [rsp+1C0h+ArgList], r15; ArgList
0x18003d6e9  mov     [rsp+1C0h+Locale], 0; Locale
0x18003d6f2  mov     [rsp+1C0h+Format], r14; Format
0x18003d6f7  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18003d6fb  lea     r8, [rbx-1]; BufferCount
0x18003d6ff  mov     rdx, [rsp+1C0h+Buffer]; Buffer
0x18003d704  mov     rcx, [rax]; Options
0x18003d707  call    cs:__imp___stdio_common_vsnwprintf_s
0x18003d70d  xor     edx, edx; Val
0x18003d70f  mov     r8d, 0F8h; Size
0x18003d715  lea     rcx, [rbp+0C0h+var_140]; void *
0x18003d719  call    memset_0
0x18003d71e  lea     rcx, [rbp+0C0h+var_140]
0x18003d722  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18003d727  nop
0x18003d728  lea     rdx, [rsi+18h]
0x18003d72c  mov     r8, [rdx+10h]
0x18003d730  cmp     qword ptr [rdx+18h], 7
0x18003d735  jbe     short loc_18003D73A
0x18003d737  mov     rdx, [rdx]
0x18003d73a  lea     rcx, [rbp+0C0h+var_130]
0x18003d73e  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x18003d743  lea     rdx, asc_1800601A0; " --- "
0x18003d74a  mov     rcx, rax
0x18003d74d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18003d752  mov     rbx, rax
0x18003d755  mov     r14d, 5Ch ; '\'
0x18003d75b  mov     edx, r14d; Ch
0x18003d75e  mov     rcx, rdi; Str
0x18003d761  call    cs:__imp_wcsrchr
0x18003d767  test    rax, rax
0x18003d76a  jz      short loc_18003D77C
0x18003d76c  mov     edx, r14d; Ch
0x18003d76f  mov     rcx, rdi; Str
0x18003d772  call    cs:__imp_wcsrchr
0x18003d778  lea     rdi, [rax+2]
0x18003d77c  mov     rdx, rdi
0x18003d77f  mov     rcx, rbx
0x18003d782  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18003d787  mov     rcx, rax
0x18003d78a  lea     rdx, asc_1800601A0; " --- "
0x18003d791  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18003d796  mov     rdx, [rsp+1C0h+Buffer]
0x18003d79b  lea     rcx, [rbp+0C0h+var_130]
0x18003d79f  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x18003d7a4  lea     rdx, ??$endl@GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@@Z; std::endl<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &)
0x18003d7ab  mov     rcx, rax
0x18003d7ae  call    cs:__imp_??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@P6AAEAV01@AEAV01@@Z@Z; std::basic_ostream<ushort>::operator<<(std::basic_ostream<ushort> & (*)(std::basic_ostream<ushort> &))
0x18003d7b4  lea     rdx, [rsp+1C0h+var_160]
0x18003d7b9  lea     rcx, [rbp+0C0h+var_128]
0x18003d7bd  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x18003d7c2  nop
0x18003d7c3  mov     rdi, [rsi+8]
0x18003d7c7  mov     rbx, [rsi]
0x18003d7ca  jmp     short loc_18003D7E4
0x18003d7cc  mov     rcx, [rbx]
0x18003d7cf  mov     rax, [rcx]
0x18003d7d2  lea     rdx, [rsp+1C0h+var_160]
0x18003d7d7  mov     rax, [rax]
0x18003d7da  call    cs:__guard_dispatch_icall_fptr
0x18003d7e0  add     rbx, 10h
0x18003d7e4  cmp     rbx, rdi
0x18003d7e7  jnz     short loc_18003D7CC
0x18003d7e9  lea     rcx, [rsp+1C0h+var_160]
0x18003d7ee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d7f3  nop
0x18003d7f4  mov     rax, [rbp+0C0h+var_140]
0x18003d7f8  movsxd  rcx, dword ptr [rax+4]
0x18003d7fc  lea     rax, ??_7?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@6B@; const std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vftable'
0x18003d803  mov     [rbp+rcx+0C0h+var_140], rax
0x18003d808  mov     rax, [rbp+0C0h+var_140]
0x18003d80c  movsxd  rcx, dword ptr [rax+4]
0x18003d810  lea     edx, [rcx-98h]
0x18003d816  mov     [rsp+rcx+1C0h+var_144], edx
0x18003d81a  lea     rcx, [rbp+0C0h+var_128]
0x18003d81e  call    ??1?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringbuf<ushort>::~basic_stringbuf<ushort>(void)
0x18003d823  lea     rcx, [rbp+0C0h+var_120]
0x18003d827  call    cs:__imp_??1?$basic_iostream@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_iostream<ushort>::~basic_iostream<ushort,std::char_traits<ushort>>(void)
0x18003d82d  lea     rcx, [rbp+0C0h+var_A8]
0x18003d831  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x18003d837  nop
0x18003d838  lea     rcx, [rsp+1C0h+Buffer]
0x18003d83d  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003d842  mov     rcx, [rbp+0C0h+var_40]
0x18003d849  xor     rcx, rsp; StackCookie
0x18003d84c  call    __security_check_cookie
0x18003d851  add     rsp, 198h
0x18003d858  pop     r15
0x18003d85a  pop     r14
0x18003d85c  pop     rdi
0x18003d85d  pop     rsi
0x18003d85e  pop     rbx
0x18003d85f  pop     rbp
0x18003d860  retn
```

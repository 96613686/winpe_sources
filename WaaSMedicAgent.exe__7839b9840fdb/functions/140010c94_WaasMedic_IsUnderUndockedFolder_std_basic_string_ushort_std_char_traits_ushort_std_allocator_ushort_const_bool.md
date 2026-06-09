# WaasMedic::IsUnderUndockedFolder(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool &)

- ea: `0x140010c94`
- end: `0x140010f0e`
- name: `?IsUnderUndockedFolder@WaasMedic@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z`
- size: `634`
- prototype: `__int64 __fastcall(_QWORD *, _BYTE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x14000f744`

## callees

- `0x140002a30`
- `0x140002a54`
- `0x140002a98`
- `0x14000369c`
- `0x140004290`
- `0x140004670`
- `0x140006424`
- `0x14000b470`
- `0x14000e9c4`
- `0x14000f27c`
- `0x14001075c`
- `0x140010818`
- `0x140010c94`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140010e71`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140010e71`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140010da7`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140010da7`

## pseudocode

```c
__int64 __fastcall WaasMedic::IsUnderUndockedFolder(_QWORD *a1, _BYTE *a2)
{
  char *v4; // rbx
  __int128 *v5; // rdi
  const char *v6; // r9
  char *v7; // rbx
  char *v8; // rdi
  unsigned __int64 v9; // r8
  __int64 v10; // rax
  char **v11; // r8
  _QWORD *v12; // rdx
  char **v13; // rcx
  unsigned int LastError; // ebx
  __int128 v16; // [rsp+20h] [rbp-E8h] BYREF
  char *v17; // [rsp+30h] [rbp-D8h]
  char *v18; // [rsp+38h] [rbp-D0h]
  __int64 v19; // [rsp+40h] [rbp-C8h]
  char *v20; // [rsp+48h] [rbp-C0h]
  char *v21; // [rsp+50h] [rbp-B8h] BYREF
  char *v22; // [rsp+58h] [rbp-B0h]
  char *v23; // [rsp+60h] [rbp-A8h]
  unsigned __int64 v24; // [rsp+68h] [rbp-A0h]
  __int128 v25; // [rsp+70h] [rbp-98h] BYREF
  __int64 v26; // [rsp+80h] [rbp-88h]
  __int64 v27; // [rsp+88h] [rbp-80h]
  __int128 v28; // [rsp+90h] [rbp-78h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-68h]
  __int64 v30; // [rsp+A8h] [rbp-60h]
  char *v31[5]; // [rsp+B0h] [rbp-58h] BYREF
  WCHAR Buffer[264]; // [rsp+D8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+320h] [rbp+218h]

  v19 = -2;
  *a2 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v25, L"uus", 3u);
  v4 = (char *)operator new(0x20u);
  *((_QWORD *)&v16 + 1) = v4;
  v17 = v4;
  v18 = v4 + 32;
  v20 = (char *)&v16 + 8;
  v5 = &v25;
  v21 = v4;
  v22 = v4;
  v23 = (char *)&v16 + 8;
  do
  {
    std::wstring::wstring(v4, v5);
    v4 += 32;
    v22 = v4;
    v5 += 2;
  }
  while ( v5 != &v28 );
  v17 = v4;
  `eh vector destructor iterator'(&v25, 0x20u, 1u, (void (*)(void *))std::wstring::~wstring);
  memset_0(Buffer, 0, 0x208u);
  if ( GetWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x181,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
                  v6);
    std::vector<std::wstring>::_Tidy((char *)&v16 + 8);
    return LastError;
  }
  else
  {
    v7 = (char *)*((_QWORD *)&v16 + 1);
    v8 = v17;
    while ( v7 != v8 )
    {
      v28 = 0;
      v29 = 0;
      v30 = 0;
      v9 = -1;
      do
        ++v9;
      while ( Buffer[v9] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&v28, Buffer, v9);
      v10 = std::operator+<unsigned short>(v31, &v28);
      std::operator+<unsigned short>(&v21, v10, v7);
      std::wstring::~wstring(v31);
      std::wstring::~wstring((char **)&v28);
      v11 = &v21;
      if ( v24 > 7 )
        v11 = (char **)v21;
      LogLevelW(4u, L"Matching against allowed folder: %s", v11);
      if ( a1[3] <= 7u )
        v12 = a1;
      else
        v12 = (_QWORD *)*a1;
      v13 = &v21;
      if ( v24 > 7 )
        v13 = (char **)v21;
      if ( !(unsigned int)_o__wcsnicmp(v13, v12, v23) )
      {
        LogLevelW(4u, L"Folder matched.");
        *a2 = 1;
        std::wstring::~wstring(&v21);
        break;
      }
      std::wstring::~wstring(&v21);
      v7 += 32;
    }
    std::vector<std::wstring>::_Tidy((char *)&v16 + 8);
    return 0;
  }
}

```

## disassembly

```asm
0x140010c94  mov     rax, rsp
0x140010c97  push    rbp
0x140010c98  push    rsi
0x140010c99  push    rdi
0x140010c9a  push    r14
0x140010c9c  push    r15
0x140010c9e  lea     rbp, [rax-218h]
0x140010ca5  sub     rsp, 2F0h
0x140010cac  mov     [rsp+310h+var_2D8], 0FFFFFFFFFFFFFFFEh
0x140010cb5  mov     [rax+18h], rbx
0x140010cb9  mov     rax, cs:__security_cookie
0x140010cc0  xor     rax, rsp
0x140010cc3  mov     [rbp+210h+var_30], rax
0x140010cca  mov     r14, rdx
0x140010ccd  mov     rsi, rcx
0x140010cd0  xor     r15d, r15d
0x140010cd3  mov     [rdx], r15b
0x140010cd6  xorps   xmm0, xmm0
0x140010cd9  movups  [rsp+310h+var_2B0+8], xmm0
0x140010cde  mov     [rsp+310h+var_298], r15
0x140010ce3  mov     [rbp+210h+var_290], r15
0x140010ce7  lea     r8d, [r15+3]
0x140010ceb  lea     rdx, aUus; "uus"
0x140010cf2  lea     rcx, [rsp+310h+var_2B0+8]
0x140010cf7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140010cfc  nop
0x140010cfd  xorps   xmm0, xmm0
0x140010d00  movdqu  [rsp+310h+var_2F8+8], xmm0
0x140010d06  mov     [rsp+310h+var_2E0], r15
0x140010d0b  lea     ecx, [r15+20h]; Size
0x140010d0f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010d14  mov     rbx, rax
0x140010d17  mov     qword ptr [rsp+310h+var_2F8+8], rax
0x140010d1c  mov     [rsp+310h+var_2E8], rax
0x140010d21  lea     rcx, [rax+20h]
0x140010d25  mov     [rsp+310h+var_2E0], rcx
0x140010d2a  lea     rax, [rsp+310h+var_2F8+8]
0x140010d2f  mov     [rsp+310h+var_2D0], rax
0x140010d34  lea     rdi, [rsp+310h+var_2B0+8]
0x140010d39  mov     [rsp+310h+var_2C8], rbx
0x140010d3e  mov     [rsp+310h+var_2C0], rbx
0x140010d43  lea     rax, [rsp+310h+var_2F8+8]
0x140010d48  mov     [rsp+310h+var_2B8], rax
0x140010d4d  mov     rdx, rdi
0x140010d50  mov     rcx, rbx
0x140010d53  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140010d58  add     rbx, 20h ; ' '
0x140010d5c  mov     [rsp+310h+var_2C0], rbx
0x140010d61  add     rdi, 20h ; ' '
0x140010d65  lea     rax, [rbp+210h+var_288]
0x140010d69  cmp     rdi, rax
0x140010d6c  jnz     short loc_140010D4D
0x140010d6e  mov     [rsp+310h+var_2E8], rbx
0x140010d73  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x140010d7a  mov     edx, 20h ; ' '; unsigned __int64
0x140010d7f  lea     r8d, [rdx-1Fh]; unsigned __int64
0x140010d83  lea     rcx, [rsp+310h+var_2B0+8]; void *
0x140010d88  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140010d8d  xor     edx, edx; Val
0x140010d8f  mov     r8d, 208h; Size
0x140010d95  lea     rcx, [rbp+210h+Buffer]; void *
0x140010d99  call    memset_0
0x140010d9e  mov     edx, 104h; uSize
0x140010da3  lea     rcx, [rbp+210h+Buffer]; lpBuffer
0x140010da7  call    cs:__imp_GetWindowsDirectoryW
0x140010dad  dec     eax
0x140010daf  cmp     eax, 103h
0x140010db4  ja      loc_140010EC2
0x140010dba  mov     rbx, qword ptr [rsp+310h+var_2F8+8]
0x140010dbf  mov     rdi, [rsp+310h+var_2E8]
0x140010dc4  jmp     loc_140010E89
0x140010dc9  xorps   xmm0, xmm0
0x140010dcc  movups  [rbp+210h+var_288], xmm0
0x140010dd0  mov     [rbp+210h+var_278], r15
0x140010dd4  mov     [rbp+210h+var_270], r15
0x140010dd8  lea     rax, [rbp+210h+Buffer]
0x140010ddc  or      r8, 0FFFFFFFFFFFFFFFFh
0x140010de0  inc     r8
0x140010de3  cmp     [rax+r8*2], r15w
0x140010de8  jnz     short loc_140010DE0
0x140010dea  lea     rdx, [rbp+210h+Buffer]
0x140010dee  lea     rcx, [rbp+210h+var_288]
0x140010df2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140010df7  nop
0x140010df8  lea     rdx, [rbp+210h+var_288]
0x140010dfc  lea     rcx, [rbp+210h+var_268]
0x140010e00  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x140010e05  nop
0x140010e06  mov     r8, rbx
0x140010e09  mov     rdx, rax
0x140010e0c  lea     rcx, [rsp+310h+var_2C8]
0x140010e11  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x140010e16  nop
0x140010e17  lea     rcx, [rbp+210h+var_268]; void *
0x140010e1b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010e20  nop
0x140010e21  lea     rcx, [rbp+210h+var_288]; void *
0x140010e25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010e2a  lea     r8, [rsp+310h+var_2C8]
0x140010e2f  cmp     qword ptr [rsp+310h+var_2B0], 7
0x140010e35  cmova   r8, [rsp+310h+var_2C8]
0x140010e3b  lea     rdx, aMatchingAgains; "Matching against allowed folder: %s"
0x140010e42  mov     ecx, 4; unsigned __int8
0x140010e47  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140010e4c  cmp     qword ptr [rsi+18h], 7
0x140010e51  jbe     short loc_140010E58
0x140010e53  mov     rdx, [rsi]
0x140010e56  jmp     short loc_140010E5B
0x140010e58  mov     rdx, rsi
0x140010e5b  lea     rcx, [rsp+310h+var_2C8]
0x140010e60  cmp     qword ptr [rsp+310h+var_2B0], 7
0x140010e66  cmova   rcx, [rsp+310h+var_2C8]
0x140010e6c  mov     r8, [rsp+310h+var_2B8]
0x140010e71  call    cs:__imp__o__wcsnicmp
0x140010e77  test    eax, eax
0x140010e79  jz      short loc_140010E94
0x140010e7b  lea     rcx, [rsp+310h+var_2C8]; void *
0x140010e80  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010e85  add     rbx, 20h ; ' '
0x140010e89  cmp     rbx, rdi
0x140010e8c  jnz     loc_140010DC9
0x140010e92  jmp     short loc_140010EB4
0x140010e94  lea     rdx, aFolderMatched; "Folder matched."
0x140010e9b  mov     ecx, 4; unsigned __int8
0x140010ea0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140010ea5  mov     byte ptr [r14], 1
0x140010ea9  lea     rcx, [rsp+310h+var_2C8]; void *
0x140010eae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010eb3  nop
0x140010eb4  lea     rcx, [rsp+310h+var_2F8+8]
0x140010eb9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x140010ebe  xor     eax, eax
0x140010ec0  jmp     short loc_140010EE8
0x140010ec2  mov     rcx, [rbp+218h]; this
0x140010ec9  lea     r8, aOnecoreEnduser_2; "onecore\\enduser\\waasmedic\\lib\\util"...
0x140010ed0  mov     edx, 181h; void *
0x140010ed5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140010eda  mov     ebx, eax
0x140010edc  lea     rcx, [rsp+310h+var_2F8+8]
0x140010ee1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x140010ee6  mov     eax, ebx
0x140010ee8  mov     rcx, [rbp+210h+var_30]
0x140010eef  xor     rcx, rsp; StackCookie
0x140010ef2  call    __security_check_cookie
0x140010ef7  mov     rbx, [rsp+310h+arg_10]
0x140010eff  add     rsp, 2F0h
0x140010f06  pop     r15
0x140010f08  pop     r14
0x140010f0a  pop     rdi
0x140010f0b  pop     rsi
0x140010f0c  pop     rbp
0x140010f0d  retn
```

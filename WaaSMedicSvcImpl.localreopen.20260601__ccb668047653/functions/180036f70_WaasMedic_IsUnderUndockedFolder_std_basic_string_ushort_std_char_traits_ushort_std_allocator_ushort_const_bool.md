# WaasMedic::IsUnderUndockedFolder(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool &)

- ea: `0x180036f70`
- end: `0x1800371c0`
- name: `?IsUnderUndockedFolder@WaasMedic@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180028bec`

## callees

- `0x1800050a0`
- `0x180005108`
- `0x180005bbc`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbb4`
- `0x18001d650`
- `0x18002e4b8`
- `0x18002e81c`
- `0x180035a24`
- `0x180035c1c`
- `0x180036f70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180037123`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180037123`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180037025`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180037025`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaasMedic::IsUnderUndockedFolder(_QWORD *a1, _BYTE *a2)
{
  const char *v4; // r9
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // r8
  void *v8; // rax
  __int64 v9; // rax
  __int128 *v10; // r8
  _QWORD *v11; // rdx
  __int128 *v12; // rcx
  unsigned int LastError; // ebx
  _QWORD v15[3]; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v16; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B0h]
  _OWORD v18[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v19[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v20[32]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[264]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  *a2 = 0;
  memset(v18, 0, sizeof(v18));
  std::wstring::_Construct<1,unsigned short const *>(v18, L"uus", 3);
  *(_QWORD *)&v16 = v18;
  *((_QWORD *)&v16 + 1) = v19;
  std::vector<std::wstring>::vector<std::wstring>(v15, &v16);
  `eh vector destructor iterator'(v18, 0x20u, 1u, std::wstring::~wstring);
  memset_0(Buffer, 0, 0x208u);
  if ( GetWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x181,
                  (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\fileutil.cpp",
                  v4);
    std::vector<std::wstring>::_Tidy(v15);
    return LastError;
  }
  else
  {
    v5 = v15[0];
    v6 = v15[1];
    while ( v5 != v6 )
    {
      memset(v19, 0, sizeof(v19));
      v7 = -1;
      do
        ++v7;
      while ( Buffer[v7] );
      std::wstring::_Construct<1,unsigned short const *>(v19, Buffer, v7);
      v8 = (void *)std::operator+<unsigned short>(v20, v19, L"\\");
      v9 = std::wstring::append(v8);
      v16 = 0;
      v17 = 0u;
      v16 = *(_OWORD *)v9;
      v17 = *(_OWORD *)(v9 + 16);
      *(_QWORD *)(v9 + 16) = 0;
      *(_QWORD *)(v9 + 24) = 7;
      *(_WORD *)v9 = 0;
      std::wstring::~wstring(v20);
      std::wstring::~wstring(v19);
      v10 = &v16;
      if ( *((_QWORD *)&v17 + 1) > 7u )
        v10 = (__int128 *)v16;
      LogLevelW(4u, L"Matching against allowed folder: %s", v10);
      if ( a1[3] <= 7u )
        v11 = a1;
      else
        v11 = (_QWORD *)*a1;
      v12 = &v16;
      if ( *((_QWORD *)&v17 + 1) > 7u )
        v12 = (__int128 *)v16;
      if ( !(unsigned int)_o__wcsnicmp(v12, v11) )
      {
        LogLevelW(4u, L"Folder matched.");
        *a2 = 1;
        std::wstring::~wstring(&v16);
        break;
      }
      std::wstring::~wstring(&v16);
      v5 += 32;
    }
    std::vector<std::wstring>::_Tidy(v15);
    return 0;
  }
}

```

## disassembly

```asm
0x180036f70  mov     [rsp-8+arg_10], rbx
0x180036f75  push    rbp
0x180036f76  push    rsi
0x180036f77  push    rdi
0x180036f78  push    r14
0x180036f7a  push    r15
0x180036f7c  lea     rbp, [rsp-1E0h]
0x180036f84  sub     rsp, 2E0h
0x180036f8b  mov     rax, cs:__security_cookie
0x180036f92  xor     rax, rsp
0x180036f95  mov     [rbp+200h+var_30], rax
0x180036f9c  mov     r14, rdx
0x180036f9f  mov     rsi, rcx
0x180036fa2  xor     r15d, r15d
0x180036fa5  mov     [rdx], r15b
0x180036fa8  xorps   xmm0, xmm0
0x180036fab  movups  [rsp+300h+var_2A0], xmm0
0x180036fb0  xorps   xmm1, xmm1
0x180036fb3  movdqu  [rsp+300h+var_290], xmm1
0x180036fb9  lea     r8d, [r15+3]
0x180036fbd  lea     rdx, aUus; "uus"
0x180036fc4  lea     rcx, [rsp+300h+var_2A0]
0x180036fc9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036fce  nop
0x180036fcf  lea     rax, [rsp+300h+var_2A0]
0x180036fd4  mov     qword ptr [rsp+300h+var_2C0], rax
0x180036fd9  lea     rax, [rbp+200h+var_280]
0x180036fdd  mov     qword ptr [rsp+300h+var_2C0+8], rax
0x180036fe2  lea     rdx, [rsp+300h+var_2C0]
0x180036fe7  lea     rcx, [rsp+300h+var_2D8]
0x180036fec  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEBV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(std::initializer_list<std::wstring>,std::allocator<std::wstring> const &)
0x180036ff1  nop
0x180036ff2  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x180036ff9  lea     edx, [r15+20h]; unsigned __int64
0x180036ffd  lea     r8d, [r15+1]; unsigned __int64
0x180037001  lea     rcx, [rsp+300h+var_2A0]; void *
0x180037006  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003700b  xor     edx, edx; Val
0x18003700d  mov     r8d, 208h; Size
0x180037013  lea     rcx, [rbp+200h+Buffer]; void *
0x180037017  call    memset_0
0x18003701c  mov     edx, 104h; uSize
0x180037021  lea     rcx, [rbp+200h+Buffer]; lpBuffer
0x180037025  call    cs:__imp_GetWindowsDirectoryW
0x18003702b  dec     eax
0x18003702d  cmp     eax, 103h
0x180037032  ja      loc_180037174
0x180037038  mov     rbx, [rsp+300h+var_2D8]
0x18003703d  mov     rdi, [rsp+300h+var_2D0]
0x180037042  jmp     loc_18003713B
0x180037047  xorps   xmm0, xmm0
0x18003704a  movups  [rbp+200h+var_280], xmm0
0x18003704e  xorps   xmm1, xmm1
0x180037051  movdqu  [rbp+200h+var_270], xmm1
0x180037056  lea     rax, [rbp+200h+Buffer]
0x18003705a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003705e  inc     r8
0x180037061  cmp     [rax+r8*2], r15w
0x180037066  jnz     short loc_18003705E
0x180037068  lea     rdx, [rbp+200h+Buffer]
0x18003706c  lea     rcx, [rbp+200h+var_280]
0x180037070  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180037075  nop
0x180037076  lea     r8, asc_180081F30; "\\"
0x18003707d  lea     rdx, [rbp+200h+var_280]
0x180037081  lea     rcx, [rbp+200h+var_260]
0x180037085  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003708a  nop
0x18003708b  mov     rdx, rbx
0x18003708e  mov     rcx, rax; Src
0x180037091  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180037096  xorps   xmm0, xmm0
0x180037099  movups  [rsp+300h+var_2C0], xmm0
0x18003709e  mov     qword ptr [rsp+300h+var_2B0], r15
0x1800370a3  mov     qword ptr [rsp+300h+var_2B0+8], r15
0x1800370a8  movups  xmm0, xmmword ptr [rax]
0x1800370ab  movups  [rsp+300h+var_2C0], xmm0
0x1800370b0  movups  xmm1, xmmword ptr [rax+10h]
0x1800370b4  movups  [rsp+300h+var_2B0], xmm1
0x1800370b9  mov     [rax+10h], r15
0x1800370bd  mov     qword ptr [rax+18h], 7
0x1800370c5  mov     [rax], r15w
0x1800370c9  lea     rcx, [rbp+200h+var_260]; void *
0x1800370cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800370d2  nop
0x1800370d3  lea     rcx, [rbp+200h+var_280]; void *
0x1800370d7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800370dc  lea     r8, [rsp+300h+var_2C0]
0x1800370e1  cmp     qword ptr [rsp+300h+var_2B0+8], 7
0x1800370e7  cmova   r8, qword ptr [rsp+300h+var_2C0]
0x1800370ed  lea     rdx, aMatchingAgains; "Matching against allowed folder: %s"
0x1800370f4  mov     ecx, 4; unsigned __int8
0x1800370f9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800370fe  cmp     qword ptr [rsi+18h], 7
0x180037103  jbe     short loc_18003710A
0x180037105  mov     rdx, [rsi]
0x180037108  jmp     short loc_18003710D
0x18003710a  mov     rdx, rsi
0x18003710d  lea     rcx, [rsp+300h+var_2C0]
0x180037112  cmp     qword ptr [rsp+300h+var_2B0+8], 7
0x180037118  cmova   rcx, qword ptr [rsp+300h+var_2C0]
0x18003711e  mov     r8, qword ptr [rsp+300h+var_2B0]
0x180037123  call    cs:__imp__o__wcsnicmp
0x180037129  test    eax, eax
0x18003712b  jz      short loc_180037146
0x18003712d  lea     rcx, [rsp+300h+var_2C0]; void *
0x180037132  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037137  add     rbx, 20h ; ' '
0x18003713b  cmp     rbx, rdi
0x18003713e  jnz     loc_180037047
0x180037144  jmp     short loc_180037166
0x180037146  lea     rdx, aFolderMatched; "Folder matched."
0x18003714d  mov     ecx, 4; unsigned __int8
0x180037152  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180037157  mov     byte ptr [r14], 1
0x18003715b  lea     rcx, [rsp+300h+var_2C0]; void *
0x180037160  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180037165  nop
0x180037166  lea     rcx, [rsp+300h+var_2D8]
0x18003716b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180037170  xor     eax, eax
0x180037172  jmp     short loc_18003719A
0x180037174  mov     rcx, [rbp+208h]; this
0x18003717b  lea     r8, aOnecoreEnduser_7; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180037182  mov     edx, 181h; void *
0x180037187  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003718c  mov     ebx, eax
0x18003718e  lea     rcx, [rsp+300h+var_2D8]
0x180037193  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180037198  mov     eax, ebx
0x18003719a  mov     rcx, [rbp+200h+var_30]
0x1800371a1  xor     rcx, rsp; StackCookie
0x1800371a4  call    __security_check_cookie
0x1800371a9  mov     rbx, [rsp+300h+arg_10]
0x1800371b1  add     rsp, 2E0h
0x1800371b8  pop     r15
0x1800371ba  pop     r14
0x1800371bc  pop     rdi
0x1800371bd  pop     rsi
0x1800371be  pop     rbp
0x1800371bf  retn
```

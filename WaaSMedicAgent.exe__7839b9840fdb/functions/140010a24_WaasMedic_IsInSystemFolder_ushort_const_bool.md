# WaasMedic::IsInSystemFolder(ushort const *,bool &)

- ea: `0x140010a24`
- end: `0x140010c8d`
- name: `?IsInSystemFolder@WaasMedic@@YAJPEBGAEA_N@Z`
- size: `617`
- prototype: `__int64 __fastcall(WaasMedic *this, unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x14000f744`

## callees

- `0x140002a30`
- `0x14000369c`
- `0x140004290`
- `0x140004670`
- `0x14000b470`
- `0x14000ea60`
- `0x14000f34c`
- `0x14000fe70`
- `0x14001075c`
- `0x140010818`
- `0x140010a24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140010c19`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140010c19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010ae0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140010ad6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140010ad6`

## string_xrefs

- `0x140010af8`: `Failed to find the Windows system directory. Error code: 0x%08x`
- `0x140010c2e`: `Expected a full path name.`

## pseudocode

```c
__int64 __fastcall WaasMedic::IsInSystemFolder(WaasMedic *this, unsigned __int16 *a2, bool *a3)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // r8
  signed int LastError; // eax
  unsigned int v8; // ebx
  __int64 last_of; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // r8
  __int128 *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int128 *v15; // rdx
  __int128 v17; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v18; // [rsp+48h] [rbp-C0h]
  __int128 v19; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+68h] [rbp-A0h]
  __int128 v21; // [rsp+78h] [rbp-90h] BYREF
  __m128i v22; // [rsp+88h] [rbp-80h]
  __int128 v23; // [rsp+98h] [rbp-70h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-60h]
  char *v25[4]; // [rsp+B8h] [rbp-50h] BYREF
  char *v26[4]; // [rsp+D8h] [rbp-30h] BYREF
  WCHAR Buffer[264]; // [rsp+F8h] [rbp-10h] BYREF

  memset_0(Buffer, 0, 0x208u);
  *(_BYTE *)a2 = 0;
  v23 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v23) = 0;
  v21 = 0;
  v22 = si128;
  LOWORD(v21) = 0;
  v19 = 0;
  v20 = 0;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( *((_WORD *)this + v6) );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v19, this, v6);
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    last_of = std::wstring::find_last_of(&v19);
    if ( last_of == -1 )
    {
      v8 = -2147024735;
      LogLevelW(2u, L"Expected a full path name.");
    }
    else
    {
      v10 = last_of + 1;
      v17 = 0;
      v18 = 0;
      if ( (unsigned __int64)v20 < last_of + 1 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
      v8 = 0;
      v11 = -1;
      if ( (_QWORD)v20 - v10 != -1 )
        v11 = v20 - v10;
      v12 = &v19;
      if ( *((_QWORD *)&v20 + 1) > 7u )
        v12 = (__int128 *)v19;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v17, (char *)v12 + 2 * v10, v11);
      std::wstring::operator=(&v23, &v17);
      std::wstring::~wstring((char **)&v17);
      v17 = 0;
      v18 = 0;
      do
        ++v5;
      while ( Buffer[v5] );
      std::wstring::_Construct<1,unsigned short const *>((char **)&v17, Buffer, v5);
      v13 = std::operator+<unsigned short>(v26, &v17);
      v14 = std::operator+<unsigned short>(v25, v13, &v23);
      std::wstring::operator=(&v21, v14);
      std::wstring::~wstring(v25);
      std::wstring::~wstring(v26);
      std::wstring::~wstring((char **)&v17);
      v15 = &v21;
      if ( v22.m128i_i64[1] > 7uLL )
        v15 = (__int128 *)v21;
      *(_BYTE *)a2 = (unsigned int)_o__wcsicmp(this, v15) == 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"Failed to find the Windows system directory. Error code: 0x%08x", v8);
  }
  std::wstring::~wstring((char **)&v19);
  std::wstring::~wstring((char **)&v21);
  std::wstring::~wstring((char **)&v23);
  return v8;
}

```

## disassembly

```asm
0x140010a24  mov     rax, rsp
0x140010a27  push    rbp
0x140010a28  push    rsi
0x140010a29  push    rdi
0x140010a2a  push    r14
0x140010a2c  push    r15
0x140010a2e  lea     rbp, [rax-238h]
0x140010a35  sub     rsp, 310h
0x140010a3c  mov     qword ptr [rsp+330h+var_308], 0FFFFFFFFFFFFFFFEh
0x140010a45  mov     [rax+18h], rbx
0x140010a49  mov     rax, cs:__security_cookie
0x140010a50  xor     rax, rsp
0x140010a53  mov     [rbp+230h+var_30], rax
0x140010a5a  mov     r14, rdx
0x140010a5d  mov     rsi, rcx
0x140010a60  xor     r15d, r15d
0x140010a63  xor     edx, edx; Val
0x140010a65  mov     r8d, 208h; Size
0x140010a6b  lea     rcx, [rbp+230h+Buffer]; void *
0x140010a6f  call    memset_0
0x140010a74  mov     [r14], r15b
0x140010a77  xorps   xmm0, xmm0
0x140010a7a  movups  [rbp+230h+var_2A0], xmm0
0x140010a7e  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140010a86  movdqu  [rbp+230h+var_290], xmm1
0x140010a8b  mov     word ptr [rbp+230h+var_2A0], r15w
0x140010a90  movups  xmmword ptr [rsp+330h+var_2C8+8], xmm0
0x140010a95  movdqu  [rbp+230h+var_2B0], xmm1
0x140010a9a  mov     word ptr [rsp+330h+var_2C8+8], r15w
0x140010aa0  movups  [rsp+330h+var_2E8+8], xmm0
0x140010aa5  xorps   xmm1, xmm1
0x140010aa8  movdqu  [rsp+330h+var_2D8+8], xmm1
0x140010aae  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140010ab2  mov     r8, rdi
0x140010ab5  inc     r8
0x140010ab8  cmp     [rsi+r8*2], r15w
0x140010abd  jnz     short loc_140010AB5
0x140010abf  mov     rdx, rsi
0x140010ac2  lea     rcx, [rsp+330h+var_2E8+8]
0x140010ac7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140010acc  nop
0x140010acd  mov     edx, 104h; uSize
0x140010ad2  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x140010ad6  call    cs:__imp_GetSystemDirectoryW
0x140010adc  test    eax, eax
0x140010ade  jnz     short loc_140010B0E
0x140010ae0  call    cs:__imp_GetLastError
0x140010ae6  mov     ebx, eax
0x140010ae8  test    eax, eax
0x140010aea  jle     short loc_140010AF5
0x140010aec  movzx   ebx, ax
0x140010aef  or      ebx, 80070000h
0x140010af5  mov     r8d, ebx
0x140010af8  lea     rdx, aFailedToFindTh; "Failed to find the Windows system direc"...
0x140010aff  mov     ecx, 2; unsigned __int8
0x140010b04  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140010b09  jmp     loc_140010C40
0x140010b0e  lea     rcx, [rsp+330h+var_2E8+8]
0x140010b13  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x140010b18  cmp     rax, rdi
0x140010b1b  jz      loc_140010C29
0x140010b21  lea     rcx, [rax+1]
0x140010b25  xorps   xmm0, xmm0
0x140010b28  movups  [rsp+330h+var_308+8], xmm0
0x140010b2d  xorps   xmm1, xmm1
0x140010b30  movdqu  [rsp+330h+var_2F8+8], xmm1
0x140010b36  mov     rax, qword ptr [rsp+330h+var_2D8+8]
0x140010b3b  cmp     rax, rcx
0x140010b3e  jb      loc_140010C87
0x140010b44  mov     ebx, r15d
0x140010b47  sub     rax, rcx
0x140010b4a  mov     r8, rdi
0x140010b4d  cmp     rax, rdi
0x140010b50  cmovb   r8, rax
0x140010b54  lea     rax, [rsp+330h+var_2E8+8]
0x140010b59  cmp     qword ptr [rsp+330h+var_2C8], 7
0x140010b5f  cmova   rax, qword ptr [rsp+330h+var_2E8+8]
0x140010b65  lea     rdx, [rax+rcx*2]
0x140010b69  lea     rcx, [rsp+330h+var_308+8]
0x140010b6e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140010b73  lea     rdx, [rsp+330h+var_308+8]
0x140010b78  lea     rcx, [rbp+230h+var_2A0]
0x140010b7c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140010b81  lea     rcx, [rsp+330h+var_308+8]; void *
0x140010b86  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010b8b  xorps   xmm0, xmm0
0x140010b8e  movups  [rsp+330h+var_308+8], xmm0
0x140010b93  xorps   xmm1, xmm1
0x140010b96  movdqu  [rsp+330h+var_2F8+8], xmm1
0x140010b9c  lea     rax, [rbp+230h+Buffer]
0x140010ba0  inc     rdi
0x140010ba3  cmp     [rax+rdi*2], r15w
0x140010ba8  jnz     short loc_140010BA0
0x140010baa  mov     r8, rdi
0x140010bad  lea     rdx, [rbp+230h+Buffer]
0x140010bb1  lea     rcx, [rsp+330h+var_308+8]
0x140010bb6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140010bbb  nop
0x140010bbc  lea     rdx, [rsp+330h+var_308+8]
0x140010bc1  lea     rcx, [rbp+230h+var_260]
0x140010bc5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x140010bca  nop
0x140010bcb  lea     r8, [rbp+230h+var_2A0]
0x140010bcf  mov     rdx, rax
0x140010bd2  lea     rcx, [rbp+230h+var_280]
0x140010bd6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x140010bdb  mov     rdx, rax
0x140010bde  lea     rcx, [rsp+330h+var_2C8+8]
0x140010be3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140010be8  lea     rcx, [rbp+230h+var_280]; void *
0x140010bec  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010bf1  nop
0x140010bf2  lea     rcx, [rbp+230h+var_260]; void *
0x140010bf6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010bfb  nop
0x140010bfc  lea     rcx, [rsp+330h+var_308+8]; void *
0x140010c01  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010c06  lea     rdx, [rsp+330h+var_2C8+8]
0x140010c0b  cmp     qword ptr [rbp+230h+var_2B0+8], 7
0x140010c10  cmova   rdx, qword ptr [rsp+330h+var_2C8+8]
0x140010c16  mov     rcx, rsi
0x140010c19  call    cs:__imp__o__wcsicmp
0x140010c1f  test    eax, eax
0x140010c21  setz    al
0x140010c24  mov     [r14], al
0x140010c27  jmp     short loc_140010C40
0x140010c29  mov     ebx, 800700A1h
0x140010c2e  lea     rdx, aExpectedAFullP; "Expected a full path name."
0x140010c35  mov     ecx, 2; unsigned __int8
0x140010c3a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x140010c3f  nop
0x140010c40  lea     rcx, [rsp+330h+var_2E8+8]; void *
0x140010c45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010c4a  nop
0x140010c4b  lea     rcx, [rsp+330h+var_2C8+8]; void *
0x140010c50  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010c55  nop
0x140010c56  lea     rcx, [rbp+230h+var_2A0]; void *
0x140010c5a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140010c5f  mov     eax, ebx
0x140010c61  mov     rcx, [rbp+230h+var_30]
0x140010c68  xor     rcx, rsp; StackCookie
0x140010c6b  call    __security_check_cookie
0x140010c70  mov     rbx, [rsp+330h+arg_10]
0x140010c78  add     rsp, 310h
0x140010c7f  pop     r15
0x140010c81  pop     r14
0x140010c83  pop     rdi
0x140010c84  pop     rsi
0x140010c85  pop     rbp
0x140010c86  retn
0x140010c87  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```

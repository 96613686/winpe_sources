# WaasMedic::IsInSystemFolder(ushort const *,bool &)

- ea: `0x180036ce4`
- end: `0x180036f67`
- name: `?IsInSystemFolder@WaasMedic@@YAJPEBGAEA_N@Z`
- size: `643`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180028bec`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x1800098f0`
- `0x180009cd0`
- `0x180010db4`
- `0x18001d3ec`
- `0x18001d650`
- `0x180029360`
- `0x18002e81c`
- `0x180035a24`
- `0x180036ce4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180036ef3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180036ef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d97`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180036d8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180036d8d`

## string_xrefs

- `0x180036f08`: `Expected a full path name.`
- `0x180036daf`: `Failed to find the Windows system directory. Error code: 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaasMedic::IsInSystemFolder(WaasMedic *this, unsigned __int16 *a2, bool *a3)
{
  __int64 v5; // rdi
  __int64 v6; // r8
  signed int LastError; // eax
  unsigned int v8; // ebx
  __int64 last_of; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int128 *v12; // rax
  void *v13; // rax
  __int64 v14; // rax
  __int128 *v15; // rdx
  __int128 v17; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v18; // [rsp+38h] [rbp-C8h]
  __int128 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v20; // [rsp+58h] [rbp-A8h]
  __int128 v21; // [rsp+68h] [rbp-98h] BYREF
  __m128i v22; // [rsp+78h] [rbp-88h]
  __int128 v23; // [rsp+88h] [rbp-78h] BYREF
  __m128i si128; // [rsp+98h] [rbp-68h]
  _OWORD v25[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v26[40]; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR Buffer[264]; // [rsp+F0h] [rbp-10h] BYREF

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
  std::wstring::_Construct<1,unsigned short const *>(&v19, this);
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
      std::wstring::_Construct<1,unsigned short const *>(&v17, (char *)v12 + 2 * v10, v11);
      std::wstring::operator=(&v23, &v17);
      std::wstring::~wstring(&v17);
      v17 = 0;
      v18 = 0;
      do
        ++v5;
      while ( Buffer[v5] );
      std::wstring::_Construct<1,unsigned short const *>(&v17, Buffer, v5);
      v13 = (void *)std::operator+<unsigned short>(v26, &v17, L"\\");
      v14 = std::wstring::append(v13);
      v25[0] = *(_OWORD *)v14;
      v25[1] = *(_OWORD *)(v14 + 16);
      *(_QWORD *)(v14 + 16) = 0;
      *(_QWORD *)(v14 + 24) = 7;
      *(_WORD *)v14 = 0;
      std::wstring::operator=(&v21, v25);
      std::wstring::~wstring(v25);
      std::wstring::~wstring(v26);
      std::wstring::~wstring(&v17);
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
  std::wstring::~wstring(&v19);
  std::wstring::~wstring(&v21);
  std::wstring::~wstring(&v23);
  return v8;
}

```

## disassembly

```asm
0x180036ce4  mov     [rsp-8+arg_10], rbx
0x180036ce9  push    rbp
0x180036cea  push    rsi
0x180036ceb  push    rdi
0x180036cec  push    r14
0x180036cee  push    r15
0x180036cf0  lea     rbp, [rsp-210h]
0x180036cf8  sub     rsp, 310h
0x180036cff  mov     rax, cs:__security_cookie
0x180036d06  xor     rax, rsp
0x180036d09  mov     [rbp+230h+var_30], rax
0x180036d10  mov     r14, rdx
0x180036d13  mov     rsi, rcx
0x180036d16  xor     r15d, r15d
0x180036d19  xor     edx, edx; Val
0x180036d1b  mov     r8d, 208h; Size
0x180036d21  lea     rcx, [rbp+230h+Buffer]; void *
0x180036d25  call    memset_0
0x180036d2a  mov     [r14], r15b
0x180036d2d  xorps   xmm0, xmm0
0x180036d30  movups  [rbp+230h+var_2A8], xmm0
0x180036d34  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180036d3c  movdqu  [rbp+230h+var_298], xmm1
0x180036d41  mov     word ptr [rbp+230h+var_2A8], r15w
0x180036d46  movups  [rsp+330h+var_2C8], xmm0
0x180036d4b  movdqu  [rsp+330h+var_2B8], xmm1
0x180036d51  mov     word ptr [rsp+330h+var_2C8], r15w
0x180036d57  movups  [rsp+330h+var_2E8], xmm0
0x180036d5c  xorps   xmm1, xmm1
0x180036d5f  movdqu  [rsp+330h+var_2D8], xmm1
0x180036d65  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180036d69  mov     r8, rdi
0x180036d6c  inc     r8
0x180036d6f  cmp     [rsi+r8*2], r15w
0x180036d74  jnz     short loc_180036D6C
0x180036d76  mov     rdx, rsi
0x180036d79  lea     rcx, [rsp+330h+var_2E8]
0x180036d7e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036d83  nop
0x180036d84  mov     edx, 104h; uSize
0x180036d89  lea     rcx, [rbp+230h+Buffer]; lpBuffer
0x180036d8d  call    cs:__imp_GetSystemDirectoryW
0x180036d93  test    eax, eax
0x180036d95  jnz     short loc_180036DC5
0x180036d97  call    cs:__imp_GetLastError
0x180036d9d  mov     ebx, eax
0x180036d9f  test    eax, eax
0x180036da1  jle     short loc_180036DAC
0x180036da3  movzx   ebx, ax
0x180036da6  or      ebx, 80070000h
0x180036dac  mov     r8d, ebx
0x180036daf  lea     rdx, aFailedToFindTh_0; "Failed to find the Windows system direc"...
0x180036db6  mov     ecx, 2; unsigned __int8
0x180036dbb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180036dc0  jmp     loc_180036F1A
0x180036dc5  lea     rcx, [rsp+330h+var_2E8]
0x180036dca  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x180036dcf  cmp     rax, rdi
0x180036dd2  jz      loc_180036F03
0x180036dd8  lea     rcx, [rax+1]
0x180036ddc  xorps   xmm0, xmm0
0x180036ddf  movups  [rsp+330h+var_308], xmm0
0x180036de4  xorps   xmm1, xmm1
0x180036de7  movdqu  [rsp+330h+var_2F8], xmm1
0x180036ded  mov     rax, qword ptr [rsp+330h+var_2D8]
0x180036df2  cmp     rax, rcx
0x180036df5  jb      loc_180036F61
0x180036dfb  mov     ebx, r15d
0x180036dfe  sub     rax, rcx
0x180036e01  mov     r8, rdi
0x180036e04  cmp     rax, rdi
0x180036e07  cmovb   r8, rax
0x180036e0b  lea     rax, [rsp+330h+var_2E8]
0x180036e10  cmp     qword ptr [rsp+330h+var_2D8+8], 7
0x180036e16  cmova   rax, qword ptr [rsp+330h+var_2E8]
0x180036e1c  lea     rdx, [rax+rcx*2]
0x180036e20  lea     rcx, [rsp+330h+var_308]
0x180036e25  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036e2a  lea     rdx, [rsp+330h+var_308]
0x180036e2f  lea     rcx, [rbp+230h+var_2A8]
0x180036e33  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036e38  lea     rcx, [rsp+330h+var_308]; void *
0x180036e3d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036e42  xorps   xmm0, xmm0
0x180036e45  movups  [rsp+330h+var_308], xmm0
0x180036e4a  xorps   xmm1, xmm1
0x180036e4d  movdqu  [rsp+330h+var_2F8], xmm1
0x180036e53  lea     rax, [rbp+230h+Buffer]
0x180036e57  inc     rdi
0x180036e5a  cmp     [rax+rdi*2], r15w
0x180036e5f  jnz     short loc_180036E57
0x180036e61  mov     r8, rdi
0x180036e64  lea     rdx, [rbp+230h+Buffer]
0x180036e68  lea     rcx, [rsp+330h+var_308]
0x180036e6d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036e72  nop
0x180036e73  lea     r8, asc_180081F30; "\\"
0x180036e7a  lea     rdx, [rsp+330h+var_308]
0x180036e7f  lea     rcx, [rbp+230h+var_268]
0x180036e83  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180036e88  nop
0x180036e89  lea     rdx, [rbp+230h+var_2A8]
0x180036e8d  mov     rcx, rax; Src
0x180036e90  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180036e95  movups  xmm0, xmmword ptr [rax]
0x180036e98  movups  [rbp+230h+var_288], xmm0
0x180036e9c  movups  xmm1, xmmword ptr [rax+10h]
0x180036ea0  movups  [rbp+230h+var_278], xmm1
0x180036ea4  mov     [rax+10h], r15
0x180036ea8  mov     qword ptr [rax+18h], 7
0x180036eb0  mov     [rax], r15w
0x180036eb4  lea     rdx, [rbp+230h+var_288]
0x180036eb8  lea     rcx, [rsp+330h+var_2C8]
0x180036ebd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180036ec2  lea     rcx, [rbp+230h+var_288]; void *
0x180036ec6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036ecb  nop
0x180036ecc  lea     rcx, [rbp+230h+var_268]; void *
0x180036ed0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036ed5  nop
0x180036ed6  lea     rcx, [rsp+330h+var_308]; void *
0x180036edb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036ee0  lea     rdx, [rsp+330h+var_2C8]
0x180036ee5  cmp     qword ptr [rbp+230h+var_2B8+8], 7
0x180036eea  cmova   rdx, qword ptr [rsp+330h+var_2C8]
0x180036ef0  mov     rcx, rsi
0x180036ef3  call    cs:__imp__o__wcsicmp
0x180036ef9  test    eax, eax
0x180036efb  setz    al
0x180036efe  mov     [r14], al
0x180036f01  jmp     short loc_180036F1A
0x180036f03  mov     ebx, 800700A1h
0x180036f08  lea     rdx, aExpectedAFullP; "Expected a full path name."
0x180036f0f  mov     ecx, 2; unsigned __int8
0x180036f14  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180036f19  nop
0x180036f1a  lea     rcx, [rsp+330h+var_2E8]; void *
0x180036f1f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036f24  nop
0x180036f25  lea     rcx, [rsp+330h+var_2C8]; void *
0x180036f2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036f2f  nop
0x180036f30  lea     rcx, [rbp+230h+var_2A8]; void *
0x180036f34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180036f39  mov     eax, ebx
0x180036f3b  mov     rcx, [rbp+230h+var_30]
0x180036f42  xor     rcx, rsp; StackCookie
0x180036f45  call    __security_check_cookie
0x180036f4a  mov     rbx, [rsp+330h+arg_10]
0x180036f52  add     rsp, 310h
0x180036f59  pop     r15
0x180036f5b  pop     r14
0x180036f5d  pop     rdi
0x180036f5e  pop     rsi
0x180036f5f  pop     rbp
0x180036f60  retn
0x180036f61  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```

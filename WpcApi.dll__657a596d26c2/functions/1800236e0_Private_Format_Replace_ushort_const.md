# Private::Format::Replace(ushort const *)

- ea: `0x1800236e0`
- end: `0x180023856`
- name: `?Replace@Format@Private@@AEAAXPEBG@Z`
- size: `374`
- prototype: `void __fastcall(Private::Format *this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x180014d98`
- `0x1800171f0`
- `0x1800199a0`

## callees

- `0x1800032a0`
- `0x180003d14`
- `0x180005950`
- `0x180005f9c`
- `0x1800198f4`
- `0x18001a548`
- `0x18001b914`
- `0x180023158`
- `0x1800236e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x18002373b`
- `api-ms-win-crt-private-l1-1-0!_o__i64tow_s` at `0x18002373b`

## pseudocode

```c
void __fastcall Private::Format::Replace(Private::Format *this, unsigned __int16 *a2)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // r8
  __int64 v6; // rax
  __int64 *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rax
  _OWORD v10[2]; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v11; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v12; // [rsp+58h] [rbp-A8h]
  _OWORD Src[2]; // [rsp+68h] [rbp-98h] BYREF
  char *v14[4]; // [rsp+88h] [rbp-78h] BYREF
  char *v15[5]; // [rsp+A8h] [rbp-58h] BYREF
  _WORD v16[72]; // [rsp+D0h] [rbp-30h] BYREF

  v4 = *((int *)this + 8);
  *((_DWORD *)this + 8) = v4 + 1;
  memset_0(v16, 0, 0x82u);
  _o__i64tow_s(v4, v16, 65, 10);
  memset(Src, 0, sizeof(Src));
  v5 = -1;
  do
    ++v5;
  while ( v16[v5] );
  std::wstring::_Construct<1,unsigned short const *>(Src, v16, v5);
  v6 = std::wstring::_Insert<unsigned short>(Src);
  v11 = 0;
  v12 = 0;
  v11 = *(_OWORD *)v6;
  v12 = *(_OWORD *)(v6 + 16);
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 7;
  *(_WORD *)v6 = 0;
  v7 = (__int64 *)std::operator+<unsigned short>(v15, &v11);
  v8 = (__int64)v7;
  if ( (unsigned __int64)v7[3] > 7 )
    v8 = *v7;
  v10[0] = *(_OWORD *)this;
  v10[1] = *((_OWORD *)this + 1);
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 7;
  *(_WORD *)this = 0;
  v9 = StringAlgo::Replace<unsigned short,unsigned short>((__int64)v14, v10, v8, a2);
  std::wstring::operator=(this, v9);
  std::wstring::~wstring(v14);
  std::wstring::~wstring(v15);
  std::wstring::~wstring((char **)&v11);
  std::wstring::~wstring((char **)Src);
}

```

## disassembly

```asm
0x1800236e0  mov     [rsp-8+arg_10], rbx
0x1800236e5  mov     [rsp-8+arg_18], rsi
0x1800236ea  push    rbp
0x1800236eb  push    rdi
0x1800236ec  push    r14
0x1800236ee  lea     rbp, [rsp-70h]
0x1800236f3  sub     rsp, 170h
0x1800236fa  mov     rax, cs:__security_cookie
0x180023701  xor     rax, rsp
0x180023704  mov     [rbp+80h+var_20], rax
0x180023708  mov     rsi, rdx
0x18002370b  mov     rdi, rcx
0x18002370e  xor     r14d, r14d
0x180023711  movsxd  rbx, dword ptr [rcx+20h]
0x180023715  lea     eax, [rbx+1]
0x180023718  mov     [rcx+20h], eax
0x18002371b  xor     edx, edx; Val
0x18002371d  mov     r8d, 82h; Size
0x180023723  lea     rcx, [rbp+80h+var_B0]; void *
0x180023727  call    memset_0
0x18002372c  mov     rcx, rbx
0x18002372f  lea     r9d, [r14+0Ah]
0x180023733  lea     r8d, [r14+41h]
0x180023737  lea     rdx, [rbp+80h+var_B0]
0x18002373b  call    cs:__imp__o__i64tow_s
0x180023741  xorps   xmm0, xmm0
0x180023744  movups  [rsp+180h+Src], xmm0
0x180023749  xorps   xmm1, xmm1
0x18002374c  movdqu  [rsp+180h+var_108], xmm1
0x180023752  lea     rax, [rbp+80h+var_B0]
0x180023756  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002375a  inc     r8
0x18002375d  cmp     [rax+r8*2], r14w
0x180023762  jnz     short loc_18002375A
0x180023764  lea     rdx, [rbp+80h+var_B0]
0x180023768  lea     rcx, [rsp+180h+Src]
0x18002376d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180023772  nop
0x180023773  mov     r9d, 1
0x180023779  lea     rcx, [rsp+180h+Src]; Src
0x18002377e  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x180023783  xorps   xmm0, xmm0
0x180023786  movups  [rsp+180h+var_138], xmm0
0x18002378b  xorps   xmm1, xmm1
0x18002378e  movdqu  [rsp+180h+var_128], xmm1
0x180023794  movups  xmm0, xmmword ptr [rax]
0x180023797  movups  [rsp+180h+var_138], xmm0
0x18002379c  movups  xmm1, xmmword ptr [rax+10h]
0x1800237a0  movups  [rsp+180h+var_128], xmm1
0x1800237a5  mov     [rax+10h], r14
0x1800237a9  mov     ebx, 7
0x1800237ae  mov     [rax+18h], rbx
0x1800237b2  mov     [rax], r14w
0x1800237b6  lea     rdx, [rsp+180h+var_138]
0x1800237bb  lea     rcx, [rbp+80h+var_D8]
0x1800237bf  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800237c4  mov     r8, rax
0x1800237c7  cmp     [rax+18h], rbx
0x1800237cb  jbe     short loc_1800237D0
0x1800237cd  mov     r8, [rax]
0x1800237d0  movups  xmm0, xmmword ptr [rdi]
0x1800237d3  movups  [rsp+180h+var_158], xmm0
0x1800237d8  movups  xmm1, xmmword ptr [rdi+10h]
0x1800237dc  movups  [rsp+180h+var_148], xmm1
0x1800237e1  mov     [rdi+10h], r14
0x1800237e5  mov     [rdi+18h], rbx
0x1800237e9  mov     [rdi], r14w
0x1800237ed  mov     r9, rsi
0x1800237f0  lea     rdx, [rsp+180h+var_158]
0x1800237f5  lea     rcx, [rbp+80h+var_F8]
0x1800237f9  call    ??$Replace@GG@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@PEBG1@Z; StringAlgo::Replace<ushort,ushort>(std::wstring,ushort const *,ushort const *)
0x1800237fe  mov     rdx, rax
0x180023801  mov     rcx, rdi
0x180023804  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180023809  lea     rcx, [rbp+80h+var_F8]
0x18002380d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023812  nop
0x180023813  lea     rcx, [rbp+80h+var_D8]
0x180023817  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002381c  nop
0x18002381d  lea     rcx, [rsp+180h+var_138]
0x180023822  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023827  nop
0x180023828  lea     rcx, [rsp+180h+Src]
0x18002382d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023832  mov     rcx, [rbp+80h+var_20]
0x180023836  xor     rcx, rsp; StackCookie
0x180023839  call    __security_check_cookie
0x18002383e  lea     r11, [rsp+180h+var_10]
0x180023846  mov     rbx, [r11+30h]
0x18002384a  mov     rsi, [r11+38h]
0x18002384e  mov     rsp, r11
0x180023851  pop     r14
0x180023853  pop     rdi
0x180023854  pop     rbp
0x180023855  retn
```

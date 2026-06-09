# CCellularSmsDevice::UpdateSMSCAddress(long,SMS_ADDRESS *,__int64)

- ea: `0x1800482c0`
- end: `0x1800484b2`
- name: `?UpdateSMSCAddress@CCellularSmsDevice@@UEAAJJPEAUSMS_ADDRESS@@_J@Z`
- size: `498`
- prototype: `__int64 __fastcall(CCellularSmsDevice *__hidden this, int, struct SMS_ADDRESS *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x18000e05c`
- `0x18000e534`
- `0x180013d40`
- `0x18002ccd8`
- `0x1800482c0`
- `0x180051420`
- `0x18006f010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18004843c`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x18004843c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004844e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004844e`
- `OLEAUT32!__imp_SysAllocString` at `0x180048419`
- `OLEAUT32!__imp_SysAllocString` at `0x180048419`

## string_xrefs

- `0x18004846d`: `CCellularSmsDevice::UpdateSMSCAddress`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCellularSmsDevice::UpdateSMSCAddress(
        CCellularSmsDevice *this,
        int a2,
        struct SMS_ADDRESS *a3,
        unsigned __int64 a4)
{
  char *v8; // r14
  __int64 *v9; // r8
  __int64 *v10; // rdx
  __int64 *v11; // rcx
  __int64 *v12; // rax
  BSTR *v13; // rbx
  __int64 v14; // r8
  _OWORD *v15; // rcx
  __int64 v16; // rax
  const OLECHAR *p_psz; // rcx
  _BYTE v19[24]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v20[128]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v21[104]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v22[528]; // [rsp+150h] [rbp+50h] BYREF
  OLECHAR *psz; // [rsp+360h] [rbp+260h] BYREF
  int v24; // [rsp+36Ch] [rbp+26Ch]
  unsigned __int64 v25; // [rsp+378h] [rbp+278h]

  v8 = (char *)this + 80;
  (**((void (__fastcall ***)(char *))this + 10))((char *)this + 80);
  v9 = (__int64 *)*((_QWORD *)this + 112);
  v10 = (__int64 *)v9[1];
  v24 = 0;
  v11 = v9;
  if ( !*((_BYTE *)v10 + 25) )
  {
    do
    {
      if ( v10[4] >= a4 )
        v11 = v10;
      v12 = v10 + 2;
      if ( v10[4] >= a4 )
        v12 = v10;
      v10 = (__int64 *)*v12;
    }
    while ( !*(_BYTE *)(*v12 + 25) );
  }
  if ( *((_BYTE *)v11 + 25) || a4 < v11[4] || v11 == v9 )
  {
    LogSmsRouterError(
      "CCellularSmsDevice::UpdateSMSCAddress",
      0x3D2u,
      -2147023728,
      "GetSmscAddress context 0x%08X not found.",
      a4);
  }
  else
  {
    v13 = *(BSTR **)(a4 + 16);
    *(_DWORD *)(a4 + 8) = a2;
    if ( a2 < 0 )
    {
      *v13 = 0;
    }
    else
    {
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v19);
      v15 = v22;
      v16 = 4;
      do
      {
        *v15 = *(_OWORD *)a3;
        v15[1] = *((_OWORD *)a3 + 1);
        v15[2] = *((_OWORD *)a3 + 2);
        v15[3] = *((_OWORD *)a3 + 3);
        v15[4] = *((_OWORD *)a3 + 4);
        v15[5] = *((_OWORD *)a3 + 5);
        v15[6] = *((_OWORD *)a3 + 6);
        v15[7] = *((_OWORD *)a3 + 7);
        v15 += 8;
        a3 = (struct SMS_ADDRESS *)((char *)a3 + 128);
        --v16;
      }
      while ( v16 );
      *(_DWORD *)v15 = *(_DWORD *)a3;
      GetSmsAddressString(v22, v19, v14);
      std::basic_stringbuf<unsigned short>::str(v20, &psz);
      p_psz = (const OLECHAR *)&psz;
      if ( v25 > 7 )
        p_psz = psz;
      *v13 = SysAllocString(p_psz);
      std::wstring::~wstring((char **)&psz);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>((__int64)v21);
      std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v21);
    }
    SetEvent(*(HANDLE *)a4);
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
  return 0;
}

```

## disassembly

```asm
0x1800482c0  mov     [rsp-8+arg_0], rbx
0x1800482c5  push    rbp
0x1800482c6  push    rsi
0x1800482c7  push    rdi
0x1800482c8  push    r14
0x1800482ca  push    r15
0x1800482cc  lea     rbp, [rsp-290h]
0x1800482d4  sub     rsp, 390h
0x1800482db  mov     rax, cs:__security_cookie
0x1800482e2  xor     rax, rsp
0x1800482e5  mov     [rbp+2B0h+var_30], rax
0x1800482ec  mov     rsi, r9
0x1800482ef  mov     rdi, r8
0x1800482f2  mov     r15d, edx
0x1800482f5  mov     rbx, rcx
0x1800482f8  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x1800482ff  mov     [rsp+3B0h+var_378], rax
0x180048304  lea     r14, [rcx+50h]
0x180048308  mov     [rsp+3B0h+var_370], r14
0x18004830d  mov     rax, [r14]
0x180048310  mov     rcx, r14
0x180048313  mov     rax, [rax]
0x180048316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004831b  nop
0x18004831c  mov     r8, [rbx+380h]
0x180048323  mov     rdx, [r8+8]
0x180048327  xor     eax, eax
0x180048329  mov     [rbp+2B0h+var_44], eax
0x18004832f  mov     rcx, r8
0x180048332  cmp     [rdx+19h], al
0x180048335  jnz     short loc_180048350
0x180048337  cmp     [rdx+20h], rsi
0x18004833b  cmovnb  rcx, rdx
0x18004833f  lea     rax, [rdx+10h]
0x180048343  cmovnb  rax, rdx
0x180048347  mov     rdx, [rax]
0x18004834a  cmp     byte ptr [rdx+19h], 0
0x18004834e  jz      short loc_180048337
0x180048350  cmp     byte ptr [rcx+19h], 0
0x180048354  jnz     loc_180048456
0x18004835a  cmp     rsi, [rcx+20h]
0x18004835e  jb      loc_180048456
0x180048364  cmp     rcx, r8
0x180048367  jz      loc_180048456
0x18004836d  mov     rbx, [rsi+10h]
0x180048371  mov     [rsi+8], r15d
0x180048375  test    r15d, r15d
0x180048378  js      loc_180048444
0x18004837e  lea     rcx, [rsp+3B0h+var_360]
0x180048383  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180048388  nop
0x180048389  lea     rcx, [rbp+2B0h+var_260]
0x18004838d  mov     eax, 4
0x180048392  lea     edx, [rax+7Ch]
0x180048395  movups  xmm0, xmmword ptr [rdi]
0x180048398  movups  xmmword ptr [rcx], xmm0
0x18004839b  movups  xmm1, xmmword ptr [rdi+10h]
0x18004839f  movups  xmmword ptr [rcx+10h], xmm1
0x1800483a3  movups  xmm0, xmmword ptr [rdi+20h]
0x1800483a7  movups  xmmword ptr [rcx+20h], xmm0
0x1800483ab  movups  xmm1, xmmword ptr [rdi+30h]
0x1800483af  movups  xmmword ptr [rcx+30h], xmm1
0x1800483b3  movups  xmm0, xmmword ptr [rdi+40h]
0x1800483b7  movups  xmmword ptr [rcx+40h], xmm0
0x1800483bb  movups  xmm1, xmmword ptr [rdi+50h]
0x1800483bf  movups  xmmword ptr [rcx+50h], xmm1
0x1800483c3  movups  xmm0, xmmword ptr [rdi+60h]
0x1800483c7  movups  xmmword ptr [rcx+60h], xmm0
0x1800483cb  movups  xmm1, xmmword ptr [rdi+70h]
0x1800483cf  movups  xmmword ptr [rcx+70h], xmm1
0x1800483d3  add     rcx, rdx
0x1800483d6  add     rdi, rdx
0x1800483d9  sub     rax, 1
0x1800483dd  jnz     short loc_180048395
0x1800483df  mov     eax, [rdi]
0x1800483e1  mov     [rcx], eax
0x1800483e3  lea     rdx, [rsp+3B0h+var_360]
0x1800483e8  lea     rcx, [rbp+2B0h+var_260]
0x1800483ec  call    ?GetSmsAddressString@@YAXUSMS_ADDRESS@@AEAV?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetSmsAddressString(SMS_ADDRESS,std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)
0x1800483f1  lea     rdx, [rbp+2B0h+psz]
0x1800483f8  lea     rcx, [rsp+3B0h+var_348]
0x1800483fd  call    ?str@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@XZ; std::basic_stringbuf<ushort>::str(void)
0x180048402  lea     rcx, [rbp+2B0h+psz]
0x180048409  cmp     [rbp+2B0h+var_38], 7
0x180048411  cmova   rcx, [rbp+2B0h+psz]; psz
0x180048419  call    cs:__imp_SysAllocString
0x18004841f  mov     [rbx], rax
0x180048422  lea     rcx, [rbp+2B0h+psz]; void *
0x180048429  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004842e  nop
0x18004842f  lea     rcx, [rbp+2B0h+var_2C8]
0x180048433  call    ??1?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x180048438  lea     rcx, [rbp+2B0h+var_2C8]
0x18004843c  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180048442  jmp     short loc_18004844B
0x180048444  mov     qword ptr [rbx], 0
0x18004844b  mov     rcx, [rsi]; hEvent
0x18004844e  call    cs:__imp_SetEvent
0x180048454  jmp     short loc_18004847A
0x180048456  mov     [rsp+3B0h+var_390], rsi
0x18004845b  lea     r9, aGetsmscaddress_0; "GetSmscAddress context 0x%08X not found"...
0x180048462  mov     edx, 3D2h; unsigned int
0x180048467  mov     r8d, 80070490h; int
0x18004846d  lea     rcx, aCcellularsmsde_5; "CCellularSmsDevice::UpdateSMSCAddress"
0x180048474  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180048479  nop
0x18004847a  mov     rax, [r14]
0x18004847d  mov     rcx, r14
0x180048480  mov     rax, [rax+8]
0x180048484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048489  nop
0x18004848a  xor     eax, eax
0x18004848c  mov     rcx, [rbp+2B0h+var_30]
0x180048493  xor     rcx, rsp; StackCookie
0x180048496  call    __security_check_cookie
0x18004849b  mov     rbx, [rsp+3B0h+arg_0]
0x1800484a3  add     rsp, 390h
0x1800484aa  pop     r15
0x1800484ac  pop     r14
0x1800484ae  pop     rdi
0x1800484af  pop     rsi
0x1800484b0  pop     rbp
0x1800484b1  retn
```

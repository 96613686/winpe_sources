# RoutingRequestDialog::Initialize(RoutingEntry const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18003705c`
- end: `0x1800372fe`
- name: `?Initialize@RoutingRequestDialog@@IEAAJPEBURoutingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z`
- size: `674`
- prototype: `__int64 __fastcall(RoutingRequestDialog *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030b40`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x18000d4ec`
- `0x180013274`
- `0x180036c4c`
- `0x180036e7c`
- `0x18003705c`
- `0x180037304`
- `0x180041594`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037177`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037188`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800372ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037177`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037188`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800372ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RoutingRequestDialog::Initialize(RoutingRequestDialog *this, __int64 a2, __int64 a3, _QWORD *a4)
{
  signed int appended; // ebx
  __int64 v8; // rax
  unsigned __int16 *v9; // rcx
  __int64 v10; // rdx
  unsigned __int16 *v11; // r8
  unsigned __int16 v12; // r9
  unsigned __int16 *v13; // rcx
  void *v14; // rcx
  bool v15; // sf
  const unsigned __int16 *v16; // r8
  int v18; // eax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v20; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v23[264]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[528]; // [rsp+270h] [rbp+170h] BYREF

  *(_OWORD *)v21 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v21[0]) = 0;
  if ( !a2 )
  {
    v20 = 0;
    pv = 0;
    appended = (*(__int64 (__fastcall **)(RoutingRequestDialog *, __int64, LPVOID *))(*(_QWORD *)this + 40LL))(
                 this,
                 107,
                 &v20);
    if ( appended >= 0 )
    {
      appended = (*(__int64 (__fastcall **)(RoutingRequestDialog *, __int64, LPVOID *))(*(_QWORD *)this + 40LL))(
                   this,
                   114,
                   &pv);
      if ( appended >= 0 )
      {
        v8 = 2147483646;
        v9 = (unsigned __int16 *)v20;
        v10 = 257;
        v11 = v23;
        do
        {
          if ( !v8 )
            break;
          v12 = *v9;
          if ( !*v9 )
            break;
          ++v9;
          *v11++ = v12;
          --v8;
          --v10;
        }
        while ( v10 );
        appended = v10 == 0 ? 0x8007007A : 0;
        v13 = v11 - 1;
        if ( v10 )
          v13 = v11;
        *v13 = 0;
        if ( v10 )
          appended = RoutingDialog::AppendConflictingAppTitles(this, pv, a4, v21);
      }
    }
    if ( pv )
      CoTaskMemFree(pv);
    v14 = v20;
LABEL_15:
    if ( v14 )
      CoTaskMemFree(v14);
    v15 = appended < 0;
    goto LABEL_18;
  }
  if ( *(_DWORD *)(a2 + 148) != 1 )
  {
    if ( *a4 == a4[1] )
    {
      appended = -2147418113;
      goto LABEL_22;
    }
    pv = 0;
    v20 = 0;
    memset_0(v24, 0, 0x208u);
    appended = (*(__int64 (__fastcall **)(RoutingRequestDialog *, __int64, LPVOID *))(*(_QWORD *)this + 40LL))(
                 this,
                 113,
                 &pv);
    if ( appended >= 0 )
    {
      appended = (*(__int64 (__fastcall **)(RoutingRequestDialog *, __int64, LPVOID *))(*(_QWORD *)this + 40LL))(
                   this,
                   114,
                   &v20);
      if ( appended >= 0 )
      {
        appended = (*(__int64 (__fastcall **)(RoutingRequestDialog *, __int64, _BYTE *))(*(_QWORD *)this + 48LL))(
                     this,
                     a2,
                     v24);
        if ( appended >= 0 )
        {
          appended = StringCchPrintfW(v23, 0x101u, (const unsigned __int16 *)pv, v24);
          if ( appended >= 0 )
            appended = RoutingDialog::AppendConflictingAppTitles(this, v20, a4, v21);
        }
      }
    }
    if ( v20 )
      CoTaskMemFree(v20);
    v14 = pv;
    goto LABEL_15;
  }
  if ( *(_QWORD *)(a3 + 16) )
    v18 = RoutingRequestDialog::BuildReplacedPaymentAppDialogText(
            (_DWORD)this,
            a2,
            a3,
            (_DWORD)a4,
            (__int64)v23,
            (__int64)v21);
  else
    v18 = RoutingRequestDialog::BuildSetPaymentAppDialogText(
            (_DWORD)this,
            a2,
            (_DWORD)a4,
            (unsigned int)v23,
            (__int64)v21);
  appended = v18;
  v15 = v18 < 0;
LABEL_18:
  if ( !v15 )
  {
    v16 = (const unsigned __int16 *)v21;
    if ( si128.m128i_i64[1] > 7uLL )
      v16 = v21[0];
    appended = RoutingRequestDialog::InitializeDialog(this, v23, v16);
  }
LABEL_22:
  std::wstring::~wstring(v21);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18003705c  push    rbp
0x18003705e  push    rbx
0x18003705f  push    rsi
0x180037060  push    rdi
0x180037061  push    r14
0x180037063  push    r15
0x180037065  lea     rbp, [rsp-398h]
0x18003706d  sub     rsp, 498h
0x180037074  mov     rax, cs:__security_cookie
0x18003707b  xor     rax, rsp
0x18003707e  mov     [rbp+3C0h+var_40], rax
0x180037085  mov     rsi, r9
0x180037088  mov     r14, rdx
0x18003708b  mov     rdi, rcx
0x18003708e  xorps   xmm0, xmm0
0x180037091  movups  xmmword ptr [rsp+4C0h+var_480], xmm0
0x180037096  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003709e  movdqu  [rsp+4C0h+var_470], xmm1
0x1800370a4  xor     r15d, r15d
0x1800370a7  mov     word ptr [rsp+4C0h+var_480], r15w
0x1800370ad  test    rdx, rdx
0x1800370b0  jnz     loc_1800371DD
0x1800370b6  mov     [rsp+4C0h+var_488], r15
0x1800370bb  mov     [rsp+4C0h+pv], r15
0x1800370c0  mov     rax, [rcx]
0x1800370c3  lea     r8, [rsp+4C0h+var_488]
0x1800370c8  lea     edx, [r14+6Bh]
0x1800370cc  mov     rax, [rax+28h]
0x1800370d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370d5  mov     ebx, eax
0x1800370d7  test    eax, eax
0x1800370d9  js      loc_18003716D
0x1800370df  mov     rax, [rdi]
0x1800370e2  lea     r8, [rsp+4C0h+pv]
0x1800370e7  lea     edx, [r14+72h]
0x1800370eb  mov     rcx, rdi
0x1800370ee  mov     rax, [rax+28h]
0x1800370f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800370f7  mov     ebx, eax
0x1800370f9  test    eax, eax
0x1800370fb  js      short loc_18003716D
0x1800370fd  mov     eax, 7FFFFFFEh
0x180037102  mov     rcx, [rsp+4C0h+var_488]
0x180037107  mov     edx, 101h
0x18003710c  lea     r8, [rsp+4C0h+var_460]
0x180037111  test    rax, rax
0x180037114  jz      short loc_180037135
0x180037116  movzx   r9d, word ptr [rcx]
0x18003711a  test    r9w, r9w
0x18003711e  jz      short loc_180037135
0x180037120  add     rcx, 2
0x180037124  mov     [r8], r9w
0x180037128  add     r8, 2
0x18003712c  dec     rax
0x18003712f  sub     rdx, 1
0x180037133  jnz     short loc_180037111
0x180037135  mov     rax, rdx
0x180037138  neg     rax
0x18003713b  sbb     ebx, ebx
0x18003713d  not     ebx
0x18003713f  and     ebx, 8007007Ah
0x180037145  lea     rcx, [r8-2]
0x180037149  test    rdx, rdx
0x18003714c  cmovnz  rcx, r8
0x180037150  mov     [rcx], r15w
0x180037154  jz      short loc_18003716D
0x180037156  lea     r9, [rsp+4C0h+var_480]
0x18003715b  mov     r8, rsi
0x18003715e  mov     rdx, [rsp+4C0h+pv]
0x180037163  mov     rcx, rdi
0x180037166  call    ?AppendConflictingAppTitles@RoutingDialog@@QEAAJPEBGAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; RoutingDialog::AppendConflictingAppTitles(ushort const *,std::vector<std::wstring> const &,std::wstring *)
0x18003716b  mov     ebx, eax
0x18003716d  mov     rcx, [rsp+4C0h+pv]; pv
0x180037172  test    rcx, rcx
0x180037175  jz      short loc_18003717E
0x180037177  call    cs:__imp_CoTaskMemFree
0x18003717d  nop
0x18003717e  mov     rcx, [rsp+4C0h+var_488]; pv
0x180037183  test    rcx, rcx
0x180037186  jz      short loc_18003718E
0x180037188  call    cs:__imp_CoTaskMemFree
0x18003718e  test    ebx, ebx
0x180037190  js      short loc_1800371B2
0x180037192  lea     r8, [rsp+4C0h+var_480]
0x180037197  cmp     qword ptr [rsp+4C0h+var_470+8], 7
0x18003719d  cmova   r8, [rsp+4C0h+var_480]; unsigned __int16 *
0x1800371a3  lea     rdx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800371a8  mov     rcx, rdi; this
0x1800371ab  call    ?InitializeDialog@RoutingRequestDialog@@AEAAJPEBG0@Z; RoutingRequestDialog::InitializeDialog(ushort const *,ushort const *)
0x1800371b0  mov     ebx, eax
0x1800371b2  lea     rcx, [rsp+4C0h+var_480]
0x1800371b7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800371bc  mov     eax, ebx
0x1800371be  mov     rcx, [rbp+3C0h+var_40]
0x1800371c5  xor     rcx, rsp; StackCookie
0x1800371c8  call    __security_check_cookie
0x1800371cd  add     rsp, 498h
0x1800371d4  pop     r15
0x1800371d6  pop     r14
0x1800371d8  pop     rdi
0x1800371d9  pop     rsi
0x1800371da  pop     rbx
0x1800371db  pop     rbp
0x1800371dc  retn
0x1800371dd  cmp     dword ptr [rdx+94h], 1
0x1800371e4  jnz     short loc_18003721F
0x1800371e6  lea     rax, [rsp+4C0h+var_480]
0x1800371eb  cmp     [r8+10h], r15
0x1800371ef  jnz     short loc_180037209
0x1800371f1  mov     [rsp+4C0h+var_4A0], rax
0x1800371f6  lea     r9, [rsp+4C0h+var_460]
0x1800371fb  mov     r8, rsi
0x1800371fe  call    ?BuildSetPaymentAppDialogText@RoutingRequestDialog@@QEAAJAEBURoutingEntry@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; RoutingRequestDialog::BuildSetPaymentAppDialogText(RoutingEntry const &,std::vector<std::wstring> const &,ushort * const,std::wstring *)
0x180037203  mov     ebx, eax
0x180037205  test    eax, eax
0x180037207  jmp     short loc_180037190
0x180037209  mov     [rsp+4C0h+var_498], rax
0x18003720e  lea     rax, [rsp+4C0h+var_460]
0x180037213  mov     [rsp+4C0h+var_4A0], rax
0x180037218  call    ?BuildReplacedPaymentAppDialogText@RoutingRequestDialog@@QEAAJAEBURoutingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@QEAGPEAV34@@Z; RoutingRequestDialog::BuildReplacedPaymentAppDialogText(RoutingEntry const &,std::wstring const &,std::vector<std::wstring> const &,ushort * const,std::wstring *)
0x18003721d  jmp     short loc_180037203
0x18003721f  mov     rax, [r9+8]
0x180037223  cmp     [r9], rax
0x180037226  jnz     short loc_18003722F
0x180037228  mov     ebx, 8000FFFFh
0x18003722d  jmp     short loc_1800371B2
0x18003722f  mov     [rsp+4C0h+pv], r15
0x180037234  mov     [rsp+4C0h+var_488], r15
0x180037239  xor     edx, edx; Val
0x18003723b  mov     r8d, 208h; Size
0x180037241  lea     rcx, [rbp+3C0h+var_250]; void *
0x180037248  call    memset_0
0x18003724d  mov     rax, [rdi]
0x180037250  lea     r8, [rsp+4C0h+pv]
0x180037255  mov     edx, 71h ; 'q'
0x18003725a  mov     rcx, rdi
0x18003725d  mov     rax, [rax+28h]
0x180037261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037266  mov     ebx, eax
0x180037268  test    eax, eax
0x18003726a  js      short loc_1800372E2
0x18003726c  mov     rax, [rdi]
0x18003726f  lea     r8, [rsp+4C0h+var_488]
0x180037274  mov     edx, 72h ; 'r'
0x180037279  mov     rcx, rdi
0x18003727c  mov     rax, [rax+28h]
0x180037280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037285  mov     ebx, eax
0x180037287  test    eax, eax
0x180037289  js      short loc_1800372E2
0x18003728b  mov     rax, [rdi]
0x18003728e  lea     r8, [rbp+3C0h+var_250]
0x180037295  mov     rdx, r14
0x180037298  mov     rcx, rdi
0x18003729b  mov     rax, [rax+30h]
0x18003729f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372a4  mov     ebx, eax
0x1800372a6  test    eax, eax
0x1800372a8  js      short loc_1800372E2
0x1800372aa  lea     r9, [rbp+3C0h+var_250]
0x1800372b1  mov     r8, [rsp+4C0h+pv]; unsigned __int16 *
0x1800372b6  mov     edx, 101h; unsigned __int64
0x1800372bb  lea     rcx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800372c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800372c5  mov     ebx, eax
0x1800372c7  test    eax, eax
0x1800372c9  js      short loc_1800372E2
0x1800372cb  lea     r9, [rsp+4C0h+var_480]
0x1800372d0  mov     r8, rsi
0x1800372d3  mov     rdx, [rsp+4C0h+var_488]
0x1800372d8  mov     rcx, rdi
0x1800372db  call    ?AppendConflictingAppTitles@RoutingDialog@@QEAAJPEBGAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; RoutingDialog::AppendConflictingAppTitles(ushort const *,std::vector<std::wstring> const &,std::wstring *)
0x1800372e0  mov     ebx, eax
0x1800372e2  mov     rcx, [rsp+4C0h+var_488]; pv
0x1800372e7  test    rcx, rcx
0x1800372ea  jz      short loc_1800372F3
0x1800372ec  call    cs:__imp_CoTaskMemFree
0x1800372f2  nop
0x1800372f3  mov     rcx, [rsp+4C0h+pv]
0x1800372f8  jmp     loc_180037183
```

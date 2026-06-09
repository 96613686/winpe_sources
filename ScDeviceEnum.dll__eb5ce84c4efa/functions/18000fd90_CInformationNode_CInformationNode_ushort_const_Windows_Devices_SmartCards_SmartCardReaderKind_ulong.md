# CInformationNode::CInformationNode(ushort const *,Windows::Devices::SmartCards::SmartCardReaderKind,ulong)

- ea: `0x18000fd90`
- end: `0x180010052`
- name: `??0CInformationNode@@QEAA@PEBGW4SmartCardReaderKind@SmartCards@Devices@Windows@@K@Z`
- size: `706`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000cf60`
- `0x18000e228`

## callees

- `0x180001444`
- `0x180006d40`
- `0x180009840`
- `0x180009c38`
- `0x18000c58c`
- `0x18000fd60`
- `0x18000fd90`
- `0x180010134`
- `0x1800105dc`
- `0x180011728`
- `0x1800117d0`
- `0x1800118c0`
- `0x18001e020`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000fea5`
- `msvcrt!swprintf_s` at `0x18000fea5`

## pseudocode

```c
__int64 __fastcall CInformationNode::CInformationNode(__int64 a1, __int64 a2, int a3, unsigned int a4)
{
  char v7; // di
  __int64 **v8; // r14
  void *v9; // rsi
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rcx
  __int64 *v16; // rdx
  __int64 *v17; // r8
  __int64 *v18; // r8
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v22[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[16]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v24; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  _BYTE v26[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v28[48]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Buffer[64]; // [rsp+F0h] [rbp-10h] BYREF

  v22[2] = a1;
  v7 = 0;
  ((void (*)(void))std::wstring::wstring)();
  v8 = (__int64 **)(a1 + 32);
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 48) = a3;
  *(_DWORD *)(a1 + 52) = a4;
  *(_QWORD *)(a1 + 56) = &Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable';
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 72) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *(_BYTE *)(a1 + 88) = 0;
  v20 = 0;
  strcpy(v28, "CInformationNode::CInformationNode");
  v22[0] = v28;
  v22[1] = &v20;
  lambda_fcd60ded7dc1582d860277ea63697796_::operator()(v22);
  v20 = 1;
  v21 = v22;
  v9 = operator new(0x20u);
  v22[3] = v9;
  if ( v9 )
  {
    v10 = std::wstring::wstring(v27, L"_");
    swprintf_s(Buffer, 0x40u, L"%lu", a4);
    std::wstring::wstring(v23, Buffer);
    if ( *(_QWORD *)(v10 + 16) <= v25 - v24 || *(_QWORD *)(v10 + 24) - *(_QWORD *)(v10 + 16) < v24 )
      v12 = std::wstring::append(v23, v10);
    else
      v12 = std::wstring::insert(v10, v11, v23);
    std::wstring::wstring(v26, v12);
    v13 = std::wstring::append(v26, a1);
    std::wstring::wstring(v9, v13);
    v7 = 63;
  }
  else
  {
    v9 = 0;
  }
  std::unique_ptr<std::wstring>::reset(a1 + 32, v9);
  if ( (v7 & 4) != 0 )
  {
    v7 &= ~4u;
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v26, v14, 0);
  }
  if ( (v7 & 2) != 0 )
  {
    v7 &= ~2u;
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v23, v14, 0);
  }
  if ( (v7 & 1) != 0 )
  {
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(v27, v14, 0);
  }
  v15 = *v8;
  if ( (unsigned __int64)(*v8)[3] < 8 )
    v16 = *v8;
  else
    v16 = (__int64 *)*v15;
  v17 = (__int64 *)((char *)v16 + 2 * v15[2]);
  if ( (unsigned __int64)(*v8)[3] >= 8 )
    v15 = (__int64 *)*v15;
  while ( v15 != v17 )
  {
    if ( *(_WORD *)v15 <= 0x20u || *(_WORD *)v15 == 44 || *(_WORD *)v15 == 92 || *(_WORD *)v15 > 0x7Fu )
      *(_WORD *)v15 = 95;
    v15 = (__int64 *)((char *)v15 + 2);
  }
  WppTraceIndent(v15, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v18 = *v8;
    if ( (unsigned __int64)(*v8)[3] < 8 )
      v18 = (__int64 *)(a1 + 32);
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)&WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids,
      (_DWORD)WPP_pszIndent,
      *v18);
  }
  WppTraceUnwinder__lambda_fcd60ded7dc1582d860277ea63697796____::_WppTraceUnwinder__lambda_fcd60ded7dc1582d860277ea63697796____(&v21);
  return a1;
}

```

## disassembly

```asm
0x18000fd90  mov     [rsp-8+arg_0], rcx
0x18000fd95  push    rbp
0x18000fd96  push    rbx
0x18000fd97  push    rsi
0x18000fd98  push    rdi
0x18000fd99  push    r12
0x18000fd9b  push    r14
0x18000fd9d  push    r15
0x18000fd9f  lea     rbp, [rsp-80h]
0x18000fda4  sub     rsp, 180h
0x18000fdab  mov     rax, cs:__security_cookie
0x18000fdb2  xor     rax, rsp
0x18000fdb5  mov     [rbp+0B0h+var_40], rax
0x18000fdb9  mov     r12d, r9d
0x18000fdbc  mov     ebx, r8d
0x18000fdbf  mov     r15, rcx
0x18000fdc2  mov     [rsp+1B0h+var_160], rcx
0x18000fdc7  xor     esi, esi
0x18000fdc9  mov     edi, esi
0x18000fdcb  mov     [rsp+1B0h+var_180], esi
0x18000fdcf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000fdd4  nop
0x18000fdd5  lea     r14, [r15+20h]
0x18000fdd9  mov     [r14], rsi
0x18000fddc  mov     [r15+28h], rsi
0x18000fde0  mov     [r15+30h], ebx
0x18000fde4  mov     [r15+34h], r12d
0x18000fde8  lea     rax, ??_7?$HandleT@USwDeviceHandleTraits@ScDeviceEnum@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ScDeviceEnum::SwDeviceHandleTraits>::`vftable'
0x18000fdef  mov     [r15+38h], rax
0x18000fdf3  mov     [r15+40h], rsi
0x18000fdf7  mov     [r15+50h], rsi
0x18000fdfb  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18000fe02  mov     [r15+48h], rax
0x18000fe06  mov     [r15+58h], sil
0x18000fe0a  mov     [rsp+1B0h+var_17C], esi
0x18000fe0e  movups  xmm0, xmmword ptr cs:aCinformationno_1; "CInformationNode::CInformationNode"
0x18000fe15  movups  xmmword ptr [rbp+0B0h+var_F0], xmm0
0x18000fe19  movups  xmm1, xmmword ptr cs:aCinformationno_1+10h; "::CInformationNode"
0x18000fe20  movups  xmmword ptr [rbp+0B0h+var_F0+10h], xmm1
0x18000fe24  mov     eax, dword ptr cs:aCinformationno_1+1Fh; "ode"
0x18000fe2a  mov     dword ptr [rbp+0B0h+var_F0+1Fh], eax
0x18000fe2d  lea     rax, [rbp+0B0h+var_F0]
0x18000fe31  mov     [rsp+1B0h+var_170], rax
0x18000fe36  lea     rax, [rsp+1B0h+var_17C]
0x18000fe3b  mov     [rsp+1B0h+var_168], rax
0x18000fe40  lea     rcx, [rsp+1B0h+var_170]
0x18000fe45  call    _lambda_fcd60ded7dc1582d860277ea63697796___operator__
0x18000fe4a  mov     [rsp+1B0h+var_17C], 1
0x18000fe52  lea     rax, [rsp+1B0h+var_170]
0x18000fe57  mov     [rsp+1B0h+var_178], rax
0x18000fe5c  lea     ebx, [rsi+20h]
0x18000fe5f  mov     ecx, ebx; Size
0x18000fe61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fe66  mov     rsi, rax
0x18000fe69  mov     [rsp+1B0h+var_158], rax
0x18000fe6e  test    rax, rax
0x18000fe71  jz      loc_18000FF33
0x18000fe77  lea     rdx, asc_18002447C; "_"
0x18000fe7e  lea     rcx, [rbp+0B0h+var_110]
0x18000fe82  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000fe87  mov     rbx, rax
0x18000fe8a  mov     [rsp+1B0h+var_180], 1
0x18000fe92  mov     r9d, r12d
0x18000fe95  lea     r8, aLu; "%lu"
0x18000fe9c  mov     edx, 40h ; '@'; BufferCount
0x18000fea1  lea     rcx, [rbp+0B0h+Buffer]; Buffer
0x18000fea5  call    cs:__imp_swprintf_s
0x18000feab  lea     rdx, [rbp+0B0h+Buffer]
0x18000feaf  lea     rcx, [rsp+1B0h+var_150]
0x18000feb4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18000feb9  nop
0x18000feba  mov     [rsp+1B0h+var_180], 0Bh
0x18000fec2  mov     rax, [rsp+1B0h+var_138]
0x18000fec7  sub     rax, [rsp+1B0h+var_140]
0x18000fecc  cmp     [rbx+10h], rax
0x18000fed0  jbe     short loc_18000FEF0
0x18000fed2  mov     rax, [rbx+18h]
0x18000fed6  sub     rax, [rbx+10h]
0x18000feda  cmp     rax, [rsp+1B0h+var_140]
0x18000fedf  jb      short loc_18000FEF0
0x18000fee1  lea     r8, [rsp+1B0h+var_150]
0x18000fee6  mov     rcx, rbx
0x18000fee9  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KAEBV12@00@Z; std::wstring::insert(unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x18000feee  jmp     short loc_18000FEFD
0x18000fef0  mov     rdx, rbx
0x18000fef3  lea     rcx, [rsp+1B0h+var_150]
0x18000fef8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000fefd  mov     rdx, rax
0x18000ff00  lea     rcx, [rbp+0B0h+var_130]
0x18000ff04  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000ff09  nop
0x18000ff0a  mov     [rsp+1B0h+var_180], 1Fh
0x18000ff12  mov     rdx, r15
0x18000ff15  lea     rcx, [rbp+0B0h+var_130]
0x18000ff19  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000ff1e  mov     rdx, rax
0x18000ff21  mov     rcx, rsi
0x18000ff24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000ff29  mov     edi, 3Fh ; '?'
0x18000ff2e  lea     ebx, [rdi-1Fh]
0x18000ff31  jmp     short loc_18000FF35
0x18000ff33  xor     esi, esi
0x18000ff35  mov     rdx, rsi
0x18000ff38  mov     rcx, r14
0x18000ff3b  call    ?reset@?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::unique_ptr<std::wstring>::reset(std::wstring *)
0x18000ff40  nop
0x18000ff41  test    dil, 4
0x18000ff45  jz      short loc_18000FF59
0x18000ff47  and     edi, 0FFFFFFFBh
0x18000ff4a  xor     r8d, r8d
0x18000ff4d  mov     dl, 1
0x18000ff4f  lea     rcx, [rbp+0B0h+var_130]
0x18000ff53  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ff58  nop
0x18000ff59  test    dil, 2
0x18000ff5d  jz      short loc_18000FF72
0x18000ff5f  and     edi, 0FFFFFFFDh
0x18000ff62  xor     r8d, r8d
0x18000ff65  mov     dl, 1
0x18000ff67  lea     rcx, [rsp+1B0h+var_150]
0x18000ff6c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ff71  nop
0x18000ff72  test    dil, 1
0x18000ff76  jz      short loc_18000FF86
0x18000ff78  xor     r8d, r8d
0x18000ff7b  mov     dl, 1
0x18000ff7d  lea     rcx, [rbp+0B0h+var_110]
0x18000ff81  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000ff86  mov     rcx, [r14]
0x18000ff89  cmp     qword ptr [rcx+18h], 8
0x18000ff8e  jb      short loc_18000FF95
0x18000ff90  mov     rdx, [rcx]
0x18000ff93  jmp     short loc_18000FF98
0x18000ff95  mov     rdx, rcx
0x18000ff98  mov     rax, [rcx+10h]
0x18000ff9c  lea     r8, [rdx+rax*2]
0x18000ffa0  jb      short loc_18000FFC7
0x18000ffa2  mov     rcx, [rcx]
0x18000ffa5  jmp     short loc_18000FFC7
0x18000ffa7  cmp     [rcx], bx
0x18000ffaa  jbe     short loc_18000FFBE
0x18000ffac  cmp     word ptr [rcx], 2Ch ; ','
0x18000ffb0  jz      short loc_18000FFBE
0x18000ffb2  cmp     word ptr [rcx], 5Ch ; '\'
0x18000ffb6  jz      short loc_18000FFBE
0x18000ffb8  cmp     word ptr [rcx], 7Fh
0x18000ffbc  jbe     short loc_18000FFC3
0x18000ffbe  mov     word ptr [rcx], 5Fh ; '_'
0x18000ffc3  add     rcx, 2
0x18000ffc7  cmp     rcx, r8
0x18000ffca  jnz     short loc_18000FFA7
0x18000ffcc  mov     edx, 2
0x18000ffd1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000ffd6  lea     rax, WPP_GLOBAL_Control
0x18000ffdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ffe4  cmp     rcx, rax
0x18000ffe7  jz      short loc_180010026
0x18000ffe9  test    byte ptr [rcx+1Ch], 1
0x18000ffed  jz      short loc_180010026
0x18000ffef  cmp     byte ptr [rcx+19h], 4
0x18000fff3  jb      short loc_180010026
0x18000fff5  mov     r8, [r14]
0x18000fff8  cmp     qword ptr [r8+18h], 8
0x18000fffd  cmovb   r8, r14
0x180010001  mov     edx, 0Bh
0x180010006  mov     r8, [r8]
0x180010009  mov     [rsp+1B0h+var_190], r8
0x18001000e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180010015  lea     r8, WPP_3eb0defb3f9436b8d8cf87a38eba3e96_Traceguids
0x18001001c  mov     rcx, [rcx+10h]
0x180010020  call    WPP_SF_sS
0x180010025  nop
0x180010026  lea     rcx, [rsp+1B0h+var_178]
0x18001002b  call    WppTraceUnwinder__lambda_fcd60ded7dc1582d860277ea63697796_______WppTraceUnwinder__lambda_fcd60ded7dc1582d860277ea63697796____
0x180010030  nop
0x180010031  mov     rax, r15
0x180010034  mov     rcx, [rbp+0B0h+var_40]
0x180010038  xor     rcx, rsp; StackCookie
0x18001003b  call    __security_check_cookie
0x180010040  add     rsp, 180h
0x180010047  pop     r15
0x180010049  pop     r14
0x18001004b  pop     r12
0x18001004d  pop     rdi
0x18001004e  pop     rsi
0x18001004f  pop     rbx
0x180010050  pop     rbp
0x180010051  retn
```

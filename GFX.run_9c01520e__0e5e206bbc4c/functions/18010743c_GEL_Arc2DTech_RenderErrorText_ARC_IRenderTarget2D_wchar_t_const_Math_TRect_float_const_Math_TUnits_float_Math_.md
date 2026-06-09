# GEL::Arc2DTech::RenderErrorText(ARC::IRenderTarget2D &,wchar_t const *,Math::TRect<float> const &,Math::TUnits<float,Math::Points>)

- ea: `0x18010743c`
- end: `0x18010771c`
- name: `?RenderErrorText@Arc2DTech@GEL@@CAXAEAUIRenderTarget2D@ARC@@PEB_WAEBU?$TRect@M@Math@@V?$TUnits@MUPoints@Math@@@6@@Z`
- size: `736`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180106790`

## callees

- `0x18000a71c`
- `0x18000a788`
- `0x180057e70`
- `0x1800dcec0`
- `0x18010743c`
- `0x18010771c`
- `0x18017cb44`

## import_xrefs

- `mso40uiWin32Client!__imp_?MsoCreateTextFormat@DWriteAssistant@Mso@@YAJAEAUIDWriteFactory@@PEB_WPEAUIDWriteFontCollection@@W4DWRITE_FONT_WEIGHT@@W4DWRITE_FONT_STYLE@@W4DWRITE_FONT_STRETCH@@M1_NPEAPEAUIDWriteTextFormat@@@Z` at `0x1801075d4`
- `mso40uiWin32Client!__imp_?MsoCreateTextFormat@DWriteAssistant@Mso@@YAJAEAUIDWriteFactory@@PEB_WPEAUIDWriteFontCollection@@W4DWRITE_FONT_WEIGHT@@W4DWRITE_FONT_STYLE@@W4DWRITE_FONT_STRETCH@@M1_NPEAPEAUIDWriteTextFormat@@@Z` at `0x1801075d4`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x18010749c`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x18010749c`
- `Mso30Win32Client!__imp_MsoFLidBiDi` at `0x1801075f5`
- `Mso30Win32Client!__imp_MsoFLidBiDi` at `0x1801075f5`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1801075ed`
- `Mso30Win32Client!__imp_MsoGetUILcid` at `0x1801075ed`
- `Mso20Win32Client!__imp_?MsoGetSysColor@@YAKH@Z` at `0x1801074b8`
- `Mso20Win32Client!__imp_?MsoGetSysColor@@YAKH@Z` at `0x1801074b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GEL::Arc2DTech::RenderErrorText(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v8; // r14
  Mso::DWriteAssistant::ResourceManager *Instance; // rax
  struct IDWriteFactory *DWriteFactory; // rbx
  __int64 v11; // rdi
  unsigned int SysColor; // eax
  __int64 v13; // rax
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, bool); // rsi
  unsigned int UILcid; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 result; // rax
  __int64 v25; // [rsp+50h] [rbp-30h]
  __int64 v26; // [rsp+58h] [rbp-28h] BYREF
  float v27[4]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v28; // [rsp+B0h] [rbp+30h] BYREF

  v8 = -1;
  if ( dword_180532558 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180532558);
    if ( dword_180532558 == -1 )
    {
      qword_180532560 = (__int64)GEL::Arc2DTech::GetUIFontName();
      Init_thread_footer(&dword_180532558);
    }
  }
  Instance = (Mso::DWriteAssistant::ResourceManager *)Mso::DWriteAssistant::ResourceManager::GetInstance();
  DWriteFactory = Mso::DWriteAssistant::ResourceManager::GetDWriteFactory(Instance);
  v11 = 0;
  v25 = 0;
  SysColor = MsoGetSysColor(8);
  v27[0] = (float)(unsigned __int8)SysColor / 255.0;
  v27[1] = (float)BYTE1(SysColor) / 255.0;
  v27[2] = (float)BYTE2(SysColor) / 255.0;
  v27[3] = 1.0;
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v14 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v13 + 456LL))(v13, &v26);
  v15 = *v14;
  if ( *v14 )
  {
    *v14 = 0;
    v11 = v15;
    v25 = v15;
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
  v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 360LL))(a1);
  (*(void (__fastcall **)(__int64, __int64, float *))(*(_QWORD *)v16 + 96LL))(v16, v11, v27);
  v28 = 0;
  v17 = Mso::DWriteAssistant::MsoCreateTextFormat(
          DWriteFactory,
          qword_180532560,
          0,
          400,
          0,
          5,
          a4,
          L"x-none",
          1,
          &v28,
          v25);
  if ( v17 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v17, 0x121C3CCu);
    __debugbreak();
  }
  v18 = v28;
  v19 = *(__int64 (__fastcall **)(__int64, bool))(*(_QWORD *)v28 + 24LL);
  UILcid = MsoGetUILcid();
  v21 = MsoFLidBiDi(UILcid);
  v22 = v19(v18, v21 != 0);
  if ( v22 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v22, 0x121C3CDu);
    __debugbreak();
  }
  v23 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 32LL))(v28, 0);
  if ( v23 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v23, 0x121C3CEu);
    __debugbreak();
  }
  do
    ++v8;
  while ( *(_WORD *)(a2 + 2 * v8) );
  result = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int64, __int64, _DWORD, _DWORD))(*(_QWORD *)a1 + 280LL))(
             a1,
             a2,
             (unsigned int)v8,
             v28,
             a3,
             v11,
             0,
             0);
  if ( v28 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v11 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  return result;
}

```

## disassembly

```asm
0x18010743c  mov     rax, rsp
0x18010743f  mov     [rax+10h], rbx
0x180107443  mov     [rax+18h], rsi
0x180107447  mov     [rax+20h], rdi
0x18010744b  push    rbp
0x18010744c  push    r12
0x18010744e  push    r13
0x180107450  push    r14
0x180107452  push    r15
0x180107454  mov     rbp, rsp
0x180107457  sub     rsp, 80h
0x18010745e  movaps  xmmword ptr [rax-38h], xmm6
0x180107462  mov     r13, r8
0x180107465  mov     r12, rdx
0x180107468  mov     r15, rcx
0x18010746b  movd    xmm6, r9d
0x180107470  mov     r9d, cs:_tls_index
0x180107477  mov     rax, gs:58h
0x180107480  mov     ecx, 4
0x180107485  mov     rax, [rax+r9*8]
0x180107489  or      r14, 0FFFFFFFFFFFFFFFFh
0x18010748d  mov     eax, [rcx+rax]
0x180107490  cmp     cs:dword_180532558, eax
0x180107496  jg      loc_1801076BF
0x18010749c  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x1801074a2  mov     rcx, rax; this
0x1801074a5  call    ?GetDWriteFactory@ResourceManager@DWriteAssistant@Mso@@UEAAAEAUIDWriteFactory@@XZ; Mso::DWriteAssistant::ResourceManager::GetDWriteFactory(void)
0x1801074aa  mov     rbx, rax
0x1801074ad  xor     esi, esi
0x1801074af  mov     edi, esi
0x1801074b1  mov     [rbp+var_30], rsi
0x1801074b5  lea     ecx, [rsi+8]
0x1801074b8  call    cs:__imp_?MsoGetSysColor@@YAKH@Z; MsoGetSysColor(int)
0x1801074be  mov     ecx, eax
0x1801074c0  shr     ecx, 10h
0x1801074c3  movzx   ecx, cl
0x1801074c6  movd    xmm3, ecx
0x1801074ca  cvtdq2ps xmm3, xmm3
0x1801074cd  movss   xmm2, cs:__real@437f0000
0x1801074d5  divss   xmm3, xmm2
0x1801074d9  movzx   ecx, ax
0x1801074dc  shr     cx, 8
0x1801074e0  movzx   ecx, cx
0x1801074e3  movd    xmm1, ecx
0x1801074e7  cvtdq2ps xmm1, xmm1
0x1801074ea  divss   xmm1, xmm2
0x1801074ee  movzx   eax, al
0x1801074f1  movd    xmm0, eax
0x1801074f5  cvtdq2ps xmm0, xmm0
0x1801074f8  divss   xmm0, xmm2
0x1801074fc  movss   [rbp+var_20], xmm0
0x180107501  movss   [rbp+var_1C], xmm1
0x180107506  movss   [rbp+var_18], xmm3
0x18010750b  mov     [rbp+var_14], 3F800000h
0x180107512  mov     rax, [r15]
0x180107515  mov     rcx, r15
0x180107518  mov     rax, [rax+18h]
0x18010751c  call    cs:__guard_dispatch_icall_fptr
0x180107522  mov     r8, rax
0x180107525  mov     rcx, [rax]
0x180107528  mov     rax, [rcx+1C8h]
0x18010752f  lea     rdx, [rbp+var_28]
0x180107533  mov     rcx, r8
0x180107536  call    cs:__guard_dispatch_icall_fptr
0x18010753c  mov     rcx, [rax]
0x18010753f  test    rcx, rcx
0x180107542  jz      short loc_18010754E
0x180107544  mov     [rax], rsi
0x180107547  mov     rdi, rcx
0x18010754a  mov     [rbp+var_30], rcx
0x18010754e  mov     rcx, [rbp+var_28]
0x180107552  test    rcx, rcx
0x180107555  jz      short loc_180107564
0x180107557  mov     rax, [rcx]
0x18010755a  mov     rax, [rax+8]
0x18010755e  call    cs:__guard_dispatch_icall_fptr
0x180107564  mov     rax, [r15]
0x180107567  mov     rcx, r15
0x18010756a  mov     rax, [rax+168h]
0x180107571  call    cs:__guard_dispatch_icall_fptr
0x180107577  mov     r9, rax
0x18010757a  mov     rcx, [rax]
0x18010757d  mov     rax, [rcx+60h]
0x180107581  lea     r8, [rbp+var_20]
0x180107585  mov     rdx, rdi
0x180107588  mov     rcx, r9
0x18010758b  call    cs:__guard_dispatch_icall_fptr
0x180107591  mov     [rbp+arg_0], rsi
0x180107595  lea     rax, [rbp+arg_0]
0x180107599  mov     [rsp+80h+var_38], rax
0x18010759e  mov     [rsp+80h+var_40], 1
0x1801075a3  lea     rax, aXNone; "x-none"
0x1801075aa  mov     [rsp+80h+var_48], rax
0x1801075af  movss   [rsp+80h+var_50], xmm6
0x1801075b5  mov     dword ptr [rsp+80h+var_58], 5
0x1801075bd  mov     dword ptr [rsp+80h+var_60], esi
0x1801075c1  mov     r9d, 190h
0x1801075c7  xor     r8d, r8d
0x1801075ca  mov     rdx, cs:qword_180532560
0x1801075d1  mov     rcx, rbx
0x1801075d4  call    cs:__imp_?MsoCreateTextFormat@DWriteAssistant@Mso@@YAJAEAUIDWriteFactory@@PEB_WPEAUIDWriteFontCollection@@W4DWRITE_FONT_WEIGHT@@W4DWRITE_FONT_STYLE@@W4DWRITE_FONT_STRETCH@@M1_NPEAPEAUIDWriteTextFormat@@@Z; Mso::DWriteAssistant::MsoCreateTextFormat(IDWriteFactory &,wchar_t const *,IDWriteFontCollection *,DWRITE_FONT_WEIGHT,DWRITE_FONT_STYLE,DWRITE_FONT_STRETCH,float,wchar_t const *,bool,IDWriteTextFormat * *)
0x1801075da  test    eax, eax
0x1801075dc  js      loc_1801076F5
0x1801075e2  mov     rbx, [rbp+arg_0]
0x1801075e6  mov     rax, [rbx]
0x1801075e9  mov     rsi, [rax+18h]
0x1801075ed  call    cs:__imp_MsoGetUILcid
0x1801075f3  mov     ecx, eax
0x1801075f5  call    cs:__imp_MsoFLidBiDi
0x1801075fb  xor     edx, edx
0x1801075fd  test    eax, eax
0x1801075ff  setnz   dl
0x180107602  mov     rcx, rbx
0x180107605  mov     rax, rsi
0x180107608  call    cs:__guard_dispatch_icall_fptr
0x18010760e  xor     ebx, ebx
0x180107610  test    eax, eax
0x180107612  js      loc_180107702
0x180107618  mov     rcx, [rbp+arg_0]
0x18010761c  mov     rax, [rcx]
0x18010761f  xor     edx, edx
0x180107621  mov     rax, [rax+20h]
0x180107625  call    cs:__guard_dispatch_icall_fptr
0x18010762b  test    eax, eax
0x18010762d  js      loc_18010770F
0x180107633  mov     rax, [r15]
0x180107636  inc     r14
0x180107639  cmp     [r12+r14*2], bx
0x18010763e  jnz     short loc_180107636
0x180107640  mov     dword ptr [rsp+80h+var_48], ebx
0x180107644  mov     [rsp+80h+var_50], ebx
0x180107648  mov     [rsp+80h+var_58], rdi
0x18010764d  mov     [rsp+80h+var_60], r13
0x180107652  mov     r9, [rbp+arg_0]
0x180107656  mov     r8d, r14d
0x180107659  mov     rdx, r12
0x18010765c  mov     rcx, r15
0x18010765f  mov     rax, [rax+118h]
0x180107666  call    cs:__guard_dispatch_icall_fptr
0x18010766c  nop
0x18010766d  mov     rcx, [rbp+arg_0]
0x180107671  test    rcx, rcx
0x180107674  jz      short loc_180107684
0x180107676  mov     rax, [rcx]
0x180107679  mov     rax, [rax+10h]
0x18010767d  call    cs:__guard_dispatch_icall_fptr
0x180107683  nop
0x180107684  test    rdi, rdi
0x180107687  jz      short loc_180107699
0x180107689  mov     rax, [rdi]
0x18010768c  mov     rcx, rdi
0x18010768f  mov     rax, [rax+8]
0x180107693  call    cs:__guard_dispatch_icall_fptr
0x180107699  lea     r11, [rsp+80h+var_s0]
0x1801076a1  mov     rbx, [r11+38h]
0x1801076a5  mov     rsi, [r11+40h]
0x1801076a9  mov     rdi, [r11+48h]
0x1801076ad  movaps  xmm6, [rsp+80h+var_10]
0x1801076b2  mov     rsp, r11
0x1801076b5  pop     r15
0x1801076b7  pop     r14
0x1801076b9  pop     r13
0x1801076bb  pop     r12
0x1801076bd  pop     rbp
0x1801076be  retn
0x1801076bf  lea     rcx, dword_180532558
0x1801076c6  call    _Init_thread_header
0x1801076cb  cmp     cs:dword_180532558, r14d
0x1801076d2  jnz     loc_18010749C
0x1801076d8  call    ?GetUIFontName@Arc2DTech@GEL@@CAPEB_WXZ; GEL::Arc2DTech::GetUIFontName(void)
0x1801076dd  mov     cs:qword_180532560, rax
0x1801076e4  lea     rcx, dword_180532558
0x1801076eb  call    _Init_thread_footer
0x1801076f0  jmp     loc_18010749C
0x1801076f5  mov     edx, 121C3CCh; unsigned int
0x1801076fa  mov     ecx, eax; int
0x1801076fc  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180107701  int     3; Trap to Debugger
0x180107702  mov     edx, 121C3CDh; unsigned int
0x180107707  mov     ecx, eax; int
0x180107709  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18010770e  int     3; Trap to Debugger
0x18010770f  mov     edx, 121C3CEh; unsigned int
0x180107714  mov     ecx, eax; int
0x180107716  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18010771b  int     3; Trap to Debugger
```

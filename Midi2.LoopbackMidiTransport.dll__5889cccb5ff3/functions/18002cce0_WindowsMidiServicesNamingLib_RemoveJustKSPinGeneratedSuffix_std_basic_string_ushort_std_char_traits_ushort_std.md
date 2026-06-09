# WindowsMidiServicesNamingLib::RemoveJustKSPinGeneratedSuffix(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002cce0`
- end: `0x18002d3f8`
- name: `?RemoveJustKSPinGeneratedSuffix@WindowsMidiServicesNamingLib@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `1816`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18002c0e0`

## callees

- `0x180004180`
- `0x180004214`
- `0x18000b740`
- `0x18000e178`
- `0x18000f0a4`
- `0x18000feb0`
- `0x1800134cc`
- `0x180014ab8`
- `0x18002cce0`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
void *__fastcall WindowsMidiServicesNamingLib::RemoveJustKSPinGeneratedSuffix(void *Src, __int64 a2)
{
  int v3; // edi
  void *v4; // rax
  wchar_t *v5; // rbx
  const wchar_t *v6; // rdx
  size_t v7; // r8
  const wchar_t *v8; // rcx
  _QWORD *v9; // rdx
  void *v10; // rax
  _BYTE v12[32]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD Srca[2]; // [rsp+58h] [rbp-A8h] BYREF
  size_t v14; // [rsp+68h] [rbp-98h]
  unsigned __int64 v15; // [rsp+70h] [rbp-90h]
  _OWORD v16[2]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t S2[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v18; // [rsp+B0h] [rbp-50h]
  _OWORD v19[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v20[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v21[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v22[2]; // [rsp+120h] [rbp+20h] BYREF
  _OWORD v23[2]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v24[2]; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v25[2]; // [rsp+180h] [rbp+80h] BYREF
  _OWORD v26[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v27[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _OWORD v28[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  _OWORD v29[2]; // [rsp+200h] [rbp+100h] BYREF
  _OWORD v30[2]; // [rsp+220h] [rbp+120h] BYREF
  _OWORD v31[2]; // [rsp+240h] [rbp+140h] BYREF
  _OWORD v32[2]; // [rsp+260h] [rbp+160h] BYREF
  _OWORD v33[2]; // [rsp+280h] [rbp+180h] BYREF
  _OWORD v34[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _OWORD v35[2]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _OWORD v36[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _OWORD v37[2]; // [rsp+300h] [rbp+200h] BYREF
  _OWORD v38[2]; // [rsp+320h] [rbp+220h] BYREF
  _OWORD v39[2]; // [rsp+340h] [rbp+240h] BYREF
  _OWORD v40[2]; // [rsp+360h] [rbp+260h] BYREF
  _OWORD v41[2]; // [rsp+380h] [rbp+280h] BYREF
  _OWORD v42[2]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _OWORD v43[2]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _OWORD v44[2]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _OWORD v45[2]; // [rsp+400h] [rbp+300h] BYREF
  _OWORD v46[2]; // [rsp+420h] [rbp+320h] BYREF
  _OWORD v47[2]; // [rsp+440h] [rbp+340h] BYREF
  _OWORD v48[2]; // [rsp+460h] [rbp+360h] BYREF
  _OWORD v49[2]; // [rsp+480h] [rbp+380h] BYREF
  _OWORD v50[2]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _OWORD v51[2]; // [rsp+4C0h] [rbp+3C0h] BYREF
  __int64 v52; // [rsp+4E0h] [rbp+3E0h] BYREF

  v3 = 0;
  v4 = (void *)std::wstring::wstring(v12, a2);
  WindowsMidiServicesInternal::TrimmedWStringCopy(Srca, v4);
  *(_OWORD *)S2 = 0;
  v18 = 0;
  std::wstring::_Construct<1,unsigned short const *>(S2, L"[0]");
  memset(v19, 0, sizeof(v19));
  std::wstring::_Construct<1,unsigned short const *>(v19, L"[1]");
  memset(v20, 0, sizeof(v20));
  std::wstring::_Construct<1,unsigned short const *>(v20, L"[2]");
  memset(v21, 0, sizeof(v21));
  std::wstring::_Construct<1,unsigned short const *>(v21, L"[3]");
  memset(v22, 0, sizeof(v22));
  std::wstring::_Construct<1,unsigned short const *>(v22, L"[4]");
  memset(v23, 0, sizeof(v23));
  std::wstring::_Construct<1,unsigned short const *>(v23, L"[5]");
  memset(v24, 0, sizeof(v24));
  std::wstring::_Construct<1,unsigned short const *>(v24, L"[6]");
  memset(v25, 0, sizeof(v25));
  std::wstring::_Construct<1,unsigned short const *>(v25, L"[7]");
  memset(v26, 0, sizeof(v26));
  std::wstring::_Construct<1,unsigned short const *>(v26, L"[8]");
  memset(v27, 0, sizeof(v27));
  std::wstring::_Construct<1,unsigned short const *>(v27, L"[9]");
  memset(v28, 0, sizeof(v28));
  std::wstring::_Construct<1,unsigned short const *>(v28, L"[10]");
  memset(v29, 0, sizeof(v29));
  std::wstring::_Construct<1,unsigned short const *>(v29, L"[11]");
  memset(v30, 0, sizeof(v30));
  std::wstring::_Construct<1,unsigned short const *>(v30, L"[12]");
  memset(v31, 0, sizeof(v31));
  std::wstring::_Construct<1,unsigned short const *>(v31, L"[13]");
  memset(v32, 0, sizeof(v32));
  std::wstring::_Construct<1,unsigned short const *>(v32, L"[14]");
  memset(v33, 0, sizeof(v33));
  std::wstring::_Construct<1,unsigned short const *>(v33, L"[15]");
  memset(v34, 0, sizeof(v34));
  std::wstring::_Construct<1,unsigned short const *>(v34, L"[16]");
  memset(v35, 0, sizeof(v35));
  std::wstring::_Construct<1,unsigned short const *>(v35, L"[17]");
  memset(v36, 0, sizeof(v36));
  std::wstring::_Construct<1,unsigned short const *>(v36, L"[18]");
  memset(v37, 0, sizeof(v37));
  std::wstring::_Construct<1,unsigned short const *>(v37, L"[19]");
  memset(v38, 0, sizeof(v38));
  std::wstring::_Construct<1,unsigned short const *>(v38, L"[20]");
  memset(v39, 0, sizeof(v39));
  std::wstring::_Construct<1,unsigned short const *>(v39, L"[21]");
  memset(v40, 0, sizeof(v40));
  std::wstring::_Construct<1,unsigned short const *>(v40, L"[22]");
  memset(v41, 0, sizeof(v41));
  std::wstring::_Construct<1,unsigned short const *>(v41, L"[23]");
  memset(v42, 0, sizeof(v42));
  std::wstring::_Construct<1,unsigned short const *>(v42, L"[24]");
  memset(v43, 0, sizeof(v43));
  std::wstring::_Construct<1,unsigned short const *>(v43, L"[25]");
  memset(v44, 0, sizeof(v44));
  std::wstring::_Construct<1,unsigned short const *>(v44, L"[26]");
  memset(v45, 0, sizeof(v45));
  std::wstring::_Construct<1,unsigned short const *>(v45, L"[27]");
  memset(v46, 0, sizeof(v46));
  std::wstring::_Construct<1,unsigned short const *>(v46, L"[28]");
  memset(v47, 0, sizeof(v47));
  std::wstring::_Construct<1,unsigned short const *>(v47, L"[29]");
  memset(v48, 0, sizeof(v48));
  std::wstring::_Construct<1,unsigned short const *>(v48, L"[30]");
  memset(v49, 0, sizeof(v49));
  std::wstring::_Construct<1,unsigned short const *>(v49, L"[31]");
  memset(v50, 0, sizeof(v50));
  std::wstring::_Construct<1,unsigned short const *>(v50, L"[32]");
  memset(v51, 0, sizeof(v51));
  std::wstring::_Construct<1,unsigned short const *>(v51, L"[:]");
  v5 = S2;
  do
  {
    if ( *((_QWORD *)v5 + 3) <= 7u )
      v6 = v5;
    else
      v6 = *(const wchar_t **)v5;
    v7 = *((_QWORD *)v5 + 2);
    v8 = (const wchar_t *)Srca;
    if ( v15 > 7 )
      v8 = (const wchar_t *)Srca[0];
    if ( v14 >= v7 && !wmemcmp(&v8[v14 - v7], v6, v7) )
    {
      memset(v16, 0, sizeof(v16));
      v9 = Srca;
      if ( v15 > 7 )
        v9 = (_QWORD *)Srca[0];
      std::wstring::_Construct<1,unsigned short const *>(v16, v9);
      v3 |= 2u;
      std::wstring::operator=(Srca, v16);
      std::wstring::~wstring(v16);
    }
    v5 += 16;
  }
  while ( v5 != (wchar_t *)&v52 );
  v10 = (void *)std::wstring::wstring(v16, Srca);
  WindowsMidiServicesInternal::TrimmedWStringCopy(Src, v10);
  `eh vector destructor iterator'(S2, 0x20u, 0x22u, std::wstring::~wstring);
  std::wstring::~wstring(Srca);
  return Src;
}

```

## disassembly

```asm
0x18002cce0  mov     [rsp-8+arg_10], rbx
0x18002cce5  mov     [rsp-8+arg_18], rsi
0x18002ccea  push    rbp
0x18002cceb  push    rdi
0x18002ccec  push    r14
0x18002ccee  lea     rbp, [rsp-3F0h]
0x18002ccf6  sub     rsp, 4F0h
0x18002ccfd  mov     rax, cs:__security_cookie
0x18002cd04  xor     rax, rsp
0x18002cd07  mov     [rbp+400h+var_20], rax
0x18002cd0e  mov     rsi, rcx
0x18002cd11  mov     [rsp+500h+var_4D0], rcx
0x18002cd16  xor     edi, edi
0x18002cd18  mov     [rsp+500h+var_4E0], edi
0x18002cd1c  lea     rcx, [rsp+500h+var_4C8]
0x18002cd21  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cd26  mov     rdx, rax; void *
0x18002cd29  lea     rcx, [rsp+500h+Src]; Src
0x18002cd2e  call    ?TrimmedWStringCopy@WindowsMidiServicesInternal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@@Z; WindowsMidiServicesInternal::TrimmedWStringCopy(std::wstring)
0x18002cd33  nop
0x18002cd34  xorps   xmm0, xmm0
0x18002cd37  movups  xmmword ptr [rbp+400h+S2], xmm0
0x18002cd3b  xorps   xmm1, xmm1
0x18002cd3e  movdqa  [rbp+400h+var_450], xmm1
0x18002cd43  lea     r14d, [rdi+3]
0x18002cd47  mov     r8d, r14d
0x18002cd4a  lea     rdx, a0_0; "[0]"
0x18002cd51  lea     rcx, [rbp+400h+S2]
0x18002cd55  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cd5a  nop
0x18002cd5b  xorps   xmm0, xmm0
0x18002cd5e  movups  [rbp+400h+var_440], xmm0
0x18002cd62  xorps   xmm1, xmm1
0x18002cd65  movdqa  [rbp+400h+var_430], xmm1
0x18002cd6a  mov     r8d, r14d
0x18002cd6d  lea     rdx, a1; "[1]"
0x18002cd74  lea     rcx, [rbp+400h+var_440]
0x18002cd78  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cd7d  nop
0x18002cd7e  xorps   xmm0, xmm0
0x18002cd81  movups  [rbp+400h+var_420], xmm0
0x18002cd85  xorps   xmm1, xmm1
0x18002cd88  movdqa  [rbp+400h+var_410], xmm1
0x18002cd8d  mov     r8d, r14d
0x18002cd90  lea     rdx, a2; "[2]"
0x18002cd97  lea     rcx, [rbp+400h+var_420]
0x18002cd9b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cda0  nop
0x18002cda1  xorps   xmm0, xmm0
0x18002cda4  movups  [rbp+400h+var_400], xmm0
0x18002cda8  xorps   xmm1, xmm1
0x18002cdab  movdqa  [rbp+400h+var_3F0], xmm1
0x18002cdb0  mov     r8d, r14d
0x18002cdb3  lea     rdx, a3; "[3]"
0x18002cdba  lea     rcx, [rbp+400h+var_400]
0x18002cdbe  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cdc3  nop
0x18002cdc4  xorps   xmm0, xmm0
0x18002cdc7  movups  [rbp+400h+var_3E0], xmm0
0x18002cdcb  xorps   xmm1, xmm1
0x18002cdce  movdqa  [rbp+400h+var_3D0], xmm1
0x18002cdd3  mov     r8d, r14d
0x18002cdd6  lea     rdx, a4; "[4]"
0x18002cddd  lea     rcx, [rbp+400h+var_3E0]
0x18002cde1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cde6  nop
0x18002cde7  xorps   xmm0, xmm0
0x18002cdea  movups  [rbp+400h+var_3C0], xmm0
0x18002cdee  xorps   xmm1, xmm1
0x18002cdf1  movdqa  [rbp+400h+var_3B0], xmm1
0x18002cdf6  mov     r8d, r14d
0x18002cdf9  lea     rdx, a5; "[5]"
0x18002ce00  lea     rcx, [rbp+400h+var_3C0]
0x18002ce04  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002ce09  nop
0x18002ce0a  xorps   xmm0, xmm0
0x18002ce0d  movups  [rbp+400h+var_3A0], xmm0
0x18002ce11  xorps   xmm1, xmm1
0x18002ce14  movdqa  [rbp+400h+var_390], xmm1
0x18002ce19  mov     r8d, r14d
0x18002ce1c  lea     rdx, a6; "[6]"
0x18002ce23  lea     rcx, [rbp+400h+var_3A0]
0x18002ce27  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002ce2c  nop
0x18002ce2d  xorps   xmm0, xmm0
0x18002ce30  movups  [rbp+400h+var_380], xmm0
0x18002ce37  xorps   xmm1, xmm1
0x18002ce3a  movdqa  [rbp+400h+var_370], xmm1
0x18002ce42  mov     r8d, r14d
0x18002ce45  lea     rdx, a7; "[7]"
0x18002ce4c  lea     rcx, [rbp+400h+var_380]
0x18002ce53  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002ce58  nop
0x18002ce59  xorps   xmm0, xmm0
0x18002ce5c  movups  [rbp+400h+var_360], xmm0
0x18002ce63  xorps   xmm1, xmm1
0x18002ce66  movdqa  [rbp+400h+var_350], xmm1
0x18002ce6e  mov     r8d, r14d
0x18002ce71  lea     rdx, a8; "[8]"
0x18002ce78  lea     rcx, [rbp+400h+var_360]
0x18002ce7f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002ce84  nop
0x18002ce85  xorps   xmm0, xmm0
0x18002ce88  movups  [rbp+400h+var_340], xmm0
0x18002ce8f  xorps   xmm1, xmm1
0x18002ce92  movdqa  [rbp+400h+var_330], xmm1
0x18002ce9a  mov     r8d, r14d
0x18002ce9d  lea     rdx, a9; "[9]"
0x18002cea4  lea     rcx, [rbp+400h+var_340]
0x18002ceab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002ceb0  nop
0x18002ceb1  xorps   xmm0, xmm0
0x18002ceb4  movups  [rbp+400h+var_320], xmm0
0x18002cebb  xorps   xmm1, xmm1
0x18002cebe  movdqa  [rbp+400h+var_310], xmm1
0x18002cec6  lea     ebx, [rdi+4]
0x18002cec9  mov     r8d, ebx
0x18002cecc  lea     rdx, a10; "[10]"
0x18002ced3  lea     rcx, [rbp+400h+var_320]
0x18002ceda  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cedf  nop
0x18002cee0  xorps   xmm0, xmm0
0x18002cee3  movups  [rbp+400h+var_300], xmm0
0x18002ceea  xorps   xmm1, xmm1
0x18002ceed  movdqa  [rbp+400h+var_2F0], xmm1
0x18002cef5  mov     r8d, ebx
0x18002cef8  lea     rdx, a11; "[11]"
0x18002ceff  lea     rcx, [rbp+400h+var_300]
0x18002cf06  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cf0b  nop
0x18002cf0c  xorps   xmm0, xmm0
0x18002cf0f  movups  [rbp+400h+var_2E0], xmm0
0x18002cf16  xorps   xmm1, xmm1
0x18002cf19  movdqa  [rbp+400h+var_2D0], xmm1
0x18002cf21  mov     r8d, ebx
0x18002cf24  lea     rdx, a12; "[12]"
0x18002cf2b  lea     rcx, [rbp+400h+var_2E0]
0x18002cf32  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cf37  nop
0x18002cf38  xorps   xmm0, xmm0
0x18002cf3b  movups  [rbp+400h+var_2C0], xmm0
0x18002cf42  xorps   xmm1, xmm1
0x18002cf45  movdqa  [rbp+400h+var_2B0], xmm1
0x18002cf4d  mov     r8d, ebx
0x18002cf50  lea     rdx, a13; "[13]"
0x18002cf57  lea     rcx, [rbp+400h+var_2C0]
0x18002cf5e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cf63  nop
0x18002cf64  xorps   xmm0, xmm0
0x18002cf67  movups  [rbp+400h+var_2A0], xmm0
0x18002cf6e  xorps   xmm1, xmm1
0x18002cf71  movdqa  [rbp+400h+var_290], xmm1
0x18002cf79  mov     r8d, ebx
0x18002cf7c  lea     rdx, a14; "[14]"
0x18002cf83  lea     rcx, [rbp+400h+var_2A0]
0x18002cf8a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cf8f  nop
0x18002cf90  xorps   xmm0, xmm0
0x18002cf93  movups  [rbp+400h+var_280], xmm0
0x18002cf9a  xorps   xmm1, xmm1
0x18002cf9d  movdqa  [rbp+400h+var_270], xmm1
0x18002cfa5  mov     r8d, ebx
0x18002cfa8  lea     rdx, a15; "[15]"
0x18002cfaf  lea     rcx, [rbp+400h+var_280]
0x18002cfb6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cfbb  nop
0x18002cfbc  xorps   xmm0, xmm0
0x18002cfbf  movups  [rbp+400h+var_260], xmm0
0x18002cfc6  xorps   xmm1, xmm1
0x18002cfc9  movdqa  [rbp+400h+var_250], xmm1
0x18002cfd1  mov     r8d, ebx
0x18002cfd4  lea     rdx, a16; "[16]"
0x18002cfdb  lea     rcx, [rbp+400h+var_260]
0x18002cfe2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002cfe7  nop
0x18002cfe8  xorps   xmm0, xmm0
0x18002cfeb  movups  [rbp+400h+var_240], xmm0
0x18002cff2  xorps   xmm1, xmm1
0x18002cff5  movdqa  [rbp+400h+var_230], xmm1
0x18002cffd  mov     r8d, ebx
0x18002d000  lea     rdx, a17; "[17]"
0x18002d007  lea     rcx, [rbp+400h+var_240]
0x18002d00e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d013  nop
0x18002d014  xorps   xmm0, xmm0
0x18002d017  movups  [rbp+400h+var_220], xmm0
0x18002d01e  xorps   xmm1, xmm1
0x18002d021  movdqa  [rbp+400h+var_210], xmm1
0x18002d029  mov     r8d, ebx
0x18002d02c  lea     rdx, a18; "[18]"
0x18002d033  lea     rcx, [rbp+400h+var_220]
0x18002d03a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d03f  nop
0x18002d040  xorps   xmm0, xmm0
0x18002d043  movups  [rbp+400h+var_200], xmm0
0x18002d04a  xorps   xmm1, xmm1
0x18002d04d  movdqa  [rbp+400h+var_1F0], xmm1
0x18002d055  mov     r8d, ebx
0x18002d058  lea     rdx, a19; "[19]"
0x18002d05f  lea     rcx, [rbp+400h+var_200]
0x18002d066  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d06b  nop
0x18002d06c  xorps   xmm0, xmm0
0x18002d06f  movups  [rbp+400h+var_1E0], xmm0
0x18002d076  xorps   xmm1, xmm1
0x18002d079  movdqa  [rbp+400h+var_1D0], xmm1
0x18002d081  mov     r8d, ebx
0x18002d084  lea     rdx, a20; "[20]"
0x18002d08b  lea     rcx, [rbp+400h+var_1E0]
0x18002d092  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d097  nop
0x18002d098  xorps   xmm0, xmm0
0x18002d09b  movups  [rbp+400h+var_1C0], xmm0
0x18002d0a2  xorps   xmm1, xmm1
0x18002d0a5  movdqa  [rbp+400h+var_1B0], xmm1
0x18002d0ad  mov     r8d, ebx
0x18002d0b0  lea     rdx, a21; "[21]"
0x18002d0b7  lea     rcx, [rbp+400h+var_1C0]
0x18002d0be  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d0c3  nop
0x18002d0c4  xorps   xmm0, xmm0
0x18002d0c7  movups  [rbp+400h+var_1A0], xmm0
0x18002d0ce  xorps   xmm1, xmm1
0x18002d0d1  movdqa  [rbp+400h+var_190], xmm1
0x18002d0d9  mov     r8d, ebx
0x18002d0dc  lea     rdx, a22; "[22]"
0x18002d0e3  lea     rcx, [rbp+400h+var_1A0]
0x18002d0ea  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d0ef  nop
0x18002d0f0  xorps   xmm0, xmm0
0x18002d0f3  movups  [rbp+400h+var_180], xmm0
0x18002d0fa  xorps   xmm1, xmm1
0x18002d0fd  movdqa  [rbp+400h+var_170], xmm1
0x18002d105  mov     r8d, ebx
0x18002d108  lea     rdx, a23; "[23]"
0x18002d10f  lea     rcx, [rbp+400h+var_180]
0x18002d116  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d11b  nop
0x18002d11c  xorps   xmm0, xmm0
0x18002d11f  movups  [rbp+400h+var_160], xmm0
0x18002d126  xorps   xmm1, xmm1
0x18002d129  movdqa  [rbp+400h+var_150], xmm1
0x18002d131  mov     r8d, ebx
0x18002d134  lea     rdx, a24; "[24]"
0x18002d13b  lea     rcx, [rbp+400h+var_160]
0x18002d142  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d147  nop
0x18002d148  xorps   xmm0, xmm0
0x18002d14b  movups  [rbp+400h+var_140], xmm0
0x18002d152  xorps   xmm1, xmm1
0x18002d155  movdqa  [rbp+400h+var_130], xmm1
0x18002d15d  mov     r8d, ebx
0x18002d160  lea     rdx, a25; "[25]"
0x18002d167  lea     rcx, [rbp+400h+var_140]
0x18002d16e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d173  nop
0x18002d174  xorps   xmm0, xmm0
0x18002d177  movups  [rbp+400h+var_120], xmm0
0x18002d17e  xorps   xmm1, xmm1
0x18002d181  movdqa  [rbp+400h+var_110], xmm1
0x18002d189  mov     r8d, ebx
0x18002d18c  lea     rdx, a26; "[26]"
0x18002d193  lea     rcx, [rbp+400h+var_120]
0x18002d19a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d19f  nop
0x18002d1a0  xorps   xmm0, xmm0
0x18002d1a3  movups  [rbp+400h+var_100], xmm0
0x18002d1aa  xorps   xmm1, xmm1
0x18002d1ad  movdqa  [rbp+400h+var_F0], xmm1
0x18002d1b5  mov     r8d, ebx
0x18002d1b8  lea     rdx, a27; "[27]"
0x18002d1bf  lea     rcx, [rbp+400h+var_100]
0x18002d1c6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d1cb  nop
0x18002d1cc  xorps   xmm0, xmm0
0x18002d1cf  movups  [rbp+400h+var_E0], xmm0
0x18002d1d6  xorps   xmm1, xmm1
0x18002d1d9  movdqa  [rbp+400h+var_D0], xmm1
0x18002d1e1  mov     r8d, ebx
0x18002d1e4  lea     rdx, a28; "[28]"
0x18002d1eb  lea     rcx, [rbp+400h+var_E0]
0x18002d1f2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d1f7  nop
0x18002d1f8  xorps   xmm0, xmm0
0x18002d1fb  movups  [rbp+400h+var_C0], xmm0
0x18002d202  xorps   xmm1, xmm1
0x18002d205  movdqa  [rbp+400h+var_B0], xmm1
0x18002d20d  mov     r8d, ebx
0x18002d210  lea     rdx, a29; "[29]"
0x18002d217  lea     rcx, [rbp+400h+var_C0]
0x18002d21e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d223  nop
0x18002d224  xorps   xmm0, xmm0
0x18002d227  movups  [rbp+400h+var_A0], xmm0
0x18002d22e  xorps   xmm1, xmm1
0x18002d231  movdqa  [rbp+400h+var_90], xmm1
0x18002d239  mov     r8d, ebx
0x18002d23c  lea     rdx, a30; "[30]"
0x18002d243  lea     rcx, [rbp+400h+var_A0]
0x18002d24a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
  ... truncated ...
```

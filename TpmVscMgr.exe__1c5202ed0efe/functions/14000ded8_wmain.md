# wmain

- ea: `0x14000ded8`
- end: `0x14000e4c2`
- name: `wmain`
- size: `1514`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x1400014e0`

## callees

- `0x1400016a0`
- `0x1400022fa`
- `0x140005e68`
- `0x140008454`
- `0x140008784`
- `0x140009434`
- `0x140009dd8`
- `0x14000cf20`
- `0x14000d5a8`
- `0x14000d858`
- `0x14000d974`
- `0x14000dab8`
- `0x14000db60`
- `0x14000dbfc`
- `0x14000dd80`
- `0x14000ddbc`
- `0x14000ded8`
- `0x14000f280`
- `0x140010c90`

## import_xrefs

- `ADVAPI32!EventSetInformation` at `0x14000df87`
- `ADVAPI32!EventSetInformation` at `0x14000df87`
- `ADVAPI32!EventRegister` at `0x14000df64`
- `ADVAPI32!EventRegister` at `0x14000df64`
- `KERNEL32!HeapSetInformation` at `0x14000df12`
- `KERNEL32!HeapSetInformation` at `0x14000df12`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x14000dff4`
- `KERNEL32!SetThreadPreferredUILanguages` at `0x14000dff4`
- `api-ms-win-crt-private-l1-1-0!_o__fileno` at `0x14000dfa1`
- `api-ms-win-crt-private-l1-1-0!_o__fileno` at `0x14000dfc0`
- `api-ms-win-crt-private-l1-1-0!_o__fileno` at `0x14000dfda`
- `api-ms-win-crt-private-l1-1-0!_o__fileno` at `0x14000dfa1`
- `api-ms-win-crt-private-l1-1-0!_o__fileno` at `0x14000dfc0`
- `api-ms-win-crt-private-l1-1-0!_o__fileno` at `0x14000dfda`
- `api-ms-win-crt-private-l1-1-0!_o__setmode` at `0x14000dfb0`
- `api-ms-win-crt-private-l1-1-0!_o__setmode` at `0x14000dfca`
- `api-ms-win-crt-private-l1-1-0!_o__setmode` at `0x14000dfe4`
- `api-ms-win-crt-private-l1-1-0!_o__setmode` at `0x14000dfb0`
- `api-ms-win-crt-private-l1-1-0!_o__setmode` at `0x14000dfca`
- `api-ms-win-crt-private-l1-1-0!_o__setmode` at `0x14000dfe4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000e323`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000e323`

## pseudocode

```c
__int64 __fastcall wmain(int a1, __int64 a2)
{
  unsigned __int64 v3; // r14
  FILE *v4; // rax
  int v5; // eax
  FILE *v6; // rax
  int v7; // eax
  FILE *v8; // rax
  int v9; // eax
  Output *v10; // rcx
  unsigned __int64 i; // rsi
  _WORD *v12; // rax
  _WORD *v13; // rax
  Output *v14; // rcx
  Output *v16; // rcx
  unsigned int v17; // edx
  char v18; // [rsp+20h] [rbp-1E8h] BYREF
  __int16 v19; // [rsp+21h] [rbp-1E7h]
  _DWORD v20[3]; // [rsp+24h] [rbp-1E4h] BYREF
  __int128 v21; // [rsp+30h] [rbp-1D8h] BYREF
  __int64 v22; // [rsp+40h] [rbp-1C8h]
  int v23[10]; // [rsp+48h] [rbp-1C0h] BYREF
  _BYTE v24[8]; // [rsp+70h] [rbp-198h] BYREF
  __int64 v25[4]; // [rsp+78h] [rbp-190h] BYREF
  char v26; // [rsp+98h] [rbp-170h]
  int v27; // [rsp+168h] [rbp-A0h]
  char v28; // [rsp+170h] [rbp-98h] BYREF
  _QWORD v29[4]; // [rsp+178h] [rbp-90h] BYREF
  char v30; // [rsp+198h] [rbp-70h]
  _QWORD *v31; // [rsp+1A0h] [rbp-68h]
  GUID ProviderId; // [rsp+1B0h] [rbp-58h] BYREF
  _QWORD v33[3]; // [rsp+1C0h] [rbp-48h] BYREF
  unsigned __int64 v34; // [rsp+1D8h] [rbp-30h]

  v3 = a1;
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  ProviderId = *(GUID *)&(*off_14001A008)[-16];
  if ( RegHandle )
    __fastfail(5u);
  xmmword_14001A028 = 0;
  if ( !EventRegister(&ProviderId, (PENABLECALLBACK)tlgEnableCallback, &dword_14001A000, &RegHandle) )
    EventSetInformation(RegHandle, 2, (char *)off_14001A008, *(unsigned __int16 *)off_14001A008);
  v19 = 256;
  v4 = o___acrt_iob_func_0(1u);
  v5 = _o__fileno(v4);
  _setmode(v5, 0x20000);
  v6 = o___acrt_iob_func_0(2u);
  v7 = _o__fileno(v6);
  _setmode(v7, 0x20000);
  v8 = o___acrt_iob_func_0(0);
  v9 = _o__fileno(v8);
  _setmode(v9, 0x20000);
  SetThreadPreferredUILanguages(0x100u, 0, 0);
  v24[0] = 0;
  v27 = 2;
  v28 = 0;
  v30 = 0;
  v31 = v29;
  if ( (_DWORD)v3 == 1 )
  {
    Output::DisplayErrorResource(v10, 0x193u);
    if ( v30 )
    {
      v30 = 0;
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v29);
    }
    goto LABEL_28;
  }
  v21 = 0;
  v22 = 0;
  for ( i = 1; i < v3; ++i )
  {
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
      v33,
      *(_WORD **)(a2 + 8 * i));
    v12 = v33;
    if ( v34 > 7 )
      v12 = (_WORD *)v33[0];
    if ( *v12 == 45 )
    {
      v13 = v33;
      if ( v34 > 7 )
        v13 = (_WORD *)v33[0];
      *v13 = 47;
    }
    if ( *((_QWORD *)&v21 + 1) == v22 )
    {
      std::vector<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>::_Emplace_reallocate<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>> const &>(
        &v21,
        *((_QWORD *)&v21 + 1),
        v33);
    }
    else
    {
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(
        *((__int64 *)&v21 + 1),
        (__int64)v33);
      *((_QWORD *)&v21 + 1) += 32LL;
    }
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v33);
  }
  if ( !ParseCommonParams((__int64)&v21, (__int64)v24) )
  {
    Output::DisplayErrorResource(v14, 0x193u);
    std::vector<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>::~vector<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>(&v21);
    if ( v30 )
    {
      v30 = 0;
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v29);
    }
    if ( !v27 )
    {
LABEL_24:
      CreateParams::~CreateParams((CreateParams *)v25);
LABEL_28:
      v27 = 2;
      wil::details::ScopeExitFnGuard__lambda_7f13740c21d1139d298f70227974c5fc___::operator()(&v18);
      return 0xFFFFFFFFLL;
    }
    if ( v27 != 1 || !v26 )
      goto LABEL_28;
LABEL_27:
    v26 = 0;
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v25);
    goto LABEL_28;
  }
  if ( v24[0] )
  {
    Output::DisplayErrorResource(v14, 0x193u);
    std::vector<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>::~vector<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>(&v21);
    if ( v30 )
    {
      v30 = 0;
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v29);
    }
    if ( v27 )
    {
      if ( v27 == 1 && v26 )
      {
        v26 = 0;
        std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v25);
      }
    }
    else
    {
      CreateParams::~CreateParams((CreateParams *)v25);
    }
  }
  else
  {
    if ( !ParseInputs((Output *)&v21, (__int64)v24) )
    {
      Output::DisplayErrorResource(v16, 0x193u);
      std::vector<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>::~vector<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>(&v21);
      if ( v30 )
      {
        v30 = 0;
        std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v29);
      }
      if ( !v27 )
        goto LABEL_24;
      if ( v27 != 1 || !v26 )
        goto LABEL_28;
      goto LABEL_27;
    }
    v20[0] = CoInitializeEx(0, 6u);
    errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(v23, 2, v20);
    errorlib::scoped_error<hresult_error::tag>::throwfailed(v23);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>((__int64)v23, v17);
    *(_WORD *)((char *)v20 + 1) = 256;
    *(_QWORD *)&ProviderId.Data1 = &v28;
    if ( v27 )
    {
      if ( v27 == 1 )
        CommandParamReceiver::operator()((Output **)&ProviderId, v25);
    }
    else
    {
      CommandParamReceiver::operator()((Output **)&ProviderId, v25);
    }
    wil::details::ScopeExitFnGuard__lambda_a802d4b419c0a4f5b811cbbd7c9663ae___::operator()(v20);
    std::vector<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>::~vector<std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>>(&v21);
    if ( v30 )
    {
      v30 = 0;
      std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v29);
    }
    if ( v27 )
    {
      if ( v27 == 1 && v26 )
      {
        v26 = 0;
        std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::~basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>(v25);
      }
    }
    else
    {
      CreateParams::~CreateParams((CreateParams *)v25);
    }
  }
  v27 = 2;
  wil::details::ScopeExitFnGuard__lambda_7f13740c21d1139d298f70227974c5fc___::operator()(&v18);
  return 0;
}

```

## disassembly

```asm
0x14000ded8  mov     [rsp+arg_0], rbx
0x14000dedd  mov     [rsp+arg_10], rsi
0x14000dee2  push    rdi
0x14000dee3  push    r14
0x14000dee5  push    r15
0x14000dee7  sub     rsp, 1F0h
0x14000deee  mov     rax, cs:__security_cookie
0x14000def5  xor     rax, rsp
0x14000def8  mov     [rsp+208h+var_28], rax
0x14000df00  mov     r15, rdx
0x14000df03  movsxd  r14, ecx
0x14000df06  xor     r9d, r9d; HeapInformationLength
0x14000df09  xor     r8d, r8d; HeapInformation
0x14000df0c  lea     edx, [r9+1]; HeapInformationClass
0x14000df10  xor     ecx, ecx; HeapHandle
0x14000df12  call    cs:__imp_HeapSetInformation
0x14000df18  mov     rax, cs:off_14001A008
0x14000df1f  movups  xmm0, xmmword ptr [rax-10h]
0x14000df23  movdqu  xmmword ptr [rsp+208h+ProviderId.Data1], xmm0
0x14000df2c  xor     ebx, ebx
0x14000df2e  cmp     cs:RegHandle, rbx
0x14000df35  jz      short loc_14000DF3C
0x14000df37  lea     ecx, [rbx+5]
0x14000df3a  int     29h; Win8: RtlFailFast(ecx)
0x14000df3c  xorps   xmm0, xmm0
0x14000df3f  movdqu  cs:xmmword_14001A028, xmm0
0x14000df47  lea     r9, RegHandle; RegHandle
0x14000df4e  lea     r8, dword_14001A000; CallbackContext
0x14000df55  lea     rdx, _tlgEnableCallback; EnableCallback
0x14000df5c  lea     rcx, [rsp+208h+ProviderId]; ProviderId
0x14000df64  call    cs:__imp_EventRegister
0x14000df6a  mov     edi, 2
0x14000df6f  test    eax, eax
0x14000df71  jnz     short loc_14000DF8D
0x14000df73  mov     r8, cs:off_14001A008
0x14000df7a  movzx   r9d, word ptr [r8]
0x14000df7e  mov     edx, edi
0x14000df80  mov     rcx, cs:RegHandle
0x14000df87  call    cs:__imp_EventSetInformation
0x14000df8d  mov     [rsp+208h+var_1E7], 100h
0x14000df94  mov     ecx, 1; Ix
0x14000df99  call    _o___acrt_iob_func_0
0x14000df9e  mov     rcx, rax
0x14000dfa1  call    cs:__imp__o__fileno
0x14000dfa7  mov     ecx, eax; FileHandle
0x14000dfa9  mov     esi, 20000h
0x14000dfae  mov     edx, esi; Mode
0x14000dfb0  call    cs:__imp__setmode
0x14000dfb6  mov     ecx, edi; Ix
0x14000dfb8  call    _o___acrt_iob_func_0
0x14000dfbd  mov     rcx, rax
0x14000dfc0  call    cs:__imp__o__fileno
0x14000dfc6  mov     ecx, eax; FileHandle
0x14000dfc8  mov     edx, esi; Mode
0x14000dfca  call    cs:__imp__setmode
0x14000dfd0  xor     ecx, ecx; Ix
0x14000dfd2  call    _o___acrt_iob_func_0
0x14000dfd7  mov     rcx, rax
0x14000dfda  call    cs:__imp__o__fileno
0x14000dfe0  mov     ecx, eax; FileHandle
0x14000dfe2  mov     edx, esi; Mode
0x14000dfe4  call    cs:__imp__setmode
0x14000dfea  xor     r8d, r8d; pulNumLanguages
0x14000dfed  xor     edx, edx; pwszLanguagesBuffer
0x14000dfef  mov     ecx, 100h; dwFlags
0x14000dff4  call    cs:__imp_SetThreadPreferredUILanguages
0x14000dffa  mov     [rsp+208h+var_198], bl
0x14000dffe  mov     [rsp+208h+var_A0], edi
0x14000e005  mov     [rsp+208h+var_98], bl
0x14000e00c  mov     [rsp+208h+var_70], bl
0x14000e013  lea     rax, [rsp+208h+var_90]
0x14000e01b  mov     [rsp+208h+var_68], rax
0x14000e023  cmp     r14d, 1
0x14000e027  jnz     short loc_14000E09A
0x14000e029  mov     edx, 193h; int
0x14000e02e  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x14000e033  nop
0x14000e034  cmp     [rsp+208h+var_70], bl
0x14000e03b  jz      short loc_14000E051
0x14000e03d  mov     [rsp+208h+var_70], bl
0x14000e044  lea     rcx, [rsp+208h+var_90]
0x14000e04c  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e051  cmp     [rsp+208h+var_A0], ebx
0x14000e058  jnz     short loc_14000E069
0x14000e05a  lea     rcx, [rsp+208h+var_190]; this
0x14000e05f  call    ??1CreateParams@@QEAA@XZ; CreateParams::~CreateParams(void)
0x14000e064  jmp     loc_14000E485
0x14000e069  cmp     [rsp+208h+var_A0], 1
0x14000e071  jnz     loc_14000E485
0x14000e077  cmp     [rsp+208h+var_170], bl
0x14000e07e  jz      loc_14000E485
0x14000e084  mov     [rsp+208h+var_170], bl
0x14000e08b  lea     rcx, [rsp+208h+var_190]
0x14000e090  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e095  jmp     loc_14000E485
0x14000e09a  xorps   xmm0, xmm0
0x14000e09d  movdqu  [rsp+208h+var_1D8], xmm0
0x14000e0a3  mov     [rsp+208h+var_1C8], rbx
0x14000e0a8  mov     esi, 1
0x14000e0ad  cmp     rsi, r14
0x14000e0b0  jnb     loc_14000E156
0x14000e0b6  mov     rdx, [r15+rsi*8]
0x14000e0ba  lea     rcx, [rsp+208h+var_48]
0x14000e0c2  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(ushort const * const)
0x14000e0c7  nop
0x14000e0c8  lea     rax, [rsp+208h+var_48]
0x14000e0d0  cmp     [rsp+208h+var_30], 7
0x14000e0d9  cmova   rax, [rsp+208h+var_48]
0x14000e0e2  cmp     word ptr [rax], 2Dh ; '-'
0x14000e0e6  jnz     short loc_14000E107
0x14000e0e8  lea     rax, [rsp+208h+var_48]
0x14000e0f0  cmp     [rsp+208h+var_30], 7
0x14000e0f9  cmova   rax, [rsp+208h+var_48]
0x14000e102  mov     word ptr [rax], 2Fh ; '/'
0x14000e107  mov     rax, qword ptr [rsp+208h+var_1D8+8]
0x14000e10c  cmp     rax, [rsp+208h+var_1C8]
0x14000e111  jz      short loc_14000E12B
0x14000e113  lea     rdx, [rsp+208h+var_48]
0x14000e11b  mov     rcx, rax
0x14000e11e  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@AEBV01@@Z; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> const &)
0x14000e123  add     qword ptr [rsp+208h+var_1D8+8], 20h ; ' '
0x14000e129  jmp     short loc_14000E141
0x14000e12b  lea     r8, [rsp+208h+var_48]
0x14000e133  mov     rdx, rax
0x14000e136  lea     rcx, [rsp+208h+var_1D8]
0x14000e13b  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@1@QEAV21@AEBV21@@Z; std::vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>::_Emplace_reallocate<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> const &>(std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> * const,std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>> const &)
0x14000e140  nop
0x14000e141  lea     rcx, [rsp+208h+var_48]
0x14000e149  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e14e  inc     rsi
0x14000e151  jmp     loc_14000E0AD
0x14000e156  lea     rdx, [rsp+208h+var_198]
0x14000e15b  lea     rcx, [rsp+208h+var_1D8]
0x14000e160  call    ?ParseCommonParams@@YA_NAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@2@@std@@PEAVInputInfo@@@Z; ParseCommonParams(std::vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>> &,InputInfo *)
0x14000e165  test    al, al
0x14000e167  jnz     loc_14000E1F2
0x14000e16d  mov     edx, 193h; int
0x14000e172  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x14000e177  nop
0x14000e178  lea     rcx, [rsp+208h+var_1D8]
0x14000e17d  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>::~vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>(void)
0x14000e182  nop
0x14000e183  cmp     [rsp+208h+var_70], bl
0x14000e18a  jz      short loc_14000E1A0
0x14000e18c  mov     [rsp+208h+var_70], bl
0x14000e193  lea     rcx, [rsp+208h+var_90]
0x14000e19b  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e1a0  cmp     [rsp+208h+var_A0], ebx
0x14000e1a7  jnz     short loc_14000E1B5
0x14000e1a9  lea     rcx, [rsp+208h+var_190]; this
0x14000e1ae  call    ??1CreateParams@@QEAA@XZ; CreateParams::~CreateParams(void)
0x14000e1b3  jmp     short loc_14000E1D9
0x14000e1b5  cmp     [rsp+208h+var_A0], 1
0x14000e1bd  jnz     short loc_14000E1D9
0x14000e1bf  cmp     [rsp+208h+var_170], bl
0x14000e1c6  jz      short loc_14000E1D9
0x14000e1c8  mov     [rsp+208h+var_170], bl
0x14000e1cf  lea     rcx, [rsp+208h+var_190]
0x14000e1d4  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e1d9  mov     [rsp+208h+var_A0], edi
0x14000e1e0  lea     rcx, [rsp+208h+var_1E8]
0x14000e1e5  call    wil__details__ScopeExitFnGuard__lambda_7f13740c21d1139d298f70227974c5fc_____operator__
0x14000e1ea  or      eax, 0FFFFFFFFh
0x14000e1ed  jmp     loc_14000E499
0x14000e1f2  cmp     [rsp+208h+var_198], bl
0x14000e1f6  jz      loc_14000E280
0x14000e1fc  mov     edx, 193h; int
0x14000e201  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x14000e206  nop
0x14000e207  lea     rcx, [rsp+208h+var_1D8]
0x14000e20c  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>::~vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>(void)
0x14000e211  nop
0x14000e212  cmp     [rsp+208h+var_70], bl
0x14000e219  jz      short loc_14000E22F
0x14000e21b  mov     [rsp+208h+var_70], bl
0x14000e222  lea     rcx, [rsp+208h+var_90]
0x14000e22a  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e22f  cmp     [rsp+208h+var_A0], ebx
0x14000e236  jnz     short loc_14000E244
0x14000e238  lea     rcx, [rsp+208h+var_190]; this
0x14000e23d  call    ??1CreateParams@@QEAA@XZ; CreateParams::~CreateParams(void)
0x14000e242  jmp     short loc_14000E268
0x14000e244  cmp     [rsp+208h+var_A0], 1
0x14000e24c  jnz     short loc_14000E268
0x14000e24e  cmp     [rsp+208h+var_170], bl
0x14000e255  jz      short loc_14000E268
0x14000e257  mov     [rsp+208h+var_170], bl
0x14000e25e  lea     rcx, [rsp+208h+var_190]
0x14000e263  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e268  mov     [rsp+208h+var_A0], edi
0x14000e26f  lea     rcx, [rsp+208h+var_1E8]
0x14000e274  call    wil__details__ScopeExitFnGuard__lambda_7f13740c21d1139d298f70227974c5fc_____operator__
0x14000e279  xor     eax, eax
0x14000e27b  jmp     loc_14000E499
0x14000e280  lea     rdx, [rsp+208h+var_198]
0x14000e285  lea     rcx, [rsp+208h+var_1D8]
0x14000e28a  call    ?ParseInputs@@YA_NAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@2@@std@@PEAVInputInfo@@@Z; ParseInputs(std::vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>> const &,InputInfo *)
0x14000e28f  test    al, al
0x14000e291  jnz     loc_14000E31C
0x14000e297  mov     edx, 193h; int
0x14000e29c  call    ?DisplayErrorResource@Output@@QEBAXH@Z; Output::DisplayErrorResource(int)
0x14000e2a1  nop
0x14000e2a2  lea     rcx, [rsp+208h+var_1D8]
0x14000e2a7  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>::~vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>(void)
0x14000e2ac  nop
0x14000e2ad  cmp     [rsp+208h+var_70], bl
0x14000e2b4  jz      short loc_14000E2CA
0x14000e2b6  mov     [rsp+208h+var_70], bl
0x14000e2bd  lea     rcx, [rsp+208h+var_90]
0x14000e2c5  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e2ca  cmp     [rsp+208h+var_A0], ebx
0x14000e2d1  jnz     short loc_14000E2DF
0x14000e2d3  lea     rcx, [rsp+208h+var_190]; this
0x14000e2d8  call    ??1CreateParams@@QEAA@XZ; CreateParams::~CreateParams(void)
0x14000e2dd  jmp     short loc_14000E303
0x14000e2df  cmp     [rsp+208h+var_A0], 1
0x14000e2e7  jnz     short loc_14000E303
0x14000e2e9  cmp     [rsp+208h+var_170], bl
0x14000e2f0  jz      short loc_14000E303
0x14000e2f2  mov     [rsp+208h+var_170], bl
0x14000e2f9  lea     rcx, [rsp+208h+var_190]
0x14000e2fe  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e303  mov     [rsp+208h+var_A0], edi
0x14000e30a  lea     rcx, [rsp+208h+var_1E8]
0x14000e30f  call    wil__details__ScopeExitFnGuard__lambda_7f13740c21d1139d298f70227974c5fc_____operator__
0x14000e314  or      eax, 0FFFFFFFFh
0x14000e317  jmp     loc_14000E499
0x14000e31c  mov     edx, 6; dwCoInit
0x14000e321  xor     ecx, ecx; pvReserved
0x14000e323  call    cs:__imp_CoInitializeEx
0x14000e329  mov     [rsp+208h+var_1E4], eax
0x14000e32d  lea     r8, [rsp+208h+var_1E4]
0x14000e332  mov     edx, edi
0x14000e334  lea     rcx, [rsp+208h+var_1C0]
0x14000e339  call    ??$?0J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAA@W4type@ErrorSource@1@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(errorlib::ErrorSource::type,long &&)
0x14000e33e  nop
0x14000e33f  lea     rcx, [rsp+208h+var_1C0]
0x14000e344  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x14000e349  nop
0x14000e34a  lea     rcx, [rsp+208h+var_1C0]
0x14000e34f  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x14000e354  mov     word ptr [rsp+208h+var_1E4+1], 100h
0x14000e35b  lea     rax, [rsp+208h+var_98]
0x14000e363  mov     qword ptr [rsp+208h+ProviderId.Data1], rax
0x14000e36b  cmp     [rsp+208h+var_A0], ebx
0x14000e372  jnz     short loc_14000E388
0x14000e374  lea     rdx, [rsp+208h+var_190]
0x14000e379  lea     rcx, [rsp+208h+ProviderId]
0x14000e381  call    ??RCommandParamReceiver@@QEAAXAEBVCreateParams@@@Z; CommandParamReceiver::operator()(CreateParams const &)
0x14000e386  jmp     short loc_14000E3A5
0x14000e388  cmp     [rsp+208h+var_A0], 1
0x14000e390  jnz     short loc_14000E3A5
0x14000e392  lea     rdx, [rsp+208h+var_190]
0x14000e397  lea     rcx, [rsp+208h+ProviderId]
0x14000e39f  call    ??RCommandParamReceiver@@QEAAXAEBVDestroyParams@@@Z; CommandParamReceiver::operator()(DestroyParams const &)
0x14000e3a4  nop
0x14000e3a5  lea     rcx, [rsp+208h+var_1E4]
0x14000e3aa  call    wil__details__ScopeExitFnGuard__lambda_a802d4b419c0a4f5b811cbbd7c9663ae_____operator__
0x14000e3af  nop
0x14000e3b0  lea     rcx, [rsp+208h+var_1D8]
0x14000e3b5  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>::~vector<std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>>(void)
0x14000e3ba  nop
0x14000e3bb  cmp     [rsp+208h+var_70], bl
0x14000e3c2  jz      short loc_14000E3D8
0x14000e3c4  mov     [rsp+208h+var_70], bl
0x14000e3cb  lea     rcx, [rsp+208h+var_90]
0x14000e3d3  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e3d8  cmp     [rsp+208h+var_A0], ebx
0x14000e3df  jnz     short loc_14000E3ED
0x14000e3e1  lea     rcx, [rsp+208h+var_190]; this
0x14000e3e6  call    ??1CreateParams@@QEAA@XZ; CreateParams::~CreateParams(void)
0x14000e3eb  jmp     short loc_14000E411
0x14000e3ed  cmp     [rsp+208h+var_A0], 1
0x14000e3f5  jnz     short loc_14000E411
0x14000e3f7  cmp     [rsp+208h+var_170], bl
0x14000e3fe  jz      short loc_14000E411
0x14000e400  mov     [rsp+208h+var_170], bl
0x14000e407  lea     rcx, [rsp+208h+var_190]
0x14000e40c  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e411  mov     [rsp+208h+var_A0], edi
0x14000e418  lea     rcx, [rsp+208h+var_1E8]
0x14000e41d  call    wil__details__ScopeExitFnGuard__lambda_7f13740c21d1139d298f70227974c5fc_____operator__
0x14000e422  xor     eax, eax
0x14000e424  jmp     short loc_14000E499
0x14000e426  xor     ebx, ebx
0x14000e428  cmp     [rsp+208h+var_70], bl
0x14000e42f  jz      short loc_14000E445
0x14000e431  mov     [rsp+208h+var_70], bl
0x14000e438  lea     rcx, [rsp+208h+var_90]
0x14000e440  call    ??1?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::~basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x14000e445  cmp     [rsp+208h+var_A0], ebx
0x14000e44c  jnz     short loc_14000E45C
0x14000e44e  lea     rcx, [rsp+208h+var_190]; this
0x14000e453  call    ??1CreateParams@@QEAA@XZ; CreateParams::~CreateParams(void)
0x14000e458  jmp     short loc_14000E480
0x14000e45a  jmp     short loc_14000E426
0x14000e45c  cmp     [rsp+208h+var_A0], 1
0x14000e464  jnz     short loc_14000E480
0x14000e466  cmp     [rsp+208h+var_170], bl
0x14000e46d  jz      short loc_14000E480
  ... truncated ...
```

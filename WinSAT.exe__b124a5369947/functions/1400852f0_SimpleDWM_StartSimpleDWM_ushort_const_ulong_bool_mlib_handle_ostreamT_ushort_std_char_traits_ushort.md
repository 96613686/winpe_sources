# SimpleDWM::StartSimpleDWM(ushort const *,ulong,bool,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> *)

- ea: `0x1400852f0`
- end: `0x14008561d`
- name: `?StartSimpleDWM@SimpleDWM@@YAJPEBGK_NPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@Z`
- size: `813`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140079e98`

## callees

- `0x140004348`
- `0x14000449c`
- `0x140005cf4`
- `0x14000695c`
- `0x140016d04`
- `0x140017af0`
- `0x14007df08`
- `0x14007e204`
- `0x14007e498`
- `0x14007e67c`
- `0x14007e910`
- `0x14007e970`
- `0x14007fa4c`
- `0x140081584`
- `0x140082be0`
- `0x140083000`
- `0x140085280`
- `0x1400852f0`
- `0x140085624`
- `0x14008a990`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14008550e`
- `KERNEL32!GetTickCount` at `0x14008550e`
- `KERNEL32!GetCurrentProcessId` at `0x140085386`
- `KERNEL32!GetCurrentProcessId` at `0x140085386`
- `msvcrt!srand` at `0x1400853b4`
- `msvcrt!srand` at `0x1400853b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SimpleDWM::StartSimpleDWM(unsigned __int16 *a1, __int64 a2, bool a3, __int64 a4)
{
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  unsigned int *v10; // r9
  unsigned int *v11; // r9
  signed int v12; // ebx
  unsigned int *v13; // r9
  D3DCommon *v14; // rcx
  unsigned __int16 v15; // dx
  __int64 v16; // rcx
  struct D3DCommon::_DX9Callbacks *v17; // rdx
  __int64 (__fastcall *v18)(); // rax
  unsigned int v19; // edx
  signed int Device; // eax
  D3DCommon *v21; // rcx
  D3DCommon *v22; // rcx
  D3DCommon *v23; // rcx
  unsigned int v25; // [rsp+20h] [rbp-69h]
  enum _D3DDEVTYPE v26; // [rsp+38h] [rbp-51h]
  int v27; // [rsp+40h] [rbp-49h]
  unsigned int v28; // [rsp+48h] [rbp-41h]
  enum _D3DSWAPEFFECT v29; // [rsp+50h] [rbp-39h]
  unsigned int v30; // [rsp+58h] [rbp-31h]
  enum _D3DMULTISAMPLE_TYPE v31; // [rsp+60h] [rbp-29h]
  int v32; // [rsp+70h] [rbp-19h]
  enum _D3DFORMAT v33; // [rsp+78h] [rbp-11h]
  unsigned int v34; // [rsp+80h] [rbp-9h]
  unsigned int *v35; // [rsp+88h] [rbp-1h]
  __int64 (__fastcall *v36)(); // [rsp+90h] [rbp+7h] BYREF
  __int64 (__fastcall *v37)(unsigned int); // [rsp+98h] [rbp+Fh]
  __int64 (__fastcall *v38)(); // [rsp+A0h] [rbp+17h]
  __int64 (__fastcall *v39)(); // [rsp+A8h] [rbp+1Fh]
  __int64 (__fastcall *v40)(); // [rsp+B0h] [rbp+27h]
  __int64 v41; // [rsp+B8h] [rbp+2Fh]
  unsigned int CurrentProcessId; // [rsp+100h] [rbp+77h] BYREF
  char v43; // [rsp+108h] [rbp+7Fh] BYREF

  if ( D3DCommon::g_bVerbose && D3DCommon::g_phStdOut )
  {
    v7 = mlib::MUILoader::MUILoader((mlib::MUILoader *)&v36, 0x65u);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      &v43,
      v7);
    mlib::operator<<<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
      D3DCommon::g_phStdOut + 240,
      &v43);
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v8, L"SimpleDWM::StartSimpleDWM");
    std::endl(v9);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v43);
  }
  D3DCommon::g_bVerbose = a3;
  D3DCommon::g_phStdOut = a4;
  CurrentProcessId = GetCurrentProcessId();
  D3DCommon::LogMessage((D3DCommon *)0x53, 1, 0, v10);
  D3DCommon::LogMessage((D3DCommon *)0x5A, 1, (int *)&CurrentProcessId, v11);
  srand(0xA017200u);
  v12 = SimpleDWM::SimpleDWMState9::Initialize((SimpleDWM::SimpleDWMState9 *)&qword_1401C6770);
  CurrentProcessId = v12;
  if ( v12 >= 0 )
  {
    v12 = SimpleDWM::SimpleDWMState9::ProcessCommandLine((SimpleDWM::SimpleDWMState9 *)&qword_1401C6770, a1);
    CurrentProcessId = v12;
    if ( v12 >= 0 )
    {
      qword_1401CBA28 = (__int64)&qword_1401C6770;
      dword_1401C67AC = 1;
      v12 = D3DCommon::DX9Init(v14);
      CurrentProcessId = v12;
      if ( v12 < 0 )
      {
        v16 = 116;
LABEL_8:
        D3DCommon::ERR((D3DCommon *)v16, v15);
        goto LABEL_29;
      }
      v12 = anonymous_namespace_::VerifyDevice();
      CurrentProcessId = v12;
      if ( v12 < 0 )
        goto LABEL_29;
      if ( !qword_1401C6808 )
      {
        D3DCommon::ERR((D3DCommon *)0x6D, (unsigned __int16)L"gs_State.m_pTexWidth", L"SimpleDWM::StartSimpleDWM");
LABEL_12:
        v12 = -2147024882;
        CurrentProcessId = -2147024882;
        goto LABEL_29;
      }
      if ( !qword_1401C6810 )
      {
        D3DCommon::ERR((D3DCommon *)0x6D, (unsigned __int16)L"gs_State.m_pTexHeight", L"SimpleDWM::StartSimpleDWM");
        goto LABEL_12;
      }
      v41 = 0;
      if ( dword_1401C67B0 == 1 )
      {
        v40 = anonymous_namespace_::OnFrameRender;
        v36 = anonymous_namespace_::OnCreateDevice;
        v37 = anonymous_namespace_::OnResetDevice;
        v39 = anonymous_namespace_::OnLostDevice;
        v18 = anonymous_namespace_::OnDestroyDevice;
      }
      else
      {
        v40 = anonymous_namespace_::OnFrameRenderToTexture;
        v36 = anonymous_namespace_::OnCreateDeviceToTexture;
        v37 = anonymous_namespace_::OnResetDeviceToTexture;
        v39 = anonymous_namespace_::OnLostDeviceToTexture;
        v18 = anonymous_namespace_::OnDestroyDeviceToTexture;
      }
      v38 = v18;
      D3DCommon::DX9SetCallbacks((D3DCommon *)&v36, v17);
      v12 = D3DCommon::DXCreateWindow(
              L"SimpleDWM Back to Front",
              (const unsigned __int16 *)(unsigned int)dword_1401C67C8);
      CurrentProcessId = v12;
      if ( v12 < 0 )
      {
        v16 = 117;
        goto LABEL_8;
      }
      dword_1401C6780 = GetTickCount();
      if ( dword_1401C6794 )
      {
        if ( byte_1401C6790 )
        {
          v29 = (_DWORD)dword_1401C67C8 != 128 ? D3DSWAPEFFECT_COPY : 0;
          v27 = dword_1401C6794;
          v26 = D3DDEVTYPE_HAL;
LABEL_23:
          Device = D3DCommon::DX9CreateDevice(
                     (D3DCommon *)1,
                     v19,
                     dword_1401C6788,
                     dword_1401C678C,
                     v25,
                     D3DFMT_UNKNOWN,
                     dword_1401C68C8,
                     v26,
                     v27,
                     v28,
                     v29,
                     v30,
                     v31,
                     0,
                     v32,
                     v33,
                     v34,
                     v35);
          goto LABEL_27;
        }
      }
      else if ( byte_1401C6790 )
      {
        v29 = (_DWORD)dword_1401C67C8 != 128 ? D3DSWAPEFFECT_COPY : 0;
        v27 = 75;
        v26 = 0x80000000;
        goto LABEL_23;
      }
      Device = D3DCommon::DX9CreateDevice(
                 (D3DCommon *)1,
                 v19,
                 dword_1401C6788,
                 dword_1401C678C,
                 v25,
                 (enum _D3DFORMAT)1,
                 dword_1401C68C8,
                 (enum _D3DDEVTYPE)0x80000000,
                 0,
                 v28,
                 (_DWORD)dword_1401C67C8 != 128 ? D3DSWAPEFFECT_COPY : (enum _D3DSWAPEFFECT)0,
                 v30,
                 v31,
                 0,
                 v32,
                 v33,
                 v34,
                 v35);
LABEL_27:
      v12 = Device;
      CurrentProcessId = Device;
      if ( Device >= 0 )
      {
        D3DCommon::LogMessage((D3DCommon *)0x59, 1, (int *)&dword_1401C6844, v13);
        v12 = D3DCommon::DX9MainLoop(v21);
        CurrentProcessId = v12;
        D3DCommon::DX9DestroyDevice(v22);
      }
    }
  }
LABEL_29:
  D3DCommon::LogMessage((D3DCommon *)0x45, 1, (int *)&CurrentProcessId, v13);
  SimpleDWM::SimpleDWMState9::Cleanup((SimpleDWM::SimpleDWMState9 *)&qword_1401C6770);
  D3DCommon::DX9Shutdown(v23);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400852f0  mov     [rsp-8+arg_0], rbx
0x1400852f5  push    rbp
0x1400852f6  push    rsi
0x1400852f7  push    rdi
0x1400852f8  push    r14
0x1400852fa  push    r15
0x1400852fc  lea     rbp, [rsp-37h]
0x140085301  sub     rsp, 0C0h
0x140085308  mov     rbx, r9
0x14008530b  mov     sil, r8b
0x14008530e  mov     rdi, rcx
0x140085311  xor     r14d, r14d
0x140085314  cmp     cs:?g_bVerbose@D3DCommon@@3_NA, r14b; bool D3DCommon::g_bVerbose
0x14008531b  jz      short loc_140085378
0x14008531d  cmp     cs:?g_phStdOut@D3DCommon@@3PEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@EA, r14; mlib::handle_ostreamT<ushort,std::char_traits<ushort>> * D3DCommon::g_phStdOut
0x140085324  jz      short loc_140085378
0x140085326  lea     edx, [r14+65h]; unsigned __int16
0x14008532a  lea     rcx, [rbp+57h+var_50]; this
0x14008532e  call    ??0MUILoader@mlib@@QEAA@G@Z; mlib::MUILoader::MUILoader(ushort)
0x140085333  mov     rdx, rax
0x140085336  lea     rcx, [rbp+57h+arg_18]
0x14008533a  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@AEBVMSInitializer@1@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(mlib::MSInitializer const &)
0x14008533f  nop
0x140085340  mov     rcx, cs:?g_phStdOut@D3DCommon@@3PEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@EA; mlib::handle_ostreamT<ushort,std::char_traits<ushort>> * D3DCommon::g_phStdOut
0x140085347  add     rcx, 0F0h
0x14008534e  lea     rdx, [rbp+57h+arg_18]
0x140085352  call    ??$?6GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@std@@AEAV12@AEBV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@0@@Z; mlib::operator<<<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::basic_ostream<ushort> &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x140085357  mov     rcx, rax
0x14008535a  lea     rdx, aSimpledwmStart_0; "SimpleDWM::StartSimpleDWM"
0x140085361  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140085366  mov     rcx, rax
0x140085369  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x14008536e  nop
0x14008536f  lea     rcx, [rbp+57h+arg_18]
0x140085373  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x140085378  mov     cs:?g_bVerbose@D3DCommon@@3_NA, sil; bool D3DCommon::g_bVerbose
0x14008537f  mov     cs:?g_phStdOut@D3DCommon@@3PEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@EA, rbx; mlib::handle_ostreamT<ushort,std::char_traits<ushort>> * D3DCommon::g_phStdOut
0x140085386  call    cs:__imp_GetCurrentProcessId
0x14008538c  mov     [rbp+57h+arg_10], eax
0x14008538f  mov     ecx, 53h ; 'S'; this
0x140085394  xor     r8d, r8d; unsigned int
0x140085397  lea     esi, [rcx-52h]
0x14008539a  mov     edx, esi; unsigned __int16
0x14008539c  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x1400853a1  lea     ecx, [rsi+59h]; this
0x1400853a4  lea     r8, [rbp+57h+arg_10]; unsigned int
0x1400853a8  mov     edx, esi; unsigned __int16
0x1400853aa  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x1400853af  mov     ecx, 0A017200h; Seed
0x1400853b4  call    cs:__imp_srand
0x1400853ba  lea     r15, qword_1401C6770
0x1400853c1  mov     rcx, r15; this
0x1400853c4  call    ?Initialize@SimpleDWMState9@SimpleDWM@@UEAAJXZ; SimpleDWM::SimpleDWMState9::Initialize(void)
0x1400853c9  mov     ebx, eax
0x1400853cb  mov     [rbp+57h+arg_10], eax
0x1400853ce  test    eax, eax
0x1400853d0  js      loc_1400855E7
0x1400853d6  mov     rdx, rdi; unsigned __int16 *
0x1400853d9  mov     rcx, r15; this
0x1400853dc  call    ?ProcessCommandLine@SimpleDWMState9@SimpleDWM@@UEAAJPEBG@Z; SimpleDWM::SimpleDWMState9::ProcessCommandLine(ushort const *)
0x1400853e1  mov     ebx, eax
0x1400853e3  mov     [rbp+57h+arg_10], eax
0x1400853e6  test    eax, eax
0x1400853e8  js      loc_1400855E7
0x1400853ee  mov     cs:qword_1401CBA28, r15
0x1400853f5  mov     cs:dword_1401C67AC, esi
0x1400853fb  call    ?DX9Init@D3DCommon@@YAJXZ; D3DCommon::DX9Init(void)
0x140085400  mov     ebx, eax
0x140085402  mov     [rbp+57h+arg_10], eax
0x140085405  test    eax, eax
0x140085407  jns     short loc_140085416
0x140085409  lea     ecx, [rsi+73h]; this
0x14008540c  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x140085411  jmp     loc_1400855E7
0x140085416  call    _anonymous_namespace___VerifyDevice
0x14008541b  mov     ebx, eax
0x14008541d  mov     [rbp+57h+arg_10], eax
0x140085420  test    eax, eax
0x140085422  js      loc_1400855E7
0x140085428  cmp     cs:qword_1401C6808, r14
0x14008542f  jnz     short loc_140085456
0x140085431  lea     rdx, aGsStateMPtexwi; "gs_State.m_pTexWidth"
0x140085438  lea     r8, aSimpledwmStart_0; "SimpleDWM::StartSimpleDWM"
0x14008543f  mov     ecx, 6Dh ; 'm'; this
0x140085444  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x140085449  mov     ebx, 8007000Eh
0x14008544e  mov     [rbp+57h+arg_10], ebx
0x140085451  jmp     loc_1400855E7
0x140085456  cmp     cs:qword_1401C6810, r14
0x14008545d  jnz     short loc_140085468
0x14008545f  lea     rdx, aGsStateMPtexhe; "gs_State.m_pTexHeight"
0x140085466  jmp     short loc_140085438
0x140085468  mov     [rbp+57h+var_28], r14
0x14008546c  cmp     cs:dword_1401C67B0, esi
0x140085472  jnz     short loc_1400854A9
0x140085474  lea     rax, _anonymous_namespace___OnFrameRender
0x14008547b  mov     [rbp+57h+var_30], rax
0x14008547f  lea     rax, _anonymous_namespace___OnCreateDevice
0x140085486  mov     [rbp+57h+var_50], rax
0x14008548a  lea     rax, _anonymous_namespace___OnResetDevice
0x140085491  mov     [rbp+57h+var_48], rax
0x140085495  lea     rax, _anonymous_namespace___OnLostDevice
0x14008549c  mov     [rbp+57h+var_38], rax
0x1400854a0  lea     rax, _anonymous_namespace___OnDestroyDevice
0x1400854a7  jmp     short loc_1400854DC
0x1400854a9  lea     rax, _anonymous_namespace___OnFrameRenderToTexture
0x1400854b0  mov     [rbp+57h+var_30], rax
0x1400854b4  lea     rax, _anonymous_namespace___OnCreateDeviceToTexture
0x1400854bb  mov     [rbp+57h+var_50], rax
0x1400854bf  lea     rax, _anonymous_namespace___OnResetDeviceToTexture
0x1400854c6  mov     [rbp+57h+var_48], rax
0x1400854ca  lea     rax, _anonymous_namespace___OnLostDeviceToTexture
0x1400854d1  mov     [rbp+57h+var_38], rax
0x1400854d5  lea     rax, _anonymous_namespace___OnDestroyDeviceToTexture
0x1400854dc  mov     [rbp+57h+var_40], rax
0x1400854e0  lea     rcx, [rbp+57h+var_50]; this
0x1400854e4  call    ?DX9SetCallbacks@D3DCommon@@YAXPEAU_DX9Callbacks@1@@Z; D3DCommon::DX9SetCallbacks(D3DCommon::_DX9Callbacks *)
0x1400854e9  mov     edx, cs:dword_1401C67C8; unsigned __int16 *
0x1400854ef  lea     rcx, WindowName; "SimpleDWM Back to Front"
0x1400854f6  call    ?DXCreateWindow@D3DCommon@@YAJPEBGI@Z; D3DCommon::DXCreateWindow(ushort const *,uint)
0x1400854fb  mov     ebx, eax
0x1400854fd  mov     [rbp+57h+arg_10], eax
0x140085500  test    eax, eax
0x140085502  jns     short loc_14008550E
0x140085504  mov     ecx, 75h ; 'u'
0x140085509  jmp     loc_14008540C
0x14008550e  call    cs:__imp_GetTickCount
0x140085514  mov     cs:dword_1401C6780, eax
0x14008551a  mov     eax, cs:dword_1401C67C8
0x140085520  add     eax, 0FFFFFF80h
0x140085523  neg     eax
0x140085525  sbb     ecx, ecx
0x140085527  and     ecx, 3
0x14008552a  mov     eax, cs:dword_1401C6794
0x140085530  test    eax, eax
0x140085532  jz      short loc_14008555F
0x140085534  cmp     cs:byte_1401C6790, r14b
0x14008553b  jz      short loc_140085583
0x14008553d  mov     [rsp+0E0h+var_78], r14d
0x140085542  mov     [rsp+0E0h+var_90], ecx
0x140085546  mov     [rsp+0E0h+var_A0], eax
0x14008554a  mov     [rsp+0E0h+var_A8], esi
0x14008554e  mov     eax, cs:dword_1401C68C8
0x140085554  mov     [rsp+0E0h+var_B0], eax
0x140085558  mov     [rsp+0E0h+var_B8], r14d
0x14008555d  jmp     short loc_1400855A7
0x14008555f  cmp     cs:byte_1401C6790, r14b
0x140085566  jz      short loc_140085583
0x140085568  mov     [rsp+0E0h+var_78], r14d
0x14008556d  mov     [rsp+0E0h+var_90], ecx
0x140085571  mov     [rsp+0E0h+var_A0], 4Bh ; 'K'
0x140085579  mov     [rsp+0E0h+var_A8], 80000000h
0x140085581  jmp     short loc_14008554E
0x140085583  mov     [rsp+0E0h+var_78], r14d; unsigned int
0x140085588  mov     [rsp+0E0h+var_90], ecx; enum _D3DSWAPEFFECT
0x14008558c  mov     [rsp+0E0h+var_A0], r14d; unsigned int
0x140085591  mov     [rsp+0E0h+var_A8], 80000000h; enum _D3DDEVTYPE
0x140085599  mov     eax, cs:dword_1401C68C8
0x14008559f  mov     [rsp+0E0h+var_B0], eax; int
0x1400855a3  mov     [rsp+0E0h+var_B8], esi; enum _D3DFORMAT
0x1400855a7  mov     r9d, cs:dword_1401C678C; unsigned int
0x1400855ae  mov     r8d, cs:dword_1401C6788; unsigned int
0x1400855b5  mov     ecx, esi; this
0x1400855b7  call    ?DX9CreateDevice@D3DCommon@@YAJKIIIW4_D3DFORMAT@@HW4_D3DDEVTYPE@@IIW4_D3DSWAPEFFECT@@IW4_D3DMULTISAMPLE_TYPE@@IH0KPEAK@Z; D3DCommon::DX9CreateDevice(ulong,uint,uint,uint,_D3DFORMAT,int,_D3DDEVTYPE,uint,uint,_D3DSWAPEFFECT,uint,_D3DMULTISAMPLE_TYPE,uint,int,_D3DFORMAT,ulong,ulong *)
0x1400855bc  mov     ebx, eax
0x1400855be  mov     [rbp+57h+arg_10], eax
0x1400855c1  test    eax, eax
0x1400855c3  js      short loc_1400855E7
0x1400855c5  mov     ecx, 59h ; 'Y'; this
0x1400855ca  lea     r8, dword_1401C6844; unsigned int
0x1400855d1  mov     edx, esi; unsigned __int16
0x1400855d3  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x1400855d8  call    ?DX9MainLoop@D3DCommon@@YAJXZ; D3DCommon::DX9MainLoop(void)
0x1400855dd  mov     ebx, eax
0x1400855df  mov     [rbp+57h+arg_10], eax
0x1400855e2  call    ?DX9DestroyDevice@D3DCommon@@YAXXZ; D3DCommon::DX9DestroyDevice(void)
0x1400855e7  mov     ecx, 45h ; 'E'; this
0x1400855ec  lea     r8, [rbp+57h+arg_10]; unsigned int
0x1400855f0  mov     edx, esi; unsigned __int16
0x1400855f2  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x1400855f7  mov     rcx, r15; this
0x1400855fa  call    ?Cleanup@SimpleDWMState9@SimpleDWM@@UEAAXXZ; SimpleDWM::SimpleDWMState9::Cleanup(void)
0x1400855ff  call    ?DX9Shutdown@D3DCommon@@YAXXZ; D3DCommon::DX9Shutdown(void)
0x140085604  mov     eax, ebx
0x140085606  mov     rbx, [rsp+0E0h+arg_0]
0x14008560e  add     rsp, 0C0h
0x140085615  pop     r15
0x140085617  pop     r14
0x140085619  pop     rdi
0x14008561a  pop     rsi
0x14008561b  pop     rbp
0x14008561c  retn
```

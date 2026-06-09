# CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>::CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>(std::shared_ptr<CRdpIdMonitor> const &,Rdp::Avenc::IGpuFrameProcessor *)

- ea: `0x18002de2c`
- end: `0x18002e1cf`
- name: `??0?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@QEAA@AEBV?$shared_ptr@VCRdpIdMonitor@@@std@@PEAUIGpuFrameProcessor@Avenc@Rdp@@@Z`
- size: `931`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e41c`

## callees

- `0x180006f60`
- `0x1800107ec`
- `0x180013bb0`
- `0x18001ddf4`
- `0x18002d684`
- `0x18002d6cc`
- `0x18002d6f0`
- `0x18002de2c`
- `0x18002e214`
- `0x18002e6a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e16c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e16c`

## string_xrefs

- `0x18002e17f`: `Failed to create WIC factory`

## pseudocode

```c
__int64 __fastcall CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>::CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  LPVOID *ppv; // r14
  __int64 v6; // rdi
  _WORD *v7; // r9
  unsigned int v8; // r8d
  __int64 v9; // r12
  _WORD *v10; // r9
  unsigned int v11; // r8d
  __int64 v12; // r15
  _WORD *v13; // r9
  unsigned int v14; // r8d
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  LPVOID v22; // rcx
  unsigned int Instance; // eax
  const char *v25; // [rsp+28h] [rbp-D8h]
  _BYTE v26[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v28[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v29[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v31[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v32[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v33[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v34[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v35[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v36[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v37[74]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v38[6]; // [rsp+1EAh] [rbp+EAh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  *(_QWORD *)a1 = &winrt::impl::producers_base<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,std::tuple<Rdp::Avenc::IGpuFrameProcessor>>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 16) = 1;
  *(_QWORD *)a1 = &CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>::`vftable'{for `winrt::impl::producers_base<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,std::tuple<Rdp::Avenc::IGpuFrameProcessor>>'};
  *(_QWORD *)(a1 + 8) = &CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>::`vftable'{for `winrt::impl::root_implements<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,Rdp::Avenc::IGpuFrameProcessor>'};
  ppv = (LPVOID *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = a3;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  v6 = a1 + 40;
  std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(a1 + 40, a2);
  *(_OWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 7;
  *(_WORD *)(a1 + 56) = 0;
  *(_DWORD *)(a1 + 88) = 0;
  v7 = v38;
  v8 = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 280LL);
  do
  {
    *--v7 = v8 % 0xA + 48;
    v8 /= 0xAu;
  }
  while ( v8 );
  std::wstring::wstring(v28, v7, v38);
  v9 = std::wstring::wstring(v37, L"_Monitor_");
  v10 = v38;
  v11 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 232LL) + 516LL);
  do
  {
    *--v10 = v11 % 0xA + 48;
    v11 /= 0xAu;
  }
  while ( v11 );
  std::wstring::wstring(v27, v10, v38);
  v12 = std::wstring::wstring(v36, L"_Session_");
  v13 = v38;
  v14 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v6 + 232LL) + 520LL);
  do
  {
    *--v13 = v14 % 0xA + 48;
    v14 /= 0xAu;
  }
  while ( v14 );
  std::wstring::wstring(v26, v13, v38);
  v15 = std::wstring::wstring(v35, L"FrameDump_TerminalLuid_");
  v16 = std::operator+<unsigned short>(v34, *(_QWORD *)(*(_QWORD *)v6 + 232LL) + 472LL, v15);
  v17 = std::operator+<unsigned short>(v33, v16, v26);
  v18 = std::operator+<unsigned short>(v32, v17, v12);
  v19 = std::operator+<unsigned short>(v31, v18, v27);
  v20 = std::operator+<unsigned short>(v30, v19, v9);
  v21 = std::operator+<unsigned short>(v29, v20, v28);
  std::wstring::operator=(a1 + 56, v21);
  std::wstring::_Tidy_deallocate(v29);
  std::wstring::_Tidy_deallocate(v30);
  std::wstring::_Tidy_deallocate(v31);
  std::wstring::_Tidy_deallocate(v32);
  std::wstring::_Tidy_deallocate(v33);
  std::wstring::_Tidy_deallocate(v34);
  std::wstring::_Tidy_deallocate(v35);
  std::wstring::_Tidy_deallocate(v26);
  std::wstring::_Tidy_deallocate(v36);
  std::wstring::_Tidy_deallocate(v27);
  std::wstring::_Tidy_deallocate(v37);
  std::wstring::_Tidy_deallocate(v28);
  v22 = *ppv;
  *ppv = 0;
  if ( v22 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
  Instance = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_7b816b45_1996_4476_b132_de9e247c8af0, ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x43,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\framebuffer.cpp",
    (const char *)Instance,
    (int)"Failed to create WIC factory",
    v25);
  return a1;
}

```

## disassembly

```asm
0x18002de2c  mov     [rsp-8+arg_10], rbx
0x18002de31  mov     [rsp-8+arg_18], rsi
0x18002de36  push    rbp
0x18002de37  push    rdi
0x18002de38  push    r12
0x18002de3a  push    r14
0x18002de3c  push    r15
0x18002de3e  lea     rbp, [rsp-100h]
0x18002de46  sub     rsp, 200h
0x18002de4d  mov     rax, cs:__security_cookie
0x18002de54  xor     rax, rsp
0x18002de57  mov     [rbp+120h+var_30], rax
0x18002de5e  mov     rsi, rdx
0x18002de61  mov     rbx, rcx
0x18002de64  mov     [rsp+220h+var_1E8], rcx
0x18002de69  lea     rax, ??_7?$producers_base@V?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@V?$tuple@UIGpuFrameProcessor@Avenc@Rdp@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,std::tuple<Rdp::Avenc::IGpuFrameProcessor>>::`vftable'
0x18002de70  mov     [rcx], rax
0x18002de73  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002de7a  mov     qword ptr [rcx+10h], 1
0x18002de82  lea     rax, ??_7?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@6B?$producers_base@V?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@V?$tuple@UIGpuFrameProcessor@Avenc@Rdp@@@std@@@impl@winrt@@@; const CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>::`vftable'{for `winrt::impl::producers_base<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,std::tuple<Rdp::Avenc::IGpuFrameProcessor>>'}
0x18002de89  mov     [rcx], rax
0x18002de8c  lea     rax, ??_7?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@6B?$root_implements@V?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@UIGpuFrameProcessor@Avenc@Rdp@@@impl@winrt@@@; const CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>::`vftable'{for `winrt::impl::root_implements<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,Rdp::Avenc::IGpuFrameProcessor>'}
0x18002de93  mov     [rcx+8], rax
0x18002de97  lea     r14, [rcx+18h]
0x18002de9b  mov     qword ptr [r14], 0
0x18002dea2  mov     [rcx+20h], r8
0x18002dea6  test    r8, r8
0x18002dea9  jz      short loc_18002DEBB
0x18002deab  mov     rax, [r8]
0x18002deae  mov     rcx, r8
0x18002deb1  mov     rax, [rax+8]
0x18002deb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002deba  nop
0x18002debb  lea     rdi, [rbx+28h]
0x18002debf  mov     rdx, rsi
0x18002dec2  mov     rcx, rdi
0x18002dec5  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x18002deca  nop
0x18002decb  lea     rsi, [rbx+38h]
0x18002decf  xorps   xmm0, xmm0
0x18002ded2  movups  xmmword ptr [rsi], xmm0
0x18002ded5  mov     qword ptr [rsi+10h], 0
0x18002dedd  mov     qword ptr [rsi+18h], 7
0x18002dee5  xor     eax, eax
0x18002dee7  mov     [rsi], ax
0x18002deea  mov     [rbx+58h], eax
0x18002deed  lea     r9, [rbp+120h+var_36]
0x18002def4  mov     rax, [rdi]
0x18002def7  mov     r8d, [rax+118h]
0x18002defe  mov     r15d, 0CCCCCCCDh
0x18002df04  sub     r9, 2
0x18002df08  mov     eax, r15d
0x18002df0b  mul     r8d
0x18002df0e  shr     edx, 3
0x18002df11  movzx   eax, dx
0x18002df14  shl     ax, 2
0x18002df18  lea     ecx, [rax+rdx]
0x18002df1b  add     cx, cx
0x18002df1e  sub     r8w, cx
0x18002df22  add     r8w, 30h ; '0'
0x18002df27  mov     [r9], r8w
0x18002df2b  mov     r8d, edx
0x18002df2e  test    edx, edx
0x18002df30  jnz     short loc_18002DF04
0x18002df32  lea     r8, [rbp+120h+var_36]
0x18002df39  mov     rdx, r9
0x18002df3c  lea     rcx, [rbp+120h+var_1A0]
0x18002df40  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18002df45  nop
0x18002df46  lea     rdx, aMonitor; "_Monitor_"
0x18002df4d  lea     rcx, [rbp+120h+var_80]
0x18002df54  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002df59  mov     r12, rax
0x18002df5c  lea     r9, [rbp+120h+var_36]
0x18002df63  mov     rax, [rdi]
0x18002df66  mov     rcx, [rax+0E8h]
0x18002df6d  mov     r8d, [rcx+204h]
0x18002df74  sub     r9, 2
0x18002df78  mov     eax, r15d
0x18002df7b  mul     r8d
0x18002df7e  shr     edx, 3
0x18002df81  movzx   eax, dx
0x18002df84  shl     ax, 2
0x18002df88  lea     ecx, [rax+rdx]
0x18002df8b  add     cx, cx
0x18002df8e  sub     r8w, cx
0x18002df92  add     r8w, 30h ; '0'
0x18002df97  mov     [r9], r8w
0x18002df9b  mov     r8d, edx
0x18002df9e  test    edx, edx
0x18002dfa0  jnz     short loc_18002DF74
0x18002dfa2  lea     r8, [rbp+120h+var_36]
0x18002dfa9  mov     rdx, r9
0x18002dfac  lea     rcx, [rsp+220h+var_1C0]
0x18002dfb1  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18002dfb6  nop
0x18002dfb7  lea     rdx, aSession; "_Session_"
0x18002dfbe  lea     rcx, [rbp+120h+var_A0]
0x18002dfc5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002dfca  mov     r15, rax
0x18002dfcd  lea     r9, [rbp+120h+var_36]
0x18002dfd4  mov     rax, [rdi]
0x18002dfd7  mov     rcx, [rax+0E8h]
0x18002dfde  mov     r8d, [rcx+208h]
0x18002dfe5  sub     r9, 2
0x18002dfe9  mov     eax, 0CCCCCCCDh
0x18002dfee  mul     r8d
0x18002dff1  shr     edx, 3
0x18002dff4  movzx   eax, dx
0x18002dff7  shl     ax, 2
0x18002dffb  lea     ecx, [rax+rdx]
0x18002dffe  add     cx, cx
0x18002e001  sub     r8w, cx
0x18002e005  add     r8w, 30h ; '0'
0x18002e00a  mov     [r9], r8w
0x18002e00e  mov     r8d, edx
0x18002e011  test    edx, edx
0x18002e013  jnz     short loc_18002DFE5
0x18002e015  lea     r8, [rbp+120h+var_36]
0x18002e01c  mov     rdx, r9
0x18002e01f  lea     rcx, [rsp+220h+var_1E0]
0x18002e024  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18002e029  nop
0x18002e02a  lea     rdx, aFramedumpTermi; "FrameDump_TerminalLuid_"
0x18002e031  lea     rcx, [rbp+120h+var_C0]
0x18002e035  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e03a  mov     r8, rax
0x18002e03d  mov     rax, [rdi]
0x18002e040  mov     rdx, [rax+0E8h]
0x18002e047  add     rdx, 1D8h
0x18002e04e  lea     rcx, [rbp+120h+var_E0]
0x18002e052  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x18002e057  nop
0x18002e058  lea     r8, [rsp+220h+var_1E0]
0x18002e05d  mov     rdx, rax
0x18002e060  lea     rcx, [rbp+120h+var_100]
0x18002e064  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002e069  nop
0x18002e06a  mov     r8, r15
0x18002e06d  mov     rdx, rax
0x18002e070  lea     rcx, [rbp+120h+var_120]
0x18002e074  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002e079  nop
0x18002e07a  lea     r8, [rsp+220h+var_1C0]
0x18002e07f  mov     rdx, rax
0x18002e082  lea     rcx, [rbp+120h+var_140]
0x18002e086  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002e08b  nop
0x18002e08c  mov     r8, r12
0x18002e08f  mov     rdx, rax
0x18002e092  lea     rcx, [rbp+120h+var_160]
0x18002e096  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002e09b  nop
0x18002e09c  lea     r8, [rbp+120h+var_1A0]
0x18002e0a0  mov     rdx, rax
0x18002e0a3  lea     rcx, [rbp+120h+var_180]
0x18002e0a7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002e0ac  mov     rdx, rax
0x18002e0af  mov     rcx, rsi
0x18002e0b2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002e0b7  lea     rcx, [rbp+120h+var_180]
0x18002e0bb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e0c0  nop
0x18002e0c1  lea     rcx, [rbp+120h+var_160]
0x18002e0c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e0ca  nop
0x18002e0cb  lea     rcx, [rbp+120h+var_140]
0x18002e0cf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e0d4  nop
0x18002e0d5  lea     rcx, [rbp+120h+var_120]
0x18002e0d9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e0de  nop
0x18002e0df  lea     rcx, [rbp+120h+var_100]
0x18002e0e3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e0e8  nop
0x18002e0e9  lea     rcx, [rbp+120h+var_E0]
0x18002e0ed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e0f2  nop
0x18002e0f3  lea     rcx, [rbp+120h+var_C0]
0x18002e0f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e0fc  nop
0x18002e0fd  lea     rcx, [rsp+220h+var_1E0]
0x18002e102  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e107  nop
0x18002e108  lea     rcx, [rbp+120h+var_A0]
0x18002e10f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e114  nop
0x18002e115  lea     rcx, [rsp+220h+var_1C0]
0x18002e11a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e11f  nop
0x18002e120  lea     rcx, [rbp+120h+var_80]
0x18002e127  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e12c  nop
0x18002e12d  lea     rcx, [rbp+120h+var_1A0]
0x18002e131  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e136  nop
0x18002e137  mov     rcx, [r14]
0x18002e13a  mov     qword ptr [r14], 0
0x18002e141  test    rcx, rcx
0x18002e144  jz      short loc_18002E153
0x18002e146  mov     rax, [rcx]
0x18002e149  mov     rax, [rax+10h]
0x18002e14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e152  nop
0x18002e153  mov     [rsp+220h+ppv], r14; ppv
0x18002e158  lea     r9, _GUID_7b816b45_1996_4476_b132_de9e247c8af0; riid
0x18002e15f  xor     edx, edx; pUnkOuter
0x18002e161  lea     r8d, [rdx+1]; dwClsContext
0x18002e165  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18002e16c  call    cs:__imp_CoCreateInstance
0x18002e173  nop     dword ptr [rax+rax+00h]
0x18002e178  mov     rcx, [rbp+128h]; this
0x18002e17f  lea     rdx, aFailedToCreate; "Failed to create WIC factory"
0x18002e186  mov     [rsp+220h+ppv], rdx; int
0x18002e18b  mov     r9d, eax; char *
0x18002e18e  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002e195  mov     edx, 43h ; 'C'; void *
0x18002e19a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002e19f  nop
0x18002e1a0  mov     rax, rbx
0x18002e1a3  mov     rcx, [rbp+120h+var_30]
0x18002e1aa  xor     rcx, rsp; StackCookie
0x18002e1ad  call    __security_check_cookie
0x18002e1b2  lea     r11, [rsp+220h+var_20]
0x18002e1ba  mov     rbx, [r11+40h]
0x18002e1be  mov     rsi, [r11+48h]
0x18002e1c2  mov     rsp, r11
0x18002e1c5  pop     r15
0x18002e1c7  pop     r14
0x18002e1c9  pop     r12
0x18002e1cb  pop     rdi
0x18002e1cc  pop     rbp
0x18002e1cd  retn
```

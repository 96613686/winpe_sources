# CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>(std::shared_ptr<CRdpIdMonitor> const &,Rdp::Avenc::ICpuFrameProcessor *)

- ea: `0x18002da80`
- end: `0x18002de23`
- name: `??0?$CFrameDumper@UICpuFrameProcessor@Avenc@Rdp@@@@QEAA@AEBV?$shared_ptr@VCRdpIdMonitor@@@std@@PEAUICpuFrameProcessor@Avenc@Rdp@@@Z`
- size: `931`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023b6c`

## callees

- `0x180006f60`
- `0x1800107ec`
- `0x180013bb0`
- `0x18001ddf4`
- `0x18002d684`
- `0x18002d6cc`
- `0x18002d6f0`
- `0x18002da80`
- `0x18002e214`
- `0x18002e6a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ddc0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ddc0`

## string_xrefs

- `0x18002ddd3`: `Failed to create WIC factory`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>::CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>(
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
  *(_QWORD *)(a1 + 8) = &CCpuFrameDumper::`vftable'{for `winrt::impl::root_implements<CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>,Rdp::Avenc::ICpuFrameProcessor>'};
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
0x18002da80  mov     [rsp-8+arg_10], rbx
0x18002da85  mov     [rsp-8+arg_18], rsi
0x18002da8a  push    rbp
0x18002da8b  push    rdi
0x18002da8c  push    r12
0x18002da8e  push    r14
0x18002da90  push    r15
0x18002da92  lea     rbp, [rsp-100h]
0x18002da9a  sub     rsp, 200h
0x18002daa1  mov     rax, cs:__security_cookie
0x18002daa8  xor     rax, rsp
0x18002daab  mov     [rbp+120h+var_30], rax
0x18002dab2  mov     rsi, rdx
0x18002dab5  mov     rbx, rcx
0x18002dab8  mov     [rsp+220h+var_1E8], rcx
0x18002dabd  lea     rax, ??_7?$producers_base@V?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@V?$tuple@UIGpuFrameProcessor@Avenc@Rdp@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,std::tuple<Rdp::Avenc::IGpuFrameProcessor>>::`vftable'
0x18002dac4  mov     [rcx], rax
0x18002dac7  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18002dace  mov     qword ptr [rcx+10h], 1
0x18002dad6  lea     rax, ??_7?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@6B?$producers_base@V?$CFrameDumper@UIGpuFrameProcessor@Avenc@Rdp@@@@V?$tuple@UIGpuFrameProcessor@Avenc@Rdp@@@std@@@impl@winrt@@@; const CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>::`vftable'{for `winrt::impl::producers_base<CFrameDumper<Rdp::Avenc::IGpuFrameProcessor>,std::tuple<Rdp::Avenc::IGpuFrameProcessor>>'}
0x18002dadd  mov     [rcx], rax
0x18002dae0  lea     rax, ??_7CCpuFrameDumper@@6B?$root_implements@V?$CFrameDumper@UICpuFrameProcessor@Avenc@Rdp@@@@UICpuFrameProcessor@Avenc@Rdp@@@impl@winrt@@@; const CCpuFrameDumper::`vftable'{for `winrt::impl::root_implements<CFrameDumper<Rdp::Avenc::ICpuFrameProcessor>,Rdp::Avenc::ICpuFrameProcessor>'}
0x18002dae7  mov     [rcx+8], rax
0x18002daeb  lea     r14, [rcx+18h]
0x18002daef  mov     qword ptr [r14], 0
0x18002daf6  mov     [rcx+20h], r8
0x18002dafa  test    r8, r8
0x18002dafd  jz      short loc_18002DB0F
0x18002daff  mov     rax, [r8]
0x18002db02  mov     rcx, r8
0x18002db05  mov     rax, [rax+8]
0x18002db09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db0e  nop
0x18002db0f  lea     rdi, [rbx+28h]
0x18002db13  mov     rdx, rsi
0x18002db16  mov     rcx, rdi
0x18002db19  call    ??0?$shared_ptr@VCRdpIdAdapter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CRdpIdAdapter>::shared_ptr<CRdpIdAdapter>(std::shared_ptr<CRdpIdAdapter> const &)
0x18002db1e  nop
0x18002db1f  lea     rsi, [rbx+38h]
0x18002db23  xorps   xmm0, xmm0
0x18002db26  movups  xmmword ptr [rsi], xmm0
0x18002db29  mov     qword ptr [rsi+10h], 0
0x18002db31  mov     qword ptr [rsi+18h], 7
0x18002db39  xor     eax, eax
0x18002db3b  mov     [rsi], ax
0x18002db3e  mov     [rbx+58h], eax
0x18002db41  lea     r9, [rbp+120h+var_36]
0x18002db48  mov     rax, [rdi]
0x18002db4b  mov     r8d, [rax+118h]
0x18002db52  mov     r15d, 0CCCCCCCDh
0x18002db58  sub     r9, 2
0x18002db5c  mov     eax, r15d
0x18002db5f  mul     r8d
0x18002db62  shr     edx, 3
0x18002db65  movzx   eax, dx
0x18002db68  shl     ax, 2
0x18002db6c  lea     ecx, [rax+rdx]
0x18002db6f  add     cx, cx
0x18002db72  sub     r8w, cx
0x18002db76  add     r8w, 30h ; '0'
0x18002db7b  mov     [r9], r8w
0x18002db7f  mov     r8d, edx
0x18002db82  test    edx, edx
0x18002db84  jnz     short loc_18002DB58
0x18002db86  lea     r8, [rbp+120h+var_36]
0x18002db8d  mov     rdx, r9
0x18002db90  lea     rcx, [rbp+120h+var_1A0]
0x18002db94  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18002db99  nop
0x18002db9a  lea     rdx, aMonitor; "_Monitor_"
0x18002dba1  lea     rcx, [rbp+120h+var_80]
0x18002dba8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002dbad  mov     r12, rax
0x18002dbb0  lea     r9, [rbp+120h+var_36]
0x18002dbb7  mov     rax, [rdi]
0x18002dbba  mov     rcx, [rax+0E8h]
0x18002dbc1  mov     r8d, [rcx+204h]
0x18002dbc8  sub     r9, 2
0x18002dbcc  mov     eax, r15d
0x18002dbcf  mul     r8d
0x18002dbd2  shr     edx, 3
0x18002dbd5  movzx   eax, dx
0x18002dbd8  shl     ax, 2
0x18002dbdc  lea     ecx, [rax+rdx]
0x18002dbdf  add     cx, cx
0x18002dbe2  sub     r8w, cx
0x18002dbe6  add     r8w, 30h ; '0'
0x18002dbeb  mov     [r9], r8w
0x18002dbef  mov     r8d, edx
0x18002dbf2  test    edx, edx
0x18002dbf4  jnz     short loc_18002DBC8
0x18002dbf6  lea     r8, [rbp+120h+var_36]
0x18002dbfd  mov     rdx, r9
0x18002dc00  lea     rcx, [rsp+220h+var_1C0]
0x18002dc05  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18002dc0a  nop
0x18002dc0b  lea     rdx, aSession; "_Session_"
0x18002dc12  lea     rcx, [rbp+120h+var_A0]
0x18002dc19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002dc1e  mov     r15, rax
0x18002dc21  lea     r9, [rbp+120h+var_36]
0x18002dc28  mov     rax, [rdi]
0x18002dc2b  mov     rcx, [rax+0E8h]
0x18002dc32  mov     r8d, [rcx+208h]
0x18002dc39  sub     r9, 2
0x18002dc3d  mov     eax, 0CCCCCCCDh
0x18002dc42  mul     r8d
0x18002dc45  shr     edx, 3
0x18002dc48  movzx   eax, dx
0x18002dc4b  shl     ax, 2
0x18002dc4f  lea     ecx, [rax+rdx]
0x18002dc52  add     cx, cx
0x18002dc55  sub     r8w, cx
0x18002dc59  add     r8w, 30h ; '0'
0x18002dc5e  mov     [r9], r8w
0x18002dc62  mov     r8d, edx
0x18002dc65  test    edx, edx
0x18002dc67  jnz     short loc_18002DC39
0x18002dc69  lea     r8, [rbp+120h+var_36]
0x18002dc70  mov     rdx, r9
0x18002dc73  lea     rcx, [rsp+220h+var_1E0]
0x18002dc78  call    ??$?0PEAG$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEAG0AEBV?$allocator@G@1@@Z; std::wstring::wstring(ushort *,ushort *,std::allocator<ushort> const &)
0x18002dc7d  nop
0x18002dc7e  lea     rdx, aFramedumpTermi; "FrameDump_TerminalLuid_"
0x18002dc85  lea     rcx, [rbp+120h+var_C0]
0x18002dc89  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002dc8e  mov     r8, rax
0x18002dc91  mov     rax, [rdi]
0x18002dc94  mov     rdx, [rax+0E8h]
0x18002dc9b  add     rdx, 1D8h
0x18002dca2  lea     rcx, [rbp+120h+var_E0]
0x18002dca6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x18002dcab  nop
0x18002dcac  lea     r8, [rsp+220h+var_1E0]
0x18002dcb1  mov     rdx, rax
0x18002dcb4  lea     rcx, [rbp+120h+var_100]
0x18002dcb8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002dcbd  nop
0x18002dcbe  mov     r8, r15
0x18002dcc1  mov     rdx, rax
0x18002dcc4  lea     rcx, [rbp+120h+var_120]
0x18002dcc8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002dccd  nop
0x18002dcce  lea     r8, [rsp+220h+var_1C0]
0x18002dcd3  mov     rdx, rax
0x18002dcd6  lea     rcx, [rbp+120h+var_140]
0x18002dcda  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002dcdf  nop
0x18002dce0  mov     r8, r12
0x18002dce3  mov     rdx, rax
0x18002dce6  lea     rcx, [rbp+120h+var_160]
0x18002dcea  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002dcef  nop
0x18002dcf0  lea     r8, [rbp+120h+var_1A0]
0x18002dcf4  mov     rdx, rax
0x18002dcf7  lea     rcx, [rbp+120h+var_180]
0x18002dcfb  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18002dd00  mov     rdx, rax
0x18002dd03  mov     rcx, rsi
0x18002dd06  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002dd0b  lea     rcx, [rbp+120h+var_180]
0x18002dd0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd14  nop
0x18002dd15  lea     rcx, [rbp+120h+var_160]
0x18002dd19  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd1e  nop
0x18002dd1f  lea     rcx, [rbp+120h+var_140]
0x18002dd23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd28  nop
0x18002dd29  lea     rcx, [rbp+120h+var_120]
0x18002dd2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd32  nop
0x18002dd33  lea     rcx, [rbp+120h+var_100]
0x18002dd37  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd3c  nop
0x18002dd3d  lea     rcx, [rbp+120h+var_E0]
0x18002dd41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd46  nop
0x18002dd47  lea     rcx, [rbp+120h+var_C0]
0x18002dd4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd50  nop
0x18002dd51  lea     rcx, [rsp+220h+var_1E0]
0x18002dd56  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd5b  nop
0x18002dd5c  lea     rcx, [rbp+120h+var_A0]
0x18002dd63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd68  nop
0x18002dd69  lea     rcx, [rsp+220h+var_1C0]
0x18002dd6e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd73  nop
0x18002dd74  lea     rcx, [rbp+120h+var_80]
0x18002dd7b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd80  nop
0x18002dd81  lea     rcx, [rbp+120h+var_1A0]
0x18002dd85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd8a  nop
0x18002dd8b  mov     rcx, [r14]
0x18002dd8e  mov     qword ptr [r14], 0
0x18002dd95  test    rcx, rcx
0x18002dd98  jz      short loc_18002DDA7
0x18002dd9a  mov     rax, [rcx]
0x18002dd9d  mov     rax, [rax+10h]
0x18002dda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dda6  nop
0x18002dda7  mov     [rsp+220h+ppv], r14; ppv
0x18002ddac  lea     r9, _GUID_7b816b45_1996_4476_b132_de9e247c8af0; riid
0x18002ddb3  xor     edx, edx; pUnkOuter
0x18002ddb5  lea     r8d, [rdx+1]; dwClsContext
0x18002ddb9  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18002ddc0  call    cs:__imp_CoCreateInstance
0x18002ddc7  nop     dword ptr [rax+rax+00h]
0x18002ddcc  mov     rcx, [rbp+128h]; this
0x18002ddd3  lea     rdx, aFailedToCreate; "Failed to create WIC factory"
0x18002ddda  mov     [rsp+220h+ppv], rdx; int
0x18002dddf  mov     r9d, eax; char *
0x18002dde2  lea     r8, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18002dde9  mov     edx, 43h ; 'C'; void *
0x18002ddee  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ddf3  nop
0x18002ddf4  mov     rax, rbx
0x18002ddf7  mov     rcx, [rbp+120h+var_30]
0x18002ddfe  xor     rcx, rsp; StackCookie
0x18002de01  call    __security_check_cookie
0x18002de06  lea     r11, [rsp+220h+var_20]
0x18002de0e  mov     rbx, [r11+40h]
0x18002de12  mov     rsi, [r11+48h]
0x18002de16  mov     rsp, r11
0x18002de19  pop     r15
0x18002de1b  pop     r14
0x18002de1d  pop     r12
0x18002de1f  pop     rdi
0x18002de20  pop     rbp
0x18002de21  retn
```

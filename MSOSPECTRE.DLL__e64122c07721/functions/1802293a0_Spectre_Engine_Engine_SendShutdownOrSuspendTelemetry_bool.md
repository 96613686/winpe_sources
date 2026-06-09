# Spectre::Engine::Engine::SendShutdownOrSuspendTelemetry(bool)

- ea: `0x1802293a0`
- end: `0x180229c26`
- name: `?SendShutdownOrSuspendTelemetry@Engine@1Spectre@@IEAAX_N@Z`
- size: `2182`
- prototype: `void __fastcall(Spectre::Engine::Engine *__hidden this, bool)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18021f290`
- `0x180229c30`

## callees

- `0x1800157b0`
- `0x180016430`
- `0x180017670`
- `0x18001dea0`
- `0x180035110`
- `0x180038200`
- `0x18009ae60`
- `0x1801b51d0`
- `0x1801cc160`
- `0x18021d3f0`
- `0x18021fa60`
- `0x1802293a0`
- `0x180263b30`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039e610`
- `0x18039ebb0`
- `0x1803a0e20`
- `0x1803a0e50`
- `0x1803a0e60`
- `0x1803a0e70`
- `0x1803a0e96`
- `0x1803a0f8f`
- `0x1803a1c20`
- `0x1804f99e0`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x180229411`
- `KERNEL32!GetCurrentProcess` at `0x180229411`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180229776`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180229820`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802298ca`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180229a0f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180229bc6`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180229776`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180229820`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1802298ca`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180229a0f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x180229bc6`

## string_xrefs

- `0x1802296fa`: `Min Time Per-render-update`
- `0x1802297ac`: `Avg Time Per-render-update`
- `0x180229856`: `Max Time Per-render-update`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Spectre::Engine::Engine::SendShutdownOrSuspendTelemetry(Spectre::Engine::Engine *this, char a2)
{
  Spectre::Engine::Engine *v2; // rsi
  float v3; // xmm6_4
  HANDLE CurrentProcess; // rax
  SIZE_T v5; // r13
  __int64 v6; // rdi
  signed __int64 v7; // rsi
  __int64 v8; // r14
  __int64 v9; // r15
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  _QWORD *v12; // r12
  int v13; // r13d
  bool v14; // zf
  float v15; // xmm6_4
  _QWORD *v16; // rax
  std::exception **v17; // r13
  __int64 v18; // rax
  __int128 v19; // xmm6
  _DWORD *v20; // r14
  __int64 v21; // rax
  _BYTE *v22; // rcx
  _BYTE *v23; // rcx
  _BYTE *v24; // rcx
  __int64 v25; // rbx
  _QWORD *v26; // rax
  void *v27; // rcx
  __int64 *v28; // rdi
  __int64 *v29; // rbx
  _BYTE *v30; // rcx
  __int64 perf_frequency_0; // rbx
  __int64 perf_counter_0; // rax
  int v33; // eax
  __int64 v34; // r10
  void *p_Block; // r8
  __int64 v36; // rdx
  void (__fastcall *v37)(_QWORD, __int64, void *); // rax
  _BYTE *v38; // rcx
  __int64 *v39; // rbp
  __int64 v40; // rax
  __int64 v41; // r8
  __int64 *v42; // rdx
  __int64 v43; // [rsp+0h] [rbp-198h] BYREF
  int v44; // [rsp+30h] [rbp-168h]
  void *v45[2]; // [rsp+38h] [rbp-160h] BYREF
  __int128 v46; // [rsp+50h] [rbp-148h] BYREF
  Spectre::Engine::Engine *v47; // [rsp+60h] [rbp-138h]
  void **v48; // [rsp+68h] [rbp-130h] BYREF
  _DWORD *v49; // [rsp+70h] [rbp-128h]
  Spectre::Engine::Engine *v50; // [rsp+78h] [rbp-120h]
  Spectre::Engine::Engine *v51; // [rsp+80h] [rbp-118h]
  _QWORD v52[2]; // [rsp+88h] [rbp-110h] BYREF
  __m128i si128; // [rsp+98h] [rbp-100h]
  float v54; // [rsp+A8h] [rbp-F0h]
  std::exception *v55[3]; // [rsp+B0h] [rbp-E8h] BYREF
  __int64 v56; // [rsp+C8h] [rbp-D0h]
  void *Block; // [rsp+D0h] [rbp-C8h] BYREF
  __int64 v58; // [rsp+D8h] [rbp-C0h]
  __int64 v59; // [rsp+E0h] [rbp-B8h]
  unsigned __int64 v60; // [rsp+E8h] [rbp-B0h]
  void *v61[2]; // [rsp+F0h] [rbp-A8h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+100h] [rbp-98h] BYREF

  v2 = this;
  v47 = this;
  v50 = this;
  v51 = this;
  if ( !*((_QWORD *)this + 60) )
  {
    if ( !*((_QWORD *)this + 62) )
      return;
    v3 = FLOAT_1000000_0;
    goto LABEL_50;
  }
  CurrentProcess = GetCurrentProcess();
  K32GetProcessMemoryInfo_0(CurrentProcess, &ppsmemCounters, 0x48u);
  v5 = ppsmemCounters.PeakWorkingSetSize - *((_QWORD *)v2 + 213);
  v45[0] = (void *)v5;
  v44 = 0;
  v6 = 0x7FFFFFFFFFFFFFFFLL;
  v7 = 0x8000000000000000uLL;
  v8 = 0;
  LODWORD(v9) = 0;
  v10 = (_QWORD *)*((_QWORD *)v47 + 21);
  v11 = (_QWORD *)*v10;
  if ( (_QWORD *)*v10 != v10 )
  {
    v12 = (_QWORD *)*((_QWORD *)v47 + 21);
    v13 = 0;
    do
    {
      Spectre::Engine::Display::GetDisplayRenderTiming(v11[2], &Block);
      if ( (_DWORD)Block )
      {
        if ( v58 < v6 )
          v6 = v58;
        if ( v7 < (__int64)v60 )
          v7 = v60;
        v8 += v59 * (unsigned int)Block;
        v13 += (int)Block;
      }
      v11 = (_QWORD *)*v11;
    }
    while ( v11 != v12 );
    v44 = v13;
    v14 = v13 == 0;
    v5 = (SIZE_T)v45[0];
    if ( !v14 )
      v9 = v8 / v44;
  }
  *(_OWORD *)v61 = 0;
  if ( (v5 & 0x8000000000000000uLL) != 0LL )
    v15 = (float)(int)(v5 & 1 | (v5 >> 1)) + (float)(int)(v5 & 1 | (v5 >> 1));
  else
    v15 = (float)(int)v5;
  v52[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  std::string::assign(v52);
  v54 = v15;
  v61[0] = 0;
  v61[1] = 0;
  v16 = operator new(0x48u);
  v45[0] = v16;
  *v16 = v16;
  v16[1] = v16;
  v16[2] = v16;
  *((_WORD *)v16 + 12) = 257;
  *(_QWORD *)&v46 = v16;
  v61[0] = v16;
  v17 = (std::exception **)v52;
  while ( 1 )
  {
    v18 = std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Find_hint<std::string>(
            v61,
            &Block,
            v16,
            v17);
    v19 = *(_OWORD *)v18;
    v56 = *(_QWORD *)(v18 + 16);
    if ( !(_BYTE)v56 )
    {
      if ( v61[1] == (void *)0x38E38E38E38E38ELL )
        std::_Throw_tree_length_error();
      v48 = v61;
      v49 = 0;
      v20 = operator new(0x48u);
      v49 = v20;
      std::string::string(v20 + 8, v17);
      v20[16] = *((_DWORD *)v17 + 8);
      v21 = v46;
      *(_QWORD *)v20 = v46;
      *((_QWORD *)v20 + 1) = v21;
      *((_QWORD *)v20 + 2) = v21;
      *((_WORD *)v20 + 12) = 0;
      v49 = 0;
      v46 = v19;
      std::_Tree_val<std::_Tree_simple_types<std::pair<enum Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>>>::_Insert_node(
        v61,
        &v46,
        v20);
      *(void **)&v46 = v61[0];
    }
    v17 += 5;
    if ( v17 == v55 )
      break;
    v16 = v45[0];
  }
  `eh vector destructor iterator'(
    v52,
    0x28u,
    1u,
    std::pair<std::string const,enum Microsoft::glTF::SchemaFlags>::~pair<std::string const,enum Microsoft::glTF::SchemaFlags>);
  if ( v44 )
  {
    Block = 0;
    v59 = 0;
    v60 = 15;
    std::string::assign(&Block);
    v3 = FLOAT_1000000_0;
    *(float *)std::map<std::string,float>::operator[](v61, &Block) = (float)(int)v6 / 1000000.0;
    if ( v60 >= 0x10 )
    {
      v22 = Block;
      if ( v60 + 1 >= 0x1000 )
      {
        v22 = (_BYTE *)*((_QWORD *)Block - 1);
        if ( (unsigned __int64)((_BYTE *)Block - v22 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v22);
    }
    Block = 0;
    v59 = 0;
    v60 = 15;
    std::string::assign(&Block);
    *(float *)std::map<std::string,float>::operator[](v61, &Block) = (float)(int)v9 / 1000000.0;
    if ( v60 >= 0x10 )
    {
      v23 = Block;
      if ( v60 + 1 >= 0x1000 )
      {
        v23 = (_BYTE *)*((_QWORD *)Block - 1);
        if ( (unsigned __int64)((_BYTE *)Block - v23 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v23);
    }
    Block = 0;
    v59 = 0;
    v60 = 15;
    std::string::assign(&Block);
    *(float *)std::map<std::string,float>::operator[](v61, &Block) = (float)(int)v7 / 1000000.0;
    if ( v60 >= 0x10 )
    {
      v24 = Block;
      if ( v60 + 1 >= 0x1000 )
      {
        v24 = (_BYTE *)*((_QWORD *)Block - 1);
        if ( (unsigned __int64)((_BYTE *)Block - v24 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v24);
    }
  }
  else
  {
    v3 = FLOAT_1000000_0;
  }
  Block = 0;
  v59 = 0;
  v60 = 15;
  std::string::assign(&Block);
  v2 = v47;
  v25 = *((_QWORD *)v47 + 60);
  *(_OWORD *)v45 = 0;
  v26 = operator new(0x60u);
  *v26 = v26;
  v26[1] = v26;
  v26[2] = v26;
  *((_WORD *)v26 + 12) = 257;
  v45[0] = v26;
  (*(void (__fastcall **)(__int64, void **, void **, void **))(*(_QWORD *)v25 + 40LL))(v25, &Block, v45, v61);
  v27 = v45[0];
  v28 = (__int64 *)*((_QWORD *)v45[0] + 1);
  if ( !*((_BYTE *)v28 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>>>(
        v45,
        v45,
        v28[2]);
      v29 = v28;
      v28 = (__int64 *)*v28;
      std::pair<std::string const,std::string>::~pair<std::string const,std::string>(v29 + 4);
      operator delete(v29);
    }
    while ( !*((_BYTE *)v28 + 25) );
    v27 = v45[0];
  }
  operator delete(v27);
  if ( v60 >= 0x10 )
  {
    v30 = Block;
    if ( v60 + 1 >= 0x1000 )
    {
      v30 = (_BYTE *)*((_QWORD *)Block - 1);
      if ( (unsigned __int64)((_BYTE *)Block - v30 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v30);
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,double>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,double>,void *>>>(
    v61,
    v61,
    *((_QWORD *)v61[0] + 1));
  operator delete(v61[0]);
  if ( *((_QWORD *)v2 + 62) )
  {
LABEL_50:
    Block = 0;
    v59 = 0;
    v60 = 15;
    std::string::assign(&Block);
    *(_OWORD *)v61 = 0;
    __ExceptionPtrCreate(v61);
    __ExceptionPtrCurrentException(v61);
    if ( __ExceptionPtrToBool(v61) )
    {
      std::exception_ptr::exception_ptr((std::exception_ptr *)&v48, (const struct std::exception_ptr *)v61);
      try
      {
        std::rethrow_exception();
      }
      catch ( std::exception *v55 )
      {
        v42 = &v43;
        v39 = v42;
        v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42[22] + 8LL))(v42[22]);
        v41 = -1;
        do
          ++v41;
        while ( *(_BYTE *)(v40 + v41) );
        std::string::assign(v39 + 26);
        v3 = FLOAT_1000000_0;
        v2 = v50;
        goto LABEL_52;
      }
    }
    __ExceptionPtrDestroy(v61);
LABEL_52:
    perf_frequency_0 = Query_perf_frequency_0();
    perf_counter_0 = Query_perf_counter_0();
    if ( perf_frequency_0 == 10000000 )
      v33 = 100 * perf_counter_0;
    else
      v33 = 1000000000 * (perf_counter_0 / perf_frequency_0)
          + 1000000000 * (perf_counter_0 % perf_frequency_0) / perf_frequency_0;
    v34 = *((_QWORD *)v51 + 62);
    p_Block = &Block;
    v36 = (unsigned int)(int)(float)((float)(v33 - *((_DWORD *)v2 + 428)) / v3);
    if ( a2 )
      v37 = *(void (__fastcall **)(_QWORD, __int64, void *))(*(_QWORD *)v34 + 40LL);
    else
      v37 = *(void (__fastcall **)(_QWORD, __int64, void *))(*(_QWORD *)v34 + 32LL);
    if ( v60 >= 0x10 )
      p_Block = Block;
    v37(*((_QWORD *)v51 + 62), v36, p_Block);
    if ( v60 >= 0x10 )
    {
      v38 = Block;
      if ( v60 + 1 >= 0x1000 )
      {
        v38 = (_BYTE *)*((_QWORD *)Block - 1);
        if ( (unsigned __int64)((_BYTE *)Block - v38 - 8) > 0x1F )
          _invalid_parameter_noinfo_noreturn();
      }
      operator delete(v38);
    }
  }
}

```

## disassembly

```asm
0x1802293a0  mov     rax, rsp
0x1802293a3  mov     [rax+18h], rbx
0x1802293a7  mov     [rax+20h], rsi
0x1802293ab  mov     [rax+10h], dl
0x1802293ae  push    rdi
0x1802293af  push    r12
0x1802293b1  push    r13
0x1802293b3  push    r14
0x1802293b5  push    r15
0x1802293b7  sub     rsp, 170h
0x1802293be  movaps  xmmword ptr [rax-38h], xmm6
0x1802293c2  mov     rax, cs:__security_cookie
0x1802293c9  xor     rax, rsp
0x1802293cc  mov     [rsp+198h+var_48], rax
0x1802293d4  mov     rsi, rcx
0x1802293d7  mov     [rsp+198h+var_138], rcx
0x1802293dc  mov     [rsp+198h+var_120], rcx
0x1802293e1  mov     [rsp+198h+var_118], rcx
0x1802293e9  cmp     qword ptr [rcx+1E0h], 0
0x1802293f1  jnz     short loc_180229411
0x1802293f3  cmp     qword ptr [rcx+1F0h], 0
0x1802293fb  jz      loc_180229BD2
0x180229401  xor     r12d, r12d
0x180229404  movss   xmm6, cs:__real@49742400
0x18022940c  jmp     loc_180229A5D
0x180229411  call    cs:__imp_GetCurrentProcess
0x180229417  mov     rcx, rax; Process
0x18022941a  mov     r8d, 48h ; 'H'; cb
0x180229420  lea     rdx, [rsp+198h+ppsmemCounters]; ppsmemCounters
0x180229428  call    K32GetProcessMemoryInfo_0
0x18022942d  mov     r13, [rsp+198h+ppsmemCounters.PeakWorkingSetSize]
0x180229435  sub     r13, [rsi+6A8h]
0x18022943c  mov     [rsp+198h+var_160], r13
0x180229441  xor     r12d, r12d
0x180229444  mov     [rsp+198h+var_168], r12d
0x180229449  mov     rdi, 7FFFFFFFFFFFFFFFh
0x180229453  mov     rsi, 8000000000000000h
0x18022945d  mov     r14d, r12d
0x180229460  mov     r15d, r12d
0x180229463  mov     rax, [rsp+198h+var_138]
0x180229468  mov     rax, [rax+0A8h]
0x18022946f  mov     rbx, [rax]
0x180229472  cmp     rbx, rax
0x180229475  jz      loc_1802294FD
0x18022947b  mov     r12, rax
0x18022947e  mov     r13d, r14d
0x180229481  lea     rdx, [rsp+198h+Block]
0x180229489  mov     rcx, [rbx+10h]
0x18022948d  call    ?GetDisplayRenderTiming@Display@Engine@Spectre@@QEBA?AUDisplayRenderTiming@123@XZ; Spectre::Engine::Display::GetDisplayRenderTiming(void)
0x180229492  mov     ecx, dword ptr [rsp+198h+Block]
0x180229499  test    ecx, ecx
0x18022949b  jz      short loc_1802294D0
0x18022949d  cmp     [rsp+198h+var_C0], rdi
0x1802294a5  cmovl   rdi, [rsp+198h+var_C0]
0x1802294ae  cmp     rsi, [rsp+198h+var_B0]
0x1802294b6  cmovl   rsi, [rsp+198h+var_B0]
0x1802294bf  mov     eax, ecx
0x1802294c1  imul    rax, [rsp+198h+var_B8]
0x1802294ca  add     r14, rax
0x1802294cd  add     r13d, ecx
0x1802294d0  mov     rax, [rbx]
0x1802294d3  mov     rbx, rax
0x1802294d6  cmp     rax, r12
0x1802294d9  jnz     short loc_180229481
0x1802294db  mov     [rsp+198h+var_168], r13d
0x1802294e0  test    r13d, r13d
0x1802294e3  mov     r12, r15
0x1802294e6  mov     r13, [rsp+198h+var_160]
0x1802294eb  jz      short loc_1802294FD
0x1802294ed  movsxd  rcx, [rsp+198h+var_168]
0x1802294f2  mov     rax, r14
0x1802294f5  cqo
0x1802294f7  idiv    rcx
0x1802294fa  mov     r15, rax
0x1802294fd  xorps   xmm0, xmm0
0x180229500  movups  xmmword ptr [rsp+198h+var_A8], xmm0
0x180229508  xorps   xmm6, xmm6
0x18022950b  test    r13, r13
0x18022950e  js      short loc_180229517
0x180229510  cvtsi2ss xmm6, r13
0x180229515  jmp     short loc_18022952D
0x180229517  mov     rax, r13
0x18022951a  shr     rax, 1
0x18022951d  and     r13d, 1
0x180229521  or      rax, r13
0x180229524  cvtsi2ss xmm6, rax
0x180229529  addss   xmm6, xmm6
0x18022952d  mov     [rsp+198h+var_110], r12
0x180229535  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18022953d  movdqu  [rsp+198h+var_100], xmm0
0x180229546  mov     byte ptr [rsp+198h+var_110], 0
0x18022954e  mov     r8d, 17h
0x180229554  lea     rdx, aEngineMaxMemor; "Engine Max Memory Usage"
0x18022955b  lea     rcx, [rsp+198h+var_110]; void *
0x180229563  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180229568  movss   [rsp+198h+var_F0], xmm6
0x180229571  mov     [rsp+198h+var_A8], r12
0x180229579  mov     [rsp+198h+var_A8+8], r12
0x180229581  mov     ecx, 48h ; 'H'; Size
0x180229586  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022958b  mov     [rsp+198h+var_160], rax
0x180229590  mov     [rax], rax
0x180229593  mov     [rax+8], rax
0x180229597  mov     [rax+10h], rax
0x18022959b  mov     word ptr [rax+18h], 101h
0x1802295a1  mov     qword ptr [rsp+198h+var_148], rax
0x1802295a6  mov     [rsp+198h+var_A8], rax
0x1802295ae  lea     r13, [rsp+198h+var_110]
0x1802295b6  mov     rbx, 38E38E38E38E38Eh
0x1802295c0  mov     r9, r13
0x1802295c3  mov     r8, rax
0x1802295c6  lea     rdx, [rsp+198h+Block]
0x1802295ce  lea     rcx, [rsp+198h+var_A8]
0x1802295d6  call    ??$_Find_hint@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_hint_result@PEAU?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@@1@QEAU?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Find_hint<std::string>(std::_Tree_node<std::string,void *> * const,std::string const &)
0x1802295db  movups  xmm6, xmmword ptr [rax]
0x1802295de  movsd   xmm0, qword ptr [rax+10h]
0x1802295e3  movsd   [rsp+198h+var_D0], xmm0
0x1802295ec  cmp     byte ptr [rsp+198h+var_D0], 0
0x1802295f4  jnz     loc_18022968D
0x1802295fa  cmp     [rsp+198h+var_A8+8], rbx
0x180229602  jz      loc_180229C04
0x180229608  lea     rax, [rsp+198h+var_A8]
0x180229610  mov     [rsp+198h+var_130], rax
0x180229615  mov     [rsp+198h+var_128], r12
0x18022961a  mov     ecx, 48h ; 'H'; Size
0x18022961f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180229624  mov     r14, rax
0x180229627  mov     [rsp+198h+var_128], rax
0x18022962c  mov     rdx, r13
0x18022962f  lea     rcx, [rax+20h]
0x180229633  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180229638  mov     ecx, [r13+20h]
0x18022963c  mov     [r14+40h], ecx
0x180229640  mov     rax, qword ptr [rsp+198h+var_148]
0x180229645  mov     [r14], rax
0x180229648  mov     [r14+8], rax
0x18022964c  mov     [r14+10h], rax
0x180229650  mov     word ptr [r14+18h], 0
0x180229657  mov     [rsp+198h+var_128], r12
0x18022965c  movaps  [rsp+198h+var_148], xmm6
0x180229661  mov     r8, r14
0x180229664  lea     rdx, [rsp+198h+var_148]
0x180229669  lea     rcx, [rsp+198h+var_A8]
0x180229671  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VCommandList@Engine@Spectre@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VCommandList@Engine@Spectre@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VCommandList@Engine@Spectre@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>,void *> *>,std::_Tree_node<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::CommandList>>,void *> * const)
0x180229676  mov     rcx, [rsp+198h+var_A8]
0x18022967e  mov     qword ptr [rsp+198h+var_148], rcx
0x180229683  mov     rbx, 38E38E38E38E38Eh
0x18022968d  add     r13, 28h ; '('
0x180229691  lea     rax, [rsp+198h+var_E8]
0x180229699  cmp     r13, rax
0x18022969c  jz      short loc_1802296A8
0x18022969e  mov     rax, [rsp+198h+var_160]
0x1802296a3  jmp     loc_1802295C0
0x1802296a8  lea     r9, ??1?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4SchemaFlags@glTF@Microsoft@@@std@@QEAA@XZ; void (*)(void *)
0x1802296af  mov     edx, 28h ; '('; unsigned __int64
0x1802296b4  lea     r8d, [rdx-27h]; unsigned __int64
0x1802296b8  lea     rcx, [rsp+198h+var_110]; void *
0x1802296c0  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1802296c5  cmp     [rsp+198h+var_168], 0
0x1802296ca  jz      loc_1802298D8
0x1802296d0  mov     [rsp+198h+Block], r12
0x1802296d8  mov     [rsp+198h+var_B8], r12
0x1802296e0  mov     [rsp+198h+var_B0], 0Fh
0x1802296ec  mov     byte ptr [rsp+198h+Block], 0
0x1802296f4  mov     r8d, 1Ah
0x1802296fa  lea     rdx, aMinTimePerRend; "Min Time Per-render-update"
0x180229701  lea     rcx, [rsp+198h+Block]; void *
0x180229709  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x18022970e  nop
0x18022970f  lea     rdx, [rsp+198h+Block]
0x180229717  lea     rcx, [rsp+198h+var_A8]
0x18022971f  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@MU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@M@std@@@2@@std@@QEAAAEAM$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,float>::operator[](std::string &&)
0x180229724  xorps   xmm0, xmm0
0x180229727  cvtsi2ss xmm0, rdi
0x18022972c  movss   xmm6, cs:__real@49742400
0x180229734  divss   xmm0, xmm6
0x180229738  movss   dword ptr [rax], xmm0
0x18022973c  mov     rdx, [rsp+198h+var_B0]
0x180229744  cmp     rdx, 10h
0x180229748  jb      short loc_180229782
0x18022974a  inc     rdx
0x18022974d  mov     rcx, [rsp+198h+Block]; Block
0x180229755  mov     rax, rcx
0x180229758  cmp     rdx, 1000h
0x18022975f  jb      short loc_18022977D
0x180229761  add     rdx, 27h ; '''
0x180229765  mov     rcx, [rcx-8]
0x180229769  sub     rax, rcx
0x18022976c  add     rax, 0FFFFFFFFFFFFFFF8h
0x180229770  cmp     rax, 1Fh
0x180229774  jbe     short loc_18022977D
0x180229776  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18022977d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180229782  mov     [rsp+198h+Block], r12
0x18022978a  mov     [rsp+198h+var_B8], r12
0x180229792  mov     [rsp+198h+var_B0], 0Fh
0x18022979e  mov     byte ptr [rsp+198h+Block], 0
0x1802297a6  mov     r8d, 1Ah
0x1802297ac  lea     rdx, aAvgTimePerRend; "Avg Time Per-render-update"
0x1802297b3  lea     rcx, [rsp+198h+Block]; void *
0x1802297bb  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1802297c0  nop
0x1802297c1  lea     rdx, [rsp+198h+Block]
0x1802297c9  lea     rcx, [rsp+198h+var_A8]
0x1802297d1  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@MU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@M@std@@@2@@std@@QEAAAEAM$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,float>::operator[](std::string &&)
0x1802297d6  xorps   xmm0, xmm0
0x1802297d9  cvtsi2ss xmm0, r15
0x1802297de  divss   xmm0, xmm6
0x1802297e2  movss   dword ptr [rax], xmm0
0x1802297e6  mov     rdx, [rsp+198h+var_B0]
0x1802297ee  cmp     rdx, 10h
0x1802297f2  jb      short loc_18022982C
0x1802297f4  inc     rdx
0x1802297f7  mov     rcx, [rsp+198h+Block]; Block
0x1802297ff  mov     rax, rcx
0x180229802  cmp     rdx, 1000h
0x180229809  jb      short loc_180229827
0x18022980b  add     rdx, 27h ; '''
0x18022980f  mov     rcx, [rcx-8]
0x180229813  sub     rax, rcx
0x180229816  add     rax, 0FFFFFFFFFFFFFFF8h
0x18022981a  cmp     rax, 1Fh
0x18022981e  jbe     short loc_180229827
0x180229820  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x180229827  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18022982c  mov     [rsp+198h+Block], r12
0x180229834  mov     [rsp+198h+var_B8], r12
0x18022983c  mov     [rsp+198h+var_B0], 0Fh
0x180229848  mov     byte ptr [rsp+198h+Block], 0
0x180229850  mov     r8d, 1Ah
0x180229856  lea     rdx, aMaxTimePerRend; "Max Time Per-render-update"
0x18022985d  lea     rcx, [rsp+198h+Block]; void *
0x180229865  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x18022986a  nop
0x18022986b  lea     rdx, [rsp+198h+Block]
0x180229873  lea     rcx, [rsp+198h+var_A8]
0x18022987b  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@MU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@M@std@@@2@@std@@QEAAAEAM$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,float>::operator[](std::string &&)
0x180229880  xorps   xmm0, xmm0
0x180229883  cvtsi2ss xmm0, rsi
0x180229888  divss   xmm0, xmm6
0x18022988c  movss   dword ptr [rax], xmm0
0x180229890  mov     rdx, [rsp+198h+var_B0]
0x180229898  cmp     rdx, 10h
0x18022989c  jb      short loc_1802298E0
0x18022989e  inc     rdx
0x1802298a1  mov     rcx, [rsp+198h+Block]; Block
0x1802298a9  mov     rax, rcx
0x1802298ac  cmp     rdx, 1000h
0x1802298b3  jb      short loc_1802298D1
0x1802298b5  add     rdx, 27h ; '''
0x1802298b9  mov     rcx, [rcx-8]
0x1802298bd  sub     rax, rcx
0x1802298c0  add     rax, 0FFFFFFFFFFFFFFF8h
0x1802298c4  cmp     rax, 1Fh
0x1802298c8  jbe     short loc_1802298D1
0x1802298ca  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x1802298d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1802298d6  jmp     short loc_1802298E0
0x1802298d8  movss   xmm6, cs:__real@49742400
0x1802298e0  mov     [rsp+198h+Block], r12
0x1802298e8  mov     [rsp+198h+var_B8], r12
0x1802298f0  mov     [rsp+198h+var_B0], 0Fh
0x1802298fc  mov     byte ptr [rsp+198h+Block], 0
0x180229904  mov     r8d, 14h
0x18022990a  lea     rdx, aEngineShutting; "Engine Shutting Down"
0x180229911  lea     rcx, [rsp+198h+Block]; void *
0x180229919  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x18022991e  nop
0x18022991f  mov     rsi, [rsp+198h+var_138]
0x180229924  mov     rbx, [rsi+1E0h]
0x18022992b  xorps   xmm0, xmm0
0x18022992e  movdqu  xmmword ptr [rsp+198h+var_160], xmm0
0x180229934  mov     ecx, 60h ; '`'; Size
0x180229939  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022993e  mov     [rax], rax
0x180229941  mov     [rax+8], rax
0x180229945  mov     [rax+10h], rax
0x180229949  mov     word ptr [rax+18h], 101h
0x18022994f  mov     [rsp+198h+var_160], rax
0x180229954  mov     rax, [rbx]
0x180229957  lea     r9, [rsp+198h+var_A8]
0x18022995f  lea     r8, [rsp+198h+var_160]
0x180229964  lea     rdx, [rsp+198h+Block]
0x18022996c  mov     rcx, rbx
0x18022996f  mov     rax, [rax+28h]
0x180229973  call    cs:__guard_dispatch_icall_fptr
0x180229979  nop
0x18022997a  mov     rcx, [rsp+198h+var_160]
0x18022997f  mov     rdi, [rcx+8]
0x180229983  cmp     byte ptr [rdi+19h], 0
0x180229987  jnz     short loc_1802299CA
0x180229989  nop     dword ptr [rax+00000000h]
0x180229990  mov     r8, [rdi+10h]
0x180229994  lea     rdx, [rsp+198h+var_160]
0x180229999  lea     rcx, [rsp+198h+var_160]
0x18022999e  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>> &,std::_Tree_node<std::pair<std::string const,std::string>,void *> *)
0x1802299a3  mov     rbx, rdi
0x1802299a6  mov     rdi, [rdi]
0x1802299a9  lea     rcx, [rbx+20h]; void *
0x1802299ad  call    ??1?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::string const,std::string>::~pair<std::string const,std::string>(void)
  ... truncated ...
```

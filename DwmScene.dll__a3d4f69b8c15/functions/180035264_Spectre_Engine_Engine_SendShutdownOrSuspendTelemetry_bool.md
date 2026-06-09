# Spectre::Engine::Engine::SendShutdownOrSuspendTelemetry(bool)

- ea: `0x180035264`
- end: `0x180035655`
- name: `?SendShutdownOrSuspendTelemetry@Engine@1Spectre@@IEAAX_N@Z`
- size: `1009`
- prototype: `void __fastcall(Spectre::Engine::Engine *__hidden this, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x180030750`

## callees

- `0x18000ca90`
- `0x18000cab4`
- `0x18000d678`
- `0x180011f64`
- `0x180012ba8`
- `0x180012cd0`
- `0x180014a3c`
- `0x18001d4ac`
- `0x180024420`
- `0x18002f974`
- `0x18002fa14`
- `0x1800301fc`
- `0x180030d48`
- `0x180035264`
- `0x180036e1c`
- `0x1800e7010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800355c6`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800355c6`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800355a5`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800355a5`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800355ba`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800355ba`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180035588`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180035588`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800352c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800352c9`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800352dd`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1800352dd`

## string_xrefs

- `0x180035420`: `Min Time Per-render-update`
- `0x180035463`: `Avg Time Per-render-update`
- `0x1800354a6`: `Max Time Per-render-update`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Spectre::Engine::Engine::SendShutdownOrSuspendTelemetry(Spectre::Engine::Engine *this)
{
  HANDLE CurrentProcess; // rax
  SIZE_T v3; // r15
  int v4; // r12d
  __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // rsi
  _QWORD *v9; // rdx
  _QWORD *i; // rax
  __int64 v11; // r8
  unsigned int v12; // r9d
  float v13; // xmm0_4
  double v14; // xmm0_8
  double v15; // xmm0_8
  double v16; // xmm0_8
  __int64 v17; // rsi
  void (__fastcall *v18)(__int64, _BYTE *, __int64, _QWORD *); // rdi
  __int64 v19; // rbx
  bool v20; // al
  __int64 v21; // rdx
  double v22; // xmm0_8
  __int64 v23; // r10
  __int64 v24; // r9
  __int64 v25; // r11
  __int64 v26; // rax
  __int64 v27; // r8
  _QWORD v28[2]; // [rsp+30h] [rbp-148h] BYREF
  __m256i v29; // [rsp+40h] [rbp-138h] BYREF
  __int128 v30; // [rsp+60h] [rbp-118h] BYREF
  Spectre::Engine::Engine *v31; // [rsp+70h] [rbp-108h]
  char *v32; // [rsp+78h] [rbp-100h]
  stdext::exception *v33; // [rsp+80h] [rbp-F8h] BYREF
  _BYTE v34[32]; // [rsp+88h] [rbp-F0h] BYREF
  _BYTE v35[32]; // [rsp+A8h] [rbp-D0h] BYREF
  float v36; // [rsp+C8h] [rbp-B0h]
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+D0h] [rbp-A8h] BYREF

  v31 = this;
  if ( *((_QWORD *)this + 60) )
  {
    memset_0(&ppsmemCounters, 0, sizeof(ppsmemCounters));
    CurrentProcess = GetCurrentProcess();
    K32GetProcessMemoryInfo(CurrentProcess, &ppsmemCounters, 0x48u);
    v3 = ppsmemCounters.PeakWorkingSetSize - *((_QWORD *)this + 146);
    v4 = 0;
    v5 = 0x7FFFFFFFFFFFFFFFLL;
    v6 = 0x8000000000000000uLL;
    v7 = 0;
    v8 = 0;
    v9 = (_QWORD *)*((_QWORD *)this + 21);
    for ( i = (_QWORD *)*v9; i != v9; i = (_QWORD *)*i )
    {
      v11 = i[2];
      v12 = *(_DWORD *)(v11 + 448);
      *(_OWORD *)((char *)v29.m256i_i64 + 4) = *(_OWORD *)(v11 + 452);
      *(_OWORD *)&v29.m256i_u64[2] = *(_OWORD *)(v11 + 464);
      if ( v12 )
      {
        if ( v29.m256i_i64[1] < v5 )
          v5 = v29.m256i_i64[1];
        if ( v6 < v29.m256i_i64[3] )
          v6 = v29.m256i_i64[3];
        v7 += v29.m256i_i64[2] * v12;
        v4 += v12;
      }
    }
    if ( v4 )
      v8 = v7 / v4;
    std::string::string(v35, "Engine Max Memory Usage");
    if ( (v3 & 0x8000000000000000uLL) != 0LL )
      v13 = (float)(int)(v3 & 1 | (v3 >> 1)) + (float)(int)(v3 & 1 | (v3 >> 1));
    else
      v13 = (float)(int)v3;
    v36 = v13;
    v29.m256i_i64[0] = (__int64)v35;
    v29.m256i_i64[1] = (__int64)&ppsmemCounters;
    std::map<std::string,float>::map<std::string,float>(v28, &v29);
    `eh vector destructor iterator'(v35, 0x28u, 1u, std::pair<std::string const,float>::~pair<std::string const,float>);
    if ( v4 )
    {
      v14 = Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(v5);
      std::string::string(v34, "Min Time Per-render-update");
      *(_DWORD *)std::map<std::string,float>::operator[](v28, v34) = LODWORD(v14);
      std::string::_Tidy_deallocate(v34);
      v15 = Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(v8);
      std::string::string(v34, "Avg Time Per-render-update");
      *(_DWORD *)std::map<std::string,float>::operator[](v28, v34) = LODWORD(v15);
      std::string::_Tidy_deallocate(v34);
      v16 = Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(v6);
      std::string::string(v34, "Max Time Per-render-update");
      *(_DWORD *)std::map<std::string,float>::operator[](v28, v34) = LODWORD(v16);
      std::string::_Tidy_deallocate(v34);
    }
    v17 = *((_QWORD *)this + 60);
    v18 = *(void (__fastcall **)(__int64, _BYTE *, __int64, _QWORD *))(*(_QWORD *)v17 + 40LL);
    v19 = std::map<std::string,std::string>::map<std::string,std::string>(&v29);
    std::string::string(v34, "Engine Shutting Down");
    v18(v17, v34, v19, v28);
    std::string::_Tidy_deallocate(v34);
    std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(&v29);
    std::_Tree<std::_Tmap_traits<std::string,Trace::LevelSettings *,std::less<std::string>,std::allocator<std::pair<std::string const,Trace::LevelSettings *>>,0>>::~_Tree<std::_Tmap_traits<std::string,Trace::LevelSettings *,std::less<std::string>,std::allocator<std::pair<std::string const,Trace::LevelSettings *>>,0>>(v28);
  }
  else if ( !*((_QWORD *)this + 62) )
  {
    return;
  }
  v32 = (char *)this + 496;
  if ( *((_QWORD *)this + 62) )
  {
    std::string::string(v34, &qword_1801687B8);
    std::current_exception(&v29);
    v20 = __ExceptionPtrToBool(&v29);
    try
    {
      if ( v20 )
      {
        v30 = 0;
        __ExceptionPtrCopy(&v30, &v29);
        v28[0] = &v30;
        __ExceptionPtrRethrow(&v30);
      }
      __ExceptionPtrDestroy(&v29);
    }
    catch ( stdext::exception *v33 )
    {
      v26 = (*(__int64 (__fastcall **)(stdext::exception *))(*(_QWORD *)v33 + 8LL))(v33);
      v27 = -1;
      do
        ++v27;
      while ( *(_BYTE *)(v26 + v27) );
      std::string::_Assign<char>(v34, v26);
    }
    std::chrono::steady_clock::now(v28);
    std::_String_val<std::_Simple_types<char>>::_Myptr(v34);
    v22 = Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(v21);
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(v23 + 32))(v25, (unsigned int)(int)*(float *)&v22, v24);
    std::string::_Tidy_deallocate(v34);
  }
}

```

## disassembly

```asm
0x180035264  mov     rax, rsp
0x180035267  push    rbx
0x180035268  push    rsi
0x180035269  push    rdi
0x18003526a  push    r12
0x18003526c  push    r14
0x18003526e  push    r15
0x180035270  sub     rsp, 148h
0x180035277  movaps  xmmword ptr [rax-48h], xmm6
0x18003527b  mov     rax, cs:__security_cookie
0x180035282  xor     rax, rsp
0x180035285  mov     [rsp+178h+var_58], rax
0x18003528d  mov     r14, rcx
0x180035290  mov     [rsp+178h+var_108], rcx
0x180035295  cmp     qword ptr [rcx+1E0h], 0
0x18003529d  jnz     short loc_1800352B2
0x18003529f  cmp     qword ptr [rcx+1F0h], 0
0x1800352a7  jz      loc_18003562C
0x1800352ad  jmp     loc_18003554D
0x1800352b2  mov     ebx, 48h ; 'H'
0x1800352b7  mov     r8d, ebx; Size
0x1800352ba  xor     edx, edx; Val
0x1800352bc  lea     rcx, [rsp+178h+ppsmemCounters]; void *
0x1800352c4  call    memset_0
0x1800352c9  call    cs:__imp_GetCurrentProcess
0x1800352cf  mov     rcx, rax; Process
0x1800352d2  mov     r8d, ebx; cb
0x1800352d5  lea     rdx, [rsp+178h+ppsmemCounters]; ppsmemCounters
0x1800352dd  call    cs:__imp_K32GetProcessMemoryInfo
0x1800352e3  mov     r15, [rsp+178h+ppsmemCounters.PeakWorkingSetSize]
0x1800352eb  sub     r15, [r14+490h]
0x1800352f2  xor     r12d, r12d
0x1800352f5  mov     rbx, 7FFFFFFFFFFFFFFFh
0x1800352ff  mov     rdi, 8000000000000000h
0x180035309  xor     ecx, ecx
0x18003530b  xor     esi, esi
0x18003530d  mov     rdx, [r14+0A8h]
0x180035314  mov     rax, [rdx]
0x180035317  cmp     rax, rdx
0x18003531a  jz      short loc_180035370
0x18003531c  mov     r8, [rax+10h]
0x180035320  mov     r9d, [r8+1C0h]
0x180035327  movups  xmm0, xmmword ptr [r8+1C4h]
0x18003532f  movups  [rsp+178h+var_134], xmm0
0x180035334  movups  xmm1, xmmword ptr [r8+1D0h]
0x18003533c  movups  [rsp+178h+var_134+0Ch], xmm1
0x180035341  test    r9d, r9d
0x180035344  jz      short loc_18003536B
0x180035346  cmp     qword ptr [rsp+178h+var_134+4], rbx
0x18003534b  cmovl   rbx, qword ptr [rsp+178h+var_134+4]
0x180035351  cmp     rdi, [rsp+178h+var_120]
0x180035356  cmovl   rdi, [rsp+178h+var_120]
0x18003535c  mov     r8d, r9d
0x18003535f  imul    r8, qword ptr [rsp+178h+var_134+0Ch]
0x180035365  add     rcx, r8
0x180035368  add     r12d, r9d
0x18003536b  mov     rax, [rax]
0x18003536e  jmp     short loc_180035317
0x180035370  test    r12d, r12d
0x180035373  jz      short loc_180035383
0x180035375  movsxd  r8, r12d
0x180035378  mov     rax, rcx
0x18003537b  cqo
0x18003537d  idiv    r8
0x180035380  mov     rsi, rax
0x180035383  lea     rdx, aEngineMaxMemor; "Engine Max Memory Usage"
0x18003538a  lea     rcx, [rsp+178h+var_D0]
0x180035392  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035397  xorps   xmm0, xmm0
0x18003539a  test    r15, r15
0x18003539d  js      short loc_1800353A6
0x18003539f  cvtsi2ss xmm0, r15
0x1800353a4  jmp     short loc_1800353BC
0x1800353a6  mov     rax, r15
0x1800353a9  shr     rax, 1
0x1800353ac  and     r15d, 1
0x1800353b0  or      rax, r15
0x1800353b3  cvtsi2ss xmm0, rax
0x1800353b8  addss   xmm0, xmm0
0x1800353bc  movss   [rsp+178h+var_B0], xmm0
0x1800353c5  lea     rax, [rsp+178h+var_D0]
0x1800353cd  mov     [rsp+40h], rax
0x1800353d2  lea     rax, [rsp+178h+ppsmemCounters]
0x1800353da  mov     qword ptr [rsp+178h+var_134+4], rax
0x1800353df  lea     rdx, [rsp+178h+var_138]
0x1800353e4  lea     rcx, [rsp+178h+var_148]
0x1800353e9  call    ??0?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@MU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@M@std@@@2@@std@@QEAA@V?$initializer_list@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@M@std@@@1@@Z; std::map<std::string,float>::map<std::string,float>(std::initializer_list<std::pair<std::string const,float>>)
0x1800353ee  nop
0x1800353ef  lea     r9, ??1?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@M@std@@QEAA@XZ; void (*)(void *)
0x1800353f6  mov     edx, 28h ; '('; unsigned __int64
0x1800353fb  lea     r8d, [rdx-27h]; unsigned __int64
0x1800353ff  lea     rcx, [rsp+178h+var_D0]; void *
0x180035407  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003540c  test    r12d, r12d
0x18003540f  jz      loc_1800354DE
0x180035415  mov     rcx, rbx
0x180035418  call    ??$GetDurationMilliseconds@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Engine@Spectre@@YAMV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z; Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::duration<__int64,std::ratio<1,1000000000>>)
0x18003541d  movaps  xmm6, xmm0
0x180035420  lea     rdx, aMinTimePerRend; "Min Time Per-render-update"
0x180035427  lea     rcx, [rsp+178h+var_F0]
0x18003542f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035434  nop
0x180035435  lea     rdx, [rsp+178h+var_F0]
0x18003543d  lea     rcx, [rsp+178h+var_148]
0x180035442  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@MU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@M@std@@@2@@std@@QEAAAEAM$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,float>::operator[](std::string &&)
0x180035447  movss   dword ptr [rax], xmm6
0x18003544b  lea     rcx, [rsp+178h+var_F0]
0x180035453  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180035458  mov     rcx, rsi
0x18003545b  call    ??$GetDurationMilliseconds@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Engine@Spectre@@YAMV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z; Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::duration<__int64,std::ratio<1,1000000000>>)
0x180035460  movaps  xmm6, xmm0
0x180035463  lea     rdx, aAvgTimePerRend; "Avg Time Per-render-update"
0x18003546a  lea     rcx, [rsp+178h+var_F0]
0x180035472  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035477  nop
0x180035478  lea     rdx, [rsp+178h+var_F0]
0x180035480  lea     rcx, [rsp+178h+var_148]
0x180035485  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@MU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@M@std@@@2@@std@@QEAAAEAM$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,float>::operator[](std::string &&)
0x18003548a  movss   dword ptr [rax], xmm6
0x18003548e  lea     rcx, [rsp+178h+var_F0]
0x180035496  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003549b  mov     rcx, rdi
0x18003549e  call    ??$GetDurationMilliseconds@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Engine@Spectre@@YAMV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z; Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::duration<__int64,std::ratio<1,1000000000>>)
0x1800354a3  movaps  xmm6, xmm0
0x1800354a6  lea     rdx, aMaxTimePerRend; "Max Time Per-render-update"
0x1800354ad  lea     rcx, [rsp+178h+var_F0]
0x1800354b5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800354ba  nop
0x1800354bb  lea     rdx, [rsp+178h+var_F0]
0x1800354c3  lea     rcx, [rsp+178h+var_148]
0x1800354c8  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@MU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@M@std@@@2@@std@@QEAAAEAM$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,float>::operator[](std::string &&)
0x1800354cd  movss   dword ptr [rax], xmm6
0x1800354d1  lea     rcx, [rsp+178h+var_F0]
0x1800354d9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800354de  mov     rsi, [r14+1E0h]
0x1800354e5  mov     rax, [rsi]
0x1800354e8  mov     rdi, [rax+28h]
0x1800354ec  lea     rcx, [rsp+178h+var_138]
0x1800354f1  call    ??0?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::string,std::string>::map<std::string,std::string>(void)
0x1800354f6  mov     rbx, rax
0x1800354f9  lea     rdx, aEngineShutting; "Engine Shutting Down"
0x180035500  lea     rcx, [rsp+178h+var_F0]
0x180035508  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003550d  nop
0x18003550e  lea     r9, [rsp+178h+var_148]
0x180035513  mov     r8, rbx
0x180035516  lea     rdx, [rsp+178h+var_F0]
0x18003551e  mov     rcx, rsi
0x180035521  mov     rax, rdi
0x180035524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035529  nop
0x18003552a  lea     rcx, [rsp+178h+var_F0]
0x180035532  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180035537  nop
0x180035538  lea     rcx, [rsp+178h+var_138]
0x18003553d  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x180035542  nop
0x180035543  lea     rcx, [rsp+178h+var_148]
0x180035548  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAVLevelSettings@Trace@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAVLevelSettings@Trace@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,Trace::LevelSettings *,std::less<std::string>,std::allocator<std::pair<std::string const,Trace::LevelSettings *>>,0>>::~_Tree<std::_Tmap_traits<std::string,Trace::LevelSettings *,std::less<std::string>,std::allocator<std::pair<std::string const,Trace::LevelSettings *>>,0>>(void)
0x18003554d  lea     rbx, [r14+1F0h]
0x180035554  mov     [rsp+178h+var_100], rbx
0x180035559  cmp     qword ptr [rbx], 0
0x18003555d  jz      loc_18003562C
0x180035563  lea     rdx, qword_1801687B8
0x18003556a  lea     rcx, [rsp+178h+var_F0]
0x180035572  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035577  nop
0x180035578  lea     rcx, [rsp+178h+var_138]
0x18003557d  call    ?current_exception@std@@YA?AVexception_ptr@1@XZ; std::current_exception(void)
0x180035582  nop
0x180035583  lea     rcx, [rsp+178h+var_138]
0x180035588  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18003558e  test    al, al
0x180035590  jz      short loc_1800355C1
0x180035592  xorps   xmm0, xmm0
0x180035595  movdqu  [rsp+178h+var_118], xmm0
0x18003559b  lea     rdx, [rsp+178h+var_138]
0x1800355a0  lea     rcx, [rsp+178h+var_118]
0x1800355a5  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800355ab  lea     rax, [rsp+178h+var_118]
0x1800355b0  mov     [rsp+178h+var_148], rax
0x1800355b5  lea     rcx, [rsp+178h+var_118]
0x1800355ba  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800355c0  nop
0x1800355c1  lea     rcx, [rsp+178h+var_138]
0x1800355c6  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800355cc  nop
0x1800355cd  jmp     short loc_1800355D9
0x1800355cf  mov     r14, [rsp+178h+var_108]
0x1800355d4  mov     rbx, [rsp+178h+var_100]
0x1800355d9  lea     rcx, [rsp+178h+var_148]
0x1800355de  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800355e3  mov     rdx, [rax]
0x1800355e6  sub     rdx, [r14+498h]
0x1800355ed  mov     r11, [rbx]
0x1800355f0  mov     r10, [r11]
0x1800355f3  lea     rcx, [rsp+178h+var_F0]
0x1800355fb  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180035600  mov     r9, rax
0x180035603  mov     rcx, rdx
0x180035606  call    ??$GetDurationMilliseconds@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Engine@Spectre@@YAMV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z; Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::duration<__int64,std::ratio<1,1000000000>>)
0x18003560b  cvttss2si edx, xmm0
0x18003560f  mov     r8, r9
0x180035612  mov     rcx, r11
0x180035615  mov     rax, [r10+20h]
0x180035619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003561e  nop
0x18003561f  lea     rcx, [rsp+178h+var_F0]
0x180035627  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003562c  mov     rcx, [rsp+178h+var_58]
0x180035634  xor     rcx, rsp; StackCookie
0x180035637  call    __security_check_cookie
0x18003563c  movaps  xmm6, [rsp+178h+var_48]
0x180035644  add     rsp, 148h
0x18003564b  pop     r15
0x18003564d  pop     r14
0x18003564f  pop     r12
0x180035651  pop     rdi
0x180035652  pop     rsi
0x180035653  pop     rbx
0x180035654  retn
```

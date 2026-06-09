# Spectre::Engine::D3D11::RenderOutputD3D11::Present(std::unique_lock<Spectre::Engine::Mutex> &,std::unique_lock<Spectre::Engine::Mutex> &,std::unique_lock<Spectre::Engine::Mutex> &)

- ea: `0x1800ba8f0`
- end: `0x1800bab92`
- name: `?Present@RenderOutputD3D11@D3D11@Engine@Spectre@@UEAAXAEAV?$unique_lock@VMutex@Engine@Spectre@@@std@@00@Z`
- size: `674`
- prototype: `__int64 __fastcall(Spectre::Engine::D3D11::RenderOutputD3D11 *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800baba0`

## callees

- `0x18001128c`
- `0x180012cd0`
- `0x18001daf4`
- `0x180026a2c`
- `0x180026ab0`
- `0x18002a5dc`
- `0x1800b7e3c`
- `0x1800ba5a4`
- `0x1800ba81c`
- `0x1800ba8f0`
- `0x1800babac`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ba98e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ba9db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ba98e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ba9db`

## string_xrefs

- `0x1800baa1b`: `Present() returned DXGI_ERROR_DEVICE_REMOVED`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Spectre::Engine::D3D11::RenderOutputD3D11::Present(
        Spectre::Engine::D3D11::RenderOutputD3D11 *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char v8; // r12
  unsigned int v9; // edi
  unsigned int v10; // ebx
  int v11; // ebx
  unsigned __int64 v12; // r8
  int v13; // r9d
  char v14; // r10
  __int64 v15; // rdx
  __int128 v16; // xmm2
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 result; // rax
  Spectre::Engine::D3D11::RenderDeviceD3D11 *v22; // [rsp+20h] [rbp-69h] BYREF
  std::_Ref_count_base *v23; // [rsp+28h] [rbp-61h]
  unsigned __int64 v24; // [rsp+30h] [rbp-59h]
  unsigned __int64 v25; // [rsp+38h] [rbp-51h]
  int v26; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v27[28]; // [rsp+44h] [rbp-45h] BYREF
  char v28; // [rsp+60h] [rbp-29h]
  int v29; // [rsp+61h] [rbp-28h]
  __int16 v30; // [rsp+65h] [rbp-24h]
  char v31; // [rsp+67h] [rbp-22h]
  unsigned __int128 v32; // [rsp+68h] [rbp-21h]
  _OWORD v33[2]; // [rsp+78h] [rbp-11h]
  __int64 v34; // [rsp+98h] [rbp+Fh]
  char v35; // [rsp+F0h] [rbp+67h]
  char v36; // [rsp+F8h] [rbp+6Fh]
  __int64 v37; // [rsp+100h] [rbp+77h] BYREF
  __int64 v38; // [rsp+108h] [rbp+7Fh] BYREF

  v36 = *(_BYTE *)(a2 + 8);
  if ( v36 )
    std::unique_lock<Spectre::Engine::Mutex>::unlock(a2);
  v8 = *(_BYTE *)(a3 + 8);
  if ( v8 )
    std::unique_lock<Spectre::Engine::Mutex>::unlock(a3);
  v35 = *(_BYTE *)(a4 + 8);
  if ( v35 )
    std::unique_lock<Spectre::Engine::Mutex>::unlock(a4);
  v9 = *((_DWORD *)this + 128);
  v10 = (*(__int64 (__fastcall **)(Spectre::Engine::D3D11::RenderOutputD3D11 *))(*(_QWORD *)this + 312LL))(this);
  v25 = __PAIR64__(v9, v10);
  v26 = 0;
  v28 = 0;
  v24 = *((_QWORD *)this + 60);
  std::chrono::steady_clock::now(&v37);
  QueryPerformanceCounter((LARGE_INTEGER *)&v27[4]);
  (*(void (__fastcall **)(Spectre::Engine::D3D11::RenderOutputD3D11 *, Spectre::Engine::D3D11::RenderDeviceD3D11 **))(*(_QWORD *)this + 320LL))(
    this,
    &v22);
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 63) + 64LL))(
          *((_QWORD *)this + 63),
          v10,
          v9);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v22);
  std::chrono::steady_clock::now(&v38);
  QueryPerformanceCounter((LARGE_INTEGER *)&v27[12]);
  if ( v11 == -2005270523 )
  {
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsRenderOutputD3D11NativeRenderer_,
      3,
      "Present() returned DXGI_ERROR_DEVICE_REMOVED");
  }
  else if ( v11 == -2005270521 )
  {
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsRenderOutputD3D11NativeRenderer_,
      3,
      "Present() returned DXGI_ERROR_DEVICE_RESET");
  }
  else if ( v11 < 0 )
  {
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsRenderOutputD3D11NativeRenderer_,
      3,
      "Present() returned error %08x",
      v11);
  }
  Spectre::Engine::D3D11::RenderOutputD3D11::GetRendererD3D11(this, &v22);
  if ( v22 )
    Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(v22, v11);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  (*(void (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 63) + 136LL))(*((_QWORD *)this + 63), &v26);
  v12 = v24;
  v13 = v26;
  v14 = v28;
  v15 = (*((_DWORD *)this + 411) + 1) % 0x14u;
  *((_DWORD *)this + 411) = v15;
  v32 = __PAIR128__(v25, v12);
  LODWORD(v33[0]) = v13;
  *(_OWORD *)((char *)v33 + 4) = *(_OWORD *)v27;
  v16 = *(_OWORD *)&v27[12];
  LOBYTE(v34) = v14;
  *(_DWORD *)((char *)&v34 + 1) = v29;
  *(_WORD *)((char *)&v34 + 5) = v30;
  HIBYTE(v34) = v31;
  v17 = 56 * v15;
  *(_OWORD *)((char *)this + v17 + 520) = __PAIR128__(v25, v12);
  *(_OWORD *)((char *)this + v17 + 536) = v33[0];
  *(_OWORD *)((char *)this + v17 + 552) = v16;
  *(_QWORD *)((char *)this + v17 + 568) = v34;
  v18 = *((_DWORD *)this + 410) + 1;
  if ( v18 > 0x14 )
    v18 = 20;
  *((_DWORD *)this + 410) = v18;
  Spectre::Engine::D3D11::RenderOutputD3D11::ObtainLatestFrameStats(this);
  Spectre::Engine::D3D11::RenderOutputD3D11::ReconcileFrameStats(this);
  if ( v35 )
    std::unique_lock<Spectre::Engine::Mutex>::lock(a4);
  if ( v8 )
    std::unique_lock<Spectre::Engine::Mutex>::lock(a3);
  if ( v36 )
    std::unique_lock<Spectre::Engine::Mutex>::lock(a2);
  v19 = v37;
  *((_QWORD *)this + 34) = v37;
  v20 = v38;
  *((_QWORD *)this + 35) = v38;
  result = v20 - v19;
  *((_QWORD *)this + 36) = result;
  return result;
}

```

## disassembly

```asm
0x1800ba8f0  push    rbp
0x1800ba8f2  push    rbx
0x1800ba8f3  push    rsi
0x1800ba8f4  push    rdi
0x1800ba8f5  push    r12
0x1800ba8f7  push    r13
0x1800ba8f9  push    r14
0x1800ba8fb  push    r15
0x1800ba8fd  lea     rbp, [rsp-1Fh]
0x1800ba902  sub     rsp, 0A8h
0x1800ba909  mov     r13, r9
0x1800ba90c  mov     r14, r8
0x1800ba90f  mov     r15, rdx
0x1800ba912  mov     rsi, rcx
0x1800ba915  mov     al, [rdx+8]
0x1800ba918  mov     [rbp+57h+arg_8], al
0x1800ba91b  test    al, al
0x1800ba91d  jz      short loc_1800BA927
0x1800ba91f  mov     rcx, rdx
0x1800ba922  call    ?unlock@?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAAXXZ; std::unique_lock<Spectre::Engine::Mutex>::unlock(void)
0x1800ba927  mov     r12b, [r14+8]
0x1800ba92b  test    r12b, r12b
0x1800ba92e  jz      short loc_1800BA938
0x1800ba930  mov     rcx, r14
0x1800ba933  call    ?unlock@?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAAXXZ; std::unique_lock<Spectre::Engine::Mutex>::unlock(void)
0x1800ba938  mov     al, [r13+8]
0x1800ba93c  mov     [rbp+57h+arg_0], al
0x1800ba93f  test    al, al
0x1800ba941  jz      short loc_1800BA94B
0x1800ba943  mov     rcx, r13
0x1800ba946  call    ?unlock@?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAAXXZ; std::unique_lock<Spectre::Engine::Mutex>::unlock(void)
0x1800ba94b  mov     edi, [rsi+200h]
0x1800ba951  mov     rax, [rsi]
0x1800ba954  mov     rcx, rsi
0x1800ba957  mov     rax, [rax+138h]
0x1800ba95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba963  mov     ebx, eax
0x1800ba965  mov     dword ptr [rbp+57h+var_A8], eax
0x1800ba968  mov     dword ptr [rbp+57h+var_A8+4], edi
0x1800ba96b  mov     [rbp+57h+var_A0], 0
0x1800ba972  mov     [rbp+57h+var_80], 0
0x1800ba976  mov     rcx, [rsi+1E0h]
0x1800ba97d  mov     [rbp+57h+var_B0], rcx
0x1800ba981  lea     rcx, [rbp+57h+arg_10]
0x1800ba985  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800ba98a  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1800ba98e  call    cs:__imp_QueryPerformanceCounter
0x1800ba994  mov     rcx, [rsi]
0x1800ba997  mov     rax, [rcx+140h]
0x1800ba99e  lea     rdx, [rbp+57h+var_C0]
0x1800ba9a2  mov     rcx, rsi
0x1800ba9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba9aa  nop
0x1800ba9ab  mov     rcx, [rsi+1F8h]
0x1800ba9b2  mov     rax, [rcx]
0x1800ba9b5  mov     r8d, edi
0x1800ba9b8  mov     edx, ebx
0x1800ba9ba  mov     rax, [rax+40h]
0x1800ba9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba9c3  mov     ebx, eax
0x1800ba9c5  lea     rcx, [rbp+57h+var_C0]
0x1800ba9c9  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1800ba9ce  lea     rcx, [rbp+57h+arg_18]
0x1800ba9d2  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800ba9d7  lea     rcx, [rbp+57h+var_90]; lpPerformanceCount
0x1800ba9db  call    cs:__imp_QueryPerformanceCounter
0x1800ba9e1  cmp     ebx, 887A0005h
0x1800ba9e7  jz      short loc_1800BAA1B
0x1800ba9e9  cmp     ebx, 887A0007h
0x1800ba9ef  jz      short loc_1800BAA12
0x1800ba9f1  test    ebx, ebx
0x1800ba9f3  jns     short loc_1800BAA33
0x1800ba9f5  mov     r9d, ebx
0x1800ba9f8  lea     r8, aPresentReturne; "Present() returned error %08x"
0x1800ba9ff  mov     edx, 3
0x1800baa04  lea     rcx, ?gTraceLevelsRenderOutputD3D11NativeRenderer_@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsRenderOutputD3D11NativeRenderer_
0x1800baa0b  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1800baa10  jmp     short loc_1800BAA33
0x1800baa12  lea     r8, aPresentReturne_1; "Present() returned DXGI_ERROR_DEVICE_RE"...
0x1800baa19  jmp     short loc_1800BAA22
0x1800baa1b  lea     r8, aPresentReturne_0; "Present() returned DXGI_ERROR_DEVICE_RE"...
0x1800baa22  mov     edx, 3
0x1800baa27  lea     rcx, ?gTraceLevelsRenderOutputD3D11NativeRenderer_@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsRenderOutputD3D11NativeRenderer_
0x1800baa2e  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1800baa33  lea     rdx, [rbp+57h+var_C0]
0x1800baa37  mov     rcx, rsi
0x1800baa3a  call    ?GetRendererD3D11@RenderOutputD3D11@D3D11@Engine@Spectre@@IEBA?AV?$shared_ptr@VRenderDeviceD3D11@D3D11@Engine@Spectre@@@std@@XZ; Spectre::Engine::D3D11::RenderOutputD3D11::GetRendererD3D11(void)
0x1800baa3f  nop
0x1800baa40  mov     rcx, [rbp+57h+var_C0]; this
0x1800baa44  test    rcx, rcx
0x1800baa47  jz      short loc_1800BAA51
0x1800baa49  mov     edx, ebx; int
0x1800baa4b  call    ?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z; Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)
0x1800baa50  nop
0x1800baa51  mov     rcx, [rbp+57h+var_B8]; this
0x1800baa55  test    rcx, rcx
0x1800baa58  jz      short loc_1800BAA5F
0x1800baa5a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800baa5f  mov     rcx, [rsi+1F8h]
0x1800baa66  mov     rax, [rcx]
0x1800baa69  lea     rdx, [rbp+57h+var_A0]
0x1800baa6d  mov     rax, [rax+88h]
0x1800baa74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baa79  mov     r8, [rbp+57h+var_B0]
0x1800baa7d  mov     r9d, [rbp+57h+var_A0]
0x1800baa81  mov     r10b, [rbp+57h+var_80]
0x1800baa85  mov     ecx, [rsi+66Ch]
0x1800baa8b  inc     ecx
0x1800baa8d  mov     eax, 0CCCCCCCDh
0x1800baa92  mul     ecx
0x1800baa94  shr     edx, 4
0x1800baa97  lea     eax, [rdx+rdx*4]
0x1800baa9a  shl     eax, 2
0x1800baa9d  sub     ecx, eax
0x1800baa9f  mov     edx, ecx
0x1800baaa1  mov     [rsi+66Ch], edx
0x1800baaa7  mov     qword ptr [rbp+57h+var_78], r8
0x1800baaab  mov     rax, [rbp+57h+var_A8]
0x1800baaaf  mov     qword ptr [rbp+57h+var_78+8], rax
0x1800baab3  mov     dword ptr [rbp+57h+var_68], r9d
0x1800baab7  movups  xmm0, xmmword ptr [rbp-45h]
0x1800baabb  movups  xmmword ptr [rbp+57h+var_68+4], xmm0
0x1800baabf  movups  xmm2, xmmword ptr [rbp+57h+var_90]
0x1800baac3  mov     byte ptr [rbp+57h+var_48], r10b
0x1800baac7  mov     eax, [rbp+57h+var_7F]
0x1800baaca  mov     dword ptr [rbp+57h+var_48+1], eax
0x1800baacd  movzx   eax, [rbp+57h+var_7B]
0x1800baad1  mov     word ptr [rbp+57h+var_48+5], ax
0x1800baad5  mov     al, [rbp+57h+var_79]
0x1800baad8  mov     byte ptr [rbp+57h+var_48+7], al
0x1800baadb  imul    rax, rdx, 38h ; '8'
0x1800baadf  movups  xmm0, [rbp+57h+var_78]
0x1800baae3  movups  xmmword ptr [rax+rsi+208h], xmm0
0x1800baaeb  movups  xmm1, xmmword ptr [rbp+57h+var_68]
0x1800baaef  movups  xmmword ptr [rax+rsi+218h], xmm1
0x1800baaf7  movups  xmmword ptr [rax+rsi+228h], xmm2
0x1800baaff  movsd   xmm0, [rbp+57h+var_48]
0x1800bab04  movsd   qword ptr [rax+rsi+238h], xmm0
0x1800bab0d  mov     eax, [rsi+668h]
0x1800bab13  inc     eax
0x1800bab15  mov     ecx, 14h
0x1800bab1a  cmp     eax, ecx
0x1800bab1c  cmova   eax, ecx
0x1800bab1f  mov     [rsi+668h], eax
0x1800bab25  mov     rcx, rsi; this
0x1800bab28  call    ?ObtainLatestFrameStats@RenderOutputD3D11@D3D11@Engine@Spectre@@AEAAXXZ; Spectre::Engine::D3D11::RenderOutputD3D11::ObtainLatestFrameStats(void)
0x1800bab2d  mov     rcx, rsi; this
0x1800bab30  call    ?ReconcileFrameStats@RenderOutputD3D11@D3D11@Engine@Spectre@@AEAAXXZ; Spectre::Engine::D3D11::RenderOutputD3D11::ReconcileFrameStats(void)
0x1800bab35  cmp     [rbp+57h+arg_0], 0
0x1800bab39  jz      short loc_1800BAB43
0x1800bab3b  mov     rcx, r13
0x1800bab3e  call    ?lock@?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAAXXZ; std::unique_lock<Spectre::Engine::Mutex>::lock(void)
0x1800bab43  test    r12b, r12b
0x1800bab46  jz      short loc_1800BAB50
0x1800bab48  mov     rcx, r14
0x1800bab4b  call    ?lock@?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAAXXZ; std::unique_lock<Spectre::Engine::Mutex>::lock(void)
0x1800bab50  cmp     [rbp+57h+arg_8], 0
0x1800bab54  jz      short loc_1800BAB5E
0x1800bab56  mov     rcx, r15
0x1800bab59  call    ?lock@?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAAXXZ; std::unique_lock<Spectre::Engine::Mutex>::lock(void)
0x1800bab5e  mov     rcx, [rbp+57h+arg_10]
0x1800bab62  mov     [rsi+110h], rcx
0x1800bab69  mov     rax, [rbp+57h+arg_18]
0x1800bab6d  mov     [rsi+118h], rax
0x1800bab74  sub     rax, rcx
0x1800bab77  mov     [rsi+120h], rax
0x1800bab7e  add     rsp, 0A8h
0x1800bab85  pop     r15
0x1800bab87  pop     r14
0x1800bab89  pop     r13
0x1800bab8b  pop     r12
0x1800bab8d  pop     rdi
0x1800bab8e  pop     rsi
0x1800bab8f  pop     rbx
0x1800bab90  pop     rbp
0x1800bab91  retn
```

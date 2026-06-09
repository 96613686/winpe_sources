# CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(CSM_BUFFER_ATTRIBUTES const &,uint)

- ea: `0x18002f690`
- end: `0x18002f9d5`
- name: `?CreateAndAddSwapChainBuffers@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJAEBUCSM_BUFFER_ATTRIBUTES@@I@Z`
- size: `837`
- prototype: `__int64 __fastcall(CGlobalCompositionSurfaceInfo::CBindInfo *__hidden this, const struct CSM_BUFFER_ATTRIBUTES *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f294`

## callees

- `0x180009bf8`
- `0x18000a254`
- `0x18002f690`
- `0x18002f9dc`
- `0x180030178`
- `0x18003044c`
- `0x180030cb8`
- `0x180030e04`
- `0x180042de0`
- `0x180053b90`
- `0x1800d5b30`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f832`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f832`
- `win32u!NtOpenCompositionSurfaceRealizationInfo` at `0x18002f720`
- `win32u!NtOpenCompositionSurfaceRealizationInfo` at `0x18002f720`

## pseudocode

```c
__int64 __fastcall CGlobalCompositionSurfaceInfo::CBindInfo::CreateAndAddSwapChainBuffers(
        CGlobalCompositionSurfaceInfo::CBindInfo *this,
        const struct CSM_BUFFER_ATTRIBUTES *a2,
        unsigned int a3)
{
  __int64 *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // r9
  int v10; // eax
  __int64 v11; // r9
  int v12; // eax
  unsigned int v13; // edi
  unsigned __int64 v14; // r8
  unsigned int i; // r12d
  __int64 v16; // rdx
  __int64 v17; // r13
  int v18; // eax
  struct ISwapChainRealization *v19; // rbx
  unsigned int j; // ebx
  void *v21; // rcx
  __int64 v23; // rcx
  unsigned __int64 v24; // [rsp+30h] [rbp-48h]
  struct ISwapChainRealization *v25; // [rsp+38h] [rbp-40h] BYREF
  __int128 v26; // [rsp+40h] [rbp-38h] BYREF
  __int64 v27; // [rsp+50h] [rbp-28h]
  __int128 v28; // [rsp+58h] [rbp-20h] BYREF
  bool v29; // [rsp+C0h] [rbp+48h]
  unsigned int v31; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v32; // [rsp+D8h] [rbp+60h]

  v31 = a3;
  v27 = 0;
  v26 = 0;
  if ( a3 )
    std::vector<CSM_REALIZATION_INFO>::_Resize_reallocate<std::_Value_init_tag>(&v26, a3);
  v4 = (__int64 *)((char *)this + 72);
  v5 = 0;
  v28 = 0;
  if ( &v28 == (__int128 *)((char *)this + 72) )
  {
    v7 = *((_QWORD *)&v28 + 1);
    v6 = v28;
  }
  else
  {
    v6 = *v4;
    *v4 = 0;
    v7 = *((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = 0;
    v5 = *((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = 0;
  }
  v8 = *(_QWORD *)this;
  v9 = v26;
  *((_BYTE *)this + 183) = 0;
  v32 = v7;
  v10 = NtOpenCompositionSurfaceRealizationInfo(*(_QWORD *)(v8 + 32), (char *)this + 24, &v31, v9);
  if ( v10 < 0 )
  {
    v13 = v10 | 0x10000000;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D3190, 4u, v10 | 0x10000000, 0x64Cu, 0);
    goto LABEL_26;
  }
  if ( v31 <= 1 && *((_DWORD *)this + 8) != 3 )
  {
    v13 = 0;
    v29 = 0;
    LOBYTE(v11) = 0;
LABEL_10:
    v14 = 0;
    v24 = 0;
    for ( i = 0; i < v31; ++i )
    {
      v16 = 5LL * i;
      v17 = v26 + 40LL * i;
      if ( *(_QWORD *)(v17 + 24) )
      {
        while ( 1 )
        {
          if ( v14 >= (v7 - v6) >> 3 )
          {
            LOBYTE(v11) = v29;
            goto LABEL_15;
          }
          v19 = *(struct ISwapChainRealization **)(v6 + 8 * v14);
          *(_QWORD *)(v6 + 8 * v14) = 0;
          v25 = v19;
          v24 = v14 + 1;
          if ( (*(__int64 (__fastcall **)(struct ISwapChainRealization *, __int64, unsigned __int64, __int64))(*(_QWORD *)v19 + 248LL))(
                 v19,
                 v16,
                 v14 + 1,
                 v11) == *(_QWORD *)(v17 + 24) )
            break;
          wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v25);
          v14 = v24;
          v7 = v32;
        }
        if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x8000000) != 0 )
          McTemplateU0x_EventWriteTransfer(v23, &CompSurfInfo_ReuseRealization);
        (*(void (__fastcall **)(struct ISwapChainRealization *, __int64))(*(_QWORD *)v19 + 96LL))(v19, v17);
      }
      else
      {
LABEL_15:
        v25 = 0;
        v18 = CGlobalCompositionSurfaceInfo::CBindInfo::CreateNewRealization(
                (struct CDecodeBitmap **)this,
                a2,
                (const struct CSM_REALIZATION_INFO *)v17,
                v11,
                &v25);
        v13 = v18;
        if ( v18 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D3190, 4u, v18, 0x689u, 0);
          if ( v25 )
            (*(void (__fastcall **)(struct ISwapChainRealization *))(*(_QWORD *)v25 + 16LL))(v25);
          goto LABEL_22;
        }
        v19 = v25;
        *(_QWORD *)(v17 + 8) = 0;
      }
      CGlobalCompositionSurfaceInfo::CBindInfo::AddRealization(this, v19);
      if ( v19 )
        (*(void (__fastcall **)(struct ISwapChainRealization *))(*(_QWORD *)v19 + 16LL))(v19);
      v14 = v24;
      v7 = v32;
      LOBYTE(v11) = v29;
    }
    if ( v31 > 1 )
      CGlobalCompositionSurfaceInfo::CBindInfo::EnsureHDRMetaData(this);
    goto LABEL_22;
  }
  v29 = 1;
  v12 = CGlobalCompositionSurfaceInfo::CBindInfo::EnsureDecodeBitmap(this);
  v13 = v12;
  if ( v12 >= 0 )
  {
    LOBYTE(v11) = 1;
    goto LABEL_10;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1802D3190, 4u, v12, 0x653u, 0);
LABEL_22:
  for ( j = 0; j < v31; ++j )
  {
    v21 = *(void **)(v26 + 40LL * j + 8);
    if ( v21 )
      CloseHandle(v21);
  }
LABEL_26:
  if ( v6 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(v6, v32);
    std::_Deallocate<16>(v6, (v5 - v6) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  if ( (_QWORD)v26 )
    std::_Deallocate<16>(v26, 8 * ((v27 - (__int64)v26) >> 3));
  return v13;
}

```

## disassembly

```asm
0x18002f690  mov     [rsp-40h+arg_10], r8d
0x18002f695  mov     [rsp-40h+arg_8], rdx
0x18002f69a  push    rbp
0x18002f69b  push    rbx
0x18002f69c  push    rsi
0x18002f69d  push    rdi
0x18002f69e  push    r12
0x18002f6a0  push    r13
0x18002f6a2  push    r14
0x18002f6a4  push    r15
0x18002f6a6  mov     rbp, rsp
0x18002f6a9  sub     rsp, 78h
0x18002f6ad  xor     r13d, r13d
0x18002f6b0  mov     edx, r8d
0x18002f6b3  mov     [rbp+var_28], r13
0x18002f6b7  xorps   xmm0, xmm0
0x18002f6ba  mov     rsi, rcx
0x18002f6bd  movdqu  [rbp+var_38], xmm0
0x18002f6c2  test    r8d, r8d
0x18002f6c5  jz      short loc_18002F6D0
0x18002f6c7  lea     rcx, [rbp+var_38]
0x18002f6cb  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UCSM_REALIZATION_INFO@@V?$allocator@UCSM_REALIZATION_INFO@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<CSM_REALIZATION_INFO>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18002f6d0  lea     rax, [rsi+48h]
0x18002f6d4  xorps   xmm0, xmm0
0x18002f6d7  lea     rcx, [rbp+var_20]
0x18002f6db  mov     r14, r13
0x18002f6de  movdqu  [rbp+var_20], xmm0
0x18002f6e3  cmp     rcx, rax
0x18002f6e6  jz      loc_18002F9A4
0x18002f6ec  mov     r15, [rax]
0x18002f6ef  mov     [rax], r13
0x18002f6f2  mov     rbx, [rax+8]
0x18002f6f6  mov     [rax+8], r13
0x18002f6fa  mov     r14, [rax+10h]
0x18002f6fe  mov     [rax+10h], r13
0x18002f702  mov     rcx, [rsi]
0x18002f705  lea     rdx, [rsi+18h]
0x18002f709  mov     r9, qword ptr [rbp+var_38]
0x18002f70d  lea     r8, [rbp+arg_10]
0x18002f711  mov     [rsi+0B7h], r13b
0x18002f718  mov     [rbp+arg_18], rbx
0x18002f71c  mov     rcx, [rcx+20h]
0x18002f720  call    cs:__imp_NtOpenCompositionSurfaceRealizationInfo
0x18002f726  mov     edi, eax
0x18002f728  test    eax, eax
0x18002f72a  js      loc_18002F8B3
0x18002f730  cmp     [rbp+arg_10], 1
0x18002f734  ja      short loc_18002F740
0x18002f736  cmp     dword ptr [rsi+20h], 3
0x18002f73a  jnz     loc_18002F8A4
0x18002f740  mov     rcx, rsi; this
0x18002f743  mov     [rbp+arg_0], 1
0x18002f747  call    ?EnsureDecodeBitmap@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJXZ; CGlobalCompositionSurfaceInfo::CBindInfo::EnsureDecodeBitmap(void)
0x18002f74c  mov     edi, eax
0x18002f74e  test    eax, eax
0x18002f750  js      loc_18002F927
0x18002f756  mov     r9b, [rbp+arg_0]
0x18002f75a  mov     r8, r13
0x18002f75d  mov     [rbp+var_48], r13
0x18002f761  mov     r12d, r13d
0x18002f764  cmp     r12d, [rbp+arg_10]
0x18002f768  jnb     loc_18002F807
0x18002f76e  mov     rax, qword ptr [rbp+var_38]
0x18002f772  mov     ecx, r12d
0x18002f775  lea     rdx, [rcx+rcx*4]
0x18002f779  lea     r13, [rax+rdx*8]
0x18002f77d  cmp     qword ptr [r13+18h], 0
0x18002f782  jz      short loc_18002F79B
0x18002f784  mov     rax, rbx
0x18002f787  sub     rax, r15
0x18002f78a  sar     rax, 3
0x18002f78e  cmp     r8, rax
0x18002f791  jb      loc_18002F952
0x18002f797  mov     r9b, [rbp+arg_0]; bool
0x18002f79b  mov     rdx, [rbp+arg_8]; struct CSM_BUFFER_ATTRIBUTES *
0x18002f79f  lea     rax, [rbp+var_40]
0x18002f7a3  mov     r8, r13; struct CSM_REALIZATION_INFO *
0x18002f7a6  mov     [rsp+78h+var_58], rax; struct ISwapChainRealization **
0x18002f7ab  mov     rcx, rsi; this
0x18002f7ae  mov     [rbp+var_40], 0
0x18002f7b6  call    ?CreateNewRealization@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAJAEBUCSM_BUFFER_ATTRIBUTES@@AEBUCSM_REALIZATION_INFO@@_NPEAPEAVISwapChainRealization@@@Z; CGlobalCompositionSurfaceInfo::CBindInfo::CreateNewRealization(CSM_BUFFER_ATTRIBUTES const &,CSM_REALIZATION_INFO const &,bool,ISwapChainRealization * *)
0x18002f7bb  mov     edi, eax
0x18002f7bd  test    eax, eax
0x18002f7bf  js      loc_18002F8E2
0x18002f7c5  mov     rbx, [rbp+var_40]
0x18002f7c9  mov     qword ptr [r13+8], 0
0x18002f7d1  mov     rdx, rbx; struct ISwapChainRealization *
0x18002f7d4  mov     rcx, rsi; this
0x18002f7d7  call    ?AddRealization@CBindInfo@CGlobalCompositionSurfaceInfo@@IEAAXPEAVISwapChainRealization@@@Z; CGlobalCompositionSurfaceInfo::CBindInfo::AddRealization(ISwapChainRealization *)
0x18002f7dc  xor     r13d, r13d
0x18002f7df  test    rbx, rbx
0x18002f7e2  jz      short loc_18002F7F3
0x18002f7e4  mov     rax, [rbx]
0x18002f7e7  mov     rcx, rbx
0x18002f7ea  mov     rax, [rax+10h]
0x18002f7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f7f3  mov     r8, [rbp+var_48]
0x18002f7f7  inc     r12d
0x18002f7fa  mov     rbx, [rbp+arg_18]
0x18002f7fe  mov     r9b, [rbp+arg_0]
0x18002f802  jmp     loc_18002F764
0x18002f807  cmp     [rbp+arg_10], 1
0x18002f80b  jbe     short loc_18002F815
0x18002f80d  mov     rcx, rsi; this
0x18002f810  call    ?EnsureHDRMetaData@CBindInfo@CGlobalCompositionSurfaceInfo@@QEAAJXZ; CGlobalCompositionSurfaceInfo::CBindInfo::EnsureHDRMetaData(void)
0x18002f815  mov     ebx, r13d
0x18002f818  cmp     [rbp+arg_10], r13d
0x18002f81c  jbe     short loc_18002F83F
0x18002f81e  mov     eax, ebx
0x18002f820  lea     rcx, [rax+rax*4]
0x18002f824  mov     rax, qword ptr [rbp+var_38]
0x18002f828  mov     rcx, [rax+rcx*8+8]; hObject
0x18002f82d  test    rcx, rcx
0x18002f830  jz      short loc_18002F838
0x18002f832  call    cs:__imp_CloseHandle
0x18002f838  inc     ebx
0x18002f83a  cmp     ebx, [rbp+arg_10]
0x18002f83d  jb      short loc_18002F81E
0x18002f83f  test    r15, r15
0x18002f842  jz      short loc_18002F862
0x18002f844  mov     rdx, [rbp+arg_18]
0x18002f848  mov     rcx, r15
0x18002f84b  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> *,wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>> &)
0x18002f850  sub     r14, r15
0x18002f853  mov     rcx, r15
0x18002f856  and     r14, 0FFFFFFFFFFFFFFF8h
0x18002f85a  mov     rdx, r14
0x18002f85d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002f862  mov     rcx, qword ptr [rbp+var_38]
0x18002f866  test    rcx, rcx
0x18002f869  jz      short loc_18002F891
0x18002f86b  mov     rax, [rbp+var_28]
0x18002f86f  mov     rdx, 0CCCCCCCCCCCCCCCDh
0x18002f879  sub     rax, rcx
0x18002f87c  sar     rax, 3
0x18002f880  imul    rax, rdx
0x18002f884  lea     rdx, [rax+rax*4]
0x18002f888  shl     rdx, 3
0x18002f88c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002f891  mov     eax, edi
0x18002f893  add     rsp, 78h
0x18002f897  pop     r15
0x18002f899  pop     r14
0x18002f89b  pop     r13
0x18002f89d  pop     r12
0x18002f89f  pop     rdi
0x18002f8a0  pop     rsi
0x18002f8a1  pop     rbx
0x18002f8a2  pop     rbp
0x18002f8a3  retn
0x18002f8a4  mov     edi, r13d
0x18002f8a7  mov     [rbp+arg_0], r13b
0x18002f8ab  mov     r9b, r13b
0x18002f8ae  jmp     loc_18002F75A
0x18002f8b3  mov     r8d, 4; unsigned int
0x18002f8b9  mov     [rsp+78h+var_50], r13; void *
0x18002f8be  bts     edi, 1Ch
0x18002f8c2  mov     dword ptr [rsp+78h+var_58], 64Ch; unsigned int
0x18002f8ca  mov     r9d, edi; int
0x18002f8cd  lea     rdx, dword_1802D3190; int *
0x18002f8d4  lea     ecx, [r8+10h]; unsigned int
0x18002f8d8  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002f8dd  jmp     loc_18002F83F
0x18002f8e2  xor     r13d, r13d
0x18002f8e5  lea     rdx, dword_1802D3190; int *
0x18002f8ec  mov     [rsp+78h+var_50], r13; void *
0x18002f8f1  mov     r9d, eax; int
0x18002f8f4  mov     dword ptr [rsp+78h+var_58], 689h; unsigned int
0x18002f8fc  lea     r8d, [r13+4]; unsigned int
0x18002f900  lea     ecx, [r13+14h]; unsigned int
0x18002f904  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002f909  mov     rcx, [rbp+var_40]
0x18002f90d  test    rcx, rcx
0x18002f910  jz      loc_18002F815
0x18002f916  mov     rax, [rcx]
0x18002f919  mov     rax, [rax+10h]
0x18002f91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f922  jmp     loc_18002F815
0x18002f927  mov     r8d, 4; unsigned int
0x18002f92d  mov     [rsp+78h+var_50], r13; void *
0x18002f932  mov     r9d, eax; int
0x18002f935  mov     dword ptr [rsp+78h+var_58], 653h; unsigned int
0x18002f93d  lea     rdx, dword_1802D3190; int *
0x18002f944  lea     ecx, [r8+10h]; unsigned int
0x18002f948  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18002f94d  jmp     loc_18002F815
0x18002f952  mov     rbx, [r15+r8*8]
0x18002f956  mov     qword ptr [r15+r8*8], 0
0x18002f95e  mov     rcx, rbx
0x18002f961  inc     r8
0x18002f964  mov     [rbp+var_40], rbx
0x18002f968  mov     [rbp+var_48], r8
0x18002f96c  mov     rax, [rbx]
0x18002f96f  mov     rax, [rax+0F8h]
0x18002f976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f97b  mov     r8, [r13+18h]
0x18002f97f  cmp     rax, r8
0x18002f982  jnz     short loc_18002F9B1
0x18002f984  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+3, 8
0x18002f98b  jnz     short loc_18002F9C7
0x18002f98d  mov     rax, [rbx]
0x18002f990  mov     rdx, r13
0x18002f993  mov     rcx, rbx
0x18002f996  mov     rax, [rax+60h]
0x18002f99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f99f  jmp     loc_18002F7D1
0x18002f9a4  mov     rbx, qword ptr [rbp+var_20+8]
0x18002f9a8  mov     r15, qword ptr [rbp+var_20]
0x18002f9ac  jmp     loc_18002F702
0x18002f9b1  lea     rcx, [rbp+var_40]
0x18002f9b5  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x18002f9ba  mov     r8, [rbp+var_48]
0x18002f9be  mov     rbx, [rbp+arg_18]
0x18002f9c2  jmp     loc_18002F784
0x18002f9c7  lea     rdx, CompSurfInfo_ReuseRealization
0x18002f9ce  call    McTemplateU0x_EventWriteTransfer
0x18002f9d3  jmp     short loc_18002F98D
```

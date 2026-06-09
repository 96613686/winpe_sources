# DeserializeEffectDescription

- ea: `0x180009730`
- end: `0x180009b33`
- name: `DeserializeEffectDescription`
- size: `1027`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004db8`
- `0x180009730`
- `0x180009b3c`
- `0x180009e44`
- `0x180009ee8`
- `0x18000a020`
- `0x18000a2c0`
- `0x18000a8d0`
- `0x18000aa58`
- `0x18000ab8c`
- `0x180015f48`
- `0x180016944`
- `0x1800176c8`
- `0x1800177ec`
- `0x18001de54`
- `0x18001ee58`
- `0x180021060`
- `0x18002699c`
- `0x180026a44`
- `0x180026b90`
- `0x18002b8b0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009769`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009769`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009758`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009758`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DeserializeEffectDescription(unsigned int *a1, unsigned int a2, _QWORD *a3)
{
  __int64 v4; // rsi
  HANDLE ProcessHeap; // rax
  _DWORD *v7; // rax
  _DWORD *v8; // rdi
  int v9; // edx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  Windows::UI::Composition *v12; // rcx
  unsigned int i; // esi
  unsigned int *v14; // r14
  unsigned int v15; // r14d
  int v16; // edx
  Windows::UI::Composition *v17; // rcx
  unsigned int j; // esi
  unsigned int *v19; // rsi
  unsigned int v20; // esi
  int v21; // edx
  Windows::UI::Composition *v22; // rcx
  unsigned int k; // ebx
  _QWORD *v24; // rdx
  unsigned int *v25; // rbx
  unsigned int v26; // ebx
  unsigned int m; // esi
  char HaveOpacityRelevance; // al
  _DWORD *v29; // rcx
  __int64 result; // rax
  _QWORD *v31; // rdx
  _QWORD *v32; // rdx
  unsigned int *v33; // rax
  unsigned int *v34; // rax
  _QWORD *v35; // rdx
  __int64 v36; // rcx
  unsigned int *v37; // [rsp+20h] [rbp-98h] BYREF
  unsigned int *v38; // [rsp+28h] [rbp-90h]
  unsigned int *v39; // [rsp+30h] [rbp-88h]
  _DWORD *v40; // [rsp+38h] [rbp-80h]
  _QWORD pExceptionObject[3]; // [rsp+40h] [rbp-78h] BYREF
  Windows::UI::Composition *v42[4]; // [rsp+58h] [rbp-60h] BYREF

  v4 = a2;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 0, 0x80u);
  try
  {
    v8 = v7;
    if ( !v7 )
    {
      pExceptionObject[2] = 0;
      pExceptionObject[1] = "bad allocation";
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    v40 = v7;
    v7[2] = 0;
    *(_QWORD *)v7 = &Windows::UI::Composition::FlattenedEffectGraph::`vftable'{for `CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>'};
    *((_QWORD *)v7 + 2) = &Windows::UI::Composition::FlattenedEffectGraph::`vftable'{for `Windows::UI::Composition::IEffectDescriptionWithNames'};
    std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(v7 + 6);
    std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(v8 + 12);
    std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(v8 + 18);
    std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(v8 + 24);
    *((_BYTE *)v8 + 120) = 0;
    v37 = a1;
    v39 = (unsigned int *)((char *)a1 + v4);
    if ( a1 + 1 > (unsigned int *)((char *)a1 + v4) )
      Windows::UI::Composition::OriginateException((Windows::UI::Composition *)((char *)a1 + v4), v9);
    v38 = a1 + 1;
    v10 = *a1;
    if ( v10 > 4 )
      Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException();
    std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::reserve((HSTRING **)v8 + 12, v10);
    for ( i = 0; i < v10; ++i )
    {
      v32 = (_QWORD *)*((_QWORD *)v8 + 13);
      if ( v32 == *((_QWORD **)v8 + 14) )
      {
        std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Emplace_reallocate<>(v8 + 24);
      }
      else
      {
        v32[1] = 0;
        *v32 = 0;
        *((_QWORD *)v8 + 13) += 16LL;
      }
      v33 = v38;
      if ( v38 + 1 > v39 )
        Windows::UI::Composition::OriginateException((Windows::UI::Composition *)(v38 + 1), (int)v32);
      v11 = *((_QWORD *)v8 + 13);
      ++v38;
      *(_DWORD *)(v11 - 8) = *v33;
      v34 = v38;
      v12 = (Windows::UI::Composition *)((char *)v38 + 1);
      if ( (unsigned int *)((char *)v38 + 1) > v39 )
        Windows::UI::Composition::OriginateException(v12, v11);
      v38 = (unsigned int *)((char *)v38 + 1);
      *(_BYTE *)(v11 - 4) = *(_BYTE *)v34;
    }
    v42[0] = (Windows::UI::Composition *)&v37;
    v14 = v38;
    if ( v38 + 1 > v39 )
      Windows::UI::Composition::OriginateException(v12, v11);
    ++v38;
    v15 = *v14;
    if ( v15 > 5 )
      Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException();
    std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::reserve(v8 + 6, v15);
    for ( j = 0; j < v15; ++j )
    {
      v31 = (_QWORD *)*((_QWORD *)v8 + 4);
      if ( v31 == *((_QWORD **)v8 + 5) )
      {
        std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::_Emplace_reallocate<>(v8 + 6);
      }
      else
      {
        *v31 = 0;
        *((_QWORD *)v8 + 4) += 8LL;
      }
      Windows::UI::Composition::FlattenedEffectGraph::FlattenedEffectGraph_::_2_::_lambda_2_::operator()(
        (__int64 *)v42,
        (Windows::UI::Composition **)(*((_QWORD *)v8 + 4) - 8LL));
    }
    v42[0] = (Windows::UI::Composition *)&v37;
    v42[1] = (Windows::UI::Composition *)v8;
    v19 = v38;
    if ( v38 + 1 > v39 )
      Windows::UI::Composition::OriginateException(v17, v16);
    ++v38;
    v20 = *v19;
    if ( v20 > 0x19 )
      Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException();
    std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::reserve(v8 + 12, v20);
    for ( k = 0; k < v20; ++k )
    {
      v24 = (_QWORD *)*((_QWORD *)v8 + 7);
      if ( v24 == *((_QWORD **)v8 + 8) )
      {
        std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Emplace_reallocate<>(v8 + 12);
      }
      else
      {
        *v24 = 0;
        *((_QWORD *)v8 + 7) += 8LL;
      }
      Windows::UI::Composition::FlattenedEffectGraph::FlattenedEffectGraph_::_2_::_lambda_3_::operator()(
        v42,
        (Windows::UI::Composition::EffectType ***)(*((_QWORD *)v8 + 7) - 8LL));
    }
    v42[0] = (Windows::UI::Composition *)&v37;
    v25 = v38;
    if ( v38 + 1 > v39 )
      Windows::UI::Composition::OriginateException(v22, v21);
    ++v38;
    v26 = *v25;
    if ( v26 > 0x177 )
      Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException();
    std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::reserve((HSTRING **)v8 + 9, v26);
    for ( m = 0; m < v26; ++m )
    {
      v35 = (_QWORD *)*((_QWORD *)v8 + 10);
      if ( v35 == *((_QWORD **)v8 + 11) )
      {
        std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Emplace_reallocate<>(v8 + 18);
      }
      else
      {
        v35[1] = 0;
        v35[2] = 0;
        *v35 = 0;
        *((_QWORD *)v8 + 10) += 24LL;
      }
      Windows::UI::Composition::FlattenedEffectGraph::FlattenedEffectGraph_::_2_::_lambda_4_::operator()(
        v42,
        *((_QWORD *)v8 + 10) - 24LL);
    }
    if ( *((_QWORD *)v8 + 3) == *((_QWORD *)v8 + 4) || *((_QWORD *)v8 + 6) == *((_QWORD *)v8 + 7) )
    {
      std::wstring::wstring(v42, L"Empty effect description");
      Windows::UI::Composition::OriginateException(v36, v42);
    }
    v40 = v8;
    if ( v8 )
      (**(void (__fastcall ***)(_DWORD *))v8)(v8);
    if ( *((_QWORD *)v8 + 6) != *((_QWORD *)v8 + 7) )
    {
      HaveOpacityRelevance = Windows::UI::Composition::FlattenedEffectGraph::DoesNodeHaveOpacityRelevance((Windows::UI::Composition::FlattenedEffectGraph *)v8);
      *((_BYTE *)v8 + 120) = HaveOpacityRelevance;
      if ( HaveOpacityRelevance )
        Windows::UI::Composition::FlattenedEffectGraph::SetNodeOpacityRelevance(
          (Windows::UI::Composition::FlattenedEffectGraph *)v8,
          ((__int64)(*((_QWORD *)v8 + 7) - *((_QWORD *)v8 + 6)) >> 3) - 1);
    }
    v29 = v8 + 4;
    if ( !v8 )
      v29 = 0;
    *a3 = v29;
    result = 0;
  }
  catch ( ... )
  {
    TranslateException();
  }
  return result;
}

```

## disassembly

```asm
0x180009730  push    rbx
0x180009732  push    rsi
0x180009733  push    rdi
0x180009734  push    r12
0x180009736  push    r14
0x180009738  push    r15
0x18000973a  sub     rsp, 88h
0x180009741  mov     rax, cs:__security_cookie
0x180009748  xor     rax, rsp
0x18000974b  mov     [rsp+0B8h+var_40], rax
0x180009750  mov     r15, r8
0x180009753  mov     esi, edx
0x180009755  mov     rbx, rcx
0x180009758  call    cs:__imp_GetProcessHeap
0x18000975e  mov     rcx, rax; hHeap
0x180009761  xor     edx, edx; dwFlags
0x180009763  mov     r8d, 80h; dwBytes
0x180009769  call    cs:__imp_HeapAlloc
0x18000976f  mov     rdi, rax
0x180009772  test    rax, rax
0x180009775  jz      loc_180009A9B
0x18000977b  mov     [rsp+0B8h+var_80], rax
0x180009780  xor     r12d, r12d
0x180009783  mov     [rax+8], r12d
0x180009787  lea     rax, ??_7FlattenedEffectGraph@Composition@UI@Windows@@6B?$CMILRefCountBaseT@UIMILRefCount@@VCMilObjectDeleter@@@@@; const Windows::UI::Composition::FlattenedEffectGraph::`vftable'{for `CMILRefCountBaseT<IMILRefCount,CMilObjectDeleter>'}
0x18000978e  mov     [rdi], rax
0x180009791  lea     rax, ??_7FlattenedEffectGraph@Composition@UI@Windows@@6BIEffectDescriptionWithNames@123@@; const Windows::UI::Composition::FlattenedEffectGraph::`vftable'{for `Windows::UI::Composition::IEffectDescriptionWithNames'}
0x180009798  mov     [rdi+10h], rax
0x18000979c  lea     rcx, [rdi+18h]
0x1800097a0  call    ??0?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(void)
0x1800097a5  nop
0x1800097a6  lea     rcx, [rdi+30h]
0x1800097aa  call    ??0?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(void)
0x1800097af  nop
0x1800097b0  lea     rcx, [rdi+48h]
0x1800097b4  call    ??0?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(void)
0x1800097b9  nop
0x1800097ba  lea     rcx, [rdi+60h]
0x1800097be  call    ??0?$vector@USurfaceData@EffectInstance@Composition@UI@Windows@@V?$allocator@USurfaceData@EffectInstance@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::UI::Composition::EffectInstance::SurfaceData>::vector<Windows::UI::Composition::EffectInstance::SurfaceData>(void)
0x1800097c3  nop
0x1800097c4  mov     [rdi+78h], r12b
0x1800097c8  mov     [rsp+0B8h+var_98], rbx
0x1800097cd  lea     rcx, [rbx+rsi]; this
0x1800097d1  mov     [rsp+0B8h+var_88], rcx
0x1800097d6  lea     rax, [rbx+4]
0x1800097da  cmp     rax, rcx
0x1800097dd  ja      loc_180009ACD
0x1800097e3  mov     [rsp+0B8h+var_90], rax
0x1800097e8  mov     ebx, [rbx]
0x1800097ea  cmp     ebx, 4
0x1800097ed  ja      loc_180009AD2
0x1800097f3  mov     edx, ebx
0x1800097f5  lea     rcx, [rdi+60h]
0x1800097f9  call    ?reserve@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@QEAAX_K@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::reserve(unsigned __int64)
0x1800097fe  mov     esi, r12d
0x180009801  cmp     esi, ebx
0x180009803  jb      loc_1800099D8
0x180009809  lea     rax, [rsp+0B8h+var_98]
0x18000980e  mov     [rsp+0B8h+var_60], rax
0x180009813  mov     r14, [rsp+0B8h+var_90]
0x180009818  lea     rax, [r14+4]
0x18000981c  cmp     rax, [rsp+0B8h+var_88]
0x180009821  ja      loc_180009AE1
0x180009827  mov     [rsp+0B8h+var_90], rax
0x18000982c  mov     r14d, [r14]
0x18000982f  cmp     r14d, 5
0x180009833  ja      loc_180009AE6
0x180009839  mov     edx, r14d
0x18000983c  lea     rcx, [rdi+18h]
0x180009840  call    ?reserve@?$vector@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::reserve(unsigned __int64)
0x180009845  mov     esi, r12d
0x180009848  cmp     esi, r14d
0x18000984b  jb      loc_1800099A9
0x180009851  lea     rax, [rsp+0B8h+var_98]
0x180009856  mov     [rsp+0B8h+var_60], rax
0x18000985b  mov     [rsp+0B8h+var_58], rdi
0x180009860  mov     rsi, [rsp+0B8h+var_90]
0x180009865  lea     rax, [rsi+4]
0x180009869  cmp     rax, [rsp+0B8h+var_88]
0x18000986e  ja      loc_180009AEB
0x180009874  mov     [rsp+0B8h+var_90], rax
0x180009879  mov     esi, [rsi]
0x18000987b  cmp     esi, 19h
0x18000987e  ja      loc_180009AF0
0x180009884  mov     edx, esi
0x180009886  lea     rcx, [rdi+30h]
0x18000988a  call    ?reserve@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@QEAAX_K@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::reserve(unsigned __int64)
0x18000988f  mov     ebx, r12d
0x180009892  cmp     ebx, esi
0x180009894  jnb     short loc_1800098C2
0x180009896  mov     rdx, [rdi+38h]
0x18000989a  cmp     rdx, [rdi+40h]
0x18000989e  jz      loc_180009A71
0x1800098a4  mov     [rdx], r12
0x1800098a7  add     qword ptr [rdi+38h], 8
0x1800098ac  mov     rdx, [rdi+38h]
0x1800098b0  sub     rdx, 8
0x1800098b4  lea     rcx, [rsp+0B8h+var_60]
0x1800098b9  call    _Windows__UI__Composition__FlattenedEffectGraph__FlattenedEffectGraph____2____lambda_3___operator__
0x1800098be  inc     ebx
0x1800098c0  jmp     short loc_180009892
0x1800098c2  lea     rax, [rsp+0B8h+var_98]
0x1800098c7  mov     [rsp+0B8h+var_60], rax
0x1800098cc  mov     rbx, [rsp+0B8h+var_90]
0x1800098d1  lea     rax, [rbx+4]
0x1800098d5  cmp     rax, [rsp+0B8h+var_88]
0x1800098da  ja      loc_180009AF5
0x1800098e0  mov     [rsp+0B8h+var_90], rax
0x1800098e5  mov     ebx, [rbx]
0x1800098e7  cmp     ebx, 177h
0x1800098ed  ja      loc_180009AFA
0x1800098f3  mov     edx, ebx
0x1800098f5  lea     rcx, [rdi+48h]
0x1800098f9  call    ?reserve@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@QEAAX_K@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::reserve(unsigned __int64)
0x1800098fe  mov     esi, r12d
0x180009901  cmp     esi, ebx
0x180009903  jb      loc_180009A3A
0x180009909  mov     rax, [rdi+20h]
0x18000990d  cmp     [rdi+18h], rax
0x180009911  jz      loc_180009B0D
0x180009917  mov     rax, [rdi+38h]
0x18000991b  cmp     [rdi+30h], rax
0x18000991f  jz      loc_180009B0D
0x180009925  mov     [rsp+0B8h+var_80], rdi
0x18000992a  test    rdi, rdi
0x18000992d  jz      short loc_18000993E
0x18000992f  mov     rax, [rdi]
0x180009932  mov     rcx, rdi
0x180009935  mov     rax, [rax]
0x180009938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000993d  nop
0x18000993e  mov     rdx, [rdi+38h]
0x180009942  mov     rax, [rdi+30h]
0x180009946  cmp     rax, rdx
0x180009949  jz      short loc_18000997B
0x18000994b  sub     rdx, rax
0x18000994e  sar     rdx, 3
0x180009952  dec     rdx; unsigned __int64
0x180009955  mov     rcx, rdi; this
0x180009958  call    ?DoesNodeHaveOpacityRelevance@FlattenedEffectGraph@Composition@UI@Windows@@AEBA_N_K@Z; Windows::UI::Composition::FlattenedEffectGraph::DoesNodeHaveOpacityRelevance(unsigned __int64)
0x18000995d  mov     [rdi+78h], al
0x180009960  test    al, al
0x180009962  jz      short loc_18000997B
0x180009964  mov     rdx, [rdi+38h]
0x180009968  sub     rdx, [rdi+30h]
0x18000996c  sar     rdx, 3
0x180009970  dec     rdx; unsigned __int64
0x180009973  mov     rcx, rdi; this
0x180009976  call    ?SetNodeOpacityRelevance@FlattenedEffectGraph@Composition@UI@Windows@@AEAAX_K@Z; Windows::UI::Composition::FlattenedEffectGraph::SetNodeOpacityRelevance(unsigned __int64)
0x18000997b  lea     rcx, [rdi+10h]
0x18000997f  test    rdi, rdi
0x180009982  cmovz   rcx, r12
0x180009986  mov     [r15], rcx
0x180009989  xor     eax, eax
0x18000998b  mov     rcx, [rsp+0B8h+var_40]
0x180009990  xor     rcx, rsp; StackCookie
0x180009993  call    __security_check_cookie
0x180009998  add     rsp, 88h
0x18000999f  pop     r15
0x1800099a1  pop     r14
0x1800099a3  pop     r12
0x1800099a5  pop     rdi
0x1800099a6  pop     rsi
0x1800099a7  pop     rbx
0x1800099a8  retn
0x1800099a9  mov     rdx, [rdi+20h]
0x1800099ad  cmp     rdx, [rdi+28h]
0x1800099b1  jz      loc_180009A7F
0x1800099b7  mov     [rdx], r12
0x1800099ba  add     qword ptr [rdi+20h], 8
0x1800099bf  mov     rdx, [rdi+20h]
0x1800099c3  sub     rdx, 8
0x1800099c7  lea     rcx, [rsp+0B8h+var_60]
0x1800099cc  call    _Windows__UI__Composition__FlattenedEffectGraph__FlattenedEffectGraph____2____lambda_2___operator__
0x1800099d1  inc     esi
0x1800099d3  jmp     loc_180009848
0x1800099d8  mov     rdx, [rdi+68h]; int
0x1800099dc  cmp     rdx, [rdi+70h]
0x1800099e0  jz      loc_180009A8D
0x1800099e6  mov     [rdx+8], r12
0x1800099ea  mov     [rdx], r12
0x1800099ed  add     qword ptr [rdi+68h], 10h
0x1800099f2  mov     rax, [rsp+0B8h+var_90]
0x1800099f7  lea     rcx, [rax+4]; this
0x1800099fb  cmp     rcx, [rsp+0B8h+var_88]
0x180009a00  ja      loc_180009AD7
0x180009a06  mov     rdx, [rdi+68h]; int
0x180009a0a  mov     [rsp+0B8h+var_90], rcx
0x180009a0f  mov     eax, [rax]
0x180009a11  mov     [rdx-8], eax
0x180009a14  mov     rax, [rsp+0B8h+var_90]
0x180009a19  lea     rcx, [rax+1]; this
0x180009a1d  cmp     rcx, [rsp+0B8h+var_88]
0x180009a22  ja      loc_180009ADC
0x180009a28  mov     [rsp+0B8h+var_90], rcx
0x180009a2d  movzx   eax, byte ptr [rax]
0x180009a30  mov     [rdx-4], al
0x180009a33  inc     esi
0x180009a35  jmp     loc_180009801
0x180009a3a  mov     rdx, [rdi+50h]
0x180009a3e  cmp     rdx, [rdi+58h]
0x180009a42  jz      loc_180009AFF
0x180009a48  mov     [rdx+8], r12
0x180009a4c  mov     [rdx+10h], r12
0x180009a50  mov     [rdx], r12
0x180009a53  add     qword ptr [rdi+50h], 18h
0x180009a58  mov     rdx, [rdi+50h]
0x180009a5c  sub     rdx, 18h
0x180009a60  lea     rcx, [rsp+0B8h+var_60]
0x180009a65  call    _Windows__UI__Composition__FlattenedEffectGraph__FlattenedEffectGraph____2____lambda_4___operator__
0x180009a6a  inc     esi
0x180009a6c  jmp     loc_180009901
0x180009a71  lea     rcx, [rdi+30h]
0x180009a75  call    ??$_Emplace_reallocate@$$V@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@1@QEAV21@@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Emplace_reallocate<>(std::unique_ptr<Windows::UI::Composition::EffectNode> * const)
0x180009a7a  jmp     loc_1800098AC
0x180009a7f  lea     rcx, [rdi+18h]
0x180009a83  call    ??$_Emplace_reallocate@$$V@?$vector@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@UEffectSubgraph@Composition@UI@Windows@@U?$default_delete@UEffectSubgraph@Composition@UI@Windows@@@std@@@1@QEAV21@@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectSubgraph>>::_Emplace_reallocate<>(std::unique_ptr<Windows::UI::Composition::EffectSubgraph> * const)
0x180009a88  jmp     loc_1800099BF
0x180009a8d  lea     rcx, [rdi+60h]
0x180009a91  call    ??$_Emplace_reallocate@$$V@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAPEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@QEAU23456@@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Emplace_reallocate<>(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const)
0x180009a96  jmp     loc_1800099F2
0x180009a9b  xorps   xmm0, xmm0
0x180009a9e  movups  [rsp+0B8h+var_70], xmm0
0x180009aa3  lea     rax, aBadAllocation; "bad allocation"
0x180009aaa  mov     qword ptr [rsp+0B8h+var_70], rax
0x180009aaf  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180009ab6  mov     [rsp+0B8h+pExceptionObject], rax
0x180009abb  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180009ac2  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180009ac7  call    _CxxThrowException_0
0x180009acd  call    ?OriginateException@Composition@UI@Windows@@YAXJ@Z; Windows::UI::Composition::OriginateException(long)
0x180009ad2  call    ?OriginateGraphTooComplexException@FlattenedEffectGraph@Composition@UI@Windows@@SAXXZ; Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException(void)
0x180009ad7  call    ?OriginateException@Composition@UI@Windows@@YAXJ@Z; Windows::UI::Composition::OriginateException(long)
0x180009adc  call    ?OriginateException@Composition@UI@Windows@@YAXJ@Z; Windows::UI::Composition::OriginateException(long)
0x180009ae1  call    ?OriginateException@Composition@UI@Windows@@YAXJ@Z; Windows::UI::Composition::OriginateException(long)
0x180009ae6  call    ?OriginateGraphTooComplexException@FlattenedEffectGraph@Composition@UI@Windows@@SAXXZ; Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException(void)
0x180009aeb  call    ?OriginateException@Composition@UI@Windows@@YAXJ@Z; Windows::UI::Composition::OriginateException(long)
0x180009af0  call    ?OriginateGraphTooComplexException@FlattenedEffectGraph@Composition@UI@Windows@@SAXXZ; Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException(void)
0x180009af5  call    ?OriginateException@Composition@UI@Windows@@YAXJ@Z; Windows::UI::Composition::OriginateException(long)
0x180009afa  call    ?OriginateGraphTooComplexException@FlattenedEffectGraph@Composition@UI@Windows@@SAXXZ; Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException(void)
0x180009aff  lea     rcx, [rdi+48h]
0x180009b03  call    ??$_Emplace_reallocate@$$V@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAPEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEAU23456@@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Emplace_reallocate<>(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const)
0x180009b08  jmp     loc_180009A58
0x180009b0d  lea     rdx, aEmptyEffectDes; "Empty effect description"
0x180009b14  lea     rcx, [rsp+0B8h+var_60]
0x180009b19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180009b1e  nop
0x180009b1f  lea     rdx, [rsp+0B8h+var_60]
0x180009b24  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x180009b2a  mov     eax, dword ptr [rsp+0B8h+var_60]
0x180009b2e  jmp     loc_18000998B
```

# Windows::UI::Composition::Traverser::VisitEffectInputs(Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *,Windows::UI::Composition::EffectSubgraph *,Windows::UI::Composition::EffectNode *)

- ea: `0x180005440`
- end: `0x180005bf7`
- name: `?VisitEffectInputs@Traverser@Composition@UI@Windows@@AEAAXPEAUIGraphicsEffectD2D1Interop@Effects@Graphics@4@PEAUEffectSubgraph@234@PEAVEffectNode@234@@Z`
- size: `1975`
- prototype: `void __fastcall(Windows::UI::Composition::Traverser *__hidden this, struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *, struct Windows::UI::Composition::EffectSubgraph *, struct Windows::UI::Composition::EffectNode *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180005ce0`

## callees

- `0x1800042ac`
- `0x180004db8`
- `0x180004df4`
- `0x180005440`
- `0x180005c00`
- `0x180005ce0`
- `0x18000b900`
- `0x180015f10`
- `0x180016240`
- `0x18001de54`
- `0x18001eaa0`
- `0x180020fd0`
- `0x180021060`
- `0x18002584c`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800055ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800055ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800056b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800056b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180005824`

## string_xrefs

- `0x1800054c5`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x1800055ca`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x1800059d1`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x1800056c9`: `onecoreuap\windows\dwm\effects\compiler\flattenedeffectgraph.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall Windows::UI::Composition::Traverser::VisitEffectInputs(
        Windows::UI::Composition::Traverser *this,
        struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *a2,
        struct Windows::UI::Composition::EffectSubgraph *a3,
        struct Windows::UI::Composition::EffectNode *a4)
{
  struct Windows::UI::Composition::EffectNode *v4; // rdi
  struct Windows::UI::Composition::EffectSubgraph *v5; // r14
  struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *v6; // r9
  Windows::UI::Composition::Traverser *v7; // rsi
  unsigned int v8; // r12d
  __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  PCWSTR StringRawBuffer; // r10
  unsigned __int64 i; // rdx
  WCHAR v15; // r8
  char v16; // r15
  unsigned __int8 v17; // r13
  Windows::UI::Composition::FlattenedEffectGraph *v18; // r14
  HSTRING v19; // rsi
  __int64 v20; // rax
  HRESULT v21; // eax
  __int64 v22; // rdx
  UINT32 v23; // ebx
  _QWORD *v24; // r8
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  struct Windows::Graphics::Effects::IGraphicsEffectSource *v28; // rcx
  unsigned __int64 v29; // rbx
  __int64 v30; // rax
  _QWORD *v31; // rdx
  struct Windows::Graphics::Effects::IGraphicsEffect *v32; // rcx
  __int64 v33; // rcx
  struct Windows::Graphics::Effects::IGraphicsEffectSource *v34; // rcx
  unsigned int v35; // ebx
  __int64 v36; // rax
  __int64 v37; // rcx
  struct Windows::Graphics::Effects::IGraphicsEffect *SourceFlatteningEffect; // rbx
  struct Windows::Graphics::Effects::IGraphicsEffectSource *v39; // rcx
  int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rax
  unsigned __int64 j; // rdi
  __int64 v45; // rcx
  unsigned int **v46; // rax
  unsigned int *v47; // rsi
  unsigned int *v48; // r12
  struct Windows::UI::Composition::EffectNode *NodeAt; // rax
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  UINT32 length; // [rsp+20h] [rbp-99h] BYREF
  struct Windows::Graphics::Effects::IGraphicsEffectSource *v58; // [rsp+28h] [rbp-91h] BYREF
  __int64 v59; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v60; // [rsp+38h] [rbp-81h]
  __int64 v61; // [rsp+40h] [rbp-79h] BYREF
  __int64 v62; // [rsp+48h] [rbp-71h] BYREF
  struct Windows::Graphics::Effects::IGraphicsEffect *v63; // [rsp+50h] [rbp-69h] BYREF
  HSTRING string; // [rsp+58h] [rbp-61h] BYREF
  Windows::UI::Composition::Traverser *v65; // [rsp+60h] [rbp-59h]
  HSTRING v66; // [rsp+68h] [rbp-51h]
  struct Windows::UI::Composition::EffectNode *v67; // [rsp+70h] [rbp-49h]
  struct Windows::UI::Composition::EffectSubgraph *v68; // [rsp+78h] [rbp-41h]
  struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *v69; // [rsp+80h] [rbp-39h]
  HSTRING newString[2]; // [rsp+88h] [rbp-31h] BYREF
  __int128 v71; // [rsp+98h] [rbp-21h]
  _BYTE v72[32]; // [rsp+A8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v4 = a4;
  v67 = a4;
  v5 = a3;
  v68 = a3;
  v6 = a2;
  v69 = a2;
  v7 = this;
  v65 = this;
  v8 = 0;
  v9 = 0x3FFFFFF43FFFFFFLL;
  while ( 1 )
  {
    v60 = v8;
    if ( v8 >= *((_DWORD *)v4 + 5) )
      break;
    v58 = 0;
    v10 = (*(__int64 (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffectD2D1Interop *, _QWORD, struct Windows::Graphics::Effects::IGraphicsEffectSource **))(*(_QWORD *)v6 + 56LL))(
            v6,
            v8,
            &v58);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x205,
        (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
        (const char *)(unsigned int)v10,
        length);
    if ( v58 )
    {
      v59 = 0;
      if ( (**(int (__fastcall ***)(struct Windows::Graphics::Effects::IGraphicsEffectSource *, GUID *, __int64 *))v58)(
             v58,
             &GUID_858ab13a_3292_4e4e_b3bb_2b6c6544a6ee,
             &v59) < 0
        || !v59 )
      {
        goto LABEL_9;
      }
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 40LL))(*(_QWORD *)v4) )
      {
        SourceFlatteningEffect = Windows::UI::Composition::Traverser::FindSourceFlatteningEffect(v7, v58);
        v39 = v58;
        if ( v58 )
        {
          v58 = 0;
          (*(void (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffectSource *))(*(_QWORD *)v39 + 16LL))(v39);
        }
        v40 = (**(__int64 (__fastcall ***)(struct Windows::Graphics::Effects::IGraphicsEffect *, GUID *, struct Windows::Graphics::Effects::IGraphicsEffectSource **))SourceFlatteningEffect)(
                SourceFlatteningEffect,
                &GUID_2d8f9ddc_4339_4eb9_9216_f9deb75658a2,
                &v58);
        if ( v40 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x21B,
            (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
            (const char *)(unsigned int)v40,
            length);
        v41 = v59;
        if ( v59 )
        {
          v59 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        }
LABEL_9:
        v63 = 0;
        if ( (**(int (__fastcall ***)(struct Windows::Graphics::Effects::IGraphicsEffectSource *, GUID *, struct Windows::Graphics::Effects::IGraphicsEffect **))v58)(
               v58,
               &GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3,
               &v63) < 0
          || !v63 )
        {
          *(_OWORD *)newString = 0;
          v71 = 0;
          std::wstring::_Construct<1,unsigned short const *>(newString, L"Unexpected effect input type.", 29);
          Windows::UI::Composition::OriginateException(v11, newString);
        }
        v29 = (unsigned int)((_std_find_trivial_8(*((_QWORD *)v7 + 12), *((_QWORD *)v7 + 13)) - *((_QWORD *)v7 + 12)) >> 3);
        if ( v29 >= (__int64)(*((_QWORD *)v7 + 13) - *((_QWORD *)v7 + 12)) >> 3 )
        {
          v35 = Windows::UI::Composition::Traverser::VisitEffect(v7, v63, v5);
          if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v4 + 32LL))(*(_QWORD *)v4, 1) )
          {
            std::wstring::wstring(v72, L"Invalid effect input.");
            Windows::UI::Composition::OriginateException(v56, v72);
          }
          v36 = *((_QWORD *)v4 + 1);
          *(_DWORD *)(v36 + 8LL * v8) = 1;
          *(_DWORD *)(v36 + 8LL * v8 + 4) = v35;
        }
        else
        {
          if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v4 + 32LL))(*(_QWORD *)v4, 3) )
          {
            std::wstring::wstring(v72, L"Invalid effect input.");
            Windows::UI::Composition::OriginateException(v55, v72);
          }
          v30 = *((_QWORD *)v4 + 1);
          *(_DWORD *)(v30 + 8LL * v8) = 3;
          *(_DWORD *)(v30 + 8LL * v8 + 4) = v29;
          LOBYTE(v62) = 1;
          *(_WORD *)((char *)&v62 + 1) = 0;
          BYTE3(v62) = 0;
          HIDWORD(v62) = v29;
          v31 = (_QWORD *)*((_QWORD *)v5 + 4);
          if ( v31 == *((_QWORD **)v5 + 5) )
          {
            std::vector<Windows::UI::Composition::EffectSubgraphInput>::_Emplace_reallocate<Windows::UI::Composition::EffectSubgraphInput>(
              (char *)v5 + 24,
              v31,
              &v62);
          }
          else
          {
            *v31 = v62;
            *((_QWORD *)v5 + 4) += 8LL;
          }
        }
        v32 = v63;
        if ( v63 )
        {
          v63 = 0;
          (*(void (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffect *))(*(_QWORD *)v32 + 16LL))(v32);
        }
        v33 = v59;
        if ( v59 )
        {
          v59 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        }
        v34 = v58;
        if ( v58 )
        {
          v58 = 0;
          (*(void (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffectSource *))(*(_QWORD *)v34 + 16LL))(v34);
        }
      }
      else
      {
        string = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v59 + 48LL))(v59, &string);
        if ( v12 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x223,
            (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
            (const char *)(unsigned int)v12,
            length);
        length = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
        if ( length > 0x64uLL )
        {
LABEL_61:
          std::wstring::wstring(v72, L"Malformed named input name.");
          Windows::UI::Composition::OriginateException(v37, v72);
        }
        for ( i = 0; i < length; ++i )
        {
          v15 = StringRawBuffer[i];
          if ( ((unsigned __int16)(v15 - 65) > 0x39u || !_bittest64(&v9, (unsigned __int16)(v15 - 65)))
            && ((unsigned __int16)(v15 - 48) > 9u || !i) )
          {
            goto LABEL_61;
          }
        }
        v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v4 + 48LL))(*(_QWORD *)v4, 0);
        v17 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 56LL))(*(_QWORD *)v4);
        v18 = *(Windows::UI::Composition::FlattenedEffectGraph **)v7;
        v19 = string;
        v66 = string;
        length = 0;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, HSTRING, UINT32 *))(*((_QWORD *)v18 + 2) + 144LL))(
               (_QWORD *)v18 + 2,
               string,
               &length) )
        {
          v43 = std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::at((char *)v18 + 96, length);
          if ( v16 || *(_DWORD *)(v43 + 8) != -1 )
          {
            std::wstring::wstring(newString, L"A graph source parameter with a transform can only be used once.");
            Windows::UI::Composition::OriginateException(v51, newString);
          }
          if ( v17 || *(_BYTE *)(v43 + 12) )
          {
            std::wstring::wstring(newString, L"A graph source parameter with a border effect can only be used once.");
            Windows::UI::Composition::OriginateException(v50, newString);
          }
        }
        else
        {
          v20 = *((_QWORD *)v18 + 13) - *((_QWORD *)v18 + 12);
          if ( v20 == 64 )
          {
            std::wstring::wstring(v72, L"No more than four graph source parameters are supported.");
            Windows::UI::Composition::OriginateException(v54, v72);
          }
          if ( v20 == 48 )
          {
            for ( j = 0; ; ++j )
            {
              v45 = *((_QWORD *)v18 + 3);
              if ( j >= (*((_QWORD *)v18 + 4) - v45) >> 3 )
                break;
              v46 = *(unsigned int ***)(v45 + 8 * j);
              v47 = *v46;
              v48 = v46[1];
              while ( v47 != v48 )
              {
                NodeAt = Windows::UI::Composition::FlattenedEffectGraph::GetNodeAt(v18, *v47);
                if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)NodeAt + 80LL))(*(_QWORD *)NodeAt) )
                {
                  std::wstring::wstring(
                    v72,
                    L"No more than three graph source parameters with white noise effect are supported.");
                  Windows::UI::Composition::OriginateException(v52, v72);
                }
                ++v47;
              }
            }
            v19 = v66;
            v4 = v67;
            v8 = v60;
          }
          newString[0] = 0;
          v21 = WindowsDuplicateString(v19, newString);
          if ( v21 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x131,
              (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\flattenedeffectgraph.cpp",
              (const char *)(unsigned int)v21,
              length);
          LODWORD(newString[1]) = -(v16 != 0) - 1;
          WORD2(newString[1]) = v17;
          v22 = *((_QWORD *)v18 + 13);
          if ( v22 == *((_QWORD *)v18 + 14) )
          {
            std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Emplace_reallocate<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>(
              (char *)v18 + 96,
              v22,
              newString);
          }
          else
          {
            *(HSTRING *)v22 = newString[0];
            newString[0] = 0;
            *(_DWORD *)(v22 + 8) = newString[1];
            *(_BYTE *)(v22 + 12) = BYTE4(newString[1]);
            *((_QWORD *)v18 + 13) += 16LL;
          }
          length = ((__int64)(*((_QWORD *)v18 + 13) - *((_QWORD *)v18 + 12)) >> 4) - 1;
          if ( newString[0] )
            WindowsDeleteString(newString[0]);
        }
        v23 = length;
        LOBYTE(v61) = 0;
        *(_WORD *)((char *)&v61 + 1) = 0;
        BYTE3(v61) = 0;
        HIDWORD(v61) = length;
        v5 = v68;
        v24 = (_QWORD *)*((_QWORD *)v68 + 4);
        v25 = *((_QWORD *)v68 + 3);
        if ( (_QWORD *)v25 == v24 )
          goto LABEL_35;
        do
        {
          if ( *(_BYTE *)v25 == 0 && *(_DWORD *)(v25 + 4) == length )
            break;
          v25 += 8;
        }
        while ( (_QWORD *)v25 != v24 );
        if ( (_QWORD *)v25 == v24 )
        {
LABEL_35:
          if ( v24 == *((_QWORD **)v68 + 5) )
          {
            std::vector<Windows::UI::Composition::EffectSubgraphInput>::_Emplace_reallocate<Windows::UI::Composition::EffectSubgraphInput>(
              (char *)v68 + 24,
              *((_QWORD *)v68 + 4),
              &v61);
          }
          else
          {
            *v24 = v61;
            *((_QWORD *)v5 + 4) += 8LL;
          }
        }
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v4 + 32LL))(*(_QWORD *)v4, 2) )
        {
          std::wstring::wstring(v72, L"Invalid effect input.");
          Windows::UI::Composition::OriginateException(v53, v72);
        }
        v26 = *((_QWORD *)v4 + 1);
        *(_DWORD *)(v26 + 8LL * v8) = 2;
        *(_DWORD *)(v26 + 8LL * v8 + 4) = v23;
        if ( string )
          WindowsDeleteString(string);
        v27 = v59;
        if ( v59 )
        {
          v59 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v28 = v58;
        if ( v58 )
        {
          v58 = 0;
          (*(void (__fastcall **)(struct Windows::Graphics::Effects::IGraphicsEffectSource *))(*(_QWORD *)v28 + 16LL))(v28);
        }
        v7 = v65;
      }
      v9 = 0x3FFFFFF43FFFFFFLL;
      goto LABEL_46;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v4 + 32LL))(*(_QWORD *)v4, 0) )
    {
      *(_OWORD *)newString = 0;
      v71 = 0;
      std::wstring::_Construct<1,unsigned short const *>(newString, L"Null effect input.", 18);
      Windows::UI::Composition::OriginateException(v42, newString);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>::InternalRelease(&v58);
LABEL_46:
    ++v8;
    v6 = v69;
  }
}

```

## disassembly

```asm
0x180005440  push    rbp
0x180005442  push    rbx
0x180005443  push    rsi
0x180005444  push    rdi
0x180005445  push    r12
0x180005447  push    r13
0x180005449  push    r14
0x18000544b  push    r15
0x18000544d  lea     rbp, [rsp-1Fh]
0x180005452  sub     rsp, 0D8h
0x180005459  mov     rax, cs:__security_cookie
0x180005460  xor     rax, rsp
0x180005463  mov     [rbp+57h+var_48], rax
0x180005467  mov     rdi, r9
0x18000546a  mov     [rbp+57h+var_A0], r9
0x18000546e  mov     r14, r8
0x180005471  mov     [rbp+57h+var_98], r8
0x180005475  mov     r9, rdx
0x180005478  mov     [rbp+57h+var_90], rdx
0x18000547c  mov     rsi, rcx
0x18000547f  mov     [rbp+57h+var_B0], rcx
0x180005483  xor     r15d, r15d
0x180005486  mov     r12d, r15d
0x180005489  mov     rbx, 3FFFFFF43FFFFFFh
0x180005493  mov     [rsp+110h+var_D8], r12d
0x180005498  cmp     r12d, [rdi+14h]
0x18000549c  jnb     short loc_1800054D7
0x18000549e  mov     [rsp+110h+var_E8], r15
0x1800054a3  mov     rax, [r9]
0x1800054a6  lea     r8, [rsp+110h+var_E8]
0x1800054ab  mov     edx, r12d
0x1800054ae  mov     rcx, r9
0x1800054b1  mov     rax, [rax+38h]
0x1800054b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054ba  mov     rcx, [rbp+5Fh]; this
0x1800054be  test    eax, eax
0x1800054c0  jns     short loc_1800054F7
0x1800054c2  mov     r9d, eax; char *
0x1800054c5  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x1800054cc  mov     edx, 205h; void *
0x1800054d1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800054d7  mov     rcx, [rbp+57h+var_48]
0x1800054db  xor     rcx, rsp; StackCookie
0x1800054de  call    __security_check_cookie
0x1800054e3  add     rsp, 0D8h
0x1800054ea  pop     r15
0x1800054ec  pop     r14
0x1800054ee  pop     r13
0x1800054f0  pop     r12
0x1800054f2  pop     rdi
0x1800054f3  pop     rsi
0x1800054f4  pop     rbx
0x1800054f5  pop     rbp
0x1800054f6  retn
0x1800054f7  mov     rcx, [rsp+110h+var_E8]
0x1800054fc  test    rcx, rcx
0x1800054ff  jz      loc_180005A04
0x180005505  mov     [rsp+110h+var_E0], r15
0x18000550a  mov     rax, [rcx]
0x18000550d  lea     r8, [rsp+110h+var_E0]
0x180005512  lea     rdx, _GUID_858ab13a_3292_4e4e_b3bb_2b6c6544a6ee
0x180005519  mov     rax, [rax]
0x18000551c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005521  nop
0x180005522  test    eax, eax
0x180005524  js      short loc_18000552E
0x180005526  cmp     [rsp+110h+var_E0], 0
0x18000552c  jnz     short loc_18000558F
0x18000552e  mov     [rbp+57h+var_C0], r15
0x180005532  mov     rcx, [rsp+110h+var_E8]
0x180005537  mov     rax, [rcx]
0x18000553a  lea     r8, [rbp+57h+var_C0]
0x18000553e  lea     rdx, _GUID_cb51c0ce_8fe6_4636_b202_861faa07d8f3
0x180005545  mov     rax, [rax]
0x180005548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000554d  nop
0x18000554e  test    eax, eax
0x180005550  js      short loc_18000555F
0x180005552  mov     r8, [rbp+57h+var_C0]
0x180005556  test    r8, r8
0x180005559  jnz     loc_18000582C
0x18000555f  xorps   xmm0, xmm0
0x180005562  movups  xmmword ptr [rbp+57h+newString], xmm0
0x180005566  xorps   xmm1, xmm1
0x180005569  movdqu  [rbp+57h+var_78], xmm1
0x18000556e  mov     r8d, 1Dh
0x180005574  lea     rdx, aUnexpectedEffe_0; "Unexpected effect input type."
0x18000557b  lea     rcx, [rbp+57h+newString]
0x18000557f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180005584  nop
0x180005585  lea     rdx, [rbp+57h+newString]
0x180005589  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000558f  mov     rcx, [rdi]
0x180005592  mov     rax, [rcx]
0x180005595  mov     rax, [rax+28h]
0x180005599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000559e  test    al, al
0x1800055a0  jnz     loc_180005980
0x1800055a6  mov     [rbp+57h+string], r15
0x1800055aa  mov     rcx, [rsp+110h+var_E0]
0x1800055af  mov     rax, [rcx]
0x1800055b2  lea     rdx, [rbp+57h+string]
0x1800055b6  mov     rax, [rax+30h]
0x1800055ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055bf  mov     rcx, [rbp+5Fh]; this
0x1800055c3  test    eax, eax
0x1800055c5  jns     short loc_1800055DC
0x1800055c7  mov     r9d, eax; char *
0x1800055ca  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x1800055d1  mov     edx, 223h; void *
0x1800055d6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800055dc  mov     [rsp+110h+length], r15d
0x1800055e1  lea     rdx, [rsp+110h+length]; length
0x1800055e6  mov     rcx, [rbp+57h+string]; string
0x1800055ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800055f0  mov     r10, rax
0x1800055f3  mov     r9d, [rsp+110h+length]
0x1800055f8  cmp     r9, 64h ; 'd'
0x1800055fc  ja      loc_180005965
0x180005602  mov     rdx, r15
0x180005605  cmp     rdx, r9
0x180005608  jnb     short loc_18000562F
0x18000560a  movzx   r8d, word ptr [r10+rdx*2]
0x18000560f  lea     ecx, [r8-41h]
0x180005613  cmp     cx, 39h ; '9'
0x180005617  ja      loc_180005950
0x18000561d  movzx   eax, cx
0x180005620  bt      rbx, rax
0x180005624  jnb     loc_180005950
0x18000562a  inc     rdx
0x18000562d  jmp     short loc_180005605
0x18000562f  mov     rcx, [rdi]
0x180005632  mov     rax, [rcx]
0x180005635  xor     edx, edx
0x180005637  mov     rax, [rax+30h]
0x18000563b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005640  movzx   r15d, al
0x180005644  mov     rcx, [rdi]
0x180005647  mov     rdx, [rcx]
0x18000564a  mov     rax, [rdx+38h]
0x18000564e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005653  movzx   r13d, al
0x180005657  mov     r14, [rsi]
0x18000565a  mov     rsi, [rbp+57h+string]
0x18000565e  mov     [rbp+57h+var_A8], rsi
0x180005662  mov     [rsp+110h+length], 0; int
0x18000566a  lea     rcx, [r14+10h]
0x18000566e  mov     rdx, [rcx]
0x180005671  mov     rax, [rdx+90h]
0x180005678  lea     r8, [rsp+110h+length]
0x18000567d  mov     rdx, rsi
0x180005680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005685  test    al, al
0x180005687  jnz     loc_180005A7D
0x18000568d  mov     rax, [r14+68h]
0x180005691  sub     rax, [r14+60h]
0x180005695  cmp     rax, 40h ; '@'
0x180005699  jz      loc_180005BA6
0x18000569f  cmp     rax, 30h ; '0'
0x1800056a3  jz      loc_180005AB8
0x1800056a9  mov     [rbp+57h+newString], 0
0x1800056b1  lea     rdx, [rbp+57h+newString]; newString
0x1800056b5  mov     rcx, rsi; string
0x1800056b8  call    cs:__imp_WindowsDuplicateString
0x1800056be  mov     rcx, [rbp+5Fh]; this
0x1800056c2  test    eax, eax
0x1800056c4  jns     short loc_1800056DB
0x1800056c6  mov     r9d, eax; char *
0x1800056c9  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x1800056d0  mov     edx, 131h; void *
0x1800056d5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800056db  neg     r15b
0x1800056de  sbb     eax, eax
0x1800056e0  dec     eax
0x1800056e2  mov     dword ptr [rbp+57h+newString+8], eax
0x1800056e5  mov     byte ptr [rbp+57h+newString+0Ch], r13b
0x1800056e9  mov     byte ptr [rbp+57h+newString+0Dh], 0
0x1800056ed  mov     rdx, [r14+68h]
0x1800056f1  cmp     rdx, [r14+70h]
0x1800056f5  jnz     loc_180005A49
0x1800056fb  lea     r8, [rbp+57h+newString]
0x1800056ff  lea     rcx, [r14+60h]
0x180005703  call    ??$_Emplace_reallocate@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAPEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@QEAU23456@$$QEAU23456@@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Emplace_reallocate<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,Windows::UI::Composition::FlattenedEffectGraph::NamedInput &&)
0x180005708  xor     r15d, r15d
0x18000570b  mov     rax, [r14+68h]
0x18000570f  sub     rax, [r14+60h]
0x180005713  sar     rax, 4
0x180005717  dec     eax
0x180005719  mov     [rsp+110h+length], eax
0x18000571d  mov     rcx, [rbp+57h+newString]; string
0x180005721  test    rcx, rcx
0x180005724  jnz     loc_180005819
0x18000572a  mov     ebx, [rsp+110h+length]
0x18000572e  xor     r10b, r10b
0x180005731  mov     byte ptr [rbp+57h+var_D0], r10b
0x180005735  xor     eax, eax
0x180005737  mov     word ptr [rbp+57h+var_D0+1], ax
0x18000573b  mov     byte ptr [rbp+57h+var_D0+3], al
0x18000573e  mov     dword ptr [rbp+57h+var_D0+4], ebx
0x180005741  mov     r14, [rbp+57h+var_98]
0x180005745  mov     r8, [r14+20h]
0x180005749  mov     rax, [r14+18h]
0x18000574d  cmp     rax, r8
0x180005750  jz      short loc_180005777
0x180005752  mov     edx, r15d
0x180005755  cmp     [rax], r10b
0x180005758  setz    dl
0x18000575b  mov     ecx, r15d
0x18000575e  mov     cl, 1
0x180005760  cmp     edx, ecx
0x180005762  jnz     short loc_180005769
0x180005764  cmp     [rax+4], ebx
0x180005767  jz      short loc_180005772
0x180005769  add     rax, 8
0x18000576d  cmp     rax, r8
0x180005770  jnz     short loc_180005752
0x180005772  cmp     rax, r8
0x180005775  jnz     short loc_180005791
0x180005777  mov     rdx, r8
0x18000577a  cmp     r8, [r14+28h]
0x18000577e  jnz     loc_180005B18
0x180005784  lea     r8, [rbp+57h+var_D0]
0x180005788  lea     rcx, [r14+18h]
0x18000578c  call    ??$_Emplace_reallocate@UEffectSubgraphInput@Composition@UI@Windows@@@?$vector@UEffectSubgraphInput@Composition@UI@Windows@@V?$allocator@UEffectSubgraphInput@Composition@UI@Windows@@@std@@@std@@AEAAPEAUEffectSubgraphInput@Composition@UI@Windows@@QEAU2345@$$QEAU2345@@Z; std::vector<Windows::UI::Composition::EffectSubgraphInput>::_Emplace_reallocate<Windows::UI::Composition::EffectSubgraphInput>(Windows::UI::Composition::EffectSubgraphInput * const,Windows::UI::Composition::EffectSubgraphInput &&)
0x180005791  mov     rcx, [rdi]
0x180005794  mov     rax, [rcx]
0x180005797  mov     edx, 2
0x18000579c  mov     rax, [rax+20h]
0x1800057a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057a5  test    al, al
0x1800057a7  jz      loc_180005B8B
0x1800057ad  mov     ecx, r12d
0x1800057b0  mov     rax, [rdi+8]
0x1800057b4  mov     dword ptr [rax+rcx*8], 2
0x1800057bb  mov     [rax+rcx*8+4], ebx
0x1800057bf  mov     rcx, [rbp+57h+string]; string
0x1800057c3  test    rcx, rcx
0x1800057c6  jnz     short loc_180005824
0x1800057c8  mov     rcx, [rsp+110h+var_E0]
0x1800057cd  test    rcx, rcx
0x1800057d0  jz      short loc_1800057E4
0x1800057d2  mov     [rsp+110h+var_E0], r15
0x1800057d7  mov     rax, [rcx]
0x1800057da  mov     rax, [rax+10h]
0x1800057de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057e3  nop
0x1800057e4  mov     rcx, [rsp+110h+var_E8]
0x1800057e9  test    rcx, rcx
0x1800057ec  jz      short loc_1800057FF
0x1800057ee  mov     [rsp+110h+var_E8], r15
0x1800057f3  mov     rax, [rcx]
0x1800057f6  mov     rax, [rax+10h]
0x1800057fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ff  mov     rsi, [rbp+57h+var_B0]
0x180005803  mov     rbx, 3FFFFFF43FFFFFFh
0x18000580d  inc     r12d
0x180005810  mov     r9, [rbp+57h+var_90]
0x180005814  jmp     loc_180005493
0x180005819  call    cs:__imp_WindowsDeleteString
0x18000581f  jmp     loc_18000572A
0x180005824  call    cs:__imp_WindowsDeleteString
0x18000582a  jmp     short loc_1800057C8
0x18000582c  mov     rdx, [rsi+68h]
0x180005830  mov     rcx, [rsi+60h]
0x180005834  call    __std_find_trivial_8
0x180005839  sub     rax, [rsi+60h]
0x18000583d  sar     rax, 3
0x180005841  mov     ebx, eax
0x180005843  mov     rax, [rsi+68h]
0x180005847  sub     rax, [rsi+60h]
0x18000584b  sar     rax, 3
0x18000584f  cmp     rbx, rax
0x180005852  jnb     loc_18000590C
0x180005858  mov     rcx, [rdi]
0x18000585b  mov     rax, [rcx]
0x18000585e  mov     edx, 3
0x180005863  mov     rax, [rax+20h]
0x180005867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000586c  test    al, al
0x18000586e  jz      loc_180005BC1
0x180005874  mov     ecx, r12d
0x180005877  mov     rax, [rdi+8]
0x18000587b  mov     dword ptr [rax+rcx*8], 3
0x180005882  mov     [rax+rcx*8+4], ebx
0x180005886  mov     byte ptr [rbp+57h+var_C8], 1
0x18000588a  xor     eax, eax
0x18000588c  mov     word ptr [rbp+57h+var_C8+1], ax
0x180005890  mov     byte ptr [rbp+57h+var_C8+3], al
0x180005893  mov     dword ptr [rbp+57h+var_C8+4], ebx
0x180005896  lea     rcx, [r14+18h]
0x18000589a  mov     rdx, [rcx+8]
0x18000589e  cmp     rdx, [rcx+10h]
0x1800058a2  jnz     loc_180005B29
0x1800058a8  lea     r8, [rbp+57h+var_C8]
0x1800058ac  call    ??$_Emplace_reallocate@UEffectSubgraphInput@Composition@UI@Windows@@@?$vector@UEffectSubgraphInput@Composition@UI@Windows@@V?$allocator@UEffectSubgraphInput@Composition@UI@Windows@@@std@@@std@@AEAAPEAUEffectSubgraphInput@Composition@UI@Windows@@QEAU2345@$$QEAU2345@@Z; std::vector<Windows::UI::Composition::EffectSubgraphInput>::_Emplace_reallocate<Windows::UI::Composition::EffectSubgraphInput>(Windows::UI::Composition::EffectSubgraphInput * const,Windows::UI::Composition::EffectSubgraphInput &&)
0x1800058b1  nop
0x1800058b2  mov     rcx, [rbp+57h+var_C0]
0x1800058b6  test    rcx, rcx
0x1800058b9  jz      short loc_1800058CC
0x1800058bb  mov     [rbp+57h+var_C0], r15
  ... truncated ...
```

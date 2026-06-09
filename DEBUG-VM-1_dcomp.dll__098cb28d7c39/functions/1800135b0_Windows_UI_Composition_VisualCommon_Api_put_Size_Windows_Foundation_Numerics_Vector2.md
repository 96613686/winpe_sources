# Windows::UI::Composition::VisualCommon::Api::put_Size(Windows::Foundation::Numerics::Vector2)

- ea: `0x1800135b0`
- end: `0x180013b23`
- name: `?put_Size@Api@VisualCommon@Composition@UI@Windows@@UEAAJUVector2@Numerics@Foundation@5@@Z`
- size: `1395`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180007484`
- `0x180012da0`
- `0x180012ee8`
- `0x180013528`
- `0x18001358c`
- `0x1800135b0`
- `0x180014e14`
- `0x180015ed0`
- `0x18001603c`
- `0x180016a08`
- `0x1800171b0`
- `0x1800311c8`
- `0x18004a0b8`
- `0x18008c56c`
- `0x18008c610`
- `0x1800e77ac`
- `0x1800f6f10`
- `0x1800f6f34`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001376c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001376c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013610`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013610`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001391a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013930`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001391a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180013930`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180013900`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800138ad`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800138ad`
- `ntdll!RtlLookupElementGenericTable` at `0x1800136d8`
- `ntdll!RtlLookupElementGenericTable` at `0x1800136d8`

## string_xrefs

- `0x1800138a2`: `The given object has already been closed / disposed and may no longer be used.`
- `0x180013aab`: `onecoreuap\windows\dwm\dcomp\winrtnested\WrtProxyObject.inl`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::VisualCommon::Api::put_Size(__int64 a1, void *a2)
{
  __int64 *v2; // rsi
  __int64 v3; // rbx
  int v4; // ecx
  char v5; // r15
  __int64 v6; // rax
  int v7; // edi
  struct _RTL_GENERIC_TABLE *BindingManager; // rax
  Windows::UI::Composition::AnimationBindingManager **v9; // rax
  Windows::UI::Composition::AnimationBindingManager **v10; // r15
  char v11; // al
  unsigned int v12; // r14d
  int v13; // edx
  int v14; // ecx
  _QWORD *v15; // rcx
  __int128 v16; // rdi
  __int64 j; // rbx
  unsigned __int64 v18; // rdx
  void *v19; // rcx
  __int64 v21; // rbx
  Windows::UI::Composition::AnimationBindingManager *v22; // rcx
  Windows::UI::Composition::AnimationBindingManager *i; // r14
  __int64 v24; // rdx
  const WCHAR *v25; // r14
  unsigned __int64 v26; // rdi
  unsigned int v27; // eax
  UINT32 v28; // edx
  HRESULT v29; // eax
  __int64 v30; // rax
  int v31; // r12d
  __int64 v32; // rax
  DirectComposition::CDevice *v33; // rdi
  _DWORD *v34; // rax
  Windows::UI::Composition::AnimationBindingManager *v35; // rdi
  Windows::UI::Composition::AnimationBindingManager *v36; // r13
  Windows::UI::Composition::AnimationBindingManager **v37; // r14
  Windows::UI::Composition::AnimationBindingManager *v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 (__fastcall *v41)(__int64 *, _BYTE *, int *); // rax
  int v42; // eax
  int v43; // [rsp+20h] [rbp-E0h] BYREF
  void *v44; // [rsp+28h] [rbp-D8h] BYREF
  void *v45; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v46; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v47; // [rsp+48h] [rbp-B8h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER Buffer; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v51[32]; // [rsp+90h] [rbp-70h] BYREF
  void *v52; // [rsp+B0h] [rbp-50h]
  int v53; // [rsp+F0h] [rbp-10h]
  char v54; // [rsp+F4h] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v2 = (__int64 *)(a1 - 184);
  v45 = a2;
  v3 = *(_QWORD *)(a1 - 184 + 24);
  v44 = a2;
  if ( *(_DWORD *)(v3 + 92) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession RIP");
  EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v3 + 56) + 24LL));
  v4 = *(_DWORD *)(v3 + 64);
  if ( v4 != *(_DWORD *)(v3 + 72) + *(_DWORD *)(v3 + 68) )
    Microsoft::WRL2::FailFast::Unexpected("ContextSession begin counts");
  *(_DWORD *)(v3 + 64) = v4 + 1;
  if ( (v2[6] & 2) != 0 )
  {
    if ( *((float *)v2 + 69) == *(float *)&v44 && *((float *)v2 + 70) == *((float *)&v44 + 1) )
    {
      v5 = 0;
    }
    else
    {
      *(__int64 *)((char *)v2 + 276) = (__int64)v44;
      v5 = 1;
    }
    v6 = *v2;
    BYTE2(v43) = v5;
    LOBYTE(v43) = 0;
    if ( !(*(__int64 (__fastcall **)(__int64 *))(v6 + 232))(v2) )
      goto LABEL_8;
    v25 = Windows::UI::Composition::VisualCommon::sc_Size;
    v26 = -1;
    string = 0;
    do
      ++v26;
    while ( Windows::UI::Composition::VisualCommon::sc_Size[v26] );
    if ( v26 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v27 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v26);
    v28 = v27 - 1;
    if ( (unsigned int)v26 < v27 )
      v28 = v26;
    v29 = WindowsCreateStringReference(v25, v28, &Buffer, &string);
    if ( v29 < 0 )
    {
      RaiseException(v29, 1u, 0, 0);
      __debugbreak();
    }
    v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const struct Microsoft::WRL::Wrappers::HStringReference *)&Buffer);
    Windows::UI::Composition::AnimationValueData::AnimationValueData(v51, v39);
    v40 = *v2;
    v52 = v44;
    v41 = *(__int64 (__fastcall **)(__int64 *, _BYTE *, int *))(v40 + 224);
    v54 = v5;
    v53 = 35;
    v42 = v41(v2, v51, &v43);
    v12 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\WrtProxyObject.inl",
        (const char *)(unsigned int)v42,
        v43);
      DoStackCaptureDirect(v12, 0x9C6u);
    }
    else
    {
LABEL_8:
      if ( !(_BYTE)v43 )
      {
        v7 = dword_1801D8038 & 0x7FFFFFFF;
        BindingManager = (struct _RTL_GENERIC_TABLE *)Windows::UI::Composition::CompositorCommon::GetBindingManager((Windows::UI::Composition::CompositorCommon *)v2[3]);
        LODWORD(v45) = *((_DWORD *)v2 + 36);
        HIDWORD(v45) = v7;
        Buffer.Reserved.Reserved1 = v45;
        *(_OWORD *)&Buffer.Reserved.Reserved2[8] = 0;
        v9 = (Windows::UI::Composition::AnimationBindingManager **)RtlLookupElementGenericTable(BindingManager, &Buffer);
        v10 = v9;
        if ( v9 )
        {
          v22 = v9[1];
          BYTE1(v43) = 1;
          if ( v22 )
          {
            BYTE1(v43) = 1;
            do
            {
              *((_WORD *)v22 + 8) = 0;
              *((_BYTE *)v22 + 18) = 0;
              v22 = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)v22 + 3);
            }
            while ( v22 );
          }
          for ( i = v9[2]; i; i = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)i + 3) )
          {
            v30 = *((_QWORD *)i + 1);
            *((_WORD *)i + 8) = 0;
            *((_BYTE *)i + 18) = 0;
            v31 = *(_DWORD *)(v30 + 144);
            if ( v31 )
            {
              v32 = *(_QWORD *)(v30 + 24);
              v45 = 0;
              v33 = *(DirectComposition::CDevice **)(v32 + 440);
              DirectComposition::CDevice::BeginKernelCommand(v33, 0x18u, &v45, 0);
              v34 = v45;
              *(_DWORD *)v45 = 11;
              v34[1] = v31;
              v34[2] = 7;
              *((_QWORD *)v34 + 2) = 0;
              v22 = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)v33 + 11);
              if ( v22 )
                (*(void (__fastcall **)(Windows::UI::Composition::AnimationBindingManager *))(*(_QWORD *)v22 + 24LL))(v22);
            }
          }
          v35 = v10[1];
          v36 = v35;
          while ( v35 )
          {
            v37 = (Windows::UI::Composition::AnimationBindingManager **)((char *)v35 + 24);
            if ( Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(
                   v22,
                   *(struct SubchannelMaskInfo **)v35) )
            {
              Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(*((_QWORD *)v35 + 1), 6, 1);
              v38 = *v37;
              if ( v35 == v10[1] )
                v10[1] = v38;
              else
                *((_QWORD *)v36 + 3) = v38;
              v22 = v35;
              v35 = *v37;
              *v37 = v10[2];
              v10[2] = v22;
            }
            else
            {
              v36 = v35;
              v35 = *v37;
            }
          }
          v11 = BYTE1(v43);
        }
        else
        {
          v11 = 0;
        }
        if ( BYTE2(v43) || v11 )
        {
          v24 = (unsigned int)dword_1801D8038;
          LODWORD(v24) = dword_1801D8038 & 0x7FFFFFFF;
          if ( byte_1801D8040 )
          {
            if ( byte_1801D8040 != 1 )
              Microsoft::WRL2::FailFast::Unexpected(0);
            Windows::UI::Composition::ProxyObject::SetBufferProperty(v2, v24, &v44, 8);
          }
          else
          {
            Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(v2, v24);
          }
        }
      }
      v12 = 0;
    }
    v13 = *(_DWORD *)(v3 + 72);
    v14 = v13 + *(_DWORD *)(v3 + 68);
    if ( --*(_DWORD *)(v3 + 64) != v14 )
      Microsoft::WRL2::FailFast::Unexpected("ContextSession end counts");
    v47 = 0;
    v46 = 0;
    if ( v13 || (v15 = (_QWORD *)(v3 + 120), &v46 == (__int128 *)(v3 + 120)) )
    {
      v16 = v46;
    }
    else
    {
      *(_QWORD *)&v16 = *v15;
      *v15 = 0;
      *((_QWORD *)&v16 + 1) = *(_QWORD *)(v3 + 128);
      *(_QWORD *)(v3 + 128) = 0;
      v47 = *(_QWORD *)(v3 + 136);
      v46 = v16;
      *(_QWORD *)(v3 + 136) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v3 + 56) + 24LL));
    if ( (_QWORD)v16 != *((_QWORD *)&v16 + 1) )
    {
      Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(&v46);
      v16 = v46;
      if ( (_QWORD)v46 != *((_QWORD *)&v46 + 1) )
      {
        v21 = v46;
        do
        {
          std::_Func_class<void,>::_Tidy(v21);
          v21 += 64;
        }
        while ( v21 != *((_QWORD *)&v16 + 1) );
        *((_QWORD *)&v16 + 1) = v16;
      }
    }
    if ( (_QWORD)v16 )
    {
      for ( j = v16; j != *((_QWORD *)&v16 + 1); j += 64 )
        std::_Func_class<void,>::_Tidy(j);
      v18 = (v47 - v16) & 0xFFFFFFFFFFFFFFC0uLL;
      if ( v18 >= 0x1000 )
      {
        v19 = *(void **)(v16 - 8);
        if ( (unsigned __int64)(v16 - (_QWORD)v19 - 8) > 0x1F )
          __fastfail(5u);
        v18 += 39LL;
      }
      else
      {
        v19 = (void *)v16;
      }
      operator delete(v19, v18);
    }
    return v12;
  }
  else
  {
    RoOriginateErrorW(
      2147483667LL,
      0,
      L"The given object has already been closed / disposed and may no longer be used.");
    Microsoft::WRL2::ContextSession::EndApiEntry((Microsoft::WRL2::ContextSession *)v3);
    return 2147483667LL;
  }
}

```

## disassembly

```asm
0x1800135b0  mov     [rsp-8+arg_10], rbx
0x1800135b5  push    rbp
0x1800135b6  push    rsi
0x1800135b7  push    rdi
0x1800135b8  push    r12
0x1800135ba  push    r13
0x1800135bc  push    r14
0x1800135be  push    r15
0x1800135c0  lea     rbp, [rsp-10h]
0x1800135c5  sub     rsp, 110h
0x1800135cc  mov     rax, cs:__security_cookie
0x1800135d3  xor     rax, rsp
0x1800135d6  mov     [rbp+40h+var_40], rax
0x1800135da  lea     rsi, [rcx-0B8h]
0x1800135e1  mov     [rsp+140h+var_110], rdx
0x1800135e6  mov     rbx, [rsi+18h]
0x1800135ea  xor     r13d, r13d
0x1800135ed  movss   xmm0, dword ptr [rsp+140h+var_110+4]
0x1800135f3  movss   [rsp+140h+var_114], xmm0
0x1800135f9  mov     [rsp+140h+var_118], edx
0x1800135fd  mov     eax, [rbx+5Ch]
0x180013600  test    eax, eax
0x180013602  jnz     loc_180013AE7
0x180013608  mov     rcx, [rbx+38h]
0x18001360c  add     rcx, 18h; lpCriticalSection
0x180013610  call    cs:__imp_EnterCriticalSection
0x180013616  mov     eax, [rbx+44h]
0x180013619  add     eax, [rbx+48h]
0x18001361c  mov     ecx, [rbx+40h]
0x18001361f  cmp     ecx, eax
0x180013621  jnz     loc_180013ADA
0x180013627  lea     eax, [rcx+1]
0x18001362a  mov     [rbx+40h], eax
0x18001362d  test    byte ptr [rsi+30h], 2
0x180013631  jz      loc_18001389D
0x180013637  movss   xmm1, [rsp+140h+var_118]
0x18001363d  movss   xmm0, dword ptr [rsi+114h]
0x180013645  ucomiss xmm0, xmm1
0x180013648  jp      loc_180013819
0x18001364e  jnz     loc_180013819
0x180013654  movss   xmm0, dword ptr [rsi+118h]
0x18001365c  ucomiss xmm0, [rsp+140h+var_114]
0x180013661  jp      loc_180013819
0x180013667  jnz     loc_180013819
0x18001366d  mov     r15b, r13b
0x180013670  mov     rax, [rsi]
0x180013673  mov     rcx, rsi
0x180013676  mov     byte ptr [rsp+140h+var_120+2], r15b
0x18001367b  mov     byte ptr [rsp+140h+var_120], r13b; int
0x180013680  mov     rax, [rax+0E8h]
0x180013687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001368c  test    rax, rax
0x18001368f  jnz     loc_1800138C2
0x180013695  cmp     byte ptr [rsp+140h+var_120], r13b
0x18001369a  jnz     short loc_180013700
0x18001369c  mov     edi, cs:dword_1801D8038
0x1800136a2  mov     rcx, [rsi+18h]; this
0x1800136a6  btr     edi, 1Fh
0x1800136aa  call    ?GetBindingManager@CompositorCommon@Composition@UI@Windows@@QEAAPEAVAnimationBindingManager@234@XZ; Windows::UI::Composition::CompositorCommon::GetBindingManager(void)
0x1800136af  mov     ecx, [rsi+90h]
0x1800136b5  lea     rdx, [rsp+140h+Buffer]; Buffer
0x1800136ba  mov     dword ptr [rsp+140h+var_110], ecx
0x1800136be  xorps   xmm0, xmm0
0x1800136c1  mov     dword ptr [rsp+140h+var_110+4], edi
0x1800136c5  mov     rcx, [rsp+140h+var_110]
0x1800136ca  mov     [rsp+140h+Buffer], rcx
0x1800136cf  mov     rcx, rax; Table
0x1800136d2  movdqu  [rsp+140h+var_C8], xmm0
0x1800136d8  call    cs:__imp_RtlLookupElementGenericTable
0x1800136de  mov     r15, rax
0x1800136e1  test    rax, rax
0x1800136e4  jnz     loc_180013837
0x1800136ea  mov     al, r13b
0x1800136ed  cmp     byte ptr [rsp+140h+var_120+2], r13b
0x1800136f2  jnz     loc_180013865
0x1800136f8  test    al, al
0x1800136fa  jnz     loc_180013865
0x180013700  mov     r14d, r13d
0x180013703  mov     ecx, [rbx+44h]
0x180013706  mov     edx, [rbx+48h]
0x180013709  add     ecx, edx
0x18001370b  dec     dword ptr [rbx+40h]
0x18001370e  cmp     [rbx+40h], ecx
0x180013711  jnz     loc_180013B0F
0x180013717  mov     [rsp+140h+var_F8], r13
0x18001371c  xorps   xmm0, xmm0
0x18001371f  movdqu  [rsp+140h+var_108], xmm0
0x180013725  test    edx, edx
0x180013727  jnz     loc_180013A0D
0x18001372d  lea     rcx, [rbx+78h]
0x180013731  lea     rax, [rsp+140h+var_108]
0x180013736  cmp     rax, rcx
0x180013739  jz      loc_180013A0D
0x18001373f  mov     rdi, [rcx]
0x180013742  mov     [rcx], r13
0x180013745  mov     rsi, [rcx+8]
0x180013749  mov     [rcx+8], r13
0x18001374d  mov     rax, [rcx+10h]
0x180013751  mov     [rsp+140h+var_F8], rax
0x180013756  mov     qword ptr [rsp+140h+var_108], rdi
0x18001375b  mov     qword ptr [rsp+140h+var_108+8], rsi
0x180013760  mov     [rcx+10h], r13
0x180013764  mov     rcx, [rbx+38h]
0x180013768  add     rcx, 18h; lpCriticalSection
0x18001376c  call    cs:__imp_LeaveCriticalSection
0x180013772  cmp     rdi, rsi
0x180013775  jnz     short loc_1800137E0
0x180013777  test    rdi, rdi
0x18001377a  jz      short loc_1800137B6
0x18001377c  mov     rbx, rdi
0x18001377f  cmp     rdi, rsi
0x180013782  jz      short loc_180013795
0x180013784  mov     rcx, rbx
0x180013787  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x18001378c  add     rbx, 40h ; '@'
0x180013790  cmp     rbx, rsi
0x180013793  jnz     short loc_180013784
0x180013795  mov     rdx, [rsp+140h+var_F8]
0x18001379a  sub     rdx, rdi
0x18001379d  and     rdx, 0FFFFFFFFFFFFFFC0h; unsigned __int64
0x1800137a1  cmp     rdx, 1000h
0x1800137a8  jnb     loc_180013A1C
0x1800137ae  mov     rcx, rdi; void *
0x1800137b1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800137b6  mov     eax, r14d
0x1800137b9  mov     rcx, [rbp+40h+var_40]
0x1800137bd  xor     rcx, rsp; StackCookie
0x1800137c0  call    __security_check_cookie
0x1800137c5  mov     rbx, [rsp+140h+arg_10]
0x1800137cd  add     rsp, 110h
0x1800137d4  pop     r15
0x1800137d6  pop     r14
0x1800137d8  pop     r13
0x1800137da  pop     r12
0x1800137dc  pop     rdi
0x1800137dd  pop     rsi
0x1800137de  pop     rbp
0x1800137df  retn
0x1800137e0  lea     rcx, [rsp+140h+var_108]
0x1800137e5  call    ?ProcessDeferredOperations_NoLock@ContextSession@WRL2@Microsoft@@CAXAEBV?$vector@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@@Z; Microsoft::WRL2::ContextSession::ProcessDeferredOperations_NoLock(std::vector<std::function<void (void)>> const &)
0x1800137ea  mov     rdi, qword ptr [rsp+140h+var_108]
0x1800137ef  mov     rsi, qword ptr [rsp+140h+var_108+8]
0x1800137f4  cmp     rdi, rsi
0x1800137f7  jz      loc_180013777
0x1800137fd  mov     rbx, rdi
0x180013800  mov     rcx, rbx
0x180013803  call    ?_Tidy@?$_Func_class@X$$V@std@@IEAAXXZ; std::_Func_class<void,>::_Tidy(void)
0x180013808  add     rbx, 40h ; '@'
0x18001380c  cmp     rbx, rsi
0x18001380f  jnz     short loc_180013800
0x180013811  mov     rsi, rdi
0x180013814  jmp     loc_180013777
0x180013819  movss   dword ptr [rsi+114h], xmm1
0x180013821  mov     r15b, 1
0x180013824  movss   xmm0, [rsp+140h+var_114]
0x18001382a  movss   dword ptr [rsi+118h], xmm0
0x180013832  jmp     loc_180013670
0x180013837  mov     rcx, [rax+8]
0x18001383b  mov     byte ptr [rsp+140h+var_120+1], 1
0x180013840  test    rcx, rcx
0x180013843  jz      short loc_18001385C
0x180013845  mov     byte ptr [rsp+140h+var_120+1], 1
0x18001384a  mov     [rcx+10h], r13w
0x18001384f  mov     [rcx+12h], r13b
0x180013853  mov     rcx, [rcx+18h]
0x180013857  test    rcx, rcx
0x18001385a  jnz     short loc_18001384A
0x18001385c  mov     r14, [rax+10h]
0x180013860  jmp     loc_180013947
0x180013865  mov     edx, cs:dword_1801D8038
0x18001386b  mov     al, cs:byte_1801D8040
0x180013871  btr     edx, 1Fh
0x180013875  test    al, al
0x180013877  jz      loc_180013AFC
0x18001387d  cmp     al, 1
0x18001387f  jnz     loc_180013AF4
0x180013885  mov     r9d, 8
0x18001388b  lea     r8, [rsp+140h+var_118]
0x180013890  mov     rcx, rsi
0x180013893  call    ?SetBufferProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@PEBX_K@Z; Windows::UI::Composition::ProxyObject::SetBufferProperty(DCOMPOSITION_PROPERTY_ID,void const *,unsigned __int64)
0x180013898  jmp     loc_180013700
0x18001389d  mov     edi, 80000013h
0x1800138a2  lea     r8, aTheGivenObject; "The given object has already been close"...
0x1800138a9  mov     ecx, edi
0x1800138ab  xor     edx, edx
0x1800138ad  call    cs:__imp_RoOriginateErrorW
0x1800138b3  mov     rcx, rbx; this
0x1800138b6  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x1800138bb  mov     eax, edi
0x1800138bd  jmp     loc_1800137B9
0x1800138c2  mov     r14, cs:?sc_Size@VisualCommon@Composition@UI@Windows@@0UAnimatedProperty@AnimationHelper@234@B; Windows::UI::Composition::AnimationHelper::AnimatedProperty const Windows::UI::Composition::VisualCommon::sc_Size
0x1800138c9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800138cd  mov     [rbp+40h+string], r13
0x1800138d1  inc     rdi
0x1800138d4  cmp     [r14+rdi*2], r13w
0x1800138d9  jnz     short loc_1800138D1
0x1800138db  mov     eax, 0FFFFFFFFh
0x1800138e0  cmp     rdi, rax
0x1800138e3  ja      short loc_180013921
0x1800138e5  mov     ecx, edi; unsigned int
0x1800138e7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800138ec  cmp     edi, eax
0x1800138ee  lea     r9, [rbp+40h+string]; string
0x1800138f2  lea     r8, [rsp+140h+Buffer]; hstringHeader
0x1800138f7  mov     rcx, r14; sourceString
0x1800138fa  lea     edx, [rax-1]
0x1800138fd  cmovb   edx, edi; length
0x180013900  call    cs:__imp_WindowsCreateStringReference
0x180013906  test    eax, eax
0x180013908  jns     loc_180013A45
0x18001390e  xor     r9d, r9d; lpArguments
0x180013911  xor     r8d, r8d; nNumberOfArguments
0x180013914  mov     ecx, eax; dwExceptionCode
0x180013916  lea     edx, [r9+1]; dwExceptionFlags
0x18001391a  call    cs:__imp_RaiseException
0x180013920  int     3; Trap to Debugger
0x180013921  xor     r9d, r9d; lpArguments
0x180013924  xor     r8d, r8d; nNumberOfArguments
0x180013927  mov     ecx, 80070216h; dwExceptionCode
0x18001392c  lea     edx, [r9+1]; dwExceptionFlags
0x180013930  call    cs:__imp_RaiseException
0x180013936  int     3; Trap to Debugger
0x180013937  mov     rax, [rcx]
0x18001393a  mov     rax, [rax+18h]
0x18001393e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013943  mov     r14, [r14+18h]
0x180013947  test    r14, r14
0x18001394a  jz      short loc_1800139AE
0x18001394c  mov     rax, [r14+8]
0x180013950  mov     [r14+10h], r13w
0x180013955  mov     [r14+12h], r13b
0x180013959  mov     r12d, [rax+90h]
0x180013960  test    r12d, r12d
0x180013963  jz      short loc_180013943
0x180013965  mov     rax, [rax+18h]
0x180013969  lea     r8, [rsp+140h+var_110]; void **
0x18001396e  xor     r9d, r9d; bool
0x180013971  mov     [rsp+140h+var_110], r13
0x180013976  mov     rdi, [rax+1B8h]
0x18001397d  mov     rcx, rdi; this
0x180013980  lea     edx, [r9+18h]; unsigned int
0x180013984  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x180013989  mov     rax, [rsp+140h+var_110]
0x18001398e  mov     dword ptr [rax], 0Bh
0x180013994  mov     [rax+4], r12d
0x180013998  mov     dword ptr [rax+8], 7
0x18001399f  mov     [rax+10h], r13
0x1800139a3  mov     rcx, [rdi+58h]
0x1800139a7  test    rcx, rcx
0x1800139aa  jnz     short loc_180013937
0x1800139ac  jmp     short loc_180013943
0x1800139ae  mov     rdi, [r15+8]
0x1800139b2  mov     r13, rdi
0x1800139b5  test    rdi, rdi
0x1800139b8  jnz     short loc_1800139C6
0x1800139ba  mov     al, byte ptr [rsp+140h+var_120+1]
0x1800139be  xor     r13d, r13d
0x1800139c1  jmp     loc_1800136ED
0x1800139c6  mov     rdx, [rdi]; struct SubchannelMaskInfo *
0x1800139c9  call    ?GetSubchannelsFromMask@AnimationBindingManager@Composition@UI@Windows@@AEAAGPEAVSubchannelMaskInfo@@@Z; Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(SubchannelMaskInfo *)
0x1800139ce  lea     r14, [rdi+18h]
0x1800139d2  test    ax, ax
0x1800139d5  jz      short loc_180013A3A
0x1800139d7  mov     rcx, [rdi+8]
0x1800139db  mov     edx, 6
0x1800139e0  lea     r8d, [rdx-5]
0x1800139e4  call    ?SetScalarIntegerProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@_J@Z; Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(DCOMPOSITION_PROPERTY_ID,__int64)
0x1800139e9  mov     rax, [r14]
0x1800139ec  cmp     rdi, [r15+8]
0x1800139f0  jnz     loc_180013AD1
0x1800139f6  mov     [r15+8], rax
0x1800139fa  mov     rax, [r15+10h]
0x1800139fe  mov     rcx, rdi
0x180013a01  mov     rdi, [r14]
0x180013a04  mov     [r14], rax
0x180013a07  mov     [r15+10h], rcx
0x180013a0b  jmp     short loc_1800139B5
0x180013a0d  mov     rsi, qword ptr [rsp+140h+var_108+8]
0x180013a12  mov     rdi, qword ptr [rsp+140h+var_108]
0x180013a17  jmp     loc_180013764
0x180013a1c  mov     rcx, [rdi-8]
0x180013a20  sub     rdi, rcx
0x180013a23  sub     rdi, 8
0x180013a27  cmp     rdi, 1Fh
0x180013a2b  ja      loc_180013B1C
0x180013a31  add     rdx, 27h ; '''
0x180013a35  jmp     loc_1800137B1
0x180013a3a  mov     r13, rdi
0x180013a3d  mov     rdi, [r14]
0x180013a40  jmp     loc_1800139B5
0x180013a45  lea     rdx, [rsp+140h+Buffer]; struct Microsoft::WRL::Wrappers::HStringReference *
0x180013a4a  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x180013a4f  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV0123@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Microsoft::WRL::Wrappers::HStringReference const &)
0x180013a54  mov     rdx, rax
0x180013a57  lea     rcx, [rbp+40h+var_B0]
0x180013a5b  call    ??0AnimationValueData@Composition@UI@Windows@@QEAA@VHStringReference@Wrappers@WRL@Microsoft@@@Z; Windows::UI::Composition::AnimationValueData::AnimationValueData(Microsoft::WRL::Wrappers::HStringReference)
0x180013a60  mov     rax, [rsi]
0x180013a63  lea     r8, [rsp+140h+var_120]
0x180013a68  movss   xmm0, [rsp+140h+var_118]
0x180013a6e  lea     rdx, [rbp+40h+var_B0]
  ... truncated ...
```

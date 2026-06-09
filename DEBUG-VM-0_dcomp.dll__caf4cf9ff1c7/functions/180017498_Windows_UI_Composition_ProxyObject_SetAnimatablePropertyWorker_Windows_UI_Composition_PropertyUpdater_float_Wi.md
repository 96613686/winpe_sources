# Windows::UI::Composition::ProxyObject::SetAnimatablePropertyWorker<Windows::UI::Composition::PropertyUpdater<float>,Windows::UI::Composition::PropertyUpdateInfo>(Windows::UI::Composition::PropertyUpdater<float> &,Windows::UI::Composition::PropertyUpdateInfo const &)

- ea: `0x180017498`
- end: `0x180017886`
- name: `??$SetAnimatablePropertyWorker@V?$PropertyUpdater@M@Composition@UI@Windows@@VPropertyUpdateInfo@234@@ProxyObject@Composition@UI@Windows@@IEAAJAEAV?$PropertyUpdater@M@123@AEBVPropertyUpdateInfo@123@@Z`
- size: `1006`
- prototype: ``
- caller_count: `7`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017fe8`
- `0x180018078`
- `0x180054d88`
- `0x1800bbf84`
- `0x1800c8960`
- `0x1800ce8cc`
- `0x1800cf320`

## callees

- `0x180007484`
- `0x18001358c`
- `0x180015ed0`
- `0x18001603c`
- `0x180016a08`
- `0x1800171b0`
- `0x180017498`
- `0x1800981e4`
- `0x1800f6f10`
- `0x1800f7a80`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017610`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017639`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017798`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800177f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017610`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017639`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017798`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800177f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017757`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800177b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017757`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800177b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800175f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800177db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800175f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017782`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800177db`
- `ntdll!RtlLookupElementGenericTable` at `0x18001755b`
- `ntdll!RtlLookupElementGenericTable` at `0x18001755b`

## string_xrefs

- `0x180017840`: `onecoreuap\windows\dwm\dcomp\winrtnested\WrtProxyObject.inl`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ProxyObject::SetAnimatablePropertyWorker<Windows::UI::Composition::PropertyUpdater<float>,Windows::UI::Composition::PropertyUpdateInfo>(
        __int64 *a1,
        __int64 a2,
        const WCHAR ***a3)
{
  _DWORD *v3; // rax
  const WCHAR ***v4; // rdi
  __int64 v5; // r12
  char v7; // r13
  __int64 v8; // rax
  int v9; // ebx
  struct _RTL_GENERIC_TABLE *BindingManager; // rax
  _QWORD *v11; // rax
  Windows::UI::Composition::AnimationBindingManager *v12; // rcx
  _QWORD *v13; // rsi
  unsigned __int64 v15; // rbx
  const WCHAR *v16; // rdi
  _DWORD *v17; // rsi
  unsigned int v18; // eax
  UINT32 v19; // edx
  HRESULT v20; // eax
  __int64 i; // rax
  __int64 j; // rdi
  __int64 v23; // rax
  int v24; // r15d
  __int64 v25; // rax
  DirectComposition::CDevice *v26; // rbx
  __int64 v27; // rax
  _QWORD *v28; // rbx
  _QWORD *v29; // r15
  _QWORD *v30; // rdi
  _QWORD *v31; // rax
  const WCHAR *StringRawBuffer; // rbx
  unsigned int v33; // eax
  UINT32 v34; // edx
  HRESULT v35; // eax
  const WCHAR *v36; // rbx
  unsigned int v37; // eax
  UINT32 v38; // edx
  HRESULT v39; // eax
  __int64 v40; // rax
  __int64 (__fastcall *v41)(__int64 *, HSTRING_HEADER *, char *); // rax
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // [rsp+20h] [rbp-E0h]
  char v45[8]; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-C8h] BYREF
  const WCHAR ***v47; // [rsp+40h] [rbp-C0h]
  __int64 v48; // [rsp+48h] [rbp-B8h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v50; // [rsp+68h] [rbp-98h] BYREF
  HSTRING_HEADER Buffer; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+88h] [rbp-78h] BYREF
  HSTRING_HEADER v53; // [rsp+90h] [rbp-70h] BYREF
  HSTRING v54; // [rsp+A8h] [rbp-58h] BYREF
  _DWORD v55[17]; // [rsp+B0h] [rbp-50h] BYREF
  char v56; // [rsp+F4h] [rbp-Ch]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v3 = *(_DWORD **)(a2 + 8);
  v4 = a3;
  v47 = a3;
  v5 = a2;
  v48 = a2;
  if ( **(float **)a2 == *(float *)v3 )
  {
    v7 = 0;
  }
  else
  {
    **(_DWORD **)a2 = *v3;
    v7 = 1;
  }
  v8 = *a1;
  v45[0] = 0;
  if ( (*(__int64 (__fastcall **)(__int64 *))(v8 + 232))(a1) )
  {
    v15 = -1;
    v16 = **v4;
    string = 0;
    do
      ++v15;
    while ( v16[v15] );
    if ( v15 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v17 = *(_DWORD **)(v5 + 16);
    v18 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v15);
    v19 = v18 - 1;
    if ( (unsigned int)v15 < v18 )
      v19 = v15;
    v20 = WindowsCreateStringReference(v16, v19, &Buffer, &string);
    if ( v20 < 0 )
    {
      RaiseException(v20, 1u, 0, 0);
      __debugbreak();
    }
    v50 = 0;
    length[0] = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, length);
    v33 = Microsoft::WRL::Wrappers::HStringReference::AddOne(length[0]);
    v34 = v33 - 1;
    if ( length[0] < v33 )
      v34 = length[0];
    v35 = WindowsCreateStringReference(StringRawBuffer, v34, &hstringHeader, &v50);
    if ( v35 < 0 )
    {
      RaiseException(v35, 1u, 0, 0);
      __debugbreak();
    }
    v54 = 0;
    length[0] = 0;
    v36 = WindowsGetStringRawBuffer(v50, length);
    v37 = Microsoft::WRL::Wrappers::HStringReference::AddOne(length[0]);
    v38 = v37 - 1;
    if ( length[0] < v37 )
      v38 = length[0];
    v39 = WindowsCreateStringReference(v36, v38, &v53, &v54);
    if ( v39 < 0 )
    {
      RaiseException(v39, 1u, 0, 0);
      __debugbreak();
    }
    memset_0(v55, 0, 0x40u);
    v40 = *a1;
    v56 = v7;
    v55[16] = 18;
    v41 = *(__int64 (__fastcall **)(__int64 *, HSTRING_HEADER *, char *))(v40 + 224);
    v55[0] = *v17;
    v42 = v41(a1, &v53, v45);
    v43 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\WrtProxyObject.inl",
        (const char *)(unsigned int)v42,
        v44);
      return v43;
    }
    v4 = v47;
  }
  if ( !v45[0] )
  {
    if ( !*(_QWORD *)(v5 + 8) )
    {
      ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
      __debugbreak();
    }
    v9 = (_DWORD)(*v4)[1] & 0x7FFFFFFF;
    BindingManager = (struct _RTL_GENERIC_TABLE *)Windows::UI::Composition::CompositorCommon::GetBindingManager((Windows::UI::Composition::CompositorCommon *)a1[3]);
    LODWORD(Buffer.Reserved.Reserved1) = *((_DWORD *)a1 + 36);
    *(_DWORD *)&Buffer.Reserved.Reserved2[4] = v9;
    *(_OWORD *)&Buffer.Reserved.Reserved2[8] = 0;
    v11 = RtlLookupElementGenericTable(BindingManager, &Buffer);
    v13 = v11;
    if ( v11 )
    {
      for ( i = v11[1]; i; i = *(_QWORD *)(i + 24) )
      {
        *(_WORD *)(i + 16) = 0;
        *(_BYTE *)(i + 18) = 0;
      }
      for ( j = v13[2]; j; j = *(_QWORD *)(j + 24) )
      {
        v23 = *(_QWORD *)(j + 8);
        v12 = 0;
        *(_WORD *)(j + 16) = 0;
        *(_BYTE *)(j + 18) = 0;
        v24 = *(_DWORD *)(v23 + 144);
        if ( v24 )
        {
          v25 = *(_QWORD *)(v23 + 24);
          *(_QWORD *)length = 0;
          v26 = *(DirectComposition::CDevice **)(v25 + 440);
          DirectComposition::CDevice::BeginKernelCommand(v26, 0x18u, (void **)length, 0);
          v27 = *(_QWORD *)length;
          **(_DWORD **)length = 11;
          *(_DWORD *)(v27 + 4) = v24;
          *(_DWORD *)(v27 + 8) = 7;
          *(_QWORD *)(v27 + 16) = 0;
          v12 = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)v26 + 11);
          if ( v12 )
            (*(void (__fastcall **)(Windows::UI::Composition::AnimationBindingManager *))(*(_QWORD *)v12 + 24LL))(v12);
        }
      }
      v28 = (_QWORD *)v13[1];
      v29 = v28;
      while ( v28 )
      {
        v30 = v28 + 3;
        if ( Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(
               v12,
               (struct SubchannelMaskInfo *)*v28) )
        {
          Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(v28[1], 6, 1);
          v31 = (_QWORD *)*v30;
          if ( v28 == (_QWORD *)v13[1] )
            v13[1] = v31;
          else
            v29[3] = v31;
          v12 = (Windows::UI::Composition::AnimationBindingManager *)v28;
          v28 = (_QWORD *)*v30;
          *v30 = v13[2];
          v13[2] = v12;
        }
        else
        {
          v29 = v28;
          v28 = (_QWORD *)*v30;
        }
      }
      v5 = v48;
      v4 = v47;
    }
    if ( v7 || v13 )
      Windows::UI::Composition::ProxyObject::UpdateAnimatedPropertyWorker<Windows::UI::Composition::PropertyUpdater<float>,Windows::UI::Composition::PropertyUpdateInfo>(
        a1,
        v5,
        v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180017498  mov     [rsp-8+arg_18], rbx
0x18001749d  push    rbp
0x18001749e  push    rsi
0x18001749f  push    rdi
0x1800174a0  push    r12
0x1800174a2  push    r13
0x1800174a4  push    r14
0x1800174a6  push    r15
0x1800174a8  lea     rbp, [rsp-10h]
0x1800174ad  sub     rsp, 110h
0x1800174b4  mov     rax, cs:__security_cookie
0x1800174bb  xor     rax, rsp
0x1800174be  mov     [rbp+40h+var_40], rax
0x1800174c2  mov     rax, [rdx+8]
0x1800174c6  xor     r15d, r15d
0x1800174c9  mov     rdi, r8
0x1800174cc  mov     [rsp+140h+var_100], r8
0x1800174d1  mov     r12, rdx
0x1800174d4  mov     [rsp+140h+var_F8], rdx
0x1800174d9  mov     r14, rcx
0x1800174dc  movss   xmm1, dword ptr [rax]
0x1800174e0  mov     rax, [rdx]
0x1800174e3  movss   xmm0, dword ptr [rax]
0x1800174e7  ucomiss xmm0, xmm1
0x1800174ea  jp      loc_1800175A8
0x1800174f0  jnz     loc_1800175A8
0x1800174f6  mov     r13b, r15b
0x1800174f9  mov     rax, [rcx]
0x1800174fc  mov     [rsp+140h+var_110], r15b
0x180017501  mov     rax, [rax+0E8h]
0x180017508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001750d  test    rax, rax
0x180017510  jnz     loc_1800175B4
0x180017516  cmp     [rsp+140h+var_110], r15b
0x18001751b  jnz     short loc_18001757F
0x18001751d  cmp     [r12+8], r15
0x180017522  jz      loc_18001786F
0x180017528  mov     rax, [rdi]
0x18001752b  mov     rcx, [r14+18h]; this
0x18001752f  mov     ebx, [rax+8]
0x180017532  btr     ebx, 1Fh
0x180017536  call    ?GetBindingManager@CompositorCommon@Composition@UI@Windows@@QEAAPEAVAnimationBindingManager@234@XZ; Windows::UI::Composition::CompositorCommon::GetBindingManager(void)
0x18001753b  mov     ecx, [r14+90h]
0x180017542  lea     rdx, [rsp+140h+Buffer]; Buffer
0x180017547  mov     [rsp+140h+Buffer], ecx
0x18001754b  xorps   xmm0, xmm0
0x18001754e  mov     rcx, rax; Table
0x180017551  mov     [rsp+140h+var_CC], ebx
0x180017555  movdqu  [rsp+140h+var_C8], xmm0
0x18001755b  call    cs:__imp_RtlLookupElementGenericTable
0x180017561  mov     rsi, rax
0x180017564  test    rax, rax
0x180017567  jnz     loc_180017640
0x18001756d  test    r13b, r13b
0x180017570  jnz     loc_180017617
0x180017576  test    rsi, rsi
0x180017579  jnz     loc_180017617
0x18001757f  xor     eax, eax
0x180017581  mov     rcx, [rbp+40h+var_40]
0x180017585  xor     rcx, rsp; StackCookie
0x180017588  call    __security_check_cookie
0x18001758d  mov     rbx, [rsp+140h+arg_18]
0x180017595  add     rsp, 110h
0x18001759c  pop     r15
0x18001759e  pop     r14
0x1800175a0  pop     r13
0x1800175a2  pop     r12
0x1800175a4  pop     rdi
0x1800175a5  pop     rsi
0x1800175a6  pop     rbp
0x1800175a7  retn
0x1800175a8  movss   dword ptr [rax], xmm1
0x1800175ac  mov     r13b, 1
0x1800175af  jmp     loc_1800174F9
0x1800175b4  mov     rax, [rdi]
0x1800175b7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800175bb  mov     rdi, [rax]
0x1800175be  mov     [rbp+40h+string], r15
0x1800175c2  inc     rbx
0x1800175c5  cmp     [rdi+rbx*2], r15w
0x1800175ca  jnz     short loc_1800175C2
0x1800175cc  mov     eax, 0FFFFFFFFh
0x1800175d1  cmp     rbx, rax
0x1800175d4  ja      short loc_18001762A
0x1800175d6  mov     rsi, [r12+10h]
0x1800175db  mov     ecx, ebx; unsigned int
0x1800175dd  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800175e2  cmp     ebx, eax
0x1800175e4  lea     r9, [rbp+40h+string]; string
0x1800175e8  lea     r8, [rsp+140h+Buffer]; hstringHeader
0x1800175ed  mov     rcx, rdi; sourceString
0x1800175f0  lea     edx, [rax-1]
0x1800175f3  cmovb   edx, ebx; length
0x1800175f6  call    cs:__imp_WindowsCreateStringReference
0x1800175fc  test    eax, eax
0x1800175fe  jns     loc_180017744
0x180017604  xor     r9d, r9d; lpArguments
0x180017607  xor     r8d, r8d; nNumberOfArguments
0x18001760a  mov     ecx, eax; dwExceptionCode
0x18001760c  lea     edx, [r9+1]; dwExceptionFlags
0x180017610  call    cs:__imp_RaiseException
0x180017616  int     3; Trap to Debugger
0x180017617  mov     r8, rdi
0x18001761a  mov     rdx, r12
0x18001761d  mov     rcx, r14
0x180017620  call    ??$UpdateAnimatedPropertyWorker@V?$PropertyUpdater@M@Composition@UI@Windows@@VPropertyUpdateInfo@234@@ProxyObject@Composition@UI@Windows@@IEAAXAEAV?$PropertyUpdater@M@123@AEBVPropertyUpdateInfo@123@_N2G@Z; Windows::UI::Composition::ProxyObject::UpdateAnimatedPropertyWorker<Windows::UI::Composition::PropertyUpdater<float>,Windows::UI::Composition::PropertyUpdateInfo>(Windows::UI::Composition::PropertyUpdater<float> &,Windows::UI::Composition::PropertyUpdateInfo const &,bool,bool,ushort)
0x180017625  jmp     loc_18001757F
0x18001762a  xor     r9d, r9d; lpArguments
0x18001762d  xor     r8d, r8d; nNumberOfArguments
0x180017630  mov     ecx, 80070216h; dwExceptionCode
0x180017635  lea     edx, [r9+1]; dwExceptionFlags
0x180017639  call    cs:__imp_RaiseException
0x18001763f  int     3; Trap to Debugger
0x180017640  mov     rax, [rax+8]
0x180017644  jmp     short loc_180017653
0x180017646  mov     [rax+10h], r15w
0x18001764b  mov     [rax+12h], r15b
0x18001764f  mov     rax, [rax+18h]
0x180017653  test    rax, rax
0x180017656  jnz     short loc_180017646
0x180017658  mov     rdi, [rsi+10h]
0x18001765c  jmp     short loc_18001766E
0x18001765e  mov     rax, [rcx]
0x180017661  mov     rax, [rax+18h]
0x180017665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001766a  mov     rdi, [rdi+18h]
0x18001766e  test    rdi, rdi
0x180017671  jz      short loc_1800176DE
0x180017673  mov     rax, [rdi+8]
0x180017677  xor     ecx, ecx
0x180017679  mov     [rdi+10h], r15w
0x18001767e  mov     [rdi+12h], r15b
0x180017682  mov     r15d, [rax+90h]
0x180017689  test    r15d, r15d
0x18001768c  jz      short loc_1800176D9
0x18001768e  mov     rax, [rax+18h]
0x180017692  lea     edx, [rcx+18h]; unsigned int
0x180017695  mov     qword ptr [rsp+140h+length], rcx
0x18001769a  lea     r8, [rsp+140h+length]; void **
0x18001769f  xor     r9d, r9d; bool
0x1800176a2  mov     rbx, [rax+1B8h]
0x1800176a9  mov     rcx, rbx; this
0x1800176ac  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x1800176b1  mov     rax, qword ptr [rsp+140h+length]
0x1800176b6  mov     dword ptr [rax], 0Bh
0x1800176bc  mov     [rax+4], r15d
0x1800176c0  xor     r15d, r15d
0x1800176c3  mov     dword ptr [rax+8], 7
0x1800176ca  mov     [rax+10h], r15
0x1800176ce  mov     rcx, [rbx+58h]
0x1800176d2  test    rcx, rcx
0x1800176d5  jz      short loc_18001766A
0x1800176d7  jmp     short loc_18001765E
0x1800176d9  xor     r15d, r15d
0x1800176dc  jmp     short loc_18001766A
0x1800176de  mov     rbx, [rsi+8]
0x1800176e2  mov     r15, rbx
0x1800176e5  test    rbx, rbx
0x1800176e8  jnz     short loc_1800176F9
0x1800176ea  mov     r12, [rsp+140h+var_F8]
0x1800176ef  mov     rdi, [rsp+140h+var_100]
0x1800176f4  jmp     loc_18001756D
0x1800176f9  mov     rdx, [rbx]; struct SubchannelMaskInfo *
0x1800176fc  lea     rdi, [rbx+18h]
0x180017700  call    ?GetSubchannelsFromMask@AnimationBindingManager@Composition@UI@Windows@@AEAAGPEAVSubchannelMaskInfo@@@Z; Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(SubchannelMaskInfo *)
0x180017705  test    ax, ax
0x180017708  jz      loc_18001785B
0x18001770e  mov     rcx, [rbx+8]
0x180017712  mov     edx, 6
0x180017717  lea     r8d, [rdx-5]
0x18001771b  call    ?SetScalarIntegerProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@_J@Z; Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(DCOMPOSITION_PROPERTY_ID,__int64)
0x180017720  mov     rax, [rdi]
0x180017723  cmp     rbx, [rsi+8]
0x180017727  jnz     loc_180017866
0x18001772d  mov     [rsi+8], rax
0x180017731  mov     rax, [rsi+10h]
0x180017735  mov     rcx, rbx
0x180017738  mov     rbx, [rdi]
0x18001773b  mov     [rdi], rax
0x18001773e  mov     [rsi+10h], rcx
0x180017742  jmp     short loc_1800176E5
0x180017744  mov     rcx, [rbp+40h+string]; string
0x180017748  lea     rdx, [rsp+140h+length]; length
0x18001774d  mov     [rsp+140h+var_D8], r15
0x180017752  mov     [rsp+140h+length], r15d
0x180017757  call    cs:__imp_WindowsGetStringRawBuffer
0x18001775d  mov     ecx, [rsp+140h+length]; unsigned int
0x180017761  mov     rbx, rax
0x180017764  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180017769  cmp     [rsp+140h+length], eax
0x18001776d  lea     r9, [rsp+140h+var_D8]; string
0x180017772  lea     r8, [rsp+140h+hstringHeader]; hstringHeader
0x180017777  mov     rcx, rbx; sourceString
0x18001777a  lea     edx, [rax-1]
0x18001777d  cmovb   edx, [rsp+140h+length]; length
0x180017782  call    cs:__imp_WindowsCreateStringReference
0x180017788  test    eax, eax
0x18001778a  jns     short loc_18001779F
0x18001778c  xor     r9d, r9d; lpArguments
0x18001778f  xor     r8d, r8d; nNumberOfArguments
0x180017792  mov     ecx, eax; dwExceptionCode
0x180017794  lea     edx, [r9+1]; dwExceptionFlags
0x180017798  call    cs:__imp_RaiseException
0x18001779e  int     3; Trap to Debugger
0x18001779f  mov     rcx, [rsp+140h+var_D8]; string
0x1800177a4  lea     rdx, [rsp+140h+length]; length
0x1800177a9  mov     [rbp+40h+var_98], r15
0x1800177ad  mov     [rsp+140h+length], r15d
0x1800177b2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800177b8  mov     ecx, [rsp+140h+length]; unsigned int
0x1800177bc  mov     rbx, rax
0x1800177bf  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800177c4  cmp     [rsp+140h+length], eax
0x1800177c8  lea     r9, [rbp+40h+var_98]; string
0x1800177cc  lea     r8, [rbp+40h+var_B0]; hstringHeader
0x1800177d0  mov     rcx, rbx; sourceString
0x1800177d3  lea     edx, [rax-1]
0x1800177d6  cmovb   edx, [rsp+140h+length]; length
0x1800177db  call    cs:__imp_WindowsCreateStringReference
0x1800177e1  test    eax, eax
0x1800177e3  jns     short loc_1800177F8
0x1800177e5  xor     r9d, r9d; lpArguments
0x1800177e8  xor     r8d, r8d; nNumberOfArguments
0x1800177eb  mov     ecx, eax; dwExceptionCode
0x1800177ed  lea     edx, [r9+1]; dwExceptionFlags
0x1800177f1  call    cs:__imp_RaiseException
0x1800177f7  int     3; Trap to Debugger
0x1800177f8  xor     edx, edx; Val
0x1800177fa  lea     rcx, [rbp+40h+var_90]; void *
0x1800177fe  lea     r8d, [rdx+40h]; Size
0x180017802  call    memset_0
0x180017807  mov     rax, [r14]
0x18001780a  lea     r8, [rsp+140h+var_110]
0x18001780f  mov     [rbp+40h+var_4C], r13b
0x180017813  lea     rdx, [rbp+40h+var_B0]
0x180017817  mov     [rbp+40h+var_50], 12h
0x18001781e  mov     rcx, r14
0x180017821  movss   xmm0, dword ptr [rsi]
0x180017825  mov     rax, [rax+0E0h]
0x18001782c  movss   [rbp+40h+var_90], xmm0
0x180017831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017836  mov     ebx, eax
0x180017838  test    eax, eax
0x18001783a  jns     short loc_18001787C
0x18001783c  mov     rcx, [rbp+48h]; this
0x180017840  lea     r8, aOnecoreuapWind_195; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180017847  mov     r9d, eax; char *
0x18001784a  mov     edx, 104h; void *
0x18001784f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017854  mov     eax, ebx
0x180017856  jmp     loc_180017581
0x18001785b  mov     r15, rbx
0x18001785e  mov     rbx, [rdi]
0x180017861  jmp     loc_1800176E5
0x180017866  mov     [r15+18h], rax
0x18001786a  jmp     loc_180017731
0x18001786f  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x180017876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001787b  int     3; Trap to Debugger
0x18001787c  mov     rdi, [rsp+140h+var_100]
0x180017881  jmp     loc_180017516
```

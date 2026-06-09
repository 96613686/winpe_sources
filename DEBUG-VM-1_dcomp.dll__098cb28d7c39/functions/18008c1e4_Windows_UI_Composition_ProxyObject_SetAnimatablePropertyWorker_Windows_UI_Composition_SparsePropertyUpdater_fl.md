# Windows::UI::Composition::ProxyObject::SetAnimatablePropertyWorker<Windows::UI::Composition::SparsePropertyUpdater<float,Windows::UI::Composition::VisualCommon,float (Windows::UI::Composition::VisualCommon::*)(void),void (Windows::UI::Composition::VisualCommon::*)(float)>,Windows::UI::Composition::PropertyUpdateInfo>(Windows::UI::Composition::SparsePropertyUpdater<float,Windows::UI::Composition::VisualCommon,float (Windows::UI::Composition::VisualCommon::*)(void),void (Windows::UI::Composition::VisualCommon::*)(float)> &,Windows::UI::Composition::PropertyUpdateInfo const &)

- ea: `0x18008c1e4`
- end: `0x18008c519`
- name: `??$SetAnimatablePropertyWorker@V?$SparsePropertyUpdater@MVVisualCommon@Composition@UI@Windows@@P81234@EBAMXZP81234@EAAXM@Z@Composition@UI@Windows@@VPropertyUpdateInfo@234@@ProxyObject@Composition@UI@Windows@@IEAAJAEAV?$SparsePropertyUpdater@MVVisualCommon@Composition@UI@Windows@@P81234@EBAMXZP81234@EAAXM@Z@123@AEBVPropertyUpdateInfo@123@@Z`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014af0`

## callees

- `0x180007484`
- `0x18001358c`
- `0x180015ed0`
- `0x18001603c`
- `0x180016a08`
- `0x1800171b0`
- `0x1800311c8`
- `0x18004a0b8`
- `0x18008c1e4`
- `0x18008c520`
- `0x18008c56c`
- `0x18008c610`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008c458`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008c477`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008c458`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18008c477`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008c442`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18008c442`
- `ntdll!RtlLookupElementGenericTable` at `0x18008c289`
- `ntdll!RtlLookupElementGenericTable` at `0x18008c289`

## string_xrefs

- `0x18008c4d7`: `onecoreuap\windows\dwm\dcomp\winrtnested\WrtProxyObject.inl`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ProxyObject::SetAnimatablePropertyWorker<Windows::UI::Composition::SparsePropertyUpdater<float,Windows::UI::Composition::VisualCommon,float (Windows::UI::Composition::VisualCommon::*)(void)const,void (Windows::UI::Composition::VisualCommon::*)(float)>,Windows::UI::Composition::PropertyUpdateInfo>(
        __int64 *a1,
        __int64 a2,
        const WCHAR ***a3)
{
  char updated; // al
  __int64 v7; // rcx
  char v8; // r15
  int v9; // ebx
  struct _RTL_GENERIC_TABLE *BindingManager; // rax
  _QWORD *v11; // rax
  Windows::UI::Composition::AnimationBindingManager *v12; // rcx
  _QWORD *v13; // rsi
  __int64 i; // rdx
  __int64 j; // rdi
  __int64 v17; // rax
  int v18; // r15d
  __int64 v19; // rax
  DirectComposition::CDevice *v20; // rbx
  _DWORD *v21; // rax
  _QWORD *v22; // rbx
  _QWORD *v23; // r15
  int *v24; // r8
  char v25; // r9
  __int64 v26; // rdx
  _QWORD *v27; // rdi
  _QWORD *v28; // rax
  unsigned __int64 v29; // rbx
  const WCHAR *v30; // rdi
  int *v31; // rsi
  unsigned int v32; // eax
  UINT32 v33; // edx
  HRESULT v34; // eax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 (__fastcall *v37)(__int64 *, _BYTE *, int *); // rax
  int v38; // eax
  unsigned int v39; // ebx
  int v40; // [rsp+20h] [rbp-A9h] BYREF
  void *v41; // [rsp+28h] [rbp-A1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-99h] BYREF
  HSTRING_HEADER Buffer; // [rsp+50h] [rbp-79h] BYREF
  HSTRING string; // [rsp+68h] [rbp-61h] BYREF
  _BYTE v45[32]; // [rsp+70h] [rbp-59h] BYREF
  int v46; // [rsp+90h] [rbp-39h]
  int v47; // [rsp+D0h] [rbp+7h]
  char v48; // [rsp+D4h] [rbp+Bh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  updated = Windows::UI::Composition::SparsePropertyUpdater<float,Windows::UI::Composition::VisualCommon,float (Windows::UI::Composition::VisualCommon::*)(void)const,void (Windows::UI::Composition::VisualCommon::*)(float)>::UpdateApiValue(a2);
  v7 = *a1;
  v8 = updated;
  BYTE1(v40) = updated;
  LOBYTE(v40) = 0;
  if ( !(*(__int64 (__fastcall **)(__int64 *))(v7 + 232))(a1) )
    goto LABEL_2;
  v29 = -1;
  v30 = **a3;
  string = 0;
  do
    ++v29;
  while ( v30[v29] );
  if ( v29 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
  }
  v31 = *(int **)(a2 + 40);
  v32 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v29);
  v33 = v32 - 1;
  if ( (unsigned int)v29 < v32 )
    v33 = v29;
  v34 = WindowsCreateStringReference(v30, v33, &Buffer, &string);
  if ( v34 < 0 )
  {
    RaiseException(v34, 1u, 0, 0);
    __debugbreak();
  }
  v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &hstringHeader,
          (const struct Microsoft::WRL::Wrappers::HStringReference *)&Buffer);
  Windows::UI::Composition::AnimationValueData::AnimationValueData(v45, v35);
  v36 = *a1;
  v48 = v8;
  v47 = 18;
  v37 = *(__int64 (__fastcall **)(__int64 *, _BYTE *, int *))(v36 + 224);
  v46 = *v31;
  v38 = v37(a1, v45, &v40);
  v39 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\WrtProxyObject.inl",
      (const char *)(unsigned int)v38,
      v40);
    return v39;
  }
  else
  {
LABEL_2:
    if ( !(_BYTE)v40 )
    {
      if ( !*(_QWORD *)(a2 + 40) )
      {
        ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
        __debugbreak();
      }
      v9 = (_DWORD)(*a3)[1] & 0x7FFFFFFF;
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
        for ( j = v11[2]; j; j = *(_QWORD *)(j + 24) )
        {
          v17 = *(_QWORD *)(j + 8);
          *(_WORD *)(j + 16) = 0;
          *(_BYTE *)(j + 18) = 0;
          v18 = *(_DWORD *)(v17 + 144);
          if ( v18 )
          {
            v19 = *(_QWORD *)(v17 + 24);
            v41 = 0;
            v20 = *(DirectComposition::CDevice **)(v19 + 440);
            DirectComposition::CDevice::BeginKernelCommand(v20, 0x18u, &v41, 0);
            v21 = v41;
            *(_DWORD *)v41 = 11;
            v21[1] = v18;
            v21[2] = 7;
            *((_QWORD *)v21 + 2) = 0;
            v12 = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)v20 + 11);
            if ( v12 )
              (*(void (__fastcall **)(Windows::UI::Composition::AnimationBindingManager *))(*(_QWORD *)v12 + 24LL))(v12);
          }
        }
        v22 = (_QWORD *)v13[1];
        v23 = v22;
        while ( v22 )
        {
          v27 = v22 + 3;
          if ( Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(
                 v12,
                 (struct SubchannelMaskInfo *)*v22) )
          {
            Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(v22[1], 6, 1);
            v28 = (_QWORD *)*v27;
            if ( v22 == (_QWORD *)v13[1] )
              v13[1] = v28;
            else
              v23[3] = v28;
            v12 = (Windows::UI::Composition::AnimationBindingManager *)v22;
            v22 = (_QWORD *)*v27;
            *v27 = v13[2];
            v13[2] = v12;
          }
          else
          {
            v23 = v22;
            v22 = (_QWORD *)*v27;
          }
        }
        v8 = BYTE1(v40);
      }
      if ( v8 || v13 )
      {
        v24 = *(int **)(a2 + 40);
        v26 = *((unsigned int *)*a3 + 2);
        v25 = *((_BYTE *)*a3 + 16);
        LODWORD(v26) = v26 & 0x7FFFFFFF;
        if ( v25 )
        {
          if ( v25 == 1 )
            Windows::UI::Composition::ProxyObject::SetBufferProperty(a1, v26, v24, 4);
          else
            Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(a1, v26, *v24);
        }
        else
        {
          Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(a1, v26);
        }
      }
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18008c1e4  mov     [rsp-8+arg_18], rbx
0x18008c1e9  push    rbp
0x18008c1ea  push    rsi
0x18008c1eb  push    rdi
0x18008c1ec  push    r12
0x18008c1ee  push    r13
0x18008c1f0  push    r14
0x18008c1f2  push    r15
0x18008c1f4  lea     rbp, [rsp-27h]
0x18008c1f9  sub     rsp, 0F0h
0x18008c200  mov     rax, cs:__security_cookie
0x18008c207  xor     rax, rsp
0x18008c20a  mov     [rbp+57h+var_40], rax
0x18008c20e  mov     r14, rcx
0x18008c211  mov     r12, r8
0x18008c214  mov     rcx, rdx
0x18008c217  mov     r13, rdx
0x18008c21a  call    ?UpdateApiValue@?$SparsePropertyUpdater@MVVisualCommon@Composition@UI@Windows@@P81234@EBAMXZP81234@EAAXM@Z@Composition@UI@Windows@@QEBA_NXZ; Windows::UI::Composition::SparsePropertyUpdater<float,Windows::UI::Composition::VisualCommon,float (Windows::UI::Composition::VisualCommon::*)(void),void (Windows::UI::Composition::VisualCommon::*)(float)>::UpdateApiValue(void)
0x18008c21f  mov     rcx, [r14]
0x18008c222  mov     r15b, al
0x18008c225  mov     byte ptr [rsp+120h+var_100+1], al
0x18008c229  xor     esi, esi
0x18008c22b  mov     byte ptr [rsp+120h+var_100], sil; int
0x18008c230  mov     rax, [rcx+0E8h]
0x18008c237  mov     rcx, r14
0x18008c23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c23f  test    rax, rax
0x18008c242  jnz     loc_18008C402
0x18008c248  cmp     byte ptr [rsp+120h+var_100], sil
0x18008c24d  jnz     short loc_18008C2AC
0x18008c24f  cmp     [r13+28h], rsi
0x18008c253  jz      loc_18008C4F2
0x18008c259  mov     rax, [r12]
0x18008c25d  mov     rcx, [r14+18h]; this
0x18008c261  mov     ebx, [rax+8]
0x18008c264  btr     ebx, 1Fh
0x18008c268  call    ?GetBindingManager@CompositorCommon@Composition@UI@Windows@@QEAAPEAVAnimationBindingManager@234@XZ; Windows::UI::Composition::CompositorCommon::GetBindingManager(void)
0x18008c26d  mov     ecx, [r14+90h]
0x18008c274  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18008c278  mov     [rbp+57h+Buffer], ecx
0x18008c27b  xorps   xmm0, xmm0
0x18008c27e  mov     rcx, rax; Table
0x18008c281  mov     [rbp+57h+var_CC], ebx
0x18008c284  movdqu  [rbp+57h+var_C8], xmm0
0x18008c289  call    cs:__imp_RtlLookupElementGenericTable
0x18008c28f  xor     r10d, r10d
0x18008c292  mov     rsi, rax
0x18008c295  test    rax, rax
0x18008c298  jnz     short loc_18008C2D5
0x18008c29a  test    r15b, r15b
0x18008c29d  jnz     loc_18008C386
0x18008c2a3  test    rsi, rsi
0x18008c2a6  jnz     loc_18008C386
0x18008c2ac  xor     eax, eax
0x18008c2ae  mov     rcx, [rbp+57h+var_40]
0x18008c2b2  xor     rcx, rsp; StackCookie
0x18008c2b5  call    __security_check_cookie
0x18008c2ba  mov     rbx, [rsp+120h+arg_18]
0x18008c2c2  add     rsp, 0F0h
0x18008c2c9  pop     r15
0x18008c2cb  pop     r14
0x18008c2cd  pop     r13
0x18008c2cf  pop     r12
0x18008c2d1  pop     rdi
0x18008c2d2  pop     rsi
0x18008c2d3  pop     rbp
0x18008c2d4  retn
0x18008c2d5  mov     rdx, [rax+8]
0x18008c2d9  jmp     short loc_18008C2E8
0x18008c2db  mov     [rdx+10h], r10w
0x18008c2e0  mov     [rdx+12h], r10b
0x18008c2e4  mov     rdx, [rdx+18h]
0x18008c2e8  test    rdx, rdx
0x18008c2eb  jnz     short loc_18008C2DB
0x18008c2ed  mov     rdi, [rax+10h]
0x18008c2f1  jmp     short loc_18008C306
0x18008c2f3  mov     rax, [rcx]
0x18008c2f6  mov     rax, [rax+18h]
0x18008c2fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c2ff  xor     r10d, r10d
0x18008c302  mov     rdi, [rdi+18h]
0x18008c306  test    rdi, rdi
0x18008c309  jz      short loc_18008C370
0x18008c30b  mov     rax, [rdi+8]
0x18008c30f  mov     [rdi+10h], r10w
0x18008c314  mov     [rdi+12h], r10b
0x18008c318  mov     r15d, [rax+90h]
0x18008c31f  test    r15d, r15d
0x18008c322  jz      short loc_18008C302
0x18008c324  mov     rax, [rax+18h]
0x18008c328  lea     r8, [rsp+120h+var_F8]; void **
0x18008c32d  xor     r9d, r9d; bool
0x18008c330  mov     [rsp+120h+var_F8], r10
0x18008c335  mov     rbx, [rax+1B8h]
0x18008c33c  mov     rcx, rbx; this
0x18008c33f  lea     edx, [r9+18h]; unsigned int
0x18008c343  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x18008c348  mov     rax, [rsp+120h+var_F8]
0x18008c34d  xor     r10d, r10d
0x18008c350  mov     dword ptr [rax], 0Bh
0x18008c356  mov     [rax+4], r15d
0x18008c35a  mov     dword ptr [rax+8], 7
0x18008c361  mov     [rax+10h], r10
0x18008c365  mov     rcx, [rbx+58h]
0x18008c369  test    rcx, rcx
0x18008c36c  jz      short loc_18008C302
0x18008c36e  jmp     short loc_18008C2F3
0x18008c370  mov     rbx, [rsi+8]
0x18008c374  mov     r15, rbx
0x18008c377  test    rbx, rbx
0x18008c37a  jnz     short loc_18008C3B4
0x18008c37c  mov     r15b, byte ptr [rsp+120h+var_100+1]
0x18008c381  jmp     loc_18008C29A
0x18008c386  mov     rax, [r12]
0x18008c38a  mov     rcx, r14
0x18008c38d  mov     r8, [r13+28h]
0x18008c391  mov     edx, [rax+8]
0x18008c394  mov     r9b, [rax+10h]
0x18008c398  btr     edx, 1Fh
0x18008c39c  test    r9b, r9b
0x18008c39f  jnz     loc_18008C4FF
0x18008c3a5  movss   xmm2, dword ptr [r8]
0x18008c3aa  call    ?SetScalarFloatProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@M@Z; Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(DCOMPOSITION_PROPERTY_ID,float)
0x18008c3af  jmp     loc_18008C2AC
0x18008c3b4  mov     rdx, [rbx]; struct SubchannelMaskInfo *
0x18008c3b7  lea     rdi, [rbx+18h]
0x18008c3bb  call    ?GetSubchannelsFromMask@AnimationBindingManager@Composition@UI@Windows@@AEAAGPEAVSubchannelMaskInfo@@@Z; Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(SubchannelMaskInfo *)
0x18008c3c0  test    ax, ax
0x18008c3c3  jz      short loc_18008C3F7
0x18008c3c5  mov     rcx, [rbx+8]
0x18008c3c9  mov     edx, 6
0x18008c3ce  lea     r8d, [rdx-5]
0x18008c3d2  call    ?SetScalarIntegerProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@_J@Z; Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(DCOMPOSITION_PROPERTY_ID,__int64)
0x18008c3d7  mov     rax, [rdi]
0x18008c3da  cmp     rbx, [rsi+8]
0x18008c3de  jnz     short loc_18008C45F
0x18008c3e0  mov     [rsi+8], rax
0x18008c3e4  mov     rax, [rsi+10h]
0x18008c3e8  mov     rcx, rbx
0x18008c3eb  mov     rbx, [rdi]
0x18008c3ee  mov     [rdi], rax
0x18008c3f1  mov     [rsi+10h], rcx
0x18008c3f5  jmp     short loc_18008C377
0x18008c3f7  mov     r15, rbx
0x18008c3fa  mov     rbx, [rdi]
0x18008c3fd  jmp     loc_18008C377
0x18008c402  mov     rax, [r12]
0x18008c406  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18008c40a  mov     rdi, [rax]
0x18008c40d  mov     [rbp+57h+string], rsi
0x18008c411  inc     rbx
0x18008c414  cmp     [rdi+rbx*2], si
0x18008c418  jnz     short loc_18008C411
0x18008c41a  mov     eax, 0FFFFFFFFh
0x18008c41f  cmp     rbx, rax
0x18008c422  ja      short loc_18008C468
0x18008c424  mov     rsi, [r13+28h]
0x18008c428  mov     ecx, ebx; unsigned int
0x18008c42a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18008c42f  cmp     ebx, eax
0x18008c431  lea     r9, [rbp+57h+string]; string
0x18008c435  lea     r8, [rbp+57h+Buffer]; hstringHeader
0x18008c439  mov     rcx, rdi; sourceString
0x18008c43c  lea     edx, [rax-1]
0x18008c43f  cmovb   edx, ebx; length
0x18008c442  call    cs:__imp_WindowsCreateStringReference
0x18008c448  test    eax, eax
0x18008c44a  jns     short loc_18008C47E
0x18008c44c  xor     r9d, r9d; lpArguments
0x18008c44f  xor     r8d, r8d; nNumberOfArguments
0x18008c452  mov     ecx, eax; dwExceptionCode
0x18008c454  lea     edx, [r9+1]; dwExceptionFlags
0x18008c458  call    cs:__imp_RaiseException
0x18008c45e  int     3; Trap to Debugger
0x18008c45f  mov     [r15+18h], rax
0x18008c463  jmp     loc_18008C3E4
0x18008c468  xor     r9d, r9d; lpArguments
0x18008c46b  xor     r8d, r8d; nNumberOfArguments
0x18008c46e  mov     ecx, 80070216h; dwExceptionCode
0x18008c473  lea     edx, [r9+1]; dwExceptionFlags
0x18008c477  call    cs:__imp_RaiseException
0x18008c47d  int     3; Trap to Debugger
0x18008c47e  lea     rdx, [rbp+57h+Buffer]; struct Microsoft::WRL::Wrappers::HStringReference *
0x18008c482  lea     rcx, [rsp+120h+hstringHeader]; hstringHeader
0x18008c487  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV0123@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Microsoft::WRL::Wrappers::HStringReference const &)
0x18008c48c  mov     rdx, rax
0x18008c48f  lea     rcx, [rbp+57h+var_B0]
0x18008c493  call    ??0AnimationValueData@Composition@UI@Windows@@QEAA@VHStringReference@Wrappers@WRL@Microsoft@@@Z; Windows::UI::Composition::AnimationValueData::AnimationValueData(Microsoft::WRL::Wrappers::HStringReference)
0x18008c498  mov     rax, [r14]
0x18008c49b  lea     r8, [rsp+120h+var_100]
0x18008c4a0  mov     [rbp+57h+var_4C], r15b
0x18008c4a4  lea     rdx, [rbp+57h+var_B0]
0x18008c4a8  mov     [rbp+57h+var_50], 12h
0x18008c4af  mov     rcx, r14
0x18008c4b2  movss   xmm0, dword ptr [rsi]
0x18008c4b6  mov     rax, [rax+0E0h]
0x18008c4bd  movss   [rbp+57h+var_90], xmm0
0x18008c4c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c4c7  xor     esi, esi
0x18008c4c9  mov     ebx, eax
0x18008c4cb  test    eax, eax
0x18008c4cd  jns     loc_18008C248
0x18008c4d3  mov     rcx, [rbp+5Fh]; this
0x18008c4d7  lea     r8, aOnecoreuapWind_195; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18008c4de  mov     r9d, eax; char *
0x18008c4e1  mov     edx, 104h; void *
0x18008c4e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008c4eb  mov     eax, ebx
0x18008c4ed  jmp     loc_18008C2AE
0x18008c4f2  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x18008c4f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c4fe  int     3; Trap to Debugger
0x18008c4ff  cmp     r9b, 1
0x18008c503  jnz     loc_18017FF2E
0x18008c509  mov     r9d, 4
0x18008c50f  call    ?SetBufferProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@PEBX_K@Z; Windows::UI::Composition::ProxyObject::SetBufferProperty(DCOMPOSITION_PROPERTY_ID,void const *,unsigned __int64)
0x18008c514  jmp     loc_18008C2AC
0x18017ff2e  movsxd  r8, dword ptr [r8]
0x18017ff31  call    ?SetScalarIntegerProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@_J@Z; Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(DCOMPOSITION_PROPERTY_ID,__int64)
0x18017ff36  nop
0x18017ff37  jmp     loc_18008C2AC
```

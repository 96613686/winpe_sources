# Windows::UI::Composition::ProxyObject::SetAnimatableProperty<Windows::Foundation::Numerics::Vector3>(Windows::Foundation::Numerics::Vector3 *,Windows::Foundation::Numerics::Vector3 const &,Windows::UI::Composition::AnimationHelper::AnimatedProperty const &)

- ea: `0x180016db8`
- end: `0x180017122`
- name: `??$SetAnimatableProperty@UVector3@Numerics@Foundation@Windows@@@ProxyObject@Composition@UI@Windows@@IEAAJPEAUVector3@Numerics@Foundation@3@AEBU4563@AEBUAnimatedProperty@AnimationHelper@123@@Z`
- size: `874`
- prototype: ``
- caller_count: `15`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180054f28`
- `0x18005540c`
- `0x180055764`
- `0x1800c6020`
- `0x1800d0e10`
- `0x180154fa0`
- `0x180156020`
- `0x180156160`
- `0x18015e8b0`
- `0x18015e948`
- `0x18015ebb8`
- `0x180169f10`
- `0x18016b2f0`
- `0x18016b3a0`
- `0x18016b450`

## callees

- `0x180007484`
- `0x18001358c`
- `0x180015ed0`
- `0x18001603c`
- `0x180016a08`
- `0x180016db8`
- `0x1800171b0`
- `0x1800311c8`
- `0x18004a0b8`
- `0x18008c56c`
- `0x18008c610`
- `0x1800e77ac`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001705b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017071`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001705b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017071`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017045`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017045`
- `ntdll!RtlLookupElementGenericTable` at `0x180016e8c`
- `ntdll!RtlLookupElementGenericTable` at `0x180016e8c`

## string_xrefs

- `0x180017101`: `onecoreuap\windows\dwm\dcomp\winrtnested\WrtProxyObject.inl`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::ProxyObject::SetAnimatableProperty<Windows::Foundation::Numerics::Vector3>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  bool v4; // zf
  __int64 v5; // rdi
  char v8; // r14
  __int64 v9; // rax
  int v10; // ebx
  struct _RTL_GENERIC_TABLE *BindingManager; // rax
  _QWORD *v12; // rax
  Windows::UI::Composition::AnimationBindingManager *v13; // rcx
  _QWORD *v14; // r14
  unsigned int v15; // ebx
  char v17; // al
  __int64 v18; // rdx
  __int64 i; // rdx
  __int64 j; // rdi
  __int64 v21; // rax
  int v22; // r12d
  __int64 v23; // rax
  DirectComposition::CDevice *v24; // rbx
  _DWORD *v25; // rax
  _QWORD *v26; // rbx
  _QWORD *v27; // r13
  _QWORD *v28; // rdi
  _QWORD *v29; // rax
  const WCHAR *v30; // rdi
  unsigned __int64 v31; // rbx
  unsigned int v32; // eax
  UINT32 v33; // edx
  HRESULT v34; // eax
  __int64 v35; // rax
  int v36; // eax
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  void *v38; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v39; // [rsp+30h] [rbp-D0h]
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER Buffer; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v43[32]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-60h]
  int v45; // [rsp+A8h] [rbp-58h]
  int v46; // [rsp+E0h] [rbp-20h]
  char v47; // [rsp+E4h] [rbp-1Ch]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v4 = *(float *)a2 == *(float *)a3;
  v5 = a4;
  v39 = a4;
  if ( v4 && *(float *)(a2 + 4) == *((float *)a3 + 1) && *(float *)(a2 + 8) == *((float *)a3 + 2) )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    *(_QWORD *)a2 = *a3;
    *(_DWORD *)(a2 + 8) = *((_DWORD *)a3 + 2);
  }
  v9 = *a1;
  BYTE1(v37) = v8;
  LOBYTE(v37) = 0;
  if ( (*(__int64 (__fastcall **)(__int64 *))(v9 + 232))(a1) )
  {
    v30 = *(const WCHAR **)v5;
    v31 = -1;
    string = 0;
    do
      ++v31;
    while ( v30[v31] );
    if ( v31 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      __debugbreak();
    }
    v32 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v31);
    v33 = v32 - 1;
    if ( (unsigned int)v31 < v32 )
      v33 = v31;
    v34 = WindowsCreateStringReference(v30, v33, &Buffer, &string);
    if ( v34 < 0 )
    {
      RaiseException(v34, 1u, 0, 0);
      __debugbreak();
    }
    v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const struct Microsoft::WRL::Wrappers::HStringReference *)&Buffer);
    Windows::UI::Composition::AnimationValueData::AnimationValueData(v43, v35);
    v47 = v8;
    v46 = 52;
    v44 = *a3;
    v45 = *((_DWORD *)a3 + 2);
    v36 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *, int *))(*a1 + 224))(a1, v43, &v37);
    v15 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\WrtProxyObject.inl",
        (const char *)(unsigned int)v36,
        v37);
      return v15;
    }
    v5 = v39;
  }
  if ( !(_BYTE)v37 )
  {
    v10 = *(_DWORD *)(v5 + 8) & 0x7FFFFFFF;
    BindingManager = (struct _RTL_GENERIC_TABLE *)Windows::UI::Composition::CompositorCommon::GetBindingManager((Windows::UI::Composition::CompositorCommon *)a1[3]);
    LODWORD(Buffer.Reserved.Reserved1) = *((_DWORD *)a1 + 36);
    *(_DWORD *)&Buffer.Reserved.Reserved2[4] = v10;
    *(_OWORD *)&Buffer.Reserved.Reserved2[8] = 0;
    v12 = RtlLookupElementGenericTable(BindingManager, &Buffer);
    v14 = v12;
    if ( v12 )
    {
      for ( i = v12[1]; i; i = *(_QWORD *)(i + 24) )
      {
        *(_WORD *)(i + 16) = 0;
        *(_BYTE *)(i + 18) = 0;
      }
      for ( j = v12[2]; j; j = *(_QWORD *)(j + 24) )
      {
        v21 = *(_QWORD *)(j + 8);
        *(_WORD *)(j + 16) = 0;
        *(_BYTE *)(j + 18) = 0;
        v22 = *(_DWORD *)(v21 + 144);
        if ( v22 )
        {
          v23 = *(_QWORD *)(v21 + 24);
          v38 = 0;
          v24 = *(DirectComposition::CDevice **)(v23 + 440);
          DirectComposition::CDevice::BeginKernelCommand(v24, 0x18u, &v38, 0);
          v25 = v38;
          *(_DWORD *)v38 = 11;
          v25[1] = v22;
          v25[2] = 7;
          *((_QWORD *)v25 + 2) = 0;
          v13 = (Windows::UI::Composition::AnimationBindingManager *)*((_QWORD *)v24 + 11);
          if ( v13 )
            (*(void (__fastcall **)(Windows::UI::Composition::AnimationBindingManager *))(*(_QWORD *)v13 + 24LL))(v13);
        }
      }
      v26 = (_QWORD *)v14[1];
      v27 = v26;
      while ( v26 )
      {
        v28 = v26 + 3;
        if ( Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(
               v13,
               (struct SubchannelMaskInfo *)*v26) )
        {
          Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(v26[1], 6, 1);
          v29 = (_QWORD *)*v28;
          if ( v26 == (_QWORD *)v14[1] )
            v14[1] = v29;
          else
            v27[3] = v29;
          v13 = (Windows::UI::Composition::AnimationBindingManager *)v26;
          v26 = (_QWORD *)*v28;
          *v28 = v14[2];
          v14[2] = v13;
        }
        else
        {
          v27 = v26;
          v26 = (_QWORD *)*v28;
        }
      }
      v5 = v39;
    }
    if ( BYTE1(v37) || v14 )
    {
      v18 = *(unsigned int *)(v5 + 8);
      v17 = *(_BYTE *)(v5 + 16);
      LODWORD(v18) = v18 & 0x7FFFFFFF;
      if ( v17 )
      {
        if ( v17 != 1 )
          Microsoft::WRL2::FailFast::Unexpected(0);
        Windows::UI::Composition::ProxyObject::SetBufferProperty(a1, v18, a3, 12);
      }
      else
      {
        Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(a1, v18);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180016db8  push    rbp
0x180016dba  push    rbx
0x180016dbb  push    rsi
0x180016dbc  push    rdi
0x180016dbd  push    r12
0x180016dbf  push    r13
0x180016dc1  push    r14
0x180016dc3  push    r15
0x180016dc5  lea     rbp, [rsp-8]
0x180016dca  sub     rsp, 108h
0x180016dd1  mov     rax, cs:__security_cookie
0x180016dd8  xor     rax, rsp
0x180016ddb  mov     [rbp+40h+var_50], rax
0x180016ddf  movss   xmm0, dword ptr [rdx]
0x180016de3  xor     r13d, r13d
0x180016de6  ucomiss xmm0, dword ptr [r8]
0x180016dea  mov     rdi, r9
0x180016ded  mov     [rsp+140h+var_110], r9
0x180016df2  mov     rsi, r8
0x180016df5  mov     r15, rcx
0x180016df8  jp      loc_180016ECB
0x180016dfe  jnz     loc_180016ECB
0x180016e04  movss   xmm0, dword ptr [rdx+4]
0x180016e09  ucomiss xmm0, dword ptr [r8+4]
0x180016e0e  jp      loc_180016ECB
0x180016e14  jnz     loc_180016ECB
0x180016e1a  movss   xmm0, dword ptr [rdx+8]
0x180016e1f  ucomiss xmm0, dword ptr [r8+8]
0x180016e24  jp      loc_180016ECB
0x180016e2a  jnz     loc_180016ECB
0x180016e30  mov     r14b, r13b
0x180016e33  mov     rax, [rcx]
0x180016e36  mov     byte ptr [rsp+140h+var_120+1], r14b
0x180016e3b  mov     byte ptr [rsp+140h+var_120], r13b; int
0x180016e40  mov     rax, [rax+0E8h]
0x180016e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e4c  test    rax, rax
0x180016e4f  jnz     loc_180017009
0x180016e55  cmp     byte ptr [rsp+140h+var_120], r13b
0x180016e5a  jnz     short loc_180016EA6
0x180016e5c  mov     ebx, [rdi+8]
0x180016e5f  mov     rcx, [r15+18h]; this
0x180016e63  btr     ebx, 1Fh
0x180016e67  call    ?GetBindingManager@CompositorCommon@Composition@UI@Windows@@QEAAPEAVAnimationBindingManager@234@XZ; Windows::UI::Composition::CompositorCommon::GetBindingManager(void)
0x180016e6c  mov     ecx, [r15+90h]
0x180016e73  lea     rdx, [rsp+140h+Buffer]; Buffer
0x180016e78  mov     [rsp+140h+Buffer], ecx
0x180016e7c  xorps   xmm0, xmm0
0x180016e7f  mov     rcx, rax; Table
0x180016e82  mov     [rsp+140h+var_E4], ebx
0x180016e86  movdqu  [rsp+140h+var_E0], xmm0
0x180016e8c  call    cs:__imp_RtlLookupElementGenericTable
0x180016e92  mov     r14, rax
0x180016e95  test    rax, rax
0x180016e98  jnz     short loc_180016F10
0x180016e9a  cmp     byte ptr [rsp+140h+var_120+1], r13b
0x180016e9f  jnz     short loc_180016EE3
0x180016ea1  test    r14, r14
0x180016ea4  jnz     short loc_180016EE3
0x180016ea6  mov     ebx, r13d
0x180016ea9  mov     eax, ebx
0x180016eab  mov     rcx, [rbp+40h+var_50]
0x180016eaf  xor     rcx, rsp; StackCookie
0x180016eb2  call    __security_check_cookie
0x180016eb7  add     rsp, 108h
0x180016ebe  pop     r15
0x180016ec0  pop     r14
0x180016ec2  pop     r13
0x180016ec4  pop     r12
0x180016ec6  pop     rdi
0x180016ec7  pop     rsi
0x180016ec8  pop     rbx
0x180016ec9  pop     rbp
0x180016eca  retn
0x180016ecb  movsd   xmm0, qword ptr [r8]
0x180016ed0  mov     r14b, 1
0x180016ed3  movsd   qword ptr [rdx], xmm0
0x180016ed7  mov     eax, [r8+8]
0x180016edb  mov     [rdx+8], eax
0x180016ede  jmp     loc_180016E33
0x180016ee3  mov     edx, [rdi+8]
0x180016ee6  mov     al, [rdi+10h]
0x180016ee9  btr     edx, 1Fh
0x180016eed  test    al, al
0x180016eef  jz      loc_1800170EC
0x180016ef5  cmp     al, 1
0x180016ef7  jnz     loc_18001711A
0x180016efd  mov     r9d, 0Ch
0x180016f03  mov     r8, rsi
0x180016f06  mov     rcx, r15
0x180016f09  call    ?SetBufferProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@PEBX_K@Z; Windows::UI::Composition::ProxyObject::SetBufferProperty(DCOMPOSITION_PROPERTY_ID,void const *,unsigned __int64)
0x180016f0e  jmp     short loc_180016EA6
0x180016f10  mov     rdx, [rax+8]
0x180016f14  jmp     short loc_180016F23
0x180016f16  mov     [rdx+10h], r13w
0x180016f1b  mov     [rdx+12h], r13b
0x180016f1f  mov     rdx, [rdx+18h]
0x180016f23  test    rdx, rdx
0x180016f26  jnz     short loc_180016F16
0x180016f28  mov     rdi, [rax+10h]
0x180016f2c  jmp     short loc_180016F3E
0x180016f2e  mov     rax, [rcx]
0x180016f31  mov     rax, [rax+18h]
0x180016f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f3a  mov     rdi, [rdi+18h]
0x180016f3e  test    rdi, rdi
0x180016f41  jz      short loc_180016FA5
0x180016f43  mov     rax, [rdi+8]
0x180016f47  mov     [rdi+10h], r13w
0x180016f4c  mov     [rdi+12h], r13b
0x180016f50  mov     r12d, [rax+90h]
0x180016f57  test    r12d, r12d
0x180016f5a  jz      short loc_180016F3A
0x180016f5c  mov     rax, [rax+18h]
0x180016f60  lea     r8, [rsp+140h+var_118]; void **
0x180016f65  xor     r9d, r9d; bool
0x180016f68  mov     [rsp+140h+var_118], r13
0x180016f6d  mov     rbx, [rax+1B8h]
0x180016f74  mov     rcx, rbx; this
0x180016f77  lea     edx, [r9+18h]; unsigned int
0x180016f7b  call    ?BeginKernelCommand@CDevice@DirectComposition@@AEAAXIPEAPEAX_N@Z; DirectComposition::CDevice::BeginKernelCommand(uint,void * *,bool)
0x180016f80  mov     rax, [rsp+140h+var_118]
0x180016f85  mov     dword ptr [rax], 0Bh
0x180016f8b  mov     [rax+4], r12d
0x180016f8f  mov     dword ptr [rax+8], 7
0x180016f96  mov     [rax+10h], r13
0x180016f9a  mov     rcx, [rbx+58h]
0x180016f9e  test    rcx, rcx
0x180016fa1  jz      short loc_180016F3A
0x180016fa3  jmp     short loc_180016F2E
0x180016fa5  mov     rbx, [r14+8]
0x180016fa9  mov     r13, rbx
0x180016fac  test    rbx, rbx
0x180016faf  jnz     short loc_180016FBE
0x180016fb1  mov     rdi, [rsp+140h+var_110]
0x180016fb6  xor     r13d, r13d
0x180016fb9  jmp     loc_180016E9A
0x180016fbe  mov     rdx, [rbx]; struct SubchannelMaskInfo *
0x180016fc1  lea     rdi, [rbx+18h]
0x180016fc5  call    ?GetSubchannelsFromMask@AnimationBindingManager@Composition@UI@Windows@@AEAAGPEAVSubchannelMaskInfo@@@Z; Windows::UI::Composition::AnimationBindingManager::GetSubchannelsFromMask(SubchannelMaskInfo *)
0x180016fca  test    ax, ax
0x180016fcd  jz      loc_180017078
0x180016fd3  mov     rcx, [rbx+8]
0x180016fd7  mov     edx, 6
0x180016fdc  lea     r8d, [rdx-5]
0x180016fe0  call    ?SetScalarIntegerProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@_J@Z; Windows::UI::Composition::ProxyObject::SetScalarIntegerProperty(DCOMPOSITION_PROPERTY_ID,__int64)
0x180016fe5  mov     rax, [rdi]
0x180016fe8  cmp     rbx, [r14+8]
0x180016fec  jnz     loc_180017083
0x180016ff2  mov     [r14+8], rax
0x180016ff6  mov     rax, [r14+10h]
0x180016ffa  mov     rcx, rbx
0x180016ffd  mov     rbx, [rdi]
0x180017000  mov     [rdi], rax
0x180017003  mov     [r14+10h], rcx
0x180017007  jmp     short loc_180016FAC
0x180017009  mov     rdi, [rdi]
0x18001700c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017010  mov     [rsp+140h+string], r13
0x180017015  inc     rbx
0x180017018  cmp     [rdi+rbx*2], r13w
0x18001701d  jnz     short loc_180017015
0x18001701f  mov     eax, 0FFFFFFFFh
0x180017024  cmp     rbx, rax
0x180017027  ja      short loc_180017062
0x180017029  mov     ecx, ebx; unsigned int
0x18001702b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180017030  cmp     ebx, eax
0x180017032  lea     r9, [rsp+140h+string]; string
0x180017037  lea     r8, [rsp+140h+Buffer]; hstringHeader
0x18001703c  mov     rcx, rdi; sourceString
0x18001703f  lea     edx, [rax-1]
0x180017042  cmovb   edx, ebx; length
0x180017045  call    cs:__imp_WindowsCreateStringReference
0x18001704b  test    eax, eax
0x18001704d  jns     short loc_18001708C
0x18001704f  xor     r9d, r9d; lpArguments
0x180017052  xor     r8d, r8d; nNumberOfArguments
0x180017055  mov     ecx, eax; dwExceptionCode
0x180017057  lea     edx, [r9+1]; dwExceptionFlags
0x18001705b  call    cs:__imp_RaiseException
0x180017061  int     3; Trap to Debugger
0x180017062  xor     r9d, r9d; lpArguments
0x180017065  xor     r8d, r8d; nNumberOfArguments
0x180017068  mov     ecx, 80070216h; dwExceptionCode
0x18001706d  lea     edx, [r9+1]; dwExceptionFlags
0x180017071  call    cs:__imp_RaiseException
0x180017077  int     3; Trap to Debugger
0x180017078  mov     r13, rbx
0x18001707b  mov     rbx, [rdi]
0x18001707e  jmp     loc_180016FAC
0x180017083  mov     [r13+18h], rax
0x180017087  jmp     loc_180016FF6
0x18001708c  lea     rdx, [rsp+140h+Buffer]; struct Microsoft::WRL::Wrappers::HStringReference *
0x180017091  lea     rcx, [rsp+140h+hstringHeader]; hstringHeader
0x180017096  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV0123@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Microsoft::WRL::Wrappers::HStringReference const &)
0x18001709b  mov     rdx, rax
0x18001709e  lea     rcx, [rbp+40h+var_C0]
0x1800170a2  call    ??0AnimationValueData@Composition@UI@Windows@@QEAA@VHStringReference@Wrappers@WRL@Microsoft@@@Z; Windows::UI::Composition::AnimationValueData::AnimationValueData(Microsoft::WRL::Wrappers::HStringReference)
0x1800170a7  mov     [rbp+40h+var_5C], r14b
0x1800170ab  lea     r8, [rsp+140h+var_120]
0x1800170b0  mov     [rbp+40h+var_60], 34h ; '4'
0x1800170b7  lea     rdx, [rbp+40h+var_C0]
0x1800170bb  movsd   xmm0, qword ptr [rsi]
0x1800170bf  mov     rcx, r15
0x1800170c2  movsd   [rbp+40h+var_A0], xmm0
0x1800170c7  mov     eax, [rsi+8]
0x1800170ca  mov     [rbp+40h+var_98], eax
0x1800170cd  mov     rax, [r15]
0x1800170d0  mov     rax, [rax+0E0h]
0x1800170d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170dc  mov     ebx, eax
0x1800170de  test    eax, eax
0x1800170e0  js      short loc_1800170FD
0x1800170e2  mov     rdi, [rsp+140h+var_110]
0x1800170e7  jmp     loc_180016E55
0x1800170ec  movss   xmm2, dword ptr [rsi]
0x1800170f0  mov     rcx, r15
0x1800170f3  call    ?SetScalarFloatProperty@ProxyObject@Composition@UI@Windows@@IEAAXUDCOMPOSITION_PROPERTY_ID@@M@Z; Windows::UI::Composition::ProxyObject::SetScalarFloatProperty(DCOMPOSITION_PROPERTY_ID,float)
0x1800170f8  jmp     loc_180016EA6
0x1800170fd  mov     rcx, [rbp+48h]; this
0x180017101  lea     r8, aOnecoreuapWind_195; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180017108  mov     r9d, eax; char *
0x18001710b  mov     edx, 104h; void *
0x180017110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017115  jmp     loc_180016EA9
0x18001711a  xor     ecx, ecx; char *
0x18001711c  call    ?Unexpected@FailFast@WRL2@Microsoft@@SAXPEBD@Z; Microsoft::WRL2::FailFast::Unexpected(char const *)
```

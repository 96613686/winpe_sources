# UIBase::Acc::GetStandardDefaultAction(ushort const *,ushort * &)

- ea: `0x180073330`
- end: `0x18007350e`
- name: `?GetStandardDefaultAction@Acc@UIBase@@YAJPEBGAEAPEAG@Z`
- size: `478`
- prototype: `__int64 __fastcall(UIBase::Acc *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180074820`

## callees

- `0x18000cb74`
- `0x18003fcac`
- `0x180040490`
- `0x1800404f8`
- `0x18004c090`
- `0x180062218`
- `0x180072ca8`
- `0x18007328c`
- `0x180073330`
- `0x180073a6c`
- `0x180080010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180073424`
- `OLEAUT32!__imp_SysFreeString` at `0x180073424`
- `OLEAUT32!__imp_VariantClear` at `0x1800734bb`
- `OLEAUT32!__imp_VariantClear` at `0x1800734bb`
- `OLEACC!CreateStdAccessibleProxyW` at `0x180073462`
- `OLEACC!CreateStdAccessibleProxyW` at `0x180073462`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UIBase::Acc::GetStandardDefaultAction(
        UIBase::Acc *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int v4; // ecx
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  __int64 Node; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rsi
  void *v12; // rbx
  void (__fastcall *v13)(void *, __int128 *, __int64); // rdi
  __int64 v14; // rax
  unsigned __int16 *v15; // rax
  __int64 result; // rax
  __int128 v17; // [rsp+30h] [rbp-68h] BYREF
  __int64 v18; // [rsp+40h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-48h] BYREF
  unsigned int v20; // [rsp+A0h] [rbp+8h]
  void *ppvObject; // [rsp+A8h] [rbp+10h] BYREF
  int v22; // [rsp+B0h] [rbp+18h] BYREF
  char v23; // [rsp+B8h] [rbp+20h] BYREF

  *(_QWORD *)a2 = 0;
  v4 = tls_index;
  v5 = 4;
  if ( dword_1800A4834 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800A4834);
    if ( dword_1800A4834 == -1 )
    {
      ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>(
        v4,
        v5,
        v6,
        v7,
        LODWORD(FLOAT_2_25));
      atexit(UIBase::Acc::GetStandardDefaultAction_::_3_::_dynamic_atexit_destructor_for__s_map__);
      Init_thread_footer(&dword_1800A4834);
    }
  }
  v22 = 0;
  LODWORD(ppvObject) = 0;
  Node = ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::GetNode(
           v4,
           v5,
           (unsigned int)&v22,
           (unsigned int)&ppvObject,
           (__int64)&v23);
  try
  {
    v11 = Node;
    if ( !Node )
    {
      ppvObject = 0;
      v11 = ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::SetAt(
              v10,
              v9,
              &ppvObject);
      SysFreeString(0);
      if ( !v11 )
        goto LABEL_13;
      ppvObject = 0;
      if ( CreateStdAccessibleProxyW(0, L"Button", -4, &IID_IAccessible, &ppvObject) >= 0 )
      {
        v12 = ppvObject;
        if ( ppvObject )
        {
          v13 = *(void (__fastcall **)(void *, __int128 *, __int64))(*(_QWORD *)ppvObject + 160LL);
          v14 = UIBase::Acc::SelfVariant::SelfVariant((UIBase::Acc::SelfVariant *)&pvarg);
          v17 = *(_OWORD *)v14;
          v18 = *(_QWORD *)(v14 + 16);
          v13(v12, &v17, v11 + 8);
          VariantClear(&pvarg);
        }
      }
      ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppvObject);
    }
    if ( *(_QWORD *)(v11 + 8) )
    {
      v15 = ATL::CComBSTR::Copy((ATL::CComBSTR *)(v11 + 8));
      *(_QWORD *)a2 = v15;
      result = v15 == 0 ? 0x8007000E : 0;
LABEL_14:
      v20 = result;
      return result;
    }
LABEL_13:
    result = 1;
    goto LABEL_14;
  }
  catch ( ... )
  {
    return v20;
  }
  return result;
}

```

## disassembly

```asm
0x180073330  mov     [rsp+arg_0], rcx
0x180073335  push    rbx
0x180073336  push    rsi
0x180073337  push    rdi
0x180073338  push    r14
0x18007333a  sub     rsp, 78h
0x18007333e  mov     r14, rdx
0x180073341  mov     dword ptr [rsp+98h+arg_0], 80004005h
0x18007334c  mov     qword ptr [rdx], 0
0x180073353  mov     ecx, cs:_tls_index
0x180073359  mov     rax, gs:58h
0x180073362  mov     edx, 4
0x180073367  mov     rax, [rax+rcx*8]
0x18007336b  mov     eax, [rdx+rax]
0x18007336e  cmp     cs:dword_1800A4834, eax
0x180073374  jle     short loc_1800733C6
0x180073376  lea     rcx, dword_1800A4834
0x18007337d  call    _Init_thread_header
0x180073382  cmp     cs:dword_1800A4834, 0FFFFFFFFh
0x180073389  jnz     short loc_1800733C6
0x18007338b  movss   xmm0, cs:__real@40100000
0x180073393  movss   dword ptr [rsp+98h+ppvObject], xmm0
0x180073399  movss   xmm3, cs:__real@3e800000
0x1800733a1  movss   xmm2, cs:__real@3f400000
0x1800733a9  call    ??0?$CAtlMap@VString@Base@@VCComBSTR@ATL@@V?$CElementTraits@VString@Base@@@4@V?$CElementTraits@VCComBSTR@ATL@@@4@@ATL@@QEAA@IMMMI@Z; ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>(uint,float,float,float,uint)
0x1800733ae  lea     rcx, _UIBase__Acc__GetStandardDefaultAction____3____dynamic_atexit_destructor_for__s_map__; void (__cdecl *)()
0x1800733b5  call    atexit
0x1800733ba  lea     rcx, dword_1800A4834
0x1800733c1  call    _Init_thread_footer
0x1800733c6  mov     [rsp+98h+arg_10], 0
0x1800733d1  mov     dword ptr [rsp+98h+arg_8], 0
0x1800733dc  lea     rax, [rsp+98h+arg_18]
0x1800733e4  mov     [rsp+98h+ppvObject], rax
0x1800733e9  lea     r9, [rsp+98h+arg_8]
0x1800733f1  lea     r8, [rsp+98h+arg_10]
0x1800733f9  call    ?GetNode@?$CAtlMap@VString@Base@@VCComBSTR@ATL@@V?$CElementTraits@VString@Base@@@4@V?$CElementTraits@VCComBSTR@ATL@@@4@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::CNode * &)
0x1800733fe  mov     rsi, rax
0x180073401  test    rax, rax
0x180073404  jnz     loc_1800734CF
0x18007340a  mov     [rsp+98h+arg_8], rax
0x180073412  lea     r8, [rsp+98h+arg_8]
0x18007341a  call    ?SetAt@?$CAtlMap@VString@Base@@VCComBSTR@ATL@@V?$CElementTraits@VString@Base@@@4@V?$CElementTraits@VCComBSTR@ATL@@@4@@ATL@@QEAAPEAU__POSITION@@PEBGAEBVCComBSTR@2@@Z; ATL::CAtlMap<Base::String,ATL::CComBSTR,ATL::CElementTraits<Base::String>,ATL::CElementTraits<ATL::CComBSTR>>::SetAt(ushort const *,ATL::CComBSTR const &)
0x18007341f  mov     rsi, rax
0x180073422  xor     ecx, ecx; bstrString
0x180073424  call    cs:__imp_SysFreeString
0x18007342a  test    rsi, rsi
0x18007342d  jz      loc_1800734EF
0x180073433  mov     [rsp+98h+arg_8], 0
0x18007343f  lea     rax, [rsp+98h+arg_8]
0x180073447  mov     [rsp+98h+ppvObject], rax; ppvObject
0x18007344c  lea     r9, IID_IAccessible; riid
0x180073453  mov     r8d, 0FFFFFFFCh; idObject
0x180073459  lea     rdx, pClassName; "Button"
0x180073460  xor     ecx, ecx; hwnd
0x180073462  call    cs:__imp_CreateStdAccessibleProxyW
0x180073468  test    eax, eax
0x18007346a  js      short loc_1800734C2
0x18007346c  mov     rbx, [rsp+98h+arg_8]
0x180073474  test    rbx, rbx
0x180073477  jz      short loc_1800734C2
0x180073479  mov     rax, [rbx]
0x18007347c  mov     rdi, [rax+0A0h]
0x180073483  lea     rcx, [rsp+98h+pvarg]; this
0x180073488  call    ??0SelfVariant@Acc@UIBase@@QEAA@XZ; UIBase::Acc::SelfVariant::SelfVariant(void)
0x18007348d  nop
0x18007348e  movups  xmm0, xmmword ptr [rax]
0x180073491  movaps  [rsp+98h+var_68], xmm0
0x180073496  movsd   xmm1, qword ptr [rax+10h]
0x18007349b  movsd   [rsp+98h+var_58], xmm1
0x1800734a1  lea     r8, [rsi+8]
0x1800734a5  lea     rdx, [rsp+98h+var_68]
0x1800734aa  mov     rcx, rbx
0x1800734ad  mov     rax, rdi
0x1800734b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800734b5  nop
0x1800734b6  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1800734bb  call    cs:__imp_VariantClear
0x1800734c1  nop
0x1800734c2  lea     rcx, [rsp+98h+arg_8]
0x1800734ca  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x1800734cf  lea     rcx, [rsi+8]; this
0x1800734d3  cmp     qword ptr [rcx], 0
0x1800734d7  jz      short loc_1800734EF
0x1800734d9  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x1800734de  mov     [r14], rax
0x1800734e1  neg     rax
0x1800734e4  sbb     eax, eax
0x1800734e6  not     eax
0x1800734e8  and     eax, 8007000Eh
0x1800734ed  jmp     short loc_1800734F4
0x1800734ef  mov     eax, 1
0x1800734f4  mov     dword ptr [rsp+98h+arg_0], eax
0x1800734fb  jmp     short loc_180073504
0x1800734fd  mov     eax, dword ptr [rsp+98h+arg_0]
0x180073504  add     rsp, 78h
0x180073508  pop     r14
0x18007350a  pop     rdi
0x18007350b  pop     rsi
0x18007350c  pop     rbx
0x18007350d  retn
```

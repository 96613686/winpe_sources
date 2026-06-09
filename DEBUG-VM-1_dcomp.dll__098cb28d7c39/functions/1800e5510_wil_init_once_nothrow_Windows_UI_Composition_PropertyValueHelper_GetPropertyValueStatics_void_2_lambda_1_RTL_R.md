# wil::init_once_nothrow<`Windows::UI::Composition::PropertyValueHelper::GetPropertyValueStatics(void)'::`2'::_lambda_1_>(_RTL_RUN_ONCE &,`Windows::UI::Composition::PropertyValueHelper::GetPropertyValueStatics(void)'::`2'::_lambda_1_,bool *)

- ea: `0x1800e5510`
- end: `0x1800e55b2`
- name: `??$init_once_nothrow@V_lambda_1_@?1??GetPropertyValueStatics@PropertyValueHelper@Composition@UI@Windows@@CAPEAUIPropertyValueStatics@Foundation@6@XZ@@wil@@YAJAEAT_RTL_RUN_ONCE@@V_lambda_1_@?1??GetPropertyValueStatics@PropertyValueHelper@Composition@UI@Windows@@CAPEAUIPropertyValueStatics@Foundation@7@XZ@PEA_N@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800e54f0`

## callees

- `0x18001358c`
- `0x1800e0af8`
- `0x1800e5510`
- `0x1800e55cc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800e5533`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800e5533`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800e558e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800e55a4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800e558e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800e55a4`

## pseudocode

```c
__int64 __fastcall ___init_once_nothrow_V_lambda_1___1__GetPropertyValueStatics_PropertyValueHelper_Composition_UI_Windows__CAPEAUIPropertyValueStatics_Foundation_6_XZ__wil__YAJAEAT_RTL_RUN_ONCE__V_lambda_1___1__GetPropertyValueStatics_PropertyValueHelper_Composition_UI_Windows__CAPEAUIPropertyValueStatics_Foundation_7_XZ_PEA_N_Z(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  const char *v3; // r9
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL fPending; // [rsp+40h] [rbp+18h] BYREF
  int v10; // [rsp+44h] [rbp+1Ch]

  v10 = HIDWORD(a3);
  fPending = 0;
  if ( !InitOnceBeginInitialize(
          &`Windows::UI::Composition::PropertyValueHelper::GetPropertyValueStatics'::`2'::init,
          0,
          &fPending,
          0) )
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0x37A, (unsigned int)"wil", v3);
  if ( fPending )
  {
    v5 = `Windows::UI::Composition::PropertyValueHelper::GetPropertyValueStatics'::`2'::_lambda_1_::operator()();
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x37F, (unsigned int)"wil", (const char *)(unsigned int)v5, v7);
      InitOnceComplete(&`Windows::UI::Composition::PropertyValueHelper::GetPropertyValueStatics'::`2'::init, 4u, 0);
      return v6;
    }
    InitOnceComplete(&`Windows::UI::Composition::PropertyValueHelper::GetPropertyValueStatics'::`2'::init, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800e5510  mov     qword ptr [rsp+fPending], r8
0x1800e5515  push    rbx; int
0x1800e5516  sub     rsp, 20h
0x1800e551a  xor     r9d, r9d; lpContext
0x1800e551d  mov     [rsp+28h+fPending], 0
0x1800e5525  lea     r8, [rsp+28h+fPending]; fPending
0x1800e552a  xor     edx, edx; dwFlags
0x1800e552c  lea     rcx, ?init@?1??GetPropertyValueStatics@PropertyValueHelper@Composition@UI@Windows@@CAPEAUIPropertyValueStatics@Foundation@5@XZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1800e5533  call    cs:__imp_InitOnceBeginInitialize
0x1800e5539  test    eax, eax
0x1800e553b  jnz     short loc_1800E5555
0x1800e553d  mov     rcx, [rsp+28h]; this
0x1800e5542  lea     r8, aWil; "wil"
0x1800e5549  mov     edx, 37Ah; void *
0x1800e554e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800e5553  jmp     short loc_1800E55AC
0x1800e5555  cmp     [rsp+28h+fPending], 0
0x1800e555a  jz      short loc_1800E55AA
0x1800e555c  call    ??R_lambda_1_@?1??GetPropertyValueStatics@PropertyValueHelper@Composition@UI@Windows@@CAPEAUIPropertyValueStatics@Foundation@5@XZ@QEBA@XZ; `Windows::UI::Composition::PropertyValueHelper::GetPropertyValueStatics(void)'::`2'::_lambda_1_::operator()(void)
0x1800e5561  mov     ebx, eax
0x1800e5563  test    eax, eax
0x1800e5565  jns     short loc_1800E5598
0x1800e5567  mov     rcx, [rsp+28h]; this
0x1800e556c  lea     r8, aWil; "wil"
0x1800e5573  mov     r9d, eax; char *
0x1800e5576  mov     edx, 37Fh; void *
0x1800e557b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5580  xor     r8d, r8d; lpContext
0x1800e5583  lea     rcx, ?init@?1??GetPropertyValueStatics@PropertyValueHelper@Composition@UI@Windows@@CAPEAUIPropertyValueStatics@Foundation@5@XZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1800e558a  lea     edx, [r8+4]; dwFlags
0x1800e558e  call    cs:__imp_InitOnceComplete
0x1800e5594  mov     eax, ebx
0x1800e5596  jmp     short loc_1800E55AC
0x1800e5598  xor     r8d, r8d; lpContext
0x1800e559b  lea     rcx, ?init@?1??GetPropertyValueStatics@PropertyValueHelper@Composition@UI@Windows@@CAPEAUIPropertyValueStatics@Foundation@5@XZ@4T_RTL_RUN_ONCE@@A; lpInitOnce
0x1800e55a2  xor     edx, edx; dwFlags
0x1800e55a4  call    cs:__imp_InitOnceComplete
0x1800e55aa  xor     eax, eax
0x1800e55ac  add     rsp, 20h
0x1800e55b0  pop     rbx
0x1800e55b1  retn
```

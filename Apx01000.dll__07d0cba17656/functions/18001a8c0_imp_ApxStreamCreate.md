# imp_ApxStreamCreate

- ea: `0x18001a8c0`
- end: `0x18001aae5`
- name: `imp_ApxStreamCreate`
- size: `549`
- prototype: `__int64 __fastcall(Apx::ApfVerify *this, Apx::ApfVerify *, Apx::ApfVerify *, Apx::ApfVerify *, Apx::ApfVerify *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x18000a12c`
- `0x18000a8e8`
- `0x18000a948`
- `0x18000d3c0`
- `0x18001051c`
- `0x18001909c`
- `0x18001a430`
- `0x18001a8c0`
- `0x18002a010`

## string_xrefs

- `0x18001a961`: `Config`
- `0x18001a993`: `Config`
- `0x18001a97d`: `*Config`

## pseudocode

```c
__int64 __fastcall imp_ApxStreamCreate(
        Apx::ApfVerify *this,
        Apx::ApfVerify *a2,
        Apx::ApfVerify *a3,
        Apx::ApfVerify *a4,
        Apx::ApfVerify *a5)
{
  int IsNull; // ebx
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  const unsigned __int16 *v13; // r8
  const unsigned __int16 *v14; // r8
  const unsigned __int16 *v15; // r8
  __int64 v16; // rdi
  _QWORD *v17; // rcx
  unsigned __int64 v18; // rax
  struct Apx::ApfStream *v20; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_95bac5cadefb32b72c5d64ba85109a3e_Traceguids);
  }
  v20 = 0;
  IsNull = Apx::ApfVerify::IsNull(this, L"Globals", (const unsigned __int16 *)a3);
  if ( IsNull < 0 )
    goto LABEL_23;
  IsNull = Apx::ApfVerify::IsNotNull(a2, L"Circuit", v10);
  if ( IsNull < 0 )
    goto LABEL_23;
  IsNull = Apx::ApfVerify::IsNull(a3, L"Attributes", v11);
  if ( IsNull < 0 )
    goto LABEL_23;
  IsNull = Apx::ApfVerify::IsNotNull(a4, L"Config", v12);
  if ( IsNull < 0 )
    goto LABEL_23;
  IsNull = Apx::ApfVerify::IsNotNull(*(Apx::ApfVerify **)a4, L"*Config", v13);
  if ( IsNull < 0 )
    goto LABEL_23;
  IsNull = Apx::ApfVerify::IsNotNull(a4, L"Config", v14);
  if ( IsNull < 0 )
    goto LABEL_23;
  IsNull = Apx::ApfVerify::IsNotNull(a5, L"Stream", v15);
  if ( IsNull < 0 )
    goto LABEL_23;
  *(_QWORD *)a5 = 0;
  v16 = ~*(_QWORD *)a4;
  if ( (Apx::ApfVerify *)~*(_QWORD *)(23LL - *(_QWORD *)a4) == a2 )
  {
    IsNull = Apx::ApfStream::_CreateAndInitialize(
               *(struct Apx::ApfCircuit **)(23LL - *(_QWORD *)a4),
               (struct Apx::ApfStreamInit *)~*(_QWORD *)a4,
               &v20);
    if ( IsNull < 0 )
    {
      if ( v20 )
        (**(void (__fastcall ***)(struct Apx::ApfStream *, __int64))v20)(v20, 1);
    }
    else
    {
      v18 = ~(unsigned __int64)v20;
      *(_QWORD *)a5 = ~(unsigned __int64)v20;
      *(_QWORD *)(v16 + 104) = v18;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl'::`2'::impl) )
        imp_ApxObjectReferenceActual(0, *(Apx::ApfVerify **)a5);
      *(_QWORD *)a4 = 0;
      IsNull = 0;
    }
    goto LABEL_23;
  }
  IsNull = -2147024809;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return (unsigned int)IsNull;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_95bac5cadefb32b72c5d64ba85109a3e_Traceguids, a2, -2147024809);
LABEL_23:
    v17 = WPP_GLOBAL_Control;
  }
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 && *((_BYTE *)v17 + 25) >= 5u )
    WPP_SF_(v17[2], 12, WPP_95bac5cadefb32b72c5d64ba85109a3e_Traceguids);
  return (unsigned int)IsNull;
}

```

## disassembly

```asm
0x18001a8c0  push    rbx
0x18001a8c2  push    rbp
0x18001a8c3  push    rsi
0x18001a8c4  push    rdi
0x18001a8c5  push    r12
0x18001a8c7  push    r14
0x18001a8c9  sub     rsp, 48h
0x18001a8cd  mov     r14, r9
0x18001a8d0  mov     rdi, r8
0x18001a8d3  mov     rbp, rdx
0x18001a8d6  mov     rbx, rcx
0x18001a8d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8e0  lea     r12, WPP_GLOBAL_Control
0x18001a8e7  cmp     rcx, r12
0x18001a8ea  jz      short loc_18001A90D
0x18001a8ec  test    byte ptr [rcx+1Ch], 1
0x18001a8f0  jz      short loc_18001A90D
0x18001a8f2  cmp     byte ptr [rcx+19h], 5
0x18001a8f6  jb      short loc_18001A90D
0x18001a8f8  mov     rcx, [rcx+10h]
0x18001a8fc  lea     r8, WPP_95bac5cadefb32b72c5d64ba85109a3e_Traceguids
0x18001a903  mov     edx, 0Ah
0x18001a908  call    WPP_SF_
0x18001a90d  lea     rdx, aGlobals; "Globals"
0x18001a914  mov     [rsp+78h+var_48], 0
0x18001a91d  mov     rcx, rbx; this
0x18001a920  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001a925  mov     ebx, eax
0x18001a927  test    eax, eax
0x18001a929  js      loc_18001AAA9
0x18001a92f  lea     rdx, aCircuit; "Circuit"
0x18001a936  mov     rcx, rbp; this
0x18001a939  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001a93e  mov     ebx, eax
0x18001a940  test    eax, eax
0x18001a942  js      loc_18001AAA9
0x18001a948  lea     rdx, aAttributes; "Attributes"
0x18001a94f  mov     rcx, rdi; this
0x18001a952  call    ?IsNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNull(void const *,ushort const *)
0x18001a957  mov     ebx, eax
0x18001a959  test    eax, eax
0x18001a95b  js      loc_18001AAA9
0x18001a961  lea     rdx, aConfig_0; "Config"
0x18001a968  mov     rcx, r14; this
0x18001a96b  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001a970  mov     ebx, eax
0x18001a972  test    eax, eax
0x18001a974  js      loc_18001AAA9
0x18001a97a  mov     rcx, [r14]; this
0x18001a97d  lea     rdx, aConfig; "*Config"
0x18001a984  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001a989  mov     ebx, eax
0x18001a98b  test    eax, eax
0x18001a98d  js      loc_18001AAA9
0x18001a993  lea     rdx, aConfig_0; "Config"
0x18001a99a  mov     rcx, r14; this
0x18001a99d  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001a9a2  mov     ebx, eax
0x18001a9a4  test    eax, eax
0x18001a9a6  js      loc_18001AAA9
0x18001a9ac  mov     rsi, [rsp+78h+arg_20]
0x18001a9b4  lea     rdx, aStream; "Stream"
0x18001a9bb  mov     rcx, rsi; this
0x18001a9be  call    ?IsNotNull@ApfVerify@Apx@@YAJPEBXPEBG@Z; Apx::ApfVerify::IsNotNull(void const *,ushort const *)
0x18001a9c3  mov     ebx, eax
0x18001a9c5  test    eax, eax
0x18001a9c7  js      loc_18001AAA9
0x18001a9cd  mov     qword ptr [rsi], 0
0x18001a9d4  mov     rdi, [r14]
0x18001a9d7  not     rdi
0x18001a9da  mov     rcx, [rdi+18h]; struct Apx::ApfCircuit *
0x18001a9de  mov     rax, rcx
0x18001a9e1  not     rax
0x18001a9e4  cmp     rax, rbp
0x18001a9e7  jz      short loc_18001AA30
0x18001a9e9  mov     ebx, 80070057h
0x18001a9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9f5  cmp     rcx, r12
0x18001a9f8  jz      loc_18001AAD6
0x18001a9fe  test    byte ptr [rcx+1Ch], 40h
0x18001aa02  jz      loc_18001AAB0
0x18001aa08  cmp     byte ptr [rcx+19h], 2
0x18001aa0c  jb      loc_18001AAB0
0x18001aa12  mov     rcx, [rcx+10h]
0x18001aa16  lea     r8, WPP_95bac5cadefb32b72c5d64ba85109a3e_Traceguids
0x18001aa1d  mov     edx, 0Bh
0x18001aa22  mov     dword ptr [rsp+78h+var_58], ebx
0x18001aa26  mov     r9, rbp
0x18001aa29  call    WPP_SF_qd
0x18001aa2e  jmp     short loc_18001AAA9
0x18001aa30  lea     r8, [rsp+78h+var_48]; struct Apx::ApfStream **
0x18001aa35  mov     rdx, rdi; struct Apx::ApfStreamInit *
0x18001aa38  call    ?_CreateAndInitialize@ApfStream@Apx@@SAJPEAVApfCircuit@2@PEAVApfStreamInit@2@PEAPEAV12@@Z; Apx::ApfStream::_CreateAndInitialize(Apx::ApfCircuit *,Apx::ApfStreamInit *,Apx::ApfStream * *)
0x18001aa3d  mov     ebx, eax
0x18001aa3f  test    eax, eax
0x18001aa41  js      short loc_18001AA8F
0x18001aa43  mov     rax, [rsp+78h+var_48]
0x18001aa48  not     rax
0x18001aa4b  mov     [rsi], rax
0x18001aa4e  mov     [rdi+68h], rax
0x18001aa52  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56664216@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216> `wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl(void)'::`2'::impl
0x18001aa59  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(void)
0x18001aa5e  test    al, al
0x18001aa60  jz      short loc_18001AA84
0x18001aa62  mov     rdx, [rsi]; Apx::ApfVerify *
0x18001aa65  lea     rax, aOnecoreuapDriv_0; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x18001aa6c  mov     r9d, 6Dh ; 'm'
0x18001aa72  mov     [rsp+78h+var_58], rax
0x18001aa77  mov     r8d, 44787041h
0x18001aa7d  xor     ecx, ecx; this
0x18001aa7f  call    imp_ApxObjectReferenceActual
0x18001aa84  mov     qword ptr [r14], 0
0x18001aa8b  xor     ebx, ebx
0x18001aa8d  jmp     short loc_18001AAA9
0x18001aa8f  mov     rcx, [rsp+78h+var_48]
0x18001aa94  test    rcx, rcx
0x18001aa97  jz      short loc_18001AAA9
0x18001aa99  mov     rax, [rcx]
0x18001aa9c  mov     edx, 1
0x18001aaa1  mov     rax, [rax]
0x18001aaa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aaa9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aab0  cmp     rcx, r12
0x18001aab3  jz      short loc_18001AAD6
0x18001aab5  test    byte ptr [rcx+1Ch], 1
0x18001aab9  jz      short loc_18001AAD6
0x18001aabb  cmp     byte ptr [rcx+19h], 5
0x18001aabf  jb      short loc_18001AAD6
0x18001aac1  mov     rcx, [rcx+10h]
0x18001aac5  lea     r8, WPP_95bac5cadefb32b72c5d64ba85109a3e_Traceguids
0x18001aacc  mov     edx, 0Ch
0x18001aad1  call    WPP_SF_
0x18001aad6  mov     eax, ebx
0x18001aad8  add     rsp, 48h
0x18001aadc  pop     r14
0x18001aade  pop     r12
0x18001aae0  pop     rdi
0x18001aae1  pop     rsi
0x18001aae2  pop     rbp
0x18001aae3  pop     rbx
0x18001aae4  retn
```

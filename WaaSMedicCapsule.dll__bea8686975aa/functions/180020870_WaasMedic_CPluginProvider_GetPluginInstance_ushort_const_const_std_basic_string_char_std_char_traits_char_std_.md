# WaasMedic::CPluginProvider::GetPluginInstance(ushort const * const,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,WaasMedic::IRemediationPlugin * *)

- ea: `0x180020870`
- end: `0x180020a6f`
- name: `?GetPluginInstance@CPluginProvider@WaasMedic@@UEAAJQEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAPEAVIRemediationPlugin@2@@Z`
- size: `511`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callees

- `0x18000b308`
- `0x18001efa0`
- `0x180020540`
- `0x180020870`
- `0x180020e68`
- `0x18004b0b0`
- `0x180064010`

## string_xrefs

- `0x1800208a0`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x180020932`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x180020a11`: `onecore\enduser\waasmedic\lib\providers\pluginprovider.cpp`
- `0x18002088c`: `Invalid pointer input to CPluginProvider::GetPluginInstance.`
- `0x180020919`: `Plugin name %ws not found from GetEffectiveRemediationPlugins vector.`
- `0x180020961`: `Invalid plugin definition with null creation routine for %ws.`
- `0x180020a31`: `Invalid plugin definition with null creation routine for %ws.`
- `0x18002098d`: `Plugin creation routine for %ws failed!`
- `0x180020a61`: `Plugin creation routine for %ws failed!`
- `0x1800209f3`: `Plugin name %ws not found on RemediationPlugins array.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::CPluginProvider::GetPluginInstance(__int64 a1, char *a2, __int64 a3, _QWORD *a4)
{
  unsigned int v7; // ebx
  __int64 i; // rax
  const char *v10; // rdi
  unsigned __int16 *v11; // rcx
  int v12; // r9d
  int v13; // edx
  __int64 (__fastcall *v14)(const char *, __int64, _QWORD *); // rax
  unsigned int v15; // eax
  const char *v16; // rdi
  unsigned __int16 *v17; // rcx
  int v18; // r9d
  int v19; // r8d
  __int64 (__fastcall *v20)(const char *, __int64, _QWORD *); // rax
  char *v21; // [rsp+28h] [rbp-50h]
  char *v22; // [rsp+28h] [rbp-50h]
  char *v23; // [rsp+28h] [rbp-50h]
  _QWORD v24[9]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a4 )
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x31,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
      (const char *)0x80004003LL,
      (int)"Invalid pointer input to CPluginProvider::GetPluginInstance.",
      v21);
    return v7;
  }
  *a4 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginContainment_56454451>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PluginContainment_56454451>::GetImpl'::`2'::impl) )
  {
    WaasMedic::CPluginProvider::GetEffectiveRemediationPlugins(v24);
    for ( i = v24[0]; ; i += 16 )
    {
      if ( i == v24[1] )
      {
        v22 = a2;
        v7 = -2147319765;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x43,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
          (const char *)0x8002802BLL,
          (int)"Plugin name %ws not found from GetEffectiveRemediationPlugins vector.",
          v22);
LABEL_13:
        std::vector<WaasMedic::tagPluginRegistrationInfo>::~vector<WaasMedic::tagPluginRegistrationInfo>(v24);
        return v7;
      }
      v10 = *(const char **)i;
      v11 = (unsigned __int16 *)a2;
      do
      {
        v12 = *(unsigned __int16 *)((char *)v11 + *(_QWORD *)i - (_QWORD)a2);
        v13 = *v11 - v12;
        if ( v13 )
          break;
        ++v11;
      }
      while ( v12 );
      if ( !v13 )
        break;
    }
    v14 = *(__int64 (__fastcall **)(const char *, __int64, _QWORD *))(i + 8);
    if ( !v14 )
    {
      v7 = -2147467261;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
        (const char *)0x80004003LL,
        (int)"Invalid plugin definition with null creation routine for %ws.",
        v10);
      goto LABEL_13;
    }
    v7 = v14(v10, a3, a4);
    if ( (v7 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
        (const char *)v7,
        (int)"Plugin creation routine for %ws failed!",
        v10);
      goto LABEL_13;
    }
    std::vector<WaasMedic::tagPluginRegistrationInfo>::~vector<WaasMedic::tagPluginRegistrationInfo>(v24);
  }
  else
  {
    v15 = 0;
    while ( 1 )
    {
      v16 = (const char *)(&off_180065310)[2 * v15];
      v17 = (unsigned __int16 *)a2;
      do
      {
        v18 = *(unsigned __int16 *)((char *)v17 + (char *)(&off_180065310)[2 * v15] - a2);
        v19 = *v17 - v18;
        if ( v19 )
          break;
        ++v17;
      }
      while ( v18 );
      if ( !v19 )
        break;
      if ( (int)++v15 >= 15 )
      {
        v23 = a2;
        v7 = -2147319765;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x56,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
          (const char *)0x8002802BLL,
          (int)"Plugin name %ws not found on RemediationPlugins array.",
          v23);
        return v7;
      }
    }
    v20 = (__int64 (__fastcall *)(const char *, __int64, _QWORD *))*(&funcs_18001F72D + 2 * v15);
    if ( !v20 )
    {
      v7 = -2147467261;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x5A,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
        (const char *)0x80004003LL,
        (int)"Invalid plugin definition with null creation routine for %ws.",
        v16);
      return v7;
    }
    v7 = v20(v16, a3, a4);
    if ( (v7 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\providers\\pluginprovider.cpp",
        (const char *)v7,
        (int)"Plugin creation routine for %ws failed!",
        v16);
      return v7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180020870  push    rbx
0x180020872  push    rbp
0x180020873  push    rsi
0x180020874  push    rdi
0x180020875  sub     rsp, 58h
0x180020879  mov     rsi, r9
0x18002087c  mov     rbp, r8
0x18002087f  mov     rbx, rdx
0x180020882  test    r9, r9
0x180020885  jnz     short loc_1800208B6
0x180020887  mov     rcx, [rsp+78h]; this
0x18002088c  lea     rax, aInvalidPointer_6; "Invalid pointer input to CPluginProvide"...
0x180020893  mov     qword ptr [rsp+78h+var_58], rax; int
0x180020898  mov     ebx, 80004003h
0x18002089d  mov     r9d, ebx; char *
0x1800208a0  lea     r8, aOnecoreEnduser_34; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x1800208a7  lea     edx, [rsi+31h]; void *
0x1800208aa  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800208af  mov     eax, ebx
0x1800208b1  jmp     loc_1800209A7
0x1800208b6  mov     qword ptr [r9], 0
0x1800208bd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PluginContainment_56454451@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PluginContainment_56454451@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginContainment_56454451> `wil::Feature<__WilFeatureTraits_Feature_PluginContainment_56454451>::GetImpl(void)'::`2'::impl
0x1800208c4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PluginContainment_56454451@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PluginContainment_56454451>::__private_IsEnabled(void)
0x1800208c9  test    al, al
0x1800208cb  jz      loc_1800209B0
0x1800208d1  lea     rcx, [rsp+78h+var_48]
0x1800208d6  call    ?GetEffectiveRemediationPlugins@CPluginProvider@WaasMedic@@SA?AV?$vector@UtagPluginRegistrationInfo@WaasMedic@@V?$allocator@UtagPluginRegistrationInfo@WaasMedic@@@std@@@std@@XZ; WaasMedic::CPluginProvider::GetEffectiveRemediationPlugins(void)
0x1800208db  nop
0x1800208dc  mov     rax, [rsp+78h+var_48]
0x1800208e1  jmp     short loc_18002090D
0x1800208e3  mov     rdi, [rax]
0x1800208e6  mov     rcx, rbx
0x1800208e9  mov     r8, rdi
0x1800208ec  sub     r8, rbx
0x1800208ef  movzx   edx, word ptr [rcx]
0x1800208f2  movzx   r9d, word ptr [rcx+r8]
0x1800208f7  sub     edx, r9d
0x1800208fa  jnz     short loc_180020905
0x1800208fc  add     rcx, 2
0x180020900  test    r9d, r9d
0x180020903  jnz     short loc_1800208EF
0x180020905  test    edx, edx
0x180020907  jz      short loc_180020953
0x180020909  add     rax, 10h
0x18002090d  cmp     rax, [rsp+78h+var_40]
0x180020912  jnz     short loc_1800208E3
0x180020914  mov     [rsp+78h+var_50], rbx; char *
0x180020919  lea     rax, aPluginNameWsNo; "Plugin name %ws not found from GetEffec"...
0x180020920  mov     ebx, 8002802Bh
0x180020925  mov     edx, 43h ; 'C'; void *
0x18002092a  mov     qword ptr [rsp+78h+var_58], rax; int
0x18002092f  mov     r9d, ebx; char *
0x180020932  lea     r8, aOnecoreEnduser_34; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180020939  mov     rcx, [rsp+78h]; this
0x18002093e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020943  nop
0x180020944  lea     rcx, [rsp+78h+var_48]
0x180020949  call    ??1?$vector@UtagPluginRegistrationInfo@WaasMedic@@V?$allocator@UtagPluginRegistrationInfo@WaasMedic@@@std@@@std@@QEAA@XZ; std::vector<WaasMedic::tagPluginRegistrationInfo>::~vector<WaasMedic::tagPluginRegistrationInfo>(void)
0x18002094e  jmp     loc_1800208AF
0x180020953  mov     rax, [rax+8]
0x180020957  test    rax, rax
0x18002095a  jnz     short loc_180020974
0x18002095c  mov     [rsp+78h+var_50], rdi
0x180020961  lea     rax, aInvalidPluginD; "Invalid plugin definition with null cre"...
0x180020968  mov     ebx, 80004003h
0x18002096d  mov     edx, 44h ; 'D'
0x180020972  jmp     short loc_18002092A
0x180020974  mov     r8, rsi
0x180020977  mov     rdx, rbp
0x18002097a  mov     rcx, rdi
0x18002097d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020982  mov     ebx, eax
0x180020984  test    eax, eax
0x180020986  jns     short loc_18002099B
0x180020988  mov     [rsp+78h+var_50], rdi
0x18002098d  lea     rax, aPluginCreation; "Plugin creation routine for %ws failed!"
0x180020994  mov     edx, 45h ; 'E'
0x180020999  jmp     short loc_18002092A
0x18002099b  lea     rcx, [rsp+78h+var_48]
0x1800209a0  call    ??1?$vector@UtagPluginRegistrationInfo@WaasMedic@@V?$allocator@UtagPluginRegistrationInfo@WaasMedic@@@std@@@std@@QEAA@XZ; std::vector<WaasMedic::tagPluginRegistrationInfo>::~vector<WaasMedic::tagPluginRegistrationInfo>(void)
0x1800209a5  xor     eax, eax
0x1800209a7  add     rsp, 58h
0x1800209ab  pop     rdi
0x1800209ac  pop     rsi
0x1800209ad  pop     rbp
0x1800209ae  pop     rbx
0x1800209af  retn
0x1800209b0  xor     eax, eax
0x1800209b2  mov     edx, eax
0x1800209b4  add     rdx, rdx
0x1800209b7  lea     r11, off_180065310; "ServiceHealthPlugin"
0x1800209be  mov     rdi, [r11+rdx*8]
0x1800209c2  mov     rcx, rbx
0x1800209c5  mov     r10, rdi
0x1800209c8  sub     r10, rbx
0x1800209cb  movzx   r8d, word ptr [rcx]
0x1800209cf  movzx   r9d, word ptr [rcx+r10]
0x1800209d4  sub     r8d, r9d
0x1800209d7  jnz     short loc_1800209E2
0x1800209d9  add     rcx, 2
0x1800209dd  test    r9d, r9d
0x1800209e0  jnz     short loc_1800209CB
0x1800209e2  test    r8d, r8d
0x1800209e5  jz      short loc_180020A22
0x1800209e7  inc     eax
0x1800209e9  cmp     eax, 0Fh
0x1800209ec  jl      short loc_1800209B2
0x1800209ee  mov     [rsp+78h+var_50], rbx; char *
0x1800209f3  lea     rax, aPluginNameWsNo_0; "Plugin name %ws not found on Remediatio"...
0x1800209fa  mov     ebx, 8002802Bh
0x1800209ff  mov     edx, 56h ; 'V'; void *
0x180020a04  mov     rcx, [rsp+78h]; this
0x180020a09  mov     qword ptr [rsp+78h+var_58], rax; int
0x180020a0e  mov     r9d, ebx; char *
0x180020a11  lea     r8, aOnecoreEnduser_34; "onecore\\enduser\\waasmedic\\lib\\provi"...
0x180020a18  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020a1d  jmp     loc_1800208AF
0x180020a22  mov     rax, ds:(funcs_18001F72D - 180065310h)[r11+rdx*8]
0x180020a27  test    rax, rax
0x180020a2a  jnz     short loc_180020A44
0x180020a2c  mov     [rsp+78h+var_50], rdi
0x180020a31  lea     rax, aInvalidPluginD; "Invalid plugin definition with null cre"...
0x180020a38  mov     ebx, 80004003h
0x180020a3d  mov     edx, 5Ah ; 'Z'
0x180020a42  jmp     short loc_180020A04
0x180020a44  mov     r8, rsi
0x180020a47  mov     rdx, rbp
0x180020a4a  mov     rcx, rdi; unsigned __int16 *
0x180020a4d  call    _guard_dispatch_icall$thunk$10345483385596137414; WaasMedic::CServiceHealthPlugin::CreateInstance(ushort const *,std::string const &,WaasMedic::IRemediationPlugin * *) ...
0x180020a52  mov     ebx, eax
0x180020a54  test    eax, eax
0x180020a56  jns     loc_1800209A5
0x180020a5c  mov     [rsp+78h+var_50], rdi
0x180020a61  lea     rax, aPluginCreation; "Plugin creation routine for %ws failed!"
0x180020a68  mov     edx, 5Bh ; '['
0x180020a6d  jmp     short loc_180020A04
```

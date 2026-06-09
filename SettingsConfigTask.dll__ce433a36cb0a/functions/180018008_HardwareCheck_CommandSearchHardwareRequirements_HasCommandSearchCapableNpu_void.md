# HardwareCheck::CommandSearchHardwareRequirements::HasCommandSearchCapableNpu(void)

- ea: `0x180018008`
- end: `0x1800181ea`
- name: `?HasCommandSearchCapableNpu@CommandSearchHardwareRequirements@HardwareCheck@@CA_NXZ`
- size: `482`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018cfc`

## callees

- `0x18000d4f4`
- `0x18000e0b8`
- `0x1800130f0`
- `0x180013a2c`
- `0x180017fb8`
- `0x180018008`
- `0x180019898`
- `0x18001cdcc`
- `0x18001ce08`
- `0x18001ce44`
- `0x18001ce80`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char HardwareCheck::CommandSearchHardwareRequirements::HasCommandSearchCapableNpu(void)
{
  struct DXCoreHardwareIDParts *v1; // rdi
  struct DXCoreHardwareIDParts *v2; // rsi
  unsigned __int64 v3; // rax
  __int64 v4; // rdx
  struct DXCoreHardwareIDParts *v5; // rcx
  struct DXCoreHardwareIDParts *v6; // [rsp+20h] [rbp-48h] BYREF
  struct DXCoreHardwareIDParts *v7; // [rsp+28h] [rbp-40h]
  __int64 v8; // [rsp+30h] [rbp-38h]
  unsigned __int64 v9; // [rsp+50h] [rbp-18h]
  struct DXCoreHardwareIDParts **v10; // [rsp+90h] [rbp+28h] BYREF

  udk::npu_detection::FindNpus(&v6);
  v10 = &v6;
  if ( (unsigned __int8)_lambda_5f0c78baaeae447c01d66254526346f7_::operator()(&v10, 1297040209) )
  {
    if ( !HardwareCheck::CommandSearchHardwareRequirements::HasCPUType(0xCu) )
      goto LABEL_32;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57629517>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57629517>::GetImpl'::`2'::impl) )
      goto LABEL_4;
    LODWORD(v10) = 2;
    goto LABEL_15;
  }
  if ( (unsigned __int8)_lambda_5f0c78baaeae447c01d66254526346f7_::operator()(&v10, 32902) )
  {
    if ( !HardwareCheck::CommandSearchHardwareRequirements::HasCPUType(9u) )
      goto LABEL_32;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606323>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57606323>::GetImpl'::`2'::impl) )
      goto LABEL_4;
    LODWORD(v10) = 3;
    goto LABEL_15;
  }
  if ( !(unsigned __int8)_lambda_5f0c78baaeae447c01d66254526346f7_::operator()(&v10, 4130) )
  {
    LODWORD(v10) = 8;
    goto LABEL_31;
  }
  if ( !HardwareCheck::CommandSearchHardwareRequirements::HasCPUType(9u) )
  {
LABEL_27:
    v1 = v6;
    goto LABEL_28;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58368509>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58368509>::GetImpl'::`2'::impl) )
  {
    v9 = 0x20000000CB0118LL;
    v1 = v6;
    v2 = v7;
    if ( v6 != v7 )
    {
      while ( 1 )
      {
        v3 = *((_QWORD *)v1 + 3);
        if ( !v3 )
        {
          if ( v9 )
          {
            v3 = *(_QWORD *)udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(
                              (udk::CopilotPlusDetection::details *)&v10,
                              v1);
            *((_QWORD *)v1 + 3) = v3;
          }
          else
          {
            v3 = 0;
          }
        }
        if ( *(_DWORD *)v1 == 4130 && *((_DWORD *)v1 + 1) == 6128 && v3 >= v9 )
          goto LABEL_13;
        v1 = (struct DXCoreHardwareIDParts *)((char *)v1 + 32);
        if ( v1 == v2 )
          goto LABEL_27;
      }
    }
LABEL_28:
    if ( v1 )
    {
      v4 = v8 - (_QWORD)v1;
      v5 = v1;
LABEL_34:
      std::_Deallocate<16>(v5, (struct std::nothrow_t *)(v4 & 0xFFFFFFFFFFFFFFE0uLL));
    }
    return 0;
  }
LABEL_13:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606309>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57606309>::GetImpl'::`2'::impl) )
  {
LABEL_4:
    LODWORD(v10) = 5;
LABEL_31:
    HardwareCheck::CommandSearchHardwareRequirementsTelemetry::HardWareCheckResult<enum HardwareCheck::HardWareCheckResult>((int *)&v10);
LABEL_32:
    v5 = v6;
    if ( v6 )
    {
      v4 = v8 - (_QWORD)v6;
      goto LABEL_34;
    }
    return 0;
  }
  LODWORD(v10) = 4;
LABEL_15:
  HardwareCheck::CommandSearchHardwareRequirementsTelemetry::HardWareCheckResult<enum HardwareCheck::HardWareCheckResult>((int *)&v10);
  if ( v6 )
    std::_Deallocate<16>(v6, (struct std::nothrow_t *)((v8 - (_QWORD)v6) & 0xFFFFFFFFFFFFFFE0uLL));
  return 1;
}

```

## disassembly

```asm
0x180018008  push    rbp
0x18001800a  push    rsi
0x18001800b  push    rdi
0x18001800c  push    r15
0x18001800e  mov     rbp, rsp
0x180018011  sub     rsp, 68h
0x180018015  lea     rcx, [rbp+var_48]
0x180018019  call    ?FindNpus@npu_detection@udk@@YA?AV?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@XZ; udk::npu_detection::FindNpus(void)
0x18001801e  nop
0x18001801f  lea     rax, [rbp+var_48]
0x180018023  mov     [rbp+arg_0], rax
0x180018027  mov     edx, 4D4F4351h
0x18001802c  lea     rcx, [rbp+arg_0]
0x180018030  call    ??R_lambda_5f0c78baaeae447c01d66254526346f7_@@QEBA@I@Z; _lambda_5f0c78baaeae447c01d66254526346f7_::operator()(uint)
0x180018035  test    al, al
0x180018037  jz      short loc_180018077
0x180018039  mov     ecx, 0Ch; unsigned __int16
0x18001803e  call    ?HasCPUType@CommandSearchHardwareRequirements@HardwareCheck@@CA_NG@Z; HardwareCheck::CommandSearchHardwareRequirements::HasCPUType(ushort)
0x180018043  test    al, al
0x180018045  jz      loc_1800181C5
0x18001804b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57629517@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57629517@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57629517> `wil::Feature<__WilFeatureTraits_Feature_57629517>::GetImpl(void)'::`2'::impl
0x180018052  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57629517@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57629517>::__private_IsEnabled(void)
0x180018057  lea     rcx, [rbp+arg_0]
0x18001805b  test    al, al
0x18001805d  jnz     short loc_18001806B
0x18001805f  mov     dword ptr [rbp+arg_0], 5
0x180018066  jmp     loc_1800181BF
0x18001806b  mov     dword ptr [rbp+arg_0], 2
0x180018072  jmp     loc_18001810F
0x180018077  mov     edx, 8086h
0x18001807c  lea     rcx, [rbp+arg_0]
0x180018080  call    ??R_lambda_5f0c78baaeae447c01d66254526346f7_@@QEBA@I@Z; _lambda_5f0c78baaeae447c01d66254526346f7_::operator()(uint)
0x180018085  test    al, al
0x180018087  jz      short loc_1800180B8
0x180018089  mov     ecx, 9; unsigned __int16
0x18001808e  call    ?HasCPUType@CommandSearchHardwareRequirements@HardwareCheck@@CA_NG@Z; HardwareCheck::CommandSearchHardwareRequirements::HasCPUType(ushort)
0x180018093  test    al, al
0x180018095  jz      loc_1800181C5
0x18001809b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57606323@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57606323@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606323> `wil::Feature<__WilFeatureTraits_Feature_57606323>::GetImpl(void)'::`2'::impl
0x1800180a2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57606323@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606323>::__private_IsEnabled(void)
0x1800180a7  lea     rcx, [rbp+arg_0]
0x1800180ab  test    al, al
0x1800180ad  jz      short loc_18001805F
0x1800180af  mov     dword ptr [rbp+arg_0], 3
0x1800180b6  jmp     short loc_18001810F
0x1800180b8  mov     edx, 1022h
0x1800180bd  lea     rcx, [rbp+arg_0]
0x1800180c1  call    ??R_lambda_5f0c78baaeae447c01d66254526346f7_@@QEBA@I@Z; _lambda_5f0c78baaeae447c01d66254526346f7_::operator()(uint)
0x1800180c6  test    al, al
0x1800180c8  jz      loc_1800181B4
0x1800180ce  mov     ecx, 9; unsigned __int16
0x1800180d3  call    ?HasCPUType@CommandSearchHardwareRequirements@HardwareCheck@@CA_NG@Z; HardwareCheck::CommandSearchHardwareRequirements::HasCPUType(ushort)
0x1800180d8  test    al, al
0x1800180da  jz      loc_18001819F
0x1800180e0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58368509@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58368509@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58368509> `wil::Feature<__WilFeatureTraits_Feature_58368509>::GetImpl(void)'::`2'::impl
0x1800180e7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58368509@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58368509>::__private_IsEnabled(void)
0x1800180ec  test    al, al
0x1800180ee  jnz     short loc_180018135
0x1800180f0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57606309@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57606309@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606309> `wil::Feature<__WilFeatureTraits_Feature_57606309>::GetImpl(void)'::`2'::impl
0x1800180f7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57606309@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57606309>::__private_IsEnabled(void)
0x1800180fc  lea     rcx, [rbp+arg_0]
0x180018100  test    al, al
0x180018102  jz      loc_18001805F
0x180018108  mov     dword ptr [rbp+arg_0], 4
0x18001810f  call    ??$HardWareCheckResult@W40HardwareCheck@@@CommandSearchHardwareRequirementsTelemetry@HardwareCheck@@SAX$$QEAW4HardWareCheckResult@1@@Z; HardwareCheck::CommandSearchHardwareRequirementsTelemetry::HardWareCheckResult<HardwareCheck::HardWareCheckResult>(HardwareCheck::HardWareCheckResult &&)
0x180018114  nop
0x180018115  mov     rcx, [rbp+var_48]
0x180018119  test    rcx, rcx
0x18001811c  jz      short loc_18001812E
0x18001811e  mov     rdx, [rbp+var_38]
0x180018122  sub     rdx, rcx
0x180018125  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180018129  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001812e  mov     al, 1
0x180018130  jmp     loc_1800181E0
0x180018135  mov     dword ptr [rbp+var_18], 0CB0118h
0x18001813c  mov     dword ptr [rbp+var_18+4], 200000h
0x180018143  mov     r15d, 20h ; ' '
0x180018149  mov     rdi, [rbp+var_48]
0x18001814d  mov     rsi, [rbp+var_40]
0x180018151  cmp     rdi, rsi
0x180018154  jz      short loc_1800181A3
0x180018156  mov     rax, [rdi+18h]
0x18001815a  test    rax, rax
0x18001815d  jnz     short loc_18001817C
0x18001815f  cmp     [rbp+var_18], rax
0x180018163  jz      short loc_18001817A
0x180018165  mov     rdx, rdi; struct DXCoreHardwareIDParts *
0x180018168  lea     rcx, [rbp+arg_0]; this
0x18001816c  call    ?QueryDriverVersionUsingSetupDi@details@CopilotPlusDetection@udk@@YA@AEBUDXCoreHardwareIDParts@@@Z; udk::CopilotPlusDetection::details::QueryDriverVersionUsingSetupDi(DXCoreHardwareIDParts const &)
0x180018171  mov     rax, [rax]
0x180018174  mov     [rdi+18h], rax
0x180018178  jmp     short loc_18001817C
0x18001817a  xor     eax, eax
0x18001817c  cmp     dword ptr [rdi], 1022h
0x180018182  jnz     short loc_180018197
0x180018184  cmp     dword ptr [rdi+4], 17F0h
0x18001818b  jnz     short loc_180018197
0x18001818d  cmp     rax, [rbp+var_18]
0x180018191  jnb     loc_1800180F0
0x180018197  add     rdi, r15
0x18001819a  cmp     rdi, rsi
0x18001819d  jnz     short loc_180018156
0x18001819f  mov     rdi, [rbp+var_48]
0x1800181a3  test    rdi, rdi
0x1800181a6  jz      short loc_1800181DE
0x1800181a8  mov     rdx, [rbp+var_38]
0x1800181ac  sub     rdx, rdi
0x1800181af  mov     rcx, rdi
0x1800181b2  jmp     short loc_1800181D5
0x1800181b4  mov     dword ptr [rbp+arg_0], 8
0x1800181bb  lea     rcx, [rbp+arg_0]
0x1800181bf  call    ??$HardWareCheckResult@W40HardwareCheck@@@CommandSearchHardwareRequirementsTelemetry@HardwareCheck@@SAX$$QEAW4HardWareCheckResult@1@@Z; HardwareCheck::CommandSearchHardwareRequirementsTelemetry::HardWareCheckResult<HardwareCheck::HardWareCheckResult>(HardwareCheck::HardWareCheckResult &&)
0x1800181c4  nop
0x1800181c5  mov     rcx, [rbp+var_48]
0x1800181c9  test    rcx, rcx
0x1800181cc  jz      short loc_1800181DE
0x1800181ce  mov     rdx, [rbp+var_38]
0x1800181d2  sub     rdx, rcx
0x1800181d5  and     rdx, 0FFFFFFFFFFFFFFE0h
0x1800181d9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800181de  xor     al, al
0x1800181e0  add     rsp, 68h
0x1800181e4  pop     r15
0x1800181e6  pop     rdi
0x1800181e7  pop     rsi
0x1800181e8  pop     rbp
0x1800181e9  retn
```

# _anonymous_namespace_::GetNameOfInboxAT

- ea: `0x14000c68c`
- end: `0x14000c7da`
- name: `_anonymous_namespace_::GetNameOfInboxAT`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000c8b4`

## callees

- `0x140009024`
- `0x14000c50c`
- `0x14000c68c`
- `0x14000cb50`

## string_xrefs

- `0x14000c6ea`: `voiceaccess`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::GetNameOfInboxAT(int a1, __int64 *a2)
{
  unsigned int v2; // edi
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  __int64 v9; // rcx
  unsigned int v10; // r8d
  const wchar_t *v11; // rdx
  unsigned int v12; // r8d
  int v14; // [rsp+60h] [rbp+18h] BYREF
  __int16 v15; // [rsp+64h] [rbp+1Ch]
  __int64 v16; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  if ( !a1 )
  {
    v10 = 8;
    v11 = L"narrator";
    goto LABEL_20;
  }
  v4 = a1 - 1;
  if ( !v4 )
  {
    v10 = 13;
    v11 = L"magnifierpane";
    goto LABEL_20;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v10 = 3;
    v11 = L"osk";
    goto LABEL_20;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v10 = 14;
    v11 = L"colorfiltering";
    goto LABEL_20;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v10 = 15;
    v11 = L"cursorindicator";
    goto LABEL_20;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v10 = 10;
    v11 = L"speechreco";
    goto LABEL_20;
  }
  v9 = (unsigned int)(v8 - 1);
  if ( !(_DWORD)v9 )
  {
    v12 = *(_DWORD *)Feature_LCTest__descriptor;
    if ( (*(_DWORD *)Feature_LCTest__descriptor & 4) == 0 )
    {
      v16 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LCTest>::GetCachedFeatureEnabledState(
                         v9,
                         &v16);
      v12 = v16;
    }
    v14 = 0;
    v15 = 3;
    wil::details::ReportUsageToService(&qword_140021390, 31072829, (v12 >> 10) & 1, (v12 >> 11) & 1, &v14, 1);
    v10 = 12;
    v11 = L"livecaptions";
    goto LABEL_20;
  }
  if ( (_DWORD)v9 == 1 )
  {
    v10 = 11;
    v11 = L"voiceaccess";
LABEL_20:
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v11, v10);
    return v2;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x14000c68c  mov     [rsp+arg_0], rbx
0x14000c691  push    rdi
0x14000c692  sub     rsp, 40h
0x14000c696  xor     edi, edi
0x14000c698  mov     rbx, rdx
0x14000c69b  test    ecx, ecx
0x14000c69d  jz      loc_14000C7B8
0x14000c6a3  sub     ecx, 1
0x14000c6a6  jz      loc_14000C7A9
0x14000c6ac  sub     ecx, 1
0x14000c6af  jz      loc_14000C79A
0x14000c6b5  sub     ecx, 1
0x14000c6b8  jz      loc_14000C78B
0x14000c6be  sub     ecx, 1
0x14000c6c1  jz      loc_14000C77C
0x14000c6c7  sub     ecx, 1
0x14000c6ca  jz      loc_14000C76D
0x14000c6d0  sub     ecx, 1
0x14000c6d3  jz      short loc_14000C6F6
0x14000c6d5  cmp     ecx, 1
0x14000c6d8  jz      short loc_14000C6E4
0x14000c6da  mov     edi, 80070057h
0x14000c6df  jmp     loc_14000C7CD
0x14000c6e4  mov     r8d, 0Bh
0x14000c6ea  lea     rdx, aVoiceaccess; "voiceaccess"
0x14000c6f1  jmp     loc_14000C7C5
0x14000c6f6  mov     rax, cs:Feature_LCTest__descriptor
0x14000c6fd  mov     r8d, [rax]
0x14000c700  test    r8b, 4
0x14000c704  jnz     short loc_14000C71B
0x14000c706  lea     rdx, [rsp+48h+arg_18]
0x14000c70b  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_LCTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LCTest>::GetCachedFeatureEnabledState(void)
0x14000c710  mov     rcx, [rax]
0x14000c713  mov     [rsp+48h+arg_18], rcx
0x14000c718  mov     r8d, ecx
0x14000c71b  mov     r9d, r8d
0x14000c71e  mov     [rsp+48h+var_20], 1
0x14000c726  xor     eax, eax
0x14000c728  shr     r9d, 0Bh
0x14000c72c  mov     [rsp+48h+arg_10], eax
0x14000c730  lea     rcx, qword_140021390
0x14000c737  shr     r8d, 0Ah
0x14000c73b  lea     rax, [rsp+48h+arg_10]
0x14000c740  and     r9d, 1
0x14000c744  mov     [rsp+48h+var_28], rax
0x14000c749  and     r8d, 1
0x14000c74d  mov     [rsp+48h+arg_14], 3
0x14000c754  mov     edx, 1DA223Dh
0x14000c759  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14000c75e  mov     r8d, 0Ch
0x14000c764  lea     rdx, aLivecaptions; "livecaptions"
0x14000c76b  jmp     short loc_14000C7C5
0x14000c76d  mov     r8d, 0Ah
0x14000c773  lea     rdx, aSpeechreco; "speechreco"
0x14000c77a  jmp     short loc_14000C7C5
0x14000c77c  mov     r8d, 0Fh
0x14000c782  lea     rdx, aCursorindicato; "cursorindicator"
0x14000c789  jmp     short loc_14000C7C5
0x14000c78b  mov     r8d, 0Eh
0x14000c791  lea     rdx, aColorfiltering_0; "colorfiltering"
0x14000c798  jmp     short loc_14000C7C5
0x14000c79a  mov     r8d, 3
0x14000c7a0  lea     rdx, aOsk; "osk"
0x14000c7a7  jmp     short loc_14000C7C5
0x14000c7a9  mov     r8d, 0Dh
0x14000c7af  lea     rdx, aMagnifierpane; "magnifierpane"
0x14000c7b6  jmp     short loc_14000C7C5
0x14000c7b8  mov     r8d, 8
0x14000c7be  lea     rdx, aNarrator; "narrator"
0x14000c7c5  mov     rcx, rbx
0x14000c7c8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14000c7cd  mov     rbx, [rsp+48h+arg_0]
0x14000c7d2  mov     eax, edi
0x14000c7d4  add     rsp, 40h
0x14000c7d8  pop     rdi
0x14000c7d9  retn
```

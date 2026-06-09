# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetCurrentFeatureEnabledState(int *)

- ea: `0x180014af4`
- end: `0x180014c14`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180014a0c`

## callees

- `0x1800148a8`
- `0x180014af4`
- `0x180014da0`
- `0x180014ff8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinIoTBugFixBundle_Ge_6>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  __int64 v7; // rcx
  int v8; // edx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v14 = a1;
  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x33D0334, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( (FeatureEnabledState & 0xFFFFFF3F) == 2 )
      v7 = 64;
    v8 = v7;
  }
  else
  {
    v7 = 64;
    v8 = 64;
  }
  v9 = 1;
  v10 = v8 | v6;
  v11 = v7 | v6;
  *(_DWORD *)a2 = v10;
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 || (LOBYTE(v7) = 0, (v11 & 0x40) != 0) )
  {
    v12 = *(_DWORD *)Feature_UxLabTest__descriptor;
    if ( (*(_DWORD *)Feature_UxLabTest__descriptor & 4) == 0 )
    {
      v15 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(
               (wil::details *)v7,
               &v15);
      v12 = v15;
    }
    WORD2(v14) = 3;
    LODWORD(v14) = 0;
    wil::details::ReportUsageToService(&qword_18001F7F8, 57048218, (v12 >> 10) & 1, (v12 >> 11) & 1, &v14, 1, 0);
    LOBYTE(v7) = 1;
  }
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x180014af4  mov     [rsp+arg_10], rbx
0x180014af9  mov     [rsp+arg_18], rsi
0x180014afe  mov     [rsp+arg_0], rcx
0x180014b03  push    rdi
0x180014b04  sub     rsp, 40h
0x180014b08  mov     ecx, 33D0334h; this
0x180014b0d  mov     rdi, rdx
0x180014b10  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180014b15  mov     edx, eax
0x180014b17  mov     qword ptr [rdi], 0
0x180014b1e  and     edx, 0FFFFFF3Fh
0x180014b24  mov     ecx, eax
0x180014b26  and     eax, 80h
0x180014b2b  mov     r8d, edx
0x180014b2e  and     r8d, 3
0x180014b32  mov     esi, 40h ; '@'
0x180014b37  shl     r8d, 2
0x180014b3b  and     ecx, esi
0x180014b3d  or      r8d, ecx
0x180014b40  shl     r8d, 2
0x180014b44  or      r8d, eax
0x180014b47  shl     r8d, 3
0x180014b4b  test    edx, edx
0x180014b4d  jnz     short loc_180014B55
0x180014b4f  mov     ecx, esi
0x180014b51  mov     edx, esi
0x180014b53  jmp     short loc_180014B5F
0x180014b55  xor     ecx, ecx
0x180014b57  cmp     edx, 2
0x180014b5a  cmovz   ecx, esi
0x180014b5d  mov     edx, ecx
0x180014b5f  mov     eax, r8d
0x180014b62  mov     ebx, 1
0x180014b67  or      eax, edx
0x180014b69  or      r8d, ecx
0x180014b6c  mov     [rdi], eax
0x180014b6e  bt      r8d, 0Ah
0x180014b73  jnb     short loc_180014B7E
0x180014b75  cmp     r8d, 800h
0x180014b7c  jnb     short loc_180014B85
0x180014b7e  xor     cl, cl
0x180014b80  test    sil, r8b
0x180014b83  jz      short loc_180014BED
0x180014b85  mov     rax, cs:Feature_UxLabTest__descriptor
0x180014b8c  mov     r8d, [rax]
0x180014b8f  test    r8b, 4
0x180014b93  jnz     short loc_180014BAA
0x180014b95  lea     rdx, [rsp+48h+arg_8]
0x180014b9a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)
0x180014b9f  mov     rcx, [rax]
0x180014ba2  mov     [rsp+48h+arg_8], rcx
0x180014ba7  mov     r8d, ecx
0x180014baa  xor     eax, eax
0x180014bac  mov     word ptr [rsp+48h+arg_0+4], 3
0x180014bb3  mov     r9d, r8d
0x180014bb6  mov     [rsp+48h+var_18], eax
0x180014bba  mov     dword ptr [rsp+48h+arg_0], eax
0x180014bbe  lea     rcx, qword_18001F7F8
0x180014bc5  shr     r9d, 0Bh
0x180014bc9  lea     rax, [rsp+48h+arg_0]
0x180014bce  shr     r8d, 0Ah
0x180014bd2  and     r9d, ebx
0x180014bd5  and     r8d, ebx
0x180014bd8  mov     [rsp+48h+var_20], ebx
0x180014bdc  mov     edx, 3667C9Ah
0x180014be1  mov     [rsp+48h+var_28], rax
0x180014be6  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180014beb  mov     cl, bl
0x180014bed  mov     eax, [rdi]
0x180014bef  test    sil, al
0x180014bf2  jz      short loc_180014BF8
0x180014bf4  test    cl, cl
0x180014bf6  jnz     short loc_180014BFA
0x180014bf8  xor     ebx, ebx
0x180014bfa  mov     rsi, [rsp+48h+arg_18]
0x180014bff  and     eax, 0FFFFFFFEh
0x180014c02  or      eax, ebx
0x180014c04  mov     rbx, [rsp+48h+arg_10]
0x180014c09  mov     [rdi], eax
0x180014c0b  mov     rax, rdi
0x180014c0e  add     rsp, 40h
0x180014c12  pop     rdi
0x180014c13  retn
```

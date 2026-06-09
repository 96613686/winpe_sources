# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18001fcbc`
- end: `0x18001fe25`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001f44c`

## callees

- `0x18001f038`
- `0x18001fcbc`
- `0x180020aa4`
- `0x180021638`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  __int64 (__fastcall *v2)(__int64, __int64); // rax
  int v4; // edx
  unsigned int v5; // r8d
  int v6; // ecx
  __int64 v7; // rdx
  int v8; // r8d
  int v9; // edi
  int v10; // eax
  unsigned int v11; // ecx
  char v12; // si
  __int64 v13; // rcx
  unsigned int v14; // r8d
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 v17; // [rsp+68h] [rbp+10h] BYREF

  v16 = a1;
  v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v2 = (__int64 (__fastcall *)(__int64, __int64))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v4 = v2(58989070, 3);
  }
  else
  {
    v4 = 0;
  }
  *a2 = 0;
  v5 = v4 & 0xFFFFFF3F;
  v6 = 8 * (v4 & 0x80 | (4 * (v4 & 0x40 | (4 * (v4 & 3)))));
  if ( (v4 & 0xFFFFFF3F) != 0 )
  {
    v7 = 0;
    if ( v5 == 2 )
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    LOBYTE(v7) = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_22;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl'::`2'::impl,
                          v7) )
  {
    v14 = *(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor;
    if ( (*(_DWORD *)Feature_Standalone_26_04_NonSec__descriptor & 4) == 0 )
    {
      v17 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(
                         v13,
                         &v17);
      v14 = v17;
    }
    WORD2(v16) = 3;
    LODWORD(v16) = 0;
    wil::details::ReportUsageToService(
      (__int64)&qword_18005FD98,
      0x37E2887u,
      (v14 >> 10) & 1,
      (v14 >> 11) & 1,
      (__int64)&v16,
      1u,
      0);
    LOBYTE(v7) = 1;
  }
  else
  {
    LOBYTE(v7) = 0;
  }
  if ( v12 && !(_BYTE)v7 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_22:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !(_BYTE)v7 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x18001fcbc  mov     [rsp+arg_10], rbx
0x18001fcc1  mov     [rsp+arg_0], rcx
0x18001fcc6  push    rbp
0x18001fcc7  push    rsi
0x18001fcc8  push    rdi
0x18001fcc9  sub     rsp, 40h
0x18001fccd  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001fcd4  mov     rbx, rdx
0x18001fcd7  test    rax, rax
0x18001fcda  jz      short loc_18001FCEF
0x18001fcdc  mov     edx, 3
0x18001fce1  mov     ecx, 3841A0Eh
0x18001fce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fceb  mov     edx, eax
0x18001fced  jmp     short loc_18001FCFD
0x18001fcef  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001fcf6  test    rax, rax
0x18001fcf9  jnz     short loc_18001FCDC
0x18001fcfb  xor     edx, edx
0x18001fcfd  mov     r8d, edx
0x18001fd00  mov     qword ptr [rbx], 0
0x18001fd07  and     r8d, 0FFFFFF3Fh
0x18001fd0e  mov     eax, edx
0x18001fd10  and     edx, 80h
0x18001fd16  mov     ecx, r8d
0x18001fd19  and     ecx, 3
0x18001fd1c  mov     ebp, 40h ; '@'
0x18001fd21  shl     ecx, 2
0x18001fd24  and     eax, ebp
0x18001fd26  or      ecx, eax
0x18001fd28  shl     ecx, 2
0x18001fd2b  or      ecx, edx
0x18001fd2d  shl     ecx, 3
0x18001fd30  test    r8d, r8d
0x18001fd33  jnz     short loc_18001FD3C
0x18001fd35  mov     edx, ebp
0x18001fd37  mov     r8d, ebp
0x18001fd3a  jmp     short loc_18001FD48
0x18001fd3c  xor     edx, edx
0x18001fd3e  cmp     r8d, 2
0x18001fd42  cmovz   edx, ebp
0x18001fd45  mov     r8d, edx
0x18001fd48  mov     eax, ecx
0x18001fd4a  mov     edi, 1
0x18001fd4f  or      eax, r8d
0x18001fd52  or      ecx, edx
0x18001fd54  mov     [rbx], eax
0x18001fd56  bt      ecx, 0Ah
0x18001fd5a  jnb     short loc_18001FD69
0x18001fd5c  cmp     ecx, 800h
0x18001fd62  jb      short loc_18001FD69
0x18001fd64  mov     sil, dil
0x18001fd67  jmp     short loc_18001FD77
0x18001fd69  xor     sil, sil
0x18001fd6c  xor     dl, dl
0x18001fd6e  test    bpl, cl
0x18001fd71  jz      loc_18001FE01
0x18001fd77  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UexTest7@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7> `wil::Feature<__WilFeatureTraits_Feature_UexTest7>::GetImpl(void)'::`2'::impl
0x18001fd7e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::__private_IsEnabled(wil::ReportingKind)
0x18001fd83  test    al, al
0x18001fd85  jz      short loc_18001FDF2
0x18001fd87  mov     rax, cs:Feature_Standalone_26_04_NonSec__descriptor
0x18001fd8e  mov     r8d, [rax]
0x18001fd91  test    r8b, 4
0x18001fd95  jnz     short loc_18001FDAC
0x18001fd97  lea     rdx, [rsp+58h+arg_8]
0x18001fd9c  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_04_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_04_NonSec>::GetCachedFeatureEnabledState(void)
0x18001fda1  mov     rcx, [rax]
0x18001fda4  mov     [rsp+58h+arg_8], rcx
0x18001fda9  mov     r8d, ecx
0x18001fdac  xor     eax, eax
0x18001fdae  mov     word ptr [rsp+58h+arg_0+4], 3
0x18001fdb5  mov     r9d, r8d
0x18001fdb8  mov     [rsp+58h+var_28], eax
0x18001fdbc  mov     dword ptr [rsp+58h+arg_0], eax
0x18001fdc0  lea     rcx, qword_18005FD98
0x18001fdc7  shr     r9d, 0Bh
0x18001fdcb  lea     rax, [rsp+58h+arg_0]
0x18001fdd0  shr     r8d, 0Ah
0x18001fdd4  and     r9d, edi
0x18001fdd7  and     r8d, edi
0x18001fdda  mov     [rsp+58h+var_30], edi
0x18001fdde  mov     edx, 37E2887h
0x18001fde3  mov     [rsp+58h+var_38], rax
0x18001fde8  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18001fded  mov     dl, dil
0x18001fdf0  jmp     short loc_18001FDF4
0x18001fdf2  xor     dl, dl
0x18001fdf4  test    sil, sil
0x18001fdf7  jz      short loc_18001FE01
0x18001fdf9  test    dl, dl
0x18001fdfb  jnz     short loc_18001FE01
0x18001fdfd  btr     dword ptr [rbx], 0Ah
0x18001fe01  mov     eax, [rbx]
0x18001fe03  test    bpl, al
0x18001fe06  jz      short loc_18001FE0C
0x18001fe08  test    dl, dl
0x18001fe0a  jnz     short loc_18001FE0E
0x18001fe0c  xor     edi, edi
0x18001fe0e  and     eax, 0FFFFFFFEh
0x18001fe11  or      eax, edi
0x18001fe13  mov     [rbx], eax
0x18001fe15  mov     rax, rbx
0x18001fe18  mov     rbx, [rsp+58h+arg_10]
0x18001fe1d  add     rsp, 40h
0x18001fe21  pop     rdi
0x18001fe22  pop     rsi
0x18001fe23  pop     rbp
0x18001fe24  retn
```

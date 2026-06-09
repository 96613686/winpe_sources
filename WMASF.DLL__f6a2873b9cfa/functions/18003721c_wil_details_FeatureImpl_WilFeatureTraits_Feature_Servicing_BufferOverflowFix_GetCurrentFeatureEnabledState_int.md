# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18003721c`
- end: `0x1800372db`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BufferOverflowFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18003649c`

## callees

- `0x18003721c`
- `0x18003bc40`
- `0x18003bec4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BufferOverflowFix>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v6; // edx
  int v7; // r8d
  int v8; // eax
  unsigned int v9; // r8d
  int v10; // edi
  char v11; // si
  char IsEnabled; // al
  _QWORD *result; // rax

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x37EA6FE, (unsigned int)a2, a3, a4);
  *a2 = 0;
  v6 = FeatureEnabledState & 0xFFFFFF3F;
  v7 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
  if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
  {
    v8 = 0;
    if ( v6 == 2 )
      v8 = 64;
  }
  else
  {
    v8 = 64;
  }
  v9 = v8 | v7;
  v10 = 1;
  *(_DWORD *)a2 = v9;
  if ( (v9 & 0x400) != 0 && v9 >= 0x800 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    IsEnabled = 0;
    if ( (v9 & 0x40) == 0 )
      goto LABEL_12;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl'::`2'::impl);
  if ( v11 && !IsEnabled )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_12:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !IsEnabled )
    v10 = 0;
  result = a2;
  *(_DWORD *)a2 = v10 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return result;
}

```

## disassembly

```asm
0x18003721c  push    rbx
0x18003721e  push    rbp
0x18003721f  push    rsi
0x180037220  push    rdi
0x180037221  sub     rsp, 28h
0x180037225  mov     ecx, 37EA6FEh; this
0x18003722a  mov     rbx, rdx
0x18003722d  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180037232  mov     edx, eax
0x180037234  mov     qword ptr [rbx], 0
0x18003723b  and     edx, 0FFFFFF3Fh
0x180037241  mov     ecx, eax
0x180037243  and     eax, 80h
0x180037248  mov     r8d, edx
0x18003724b  and     r8d, 3
0x18003724f  mov     ebp, 40h ; '@'
0x180037254  shl     r8d, 2
0x180037258  and     ecx, ebp
0x18003725a  or      r8d, ecx
0x18003725d  shl     r8d, 2
0x180037261  or      r8d, eax
0x180037264  shl     r8d, 3
0x180037268  test    edx, edx
0x18003726a  jnz     short loc_180037270
0x18003726c  mov     eax, ebp
0x18003726e  jmp     short loc_180037278
0x180037270  xor     eax, eax
0x180037272  cmp     edx, 2
0x180037275  cmovz   eax, ebp
0x180037278  or      r8d, eax
0x18003727b  mov     edi, 1
0x180037280  mov     [rbx], r8d
0x180037283  bt      r8d, 0Ah
0x180037288  jnb     short loc_180037298
0x18003728a  cmp     r8d, 800h
0x180037291  jb      short loc_180037298
0x180037293  mov     sil, dil
0x180037296  jmp     short loc_1800372A2
0x180037298  xor     sil, sil
0x18003729b  xor     al, al
0x18003729d  test    bpl, r8b
0x1800372a0  jz      short loc_1800372BB
0x1800372a2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ten2Loc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc> `wil::Feature<__WilFeatureTraits_Feature_Ten2Loc>::GetImpl(void)'::`2'::impl
0x1800372a9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::__private_IsEnabled(wil::ReportingKind)
0x1800372ae  test    sil, sil
0x1800372b1  jz      short loc_1800372BB
0x1800372b3  test    al, al
0x1800372b5  jnz     short loc_1800372BB
0x1800372b7  btr     dword ptr [rbx], 0Ah
0x1800372bb  mov     ecx, [rbx]
0x1800372bd  test    bpl, cl
0x1800372c0  jz      short loc_1800372C6
0x1800372c2  test    al, al
0x1800372c4  jnz     short loc_1800372C8
0x1800372c6  xor     edi, edi
0x1800372c8  and     ecx, 0FFFFFFFEh
0x1800372cb  mov     rax, rbx
0x1800372ce  or      ecx, edi
0x1800372d0  mov     [rbx], ecx
0x1800372d2  add     rsp, 28h
0x1800372d6  pop     rdi
0x1800372d7  pop     rsi
0x1800372d8  pop     rbp
0x1800372d9  pop     rbx
0x1800372da  retn
```

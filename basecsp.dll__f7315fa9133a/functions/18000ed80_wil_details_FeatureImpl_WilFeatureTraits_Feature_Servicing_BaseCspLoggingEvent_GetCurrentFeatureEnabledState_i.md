# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::GetCurrentFeatureEnabledState(int *)

- ea: `0x18000ed80`
- end: `0x18000ee44`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000df60`

## callees

- `0x18000ed80`
- `0x180017994`
- `0x18001875c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::GetCurrentFeatureEnabledState(
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

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x39AF3FF, 3u, a3, a4);
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
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl'::`2'::impl);
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
0x18000ed80  push    rbx
0x18000ed82  push    rbp
0x18000ed83  push    rsi
0x18000ed84  push    rdi
0x18000ed85  sub     rsp, 28h
0x18000ed89  mov     rbx, rdx
0x18000ed8c  mov     ecx, 39AF3FFh; this
0x18000ed91  mov     edx, 3; unsigned int
0x18000ed96  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x18000ed9b  mov     edx, eax
0x18000ed9d  mov     qword ptr [rbx], 0
0x18000eda4  and     edx, 0FFFFFF3Fh
0x18000edaa  mov     ecx, eax
0x18000edac  and     eax, 80h
0x18000edb1  mov     r8d, edx
0x18000edb4  and     r8d, 3
0x18000edb8  mov     ebp, 40h ; '@'
0x18000edbd  shl     r8d, 2
0x18000edc1  and     ecx, ebp
0x18000edc3  or      r8d, ecx
0x18000edc6  shl     r8d, 2
0x18000edca  or      r8d, eax
0x18000edcd  shl     r8d, 3
0x18000edd1  test    edx, edx
0x18000edd3  jnz     short loc_18000EDD9
0x18000edd5  mov     eax, ebp
0x18000edd7  jmp     short loc_18000EDE1
0x18000edd9  xor     eax, eax
0x18000eddb  cmp     edx, 2
0x18000edde  cmovz   eax, ebp
0x18000ede1  or      r8d, eax
0x18000ede4  mov     edi, 1
0x18000ede9  mov     [rbx], r8d
0x18000edec  bt      r8d, 0Ah
0x18000edf1  jnb     short loc_18000EE01
0x18000edf3  cmp     r8d, 800h
0x18000edfa  jb      short loc_18000EE01
0x18000edfc  mov     sil, dil
0x18000edff  jmp     short loc_18000EE0B
0x18000ee01  xor     sil, sil
0x18000ee04  xor     al, al
0x18000ee06  test    bpl, r8b
0x18000ee09  jz      short loc_18000EE24
0x18000ee0b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestUex12@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12> `wil::Feature<__WilFeatureTraits_Feature_TestUex12>::GetImpl(void)'::`2'::impl
0x18000ee12  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestUex12@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestUex12>::__private_IsEnabled(wil::ReportingKind)
0x18000ee17  test    sil, sil
0x18000ee1a  jz      short loc_18000EE24
0x18000ee1c  test    al, al
0x18000ee1e  jnz     short loc_18000EE24
0x18000ee20  btr     dword ptr [rbx], 0Ah
0x18000ee24  mov     ecx, [rbx]
0x18000ee26  test    bpl, cl
0x18000ee29  jz      short loc_18000EE2F
0x18000ee2b  test    al, al
0x18000ee2d  jnz     short loc_18000EE31
0x18000ee2f  xor     edi, edi
0x18000ee31  and     ecx, 0FFFFFFFEh
0x18000ee34  mov     rax, rbx
0x18000ee37  or      ecx, edi
0x18000ee39  mov     [rbx], ecx
0x18000ee3b  add     rsp, 28h
0x18000ee3f  pop     rdi
0x18000ee40  pop     rsi
0x18000ee41  pop     rbp
0x18000ee42  pop     rbx
0x18000ee43  retn
```

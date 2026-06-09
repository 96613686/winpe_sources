# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)

- ea: `0x14000c6f8`
- end: `0x14000c7db`
- name: `?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z`
- size: `227`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000bd88`

## callees

- `0x14000c6f8`
- `0x14000fe94`
- `0x140011454`
- `0x140011c18`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(
        __int64 a1,
        _QWORD *a2,
        enum FEATURE_CHANGE_TIME a3,
        int *a4)
{
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  int v9; // edi
  int v10; // eax
  unsigned int v11; // r8d
  char v12; // si
  char v13; // cl

  FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState((wil::details *)0x38419CA, 3u, a3, a4);
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
  if ( (v11 & 0x400) != 0 && v11 >= 0x800 )
  {
    v12 = 1;
  }
  else
  {
    v12 = 0;
    v13 = 0;
    if ( (v11 & 0x40) == 0 )
      goto LABEL_16;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl'::`2'::impl) )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(`wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl'::`2'::impl);
    v13 = 1;
  }
  else
  {
    v13 = 0;
  }
  if ( v12 && !v13 )
    *(_DWORD *)a2 &= ~0x400u;
LABEL_16:
  if ( (*(_DWORD *)a2 & 0x40) == 0 || !v13 )
    v9 = 0;
  *(_DWORD *)a2 = v9 | *(_DWORD *)a2 & 0xFFFFFFFE;
  return a2;
}

```

## disassembly

```asm
0x14000c6f8  push    rbx
0x14000c6fa  push    rbp
0x14000c6fb  push    rsi
0x14000c6fc  push    rdi
0x14000c6fd  sub     rsp, 28h
0x14000c701  mov     rbx, rdx
0x14000c704  mov     ecx, 38419CAh; this
0x14000c709  mov     edx, 3; unsigned int
0x14000c70e  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x14000c713  mov     edx, eax
0x14000c715  mov     qword ptr [rbx], 0
0x14000c71c  and     edx, 0FFFFFF3Fh
0x14000c722  mov     ecx, eax
0x14000c724  and     eax, 80h
0x14000c729  mov     r8d, edx
0x14000c72c  and     r8d, 3
0x14000c730  mov     ebp, 40h ; '@'
0x14000c735  shl     r8d, 2
0x14000c739  and     ecx, ebp
0x14000c73b  or      r8d, ecx
0x14000c73e  shl     r8d, 2
0x14000c742  or      r8d, eax
0x14000c745  shl     r8d, 3
0x14000c749  test    edx, edx
0x14000c74b  jnz     short loc_14000C753
0x14000c74d  mov     ecx, ebp
0x14000c74f  mov     edx, ebp
0x14000c751  jmp     short loc_14000C75D
0x14000c753  xor     ecx, ecx
0x14000c755  cmp     edx, 2
0x14000c758  cmovz   ecx, ebp
0x14000c75b  mov     edx, ecx
0x14000c75d  mov     eax, r8d
0x14000c760  mov     edi, 1
0x14000c765  or      eax, edx
0x14000c767  or      r8d, ecx
0x14000c76a  mov     [rbx], eax
0x14000c76c  bt      r8d, 0Ah
0x14000c771  jnb     short loc_14000C781
0x14000c773  cmp     r8d, 800h
0x14000c77a  jb      short loc_14000C781
0x14000c77c  mov     sil, dil
0x14000c77f  jmp     short loc_14000C78B
0x14000c781  xor     sil, sil
0x14000c784  xor     cl, cl
0x14000c786  test    bpl, r8b
0x14000c789  jz      short loc_14000C7BB
0x14000c78b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TestLoc1Perf@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf> `wil::Feature<__WilFeatureTraits_Feature_TestLoc1Perf>::GetImpl(void)'::`2'::impl
0x14000c792  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::__private_IsEnabled(wil::ReportingKind)
0x14000c797  test    al, al
0x14000c799  jz      short loc_14000C7AC
0x14000c79b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec> `wil::Feature<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetImpl(void)'::`2'::impl
0x14000c7a2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14000c7a7  mov     cl, dil
0x14000c7aa  jmp     short loc_14000C7AE
0x14000c7ac  xor     cl, cl
0x14000c7ae  test    sil, sil
0x14000c7b1  jz      short loc_14000C7BB
0x14000c7b3  test    cl, cl
0x14000c7b5  jnz     short loc_14000C7BB
0x14000c7b7  btr     dword ptr [rbx], 0Ah
0x14000c7bb  mov     eax, [rbx]
0x14000c7bd  test    bpl, al
0x14000c7c0  jz      short loc_14000C7C6
0x14000c7c2  test    cl, cl
0x14000c7c4  jnz     short loc_14000C7C8
0x14000c7c6  xor     edi, edi
0x14000c7c8  and     eax, 0FFFFFFFEh
0x14000c7cb  or      eax, edi
0x14000c7cd  mov     [rbx], eax
0x14000c7cf  mov     rax, rbx
0x14000c7d2  add     rsp, 28h
0x14000c7d6  pop     rdi
0x14000c7d7  pop     rsi
0x14000c7d8  pop     rbp
0x14000c7d9  pop     rbx
0x14000c7da  retn
```

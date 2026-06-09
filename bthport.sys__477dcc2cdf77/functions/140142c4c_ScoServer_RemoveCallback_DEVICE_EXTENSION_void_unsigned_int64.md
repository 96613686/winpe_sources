# ScoServer_RemoveCallback(DEVICE_EXTENSION *,void *,unsigned __int64)

- ea: `0x140142c4c`
- end: `0x140143072`
- name: `?ScoServer_RemoveCallback@@YAJPEAUDEVICE_EXTENSION@@PEAX_K@Z`
- size: `1062`
- prototype: `int(struct DEVICE_EXTENSION *, void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140143178`

## callees

- `0x140005608`
- `0x140005b4c`
- `0x14000bdb8`
- `0x14000e39c`
- `0x1400266f4`
- `0x140142ba4`
- `0x140142c4c`
- `0x140143078`
- `0x140165580`
- `0x140165940`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140142fcc`
- `ntoskrnl!ObfDereferenceObject` at `0x140142fcc`
- `ntoskrnl!RtlRbRemoveNode` at `0x140142ee4`
- `ntoskrnl!RtlRbRemoveNode` at `0x140142ee4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140142dd2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140142dd2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140142f59`
- `ntoskrnl!KeReleaseSpinLock` at `0x140142f59`

## pseudocode

```c
__int64 __fastcall ScoServer_RemoveCallback(
        struct DEVICE_EXTENSION *a1,
        $4863FEEAC76D187EF6BF20EA3B69A2F3 *a2,
        __int64 a3)
{
  int v6; // edx
  int v7; // r8d
  char v8; // di
  __int16 DeviceType; // ax
  unsigned int v10; // r15d
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // r9
  int v13; // edx
  int v14; // r8d
  PDEVICE_OBJECT v15; // rcx
  char *v16; // rsi
  KIRQL v17; // al
  _RTL_RB_TREE *p_ScoRbTree; // r14
  unsigned __int64 Root; // rbx
  int v20; // ebp
  int v21; // eax
  int v22; // edx
  unsigned __int64 v23; // rax
  int v24; // r8d
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r9
  int v27; // edx
  int v28; // r8d
  void *v29; // rbx
  __int16 v30; // ax
  __int16 v32; // [rsp+30h] [rbp-108h]
  __int128 v33; // [rsp+60h] [rbp-D8h] BYREF
  __int64 v34; // [rsp+70h] [rbp-C8h]
  _QWORD v35[23]; // [rsp+80h] [rbp-B8h] BYREF
  KIRQL NewIrql; // [rsp+148h] [rbp+10h]
  unsigned __int64 *SpinLock; // [rsp+158h] [rbp+20h]

  v34 = 0;
  v33 = 0;
  memset(v35, 0, 0x80u);
  v8 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v6) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    LOBYTE(v6) = 0;
  DeviceType = WPP_GLOBAL_Control->DeviceType;
  if ( (_BYTE)v6 || DeviceType )
  {
    LOBYTE(v7) = DeviceType != 0;
    WPP_RECORDER_AND_TRACE_SF_qLL(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v7,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      4,
      13,
      (__int64)WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids,
      (char)a2,
      SBYTE4(a3),
      a3);
  }
  if ( !a2 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v6) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v6) = 0;
    LOBYTE(v7) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v7,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      14,
      (__int64)WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids);
    v10 = -1073741811;
    BthVerif_BugCheckIfVerifierOn(9u, 0, v11, v12);
    goto LABEL_48;
  }
  if ( !a3 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v6) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v6) = 0;
    v32 = 15;
LABEL_17:
    LOBYTE(v7) = 1;
    WPP_RECORDER_AND_TRACE_SF_(
      v15->AttachedDevice,
      v6,
      v7,
      v15->DeviceExtension,
      2,
      4,
      v32,
      (__int64)WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids);
    v10 = -1073741811;
    goto LABEL_48;
  }
  v10 = 0;
  SpinLock = &a1->AllChildPdoLock;
  v16 = 0;
  v17 = KeAcquireSpinLockRaiseToDpc(&a1->AllChildPdoLock);
  p_ScoRbTree = &a1->ScoRbTree;
  v35[10] = a3;
  NewIrql = v17;
  Root = (unsigned __int64)p_ScoRbTree->Root;
  if ( (*(_BYTE *)&p_ScoRbTree->0 & 1) != 0 )
  {
    if ( !Root )
      goto LABEL_41;
    Root ^= (unsigned __int64)p_ScoRbTree;
  }
  v20 = *(_BYTE *)&p_ScoRbTree->0 & 1;
  if ( Root )
  {
    do
    {
      v21 = ScoServer_NodeCompare(v35, (struct _RTL_BALANCED_NODE *)Root);
      if ( v21 >= 0 )
      {
        if ( v21 <= 0 )
          break;
        v23 = *(_QWORD *)(Root + 8);
      }
      else
      {
        v23 = *(_QWORD *)Root;
      }
      if ( v20 && v23 )
        Root ^= v23;
      else
        Root = v23;
    }
    while ( Root );
    if ( Root )
    {
      v16 = (char *)(Root - 104);
      if ( ($4863FEEAC76D187EF6BF20EA3B69A2F3 *)(Root - 104) == a2 )
      {
        RtlRbRemoveNode(p_ScoRbTree, Root);
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v27) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
          LOBYTE(v27) = 0;
        LOBYTE(v28) = 1;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v27,
          v28,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          17,
          (__int64)WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids,
          v16);
      }
      else
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v22) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v22) = 0;
        v24 = WORD2(a3);
        LOBYTE(v24) = 1;
        WPP_RECORDER_AND_TRACE_SF_qLL(
          WPP_GLOBAL_Control->AttachedDevice,
          v22,
          v24,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          16,
          (__int64)WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids,
          (char)a2,
          SBYTE4(a3),
          a3);
        v10 = -1073741811;
        BthVerif_BugCheckIfVerifierOn(9u, (ULONG_PTR)a2, v25, v26);
        v16 = 0;
      }
    }
  }
LABEL_41:
  KeReleaseSpinLock(SpinLock, NewIrql);
  if ( !v16 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v6) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v6) = 0;
    v32 = 18;
    goto LABEL_17;
  }
  v34 = 0;
  v33 = 0;
  (*((void (__fastcall **)(_QWORD, __int64, __int128 *))v16 + 4))(*((_QWORD *)v16 + 5), 1, &v33);
  v29 = (void *)*((_QWORD *)v16 + 6);
  ScoServer_SynchFreeInfo(v16);
  if ( v29 )
    ObfDereferenceObject(v29);
LABEL_48:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    v8 = 0;
  v30 = WPP_GLOBAL_Control->DeviceType;
  if ( v8 || v30 )
  {
    LOBYTE(v13) = v8;
    LOBYTE(v14) = v30 != 0;
    WPP_RECORDER_AND_TRACE_SF_qLdL(
      WPP_GLOBAL_Control->AttachedDevice,
      v13,
      v14,
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      4,
      19,
      (__int64)WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids,
      (char)a2,
      SBYTE4(a3),
      a3,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x140142c4c  mov     [rsp+arg_0], rbx
0x140142c51  push    rbp
0x140142c52  push    rsi
0x140142c53  push    rdi
0x140142c54  push    r12
0x140142c56  push    r13
0x140142c58  push    r14
0x140142c5a  push    r15
0x140142c5c  sub     rsp, 100h
0x140142c63  mov     r12, r8
0x140142c66  mov     r13, rdx
0x140142c69  mov     r14, rcx
0x140142c6c  xorps   xmm0, xmm0
0x140142c6f  xor     eax, eax
0x140142c71  lea     rcx, [rsp+138h+var_B8]; void *
0x140142c79  xor     edx, edx; Val
0x140142c7b  mov     [rsp+138h+var_C8], rax
0x140142c80  mov     r8d, 80h; Size
0x140142c86  movups  [rsp+138h+var_D8], xmm0
0x140142c8b  call    memset
0x140142c90  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140142c97  xor     ebp, ebp
0x140142c99  mov     eax, [rcx+2Ch]
0x140142c9c  lea     edi, [rbp+1]
0x140142c9f  test    al, 8
0x140142ca1  jz      short loc_140142CAC
0x140142ca3  cmp     byte ptr [rcx+29h], 5
0x140142ca7  mov     dl, dil
0x140142caa  jnb     short loc_140142CAF
0x140142cac  mov     dl, bpl
0x140142caf  movzx   eax, word ptr [rcx+48h]
0x140142cb3  lea     rbx, WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids
0x140142cba  test    ax, ax
0x140142cbd  setnz   r8b
0x140142cc1  test    dl, dl
0x140142cc3  jnz     short loc_140142CCA
0x140142cc5  test    ax, ax
0x140142cc8  jz      short loc_140142D0A
0x140142cca  mov     [rsp+138h+var_E8], r12d
0x140142ccf  mov     rax, r12
0x140142cd2  shr     rax, 20h
0x140142cd6  movzx   r9d, ax
0x140142cda  mov     [rsp+138h+var_F0], r9d
0x140142cdf  mov     r9, [rcx+40h]
0x140142ce3  mov     rcx, [rcx+18h]
0x140142ce7  mov     [rsp+138h+var_F8], r13
0x140142cec  mov     [rsp+138h+var_100], rbx
0x140142cf1  mov     [rsp+138h+var_108], 0Dh
0x140142cf8  mov     [rsp+138h+var_110], 4
0x140142d00  mov     [rsp+138h+var_118], 5
0x140142d05  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x140142d0a  test    r13, r13
0x140142d0d  jnz     short loc_140142D67
0x140142d0f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140142d16  mov     eax, [rcx+2Ch]
0x140142d19  test    al, 8
0x140142d1b  jz      short loc_140142D26
0x140142d1d  cmp     byte ptr [rcx+29h], 2
0x140142d21  mov     dl, dil
0x140142d24  jnb     short loc_140142D29
0x140142d26  mov     dl, bpl
0x140142d29  mov     r9, [rcx+40h]
0x140142d2d  mov     r8b, dil
0x140142d30  mov     rcx, [rcx+18h]
0x140142d34  mov     [rsp+138h+var_100], rbx
0x140142d39  mov     [rsp+138h+var_108], 0Eh
0x140142d40  mov     [rsp+138h+var_110], 4
0x140142d48  mov     [rsp+138h+var_118], 2
0x140142d4d  call    WPP_RECORDER_AND_TRACE_SF_
0x140142d52  xor     edx, edx; BugCheckParameter2
0x140142d54  mov     r15d, 0C000000Dh
0x140142d5a  lea     ecx, [rdx+9]; BugCheckParameter1
0x140142d5d  call    ?BthVerif_BugCheckIfVerifierOn@@YAXK_K00@Z; BthVerif_BugCheckIfVerifierOn(ulong,unsigned __int64,unsigned __int64,unsigned __int64)
0x140142d62  jmp     loc_140142FDF
0x140142d67  test    r12, r12
0x140142d6a  jnz     short loc_140142DBA
0x140142d6c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140142d73  mov     eax, [rcx+2Ch]
0x140142d76  test    al, 8
0x140142d78  jz      short loc_140142D83
0x140142d7a  cmp     byte ptr [rcx+29h], 2
0x140142d7e  mov     dl, dil
0x140142d81  jnb     short loc_140142D86
0x140142d83  mov     dl, bpl
0x140142d86  mov     [rsp+138h+var_100], rbx
0x140142d8b  mov     [rsp+138h+var_108], 0Fh
0x140142d92  mov     r9, [rcx+40h]
0x140142d96  mov     r8b, dil
0x140142d99  mov     rcx, [rcx+18h]
0x140142d9d  mov     [rsp+138h+var_110], 4
0x140142da5  mov     [rsp+138h+var_118], 2
0x140142daa  call    WPP_RECORDER_AND_TRACE_SF_
0x140142daf  mov     r15d, 0C000000Dh
0x140142db5  jmp     loc_140142FDF
0x140142dba  lea     rax, [r14+110h]
0x140142dc1  mov     r15d, ebp
0x140142dc4  mov     rcx, rax; SpinLock
0x140142dc7  mov     [rsp+138h+SpinLock], rax
0x140142dcf  mov     rsi, rbp
0x140142dd2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140142dd9  nop     dword ptr [rax+rax+00h]
0x140142dde  add     r14, 0F0h
0x140142de5  mov     [rsp+138h+var_68], r12
0x140142ded  mov     [rsp+138h+NewIrql], al
0x140142df4  mov     rbx, [r14]
0x140142df7  test    [r14+8], dil
0x140142dfb  jz      short loc_140142E09
0x140142dfd  test    rbx, rbx
0x140142e00  jz      loc_140142F43
0x140142e06  xor     rbx, r14
0x140142e09  movzx   ebp, byte ptr [r14+8]
0x140142e0e  and     ebp, edi
0x140142e10  test    rbx, rbx
0x140142e13  jz      loc_140142F41
0x140142e19  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x140142e1c  lea     rcx, [rsp+138h+var_B8]; void *
0x140142e24  call    ?ScoServer_NodeCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; ScoServer_NodeCompare(void *,_RTL_BALANCED_NODE *)
0x140142e29  test    eax, eax
0x140142e2b  jns     short loc_140142E32
0x140142e2d  mov     rax, [rbx]
0x140142e30  jmp     short loc_140142E38
0x140142e32  jle     short loc_140142E4E
0x140142e34  mov     rax, [rbx+8]
0x140142e38  test    ebp, ebp
0x140142e3a  jz      short loc_140142E46
0x140142e3c  test    rax, rax
0x140142e3f  jz      short loc_140142E46
0x140142e41  xor     rbx, rax
0x140142e44  jmp     short loc_140142E49
0x140142e46  mov     rbx, rax
0x140142e49  test    rbx, rbx
0x140142e4c  jnz     short loc_140142E19
0x140142e4e  xor     ebp, ebp
0x140142e50  test    rbx, rbx
0x140142e53  jz      loc_140142F43
0x140142e59  lea     rsi, [rbx-68h]
0x140142e5d  cmp     rsi, r13
0x140142e60  jz      short loc_140142EDE
0x140142e62  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140142e69  mov     eax, [rcx+2Ch]
0x140142e6c  test    al, 8
0x140142e6e  jz      short loc_140142E79
0x140142e70  cmp     byte ptr [rcx+29h], 2
0x140142e74  mov     dl, dil
0x140142e77  jnb     short loc_140142E7C
0x140142e79  mov     dl, bpl
0x140142e7c  mov     r9, [rcx+40h]
0x140142e80  lea     rbx, WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids
0x140142e87  mov     rcx, [rcx+18h]
0x140142e8b  mov     rax, r12
0x140142e8e  mov     [rsp+138h+var_E8], r12d
0x140142e93  shr     rax, 20h
0x140142e97  movzx   r8d, ax
0x140142e9b  mov     [rsp+138h+var_F0], r8d
0x140142ea0  mov     r8b, dil
0x140142ea3  mov     [rsp+138h+var_F8], r13
0x140142ea8  mov     [rsp+138h+var_100], rbx
0x140142ead  mov     [rsp+138h+var_108], 10h
0x140142eb4  mov     [rsp+138h+var_110], 4
0x140142ebc  mov     [rsp+138h+var_118], 2
0x140142ec1  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x140142ec6  mov     rdx, r13; BugCheckParameter2
0x140142ec9  mov     ecx, 9; BugCheckParameter1
0x140142ece  mov     r15d, 0C000000Dh
0x140142ed4  call    ?BthVerif_BugCheckIfVerifierOn@@YAXK_K00@Z; BthVerif_BugCheckIfVerifierOn(ulong,unsigned __int64,unsigned __int64,unsigned __int64)
0x140142ed9  mov     rsi, rbp
0x140142edc  jmp     short loc_140142F4A
0x140142ede  mov     rdx, rbx
0x140142ee1  mov     rcx, r14
0x140142ee4  call    cs:__imp_RtlRbRemoveNode
0x140142eeb  nop     dword ptr [rax+rax+00h]
0x140142ef0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140142ef7  mov     eax, [rcx+2Ch]
0x140142efa  test    al, 8
0x140142efc  jz      short loc_140142F07
0x140142efe  cmp     byte ptr [rcx+29h], 4
0x140142f02  mov     dl, dil
0x140142f05  jnb     short loc_140142F0A
0x140142f07  mov     dl, bpl
0x140142f0a  mov     r9, [rcx+40h]
0x140142f0e  lea     rbx, WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids
0x140142f15  mov     rcx, [rcx+18h]
0x140142f19  mov     r8b, dil
0x140142f1c  mov     [rsp+138h+var_F8], rsi
0x140142f21  mov     [rsp+138h+var_100], rbx
0x140142f26  mov     [rsp+138h+var_108], 11h
0x140142f2d  mov     [rsp+138h+var_110], 4
0x140142f35  mov     [rsp+138h+var_118], 4
0x140142f3a  call    WPP_RECORDER_AND_TRACE_SF_q
0x140142f3f  jmp     short loc_140142F4A
0x140142f41  xor     ebp, ebp
0x140142f43  lea     rbx, WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids
0x140142f4a  mov     dl, [rsp+138h+NewIrql]; NewIrql
0x140142f51  mov     rcx, [rsp+138h+SpinLock]; SpinLock
0x140142f59  call    cs:__imp_KeReleaseSpinLock
0x140142f60  nop     dword ptr [rax+rax+00h]
0x140142f65  test    rsi, rsi
0x140142f68  jnz     short loc_140142F95
0x140142f6a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140142f71  mov     eax, [rcx+2Ch]
0x140142f74  test    al, 8
0x140142f76  jz      short loc_140142F81
0x140142f78  cmp     byte ptr [rcx+29h], 2
0x140142f7c  mov     dl, dil
0x140142f7f  jnb     short loc_140142F84
0x140142f81  mov     dl, bpl
0x140142f84  mov     [rsp+138h+var_100], rbx
0x140142f89  mov     [rsp+138h+var_108], 12h
0x140142f90  jmp     loc_140142D92
0x140142f95  xor     eax, eax
0x140142f97  lea     r8, [rsp+138h+var_D8]
0x140142f9c  mov     [rsp+138h+var_C8], rax
0x140142fa1  xorps   xmm0, xmm0
0x140142fa4  movups  [rsp+138h+var_D8], xmm0
0x140142fa9  mov     rax, [rsi+20h]
0x140142fad  mov     edx, edi
0x140142faf  mov     rcx, [rsi+28h]
0x140142fb3  call    _guard_dispatch_icall
0x140142fb8  mov     rbx, [rsi+30h]
0x140142fbc  mov     rcx, rsi; P
0x140142fbf  call    ?ScoServer_SynchFreeInfo@@YAXPEAU_SCO_SERVER_INFO@@@Z; ScoServer_SynchFreeInfo(_SCO_SERVER_INFO *)
0x140142fc4  test    rbx, rbx
0x140142fc7  jz      short loc_140142FD8
0x140142fc9  mov     rcx, rbx; Object
0x140142fcc  call    cs:__imp_ObfDereferenceObject
0x140142fd3  nop     dword ptr [rax+rax+00h]
0x140142fd8  lea     rbx, WPP_7c6dd03ac08a37dbf42aef9cb2166acd_Traceguids
0x140142fdf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140142fe6  mov     eax, [rcx+2Ch]
0x140142fe9  test    al, 8
0x140142feb  jz      short loc_140142FF3
0x140142fed  cmp     byte ptr [rcx+29h], 5
0x140142ff1  jnb     short loc_140142FF6
0x140142ff3  mov     dil, bpl
0x140142ff6  movzx   eax, word ptr [rcx+48h]
0x140142ffa  test    ax, ax
0x140142ffd  setnz   r8b
0x140143001  test    dil, dil
0x140143004  jnz     short loc_14014300B
0x140143006  test    ax, ax
0x140143009  jz      short loc_140143053
0x14014300b  mov     [rsp+138h+var_E0], r15d
0x140143010  mov     rax, r12
0x140143013  mov     [rsp+138h+var_E8], r12d
0x140143018  mov     dl, dil
0x14014301b  shr     rax, 20h
0x14014301f  movzx   r9d, ax
0x140143023  mov     [rsp+138h+var_F0], r9d
0x140143028  mov     r9, [rcx+40h]
0x14014302c  mov     rcx, [rcx+18h]
0x140143030  mov     [rsp+138h+var_F8], r13
0x140143035  mov     [rsp+138h+var_100], rbx
0x14014303a  mov     [rsp+138h+var_108], 13h
0x140143041  mov     [rsp+138h+var_110], 4
0x140143049  mov     [rsp+138h+var_118], 5
0x14014304e  call    WPP_RECORDER_AND_TRACE_SF_qLdL
0x140143053  mov     rbx, [rsp+138h+arg_0]
0x14014305b  mov     eax, r15d
0x14014305e  add     rsp, 100h
0x140143065  pop     r15
0x140143067  pop     r14
0x140143069  pop     r13
0x14014306b  pop     r12
0x14014306d  pop     rdi
0x14014306e  pop     rsi
0x14014306f  pop     rbp
0x140143070  retn
```

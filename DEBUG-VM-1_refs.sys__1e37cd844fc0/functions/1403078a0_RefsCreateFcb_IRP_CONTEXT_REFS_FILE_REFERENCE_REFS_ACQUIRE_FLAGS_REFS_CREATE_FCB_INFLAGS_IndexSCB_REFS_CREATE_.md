# RefsCreateFcb(_IRP_CONTEXT *,_REFS_FILE_REFERENCE,_REFS_ACQUIRE_FLAGS,_REFS_CREATE_FCB_INFLAGS,IndexSCB *,_REFS_CREATE_FCB_OUTFLAGS *)

- ea: `0x1403078a0`
- end: `0x140307daa`
- name: `?RefsCreateFcb@@YAPEAU_FCB@@PEAU_IRP_CONTEXT@@U_REFS_FILE_REFERENCE@@W4_REFS_ACQUIRE_FLAGS@@W4_REFS_CREATE_FCB_INFLAGS@@PEAUIndexSCB@@PEAW4_REFS_CREATE_FCB_OUTFLAGS@@@Z`
- size: `1290`
- prototype: ``
- caller_count: `15`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400d63f4`
- `0x1400daa80`
- `0x1401005bc`
- `0x140103530`
- `0x140297d70`
- `0x1402986f0`
- `0x14029a0bc`
- `0x14029bf9c`
- `0x1402aa38c`
- `0x1402cc968`
- `0x1402fbbf8`
- `0x140306d6c`
- `0x140307728`
- `0x140307db0`
- `0x14033c460`

## callees

- `0x14004ffc0`
- `0x140075ae0`
- `0x140076ad0`
- `0x1400862c0`
- `0x1400873b0`
- `0x140088960`
- `0x14009f9b0`
- `0x1400d0fd8`
- `0x14028d7ec`
- `0x1403078a0`
- `0x140327c50`

## import_xrefs

- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14030793d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140307c3f`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403420f0`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x14030793d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140307c3f`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403420f0`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140307a23`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140307a43`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140307a23`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140307a43`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140307afc`
- `ntoskrnl!RtlAvlInsertNodeEx` at `0x140307afc`
- `ntoskrnl!ExReleaseFastResource` at `0x140307be1`
- `ntoskrnl!ExReleaseFastResource` at `0x140307c5c`
- `ntoskrnl!ExReleaseFastResource` at `0x140307c89`
- `ntoskrnl!ExReleaseFastResource` at `0x140307ca7`
- `ntoskrnl!ExReleaseFastResource` at `0x1403420b4`
- `ntoskrnl!ExReleaseFastResource` at `0x14034210d`
- `ntoskrnl!ExReleaseFastResource` at `0x14034213e`
- `ntoskrnl!ExReleaseFastResource` at `0x140307be1`
- `ntoskrnl!ExReleaseFastResource` at `0x140307c5c`
- `ntoskrnl!ExReleaseFastResource` at `0x140307c89`
- `ntoskrnl!ExReleaseFastResource` at `0x140307ca7`
- `ntoskrnl!ExReleaseFastResource` at `0x1403420b4`
- `ntoskrnl!ExReleaseFastResource` at `0x14034210d`
- `ntoskrnl!ExReleaseFastResource` at `0x14034213e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034209a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034209a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1403079d2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1403079d2`

## pseudocode

```c
_FCB *__fastcall RefsCreateFcb(struct _IRP_CONTEXT *a1, __int64 a2, __int64 a3, char a4, struct _SRV_OPEN *a5, int *a6)
{
  struct _VCB *v8; // rdi
  char v9; // si
  int *v10; // r15
  _FCB *PoolWithTag; // rbx
  _QWORD *v12; // rdi
  char v13; // r12
  int v14; // eax
  _QWORD *v15; // rax
  __int64 v16; // r12
  unsigned int v17; // r8d
  __int64 v18; // rsi
  _FCB *v19; // rax
  unsigned __int64 v20; // r8
  struct _VCB *v21; // r12
  unsigned int v22; // r8d
  __int64 NonpagedFcb; // r9
  unsigned __int64 v24; // rdx
  char v25; // r8
  char v26; // di
  __int64 v27; // r9
  char v28; // al
  _QWORD *v29; // r13
  __int64 v30; // r9
  unsigned __int8 v32; // [rsp+31h] [rbp-97h]
  unsigned __int8 v33; // [rsp+32h] [rbp-96h]
  int v35; // [rsp+38h] [rbp-90h]
  _QWORD *v36; // [rsp+48h] [rbp-80h]
  int v37; // [rsp+60h] [rbp-68h] BYREF
  struct _VCB *v38; // [rsp+68h] [rbp-60h]
  __int64 v39; // [rsp+70h] [rbp-58h]
  struct _VCB *v40; // [rsp+78h] [rbp-50h]
  int *v41; // [rsp+80h] [rbp-48h]

  v35 = a3;
  v8 = (struct _VCB *)*((_QWORD *)a1 + 8);
  v38 = v8;
  v40 = v8;
  v37 = 0;
  v9 = 0;
  v39 = 0;
  if ( *(_QWORD *)a2 || (v32 = 1, !*(_QWORD *)(a2 + 8)) )
    v32 = 0;
  v10 = &v37;
  if ( a6 )
    v10 = a6;
  v41 = v10;
  *v10 = 0;
  PoolWithTag = 0;
  v36 = (_QWORD *)((char *)v8 + 624);
  LOBYTE(a3) = 1;
  ExAcquireFastResourceExclusive((char *)v8 + 624, 0, a3);
  v12 = (_QWORD *)*((_QWORD *)v8 + 104);
  v33 = 0;
  v13 = 0;
  if ( v12 )
  {
    while ( 1 )
    {
      v14 = RefsFcbTableCompare(a2, v12);
      if ( v14 <= 0 )
      {
        if ( v14 >= 0 )
        {
          v13 = 1;
          break;
        }
        v15 = (_QWORD *)*v12;
        if ( !*v12 )
        {
          v33 = 0;
          break;
        }
      }
      else
      {
        v15 = (_QWORD *)v12[1];
        if ( !v15 )
        {
          v33 = 1;
          break;
        }
      }
      v12 = v15;
    }
  }
  if ( v13 )
  {
    PoolWithTag = (_FCB *)*(v12 - 1);
    *v10 |= 1u;
  }
  if ( !PoolWithTag )
  {
    if ( (a4 & 9) != 0 )
    {
      v16 = 368;
      PoolWithTag = (_FCB *)ExAllocatePoolWithTag((POOL_TYPE)528, 0x170u, 0x66666552u);
      v18 = 2;
      if ( (a4 & 1) != 0 )
      {
        if ( (*((_DWORD *)v38 + 6) & 0x2000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              14,
              &WPP_b377220437133d205b632595b26e896b_Traceguids,
              3221225634LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741662, a1, "StrucSup.c", 0xC1Bu);
          RefsRaiseStatusInternal(a1, -1073741662, v17);
          goto LABEL_66;
        }
        v18 = 6;
      }
    }
    else
    {
      if ( v32 )
      {
        v19 = (_FCB *)ExAllocateFromLookasideListEx(&RefsFcbIndexLookasideList);
        v18 = 1024;
        v16 = 1520;
      }
      else
      {
        v19 = (_FCB *)ExAllocateFromLookasideListEx(&RefsFcbDataLookasideList);
        v18 = 512;
        v16 = 1232;
      }
      PoolWithTag = v19;
    }
    v20 = v16;
    v21 = v38;
    _FCB::Initialize(PoolWithTag, v38, v20);
    PoolWithTag->Header.Resource = (PERESOURCE)v18;
    PoolWithTag->ScavengerFinalizationList.Blink = 0;
    NonpagedFcb = RefsCreateNonpagedFcb((_DWORD)a1, (_DWORD)PoolWithTag, a2, v32, v35);
    PoolWithTag->pNetRoot = (PMRX_NET_ROOT)NonpagedFcb;
    v39 = NonpagedFcb;
    if ( NonpagedFcb )
    {
      v9 = 1;
      PoolWithTag->InternalSrvOpen = a5;
      if ( (a4 & 8) != 0 )
      {
        PoolWithTag->Header.Resource = (PERESOURCE)((unsigned __int64)PoolWithTag->Header.Resource | 0x1000000);
      }
      else
      {
        RtlAvlInsertNodeEx(PoolWithTag->Header.FileContextSupportPointer + 104, v12, v33, NonpagedFcb + 272);
        ++*((_DWORD *)PoolWithTag->Header.FileContextSupportPointer + 210);
        PoolWithTag->Header.Resource = (PERESOURCE)((unsigned __int64)PoolWithTag->Header.Resource | 0x40);
      }
      if ( RefsIsSystemObjectId((const struct _REFS_FILE_REFERENCE *)a2) )
      {
        v24 |= 0x100u;
        PoolWithTag->Header.Resource = (PERESOURCE)v24;
      }
      if ( (v25 & 0x10) != 0 )
      {
        v24 |= 0x10000000u;
        PoolWithTag->Header.Resource = (PERESOURCE)v24;
      }
      if ( (v25 & 0x20) != 0 )
      {
        v24 |= 0x200000u;
        PoolWithTag->Header.Resource = (PERESOURCE)v24;
      }
      if ( (*((_DWORD *)v21 + 7) & 1) != 0 )
      {
        v24 |= 0x80u;
        PoolWithTag->Header.Resource = (PERESOURCE)v24;
      }
      if ( (*((_DWORD *)v21 + 7) & 0x40) != 0 )
        PoolWithTag->Header.Resource = (PERESOURCE)(v24 | 0x20);
      goto LABEL_40;
    }
LABEL_66:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, &WPP_b377220437133d205b632595b26e896b_Traceguids, 3221225626LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741670, a1, "StrucSup.c", 0xC4Fu);
    RefsRaiseStatusInternal(a1, -1073741670, v22);
    __debugbreak();
    JUMPOUT(0x140307DAALL);
  }
LABEL_40:
  v26 = 1;
  if ( !PoolWithTag )
  {
    ExReleaseFastResource(v36, 0);
    return PoolWithTag;
  }
  if ( !v9 )
  {
    v27 = v35 | 2u;
    if ( (v35 & 0x10) != 0 )
      v28 = RefsAcquireFcbWithPaging((__int64)a1, (__int64)PoolWithTag, 0, v27);
    else
      v28 = RefsAcquireExclusiveFcb(a1, PoolWithTag, 0, v27);
    if ( !v28 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&PoolWithTag->Header.AllocationSize);
      v29 = v36;
      ExReleaseFastResource(v36, 0);
      v26 = 0;
      *v10 |= 4u;
      if ( (a4 & 0x40) == 0 )
      {
        v30 = v35 | 4u;
        if ( (v35 & 0x10) != 0 )
          RefsAcquireFcbWithPaging((__int64)a1, (__int64)PoolWithTag, 0, v30);
        else
          RefsAcquireExclusiveFcb(a1, PoolWithTag, 0, v30);
        v9 = 1;
        *v10 &= ~4u;
        ExAcquireFastResourceExclusive(PoolWithTag->Header.FileContextSupportPointer + 78, 0, 1);
        _InterlockedDecrement((volatile signed __int32 *)&PoolWithTag->Header.AllocationSize);
        ExReleaseFastResource(PoolWithTag->Header.FileContextSupportPointer + 78, 0);
      }
      goto LABEL_53;
    }
    v9 = 1;
  }
  v29 = v36;
LABEL_53:
  if ( v26 )
    ExReleaseFastResource(v29, 0);
  if ( v9 )
    *v10 |= 8u;
  return PoolWithTag;
}

```

## disassembly

```asm
0x1403078a0  push    rbx
0x1403078a2  push    rsi
0x1403078a3  push    rdi
0x1403078a4  push    r12
0x1403078a6  push    r13
0x1403078a8  push    r14
0x1403078aa  push    r15
0x1403078ac  sub     rsp, 90h
0x1403078b3  mov     [rsp+0C8h+var_94], r9d
0x1403078b8  mov     [rsp+0C8h+var_90], r8d
0x1403078bd  mov     r13, rdx
0x1403078c0  mov     r14, rcx
0x1403078c3  mov     rax, [rsp+0C8h+arg_28]
0x1403078cb  xor     ecx, ecx
0x1403078cd  mov     [rsp+0C8h+var_88], rcx
0x1403078d2  mov     rdi, [r14+40h]
0x1403078d6  mov     [rsp+0C8h+var_60], rdi
0x1403078db  mov     [rsp+0C8h+var_50], rdi
0x1403078e0  mov     [rsp+0C8h+var_68], ecx
0x1403078e4  xor     sil, sil
0x1403078e7  mov     [rsp+0C8h+var_98], sil
0x1403078ec  mov     [rsp+0C8h+var_70], rcx
0x1403078f1  mov     [rsp+0C8h+var_58], rcx
0x1403078f6  cmp     [rdx], rcx
0x1403078f9  jnz     short loc_140307906
0x1403078fb  cmp     [rdx+8], rcx
0x1403078ff  mov     [rsp+0C8h+var_97], 1
0x140307904  jnz     short loc_14030790A
0x140307906  mov     [rsp+0C8h+var_97], cl
0x14030790a  lea     r15, [rsp+0C8h+var_68]
0x14030790f  test    rax, rax
0x140307912  cmovnz  r15, rax
0x140307916  mov     [rsp+0C8h+var_48], r15
0x14030791e  mov     [r15], ecx
0x140307921  mov     rbx, rcx
0x140307924  mov     [rsp+0C8h+var_88], rcx
0x140307929  lea     rax, [rdi+270h]
0x140307930  mov     [rsp+0C8h+var_80], rax
0x140307935  mov     r8b, 1
0x140307938  xor     edx, edx
0x14030793a  mov     rcx, rax
0x14030793d  call    cs:__imp_ExAcquireFastResourceExclusive
0x140307944  nop     dword ptr [rax+rax+00h]
0x140307949  mov     rdi, [rdi+340h]
0x140307950  mov     [rsp+0C8h+var_96], bl
0x140307954  xor     r12b, r12b
0x140307957  test    rdi, rdi
0x14030795a  jz      short loc_140307997
0x14030795c  nop     dword ptr [rax+00h]
0x140307960  mov     rdx, rdi
0x140307963  mov     rcx, r13
0x140307966  call    RefsFcbTableCompare
0x14030796b  test    eax, eax
0x14030796d  jle     short loc_14030797F
0x14030796f  mov     rax, [rdi+8]
0x140307973  test    rax, rax
0x140307976  jnz     short loc_140307989
0x140307978  mov     [rsp+0C8h+var_96], 1
0x14030797d  jmp     short loc_140307997
0x14030797f  jns     short loc_140307994
0x140307981  mov     rax, [rdi]
0x140307984  test    rax, rax
0x140307987  jz      short loc_14030798E
0x140307989  mov     rdi, rax
0x14030798c  jmp     short loc_140307960
0x14030798e  mov     [rsp+0C8h+var_96], bl
0x140307992  jmp     short loc_140307997
0x140307994  mov     r12b, 1
0x140307997  test    r12b, r12b
0x14030799a  jz      short loc_1403079A9
0x14030799c  mov     rbx, [rdi-8]
0x1403079a0  mov     [rsp+0C8h+var_88], rbx
0x1403079a5  or      dword ptr [r15], 1
0x1403079a9  test    rbx, rbx
0x1403079ac  jnz     loc_140307B81
0x1403079b2  mov     [rsp+0C8h+var_78], rbx
0x1403079b7  test    byte ptr [rsp+0C8h+var_94], 9
0x1403079bc  jz      short loc_140307A15
0x1403079be  mov     r8d, 66666552h; Tag
0x1403079c4  mov     r12d, 170h
0x1403079ca  mov     edx, r12d; NumberOfBytes
0x1403079cd  mov     ecx, 210h; PoolType
0x1403079d2  call    cs:__imp_ExAllocatePoolWithTag
0x1403079d9  nop     dword ptr [rax+rax+00h]
0x1403079de  mov     rbx, rax
0x1403079e1  mov     [rsp+0C8h+var_70], rax
0x1403079e6  mov     [rsp+0C8h+var_88], rax
0x1403079eb  mov     esi, 2
0x1403079f0  mov     [rsp+0C8h+var_78], rsi
0x1403079f5  test    byte ptr [rsp+0C8h+var_94], 1
0x1403079fa  jz      short loc_140307A6C
0x1403079fc  mov     rax, [rsp+0C8h+var_60]
0x140307a01  test    dword ptr [rax+18h], 2000000h
0x140307a08  jnz     loc_140307CCA
0x140307a0e  mov     esi, 6
0x140307a13  jmp     short loc_140307A67
0x140307a15  cmp     [rsp+0C8h+var_97], 0
0x140307a1a  jz      short loc_140307A3C
0x140307a1c  lea     rcx, ?RefsFcbIndexLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140307a23  call    cs:__imp_ExAllocateFromLookasideListEx
0x140307a2a  nop     dword ptr [rax+rax+00h]
0x140307a2f  mov     esi, 400h
0x140307a34  mov     r12d, 5F0h
0x140307a3a  jmp     short loc_140307A5A
0x140307a3c  lea     rcx, ?RefsFcbDataLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x140307a43  call    cs:__imp_ExAllocateFromLookasideListEx
0x140307a4a  nop     dword ptr [rax+rax+00h]
0x140307a4f  mov     esi, 200h
0x140307a54  mov     r12d, 4D0h
0x140307a5a  mov     [rsp+0C8h+var_70], rax
0x140307a5f  mov     [rsp+0C8h+var_88], rax
0x140307a64  mov     rbx, rax
0x140307a67  mov     [rsp+0C8h+var_78], rsi
0x140307a6c  mov     r8, r12; unsigned __int64
0x140307a6f  mov     r12, [rsp+0C8h+var_60]
0x140307a74  mov     rdx, r12; struct _VCB *
0x140307a77  mov     rcx, rbx; this
0x140307a7a  call    ?Initialize@_FCB@@QEAAXAEAU_VCB@@_K@Z; _FCB::Initialize(_VCB &,unsigned __int64)
0x140307a7f  mov     [rbx+8], rsi
0x140307a83  mov     qword ptr [rbx+0C8h], 0
0x140307a8e  mov     eax, [rsp+0C8h+var_90]
0x140307a92  mov     [rsp+0C8h+var_A8], eax
0x140307a96  movzx   r9d, [rsp+0C8h+var_97]
0x140307a9c  mov     r8, r13
0x140307a9f  mov     rdx, rbx
0x140307aa2  mov     rcx, r14
0x140307aa5  call    RefsCreateNonpagedFcb
0x140307aaa  mov     r9, rax
0x140307aad  mov     [rbx+58h], rax
0x140307ab1  mov     [rsp+0C8h+var_58], rax
0x140307ab6  test    rax, rax
0x140307ab9  jz      loc_140307D39
0x140307abf  mov     sil, 1
0x140307ac2  mov     [rsp+0C8h+var_98], sil
0x140307ac7  mov     rax, [rsp+0C8h+arg_20]
0x140307acf  mov     [rbx+148h], rax
0x140307ad6  mov     r8d, [rsp+0C8h+var_94]
0x140307adb  test    r8b, 8
0x140307adf  jnz     short loc_140307B1E
0x140307ae1  add     r9, 110h
0x140307ae8  mov     rcx, [rbx+50h]
0x140307aec  add     rcx, 340h
0x140307af3  movzx   r8d, [rsp+0C8h+var_96]
0x140307af9  mov     rdx, rdi
0x140307afc  call    cs:__imp_RtlAvlInsertNodeEx
0x140307b03  nop     dword ptr [rax+rax+00h]
0x140307b08  mov     rax, [rbx+50h]
0x140307b0c  inc     dword ptr [rax+348h]
0x140307b12  or      qword ptr [rbx+8], 40h
0x140307b17  mov     r8d, [rsp+0C8h+var_94]
0x140307b1c  jmp     short loc_140307B26
0x140307b1e  or      qword ptr [rbx+8], 1000000h
0x140307b26  mov     rdx, [rbx+8]
0x140307b2a  mov     rcx, r13; struct _REFS_FILE_REFERENCE *
0x140307b2d  call    ?RefsIsSystemObjectId@@YAEPEBU_REFS_FILE_REFERENCE@@@Z; RefsIsSystemObjectId(_REFS_FILE_REFERENCE const *)
0x140307b32  test    al, al
0x140307b34  jz      short loc_140307B3F
0x140307b36  bts     rdx, 8
0x140307b3b  mov     [rbx+8], rdx
0x140307b3f  test    r8b, 10h
0x140307b43  jz      short loc_140307B4E
0x140307b45  bts     rdx, 1Ch
0x140307b4a  mov     [rbx+8], rdx
0x140307b4e  test    r8b, 20h
0x140307b52  jz      short loc_140307B5D
0x140307b54  bts     rdx, 15h
0x140307b59  mov     [rbx+8], rdx
0x140307b5d  mov     eax, [r12+1Ch]
0x140307b62  test    sil, al
0x140307b65  jz      short loc_140307B70
0x140307b67  bts     rdx, 7
0x140307b6c  mov     [rbx+8], rdx
0x140307b70  mov     eax, [r12+1Ch]
0x140307b75  test    al, 40h
0x140307b77  jz      short loc_140307B81
0x140307b79  or      rdx, 20h
0x140307b7d  mov     [rbx+8], rdx
0x140307b81  mov     dil, 1
0x140307b84  mov     [rsp+0C8h+var_95], dil
0x140307b89  test    rbx, rbx
0x140307b8c  jz      loc_140307CA0
0x140307b92  mov     r12d, [rsp+0C8h+var_90]
0x140307b97  test    sil, sil
0x140307b9a  jnz     loc_140307C7A
0x140307ba0  mov     r9d, r12d
0x140307ba3  or      r9d, 2
0x140307ba7  xor     r8d, r8d
0x140307baa  mov     rdx, rbx
0x140307bad  mov     rcx, r14
0x140307bb0  test    r12b, 10h
0x140307bb4  jnz     short loc_140307BC0
0x140307bb6  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140307bbb  jmp     loc_140307C6A
0x140307bc0  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140307bc5  jmp     loc_140307C6A
0x140307bca  test    sil, sil
0x140307bcd  jnz     loc_140307C7A
0x140307bd3  lock inc dword ptr [rbx+18h]
0x140307bd7  xor     edx, edx
0x140307bd9  mov     r13, [rsp+0C8h+var_80]
0x140307bde  mov     rcx, r13
0x140307be1  call    cs:__imp_ExReleaseFastResource
0x140307be8  nop     dword ptr [rax+rax+00h]
0x140307bed  xor     dil, dil
0x140307bf0  mov     [rsp+0C8h+var_95], dil
0x140307bf5  or      dword ptr [r15], 4
0x140307bf9  test    byte ptr [rsp+0C8h+var_94], 40h
0x140307bfe  jnz     short loc_140307C7F
0x140307c00  mov     r9d, r12d
0x140307c03  or      r9d, 4
0x140307c07  xor     r8d, r8d
0x140307c0a  mov     rdx, rbx
0x140307c0d  mov     rcx, r14
0x140307c10  test    r12b, 10h
0x140307c14  jnz     short loc_140307C1D
0x140307c16  call    ?RefsAcquireExclusiveFcb@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireExclusiveFcb(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140307c1b  jmp     short loc_140307C22
0x140307c1d  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140307c22  mov     sil, 1
0x140307c25  mov     [rsp+0C8h+var_98], sil
0x140307c2a  and     dword ptr [r15], 0FFFFFFFBh
0x140307c2e  mov     rcx, [rbx+50h]
0x140307c32  add     rcx, 270h
0x140307c39  movzx   r8d, sil
0x140307c3d  xor     edx, edx
0x140307c3f  call    cs:__imp_ExAcquireFastResourceExclusive
0x140307c46  nop     dword ptr [rax+rax+00h]
0x140307c4b  lock dec dword ptr [rbx+18h]
0x140307c4f  mov     rcx, [rbx+50h]
0x140307c53  add     rcx, 270h
0x140307c5a  xor     edx, edx
0x140307c5c  call    cs:__imp_ExReleaseFastResource
0x140307c63  nop     dword ptr [rax+rax+00h]
0x140307c68  jmp     short loc_140307C7F
0x140307c6a  test    al, al
0x140307c6c  jz      loc_140307BCA
0x140307c72  mov     sil, 1
0x140307c75  mov     [rsp+0C8h+var_98], sil
0x140307c7a  mov     r13, [rsp+0C8h+var_80]
0x140307c7f  test    dil, dil
0x140307c82  jz      short loc_140307C95
0x140307c84  xor     edx, edx
0x140307c86  mov     rcx, r13
0x140307c89  call    cs:__imp_ExReleaseFastResource
0x140307c90  nop     dword ptr [rax+rax+00h]
0x140307c95  test    sil, sil
0x140307c98  jz      short loc_140307CB3
0x140307c9a  or      dword ptr [r15], 8
0x140307c9e  jmp     short loc_140307CB3
0x140307ca0  xor     edx, edx
0x140307ca2  mov     rcx, [rsp+0C8h+var_80]
0x140307ca7  call    cs:__imp_ExReleaseFastResource
0x140307cae  nop     dword ptr [rax+rax+00h]
0x140307cb3  mov     rax, rbx
0x140307cb6  add     rsp, 90h
0x140307cbd  pop     r15
0x140307cbf  pop     r14
0x140307cc1  pop     r13
0x140307cc3  pop     r12
0x140307cc5  pop     rdi
0x140307cc6  pop     rsi
0x140307cc7  pop     rbx
0x140307cc8  retn
0x140307cca  lea     rax, WPP_GLOBAL_Control
0x140307cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x140307cd8  cmp     rcx, rax
0x140307cdb  jz      short loc_140307D07
0x140307cdd  test    dword ptr [rcx+2Ch], 100h
0x140307ce4  jz      short loc_140307D07
0x140307ce6  cmp     byte ptr [rcx+29h], 4
0x140307cea  jb      short loc_140307D07
0x140307cec  mov     edx, 0Eh
0x140307cf1  mov     r9d, 0C00000A2h
0x140307cf7  lea     r8, WPP_b377220437133d205b632595b26e896b_Traceguids
0x140307cfe  mov     rcx, [rcx+18h]
0x140307d02  call    WPP_SF_d
0x140307d07  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140307d0e  test    al, al
0x140307d10  jz      short loc_140307D2C
0x140307d12  mov     r9d, 0C1Bh; unsigned int
0x140307d18  lea     r8, aStrucsupC; "StrucSup.c"
0x140307d1f  mov     rdx, r14; struct _IRP_CONTEXT *
0x140307d22  mov     ecx, 0C00000A2h; Status
0x140307d27  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140307d2c  mov     edx, 0C00000A2h; int
0x140307d31  mov     rcx, r14; struct _IRP_CONTEXT *
0x140307d34  call    ?RefsRaiseStatusInternal@@YAXPEAU_IRP_CONTEXT@@JK@Z; RefsRaiseStatusInternal(_IRP_CONTEXT *,long,ulong)
0x140307d39  lea     rax, WPP_GLOBAL_Control
0x140307d40  mov     rcx, cs:WPP_GLOBAL_Control
0x140307d47  cmp     rcx, rax
0x140307d4a  jz      short loc_140307D76
0x140307d4c  test    dword ptr [rcx+2Ch], 100h
0x140307d53  jz      short loc_140307D76
0x140307d55  cmp     byte ptr [rcx+29h], 4
0x140307d59  jb      short loc_140307D76
0x140307d5b  mov     edx, 0Fh
0x140307d60  mov     r9d, 0C000009Ah
0x140307d66  lea     r8, WPP_b377220437133d205b632595b26e896b_Traceguids
0x140307d6d  mov     rcx, [rcx+18h]
0x140307d71  call    WPP_SF_d
  ... truncated ...
```

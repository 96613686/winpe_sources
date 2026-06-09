# NtfsCreateNonresidentWithValue

- ea: `0x1401578f0`
- end: `0x14015811f`
- name: `NtfsCreateNonresidentWithValue`
- size: `2095`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401560d0`
- `0x140158130`
- `0x140278f28`

## callees

- `0x140007ea0`
- `0x14000ea70`
- `0x14001e810`
- `0x1400285c0`
- `0x140040ec4`
- `0x1400592c0`
- `0x140059440`
- `0x140059740`
- `0x14013c320`
- `0x14013f3c4`
- `0x140150c10`
- `0x1401578f0`
- `0x1401597b8`
- `0x1401606f0`
- `0x140163fc8`
- `0x14019a768`
- `0x1401e0e8c`
- `0x140223ab0`

## import_xrefs

- `ntoskrnl!CcSetFileSizesEx` at `0x140157b59`
- `ntoskrnl!CcSetFileSizesEx` at `0x140157b59`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a8587`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402a8587`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140157f8e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140157f8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157cfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a85f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140157cfc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a85f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140157c77`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140157c77`
- `ntoskrnl!CcUnpinData` at `0x140157f12`
- `ntoskrnl!CcUnpinData` at `0x140157f40`
- `ntoskrnl!CcUnpinData` at `0x1402a85bb`
- `ntoskrnl!CcUnpinData` at `0x140157f12`
- `ntoskrnl!CcUnpinData` at `0x140157f40`
- `ntoskrnl!CcUnpinData` at `0x1402a85bb`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140157e36`
- `ntoskrnl!MmSetAddressRangeModified` at `0x140157e36`
- `ntoskrnl!ExRaiseStatus` at `0x1401580da`
- `ntoskrnl!ExRaiseStatus` at `0x1401580da`

## pseudocode

```c
__int64 __fastcall NtfsCreateNonresidentWithValue(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        UNICODE_STRING *a4,
        void *a5,
        int a6,
        __int16 a7,
        __int16 *a8,
        char a9,
        char a10,
        __int64 a11)
{
  __int64 v14; // r15
  int v15; // ecx
  __int16 v16; // si
  __int16 *v17; // rbx
  unsigned __int8 v18; // r12
  __int64 v19; // rsi
  bool v20; // dl
  size_t v21; // r14
  struct _FILE_OBJECT *v22; // r9
  struct _CC_FILE_SIZES *v23; // rdx
  int v24; // eax
  __int64 result; // rax
  unsigned int v26; // r8d
  unsigned int v27; // esi
  void *v28; // r14
  signed __int64 v29; // r8
  void *v30; // rcx
  size_t v31; // rax
  unsigned int v32; // r14d
  _WORD *v33; // rax
  int v34; // ecx
  __int128 v35; // xmm1
  __int64 v36; // rdx
  signed __int64 v37; // rdx
  signed __int64 v38; // r8
  signed __int64 v39; // r9
  signed __int64 v40; // r10
  unsigned __int64 v41; // rax
  __int16 Buffer; // [rsp+20h] [rbp-118h]
  int v43; // [rsp+28h] [rbp-110h]
  char v44; // [rsp+70h] [rbp-C8h] BYREF
  bool v45; // [rsp+71h] [rbp-C7h]
  _DWORD Length[3]; // [rsp+74h] [rbp-C4h] BYREF
  void *v47; // [rsp+80h] [rbp-B8h] BYREF
  void *Src; // [rsp+88h] [rbp-B0h]
  size_t Size; // [rsp+90h] [rbp-A8h]
  _WORD *v50; // [rsp+98h] [rbp-A0h]
  int v51[2]; // [rsp+A0h] [rbp-98h]
  unsigned int v52; // [rsp+A8h] [rbp-90h]
  __int64 v53; // [rsp+B0h] [rbp-88h]
  void *v54; // [rsp+B8h] [rbp-80h]
  UNICODE_STRING v55; // [rsp+C0h] [rbp-78h] BYREF
  void *v56; // [rsp+D0h] [rbp-68h]
  size_t v57; // [rsp+D8h] [rbp-60h]
  __int128 v58; // [rsp+E0h] [rbp-58h] BYREF
  __int64 v59; // [rsp+F0h] [rbp-48h]

  LODWORD(v47) = a3;
  *(_QWORD *)v51 = a1;
  Src = a5;
  v54 = a5;
  Length[0] = a6;
  v53 = a11;
  v44 = 0;
  v55 = 0;
  v14 = *(_QWORD *)(a2 + 96);
  *(_QWORD *)&Length[1] = 0;
  v50 = 0;
  v15 = *(_DWORD *)(160LL * ((a3 >> 4) - 1) + *(_QWORD *)(v14 + 4704) + 140);
  v45 = (v15 & 0x80u) != 0 || *(_DWORD *)(a2 + 8) == 4;
  v16 = *(_WORD *)(v14 + 776) & a7;
  if ( a4 )
    v55 = *a4;
  if ( a2 == *(_QWORD *)(*(_QWORD *)(v14 + 48) + 184LL)
    && a3 == 32
    && (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 2) != 0 )
  {
    McTemplateU0pdd_EtwWriteTransfer(v15, (unsigned int)attrsup_c3873, a1, Length[0], v16);
  }
  if ( a8 )
  {
    v17 = a8;
    v44 = 1;
  }
  else
  {
    v50 = ExAllocateFromLookasideListEx(&NtfsRollbackStructLookasideList);
    NtfsAddPreallocatedStructToRollbackList(a1, 0, 0, v50);
    v17 = NtfsCreateScb(a1, a2, a3, &v55, 0, 0, &v44);
    ClearFlagInterlocked(v17 + 100, 552);
    if ( !v44 )
    {
      v33 = v50;
      *v50 = 1830;
      *((_QWORD *)v33 + 3) = v17;
      v34 = *((_DWORD *)v33 + 1) | 4;
      *((_DWORD *)v33 + 15) |= 0x40u;
      *((_DWORD *)v33 + 14) |= 0x40u;
      *((_DWORD *)v33 + 1) = v34 | 8;
      *((_DWORD *)v17 + 128) |= 0x2000000u;
    }
  }
  v18 = a10 | v45;
  Size = Length[0];
  Buffer = v16;
  v19 = *(_QWORD *)v51;
  NtfsAllocateAttribute(v51[0], Buffer, 1, a9, Length[0], v53);
  NtfsUpdateScbFromAttribute(v19, v17, 0);
  if ( !v44 && *((_DWORD *)v17 + 64) != 128 )
    SetFlagInterlocked(*((_QWORD *)v17 + 62) + 88LL, 8);
  if ( (*((_DWORD *)v17 + 50) & 1) == 0 )
    _InterlockedOr((volatile signed __int32 *)v17 + 50, 1u);
  v20 = v45;
  if ( v45 )
  {
    NtfsCreateInternalAttributeStream(v19, (__int64)v17, 1, 0, (__int64)L"8:", 0);
    v20 = v45;
  }
  v21 = Size;
  if ( (*((_DWORD *)v17 + 50) & 0x20000) != 0 && *((_QWORD *)v17 + 4) < (signed __int64)Size )
  {
    v29 = Size;
    if ( (signed __int64)Size >= *((_QWORD *)v17 + 58) )
      v29 = *((_QWORD *)v17 + 58);
    if ( v29 > *((_QWORD *)v17 + 5) )
    {
      if ( (*((_DWORD *)v17 + 50) & 0x20000) != 0 )
      {
        v39 = *((_QWORD *)v17 + 58);
        if ( v39 < v29 )
        {
LABEL_89:
          *((_QWORD *)v17 + 58) = v29;
          goto LABEL_90;
        }
        if ( *((_QWORD *)v17 + 5) > v29 )
        {
          if ( *(_QWORD *)(*((_QWORD *)v17 + 36) + 16LL) && v29 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v40 = (v29 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v40 < v39 )
              *((_QWORD *)v17 + 58) = v40;
            goto LABEL_90;
          }
          goto LABEL_89;
        }
      }
LABEL_90:
      *((_QWORD *)v17 + 5) = v29;
    }
  }
  *((_QWORD *)v17 + 4) = v21;
  if ( Src )
  {
    v26 = Length[0];
    if ( Length[0] )
    {
      if ( v20 )
      {
        v30 = 0;
        v47 = 0;
        v31 = 0;
        Size = 0;
        while ( v26 )
        {
          v32 = 4096;
          if ( v26 < 0x1000 )
            v32 = v26;
          if ( v30 )
          {
            CcUnpinData(v30);
            v47 = 0;
            v31 = Size;
          }
          NtfsPinStream(v19, v17, v31, v32, &v47, &Length[1]);
          if ( a8 )
            MmSetAddressRangeModified(*(PVOID *)&Length[1], v32);
          else
            memmove(*(void **)&Length[1], Src, v32);
          NtfsWriteLog(v19, (_DWORD)v17, (_DWORD)v47, 8, *(__int64 *)&Length[1], v32, 0, 0, 0, Size, 0, 0, v32);
          v26 = Length[0] - v32;
          Length[0] = v26;
          v52 = v26;
          Src = (char *)Src + v32;
          v56 = Src;
          v31 = v32 + Size;
          Size = v31;
          v57 = v31;
          v30 = v47;
        }
        if ( v30 )
        {
          CcUnpinData(v30);
          v47 = 0;
        }
      }
      else
      {
        v27 = -*(_DWORD *)(v14 + 356) & (*(_DWORD *)(v14 + 356) + Length[0] - 1);
        if ( v27 == Length[0] )
        {
          v28 = Src;
          *(_QWORD *)&Length[1] = Src;
        }
        else
        {
          *(_QWORD *)&Length[1] = ExAllocatePoolWithTag((POOL_TYPE)528, v27, 0x4146744Eu);
          memmove(*(void **)&Length[1], Src, v21);
          if ( v27 > Length[0] )
            memset((void *)(v21 + *(_QWORD *)&Length[1]), 0, v27 - Length[0]);
          v28 = Src;
        }
        v43 = v27;
        v19 = *(_QWORD *)v51;
        NtfsWriteBytes(v51[0], v14, (int)v17, 0, *(PVOID *)&Length[1], v43, 0);
        if ( *(void **)&Length[1] != v28 )
          ExFreePoolWithTag(*(PVOID *)&Length[1], 0);
        v18 = 1;
      }
      if ( (*((_DWORD *)v17 + 50) & 0x20000) == 0 )
        goto LABEL_46;
      v37 = *((_QWORD *)v17 + 4);
      v38 = *((_QWORD *)v17 + 58);
      if ( v38 < v37 )
        goto LABEL_96;
      if ( *((_QWORD *)v17 + 5) > v37 )
      {
        if ( !*(_QWORD *)(*((_QWORD *)v17 + 36) + 16LL) || v37 == 0x7FFFFFFFFFFFFFFFLL )
        {
LABEL_96:
          v41 = *((_QWORD *)v17 + 4);
          goto LABEL_97;
        }
        if ( (__int64)((v37 + 4095) & 0xFFFFFFFFFFFFF000uLL) < v38 )
        {
          v41 = (*((_QWORD *)v17 + 4) + 4095LL) & 0xFFFFFFFFFFFFF000uLL;
LABEL_97:
          *((_QWORD *)v17 + 58) = v41;
        }
      }
LABEL_46:
      *((_QWORD *)v17 + 5) = *((_QWORD *)v17 + 4);
    }
  }
  NtfsWriteFileSizes(v19, (_DWORD)v17, 0, v18, a9, 0);
  v22 = (struct _FILE_OBJECT *)*((_QWORD *)v17 + 35);
  if ( v22 )
  {
    if ( v22->SectionObjectPointer != (PSECTION_OBJECT_POINTERS)(*((_QWORD *)v17 + 36) + 16LL) && v19 )
    {
      NtfsCreateInternalAttributeStream(v19, (__int64)v17, 0, 0, 0, 0);
      v22 = (struct _FILE_OBJECT *)*((_QWORD *)v17 + 35);
    }
    if ( *(_QWORD *)(*((_QWORD *)v17 + 36) + 24LL) )
    {
      v23 = (struct _CC_FILE_SIZES *)(v17 + 12);
      if ( (*((_DWORD *)v17 + 128) & 1) != 0 )
      {
        v35 = *(_OWORD *)&v23->AllocationSize.LowPart;
        v58 = v35;
        v59 = *((_QWORD *)v17 + 5);
        v36 = *((_QWORD *)v17 + 24);
        *(_QWORD *)&v58 = v35 - *(_QWORD *)(v36 + 1952);
        *((_QWORD *)&v58 + 1) = *((_QWORD *)&v35 + 1) - *(_QWORD *)(v36 + 1952);
        NtfsSetCcFileSizes(v22, v17, &v58);
      }
      else
      {
        v24 = CcSetFileSizesEx(v22, v23);
        if ( v24 < 0 && *((_DWORD *)v17 + 55) )
          ExRaiseStatus(v24);
        if ( NtfsStatusDebugFlags
          && v24
          && v24 != 294
          && (unsigned int)(v24 - 298) > 1
          && (unsigned int)v24 < 0xFFFFFFED
          && v24 != -1073741608
          && v24 != -1073741802
          && v24 != -1073741807
          && (unsigned int)(v24 + 2147483643) > 1
          && v24 != 259 )
        {
          NtfsStatusTraceAndDebugInternal(0, (unsigned int)v24, 333485);
        }
      }
    }
  }
  result = *((unsigned int *)v17 + 50);
  if ( (result & 0x10) != 0 )
  {
    *(_QWORD *)(a2 + 160) = *((_QWORD *)v17 + 59);
    result = *((_QWORD *)v17 + 4);
    *(_QWORD *)(a2 + 168) = result;
    *(_DWORD *)(a2 + 184) |= 0x40000008u;
  }
  return result;
}

```

## disassembly

```asm
0x1401578f0  push    rbx
0x1401578f2  push    rsi
0x1401578f3  push    rdi
0x1401578f4  push    r12
0x1401578f6  push    r13
0x1401578f8  push    r14
0x1401578fa  push    r15
0x1401578fc  sub     rsp, 100h
0x140157903  mov     rax, cs:__security_cookie
0x14015790a  xor     rax, rsp
0x14015790d  mov     [rsp+138h+var_40], rax
0x140157915  mov     r14, r9
0x140157918  mov     ebx, r8d
0x14015791b  mov     dword ptr [rsp+138h+var_B8], ebx
0x140157922  mov     rdi, rdx
0x140157925  mov     r12, rcx
0x140157928  mov     qword ptr [rsp+138h+var_98], rcx
0x140157930  mov     rax, [rsp+138h+arg_20]
0x140157938  mov     [rsp+138h+Src], rax
0x140157940  mov     [rsp+138h+var_80], rax
0x140157948  mov     eax, [rsp+138h+arg_28]
0x14015794f  mov     dword ptr [rsp+138h+Length], eax
0x140157953  mov     r13, [rsp+138h+arg_38]
0x14015795b  mov     rax, [rsp+138h+arg_50]
0x140157963  mov     [rsp+138h+var_88], rax
0x14015796b  mov     [rsp+138h+var_C8], 0
0x140157970  xorps   xmm0, xmm0
0x140157973  movups  [rsp+138h+var_78], xmm0
0x14015797b  mov     r15, [rdx+60h]
0x14015797f  xor     eax, eax
0x140157981  mov     qword ptr [rsp+138h+Length+4], rax
0x140157986  mov     [rsp+138h+var_A0], rax
0x14015798e  mov     eax, r8d
0x140157991  shr     eax, 4
0x140157994  dec     eax
0x140157996  lea     rcx, [rax+rax*4]
0x14015799a  shl     rcx, 5
0x14015799e  mov     rax, [r15+1260h]
0x1401579a5  mov     ecx, [rcx+rax+8Ch]
0x1401579ac  test    cl, cl
0x1401579ae  js      loc_140157C30
0x1401579b4  cmp     dword ptr [rdx+8], 4
0x1401579b8  jz      loc_140157C30
0x1401579be  mov     [rsp+138h+var_C7], 0
0x1401579c3  movzx   esi, [rsp+138h+arg_30]
0x1401579cb  and     si, [r15+308h]
0x1401579d3  test    r14, r14
0x1401579d6  jz      short loc_1401579E4
0x1401579d8  movups  xmm0, xmmword ptr [r9]
0x1401579dc  movups  [rsp+138h+var_78], xmm0
0x1401579e4  mov     rax, [r15+30h]
0x1401579e8  cmp     rdi, [rax+0B8h]
0x1401579ef  jz      loc_140157D3B
0x1401579f5  test    r13, r13
0x1401579f8  jz      loc_140157F87
0x1401579fe  mov     rbx, r13
0x140157a01  mov     [rsp+138h+var_C8], 1
0x140157a06  movzx   r12d, [rsp+138h+var_C7]
0x140157a0c  or      r12b, [rsp+138h+arg_48]
0x140157a14  mov     eax, dword ptr [rsp+138h+Length]
0x140157a18  mov     [rsp+138h+Size], rax
0x140157a20  mov     rcx, [rsp+138h+var_88]
0x140157a28  mov     [rsp+138h+var_F8], rcx
0x140157a2d  mov     [rsp+138h+var_100], rax
0x140157a32  movzx   eax, [rsp+138h+arg_40]
0x140157a3a  mov     byte ptr [rsp+138h+var_108], al
0x140157a3e  mov     byte ptr [rsp+138h+var_110], 1
0x140157a43  mov     word ptr [rsp+138h+Buffer], si
0x140157a48  mov     r9, r14
0x140157a4b  mov     r8d, dword ptr [rsp+138h+var_B8]
0x140157a53  mov     rdx, rbx
0x140157a56  mov     rsi, qword ptr [rsp+138h+var_98]
0x140157a5e  mov     rcx, rsi
0x140157a61  call    NtfsAllocateAttribute
0x140157a66  xor     r8d, r8d
0x140157a69  mov     rdx, rbx
0x140157a6c  mov     rcx, rsi
0x140157a6f  call    NtfsUpdateScbFromAttribute
0x140157a74  cmp     [rsp+138h+var_C8], 0
0x140157a79  jz      loc_140157F5D
0x140157a7f  mov     eax, [rbx+0C8h]
0x140157a85  test    al, 1
0x140157a87  jnz     short loc_140157A91
0x140157a89  lock or dword ptr [rbx+0C8h], 1
0x140157a91  movzx   edx, [rsp+138h+var_C7]
0x140157a96  test    dl, dl
0x140157a98  jz      short loc_140157AC5
0x140157a9a  mov     qword ptr [rsp+138h+var_110], 0
0x140157aa3  lea     rax, a8_0; "8:"
0x140157aaa  mov     [rsp+138h+Buffer], rax
0x140157aaf  xor     r9d, r9d
0x140157ab2  mov     r8b, 1
0x140157ab5  mov     rdx, rbx
0x140157ab8  mov     rcx, rsi
0x140157abb  call    NtfsCreateInternalAttributeStream
0x140157ac0  movzx   edx, [rsp+138h+var_C7]
0x140157ac5  mov     ecx, [rbx+0C8h]
0x140157acb  mov     r14, [rsp+138h+Size]
0x140157ad3  bt      ecx, 11h
0x140157ad7  jb      loc_140157D7A
0x140157add  mov     [rbx+20h], r14
0x140157ae1  cmp     [rsp+138h+Src], 0
0x140157aea  jnz     loc_140157C3A
0x140157af0  mov     byte ptr [rsp+138h+var_110], 0
0x140157af5  movzx   eax, [rsp+138h+arg_40]
0x140157afd  mov     byte ptr [rsp+138h+Buffer], al
0x140157b01  movzx   r9d, r12b
0x140157b05  xor     r8d, r8d
0x140157b08  mov     rdx, rbx
0x140157b0b  mov     rcx, rsi
0x140157b0e  call    NtfsWriteFileSizes
0x140157b13  mov     r9, [rbx+118h]
0x140157b1a  test    r9, r9
0x140157b1d  jz      short loc_140157B7A
0x140157b1f  mov     rax, [rbx+120h]
0x140157b26  add     rax, 10h
0x140157b2a  cmp     [r9+28h], rax
0x140157b2e  jnz     loc_14015808C
0x140157b34  mov     rax, [rbx+120h]
0x140157b3b  mov     rcx, [rax+18h]
0x140157b3f  test    rcx, rcx
0x140157b42  jz      short loc_140157B7A
0x140157b44  lea     rdx, [rbx+18h]; FileSizes
0x140157b48  mov     eax, [rbx+200h]
0x140157b4e  mov     rcx, r9; FileObject
0x140157b51  test    al, 1
0x140157b53  jnz     loc_140158034
0x140157b59  call    cs:__imp_CcSetFileSizesEx
0x140157b60  nop     dword ptr [rax+rax+00h]
0x140157b65  mov     edx, eax
0x140157b67  test    eax, eax
0x140157b69  js      loc_1401580C4
0x140157b6f  movzx   eax, cs:NtfsStatusDebugFlags
0x140157b76  test    al, al
0x140157b78  jnz     short loc_140157BCB
0x140157b7a  mov     eax, [rbx+0C8h]
0x140157b80  test    al, 10h
0x140157b82  jz      short loc_140157BA7
0x140157b84  mov     rax, [rbx+1D8h]
0x140157b8b  mov     [rdi+0A0h], rax
0x140157b92  mov     rax, [rbx+20h]
0x140157b96  mov     [rdi+0A8h], rax
0x140157b9d  or      dword ptr [rdi+0B8h], 40000008h
0x140157ba7  mov     rcx, [rsp+138h+var_40]
0x140157baf  xor     rcx, rsp; StackCookie
0x140157bb2  call    __security_check_cookie
0x140157bb7  add     rsp, 100h
0x140157bbe  pop     r15
0x140157bc0  pop     r14
0x140157bc2  pop     r13
0x140157bc4  pop     r12
0x140157bc6  pop     rdi
0x140157bc7  pop     rsi
0x140157bc8  pop     rbx
0x140157bc9  retn
0x140157bcb  test    edx, edx
0x140157bcd  jz      short loc_140157B7A
0x140157bcf  cmp     edx, 126h
0x140157bd5  jz      short loc_140157B7A
0x140157bd7  lea     eax, [rdx-12Ah]
0x140157bdd  cmp     eax, 1
0x140157be0  jbe     short loc_140157B7A
0x140157be2  cmp     edx, 0FFFFFFEDh
0x140157be5  jnb     short loc_140157B7A
0x140157be7  cmp     edx, 0C00000D8h
0x140157bed  jz      short loc_140157B7A
0x140157bef  cmp     edx, 0C0000016h
0x140157bf5  jz      short loc_140157B7A
0x140157bf7  cmp     edx, 0C0000011h
0x140157bfd  jz      loc_140157B7A
0x140157c03  lea     eax, [rdx+7FFFFFFBh]
0x140157c09  cmp     eax, 1
0x140157c0c  jbe     loc_140157B7A
0x140157c12  cmp     edx, 103h
0x140157c18  jz      loc_140157B7A
0x140157c1e  xor     ecx, ecx
0x140157c20  mov     r8d, 516ADh
0x140157c26  call    NtfsStatusTraceAndDebugInternal
0x140157c2b  jmp     loc_140157B7A
0x140157c30  mov     [rsp+138h+var_C7], 1
0x140157c35  jmp     loc_1401579C3
0x140157c3a  mov     r8d, dword ptr [rsp+138h+Length]
0x140157c3f  test    r8d, r8d
0x140157c42  jz      loc_140157AF0
0x140157c48  test    dl, dl
0x140157c4a  jnz     loc_140157DC7
0x140157c50  mov     eax, [r15+164h]
0x140157c57  lea     esi, [r8-1]
0x140157c5b  add     esi, eax
0x140157c5d  neg     eax
0x140157c5f  and     esi, eax
0x140157c61  cmp     esi, r8d
0x140157c64  jz      loc_140157DB5
0x140157c6a  mov     edx, esi; NumberOfBytes
0x140157c6c  mov     ecx, 210h; PoolType
0x140157c71  mov     r8d, 4146744Eh; Tag
0x140157c77  call    cs:__imp_ExAllocatePoolWithTag
0x140157c7e  nop     dword ptr [rax+rax+00h]
0x140157c83  mov     qword ptr [rsp+138h+Length+4], rax
0x140157c88  mov     r8, r14; Size
0x140157c8b  mov     rdx, [rsp+138h+Src]; Src
0x140157c93  mov     rcx, rax; void *
0x140157c96  call    memmove
0x140157c9b  mov     ecx, dword ptr [rsp+138h+Length]
0x140157c9f  cmp     esi, ecx
0x140157ca1  jbe     short loc_140157CB8
0x140157ca3  mov     r8d, esi
0x140157ca6  sub     r8d, ecx; Size
0x140157ca9  mov     rcx, qword ptr [rsp+138h+Length+4]
0x140157cae  add     rcx, r14; void *
0x140157cb1  xor     edx, edx; Val
0x140157cb3  call    memset
0x140157cb8  mov     r14, [rsp+138h+Src]
0x140157cc0  mov     [rsp+138h+var_108], 0; int
0x140157cc8  mov     [rsp+138h+var_110], esi; int
0x140157ccc  mov     rax, qword ptr [rsp+138h+Length+4]
0x140157cd1  mov     [rsp+138h+Buffer], rax; Buffer
0x140157cd6  xor     r9d, r9d; int
0x140157cd9  mov     r8, rbx; int
0x140157cdc  mov     rdx, r15; int
0x140157cdf  mov     rsi, qword ptr [rsp+138h+var_98]
0x140157ce7  mov     rcx, rsi; int
0x140157cea  call    NtfsWriteBytes
0x140157cef  nop
0x140157cf0  mov     rcx, qword ptr [rsp+138h+Length+4]; P
0x140157cf5  cmp     rcx, r14
0x140157cf8  jz      short loc_140157D08
0x140157cfa  xor     edx, edx; Tag
0x140157cfc  call    cs:__imp_ExFreePoolWithTag
0x140157d03  nop     dword ptr [rax+rax+00h]
0x140157d08  mov     r12b, 1
0x140157d0b  test    dword ptr [rbx+0C8h], 200h
0x140157d15  jz      short loc_140157D1E
0x140157d17  movzx   eax, cs:NtfsStatusDebugFlags
0x140157d1e  mov     ecx, [rbx+0C8h]
0x140157d24  bt      ecx, 11h
0x140157d28  jb      loc_1401580FC
0x140157d2e  mov     rax, [rbx+20h]
0x140157d32  mov     [rbx+28h], rax
0x140157d36  jmp     loc_140157AF0
0x140157d3b  cmp     ebx, 20h ; ' '
0x140157d3e  jnz     loc_1401579F5
0x140157d44  test    r12, r12
0x140157d47  jnz     loc_1401580E7
0x140157d4d  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 2
0x140157d54  jz      loc_1401579F5
0x140157d5a  movzx   eax, si
0x140157d5d  mov     dword ptr [rsp+138h+Buffer], eax
0x140157d61  mov     r9d, dword ptr [rsp+138h+Length]
0x140157d66  mov     r8, r12
0x140157d69  lea     rdx, attrsup_c3873
0x140157d70  call    McTemplateU0pdd_EtwWriteTransfer
0x140157d75  jmp     loc_1401579F5
0x140157d7a  cmp     [rbx+20h], r14
0x140157d7e  jge     loc_140157ADD
0x140157d84  mov     rax, [rbx+1D0h]
0x140157d8b  mov     r8, r14
0x140157d8e  cmp     r14, rax
0x140157d91  cmovge  r8, rax
0x140157d95  cmp     r8, [rbx+28h]
0x140157d99  jle     loc_140157ADD
0x140157d9f  bt      ecx, 9
0x140157da3  jnb     loc_1402C92E8
0x140157da9  movzx   eax, cs:NtfsStatusDebugFlags
0x140157db0  jmp     loc_1402C92E8
0x140157db5  mov     r14, [rsp+138h+Src]
0x140157dbd  mov     qword ptr [rsp+138h+Length+4], r14
0x140157dc2  jmp     loc_140157CC0
0x140157dc7  xor     ecx, ecx; Bcb
0x140157dc9  mov     [rsp+138h+var_B8], rcx
0x140157dd1  xor     eax, eax
0x140157dd3  mov     [rsp+138h+Size], rax
0x140157ddb  test    r8d, r8d
0x140157dde  jz      loc_140157F37
0x140157de4  mov     r14d, 1000h
0x140157dea  cmp     r8d, r14d
0x140157ded  cmovb   r14d, r8d
0x140157df1  test    rcx, rcx
0x140157df4  jnz     loc_140157F12
0x140157dfa  lea     rcx, [rsp+138h+Length+4]
0x140157dff  mov     qword ptr [rsp+138h+var_110], rcx
0x140157e04  lea     rcx, [rsp+138h+var_B8]
0x140157e0c  mov     [rsp+138h+Buffer], rcx
0x140157e11  mov     r9d, r14d
0x140157e14  mov     r8, rax
0x140157e17  mov     rdx, rbx
0x140157e1a  mov     rcx, rsi
0x140157e1d  call    NtfsPinStream
0x140157e22  mov     r15d, r14d
0x140157e25  mov     rcx, qword ptr [rsp+138h+Length+4]; void *
0x140157e2a  test    r13, r13
0x140157e2d  jz      loc_140157EFD
0x140157e33  mov     edx, r15d; Length
0x140157e36  call    cs:__imp_MmSetAddressRangeModified
0x140157e3d  nop     dword ptr [rax+rax+00h]
0x140157e42  mov     [rsp+138h+var_D8], r14d
0x140157e47  mov     [rsp+138h+var_E0], 0
0x140157e4f  mov     [rsp+138h+var_E8], 0
0x140157e57  mov     rax, [rsp+138h+Size]
0x140157e5f  mov     [rsp+138h+var_F0], rax
  ... truncated ...
```

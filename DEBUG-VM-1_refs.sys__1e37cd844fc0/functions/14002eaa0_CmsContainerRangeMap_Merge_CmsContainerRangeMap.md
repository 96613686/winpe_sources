# CmsContainerRangeMap::Merge(CmsContainerRangeMap *)

- ea: `0x14002eaa0`
- end: `0x14002f272`
- name: `?Merge@CmsContainerRangeMap@@QEAAXPEAV1@@Z`
- size: `2002`
- prototype: `void(CmsContainerRangeMap *__hidden this, struct CmsContainerRangeMap *)`
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140030130`
- `0x1400318ac`
- `0x1400568e0`
- `0x1400ccdf4`
- `0x140121b90`
- `0x140125eb8`
- `0x140125f54`
- `0x140145a74`

## callees

- `0x140024c60`
- `0x14002eaa0`
- `0x1400b48a0`
- `0x140177d64`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002ef5e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002ef5e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002edb7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002f150`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002edb7`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002f150`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002efe5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14002efe5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fb491`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1401fb491`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002edeb`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002ee01`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002ef16`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002efd1`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002f09c`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002f0fc`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002f18a`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002edeb`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002ee01`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002ef16`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002efd1`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002f09c`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002f0fc`
- `ntoskrnl!ExReleasePushLockEx` at `0x14002f18a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f254`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002f254`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002ee48`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002eea7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002f059`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002ee48`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002eea7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002f059`

## pseudocode

```c
void __fastcall CmsContainerRangeMap::Merge(CmsContainerRangeMap *this, struct CmsContainerRangeMap *a2)
{
  CmsContainerRangeMap *v3; // r12
  unsigned int v4; // ebx
  int v5; // r9d
  unsigned int v6; // edi
  __int64 v7; // rdx
  char v8; // r9
  __int64 *v9; // rax
  __int64 v10; // rax
  bool v11; // zf
  __int64 *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  int v16; // r15d
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // r12
  _QWORD *v20; // r13
  volatile signed __int32 *v21; // rax
  volatile signed __int32 *v22; // r12
  signed __int64 *v23; // rdx
  _QWORD *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r14
  struct _SLIST_ENTRY *v27; // r13
  struct _PAGED_LOOKASIDE_LIST *v28; // rcx
  _QWORD *v29; // rax
  _QWORD *v30; // rdx
  volatile signed __int32 *v31; // rax
  signed __int64 *v32; // rdx
  _QWORD *v33; // rax
  __int64 v34; // rcx
  signed __int64 v35; // rax
  signed __int64 v36; // rax
  signed __int64 v37; // rax
  signed __int64 v38; // rax
  __int64 v39; // [rsp+30h] [rbp-41h]
  __int128 v40; // [rsp+38h] [rbp-39h]
  __int128 v41; // [rsp+58h] [rbp-19h]
  int v43; // [rsp+E0h] [rbp+6Fh]
  __int64 v44; // [rsp+E8h] [rbp+77h]
  _QWORD *v45; // [rsp+E8h] [rbp+77h]
  _QWORD *v46; // [rsp+E8h] [rbp+77h]
  volatile signed __int32 **v47; // [rsp+E8h] [rbp+77h]
  _QWORD *v48; // [rsp+F0h] [rbp+7Fh]
  __int64 v49; // [rsp+F0h] [rbp+7Fh]

  v3 = this;
  *(_QWORD *)&v40 = 0;
  v41 = 0;
  if ( !*((_BYTE *)a2 + 54) )
    return;
  if ( !*((_BYTE *)this + 54) )
  {
    if ( this != a2 )
    {
      CmsHashTableLite::operator=();
      *(_QWORD *)(v18 + 32) = *(_QWORD *)(v17 + 32);
      *(_DWORD *)(v18 + 48) = *(_DWORD *)(v17 + 48);
      *(_BYTE *)(v18 + 52) = *(_BYTE *)(v17 + 52);
      *(_BYTE *)(v18 + 54) = *(_BYTE *)(v17 + 54);
      *(_BYTE *)(v18 + 53) = *(_BYTE *)(v17 + 53);
      *(_QWORD *)(v17 + 32) = 0;
      *(_BYTE *)(v17 + 54) = 0;
    }
    return;
  }
  v4 = 0;
  v5 = 0;
  v6 = 0;
  v43 = 0;
  while ( 2 )
  {
    if ( v5 == 1 )
    {
      v7 = 0;
      if ( *((_QWORD *)a2 + 2 * v6) )
      {
        v12 = 0;
        while ( 1 )
        {
          if ( !v12 )
            v12 = (__int64 *)(*((_QWORD *)a2 + 2 * v6) + 24LL * v4);
          if ( *v12 != *(_QWORD *)v40 )
            break;
          if ( ++v4 == *((_DWORD *)a2 + 4 * v6 + 2) )
          {
            if ( v6 || !*((_QWORD *)a2 + 2) )
              goto LABEL_44;
            v6 = 1;
            v4 = 0;
          }
          if ( !v4 )
            v4 = 0;
          while ( 1 )
          {
            v13 = *((_QWORD *)a2 + 2 * v6);
            v11 = *(_QWORD *)(v13 + 24LL * v4 + 8) == 0;
            v12 = (__int64 *)(v13 + 24LL * v4);
            if ( !v11 )
              break;
            if ( ++v4 == -1 || v4 == *((_DWORD *)a2 + 4 * v6 + 2) )
            {
              if ( v6 || !*((_QWORD *)a2 + 2) )
              {
                v7 = 0;
LABEL_44:
                v16 = -1073741197;
                goto LABEL_39;
              }
              v6 = 1;
              v4 = 0;
            }
          }
          v7 = *v12;
          if ( *v12 )
            goto LABEL_45;
        }
        v7 = *(_QWORD *)v40;
      }
LABEL_45:
      v16 = -1073741197;
      if ( v7 )
        v16 = 0;
      goto LABEL_39;
    }
    v6 = 0;
    v43 = 1;
    if ( !(*((_DWORD *)a2 + 3) + *((_DWORD *)a2 + 7)) )
    {
      v14 = *((_QWORD *)a2 + 2);
      v15 = 12;
      v16 = -1073741197;
      LOBYTE(v6) = v14 != 0;
      if ( v14 )
        v15 = 28;
      v4 = *(_DWORD *)((char *)a2 + v15);
      goto LABEL_40;
    }
    v7 = 0;
    v4 = 0;
    if ( !*(_QWORD *)a2 )
      goto LABEL_38;
    v8 = 1;
    v9 = 0;
    while ( 1 )
    {
      if ( (v8 & 4) == 0 )
        goto LABEL_9;
      if ( !v9 )
        v9 = (__int64 *)(*((_QWORD *)a2 + 2 * v6) + 24LL * v4);
      if ( *v9 != *(_QWORD *)v40 )
        break;
      if ( ++v4 == *((_DWORD *)a2 + 4 * v6 + 2) )
      {
        if ( v6 || !*((_QWORD *)a2 + 2) )
          goto LABEL_38;
        v6 = 1;
        v4 = 0;
      }
LABEL_9:
      if ( !v4 )
        v4 = 0;
      while ( 1 )
      {
        v10 = *((_QWORD *)a2 + 2 * v6);
        v11 = *(_QWORD *)(v10 + 24LL * v4 + 8) == 0;
        v9 = (__int64 *)(v10 + 24LL * v4);
        if ( !v11 )
          break;
        if ( ++v4 == -1 || v4 == *((_DWORD *)a2 + 4 * v6 + 2) )
        {
          if ( v6 || !*((_QWORD *)a2 + 2) )
          {
            v7 = 0;
            goto LABEL_38;
          }
          v6 = 1;
          v4 = 0;
        }
      }
      v7 = *v9;
      if ( *v9 )
        goto LABEL_85;
      v8 |= 4u;
    }
    v7 = *(_QWORD *)v40;
    if ( *(_QWORD *)v40 )
    {
LABEL_85:
      v16 = 0;
      goto LABEL_39;
    }
LABEL_38:
    v16 = -1073741197;
LABEL_39:
    *(_QWORD *)&v40 = v7;
LABEL_40:
    *((_QWORD *)&v40 + 1) = __PAIR64__(v4, v6);
    if ( (_QWORD)v41 )
    {
      v44 = *(_QWORD *)(v41 + 16);
      v19 = (_QWORD *)(*(_QWORD *)v3
                     + 24
                     * ((((unsigned int)(1103515245 * v44 + 12345) >> 16)
                       | (unsigned __int64)((69069 * (_DWORD)v44 + 1) & 0xFFFF0000))
                      % *((unsigned int *)v3 + 2)));
      v20 = v19 + 2;
      ExAcquirePushLockSharedEx(v19 + 2, 4);
      if ( v19[1] )
      {
        v21 = (volatile signed __int32 *)*v19;
        v22 = (volatile signed __int32 *)*v19;
        while ( *((_QWORD *)v22 + 2) != v44 )
        {
          v22 = *(volatile signed __int32 **)v22;
          if ( v22 == v21 )
            goto LABEL_57;
        }
        ExReleasePushLockEx(v20, 0);
        v23 = *(signed __int64 **)(v41 + 32);
        if ( v23 )
        {
          _m_prefetchw((const void *)(v22 + 6));
          do
          {
            v35 = *((_QWORD *)v22 + 3);
            *v23 = v35;
            v36 = _InterlockedCompareExchange64((volatile signed __int64 *)v22 + 3, *(_QWORD *)(v41 + 24), v35);
          }
          while ( v36 != *v23 );
          if ( !v36 )
            *((_QWORD *)v22 + 4) = *(_QWORD *)(v41 + 32);
          if ( (*(_DWORD *)(v41 + 44) & 1) != 0 )
            _InterlockedOr(v22 + 11, 1u);
          _InterlockedAdd(v22 + 10, *(_DWORD *)(v41 + 40));
          _InterlockedAdd64((volatile signed __int64 *)this + 4, *(int *)(v41 + 40));
          *(_QWORD *)(v41 + 24) = 0;
          *(_QWORD *)(v41 + 32) = 0;
          *(_QWORD *)(v41 + 40) = 0;
        }
      }
      else
      {
LABEL_57:
        ExReleasePushLockEx(v20, 0);
        v22 = (volatile signed __int32 *)v41;
      }
      v45 = (_QWORD *)(*((_QWORD *)a2 + 2 * DWORD2(v41)) + 24LL * HIDWORD(v41));
      ExAcquirePushLockExclusiveEx(v45 + 2, 0);
      v24 = *(_QWORD **)(v41 + 8);
      v25 = *(_QWORD *)v41;
      *v24 = *(_QWORD *)v41;
      *(_QWORD *)(v25 + 8) = v24;
      if ( *v45 == (_QWORD)v41 )
        *v45 = v25;
      if ( v24 == (_QWORD *)v41 )
        *v45 = 0;
      --v45[1];
      _InterlockedDecrement((volatile signed __int32 *)a2 + 4 * DWORD2(v41) + 3);
      ExReleasePushLockEx(v45 + 2, 0);
      if ( v22 == (volatile signed __int32 *)v41 )
      {
        v39 = *(_QWORD *)(v41 + 16);
        v48 = (_QWORD *)(*(_QWORD *)this
                       + 24
                       * (((69069 * (_DWORD)v39 + 1) & 0xFFFF0000
                         | (unsigned __int64)((unsigned int)(1103515245 * v39 + 12345) >> 16))
                        % *((unsigned int *)this + 2)));
        v46 = v48 + 2;
        ExAcquirePushLockExclusiveEx(v48 + 2, 0);
        if ( v48[1] )
        {
          v33 = (_QWORD *)*v48;
          while ( v33[2] != v39 )
          {
            v33 = (_QWORD *)*v33;
            if ( v33 == (_QWORD *)*v48 )
              goto LABEL_78;
          }
          ExReleasePushLockEx(v46, 0);
          v49 = *(_QWORD *)(v41 + 16);
          v47 = (volatile signed __int32 **)(*(_QWORD *)this
                                           + 24
                                           * (((69069 * (_DWORD)v49 + 1) & 0xFFFF0000
                                             | (unsigned __int64)((unsigned int)(1103515245 * v49 + 12345) >> 16))
                                            % *((unsigned int *)this + 2)));
          ExAcquirePushLockSharedEx(v47 + 2, 4);
          if ( v47[1] )
          {
            v31 = *v47;
            while ( *((_QWORD *)v31 + 2) != v49 )
            {
              v31 = *(volatile signed __int32 **)v31;
              if ( v31 == *v47 )
                goto LABEL_92;
            }
            v22 = v31;
          }
LABEL_92:
          ExReleasePushLockEx(v47 + 2, 0);
          v32 = *(signed __int64 **)(v41 + 32);
          if ( v32 )
          {
            _m_prefetchw((const void *)(v22 + 6));
            do
            {
              v37 = *((_QWORD *)v22 + 3);
              *v32 = v37;
              v38 = _InterlockedCompareExchange64((volatile signed __int64 *)v22 + 3, *(_QWORD *)(v41 + 24), v37);
            }
            while ( v38 != *v32 );
            if ( !v38 )
              *((_QWORD *)v22 + 4) = *(_QWORD *)(v41 + 32);
            if ( (*(_DWORD *)(v41 + 44) & 1) != 0 )
              _InterlockedOr(v22 + 11, 1u);
            _InterlockedAdd(v22 + 10, *(_DWORD *)(v41 + 40));
            v3 = this;
            _InterlockedAdd64((volatile signed __int64 *)this + 4, *(int *)(v41 + 40));
            *(_QWORD *)(v41 + 24) = 0;
            *(_QWORD *)(v41 + 32) = 0;
            *(_QWORD *)(v41 + 40) = 0;
          }
          else
          {
            v3 = this;
          }
          CmsLookasides::Free((_QWORD *)v41);
        }
        else
        {
LABEL_78:
          v29 = (_QWORD *)*v48;
          if ( *v48 )
          {
            v30 = (_QWORD *)v29[1];
            if ( (_QWORD *)*v30 != v29 )
              __fastfail(3u);
            *(_QWORD *)v41 = v29;
            *(_QWORD *)(v41 + 8) = v30;
            *v30 = v41;
            v29[1] = v41;
          }
          else
          {
            *(_QWORD *)(v41 + 8) = v41;
            *(_QWORD *)v41 = v41;
            *v48 = v41;
          }
          ++v48[1];
          v3 = this;
          _InterlockedIncrement((volatile signed __int32 *)this + 3);
          ExReleasePushLockEx(v46, 0);
          _InterlockedAdd64((volatile signed __int64 *)this + 4, *(int *)(v41 + 40));
        }
        goto LABEL_41;
      }
      v26 = *(_QWORD *)(v41 - 16);
      v27 = (struct _SLIST_ENTRY *)(v41 - 16);
      if ( v26 )
      {
        if ( *(_BYTE *)(v26 + 8) )
        {
          v28 = (struct _PAGED_LOOKASIDE_LIST *)(v26 + 64);
          if ( !*(_BYTE *)(v26 + 9) )
          {
            ExFreeToPagedLookasideList(v28, v27);
            v3 = this;
            goto LABEL_41;
          }
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)v28, v27);
LABEL_68:
          v3 = this;
          goto LABEL_41;
        }
        v34 = *(_QWORD *)(v26 + 88);
        if ( (int)v34 < *(_DWORD *)(v26 + 80) || SHIDWORD(v34) >= (int)v34 )
        {
          ExpInterlockedPushEntrySList((PSLIST_HEADER)(v26 + 64), v27);
          _InterlockedIncrement((volatile signed __int32 *)(v26 + 88));
          goto LABEL_68;
        }
      }
      ExFreePoolWithTag(v27, 0);
      goto LABEL_68;
    }
LABEL_41:
    v41 = v40;
    if ( !v16 )
    {
      v5 = v43;
      continue;
    }
    break;
  }
  v11 = *((_BYTE *)a2 + 53) == 0;
  *((_QWORD *)a2 + 4) = 0;
  if ( !v11 )
    CmsContainerRangeMap::UninitializeMap(a2);
}

```

## disassembly

```asm
0x14002eaa0  mov     rax, rsp
0x14002eaa3  mov     [rax+8], rcx
0x14002eaa7  push    rbp
0x14002eaa8  push    rsi
0x14002eaa9  push    r12
0x14002eaab  lea     rbp, [rax-5Fh]
0x14002eaaf  sub     rsp, 0B0h
0x14002eab6  cmp     byte ptr [rdx+36h], 0
0x14002eaba  xorps   xmm0, xmm0
0x14002eabd  movaps  xmmword ptr [rax-58h], xmm6
0x14002eac1  mov     rsi, rdx
0x14002eac4  xorps   xmm6, xmm6
0x14002eac7  mov     r12, rcx
0x14002eaca  movups  [rbp+57h+var_90], xmm6
0x14002eace  movups  [rbp+57h+var_80], xmm6
0x14002ead2  movups  [rbp+57h+var_70], xmm0
0x14002ead6  jz      loc_14002EBEF
0x14002eadc  cmp     byte ptr [rcx+36h], 0
0x14002eae0  jz      loc_14002ED2F
0x14002eae6  mov     [rax-20h], rbx
0x14002eaea  xor     r10d, r10d
0x14002eaed  mov     ebx, dword ptr [rbp+57h+var_90+0Ch]
0x14002eaf0  mov     r9d, r10d
0x14002eaf3  mov     [rax-28h], rdi
0x14002eaf7  mov     edi, dword ptr [rbp+57h+var_90+8]
0x14002eafa  mov     [rax-30h], r13
0x14002eafe  mov     [rax-38h], r14
0x14002eb02  mov     [rax-40h], r15
0x14002eb06  mov     [rbp+57h+arg_8], r10d
0x14002eb0a  mov     edx, 1Ch
0x14002eb0f  cmp     r9d, 1
0x14002eb13  jz      loc_14002EC01
0x14002eb19  mov     eax, [rsi+1Ch]
0x14002eb1c  mov     edi, r10d
0x14002eb1f  mov     [rbp+57h+arg_8], 1
0x14002eb26  add     eax, [rsi+0Ch]
0x14002eb29  jz      loc_14002EC91
0x14002eb2f  cmp     qword ptr [rsi], 0
0x14002eb33  mov     rdx, r10
0x14002eb36  mov     qword ptr [rbp+57h+var_90+8], 0
0x14002eb3e  mov     ebx, r10d
0x14002eb41  mov     qword ptr [rbp+57h+var_80], r10
0x14002eb45  jz      loc_14002ECB6
0x14002eb4b  mov     r11, qword ptr [rbp+57h+var_90]
0x14002eb4f  mov     r9d, 1
0x14002eb55  mov     rax, r10
0x14002eb58  test    r9b, 4
0x14002eb5c  jnz     loc_14002EF76
0x14002eb62  test    ebx, ebx
0x14002eb64  cmovz   ebx, r10d
0x14002eb68  nop     dword ptr [rax+rax+00000000h]
0x14002eb70  mov     eax, ebx
0x14002eb72  mov     edx, edi
0x14002eb74  add     rdx, rdx
0x14002eb77  lea     rcx, [rax+rax*2]
0x14002eb7b  mov     rax, [rsi+rdx*8]
0x14002eb7f  cmp     qword ptr [rax+rcx*8+8], 0
0x14002eb85  lea     rax, [rax+rcx*8]
0x14002eb89  jnz     loc_14002ED1A
0x14002eb8f  inc     ebx
0x14002eb91  cmp     ebx, 0FFFFFFFFh
0x14002eb94  jnb     short loc_14002EB9C
0x14002eb96  cmp     ebx, [rsi+rdx*8+8]
0x14002eb9a  jnz     short loc_14002EB70
0x14002eb9c  test    edi, edi
0x14002eb9e  jnz     loc_14002ECB3
0x14002eba4  cmp     qword ptr [rsi+10h], 0
0x14002eba9  jz      loc_14002ECB3
0x14002ebaf  mov     edi, 1
0x14002ebb4  mov     ebx, r10d
0x14002ebb7  jmp     short loc_14002EB70
0x14002ebb9  cmp     byte ptr [rsi+35h], 0
0x14002ebbd  mov     [rsi+20h], r10
0x14002ebc1  jnz     loc_14002F265
0x14002ebc7  mov     r15, [rsp+0C0h+var_38]
0x14002ebcf  mov     r13, [rsp+0C0h+var_28]
0x14002ebd7  mov     rdi, [rsp+0C0h+var_20]
0x14002ebdf  mov     rbx, [rsp+0A8h]
0x14002ebe7  mov     r14, [rsp+0C0h+var_30]
0x14002ebef  movaps  xmm6, [rsp+0C0h+var_58+8]
0x14002ebf4  add     rsp, 0B0h
0x14002ebfb  pop     r12
0x14002ebfd  pop     rsi
0x14002ebfe  pop     rbp
0x14002ebff  retn
0x14002ec01  mov     eax, edi
0x14002ec03  mov     rdx, r10
0x14002ec06  add     rax, rax
0x14002ec09  cmp     qword ptr [rsi+rax*8], 0
0x14002ec0e  jz      loc_14002ECFC
0x14002ec14  mov     r11, qword ptr [rbp+57h+var_90]
0x14002ec18  mov     rax, r10
0x14002ec1b  mov     r8d, edi
0x14002ec1e  add     r8, r8
0x14002ec21  test    rax, rax
0x14002ec24  jz      loc_14002F1B7
0x14002ec2a  mov     rcx, [r11]
0x14002ec2d  cmp     [rax], rcx
0x14002ec30  jnz     loc_14002F1EA
0x14002ec36  inc     ebx
0x14002ec38  cmp     ebx, [rsi+r8*8+8]
0x14002ec3d  jz      loc_14002F1CA
0x14002ec43  test    ebx, ebx
0x14002ec45  cmovz   ebx, r10d
0x14002ec49  nop     dword ptr [rax+00000000h]
0x14002ec50  mov     eax, ebx
0x14002ec52  mov     edx, edi
0x14002ec54  add     rdx, rdx
0x14002ec57  lea     rcx, [rax+rax*2]
0x14002ec5b  mov     rax, [rsi+rdx*8]
0x14002ec5f  cmp     qword ptr [rax+rcx*8+8], 0
0x14002ec65  lea     rax, [rax+rcx*8]
0x14002ec69  jnz     loc_14002ED0C
0x14002ec6f  inc     ebx
0x14002ec71  cmp     ebx, 0FFFFFFFFh
0x14002ec74  jnb     short loc_14002EC7C
0x14002ec76  cmp     ebx, [rsi+rdx*8+8]
0x14002ec7a  jnz     short loc_14002EC50
0x14002ec7c  test    edi, edi
0x14002ec7e  jnz     short loc_14002ECF1
0x14002ec80  cmp     qword ptr [rsi+10h], 0
0x14002ec85  jz      short loc_14002ECF1
0x14002ec87  mov     edi, 1
0x14002ec8c  mov     ebx, r10d
0x14002ec8f  jmp     short loc_14002EC50
0x14002ec91  mov     rcx, [rsi+10h]
0x14002ec95  mov     eax, 0Ch
0x14002ec9a  test    rcx, rcx
0x14002ec9d  mov     r15d, 0C0000273h
0x14002eca3  setnz   dil
0x14002eca7  test    rcx, rcx
0x14002ecaa  cmovnz  rax, rdx
0x14002ecae  mov     ebx, [rax+rsi]
0x14002ecb1  jmp     short loc_14002ECC4
0x14002ecb3  mov     rdx, r10
0x14002ecb6  mov     r15d, 0C0000273h
0x14002ecbc  movups  xmm6, [rbp+57h+var_80]
0x14002ecc0  mov     qword ptr [rbp+57h+var_90], rdx
0x14002ecc4  mov     r14, qword ptr [rbp+57h+var_70]
0x14002ecc8  mov     dword ptr [rbp+57h+var_90+8], edi
0x14002eccb  mov     dword ptr [rbp+57h+var_90+0Ch], ebx
0x14002ecce  test    r14, r14
0x14002ecd1  jnz     loc_14002ED71
0x14002ecd7  movups  xmm0, [rbp+57h+var_90]
0x14002ecdb  movups  [rbp+57h+var_70], xmm0
0x14002ecdf  test    r15d, r15d
0x14002ece2  jnz     loc_14002EBB9
0x14002ece8  mov     r9d, [rbp+57h+arg_8]
0x14002ecec  jmp     loc_14002EB0A
0x14002ecf1  mov     rdx, r10
0x14002ecf4  mov     r15d, 0C0000273h
0x14002ecfa  jmp     short loc_14002ECC0
0x14002ecfc  mov     r15d, 0C0000273h
0x14002ed02  test    rdx, rdx
0x14002ed05  jz      short loc_14002ECC0
0x14002ed07  mov     r15d, r10d
0x14002ed0a  jmp     short loc_14002ECC0
0x14002ed0c  mov     rdx, [rax]
0x14002ed0f  test    rdx, rdx
0x14002ed12  jz      loc_14002EC1B
0x14002ed18  jmp     short loc_14002ECFC
0x14002ed1a  mov     rdx, [rax]
0x14002ed1d  test    rdx, rdx
0x14002ed20  jnz     loc_14002F0EE
0x14002ed26  or      r9d, 4
0x14002ed2a  jmp     loc_14002EB58
0x14002ed2f  cmp     rcx, rsi
0x14002ed32  jz      loc_14002EBEF
0x14002ed38  call    ??4CmsHashTableLite@@QEAAAEAV0@$$QEAV0@@Z; CmsHashTableLite::operator=(CmsHashTableLite &&)
0x14002ed3d  mov     rax, [rdx+20h]
0x14002ed41  mov     [rcx+20h], rax
0x14002ed45  mov     eax, [rdx+30h]
0x14002ed48  mov     [rcx+30h], eax
0x14002ed4b  movzx   eax, byte ptr [rdx+34h]
0x14002ed4f  mov     [rcx+34h], al
0x14002ed52  movzx   eax, byte ptr [rdx+36h]
0x14002ed56  mov     [rcx+36h], al
0x14002ed59  movzx   eax, byte ptr [rdx+35h]
0x14002ed5d  mov     [rcx+35h], al
0x14002ed60  mov     qword ptr [rdx+20h], 0
0x14002ed68  mov     byte ptr [rdx+36h], 0
0x14002ed6c  jmp     loc_14002EBEF
0x14002ed71  mov     rcx, [r14+10h]
0x14002ed75  xor     edx, edx
0x14002ed77  imul    eax, ecx, 10DCDh
0x14002ed7d  mov     [rbp+57h+arg_10], rcx
0x14002ed81  imul    ecx, 41C64E6Dh
0x14002ed87  inc     eax
0x14002ed89  and     eax, 0FFFF0000h
0x14002ed8e  add     ecx, 3039h
0x14002ed94  shr     ecx, 10h
0x14002ed97  or      eax, ecx
0x14002ed99  div     dword ptr [r12+8]
0x14002ed9e  mov     rax, [r12]
0x14002eda2  lea     rdx, [rdx+rdx*2]
0x14002eda6  lea     r12, [rax+rdx*8]
0x14002edaa  mov     edx, 4
0x14002edaf  lea     r13, [r12+10h]
0x14002edb4  mov     rcx, r13
0x14002edb7  call    cs:__imp_ExAcquirePushLockSharedEx
0x14002edbe  nop     dword ptr [rax+rax+00h]
0x14002edc3  cmp     qword ptr [r12+8], 0
0x14002edc9  jbe     short loc_14002EDE6
0x14002edcb  mov     rax, [r12]
0x14002edcf  mov     rcx, [rbp+57h+arg_10]
0x14002edd3  mov     r12, rax
0x14002edd6  cmp     [r12+10h], rcx
0x14002eddb  jz      short loc_14002EDFC
0x14002eddd  mov     r12, [r12]
0x14002ede1  cmp     r12, rax
0x14002ede4  jnz     short loc_14002EDD6
0x14002ede6  xor     edx, edx
0x14002ede8  mov     rcx, r13
0x14002edeb  call    cs:__imp_ExReleasePushLockEx
0x14002edf2  nop     dword ptr [rax+rax+00h]
0x14002edf7  mov     r12, r14
0x14002edfa  jmp     short loc_14002EE1A
0x14002edfc  xor     edx, edx
0x14002edfe  mov     rcx, r13
0x14002ee01  call    cs:__imp_ExReleasePushLockEx
0x14002ee08  nop     dword ptr [rax+rax+00h]
0x14002ee0d  mov     rdx, [r14+20h]
0x14002ee11  test    rdx, rdx
0x14002ee14  jnz     loc_14002F20D
0x14002ee1a  mov     rax, [r14+10h]
0x14002ee1e  mov     [rbp+57h+arg_18], rax
0x14002ee22  mov     rax, qword ptr [rbp+57h+var_70+8]
0x14002ee26  mov     edx, eax
0x14002ee28  add     rdx, rdx
0x14002ee2b  mov     [rbp+57h+var_A0], rax
0x14002ee2f  mov     eax, dword ptr [rbp+57h+var_70+0Ch]
0x14002ee32  lea     rcx, [rax+rax*2]
0x14002ee36  mov     rax, [rsi+rdx*8]
0x14002ee3a  lea     rdx, [rax+rcx*8]
0x14002ee3e  mov     [rbp+57h+arg_10], rdx
0x14002ee42  lea     rcx, [rdx+10h]
0x14002ee46  xor     edx, edx
0x14002ee48  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002ee4f  nop     dword ptr [rax+rax+00h]
0x14002ee54  mov     r13, r14
0x14002ee57  test    r14, r14
0x14002ee5a  jnz     loc_14002F0BC
0x14002ee60  mov     rcx, [rbp+57h+arg_18]
0x14002ee64  xor     edx, edx
0x14002ee66  imul    eax, ecx, 10DCDh
0x14002ee6c  imul    ecx, 41C64E6Dh
0x14002ee72  mov     dword ptr [rbp+57h+var_A0], r14d
0x14002ee76  inc     eax
0x14002ee78  and     eax, 0FFFF0000h
0x14002ee7d  add     ecx, 3039h
0x14002ee83  shr     ecx, 10h
0x14002ee86  or      eax, ecx
0x14002ee88  div     dword ptr [rsi+8]
0x14002ee8b  mov     rax, [rsi]
0x14002ee8e  lea     rdx, [rdx+rdx*2]
0x14002ee92  lea     rdx, [rax+rdx*8]
0x14002ee96  lea     rax, [rdx+10h]
0x14002ee9a  mov     [rbp+57h+arg_10], rdx
0x14002ee9e  mov     rcx, rax
0x14002eea1  mov     [rbp+57h+var_98], rax
0x14002eea5  xor     edx, edx
0x14002eea7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14002eeae  nop     dword ptr [rax+rax+00h]
0x14002eeb3  mov     rcx, [rbp+57h+arg_10]
0x14002eeb7  cmp     [rcx+8], r14
0x14002eebb  jbe     loc_14002EFCB
0x14002eec1  mov     rax, [rcx]
0x14002eec4  mov     rdx, [rbp+57h+arg_18]
0x14002eec8  mov     r13, rax
0x14002eecb  cmp     [r13+10h], rdx
0x14002eecf  jnz     loc_14002EFBE
0x14002eed5  test    r13, r13
0x14002eed8  jz      loc_14002EFDD
0x14002eede  mov     rdx, [r13+8]
0x14002eee2  mov     rax, [r13+0]
0x14002eee6  mov     [rdx], rax
0x14002eee9  mov     [rax+8], rdx
0x14002eeed  cmp     [rcx], r13
0x14002eef0  jnz     short loc_14002EEF5
0x14002eef2  mov     [rcx], rax
0x14002eef5  cmp     rdx, r13
0x14002eef8  jz      loc_14002EFFD
0x14002eefe  dec     qword ptr [rcx+8]
0x14002ef02  xor     edx, edx
0x14002ef04  mov     eax, dword ptr [rbp+57h+var_A0]
0x14002ef07  nop
0x14002ef08  shl     rax, 4
0x14002ef0c  add     rcx, 10h
0x14002ef10  lock dec dword ptr [rax+rsi+0Ch]
0x14002ef15  nop
0x14002ef16  call    cs:__imp_ExReleasePushLockEx
0x14002ef1d  nop     dword ptr [rax+rax+00h]
0x14002ef22  cmp     r12, r14
0x14002ef25  jz      loc_14002F009
0x14002ef2b  test    r13, r13
0x14002ef2e  jz      short loc_14002EF6A
0x14002ef30  mov     r14, [r13-10h]
0x14002ef34  add     r13, 0FFFFFFFFFFFFFFF0h
0x14002ef38  test    r14, r14
0x14002ef3b  jz      loc_14002F24F
  ... truncated ...
```

# DirectComposition::CBatch::EnsureBatchBuffer(DirectComposition::CBatch * *,unsigned __int64,void * *)

- ea: `0x14004ba30`
- end: `0x14004be98`
- name: `?EnsureBatchBuffer@CBatch@DirectComposition@@SA_NPEAPEAV12@_KPEAPEAX@Z`
- size: `1128`
- prototype: `bool __fastcall(struct DirectComposition::CBatch **, unsigned __int64, void **)`
- caller_count: `577`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002b7d0`
- `0x14004b8b8`
- `0x14004c12c`
- `0x14004c298`
- `0x14004cc64`
- `0x14004cce4`
- `0x14004cf60`
- `0x14004d050`
- `0x14004d0d8`
- `0x14004d200`
- `0x14004d588`
- `0x14004d61c`
- `0x14004d678`
- `0x14004d714`
- `0x14004d900`
- `0x14004daec`
- `0x14004db70`
- `0x14004e354`
- `0x14004e668`
- `0x14004e6fc`
- `0x14004e78c`
- `0x1400eb4bc`
- `0x1400ebd50`
- `0x1400ec9f0`
- `0x1400eca80`
- `0x1400ecb80`
- `0x1400ecbe8`
- `0x1400ecc44`
- `0x1400eccb0`
- `0x1400ecd18`
- `0x1400ecd74`
- `0x1400ecdd0`
- `0x1400ece30`
- `0x1400ecf74`
- `0x1400ecff8`
- `0x1400ed0c4`
- `0x1400f0ae0`
- `0x1400f10a8`
- `0x1400f1124`
- `0x1400f11a4`
- `0x1400f1220`
- `0x1400f12a4`
- `0x1400f1358`
- `0x1400f13d8`
- `0x1400f1460`
- `0x1400f14e4`
- `0x1400f1564`
- `0x1400f15e4`
- `0x1400f166c`
- `0x1400f16ec`

## callees

- `0x14004b148`
- `0x14004b720`
- `0x14004ba30`
- `0x14004bea0`
- `0x1400bdd00`
- `0x14021cb1c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14004bd1b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004bd1b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004bd71`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004bd71`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004be02`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004be02`
- `ntoskrnl!KeResetEvent` at `0x14004bac4`
- `ntoskrnl!KeResetEvent` at `0x14004bd52`
- `ntoskrnl!KeResetEvent` at `0x14004bac4`
- `ntoskrnl!KeResetEvent` at `0x14004bd52`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004bd2c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004bd2c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004bad7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004bd01`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004bad7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14004bd01`
- `ntoskrnl!KeBugCheck` at `0x14004bcab`
- `ntoskrnl!KeBugCheck` at `0x14004bcab`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bd65`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004bd65`

## pseudocode

```c
char __fastcall DirectComposition::CBatch::EnsureBatchBuffer(
        struct DirectComposition::CBatch **a1,
        unsigned __int64 a2,
        void **a3)
{
  _QWORD *v5; // rdx
  __int64 v7; // r9
  __int64 v8; // r10
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  void *v11; // rcx
  struct DirectComposition::CBatch *v12; // rdi
  __int64 v13; // rsi
  PSLIST_ENTRY i; // rbx
  struct DirectComposition::CBatch *v15; // rdx
  struct DirectComposition::CBatchSharedMemoryPool *v16; // r14
  struct DirectComposition::CBatchSharedMemoryPool *j; // rbx
  __int64 v18; // r15
  struct DirectComposition::CBatchSharedMemoryPool **v19; // rax
  struct DirectComposition::CBatchSharedMemoryPool *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rcx
  struct _ERESOURCE *v23; // rbx
  struct DirectComposition::CBatch **v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rdx
  unsigned __int64 v27; // rbp
  __int64 v28; // r8
  void *v29; // r8
  struct _SLIST_ENTRY *Next; // rax
  char v32; // di
  char v33; // al
  struct DirectComposition::CBatch *v34; // [rsp+30h] [rbp-58h] BYREF
  struct DirectComposition::CBatchSharedMemoryPool *v35; // [rsp+38h] [rbp-50h] BYREF
  _QWORD *v36; // [rsp+40h] [rbp-48h]
  char v38; // [rsp+A0h] [rbp+18h]
  int v39; // [rsp+A8h] [rbp+20h]

  v5 = *a1;
  v7 = *((_QWORD *)*a1 + 17);
  v8 = *(_QWORD *)(v7 + 40);
  v9 = 4096 - v8;
  if ( a3 )
  {
    if ( a2 <= v9 )
    {
      v10 = *(_QWORD *)(v7 + 56);
      *(_QWORD *)(v7 + 40) = v8 + a2;
      v11 = (void *)(v8 + v10);
      if ( v11 )
      {
        *a3 = v11;
        v5[19] += a2;
        return 1;
      }
    }
  }
  else if ( a2 <= v9 )
  {
    return 1;
  }
  v36 = *a1;
  v12 = 0;
  v34 = 0;
  v13 = v36[1];
  v39 = *((_DWORD *)v36 + 4);
  v38 = *((_BYTE *)v36 + 32);
  KeResetEvent(*(PRKEVENT *)(*(_QWORD *)(v13 + 240) + 8LL));
  for ( i = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v13 + 208));
        i;
        i = ExpInterlockedPopEntrySList((PSLIST_HEADER)(v13 + 208)) )
  {
    --*(_DWORD *)(v13 + 252);
    Next = i[4].Next;
    if ( (unsigned __int64)Next > *(_QWORD *)(v13 + 256) )
    {
      *(_BYTE *)(v13 + 264) |= 2u;
      *(_QWORD *)(v13 + 256) = Next;
    }
    DirectComposition::CBatch::Clear((DirectComposition::CBatch *)i);
    i->Next = *(struct _SLIST_ENTRY **)(v13 + 200);
    *(_QWORD *)(v13 + 200) = i;
  }
  v15 = *(struct DirectComposition::CBatch **)(v13 + 184);
  if ( v15 )
  {
    v12 = *(struct DirectComposition::CBatch **)(v13 + 184);
    *(_QWORD *)(v13 + 184) = 0;
LABEL_25:
    *((_DWORD *)v15 + 4) = v39;
    *((_BYTE *)v15 + 32) ^= (v38 ^ *((_BYTE *)v15 + 32)) & 1;
    *(_QWORD *)v12 = 0;
    ++*(_DWORD *)(v13 + 252);
    *(_BYTE *)(v13 + 264) |= 8u;
    v23 = *(struct _ERESOURCE **)(v13 + 392);
    if ( v23 )
    {
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(v23, 1u);
      if ( ++*(_DWORD *)(v13 + 248) == 1 )
        KeResetEvent(*(PRKEVENT *)(*(_QWORD *)(v13 + 384) + 8LL));
      ExReleaseResourceLite(*(PERESOURCE *)(v13 + 392));
      KeLeaveCriticalRegion();
    }
  }
  else
  {
    v16 = (struct DirectComposition::CBatchSharedMemoryPool *)(v13 + 2648);
    v35 = 0;
    for ( j = *(struct DirectComposition::CBatchSharedMemoryPool **)(v13 + 2648);
          ;
          j = *(struct DirectComposition::CBatchSharedMemoryPool **)j )
    {
      if ( j == v16 )
      {
        if ( (int)DirectComposition::CBatchSharedMemoryPool::Create(
                    (struct DirectComposition::CBatchSharedMemoryPoolSet *)(v13 + 2648),
                    *(_BYTE *)(v13 + 2672),
                    &v35) < 0 )
          goto LABEL_26;
        j = v35;
        v18 = 0;
        if ( !*((_BYTE *)v35 + 64) && (unsigned __int64)(4096LL - *((_QWORD *)v35 + 5)) >= 0x228 )
        {
          v18 = *((_QWORD *)v35 + 5);
          *((_BYTE *)v35 + 64) = 1;
        }
        v21 = *(_QWORD *)v16;
        if ( *(struct DirectComposition::CBatchSharedMemoryPool **)(*(_QWORD *)v16 + 8LL) != v16 )
LABEL_15:
          __fastfail(3u);
        goto LABEL_17;
      }
      if ( !*((_BYTE *)j + 64) )
      {
        v18 = *((_QWORD *)j + 5);
        if ( (unsigned __int64)(4096 - v18) >= 0x228 )
          break;
      }
    }
    *((_BYTE *)j + 64) = 1;
    v19 = (struct DirectComposition::CBatchSharedMemoryPool **)*((_QWORD *)j + 1);
    if ( v19 == (struct DirectComposition::CBatchSharedMemoryPool **)v16 )
      goto LABEL_18;
    v20 = *(struct DirectComposition::CBatchSharedMemoryPool **)j;
    if ( *(struct DirectComposition::CBatchSharedMemoryPool **)(*(_QWORD *)j + 8LL) != j )
      goto LABEL_15;
    if ( *v19 != j )
      goto LABEL_15;
    *v19 = v20;
    *((_QWORD *)v20 + 1) = v19;
    v21 = *(_QWORD *)v16;
    if ( *(struct DirectComposition::CBatchSharedMemoryPool **)(*(_QWORD *)v16 + 8LL) != v16 )
      goto LABEL_15;
LABEL_17:
    *(_QWORD *)j = v21;
    *((_QWORD *)j + 1) = v16;
    *(_QWORD *)(v21 + 8) = j;
    *(_QWORD *)v16 = j;
LABEL_18:
    if ( !j )
      goto LABEL_26;
    v22 = *((_QWORD *)j + 5);
    if ( (unsigned __int64)(4096 - v22) >= 0x28 )
      *((_QWORD *)j + 5) = v22 + 40;
    v12 = *(struct DirectComposition::CBatch **)(v13 + 200);
    if ( v12 )
    {
      *(_QWORD *)(v13 + 200) = *(_QWORD *)v12;
    }
    else
    {
      if ( (int)DirectComposition::CApplicationChannel::CreateBatch((DirectComposition::CApplicationChannel *)v13, &v34) < 0
        && *(int *)(v13 + 252) > 0 )
      {
        v32 = 1;
        v33 = 0;
        while ( *(int *)(v13 + 252) > 0 )
        {
          if ( v33
            && DirectComposition::CConnection::ShouldWaitForReturnedBatches(*(DirectComposition::CConnection **)(v13 + 40))
            && KeWaitForSingleObject(*(PVOID *)(*(_QWORD *)(v13 + 240) + 8LL), UserRequest, 0, 1u, 0) )
          {
            v32 = 0;
          }
          if ( DirectComposition::CApplicationChannel::ProcessReturnedBatches((DirectComposition::CApplicationChannel *)v13) )
          {
            v12 = *(struct DirectComposition::CBatch **)(v13 + 200);
            *(_QWORD *)(v13 + 200) = *(_QWORD *)v12;
            goto LABEL_23;
          }
          v33 = 1;
          if ( !v32 )
            break;
        }
      }
      v12 = v34;
    }
LABEL_23:
    if ( v12 )
    {
      *((_QWORD *)v12 + 18) = v18;
      v15 = v12;
      *((_QWORD *)v12 + 17) = j;
      goto LABEL_25;
    }
    *((_BYTE *)j + 64) = 0;
  }
LABEL_26:
  if ( v12 )
  {
    v24 = (struct DirectComposition::CBatch **)v36;
    *(_BYTE *)(v36[17] + 64LL) = 0;
    *v24 = v12;
    *a1 = v12;
    v25 = *((_QWORD *)v12 + 17);
    v26 = *(_QWORD *)(v25 + 40);
    v27 = 4096 - v26;
    if ( a3 )
    {
      if ( a2 <= v27 )
      {
        v28 = *(_QWORD *)(v25 + 56);
        *(_QWORD *)(v25 + 40) = v26 + a2;
        v29 = (void *)(v26 + v28);
        if ( v29 )
        {
          *a3 = v29;
          *((_QWORD *)v12 + 19) += a2;
          return 1;
        }
      }
    }
    else if ( a2 <= v27 )
    {
      return 1;
    }
    KeBugCheck(0xC000000D);
  }
  return 0;
}

```

## disassembly

```asm
0x14004ba30  mov     [rsp+arg_8], rbx
0x14004ba35  mov     [rsp+arg_0], rcx
0x14004ba3a  push    rbp
0x14004ba3b  push    rsi
0x14004ba3c  push    rdi
0x14004ba3d  push    r12
0x14004ba3f  push    r13
0x14004ba41  push    r14
0x14004ba43  push    r15
0x14004ba45  sub     rsp, 50h
0x14004ba49  mov     r13, r8
0x14004ba4c  mov     r12, rdx
0x14004ba4f  mov     rdx, [rcx]
0x14004ba52  mov     ebp, 1000h
0x14004ba57  mov     eax, ebp
0x14004ba59  mov     r8, rcx
0x14004ba5c  mov     r9, [rdx+88h]
0x14004ba63  mov     r10, [r9+28h]
0x14004ba67  sub     rax, r10
0x14004ba6a  test    r13, r13
0x14004ba6d  jz      loc_14004BD82
0x14004ba73  cmp     r12, rax
0x14004ba76  ja      short loc_14004BA8D
0x14004ba78  mov     rcx, [r9+38h]
0x14004ba7c  lea     rax, [r10+r12]
0x14004ba80  mov     [r9+28h], rax
0x14004ba84  add     rcx, r10
0x14004ba87  jnz     loc_14004BB66
0x14004ba8d  mov     rax, [r8]
0x14004ba90  xor     r15d, r15d
0x14004ba93  mov     [rsp+88h+var_48], rax
0x14004ba98  mov     edi, r15d
0x14004ba9b  mov     [rsp+88h+var_58], r15
0x14004baa0  mov     ecx, [rax+10h]
0x14004baa3  mov     rsi, [rax+8]
0x14004baa7  movzx   eax, byte ptr [rax+20h]
0x14004baab  mov     [rsp+88h+arg_18], ecx
0x14004bab2  mov     [rsp+88h+arg_10], al
0x14004bab9  mov     rcx, [rsi+0F0h]
0x14004bac0  mov     rcx, [rcx+8]; Event
0x14004bac4  call    cs:__imp_KeResetEvent
0x14004bacb  nop     dword ptr [rax+rax+00h]
0x14004bad0  lea     rcx, [rsi+0D0h]; ListHead
0x14004bad7  call    cs:__imp_ExpInterlockedPopEntrySList
0x14004bade  nop     dword ptr [rax+rax+00h]
0x14004bae3  mov     rbx, rax
0x14004bae6  test    rax, rax
0x14004bae9  jnz     loc_14004BCC0
0x14004baef  mov     rdx, [rsi+0B8h]
0x14004baf6  test    rdx, rdx
0x14004baf9  jnz     loc_14004BC92
0x14004baff  lea     r14, [rsi+0A58h]
0x14004bb06  mov     [rsp+88h+var_50], r15
0x14004bb0b  mov     rbx, [r14]
0x14004bb0e  cmp     rbx, r14
0x14004bb11  jz      loc_14004BE2F
0x14004bb17  cmp     [rbx+40h], dil
0x14004bb1b  jnz     short loc_14004BB2F
0x14004bb1d  mov     r15, [rbx+28h]
0x14004bb21  mov     rax, rbp
0x14004bb24  sub     rax, r15
0x14004bb27  cmp     rax, 228h
0x14004bb2d  jnb     short loc_14004BB34
0x14004bb2f  mov     rbx, [rbx]
0x14004bb32  jmp     short loc_14004BB0E
0x14004bb34  mov     byte ptr [rbx+40h], 1
0x14004bb38  mov     rax, [rbx+8]
0x14004bb3c  cmp     rax, r14
0x14004bb3f  jz      short loc_14004BB84
0x14004bb41  mov     rcx, [rbx]
0x14004bb44  cmp     [rcx+8], rbx
0x14004bb48  jnz     short loc_14004BB5F
0x14004bb4a  cmp     [rax], rbx
0x14004bb4d  jnz     short loc_14004BB5F
0x14004bb4f  mov     [rax], rcx
0x14004bb52  mov     [rcx+8], rax
0x14004bb56  mov     rax, [r14]
0x14004bb59  cmp     [rax+8], r14
0x14004bb5d  jz      short loc_14004BB76
0x14004bb5f  mov     ecx, 3
0x14004bb64  int     29h; Win8: RtlFailFast(ecx)
0x14004bb66  mov     [r13+0], rcx
0x14004bb6a  add     [rdx+98h], r12
0x14004bb71  jmp     loc_14004BC77
0x14004bb76  mov     [rbx], rax
0x14004bb79  mov     [rbx+8], r14
0x14004bb7d  mov     [rax+8], rbx
0x14004bb81  mov     [r14], rbx
0x14004bb84  test    rbx, rbx
0x14004bb87  jz      loc_14004BC1C
0x14004bb8d  mov     rcx, [rbx+28h]
0x14004bb91  mov     rax, rbp
0x14004bb94  sub     rax, rcx
0x14004bb97  cmp     rax, 28h ; '('
0x14004bb9b  jb      short loc_14004BBA5
0x14004bb9d  lea     rax, [rcx+28h]
0x14004bba1  mov     [rbx+28h], rax
0x14004bba5  mov     rdi, [rsi+0C8h]
0x14004bbac  test    rdi, rdi
0x14004bbaf  jz      loc_14004BDA0
0x14004bbb5  mov     rax, [rdi]
0x14004bbb8  mov     [rsi+0C8h], rax
0x14004bbbf  test    rdi, rdi
0x14004bbc2  jz      loc_14004BD90
0x14004bbc8  mov     [rdi+90h], r15
0x14004bbcf  mov     rdx, rdi
0x14004bbd2  xor     r15d, r15d
0x14004bbd5  mov     [rdi+88h], rbx
0x14004bbdc  mov     eax, [rsp+88h+arg_18]
0x14004bbe3  mov     [rdx+10h], eax
0x14004bbe6  movzx   eax, byte ptr [rdx+20h]
0x14004bbea  movzx   ecx, al
0x14004bbed  xor     cl, [rsp+88h+arg_10]
0x14004bbf4  and     cl, 1
0x14004bbf7  xor     cl, al
0x14004bbf9  mov     [rdx+20h], cl
0x14004bbfc  mov     [rdi], r15
0x14004bbff  inc     dword ptr [rsi+0FCh]
0x14004bc05  or      byte ptr [rsi+108h], 8
0x14004bc0c  mov     rbx, [rsi+188h]
0x14004bc13  test    rbx, rbx
0x14004bc16  jnz     loc_14004BD1B
0x14004bc1c  test    rdi, rdi
0x14004bc1f  jz      loc_14004BCB8
0x14004bc25  mov     rcx, [rsp+88h+var_48]
0x14004bc2a  mov     rax, [rcx+88h]
0x14004bc31  mov     byte ptr [rax+40h], 0
0x14004bc35  mov     rax, [rsp+88h+arg_0]
0x14004bc3d  mov     [rcx], rdi
0x14004bc40  mov     [rax], rdi
0x14004bc43  mov     rcx, [rdi+88h]
0x14004bc4a  mov     rdx, [rcx+28h]
0x14004bc4e  sub     rbp, rdx
0x14004bc51  test    r13, r13
0x14004bc54  jz      short loc_14004BCA1
0x14004bc56  cmp     r12, rbp
0x14004bc59  ja      short loc_14004BCA6
0x14004bc5b  mov     r8, [rcx+38h]
0x14004bc5f  lea     rax, [rdx+r12]
0x14004bc63  mov     [rcx+28h], rax
0x14004bc67  add     r8, rdx
0x14004bc6a  jz      short loc_14004BCA6
0x14004bc6c  mov     [r13+0], r8
0x14004bc70  add     [rdi+98h], r12
0x14004bc77  mov     al, 1
0x14004bc79  mov     rbx, [rsp+88h+arg_8]
0x14004bc81  add     rsp, 50h
0x14004bc85  pop     r15
0x14004bc87  pop     r14
0x14004bc89  pop     r13
0x14004bc8b  pop     r12
0x14004bc8d  pop     rdi
0x14004bc8e  pop     rsi
0x14004bc8f  pop     rbp
0x14004bc90  retn
0x14004bc92  mov     rdi, rdx
0x14004bc95  mov     [rsi+0B8h], r15
0x14004bc9c  jmp     loc_14004BBDC
0x14004bca1  cmp     r12, rbp
0x14004bca4  jbe     short loc_14004BC77
0x14004bca6  mov     ecx, 0C000000Dh; BugCheckCode
0x14004bcab  call    cs:__imp_KeBugCheck
0x14004bcb8  xor     al, al
0x14004bcba  jmp     short loc_14004BC79
0x14004bcc0  dec     dword ptr [rsi+0FCh]
0x14004bcc6  mov     rax, [rbx+40h]
0x14004bcca  cmp     rax, [rsi+100h]
0x14004bcd1  jbe     short loc_14004BCE1
0x14004bcd3  or      byte ptr [rsi+108h], 2
0x14004bcda  mov     [rsi+100h], rax
0x14004bce1  mov     rcx, rbx; this
0x14004bce4  call    ?Clear@CBatch@DirectComposition@@QEAAXXZ; DirectComposition::CBatch::Clear(void)
0x14004bce9  mov     rax, [rsi+0C8h]
0x14004bcf0  lea     rcx, [rsi+0D0h]; ListHead
0x14004bcf7  mov     [rbx], rax
0x14004bcfa  mov     [rsi+0C8h], rbx
0x14004bd01  call    cs:__imp_ExpInterlockedPopEntrySList
0x14004bd08  nop     dword ptr [rax+rax+00h]
0x14004bd0d  mov     rbx, rax
0x14004bd10  test    rax, rax
0x14004bd13  jz      loc_14004BAEF
0x14004bd19  jmp     short loc_14004BCC0
0x14004bd1b  call    cs:__imp_KeEnterCriticalRegion
0x14004bd22  nop     dword ptr [rax+rax+00h]
0x14004bd27  mov     dl, 1; Wait
0x14004bd29  mov     rcx, rbx; Resource
0x14004bd2c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004bd33  nop     dword ptr [rax+rax+00h]
0x14004bd38  inc     dword ptr [rsi+0F8h]
0x14004bd3e  cmp     dword ptr [rsi+0F8h], 1
0x14004bd45  jnz     short loc_14004BD5E
0x14004bd47  mov     rcx, [rsi+180h]
0x14004bd4e  mov     rcx, [rcx+8]; Event
0x14004bd52  call    cs:__imp_KeResetEvent
0x14004bd59  nop     dword ptr [rax+rax+00h]
0x14004bd5e  mov     rcx, [rsi+188h]; Resource
0x14004bd65  call    cs:__imp_ExReleaseResourceLite
0x14004bd6c  nop     dword ptr [rax+rax+00h]
0x14004bd71  call    cs:__imp_KeLeaveCriticalRegion
0x14004bd78  nop     dword ptr [rax+rax+00h]
0x14004bd7d  jmp     loc_14004BC1C
0x14004bd82  cmp     r12, rax
0x14004bd85  ja      loc_14004BA8D
0x14004bd8b  jmp     loc_14004BC77
0x14004bd90  mov     byte ptr [rbx+40h], 0
0x14004bd94  jmp     loc_14004BC1C
0x14004bda0  lea     rdx, [rsp+88h+var_58]; struct DirectComposition::CBatch **
0x14004bda5  mov     rcx, rsi; this
0x14004bda8  call    ?CreateBatch@CApplicationChannel@DirectComposition@@QEAAJPEAPEAVCBatch@2@@Z; DirectComposition::CApplicationChannel::CreateBatch(DirectComposition::CBatch * *)
0x14004bdad  test    eax, eax
0x14004bdaf  js      short loc_14004BDBB
0x14004bdb1  mov     rdi, [rsp+88h+var_58]
0x14004bdb6  jmp     loc_14004BBBF
0x14004bdbb  cmp     dword ptr [rsi+0FCh], 0
0x14004bdc2  jle     short loc_14004BDB1
0x14004bdc4  mov     dil, 1
0x14004bdc7  xor     al, al
0x14004bdc9  cmp     dword ptr [rsi+0FCh], 0
0x14004bdd0  jle     short loc_14004BDB1
0x14004bdd2  test    al, al
0x14004bdd4  jz      short loc_14004BE1A
0x14004bdd6  mov     rcx, [rsi+28h]; this
0x14004bdda  call    ?ShouldWaitForReturnedBatches@CConnection@DirectComposition@@QEAA_NXZ; DirectComposition::CConnection::ShouldWaitForReturnedBatches(void)
0x14004bddf  test    al, al
0x14004bde1  jz      short loc_14004BE1A
0x14004bde3  mov     rcx, [rsi+0F0h]
0x14004bdea  mov     r9b, 1; Alertable
0x14004bded  xor     r8d, r8d; WaitMode
0x14004bdf0  mov     [rsp+88h+Timeout], 0; Timeout
0x14004bdf9  mov     edx, 6; WaitReason
0x14004bdfe  mov     rcx, [rcx+8]; Object
0x14004be02  call    cs:__imp_KeWaitForSingleObject
0x14004be09  nop     dword ptr [rax+rax+00h]
0x14004be0e  test    eax, eax
0x14004be10  jz      short loc_14004BE1A
0x14004be12  sub     eax, 0C0h
0x14004be17  xor     dil, dil
0x14004be1a  mov     rcx, rsi; this
0x14004be1d  call    ?ProcessReturnedBatches@CApplicationChannel@DirectComposition@@IEAA_NXZ; DirectComposition::CApplicationChannel::ProcessReturnedBatches(void)
0x14004be22  test    al, al
0x14004be24  jnz     short loc_14004BE82
0x14004be26  mov     al, 1
0x14004be28  test    dil, dil
0x14004be2b  jnz     short loc_14004BDC9
0x14004be2d  jmp     short loc_14004BDB1
0x14004be2f  movzx   edx, byte ptr [r14+18h]; bool
0x14004be34  lea     r8, [rsp+88h+var_50]; struct DirectComposition::CBatchSharedMemoryPool **
0x14004be39  mov     rcx, r14; struct DirectComposition::CBatchSharedMemoryPoolSet *
0x14004be3c  call    ?Create@CBatchSharedMemoryPool@DirectComposition@@SAJPEAVCBatchSharedMemoryPoolSet@2@_NPEAPEAV12@@Z; DirectComposition::CBatchSharedMemoryPool::Create(DirectComposition::CBatchSharedMemoryPoolSet *,bool,DirectComposition::CBatchSharedMemoryPool * *)
0x14004be41  test    eax, eax
0x14004be43  js      loc_14004BC1C
0x14004be49  mov     rbx, [rsp+88h+var_50]
0x14004be4e  xor     r15d, r15d
0x14004be51  cmp     [rbx+40h], dil
0x14004be55  jnz     short loc_14004BE70
0x14004be57  mov     rcx, [rbx+28h]
0x14004be5b  mov     rax, rbp
0x14004be5e  sub     rax, rcx
0x14004be61  cmp     rax, 228h
0x14004be67  jb      short loc_14004BE70
0x14004be69  mov     r15, rcx
0x14004be6c  mov     byte ptr [rbx+40h], 1
0x14004be70  mov     rax, [r14]
0x14004be73  cmp     [rax+8], r14
0x14004be77  jnz     loc_14004BB5F
0x14004be7d  jmp     loc_14004BB76
0x14004be82  mov     rdi, [rsi+0C8h]
0x14004be89  mov     rax, [rdi]
0x14004be8c  mov     [rsi+0C8h], rax
0x14004be93  jmp     loc_14004BBBF
```

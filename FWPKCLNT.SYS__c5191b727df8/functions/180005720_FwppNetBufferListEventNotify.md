# FwppNetBufferListEventNotify

- ea: `0x180005720`
- end: `0x180005d38`
- name: `FwppNetBufferListEventNotify`
- size: `1560`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180005720`
- `0x1800063b0`
- `0x180006a1c`
- `0x180006c10`
- `0x180006ce0`
- `0x180006dd4`
- `0x180006e74`
- `0x180006f00`
- `0x180020400`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180005942`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800059a7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180005942`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800059a7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x180005924`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x180005924`
- `ntoskrnl!MmBadPointer` at `0x180005775`
- `ntoskrnl!MmBadPointer` at `0x18000582a`
- `ntoskrnl!MmBadPointer` at `0x1800058c2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1800059d0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1800059d0`
- `ntoskrnl!ObfDereferenceObject` at `0x18000587a`
- `ntoskrnl!ObfDereferenceObject` at `0x18000587a`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000590a`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000590a`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x180005a8e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x180005c5a`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x180005a8e`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x180005c5a`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x180005cd8`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x180005cd8`
- `NETIO!WfpNblInfoGet` at `0x18000575d`
- `NETIO!WfpNblInfoGet` at `0x180005816`
- `NETIO!WfpNblInfoGet` at `0x1800058b1`
- `NETIO!WfpNblInfoGet` at `0x18000575d`
- `NETIO!WfpNblInfoGet` at `0x180005816`
- `NETIO!WfpNblInfoGet` at `0x1800058b1`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x18000588c`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x18000588c`

## pseudocode

```c
__int64 __fastcall FwppNetBufferListEventNotify(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // r14
  unsigned int v6; // ebx
  _DWORD *v7; // rsi
  __int64 v8; // r14
  _DWORD *v9; // rdi
  int v10; // r13d
  int v11; // eax
  unsigned __int64 v12; // r14
  _DWORD *v13; // rdi
  __int64 v14; // rax
  _DWORD *v15; // rax
  void *v16; // rcx
  _QWORD *v17; // rax
  _QWORD *v18; // rdi
  KIRQL CurrentIrql; // di
  __int64 v21; // rdx
  __int64 TaggedContextList; // rax
  __int64 v23; // rdi
  _DWORD *v24; // rdx
  _QWORD *v25; // rax
  _QWORD *v26; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v27; // r14
  _QWORD *v28; // rdi
  _QWORD *v29; // rsi
  _QWORD *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rdi
  __int64 v33; // rcx
  __int64 v34; // rcx
  int v35; // eax
  void (__fastcall *v36)(__int64, __int64, _QWORD, _QWORD, _QWORD, _QWORD); // rax
  _QWORD *v37; // [rsp+40h] [rbp-39h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v38; // [rsp+48h] [rbp-31h]
  _QWORD *v39; // [rsp+50h] [rbp-29h] BYREF
  __int128 v40; // [rsp+58h] [rbp-21h] BYREF
  struct _KLOCK_QUEUE_HANDLE v41; // [rsp+68h] [rbp-11h] BYREF
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp+7h] BYREF
  _QWORD *v44; // [rsp+F8h] [rbp+7Fh] BYREF

  memset(&v41, 0, sizeof(v41));
  v40 = 0;
  v4 = a2;
  v6 = 0;
  v7 = (_DWORD *)WfpNblInfoGet(a1);
  if ( v7 && v7 != MmBadPointer && v7[10] )
  {
    v8 = 0;
    LODWORD(v44) = 0;
    do
    {
      v9 = &v7[18 * v8];
      if ( *((_BYTE *)v9 + 49) )
      {
        v10 = v7[10];
        if ( a3 == 5 )
          *((_BYTE *)v9 + 49) = 0;
        v11 = v9[28];
        v6 = 0;
        if ( v11 )
        {
          if ( v11 == 1 )
            v6 = (*((__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD, _QWORD))v9 + 13))(
                   a3,
                   a1,
                   a2,
                   *((unsigned __int16 *)v9 + 25),
                   *((_QWORD *)v9 + 7),
                   *((_QWORD *)v9 + 8));
        }
        else
        {
          (*((void (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _QWORD, _QWORD))v9 + 12))(
            a3,
            a1,
            a2,
            *((unsigned __int16 *)v9 + 25),
            *((_QWORD *)v9 + 7),
            *((_QWORD *)v9 + 8));
        }
        if ( a3 == 5 )
        {
          v12 = *((_QWORD *)v9 + 8);
          *((_BYTE *)v9 + 49) = 1;
          memset(&LockHandle, 0, sizeof(LockHandle));
          v13 = (_DWORD *)WfpNblInfoGet(a1);
          if ( v13 && v13 != MmBadPointer )
          {
            if ( (v12 - 1 <= 3 || v12 - 65537 <= 3)
              && (v12 > 4 ? (v14 = (unsigned int)(v12 - 65533)) : (v14 = (unsigned int)(v12 - 1)),
                  (v15 = &v13[18 * v14 + 12]) != 0) )
            {
              if ( *((_BYTE *)v15 + 1) )
              {
                v16 = (void *)*((_QWORD *)v15 + 5);
                *((_BYTE *)v15 + 1) = 0;
                if ( v16 )
                  ObfDereferenceObject(v16);
                --v13[10];
                WfpNblInfoDestroyIfUnused(a1);
              }
            }
            else
            {
              CurrentIrql = KeGetCurrentIrql();
              KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
              if ( CurrentIrql != 2 && WPP_MAIN_CB.DeviceExtension )
              {
                v21 = *(_QWORD *)((char *)WPP_MAIN_CB.DeviceExtension
                                + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
                *(_QWORD *)(v21 + 8) = MEMORY[0xFFFFF78000000008];
                *(_DWORD *)v21 = 4;
              }
              TaggedContextList = FwppGetTaggedContextList(a1);
              v38 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)TaggedContextList;
              v23 = TaggedContextList;
              if ( TaggedContextList )
              {
                v25 = (_QWORD *)(TaggedContextList + 128);
                v37 = v25;
                v26 = v25;
                v39 = v25;
                while ( *(_BYTE *)(v23 + 184) || *(_QWORD *)(v23 + 16) != v12 )
                {
                  v28 = (_QWORD *)*v25;
                  v25 = v28;
                  v37 = v28;
                  if ( v28 == v26 )
                    goto LABEL_35;
                  v23 = (__int64)(v28 - 16);
                  v38 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)v23;
                }
                FwppRemoveTaggedContextFromNetBufferList(a1, v23, &v39, &v37);
                WfpObjectDereference(v23 + 72);
                v27 = v38;
                RtlRemoveEntryHashTable(&HashTable, v38 + 4, 0);
                LOBYTE(v27[7].Signature) = 1;
                WfpObjectDereference(v23 + 72);
              }
LABEL_35:
              if ( byte_1800486F8 )
              {
                RtlEndEnumerationHashTable(qword_1800486C8, &Enumerator);
                byte_1800486F8 = 0;
              }
              if ( WPP_MAIN_CB.DeviceExtension )
              {
                v24 = *(_DWORD **)((char *)WPP_MAIN_CB.DeviceExtension
                                 + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
                if ( *v24 == 4 )
                  *v24 = 0;
              }
              KeReleaseInStackQueuedSpinLock(&LockHandle);
            }
          }
          LODWORD(v8) = (_DWORD)v44;
        }
        if ( (v6 & 0x80000000) != 0 )
          return v6;
        if ( v10 == 1 )
          break;
      }
      v8 = (unsigned int)(v8 + 1);
      LODWORD(v44) = v8;
    }
    while ( (unsigned int)v8 < 8 );
    v4 = a2;
  }
  v17 = (_QWORD *)WfpNblInfoGet(a1);
  if ( v17 )
  {
    if ( v17 != MmBadPointer )
    {
      v18 = (_QWORD *)v17[2];
      if ( v18 )
      {
        *((_QWORD *)&v40 + 1) = &v40;
        v29 = v18 + 16;
        v44 = v18 + 16;
        *(_QWORD *)&v40 = &v40;
        v37 = v18 + 16;
        WfpAcquireSpinLock(&SpinLock, &v41);
        while ( !*((_BYTE *)v18 + 184) )
        {
          v30 = (_QWORD *)*((_QWORD *)&v40 + 1);
          if ( **((__int128 ***)&v40 + 1) != &v40 )
LABEL_71:
            __fastfail(3u);
          v18[21] = *((_QWORD *)&v40 + 1);
          v18[20] = &v40;
          *v30 = v18 + 20;
          *((_QWORD *)&v40 + 1) = v18 + 20;
          if ( a3 == 5 )
          {
            RtlRemoveEntryHashTable(&HashTable, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v18 + 4, 0);
            WfpObjectDereference(v18 + 9);
            *((_BYTE *)v18 + 184) = 1;
            FwppRemoveTaggedContextFromNetBufferList(a1, v18, &v37, &v44);
LABEL_74:
            v29 = v44;
            goto LABEL_56;
          }
          _InterlockedIncrement((volatile signed __int32 *)v18 + 19);
          v29 = (_QWORD *)*v29;
          v44 = v29;
LABEL_56:
          if ( v29 )
            v18 = v29 - 16;
          if ( v29 == v37 )
          {
            WfpObjectManagerUnlock(&unk_180048680, &v41);
            while ( 1 )
            {
              if ( (__int128 *)v40 == &v40 )
                return v6;
              if ( *(__int128 **)(v40 + 8) != &v40 )
                goto LABEL_71;
              v31 = *(_QWORD *)v40;
              if ( *(_QWORD *)(*(_QWORD *)v40 + 8LL) != (_QWORD)v40 )
                goto LABEL_71;
              v32 = v40 - 160;
              *(_QWORD *)&v40 = *(_QWORD *)v40;
              *(_QWORD *)(v31 + 8) = &v40;
              if ( a3 != 5 )
              {
                WfpAcquireSpinLock((PKSPIN_LOCK)(v32 + 120), &v41);
                if ( *(_BYTE *)(v32 + 186) )
                {
                  WfpReleaseSpinLock(v33, &v41);
                  WfpAcquireSpinLock((PKSPIN_LOCK)(v32 + 120), &v41);
                }
                else
                {
                  *(_BYTE *)(v32 + 187) = 1;
                  WfpReleaseSpinLock(v33, &v41);
                  v6 = FwppInvokeTaggedContextNotifyFn(v32, a1, v4, a3);
                  WfpAcquireSpinLock((PKSPIN_LOCK)(v32 + 120), &v41);
                  *(_BYTE *)(v32 + 187) = 0;
                }
                WfpReleaseSpinLock(v34, &v41);
              }
              v35 = *(_DWORD *)(v32 + 64);
              if ( !v35 )
                break;
              if ( v35 != 1 )
                goto LABEL_70;
              if ( *(_BYTE *)(v32 + 185) )
              {
                (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(v32 + 56))(
                  5,
                  0,
                  0,
                  *(unsigned __int16 *)(v32 + 2),
                  *(_QWORD *)(v32 + 8),
                  *(_QWORD *)(v32 + 16));
                goto LABEL_70;
              }
              if ( a3 == 5 )
              {
                v36 = *(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, _QWORD))(v32 + 56);
LABEL_83:
                v36(5, a1, 0, *(unsigned __int16 *)(v32 + 2), *(_QWORD *)(v32 + 8), *(_QWORD *)(v32 + 16));
              }
LABEL_70:
              WfpObjectDereference(v32 + 72);
            }
            if ( *(_BYTE *)(v32 + 185) )
            {
              (*(void (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(v32 + 48))(
                5,
                0,
                0,
                *(unsigned __int16 *)(v32 + 2),
                *(_QWORD *)(v32 + 8),
                *(_QWORD *)(v32 + 16));
              goto LABEL_70;
            }
            if ( a3 != 5 )
              goto LABEL_70;
            v36 = *(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD, _QWORD))(v32 + 48);
            goto LABEL_83;
          }
        }
        FwppRemoveTaggedContextFromNetBufferList(a1, v18, &v37, &v44);
        WfpObjectDereference(v18 + 9);
        goto LABEL_74;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180005720  mov     [rsp-8+arg_0], rbx
0x180005725  mov     [rsp-8+arg_8], rdx
0x18000572a  push    rbp
0x18000572b  push    rsi
0x18000572c  push    rdi
0x18000572d  push    r12
0x18000572f  push    r13
0x180005731  push    r14
0x180005733  push    r15
0x180005735  lea     rbp, [rsp-27h]
0x18000573a  sub     rsp, 0A0h
0x180005741  xorps   xmm0, xmm0
0x180005744  xor     eax, eax
0x180005746  movups  xmmword ptr [rbp+57h+var_68.LockQueue.Next], xmm0
0x18000574a  mov     qword ptr [rbp+57h+var_68.OldIrql], rax
0x18000574e  mov     r12d, r8d
0x180005751  movups  [rbp+57h+var_78], xmm0
0x180005755  mov     r14, rdx
0x180005758  mov     r15, rcx
0x18000575b  xor     ebx, ebx
0x18000575d  call    cs:__imp_WfpNblInfoGet
0x180005764  nop     dword ptr [rax+rax+00h]
0x180005769  mov     rsi, rax
0x18000576c  test    rax, rax
0x18000576f  jz      loc_1800058AE
0x180005775  mov     rax, cs:MmBadPointer
0x18000577c  cmp     rsi, [rax]
0x18000577f  jz      loc_1800058AE
0x180005785  cmp     [rsi+28h], ebx
0x180005788  jbe     loc_1800058AE
0x18000578e  xor     r14d, r14d
0x180005791  mov     dword ptr [rbp+57h+arg_18], r14d
0x180005795  lea     rcx, [r14+r14*8]
0x180005799  cmp     byte ptr [rsi+rcx*8+31h], 0
0x18000579e  lea     rdi, [rsi+rcx*8]
0x1800057a2  jz      loc_180005A10
0x1800057a8  mov     r13d, [rsi+28h]
0x1800057ac  cmp     r12d, 5
0x1800057b0  jnz     short loc_1800057B6
0x1800057b2  mov     byte ptr [rdi+31h], 0
0x1800057b6  mov     eax, [rdi+70h]
0x1800057b9  xor     ebx, ebx
0x1800057bb  test    eax, eax
0x1800057bd  jz      loc_1800059E1
0x1800057c3  cmp     eax, 1
0x1800057c6  jnz     short loc_1800057F4
0x1800057c8  mov     rax, [rdi+40h]
0x1800057cc  mov     rdx, r15
0x1800057cf  movzx   r9d, word ptr [rdi+32h]
0x1800057d4  mov     ecx, r12d
0x1800057d7  mov     r8, [rbp+57h+arg_8]
0x1800057db  mov     [rsp+0D0h+var_A8], rax
0x1800057e0  mov     rax, [rdi+38h]
0x1800057e4  mov     [rsp+0D0h+var_B0], rax
0x1800057e9  mov     rax, [rdi+68h]
0x1800057ed  call    _guard_dispatch_icall
0x1800057f2  mov     ebx, eax
0x1800057f4  cmp     r12d, 5
0x1800057f8  jnz     loc_18000589C
0x1800057fe  mov     r14, [rdi+40h]
0x180005802  xorps   xmm0, xmm0
0x180005805  xor     eax, eax
0x180005807  mov     byte ptr [rdi+31h], 1
0x18000580b  mov     rcx, r15
0x18000580e  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x180005812  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x180005816  call    cs:__imp_WfpNblInfoGet
0x18000581d  nop     dword ptr [rax+rax+00h]
0x180005822  mov     rdi, rax
0x180005825  test    rax, rax
0x180005828  jz      short loc_180005898
0x18000582a  mov     rax, cs:MmBadPointer
0x180005831  cmp     rdi, [rax]
0x180005834  jz      short loc_180005898
0x180005836  lea     rax, [r14-1]
0x18000583a  cmp     rax, 3
0x18000583e  ja      loc_1800058F9
0x180005844  cmp     r14, 4
0x180005848  ja      loc_180005A2E
0x18000584e  lea     eax, [r14-1]
0x180005852  lea     rax, [rax+rax*8]
0x180005856  lea     rax, [rax+6]
0x18000585a  lea     rax, [rdi+rax*8]
0x18000585e  test    rax, rax
0x180005861  jz      loc_18000590A
0x180005867  cmp     byte ptr [rax+1], 0
0x18000586b  jz      short loc_180005898
0x18000586d  mov     rcx, [rax+28h]; Object
0x180005871  mov     byte ptr [rax+1], 0
0x180005875  test    rcx, rcx
0x180005878  jz      short loc_180005886
0x18000587a  call    cs:__imp_ObfDereferenceObject
0x180005881  nop     dword ptr [rax+rax+00h]
0x180005886  dec     dword ptr [rdi+28h]
0x180005889  mov     rcx, r15
0x18000588c  call    cs:__imp_WfpNblInfoDestroyIfUnused
0x180005893  nop     dword ptr [rax+rax+00h]
0x180005898  mov     r14d, dword ptr [rbp+57h+arg_18]
0x18000589c  test    ebx, ebx
0x18000589e  js      short loc_1800058DB
0x1800058a0  cmp     r13d, 1
0x1800058a4  jnz     loc_180005A10
0x1800058aa  mov     r14, [rbp+57h+arg_8]
0x1800058ae  mov     rcx, r15
0x1800058b1  call    cs:__imp_WfpNblInfoGet
0x1800058b8  nop     dword ptr [rax+rax+00h]
0x1800058bd  test    rax, rax
0x1800058c0  jz      short loc_1800058DB
0x1800058c2  mov     rcx, cs:MmBadPointer
0x1800058c9  cmp     rax, [rcx]
0x1800058cc  jz      short loc_1800058DB
0x1800058ce  mov     rdi, [rax+10h]
0x1800058d2  test    rdi, rdi
0x1800058d5  jnz     loc_180005ACD
0x1800058db  mov     eax, ebx
0x1800058dd  mov     rbx, [rsp+0D0h+arg_0]
0x1800058e5  add     rsp, 0A0h
0x1800058ec  pop     r15
0x1800058ee  pop     r14
0x1800058f0  pop     r13
0x1800058f2  pop     r12
0x1800058f4  pop     rdi
0x1800058f5  pop     rsi
0x1800058f6  pop     rbp
0x1800058f7  retn
0x1800058f9  lea     rax, [r14-10001h]
0x180005900  cmp     rax, 3
0x180005904  jbe     loc_180005844
0x18000590a  call    cs:__imp_KeGetCurrentIrql
0x180005911  nop     dword ptr [rax+rax+00h]
0x180005916  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x18000591a  movzx   edi, al
0x18000591d  lea     rcx, SpinLock; SpinLock
0x180005924  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x18000592b  nop     dword ptr [rax+rax+00h]
0x180005930  cmp     dil, 2
0x180005934  jz      short loc_180005976
0x180005936  cmp     cs:WPP_MAIN_CB.DeviceExtension, 0
0x18000593e  jz      short loc_180005976
0x180005940  xor     ecx, ecx; ProcNumber
0x180005942  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x180005949  nop     dword ptr [rax+rax+00h]
0x18000594e  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x180005955  mov     ecx, eax
0x180005957  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x18000595e  mov     rdx, [rcx+rax]
0x180005962  mov     rax, ds:0FFFFF78000000008h
0x18000596c  mov     [rdx+8], rax
0x180005970  mov     dword ptr [rdx], 4
0x180005976  mov     rcx, r15
0x180005979  call    FwppGetTaggedContextList
0x18000597e  mov     [rbp+57h+var_88], rax
0x180005982  mov     rdi, rax
0x180005985  test    rax, rax
0x180005988  jnz     loc_180005A42
0x18000598e  cmp     cs:byte_1800486F8, 0
0x180005995  jnz     loc_180005CCA
0x18000599b  cmp     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1800059a3  jz      short loc_1800059CC
0x1800059a5  xor     ecx, ecx; ProcNumber
0x1800059a7  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1800059ae  nop     dword ptr [rax+rax+00h]
0x1800059b3  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x1800059ba  mov     ecx, eax
0x1800059bc  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x1800059c3  mov     rdx, [rcx+rax]
0x1800059c7  cmp     dword ptr [rdx], 4
0x1800059ca  jz      short loc_180005A3A
0x1800059cc  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1800059d0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1800059d7  nop     dword ptr [rax+rax+00h]
0x1800059dc  jmp     loc_180005898
0x1800059e1  mov     rax, [rdi+40h]
0x1800059e5  mov     rdx, r15
0x1800059e8  movzx   r9d, word ptr [rdi+32h]
0x1800059ed  mov     ecx, r12d
0x1800059f0  mov     r8, [rbp+57h+arg_8]
0x1800059f4  mov     [rsp+0D0h+var_A8], rax
0x1800059f9  mov     rax, [rdi+38h]
0x1800059fd  mov     [rsp+0D0h+var_B0], rax
0x180005a02  mov     rax, [rdi+60h]
0x180005a06  call    _guard_dispatch_icall
0x180005a0b  jmp     loc_1800057F4
0x180005a10  inc     r14d
0x180005a13  mov     dword ptr [rbp+57h+arg_18], r14d
0x180005a17  cmp     r14d, 8
0x180005a1b  jb      loc_180005795
0x180005a21  test    ebx, ebx
0x180005a23  jns     loc_1800058AA
0x180005a29  jmp     loc_1800058DB
0x180005a2e  lea     eax, [r14-0FFFDh]
0x180005a35  jmp     loc_180005852
0x180005a3a  mov     dword ptr [rdx], 0
0x180005a40  jmp     short loc_1800059CC
0x180005a42  sub     rax, 0FFFFFFFFFFFFFF80h
0x180005a46  mov     [rbp+57h+var_90], rax
0x180005a4a  mov     rcx, rax
0x180005a4d  mov     [rbp+57h+var_80], rax
0x180005a51  cmp     byte ptr [rdi+0B8h], 0
0x180005a58  jnz     short loc_180005AB0
0x180005a5a  cmp     [rdi+10h], r14
0x180005a5e  jnz     short loc_180005AB0
0x180005a60  lea     r9, [rbp+57h+var_90]
0x180005a64  mov     rdx, rdi
0x180005a67  lea     r8, [rbp+57h+var_80]
0x180005a6b  mov     rcx, r15
0x180005a6e  call    FwppRemoveTaggedContextFromNetBufferList
0x180005a73  lea     rcx, [rdi+48h]
0x180005a77  call    WfpObjectDereference
0x180005a7c  mov     r14, [rbp+57h+var_88]
0x180005a80  lea     rcx, HashTable; HashTable
0x180005a87  xor     r8d, r8d; Context
0x180005a8a  lea     rdx, [r14+60h]; Entry
0x180005a8e  call    cs:__imp_RtlRemoveEntryHashTable
0x180005a95  nop     dword ptr [rax+rax+00h]
0x180005a9a  lea     rcx, [rdi+48h]
0x180005a9e  mov     byte ptr [r14+0B8h], 1
0x180005aa6  call    WfpObjectDereference
0x180005aab  jmp     loc_18000598E
0x180005ab0  mov     rdi, [rax]
0x180005ab3  mov     rax, rdi
0x180005ab6  mov     [rbp+57h+var_90], rax
0x180005aba  cmp     rdi, rcx
0x180005abd  jz      loc_18000598E
0x180005ac3  add     rdi, 0FFFFFFFFFFFFFF80h
0x180005ac7  mov     [rbp+57h+var_88], rdi
0x180005acb  jmp     short loc_180005A51
0x180005acd  lea     rax, [rbp+57h+var_78]
0x180005ad1  mov     qword ptr [rbp+57h+var_78+8], rax
0x180005ad5  lea     rsi, [rdi+80h]
0x180005adc  lea     rax, [rbp+57h+var_78]
0x180005ae0  mov     [rbp+57h+arg_18], rsi
0x180005ae4  lea     rdx, [rbp+57h+var_68]; LockHandle
0x180005ae8  mov     qword ptr [rbp+57h+var_78], rax
0x180005aec  lea     rcx, SpinLock; SpinLock
0x180005af3  mov     [rbp+57h+var_90], rsi
0x180005af7  call    WfpAcquireSpinLock
0x180005afc  cmp     byte ptr [rdi+0B8h], 0
0x180005b03  jnz     loc_180005C92
0x180005b09  mov     rcx, qword ptr [rbp+57h+var_78+8]
0x180005b0d  lea     rax, [rbp+57h+var_78]
0x180005b11  cmp     [rcx], rax
0x180005b14  jnz     loc_180005C31
0x180005b1a  lea     rax, [rdi+0A0h]
0x180005b21  mov     [rax+8], rcx
0x180005b25  lea     rdx, [rbp+57h+var_78]
0x180005b29  mov     [rax], rdx
0x180005b2c  mov     [rcx], rax
0x180005b2f  mov     qword ptr [rbp+57h+var_78+8], rax
0x180005b33  cmp     r12d, 5
0x180005b37  jz      loc_180005C4C
0x180005b3d  lock inc dword ptr [rdi+4Ch]
0x180005b41  mov     rsi, [rsi]
0x180005b44  mov     [rbp+57h+arg_18], rsi
0x180005b48  test    rsi, rsi
0x180005b4b  jz      short loc_180005B51
0x180005b4d  lea     rdi, [rsi-80h]
0x180005b51  cmp     rsi, [rbp+57h+var_90]
0x180005b55  jnz     short loc_180005AFC
0x180005b57  lea     rdx, [rbp+57h+var_68]
0x180005b5b  lea     rcx, unk_180048680
0x180005b62  call    WfpObjectManagerUnlock
0x180005b67  mov     rdi, qword ptr [rbp+57h+var_78]
0x180005b6b  lea     rax, [rbp+57h+var_78]
0x180005b6f  cmp     rdi, rax
0x180005b72  jz      loc_1800058DB
0x180005b78  lea     rax, [rbp+57h+var_78]
0x180005b7c  cmp     [rdi+8], rax
0x180005b80  jnz     loc_180005C31
0x180005b86  mov     rax, [rdi]
0x180005b89  cmp     [rax+8], rdi
0x180005b8d  jnz     loc_180005C31
0x180005b93  add     rdi, 0FFFFFFFFFFFFFF60h
0x180005b9a  mov     qword ptr [rbp+57h+var_78], rax
0x180005b9e  lea     rcx, [rbp+57h+var_78]
0x180005ba2  mov     [rax+8], rcx
0x180005ba6  cmp     r12d, 5
0x180005baa  jz      short loc_180005C02
0x180005bac  lea     rdx, [rbp+57h+var_68]; LockHandle
0x180005bb0  lea     rcx, [rdi+78h]; SpinLock
0x180005bb4  call    WfpAcquireSpinLock
0x180005bb9  cmp     byte ptr [rdi+0BAh], 0
0x180005bc0  lea     rdx, [rbp+57h+var_68]
0x180005bc4  jnz     short loc_180005C38
0x180005bc6  mov     byte ptr [rdi+0BBh], 1
0x180005bcd  call    WfpReleaseSpinLock
0x180005bd2  mov     r9d, r12d
0x180005bd5  mov     r8, r14
0x180005bd8  mov     rdx, r15
0x180005bdb  mov     rcx, rdi
0x180005bde  call    FwppInvokeTaggedContextNotifyFn
0x180005be3  lea     rdx, [rbp+57h+var_68]; LockHandle
0x180005be7  mov     ebx, eax
0x180005be9  lea     rcx, [rdi+78h]; SpinLock
0x180005bed  call    WfpAcquireSpinLock
0x180005bf2  mov     byte ptr [rdi+0BBh], 0
0x180005bf9  lea     rdx, [rbp+57h+var_68]
0x180005bfd  call    WfpReleaseSpinLock
0x180005c02  mov     eax, [rdi+40h]
0x180005c05  test    eax, eax
  ... truncated ...
```

# NtfsCompleteMdl

- ea: `0x14018a28c`
- end: `0x14018a897`
- name: `NtfsCompleteMdl`
- size: `1547`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140015540`
- `0x140016850`

## callees

- `0x1400082b0`
- `0x140009af0`
- `0x140021590`
- `0x140030a80`
- `0x140039038`
- `0x1400c65ec`
- `0x140188d34`
- `0x140188f30`
- `0x14018a28c`
- `0x14018a8a0`
- `0x1401be3e8`
- `0x1401c0130`

## import_xrefs

- `ntoskrnl!CcMdlWriteComplete` at `0x14018a7bb`
- `ntoskrnl!CcMdlWriteComplete` at `0x14018a7bb`
- `ntoskrnl!KeBugCheckEx` at `0x1402caa61`
- `ntoskrnl!KeBugCheckEx` at `0x1402caa61`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14018a634`
- `ntoskrnl!FsRtlReleaseHeaderMutex` at `0x14018a634`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14018a5e4`
- `ntoskrnl!FsRtlAcquireHeaderMutex` at `0x14018a5e4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018a74c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14018a74c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018a3b0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018a586`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018a3b0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14018a586`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a4a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a669`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a6a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a728`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a4a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a669`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a6a3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14018a728`
- `ntoskrnl!CcMdlReadComplete` at `0x14018a832`
- `ntoskrnl!CcMdlReadComplete` at `0x14018a832`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14018a70b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14018a70b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14018a418`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14018a418`

## pseudocode

```c
__int64 __fastcall NtfsCompleteMdl(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  int v4; // r13d
  __int64 v5; // r9
  struct _FILE_OBJECT *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned int v9; // eax
  _QWORD *FsContext; // rsi
  union _LARGE_INTEGER *v11; // rdx
  PMDL *v12; // r12
  PMDL v13; // rcx
  __int64 QuadPart; // rdx
  __int64 v15; // r13
  BOOLEAN v16; // r15
  _QWORD *v17; // rdi
  __int64 v18; // rdx
  PSECTION_OBJECT_POINTERS SectionObjectPointer; // rcx
  __int64 v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // rdi
  __int64 v23; // r13
  __int64 v24; // r15
  __int64 v25; // r15
  char v26; // al
  __int64 v27; // r12
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  int v37; // [rsp+50h] [rbp-A8h]
  int v38; // [rsp+54h] [rbp-A4h]
  __int64 v39; // [rsp+60h] [rbp-98h] BYREF
  unsigned int v40; // [rsp+68h] [rbp-90h]
  __int64 v41; // [rsp+70h] [rbp-88h]
  __int64 v42; // [rsp+78h] [rbp-80h]
  __int64 v43; // [rsp+80h] [rbp-78h]
  PMDL *v44; // [rsp+88h] [rbp-70h]
  __int64 v45; // [rsp+90h] [rbp-68h]
  signed __int64 v46; // [rsp+98h] [rbp-60h]
  struct _FILE_OBJECT *v47; // [rsp+A0h] [rbp-58h]
  _QWORD *v48; // [rsp+A8h] [rbp-50h]
  __int64 v49; // [rsp+B0h] [rbp-48h]
  union _LARGE_INTEGER *v50; // [rsp+B8h] [rbp-40h]
  char v52; // [rsp+110h] [rbp+18h] BYREF
  struct _FILE_OBJECT *v53; // [rsp+118h] [rbp+20h]

  v2 = a2;
  v39 = 0;
  v4 = 0;
  v38 = 0;
  v5 = *(_QWORD *)(a2 + 184);
  v6 = *(struct _FILE_OBJECT **)(v5 + 48);
  v53 = v6;
  v47 = v6;
  v7 = *(unsigned __int8 *)(a1 + 32);
  v8 = (unsigned int)*(unsigned __int8 *)(a1 + 32) - 3;
  if ( (_DWORD)v8 )
  {
    if ( (_DWORD)v8 != 1 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x800) != 0 )
      {
        McTemplateU0q_EtwWriteTransfer(v8, cachesup_c1885, v7);
      }
      KeBugCheckEx(0x24u, 0xAC00050762uLL, *(unsigned __int8 *)(a1 + 32), 0, 0);
    }
    v9 = 0;
    v40 = 0;
    v52 = 0;
    v45 = 0;
    FsContext = v6->FsContext;
    v48 = FsContext;
    v11 = (union _LARGE_INTEGER *)(v5 + 24);
    v50 = (union _LARGE_INTEGER *)(v5 + 24);
    v12 = (PMDL *)(v2 + 8);
    if ( FsContext[2] )
    {
      v44 = (PMDL *)(v2 + 8);
      v13 = *v12;
      QuadPart = v11->QuadPart;
      v42 = QuadPart;
      v49 = QuadPart;
      while ( v13 )
      {
        v9 += v13->ByteCount;
        v40 = v9;
        v13 = v13->Next;
      }
      v15 = v9;
      v46 = (v9 + QuadPart + 4095) & 0xFFFFFFFFFFFFF000uLL;
      if ( *((_BYTE *)FsContext + 460) )
      {
        v16 = 0;
        if ( *(_WORD *)FsContext == 1794 )
        {
          v17 = FsContext;
        }
        else
        {
          v17 = 0;
          if ( FsContext[2] )
            v17 = (_QWORD *)FsContext[23];
        }
        do
        {
          if ( (v17[2] & 0x200) == 0
            || a1
            && ((*(_DWORD *)(a1 + 16) & 0x40000000) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 144) + 16LL) & 0x40000000) != 0)
            || ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v17[12] + 2160LL)) )
          {
            if ( v16 )
              break;
          }
          else
          {
            if ( v16 )
              ExReleaseResourceLite((PERESOURCE)v17[14]);
            KeWaitForSingleObject(*(PVOID *)(v17[12] + 1432LL), Executive, 0, 0, 0);
          }
          v16 = ExAcquireResourceExclusiveLite((PERESOURCE)v17[14], 1u);
        }
        while ( v16 );
        v6 = v53;
        v2 = a2;
      }
      else
      {
        LOBYTE(v7) = 1;
        NtfsAcquirePagingShared(a1, FsContext, v7, 0);
        if ( *((_BYTE *)FsContext + 460) )
        {
          NtfsReleasePagingResourcePriv(v28, FsContext, v29, v30);
          LOBYTE(v31) = 1;
          NtfsAcquirePagingResourceExclusive(a1, FsContext, v31);
        }
      }
      v18 = FsContext[66];
      if ( v18 )
      {
        if ( *((_DWORD *)FsContext + 64) == 128 )
        {
          SectionObjectPointer = v6->SectionObjectPointer;
          if ( SectionObjectPointer == (PSECTION_OBJECT_POINTERS)(FsContext[36] + 16LL)
            || SectionObjectPointer[1].ImageSectionObject )
          {
            ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v18 + 64) + 136LL), 1u);
            v20 = FsContext[66];
            v21 = *(_QWORD *)(v20 + 64);
            if ( *(_QWORD *)(v21 + 24) )
            {
              v41 = 0;
              if ( v20 )
              {
                v22 = *(_QWORD *)(v20 + 56);
                v41 = v22;
                while ( v22 )
                {
                  if ( !*(_WORD *)(v22 + 304) || (*(_DWORD *)(v22 + 8) & 0x2000) == 0 )
                  {
                    if ( (*(_DWORD *)(v22 + 8) & 0x2001) != 0 )
                      v22 = 0;
                    v41 = v22;
                    if ( v22 )
                      _InterlockedIncrement((volatile signed __int32 *)(v22 + 4));
                    break;
                  }
                  v22 = *(_QWORD *)(v22 + 32);
                  v41 = v22;
                }
                v43 = v22;
              }
              else
              {
                v22 = 0;
                v43 = 0;
              }
              v45 = v22;
              ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(FsContext[66] + 64LL) + 136LL));
              v38 = 1;
              v37 = TxfLogPriorToWrite(a1, (__int64)v53, v22, v42, v15, v2, 1, 0);
              if ( v22 )
              {
                v23 = v22;
                v24 = *(_QWORD *)(v22 + 16);
                if ( v24 )
                  v25 = *(_QWORD *)(v24 + 64);
                else
                  v25 = 0;
                v26 = 0;
                do
                {
                  v27 = 0;
                  if ( v25 && !v26 )
                  {
                    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v25 + 136), 1u);
                    v26 = 1;
                  }
                  _InterlockedDecrement((volatile signed __int32 *)(v23 + 4));
                  if ( !*(_DWORD *)(v23 + 4) )
                  {
                    v27 = *(_QWORD *)(v23 + 40);
                    TxfDeleteTxfVscb((char *)v23);
                    v26 = 0;
                  }
                  v23 = v27;
                }
                while ( v27 );
                if ( v26 && v25 )
                  ExReleaseResourceLite(*(PERESOURCE *)(v25 + 136));
              }
              if ( v37 )
                *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v22 + 16) + 64LL) + 4LL) |= 0x2000u;
              v12 = v44;
            }
            else
            {
              ExReleaseResourceLite(*(PERESOURCE *)(v21 + 136));
            }
          }
        }
      }
      FsRtlAcquireHeaderMutex(FsContext + 15, FsContext + 20);
      if ( v46 > FsContext[5] )
        NtfsGetIoAtEof(a1, (_DWORD)FsContext, v42, v46 - v42, 1, (__int64)&v52);
      FsRtlReleaseHeaderMutex(FsContext + 15, FsContext + 20);
      v2 = a2;
      v6 = v53;
      v4 = v38;
      v11 = v50;
    }
    CcMdlWriteComplete(v6, v11, *v12);
    if ( FsContext[2] )
      NtfsReleasePagingResourcePriv(v33, FsContext, v34, v35);
    if ( v4 && v39 )
    {
      LOBYTE(v32) = 1;
      TxfDereferenceTransaction(&v39, v32);
    }
  }
  else
  {
    v12 = (PMDL *)(a2 + 8);
    CcMdlReadComplete(v6, *(PMDL *)(a2 + 8));
  }
  *(_DWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 4) &= ~0x100u;
  *v12 = 0;
  LOBYTE(v35) = v2 != 0;
  NtfsExtendedCompleteRequestInternal(a1, v2, 0, v35, 1);
  return 0;
}

```

## disassembly

```asm
0x14018a28c  mov     r11, rsp
0x14018a28f  mov     [r11+10h], rdx
0x14018a293  mov     [r11+8], rcx
0x14018a297  push    rbx
0x14018a298  push    rsi
0x14018a299  push    rdi
0x14018a29a  push    r12
0x14018a29c  push    r13
0x14018a29e  push    r14
0x14018a2a0  push    r15
0x14018a2a2  sub     rsp, 0C0h
0x14018a2a9  mov     r15, rdx
0x14018a2ac  mov     r14, rcx
0x14018a2af  xor     ebx, ebx
0x14018a2b1  mov     [rsp+0F8h+var_A0], rbx
0x14018a2b6  mov     [rsp+0F8h+var_98], rbx
0x14018a2bb  mov     r13d, ebx
0x14018a2be  mov     [rsp+0F8h+var_A4], ebx
0x14018a2c2  mov     r9, [rdx+0B8h]
0x14018a2c9  mov     rdi, [r9+30h]
0x14018a2cd  mov     [rsp+0F8h+arg_18], rdi
0x14018a2d5  mov     [rsp+0F8h+var_58], rdi
0x14018a2dd  movzx   r8d, byte ptr [rcx+20h]
0x14018a2e2  mov     ecx, r8d
0x14018a2e5  sub     ecx, 3
0x14018a2e8  jz      loc_14018A827
0x14018a2ee  cmp     ecx, 1
0x14018a2f1  jnz     loc_14018A840
0x14018a2f7  mov     eax, ebx
0x14018a2f9  mov     [rsp+0F8h+var_90], ebx
0x14018a2fd  mov     [r11+18h], bl
0x14018a301  mov     [r11-68h], rbx
0x14018a305  mov     [rsp+0F8h+var_A8], 0C0000001h
0x14018a30d  mov     rsi, [rdi+18h]
0x14018a311  mov     [rsp+0F8h+var_50], rsi
0x14018a319  mov     [rsp+0F8h+var_A0], rsi
0x14018a31e  lea     rdx, [r9+18h]; FileOffset
0x14018a322  mov     [rsp+0F8h+var_40], rdx
0x14018a32a  lea     r12, [r15+8]
0x14018a32e  cmp     [rsi+10h], rbx
0x14018a332  jz      loc_14018A7B4
0x14018a338  mov     [rsp+0F8h+var_70], r12
0x14018a340  mov     rcx, [r12]
0x14018a344  mov     rdx, [rdx]
0x14018a347  mov     [rsp+0F8h+var_80], rdx
0x14018a34c  mov     [rsp+0F8h+var_48], rdx
0x14018a354  test    rcx, rcx
0x14018a357  jnz     loc_14018A75D
0x14018a35d  mov     r13d, eax
0x14018a360  lea     rax, [rdx+0FFFh]
0x14018a367  add     rax, r13
0x14018a36a  and     rax, 0FFFFFFFFFFFFF000h
0x14018a370  mov     [rsp+0F8h+var_60], rax
0x14018a378  cmp     [rsi+1CCh], cl
0x14018a37e  jz      loc_14018A76C
0x14018a384  mov     r15b, bl
0x14018a387  mov     eax, 702h
0x14018a38c  cmp     ax, [rsi]
0x14018a38f  jnz     loc_14018A67A
0x14018a395  mov     rdi, rsi
0x14018a398  test    dword ptr [rdi+10h], 200h
0x14018a39f  jnz     loc_14018A6D7
0x14018a3a5  test    r15b, r15b
0x14018a3a8  jnz     short loc_14018A3C3
0x14018a3aa  mov     dl, 1; Wait
0x14018a3ac  mov     rcx, [rdi+70h]; Resource
0x14018a3b0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14018a3b7  nop     dword ptr [rax+rax+00h]
0x14018a3bc  mov     r15b, al
0x14018a3bf  test    al, al
0x14018a3c1  jnz     short loc_14018A398
0x14018a3c3  mov     rdi, [rsp+0F8h+arg_18]
0x14018a3cb  mov     r15, [rsp+0F8h+arg_8]
0x14018a3d3  mov     rdx, [rsi+210h]
0x14018a3da  test    rdx, rdx
0x14018a3dd  jz      loc_14018A5D6
0x14018a3e3  cmp     dword ptr [rsi+100h], 80h
0x14018a3ed  jnz     loc_14018A5D6
0x14018a3f3  mov     rcx, [rdi+28h]
0x14018a3f7  mov     rax, [rsi+120h]
0x14018a3fe  add     rax, 10h
0x14018a402  cmp     rcx, rax
0x14018a405  jnz     loc_14018A7A5
0x14018a40b  mov     rcx, [rdx+40h]
0x14018a40f  mov     dl, 1; Wait
0x14018a411  mov     rcx, [rcx+88h]; Resource
0x14018a418  call    cs:__imp_ExAcquireResourceSharedLite
0x14018a41f  nop     dword ptr [rax+rax+00h]
0x14018a424  mov     rdi, [rsi+210h]
0x14018a42b  mov     rcx, [rdi+40h]
0x14018a42f  cmp     [rcx+18h], rbx
0x14018a433  jz      loc_14018A662
0x14018a439  mov     [rsp+0F8h+var_88], rbx
0x14018a43e  test    rdi, rdi
0x14018a441  jz      loc_14018A53E
0x14018a447  mov     rdi, [rdi+38h]
0x14018a44b  mov     [rsp+0F8h+var_88], rdi
0x14018a450  test    rdi, rdi
0x14018a453  jz      short loc_14018A480
0x14018a455  cmp     [rdi+130h], bx
0x14018a45c  jnz     loc_14018A523
0x14018a462  test    rdi, rdi
0x14018a465  jz      short loc_14018A480
0x14018a467  test    dword ptr [rdi+8], 2001h
0x14018a46e  cmovnz  rdi, rbx
0x14018a472  mov     [rsp+0F8h+var_88], rdi
0x14018a477  test    rdi, rdi
0x14018a47a  jz      short loc_14018A480
0x14018a47c  lock inc dword ptr [rdi+4]
0x14018a480  mov     [rsp+0F8h+var_78], rdi
0x14018a488  mov     [rsp+0F8h+var_68], rdi
0x14018a490  mov     rax, [rsi+210h]
0x14018a497  mov     rcx, [rax+40h]
0x14018a49b  mov     rcx, [rcx+88h]; Resource
0x14018a4a2  call    cs:__imp_ExReleaseResourceLite
0x14018a4a9  nop     dword ptr [rax+rax+00h]
0x14018a4ae  mov     [rsp+0F8h+var_A4], 1
0x14018a4b6  mov     [rsp+0F8h+var_C0], ebx
0x14018a4ba  mov     [rsp+0F8h+var_C8], 1
0x14018a4c2  mov     [rsp+0F8h+var_D0], r15
0x14018a4c7  mov     [rsp+0F8h+Timeout], r13
0x14018a4cc  mov     r9, [rsp+0F8h+var_80]
0x14018a4d1  mov     r8, rdi
0x14018a4d4  mov     rdx, [rsp+0F8h+arg_18]
0x14018a4dc  mov     rcx, r14
0x14018a4df  call    TxfLogPriorToWrite
0x14018a4e4  mov     [rsp+0F8h+var_A8], eax
0x14018a4e8  jmp     short loc_14018A54E
0x14018a4ea  xor     ebx, ebx
0x14018a4ec  mov     r14, [rsp+0F8h+arg_0]
0x14018a4f4  mov     rdx, [rsp+0F8h+var_58]
0x14018a4fc  mov     [rsp+0F8h+arg_18], rdx
0x14018a504  mov     rsi, [rsp+0F8h+var_50]
0x14018a50c  mov     rax, [rsp+0F8h+var_48]
0x14018a514  mov     [rsp+0F8h+var_80], rax
0x14018a519  mov     rdi, [rsp+0F8h+var_78]
0x14018a521  jmp     short loc_14018A54E
0x14018a523  test    dword ptr [rdi+8], 2000h
0x14018a52a  jz      loc_14018A462
0x14018a530  mov     rdi, [rdi+20h]
0x14018a534  mov     [rsp+0F8h+var_88], rdi
0x14018a539  jmp     loc_14018A450
0x14018a53e  mov     rdi, rbx
0x14018a541  mov     [rsp+0F8h+var_78], rbx
0x14018a549  jmp     loc_14018A488
0x14018a54e  test    rdi, rdi
0x14018a551  jz      short loc_14018A5B7
0x14018a553  mov     [rsp+0F8h+var_B0], bl
0x14018a557  mov     r13, rdi
0x14018a55a  mov     r15, [rdi+10h]
0x14018a55e  test    r15, r15
0x14018a561  jz      loc_14018A6CF
0x14018a567  mov     r15, [r15+40h]
0x14018a56b  mov     al, bl
0x14018a56d  mov     [rsp+0F8h+var_B8], bl
0x14018a571  mov     r12, rbx
0x14018a574  test    r15, r15
0x14018a577  jz      short loc_14018A598
0x14018a579  test    al, al
0x14018a57b  jnz     short loc_14018A598
0x14018a57d  mov     dl, 1; Wait
0x14018a57f  mov     rcx, [r15+88h]; Resource
0x14018a586  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14018a58d  nop     dword ptr [rax+rax+00h]
0x14018a592  mov     al, 1
0x14018a594  mov     [rsp+0F8h+var_B8], al
0x14018a598  lock dec dword ptr [r13+4]
0x14018a59d  cmp     [r13+4], ebx
0x14018a5a1  jz      loc_14018A6B4
0x14018a5a7  mov     r13, r12
0x14018a5aa  test    r12, r12
0x14018a5ad  jnz     short loc_14018A571
0x14018a5af  test    al, al
0x14018a5b1  jnz     loc_14018A693
0x14018a5b7  cmp     [rsp+0F8h+var_A8], ebx
0x14018a5bb  jz      short loc_14018A5CA
0x14018a5bd  mov     rax, [rdi+10h]
0x14018a5c1  mov     rcx, [rax+40h]
0x14018a5c5  bts     dword ptr [rcx+4], 0Dh
0x14018a5ca  mov     r12, [rsp+0F8h+var_70]
0x14018a5d2  mov     [rsp+0F8h+var_A8], ebx
0x14018a5d6  lea     rdi, [rsi+0A0h]
0x14018a5dd  mov     rdx, rdi
0x14018a5e0  lea     rcx, [rsi+78h]
0x14018a5e4  call    cs:__imp_FsRtlAcquireHeaderMutex
0x14018a5eb  nop     dword ptr [rax+rax+00h]
0x14018a5f0  mov     rax, [rsp+0F8h+var_60]
0x14018a5f8  mov     rcx, [rsp+0F8h+var_A0]
0x14018a5fd  cmp     rax, [rcx+28h]
0x14018a601  jle     short loc_14018A62D
0x14018a603  sub     rax, [rsp+0F8h+var_80]
0x14018a608  lea     rdx, [rsp+0F8h+arg_10]
0x14018a610  mov     [rsp+0F8h+var_D0], rdx
0x14018a615  mov     byte ptr [rsp+0F8h+Timeout], 1
0x14018a61a  mov     r9, rax
0x14018a61d  mov     r8, [rsp+0F8h+var_80]
0x14018a622  mov     rdx, rsi
0x14018a625  mov     rcx, r14
0x14018a628  call    NtfsGetIoAtEof
0x14018a62d  mov     rdx, rdi
0x14018a630  lea     rcx, [rsi+78h]
0x14018a634  call    cs:__imp_FsRtlReleaseHeaderMutex
0x14018a63b  nop     dword ptr [rax+rax+00h]
0x14018a640  mov     r15, [rsp+0F8h+arg_8]
0x14018a648  mov     rdi, [rsp+0F8h+arg_18]
0x14018a650  mov     r13d, [rsp+0F8h+var_A4]
0x14018a655  mov     rdx, [rsp+0F8h+var_40]
0x14018a65d  jmp     loc_14018A7B4
0x14018a662  mov     rcx, [rcx+88h]; Resource
0x14018a669  call    cs:__imp_ExReleaseResourceLite
0x14018a670  nop     dword ptr [rax+rax+00h]
0x14018a675  jmp     loc_14018A5D2
0x14018a67a  mov     rdi, rbx
0x14018a67d  cmp     [rsi+10h], rbx
0x14018a681  jz      loc_14018A398
0x14018a687  mov     rdi, [rsi+0B8h]
0x14018a68e  jmp     loc_14018A398
0x14018a693  test    r15, r15
0x14018a696  jz      loc_14018A5B7
0x14018a69c  mov     rcx, [r15+88h]; Resource
0x14018a6a3  call    cs:__imp_ExReleaseResourceLite
0x14018a6aa  nop     dword ptr [rax+rax+00h]
0x14018a6af  jmp     loc_14018A5B7
0x14018a6b4  mov     r12, [r13+28h]
0x14018a6b8  mov     rcx, r13; Entry
0x14018a6bb  call    TxfDeleteTxfVscb
0x14018a6c0  mov     al, bl
0x14018a6c2  mov     [rsp+0F8h+var_B8], bl
0x14018a6c6  mov     [rsp+0F8h+var_B0], bl
0x14018a6ca  jmp     loc_14018A5A7
0x14018a6cf  mov     r15, rbx
0x14018a6d2  jmp     loc_14018A56B
0x14018a6d7  test    r14, r14
0x14018a6da  jz      short loc_14018A700
0x14018a6dc  mov     eax, [r14+10h]
0x14018a6e0  bt      rax, 1Eh
0x14018a6e5  jb      loc_14018A3A5
0x14018a6eb  mov     rax, [r14+90h]
0x14018a6f2  mov     ecx, [rax+10h]
0x14018a6f5  bt      rcx, 1Eh
0x14018a6fa  jb      loc_14018A3A5
0x14018a700  mov     rcx, [rdi+60h]
0x14018a704  add     rcx, 870h; Resource
0x14018a70b  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x14018a712  nop     dword ptr [rax+rax+00h]
0x14018a717  test    al, al
0x14018a719  jnz     loc_14018A3A5
0x14018a71f  test    r15b, r15b
0x14018a722  jz      short loc_14018A734
0x14018a724  mov     rcx, [rdi+70h]; Resource
0x14018a728  call    cs:__imp_ExReleaseResourceLite
0x14018a72f  nop     dword ptr [rax+rax+00h]
0x14018a734  mov     rcx, [rdi+60h]
0x14018a738  mov     [rsp+0F8h+Timeout], rbx; Timeout
0x14018a73d  xor     r9d, r9d; Alertable
0x14018a740  xor     r8d, r8d; WaitMode
0x14018a743  xor     edx, edx; WaitReason
0x14018a745  mov     rcx, [rcx+598h]; Object
0x14018a74c  call    cs:__imp_KeWaitForSingleObject
0x14018a753  nop     dword ptr [rax+rax+00h]
0x14018a758  jmp     loc_14018A3AA
0x14018a75d  add     eax, [rcx+28h]
0x14018a760  mov     [rsp+0F8h+var_90], eax
0x14018a764  mov     rcx, [rcx]
0x14018a767  jmp     loc_14018A354
0x14018a76c  xor     r9d, r9d
0x14018a76f  mov     r8b, 1
0x14018a772  mov     rdx, rsi
0x14018a775  mov     rcx, r14
0x14018a778  call    NtfsAcquirePagingShared
0x14018a77d  cmp     byte ptr [rsi+1CCh], 0
0x14018a784  jz      loc_14018A3D3
0x14018a78a  mov     rdx, rsi
0x14018a78d  call    NtfsReleasePagingResourcePriv
0x14018a792  mov     r8b, 1
0x14018a795  mov     rdx, rsi
0x14018a798  mov     rcx, r14
0x14018a79b  call    NtfsAcquirePagingResourceExclusive
0x14018a7a0  jmp     loc_14018A3D3
0x14018a7a5  cmp     [rcx+28h], rbx
0x14018a7a9  jz      loc_14018A5D6
0x14018a7af  jmp     loc_14018A40B
0x14018a7b4  mov     r8, [r12]; MdlChain
0x14018a7b8  mov     rcx, rdi; FileObject
0x14018a7bb  call    cs:__imp_CcMdlWriteComplete
0x14018a7c2  nop     dword ptr [rax+rax+00h]
0x14018a7c7  nop
0x14018a7c8  mov     rax, [rsp+0F8h+var_A0]
0x14018a7cd  cmp     [rax+10h], rbx
0x14018a7d1  jnz     loc_14018A86E
0x14018a7d7  test    r13d, r13d
0x14018a7da  jnz     loc_14018A87B
0x14018a7e0  mov     [r14+18h], ebx
0x14018a7e4  btr     dword ptr [r14+4], 8
0x14018a7ea  mov     [r12], rbx
0x14018a7ee  mov     al, cs:NtfsStatusDebugFlags
0x14018a7f4  test    r15, r15
0x14018a7f7  setnz   r9b
0x14018a7fb  mov     dword ptr [rsp+0F8h+Timeout], 1
0x14018a803  xor     r8d, r8d
  ... truncated ...
```

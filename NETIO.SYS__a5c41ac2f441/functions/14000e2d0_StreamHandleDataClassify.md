# StreamHandleDataClassify

- ea: `0x14000e2d0`
- end: `0x14000e8c6`
- name: `StreamHandleDataClassify`
- size: `1526`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x14000d720`

## callees

- `0x14000e2d0`
- `0x140035e50`
- `0x140035e84`
- `0x1400363b4`
- `0x1400365e4`
- `0x14004efd4`
- `0x140050100`
- `0x14006f11c`
- `0x14006feb8`
- `0x14006ff4c`
- `0x140070a64`
- `0x1400716cc`
- `0x140071808`
- `0x140071940`
- `0x140071b64`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000e421`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000e6d7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000e421`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000e6d7`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e3ec`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000e3ec`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000e404`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000e404`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000e707`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000e707`

## string_xrefs

- `0x14000e737`: `StreamHandleDataClassify`

## pseudocode

```c
__int64 __fastcall StreamHandleDataClassify(_BYTE *a1, _DWORD *a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  __int64 v6; // r8
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  KIRQL CurrentIrql; // bl
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // ecx
  __int64 v19; // rbx
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // r8
  int v23; // r14d
  __int64 v24; // rax
  __int64 v25; // r9
  __int64 v26; // r9
  _DWORD *v27; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // r9
  __int64 v32; // rcx
  int v33; // ecx
  __int64 v34; // [rsp+38h] [rbp-80h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-58h] BYREF

  v6 = *(unsigned int *)(a3 + 32);
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (_DWORD)v6 || (v10 = *(_QWORD *)(a3 + 24)) == 0 || !*(_DWORD *)(v10 + 196) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_18;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
    {
      v11 = *(_QWORD *)(a3 + 24);
      if ( v11 )
        v12 = *(unsigned int *)(v11 + 196);
      else
        v12 = 0;
      WPP_SF_qqqLqqDD(
        WPP_GLOBAL_Control->AttachedDevice,
        v12,
        v6,
        *(_QWORD *)(a3 + 8),
        a1,
        a2,
        *a2,
        *((_QWORD *)a2 + 2),
        v11,
        v6,
        v12);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
  {
    v13 = *(_QWORD *)(a3 + 24);
    if ( v13 )
      v14 = *(_QWORD *)(v13 + 128);
    else
      v14 = 0;
    WPP_SF_qqqLqPl(
      WPP_GLOBAL_Control->AttachedDevice,
      v13,
      v14,
      *(_QWORD *)(a3 + 8),
      a1,
      a2,
      *a2,
      v13,
      v14,
      (unsigned __int8)*a5);
  }
LABEL_18:
  CurrentIrql = KeGetCurrentIrql();
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a2 + 10, &LockHandle);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v16 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v16 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v16 = 4;
  }
  v18 = *a2;
  if ( *a2 == 2 )
  {
    v19 = StreamAccumulateData(a2, a3, a4, a1);
    if ( !v19 )
    {
      v21 = *(_DWORD *)(*((_QWORD *)a2 + 2) + 196LL);
      if ( (v21 & 0x180000) != 0 )
      {
        a1[304] = 1;
        a1[408] = 1;
      }
      else if ( (v21 & 0xC) != 0 )
      {
        a1[96] = 1;
        a1[200] = 1;
      }
      if ( *a2 == 2 )
      {
        v22 = *(_QWORD *)(a3 + 24);
        if ( v22
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
        {
          WPP_SF_qqqLqq(
            WPP_GLOBAL_Control->AttachedDevice,
            56,
            v22,
            *(_QWORD *)(a3 + 8),
            a1,
            a2,
            2,
            *((_QWORD *)a2 + 2),
            *(_QWORD *)(a3 + 24));
        }
      }
      else
      {
        StreamGetClassifyDataFromCalloutContext(a3, a2, a1);
      }
      goto LABEL_61;
    }
    goto LABEL_57;
  }
  if ( (unsigned int)(v18 - 3) > 1 )
  {
    v23 = 5;
    if ( v18 != 5 )
    {
      v19 = 0;
      if ( v18 != 1 )
        goto LABEL_61;
LABEL_44:
      if ( *a2 == 1 && *((_BYTE *)a2 + 5) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
        {
          v24 = *(_QWORD *)(a3 + 24);
          if ( v24 )
            v25 = *(_QWORD *)(v24 + 128);
          else
            v25 = 0;
          WPP_SF_PqqqLq(
            WPP_GLOBAL_Control->AttachedDevice,
            58,
            v17,
            v25,
            *(_QWORD *)(a3 + 8),
            a1,
            a2,
            1,
            *(_QWORD *)(a3 + 24));
        }
        v26 = *((_QWORD *)a2 + 3);
        if ( v26 )
        {
          if ( (*(_DWORD *)(v26 + 196) & 0x18000C) != 0 )
          {
            *a5 = 1;
          }
          else
          {
            v19 = StreamDataCat(*(_QWORD *)(a3 + 8), (_DWORD)a1, (_DWORD)a2, v26, a3 + 24, *(_BYTE *)(a3 + 16));
            if ( v19 )
            {
              *a2 = 6;
LABEL_57:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
              {
                LODWORD(v34) = *a2;
                WPP_SF_DqqqL(
                  WPP_GLOBAL_Control->AttachedDevice,
                  59,
                  v20,
                  (unsigned int)v19,
                  *(_QWORD *)(a3 + 8),
                  a1,
                  a2,
                  v34);
              }
              goto LABEL_61;
            }
          }
        }
        else
        {
          *((_QWORD *)a2 + 3) = *(_QWORD *)(a3 + 24);
          *(_QWORD *)(a3 + 24) = 0;
        }
      }
      if ( !*(_QWORD *)(a3 + 24) )
        goto LABEL_86;
      v29 = *((_QWORD *)a2 + 2);
      if ( v29 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
LABEL_85:
          *((_QWORD *)a2 + 2) = *(_QWORD *)(a3 + 24);
LABEL_86:
          v32 = *((_QWORD *)a2 + 2);
          if ( v32 )
            StreamCheckAndMarkEof(v32, a1);
          goto LABEL_61;
        }
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
          WPP_SF_qqLq(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_62149f72f91b37f589f88293e09854d5_Traceguids,
            *(_QWORD *)(a3 + 8),
            a2,
            *a2,
            *((_QWORD *)a2 + 2));
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
      {
        v30 = *(_QWORD *)(a3 + 24);
        if ( v30 )
        {
          v23 = *(_DWORD *)(v30 + 80);
          v31 = *(_QWORD *)(v30 + 128);
        }
        else
        {
          v31 = 0;
        }
        WPP_SF_PqqqLqL(WPP_GLOBAL_Control->AttachedDevice, v16, v29, v31, *(_QWORD *)(a3 + 8), a1, a2, *a2, v30, v23);
      }
      goto LABEL_85;
    }
    if ( *(_DWORD *)a3 == a2[2] )
    {
      v16 = *(unsigned __int8 *)(a3 + 36);
      v19 = 0;
      if ( (_BYTE)v16 )
      {
        v17 = *(unsigned __int8 *)(a3 + 37);
        if ( !(_BYTE)v17
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0 )
        {
          WPP_SF_qqqLqqll(
            WPP_GLOBAL_Control->AttachedDevice,
            v16,
            v17,
            *(_QWORD *)(a3 + 8),
            a1,
            a2,
            5,
            *((_QWORD *)a2 + 2),
            *(_QWORD *)(a3 + 24),
            v16,
            *(unsigned __int8 *)(a3 + 37));
        }
      }
      goto LABEL_44;
    }
  }
  v19 = StreamAbsorbData(a2, a3, a5, a1);
  if ( v19 )
    goto LABEL_57;
  if ( *a2 == 3 )
  {
    v33 = *(_DWORD *)(*((_QWORD *)a2 + 2) + 196LL);
    if ( (v33 & 0x180000) != 0 )
    {
      a1[304] = 1;
      a1[408] = 1;
    }
    else if ( (v33 & 0xC) != 0 )
    {
      a1[96] = 1;
      a1[200] = 1;
    }
  }
LABEL_61:
  if ( gWfpPerProContext )
  {
    v27 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v27 == 4 )
      *v27 = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v19
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"StreamHandleDataClassify",
      v19);
  }
  return v19;
}

```

## disassembly

```asm
0x14000e2d0  push    rbx
0x14000e2d2  push    rbp
0x14000e2d3  push    rsi
0x14000e2d4  push    rdi
0x14000e2d5  push    r12
0x14000e2d7  push    r14
0x14000e2d9  push    r15
0x14000e2db  sub     rsp, 80h
0x14000e2e2  mov     r15, [rsp+0B8h+arg_20]
0x14000e2ea  lea     r12, WPP_GLOBAL_Control
0x14000e2f1  xor     eax, eax
0x14000e2f3  mov     rsi, r8
0x14000e2f6  mov     r8d, [r8+20h]
0x14000e2fa  xorps   xmm0, xmm0
0x14000e2fd  mov     qword ptr [rsp+0B8h+LockHandle.OldIrql], rax
0x14000e302  mov     r14, r9
0x14000e305  mov     rdi, rdx
0x14000e308  mov     rbp, rcx
0x14000e30b  movups  xmmword ptr [rsp+0B8h+LockHandle.LockQueue.Next], xmm0
0x14000e310  test    r8d, r8d
0x14000e313  jnz     short loc_14000E327
0x14000e315  mov     rax, [rsi+18h]
0x14000e319  test    rax, rax
0x14000e31c  jz      short loc_14000E327
0x14000e31e  cmp     [rax+0C4h], r8d
0x14000e325  jnz     short loc_14000E38D
0x14000e327  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e32e  cmp     rcx, r12
0x14000e331  jz      loc_14000E3EC
0x14000e337  cmp     byte ptr [rcx+29h], 3
0x14000e33b  jb      short loc_14000E38D
0x14000e33d  test    dword ptr [rcx+2Ch], 4000h
0x14000e344  jz      short loc_14000E38D
0x14000e346  mov     rax, [rsi+18h]
0x14000e34a  test    rax, rax
0x14000e34d  jz      short loc_14000E357
0x14000e34f  mov     edx, [rax+0C4h]
0x14000e355  jmp     short loc_14000E359
0x14000e357  xor     edx, edx
0x14000e359  mov     r9, [rsi+8]
0x14000e35d  mov     rcx, [rcx+18h]
0x14000e361  mov     [rsp+0B8h+var_68], edx
0x14000e365  mov     [rsp+0B8h+var_70], r8d
0x14000e36a  mov     [rsp+0B8h+var_78], rax
0x14000e36f  mov     rax, [rdi+10h]
0x14000e373  mov     [rsp+0B8h+var_80], rax
0x14000e378  mov     eax, [rdi]
0x14000e37a  mov     dword ptr [rsp+0B8h+var_88], eax
0x14000e37e  mov     [rsp+0B8h+var_90], rdi
0x14000e383  mov     [rsp+0B8h+var_98], rbp
0x14000e388  call    WPP_SF_qqqLqqDD
0x14000e38d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e394  cmp     rcx, r12
0x14000e397  jz      short loc_14000E3EC
0x14000e399  cmp     byte ptr [rcx+29h], 4
0x14000e39d  jb      short loc_14000E3EC
0x14000e39f  test    dword ptr [rcx+2Ch], 4000h
0x14000e3a6  jz      short loc_14000E3EC
0x14000e3a8  mov     rdx, [rsi+18h]
0x14000e3ac  test    rdx, rdx
0x14000e3af  jz      short loc_14000E3BA
0x14000e3b1  mov     r8, [rdx+80h]
0x14000e3b8  jmp     short loc_14000E3BD
0x14000e3ba  xor     r8d, r8d
0x14000e3bd  movzx   eax, byte ptr [r15]
0x14000e3c1  mov     r9, [rsi+8]
0x14000e3c5  mov     rcx, [rcx+18h]
0x14000e3c9  mov     [rsp+0B8h+var_70], eax
0x14000e3cd  mov     eax, [rdi]
0x14000e3cf  mov     [rsp+0B8h+var_78], r8
0x14000e3d4  mov     [rsp+0B8h+var_80], rdx
0x14000e3d9  mov     dword ptr [rsp+0B8h+var_88], eax
0x14000e3dd  mov     [rsp+0B8h+var_90], rdi
0x14000e3e2  mov     [rsp+0B8h+var_98], rbp
0x14000e3e7  call    WPP_SF_qqqLqPl
0x14000e3ec  call    cs:__imp_KeGetCurrentIrql
0x14000e3f3  nop     dword ptr [rax+rax+00h]
0x14000e3f8  lea     rcx, [rdi+50h]; SpinLock
0x14000e3fc  movzx   ebx, al
0x14000e3ff  lea     rdx, [rsp+0B8h+LockHandle]; LockHandle
0x14000e404  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000e40b  nop     dword ptr [rax+rax+00h]
0x14000e410  cmp     bl, 2
0x14000e413  jz      short loc_14000E455
0x14000e415  cmp     cs:gWfpPerProContext, 0
0x14000e41d  jz      short loc_14000E455
0x14000e41f  xor     ecx, ecx; ProcNumber
0x14000e421  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000e428  nop     dword ptr [rax+rax+00h]
0x14000e42d  imul    eax, cs:gWfpPerProContextSize
0x14000e434  mov     ecx, eax
0x14000e436  mov     rax, cs:gWfpPerProContext
0x14000e43d  mov     rdx, [rcx+rax]
0x14000e441  mov     rax, ds:0FFFFF78000000008h
0x14000e44b  mov     [rdx+8], rax
0x14000e44f  mov     dword ptr [rdx], 4
0x14000e455  mov     ecx, [rdi]
0x14000e457  cmp     ecx, 2
0x14000e45a  jnz     loc_14000E530
0x14000e460  mov     r9, rbp
0x14000e463  mov     r8, r14
0x14000e466  mov     rdx, rsi
0x14000e469  mov     rcx, rdi
0x14000e46c  call    StreamAccumulateData
0x14000e471  mov     rbx, rax
0x14000e474  test    rax, rax
0x14000e477  jnz     loc_14000E686
0x14000e47d  mov     rcx, [rdi+10h]
0x14000e481  mov     eax, [rcx+0C4h]
0x14000e487  test    eax, 180000h
0x14000e48c  jnz     short loc_14000E49F
0x14000e48e  test    al, 0Ch
0x14000e490  jz      short loc_14000E4AD
0x14000e492  mov     byte ptr [rbp+60h], 1
0x14000e496  mov     byte ptr [rbp+0C8h], 1
0x14000e49d  jmp     short loc_14000E4AD
0x14000e49f  mov     byte ptr [rbp+130h], 1
0x14000e4a6  mov     byte ptr [rbp+198h], 1
0x14000e4ad  cmp     dword ptr [rdi], 2
0x14000e4b0  jnz     short loc_14000E51D
0x14000e4b2  mov     r8, [rsi+18h]
0x14000e4b6  test    r8, r8
0x14000e4b9  jz      loc_14000E6CB
0x14000e4bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4c6  cmp     rcx, r12
0x14000e4c9  jz      loc_14000E6CB
0x14000e4cf  cmp     byte ptr [rcx+29h], 3
0x14000e4d3  jb      loc_14000E6CB
0x14000e4d9  test    dword ptr [rcx+2Ch], 4000h
0x14000e4e0  jz      loc_14000E6CB
0x14000e4e6  mov     rax, [rdi+10h]
0x14000e4ea  mov     edx, 38h ; '8'
0x14000e4ef  mov     r9, [rsi+8]
0x14000e4f3  mov     rcx, [rcx+18h]
0x14000e4f7  mov     [rsp+0B8h+var_78], r8
0x14000e4fc  mov     [rsp+0B8h+var_80], rax
0x14000e501  mov     dword ptr [rsp+0B8h+var_88], 2
0x14000e509  mov     [rsp+0B8h+var_90], rdi
0x14000e50e  mov     [rsp+0B8h+var_98], rbp
0x14000e513  call    WPP_SF_qqqLqq
0x14000e518  jmp     loc_14000E6CB
0x14000e51d  mov     r8, rbp
0x14000e520  mov     rdx, rdi
0x14000e523  mov     rcx, rsi
0x14000e526  call    StreamGetClassifyDataFromCalloutContext
0x14000e52b  jmp     loc_14000E6CB
0x14000e530  lea     eax, [rcx-3]
0x14000e533  cmp     eax, 1
0x14000e536  jbe     loc_14000E862
0x14000e53c  mov     r14d, 5
0x14000e542  cmp     ecx, r14d
0x14000e545  jnz     short loc_14000E5BA
0x14000e547  mov     eax, [rdi+8]
0x14000e54a  cmp     [rsi], eax
0x14000e54c  jnz     loc_14000E862
0x14000e552  movzx   edx, byte ptr [rsi+24h]
0x14000e556  xor     ebx, ebx
0x14000e558  test    dl, dl
0x14000e55a  jz      short loc_14000E5C5
0x14000e55c  movzx   r8d, byte ptr [rsi+25h]
0x14000e561  test    r8b, r8b
0x14000e564  jnz     short loc_14000E5C5
0x14000e566  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e56d  cmp     rcx, r12
0x14000e570  jz      short loc_14000E5C5
0x14000e572  cmp     byte ptr [rcx+29h], 3
0x14000e576  jb      short loc_14000E5C5
0x14000e578  test    dword ptr [rcx+2Ch], 4000h
0x14000e57f  jz      short loc_14000E5C5
0x14000e581  mov     rax, [rsi+18h]
0x14000e585  mov     r9, [rsi+8]
0x14000e589  mov     rcx, [rcx+18h]
0x14000e58d  mov     [rsp+0B8h+var_68], r8d
0x14000e592  mov     [rsp+0B8h+var_70], edx
0x14000e596  mov     [rsp+0B8h+var_78], rax
0x14000e59b  mov     rax, [rdi+10h]
0x14000e59f  mov     [rsp+0B8h+var_80], rax
0x14000e5a4  mov     dword ptr [rsp+0B8h+var_88], r14d
0x14000e5a9  mov     [rsp+0B8h+var_90], rdi
0x14000e5ae  mov     [rsp+0B8h+var_98], rbp
0x14000e5b3  call    WPP_SF_qqqLqqll
0x14000e5b8  jmp     short loc_14000E5C5
0x14000e5ba  xor     ebx, ebx
0x14000e5bc  cmp     ecx, 1
0x14000e5bf  jnz     loc_14000E6CB
0x14000e5c5  cmp     dword ptr [rdi], 1
0x14000e5c8  jnz     loc_14000E77F
0x14000e5ce  cmp     byte ptr [rdi+5], 0
0x14000e5d2  jz      loc_14000E77F
0x14000e5d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e5df  cmp     rcx, r12
0x14000e5e2  jz      short loc_14000E636
0x14000e5e4  cmp     byte ptr [rcx+29h], 4
0x14000e5e8  jb      short loc_14000E636
0x14000e5ea  test    dword ptr [rcx+2Ch], 4000h
0x14000e5f1  jz      short loc_14000E636
0x14000e5f3  mov     rax, [rsi+18h]
0x14000e5f7  test    rax, rax
0x14000e5fa  jz      short loc_14000E605
0x14000e5fc  mov     r9, [rax+80h]
0x14000e603  jmp     short loc_14000E608
0x14000e605  xor     r9d, r9d
0x14000e608  mov     rcx, [rcx+18h]
0x14000e60c  mov     edx, 3Ah ; ':'
0x14000e611  mov     [rsp+0B8h+var_78], rax
0x14000e616  mov     rax, [rsi+8]
0x14000e61a  mov     dword ptr [rsp+0B8h+var_80], 1
0x14000e622  mov     [rsp+0B8h+var_88], rdi
0x14000e627  mov     [rsp+0B8h+var_90], rbp
0x14000e62c  mov     [rsp+0B8h+var_98], rax
0x14000e631  call    WPP_SF_PqqqLq
0x14000e636  mov     r9, [rdi+18h]
0x14000e63a  test    r9, r9
0x14000e63d  jz      loc_14000E76F
0x14000e643  test    dword ptr [r9+0C4h], 18000Ch
0x14000e64e  jnz     loc_14000E769
0x14000e654  movzx   eax, byte ptr [rsi+10h]
0x14000e658  lea     rcx, [rsi+18h]
0x14000e65c  mov     byte ptr [rsp+0B8h+var_90], al
0x14000e660  mov     r8, rdi
0x14000e663  mov     [rsp+0B8h+var_98], rcx
0x14000e668  mov     rdx, rbp
0x14000e66b  mov     rcx, [rsi+8]
0x14000e66f  call    StreamDataCat
0x14000e674  mov     rbx, rax
0x14000e677  test    rax, rax
0x14000e67a  jz      loc_14000E77F
0x14000e680  mov     dword ptr [rdi], 6
0x14000e686  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e68d  cmp     rcx, r12
0x14000e690  jz      short loc_14000E6CB
0x14000e692  cmp     byte ptr [rcx+29h], 2
0x14000e696  jb      short loc_14000E6CB
0x14000e698  test    dword ptr [rcx+2Ch], 4000h
0x14000e69f  jz      short loc_14000E6CB
0x14000e6a1  mov     eax, [rdi]
0x14000e6a3  mov     r9d, ebx
0x14000e6a6  mov     rcx, [rcx+18h]
0x14000e6aa  mov     edx, 3Bh ; ';'
0x14000e6af  mov     dword ptr [rsp+0B8h+var_80], eax
0x14000e6b3  mov     rax, [rsi+8]
0x14000e6b7  mov     [rsp+0B8h+var_88], rdi
0x14000e6bc  mov     [rsp+0B8h+var_90], rbp
0x14000e6c1  mov     [rsp+0B8h+var_98], rax
0x14000e6c6  call    WPP_SF_DqqqL
0x14000e6cb  cmp     cs:gWfpPerProContext, 0
0x14000e6d3  jz      short loc_14000E702
0x14000e6d5  xor     ecx, ecx; ProcNumber
0x14000e6d7  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000e6de  nop     dword ptr [rax+rax+00h]
0x14000e6e3  imul    eax, cs:gWfpPerProContextSize
0x14000e6ea  mov     ecx, eax
0x14000e6ec  mov     rax, cs:gWfpPerProContext
0x14000e6f3  mov     rdx, [rcx+rax]
0x14000e6f7  cmp     dword ptr [rdx], 4
0x14000e6fa  jnz     short loc_14000E702
0x14000e6fc  mov     dword ptr [rdx], 0
0x14000e702  lea     rcx, [rsp+0B8h+LockHandle]; LockHandle
0x14000e707  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000e70e  nop     dword ptr [rax+rax+00h]
0x14000e713  test    rbx, rbx
0x14000e716  jz      short loc_14000E753
0x14000e718  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e71f  cmp     rcx, r12
0x14000e722  jz      short loc_14000E753
0x14000e724  cmp     byte ptr [rcx+29h], 2
0x14000e728  jb      short loc_14000E753
0x14000e72a  test    dword ptr [rcx+2Ch], 1000h
0x14000e731  jz      short loc_14000E753
0x14000e733  mov     rcx, [rcx+18h]
0x14000e737  lea     r9, aStreamhandleda; "StreamHandleDataClassify"
0x14000e73e  mov     edx, 0Fh
0x14000e743  mov     dword ptr [rsp+0B8h+var_98], ebx
0x14000e747  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000e74e  call    WPP_SF_sd
0x14000e753  mov     rax, rbx
0x14000e756  add     rsp, 80h
0x14000e75d  pop     r15
0x14000e75f  pop     r14
0x14000e761  pop     r12
0x14000e763  pop     rdi
0x14000e764  pop     rsi
0x14000e765  pop     rbp
0x14000e766  pop     rbx
0x14000e767  retn
0x14000e769  mov     byte ptr [r15], 1
0x14000e76d  jmp     short loc_14000E77F
0x14000e76f  mov     rax, [rsi+18h]
0x14000e773  mov     [rdi+18h], rax
0x14000e777  mov     qword ptr [rsi+18h], 0
0x14000e77f  cmp     qword ptr [rsi+18h], 0
0x14000e784  jz      loc_14000E843
0x14000e78a  mov     r8, [rdi+10h]
0x14000e78e  test    r8, r8
0x14000e791  jz      short loc_14000E7DB
0x14000e793  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e79a  cmp     rcx, r12
0x14000e79d  jz      loc_14000E83B
0x14000e7a3  cmp     byte ptr [rcx+29h], 3
0x14000e7a7  jb      short loc_14000E7DB
  ... truncated ...
```

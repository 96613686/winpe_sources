# NtfsSendUnusedClustersHint

- ea: `0x140214400`
- end: `0x1402149c9`
- name: `NtfsSendUnusedClustersHint`
- size: `1481`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400cb8c4`
- `0x14020f3a0`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14003c184`
- `0x14003c210`
- `0x140040030`
- `0x1400400d8`
- `0x14004062c`
- `0x140040d48`
- `0x1400410a8`
- `0x140059740`
- `0x14014de30`
- `0x140214400`
- `0x14024354c`

## import_xrefs

- `ntoskrnl!FsRtlLookupLastBaseMcbEntryAndIndex` at `0x1402147f3`
- `ntoskrnl!FsRtlLookupLastBaseMcbEntryAndIndex` at `0x1402147f3`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402145b6`
- `ntoskrnl!IoGetActivityIdThread` at `0x1402145b6`
- `ntoskrnl!FsRtlAddBaseMcbEntryEx` at `0x140214691`
- `ntoskrnl!FsRtlAddBaseMcbEntryEx` at `0x140214691`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402148e6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14021490a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140214925`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4e9e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4ecc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4ee9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402148e6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14021490a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140214925`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4e9e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4ecc`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b4ee9`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402148d0`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402b4e87`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402148d0`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x1402b4e87`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140214514`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x140214514`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402144d5`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14021452c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14021455d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402144d5`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14021452c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14021455d`

## pseudocode

```c
void __fastcall NtfsSendUnusedClustersHint(_QWORD *a1, LONGLONG a2, unsigned int a3, PVOID *a4, _BYTE *a5)
{
  LONGLONG v6; // r13
  _QWORD *v8; // rsi
  __int64 v9; // r14
  char *v10; // r15
  char v11; // bl
  char *v12; // rax
  _OWORD *v13; // rax
  _QWORD *v14; // rbx
  int v15; // edx
  char *v16; // rbx
  _OWORD *v17; // rax
  _OWORD *ActivityIdThread; // rax
  _DWORD *v19; // rbx
  int v20; // edx
  _QWORD *v21; // r8
  unsigned int v22; // eax
  _QWORD *v23; // r8
  _QWORD *v24; // rcx
  int v25; // ecx
  unsigned int v26; // eax
  _QWORD *v27; // rdx
  _QWORD *v28; // rax
  void *v29; // rdx
  int v30; // [rsp+28h] [rbp-70h]
  char v31; // [rsp+40h] [rbp-58h]
  ULONG Index; // [rsp+44h] [rbp-54h] BYREF
  __int64 v33; // [rsp+48h] [rbp-50h]
  __int64 LargeVbn; // [rsp+50h] [rbp-48h] BYREF
  char *v35; // [rsp+58h] [rbp-40h]
  __int64 v36; // [rsp+60h] [rbp-38h]

  v6 = a3;
  v8 = a1;
  v36 = a1[13];
  v9 = v36;
  v10 = 0;
  v35 = 0;
  v11 = 0;
  v31 = 0;
  if ( !*(_BYTE *)(v36 + 5521) )
  {
    if ( a2 || a3 )
    {
      if ( (a1[2] & 0x100000LL) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
      {
        McTemplateU0ppd_EtwWriteTransfer((_DWORD)a1, (unsigned int)delnotify_c196, v36, a2, a3);
      }
    }
    else if ( (a1[2] & 0x100000LL) == 0
           && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
    {
      McTemplateU0p_EtwWriteTransfer(a1, delnotify_c206, v36);
    }
    if ( *a4 )
    {
      v19 = (_DWORD *)*((_QWORD *)*a4 + 4);
    }
    else
    {
      if ( !(_DWORD)v6
        || *a5
        || (v12 = (char *)ExAllocateFromLookasideListEx(&NtfsDeallocatedClustersLookasideList),
            v10 = v12,
            (v35 = v12) == 0) )
      {
        v11 = 0;
        goto LABEL_54;
      }
      *(_OWORD *)v12 = 0;
      *((_OWORD *)v12 + 1) = 0;
      *((_OWORD *)v12 + 2) = 0;
      *((_OWORD *)v12 + 3) = 0;
      FsRtlInitializeBaseMcbEx((PBASE_MCB)(v12 + 16), PoolType, 1u);
      v31 = 1;
      v13 = ExAllocateFromLookasideListEx(&NtfsMarkUnusedContextLookasideList);
      *a4 = v13;
      *v13 = 0;
      v13[1] = 0;
      v13[2] = 0;
      v13[3] = 0;
      *((_QWORD *)v13 + 8) = 0;
      v14 = *a4;
      v14[4] = ExAllocateFromLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList);
      memset(*((void **)*a4 + 4), 0, 0x400u);
      *((_DWORD *)v10 + 14) |= 1u;
      *((_QWORD *)*a4 + 3) = v10;
      v10 = 0;
      v35 = 0;
      v16 = (char *)*a4;
      v17 = (_OWORD *)v8[15];
      if ( v17 )
      {
        *(_OWORD *)(v16 + 56) = *v17;
        *((_QWORD *)v16 + 6) = v16 + 56;
      }
      else
      {
        ActivityIdThread = (_OWORD *)IoGetActivityIdThread();
        if ( ActivityIdThread )
        {
          *(_OWORD *)(v16 + 56) = *ActivityIdThread;
          *((_QWORD *)v16 + 6) = v16 + 56;
        }
        else
        {
          *((_QWORD *)v16 + 6) = 0;
        }
      }
      *((_QWORD *)*a4 + 2) = v9;
      v19 = (_DWORD *)*((_QWORD *)*a4 + 4);
      *v19 = 1024;
      v19[1] = 1;
      v19[2] = 0x80000000;
      v19[5] = 32;
      if ( (v8[2] & 0x100000) == 0 && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        McTemplateU0pppp_EtwWriteTransfer(
          *((_QWORD *)*a4 + 3),
          v15,
          v9,
          (unsigned int)*a4,
          *((_QWORD *)*a4 + 3),
          *((_QWORD *)*a4 + 3) + 16);
    }
    Index = v19[5];
    LODWORD(LargeVbn) = (*v19 - Index) & 0xFFFFFFF0;
    if ( !(_DWORD)v6 )
      goto LABEL_36;
    if ( !a2 )
    {
      v33 = 0xD30039016CLL;
      NtfsAttachCorruptionSimple((_DWORD)v8, 1, 2050, 3735916, 0, v30);
      NtfsAttachRepairInfoPriv(v8, 0, 0, 0xD30039016CLL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v8, 3221225522LL, 3735916);
      NtfsRaiseStatusInternal((_DWORD)v8, -1073741774, 0, 0, 3735916);
      __debugbreak();
      JUMPOUT(0x1402149C9LL);
    }
    a1 = a5;
    if ( !*a5 )
    {
      LODWORD(v33) = v19[6];
      if ( FsRtlAddBaseMcbEntryEx((PBASE_MCB)(*((_QWORD *)*a4 + 3) + 16LL), a2, a2, v6) >= 0 )
      {
        v21 = (_QWORD *)((char *)v19 + (unsigned int)v33 + Index);
        v33 = (__int64)v21;
        if ( (v8[2] & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          McTemplateU0pidp_EtwWriteTransfer(*((_QWORD *)*a4 + 3) + 16, v20, v9, a2, v6, *((_QWORD *)*a4 + 3) + 16);
          v21 = (_QWORD *)v33;
        }
        *v21 = a2 << *(_BYTE *)(v9 + 488);
        v21[1] = v6 << *(_BYTE *)(v9 + 488);
        v19[6] += 16;
        *(_QWORD *)(*((_QWORD *)*a4 + 3) + 48LL) += v6;
        goto LABEL_36;
      }
      a1 = a5;
    }
    *(_BYTE *)a1 = 1;
    if ( (v8[2] & 0x100000) != 0 || (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) == 0 )
    {
LABEL_37:
      v22 = v19[6];
      if ( v22 >= (unsigned int)LargeVbn || (*(_BYTE *)a1 || !(_DWORD)v6) && v22 )
      {
        v23 = *(_QWORD **)(v9 + 1616);
        if ( *v23 != v9 + 1608 )
          __fastfail(3u);
        v24 = (_QWORD *)*((_QWORD *)*a4 + 3);
        *v24 = v9 + 1608;
        v24[1] = v23;
        *v23 = v24;
        *(_QWORD *)(v9 + 1616) = v24;
        *(_QWORD *)(v9 + 312) += *(_QWORD *)(*((_QWORD *)*a4 + 3) + 48LL);
        *((_QWORD *)*a4 + 5) = *(_QWORD *)(*((_QWORD *)*a4 + 3) + 48LL);
        Index = 0;
        LargeVbn = 0;
        FsRtlLookupLastBaseMcbEntryAndIndex((PBASE_MCB)(*((_QWORD *)*a4 + 3) + 16LL), &LargeVbn, &LargeVbn, &Index);
        *(_DWORD *)(v9 + 1512) += Index;
        v26 = *(_DWORD *)(v9 + 1512);
        if ( *(_DWORD *)(v9 + 8964) < v26 )
          *(_DWORD *)(v9 + 8964) = v26;
        if ( (v8[2] & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          McTemplateU0ppp_EtwWriteTransfer(v25, (unsigned int)delnotify_c508, v9, (unsigned int)*a4, (char)v8);
        }
        *v19 = 28;
        a1 = v8 + 58;
        v27 = (_QWORD *)v8[59];
        if ( (_QWORD *)*v27 != v8 + 58 )
          __fastfail(3u);
        v28 = *a4;
        *v28 = a1;
        v28[1] = v27;
        *v27 = v28;
        v8[59] = v28;
        *a4 = 0;
      }
      v11 = v31;
      goto LABEL_54;
    }
    McTemplateU0pp_EtwWriteTransfer(a1, delnotify_c427, v9, *((_QWORD *)*a4 + 3) + 16LL);
LABEL_36:
    a1 = a5;
    goto LABEL_37;
  }
  a1 = *a4;
  if ( *a4 )
  {
    NtfsFreeMarkUnusedContext(a1);
    *a4 = 0;
  }
LABEL_54:
  if ( v10 )
  {
    if ( (v8[2] & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000) != 0 )
    {
      McTemplateU0p_EtwWriteTransfer(a1, delnotify_c557, v9);
    }
    if ( v11 )
      FsRtlUninitializeBaseMcb((PBASE_MCB)(v10 + 16));
    ExFreeToLookasideListEx(&NtfsDeallocatedClustersLookasideList, v10);
    if ( *a4 )
    {
      v29 = (void *)*((_QWORD *)*a4 + 4);
      if ( v29 )
        ExFreeToLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList, v29);
    }
    if ( *a4 )
    {
      ExFreeToLookasideListEx(&NtfsMarkUnusedContextLookasideList, *a4);
      *a4 = 0;
    }
  }
}

```

## disassembly

```asm
0x140214400  mov     [rsp+arg_8], rbx
0x140214405  mov     [rsp+arg_10], rsi
0x14021440a  mov     [rsp+arg_18], r9
0x14021440f  mov     [rsp+arg_0], rcx
0x140214414  push    rdi
0x140214415  push    r12
0x140214417  push    r13
0x140214419  push    r14
0x14021441b  push    r15
0x14021441d  sub     rsp, 70h
0x140214421  mov     rdi, r9
0x140214424  mov     r13d, r8d
0x140214427  mov     r12, rdx
0x14021442a  mov     rsi, rcx
0x14021442d  mov     r14, [rcx+68h]
0x140214431  mov     [rsp+98h+var_38], r14
0x140214436  xor     r15d, r15d
0x140214439  mov     [rsp+98h+var_40], r15
0x14021443e  xor     bl, bl
0x140214440  mov     [rsp+98h+var_58], bl
0x140214444  cmp     [r14+1591h], bl
0x14021444b  jnz     loc_140214882
0x140214451  test    rdx, rdx
0x140214454  jnz     short loc_14021447F
0x140214456  test    r8d, r8d
0x140214459  jnz     short loc_14021447F
0x14021445b  mov     eax, [rcx+10h]
0x14021445e  bt      rax, 14h
0x140214463  jb      short loc_1402144A9
0x140214465  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x14021446c  jz      short loc_1402144A9
0x14021446e  mov     r8, r14
0x140214471  lea     rdx, delnotify_c206
0x140214478  call    McTemplateU0p_EtwWriteTransfer
0x14021447d  jmp     short loc_1402144A9
0x14021447f  mov     eax, [rcx+10h]
0x140214482  bt      rax, 14h
0x140214487  jb      short loc_1402144A9
0x140214489  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x140214490  jz      short loc_1402144A9
0x140214492  mov     dword ptr [rsp+98h+var_78], r13d
0x140214497  mov     r9, r12
0x14021449a  mov     r8, r14
0x14021449d  lea     rdx, delnotify_c196
0x1402144a4  call    McTemplateU0ppd_EtwWriteTransfer
0x1402144a9  mov     rbx, [rdi]
0x1402144ac  test    rbx, rbx
0x1402144af  jnz     loc_14021463D
0x1402144b5  test    r13d, r13d
0x1402144b8  jz      loc_140214636
0x1402144be  mov     rax, [rsp+98h+arg_20]
0x1402144c6  cmp     [rax], bl
0x1402144c8  jnz     loc_140214636
0x1402144ce  lea     rcx, NtfsDeallocatedClustersLookasideList; Lookaside
0x1402144d5  call    cs:__imp_ExAllocateFromLookasideListEx
0x1402144dc  nop     dword ptr [rax+rax+00h]
0x1402144e1  mov     r15, rax
0x1402144e4  mov     [rsp+98h+var_40], rax
0x1402144e9  test    rax, rax
0x1402144ec  jz      loc_140214636
0x1402144f2  xorps   xmm0, xmm0
0x1402144f5  movups  xmmword ptr [rax], xmm0
0x1402144f8  movups  xmmword ptr [rax+10h], xmm0
0x1402144fc  movups  xmmword ptr [rax+20h], xmm0
0x140214500  movups  xmmword ptr [rax+30h], xmm0
0x140214504  mov     r8d, 1; Flags
0x14021450a  lea     rcx, [rax+10h]; Mcb
0x14021450e  mov     edx, cs:PoolType; PoolType
0x140214514  call    cs:__imp_FsRtlInitializeBaseMcbEx
0x14021451b  nop     dword ptr [rax+rax+00h]
0x140214520  mov     [rsp+98h+var_58], 1
0x140214525  lea     rcx, NtfsMarkUnusedContextLookasideList; Lookaside
0x14021452c  call    cs:__imp_ExAllocateFromLookasideListEx
0x140214533  nop     dword ptr [rax+rax+00h]
0x140214538  mov     [rdi], rax
0x14021453b  xorps   xmm0, xmm0
0x14021453e  xor     ecx, ecx
0x140214540  movups  xmmword ptr [rax], xmm0
0x140214543  movups  xmmword ptr [rax+10h], xmm0
0x140214547  movups  xmmword ptr [rax+20h], xmm0
0x14021454b  movups  xmmword ptr [rax+30h], xmm0
0x14021454f  mov     [rax+40h], rcx
0x140214553  mov     rbx, [rdi]
0x140214556  lea     rcx, NtfsDeviceManageDataSetAttributesLookasideList; Lookaside
0x14021455d  call    cs:__imp_ExAllocateFromLookasideListEx
0x140214564  nop     dword ptr [rax+rax+00h]
0x140214569  mov     [rbx+20h], rax
0x14021456d  mov     rcx, [rdi]
0x140214570  xor     edx, edx; Val
0x140214572  mov     r8d, 400h; Size
0x140214578  mov     rcx, [rcx+20h]; void *
0x14021457c  call    memset
0x140214581  or      dword ptr [r15+38h], 1
0x140214586  mov     rax, [rdi]
0x140214589  mov     [rax+18h], r15
0x14021458d  xor     r15d, r15d
0x140214590  mov     [rsp+98h+var_40], r15
0x140214595  mov     rbx, [rdi]
0x140214598  mov     rax, [rsi+78h]
0x14021459c  test    rax, rax
0x14021459f  jz      short loc_1402145B6
0x1402145a1  movups  xmm0, xmmword ptr [rax]
0x1402145a4  movups  xmmword ptr [rbx+38h], xmm0
0x1402145a8  lea     rax, [rbx+38h]
0x1402145ac  mov     [rbx+30h], rax
0x1402145b0  mov     rax, [rbx+30h]
0x1402145b4  jmp     short loc_1402145DB
0x1402145b6  call    cs:__imp_IoGetActivityIdThread
0x1402145bd  nop     dword ptr [rax+rax+00h]
0x1402145c2  test    rax, rax
0x1402145c5  jz      short loc_1402145D7
0x1402145c7  lea     rcx, [rbx+38h]
0x1402145cb  movups  xmm0, xmmword ptr [rax]
0x1402145ce  movups  xmmword ptr [rcx], xmm0
0x1402145d1  mov     [rbx+30h], rcx
0x1402145d5  jmp     short loc_1402145DB
0x1402145d7  mov     [rbx+30h], r15
0x1402145db  mov     rax, [rdi]
0x1402145de  mov     [rax+10h], r14
0x1402145e2  mov     rax, [rdi]
0x1402145e5  mov     rbx, [rax+20h]
0x1402145e9  mov     dword ptr [rbx], 400h
0x1402145ef  mov     dword ptr [rbx+4], 1
0x1402145f6  mov     dword ptr [rbx+8], 80000000h
0x1402145fd  mov     dword ptr [rbx+14h], 20h ; ' '
0x140214604  mov     eax, [rsi+10h]
0x140214607  bt      rax, 14h
0x14021460c  jb      short loc_140214641
0x14021460e  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x140214615  jz      short loc_140214641
0x140214617  mov     r9, [rdi]
0x14021461a  mov     rcx, [r9+18h]
0x14021461e  lea     rax, [rcx+10h]
0x140214622  mov     qword ptr [rsp+98h+var_70], rax
0x140214627  mov     [rsp+98h+var_78], rcx
0x14021462c  mov     r8, r14
0x14021462f  call    McTemplateU0pppp_EtwWriteTransfer
0x140214634  jmp     short loc_140214641
0x140214636  xor     bl, bl
0x140214638  jmp     loc_14021489D
0x14021463d  mov     rbx, [rbx+20h]
0x140214641  mov     eax, [rbx+14h]
0x140214644  mov     [rsp+98h+Index], eax
0x140214648  mov     ecx, [rbx]
0x14021464a  sub     ecx, eax
0x14021464c  and     ecx, 0FFFFFFF0h
0x14021464f  mov     dword ptr [rsp+98h+LargeVbn], ecx
0x140214653  test    r13d, r13d
0x140214656  jz      loc_140214754
0x14021465c  test    r12, r12
0x14021465f  jz      loc_140214953
0x140214665  mov     rcx, [rsp+98h+arg_20]
0x14021466d  cmp     byte ptr [rcx], 0
0x140214670  jnz     loc_140214724
0x140214676  mov     eax, [rbx+18h]
0x140214679  mov     dword ptr [rsp+98h+var_50], eax
0x14021467d  mov     r9, r13; SectorCount
0x140214680  mov     rax, [rdi]
0x140214683  mov     rcx, [rax+18h]
0x140214687  add     rcx, 10h; Mcb
0x14021468b  mov     r8, r12; Lbn
0x14021468e  mov     rdx, r12; Vbn
0x140214691  call    cs:__imp_FsRtlAddBaseMcbEntryEx
0x140214698  nop     dword ptr [rax+rax+00h]
0x14021469d  test    eax, eax
0x14021469f  js      short loc_14021471C
0x1402146a1  mov     r8d, [rsp+98h+Index]
0x1402146a6  add     r8d, dword ptr [rsp+98h+var_50]
0x1402146ab  add     r8, rbx
0x1402146ae  mov     [rsp+98h+var_50], r8
0x1402146b3  mov     eax, [rsi+10h]
0x1402146b6  bt      rax, 14h
0x1402146bb  jb      short loc_1402146EB
0x1402146bd  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x1402146c4  jz      short loc_1402146EB
0x1402146c6  mov     rax, [rdi]
0x1402146c9  mov     rcx, [rax+18h]
0x1402146cd  add     rcx, 10h
0x1402146d1  mov     qword ptr [rsp+98h+var_70], rcx
0x1402146d6  mov     dword ptr [rsp+98h+var_78], r13d
0x1402146db  mov     r9, r12
0x1402146de  mov     r8, r14
0x1402146e1  call    McTemplateU0pidp_EtwWriteTransfer
0x1402146e6  mov     r8, [rsp+98h+var_50]
0x1402146eb  movzx   ecx, byte ptr [r14+1E8h]
0x1402146f3  shl     r12, cl
0x1402146f6  mov     [r8], r12
0x1402146f9  movzx   ecx, byte ptr [r14+1E8h]
0x140214701  mov     rax, r13
0x140214704  shl     rax, cl
0x140214707  mov     [r8+8], rax
0x14021470b  add     dword ptr [rbx+18h], 10h
0x14021470f  mov     rax, [rdi]
0x140214712  mov     rcx, [rax+18h]
0x140214716  add     [rcx+30h], r13
0x14021471a  jmp     short loc_140214754
0x14021471c  mov     rcx, [rsp+98h+arg_20]
0x140214724  mov     byte ptr [rcx], 1
0x140214727  mov     eax, [rsi+10h]
0x14021472a  bt      rax, 14h
0x14021472f  jb      short loc_14021475C
0x140214731  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x140214738  jz      short loc_14021475C
0x14021473a  mov     rax, [rdi]
0x14021473d  mov     r9, [rax+18h]
0x140214741  add     r9, 10h
0x140214745  mov     r8, r14
0x140214748  lea     rdx, delnotify_c427
0x14021474f  call    McTemplateU0pp_EtwWriteTransfer
0x140214754  mov     rcx, [rsp+98h+arg_20]
0x14021475c  mov     eax, [rbx+18h]
0x14021475f  cmp     eax, dword ptr [rsp+98h+LargeVbn]
0x140214763  jnb     short loc_14021477B
0x140214765  cmp     byte ptr [rcx], 0
0x140214768  jnz     short loc_140214773
0x14021476a  test    r13d, r13d
0x14021476d  jnz     loc_140214898
0x140214773  test    eax, eax
0x140214775  jz      loc_140214898
0x14021477b  lea     rdx, [r14+648h]
0x140214782  mov     r8, [rdx+8]
0x140214786  cmp     [r8], rdx
0x140214789  jz      short loc_140214792
0x14021478b  mov     ecx, 3
0x140214790  int     29h; Win8: RtlFailFast(ecx)
0x140214792  mov     rax, [rdi]
0x140214795  mov     rcx, [rax+18h]
0x140214799  mov     [rcx], rdx
0x14021479c  mov     [rcx+8], r8
0x1402147a0  mov     [r8], rcx
0x1402147a3  mov     [rdx+8], rcx
0x1402147a7  mov     rax, [rdi]
0x1402147aa  mov     rcx, [rax+18h]
0x1402147ae  mov     rax, [rcx+30h]
0x1402147b2  add     [r14+138h], rax
0x1402147b9  mov     rdx, [rdi]
0x1402147bc  mov     rax, [rdx+18h]
0x1402147c0  mov     rcx, [rax+30h]
0x1402147c4  mov     [rdx+28h], rcx
0x1402147c8  mov     [rsp+98h+Index], 0
0x1402147d0  mov     [rsp+98h+LargeVbn], 0
0x1402147d9  mov     rax, [rdi]
0x1402147dc  mov     rcx, [rax+18h]
0x1402147e0  add     rcx, 10h; OpaqueMcb
0x1402147e4  lea     r9, [rsp+98h+Index]; Index
0x1402147e9  lea     r8, [rsp+98h+LargeVbn]; LargeLbn
0x1402147ee  lea     rdx, [rsp+98h+LargeVbn]; LargeVbn
0x1402147f3  call    cs:__imp_FsRtlLookupLastBaseMcbEntryAndIndex
0x1402147fa  nop     dword ptr [rax+rax+00h]
0x1402147ff  mov     eax, [rsp+98h+Index]
0x140214803  add     [r14+5E8h], eax
0x14021480a  mov     eax, [r14+5E8h]
0x140214811  cmp     [r14+2304h], eax
0x140214818  jnb     short loc_140214821
0x14021481a  mov     [r14+2304h], eax
0x140214821  mov     eax, [rsi+10h]
0x140214824  bt      rax, 14h
0x140214829  jb      short loc_14021484B
0x14021482b  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x140214832  jz      short loc_14021484B
0x140214834  mov     [rsp+98h+var_78], rsi
0x140214839  mov     r9, [rdi]
0x14021483c  mov     r8, r14
0x14021483f  lea     rdx, delnotify_c508
0x140214846  call    McTemplateU0ppp_EtwWriteTransfer
0x14021484b  mov     dword ptr [rbx], 1Ch
0x140214851  lea     rcx, [rsi+1D0h]
0x140214858  mov     rdx, [rcx+8]
0x14021485c  cmp     [rdx], rcx
0x14021485f  jz      short loc_140214868
0x140214861  mov     ecx, 3
0x140214866  int     29h; Win8: RtlFailFast(ecx)
0x140214868  mov     rax, [rdi]
0x14021486b  mov     [rax], rcx
0x14021486e  mov     [rax+8], rdx
0x140214872  mov     [rdx], rax
0x140214875  mov     [rcx+8], rax
0x140214879  mov     qword ptr [rdi], 0
0x140214880  jmp     short loc_140214898
0x140214882  mov     rcx, [r9]; Entry
0x140214885  test    rcx, rcx
0x140214888  jz      short loc_14021489D
0x14021488a  call    NtfsFreeMarkUnusedContext
0x14021488f  mov     qword ptr [rdi], 0
0x140214896  jmp     short loc_14021489D
0x140214898  movzx   ebx, [rsp+98h+var_58]
0x14021489d  test    r15, r15
0x1402148a0  jz      loc_140214938
0x1402148a6  mov     eax, [rsi+10h]
0x1402148a9  bt      rax, 14h
0x1402148ae  jb      short loc_1402148C8
0x1402148b0  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 10h
0x1402148b7  jz      short loc_1402148C8
0x1402148b9  mov     r8, r14
0x1402148bc  lea     rdx, delnotify_c557
0x1402148c3  call    McTemplateU0p_EtwWriteTransfer
0x1402148c8  test    bl, bl
0x1402148ca  jz      short loc_1402148DC
0x1402148cc  lea     rcx, [r15+10h]; Mcb
0x1402148d0  call    cs:__imp_FsRtlUninitializeBaseMcb
  ... truncated ...
```

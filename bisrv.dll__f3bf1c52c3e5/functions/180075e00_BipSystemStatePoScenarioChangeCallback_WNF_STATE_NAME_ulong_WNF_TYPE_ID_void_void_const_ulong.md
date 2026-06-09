# BipSystemStatePoScenarioChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180075e00`
- end: `0x180076491`
- name: `?BipSystemStatePoScenarioChangeCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `1681`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180005ff0`
- `0x180006300`
- `0x1800121b0`
- `0x18002b060`
- `0x18002dae4`
- `0x180034fa8`
- `0x18004af00`
- `0x18004e4d0`
- `0x180053100`
- `0x18006bc3c`
- `0x180075e00`
- `0x1800766e8`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlStringFromGUIDEx` at `0x18007609c`
- `ntdll!RtlStringFromGUIDEx` at `0x18007609c`
- `ntdll!RtlFreeHeap` at `0x180076395`
- `ntdll!RtlFreeHeap` at `0x1800763ac`
- `ntdll!RtlFreeHeap` at `0x180076395`
- `ntdll!RtlFreeHeap` at `0x1800763ac`
- `ntdll!RtlAllocateHeap` at `0x180075fdf`
- `ntdll!RtlAllocateHeap` at `0x180076033`
- `ntdll!RtlAllocateHeap` at `0x180075fdf`
- `ntdll!RtlAllocateHeap` at `0x180076033`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18007634b`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18007634b`
- `api-ms-win-appmodel-runtime-l1-1-1!FormatApplicationUserModelId` at `0x1800760c6`
- `api-ms-win-appmodel-runtime-l1-1-1!FormatApplicationUserModelId` at `0x1800760c6`

## string_xrefs

- `0x180076120`: `Settings.Network Requests (Background Tasks).App: %s.TaskID: %s`

## pseudocode

```c
__int64 __fastcall BipSystemStatePoScenarioChangeCallback(
        struct _WNF_STATE_NAME a1,
        int a2,
        struct _WNF_TYPE_ID *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  char *v5; // rsi
  signed int v8; // ebx
  _QWORD *v9; // r15
  unsigned __int64 v10; // r14
  __int64 v11; // rdx
  __int64 v12; // rcx
  bool v13; // zf
  __int64 v14; // rcx
  struct _EVENT_DATA_DESCRIPTOR *v15; // rdi
  _QWORD **v16; // r8
  _QWORD *v17; // rcx
  unsigned int v18; // edx
  __int64 v19; // rax
  ULONG v20; // r13d
  size_t v21; // rbx
  struct _EVENT_DATA_DESCRIPTOR *Heap; // rax
  unsigned int v23; // ebx
  char *v24; // rax
  SIZE_T *v25; // rax
  SIZE_T i; // rcx
  SIZE_T v27; // rbx
  __int64 v28; // rax
  UINT32 v29; // edx
  unsigned __int16 *v30; // rbx
  int v31; // ecx
  SIZE_T v32; // rbx
  const unsigned __int16 *v33; // r8
  __int64 EntryPoint; // rax
  unsigned __int16 *v35; // rbx
  int v36; // r9d
  __int64 v37; // rcx
  __int64 v38; // rcx
  _DWORD *v39; // r10
  __int64 v40; // rcx
  int v41; // edx
  __int64 v42; // rcx
  _DWORD *v43; // r8
  __int64 v44; // rcx
  unsigned int v45; // edx
  __int64 v46; // rcx
  __int128 *v47; // rax
  __int128 v48; // xmm1
  __int64 v50; // [rsp+40h] [rbp-C0h]
  char v51; // [rsp+50h] [rbp-B0h] BYREF
  SIZE_T v52; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v53; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v54; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v55; // [rsp+68h] [rbp-98h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v57; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v58; // [rsp+80h] [rbp-80h] BYREF
  __int128 v59; // [rsp+88h] [rbp-78h] BYREF
  char v60[16]; // [rsp+98h] [rbp-68h] BYREF
  SIZE_T Size[3]; // [rsp+A8h] [rbp-58h] BYREF
  char v62[32]; // [rsp+C0h] [rbp-40h] BYREF
  SIZE_T *v63; // [rsp+E0h] [rbp-20h]
  __int64 v64; // [rsp+E8h] [rbp-18h]
  unsigned __int64 *v65; // [rsp+F0h] [rbp-10h]
  __int64 v66; // [rsp+F8h] [rbp-8h]
  unsigned __int16 **v67; // [rsp+100h] [rbp+0h]
  __int64 v68; // [rsp+108h] [rbp+8h]
  SIZE_T *v69; // [rsp+110h] [rbp+10h]
  __int64 v70; // [rsp+118h] [rbp+18h]
  _BYTE v71[80]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+170h] [rbp+70h] BYREF
  unsigned __int16 v73[128]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v74[128]; // [rsp+380h] [rbp+280h] BYREF

  v5 = 0;
  v55 = 0;
  v57 = 0;
  applicationUserModelIdLength = 0;
  v54 = 0;
  v53 = 0;
  v52 = 0;
  LODWORD(Size[0]) = 0;
  v51 = 0;
  v59 = 0;
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, a3) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_1800C3098,
      (unsigned __int8 *)&word_1800AEC0E);
  if ( !a2 )
  {
    v8 = -1073741584;
    v55 = -1;
    v9 = 0;
    v10 = 0;
    goto LABEL_47;
  }
  v9 = a5;
  v10 = a5[2];
  BipSyncAcquireLock((struct _BI_LOCK *)P);
  v12 = *a5 - *(_QWORD *)&GUID_SPM_LOW_POWER_CS.Data1;
  if ( *a5 == *(_QWORD *)&GUID_SPM_LOW_POWER_CS.Data1 )
    v12 = a5[1] - *(_QWORD *)GUID_SPM_LOW_POWER_CS.Data4;
  v13 = v12 == 0;
  v14 = a4[280];
  if ( v13 )
  {
    *(_QWORD *)(v14 + 88) = v10;
    v55 = v10;
  }
  else
  {
    v55 = *(_QWORD *)(v14 + 88);
    *(_QWORD *)(v14 + 88) = -1;
  }
  LOBYTE(v11) = 1;
  BipSyncReleaseLock(P, v11);
  if ( v55 == v10 )
  {
    v8 = 0;
    goto LABEL_47;
  }
  if ( v55 == -1 )
  {
    v8 = -1073700861;
    goto LABEL_47;
  }
  v15 = 0;
  BipSyncAcquireLock((struct _BI_LOCK *)P);
  v16 = (_QWORD **)(a4[280] + 32LL);
  v53 = 0;
  v17 = *v16;
  if ( *v16 == v16 )
  {
LABEL_42:
    v8 = -1073741275;
    goto LABEL_43;
  }
  v18 = 0;
  do
  {
    v19 = v18 + 1;
    if ( (unsigned int)v19 < v18 )
    {
      v53 = -1;
      goto LABEL_41;
    }
    v53 = ++v18;
    v17 = (_QWORD *)*v17;
  }
  while ( v17 != v16 );
  if ( !(_DWORD)v19 )
    goto LABEL_42;
  v8 = RtlULongLongToULong(5 * v19, (unsigned int *)&v52 + 1);
  if ( v8 < 0 )
    goto LABEL_43;
  v20 = HIDWORD(v52) + 3;
  if ( (unsigned int)(HIDWORD(v52) + 3) < HIDWORD(v52) )
  {
LABEL_41:
    v8 = -1073741675;
    goto LABEL_43;
  }
  v8 = RtlULongLongToULong(16LL * v20, (unsigned int *)Size);
  if ( v8 < 0 )
    goto LABEL_43;
  v21 = LODWORD(Size[0]);
  Heap = (struct _EVENT_DATA_DESCRIPTOR *)RtlAllocateHeap(BipHeap, 0, LODWORD(Size[0]));
  v15 = Heap;
  if ( !Heap )
    goto LABEL_24;
  memset_0(Heap, 0, v21);
  v8 = RtlULongLongToULong(1068LL * v53, (unsigned int *)&v52);
  if ( v8 >= 0 )
  {
    v23 = v52;
    v24 = (char *)RtlAllocateHeap(BipHeap, 0, (unsigned int)v52);
    v5 = v24;
    if ( !v24 )
    {
LABEL_24:
      v8 = -1073741801;
      goto LABEL_43;
    }
    memset_0(v24, 0, v23);
    v52 = 2;
    *(_QWORD *)&v59 = 5111808;
    *((_QWORD *)&v59 + 1) = v71;
    v25 = (SIZE_T *)(a4[280] + 32LL);
    for ( i = *v25; ; i = *(_QWORD *)Size[0] )
    {
      Size[0] = i;
      if ( (SIZE_T *)i == v25 )
      {
        BipSyncReleaseLock(P, 0);
        v51 = v55;
        v46 = v20 - 1;
        *(_QWORD *)&v15->Size = 1;
        *(_QWORD *)&v15[1].Size = 4;
        v15->Ptr = (ULONGLONG)&v51;
        v15[1].Ptr = (ULONGLONG)&v53;
        v15[v46].Ptr = (ULONGLONG)&v55;
        *(_QWORD *)&v15[v46].Size = 8;
        EventWrite(*(_QWORD *)(a4[280] + 96LL), &SLEEPSTUDY_EVT_SCENARIO_BLOCKER_DATA, v20, v15);
        v8 = 0;
        goto LABEL_44;
      }
      v27 = i - 192;
      RtlStringFromGUIDEx(i - 192 + 32, &v59, 0);
      applicationUserModelIdLength = 130;
      LODWORD(v28) = FormatApplicationUserModelId(
                       (PCWSTR)(*(_QWORD *)(v27 + 80) + 416LL),
                       (PCWSTR)(*(_QWORD *)(v27 + 88) + 60LL),
                       &applicationUserModelIdLength,
                       applicationUserModelId);
      v8 = v28;
      if ( (_DWORD)v28 )
        break;
      v29 = applicationUserModelIdLength;
      if ( applicationUserModelIdLength )
      {
        do
        {
          if ( applicationUserModelId[v28] == 46 )
            applicationUserModelId[v28] = 95;
          v28 = (unsigned int)(v28 + 1);
        }
        while ( (unsigned int)v28 < v29 );
      }
      v30 = (unsigned __int16 *)&v5[1068 * HIDWORD(v52)];
      v58 = v30;
      RtlStringCchPrintfExW(
        v30 + 2,
        0xE6u,
        0,
        &v57,
        0,
        L"Settings.Network Requests (Background Tasks).App: %s.TaskID: %s",
        applicationUserModelId,
        v71);
      RtlULongLongToULong(v57, &v54);
      RtlULongSub(0xE6u, v54, (unsigned int *)v30);
      v32 = Size[0];
      v33 = *(const unsigned __int16 **)(Size[0] + 200);
      if ( !v33 )
        v33 = L"N/A";
      RtlStringCchCopyW(v73, (unsigned int)(v31 - 102), v33);
      EntryPoint = BipWorkItemGetEntryPoint(v32 - 192);
      RtlStringCchCopyW(v74, 0x80u, *(const unsigned __int16 **)(EntryPoint + 8));
      v35 = v58 + 234;
      LODWORD(v50) = *(_DWORD *)(*(_QWORD *)(Size[0] - 120) + 584LL);
      RtlStringCchPrintfExW(v58 + 234, 0x12Bu, 0, &v57, 0, L"Name: %s; EntryPoint: %s; Type: %d", v73, v74, v50);
      RtlULongLongToULong(v57, &v54);
      RtlULongSub(0x12Bu, v54, (unsigned int *)v58 + 116);
      v36 = v52;
      ++HIDWORD(v52);
      v37 = (unsigned int)v52;
      v15[v37].Ptr = (ULONGLONG)&GUID_SPR_SESSION_METADATA_CONTAINER;
      *(_QWORD *)&v15[v37].Size = 16;
      v38 = (unsigned int)(v36 + 1);
      v15[v38].Ptr = (ULONGLONG)v39;
      *(_QWORD *)&v15[v38].Size = 4;
      v40 = (unsigned int)(v36 + 2);
      v41 = 2 * *v39;
      v15[v40].Ptr = (ULONGLONG)(v39 + 1);
      v15[v40].Size = v41;
      v15[v40].Reserved = 0;
      v42 = (unsigned int)(v36 + 3);
      v15[v42].Ptr = (ULONGLONG)v43;
      *(_QWORD *)&v15[v42].Size = 4;
      v44 = (unsigned int)(v36 + 4);
      v45 = 2 * *v43;
      LODWORD(v52) = v36 + 5;
      v15[v44].Ptr = (ULONGLONG)v35;
      *(_QWORD *)&v15[v44].Size = v45;
      v25 = (SIZE_T *)(a4[280] + 32LL);
    }
    if ( (int)v28 > 0 )
      v8 = (unsigned __int16)v28 | 0xC0070000;
  }
LABEL_43:
  BipSyncReleaseLock(P, 0);
  if ( v15 )
LABEL_44:
    RtlFreeHeap(BipHeap, 0, v15);
  if ( v5 )
    RtlFreeHeap(BipHeap, 0, v5);
LABEL_47:
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, a3) )
  {
    v57 = v55;
    LODWORD(v52) = v8;
    v58 = (unsigned __int16 *)v10;
    v47 = (__int128 *)BipTraceOptionalGuid(v60, v9);
    v70 = 4;
    v68 = 8;
    v66 = 8;
    v48 = *v47;
    v64 = 16;
    v69 = &v52;
    v67 = &v58;
    v65 = &v57;
    v63 = Size;
    *(_OWORD *)Size = v48;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, byte_1800AEEC1, 0, 0, 6, v62);
  }
  return 0;
}

```

## disassembly

```asm
0x180075e00  push    rbp
0x180075e02  push    rbx
0x180075e03  push    rsi
0x180075e04  push    rdi
0x180075e05  push    r12
0x180075e07  push    r13
0x180075e09  push    r14
0x180075e0b  push    r15
0x180075e0d  lea     rbp, [rsp-398h]
0x180075e15  sub     rsp, 498h
0x180075e1c  mov     rax, cs:__security_cookie
0x180075e23  xor     rax, rsp
0x180075e26  mov     [rbp+3D0h+var_50], rax
0x180075e2d  mov     eax, cs:dword_1800C3098
0x180075e33  xor     esi, esi
0x180075e35  mov     [rsp+4D0h+var_468], rsi
0x180075e3a  xorps   xmm0, xmm0
0x180075e3d  mov     [rsp+4D0h+var_458], rsi
0x180075e42  mov     r12, r9
0x180075e45  mov     [rsp+4D0h+applicationUserModelIdLength], esi
0x180075e49  mov     ebx, edx
0x180075e4b  mov     [rsp+4D0h+var_470], esi
0x180075e4f  mov     [rsp+4D0h+var_474], esi
0x180075e53  mov     dword ptr [rsp+4D0h+var_47C], esi
0x180075e57  mov     dword ptr [rsp+4D0h+var_47C+4], esi
0x180075e5b  mov     dword ptr [rbp+3D0h+Size], esi
0x180075e5e  mov     [rsp+4D0h+var_480], sil
0x180075e63  movups  [rbp+3D0h+var_448], xmm0
0x180075e67  cmp     eax, 5
0x180075e6a  jbe     short loc_180075E92
0x180075e6c  lea     edx, [rsi+2]
0x180075e6f  lea     rcx, dword_1800C3098
0x180075e76  call    _tlgKeywordOn
0x180075e7b  test    al, al
0x180075e7d  jz      short loc_180075E92
0x180075e7f  lea     rdx, word_1800AEC0E
0x180075e86  lea     rcx, dword_1800C3098
0x180075e8d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180075e92  test    ebx, ebx
0x180075e94  jnz     short loc_180075EAF
0x180075e96  mov     ebx, 0C00000F0h
0x180075e9b  mov     [rsp+4D0h+var_468], 0FFFFFFFFFFFFFFFFh
0x180075ea4  mov     r15, rsi
0x180075ea7  mov     r14, rsi
0x180075eaa  jmp     loc_1800763B2
0x180075eaf  mov     r15, [rbp+3D0h+arg_20]
0x180075eb6  mov     dl, 1
0x180075eb8  mov     rcx, cs:P; struct _BI_LOCK *
0x180075ebf  mov     r14, [r15+10h]
0x180075ec3  call    BipSyncAcquireLock
0x180075ec8  mov     rcx, [r15]
0x180075ecb  sub     rcx, qword ptr cs:GUID_SPM_LOW_POWER_CS.Data1
0x180075ed2  jnz     short loc_180075EDF
0x180075ed4  mov     rcx, [r15+8]
0x180075ed8  sub     rcx, qword ptr cs:GUID_SPM_LOW_POWER_CS.Data4
0x180075edf  test    rcx, rcx
0x180075ee2  mov     eax, esi
0x180075ee4  mov     rcx, [r12+8C0h]
0x180075eec  setz    al
0x180075eef  test    eax, eax
0x180075ef1  jz      short loc_180075EFE
0x180075ef3  mov     [rcx+58h], r14
0x180075ef7  mov     [rsp+4D0h+var_468], r14
0x180075efc  jmp     short loc_180075F0F
0x180075efe  mov     rax, [rcx+58h]
0x180075f02  mov     [rsp+4D0h+var_468], rax
0x180075f07  mov     qword ptr [rcx+58h], 0FFFFFFFFFFFFFFFFh
0x180075f0f  mov     rcx, cs:P
0x180075f16  mov     dl, 1
0x180075f18  call    BipSyncReleaseLock
0x180075f1d  cmp     [rsp+4D0h+var_468], r14
0x180075f22  jnz     short loc_180075F2B
0x180075f24  mov     ebx, esi
0x180075f26  jmp     loc_1800763B2
0x180075f2b  cmp     [rsp+4D0h+var_468], 0FFFFFFFFFFFFFFFFh
0x180075f31  jnz     short loc_180075F3D
0x180075f33  mov     ebx, 0C000A003h
0x180075f38  jmp     loc_1800763B2
0x180075f3d  mov     rcx, cs:P; struct _BI_LOCK *
0x180075f44  xor     edx, edx
0x180075f46  mov     rdi, rsi
0x180075f49  call    BipSyncAcquireLock
0x180075f4e  mov     r8, [r12+8C0h]
0x180075f56  add     r8, 20h ; ' '
0x180075f5a  mov     [rsp+4D0h+var_474], esi
0x180075f5e  mov     rcx, [r8]
0x180075f61  cmp     rcx, r8
0x180075f64  jz      loc_180076371
0x180075f6a  xor     edx, edx
0x180075f6c  lea     eax, [rdx+1]
0x180075f6f  cmp     eax, edx
0x180075f71  jb      loc_180076362
0x180075f77  mov     [rsp+4D0h+var_474], eax
0x180075f7b  mov     edx, eax
0x180075f7d  mov     rcx, [rcx]
0x180075f80  cmp     rcx, r8
0x180075f83  jnz     short loc_180075F6C
0x180075f85  test    eax, eax
0x180075f87  jz      loc_180076371
0x180075f8d  lea     rcx, [rax+rax*4]; unsigned __int64
0x180075f91  lea     rdx, [rsp+4D0h+var_47C+4]; unsigned int *
0x180075f96  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x180075f9b  mov     ebx, eax
0x180075f9d  test    eax, eax
0x180075f9f  js      loc_180076376
0x180075fa5  mov     eax, dword ptr [rsp+4D0h+var_47C+4]
0x180075fa9  lea     r13d, [rax+3]
0x180075fad  cmp     r13d, eax
0x180075fb0  jb      loc_18007636A
0x180075fb6  mov     ecx, r13d
0x180075fb9  lea     rdx, [rbp+3D0h+Size]; unsigned int *
0x180075fbd  shl     rcx, 4; unsigned __int64
0x180075fc1  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x180075fc6  mov     ebx, eax
0x180075fc8  test    eax, eax
0x180075fca  js      loc_180076376
0x180075fd0  mov     ebx, dword ptr [rbp+3D0h+Size]
0x180075fd3  xor     edx, edx; Flags
0x180075fd5  mov     rcx, cs:BipHeap; HeapHandle
0x180075fdc  mov     r8d, ebx; Size
0x180075fdf  call    cs:__imp_RtlAllocateHeap
0x180075fe5  mov     rdi, rax
0x180075fe8  test    rax, rax
0x180075feb  jnz     short loc_180075FF7
0x180075fed  mov     ebx, 0C0000017h
0x180075ff2  jmp     loc_180076376
0x180075ff7  mov     r8, rbx; Size
0x180075ffa  xor     edx, edx; Val
0x180075ffc  mov     rcx, rdi; void *
0x180075fff  call    memset_0
0x180076004  mov     eax, [rsp+4D0h+var_474]
0x180076008  lea     rdx, [rsp+4D0h+var_47C]; unsigned int *
0x18007600d  imul    rcx, rax, 42Ch; unsigned __int64
0x180076014  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x180076019  mov     ebx, eax
0x18007601b  test    eax, eax
0x18007601d  js      loc_180076376
0x180076023  mov     ebx, dword ptr [rsp+4D0h+var_47C]
0x180076027  xor     edx, edx; Flags
0x180076029  mov     rcx, cs:BipHeap; HeapHandle
0x180076030  mov     r8d, ebx; Size
0x180076033  call    cs:__imp_RtlAllocateHeap
0x180076039  mov     rsi, rax
0x18007603c  test    rax, rax
0x18007603f  jz      short loc_180075FED
0x180076041  mov     r8d, ebx; Size
0x180076044  xor     edx, edx; Val
0x180076046  mov     rcx, rax; void *
0x180076049  call    memset_0
0x18007604e  mov     eax, 4Eh ; 'N'
0x180076053  mov     dword ptr [rsp+4D0h+var_47C+4], 0
0x18007605b  xorps   xmm0, xmm0
0x18007605e  mov     dword ptr [rsp+4D0h+var_47C], 2
0x180076066  movups  [rbp+3D0h+var_448], xmm0
0x18007606a  mov     word ptr [rbp+3D0h+var_448+2], ax
0x18007606e  lea     rax, [rbp+3D0h+var_3B0]
0x180076072  mov     qword ptr [rbp+3D0h+var_448+8], rax
0x180076076  mov     rax, [r12+8C0h]
0x18007607e  add     rax, 20h ; ' '
0x180076082  mov     rcx, [rax]
0x180076085  jmp     loc_1800762D5
0x18007608a  lea     rbx, [rcx-0C0h]
0x180076091  xor     r8d, r8d
0x180076094  lea     rcx, [rbx+20h]
0x180076098  lea     rdx, [rbp+3D0h+var_448]
0x18007609c  call    cs:__imp_RtlStringFromGUIDEx
0x1800760a2  mov     [rsp+4D0h+applicationUserModelIdLength], 82h
0x1800760aa  lea     r9, [rbp+3D0h+applicationUserModelId]; applicationUserModelId
0x1800760ae  mov     rdx, [rbx+58h]
0x1800760b2  lea     r8, [rsp+4D0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800760b7  mov     rcx, [rbx+50h]
0x1800760bb  add     rdx, 3Ch ; '<'; packageRelativeApplicationId
0x1800760bf  add     rcx, 1A0h; packageFamilyName
0x1800760c6  call    cs:__imp_FormatApplicationUserModelId
0x1800760cc  mov     ebx, eax
0x1800760ce  test    eax, eax
0x1800760d0  jnz     loc_180076355
0x1800760d6  mov     edx, [rsp+4D0h+applicationUserModelIdLength]
0x1800760da  test    edx, edx
0x1800760dc  jz      short loc_1800760F8
0x1800760de  cmp     [rbp+rax*2+3D0h+applicationUserModelId], 2Eh ; '.'
0x1800760e4  jnz     short loc_1800760F2
0x1800760e6  mov     r8d, 5Fh ; '_'
0x1800760ec  mov     [rbp+rax*2+3D0h+applicationUserModelId], r8w
0x1800760f2  inc     eax
0x1800760f4  cmp     eax, edx
0x1800760f6  jb      short loc_1800760DE
0x1800760f8  mov     eax, dword ptr [rsp+4D0h+var_47C+4]
0x1800760fc  lea     rcx, [rbp+3D0h+var_3B0]
0x180076100  mov     [rsp+4D0h+var_498], rcx
0x180076105  lea     r9, [rsp+4D0h+var_458]; unsigned __int64 *
0x18007610a  imul    rbx, rax, 42Ch
0x180076111  lea     rcx, [rbp+3D0h+applicationUserModelId]
0x180076115  xor     r8d, r8d; unsigned __int16 **
0x180076118  mov     [rsp+4D0h+var_4A0], rcx
0x18007611d  add     rbx, rsi
0x180076120  lea     rcx, aSettingsNetwor; "Settings.Network Requests (Background T"...
0x180076127  mov     [rbp+3D0h+var_450], rbx
0x18007612b  mov     [rsp+4D0h+var_4A8], rcx; unsigned __int16 *
0x180076130  mov     edx, 0E6h; unsigned __int64
0x180076135  mov     qword ptr [rsp+4D0h+var_4B0], 0; unsigned int
0x18007613e  lea     rcx, [rbx+4]; unsigned __int16 *
0x180076142  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180076147  mov     rcx, [rsp+4D0h+var_458]; unsigned __int64
0x18007614c  lea     rdx, [rsp+4D0h+var_470]; unsigned int *
0x180076151  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x180076156  mov     edx, [rsp+4D0h+var_470]; unsigned int
0x18007615a  mov     r8, rbx; unsigned int *
0x18007615d  mov     ecx, 0E6h; unsigned int
0x180076162  call    ?RtlULongSub@@YAJKKPEAK@Z; RtlULongSub(ulong,ulong,ulong *)
0x180076167  mov     rbx, [rbp+3D0h+Size]
0x18007616b  lea     edx, [rcx-66h]; unsigned __int64
0x18007616e  lea     rcx, [rbp+3D0h+var_250]; unsigned __int16 *
0x180076175  mov     r8, [rbx+0C8h]
0x18007617c  test    r8, r8
0x18007617f  jnz     short loc_180076188
0x180076181  lea     r8, aNA; "N/A"
0x180076188  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007618d  lea     rcx, [rbx-0C0h]
0x180076194  call    BipWorkItemGetEntryPoint
0x180076199  mov     edx, 80h; unsigned __int64
0x18007619e  lea     rcx, [rbp+3D0h+var_150]; unsigned __int16 *
0x1800761a5  mov     r8, [rax+8]; unsigned __int16 *
0x1800761a9  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800761ae  mov     rax, [rbp+3D0h+Size]
0x1800761b2  lea     r9, [rsp+4D0h+var_458]; unsigned __int64 *
0x1800761b7  mov     rbx, [rbp+3D0h+var_450]
0x1800761bb  xor     r8d, r8d; unsigned __int16 **
0x1800761be  add     rbx, 1D4h
0x1800761c5  mov     edx, 12Bh; unsigned __int64
0x1800761ca  mov     rax, [rax-78h]
0x1800761ce  mov     ecx, [rax+248h]
0x1800761d4  lea     rax, [rbp+3D0h+var_150]
0x1800761db  mov     [rsp+4D0h+var_490], ecx
0x1800761df  mov     rcx, rbx; unsigned __int16 *
0x1800761e2  mov     [rsp+4D0h+var_498], rax
0x1800761e7  lea     rax, [rbp+3D0h+var_250]
0x1800761ee  mov     [rsp+4D0h+var_4A0], rax
0x1800761f3  lea     rax, aNameSEntrypoin; "Name: %s; EntryPoint: %s; Type: %d"
0x1800761fa  mov     [rsp+4D0h+var_4A8], rax; unsigned __int16 *
0x1800761ff  mov     qword ptr [rsp+4D0h+var_4B0], 0; unsigned int
0x180076208  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18007620d  mov     rcx, [rsp+4D0h+var_458]; unsigned __int64
0x180076212  lea     rdx, [rsp+4D0h+var_470]; unsigned int *
0x180076217  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x18007621c  mov     r10, [rbp+3D0h+var_450]
0x180076220  mov     ecx, 12Bh; unsigned int
0x180076225  mov     edx, [rsp+4D0h+var_470]; unsigned int
0x180076229  lea     r8, [r10+1D0h]; unsigned int *
0x180076230  call    ?RtlULongSub@@YAJKKPEAK@Z; RtlULongSub(ulong,ulong,ulong *)
0x180076235  mov     r9d, dword ptr [rsp+4D0h+var_47C]
0x18007623a  lea     rax, GUID_SPR_SESSION_METADATA_CONTAINER
0x180076241  inc     dword ptr [rsp+4D0h+var_47C+4]
0x180076245  xor     r11d, r11d
0x180076248  mov     ecx, r9d
0x18007624b  add     rcx, rcx
0x18007624e  mov     [rdi+rcx*8], rax
0x180076252  lea     rax, [r10+4]
0x180076256  mov     qword ptr [rdi+rcx*8+8], 10h
0x18007625f  lea     ecx, [r9+1]
0x180076263  add     rcx, rcx
0x180076266  mov     [rdi+rcx*8], r10
0x18007626a  mov     qword ptr [rdi+rcx*8+8], 4
0x180076273  lea     ecx, [r9+2]
0x180076277  mov     edx, [r10]
0x18007627a  add     rcx, rcx
0x18007627d  add     edx, edx
0x18007627f  mov     [rdi+rcx*8], rax
0x180076283  mov     [rdi+rcx*8+8], edx
0x180076287  mov     [rdi+rcx*8+0Ch], r11d
0x18007628c  lea     ecx, [r9+3]
0x180076290  add     rcx, rcx
0x180076293  mov     [rdi+rcx*8], r8
0x180076297  mov     qword ptr [rdi+rcx*8+8], 4
0x1800762a0  lea     ecx, [r9+4]
0x1800762a4  mov     edx, [r8]
0x1800762a7  add     rcx, rcx
0x1800762aa  add     edx, edx
0x1800762ac  add     r9d, 5
0x1800762b0  mov     dword ptr [rsp+4D0h+var_47C], r9d
0x1800762b5  mov     [rdi+rcx*8], rbx
0x1800762b9  mov     [rdi+rcx*8+8], edx
0x1800762bd  mov     [rdi+rcx*8+0Ch], r11d
0x1800762c2  mov     rcx, [rbp+3D0h+Size]
0x1800762c6  mov     rax, [r12+8C0h]
0x1800762ce  add     rax, 20h ; ' '
0x1800762d2  mov     rcx, [rcx]
0x1800762d5  mov     [rbp+3D0h+Size], rcx
0x1800762d9  cmp     rcx, rax
0x1800762dc  jnz     loc_18007608A
0x1800762e2  mov     rcx, cs:P
0x1800762e9  xor     edx, edx
0x1800762eb  call    BipSyncReleaseLock
0x1800762f0  mov     al, byte ptr [rsp+4D0h+var_468]
0x1800762f4  lea     ecx, [r13-1]
0x1800762f8  mov     [rsp+4D0h+var_480], al
0x1800762fc  lea     rdx, SLEEPSTUDY_EVT_SCENARIO_BLOCKER_DATA; EventDescriptor
0x180076303  add     rcx, rcx
0x180076306  mov     qword ptr [rdi+8], 1
0x18007630e  mov     qword ptr [rdi+18h], 4
  ... truncated ...
```

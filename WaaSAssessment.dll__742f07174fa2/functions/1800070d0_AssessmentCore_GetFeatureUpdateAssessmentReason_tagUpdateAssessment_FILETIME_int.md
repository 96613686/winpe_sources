# AssessmentCore::GetFeatureUpdateAssessmentReason(tagUpdateAssessment &,_FILETIME *,int)

- ea: `0x1800070d0`
- end: `0x180007375`
- name: `?GetFeatureUpdateAssessmentReason@AssessmentCore@@MEAAJAEAUtagUpdateAssessment@@PEAU_FILETIME@@H@Z`
- size: `677`
- prototype: `int(AssessmentCore *__hidden this, struct tagUpdateAssessment *, struct _FILETIME *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800070d0`
- `0x18001752c`
- `0x1800184dc`
- `0x1800186f0`
- `0x180018fe0`
- `0x18001b010`

## string_xrefs

- `0x180007234`: `Device has paused feature updates`
- `0x180007351`: `GetFeatureUpdateAssessmentReason Failure: 0x%x`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetFeatureUpdateAssessmentReason(
        AssessmentCore *this,
        struct tagUpdateAssessment *a2,
        struct _FILETIME *a3,
        int a4)
{
  char *v4; // r12
  unsigned int v6; // r8d
  struct UpdatePublishedHistory *v8; // rdx
  FILETIME v11; // rcx
  int NextPublishedUpdate; // edi
  char *v13; // r14
  int v14; // ecx
  int v15; // ecx
  __int64 v16; // rax
  int v19; // [rsp+40h] [rbp-28h] BYREF
  int v20; // [rsp+44h] [rbp-24h] BYREF
  int v21; // [rsp+48h] [rbp-20h] BYREF
  int v22; // [rsp+4Ch] [rbp-1Ch] BYREF
  unsigned int v23; // [rsp+50h] [rbp-18h] BYREF
  int v24; // [rsp+54h] [rbp-14h] BYREF
  struct _FILETIME v25; // [rsp+58h] [rbp-10h] BYREF
  unsigned int v26; // [rsp+B0h] [rbp+48h] BYREF

  v4 = (char *)this + 1256;
  v19 = 0;
  v20 = 0;
  v6 = *((_DWORD *)this + 582);
  v8 = (struct UpdatePublishedHistory *)*((_QWORD *)this + 290);
  v21 = 0;
  v11 = *(FILETIME *)((char *)this + 108);
  v22 = 0;
  v24 = 0;
  NextPublishedUpdate = FindNextPublishedUpdate(v11, v8, v6, 1, v4, a3);
  if ( NextPublishedUpdate < 0 )
    goto LABEL_28;
  (*(void (__fastcall **)(AssessmentCore *, UpdateImpactLevel *, DWORD *, _QWORD))(*(_QWORD *)this + 216LL))(
    this,
    &a2->impact,
    &a2->daysOutOfDate,
    *a3);
  v13 = (char *)this + 208;
  NextPublishedUpdate = (*(__int64 (__fastcall **)(char *, int *))(*((_QWORD *)this + 26) + 80LL))(
                          (char *)this + 208,
                          &v19);
  if ( NextPublishedUpdate < 0 )
    goto LABEL_28;
  NextPublishedUpdate = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v13 + 72LL))((char *)this + 208, &v20);
  if ( NextPublishedUpdate < 0 )
    goto LABEL_28;
  NextPublishedUpdate = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v13 + 88LL))((char *)this + 208, &v21);
  if ( NextPublishedUpdate < 0 )
    goto LABEL_28;
  if ( v19 && (!v20 || v21) )
  {
    LogLevel(4u, L"Device is managed");
    a2->status = UpdateAssessmentStatus_NotLatestManaged;
    return (unsigned int)NextPublishedUpdate;
  }
  v14 = *((_DWORD *)this + 17);
  if ( !v14 )
  {
    NextPublishedUpdate = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v13 + 56LL))((char *)this + 208, &v22);
    if ( NextPublishedUpdate >= 0 )
    {
      if ( v22 )
      {
        LogLevel(4u, L"Device has paused feature updates");
        a2->status = UpdateAssessmentStatus_NotLatestPausedFeature;
        return (unsigned int)NextPublishedUpdate;
      }
      v16 = *(_QWORD *)v13;
      v25 = 0;
      v26 = 0;
      v23 = 0;
      (*(void (__fastcall **)(char *, unsigned int *))(v16 + 40))((char *)this + 208, &v26);
      SubtractDaysFromCurrentTimeUTC(v26, &v25);
      NextPublishedUpdate = CountUpdatesPublishedBetweenRange(
                              *(FILETIME *)((char *)this + 108),
                              v25,
                              *((struct UpdatePublishedHistory **)this + 290),
                              *((_DWORD *)this + 582),
                              1,
                              v4,
                              &v23);
      if ( NextPublishedUpdate >= 0 )
      {
        if ( v26 && !v23 )
        {
          LogLevel(4u, L"Device has deferred feature set");
          a2->status = UpdateAssessmentStatus_NotLatestDeferredFeature;
          return (unsigned int)NextPublishedUpdate;
        }
        if ( *((_DWORD *)this + 16) > 1u && a4 )
        {
          LogLevel(4u, L"Device is not on current branch");
          a2->status = UpdateAssessmentStatus_NotLatestServicingTrain;
          return (unsigned int)NextPublishedUpdate;
        }
        NextPublishedUpdate = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v13 + 96LL))(
                                (char *)this + 208,
                                &v24);
        if ( NextPublishedUpdate >= 0 )
        {
          if ( v24 )
          {
            LogLevel(4u, L"Device has set targeted version");
            a2->status = UpdateAssessmentStatus_NotLatestUnknown|UpdateAssessmentStatus_NotLatestSoftRestriction;
          }
          else
          {
            LogLevel(4u, L"Device is not latest");
            a2->status = UpdateAssessmentStatus_NotLatestUnknown;
          }
          return (unsigned int)NextPublishedUpdate;
        }
      }
    }
LABEL_28:
    LogLevel(2u, L"GetFeatureUpdateAssessmentReason Failure: 0x%x", (unsigned int)NextPublishedUpdate);
    return (unsigned int)NextPublishedUpdate;
  }
  v15 = v14 - 1;
  if ( v15 )
  {
    if ( v15 == 1 )
      a2->status = UpdateAssessmentStatus_NotLatestHardRestriction;
  }
  else
  {
    a2->status = UpdateAssessmentStatus_NotLatestSoftRestriction;
  }
  return (unsigned int)NextPublishedUpdate;
}

```

## disassembly

```asm
0x1800070d0  push    rbp
0x1800070d2  push    rbx
0x1800070d3  push    rsi
0x1800070d4  push    rdi
0x1800070d5  push    r12
0x1800070d7  push    r13
0x1800070d9  push    r14
0x1800070db  push    r15
0x1800070dd  mov     rbp, rsp
0x1800070e0  sub     rsp, 68h
0x1800070e4  xor     r13d, r13d
0x1800070e7  mov     [rsp+68h+var_40], r8; struct _FILETIME *
0x1800070ec  lea     r12, [rcx+4E8h]
0x1800070f3  mov     [rbp+var_28], r13d
0x1800070f7  mov     r14, r8
0x1800070fa  mov     [rbp+var_24], r13d
0x1800070fe  mov     r8d, [rcx+918h]; unsigned int
0x180007105  mov     rbx, rdx
0x180007108  mov     rdx, [rcx+910h]; struct UpdatePublishedHistory *
0x18000710f  mov     r15d, r9d
0x180007112  mov     rsi, rcx
0x180007115  mov     [rbp+var_20], r13d
0x180007119  mov     rcx, [rcx+6Ch]; struct _FILETIME
0x18000711d  lea     r9d, [r13+1]; int
0x180007121  mov     [rbp+var_1C], r13d
0x180007125  mov     [rbp+var_14], r13d
0x180007129  mov     [rsp+68h+var_48], r12; unsigned __int16 *
0x18000712e  call    ?FindNextPublishedUpdate@@YAJU_FILETIME@@PEAUUpdatePublishedHistory@@KHPEBGPEAU1@@Z; FindNextPublishedUpdate(_FILETIME,UpdatePublishedHistory *,ulong,int,ushort const *,_FILETIME *)
0x180007133  mov     edi, eax
0x180007135  test    eax, eax
0x180007137  js      loc_18000734E
0x18000713d  mov     rax, [rsi]
0x180007140  lea     r8, [rbx+8]
0x180007144  mov     r9, [r14]
0x180007147  lea     rdx, [rbx+4]
0x18000714b  mov     rcx, rsi
0x18000714e  mov     rax, [rax+0D8h]
0x180007155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000715a  lea     r14, [rsi+0D0h]
0x180007161  mov     rax, [r14]
0x180007164  lea     rdx, [rbp+var_28]
0x180007168  mov     rcx, r14
0x18000716b  mov     rax, [rax+50h]
0x18000716f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007174  mov     edi, eax
0x180007176  test    eax, eax
0x180007178  js      loc_18000734E
0x18000717e  mov     rax, [r14]
0x180007181  lea     rdx, [rbp+var_24]
0x180007185  mov     rcx, r14
0x180007188  mov     rax, [rax+48h]
0x18000718c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007191  mov     edi, eax
0x180007193  test    eax, eax
0x180007195  js      loc_18000734E
0x18000719b  mov     rax, [r14]
0x18000719e  lea     rdx, [rbp+var_20]
0x1800071a2  mov     rcx, r14
0x1800071a5  mov     rax, [rax+58h]
0x1800071a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ae  mov     edi, eax
0x1800071b0  test    eax, eax
0x1800071b2  js      loc_18000734E
0x1800071b8  cmp     [rbp+var_28], r13d
0x1800071bc  jz      short loc_1800071E6
0x1800071be  cmp     [rbp+var_24], r13d
0x1800071c2  jz      short loc_1800071CA
0x1800071c4  cmp     [rbp+var_20], r13d
0x1800071c8  jz      short loc_1800071E6
0x1800071ca  lea     rdx, aDeviceIsManage_0; "Device is managed"
0x1800071d1  mov     ecx, 4; unsigned __int8
0x1800071d6  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800071db  mov     dword ptr [rbx], 9
0x1800071e1  jmp     loc_180007362
0x1800071e6  mov     ecx, [rsi+44h]
0x1800071e9  test    ecx, ecx
0x1800071eb  jz      short loc_180007211
0x1800071ed  sub     ecx, 1
0x1800071f0  jz      short loc_180007206
0x1800071f2  cmp     ecx, 1
0x1800071f5  jnz     loc_180007362
0x1800071fb  mov     dword ptr [rbx], 2
0x180007201  jmp     loc_180007362
0x180007206  mov     dword ptr [rbx], 1
0x18000720c  jmp     loc_180007362
0x180007211  mov     rax, [r14]
0x180007214  lea     rdx, [rbp+var_1C]
0x180007218  mov     rcx, r14
0x18000721b  mov     rax, [rax+38h]
0x18000721f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007224  mov     edi, eax
0x180007226  test    eax, eax
0x180007228  js      loc_18000734E
0x18000722e  cmp     [rbp+var_1C], r13d
0x180007232  jz      short loc_180007250
0x180007234  lea     rdx, aDeviceHasPause_0; "Device has paused feature updates"
0x18000723b  mov     ecx, 4; unsigned __int8
0x180007240  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007245  mov     dword ptr [rbx], 7
0x18000724b  jmp     loc_180007362
0x180007250  mov     rax, [r14]
0x180007253  lea     rdx, [rbp+arg_0]
0x180007257  mov     rcx, r14
0x18000725a  mov     qword ptr [rbp+var_10.dwLowDateTime], r13
0x18000725e  mov     [rbp+arg_0], r13d
0x180007262  mov     [rbp+var_18], r13d
0x180007266  mov     rax, [rax+28h]
0x18000726a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000726f  mov     ecx, [rbp+arg_0]; unsigned int
0x180007272  lea     rdx, [rbp+var_10]; struct _FILETIME *
0x180007276  call    ?SubtractDaysFromCurrentTimeUTC@@YAJKPEAU_FILETIME@@@Z; SubtractDaysFromCurrentTimeUTC(ulong,_FILETIME *)
0x18000727b  mov     r9d, [rsi+918h]; unsigned int
0x180007282  lea     rax, [rbp+var_18]
0x180007286  mov     r8, [rsi+910h]; struct UpdatePublishedHistory *
0x18000728d  mov     rdx, qword ptr [rbp+var_10.dwLowDateTime]; struct _FILETIME
0x180007291  mov     rcx, [rsi+6Ch]; struct _FILETIME
0x180007295  mov     [rsp+68h+var_38], rax; unsigned int *
0x18000729a  mov     [rsp+68h+var_40], r12; unsigned __int16 *
0x18000729f  mov     dword ptr [rsp+68h+var_48], 1; int
0x1800072a7  call    ?CountUpdatesPublishedBetweenRange@@YAJU_FILETIME@@0PEAUUpdatePublishedHistory@@KHPEBGAEAK@Z; CountUpdatesPublishedBetweenRange(_FILETIME,_FILETIME,UpdatePublishedHistory *,ulong,int,ushort const *,ulong &)
0x1800072ac  mov     edi, eax
0x1800072ae  test    eax, eax
0x1800072b0  js      loc_18000734E
0x1800072b6  cmp     [rbp+arg_0], r13d
0x1800072ba  jbe     short loc_1800072DE
0x1800072bc  cmp     [rbp+var_18], r13d
0x1800072c0  jnz     short loc_1800072DE
0x1800072c2  lea     rdx, aDeviceHasDefer; "Device has deferred feature set"
0x1800072c9  mov     ecx, 4; unsigned __int8
0x1800072ce  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800072d3  mov     dword ptr [rbx], 5
0x1800072d9  jmp     loc_180007362
0x1800072de  cmp     dword ptr [rsi+40h], 1
0x1800072e2  jbe     short loc_180007302
0x1800072e4  test    r15d, r15d
0x1800072e7  jz      short loc_180007302
0x1800072e9  lea     rdx, aDeviceIsNotOnC; "Device is not on current branch"
0x1800072f0  mov     ecx, 4; unsigned __int8
0x1800072f5  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800072fa  mov     dword ptr [rbx], 4
0x180007300  jmp     short loc_180007362
0x180007302  mov     rax, [r14]
0x180007305  lea     rdx, [rbp+var_14]
0x180007309  mov     rcx, r14
0x18000730c  mov     rax, [rax+60h]
0x180007310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007315  mov     edi, eax
0x180007317  test    eax, eax
0x180007319  js      short loc_18000734E
0x18000731b  mov     ecx, 4; unsigned __int8
0x180007320  cmp     [rbp+var_14], r13d
0x180007324  jz      short loc_18000733A
0x180007326  lea     rdx, aDeviceHasSetTa; "Device has set targeted version"
0x18000732d  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007332  mov     dword ptr [rbx], 0Bh
0x180007338  jmp     short loc_180007362
0x18000733a  lea     rdx, aDeviceIsNotLat; "Device is not latest"
0x180007341  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007346  mov     dword ptr [rbx], 0Ah
0x18000734c  jmp     short loc_180007362
0x18000734e  mov     r8d, edi
0x180007351  lea     rdx, aGetfeatureupda; "GetFeatureUpdateAssessmentReason Failur"...
0x180007358  mov     ecx, 2; unsigned __int8
0x18000735d  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007362  mov     eax, edi
0x180007364  add     rsp, 68h
0x180007368  pop     r15
0x18000736a  pop     r14
0x18000736c  pop     r13
0x18000736e  pop     r12
0x180007370  pop     rdi
0x180007371  pop     rsi
0x180007372  pop     rbx
0x180007373  pop     rbp
0x180007374  retn
```

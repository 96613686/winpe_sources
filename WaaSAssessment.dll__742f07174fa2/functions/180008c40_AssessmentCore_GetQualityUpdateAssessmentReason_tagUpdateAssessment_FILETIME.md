# AssessmentCore::GetQualityUpdateAssessmentReason(tagUpdateAssessment &,_FILETIME *)

- ea: `0x180008c40`
- end: `0x180008e5d`
- name: `?GetQualityUpdateAssessmentReason@AssessmentCore@@MEAAJAEAUtagUpdateAssessment@@PEAU_FILETIME@@@Z`
- size: `541`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, struct tagUpdateAssessment *, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180008c40`
- `0x18001752c`
- `0x1800184dc`
- `0x1800186f0`
- `0x180018fe0`
- `0x18001b010`

## string_xrefs

- `0x180008d75`: `Device has paused quality updates`
- `0x180008e31`: `GetQualityUpdateAssessmentReason Failure: 0x%x`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetQualityUpdateAssessmentReason(
        AssessmentCore *this,
        struct tagUpdateAssessment *a2,
        struct _FILETIME *a3)
{
  char *v3; // r15
  unsigned int v5; // r8d
  struct UpdatePublishedHistory *v7; // rdx
  FILETIME v9; // rcx
  int NextPublishedUpdate; // ebx
  char *v11; // rdi
  __int64 v12; // rax
  int v15; // [rsp+40h] [rbp-20h] BYREF
  int v16; // [rsp+44h] [rbp-1Ch] BYREF
  int v17; // [rsp+48h] [rbp-18h] BYREF
  unsigned int v18; // [rsp+4Ch] [rbp-14h] BYREF
  struct _FILETIME v19; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+30h] BYREF
  int v21; // [rsp+A8h] [rbp+48h] BYREF

  v3 = (char *)this + 1256;
  v21 = 0;
  v15 = 0;
  v5 = *((_DWORD *)this + 582);
  v7 = (struct UpdatePublishedHistory *)*((_QWORD *)this + 290);
  v9 = *(FILETIME *)((char *)this + 100);
  v16 = 0;
  v17 = 0;
  NextPublishedUpdate = FindNextPublishedUpdate(v9, v7, v5, 0, v3, a3);
  if ( NextPublishedUpdate < 0 )
    goto LABEL_17;
  (*(void (__fastcall **)(AssessmentCore *, UpdateImpactLevel *, DWORD *, _QWORD))(*(_QWORD *)this + 208LL))(
    this,
    &a2->impact,
    &a2->daysOutOfDate,
    *a3);
  v11 = (char *)this + 208;
  NextPublishedUpdate = (*(__int64 (__fastcall **)(char *, int *))(*((_QWORD *)this + 26) + 80LL))(
                          (char *)this + 208,
                          &v21);
  if ( NextPublishedUpdate < 0 )
    goto LABEL_17;
  NextPublishedUpdate = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v11 + 72LL))((char *)this + 208, &v15);
  if ( NextPublishedUpdate < 0 )
    goto LABEL_17;
  NextPublishedUpdate = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v11 + 88LL))((char *)this + 208, &v16);
  if ( NextPublishedUpdate < 0 )
    goto LABEL_17;
  if ( v21 && (!v15 || v16) )
  {
    LogLevel(4u, L"Device is managed");
    a2->status = UpdateAssessmentStatus_NotLatestManaged;
    return (unsigned int)NextPublishedUpdate;
  }
  NextPublishedUpdate = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v11 + 64LL))((char *)this + 208, &v17);
  if ( NextPublishedUpdate < 0 )
    goto LABEL_17;
  if ( v17 )
  {
    LogLevel(4u, L"Device has paused quality updates");
    a2->status = UpdateAssessmentStatus_NotLatestPausedQuality;
    return (unsigned int)NextPublishedUpdate;
  }
  v12 = *(_QWORD *)v11;
  v19 = 0;
  v20 = 0;
  v18 = 0;
  (*(void (__fastcall **)(char *, unsigned int *))(v12 + 48))((char *)this + 208, &v20);
  SubtractDaysFromCurrentTimeUTC(v20, &v19);
  NextPublishedUpdate = CountUpdatesPublishedBetweenRange(
                          *(FILETIME *)((char *)this + 100),
                          v19,
                          *((struct UpdatePublishedHistory **)this + 290),
                          *((_DWORD *)this + 582),
                          0,
                          v3,
                          &v18);
  if ( NextPublishedUpdate < 0 )
  {
LABEL_17:
    LogLevel(2u, L"GetQualityUpdateAssessmentReason Failure: 0x%x", (unsigned int)NextPublishedUpdate);
    return (unsigned int)NextPublishedUpdate;
  }
  if ( !v20 || v18 )
  {
    LogLevel(4u, L"Device is not latest");
    a2->status = UpdateAssessmentStatus_NotLatestUnknown;
  }
  else
  {
    LogLevel(4u, L"Device has deferral quality set");
    a2->status = UpdateAssessmentStatus_NotLatestDeferredQuality;
  }
  return (unsigned int)NextPublishedUpdate;
}

```

## disassembly

```asm
0x180008c40  mov     rax, rsp
0x180008c43  mov     [rax+10h], rbx
0x180008c47  mov     [rax+18h], rsi
0x180008c4b  push    rbp
0x180008c4c  push    rdi
0x180008c4d  push    r12
0x180008c4f  push    r14
0x180008c51  push    r15
0x180008c53  mov     rbp, rsp
0x180008c56  sub     rsp, 60h
0x180008c5a  xor     r12d, r12d
0x180008c5d  mov     [rax-60h], r8
0x180008c61  lea     r15, [rcx+4E8h]
0x180008c68  mov     [rbp+arg_18], r12d
0x180008c6c  mov     rdi, r8
0x180008c6f  mov     [rbp+var_20], r12d
0x180008c73  mov     r8d, [rcx+918h]; unsigned int
0x180008c7a  mov     rsi, rdx
0x180008c7d  mov     rdx, [rcx+910h]; struct UpdatePublishedHistory *
0x180008c84  mov     r14, rcx
0x180008c87  mov     rcx, [rcx+64h]; struct _FILETIME
0x180008c8b  xor     r9d, r9d; int
0x180008c8e  mov     [rbp+var_1C], r12d
0x180008c92  mov     [rbp+var_18], r12d
0x180008c96  mov     [rax-68h], r15
0x180008c9a  call    ?FindNextPublishedUpdate@@YAJU_FILETIME@@PEAUUpdatePublishedHistory@@KHPEBGPEAU1@@Z; FindNextPublishedUpdate(_FILETIME,UpdatePublishedHistory *,ulong,int,ushort const *,_FILETIME *)
0x180008c9f  mov     ebx, eax
0x180008ca1  test    eax, eax
0x180008ca3  js      loc_180008E2E
0x180008ca9  mov     rax, [r14]
0x180008cac  lea     r8, [rsi+8]
0x180008cb0  mov     r9, [rdi]
0x180008cb3  lea     rdx, [rsi+4]
0x180008cb7  mov     rcx, r14
0x180008cba  mov     rax, [rax+0D0h]
0x180008cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc6  lea     rdi, [r14+0D0h]
0x180008ccd  mov     rax, [rdi]
0x180008cd0  lea     rdx, [rbp+arg_18]
0x180008cd4  mov     rcx, rdi
0x180008cd7  mov     rax, [rax+50h]
0x180008cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ce0  mov     ebx, eax
0x180008ce2  test    eax, eax
0x180008ce4  js      loc_180008E2E
0x180008cea  mov     rax, [rdi]
0x180008ced  lea     rdx, [rbp+var_20]
0x180008cf1  mov     rcx, rdi
0x180008cf4  mov     rax, [rax+48h]
0x180008cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cfd  mov     ebx, eax
0x180008cff  test    eax, eax
0x180008d01  js      loc_180008E2E
0x180008d07  mov     rax, [rdi]
0x180008d0a  lea     rdx, [rbp+var_1C]
0x180008d0e  mov     rcx, rdi
0x180008d11  mov     rax, [rax+58h]
0x180008d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d1a  mov     ebx, eax
0x180008d1c  test    eax, eax
0x180008d1e  js      loc_180008E2E
0x180008d24  cmp     [rbp+arg_18], r12d
0x180008d28  jz      short loc_180008D52
0x180008d2a  cmp     [rbp+var_20], r12d
0x180008d2e  jz      short loc_180008D36
0x180008d30  cmp     [rbp+var_1C], r12d
0x180008d34  jz      short loc_180008D52
0x180008d36  lea     rdx, aDeviceIsManage_0; "Device is managed"
0x180008d3d  mov     ecx, 4; unsigned __int8
0x180008d42  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008d47  mov     dword ptr [rsi], 9
0x180008d4d  jmp     loc_180008E42
0x180008d52  mov     rax, [rdi]
0x180008d55  lea     rdx, [rbp+var_18]
0x180008d59  mov     rcx, rdi
0x180008d5c  mov     rax, [rax+40h]
0x180008d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d65  mov     ebx, eax
0x180008d67  test    eax, eax
0x180008d69  js      loc_180008E2E
0x180008d6f  cmp     [rbp+var_18], r12d
0x180008d73  jz      short loc_180008D91
0x180008d75  lea     rdx, aDeviceHasPause; "Device has paused quality updates"
0x180008d7c  mov     ecx, 4; unsigned __int8
0x180008d81  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008d86  mov     dword ptr [rsi], 8
0x180008d8c  jmp     loc_180008E42
0x180008d91  mov     rax, [rdi]
0x180008d94  lea     rdx, [rbp+arg_0]
0x180008d98  mov     rcx, rdi
0x180008d9b  mov     qword ptr [rbp+var_10.dwLowDateTime], r12
0x180008d9f  mov     [rbp+arg_0], r12d
0x180008da3  mov     [rbp+var_14], r12d
0x180008da7  mov     rax, [rax+30h]
0x180008dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008db0  mov     ecx, [rbp+arg_0]; unsigned int
0x180008db3  lea     rdx, [rbp+var_10]; struct _FILETIME *
0x180008db7  call    ?SubtractDaysFromCurrentTimeUTC@@YAJKPEAU_FILETIME@@@Z; SubtractDaysFromCurrentTimeUTC(ulong,_FILETIME *)
0x180008dbc  mov     r9d, [r14+918h]; unsigned int
0x180008dc3  lea     rax, [rbp+var_14]
0x180008dc7  mov     r8, [r14+910h]; struct UpdatePublishedHistory *
0x180008dce  mov     rdx, qword ptr [rbp+var_10.dwLowDateTime]; struct _FILETIME
0x180008dd2  mov     rcx, [r14+64h]; struct _FILETIME
0x180008dd6  mov     [rsp+60h+var_30], rax; unsigned int *
0x180008ddb  mov     [rsp+60h+var_38], r15; unsigned __int16 *
0x180008de0  mov     [rsp+60h+var_40], r12d; int
0x180008de5  call    ?CountUpdatesPublishedBetweenRange@@YAJU_FILETIME@@0PEAUUpdatePublishedHistory@@KHPEBGAEAK@Z; CountUpdatesPublishedBetweenRange(_FILETIME,_FILETIME,UpdatePublishedHistory *,ulong,int,ushort const *,ulong &)
0x180008dea  mov     ebx, eax
0x180008dec  test    eax, eax
0x180008dee  js      short loc_180008E2E
0x180008df0  cmp     [rbp+arg_0], r12d
0x180008df4  jbe     short loc_180008E15
0x180008df6  cmp     [rbp+var_14], r12d
0x180008dfa  jnz     short loc_180008E15
0x180008dfc  lea     rdx, aDeviceHasDefer_0; "Device has deferral quality set"
0x180008e03  mov     ecx, 4; unsigned __int8
0x180008e08  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008e0d  mov     dword ptr [rsi], 6
0x180008e13  jmp     short loc_180008E42
0x180008e15  lea     rdx, aDeviceIsNotLat; "Device is not latest"
0x180008e1c  mov     ecx, 4; unsigned __int8
0x180008e21  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008e26  mov     dword ptr [rsi], 0Ah
0x180008e2c  jmp     short loc_180008E42
0x180008e2e  mov     r8d, ebx
0x180008e31  lea     rdx, aGetqualityupda_0; "GetQualityUpdateAssessmentReason Failur"...
0x180008e38  mov     ecx, 2; unsigned __int8
0x180008e3d  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008e42  lea     r11, [rsp+60h+var_s0]
0x180008e47  mov     eax, ebx
0x180008e49  mov     rbx, [r11+38h]
0x180008e4d  mov     rsi, [r11+40h]
0x180008e51  mov     rsp, r11
0x180008e54  pop     r15
0x180008e56  pop     r14
0x180008e58  pop     r12
0x180008e5a  pop     rdi
0x180008e5b  pop     rbp
0x180008e5c  retn
```

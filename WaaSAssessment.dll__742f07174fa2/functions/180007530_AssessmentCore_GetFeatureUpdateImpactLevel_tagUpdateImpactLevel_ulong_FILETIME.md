# AssessmentCore::GetFeatureUpdateImpactLevel(tagUpdateImpactLevel &,ulong &,_FILETIME)

- ea: `0x180007530`
- end: `0x180007663`
- name: `?GetFeatureUpdateImpactLevel@AssessmentCore@@MEAAJAEAW4tagUpdateImpactLevel@@AEAKU_FILETIME@@@Z`
- size: `307`
- prototype: `int(AssessmentCore *__hidden this, enum tagUpdateImpactLevel *, unsigned int *, struct _FILETIME)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180007530`
- `0x18001752c`
- `0x180018808`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007562`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007562`

## string_xrefs

- `0x18000763d`: `GetFeatureUpdateImpactLevel Failure: 0x%x`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetFeatureUpdateImpactLevel(
        AssessmentCore *this,
        enum tagUpdateImpactLevel *a2,
        unsigned int *a3,
        FILETIME a4)
{
  struct _FILETIME v8; // rcx
  int DaysBetweenFileTimes; // ebx
  unsigned int v10; // r8d
  struct _FILETIME v12; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v13; // [rsp+58h] [rbp+10h] BYREF

  v12 = 0;
  v13 = 0;
  GetSystemTimeAsFileTime(&v12);
  v8 = v12;
  *a2 = UpdateImpactLevel_None;
  DaysBetweenFileTimes = GetDaysBetweenFileTimes(v8, a4, a3);
  if ( DaysBetweenFileTimes < 0
    || (LogLevel(4u, L"Device is %d out of date", *a3),
        DaysBetweenFileTimes = (*(__int64 (__fastcall **)(char *, unsigned int *))(*((_QWORD *)this + 26) + 40LL))(
                                 (char *)this + 208,
                                 &v13),
        DaysBetweenFileTimes < 0) )
  {
    LogLevel(2u, L"GetFeatureUpdateImpactLevel Failure: 0x%x", (unsigned int)DaysBetweenFileTimes);
  }
  else
  {
    if ( *a3 <= v13 )
      v10 = 0;
    else
      v10 = *a3 - v13;
    *a3 = v10;
    LogLevel(4u, L"Device is %d out of date after accounting for feature deferral");
    if ( *a3 >= *((_DWORD *)this + 23) )
    {
      LogLevel(4u, L"Impact Status is low");
      *a2 = UpdateImpactLevel_Low;
    }
    if ( *a3 >= *((_DWORD *)this + 22) )
    {
      LogLevel(4u, L"Impact Status is medium");
      *a2 = UpdateImpactLevel_Medium;
    }
    if ( *a3 >= *((_DWORD *)this + 21) )
    {
      LogLevel(4u, L"Impact Status is high");
      *a2 = UpdateImpactLevel_High;
    }
  }
  return (unsigned int)DaysBetweenFileTimes;
}

```

## disassembly

```asm
0x180007530  mov     rax, rsp
0x180007533  mov     [rax+8], rbx
0x180007537  mov     [rax+18h], rbp
0x18000753b  push    rsi
0x18000753c  push    rdi
0x18000753d  push    r14
0x18000753f  sub     rsp, 30h
0x180007543  mov     rbp, rcx
0x180007546  mov     qword ptr [rax-28h], 0
0x18000754e  lea     rcx, [rax-28h]; lpSystemTimeAsFileTime
0x180007552  mov     dword ptr [rax+10h], 0
0x180007559  mov     rbx, r9
0x18000755c  mov     rdi, r8
0x18000755f  mov     rsi, rdx
0x180007562  call    cs:__imp_GetSystemTimeAsFileTime
0x180007568  mov     rcx, qword ptr [rsp+48h+var_28.dwLowDateTime]; struct _FILETIME
0x18000756d  mov     r8, rdi; unsigned int *
0x180007570  mov     rdx, rbx; struct _FILETIME
0x180007573  mov     dword ptr [rsi], 0
0x180007579  call    ?GetDaysBetweenFileTimes@@YAJU_FILETIME@@0PEAK@Z; GetDaysBetweenFileTimes(_FILETIME,_FILETIME,ulong *)
0x18000757e  mov     ebx, eax
0x180007580  test    eax, eax
0x180007582  js      loc_18000763A
0x180007588  mov     r8d, [rdi]
0x18000758b  lea     rdx, aDeviceIsDOutOf; "Device is %d out of date"
0x180007592  mov     r14d, 4
0x180007598  mov     ecx, r14d; unsigned __int8
0x18000759b  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800075a0  lea     rcx, [rbp+0D0h]
0x1800075a7  mov     rax, [rcx]
0x1800075aa  lea     rdx, [rsp+48h+arg_8]
0x1800075af  mov     rax, [rax+28h]
0x1800075b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075b8  mov     ebx, eax
0x1800075ba  test    eax, eax
0x1800075bc  js      short loc_18000763A
0x1800075be  mov     r8d, [rdi]
0x1800075c1  cmp     r8d, [rsp+48h+arg_8]
0x1800075c6  jbe     short loc_1800075CF
0x1800075c8  sub     r8d, [rsp+48h+arg_8]
0x1800075cd  jmp     short loc_1800075D2
0x1800075cf  xor     r8d, r8d
0x1800075d2  lea     rdx, aDeviceIsDOutOf_0; "Device is %d out of date after accounti"...
0x1800075d9  mov     [rdi], r8d
0x1800075dc  mov     ecx, r14d; unsigned __int8
0x1800075df  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800075e4  mov     eax, [rbp+5Ch]
0x1800075e7  cmp     [rdi], eax
0x1800075e9  jb      short loc_180007600
0x1800075eb  lea     rdx, aImpactStatusIs; "Impact Status is low"
0x1800075f2  mov     ecx, r14d; unsigned __int8
0x1800075f5  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800075fa  mov     dword ptr [rsi], 1
0x180007600  mov     eax, [rbp+58h]
0x180007603  cmp     [rdi], eax
0x180007605  jb      short loc_18000761C
0x180007607  lea     rdx, aImpactStatusIs_1; "Impact Status is medium"
0x18000760e  mov     ecx, r14d; unsigned __int8
0x180007611  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007616  mov     dword ptr [rsi], 2
0x18000761c  mov     eax, [rbp+54h]
0x18000761f  cmp     [rdi], eax
0x180007621  jb      short loc_18000764E
0x180007623  lea     rdx, aImpactStatusIs_0; "Impact Status is high"
0x18000762a  mov     ecx, r14d; unsigned __int8
0x18000762d  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007632  mov     dword ptr [rsi], 3
0x180007638  jmp     short loc_18000764E
0x18000763a  mov     r8d, ebx
0x18000763d  lea     rdx, aGetfeatureupda_1; "GetFeatureUpdateImpactLevel Failure: 0x"...
0x180007644  mov     ecx, 2; unsigned __int8
0x180007649  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000764e  mov     rbp, [rsp+48h+arg_10]
0x180007653  mov     eax, ebx
0x180007655  mov     rbx, [rsp+48h+arg_0]
0x18000765a  add     rsp, 30h
0x18000765e  pop     r14
0x180007660  pop     rdi
0x180007661  pop     rsi
0x180007662  retn
```

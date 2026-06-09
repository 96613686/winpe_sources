# AssessmentCore::GetQualityUpdateImpactLevel(tagUpdateImpactLevel &,ulong &,_FILETIME)

- ea: `0x180009020`
- end: `0x180009153`
- name: `?GetQualityUpdateImpactLevel@AssessmentCore@@MEAAJAEAW4tagUpdateImpactLevel@@AEAKU_FILETIME@@@Z`
- size: `307`
- prototype: `int(AssessmentCore *__hidden this, enum tagUpdateImpactLevel *, unsigned int *, struct _FILETIME)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180009020`
- `0x18001752c`
- `0x180018808`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009052`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009052`

## string_xrefs

- `0x18000912d`: `GetQualityUpdateImpactLevel Failure: 0x%x`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetQualityUpdateImpactLevel(
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
        DaysBetweenFileTimes = (*(__int64 (__fastcall **)(char *, unsigned int *))(*((_QWORD *)this + 26) + 48LL))(
                                 (char *)this + 208,
                                 &v13),
        DaysBetweenFileTimes < 0) )
  {
    LogLevel(2u, L"GetQualityUpdateImpactLevel Failure: 0x%x", (unsigned int)DaysBetweenFileTimes);
  }
  else
  {
    if ( *a3 <= v13 )
      v10 = 0;
    else
      v10 = *a3 - v13;
    *a3 = v10;
    LogLevel(4u, L"Device is %d out of date after accounting for quality deferral");
    if ( *a3 >= *((_DWORD *)this + 20) )
    {
      LogLevel(4u, L"Impact Status is low");
      *a2 = UpdateImpactLevel_Low;
    }
    if ( *a3 >= *((_DWORD *)this + 19) )
    {
      LogLevel(4u, L"Impact Status is medium");
      *a2 = UpdateImpactLevel_Medium;
    }
    if ( *a3 >= *((_DWORD *)this + 18) )
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
0x180009020  mov     rax, rsp
0x180009023  mov     [rax+8], rbx
0x180009027  mov     [rax+18h], rbp
0x18000902b  push    rsi
0x18000902c  push    rdi
0x18000902d  push    r14
0x18000902f  sub     rsp, 30h
0x180009033  mov     rbp, rcx
0x180009036  mov     qword ptr [rax-28h], 0
0x18000903e  lea     rcx, [rax-28h]; lpSystemTimeAsFileTime
0x180009042  mov     dword ptr [rax+10h], 0
0x180009049  mov     rbx, r9
0x18000904c  mov     rdi, r8
0x18000904f  mov     rsi, rdx
0x180009052  call    cs:__imp_GetSystemTimeAsFileTime
0x180009058  mov     rcx, qword ptr [rsp+48h+var_28.dwLowDateTime]; struct _FILETIME
0x18000905d  mov     r8, rdi; unsigned int *
0x180009060  mov     rdx, rbx; struct _FILETIME
0x180009063  mov     dword ptr [rsi], 0
0x180009069  call    ?GetDaysBetweenFileTimes@@YAJU_FILETIME@@0PEAK@Z; GetDaysBetweenFileTimes(_FILETIME,_FILETIME,ulong *)
0x18000906e  mov     ebx, eax
0x180009070  test    eax, eax
0x180009072  js      loc_18000912A
0x180009078  mov     r8d, [rdi]
0x18000907b  lea     rdx, aDeviceIsDOutOf; "Device is %d out of date"
0x180009082  mov     r14d, 4
0x180009088  mov     ecx, r14d; unsigned __int8
0x18000908b  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009090  lea     rcx, [rbp+0D0h]
0x180009097  mov     rax, [rcx]
0x18000909a  lea     rdx, [rsp+48h+arg_8]
0x18000909f  mov     rax, [rax+30h]
0x1800090a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090a8  mov     ebx, eax
0x1800090aa  test    eax, eax
0x1800090ac  js      short loc_18000912A
0x1800090ae  mov     r8d, [rdi]
0x1800090b1  cmp     r8d, [rsp+48h+arg_8]
0x1800090b6  jbe     short loc_1800090BF
0x1800090b8  sub     r8d, [rsp+48h+arg_8]
0x1800090bd  jmp     short loc_1800090C2
0x1800090bf  xor     r8d, r8d
0x1800090c2  lea     rdx, aDeviceIsDOutOf_1; "Device is %d out of date after accounti"...
0x1800090c9  mov     [rdi], r8d
0x1800090cc  mov     ecx, r14d; unsigned __int8
0x1800090cf  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800090d4  mov     eax, [rbp+50h]
0x1800090d7  cmp     [rdi], eax
0x1800090d9  jb      short loc_1800090F0
0x1800090db  lea     rdx, aImpactStatusIs; "Impact Status is low"
0x1800090e2  mov     ecx, r14d; unsigned __int8
0x1800090e5  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800090ea  mov     dword ptr [rsi], 1
0x1800090f0  mov     eax, [rbp+4Ch]
0x1800090f3  cmp     [rdi], eax
0x1800090f5  jb      short loc_18000910C
0x1800090f7  lea     rdx, aImpactStatusIs_1; "Impact Status is medium"
0x1800090fe  mov     ecx, r14d; unsigned __int8
0x180009101  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009106  mov     dword ptr [rsi], 2
0x18000910c  mov     eax, [rbp+48h]
0x18000910f  cmp     [rdi], eax
0x180009111  jb      short loc_18000913E
0x180009113  lea     rdx, aImpactStatusIs_0; "Impact Status is high"
0x18000911a  mov     ecx, r14d; unsigned __int8
0x18000911d  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009122  mov     dword ptr [rsi], 3
0x180009128  jmp     short loc_18000913E
0x18000912a  mov     r8d, ebx
0x18000912d  lea     rdx, aGetqualityupda; "GetQualityUpdateImpactLevel Failure: 0x"...
0x180009134  mov     ecx, 2; unsigned __int8
0x180009139  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000913e  mov     rbp, [rsp+48h+arg_10]
0x180009143  mov     eax, ebx
0x180009145  mov     rbx, [rsp+48h+arg_0]
0x18000914a  add     rsp, 30h
0x18000914e  pop     r14
0x180009150  pop     rdi
0x180009151  pop     rsi
0x180009152  retn
```

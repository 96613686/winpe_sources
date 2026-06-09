# AssessmentCore::GetFeatureUpdateAssessmentReasonEx(tagUpdateAssessmentStatusEx *)

- ea: `0x180007380`
- end: `0x180007520`
- name: `?GetFeatureUpdateAssessmentReasonEx@AssessmentCore@@MEAAJPEAW4tagUpdateAssessmentStatusEx@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, enum tagUpdateAssessmentStatusEx *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180007380`
- `0x18001752c`
- `0x1800184dc`
- `0x180018fe0`
- `0x18001b010`

## string_xrefs

- `0x18000745c`: `Device has paused feature updates`
- `0x1800074f9`: `GetFeatureUpdateAssessmentReasonEx Failure: 0x%x`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetFeatureUpdateAssessmentReasonEx(
        AssessmentCore *this,
        enum tagUpdateAssessmentStatusEx *a2)
{
  char *v2; // rdi
  __int64 v4; // rax
  __int64 (__fastcall *v6)(char *, int *); // rax
  int v7; // ebx
  __int64 v8; // rax
  int v10; // [rsp+40h] [rbp-20h] BYREF
  int v11; // [rsp+44h] [rbp-1Ch] BYREF
  unsigned int v12; // [rsp+48h] [rbp-18h] BYREF
  struct _FILETIME v13; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v14; // [rsp+98h] [rbp+38h] BYREF
  int v15; // [rsp+A0h] [rbp+40h] BYREF
  int v16; // [rsp+A8h] [rbp+48h] BYREF

  v2 = (char *)this + 208;
  *(_DWORD *)a2 = 0;
  v4 = *((_QWORD *)this + 26);
  v15 = 0;
  v16 = 0;
  v10 = 0;
  v6 = *(__int64 (__fastcall **)(char *, int *))(v4 + 80);
  v11 = 0;
  v7 = v6((char *)this + 208, &v15);
  if ( v7 < 0 )
    goto LABEL_14;
  v7 = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v2 + 72LL))(v2, &v16);
  if ( v7 < 0 )
    goto LABEL_14;
  v7 = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v2 + 88LL))(v2, &v10);
  if ( v7 < 0 )
    goto LABEL_14;
  if ( v15 && (!v16 || v10) )
  {
    LogLevel(4u, L"Device is managed only through WSUS.");
    return (unsigned int)v7;
  }
  v7 = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v2 + 56LL))(v2, &v11);
  if ( v7 < 0 )
    goto LABEL_14;
  if ( !v11 )
    return (unsigned int)v7;
  LogLevel(4u, L"Device has paused feature updates");
  v8 = *(_QWORD *)v2;
  v13 = 0;
  v14 = 0;
  v12 = 0;
  (*(void (__fastcall **)(char *, unsigned int *))(v8 + 40))(v2, &v14);
  SubtractDaysFromCurrentTimeUTC(v14, &v13);
  v7 = CountUpdatesPublishedBetweenRange(
         *(FILETIME *)((char *)this + 108),
         v13,
         *((struct UpdatePublishedHistory **)this + 290),
         *((_DWORD *)this + 582),
         1,
         (char *)this + 1256,
         &v12);
  if ( v7 < 0 )
  {
LABEL_14:
    LogLevel(2u, L"GetFeatureUpdateAssessmentReasonEx Failure: 0x%x", (unsigned int)v7);
    return (unsigned int)v7;
  }
  if ( v14 && !v12 )
  {
    LogLevel(4u, L"Device is paused and has deferred feature set");
    *(_DWORD *)a2 = 1;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007380  mov     [rsp-28h+arg_0], rbx
0x180007385  push    rbp
0x180007386  push    rsi
0x180007387  push    rdi
0x180007388  push    r14
0x18000738a  push    r15
0x18000738c  mov     rbp, rsp
0x18000738f  sub     rsp, 60h
0x180007393  xor     r15d, r15d
0x180007396  lea     rdi, [rcx+0D0h]
0x18000739d  mov     [rdx], r15d
0x1800073a0  mov     rsi, rdx
0x1800073a3  mov     rax, [rdi]
0x1800073a6  lea     rdx, [rbp+arg_10]
0x1800073aa  mov     r14, rcx
0x1800073ad  mov     [rbp+arg_10], r15d
0x1800073b1  mov     rcx, rdi
0x1800073b4  mov     [rbp+arg_18], r15d
0x1800073b8  mov     [rbp+var_20], r15d
0x1800073bc  mov     rax, [rax+50h]
0x1800073c0  mov     [rbp+var_1C], r15d
0x1800073c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c9  mov     ebx, eax
0x1800073cb  test    eax, eax
0x1800073cd  js      loc_1800074F6
0x1800073d3  mov     rax, [rdi]
0x1800073d6  lea     rdx, [rbp+arg_18]
0x1800073da  mov     rcx, rdi
0x1800073dd  mov     rax, [rax+48h]
0x1800073e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073e6  mov     ebx, eax
0x1800073e8  test    eax, eax
0x1800073ea  js      loc_1800074F6
0x1800073f0  mov     rax, [rdi]
0x1800073f3  lea     rdx, [rbp+var_20]
0x1800073f7  mov     rcx, rdi
0x1800073fa  mov     rax, [rax+58h]
0x1800073fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007403  mov     ebx, eax
0x180007405  test    eax, eax
0x180007407  js      loc_1800074F6
0x18000740d  cmp     [rbp+arg_10], r15d
0x180007411  jz      short loc_180007435
0x180007413  cmp     [rbp+arg_18], r15d
0x180007417  jz      short loc_18000741F
0x180007419  cmp     [rbp+var_20], r15d
0x18000741d  jz      short loc_180007435
0x18000741f  lea     rdx, aDeviceIsManage; "Device is managed only through WSUS."
0x180007426  mov     ecx, 4; unsigned __int8
0x18000742b  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180007430  jmp     loc_18000750A
0x180007435  mov     rax, [rdi]
0x180007438  lea     rdx, [rbp+var_1C]
0x18000743c  mov     rcx, rdi
0x18000743f  mov     rax, [rax+38h]
0x180007443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007448  mov     ebx, eax
0x18000744a  test    eax, eax
0x18000744c  js      loc_1800074F6
0x180007452  cmp     [rbp+var_1C], r15d
0x180007456  jz      loc_18000750A
0x18000745c  lea     rdx, aDeviceHasPause_0; "Device has paused feature updates"
0x180007463  mov     ecx, 4; unsigned __int8
0x180007468  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000746d  mov     rax, [rdi]
0x180007470  lea     rdx, [rbp+arg_8]
0x180007474  mov     rcx, rdi
0x180007477  mov     qword ptr [rbp+var_10.dwLowDateTime], r15
0x18000747b  mov     [rbp+arg_8], r15d
0x18000747f  mov     [rbp+var_18], r15d
0x180007483  mov     rax, [rax+28h]
0x180007487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000748c  mov     ecx, [rbp+arg_8]; unsigned int
0x18000748f  lea     rdx, [rbp+var_10]; struct _FILETIME *
0x180007493  call    ?SubtractDaysFromCurrentTimeUTC@@YAJKPEAU_FILETIME@@@Z; SubtractDaysFromCurrentTimeUTC(ulong,_FILETIME *)
0x180007498  mov     r9d, [r14+918h]; unsigned int
0x18000749f  lea     rcx, [rbp+var_18]
0x1800074a3  mov     r8, [r14+910h]; struct UpdatePublishedHistory *
0x1800074aa  lea     rax, [r14+4E8h]
0x1800074b1  mov     rdx, qword ptr [rbp+var_10.dwLowDateTime]; struct _FILETIME
0x1800074b5  mov     edi, 1
0x1800074ba  mov     [rsp+60h+var_30], rcx; unsigned int *
0x1800074bf  mov     rcx, [r14+6Ch]; struct _FILETIME
0x1800074c3  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x1800074c8  mov     [rsp+60h+var_40], edi; int
0x1800074cc  call    ?CountUpdatesPublishedBetweenRange@@YAJU_FILETIME@@0PEAUUpdatePublishedHistory@@KHPEBGAEAK@Z; CountUpdatesPublishedBetweenRange(_FILETIME,_FILETIME,UpdatePublishedHistory *,ulong,int,ushort const *,ulong &)
0x1800074d1  mov     ebx, eax
0x1800074d3  test    eax, eax
0x1800074d5  js      short loc_1800074F6
0x1800074d7  cmp     [rbp+arg_8], r15d
0x1800074db  jbe     short loc_18000750A
0x1800074dd  cmp     [rbp+var_18], r15d
0x1800074e1  jnz     short loc_18000750A
0x1800074e3  lea     rdx, aDeviceIsPaused; "Device is paused and has deferred featu"...
0x1800074ea  lea     ecx, [rdi+3]; unsigned __int8
0x1800074ed  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800074f2  mov     [rsi], edi
0x1800074f4  jmp     short loc_18000750A
0x1800074f6  mov     r8d, ebx
0x1800074f9  lea     rdx, aGetfeatureupda_0; "GetFeatureUpdateAssessmentReasonEx Fail"...
0x180007500  mov     ecx, 2; unsigned __int8
0x180007505  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000750a  mov     eax, ebx
0x18000750c  mov     rbx, [rsp+60h+arg_0]
0x180007514  add     rsp, 60h
0x180007518  pop     r15
0x18000751a  pop     r14
0x18000751c  pop     rdi
0x18000751d  pop     rsi
0x18000751e  pop     rbp
0x18000751f  retn
```

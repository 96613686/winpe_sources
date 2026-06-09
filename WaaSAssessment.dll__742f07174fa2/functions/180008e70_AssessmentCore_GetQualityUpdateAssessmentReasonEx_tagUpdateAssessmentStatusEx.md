# AssessmentCore::GetQualityUpdateAssessmentReasonEx(tagUpdateAssessmentStatusEx *)

- ea: `0x180008e70`
- end: `0x180009012`
- name: `?GetQualityUpdateAssessmentReasonEx@AssessmentCore@@MEAAJPEAW4tagUpdateAssessmentStatusEx@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, enum tagUpdateAssessmentStatusEx *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180008e70`
- `0x18001752c`
- `0x1800184dc`
- `0x180018fe0`
- `0x18001b010`

## string_xrefs

- `0x180008f4c`: `Device has paused quality updates`
- `0x180008feb`: `GetQualityUpdateAssessmentReasonEx Failure: 0x%x`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetQualityUpdateAssessmentReasonEx(
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
  v7 = (*(__int64 (__fastcall **)(char *, int *))(*(_QWORD *)v2 + 64LL))(v2, &v11);
  if ( v7 < 0 )
    goto LABEL_14;
  if ( !v11 )
    return (unsigned int)v7;
  LogLevel(4u, L"Device has paused quality updates");
  v8 = *(_QWORD *)v2;
  v13 = 0;
  v14 = 0;
  v12 = 0;
  (*(void (__fastcall **)(char *, unsigned int *))(v8 + 48))(v2, &v14);
  SubtractDaysFromCurrentTimeUTC(v14, &v13);
  v7 = CountUpdatesPublishedBetweenRange(
         *(FILETIME *)((char *)this + 100),
         v13,
         *((struct UpdatePublishedHistory **)this + 290),
         *((_DWORD *)this + 582),
         0,
         (char *)this + 1256,
         &v12);
  if ( v7 < 0 )
  {
LABEL_14:
    LogLevel(2u, L"GetQualityUpdateAssessmentReasonEx Failure: 0x%x", (unsigned int)v7);
    return (unsigned int)v7;
  }
  if ( v14 && !v12 )
  {
    LogLevel(4u, L"Device has deferral quality set");
    *(_DWORD *)a2 = 1;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008e70  mov     [rsp-28h+arg_0], rbx
0x180008e75  push    rbp
0x180008e76  push    rsi
0x180008e77  push    rdi
0x180008e78  push    r14
0x180008e7a  push    r15
0x180008e7c  mov     rbp, rsp
0x180008e7f  sub     rsp, 60h
0x180008e83  xor     r15d, r15d
0x180008e86  lea     rdi, [rcx+0D0h]
0x180008e8d  mov     [rdx], r15d
0x180008e90  mov     rsi, rdx
0x180008e93  mov     rax, [rdi]
0x180008e96  lea     rdx, [rbp+arg_10]
0x180008e9a  mov     r14, rcx
0x180008e9d  mov     [rbp+arg_10], r15d
0x180008ea1  mov     rcx, rdi
0x180008ea4  mov     [rbp+arg_18], r15d
0x180008ea8  mov     [rbp+var_20], r15d
0x180008eac  mov     rax, [rax+50h]
0x180008eb0  mov     [rbp+var_1C], r15d
0x180008eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eb9  mov     ebx, eax
0x180008ebb  test    eax, eax
0x180008ebd  js      loc_180008FE8
0x180008ec3  mov     rax, [rdi]
0x180008ec6  lea     rdx, [rbp+arg_18]
0x180008eca  mov     rcx, rdi
0x180008ecd  mov     rax, [rax+48h]
0x180008ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ed6  mov     ebx, eax
0x180008ed8  test    eax, eax
0x180008eda  js      loc_180008FE8
0x180008ee0  mov     rax, [rdi]
0x180008ee3  lea     rdx, [rbp+var_20]
0x180008ee7  mov     rcx, rdi
0x180008eea  mov     rax, [rax+58h]
0x180008eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef3  mov     ebx, eax
0x180008ef5  test    eax, eax
0x180008ef7  js      loc_180008FE8
0x180008efd  cmp     [rbp+arg_10], r15d
0x180008f01  jz      short loc_180008F25
0x180008f03  cmp     [rbp+arg_18], r15d
0x180008f07  jz      short loc_180008F0F
0x180008f09  cmp     [rbp+var_20], r15d
0x180008f0d  jz      short loc_180008F25
0x180008f0f  lea     rdx, aDeviceIsManage; "Device is managed only through WSUS."
0x180008f16  mov     ecx, 4; unsigned __int8
0x180008f1b  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008f20  jmp     loc_180008FFC
0x180008f25  mov     rax, [rdi]
0x180008f28  lea     rdx, [rbp+var_1C]
0x180008f2c  mov     rcx, rdi
0x180008f2f  mov     rax, [rax+40h]
0x180008f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f38  mov     ebx, eax
0x180008f3a  test    eax, eax
0x180008f3c  js      loc_180008FE8
0x180008f42  cmp     [rbp+var_1C], r15d
0x180008f46  jz      loc_180008FFC
0x180008f4c  lea     rdx, aDeviceHasPause; "Device has paused quality updates"
0x180008f53  mov     ecx, 4; unsigned __int8
0x180008f58  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008f5d  mov     rax, [rdi]
0x180008f60  lea     rdx, [rbp+arg_8]
0x180008f64  mov     rcx, rdi
0x180008f67  mov     qword ptr [rbp+var_10.dwLowDateTime], r15
0x180008f6b  mov     [rbp+arg_8], r15d
0x180008f6f  mov     [rbp+var_18], r15d
0x180008f73  mov     rax, [rax+30h]
0x180008f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f7c  mov     ecx, [rbp+arg_8]; unsigned int
0x180008f7f  lea     rdx, [rbp+var_10]; struct _FILETIME *
0x180008f83  call    ?SubtractDaysFromCurrentTimeUTC@@YAJKPEAU_FILETIME@@@Z; SubtractDaysFromCurrentTimeUTC(ulong,_FILETIME *)
0x180008f88  mov     r9d, [r14+918h]; unsigned int
0x180008f8f  lea     rcx, [rbp+var_18]
0x180008f93  mov     r8, [r14+910h]; struct UpdatePublishedHistory *
0x180008f9a  lea     rax, [r14+4E8h]
0x180008fa1  mov     rdx, qword ptr [rbp+var_10.dwLowDateTime]; struct _FILETIME
0x180008fa5  mov     [rsp+60h+var_30], rcx; unsigned int *
0x180008faa  mov     rcx, [r14+64h]; struct _FILETIME
0x180008fae  mov     [rsp+60h+var_38], rax; unsigned __int16 *
0x180008fb3  mov     [rsp+60h+var_40], r15d; int
0x180008fb8  call    ?CountUpdatesPublishedBetweenRange@@YAJU_FILETIME@@0PEAUUpdatePublishedHistory@@KHPEBGAEAK@Z; CountUpdatesPublishedBetweenRange(_FILETIME,_FILETIME,UpdatePublishedHistory *,ulong,int,ushort const *,ulong &)
0x180008fbd  mov     ebx, eax
0x180008fbf  test    eax, eax
0x180008fc1  js      short loc_180008FE8
0x180008fc3  cmp     [rbp+arg_8], r15d
0x180008fc7  jbe     short loc_180008FFC
0x180008fc9  cmp     [rbp+var_18], r15d
0x180008fcd  jnz     short loc_180008FFC
0x180008fcf  lea     rdx, aDeviceHasDefer_0; "Device has deferral quality set"
0x180008fd6  mov     ecx, 4; unsigned __int8
0x180008fdb  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008fe0  mov     dword ptr [rsi], 1
0x180008fe6  jmp     short loc_180008FFC
0x180008fe8  mov     r8d, ebx
0x180008feb  lea     rdx, aGetqualityupda_1; "GetQualityUpdateAssessmentReasonEx Fail"...
0x180008ff2  mov     ecx, 2; unsigned __int8
0x180008ff7  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180008ffc  mov     eax, ebx
0x180008ffe  mov     rbx, [rsp+60h+arg_0]
0x180009006  add     rsp, 60h
0x18000900a  pop     r15
0x18000900c  pop     r14
0x18000900e  pop     rdi
0x18000900f  pop     rsi
0x180009010  pop     rbp
0x180009011  retn
```

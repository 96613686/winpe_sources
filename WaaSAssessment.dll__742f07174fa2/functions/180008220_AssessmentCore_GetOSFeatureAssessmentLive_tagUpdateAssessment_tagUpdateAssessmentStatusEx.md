# AssessmentCore::GetOSFeatureAssessmentLive(tagUpdateAssessment *,tagUpdateAssessmentStatusEx *)

- ea: `0x180008220`
- end: `0x180008307`
- name: `?GetOSFeatureAssessmentLive@AssessmentCore@@UEAAJPEAUtagUpdateAssessment@@PEAW4tagUpdateAssessmentStatusEx@@@Z`
- size: `231`
- prototype: `int(AssessmentCore *__hidden this, struct tagUpdateAssessment *, enum tagUpdateAssessmentStatusEx *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180008220`
- `0x1800180e8`
- `0x180018130`
- `0x180018430`
- `0x180019760`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetOSFeatureAssessmentLive(
        AssessmentCore *this,
        struct tagUpdateAssessment *a2,
        enum tagUpdateAssessmentStatusEx *a3)
{
  int v6; // ebx
  _BYTE v8[192]; // [rsp+30h] [rbp-E8h] BYREF

  *(_DWORD *)a3 = 0;
  AssessmentEvent::AssessmentEvent((__int64)v8, 2, *((_WORD **)this + 24), *((char **)this + 25));
  v6 = (*(__int64 (__fastcall **)(AssessmentCore *, struct tagUpdateAssessment *, _QWORD, _QWORD, int))(*(_QWORD *)this + 136LL))(
         this,
         a2,
         0,
         0,
         1);
  if ( v6 >= 0 )
  {
    if ( a2->status )
      v6 = (*(__int64 (__fastcall **)(AssessmentCore *, enum tagUpdateAssessmentStatusEx *))(*(_QWORD *)this + 256LL))(
             this,
             a3);
    else
      *(_DWORD *)a3 = 0;
  }
  AssessmentEvent::SetAssessmentEventData((AssessmentEvent *)v8, v6, 0, 1, a2);
  AssessmentEvent::~AssessmentEvent((AssessmentEvent *)v8);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180008220  mov     [rsp+arg_18], rbx
0x180008225  push    rsi
0x180008226  push    rdi
0x180008227  push    r14
0x180008229  sub     rsp, 100h
0x180008230  mov     rax, cs:__security_cookie
0x180008237  xor     rax, rsp
0x18000823a  mov     [rsp+118h+var_28], rax
0x180008242  mov     dword ptr [r8], 0
0x180008249  mov     r14, r8
0x18000824c  mov     r9, [rcx+0C8h]
0x180008253  mov     rsi, rdx
0x180008256  mov     r8, [rcx+0C0h]
0x18000825d  mov     rdi, rcx
0x180008260  lea     rcx, [rsp+118h+var_E8]
0x180008265  mov     edx, 2
0x18000826a  call    ??0AssessmentEvent@@QEAA@W4tagUpdateAssessmentType@@PEBGPEBD@Z; AssessmentEvent::AssessmentEvent(tagUpdateAssessmentType,ushort const *,char const *)
0x18000826f  mov     rax, [rdi]
0x180008272  xor     r9d, r9d
0x180008275  xor     r8d, r8d
0x180008278  mov     dword ptr [rsp+118h+var_F8], 1
0x180008280  mov     rdx, rsi
0x180008283  mov     rcx, rdi
0x180008286  mov     rax, [rax+88h]
0x18000828d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008292  mov     ebx, eax
0x180008294  test    eax, eax
0x180008296  js      short loc_1800082BD
0x180008298  cmp     dword ptr [rsi], 0
0x18000829b  jz      short loc_1800082B6
0x18000829d  mov     rax, [rdi]
0x1800082a0  mov     rdx, r14
0x1800082a3  mov     rcx, rdi
0x1800082a6  mov     rax, [rax+100h]
0x1800082ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082b2  mov     ebx, eax
0x1800082b4  jmp     short loc_1800082BD
0x1800082b6  mov     dword ptr [r14], 0
0x1800082bd  mov     r9d, 1; int
0x1800082c3  mov     [rsp+118h+var_F8], rsi; struct tagUpdateAssessment *
0x1800082c8  xor     r8d, r8d; int
0x1800082cb  lea     rcx, [rsp+118h+var_E8]; this
0x1800082d0  mov     edx, ebx; int
0x1800082d2  call    ?SetAssessmentEventData@AssessmentEvent@@QEAAXJHHPEAUtagUpdateAssessment@@@Z; AssessmentEvent::SetAssessmentEventData(long,int,int,tagUpdateAssessment *)
0x1800082d7  lea     rcx, [rsp+118h+var_E8]; this
0x1800082dc  call    ??1AssessmentEvent@@QEAA@XZ; AssessmentEvent::~AssessmentEvent(void)
0x1800082e1  mov     eax, ebx
0x1800082e3  mov     rcx, [rsp+118h+var_28]
0x1800082eb  xor     rcx, rsp; StackCookie
0x1800082ee  call    __security_check_cookie
0x1800082f3  mov     rbx, [rsp+118h+arg_18]
0x1800082fb  add     rsp, 100h
0x180008302  pop     r14
0x180008304  pop     rdi
0x180008305  pop     rsi
0x180008306  retn
```

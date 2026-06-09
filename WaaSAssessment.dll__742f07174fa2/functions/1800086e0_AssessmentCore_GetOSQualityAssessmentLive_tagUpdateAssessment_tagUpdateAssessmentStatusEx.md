# AssessmentCore::GetOSQualityAssessmentLive(tagUpdateAssessment *,tagUpdateAssessmentStatusEx *)

- ea: `0x1800086e0`
- end: `0x1800087c7`
- name: `?GetOSQualityAssessmentLive@AssessmentCore@@UEAAJPEAUtagUpdateAssessment@@PEAW4tagUpdateAssessmentStatusEx@@@Z`
- size: `231`
- prototype: `int(AssessmentCore *__hidden this, struct tagUpdateAssessment *, enum tagUpdateAssessmentStatusEx *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800086e0`
- `0x1800180e8`
- `0x180018130`
- `0x180018430`
- `0x180019760`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetOSQualityAssessmentLive(
        AssessmentCore *this,
        struct tagUpdateAssessment *a2,
        enum tagUpdateAssessmentStatusEx *a3)
{
  int v6; // ebx
  _BYTE v8[192]; // [rsp+30h] [rbp-E8h] BYREF

  *(_DWORD *)a3 = 0;
  AssessmentEvent::AssessmentEvent((__int64)v8, 3, *((_WORD **)this + 24), *((char **)this + 25));
  v6 = (*(__int64 (__fastcall **)(AssessmentCore *, struct tagUpdateAssessment *, _QWORD, _QWORD, int))(*(_QWORD *)this + 144LL))(
         this,
         a2,
         0,
         0,
         1);
  if ( v6 >= 0 )
  {
    if ( a2->status )
      v6 = (*(__int64 (__fastcall **)(AssessmentCore *, enum tagUpdateAssessmentStatusEx *))(*(_QWORD *)this + 240LL))(
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
0x1800086e0  mov     [rsp+arg_18], rbx
0x1800086e5  push    rsi
0x1800086e6  push    rdi
0x1800086e7  push    r14
0x1800086e9  sub     rsp, 100h
0x1800086f0  mov     rax, cs:__security_cookie
0x1800086f7  xor     rax, rsp
0x1800086fa  mov     [rsp+118h+var_28], rax
0x180008702  mov     dword ptr [r8], 0
0x180008709  mov     r14, r8
0x18000870c  mov     r9, [rcx+0C8h]
0x180008713  mov     rsi, rdx
0x180008716  mov     r8, [rcx+0C0h]
0x18000871d  mov     rdi, rcx
0x180008720  lea     rcx, [rsp+118h+var_E8]
0x180008725  mov     edx, 3
0x18000872a  call    ??0AssessmentEvent@@QEAA@W4tagUpdateAssessmentType@@PEBGPEBD@Z; AssessmentEvent::AssessmentEvent(tagUpdateAssessmentType,ushort const *,char const *)
0x18000872f  mov     rax, [rdi]
0x180008732  xor     r9d, r9d
0x180008735  xor     r8d, r8d
0x180008738  mov     dword ptr [rsp+118h+var_F8], 1
0x180008740  mov     rdx, rsi
0x180008743  mov     rcx, rdi
0x180008746  mov     rax, [rax+90h]
0x18000874d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008752  mov     ebx, eax
0x180008754  test    eax, eax
0x180008756  js      short loc_18000877D
0x180008758  cmp     dword ptr [rsi], 0
0x18000875b  jz      short loc_180008776
0x18000875d  mov     rax, [rdi]
0x180008760  mov     rdx, r14
0x180008763  mov     rcx, rdi
0x180008766  mov     rax, [rax+0F0h]
0x18000876d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008772  mov     ebx, eax
0x180008774  jmp     short loc_18000877D
0x180008776  mov     dword ptr [r14], 0
0x18000877d  mov     r9d, 1; int
0x180008783  mov     [rsp+118h+var_F8], rsi; struct tagUpdateAssessment *
0x180008788  xor     r8d, r8d; int
0x18000878b  lea     rcx, [rsp+118h+var_E8]; this
0x180008790  mov     edx, ebx; int
0x180008792  call    ?SetAssessmentEventData@AssessmentEvent@@QEAAXJHHPEAUtagUpdateAssessment@@@Z; AssessmentEvent::SetAssessmentEventData(long,int,int,tagUpdateAssessment *)
0x180008797  lea     rcx, [rsp+118h+var_E8]; this
0x18000879c  call    ??1AssessmentEvent@@QEAA@XZ; AssessmentEvent::~AssessmentEvent(void)
0x1800087a1  mov     eax, ebx
0x1800087a3  mov     rcx, [rsp+118h+var_28]
0x1800087ab  xor     rcx, rsp; StackCookie
0x1800087ae  call    __security_check_cookie
0x1800087b3  mov     rbx, [rsp+118h+arg_18]
0x1800087bb  add     rsp, 100h
0x1800087c2  pop     r14
0x1800087c4  pop     rdi
0x1800087c5  pop     rsi
0x1800087c6  retn
```

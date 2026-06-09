# AssessmentCore::GetOSQualityAssessment(tagUpdateAssessment *,int)

- ea: `0x180008310`
- end: `0x1800083b6`
- name: `?GetOSQualityAssessment@AssessmentCore@@UEAAJPEAUtagUpdateAssessment@@H@Z`
- size: `166`
- prototype: `int(AssessmentCore *__hidden this, struct tagUpdateAssessment *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800180e8`
- `0x180018130`
- `0x180018430`
- `0x180019760`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetOSQualityAssessment(char **this, struct tagUpdateAssessment *a2, unsigned int a3)
{
  AssessmentCore *v5; // rbx
  _BYTE v7[192]; // [rsp+30h] [rbp-E8h] BYREF

  v5 = (AssessmentCore *)this;
  AssessmentEvent::AssessmentEvent((__int64)v7, 3, this[24], this[25]);
  LODWORD(v5) = (*(__int64 (__fastcall **)(AssessmentCore *, struct tagUpdateAssessment *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v5 + 144LL))(
                  v5,
                  a2,
                  0,
                  a3,
                  0);
  AssessmentEvent::SetAssessmentEventData((AssessmentEvent *)v7, (int)v5, a3, 0, a2);
  AssessmentEvent::~AssessmentEvent((AssessmentEvent *)v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008310  push    rbx
0x180008312  push    rsi
0x180008313  push    rdi
0x180008314  sub     rsp, 100h
0x18000831b  mov     rax, cs:__security_cookie
0x180008322  xor     rax, rsp
0x180008325  mov     [rsp+118h+var_28], rax
0x18000832d  mov     r9, [rcx+0C8h]
0x180008334  mov     esi, r8d
0x180008337  mov     r8, [rcx+0C0h]
0x18000833e  mov     rdi, rdx
0x180008341  mov     rbx, rcx
0x180008344  mov     edx, 3
0x180008349  lea     rcx, [rsp+118h+var_E8]
0x18000834e  call    ??0AssessmentEvent@@QEAA@W4tagUpdateAssessmentType@@PEBGPEBD@Z; AssessmentEvent::AssessmentEvent(tagUpdateAssessmentType,ushort const *,char const *)
0x180008353  mov     rax, [rbx]
0x180008356  mov     r9d, esi
0x180008359  xor     r8d, r8d
0x18000835c  mov     dword ptr [rsp+118h+var_F8], 0
0x180008364  mov     rdx, rdi
0x180008367  mov     rcx, rbx
0x18000836a  mov     rax, [rax+90h]
0x180008371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008376  xor     r9d, r9d; int
0x180008379  mov     [rsp+118h+var_F8], rdi; struct tagUpdateAssessment *
0x18000837e  mov     r8d, esi; int
0x180008381  lea     rcx, [rsp+118h+var_E8]; this
0x180008386  mov     edx, eax; int
0x180008388  mov     ebx, eax
0x18000838a  call    ?SetAssessmentEventData@AssessmentEvent@@QEAAXJHHPEAUtagUpdateAssessment@@@Z; AssessmentEvent::SetAssessmentEventData(long,int,int,tagUpdateAssessment *)
0x18000838f  lea     rcx, [rsp+118h+var_E8]; this
0x180008394  call    ??1AssessmentEvent@@QEAA@XZ; AssessmentEvent::~AssessmentEvent(void)
0x180008399  mov     eax, ebx
0x18000839b  mov     rcx, [rsp+118h+var_28]
0x1800083a3  xor     rcx, rsp; StackCookie
0x1800083a6  call    __security_check_cookie
0x1800083ab  add     rsp, 100h
0x1800083b2  pop     rdi
0x1800083b3  pop     rsi
0x1800083b4  pop     rbx
0x1800083b5  retn
```

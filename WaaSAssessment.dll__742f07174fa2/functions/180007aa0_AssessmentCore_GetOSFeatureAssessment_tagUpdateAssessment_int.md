# AssessmentCore::GetOSFeatureAssessment(tagUpdateAssessment *,int)

- ea: `0x180007aa0`
- end: `0x180007b46`
- name: `?GetOSFeatureAssessment@AssessmentCore@@UEAAJPEAUtagUpdateAssessment@@H@Z`
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
__int64 __fastcall AssessmentCore::GetOSFeatureAssessment(char **this, struct tagUpdateAssessment *a2, unsigned int a3)
{
  AssessmentCore *v5; // rbx
  _BYTE v7[192]; // [rsp+30h] [rbp-E8h] BYREF

  v5 = (AssessmentCore *)this;
  AssessmentEvent::AssessmentEvent((__int64)v7, 2, this[24], this[25]);
  LODWORD(v5) = (*(__int64 (__fastcall **)(AssessmentCore *, struct tagUpdateAssessment *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v5 + 136LL))(
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
0x180007aa0  push    rbx
0x180007aa2  push    rsi
0x180007aa3  push    rdi
0x180007aa4  sub     rsp, 100h
0x180007aab  mov     rax, cs:__security_cookie
0x180007ab2  xor     rax, rsp
0x180007ab5  mov     [rsp+118h+var_28], rax
0x180007abd  mov     r9, [rcx+0C8h]
0x180007ac4  mov     esi, r8d
0x180007ac7  mov     r8, [rcx+0C0h]
0x180007ace  mov     rdi, rdx
0x180007ad1  mov     rbx, rcx
0x180007ad4  mov     edx, 2
0x180007ad9  lea     rcx, [rsp+118h+var_E8]
0x180007ade  call    ??0AssessmentEvent@@QEAA@W4tagUpdateAssessmentType@@PEBGPEBD@Z; AssessmentEvent::AssessmentEvent(tagUpdateAssessmentType,ushort const *,char const *)
0x180007ae3  mov     rax, [rbx]
0x180007ae6  mov     r9d, esi
0x180007ae9  xor     r8d, r8d
0x180007aec  mov     dword ptr [rsp+118h+var_F8], 0
0x180007af4  mov     rdx, rdi
0x180007af7  mov     rcx, rbx
0x180007afa  mov     rax, [rax+88h]
0x180007b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b06  xor     r9d, r9d; int
0x180007b09  mov     [rsp+118h+var_F8], rdi; struct tagUpdateAssessment *
0x180007b0e  mov     r8d, esi; int
0x180007b11  lea     rcx, [rsp+118h+var_E8]; this
0x180007b16  mov     edx, eax; int
0x180007b18  mov     ebx, eax
0x180007b1a  call    ?SetAssessmentEventData@AssessmentEvent@@QEAAXJHHPEAUtagUpdateAssessment@@@Z; AssessmentEvent::SetAssessmentEventData(long,int,int,tagUpdateAssessment *)
0x180007b1f  lea     rcx, [rsp+118h+var_E8]; this
0x180007b24  call    ??1AssessmentEvent@@QEAA@XZ; AssessmentEvent::~AssessmentEvent(void)
0x180007b29  mov     eax, ebx
0x180007b2b  mov     rcx, [rsp+118h+var_28]
0x180007b33  xor     rcx, rsp; StackCookie
0x180007b36  call    __security_check_cookie
0x180007b3b  add     rsp, 100h
0x180007b42  pop     rdi
0x180007b43  pop     rsi
0x180007b44  pop     rbx
0x180007b45  retn
```

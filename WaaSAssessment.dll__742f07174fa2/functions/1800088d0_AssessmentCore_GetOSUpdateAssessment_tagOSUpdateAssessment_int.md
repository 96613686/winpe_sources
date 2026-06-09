# AssessmentCore::GetOSUpdateAssessment(tagOSUpdateAssessment *,int)

- ea: `0x1800088d0`
- end: `0x1800089c3`
- name: `?GetOSUpdateAssessment@AssessmentCore@@UEAAJPEAUtagOSUpdateAssessment@@H@Z`
- size: `243`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, struct tagOSUpdateAssessment *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800088d0`
- `0x1800176a4`
- `0x180018130`
- `0x180018234`
- `0x180019760`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetOSUpdateAssessment(
        AssessmentCore *this,
        struct tagOSUpdateAssessment *a2,
        int a3)
{
  int v6; // eax
  unsigned int v7; // edi
  UpdateImpactLevel impact; // ecx
  int v10; // [rsp+30h] [rbp-89h] BYREF
  int v11; // [rsp+34h] [rbp-85h]
  char v12[136]; // [rsp+38h] [rbp-81h] BYREF
  unsigned __int16 *v13; // [rsp+C0h] [rbp+7h]
  int v14; // [rsp+C8h] [rbp+Fh]
  int v15; // [rsp+D0h] [rbp+17h]
  UpdateImpactLevel v16; // [rsp+E0h] [rbp+27h]
  UpdateAssessmentStatus status; // [rsp+E4h] [rbp+2Bh]
  UpdateImpactLevel v18; // [rsp+E8h] [rbp+2Fh]
  UpdateAssessmentStatus v19; // [rsp+ECh] [rbp+33h]

  if ( (int)AssessmentEvent::InitializeInternal((__int64)&v10, 0, *((_WORD **)this + 24), *((char **)this + 25)) < 0 )
  {
    v10 = 0;
  }
  else
  {
    v10 = 1;
    LogOSAssessmentStart(v12, v13);
  }
  v6 = (*(__int64 (__fastcall **)(AssessmentCore *, struct tagOSUpdateAssessment *, _QWORD, _QWORD, int))(*(_QWORD *)this + 128LL))(
         this,
         a2,
         0,
         0,
         a3);
  v14 = v6;
  v7 = v6;
  v15 = a3;
  if ( !a2 || v6 < 0 || v6 == 1 )
  {
    v11 = 0;
  }
  else
  {
    impact = a2->assessmentForCurrent.impact;
    status = a2->assessmentForCurrent.status;
    v18 = a2->assessmentForUpToDate.impact;
    v19 = a2->assessmentForUpToDate.status;
    v11 = 1;
    v16 = impact;
  }
  AssessmentEvent::~AssessmentEvent((AssessmentEvent *)&v10);
  return v7;
}

```

## disassembly

```asm
0x1800088d0  mov     [rsp-8+arg_18], rbx
0x1800088d5  push    rbp
0x1800088d6  push    rsi
0x1800088d7  push    rdi
0x1800088d8  lea     rbp, [rsp-47h]
0x1800088dd  sub     rsp, 100h
0x1800088e4  mov     rax, cs:__security_cookie
0x1800088eb  xor     rax, rsp
0x1800088ee  mov     [rbp+57h+var_20], rax
0x1800088f2  mov     r9, [rcx+0C8h]
0x1800088f9  mov     esi, r8d
0x1800088fc  mov     r8, [rcx+0C0h]
0x180008903  mov     rbx, rdx
0x180008906  mov     rdi, rcx
0x180008909  xor     edx, edx
0x18000890b  lea     rcx, [rsp+110h+var_E0]
0x180008910  call    ?InitializeInternal@AssessmentEvent@@AEAAJW4tagUpdateAssessmentType@@PEBGPEBD@Z; AssessmentEvent::InitializeInternal(tagUpdateAssessmentType,ushort const *,char const *)
0x180008915  test    eax, eax
0x180008917  js      short loc_180008931
0x180008919  mov     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x18000891d  lea     rcx, [rsp+110h+var_D8]; char *
0x180008922  mov     [rsp+110h+var_E0], 1
0x18000892a  call    ?LogOSAssessmentStart@@YAXPEBDPEBG@Z; LogOSAssessmentStart(char const *,ushort const *)
0x18000892f  jmp     short loc_180008939
0x180008931  mov     [rsp+110h+var_E0], 0
0x180008939  mov     rax, [rdi]
0x18000893c  xor     r9d, r9d
0x18000893f  xor     r8d, r8d
0x180008942  mov     [rsp+110h+var_F0], esi
0x180008946  mov     rdx, rbx
0x180008949  mov     rcx, rdi
0x18000894c  mov     rax, [rax+80h]
0x180008953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008958  mov     [rbp+57h+var_48], eax
0x18000895b  mov     edi, eax
0x18000895d  mov     [rbp+57h+var_40], esi
0x180008960  test    rbx, rbx
0x180008963  jz      short loc_180008990
0x180008965  test    eax, eax
0x180008967  js      short loc_180008990
0x180008969  cmp     eax, 1
0x18000896c  jz      short loc_180008990
0x18000896e  mov     eax, [rbx+4]
0x180008971  mov     ecx, [rbx+8]
0x180008974  mov     [rbp+57h+var_2C], eax
0x180008977  mov     eax, [rbx+14h]
0x18000897a  mov     [rbp+57h+var_28], eax
0x18000897d  mov     eax, [rbx+10h]
0x180008980  mov     [rbp+57h+var_24], eax
0x180008983  mov     [rsp+110h+var_DC], 1
0x18000898b  mov     [rbp+57h+var_30], ecx
0x18000898e  jmp     short loc_180008998
0x180008990  mov     [rsp+110h+var_DC], 0
0x180008998  lea     rcx, [rsp+110h+var_E0]; this
0x18000899d  call    ??1AssessmentEvent@@QEAA@XZ; AssessmentEvent::~AssessmentEvent(void)
0x1800089a2  mov     eax, edi
0x1800089a4  mov     rcx, [rbp+57h+var_20]
0x1800089a8  xor     rcx, rsp; StackCookie
0x1800089ab  call    __security_check_cookie
0x1800089b0  mov     rbx, [rsp+110h+arg_18]
0x1800089b8  add     rsp, 100h
0x1800089bf  pop     rdi
0x1800089c0  pop     rsi
0x1800089c1  pop     rbp
0x1800089c2  retn
```

# AssessmentCore::GetOSUpdateAssessment(tagOSUpdateAssessment *)

- ea: `0x1800087d0`
- end: `0x1800088c6`
- name: `?GetOSUpdateAssessment@AssessmentCore@@UEAAJPEAUtagOSUpdateAssessment@@@Z`
- size: `246`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, struct tagOSUpdateAssessment *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x1800087d0`
- `0x1800176a4`
- `0x180018130`
- `0x180018234`
- `0x180019760`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall AssessmentCore::GetOSUpdateAssessment(AssessmentCore *this, struct tagOSUpdateAssessment *a2)
{
  int v4; // eax
  unsigned int v5; // edi
  UpdateImpactLevel impact; // ecx
  int v8; // [rsp+30h] [rbp-79h] BYREF
  int v9; // [rsp+34h] [rbp-75h]
  char v10[136]; // [rsp+38h] [rbp-71h] BYREF
  unsigned __int16 *v11; // [rsp+C0h] [rbp+17h]
  int v12; // [rsp+C8h] [rbp+1Fh]
  int v13; // [rsp+D0h] [rbp+27h]
  UpdateImpactLevel v14; // [rsp+E0h] [rbp+37h]
  UpdateAssessmentStatus status; // [rsp+E4h] [rbp+3Bh]
  UpdateImpactLevel v16; // [rsp+E8h] [rbp+3Fh]
  UpdateAssessmentStatus v17; // [rsp+ECh] [rbp+43h]

  if ( (int)AssessmentEvent::InitializeInternal((__int64)&v8, 0, *((_WORD **)this + 24), *((char **)this + 25)) < 0 )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    LogOSAssessmentStart(v10, v11);
  }
  v4 = (*(__int64 (__fastcall **)(AssessmentCore *, struct tagOSUpdateAssessment *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)this + 128LL))(
         this,
         a2,
         0,
         0,
         0);
  v12 = v4;
  v5 = v4;
  v13 = 0;
  if ( !a2 || v4 < 0 || v4 == 1 )
  {
    v9 = 0;
  }
  else
  {
    impact = a2->assessmentForCurrent.impact;
    status = a2->assessmentForCurrent.status;
    v16 = a2->assessmentForUpToDate.impact;
    v17 = a2->assessmentForUpToDate.status;
    v9 = 1;
    v14 = impact;
  }
  AssessmentEvent::~AssessmentEvent((AssessmentEvent *)&v8);
  return v5;
}

```

## disassembly

```asm
0x1800087d0  mov     [rsp-8+arg_10], rbx
0x1800087d5  mov     [rsp-8+arg_18], rdi
0x1800087da  push    rbp
0x1800087db  lea     rbp, [rsp-57h]
0x1800087e0  sub     rsp, 100h
0x1800087e7  mov     rax, cs:__security_cookie
0x1800087ee  xor     rax, rsp
0x1800087f1  mov     [rbp+57h+var_10], rax
0x1800087f5  mov     r9, [rcx+0C8h]
0x1800087fc  mov     rbx, rdx
0x1800087ff  mov     r8, [rcx+0C0h]
0x180008806  mov     rdi, rcx
0x180008809  xor     edx, edx
0x18000880b  lea     rcx, [rbp+57h+var_D0]
0x18000880f  call    ?InitializeInternal@AssessmentEvent@@AEAAJW4tagUpdateAssessmentType@@PEBGPEBD@Z; AssessmentEvent::InitializeInternal(tagUpdateAssessmentType,ushort const *,char const *)
0x180008814  test    eax, eax
0x180008816  js      short loc_18000882E
0x180008818  mov     rdx, [rbp+57h+var_40]; unsigned __int16 *
0x18000881c  lea     rcx, [rbp+57h+var_C8]; char *
0x180008820  mov     [rbp+57h+var_D0], 1
0x180008827  call    ?LogOSAssessmentStart@@YAXPEBDPEBG@Z; LogOSAssessmentStart(char const *,ushort const *)
0x18000882c  jmp     short loc_180008835
0x18000882e  mov     [rbp+57h+var_D0], 0
0x180008835  mov     rax, [rdi]
0x180008838  xor     r9d, r9d
0x18000883b  xor     r8d, r8d
0x18000883e  mov     [rsp+100h+var_E0], 0
0x180008846  mov     rdx, rbx
0x180008849  mov     rcx, rdi
0x18000884c  mov     rax, [rax+80h]
0x180008853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008858  mov     [rbp+57h+var_38], eax
0x18000885b  mov     edi, eax
0x18000885d  mov     [rbp+57h+var_30], 0
0x180008864  test    rbx, rbx
0x180008867  jz      short loc_180008893
0x180008869  test    eax, eax
0x18000886b  js      short loc_180008893
0x18000886d  cmp     eax, 1
0x180008870  jz      short loc_180008893
0x180008872  mov     eax, [rbx+4]
0x180008875  mov     ecx, [rbx+8]
0x180008878  mov     [rbp+57h+var_1C], eax
0x18000887b  mov     eax, [rbx+14h]
0x18000887e  mov     [rbp+57h+var_18], eax
0x180008881  mov     eax, [rbx+10h]
0x180008884  mov     [rbp+57h+var_14], eax
0x180008887  mov     [rbp+57h+var_CC], 1
0x18000888e  mov     [rbp+57h+var_20], ecx
0x180008891  jmp     short loc_18000889A
0x180008893  mov     [rbp+57h+var_CC], 0
0x18000889a  lea     rcx, [rbp+57h+var_D0]; this
0x18000889e  call    ??1AssessmentEvent@@QEAA@XZ; AssessmentEvent::~AssessmentEvent(void)
0x1800088a3  mov     eax, edi
0x1800088a5  mov     rcx, [rbp+57h+var_10]
0x1800088a9  xor     rcx, rsp; StackCookie
0x1800088ac  call    __security_check_cookie
0x1800088b1  lea     r11, [rsp+100h+var_s0]
0x1800088b9  mov     rbx, [r11+20h]
0x1800088bd  mov     rdi, [r11+28h]
0x1800088c1  mov     rsp, r11
0x1800088c4  pop     rbp
0x1800088c5  retn
```

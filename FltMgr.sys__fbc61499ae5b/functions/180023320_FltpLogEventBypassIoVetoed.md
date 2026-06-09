# FltpLogEventBypassIoVetoed

- ea: `0x180023320`
- end: `0x1800236c0`
- name: `FltpLogEventBypassIoVetoed`
- size: `928`
- prototype: `__int64 __fastcall(int, int, int, int, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800537e0`

## callees

- `0x180001e1c`
- `0x180009f20`
- `0x1800161f0`
- `0x18001eae0`
- `0x180020970`
- `0x180022e0c`
- `0x180023320`
- `0x180023a44`
- `0x180024800`
- `0x18004db20`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180023669`
- `ntoskrnl!ExFreePoolWithTag` at `0x180023669`
- `ntoskrnl!ObfDereferenceObject` at `0x180023689`
- `ntoskrnl!ObfDereferenceObject` at `0x180023689`
- `ntoskrnl!IoGetStackLimits` at `0x1800234ed`
- `ntoskrnl!IoGetStackLimits` at `0x1800234ed`
- `ntoskrnl!PsGetProcessImageFileName` at `0x180023427`
- `ntoskrnl!PsGetProcessImageFileName` at `0x180023427`
- `ntoskrnl!RtlSystemTimeToLocalTime` at `0x1800233e9`
- `ntoskrnl!RtlSystemTimeToLocalTime` at `0x1800233e9`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1800233fc`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x1800233fc`
- `ntoskrnl!RtlSecondsSince1970ToTime` at `0x1800233d4`
- `ntoskrnl!RtlSecondsSince1970ToTime` at `0x1800233d4`

## pseudocode

```c
void __fastcall FltpLogEventBypassIoVetoed(__int64 a1, __int64 a2, ULONG a3, int a4, PCUNICODE_STRING SourceString)
{
  const UNICODE_STRING *v5; // r14
  __int16 *ProcessImageFileName; // rbx
  wchar_t *Buffer; // rcx
  unsigned int DriverVersion; // eax
  unsigned int v13; // eax
  __int64 v14; // r8
  int v15; // edx
  int v16; // ecx
  int v17; // r8d
  int v18; // edi
  int v19; // esi
  int v20; // r9d
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // r8
  char v24[4]; // [rsp+60h] [rbp-A0h] BYREF
  ULONG ElapsedSeconds; // [rsp+64h] [rbp-9Ch] BYREF
  int v26; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int64 LowLimit; // [rsp+70h] [rbp-90h] BYREF
  LARGE_INTEGER LocalTime; // [rsp+78h] [rbp-88h] BYREF
  PEPROCESS Process; // [rsp+80h] [rbp-80h] BYREF
  PVOID P[2]; // [rsp+88h] [rbp-78h] BYREF
  LARGE_INTEGER Time; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 HighLimit; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v34; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+E8h] [rbp-18h]
  wchar_t **p_Buffer; // [rsp+F0h] [rbp-10h]
  __int64 v40; // [rsp+F8h] [rbp-8h]
  char v41[16]; // [rsp+100h] [rbp+0h] BYREF
  int *v42; // [rsp+110h] [rbp+10h]
  __int64 v43; // [rsp+118h] [rbp+18h]
  int *v44; // [rsp+120h] [rbp+20h]
  __int64 v45; // [rsp+128h] [rbp+28h]
  LARGE_INTEGER *p_LocalTime; // [rsp+130h] [rbp+30h]
  __int64 v47; // [rsp+138h] [rbp+38h]
  __int16 *v48; // [rsp+140h] [rbp+40h]
  int v49; // [rsp+148h] [rbp+48h]
  int v50; // [rsp+14Ch] [rbp+4Ch]
  ULONG *p_ElapsedSeconds; // [rsp+150h] [rbp+50h]
  __int64 v52; // [rsp+158h] [rbp+58h]
  unsigned __int64 *p_LowLimit; // [rsp+160h] [rbp+60h]
  __int64 v54; // [rsp+168h] [rbp+68h]
  char v55[16]; // [rsp+170h] [rbp+70h] BYREF
  __int64 *v56; // [rsp+180h] [rbp+80h]
  __int64 v57; // [rsp+188h] [rbp+88h]
  wchar_t pszDest[32]; // [rsp+190h] [rbp+90h] BYREF
  wchar_t v59[128]; // [rsp+1D0h] [rbp+D0h] BYREF

  v5 = *(const UNICODE_STRING **)(a2 + 8);
  ProcessImageFileName = &word_18002CAAA;
  Time.QuadPart = 0;
  LocalTime.QuadPart = 0;
  Process = 0;
  v26 = 0;
  v27 = 0;
  *(_OWORD *)P = 0;
  Buffer = v5[6].Buffer;
  ElapsedSeconds = 0;
  v24[0] = 0;
  DriverVersion = FltpGetDriverVersion(
                    (_DWORD)Buffer,
                    (unsigned int)&v26,
                    (unsigned int)&v27,
                    (unsigned int)&ElapsedSeconds,
                    0);
  if ( (int)FltpDbgStatus(DriverVersion, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 2733, 0) >= 0 )
  {
    RtlSecondsSince1970ToTime(ElapsedSeconds, &Time);
    RtlSystemTimeToLocalTime(&Time, &LocalTime);
  }
  v13 = PsLookupProcessByProcessId((HANDLE)*(unsigned int *)(a1 - 4), &Process);
  if ( (int)FltpDbgStatus(v13, "minkernel\\fs\\filtermgr\\filter\\telemetrysup.c", 2747, 0) >= 0 )
    ProcessImageFileName = (__int16 *)PsGetProcessImageFileName(Process);
  FltpBuildPathNameForEventLog(a1, a2, v14, P, v24);
  RtlStringCbCopyUnicodeString(pszDest, 0x40u, v5 + 4);
  RtlStringCbCopyUnicodeString(v59, 0x100u, SourceString);
  v18 = v26;
  v19 = v27;
  if ( (Microsoft_Windows_FilterManagerEnableBits & 4) != 0 )
    McTemplateK0zqqmszqzd_EtwWriteTransfer(
      v16,
      v15,
      v17,
      (unsigned int)pszDest,
      v26,
      v27,
      (__int64)&LocalTime,
      (__int64)ProcessImageFileName,
      (__int64)P[1],
      a3,
      (__int64)v59,
      a4);
  if ( (unsigned int)dword_18003E018 > 5 )
  {
    HighLimit = 0;
    LowLimit = 0;
    IoGetStackLimits(&LowLimit, &HighLimit);
    if ( (unsigned __int64)&HighLimit - LowLimit >= 0x200 )
    {
      if ( (unsigned int)dword_18003E018 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18003E018, 0x400000000000LL) )
      {
        v38 = 8;
        v37 = &v34;
        v40 = 16;
        p_Buffer = &v5[2].Buffer;
        v34 = 1;
        tlgCreate1Sz_wchar_t(v41, pszDest);
        v27 = v18;
        v42 = &v27;
        v44 = &v26;
        p_LocalTime = &LocalTime;
        v43 = 4;
        v26 = v19;
        v45 = 4;
        v47 = 8;
        if ( ProcessImageFileName )
        {
          v21 = -1;
          do
            ++v21;
          while ( *((_BYTE *)ProcessImageFileName + v21) );
          v20 = v21 + 1;
        }
        else
        {
          ProcessImageFileName = &word_18002CAAA;
        }
        v48 = ProcessImageFileName;
        p_ElapsedSeconds = &ElapsedSeconds;
        v49 = v20;
        p_LowLimit = &LowLimit;
        v50 = 0;
        ElapsedSeconds = a3;
        v52 = 4;
        LODWORD(LowLimit) = a4;
        v54 = 4;
        tlgCreate1Sz_wchar_t(v55, v59);
        v35 = 0x1000000;
        v56 = &v35;
        v57 = 8;
        tlgWriteAgg(v22, (unsigned __int8 *)&qword_180031FA0, v23, 0xDu, &v36);
      }
    }
    else
    {
      _InterlockedAdd(&dword_180040530, 1u);
    }
  }
  if ( v24[0] )
  {
    ExFreePoolWithTag(P[1], 0);
    P[1] = 0;
    LODWORD(P[0]) = 0;
  }
  if ( Process )
    ObfDereferenceObject(Process);
}

```

## disassembly

```asm
0x180023320  mov     [rsp-8+arg_10], rbx
0x180023325  push    rbp
0x180023326  push    rsi
0x180023327  push    rdi
0x180023328  push    r12
0x18002332a  push    r13
0x18002332c  push    r14
0x18002332e  push    r15
0x180023330  lea     rbp, [rsp-1E0h]
0x180023338  sub     rsp, 2E0h
0x18002333f  mov     rax, cs:__security_cookie
0x180023346  xor     rax, rsp
0x180023349  mov     [rbp+210h+var_40], rax
0x180023350  mov     r14, [rdx+8]
0x180023354  lea     rbx, word_18002CAAA
0x18002335b  mov     r13, [rbp+210h+SourceString]
0x180023362  xor     eax, eax
0x180023364  xorps   xmm0, xmm0
0x180023367  mov     qword ptr [rbp+210h+Time], rax
0x18002336b  mov     r15d, r9d
0x18002336e  mov     qword ptr [rsp+310h+LocalTime], rax
0x180023373  mov     r12d, r8d
0x180023376  mov     [rbp+210h+Process], rax
0x18002337a  mov     rsi, rdx
0x18002337d  mov     [rsp+310h+var_2A8], eax
0x180023381  mov     rdi, rcx
0x180023384  mov     [rsp+310h+var_2A4], eax
0x180023388  movups  xmmword ptr [rbp+210h+P], xmm0
0x18002338c  mov     rcx, [r14+68h]
0x180023390  lea     r9, [rsp+310h+ElapsedSeconds]
0x180023395  lea     r8, [rsp+310h+var_2A4]
0x18002339a  mov     [rsp+310h+ElapsedSeconds], eax
0x18002339e  lea     rdx, [rsp+310h+var_2A8]
0x1800233a3  mov     [rsp+310h+var_2B0], al
0x1800233a7  mov     [rsp+310h+var_2F0], rax
0x1800233ac  call    FltpGetDriverVersion
0x1800233b1  mov     r8d, 0AADh
0x1800233b7  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x1800233be  xor     r9d, r9d
0x1800233c1  mov     ecx, eax
0x1800233c3  call    FltpDbgStatus
0x1800233c8  test    eax, eax
0x1800233ca  js      short loc_1800233F5
0x1800233cc  mov     ecx, [rsp+310h+ElapsedSeconds]; ElapsedSeconds
0x1800233d0  lea     rdx, [rbp+210h+Time]; Time
0x1800233d4  call    cs:__imp_RtlSecondsSince1970ToTime
0x1800233db  nop     dword ptr [rax+rax+00h]
0x1800233e0  lea     rdx, [rsp+310h+LocalTime]; LocalTime
0x1800233e5  lea     rcx, [rbp+210h+Time]; SystemTime
0x1800233e9  call    cs:__imp_RtlSystemTimeToLocalTime
0x1800233f0  nop     dword ptr [rax+rax+00h]
0x1800233f5  mov     ecx, [rdi-4]; ProcessId
0x1800233f8  lea     rdx, [rbp+210h+Process]; Process
0x1800233fc  call    cs:__imp_PsLookupProcessByProcessId
0x180023403  nop     dword ptr [rax+rax+00h]
0x180023408  xor     r9d, r9d
0x18002340b  lea     rdx, aMinkernelFsFil_13; "minkernel\\fs\\filtermgr\\filter\\telem"...
0x180023412  mov     ecx, eax
0x180023414  mov     r8d, 0ABBh
0x18002341a  call    FltpDbgStatus
0x18002341f  test    eax, eax
0x180023421  js      short loc_180023436
0x180023423  mov     rcx, [rbp+210h+Process]
0x180023427  call    cs:__imp_PsGetProcessImageFileName
0x18002342e  nop     dword ptr [rax+rax+00h]
0x180023433  mov     rbx, rax
0x180023436  lea     rax, [rsp+310h+var_2B0]
0x18002343b  mov     rdx, rsi
0x18002343e  lea     r9, [rbp+210h+P]
0x180023442  mov     [rsp+310h+var_2F0], rax
0x180023447  mov     rcx, rdi
0x18002344a  call    FltpBuildPathNameForEventLog
0x18002344f  lea     r8, [r14+40h]; SourceString
0x180023453  mov     edx, 40h ; '@'; cbDest
0x180023458  lea     rcx, [rbp+210h+pszDest]; pszDest
0x18002345f  call    RtlStringCbCopyUnicodeString
0x180023464  mov     r8, r13; SourceString
0x180023467  lea     rcx, [rbp+210h+var_140]; pszDest
0x18002346e  mov     edx, 100h; cbDest
0x180023473  call    RtlStringCbCopyUnicodeString
0x180023478  test    cs:Microsoft_Windows_FilterManagerEnableBits, 4
0x18002347f  mov     edi, [rsp+310h+var_2A8]
0x180023483  mov     esi, [rsp+310h+var_2A4]
0x180023487  jz      short loc_1800234CB
0x180023489  mov     [rsp+310h+var_2B8], r15d
0x18002348e  lea     rax, [rbp+210h+var_140]
0x180023495  mov     [rsp+310h+var_2C0], rax
0x18002349a  lea     r9, [rbp+210h+pszDest]
0x1800234a1  mov     rax, [rbp+210h+P+8]
0x1800234a5  mov     [rsp+310h+var_2C8], r12d
0x1800234aa  mov     [rsp+310h+var_2D0], rax
0x1800234af  lea     rax, [rsp+310h+LocalTime]
0x1800234b4  mov     [rsp+310h+var_2D8], rbx
0x1800234b9  mov     [rsp+310h+var_2E0], rax
0x1800234be  mov     [rsp+310h+var_2E8], esi
0x1800234c2  mov     dword ptr [rsp+310h+var_2F0], edi
0x1800234c6  call    McTemplateK0zqqmszqzd_EtwWriteTransfer
0x1800234cb  xor     r13d, r13d
0x1800234ce  cmp     cs:dword_18003E018, 5
0x1800234d5  jbe     loc_18002365C
0x1800234db  lea     rdx, [rbp+210h+HighLimit]; HighLimit
0x1800234df  mov     [rbp+210h+HighLimit], r13
0x1800234e3  lea     rcx, [rsp+310h+LowLimit]; LowLimit
0x1800234e8  mov     [rsp+310h+LowLimit], r13
0x1800234ed  call    cs:__imp_IoGetStackLimits
0x1800234f4  nop     dword ptr [rax+rax+00h]
0x1800234f9  lea     rax, [rbp+210h+HighLimit]
0x1800234fd  sub     rax, [rsp+310h+LowLimit]
0x180023502  cmp     rax, 200h
0x180023508  jnb     short loc_18002351B
0x18002350a  lea     r9d, [r13+1]
0x18002350e  lock add cs:dword_180040530, r9d
0x180023516  jmp     loc_18002365C
0x18002351b  mov     eax, cs:dword_18003E018
0x180023521  cmp     eax, 5
0x180023524  jbe     loc_18002365C
0x18002352a  mov     rdx, 400000000000h
0x180023534  lea     rcx, dword_18003E018
0x18002353b  call    _tlgKeywordOn
0x180023540  test    al, al
0x180023542  jz      loc_18002365C
0x180023548  lea     rax, [rbp+210h+var_268]
0x18002354c  mov     [rbp+210h+var_228], 8
0x180023554  mov     [rbp+210h+var_230], rax
0x180023558  lea     rdx, [rbp+210h+pszDest]
0x18002355f  lea     rax, [r14+28h]
0x180023563  mov     [rbp+210h+var_218], 10h
0x18002356b  mov     r9d, 1
0x180023571  mov     [rbp+210h+var_220], rax
0x180023575  lea     rcx, [rbp+210h+var_210]
0x180023579  mov     [rbp+210h+var_268], r9
0x18002357d  call    _tlgCreate1Sz_wchar_t
0x180023582  mov     [rsp+310h+var_2A4], edi
0x180023586  lea     rax, [rsp+310h+var_2A4]
0x18002358b  mov     [rbp+210h+var_200], rax
0x18002358f  lea     rax, [rsp+310h+var_2A8]
0x180023594  mov     [rbp+210h+var_1F0], rax
0x180023598  lea     rax, [rsp+310h+LocalTime]
0x18002359d  mov     [rbp+210h+var_1E0], rax
0x1800235a1  mov     [rbp+210h+var_1F8], 4
0x1800235a9  mov     [rsp+310h+var_2A8], esi
0x1800235ad  mov     [rbp+210h+var_1E8], 4
0x1800235b5  mov     [rbp+210h+var_1D8], 8
0x1800235bd  test    rbx, rbx
0x1800235c0  jz      short loc_1800235D4
0x1800235c2  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800235c6  inc     r9
0x1800235c9  cmp     [rbx+r9], r13b
0x1800235cd  jnz     short loc_1800235C6
0x1800235cf  inc     r9d
0x1800235d2  jmp     short loc_1800235DB
0x1800235d4  lea     rbx, word_18002CAAA
0x1800235db  lea     rax, [rsp+310h+ElapsedSeconds]
0x1800235e0  mov     [rbp+210h+var_1D0], rbx
0x1800235e4  mov     [rbp+210h+var_1C0], rax
0x1800235e8  lea     rdx, [rbp+210h+var_140]
0x1800235ef  lea     rax, [rsp+310h+LowLimit]
0x1800235f4  mov     [rbp+210h+var_1C8], r9d
0x1800235f8  lea     rcx, [rbp+210h+var_1A0]
0x1800235fc  mov     [rbp+210h+var_1B0], rax
0x180023600  mov     [rbp+210h+var_1C4], r13d
0x180023604  mov     [rsp+310h+ElapsedSeconds], r12d
0x180023609  mov     [rbp+210h+var_1B8], 4
0x180023611  mov     dword ptr [rsp+310h+LowLimit], r15d
0x180023616  mov     [rbp+210h+var_1A8], 4
0x18002361e  call    _tlgCreate1Sz_wchar_t
0x180023623  lea     rax, [rbp+210h+var_260]
0x180023627  mov     [rbp+210h+var_260], 1000000h
0x18002362f  mov     [rbp+210h+var_190], rax
0x180023636  lea     rdx, qword_180031FA0; int
0x18002363d  lea     rax, [rbp+210h+var_250]
0x180023641  mov     [rbp+210h+var_188], 8
0x18002364c  mov     r9d, 0Dh; int
0x180023652  mov     [rsp+310h+var_2F0], rax; PEVENT_DATA_DESCRIPTOR
0x180023657  call    _tlgWriteAgg
0x18002365c  cmp     [rsp+310h+var_2B0], r13b
0x180023661  jz      short loc_180023680
0x180023663  mov     rcx, [rbp+210h+P+8]; P
0x180023667  xor     edx, edx; Tag
0x180023669  call    cs:__imp_ExFreePoolWithTag
0x180023670  nop     dword ptr [rax+rax+00h]
0x180023675  mov     [rbp+210h+P+8], r13
0x180023679  mov     dword ptr [rbp+210h+P], 0
0x180023680  mov     rcx, [rbp+210h+Process]; Object
0x180023684  test    rcx, rcx
0x180023687  jz      short loc_180023695
0x180023689  call    cs:__imp_ObfDereferenceObject
0x180023690  nop     dword ptr [rax+rax+00h]
0x180023695  mov     rcx, [rbp+210h+var_40]
0x18002369c  xor     rcx, rsp; StackCookie
0x18002369f  call    __security_check_cookie
0x1800236a4  mov     rbx, [rsp+310h+arg_10]
0x1800236ac  add     rsp, 2E0h
0x1800236b3  pop     r15
0x1800236b5  pop     r14
0x1800236b7  pop     r13
0x1800236b9  pop     r12
0x1800236bb  pop     rdi
0x1800236bc  pop     rsi
0x1800236bd  pop     rbp
0x1800236be  retn
```

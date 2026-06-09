# SmartlockerTelemetrizeOriginInfo

- ea: `0x140030620`
- end: `0x140030aa9`
- name: `SmartlockerTelemetrizeOriginInfo`
- size: `1161`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14002f560`

## callees

- `0x140001b3c`
- `0x140006a20`
- `0x140006c40`
- `0x140030620`
- `0x140032980`
- `0x140032a50`
- `0x1400356b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140030a49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030a5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030a75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030a49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030a5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030a75`
- `ntoskrnl!RtlInitAnsiString` at `0x140030743`
- `ntoskrnl!RtlInitAnsiString` at `0x140030743`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140030730`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140030730`
- `ntoskrnl!PsGetCurrentProcess` at `0x140030721`
- `ntoskrnl!PsGetCurrentProcess` at `0x140030721`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003074f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003074f`
- `ntoskrnl!ZwQueryInformationFile` at `0x140030774`
- `ntoskrnl!ZwQueryInformationFile` at `0x140030774`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140030794`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140030794`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400307e4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400308e5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140030908`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400307e4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400308e5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140030908`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x140030897`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x140030897`
- `ntoskrnl!ZwClose` at `0x140030861`
- `ntoskrnl!ZwClose` at `0x140030861`
- `ksecdd!BCryptGenRandom` at `0x140030715`
- `ksecdd!BCryptGenRandom` at `0x140030715`

## pseudocode

```c
void __fastcall SmartlockerTelemetrizeOriginInfo(
        __int64 a1,
        __int64 a2,
        void *a3,
        int a4,
        unsigned int a5,
        char a6,
        __int64 a7,
        __int64 a8,
        char a9,
        char a10,
        int a11,
        __int64 a12,
        __int64 a13,
        char a14)
{
  char v14; // di
  UNICODE_STRING *v17; // rsi
  __int64 *v18; // rax
  __int64 CurrentProcess; // rax
  const char *ProcessImageFileName; // rax
  int v21; // eax
  PWSTR Buffer; // r15
  ULONG v23; // eax
  unsigned int v24; // r8d
  unsigned int i; // edx
  __int64 v26; // r9
  const UNICODE_STRING *v27; // rax
  PCUNICODE_STRING v28; // r15
  int v29; // eax
  _DWORD *v30; // r12
  const UNICODE_STRING *v31; // rcx
  ULONG v32; // eax
  void *v33; // r15
  BOOLEAN v34; // al
  PCUNICODE_STRING v35; // rcx
  BOOLEAN v36; // al
  int v37; // edx
  unsigned __int64 v38; // r9
  bool v39; // zf
  __int64 FileInformationClass; // [rsp+20h] [rbp-E0h]
  __int64 v41; // [rsp+28h] [rbp-D8h]
  char v42[8]; // [rsp+30h] [rbp-D0h]
  int v43; // [rsp+38h] [rbp-C8h]
  ULONG UnicodeStringActualByteCount; // [rsp+60h] [rbp-A0h] BYREF
  PCUNICODE_STRING String1; // [rsp+68h] [rbp-98h] BYREF
  PVOID P; // [rsp+70h] [rbp-90h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  void *v48; // [rsp+80h] [rbp-80h]
  PCEVENT_DESCRIPTOR EventDescriptor; // [rsp+88h] [rbp-78h]
  _STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  __int128 v51; // [rsp+A0h] [rbp-60h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  __int128 FileInformation; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-30h]
  UCHAR pbBuffer[16]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR UnicodeStringDestination[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v57; // [rsp+F8h] [rbp-8h]

  v54 = 0;
  v14 = a4;
  TokenHandle = 0;
  P = 0;
  String1 = 0;
  v17 = 0;
  DestinationString = 0;
  v51 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  *(_OWORD *)pbBuffer = 0;
  *(_OWORD *)UnicodeStringDestination = 0;
  v57 = 0;
  if ( (a11 & 0xFF0000) != 0x10000 && (a4 || a10) )
  {
    if ( a14 )
    {
      if ( (dword_140019728 & 1) == 0 )
        return;
    }
    else if ( (dword_140019728 & 2) == 0 )
    {
      return;
    }
    v18 = AppIdSmartlockerEnforcementStatusAudit;
    if ( !a9 )
      v18 = AppIdSmartlockerEnforcementStatusFail;
  }
  else
  {
    v14 = 0;
    v18 = AppIdSmartlockerEnforcementStatusSuccess;
  }
  v48 = 0;
  EventDescriptor = (PCEVENT_DESCRIPTOR)v18;
  BCryptGenRandom(0, pbBuffer, 0x10u, 2u);
  CurrentProcess = PsGetCurrentProcess();
  ProcessImageFileName = (const char *)PsGetProcessImageFileName(CurrentProcess);
  RtlInitAnsiString(&DestinationString, ProcessImageFileName);
  PsGetCurrentProcessId();
  ZwQueryInformationFile(
    a3,
    &IoStatusBlock,
    &FileInformation,
    0x18u,
    FileMaximumInformation|FileBothDirectoryInformation);
  if ( ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0x200u, &TokenHandle) < 0 )
  {
    v28 = (PCUNICODE_STRING)*((_QWORD *)&v51 + 1);
  }
  else
  {
    v21 = AiQueryTokenAttributes(TokenHandle, &String1);
    v17 = (UNICODE_STRING *)String1;
    if ( v21 >= 0 )
    {
      Buffer = String1->Buffer;
      v23 = 0;
      while ( 1 )
      {
        UnicodeStringActualByteCount = v23;
        if ( v23 >= *(_DWORD *)(&v17->MaximumLength + 1) )
          break;
        if ( RtlEqualUnicodeString((PCUNICODE_STRING)Buffer, &stru_1400092D8, 1u) )
        {
          if ( Buffer[8] != 3 )
            break;
          v24 = *((_DWORD *)Buffer + 6);
          if ( !v24 )
            break;
          for ( i = 0; i < v24; ++i )
          {
            v26 = *((_QWORD *)Buffer + 4) + 16LL * i;
            v27 = *(const UNICODE_STRING **)(v26 + 8);
            String1 = v27;
            if ( v27 && *(_WORD *)v26 && v27->Length != 37 )
            {
              v28 = String1;
              goto LABEL_29;
            }
          }
          v28 = *(PCUNICODE_STRING *)(*((_QWORD *)Buffer + 4) + 8LL);
          goto LABEL_29;
        }
        v23 = UnicodeStringActualByteCount + 1;
        Buffer += 20;
      }
    }
    v28 = (PCUNICODE_STRING)*((_QWORD *)&v51 + 1);
LABEL_29:
    ZwClose(TokenHandle);
  }
  if ( !v28 )
  {
    UnicodeStringActualByteCount = 0;
    RtlUTF8ToUnicodeN(
      UnicodeStringDestination,
      0x20u,
      &UnicodeStringActualByteCount,
      DestinationString.Buffer,
      DestinationString.Length);
  }
  v29 = AiQueryTokenAttributes(a1, &P);
  v30 = P;
  if ( v29 < 0 )
  {
    v33 = v48;
  }
  else
  {
    v31 = (const UNICODE_STRING *)*((_QWORD *)P + 1);
    v32 = 0;
    v33 = 0;
    while ( 1 )
    {
      String1 = v31;
      UnicodeStringActualByteCount = v32;
      if ( v32 >= v30[1] )
        break;
      v34 = RtlEqualUnicodeString(v31, &stru_1400092C8, 1u);
      v35 = String1;
      if ( !v34 )
      {
        v36 = RtlEqualUnicodeString(String1, &stru_1400092B8, 1u);
        v35 = String1;
        if ( v36 )
        {
          if ( String1[1].Length == 4 && LODWORD(String1[1].Buffer) == 1 )
          {
            v37 = *(unsigned __int16 *)(*(_QWORD *)&String1[2].Length + 8LL);
            LODWORD(P) = v37;
            if ( (unsigned int)(v37 - 1) <= 0xFFCC )
            {
              v33 = (void *)AiAlloc((unsigned int)(v37 + 50));
              if ( !v33 )
                goto LABEL_50;
              memmove(
                v33,
                *(const void **)(*(_QWORD *)&String1[2].Length + 16LL),
                *(unsigned __int16 *)(*(_QWORD *)&String1[2].Length + 8LL));
              v38 = **(_QWORD **)&String1[2].Length;
              *(_DWORD *)v42 = (unsigned __int16)v38;
              LODWORD(v41) = WORD1(v38);
              LODWORD(FileInformationClass) = WORD2(v38);
              RtlStringCbPrintfW(
                (NTSTRSAFE_PWSTR)v33 + ((unsigned __int64)(unsigned __int16)P >> 1),
                0x32u,
                L"\\%u.%u.%u.%u",
                HIWORD(v38),
                FileInformationClass,
                v41,
                *(_QWORD *)v42);
              v35 = String1;
            }
          }
        }
      }
      v32 = UnicodeStringActualByteCount + 1;
      v31 = (PCUNICODE_STRING)((char *)v35 + 40);
    }
  }
  v39 = a13 == 0;
  if ( a13 )
  {
    if ( a5 <= 1 )
      --*(_DWORD *)(a13 + 12);
    v39 = a13 == 0;
  }
  AiLogSmartlockerEnforcementStatusEvent(
    qword_1400196F8,
    EventDescriptor,
    v14,
    a5,
    a6,
    v43,
    (__int64)&FileInformation + 8,
    0,
    !v39,
    a13);
LABEL_50:
  if ( v17 )
    ExFreePoolWithTag(v17, 0);
  if ( v30 )
    ExFreePoolWithTag(v30, 0);
  if ( v33 )
    ExFreePoolWithTag(v33, 0);
}

```

## disassembly

```asm
0x140030620  mov     [rsp-8+arg_18], rbx
0x140030625  push    rbp
0x140030626  push    rsi
0x140030627  push    rdi
0x140030628  push    r12
0x14003062a  push    r13
0x14003062c  push    r14
0x14003062e  push    r15
0x140030630  lea     rbp, [rsp-10h]
0x140030635  sub     rsp, 110h
0x14003063c  mov     rax, cs:__security_cookie
0x140030643  xor     rax, rsp
0x140030646  mov     [rbp+40h+var_38], rax
0x14003064a  mov     ebx, [rbp+40h+arg_50]
0x140030650  xorps   xmm0, xmm0
0x140030653  mov     r14, [rbp+40h+arg_60]
0x14003065a  xor     eax, eax
0x14003065c  xorps   xmm1, xmm1
0x14003065f  mov     [rbp+40h+var_70], rax
0x140030663  mov     r13, rdx
0x140030666  and     ebx, 0FF0000h
0x14003066c  xor     edx, edx
0x14003066e  mov     edi, r9d
0x140030671  mov     [rsp+140h+TokenHandle], rdx
0x140030676  mov     r15, r8
0x140030679  mov     [rsp+140h+P], rdx
0x14003067e  mov     r12, rcx
0x140030681  mov     [rsp+140h+String1], rdx
0x140030686  mov     esi, edx
0x140030688  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x14003068c  movups  [rbp+40h+var_A0], xmm1
0x140030690  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x140030694  movups  [rbp+40h+FileInformation], xmm1
0x140030698  movups  xmmword ptr [rbp+40h+pbBuffer], xmm0
0x14003069c  movups  xmmword ptr [rbp+40h+UnicodeStringDestination], xmm0
0x1400306a0  movups  [rbp+40h+var_48], xmm0
0x1400306a4  cmp     ebx, 10000h
0x1400306aa  jz      short loc_1400306F2
0x1400306ac  test    r9d, r9d
0x1400306af  jnz     short loc_1400306B9
0x1400306b1  cmp     [rbp+40h+arg_48], al
0x1400306b7  jz      short loc_1400306F2
0x1400306b9  cmp     [rbp+40h+arg_68], al
0x1400306bf  mov     eax, cs:dword_140019728
0x1400306c5  jz      short loc_1400306D0
0x1400306c7  test    al, 1
0x1400306c9  jnz     short loc_1400306D8
0x1400306cb  jmp     loc_140030A81
0x1400306d0  test    al, 2
0x1400306d2  jz      loc_140030A81
0x1400306d8  cmp     [rbp+40h+arg_40], dl
0x1400306de  lea     rax, AppIdSmartlockerEnforcementStatusAudit
0x1400306e5  lea     rcx, AppIdSmartlockerEnforcementStatusFail
0x1400306ec  cmovz   rax, rcx
0x1400306f0  jmp     short loc_1400306FB
0x1400306f2  mov     edi, edx
0x1400306f4  lea     rax, AppIdSmartlockerEnforcementStatusSuccess
0x1400306fb  mov     [rbp+40h+var_C0], rdx
0x1400306ff  mov     r9d, 2; dwFlags
0x140030705  lea     rdx, [rbp+40h+pbBuffer]; pbBuffer
0x140030709  mov     [rbp+40h+EventDescriptor], rax
0x14003070d  mov     r8d, 10h; cbBuffer
0x140030713  xor     ecx, ecx; hAlgorithm
0x140030715  call    cs:__imp_BCryptGenRandom
0x14003071c  nop     dword ptr [rax+rax+00h]
0x140030721  call    cs:__imp_PsGetCurrentProcess
0x140030728  nop     dword ptr [rax+rax+00h]
0x14003072d  mov     rcx, rax
0x140030730  call    cs:__imp_PsGetProcessImageFileName
0x140030737  nop     dword ptr [rax+rax+00h]
0x14003073c  mov     rdx, rax; SourceString
0x14003073f  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x140030743  call    cs:__imp_RtlInitAnsiString
0x14003074a  nop     dword ptr [rax+rax+00h]
0x14003074f  call    cs:__imp_PsGetCurrentProcessId
0x140030756  nop     dword ptr [rax+rax+00h]
0x14003075b  mov     r9d, 18h; Length
0x140030761  mov     dword ptr [rsp+140h+FileInformationClass], 3Bh ; ';'; FileInformationClass
0x140030769  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x14003076d  mov     rcx, r15; FileHandle
0x140030770  lea     rdx, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x140030774  call    cs:__imp_ZwQueryInformationFile
0x14003077b  nop     dword ptr [rax+rax+00h]
0x140030780  lea     r9, [rsp+140h+TokenHandle]; TokenHandle
0x140030785  xor     edx, edx; DesiredAccess
0x140030787  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14003078e  mov     r8d, 200h; HandleAttributes
0x140030794  call    cs:__imp_ZwOpenProcessTokenEx
0x14003079b  nop     dword ptr [rax+rax+00h]
0x1400307a0  test    eax, eax
0x1400307a2  js      loc_14003086F
0x1400307a8  mov     rcx, [rsp+140h+TokenHandle]
0x1400307ad  lea     rdx, [rsp+140h+String1]
0x1400307b2  call    AiQueryTokenAttributes
0x1400307b7  mov     rsi, [rsp+140h+String1]
0x1400307bc  test    eax, eax
0x1400307be  js      loc_140030858
0x1400307c4  mov     r15, [rsi+8]
0x1400307c8  xor     eax, eax
0x1400307ca  mov     [rsp+140h+UnicodeStringActualByteCount], eax
0x1400307ce  cmp     eax, [rsi+4]
0x1400307d1  jnb     loc_140030858
0x1400307d7  mov     r8b, 1; CaseInSensitive
0x1400307da  lea     rdx, stru_1400092D8; String2
0x1400307e1  mov     rcx, r15; String1
0x1400307e4  call    cs:__imp_RtlEqualUnicodeString
0x1400307eb  nop     dword ptr [rax+rax+00h]
0x1400307f0  test    al, al
0x1400307f2  jnz     short loc_140030800
0x1400307f4  mov     eax, [rsp+140h+UnicodeStringActualByteCount]
0x1400307f8  inc     eax
0x1400307fa  add     r15, 28h ; '('
0x1400307fe  jmp     short loc_1400307CA
0x140030800  mov     eax, 3
0x140030805  cmp     ax, [r15+10h]
0x14003080a  jnz     short loc_140030858
0x14003080c  mov     r8d, [r15+18h]
0x140030810  cmp     r8d, 1
0x140030814  jb      short loc_140030858
0x140030816  xor     edx, edx
0x140030818  cmp     edx, r8d
0x14003081b  jnb     short loc_14003084E
0x14003081d  mov     r9d, edx
0x140030820  shl     r9, 4
0x140030824  add     r9, [r15+20h]
0x140030828  mov     rax, [r9+8]
0x14003082c  mov     [rsp+140h+String1], rax
0x140030831  test    rax, rax
0x140030834  jz      short loc_140030843
0x140030836  cmp     word ptr [r9], 0
0x14003083b  jbe     short loc_140030843
0x14003083d  cmp     word ptr [rax], 25h ; '%'
0x140030841  jnz     short loc_140030847
0x140030843  inc     edx
0x140030845  jmp     short loc_140030818
0x140030847  mov     r15, [rsp+140h+String1]
0x14003084c  jmp     short loc_14003085C
0x14003084e  mov     rax, [r15+20h]
0x140030852  mov     r15, [rax+8]
0x140030856  jmp     short loc_14003085C
0x140030858  mov     r15, qword ptr [rbp+40h+var_A0+8]
0x14003085c  mov     rcx, [rsp+140h+TokenHandle]; Handle
0x140030861  call    cs:__imp_ZwClose
0x140030868  nop     dword ptr [rax+rax+00h]
0x14003086d  jmp     short loc_140030873
0x14003086f  mov     r15, qword ptr [rbp+40h+var_A0+8]
0x140030873  test    r15, r15
0x140030876  jnz     short loc_1400308A3
0x140030878  movzx   eax, [rbp+40h+DestinationString.Length]
0x14003087c  lea     r8, [rsp+140h+UnicodeStringActualByteCount]; UnicodeStringActualByteCount
0x140030881  mov     r9, [rbp+40h+DestinationString.Buffer]; UTF8StringSource
0x140030885  lea     rcx, [rbp+40h+UnicodeStringDestination]; UnicodeStringDestination
0x140030889  mov     edx, 20h ; ' '; UnicodeStringMaxByteCount
0x14003088e  mov     dword ptr [rsp+140h+FileInformationClass], eax; UTF8StringByteCount
0x140030892  mov     [rsp+140h+UnicodeStringActualByteCount], r15d
0x140030897  call    cs:__imp_RtlUTF8ToUnicodeN
0x14003089e  nop     dword ptr [rax+rax+00h]
0x1400308a3  lea     rdx, [rsp+140h+P]
0x1400308a8  mov     rcx, r12
0x1400308ab  call    AiQueryTokenAttributes
0x1400308b0  mov     r12, [rsp+140h+P]
0x1400308b5  test    eax, eax
0x1400308b7  js      loc_1400309E6
0x1400308bd  mov     rcx, [r12+8]; String1
0x1400308c2  xor     eax, eax
0x1400308c4  mov     r15d, eax
0x1400308c7  mov     [rsp+140h+String1], rcx
0x1400308cc  mov     [rsp+140h+UnicodeStringActualByteCount], eax
0x1400308d0  cmp     eax, [r12+4]
0x1400308d5  jnb     loc_1400309EA
0x1400308db  mov     r8b, 1; CaseInSensitive
0x1400308de  lea     rdx, stru_1400092C8; String2
0x1400308e5  call    cs:__imp_RtlEqualUnicodeString
0x1400308ec  nop     dword ptr [rax+rax+00h]
0x1400308f1  mov     rcx, [rsp+140h+String1]; String1
0x1400308f6  test    al, al
0x1400308f8  jnz     loc_1400309D7
0x1400308fe  mov     r8b, 1; CaseInSensitive
0x140030901  lea     rdx, stru_1400092B8; String2
0x140030908  call    cs:__imp_RtlEqualUnicodeString
0x14003090f  nop     dword ptr [rax+rax+00h]
0x140030914  mov     rcx, [rsp+140h+String1]
0x140030919  test    al, al
0x14003091b  jz      loc_1400309D7
0x140030921  cmp     word ptr [rcx+10h], 4
0x140030926  jnz     loc_1400309D7
0x14003092c  cmp     dword ptr [rcx+18h], 1
0x140030930  jnz     loc_1400309D7
0x140030936  mov     rax, [rcx+20h]
0x14003093a  movzx   edx, word ptr [rax+8]
0x14003093e  mov     dword ptr [rsp+140h+P], edx
0x140030942  lea     eax, [rdx-1]
0x140030945  cmp     eax, 0FFCCh
0x14003094a  ja      loc_1400309D7
0x140030950  lea     ecx, [rdx+32h]
0x140030953  call    AiAlloc
0x140030958  mov     r15, rax
0x14003095b  test    rax, rax
0x14003095e  jz      loc_140030A3F
0x140030964  mov     rax, [rsp+140h+String1]
0x140030969  mov     rcx, r15; void *
0x14003096c  mov     rdx, [rax+20h]
0x140030970  movzx   r8d, word ptr [rdx+8]; Size
0x140030975  mov     rdx, [rdx+10h]; Src
0x140030979  call    memmove
0x14003097e  mov     rax, [rsp+140h+String1]
0x140030983  mov     rcx, [rax+20h]
0x140030987  mov     r9, [rcx]
0x14003098a  mov     rax, r9
0x14003098d  movzx   r10d, r9w
0x140030991  shr     rax, 20h
0x140030995  mov     rcx, r9
0x140030998  movzx   edx, ax
0x14003099b  movzx   eax, word ptr [rsp+140h+P]
0x1400309a0  shr     rcx, 10h
0x1400309a4  movzx   r8d, cx
0x1400309a8  mov     dword ptr [rsp+140h+var_110], r10d
0x1400309ad  mov     dword ptr [rsp+140h+var_118], r8d
0x1400309b2  lea     r8, aUUUU; "\\%u.%u.%u.%u"
0x1400309b9  shr     rax, 1
0x1400309bc  mov     dword ptr [rsp+140h+FileInformationClass], edx
0x1400309c0  mov     edx, 32h ; '2'; cbDest
0x1400309c5  shr     r9, 30h
0x1400309c9  lea     rcx, [r15+rax*2]; pszDest
0x1400309cd  call    RtlStringCbPrintfW
0x1400309d2  mov     rcx, [rsp+140h+String1]
0x1400309d7  mov     eax, [rsp+140h+UnicodeStringActualByteCount]
0x1400309db  inc     eax
0x1400309dd  add     rcx, 28h ; '('
0x1400309e1  jmp     loc_1400308C7
0x1400309e6  mov     r15, [rbp+40h+var_C0]
0x1400309ea  mov     ecx, dword ptr [rbp+40h+arg_20]
0x1400309ed  test    r14, r14
0x1400309f0  jz      short loc_1400309FE
0x1400309f2  cmp     ecx, 1
0x1400309f5  ja      short loc_1400309FB
0x1400309f7  dec     dword ptr [r14+0Ch]
0x1400309fb  test    r14, r14
0x1400309fe  mov     rdx, [rbp+40h+EventDescriptor]; EventDescriptor
0x140030a02  lea     r9, [rbp+40h+DestinationString]
0x140030a06  mov     [rsp+140h+var_E8], r14; __int64
0x140030a0b  setnz   al
0x140030a0e  mov     [rsp+140h+var_F0], al; char
0x140030a12  mov     r8, r13
0x140030a15  mov     dword ptr [rsp+140h+var_F8], ebx; char
0x140030a19  lea     rax, [rbp+40h+FileInformation+8]
0x140030a1d  mov     [rsp+140h+var_100], rax; __int64
0x140030a22  mov     rax, qword ptr [rbp+40h+arg_28]
0x140030a26  mov     qword ptr [rsp+140h+var_110], rax; char
0x140030a2b  mov     dword ptr [rsp+140h+var_118], ecx; char
0x140030a2f  mov     rcx, cs:qword_1400196F8; RegHandle
0x140030a36  mov     dword ptr [rsp+140h+FileInformationClass], edi; char
0x140030a3a  call    AiLogSmartlockerEnforcementStatusEvent
0x140030a3f  test    rsi, rsi
0x140030a42  jz      short loc_140030A55
0x140030a44  xor     edx, edx; Tag
0x140030a46  mov     rcx, rsi; P
0x140030a49  call    cs:__imp_ExFreePoolWithTag
0x140030a50  nop     dword ptr [rax+rax+00h]
0x140030a55  test    r12, r12
0x140030a58  jz      short loc_140030A6B
0x140030a5a  xor     edx, edx; Tag
0x140030a5c  mov     rcx, r12; P
0x140030a5f  call    cs:__imp_ExFreePoolWithTag
0x140030a66  nop     dword ptr [rax+rax+00h]
0x140030a6b  test    r15, r15
0x140030a6e  jz      short loc_140030A81
0x140030a70  xor     edx, edx; Tag
0x140030a72  mov     rcx, r15; P
0x140030a75  call    cs:__imp_ExFreePoolWithTag
0x140030a7c  nop     dword ptr [rax+rax+00h]
0x140030a81  mov     rcx, [rbp+40h+var_38]
0x140030a85  xor     rcx, rsp; StackCookie
0x140030a88  call    __security_check_cookie
0x140030a8d  mov     rbx, [rsp+140h+arg_18]
0x140030a95  add     rsp, 110h
0x140030a9c  pop     r15
0x140030a9e  pop     r14
0x140030aa0  pop     r13
0x140030aa2  pop     r12
0x140030aa4  pop     rdi
0x140030aa5  pop     rsi
0x140030aa6  pop     rbp
0x140030aa7  retn
```

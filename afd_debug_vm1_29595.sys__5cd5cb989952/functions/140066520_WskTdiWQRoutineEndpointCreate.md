# WskTdiWQRoutineEndpointCreate

- ea: `0x140066520`
- end: `0x140066a55`
- name: `WskTdiWQRoutineEndpointCreate`
- size: `1333`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400644e0`
- `0x140064720`
- `0x140064d00`

## callees

- `0x140005b60`
- `0x14000f980`
- `0x140013030`
- `0x140037394`
- `0x14003ffdc`
- `0x1400479d0`
- `0x140066520`
- `0x140072840`
- `0x140072920`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400665e4`
- `ntoskrnl!KeInitializeEvent` at `0x1400665e4`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006663c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006663c`
- `ntoskrnl!PsReturnPoolQuota` at `0x140066a0d`
- `ntoskrnl!PsReturnPoolQuota` at `0x140066a0d`
- `ntoskrnl!PsGetCurrentProcess` at `0x14006654a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14006654a`
- `ntoskrnl!KeAttachProcess` at `0x140066918`
- `ntoskrnl!KeAttachProcess` at `0x140066918`
- `ntoskrnl!KeDetachProcess` at `0x14006693b`
- `ntoskrnl!KeDetachProcess` at `0x14006693b`
- `ntoskrnl!RtlIntegerToUnicode` at `0x1400667c7`
- `ntoskrnl!RtlIntegerToUnicode` at `0x1400667c7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140066806`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140066806`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140066782`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140066782`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006681e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140066833`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006681e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140066833`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006670e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006672e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006670e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006672e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400666aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400666df`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400666f6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400666aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400666df`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400666f6`
- `ntoskrnl!InitializeSListHead` at `0x1400668ba`
- `ntoskrnl!InitializeSListHead` at `0x1400668cd`
- `ntoskrnl!InitializeSListHead` at `0x1400668ba`
- `ntoskrnl!InitializeSListHead` at `0x1400668cd`
- `ntoskrnl!KeInitializeSpinLock` at `0x140066888`
- `ntoskrnl!KeInitializeSpinLock` at `0x140066888`
- `ntoskrnl!ObfDereferenceObject` at `0x140066a1c`
- `ntoskrnl!ObfDereferenceObject` at `0x140066a1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066990`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400669c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400669ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066990`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400669c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400669ee`

## pseudocode

```c
void __fastcall WskTdiWQRoutineEndpointCreate(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 *v4; // rbx
  __int64 CurrentProcess; // r13
  volatile signed __int64 *v6; // rdi
  __int64 *v7; // r14
  __int64 *v8; // r12
  unsigned int v9; // esi
  __int64 v10; // rcx
  signed __int64 v11; // rax
  bool v12; // cc
  signed __int64 v13; // rax
  __int64 v14; // rdx
  __int16 *v15; // r15
  struct _UNICODE_STRING *p_DestinationString; // rcx
  int TransportInfo; // eax
  __int64 v18; // rcx
  __int16 v19; // ax
  ULONG v20; // ecx
  bool v21; // zf
  struct _KPROCESS *v22; // rcx
  char v23; // bl
  unsigned int v24; // edi
  void *v25; // r8
  struct _KPROCESS *v26; // rbx
  __int64 v27; // [rsp+30h] [rbp-99h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-91h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-81h] BYREF
  struct _KEVENT Event; // [rsp+58h] [rbp-71h] BYREF
  _BYTE Object[24]; // [rsp+70h] [rbp-59h] BYREF
  __int64 v32; // [rsp+88h] [rbp-41h]
  WCHAR String[8]; // [rsp+90h] [rbp-39h] BYREF
  __int16 v34; // [rsp+A0h] [rbp-29h] BYREF

  v4 = a1;
  CurrentProcess = PsGetCurrentProcess(a1, a2, a3, a4);
  do
  {
    v6 = 0;
    v7 = v4 - 37;
    v27 = 0;
    DestinationString = 0;
    v8 = (__int64 *)*v4;
    if ( (*(_DWORD *)(v4 - 35) & 1) != 0 && !*(v4 - 22) )
    {
      v9 = *((_DWORD *)v4 - 46);
LABEL_5:
      if ( (*(_DWORD *)(v4 - 35) & 1) != 0 )
      {
        if ( *(v4 - 22) )
        {
          v32 = 0;
          *(_QWORD *)Object = &Event;
          *(_OWORD *)&Object[8] = 0;
          Destination = 0;
          memset(&Event, 0, sizeof(Event));
          KeInitializeEvent(&Event, SynchronizationEvent, 0);
          v10 = *(v4 - 23);
          *(_QWORD *)&Destination.Length = AfdSynchronousTlCloseRequestComplete;
          Destination.Buffer = (PWSTR)Object;
          if ( (*(unsigned int (__fastcall **)(__int64, struct _UNICODE_STRING *))*(v4 - 22))(v10, &Destination) == 259 )
            KeWaitForSingleObject(*(PVOID *)Object, Executive, 0, 0, 0);
          *(v4 - 22) = 0;
        }
        AfdTlDereferenceTransport(*(v4 - 21));
      }
      if ( v6 )
      {
        v11 = _InterlockedExchangeAdd64(v6 + 2, 0xFFFFFFFFFFFFFFFFuLL);
        v12 = v11 <= 1;
        v13 = v11 - 1;
        if ( v12 )
        {
          if ( v13 )
            __fastfail(0xEu);
          AfdFreeTransportInfo((PVOID)v6);
        }
      }
      if ( (*(_DWORD *)(v4 - 35) & 0x200) != 0 )
      {
        v24 = SOCKADDR_SIZE(*(_WORD *)*(v4 - 12));
        if ( v24 > (unsigned int)AfdStandardAddressLength )
          ExFreePoolWithTag(v25, 0x52646641u);
        else
          PplFreeToLookasideList((__int64)PplAddressPool, v25);
        if ( v24 > (unsigned int)AfdStandardAddressLength )
          ExFreePoolWithTag((PVOID)*(v4 - 31), 0x52646641u);
        else
          PplFreeToLookasideList((__int64)PplAddressPool, (void *)*(v4 - 31));
      }
      ((void (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD))v4[2])(v4[1], v9, 0, 0);
      v26 = (struct _KPROCESS *)*(v4 - 3);
      ExFreePoolWithTag(v7, 0x744B5357u);
      if ( v26 )
      {
        PsReturnPoolQuota(v26, (POOL_TYPE)512, 0x140u);
        ObfDereferenceObject(v26);
      }
      goto LABEL_55;
    }
    v14 = *(_QWORD *)(v4[1] + 184);
    v15 = *(__int16 **)(v14 + 8);
    RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(v14 + 16));
    if ( (*(_DWORD *)(v4 - 35) & 0x40000) == 0 )
      goto LABEL_19;
    *(_OWORD *)Object = 0;
    *(_OWORD *)&Event.Header.Lock = 0;
    RtlInitUnicodeString((PUNICODE_STRING)Object, L"\\Device\\RawIp");
    RtlInitUnicodeString((PUNICODE_STRING)&Event, L"\\Device\\RawIp6");
    if ( !RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)Object, 1u)
      && !RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)&Event, 1u) )
    {
      *((_DWORD *)v4 - 70) &= ~0x40000u;
LABEL_19:
      p_DestinationString = &DestinationString;
      goto LABEL_20;
    }
    v20 = *((unsigned __int16 *)v4 - 134);
    Destination = 0;
    if ( RtlIntegerToUnicode(v20, 0xAu, 6u, String) )
    {
      v9 = -1073741811;
      goto LABEL_5;
    }
    *(_DWORD *)&Destination.Length = 2883584;
    String[5] = 0;
    v34 = 0;
    Destination.Buffer = (PWSTR)&v34;
    RtlAppendUnicodeStringToString(&Destination, &DestinationString);
    RtlAppendUnicodeToString(&Destination, L"\\");
    RtlAppendUnicodeToString(&Destination, String);
    p_DestinationString = &Destination;
LABEL_20:
    TransportInfo = AfdGetTransportInfo(p_DestinationString, &v27);
    v6 = (volatile signed __int64 *)v27;
    v9 = TransportInfo;
    if ( TransportInfo < 0 )
      goto LABEL_5;
    v18 = *(v4 - 32);
    if ( v18 )
    {
      if ( (*(_DWORD *)(v27 + 72) & 0x100000) == 0 )
      {
        v9 = -1073741609;
        goto LABEL_5;
      }
      ObReferenceSecurityDescriptor(v18, 1);
    }
    v19 = *v15;
    if ( *v15 == -21278 )
    {
      *(_WORD *)v7 = -21294;
    }
    else if ( v19 == -21279 )
    {
      *(_WORD *)v7 = -21295;
    }
    else if ( v19 == -21277 )
    {
      *(_WORD *)v7 = -21293;
    }
    else
    {
      *(_WORD *)v7 = -21296;
    }
    *(v4 - 2) = (__int64)v15;
    KeInitializeSpinLock((PKSPIN_LOCK)v4 - 36);
    *((_DWORD *)v4 - 69) = 1;
    *((_DWORD *)v4 - 68) = 1;
    if ( *(_WORD *)v7 == 0xACD1 )
    {
      InitializeSListHead((PSLIST_HEADER)(v4 - 19));
      InitializeSListHead((PSLIST_HEADER)(v4 - 17));
    }
    v21 = (*(_DWORD *)(v4 - 35) & 0x200) == 0;
    *(v4 - 33) = (__int64)v6;
    if ( v21 )
    {
      ((void (__fastcall *)(__int64, _QWORD, __int64 *, __int64 (__fastcall **)()))v4[2])(
        v4[1],
        v9,
        v4 - 37,
        WskTdiTLProviderEndpointDispatch);
    }
    else
    {
      v22 = (struct _KPROCESS *)*(v4 - 3);
      if ( !v22 || (struct _KPROCESS *)CurrentProcess == v22 )
      {
        v23 = 0;
      }
      else
      {
        KeAttachProcess(v22);
        v23 = 1;
      }
      WskTdiConnectCore((__int64)v7);
      if ( v23 )
        KeDetachProcess();
    }
LABEL_55:
    v4 = v8;
  }
  while ( v8 );
}

```

## disassembly

```asm
0x140066520  push    rbp
0x140066522  push    rbx
0x140066523  push    rsi
0x140066524  push    rdi
0x140066525  push    r12
0x140066527  push    r13
0x140066529  push    r14
0x14006652b  push    r15
0x14006652d  lea     rbp, [rsp-1Fh]
0x140066532  sub     rsp, 0E8h
0x140066539  mov     rax, cs:__security_cookie
0x140066540  xor     rax, rsp
0x140066543  mov     [rbp+57h+var_50], rax
0x140066547  mov     rbx, rcx
0x14006654a  call    cs:__imp_PsGetCurrentProcess
0x140066551  nop     dword ptr [rax+rax+00h]
0x140066556  mov     r13, rax
0x140066559  xor     edi, edi
0x14006655b  lea     r14, [rbx-128h]
0x140066562  xorps   xmm0, xmm0
0x140066565  mov     [rsp+120h+var_F0], rdi
0x14006656a  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x14006656f  mov     eax, [rbx-118h]
0x140066575  mov     r12, [rbx]
0x140066578  test    al, 1
0x14006657a  jz      loc_140066692
0x140066580  cmp     [rbx-0B0h], rdi
0x140066587  jnz     loc_140066692
0x14006658d  mov     esi, [rbx-0B8h]
0x140066593  mov     eax, [rbx-118h]
0x140066599  test    al, 1
0x14006659b  jz      loc_14006665F
0x1400665a1  cmp     qword ptr [rbx-0B0h], 0
0x1400665a9  jz      loc_140066653
0x1400665af  xor     eax, eax
0x1400665b1  mov     [rbp+57h+var_98], 0
0x1400665b9  xorps   xmm0, xmm0
0x1400665bc  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x1400665c0  xor     r8d, r8d; State
0x1400665c3  lea     rax, [rbp+57h+Event]
0x1400665c7  xorps   xmm1, xmm1
0x1400665ca  mov     qword ptr [rbp+57h+Object], rax
0x1400665ce  lea     rcx, [rbp+57h+Event]; Event
0x1400665d2  movdqu  xmmword ptr [rbp+57h+Object+8], xmm0
0x1400665d7  lea     edx, [r8+1]; Type
0x1400665db  movups  xmmword ptr [rsp+120h+Destination.Length], xmm0
0x1400665e0  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x1400665e4  call    cs:__imp_KeInitializeEvent
0x1400665eb  nop     dword ptr [rax+rax+00h]
0x1400665f0  mov     rcx, [rbx-0B8h]
0x1400665f7  lea     rax, AfdSynchronousTlCloseRequestComplete
0x1400665fe  mov     qword ptr [rsp+120h+Destination.Length], rax
0x140066603  lea     rdx, [rsp+120h+Destination]
0x140066608  lea     rax, [rbp+57h+Object]
0x14006660c  mov     [rsp+120h+Destination.Buffer], rax
0x140066611  mov     rax, [rbx-0B0h]
0x140066618  mov     rax, [rax]
0x14006661b  call    _guard_dispatch_icall
0x140066620  cmp     eax, 103h
0x140066625  jnz     short loc_140066648
0x140066627  mov     rcx, qword ptr [rbp+57h+Object]; Object
0x14006662b  xor     r9d, r9d; Alertable
0x14006662e  xor     r8d, r8d; WaitMode
0x140066631  mov     [rsp+120h+Timeout], 0; Timeout
0x14006663a  xor     edx, edx; WaitReason
0x14006663c  call    cs:__imp_KeWaitForSingleObject
0x140066643  nop     dword ptr [rax+rax+00h]
0x140066648  mov     qword ptr [rbx-0B0h], 0
0x140066653  mov     rcx, [rbx-0A8h]
0x14006665a  call    AfdTlDereferenceTransport
0x14006665f  test    rdi, rdi
0x140066662  jz      loc_140066953
0x140066668  or      rax, 0FFFFFFFFFFFFFFFFh
0x14006666c  lock xadd [rdi+10h], rax
0x140066672  sub     rax, 1
0x140066676  jg      loc_140066953
0x14006667c  test    rax, rax
0x14006667f  jnz     loc_14006694C
0x140066685  mov     rcx, rdi; P
0x140066688  call    AfdFreeTransportInfo
0x14006668d  jmp     loc_140066953
0x140066692  mov     rax, [rbx+8]
0x140066696  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x14006669b  mov     rdx, [rax+0B8h]
0x1400666a2  mov     r15, [rdx+8]
0x1400666a6  mov     rdx, [rdx+10h]; SourceString
0x1400666aa  call    cs:__imp_RtlInitUnicodeString
0x1400666b1  nop     dword ptr [rax+rax+00h]
0x1400666b6  test    dword ptr [rbx-118h], 40000h
0x1400666c0  jz      loc_140066746
0x1400666c6  xorps   xmm0, xmm0
0x1400666c9  lea     rdx, Source; "\\Device\\RawIp"
0x1400666d0  xorps   xmm1, xmm1
0x1400666d3  lea     rcx, [rbp+57h+Object]; DestinationString
0x1400666d7  movups  xmmword ptr [rbp+57h+Object], xmm0
0x1400666db  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x1400666df  call    cs:__imp_RtlInitUnicodeString
0x1400666e6  nop     dword ptr [rax+rax+00h]
0x1400666eb  lea     rdx, aDeviceRawip6; "\\Device\\RawIp6"
0x1400666f2  lea     rcx, [rbp+57h+Event]; DestinationString
0x1400666f6  call    cs:__imp_RtlInitUnicodeString
0x1400666fd  nop     dword ptr [rax+rax+00h]
0x140066702  mov     r8b, 1; CaseInSensitive
0x140066705  lea     rdx, [rbp+57h+Object]; String2
0x140066709  lea     rcx, [rsp+120h+DestinationString]; String1
0x14006670e  call    cs:__imp_RtlEqualUnicodeString
0x140066715  nop     dword ptr [rax+rax+00h]
0x14006671a  test    al, al
0x14006671c  jnz     loc_1400667AB
0x140066722  mov     r8b, 1; CaseInSensitive
0x140066725  lea     rdx, [rbp+57h+Event]; String2
0x140066729  lea     rcx, [rsp+120h+DestinationString]; String1
0x14006672e  call    cs:__imp_RtlEqualUnicodeString
0x140066735  nop     dword ptr [rax+rax+00h]
0x14006673a  test    al, al
0x14006673c  jnz     short loc_1400667AB
0x14006673e  btr     dword ptr [rbx-118h], 12h
0x140066746  lea     rcx, [rsp+120h+DestinationString]; SourceString
0x14006674b  lea     rdx, [rsp+120h+var_F0]
0x140066750  call    AfdGetTransportInfo
0x140066755  mov     rdi, [rsp+120h+var_F0]
0x14006675a  mov     esi, eax
0x14006675c  test    eax, eax
0x14006675e  js      loc_140066593
0x140066764  mov     rcx, [rbx-100h]
0x14006676b  test    rcx, rcx
0x14006676e  jz      short loc_14006678E
0x140066770  test    dword ptr [rdi+48h], 100000h
0x140066777  jz      loc_140066849
0x14006677d  mov     edx, 1
0x140066782  call    cs:__imp_ObReferenceSecurityDescriptor
0x140066789  nop     dword ptr [rax+rax+00h]
0x14006678e  movzx   eax, word ptr [r15]
0x140066792  mov     ecx, 0ACE2h
0x140066797  cmp     ax, cx
0x14006679a  jnz     loc_140066853
0x1400667a0  mov     word ptr [r14], 0ACD2h
0x1400667a6  jmp     loc_14006687D
0x1400667ab  movzx   ecx, word ptr [rbx-10Ch]; Value
0x1400667b2  lea     r9, [rbp+57h+String]; String
0x1400667b6  mov     edx, 0Ah; Base
0x1400667bb  xorps   xmm0, xmm0
0x1400667be  movups  xmmword ptr [rsp+120h+Destination.Length], xmm0
0x1400667c3  lea     r8d, [rdx-4]; Length
0x1400667c7  call    cs:__imp_RtlIntegerToUnicode
0x1400667ce  nop     dword ptr [rax+rax+00h]
0x1400667d3  test    eax, eax
0x1400667d5  jz      short loc_1400667E1
0x1400667d7  mov     esi, 0C000000Dh
0x1400667dc  jmp     loc_140066593
0x1400667e1  xor     eax, eax
0x1400667e3  mov     dword ptr [rsp+120h+Destination.Length], 2C0000h
0x1400667eb  mov     [rbp+57h+var_86], ax
0x1400667ef  lea     rdx, [rsp+120h+DestinationString]; Source
0x1400667f4  mov     [rbp+57h+var_80], ax
0x1400667f8  lea     rcx, [rsp+120h+Destination]; Destination
0x1400667fd  lea     rax, [rbp+57h+var_80]
0x140066801  mov     [rsp+120h+Destination.Buffer], rax
0x140066806  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006680d  nop     dword ptr [rax+rax+00h]
0x140066812  lea     rdx, asc_14007E0D0; "\\"
0x140066819  lea     rcx, [rsp+120h+Destination]; Destination
0x14006681e  call    cs:__imp_RtlAppendUnicodeToString
0x140066825  nop     dword ptr [rax+rax+00h]
0x14006682a  lea     rdx, [rbp+57h+String]; Source
0x14006682e  lea     rcx, [rsp+120h+Destination]; Destination
0x140066833  call    cs:__imp_RtlAppendUnicodeToString
0x14006683a  nop     dword ptr [rax+rax+00h]
0x14006683f  lea     rcx, [rsp+120h+Destination]
0x140066844  jmp     loc_14006674B
0x140066849  mov     esi, 0C00000D7h
0x14006684e  jmp     loc_140066593
0x140066853  mov     ecx, 0ACE1h
0x140066858  cmp     ax, cx
0x14006685b  jnz     short loc_140066865
0x14006685d  mov     word ptr [r14], 0ACD1h
0x140066863  jmp     short loc_14006687D
0x140066865  mov     ecx, 0ACE3h
0x14006686a  cmp     ax, cx
0x14006686d  jnz     short loc_140066877
0x14006686f  mov     word ptr [r14], 0ACD3h
0x140066875  jmp     short loc_14006687D
0x140066877  mov     word ptr [r14], 0ACD0h
0x14006687d  lea     rcx, [rbx-120h]; SpinLock
0x140066884  mov     [rbx-10h], r15
0x140066888  call    cs:__imp_KeInitializeSpinLock
0x14006688f  nop     dword ptr [rax+rax+00h]
0x140066894  mov     r15d, 1
0x14006689a  mov     eax, 0ACD1h
0x14006689f  mov     [rbx-114h], r15d
0x1400668a6  mov     [rbx-110h], r15d
0x1400668ad  cmp     [r14], ax
0x1400668b1  jnz     short loc_1400668D9
0x1400668b3  lea     rcx, [rbx-98h]; SListHead
0x1400668ba  call    cs:__imp_InitializeSListHead
0x1400668c1  nop     dword ptr [rax+rax+00h]
0x1400668c6  lea     rcx, [rbx-88h]; SListHead
0x1400668cd  call    cs:__imp_InitializeSListHead
0x1400668d4  nop     dword ptr [rax+rax+00h]
0x1400668d9  test    dword ptr [rbx-118h], 200h
0x1400668e3  mov     [rbx-108h], rdi
0x1400668ea  jnz     short loc_14006690A
0x1400668ec  mov     rax, [rbx+10h]
0x1400668f0  lea     r9, WskTdiTLProviderEndpointDispatch
0x1400668f7  mov     rcx, [rbx+8]
0x1400668fb  mov     r8, r14
0x1400668fe  mov     edx, esi
0x140066900  call    _guard_dispatch_icall
0x140066905  jmp     loc_140066A28
0x14006690a  mov     rcx, [rbx-18h]; Process
0x14006690e  test    rcx, rcx
0x140066911  jz      short loc_140066929
0x140066913  cmp     r13, rcx
0x140066916  jz      short loc_140066929
0x140066918  call    cs:__imp_KeAttachProcess
0x14006691f  nop     dword ptr [rax+rax+00h]
0x140066924  mov     bl, r15b
0x140066927  jmp     short loc_14006692B
0x140066929  xor     bl, bl
0x14006692b  mov     rcx, r14
0x14006692e  call    WskTdiConnectCore
0x140066933  test    bl, bl
0x140066935  jz      loc_140066A28
0x14006693b  call    cs:__imp_KeDetachProcess
0x140066942  nop     dword ptr [rax+rax+00h]
0x140066947  jmp     loc_140066A28
0x14006694c  mov     ecx, 0Eh
0x140066951  int     29h; Win8: RtlFailFast(ecx)
0x140066953  test    dword ptr [rbx-118h], 200h
0x14006695d  jz      short loc_1400669CD
0x14006695f  mov     r8, [rbx-60h]
0x140066963  movzx   ecx, word ptr [r8]; af
0x140066967  call    SOCKADDR_SIZE
0x14006696c  movzx   edi, al
0x14006696f  cmp     edi, cs:AfdStandardAddressLength
0x140066975  ja      short loc_140066988
0x140066977  mov     rcx, cs:PplAddressPool
0x14006697e  mov     rdx, r8
0x140066981  call    PplFreeToLookasideList
0x140066986  jmp     short loc_14006699C
0x140066988  mov     edx, 52646641h; Tag
0x14006698d  mov     rcx, r8; P
0x140066990  call    cs:__imp_ExFreePoolWithTag
0x140066997  nop     dword ptr [rax+rax+00h]
0x14006699c  cmp     edi, cs:AfdStandardAddressLength
0x1400669a2  mov     rcx, [rbx-0F8h]; P
0x1400669a9  ja      short loc_1400669BC
0x1400669ab  mov     rdx, rcx
0x1400669ae  mov     rcx, cs:PplAddressPool
0x1400669b5  call    PplFreeToLookasideList
0x1400669ba  jmp     short loc_1400669CD
0x1400669bc  mov     edx, 52646641h; Tag
0x1400669c1  call    cs:__imp_ExFreePoolWithTag
0x1400669c8  nop     dword ptr [rax+rax+00h]
0x1400669cd  mov     rax, [rbx+10h]
0x1400669d1  xor     r9d, r9d
0x1400669d4  mov     rcx, [rbx+8]
0x1400669d8  xor     r8d, r8d
0x1400669db  mov     edx, esi
0x1400669dd  call    _guard_dispatch_icall
0x1400669e2  mov     rbx, [rbx-18h]
0x1400669e6  mov     edx, 744B5357h; Tag
0x1400669eb  mov     rcx, r14; P
0x1400669ee  call    cs:__imp_ExFreePoolWithTag
0x1400669f5  nop     dword ptr [rax+rax+00h]
0x1400669fa  test    rbx, rbx
0x1400669fd  jz      short loc_140066A28
0x1400669ff  mov     edx, 200h; PoolType
0x140066a04  mov     r8d, 140h; Amount
0x140066a0a  mov     rcx, rbx; Process
0x140066a0d  call    cs:__imp_PsReturnPoolQuota
0x140066a14  nop     dword ptr [rax+rax+00h]
0x140066a19  mov     rcx, rbx; Object
0x140066a1c  call    cs:__imp_ObfDereferenceObject
0x140066a23  nop     dword ptr [rax+rax+00h]
0x140066a28  mov     rbx, r12
0x140066a2b  test    r12, r12
0x140066a2e  jnz     loc_140066559
0x140066a34  mov     rcx, [rbp+57h+var_50]
0x140066a38  xor     rcx, rsp; StackCookie
0x140066a3b  call    __security_check_cookie
0x140066a40  add     rsp, 0E8h
0x140066a47  pop     r15
0x140066a49  pop     r14
0x140066a4b  pop     r13
0x140066a4d  pop     r12
0x140066a4f  pop     rdi
0x140066a50  pop     rsi
0x140066a51  pop     rbx
0x140066a52  pop     rbp
0x140066a53  retn
```

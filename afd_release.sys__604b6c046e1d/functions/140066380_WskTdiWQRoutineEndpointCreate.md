# WskTdiWQRoutineEndpointCreate

- ea: `0x140066380`
- end: `0x1400668b5`
- name: `WskTdiWQRoutineEndpointCreate`
- size: `1333`
- prototype: `void __fastcall(__int64 *, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140064340`
- `0x140064580`
- `0x140064b60`

## callees

- `0x140005b60`
- `0x14000f980`
- `0x140013030`
- `0x140037374`
- `0x14003ffbc`
- `0x140047950`
- `0x140066380`
- `0x1400726a0`
- `0x140072780`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140066444`
- `ntoskrnl!KeInitializeEvent` at `0x140066444`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006649c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006649c`
- `ntoskrnl!PsReturnPoolQuota` at `0x14006686d`
- `ntoskrnl!PsReturnPoolQuota` at `0x14006686d`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400663aa`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400663aa`
- `ntoskrnl!KeAttachProcess` at `0x140066778`
- `ntoskrnl!KeAttachProcess` at `0x140066778`
- `ntoskrnl!KeDetachProcess` at `0x14006679b`
- `ntoskrnl!KeDetachProcess` at `0x14006679b`
- `ntoskrnl!RtlIntegerToUnicode` at `0x140066627`
- `ntoskrnl!RtlIntegerToUnicode` at `0x140066627`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140066666`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140066666`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x1400665e2`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x1400665e2`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006667e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140066693`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14006667e`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140066693`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006656e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006658e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006656e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14006658e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006650a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006653f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140066556`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006650a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14006653f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140066556`
- `ntoskrnl!InitializeSListHead` at `0x14006671a`
- `ntoskrnl!InitializeSListHead` at `0x14006672d`
- `ntoskrnl!InitializeSListHead` at `0x14006671a`
- `ntoskrnl!InitializeSListHead` at `0x14006672d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400666e8`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400666e8`
- `ntoskrnl!ObfDereferenceObject` at `0x14006687c`
- `ntoskrnl!ObfDereferenceObject` at `0x14006687c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400667f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066821`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006684e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400667f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066821`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006684e`

## pseudocode

```c
void __fastcall WskTdiWQRoutineEndpointCreate(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 *v4; // rbx
  __int64 CurrentProcess; // r13
  __int64 v6; // rdi
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
        v11 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v6 + 16), 0xFFFFFFFFFFFFFFFFuLL);
        v12 = v11 <= 1;
        v13 = v11 - 1;
        if ( v12 )
        {
          if ( v13 )
            __fastfail(0xEu);
          AfdFreeTransportInfo((_QWORD *)v6);
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
    v6 = v27;
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
    *(v4 - 33) = v6;
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
0x140066380  push    rbp
0x140066382  push    rbx
0x140066383  push    rsi
0x140066384  push    rdi
0x140066385  push    r12
0x140066387  push    r13
0x140066389  push    r14
0x14006638b  push    r15
0x14006638d  lea     rbp, [rsp-1Fh]
0x140066392  sub     rsp, 0E8h
0x140066399  mov     rax, cs:__security_cookie
0x1400663a0  xor     rax, rsp
0x1400663a3  mov     [rbp+57h+var_50], rax
0x1400663a7  mov     rbx, rcx
0x1400663aa  call    cs:__imp_PsGetCurrentProcess
0x1400663b1  nop     dword ptr [rax+rax+00h]
0x1400663b6  mov     r13, rax
0x1400663b9  xor     edi, edi
0x1400663bb  lea     r14, [rbx-128h]
0x1400663c2  xorps   xmm0, xmm0
0x1400663c5  mov     [rsp+120h+var_F0], rdi
0x1400663ca  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x1400663cf  mov     eax, [rbx-118h]
0x1400663d5  mov     r12, [rbx]
0x1400663d8  test    al, 1
0x1400663da  jz      loc_1400664F2
0x1400663e0  cmp     [rbx-0B0h], rdi
0x1400663e7  jnz     loc_1400664F2
0x1400663ed  mov     esi, [rbx-0B8h]
0x1400663f3  mov     eax, [rbx-118h]
0x1400663f9  test    al, 1
0x1400663fb  jz      loc_1400664BF
0x140066401  cmp     qword ptr [rbx-0B0h], 0
0x140066409  jz      loc_1400664B3
0x14006640f  xor     eax, eax
0x140066411  mov     [rbp+57h+var_98], 0
0x140066419  xorps   xmm0, xmm0
0x14006641c  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x140066420  xor     r8d, r8d; State
0x140066423  lea     rax, [rbp+57h+Event]
0x140066427  xorps   xmm1, xmm1
0x14006642a  mov     qword ptr [rbp+57h+Object], rax
0x14006642e  lea     rcx, [rbp+57h+Event]; Event
0x140066432  movdqu  xmmword ptr [rbp+57h+Object+8], xmm0
0x140066437  lea     edx, [r8+1]; Type
0x14006643b  movups  xmmword ptr [rsp+120h+Destination.Length], xmm0
0x140066440  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x140066444  call    cs:__imp_KeInitializeEvent
0x14006644b  nop     dword ptr [rax+rax+00h]
0x140066450  mov     rcx, [rbx-0B8h]
0x140066457  lea     rax, AfdSynchronousTlCloseRequestComplete
0x14006645e  mov     qword ptr [rsp+120h+Destination.Length], rax
0x140066463  lea     rdx, [rsp+120h+Destination]
0x140066468  lea     rax, [rbp+57h+Object]
0x14006646c  mov     [rsp+120h+Destination.Buffer], rax
0x140066471  mov     rax, [rbx-0B0h]
0x140066478  mov     rax, [rax]
0x14006647b  call    _guard_dispatch_icall
0x140066480  cmp     eax, 103h
0x140066485  jnz     short loc_1400664A8
0x140066487  mov     rcx, qword ptr [rbp+57h+Object]; Object
0x14006648b  xor     r9d, r9d; Alertable
0x14006648e  xor     r8d, r8d; WaitMode
0x140066491  mov     [rsp+120h+Timeout], 0; Timeout
0x14006649a  xor     edx, edx; WaitReason
0x14006649c  call    cs:__imp_KeWaitForSingleObject
0x1400664a3  nop     dword ptr [rax+rax+00h]
0x1400664a8  mov     qword ptr [rbx-0B0h], 0
0x1400664b3  mov     rcx, [rbx-0A8h]
0x1400664ba  call    AfdTlDereferenceTransport
0x1400664bf  test    rdi, rdi
0x1400664c2  jz      loc_1400667B3
0x1400664c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400664cc  lock xadd [rdi+10h], rax
0x1400664d2  sub     rax, 1
0x1400664d6  jg      loc_1400667B3
0x1400664dc  test    rax, rax
0x1400664df  jnz     loc_1400667AC
0x1400664e5  mov     rcx, rdi; P
0x1400664e8  call    AfdFreeTransportInfo
0x1400664ed  jmp     loc_1400667B3
0x1400664f2  mov     rax, [rbx+8]
0x1400664f6  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x1400664fb  mov     rdx, [rax+0B8h]
0x140066502  mov     r15, [rdx+8]
0x140066506  mov     rdx, [rdx+10h]; SourceString
0x14006650a  call    cs:__imp_RtlInitUnicodeString
0x140066511  nop     dword ptr [rax+rax+00h]
0x140066516  test    dword ptr [rbx-118h], 40000h
0x140066520  jz      loc_1400665A6
0x140066526  xorps   xmm0, xmm0
0x140066529  lea     rdx, Source; "\\Device\\RawIp"
0x140066530  xorps   xmm1, xmm1
0x140066533  lea     rcx, [rbp+57h+Object]; DestinationString
0x140066537  movups  xmmword ptr [rbp+57h+Object], xmm0
0x14006653b  movups  xmmword ptr [rbp+57h+Event.Header], xmm1
0x14006653f  call    cs:__imp_RtlInitUnicodeString
0x140066546  nop     dword ptr [rax+rax+00h]
0x14006654b  lea     rdx, aDeviceRawip6; "\\Device\\RawIp6"
0x140066552  lea     rcx, [rbp+57h+Event]; DestinationString
0x140066556  call    cs:__imp_RtlInitUnicodeString
0x14006655d  nop     dword ptr [rax+rax+00h]
0x140066562  mov     r8b, 1; CaseInSensitive
0x140066565  lea     rdx, [rbp+57h+Object]; String2
0x140066569  lea     rcx, [rsp+120h+DestinationString]; String1
0x14006656e  call    cs:__imp_RtlEqualUnicodeString
0x140066575  nop     dword ptr [rax+rax+00h]
0x14006657a  test    al, al
0x14006657c  jnz     loc_14006660B
0x140066582  mov     r8b, 1; CaseInSensitive
0x140066585  lea     rdx, [rbp+57h+Event]; String2
0x140066589  lea     rcx, [rsp+120h+DestinationString]; String1
0x14006658e  call    cs:__imp_RtlEqualUnicodeString
0x140066595  nop     dword ptr [rax+rax+00h]
0x14006659a  test    al, al
0x14006659c  jnz     short loc_14006660B
0x14006659e  btr     dword ptr [rbx-118h], 12h
0x1400665a6  lea     rcx, [rsp+120h+DestinationString]; SourceString
0x1400665ab  lea     rdx, [rsp+120h+var_F0]
0x1400665b0  call    AfdGetTransportInfo
0x1400665b5  mov     rdi, [rsp+120h+var_F0]
0x1400665ba  mov     esi, eax
0x1400665bc  test    eax, eax
0x1400665be  js      loc_1400663F3
0x1400665c4  mov     rcx, [rbx-100h]
0x1400665cb  test    rcx, rcx
0x1400665ce  jz      short loc_1400665EE
0x1400665d0  test    dword ptr [rdi+48h], 100000h
0x1400665d7  jz      loc_1400666A9
0x1400665dd  mov     edx, 1
0x1400665e2  call    cs:__imp_ObReferenceSecurityDescriptor
0x1400665e9  nop     dword ptr [rax+rax+00h]
0x1400665ee  movzx   eax, word ptr [r15]
0x1400665f2  mov     ecx, 0ACE2h
0x1400665f7  cmp     ax, cx
0x1400665fa  jnz     loc_1400666B3
0x140066600  mov     word ptr [r14], 0ACD2h
0x140066606  jmp     loc_1400666DD
0x14006660b  movzx   ecx, word ptr [rbx-10Ch]; Value
0x140066612  lea     r9, [rbp+57h+String]; String
0x140066616  mov     edx, 0Ah; Base
0x14006661b  xorps   xmm0, xmm0
0x14006661e  movups  xmmword ptr [rsp+120h+Destination.Length], xmm0
0x140066623  lea     r8d, [rdx-4]; Length
0x140066627  call    cs:__imp_RtlIntegerToUnicode
0x14006662e  nop     dword ptr [rax+rax+00h]
0x140066633  test    eax, eax
0x140066635  jz      short loc_140066641
0x140066637  mov     esi, 0C000000Dh
0x14006663c  jmp     loc_1400663F3
0x140066641  xor     eax, eax
0x140066643  mov     dword ptr [rsp+120h+Destination.Length], 2C0000h
0x14006664b  mov     [rbp+57h+var_86], ax
0x14006664f  lea     rdx, [rsp+120h+DestinationString]; Source
0x140066654  mov     [rbp+57h+var_80], ax
0x140066658  lea     rcx, [rsp+120h+Destination]; Destination
0x14006665d  lea     rax, [rbp+57h+var_80]
0x140066661  mov     [rsp+120h+Destination.Buffer], rax
0x140066666  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006666d  nop     dword ptr [rax+rax+00h]
0x140066672  lea     rdx, asc_14007E0C8; "\\"
0x140066679  lea     rcx, [rsp+120h+Destination]; Destination
0x14006667e  call    cs:__imp_RtlAppendUnicodeToString
0x140066685  nop     dword ptr [rax+rax+00h]
0x14006668a  lea     rdx, [rbp+57h+String]; Source
0x14006668e  lea     rcx, [rsp+120h+Destination]; Destination
0x140066693  call    cs:__imp_RtlAppendUnicodeToString
0x14006669a  nop     dword ptr [rax+rax+00h]
0x14006669f  lea     rcx, [rsp+120h+Destination]
0x1400666a4  jmp     loc_1400665AB
0x1400666a9  mov     esi, 0C00000D7h
0x1400666ae  jmp     loc_1400663F3
0x1400666b3  mov     ecx, 0ACE1h
0x1400666b8  cmp     ax, cx
0x1400666bb  jnz     short loc_1400666C5
0x1400666bd  mov     word ptr [r14], 0ACD1h
0x1400666c3  jmp     short loc_1400666DD
0x1400666c5  mov     ecx, 0ACE3h
0x1400666ca  cmp     ax, cx
0x1400666cd  jnz     short loc_1400666D7
0x1400666cf  mov     word ptr [r14], 0ACD3h
0x1400666d5  jmp     short loc_1400666DD
0x1400666d7  mov     word ptr [r14], 0ACD0h
0x1400666dd  lea     rcx, [rbx-120h]; SpinLock
0x1400666e4  mov     [rbx-10h], r15
0x1400666e8  call    cs:__imp_KeInitializeSpinLock
0x1400666ef  nop     dword ptr [rax+rax+00h]
0x1400666f4  mov     r15d, 1
0x1400666fa  mov     eax, 0ACD1h
0x1400666ff  mov     [rbx-114h], r15d
0x140066706  mov     [rbx-110h], r15d
0x14006670d  cmp     [r14], ax
0x140066711  jnz     short loc_140066739
0x140066713  lea     rcx, [rbx-98h]; SListHead
0x14006671a  call    cs:__imp_InitializeSListHead
0x140066721  nop     dword ptr [rax+rax+00h]
0x140066726  lea     rcx, [rbx-88h]; SListHead
0x14006672d  call    cs:__imp_InitializeSListHead
0x140066734  nop     dword ptr [rax+rax+00h]
0x140066739  test    dword ptr [rbx-118h], 200h
0x140066743  mov     [rbx-108h], rdi
0x14006674a  jnz     short loc_14006676A
0x14006674c  mov     rax, [rbx+10h]
0x140066750  lea     r9, WskTdiTLProviderEndpointDispatch
0x140066757  mov     rcx, [rbx+8]
0x14006675b  mov     r8, r14
0x14006675e  mov     edx, esi
0x140066760  call    _guard_dispatch_icall
0x140066765  jmp     loc_140066888
0x14006676a  mov     rcx, [rbx-18h]; Process
0x14006676e  test    rcx, rcx
0x140066771  jz      short loc_140066789
0x140066773  cmp     r13, rcx
0x140066776  jz      short loc_140066789
0x140066778  call    cs:__imp_KeAttachProcess
0x14006677f  nop     dword ptr [rax+rax+00h]
0x140066784  mov     bl, r15b
0x140066787  jmp     short loc_14006678B
0x140066789  xor     bl, bl
0x14006678b  mov     rcx, r14
0x14006678e  call    WskTdiConnectCore
0x140066793  test    bl, bl
0x140066795  jz      loc_140066888
0x14006679b  call    cs:__imp_KeDetachProcess
0x1400667a2  nop     dword ptr [rax+rax+00h]
0x1400667a7  jmp     loc_140066888
0x1400667ac  mov     ecx, 0Eh
0x1400667b1  int     29h; Win8: RtlFailFast(ecx)
0x1400667b3  test    dword ptr [rbx-118h], 200h
0x1400667bd  jz      short loc_14006682D
0x1400667bf  mov     r8, [rbx-60h]
0x1400667c3  movzx   ecx, word ptr [r8]; af
0x1400667c7  call    SOCKADDR_SIZE
0x1400667cc  movzx   edi, al
0x1400667cf  cmp     edi, cs:AfdStandardAddressLength
0x1400667d5  ja      short loc_1400667E8
0x1400667d7  mov     rcx, cs:PplAddressPool
0x1400667de  mov     rdx, r8
0x1400667e1  call    PplFreeToLookasideList
0x1400667e6  jmp     short loc_1400667FC
0x1400667e8  mov     edx, 52646641h; Tag
0x1400667ed  mov     rcx, r8; P
0x1400667f0  call    cs:__imp_ExFreePoolWithTag
0x1400667f7  nop     dword ptr [rax+rax+00h]
0x1400667fc  cmp     edi, cs:AfdStandardAddressLength
0x140066802  mov     rcx, [rbx-0F8h]; P
0x140066809  ja      short loc_14006681C
0x14006680b  mov     rdx, rcx
0x14006680e  mov     rcx, cs:PplAddressPool
0x140066815  call    PplFreeToLookasideList
0x14006681a  jmp     short loc_14006682D
0x14006681c  mov     edx, 52646641h; Tag
0x140066821  call    cs:__imp_ExFreePoolWithTag
0x140066828  nop     dword ptr [rax+rax+00h]
0x14006682d  mov     rax, [rbx+10h]
0x140066831  xor     r9d, r9d
0x140066834  mov     rcx, [rbx+8]
0x140066838  xor     r8d, r8d
0x14006683b  mov     edx, esi
0x14006683d  call    _guard_dispatch_icall
0x140066842  mov     rbx, [rbx-18h]
0x140066846  mov     edx, 744B5357h; Tag
0x14006684b  mov     rcx, r14; P
0x14006684e  call    cs:__imp_ExFreePoolWithTag
0x140066855  nop     dword ptr [rax+rax+00h]
0x14006685a  test    rbx, rbx
0x14006685d  jz      short loc_140066888
0x14006685f  mov     edx, 200h; PoolType
0x140066864  mov     r8d, 140h; Amount
0x14006686a  mov     rcx, rbx; Process
0x14006686d  call    cs:__imp_PsReturnPoolQuota
0x140066874  nop     dword ptr [rax+rax+00h]
0x140066879  mov     rcx, rbx; Object
0x14006687c  call    cs:__imp_ObfDereferenceObject
0x140066883  nop     dword ptr [rax+rax+00h]
0x140066888  mov     rbx, r12
0x14006688b  test    r12, r12
0x14006688e  jnz     loc_1400663B9
0x140066894  mov     rcx, [rbp+57h+var_50]
0x140066898  xor     rcx, rsp; StackCookie
0x14006689b  call    __security_check_cookie
0x1400668a0  add     rsp, 0E8h
0x1400668a7  pop     r15
0x1400668a9  pop     r14
0x1400668ab  pop     r13
0x1400668ad  pop     r12
0x1400668af  pop     rdi
0x1400668b0  pop     rsi
0x1400668b1  pop     rbx
0x1400668b2  pop     rbp
0x1400668b3  retn
```

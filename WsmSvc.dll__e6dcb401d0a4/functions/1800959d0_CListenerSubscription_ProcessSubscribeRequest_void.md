# CListenerSubscription::ProcessSubscribeRequest(void)

- ea: `0x1800959d0`
- end: `0x180096263`
- name: `?ProcessSubscribeRequest@CListenerSubscription@@AEAAHXZ`
- size: `2195`
- prototype: `__int64 __fastcall(CListenerSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18017e660`

## callees

- `0x180005d10`
- `0x180013760`
- `0x180028038`
- `0x18002b7a0`
- `0x18005a5b0`
- `0x1800621e0`
- `0x1800951bc`
- `0x18009524c`
- `0x1800959d0`
- `0x1800973c0`
- `0x1800ac320`
- `0x1800dab88`
- `0x1800db34c`
- `0x1800db5a0`
- `0x1800f3f24`
- `0x1800fbd00`
- `0x1800fe670`
- `0x1800ff678`
- `0x180112380`
- `0x1801123a8`
- `0x180112460`
- `0x1801133b0`
- `0x18011a6d4`
- `0x1801557d0`
- `0x18017e8ac`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_scwprintf` at `0x180095fd2`
- `msvcrt!_scwprintf` at `0x180095fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095a62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095e1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095a62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095c23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095e1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180095a3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180095a84`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180095a3d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180095a84`
- `SspiCli!GetUserNameExW` at `0x180095c1b`
- `SspiCli!GetUserNameExW` at `0x180095d0e`
- `SspiCli!GetUserNameExW` at `0x180095c1b`
- `SspiCli!GetUserNameExW` at `0x180095d0e`

## string_xrefs

- `0x180095bfb`: `http://schemas.microsoft.com/wbem/wsman/1/windows/EventLog`
- `0x180095ae6`: `onecore\admin\wmi\wmx\service\listenersubscribe.cpp`
- `0x180095fcb`: `<w:DroppedEvents xmlns:w="http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd" Action="http://schemas.dmtf.org/wbem/wsman/1/wsman/Event">%ld</w:DroppedEvents>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CListenerSubscription::ProcessSubscribeRequest(CListenerSubscription *this)
{
  __int64 v2; // rsi
  __int64 v3; // r14
  HANDLE EventW; // rax
  void (__fastcall *v5)(__int64, _QWORD); // rbx
  DWORD LastError; // eax
  __int64 v7; // rcx
  HANDLE v8; // rax
  struct IRequestContext *v9; // r8
  __int64 v10; // rax
  unsigned int *v11; // r14
  unsigned int *v12; // r12
  struct FWXML_ELEMENT_LIST *v13; // rdx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  const WCHAR *v16; // rax
  wchar_t *Value; // rbx
  _DWORD *v18; // rcx
  unsigned int v19; // edx
  __int64 v20; // r15
  BOOLEAN UserName; // bl
  DWORD v22; // eax
  DWORD v23; // esi
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 *v27; // rbx
  DWORD v28; // ebx
  __int64 v29; // r9
  struct CWSManEventSession *v30; // rax
  __int64 v31; // rdi
  unsigned int v32; // r8d
  __int64 v33; // rcx
  unsigned int v34; // r8d
  unsigned int v35; // edx
  unsigned int v36; // ebx
  unsigned int v37; // eax
  int v38; // edx
  __int64 v39; // rax
  void (__fastcall ***v40)(_QWORD); // rcx
  __int64 v41; // rax
  __int64 v43; // rcx
  struct _WSMAN_AUTHENTICATION_CREDENTIALS v44; // [rsp+60h] [rbp-9h] BYREF
  ULONG nSize; // [rsp+D0h] [rbp+67h] BYREF
  unsigned __int16 *v46; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned __int16 *v47; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int16 *v48; // [rsp+E8h] [rbp+7Fh] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids, this);
  v2 = *((_QWORD *)this + 263);
  v3 = *((_QWORD *)this + 19);
  EventW = CreateEventW(0, 1, 1, 0);
  AutoHandle::operator=((char *)this + 2968, EventW);
  if ( !*((_QWORD *)this + 371)
    || (v8 = CreateEventW(0, 0, 0, 0), AutoHandle::operator=((char *)this + 2984, v8), !*((_QWORD *)this + 373)) )
  {
    v5 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 72LL);
    LastError = GetLastError();
    v7 = v2;
LABEL_6:
    v5(v7, LastError);
    return 0;
  }
  *((_QWORD *)this + 372) = v3;
  *((_DWORD *)this + 762) = 0;
  *((_DWORD *)this + 763) = 0;
  *((_BYTE *)this + 3056) = 0;
  v9 = (struct IRequestContext *)*((_QWORD *)this + 263);
  *((_DWORD *)this + 760) = 1;
  if ( !v9 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\listenersubscribe.cpp", 105, L"105", 0x54Fu, 0);
    return 0;
  }
  v10 = *((_QWORD *)this + 32);
  v11 = (unsigned int *)((char *)this + 2440);
  v12 = (unsigned int *)((char *)this + 2872);
  v47 = 0;
  v13 = (struct FWXML_ELEMENT_LIST *)(*(_QWORD *)(v10 + 2736) + 128LL);
  v48 = 0;
  v46 = 0;
  if ( !(unsigned int)CListenerSubscription::ExtractSubscriptionParams(
                        this,
                        v13,
                        (const unsigned __int16 **)&v47,
                        (const unsigned __int16 **)&v48,
                        (const unsigned __int16 **)&v46,
                        (unsigned int *)this + 623,
                        (CListenerSubscription *)((char *)this + 2500),
                        (union _ULARGE_INTEGER *)this + 359,
                        v9) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return 0;
    v15 = 13;
    goto LABEL_91;
  }
  if ( (*(_BYTE *)v11 & 0x10) != 0 )
    goto LABEL_68;
  *((_QWORD *)this + 308) = (char *)this + 2532;
  v16 = (const WCHAR *)*((_QWORD *)this + 328);
  memset(&v44, 0, sizeof(v44));
  if ( v16 )
  {
    v44.authenticationMechanism = 32;
    v44.userAccount.username = v16;
  }
  Value = 0;
  v18 = (_DWORD *)(*((_QWORD *)this + 32) + 3024LL);
  nSize = 0;
  if ( *v18 )
    Value = (wchar_t *)PacketParser::PacketElement<unsigned short const *>::GetValue(v18);
  v20 = -1;
  if ( !(*(unsigned __int8 (__fastcall **)(CListenerSubscription *))(*(_QWORD *)this + 272LL))(this)
    && !(unsigned int)StringCchStartsWithCI(
                        Value,
                        (wchar_t *)L"http://schemas.microsoft.com/wbem/wsman/1/windows/EventLog") )
  {
    UserName = GetUserNameExW(NameUserPrincipal, 0, &nSize);
    v22 = GetLastError();
    v23 = v22;
    if ( UserName || v22 == 234 )
    {
      v25 = 2LL * nSize;
      if ( !is_mul_ok(nSize, 2u) )
        v25 = -1;
      v26 = WSManMemory::Alloc(v25, 0, 0);
      v27 = (__int64 *)((char *)this + 2632);
      AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=((char *)this + 2632, v26);
      if ( !*((_QWORD *)this + 329) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 263) + 24LL))(*((_QWORD *)this + 263));
        return 0;
      }
      if ( !GetUserNameExW(NameUserPrincipal, *((LPWSTR *)this + 329), &nSize) )
      {
        v28 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids);
        v24 = v28;
        goto LABEL_28;
      }
      v29 = *v27;
      *((_QWORD *)this + 307) = *v27;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids, v29);
      goto LABEL_47;
    }
    if ( v22 != 1332 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids);
      v24 = v23;
LABEL_28:
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 263) + 72LL))(*((_QWORD *)this + 263), v24);
      return 0;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids);
LABEL_47:
  v30 = CWSManEventSession::CreateNewCWSManEventSession(*((_DWORD *)this + 632), v19, &v44, (char *)this + 2440);
  *((_QWORD *)this + 315) = v30;
  if ( !v30 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids);
    v31 = *((_QWORD *)this + 263);
    v5 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v31 + 72LL);
    LastError = GetLastError();
    v7 = v31;
    goto LABEL_6;
  }
  if ( !CListenerSubscription::VerifyConnectivity(this, *((struct CRequestContext **)this + 263), v30) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids);
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 263) + 72LL))(*((_QWORD *)this + 263), 2150858901LL);
LABEL_57:
    CWSManEventSession::CloseEventSession(
      *((CWSManEventSession **)this + 315),
      *((struct CRequestContext **)this + 263),
      v32);
    *((_QWORD *)this + 315) = 0;
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids);
  CWSManEventSession::SetMasterOperation(*((CWSManEventSession **)this + 315), this);
  Locale::operator=(*((_QWORD *)this + 315) + 64LL, *((_QWORD *)this + 263) + 492LL);
  v33 = *((_QWORD *)this + 315);
  v34 = *((_DWORD *)this + 661);
  v35 = *((_DWORD *)this + 660);
  *(_DWORD *)(v33 + 1464) = v35;
  *(_DWORD *)(v33 + 1468) = v34;
  CRemoteOperation::SetRetry(*(CRemoteOperation **)(v33 + 1128), v35, v34);
  v36 = CWSManEventSession::ComputeMaximumPacketOverhead(
          *((CWSManEventSession **)this + 315),
          *((struct IRequestContext **)this + 263),
          *v11);
  if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 263) + 144LL))(*((_QWORD *)this + 263)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 263) + 152LL))(*((_QWORD *)this + 263));
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids, v37);
    }
    goto LABEL_57;
  }
  *((_DWORD *)this + 622) = CWSManEventSession::ComputeMaximumPerEventOverhead(
                              *((CWSManEventSession **)this + 315),
                              *v11);
  v38 = 2
      * _scwprintf(
          L"<w:DroppedEvents xmlns:w=\"http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd\" Action=\"http://schemas.dmtf.org/w"
           "bem/wsman/1/wsman/Event\">%ld</w:DroppedEvents>",
          0xFFFFFFFFLL);
  do
    ++v20;
  while ( *(_WORD *)(*((_QWORD *)this + 309) + 2 * v20) );
  *((_DWORD *)this + 625) += -2 - 2 * v20 - v36 - v38;
LABEL_68:
  CListenerMasterOperation::GenerateNextSoapContext(this);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    v39 = PacketParser::PacketElement<unsigned short const *>::GetValue(*((_QWORD *)this + 32) + 3024LL);
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids, v39);
  }
  v40 = (void (__fastcall ***)(_QWORD))*((_QWORD *)this + 315);
  if ( v40 )
    (**v40)(v40);
  v41 = *((_QWORD *)this + 151);
  *((_QWORD *)this + 331) = 0;
  if ( !(*(unsigned int (__fastcall **)(_QWORD, unsigned __int64, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, _QWORD, char *, _QWORD, char *, char *))(*(_QWORD *)(v41 + 16) + dword_18027E228))(
          *v11,
          ((unsigned __int64)this + 112) & -(__int64)(this != 0),
          v48,
          v47,
          v46,
          *((_QWORD *)this + 326),
          (char *)this + 2500,
          *((_QWORD *)this + 315),
          (char *)this + 2648,
          (char *)this + 2416) )
  {
    (*(void (__fastcall **)(_QWORD, char *, _QWORD, _QWORD))(**((_QWORD **)this + 263) + 104LL))(
      *((_QWORD *)this + 263),
      (char *)this + 2424,
      **(_QWORD **)(*((_QWORD *)this + 151) + 16LL),
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 151) + 16LL) + 8LL));
LABEL_94:
    v43 = *((_QWORD *)this + 315);
    if ( v43 )
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v43 + 8LL))(v43, 0, 0);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids);
  Timer::StopTimer((CListenerSubscription *)((char *)this + 32));
  if ( *((_DWORD *)this + 98) )
    goto LABEL_94;
  if ( (*(_BYTE *)v11 & 0x10) != 0
    && !Timer::StartTimer((char *)this + 3064, *((struct IRequestContext **)this + 263), *((_DWORD *)this + 623)) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
      return 0;
    v15 = 25;
    goto LABEL_91;
  }
  CListenerSubscription::SendSubscribeResponse(this);
  if ( !*v12 )
    return 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids, this, *v12);
  if ( Timer::StartTimer((char *)this + 3152, *((struct IRequestContext **)this + 263), *v12) )
    return 1;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    v15 = 27;
LABEL_91:
    WPP_SF_(v14[2], v15, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1800959d0  push    rbp
0x1800959d2  push    rbx
0x1800959d3  push    rsi
0x1800959d4  push    rdi
0x1800959d5  push    r12
0x1800959d7  push    r13
0x1800959d9  push    r14
0x1800959db  push    r15
0x1800959dd  lea     rbp, [rsp-1Fh]
0x1800959e2  sub     rsp, 88h
0x1800959e9  mov     rdi, rcx
0x1800959ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800959f3  lea     r15, WPP_GLOBAL_Control
0x1800959fa  cmp     rcx, r15
0x1800959fd  jz      short loc_180095A20
0x1800959ff  test    dword ptr [rcx+1Ch], 400h
0x180095a06  jz      short loc_180095A20
0x180095a08  mov     rcx, [rcx+10h]
0x180095a0c  lea     r8, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids
0x180095a13  mov     edx, 0Ch
0x180095a18  mov     r9, rdi
0x180095a1b  call    WPP_SF_q
0x180095a20  mov     rsi, [rdi+838h]
0x180095a27  xor     r9d, r9d; lpName
0x180095a2a  mov     r14, [rdi+98h]
0x180095a31  xor     ecx, ecx; lpEventAttributes
0x180095a33  lea     r12d, [r9+1]
0x180095a37  mov     r8d, r12d; bInitialState
0x180095a3a  mov     edx, r12d; bManualReset
0x180095a3d  call    cs:__imp_CreateEventW
0x180095a43  lea     rbx, [rdi+0B98h]
0x180095a4a  mov     rdx, rax
0x180095a4d  mov     rcx, rbx
0x180095a50  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x180095a55  cmp     qword ptr [rbx], 0
0x180095a59  jnz     short loc_180095A7A
0x180095a5b  mov     rax, [rsi]
0x180095a5e  mov     rbx, [rax+48h]
0x180095a62  call    cs:__imp_GetLastError
0x180095a68  mov     rcx, rsi
0x180095a6b  mov     edx, eax
0x180095a6d  mov     rax, rbx
0x180095a70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095a75  jmp     loc_18009624D
0x180095a7a  xor     r9d, r9d; lpName
0x180095a7d  xor     r8d, r8d; bInitialState
0x180095a80  xor     edx, edx; bManualReset
0x180095a82  xor     ecx, ecx; lpEventAttributes
0x180095a84  call    cs:__imp_CreateEventW
0x180095a8a  lea     rbx, [rdi+0BA8h]
0x180095a91  mov     rdx, rax
0x180095a94  mov     rcx, rbx
0x180095a97  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x180095a9c  cmp     qword ptr [rbx], 0
0x180095aa0  jz      short loc_180095A5B
0x180095aa2  mov     [rdi+0BA0h], r14
0x180095aa9  xor     esi, esi
0x180095aab  mov     [rdi+0BE8h], esi
0x180095ab1  mov     [rdi+0BECh], esi
0x180095ab7  mov     [rdi+0BF0h], sil
0x180095abe  mov     r8, [rdi+838h]
0x180095ac5  mov     [rdi+0BE0h], r12d
0x180095acc  test    r8, r8
0x180095acf  jnz     short loc_180095AF7
0x180095ad1  mov     r9d, 54Fh; unsigned int
0x180095ad7  mov     [rsp+0C0h+var_A0], rsi; struct IRequestContext *
0x180095adc  lea     r8, a105; "105"
0x180095ae3  lea     edx, [rsi+69h]; unsigned int
0x180095ae6  lea     rcx, aOnecoreAdminWm_81; "onecore\\admin\\wmi\\wmx\\service\\list"...
0x180095aed  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x180095af2  jmp     loc_18009624D
0x180095af7  mov     rax, [rdi+100h]
0x180095afe  lea     r14, [rdi+988h]
0x180095b05  mov     [rsp+0C0h+var_80], r8; struct IRequestContext *
0x180095b0a  lea     rcx, [r14+34h]
0x180095b0e  lea     r12, [rdi+0B38h]
0x180095b15  mov     [rbp+57h+arg_10], rsi
0x180095b19  mov     [rsp+0C0h+var_88], r12; union _ULARGE_INTEGER *
0x180095b1e  lea     r13, [r14+3Ch]
0x180095b22  mov     rdx, [rax+0AB0h]
0x180095b29  lea     r9, [rbp+57h+arg_18]; unsigned __int16 **
0x180095b2d  mov     [rsp+0C0h+var_90], r13; struct _WSMAN_BATCH_SETTINGS *
0x180095b32  lea     rax, [rbp+57h+arg_8]
0x180095b36  mov     [rsp+0C0h+var_98], rcx; unsigned int *
0x180095b3b  lea     r8, [rbp+57h+arg_10]; unsigned __int16 **
0x180095b3f  sub     rdx, 0FFFFFFFFFFFFFF80h; struct FWXML_ELEMENT_LIST *
0x180095b43  mov     [rsp+0C0h+var_A0], rax; unsigned __int16 **
0x180095b48  mov     rcx, rdi; this
0x180095b4b  mov     [rbp+57h+arg_18], rsi
0x180095b4f  mov     [rbp+57h+arg_8], rsi
0x180095b53  call    ?ExtractSubscriptionParams@CListenerSubscription@@AEAAHPEAUFWXML_ELEMENT_LIST@@PEAPEBG11PEAKPEAU_WSMAN_BATCH_SETTINGS@@PEAT_ULARGE_INTEGER@@PEAVIRequestContext@@@Z; CListenerSubscription::ExtractSubscriptionParams(FWXML_ELEMENT_LIST *,ushort const * *,ushort const * *,ushort const * *,ulong *,_WSMAN_BATCH_SETTINGS *,_ULARGE_INTEGER *,IRequestContext *)
0x180095b58  test    eax, eax
0x180095b5a  jnz     short loc_180095B81
0x180095b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180095b63  cmp     rcx, r15
0x180095b66  jz      loc_18009624D
0x180095b6c  test    dword ptr [rcx+1Ch], 200h
0x180095b73  jz      loc_18009624D
0x180095b79  lea     edx, [rax+0Dh]
0x180095b7c  jmp     loc_1800961EE
0x180095b81  test    byte ptr [r14], 10h
0x180095b85  jnz     loc_180096009
0x180095b8b  lea     rax, [rdi+9E4h]
0x180095b92  xorps   xmm0, xmm0
0x180095b95  mov     [rdi+9A0h], rax
0x180095b9c  xor     eax, eax
0x180095b9e  mov     qword ptr [rbp+57h+var_60.8+8], rax
0x180095ba2  mov     rax, [rdi+0A40h]
0x180095ba9  movups  xmmword ptr [rbp+57h+var_60.authenticationMechanism], xmm0
0x180095bad  test    rax, rax
0x180095bb0  jz      short loc_180095BBD
0x180095bb2  mov     [rbp+57h+var_60.authenticationMechanism], 20h ; ' '
0x180095bb9  mov     qword ptr [rbp+57h+var_60.8], rax
0x180095bbd  mov     rcx, [rdi+100h]
0x180095bc4  mov     rbx, rsi
0x180095bc7  add     rcx, 0BD0h
0x180095bce  mov     [rbp+57h+nSize], esi
0x180095bd1  cmp     [rcx], esi
0x180095bd3  jz      short loc_180095BDD
0x180095bd5  call    ?GetValue@?$PacketElement@PEBG@PacketParser@@QEBAPEBGXZ; PacketParser::PacketElement<ushort const *>::GetValue(void)
0x180095bda  mov     rbx, rax
0x180095bdd  mov     rax, [rdi]
0x180095be0  mov     rcx, rdi
0x180095be3  mov     rax, [rax+110h]
0x180095bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095bef  or      r15, 0FFFFFFFFFFFFFFFFh
0x180095bf3  test    al, al
0x180095bf5  jnz     loc_180095D97
0x180095bfb  lea     rdx, aHttpSchemasMic_23; "http://schemas.microsoft.com/wbem/wsman"...
0x180095c02  mov     rcx, rbx; String1
0x180095c05  call    ?StringCchStartsWithCI@@YAHPEBG0@Z; StringCchStartsWithCI(ushort const *,ushort const *)
0x180095c0a  test    eax, eax
0x180095c0c  jnz     loc_180095D97
0x180095c12  lea     r8, [rbp+57h+nSize]; nSize
0x180095c16  xor     edx, edx; lpNameBuffer
0x180095c18  lea     ecx, [rax+8]; NameFormat
0x180095c1b  call    cs:__imp_GetUserNameExW
0x180095c21  mov     bl, al
0x180095c23  call    cs:__imp_GetLastError
0x180095c29  mov     esi, eax
0x180095c2b  test    bl, bl
0x180095c2d  jnz     short loc_180095C86
0x180095c2f  cmp     eax, 0EAh
0x180095c34  jz      short loc_180095C86
0x180095c36  cmp     eax, 534h
0x180095c3b  jz      loc_180095D95
0x180095c41  mov     rcx, cs:WPP_GLOBAL_Control
0x180095c48  lea     rdx, WPP_GLOBAL_Control
0x180095c4f  cmp     rcx, rdx
0x180095c52  jz      short loc_180095C71
0x180095c54  test    dword ptr [rcx+1Ch], 200h
0x180095c5b  jz      short loc_180095C71
0x180095c5d  mov     rcx, [rcx+10h]
0x180095c61  lea     edx, [r15+0Fh]
0x180095c65  lea     r8, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids
0x180095c6c  call    WPP_SF_
0x180095c71  mov     edx, esi
0x180095c73  mov     rcx, [rdi+838h]
0x180095c7a  mov     rax, [rcx]
0x180095c7d  mov     rax, [rax+48h]
0x180095c81  jmp     loc_180095A70
0x180095c86  mov     ecx, [rbp+57h+nSize]
0x180095c89  mov     eax, 2
0x180095c8e  mul     rcx
0x180095c91  cmovb   rax, r15
0x180095c95  xor     r8d, r8d
0x180095c98  mov     rcx, rax
0x180095c9b  xor     edx, edx
0x180095c9d  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x180095ca2  lea     rbx, [rdi+0A48h]
0x180095ca9  mov     rdx, rax
0x180095cac  mov     rcx, rbx
0x180095caf  call    ??4?$AutoDeleteVector@U_WINRS_RUN_COMMAND_ARG@@@@QEAAAEAV0@PEAU_WINRS_RUN_COMMAND_ARG@@@Z; AutoDeleteVector<_WINRS_RUN_COMMAND_ARG>::operator=(_WINRS_RUN_COMMAND_ARG *)
0x180095cb4  mov     rdx, [rbx]; lpNameBuffer
0x180095cb7  xor     esi, esi
0x180095cb9  test    rdx, rdx
0x180095cbc  jnz     short loc_180095D05
0x180095cbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180095cc5  lea     rdx, WPP_GLOBAL_Control
0x180095ccc  cmp     rcx, rdx
0x180095ccf  jz      short loc_180095CED
0x180095cd1  test    dword ptr [rcx+1Ch], 200h
0x180095cd8  jz      short loc_180095CED
0x180095cda  mov     rcx, [rcx+10h]
0x180095cde  lea     edx, [rsi+10h]
0x180095ce1  lea     r8, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids
0x180095ce8  call    WPP_SF_
0x180095ced  mov     rcx, [rdi+838h]
0x180095cf4  mov     rax, [rcx]
0x180095cf7  mov     rax, [rax+18h]
0x180095cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095d00  jmp     loc_18009624D
0x180095d05  lea     r8, [rbp+57h+nSize]; nSize
0x180095d09  mov     ecx, 8; NameFormat
0x180095d0e  call    cs:__imp_GetUserNameExW
0x180095d14  test    al, al
0x180095d16  jnz     short loc_180095D58
0x180095d18  call    cs:__imp_GetLastError
0x180095d1e  mov     ebx, eax
0x180095d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180095d27  lea     rdx, WPP_GLOBAL_Control
0x180095d2e  cmp     rcx, rdx
0x180095d31  jz      short loc_180095D51
0x180095d33  test    dword ptr [rcx+1Ch], 200h
0x180095d3a  jz      short loc_180095D51
0x180095d3c  mov     rcx, [rcx+10h]
0x180095d40  lea     r8, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids
0x180095d47  mov     edx, 11h
0x180095d4c  call    WPP_SF_
0x180095d51  mov     edx, ebx
0x180095d53  jmp     loc_180095C73
0x180095d58  mov     r9, [rbx]
0x180095d5b  mov     [rdi+998h], r9
0x180095d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180095d69  lea     rbx, WPP_GLOBAL_Control
0x180095d70  cmp     rcx, rbx
0x180095d73  jz      short loc_180095DC8
0x180095d75  test    dword ptr [rcx+1Ch], 400h
0x180095d7c  jz      short loc_180095DC8
0x180095d7e  mov     rcx, [rcx+10h]
0x180095d82  lea     r8, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids
0x180095d89  mov     edx, 12h
0x180095d8e  call    WPP_SF_S
0x180095d93  jmp     short loc_180095DC8
0x180095d95  xor     esi, esi
0x180095d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180095d9e  lea     rbx, WPP_GLOBAL_Control
0x180095da5  cmp     rcx, rbx
0x180095da8  jz      short loc_180095DC8
0x180095daa  test    dword ptr [rcx+1Ch], 400h
0x180095db1  jz      short loc_180095DC8
0x180095db3  mov     rcx, [rcx+10h]
0x180095db7  lea     r8, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids
0x180095dbe  mov     edx, 0Fh
0x180095dc3  call    WPP_SF_
0x180095dc8  mov     ecx, [rdi+9E0h]; unsigned int
0x180095dce  lea     r8, [rbp+57h+var_60]; struct _WSMAN_AUTHENTICATION_CREDENTIALS *
0x180095dd2  mov     r9, r14; void *
0x180095dd5  call    ?CreateNewCWSManEventSession@CWSManEventSession@@SAPEAV1@KKPEAU_WSMAN_AUTHENTICATION_CREDENTIALS@@PEAX@Z; CWSManEventSession::CreateNewCWSManEventSession(ulong,ulong,_WSMAN_AUTHENTICATION_CREDENTIALS *,void *)
0x180095dda  mov     [rdi+9D8h], rax
0x180095de1  test    rax, rax
0x180095de4  jnz     short loc_180095E2A
0x180095de6  mov     rcx, cs:WPP_GLOBAL_Control
0x180095ded  cmp     rcx, rbx
0x180095df0  jz      short loc_180095E0E
0x180095df2  test    dword ptr [rcx+1Ch], 200h
0x180095df9  jz      short loc_180095E0E
0x180095dfb  mov     rcx, [rcx+10h]
0x180095dff  lea     edx, [rax+13h]
0x180095e02  lea     r8, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids
0x180095e09  call    WPP_SF_
0x180095e0e  mov     rdi, [rdi+838h]
0x180095e15  mov     rax, [rdi]
0x180095e18  mov     rbx, [rax+48h]
0x180095e1c  call    cs:__imp_GetLastError
0x180095e22  mov     rcx, rdi
0x180095e25  jmp     loc_180095A6B
0x180095e2a  mov     rdx, [rdi+838h]; struct CRequestContext *
0x180095e31  mov     r8, rax; struct CWSManEventSession *
0x180095e34  mov     rcx, rdi; this
0x180095e37  call    ?VerifyConnectivity@CListenerSubscription@@AEAAHPEAVCRequestContext@@PEAVCWSManEventSession@@@Z; CListenerSubscription::VerifyConnectivity(CRequestContext *,CWSManEventSession *)
0x180095e3c  test    eax, eax
0x180095e3e  jnz     short loc_180095E9F
0x180095e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180095e47  cmp     rcx, rbx
0x180095e4a  jz      short loc_180095E68
0x180095e4c  test    dword ptr [rcx+1Ch], 200h
0x180095e53  jz      short loc_180095E68
0x180095e55  mov     rcx, [rcx+10h]
0x180095e59  lea     edx, [rax+14h]
0x180095e5c  lea     r8, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids
0x180095e63  call    WPP_SF_
0x180095e68  mov     rcx, [rdi+838h]
0x180095e6f  mov     edx, 80338095h
0x180095e74  mov     rax, [rcx]
0x180095e77  mov     rax, [rax+48h]
0x180095e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095e80  mov     rdx, [rdi+838h]; struct CRequestContext *
0x180095e87  mov     rcx, [rdi+9D8h]; this
0x180095e8e  call    ?CloseEventSession@CWSManEventSession@@QEAAHPEAVCRequestContext@@K@Z; CWSManEventSession::CloseEventSession(CRequestContext *,ulong)
0x180095e93  mov     [rdi+9D8h], rsi
0x180095e9a  jmp     loc_18009624D
0x180095e9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180095ea6  cmp     rcx, rbx
0x180095ea9  jz      short loc_180095EC9
0x180095eab  test    dword ptr [rcx+1Ch], 400h
0x180095eb2  jz      short loc_180095EC9
0x180095eb4  mov     rcx, [rcx+10h]
0x180095eb8  lea     r8, WPP_9f47502b6e6e3d472175442fb725829e_Traceguids
0x180095ebf  mov     edx, 15h
0x180095ec4  call    WPP_SF_
0x180095ec9  mov     rcx, [rdi+9D8h]; this
0x180095ed0  mov     rdx, rdi; struct CListenerSubscription *
0x180095ed3  call    ?SetMasterOperation@CWSManEventSession@@QEAAXPEAVCListenerSubscription@@@Z; CWSManEventSession::SetMasterOperation(CListenerSubscription *)
0x180095ed8  mov     rdx, [rdi+838h]
0x180095edf  mov     rcx, [rdi+9D8h]
0x180095ee6  add     rdx, 1ECh
0x180095eed  add     rcx, 40h ; '@'
0x180095ef1  call    ??4Locale@@QEAAAEAV0@AEBV0@@Z; Locale::operator=(Locale const &)
0x180095ef6  mov     rcx, [rdi+9D8h]
  ... truncated ...
```

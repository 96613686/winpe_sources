# CRuntimeBroker::GetActivationFactory(ushort const *,_GUID const &,void * *)

- ea: `0x140002590`
- end: `0x1400027a4`
- name: `?GetActivationFactory@CRuntimeBroker@@UEAAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `532`
- prototype: `int(CRuntimeBroker *__hidden this, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002590`
- `0x1400027ac`
- `0x1400027d0`
- `0x140002d70`
- `0x140008c80`
- `0x14000cdc8`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1400026f0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x140002754`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1400026f0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x140002754`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140002606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140002606`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400025f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002633`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400025f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140002633`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140002675`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140002675`

## string_xrefs

- `0x14000261a`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x1400026a2`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x1400026fe`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x140002762`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x14000278b`: `onecore\com\combase\runtimebroker\exe\runtimebroker.cpp`
- `0x1400026bb`: `activatableClassId`
- `0x14000271f`: `activatableClassId`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::GetActivationFactory(
        CRuntimeBroker *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned __int64 v7; // rbx
  HRESULT v8; // eax
  unsigned int v9; // ebx
  int v11; // eax
  int ActivationFactory; // eax
  int v13; // [rsp+20h] [rbp-78h]
  HSTRING string; // [rsp+30h] [rbp-68h] BYREF
  int v15; // [rsp+38h] [rbp-60h] BYREF
  __int128 v16; // [rsp+40h] [rbp-58h] BYREF
  _BYTE v17[22]; // [rsp+50h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v15 = 0;
  *a4 = 0;
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    if ( v7 > 0xFFFFFFFF )
    {
      v16 = *(_OWORD *)L"activatableClassId";
      *(_OWORD *)v17 = *(_OWORD *)L"bleClassId";
      *(_QWORD *)&v17[14] = *(_QWORD *)L"sId";
      RoOriginateErrorW(2147942487LL, 18, &v16);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C5,
        (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
        (const char *)0x80070057LL,
        v13);
      return 2147942487LL;
    }
    else
    {
      WindowsDeleteString(0);
      string = 0;
      v8 = WindowsCreateString(a2, v7, &string);
      v9 = v8;
      if ( v8 >= 0 )
      {
        v11 = CRuntimeBroker::ValidateBrokeredActivationRequest(a2, (enum Windows::Foundation::ThreadingType *)&v15);
        v9 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2CB,
            (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
            (const char *)(unsigned int)v11,
            v13);
        }
        else
        {
          ActivationFactory = RoGetActivationFactory(string, a3, a4);
          v9 = ActivationFactory;
          if ( ActivationFactory < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x2CE,
              (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
              (const char *)(unsigned int)ActivationFactory,
              v13);
          CRuntimeBroker::LogActivation(string, a3, v9, 0);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2CA,
          (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
          (const char *)(unsigned int)v8,
          v13);
      }
      WindowsDeleteString(string);
      return v9;
    }
  }
  else
  {
    v16 = *(_OWORD *)L"activatableClassId";
    *(_OWORD *)v17 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v17[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v16);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2BD,
      (unsigned int)"onecore\\com\\combase\\runtimebroker\\exe\\runtimebroker.cpp",
      (const char *)0x80070057LL,
      v13);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140002590  push    rbp
0x140002592  push    rsi
0x140002593  push    rdi
0x140002594  push    r14
0x140002596  sub     rsp, 78h
0x14000259a  mov     rax, cs:__security_cookie
0x1400025a1  xor     rax, rsp
0x1400025a4  mov     [rsp+98h+var_30], rax
0x1400025a9  xor     r14d, r14d
0x1400025ac  mov     rsi, r9
0x1400025af  mov     [rsp+98h+var_60], r14d
0x1400025b4  mov     rbp, r8
0x1400025b7  mov     [r9], r14
0x1400025ba  mov     rdi, rdx
0x1400025bd  test    rdx, rdx
0x1400025c0  jz      loc_1400026BB
0x1400025c6  mov     [rsp+98h+var_28], rbx
0x1400025cb  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400025d2  inc     rbx
0x1400025d5  cmp     [rdx+rbx*2], r14w
0x1400025da  jnz     short loc_1400025D2
0x1400025dc  mov     eax, 0FFFFFFFFh
0x1400025e1  cmp     rbx, rax
0x1400025e4  ja      loc_14000271F
0x1400025ea  xor     ecx, ecx; string
0x1400025ec  mov     [rsp+98h+string], r14
0x1400025f1  call    cs:__imp_WindowsDeleteString
0x1400025f7  mov     edx, ebx; length
0x1400025f9  mov     [rsp+98h+string], r14
0x1400025fe  lea     r8, [rsp+98h+string]; string
0x140002603  mov     rcx, rdi; sourceString
0x140002606  call    cs:__imp_WindowsCreateString
0x14000260c  mov     ebx, eax
0x14000260e  test    eax, eax
0x140002610  jns     short loc_140002657
0x140002612  mov     rcx, [rsp+98h]; this
0x14000261a  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x140002621  mov     r9d, eax; char *
0x140002624  mov     edx, 2CAh; void *
0x140002629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000262e  mov     rcx, [rsp+98h+string]; string
0x140002633  call    cs:__imp_WindowsDeleteString
0x140002639  mov     eax, ebx
0x14000263b  mov     rbx, [rsp+98h+var_28]
0x140002640  mov     rcx, [rsp+98h+var_30]
0x140002645  xor     rcx, rsp; StackCookie
0x140002648  call    __security_check_cookie
0x14000264d  add     rsp, 78h
0x140002651  pop     r14
0x140002653  pop     rdi
0x140002654  pop     rsi
0x140002655  pop     rbp
0x140002656  retn
0x140002657  lea     rdx, [rsp+98h+var_60]; enum Windows::Foundation::ThreadingType *
0x14000265c  mov     rcx, rdi; sourceString
0x14000265f  call    ?ValidateBrokeredActivationRequest@CRuntimeBroker@@CAJPEBGAEAW4ThreadingType@Foundation@Windows@@@Z; CRuntimeBroker::ValidateBrokeredActivationRequest(ushort const *,Windows::Foundation::ThreadingType &)
0x140002664  mov     ebx, eax
0x140002666  test    eax, eax
0x140002668  js      short loc_14000269A
0x14000266a  mov     rcx, [rsp+98h+string]
0x14000266f  mov     r8, rsi
0x140002672  mov     rdx, rbp
0x140002675  call    cs:__imp_RoGetActivationFactory
0x14000267b  mov     ebx, eax
0x14000267d  test    eax, eax
0x14000267f  js      loc_140002783
0x140002685  mov     rcx, [rsp+98h+string]; HSTRING
0x14000268a  xor     r9d, r9d; bool
0x14000268d  mov     r8d, ebx; int
0x140002690  mov     rdx, rbp; struct _GUID *
0x140002693  call    ?LogActivation@CRuntimeBroker@@SAXPEAUHSTRING__@@AEBU_GUID@@J_N2@Z; CRuntimeBroker::LogActivation(HSTRING__ *,_GUID const &,long,bool,bool)
0x140002698  jmp     short loc_14000262E
0x14000269a  mov     rcx, [rsp+98h]; this
0x1400026a2  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x1400026a9  mov     r9d, ebx; char *
0x1400026ac  mov     edx, 2CBh; void *
0x1400026b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400026b6  jmp     loc_14000262E
0x1400026bb  movups  xmm0, xmmword ptr cs:aActivatablecla; "activatableClassId"
0x1400026c2  lea     r8, [rsp+98h+var_58]
0x1400026c7  mov     edx, 12h
0x1400026cc  movups  xmm1, xmmword ptr cs:aActivatablecla+10h; "bleClassId"
0x1400026d3  mov     ecx, 80070057h
0x1400026d8  movups  [rsp+98h+var_58], xmm0
0x1400026dd  movsd   xmm0, qword ptr cs:aActivatablecla+1Eh; "sId"
0x1400026e5  movups  xmmword ptr [rsp+98h+var_48], xmm1
0x1400026ea  movsd   qword ptr [rsp+98h+var_48+0Eh], xmm0
0x1400026f0  call    cs:__imp_RoOriginateErrorW
0x1400026f6  mov     rcx, [rsp+98h]; this
0x1400026fe  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x140002705  mov     r9d, 80070057h; char *
0x14000270b  mov     edx, 2BDh; void *
0x140002710  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002715  mov     eax, 80070057h
0x14000271a  jmp     loc_140002640
0x14000271f  movups  xmm0, xmmword ptr cs:aActivatablecla; "activatableClassId"
0x140002726  lea     r8, [rsp+98h+var_58]
0x14000272b  mov     edx, 12h
0x140002730  movups  xmm1, xmmword ptr cs:aActivatablecla+10h; "bleClassId"
0x140002737  mov     ecx, 80070057h
0x14000273c  movups  [rsp+98h+var_58], xmm0
0x140002741  movsd   xmm0, qword ptr cs:aActivatablecla+1Eh; "sId"
0x140002749  movups  xmmword ptr [rsp+98h+var_48], xmm1
0x14000274e  movsd   qword ptr [rsp+98h+var_48+0Eh], xmm0
0x140002754  call    cs:__imp_RoOriginateErrorW
0x14000275a  mov     rcx, [rsp+98h]; this
0x140002762  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x140002769  mov     r9d, 80070057h; char *
0x14000276f  mov     edx, 2C5h; void *
0x140002774  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140002779  mov     eax, 80070057h
0x14000277e  jmp     loc_14000263B
0x140002783  mov     rcx, [rsp+98h]; this
0x14000278b  lea     r8, aOnecoreComComb_2; "onecore\\com\\combase\\runtimebroker\\e"...
0x140002792  mov     r9d, ebx; char *
0x140002795  mov     edx, 2CEh; void *
0x14000279a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000279f  jmp     loc_140002685
```

# CRDPNetworkDetector::Initialize(IUnknown *)

- ea: `0x18001dc60`
- end: `0x18001e007`
- name: `?Initialize@CRDPNetworkDetector@@UEAAJPEAUIUnknown@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(CRDPNetworkDetector *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001eca4`

## callees

- `0x180019a80`
- `0x180019ab0`
- `0x18001dc60`
- `0x18001e164`
- `0x18001e318`
- `0x18001ea10`
- `0x18001ebac`
- `0x180046a84`
- `0x1800711c8`
- `0x1800721d4`
- `0x1800923f8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001dce4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18001dce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ddef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ddef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001deed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dca7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dcc9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dca7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001dcc9`

## pseudocode

```c
__int64 __fastcall CRDPNetworkDetector::Initialize(CRDPNetworkDetector *this, struct IUnknown *a2)
{
  HANDLE EventW; // rax
  HANDLE v5; // rax
  const struct _GUID *v6; // rcx
  CNetDetectETWEvents *v7; // rcx
  struct IUnknownVtbl *lpVtbl; // rax
  int v9; // eax
  char v10; // bl
  __int64 v11; // rcx
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // [rsp+40h] [rbp+8h] BYREF
  LARGE_INTEGER Frequency; // [rsp+50h] [rbp+18h] BYREF

  Frequency.QuadPart = 0;
  LODWORD(v20) = 0;
  if ( !(unsigned int)CTSCriticalSection::Initialize((CRDPNetworkDetector *)((char *)this + 21320)) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147500037LL;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 22;
    goto LABEL_28;
  }
  *((_DWORD *)this + 7) |= 2u;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 2667) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_17;
    }
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 24;
    goto LABEL_32;
  }
  v5 = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 2668) = v5;
  if ( v5 )
  {
    if ( QueryPerformanceFrequency(&Frequency) )
    {
      *((LARGE_INTEGER *)this + 16) = Frequency;
      if ( a2 != *((struct IUnknown **)this + 10) )
      {
        TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 80);
        *((_QWORD *)this + 10) = a2;
        TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 80);
      }
      if ( !(unsigned int)RegGetMinWindowSize((unsigned int *)&v20) )
        *((_DWORD *)this + 5340) = v20;
      CNetDetectETWEvents::CreateInstance(v6, (void **)this + 14);
      v7 = (CNetDetectETWEvents *)*((_QWORD *)this + 14);
      if ( v7 )
      {
        CNetDetectETWEvents::Enable(v7);
        if ( a2 )
        {
          lpVtbl = a2->lpVtbl;
          v20 = 0;
          if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
                 a2,
                 &IID_IRDPCollection,
                 &v20) >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, GUID *, char *))(*(_QWORD *)v20 + 48LL))(
                   v20,
                   L"RDP::EventLog::Session",
                   &IID_IRdpTransportEventLogCallbacks,
                   (char *)this + 21592);
            v10 = v9;
            if ( v9 < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v19 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                28,
                (unsigned int)&WPP_411b68934074348d2965b0d30520efb5_Traceguids,
                v19,
                (__int64)"Failed to get eventlog instance, but it is OK.",
                v10);
            }
          }
          v11 = v20;
          if ( v20 )
          {
            v20 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          }
        }
        *((_DWORD *)this + 5367) = 1;
        *((_DWORD *)this + 5351) = 4;
        *((_DWORD *)this + 5350) = 4;
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Ds(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            (unsigned int)&WPP_411b68934074348d2965b0d30520efb5_Traceguids,
            v18,
            (__int64)"\"CNetDetectETWEvents\"");
        }
        return 2147942414LL;
      }
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147500037LL;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 26;
LABEL_28:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      &WPP_411b68934074348d2965b0d30520efb5_Traceguids,
      CurrentThreadActivityIdPrefix,
      -2147467259);
    return 2147500037LL;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 25;
LABEL_32:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v17,
      &WPP_411b68934074348d2965b0d30520efb5_Traceguids,
      v16,
      LastError);
  }
LABEL_17:
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError >= 0 )
    return (unsigned int)-2147467259;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001dc60  mov     rax, rsp
0x18001dc63  mov     [rax+10h], rbx
0x18001dc67  mov     [rax+20h], rsi
0x18001dc6b  push    rdi
0x18001dc6c  sub     rsp, 30h
0x18001dc70  mov     rdi, rcx
0x18001dc73  mov     qword ptr [rax+18h], 0
0x18001dc7b  add     rcx, 5348h; this
0x18001dc82  mov     dword ptr [rax+8], 0
0x18001dc89  mov     rsi, rdx
0x18001dc8c  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x18001dc91  test    eax, eax
0x18001dc93  jz      loc_18001DE47
0x18001dc99  or      dword ptr [rdi+1Ch], 2
0x18001dc9d  xor     r9d, r9d; lpName
0x18001dca0  xor     r8d, r8d; bInitialState
0x18001dca3  xor     edx, edx; bManualReset
0x18001dca5  xor     ecx, ecx; lpEventAttributes
0x18001dca7  call    cs:__imp_CreateEventW
0x18001dcad  mov     [rdi+5358h], rax
0x18001dcb4  test    rax, rax
0x18001dcb7  jz      loc_18001DDEF
0x18001dcbd  xor     r9d, r9d; lpName
0x18001dcc0  xor     r8d, r8d; bInitialState
0x18001dcc3  xor     ecx, ecx; lpEventAttributes
0x18001dcc5  lea     edx, [r9+1]; bManualReset
0x18001dcc9  call    cs:__imp_CreateEventW
0x18001dccf  mov     [rdi+5360h], rax
0x18001dcd6  test    rax, rax
0x18001dcd9  jz      loc_18001DEED
0x18001dcdf  lea     rcx, [rsp+38h+Frequency]; lpFrequency
0x18001dce4  call    cs:__imp_QueryPerformanceFrequency
0x18001dcea  test    eax, eax
0x18001dcec  jz      loc_18001DE29
0x18001dcf2  mov     rax, qword ptr [rsp+38h+Frequency]
0x18001dcf7  lea     rbx, [rdi+50h]
0x18001dcfb  mov     [rdi+80h], rax
0x18001dd02  cmp     rsi, [rbx]
0x18001dd05  jz      short loc_18001DD1A
0x18001dd07  mov     rcx, rbx; void *
0x18001dd0a  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18001dd0f  mov     rcx, rbx
0x18001dd12  mov     [rbx], rsi
0x18001dd15  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18001dd1a  lea     rcx, [rsp+38h+arg_0]; unsigned int *
0x18001dd1f  call    ?RegGetMinWindowSize@@YAJPEAK@Z; RegGetMinWindowSize(ulong *)
0x18001dd24  test    eax, eax
0x18001dd26  jz      loc_18001DF3B
0x18001dd2c  lea     rdx, [rdi+70h]; void **
0x18001dd30  call    ?CreateInstance@CNetDetectETWEvents@@SAJAEBU_GUID@@PEAPEAX@Z; CNetDetectETWEvents::CreateInstance(_GUID const &,void * *)
0x18001dd35  mov     rcx, [rdi+70h]; this
0x18001dd39  test    rcx, rcx
0x18001dd3c  jz      loc_18001DF4A
0x18001dd42  call    ?Enable@CNetDetectETWEvents@@QEAAJXZ; CNetDetectETWEvents::Enable(void)
0x18001dd47  test    rsi, rsi
0x18001dd4a  jz      short loc_18001DDC2
0x18001dd4c  mov     rax, [rsi]
0x18001dd4f  lea     r8, [rsp+38h+arg_0]
0x18001dd54  lea     rdx, IID_IRDPCollection
0x18001dd5b  mov     [rsp+38h+arg_0], 0
0x18001dd64  mov     rcx, rsi
0x18001dd67  mov     rax, [rax]
0x18001dd6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd6f  test    eax, eax
0x18001dd71  js      short loc_18001DDA3
0x18001dd73  mov     rcx, [rsp+38h+arg_0]
0x18001dd78  lea     r9, [rdi+5458h]
0x18001dd7f  lea     r8, IID_IRdpTransportEventLogCallbacks
0x18001dd86  lea     rdx, aRdpEventlogSes; "RDP::EventLog::Session"
0x18001dd8d  mov     rax, [rcx]
0x18001dd90  mov     rax, [rax+30h]
0x18001dd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd99  mov     ebx, eax
0x18001dd9b  test    eax, eax
0x18001dd9d  js      loc_18001DFA3
0x18001dda3  mov     rcx, [rsp+38h+arg_0]
0x18001dda8  test    rcx, rcx
0x18001ddab  jz      short loc_18001DDC2
0x18001ddad  mov     [rsp+38h+arg_0], 0
0x18001ddb6  mov     rax, [rcx]
0x18001ddb9  mov     rax, [rax+10h]
0x18001ddbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddc2  mov     eax, 4
0x18001ddc7  mov     dword ptr [rdi+53DCh], 1
0x18001ddd1  mov     [rdi+539Ch], eax
0x18001ddd7  mov     [rdi+5398h], eax
0x18001dddd  xor     eax, eax
0x18001dddf  mov     rbx, [rsp+38h+arg_8]
0x18001dde4  mov     rsi, [rsp+38h+arg_18]
0x18001dde9  add     rsp, 30h
0x18001dded  pop     rdi
0x18001ddee  retn
0x18001ddef  call    cs:__imp_GetLastError
0x18001ddf5  mov     ebx, eax
0x18001ddf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddfe  lea     rax, WPP_GLOBAL_Control
0x18001de05  cmp     rcx, rax
0x18001de08  jnz     loc_18001DEA0
0x18001de0e  test    ebx, ebx
0x18001de10  jle     short loc_18001DE1B
0x18001de12  movzx   ebx, bx
0x18001de15  or      ebx, 80070000h
0x18001de1b  mov     eax, 80004005h
0x18001de20  test    ebx, ebx
0x18001de22  cmovns  ebx, eax
0x18001de25  mov     eax, ebx
0x18001de27  jmp     short loc_18001DDDF
0x18001de29  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de30  lea     rax, WPP_GLOBAL_Control
0x18001de37  cmp     rcx, rax
0x18001de3a  jnz     loc_18001DF22
0x18001de40  mov     eax, 80004005h
0x18001de45  jmp     short loc_18001DDDF
0x18001de47  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de4e  lea     rax, WPP_GLOBAL_Control
0x18001de55  cmp     rcx, rax
0x18001de58  jz      short loc_18001DE40
0x18001de5a  test    byte ptr [rcx+1Ch], 8
0x18001de5e  jz      short loc_18001DE40
0x18001de60  cmp     byte ptr [rcx+19h], 2
0x18001de64  jb      short loc_18001DE40
0x18001de66  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001de6b  mov     edx, 16h
0x18001de70  jmp     short loc_18001DE7C
0x18001de72  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001de77  mov     edx, 1Ah
0x18001de7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001de83  lea     r8, WPP_411b68934074348d2965b0d30520efb5_Traceguids
0x18001de8a  mov     r9d, eax
0x18001de8d  mov     dword ptr [rsp+38h+var_18], 80004005h
0x18001de95  mov     rcx, [rcx+10h]
0x18001de99  call    WPP_SF_Dd
0x18001de9e  jmp     short loc_18001DE40
0x18001dea0  test    byte ptr [rcx+1Ch], 8
0x18001dea4  jz      loc_18001DE0E
0x18001deaa  cmp     byte ptr [rcx+19h], 2
0x18001deae  jb      loc_18001DE0E
0x18001deb4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001deb9  mov     edx, 18h
0x18001debe  jmp     short loc_18001DECA
0x18001dec0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001dec5  mov     edx, 19h
0x18001deca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ded1  lea     r8, WPP_411b68934074348d2965b0d30520efb5_Traceguids
0x18001ded8  mov     r9d, eax
0x18001dedb  mov     dword ptr [rsp+38h+var_18], ebx
0x18001dedf  mov     rcx, [rcx+10h]
0x18001dee3  call    WPP_SF_Dd
0x18001dee8  jmp     loc_18001DE0E
0x18001deed  call    cs:__imp_GetLastError
0x18001def3  mov     ebx, eax
0x18001def5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001defc  lea     rax, WPP_GLOBAL_Control
0x18001df03  cmp     rcx, rax
0x18001df06  jz      loc_18001DE0E
0x18001df0c  test    byte ptr [rcx+1Ch], 8
0x18001df10  jz      loc_18001DE0E
0x18001df16  cmp     byte ptr [rcx+19h], 2
0x18001df1a  jb      loc_18001DE0E
0x18001df20  jmp     short loc_18001DEC0
0x18001df22  test    byte ptr [rcx+1Ch], 8
0x18001df26  jz      loc_18001DE40
0x18001df2c  cmp     byte ptr [rcx+19h], 2
0x18001df30  jb      loc_18001DE40
0x18001df36  jmp     loc_18001DE72
0x18001df3b  mov     eax, dword ptr [rsp+38h+arg_0]
0x18001df3f  mov     [rdi+5370h], eax
0x18001df45  jmp     loc_18001DD2C
0x18001df4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df51  lea     rax, WPP_GLOBAL_Control
0x18001df58  cmp     rcx, rax
0x18001df5b  jz      short loc_18001DF99
0x18001df5d  test    byte ptr [rcx+1Ch], 8
0x18001df61  jz      short loc_18001DF99
0x18001df63  cmp     byte ptr [rcx+19h], 2
0x18001df67  jb      short loc_18001DF99
0x18001df69  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001df6e  lea     rcx, aCnetdetectetwe_0; "\"CNetDetectETWEvents\""
0x18001df75  mov     edx, 1Bh
0x18001df7a  mov     [rsp+38h+var_18], rcx
0x18001df7f  lea     r8, WPP_411b68934074348d2965b0d30520efb5_Traceguids
0x18001df86  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df8d  mov     r9d, eax
0x18001df90  mov     rcx, [rcx+10h]
0x18001df94  call    WPP_SF_Ds
0x18001df99  mov     eax, 8007000Eh
0x18001df9e  jmp     loc_18001DDDF
0x18001dfa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfaa  lea     rax, WPP_GLOBAL_Control
0x18001dfb1  cmp     rcx, rax
0x18001dfb4  jz      loc_18001DDA3
0x18001dfba  test    byte ptr [rcx+1Ch], 8
0x18001dfbe  jz      loc_18001DDA3
0x18001dfc4  cmp     byte ptr [rcx+19h], 2
0x18001dfc8  jb      loc_18001DDA3
0x18001dfce  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001dfd3  lea     rcx, aFailedToGetEve_0; "Failed to get eventlog instance, but it"...
0x18001dfda  mov     [rsp+38h+var_10], ebx
0x18001dfde  mov     [rsp+38h+var_18], rcx
0x18001dfe3  lea     r8, WPP_411b68934074348d2965b0d30520efb5_Traceguids
0x18001dfea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dff1  mov     edx, 1Ch
0x18001dff6  mov     r9d, eax
0x18001dff9  mov     rcx, [rcx+10h]
0x18001dffd  call    WPP_SF_DsD
0x18001e002  jmp     loc_18001DDA3
```

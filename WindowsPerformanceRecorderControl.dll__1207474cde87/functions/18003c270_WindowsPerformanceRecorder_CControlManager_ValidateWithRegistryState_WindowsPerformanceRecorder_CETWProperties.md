# WindowsPerformanceRecorder::CControlManager::ValidateWithRegistryState(WindowsPerformanceRecorder::CETWProperties &,bool)

- ea: `0x18003c270`
- end: `0x18003c69b`
- name: `?ValidateWithRegistryState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z`
- size: `1067`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, struct WindowsPerformanceRecorder::CETWProperties *, bool)`
- caller_count: `5`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a1f0`
- `0x180059060`
- `0x18005deb0`
- `0x18005f068`
- `0x180061780`

## callees

- `0x18001e6b8`
- `0x18001e6e0`
- `0x18001ea58`
- `0x180024428`
- `0x1800248d8`
- `0x180031374`
- `0x180034bec`
- `0x18003bcd0`
- `0x18003c270`
- `0x180043514`
- `0x1800473a4`
- `0x18005f3f8`
- `0x18005f590`

## string_xrefs

- `0x18003c49e`: `ValidateWithRegistryState`
- `0x18003c536`: `ValidateWithRegistryState`
- `0x18003c5ae`: `ValidateWithRegistryState`
- `0x18003c61e`: `ValidateWithRegistryState`
- `0x18003c609`: `Registry LoggingMode %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::ValidateWithRegistryState(
        const unsigned __int16 **this,
        struct WindowsPerformanceRecorder::CETWProperties *a2,
        bool a3)
{
  bool v3; // r15
  signed int RegistryETWProperties; // ebx
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v7; // r14
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v8; // rsi
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v9; // r12
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v10; // rdi
  WindowsPerformanceRecorder *v11; // rax
  const unsigned __int16 *v12; // r9
  WindowsPerformanceRecorder::CControlManager *v13; // rcx
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v14; // rcx
  char v15; // al
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v16; // r14
  unsigned __int64 v17; // rcx
  unsigned __int16 *v18; // rax
  int v19; // eax
  const struct _GUID *v20; // r8
  const struct _GUID *v21; // r9
  __int64 v22; // r15
  const unsigned __int16 *v23; // rax
  const char *v24; // rax
  const unsigned __int16 *v25; // rax
  const char *v26; // rax
  char *Format; // [rsp+20h] [rbp-218h]
  char *v29; // [rsp+28h] [rbp-210h]
  char *SessionName; // [rsp+28h] [rbp-210h]
  __int64 v31; // [rsp+30h] [rbp-208h]
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v32; // [rsp+40h] [rbp-1F8h]
  char v33[8]; // [rsp+50h] [rbp-1E8h] BYREF
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v34; // [rsp+58h] [rbp-1E0h]
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v35; // [rsp+60h] [rbp-1D8h]
  char *v36; // [rsp+150h] [rbp-E8h]
  char v38; // [rsp+258h] [rbp+20h]

  v3 = a3;
  WindowsPerformanceRecorder::CETWProperties::CETWProperties((WindowsPerformanceRecorder::CETWProperties *)v33);
  RegistryETWProperties = WindowsPerformanceRecorder::CControlManager::GetRegistryETWProperties(
                            (WindowsPerformanceRecorder::CControlManager *)this,
                            (struct WindowsPerformanceRecorder::CETWProperties *)v33,
                            v3);
  if ( RegistryETWProperties >= 0 )
  {
    v7 = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)a2 + 2);
    v32 = v7;
    v8 = (WindowsPerformanceRecorder::CETWProperties::CEventSession **)*((_QWORD *)a2 + 1);
    v9 = v35;
    v10 = v34;
    if ( (char *)v7 - (char *)v8 != (char *)v35 - (char *)v34 )
    {
      RegistryETWProperties = -984076286;
      goto LABEL_46;
    }
    if ( v8 != v7 )
    {
LABEL_5:
      if ( RegistryETWProperties < 0 )
        goto LABEL_46;
      v38 = 0;
      if ( v10 == v9 )
      {
LABEL_47:
        RegistryETWProperties = -984076271;
        Format = (char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v8);
        WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
          this,
          3310891025LL,
          2,
          &IID_IControlManager,
          Format);
        SessionName = (char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v8);
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          (unsigned __int8)"ValidateWithRegistryState",
          (const char *)0x17A6,
          0xC5583011,
          "%ws",
          SessionName);
        goto LABEL_46;
      }
      while ( 1 )
      {
        if ( RegistryETWProperties < 0 )
        {
          v15 = v38;
LABEL_40:
          if ( !v15 )
            goto LABEL_47;
LABEL_41:
          if ( ++v8 == v32 )
          {
            if ( RegistryETWProperties < 0 )
              goto LABEL_46;
            goto LABEL_44;
          }
          v9 = v35;
          v10 = v34;
          goto LABEL_5;
        }
        WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v10);
        v11 = (WindowsPerformanceRecorder *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v8);
        if ( !WindowsPerformanceRecorder::CompareWPREventSessionNames(v11, v12, this[28], v12) )
          goto LABEL_20;
        LOBYTE(v13) = *((_QWORD *)*v8 + 3) == *((_QWORD *)*v8 + 4) || *((_QWORD *)*v10 + 3) == *((_QWORD *)*v10 + 4);
        if ( (unsigned int)WindowsPerformanceRecorder::CControlManager::ValidateEventSession(
                             v13,
                             *((const struct _EVENT_TRACE_PROPERTIES **)*v8 + 1),
                             *((const struct _EVENT_TRACE_PROPERTIES **)*v10 + 1),
                             v3,
                             (bool)v13) )
        {
          v14 = *v8;
          if ( *(_DWORD *)*v8 == 1 )
          {
            RegistryETWProperties = -984076285;
            goto LABEL_38;
          }
          switch ( *(_DWORD *)v14 )
          {
            case 2:
              RegistryETWProperties = -984076284;
              goto LABEL_38;
            case 3:
              RegistryETWProperties = -984076283;
              goto LABEL_38;
            case 5:
              RegistryETWProperties = -984076266;
LABEL_38:
              v25 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v14);
              WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
                this,
                (unsigned int)RegistryETWProperties,
                2,
                &IID_IControlManager,
                v25);
              v26 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v8);
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)2,
                (unsigned __int8)"ValidateWithRegistryState",
                (const char *)0x1760,
                RegistryETWProperties,
                "%ws",
                v26);
              goto LABEL_41;
          }
        }
        v15 = 1;
        v38 = 1;
        if ( !v3 )
          break;
LABEL_21:
        ++v10;
        v3 = a3;
        if ( v10 == v9 )
          goto LABEL_40;
      }
      v16 = *v8;
      v17 = (unsigned int)(*(_DWORD *)*v8 - 1);
      switch ( *(_DWORD *)*v8 )
      {
        case 1:
          v22 = *((_QWORD *)v16 + 1);
          if ( !*(_DWORD *)(v22 + 72) )
          {
            v17 = *((_QWORD *)*v10 + 1);
            if ( !*(_DWORD *)(v17 + 72) )
              goto LABEL_20;
          }
          v19 = WindowsPerformanceRecorder::CControlManager::ValidateSystemProvidersWithRegistryState(
                  (WindowsPerformanceRecorder::CControlManager *)v17,
                  *v8,
                  *v10);
          RegistryETWProperties = v19;
          if ( v19 >= 0 )
            goto LABEL_20;
          v21 = (const struct _GUID *)(v22 + 24);
          break;
        case 2:
          if ( *(_DWORD *)(*((_QWORD *)v16 + 1) + 72LL) != *(_DWORD *)(*((_QWORD *)*v10 + 1) + 72LL) )
          {
            RegistryETWProperties = -984076284;
            LODWORD(v31) = *(_DWORD *)(*((_QWORD *)*v10 + 1) + 72LL);
            LODWORD(v29) = *(_DWORD *)(*((_QWORD *)v16 + 1) + 72LL);
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)2,
              (unsigned __int8)"ValidateWithRegistryState",
              (const char *)0x177D,
              0xC5583004,
              "EnableFlags=0x%x, EnableFlags=0x%x",
              v29,
              v31);
            goto LABEL_32;
          }
LABEL_19:
          v18 = (unsigned __int16 *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v8);
          RegistryETWProperties = WindowsPerformanceRecorder::CControlManager::ValidateEventProviders(
                                    (WindowsPerformanceRecorder::CControlManager *)this,
                                    *((unsigned __int16 **)a2 + 40),
                                    v18,
                                    (__int64)*v10 + 24);
          if ( RegistryETWProperties >= 0 )
          {
LABEL_20:
            v15 = v38;
            goto LABEL_21;
          }
LABEL_32:
          v23 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v8);
          WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
            this,
            (unsigned int)RegistryETWProperties,
            2,
            &IID_IControlManager,
            v23);
          v24 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(*v8);
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"ValidateWithRegistryState",
            (const char *)0x179D,
            RegistryETWProperties,
            "%ws",
            v24);
          goto LABEL_20;
        case 3:
          v19 = WindowsPerformanceRecorder::CControlManager::ValidateHeapEventProvidersWithRegistryState(
                  (WindowsPerformanceRecorder::CControlManager *)(unsigned int)(*(_DWORD *)*v8 - 3),
                  *v8,
                  *v10);
          RegistryETWProperties = v19;
          if ( v19 >= 0 )
            goto LABEL_20;
          v21 = (const struct _GUID *)(*((_QWORD *)v16 + 1) + 24LL);
          break;
        case 5:
          goto LABEL_19;
        default:
          goto LABEL_21;
      }
      WindowsPerformanceRecorder::CControlManager::SetProviderControlErrorInfo(
        (WindowsPerformanceRecorder::CControlManager *)this,
        v19,
        v20,
        v21);
      goto LABEL_32;
    }
LABEL_44:
    if ( *((_DWORD *)a2 + 64) != (_DWORD)v36 )
    {
      RegistryETWProperties = -984076277;
      LODWORD(v29) = (_DWORD)v36;
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"ValidateWithRegistryState",
        (const char *)0x17AF,
        0xC558300B,
        "Registry LoggingMode %d",
        v29);
    }
  }
LABEL_46:
  WindowsPerformanceRecorder::CETWProperties::~CETWProperties((WindowsPerformanceRecorder::CETWProperties *)v33);
  return (unsigned int)RegistryETWProperties;
}

```

## disassembly

```asm
0x18003c270  mov     rax, rsp
0x18003c273  mov     [rax+18h], r8b
0x18003c277  push    rbp
0x18003c278  push    rsi
0x18003c279  push    rdi
0x18003c27a  push    r12
0x18003c27c  push    r13
0x18003c27e  push    r14
0x18003c280  push    r15
0x18003c282  sub     rsp, 200h
0x18003c289  mov     [rsp+238h+var_1F0], 0FFFFFFFFFFFFFFFEh
0x18003c292  mov     [rax+8], rbx
0x18003c296  mov     r15b, r8b
0x18003c299  mov     r13, rdx
0x18003c29c  mov     rbp, rcx
0x18003c29f  lea     rcx, [rsp+238h+var_1E8]; this
0x18003c2a4  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x18003c2a9  nop
0x18003c2aa  mov     r8b, r15b; bool
0x18003c2ad  lea     rdx, [rsp+238h+var_1E8]; struct WindowsPerformanceRecorder::CETWProperties *
0x18003c2b2  mov     rcx, rbp; this
0x18003c2b5  call    ?GetRegistryETWProperties@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z; WindowsPerformanceRecorder::CControlManager::GetRegistryETWProperties(WindowsPerformanceRecorder::CETWProperties &,bool)
0x18003c2ba  mov     ebx, eax
0x18003c2bc  test    eax, eax
0x18003c2be  js      loc_18003C630
0x18003c2c4  mov     r14, [r13+10h]
0x18003c2c8  mov     [rsp+238h+var_1F8], r14
0x18003c2cd  mov     rsi, [r13+8]
0x18003c2d1  mov     rdx, r14
0x18003c2d4  sub     rdx, rsi
0x18003c2d7  mov     r12, [rsp+238h+var_1D8]
0x18003c2dc  mov     rcx, r12
0x18003c2df  mov     rdi, [rsp+238h+var_1E0]
0x18003c2e4  sub     rcx, rdi
0x18003c2e7  cmp     rdx, rcx
0x18003c2ea  jz      short loc_18003C2F6
0x18003c2ec  mov     ebx, 0C5583002h
0x18003c2f1  jmp     loc_18003C630
0x18003c2f6  cmp     rsi, r14
0x18003c2f9  jz      loc_18003C5F0
0x18003c2ff  lea     r14, aWs_0; "%ws"
0x18003c306  test    ebx, ebx
0x18003c308  js      loc_18003C630
0x18003c30e  xor     al, al
0x18003c310  mov     [rsp+238h+arg_18], al
0x18003c317  cmp     rdi, r12
0x18003c31a  jz      loc_18003C657
0x18003c320  test    ebx, ebx
0x18003c322  js      loc_18003C5C1
0x18003c328  mov     rcx, [rdi]; this
0x18003c32b  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003c330  mov     r9, rax
0x18003c333  mov     rcx, [rsi]; this
0x18003c336  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003c33b  mov     r8, [rbp+0E0h]; unsigned __int16 *
0x18003c342  mov     rdx, r9; unsigned __int16 *
0x18003c345  mov     rcx, rax; this
0x18003c348  call    ?CompareWPREventSessionNames@WindowsPerformanceRecorder@@YA_NPEBG00@Z; WindowsPerformanceRecorder::CompareWPREventSessionNames(ushort const *,ushort const *,ushort const *)
0x18003c34d  test    al, al
0x18003c34f  jz      loc_18003C424
0x18003c355  mov     rdx, [rsi]
0x18003c358  mov     r8, [rdi]
0x18003c35b  mov     rax, [r8+20h]
0x18003c35f  cmp     [r8+18h], rax
0x18003c363  setz    cl
0x18003c366  mov     rax, [rdx+20h]
0x18003c36a  cmp     [rdx+18h], rax
0x18003c36e  setz    al
0x18003c371  or      cl, al; this
0x18003c373  mov     byte ptr [rsp+238h+Format], cl; bool
0x18003c377  mov     r9b, r15b; bool
0x18003c37a  mov     r8, [r8+8]; struct _EVENT_TRACE_PROPERTIES *
0x18003c37e  mov     rdx, [rdx+8]; struct _EVENT_TRACE_PROPERTIES *
0x18003c382  call    ?ValidateEventSession@CControlManager@WindowsPerformanceRecorder@@AEBAJPEBU_EVENT_TRACE_PROPERTIES@@0_N1@Z; WindowsPerformanceRecorder::CControlManager::ValidateEventSession(_EVENT_TRACE_PROPERTIES const *,_EVENT_TRACE_PROPERTIES const *,bool,bool)
0x18003c387  test    eax, eax
0x18003c389  jz      short loc_18003C3B2
0x18003c38b  mov     rcx, [rsi]; this
0x18003c38e  cmp     dword ptr [rcx], 1
0x18003c391  jz      loc_18003C56D
0x18003c397  cmp     dword ptr [rcx], 2
0x18003c39a  jz      loc_18003C566
0x18003c3a0  cmp     dword ptr [rcx], 3
0x18003c3a3  jz      loc_18003C55F
0x18003c3a9  cmp     dword ptr [rcx], 5
0x18003c3ac  jz      loc_18003C558
0x18003c3b2  mov     al, 1
0x18003c3b4  mov     [rsp+238h+arg_18], al
0x18003c3bb  test    r15b, r15b
0x18003c3be  jnz     short loc_18003C42B
0x18003c3c0  mov     r14, [rsi]
0x18003c3c3  mov     ecx, [r14]
0x18003c3c6  sub     ecx, 1
0x18003c3c9  jz      loc_18003C4B1
0x18003c3cf  sub     ecx, 1
0x18003c3d2  jz      loc_18003C463
0x18003c3d8  sub     ecx, 1; this
0x18003c3db  jz      short loc_18003C445
0x18003c3dd  cmp     ecx, 2
0x18003c3e0  jnz     loc_18003C54C
0x18003c3e6  mov     rcx, r14; this
0x18003c3e9  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003c3ee  mov     r8, rax; unsigned __int16 *
0x18003c3f1  mov     rax, [rdi]
0x18003c3f4  add     rax, 18h
0x18003c3f8  lea     r9, [r14+18h]
0x18003c3fc  mov     rdx, [r13+140h]; unsigned __int16 *
0x18003c403  mov     r10, rbp
0x18003c406  mov     [rsp+238h+Format], rax; __int64
0x18003c40b  mov     rcx, rbp; this
0x18003c40e  call    ?ValidateEventProviders@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBG0AEBV?$vector@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@1@Z; WindowsPerformanceRecorder::CControlManager::ValidateEventProviders(ushort const *,ushort const *,std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider> const &,std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider> const &)
0x18003c413  mov     ebx, eax
0x18003c415  test    eax, eax
0x18003c417  js      loc_18003C4F0
0x18003c41d  lea     r14, aWs_0; "%ws"
0x18003c424  mov     al, [rsp+238h+arg_18]
0x18003c42b  add     rdi, 8
0x18003c42f  mov     r15b, [rsp+238h+arg_10]
0x18003c437  cmp     rdi, r12
0x18003c43a  jz      loc_18003C5C8
0x18003c440  jmp     loc_18003C320
0x18003c445  mov     r8, [rdi]; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18003c448  mov     rdx, r14; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18003c44b  call    ?ValidateHeapEventProvidersWithRegistryState@CControlManager@WindowsPerformanceRecorder@@AEBAJAEBUCEventSession@CETWProperties@2@0@Z; WindowsPerformanceRecorder::CControlManager::ValidateHeapEventProvidersWithRegistryState(WindowsPerformanceRecorder::CETWProperties::CEventSession const &,WindowsPerformanceRecorder::CETWProperties::CEventSession const &)
0x18003c450  mov     ebx, eax
0x18003c452  test    eax, eax
0x18003c454  jns     short loc_18003C41D
0x18003c456  mov     r9, [r14+8]
0x18003c45a  add     r9, 18h
0x18003c45e  jmp     loc_18003C4E6
0x18003c463  mov     rax, [rdi]
0x18003c466  mov     rcx, [rax+8]
0x18003c46a  mov     edx, [rcx+48h]
0x18003c46d  mov     rax, [r14+8]
0x18003c471  mov     ecx, [rax+48h]
0x18003c474  cmp     ecx, edx
0x18003c476  jz      loc_18003C3E6
0x18003c47c  mov     ebx, 0C5583004h
0x18003c481  mov     [rsp+238h+var_208], edx
0x18003c485  mov     dword ptr [rsp+238h+var_210], ecx; char *
0x18003c489  lea     rax, aEnableflags0xX; "EnableFlags=0x%x, EnableFlags=0x%x"
0x18003c490  mov     [rsp+238h+Format], rax; Format
0x18003c495  mov     r9d, ebx; unsigned int
0x18003c498  mov     r8d, 177Dh; char *
0x18003c49e  lea     rdx, aValidatewithre; "ValidateWithRegistryState"
0x18003c4a5  mov     ecx, 2; this
0x18003c4aa  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003c4af  jmp     short loc_18003C4F0
0x18003c4b1  mov     r15, [r14+8]
0x18003c4b5  cmp     dword ptr [r15+48h], 0
0x18003c4ba  jnz     short loc_18003C4CD
0x18003c4bc  mov     rax, [rdi]
0x18003c4bf  mov     rcx, [rax+8]; this
0x18003c4c3  cmp     dword ptr [rcx+48h], 0
0x18003c4c7  jz      loc_18003C41D
0x18003c4cd  mov     r8, [rdi]; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18003c4d0  mov     rdx, r14; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18003c4d3  call    ?ValidateSystemProvidersWithRegistryState@CControlManager@WindowsPerformanceRecorder@@AEBAJAEBUCEventSession@CETWProperties@2@0@Z; WindowsPerformanceRecorder::CControlManager::ValidateSystemProvidersWithRegistryState(WindowsPerformanceRecorder::CETWProperties::CEventSession const &,WindowsPerformanceRecorder::CETWProperties::CEventSession const &)
0x18003c4d8  mov     ebx, eax
0x18003c4da  test    eax, eax
0x18003c4dc  jns     loc_18003C41D
0x18003c4e2  lea     r9, [r15+18h]; struct _GUID *
0x18003c4e6  mov     edx, eax; int
0x18003c4e8  mov     rcx, rbp; this
0x18003c4eb  call    ?SetProviderControlErrorInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@@Z; WindowsPerformanceRecorder::CControlManager::SetProviderControlErrorInfo(long,_GUID const &,_GUID const *)
0x18003c4f0  mov     rcx, [rsi]; this
0x18003c4f3  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003c4f8  mov     [rsp+238h+Format], rax
0x18003c4fd  lea     r9, IID_IControlManager
0x18003c504  mov     r8d, 2
0x18003c50a  mov     edx, ebx
0x18003c50c  mov     rcx, rbp
0x18003c50f  call    ?SetControlErrorInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJW4__MIDL_IControlErrorInfo_0001@@AEBU_GUID@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(long,__MIDL_IControlErrorInfo_0001,_GUID const &,ushort const *)
0x18003c514  mov     rcx, [rsi]; this
0x18003c517  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003c51c  mov     [rsp+238h+var_210], rax; char *
0x18003c521  lea     r14, aWs_0; "%ws"
0x18003c528  mov     [rsp+238h+Format], r14; Format
0x18003c52d  mov     r9d, ebx; unsigned int
0x18003c530  mov     r8d, 179Dh; char *
0x18003c536  lea     rdx, aValidatewithre; "ValidateWithRegistryState"
0x18003c53d  mov     ecx, 2; this
0x18003c542  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003c547  jmp     loc_18003C424
0x18003c54c  lea     r14, aWs_0; "%ws"
0x18003c553  jmp     loc_18003C42B
0x18003c558  mov     ebx, 0C5583016h
0x18003c55d  jmp     short loc_18003C572
0x18003c55f  mov     ebx, 0C5583005h
0x18003c564  jmp     short loc_18003C572
0x18003c566  mov     ebx, 0C5583004h
0x18003c56b  jmp     short loc_18003C572
0x18003c56d  mov     ebx, 0C5583003h
0x18003c572  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003c577  mov     [rsp+238h+Format], rax
0x18003c57c  lea     r9, IID_IControlManager
0x18003c583  mov     r8d, 2
0x18003c589  mov     edx, ebx
0x18003c58b  mov     rcx, rbp
0x18003c58e  call    ?SetControlErrorInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJW4__MIDL_IControlErrorInfo_0001@@AEBU_GUID@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(long,__MIDL_IControlErrorInfo_0001,_GUID const &,ushort const *)
0x18003c593  mov     rcx, [rsi]; this
0x18003c596  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003c59b  mov     [rsp+238h+var_210], rax; char *
0x18003c5a0  mov     [rsp+238h+Format], r14; Format
0x18003c5a5  mov     r9d, ebx; unsigned int
0x18003c5a8  mov     r8d, 1760h; char *
0x18003c5ae  lea     rdx, aValidatewithre; "ValidateWithRegistryState"
0x18003c5b5  mov     ecx, 2; this
0x18003c5ba  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003c5bf  jmp     short loc_18003C5D0
0x18003c5c1  mov     al, [rsp+238h+arg_18]
0x18003c5c8  test    al, al
0x18003c5ca  jz      loc_18003C657
0x18003c5d0  mov     eax, ebx
0x18003c5d2  add     rsi, 8
0x18003c5d6  cmp     rsi, [rsp+238h+var_1F8]
0x18003c5db  jz      short loc_18003C5EC
0x18003c5dd  mov     r12, [rsp+238h+var_1D8]
0x18003c5e2  mov     rdi, [rsp+238h+var_1E0]
0x18003c5e7  jmp     loc_18003C306
0x18003c5ec  test    eax, eax
0x18003c5ee  js      short loc_18003C630
0x18003c5f0  mov     eax, dword ptr [rsp+238h+var_E8]
0x18003c5f7  cmp     [r13+100h], eax
0x18003c5fe  jz      short loc_18003C630
0x18003c600  mov     ebx, 0C558300Bh
0x18003c605  mov     dword ptr [rsp+238h+var_210], eax; char *
0x18003c609  lea     rax, aRegistryLoggin; "Registry LoggingMode %d"
0x18003c610  mov     [rsp+238h+Format], rax; Format
0x18003c615  mov     r8d, 17AFh; char *
0x18003c61b  mov     r9d, ebx; unsigned int
0x18003c61e  lea     rdx, aValidatewithre; "ValidateWithRegistryState"
0x18003c625  mov     ecx, 2; this
0x18003c62a  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18003c62f  nop
0x18003c630  lea     rcx, [rsp+238h+var_1E8]; this
0x18003c635  call    ??1CETWProperties@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::CETWProperties::~CETWProperties(void)
0x18003c63a  mov     eax, ebx
0x18003c63c  mov     rbx, [rsp+238h+arg_0]
0x18003c644  add     rsp, 200h
0x18003c64b  pop     r15
0x18003c64d  pop     r14
0x18003c64f  pop     r13
0x18003c651  pop     r12
0x18003c653  pop     rdi
0x18003c654  pop     rsi
0x18003c655  pop     rbp
0x18003c656  retn
0x18003c657  mov     ebx, 0C5583011h
0x18003c65c  mov     rcx, [rsi]; this
0x18003c65f  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003c664  mov     [rsp+238h+Format], rax
0x18003c669  lea     r9, IID_IControlManager
0x18003c670  mov     r8d, 2
0x18003c676  mov     edx, ebx
0x18003c678  mov     rcx, rbp
0x18003c67b  call    ?SetControlErrorInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJW4__MIDL_IControlErrorInfo_0001@@AEBU_GUID@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(long,__MIDL_IControlErrorInfo_0001,_GUID const &,ushort const *)
0x18003c680  mov     rcx, [rsi]; this
0x18003c683  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003c688  mov     [rsp+238h+var_210], rax
0x18003c68d  mov     [rsp+238h+Format], r14
0x18003c692  mov     r8d, 17A6h
0x18003c698  jmp     short loc_18003C61B
```

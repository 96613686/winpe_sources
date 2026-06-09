# WPRCCreateInstanceUnderInstanceName

- ea: `0x18001cdd0`
- end: `0x18001d188`
- name: `WPRCCreateInstanceUnderInstanceName`
- size: `952`
- prototype: `__int64 __fastcall(BSTR pbstr, _DWORD *, __int64, int, __int64, void (__fastcall ****)(_QWORD, GUID *, __int64 *))`
- caller_count: `7`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c5a0`
- `0x18001c8bc`
- `0x180031374`
- `0x180036fe8`
- `0x180037fb0`
- `0x18004a858`
- `0x1800725f0`

## callees

- `0x180008330`
- `0x180009a84`
- `0x18000eeb0`
- `0x18001cdd0`
- `0x18001e6e0`
- `0x1800234f0`
- `0x180040a04`
- `0x1800462a0`
- `0x1800538f0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d14d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d14d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ce62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ce62`
- `OLEAUT32!__imp_SysStringLen` at `0x18001d025`
- `OLEAUT32!__imp_SysStringLen` at `0x18001d025`

## string_xrefs

- `0x18001ce2a`: `COMGUARD`
- `0x18001d0a0`: `COMGUARD`
- `0x18001d101`: `COMGUARD`
- `0x18001ce3f`: `WPRCCreateInstanceUnderInstanceName`
- `0x18001cffb`: `WPRCCreateInstanceUnderInstanceName`
- `0x18001d06b`: `WPRCCreateInstanceUnderInstanceName`
- `0x18001d0b5`: `WPRCCreateInstanceUnderInstanceName`
- `0x18001d116`: `WPRCCreateInstanceUnderInstanceName`
- `0x18001d058`: `InstanceName (%ws), clsid (0x%x...)`

## pseudocode

```c
__int64 __fastcall WPRCCreateInstanceUnderInstanceName(
        BSTR pbstr,
        _DWORD *a2,
        __int64 a3,
        int a4,
        __int64 a5,
        void (__fastcall ****a6)(_QWORD, GUID *, __int64 *))
{
  __int64 v6; // rdi
  char v9; // r15
  signed int Instance; // eax
  int v12; // ebx
  struct _RTL_CRITICAL_SECTION *v13; // r12
  struct ATL::_ATL_OBJMAP_ENTRY30 **i; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v15; // rsi
  _DWORD *v16; // rdx
  _QWORD *v17; // rdi
  bool v18; // sf
  int v19; // eax
  void (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v21; // rax
  struct WindowsPerformanceRecorder::CWPRControl *v22; // rbx
  BSTR v23; // rdx
  signed int v24; // eax
  signed int v25; // eax
  char *v26; // [rsp+28h] [rbp-51h]
  char *v27; // [rsp+28h] [rbp-51h]
  __int64 v28; // [rsp+40h] [rbp-39h] BYREF
  __int64 v29; // [rsp+48h] [rbp-31h] BYREF
  char *v30; // [rsp+50h] [rbp-29h] BYREF
  char v31; // [rsp+58h] [rbp-21h]
  struct WindowsPerformanceRecorder::CWPRControl *v32[2]; // [rsp+60h] [rbp-19h] BYREF
  LPCRITICAL_SECTION v33; // [rsp+70h] [rbp-9h] BYREF
  char v34; // [rsp+78h] [rbp-1h]

  v32[1] = (struct WindowsPerformanceRecorder::CWPRControl *)-2LL;
  v6 = a3;
  v9 = 1;
  if ( a4 != 1 )
    return 2147942487LL;
  v32[0] = 0;
  Instance = WindowsPerformanceRecorder::CWPRControl::GetInstance(v32);
  v12 = Instance;
  if ( Instance >= 0 )
  {
    v13 = WindowsPerformanceRecorder::g_spWPRControlCriticalSection;
    v33 = WindowsPerformanceRecorder::g_spWPRControlCriticalSection;
    EnterCriticalSection(WindowsPerformanceRecorder::g_spWPRControlCriticalSection);
    v34 = 1;
    v29 = 0;
    if ( ATL::_AtlComModule )
    {
      v12 = 0;
      for ( i = off_1800BDED0; i < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_1800BDED8; ++i )
      {
        v15 = *i;
        if ( *i )
        {
          if ( *((_QWORD *)v15 + 2) )
          {
            v16 = *(_DWORD **)v15;
            if ( *a2 == **(_DWORD **)v15 && a2[1] == v16[1] && a2[2] == v16[2] && a2[3] == v16[3] )
            {
              v17 = (_QWORD *)((char *)v15 + 32);
              if ( !*((_QWORD *)v15 + 4) )
              {
                v30 = (char *)qword_1800BDEE0;
                v31 = 0;
                v12 = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v30);
                if ( v12 < 0 )
                {
                  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v30);
LABEL_24:
                  v6 = a3;
                  break;
                }
                if ( !*v17 )
                  v12 = (*((__int64 (__fastcall **)(_QWORD, GUID *, __int64))v15 + 2))(
                          *((_QWORD *)v15 + 3),
                          &GUID_00000000_0000_0000_c000_000000000046,
                          (__int64)v15 + 32);
                ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v30);
              }
              if ( *v17 )
                v12 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v17)(*v17, &IID_IClassFactory, &v29);
              goto LABEL_24;
            }
          }
        }
      }
      if ( v29 )
      {
        v18 = v12 < 0;
      }
      else
      {
        v18 = v12 < 0;
        if ( !v12 )
        {
          v12 = -2147221231;
          goto LABEL_32;
        }
      }
      if ( !v18 )
      {
        v19 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, void (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v29 + 24LL))(
                v29,
                v6,
                a5,
                a6);
        if ( v19 >= 0 )
        {
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          v20 = *a6;
          v21 = 0;
          v28 = 0;
          if ( v20 )
          {
            (**v20)(v20, &GUID_00383df6_90fc_49c0_b65e_0b585bdfddda, &v28);
            v21 = v28;
          }
          if ( v21 )
          {
            v22 = v32[0];
            if ( pbstr && SysStringLen(pbstr) )
            {
              v23 = pbstr;
            }
            else
            {
              v9 = 0;
              v23 = (BSTR)*((_QWORD *)v22 + 23);
            }
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v30,
              v23);
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)4,
              (unsigned __int8)"WPRCCreateInstanceUnderInstanceName",
              (const char *)0x4C,
              0,
              "InstanceName (%ws), clsid (0x%x...)",
              v30,
              *a2);
            if ( !v9 )
              pbstr = (BSTR)*((_QWORD *)v22 + 23);
            v24 = (*(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v28 + 24LL))(v28, pbstr);
            v12 = v24;
            if ( v24 >= 0 )
            {
              v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 32LL))(v28);
              v12 = v25;
              if ( v25 >= 0 )
              {
                WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v30);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
                v12 = 0;
                goto LABEL_54;
              }
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)2,
                (unsigned __int8)"WPRCCreateInstanceUnderInstanceName",
                (const char *)0x4F,
                v25,
                "COMGUARD",
                v27);
              ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
              if ( v28 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            }
            else
            {
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)2,
                (unsigned __int8)"WPRCCreateInstanceUnderInstanceName",
                (const char *)0x4E,
                v24,
                "COMGUARD",
                v27);
              ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
              if ( v28 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
            }
            LeaveCriticalSection(v13);
            return (unsigned int)v12;
          }
          v12 = -2147418113;
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"WPRCCreateInstanceUnderInstanceName",
            (const char *)0x46,
            0x8000FFFF,
            "InstanceScopeObject is null",
            v26);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
LABEL_54:
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v33);
          return (unsigned int)v12;
        }
        v12 = v19;
      }
    }
    else
    {
      v12 = -2147418113;
    }
LABEL_32:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
    goto LABEL_54;
  }
  WindowsPerformanceRecorder::TraceHR(
    (WindowsPerformanceRecorder *)2,
    (unsigned __int8)"WPRCCreateInstanceUnderInstanceName",
    (const char *)0x33,
    Instance,
    "COMGUARD",
    v26);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001cdd0  mov     [rsp-8+arg_10], r8
0x18001cdd5  push    rbp
0x18001cdd6  push    rbx
0x18001cdd7  push    rsi
0x18001cdd8  push    rdi
0x18001cdd9  push    r12
0x18001cddb  push    r13
0x18001cddd  push    r14
0x18001cddf  push    r15
0x18001cde1  lea     rbp, [rsp-0Fh]
0x18001cde6  sub     rsp, 88h
0x18001cded  mov     [rbp+47h+var_58], 0FFFFFFFFFFFFFFFEh
0x18001cdf5  mov     rdi, r8
0x18001cdf8  mov     r13, rdx
0x18001cdfb  mov     r14, rcx
0x18001cdfe  mov     r15d, 1
0x18001ce04  cmp     r9d, r15d
0x18001ce07  jz      short loc_18001CE13
0x18001ce09  mov     eax, 80070057h
0x18001ce0e  jmp     loc_18001D174
0x18001ce13  mov     [rbp+47h+var_60], 0
0x18001ce1b  lea     rcx, [rbp+47h+var_60]; struct WindowsPerformanceRecorder::CWPRControl **
0x18001ce1f  call    ?GetInstance@CWPRControl@WindowsPerformanceRecorder@@SAJPEAPEAV12@@Z; WindowsPerformanceRecorder::CWPRControl::GetInstance(WindowsPerformanceRecorder::CWPRControl * *)
0x18001ce24  mov     ebx, eax
0x18001ce26  test    eax, eax
0x18001ce28  jns     short loc_18001CE54
0x18001ce2a  lea     rcx, aComguard; "COMGUARD"
0x18001ce31  mov     [rsp+0C0h+Format], rcx; Format
0x18001ce36  mov     r9d, eax; unsigned int
0x18001ce39  mov     r8d, 33h ; '3'; char *
0x18001ce3f  lea     rdx, aWprccreateinst_1; "WPRCCreateInstanceUnderInstanceName"
0x18001ce46  lea     ecx, [r8-31h]; this
0x18001ce4a  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001ce4f  jmp     loc_18001D172
0x18001ce54  mov     r12, cs:?g_spWPRControlCriticalSection@WindowsPerformanceRecorder@@3V?$CAtlGlobalPtr@VCComAutoCriticalSection@ATL@@@Performance@@A; Performance::CAtlGlobalPtr<ATL::CComAutoCriticalSection> WindowsPerformanceRecorder::g_spWPRControlCriticalSection
0x18001ce5b  mov     [rbp+47h+var_50], r12
0x18001ce5f  mov     rcx, r12; lpCriticalSection
0x18001ce62  call    cs:__imp_EnterCriticalSection
0x18001ce68  mov     [rbp+47h+var_48], r15b
0x18001ce6c  mov     [rbp+47h+var_78], 0
0x18001ce74  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18001ce7b  jnz     short loc_18001CE87
0x18001ce7d  mov     ebx, 8000FFFFh
0x18001ce82  jmp     loc_18001CF90
0x18001ce87  xor     ebx, ebx
0x18001ce89  mov     rcx, cs:off_1800BDED0
0x18001ce90  xor     r8d, r8d
0x18001ce93  cmp     rcx, cs:off_1800BDED8
0x18001ce9a  jnb     loc_18001CF58
0x18001cea0  mov     rsi, [rcx]
0x18001cea3  test    rsi, rsi
0x18001cea6  jz      short loc_18001CED4
0x18001cea8  cmp     [rsi+10h], r8
0x18001ceac  jz      short loc_18001CED4
0x18001ceae  mov     rdx, [rsi]
0x18001ceb1  mov     eax, [rdx]
0x18001ceb3  cmp     [r13+0], eax
0x18001ceb7  jnz     short loc_18001CED4
0x18001ceb9  mov     eax, [rdx+4]
0x18001cebc  cmp     [r13+4], eax
0x18001cec0  jnz     short loc_18001CED4
0x18001cec2  mov     eax, [rdx+8]
0x18001cec5  cmp     [r13+8], eax
0x18001cec9  jnz     short loc_18001CED4
0x18001cecb  mov     eax, [rdx+0Ch]
0x18001cece  cmp     [r13+0Ch], eax
0x18001ced2  jz      short loc_18001CEDA
0x18001ced4  add     rcx, 8
0x18001ced8  jmp     short loc_18001CE93
0x18001ceda  lea     rdi, [rsi+20h]
0x18001cede  cmp     [rdi], r8
0x18001cee1  jnz     short loc_18001CF34
0x18001cee3  lea     rax, qword_1800BDEE0
0x18001ceea  mov     [rbp+47h+var_70], rax
0x18001ceee  mov     [rbp+47h+var_68], r8b
0x18001cef2  lea     rcx, [rbp+47h+var_70]
0x18001cef6  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18001cefb  mov     ebx, eax
0x18001cefd  test    eax, eax
0x18001ceff  jns     short loc_18001CF0C
0x18001cf01  lea     rcx, [rbp+47h+var_70]
0x18001cf05  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001cf0a  jmp     short loc_18001CF54
0x18001cf0c  cmp     qword ptr [rdi], 0
0x18001cf10  jnz     short loc_18001CF2B
0x18001cf12  mov     r8, rdi
0x18001cf15  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001cf1c  mov     rcx, [rsi+18h]
0x18001cf20  mov     rax, [rsi+10h]
0x18001cf24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf29  mov     ebx, eax
0x18001cf2b  lea     rcx, [rbp+47h+var_70]
0x18001cf2f  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001cf34  mov     rcx, [rdi]
0x18001cf37  test    rcx, rcx
0x18001cf3a  jz      short loc_18001CF54
0x18001cf3c  mov     rax, [rcx]
0x18001cf3f  lea     r8, [rbp+47h+var_78]
0x18001cf43  lea     rdx, IID_IClassFactory
0x18001cf4a  mov     rax, [rax]
0x18001cf4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf52  mov     ebx, eax
0x18001cf54  mov     rdi, [rbp+47h+arg_10]
0x18001cf58  mov     rcx, [rbp+47h+var_78]
0x18001cf5c  test    rcx, rcx
0x18001cf5f  jnz     short loc_18001CF6C
0x18001cf61  test    ebx, ebx
0x18001cf63  jnz     short loc_18001CF6E
0x18001cf65  mov     ebx, 80040111h
0x18001cf6a  jmp     short loc_18001CF90
0x18001cf6c  test    ebx, ebx
0x18001cf6e  js      short loc_18001CF90
0x18001cf70  mov     rax, [rcx]
0x18001cf73  mov     rbx, [rbp+47h+arg_28]
0x18001cf77  mov     r9, rbx
0x18001cf7a  mov     r8, [rbp+47h+arg_20]
0x18001cf7e  mov     rdx, rdi
0x18001cf81  mov     rax, [rax+18h]
0x18001cf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf8a  test    eax, eax
0x18001cf8c  jns     short loc_18001CF9E
0x18001cf8e  mov     ebx, eax
0x18001cf90  lea     rcx, [rbp+47h+var_78]
0x18001cf94  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001cf99  jmp     loc_18001D169
0x18001cf9e  mov     rcx, [rbp+47h+var_78]
0x18001cfa2  test    rcx, rcx
0x18001cfa5  jz      short loc_18001CFB4
0x18001cfa7  mov     rax, [rcx]
0x18001cfaa  mov     rax, [rax+10h]
0x18001cfae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfb3  nop
0x18001cfb4  mov     rcx, [rbx]
0x18001cfb7  xor     eax, eax
0x18001cfb9  mov     [rbp+47h+var_80], rax
0x18001cfbd  test    rcx, rcx
0x18001cfc0  jz      short loc_18001CFDC
0x18001cfc2  mov     rax, [rcx]
0x18001cfc5  lea     r8, [rbp+47h+var_80]
0x18001cfc9  lea     rdx, _GUID_00383df6_90fc_49c0_b65e_0b585bdfddda
0x18001cfd0  mov     rax, [rax]
0x18001cfd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cfd8  mov     rax, [rbp+47h+var_80]
0x18001cfdc  test    rax, rax
0x18001cfdf  jnz     short loc_18001D019
0x18001cfe1  lea     rax, aInstancescopeo; "InstanceScopeObject is null"
0x18001cfe8  mov     [rsp+0C0h+Format], rax; Format
0x18001cfed  mov     ebx, 8000FFFFh
0x18001cff2  mov     r9d, ebx; unsigned int
0x18001cff5  mov     r8d, 46h ; 'F'; char *
0x18001cffb  lea     rdx, aWprccreateinst_1; "WPRCCreateInstanceUnderInstanceName"
0x18001d002  lea     ecx, [r8-44h]; this
0x18001d006  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d00b  lea     rcx, [rbp+47h+var_80]
0x18001d00f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d014  jmp     loc_18001D169
0x18001d019  mov     rbx, [rbp+47h+var_60]
0x18001d01d  test    r14, r14
0x18001d020  jz      short loc_18001D034
0x18001d022  mov     rcx, r14; pbstr
0x18001d025  call    cs:__imp_SysStringLen
0x18001d02b  test    eax, eax
0x18001d02d  jz      short loc_18001D034
0x18001d02f  mov     rdx, r14
0x18001d032  jmp     short loc_18001D03E
0x18001d034  xor     r15b, r15b
0x18001d037  mov     rdx, [rbx+0B8h]
0x18001d03e  lea     rcx, [rbp+47h+var_70]
0x18001d042  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001d047  mov     eax, [r13+0]
0x18001d04b  mov     [rsp+0C0h+var_90], eax
0x18001d04f  mov     rax, [rbp+47h+var_70]
0x18001d053  mov     [rsp+0C0h+var_98], rax; char *
0x18001d058  lea     rax, aInstancenameWs_1; "InstanceName (%ws), clsid (0x%x...)"
0x18001d05f  mov     [rsp+0C0h+Format], rax; Format
0x18001d064  xor     r9d, r9d; unsigned int
0x18001d067  lea     r8d, [r9+4Ch]; char *
0x18001d06b  lea     rdx, aWprccreateinst_1; "WPRCCreateInstanceUnderInstanceName"
0x18001d072  lea     ecx, [r9+4]; this
0x18001d076  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d07b  mov     rcx, [rbp+47h+var_80]
0x18001d07f  mov     rax, [rcx]
0x18001d082  test    r15b, r15b
0x18001d085  jnz     short loc_18001D08E
0x18001d087  mov     r14, [rbx+0B8h]
0x18001d08e  mov     rdx, r14
0x18001d091  mov     rax, [rax+18h]
0x18001d095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d09a  mov     ebx, eax
0x18001d09c  test    eax, eax
0x18001d09e  jns     short loc_18001D0EB
0x18001d0a0  lea     rcx, aComguard; "COMGUARD"
0x18001d0a7  mov     [rsp+0C0h+Format], rcx; Format
0x18001d0ac  mov     r9d, eax; unsigned int
0x18001d0af  mov     r8d, 4Eh ; 'N'; char *
0x18001d0b5  lea     rdx, aWprccreateinst_1; "WPRCCreateInstanceUnderInstanceName"
0x18001d0bc  lea     ecx, [r8-4Ch]; this
0x18001d0c0  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d0c5  mov     rcx, [rbp+47h+var_70]
0x18001d0c9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d0cd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d0d2  nop
0x18001d0d3  mov     rcx, [rbp+47h+var_80]
0x18001d0d7  test    rcx, rcx
0x18001d0da  jz      short loc_18001D0E9
0x18001d0dc  mov     rax, [rcx]
0x18001d0df  mov     rax, [rax+10h]
0x18001d0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0e8  nop
0x18001d0e9  jmp     short loc_18001D14A
0x18001d0eb  mov     rcx, [rbp+47h+var_80]
0x18001d0ef  mov     rax, [rcx]
0x18001d0f2  mov     rax, [rax+20h]
0x18001d0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0fb  mov     ebx, eax
0x18001d0fd  test    eax, eax
0x18001d0ff  jns     short loc_18001D155
0x18001d101  lea     rcx, aComguard; "COMGUARD"
0x18001d108  mov     [rsp+0C0h+Format], rcx; Format
0x18001d10d  mov     r9d, eax; unsigned int
0x18001d110  mov     r8d, 4Fh ; 'O'; char *
0x18001d116  lea     rdx, aWprccreateinst_1; "WPRCCreateInstanceUnderInstanceName"
0x18001d11d  lea     ecx, [r8-4Dh]; this
0x18001d121  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001d126  mov     rcx, [rbp+47h+var_70]
0x18001d12a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001d12e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001d133  nop
0x18001d134  mov     rcx, [rbp+47h+var_80]
0x18001d138  test    rcx, rcx
0x18001d13b  jz      short loc_18001D14A
0x18001d13d  mov     rax, [rcx]
0x18001d140  mov     rax, [rax+10h]
0x18001d144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d149  nop
0x18001d14a  mov     rcx, r12; lpCriticalSection
0x18001d14d  call    cs:__imp_LeaveCriticalSection
0x18001d153  jmp     short loc_18001D172
0x18001d155  lea     rcx, [rbp+47h+var_70]; this
0x18001d159  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001d15e  lea     rcx, [rbp+47h+var_80]
0x18001d162  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001d167  xor     ebx, ebx
0x18001d169  lea     rcx, [rbp+47h+var_50]
0x18001d16d  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001d172  mov     eax, ebx
0x18001d174  add     rsp, 88h
0x18001d17b  pop     r15
0x18001d17d  pop     r14
0x18001d17f  pop     r13
0x18001d181  pop     r12
0x18001d183  pop     rdi
0x18001d184  pop     rsi
0x18001d185  pop     rbx
0x18001d186  pop     rbp
0x18001d187  retn
```

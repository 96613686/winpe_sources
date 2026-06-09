# WindowsPerformanceRecorder::CControlManager::LogCaptureStateProviderError(_GUID,ulong)

- ea: `0x1800604bc`
- end: `0x1800605ab`
- name: `?LogCaptureStateProviderError@CControlManager@WindowsPerformanceRecorder@@AEAAXU_GUID@@K@Z`
- size: `239`
- prototype: `void __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, struct _GUID *__struct_ptr, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800091b0`
- `0x18002f5c4`

## callees

- `0x180008330`
- `0x1800131a0`
- `0x18001c458`
- `0x18001c820`
- `0x1800600a0`
- `0x1800604bc`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006059a`
- `OLEAUT32!__imp_SysFreeString` at `0x18006059a`

## string_xrefs

- `0x18006054e`: `Access Denied`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WindowsPerformanceRecorder::CControlManager::LogCaptureStateProviderError(
        WindowsPerformanceRecorder::CControlManager *this,
        struct _GUID *a2,
        unsigned int a3)
{
  unsigned int v4; // ebx
  unsigned int v5; // ebx
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  const wchar_t *v8; // rdx
  __int64 v9; // [rsp+20h] [rbp-20h] BYREF
  BSTR bstrString[3]; // [rsp+28h] [rbp-18h] BYREF

  bstrString[1] = (BSTR)-2LL;
  bstrString[0] = 0;
  (*(void (__fastcall **)(char *, BSTR *, struct _GUID *))(*((_QWORD *)this + 23) + 160LL))(
    (char *)this + 184,
    bstrString,
    a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v9);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v9,
    L"%x",
    a3);
  v4 = a3 - 1;
  if ( v4 )
  {
    v5 = v4 - 4;
    if ( v5 )
    {
      v6 = v5 - 82;
      if ( v6 )
      {
        v7 = v6 - 1363;
        if ( v7 )
        {
          if ( v7 != 10 )
            goto LABEL_12;
          v8 = L"Timeout";
        }
        else
        {
          v8 = L"No System Resources";
        }
      }
      else
      {
        v8 = L"Invalid Parameter";
      }
    }
    else
    {
      v8 = L"Access Denied";
    }
  }
  else
  {
    v8 = L"Invalid Function";
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v9, v8);
LABEL_12:
  if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 8) != 0 )
    McTemplateU0zz_EventWriteTransfer(
      &WindowsPerformanceRecorderControlProvider_Context,
      Perf_CaptureState_Failed,
      bstrString[0],
      v9);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v9);
  SysFreeString(bstrString[0]);
}

```

## disassembly

```asm
0x1800604bc  push    rbp
0x1800604be  mov     rbp, rsp
0x1800604c1  sub     rsp, 40h
0x1800604c5  mov     [rbp+var_10], 0FFFFFFFFFFFFFFFEh
0x1800604cd  mov     [rsp+40h+arg_18], rbx
0x1800604d2  mov     ebx, r8d
0x1800604d5  mov     [rbp+bstrString], 0
0x1800604dd  add     rcx, 0B8h
0x1800604e4  mov     rax, [rcx]
0x1800604e7  mov     r8, rdx
0x1800604ea  lea     rdx, [rbp+bstrString]
0x1800604ee  mov     rax, [rax+0A0h]
0x1800604f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800604fa  lea     rcx, [rbp+var_20]; void *
0x1800604fe  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180060503  nop
0x180060504  mov     r8d, ebx
0x180060507  lea     rdx, asc_18009BAB8; "%x"
0x18006050e  lea     rcx, [rbp+var_20]
0x180060512  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180060517  sub     ebx, 1
0x18006051a  jz      short loc_180060557
0x18006051c  sub     ebx, 4
0x18006051f  jz      short loc_18006054E
0x180060521  sub     ebx, 52h ; 'R'
0x180060524  jz      short loc_180060545
0x180060526  sub     ebx, 553h
0x18006052c  jz      short loc_18006053C
0x18006052e  cmp     ebx, 0Ah
0x180060531  jnz     short loc_180060567
0x180060533  lea     rdx, aTimeout; "Timeout"
0x18006053a  jmp     short loc_18006055E
0x18006053c  lea     rdx, aNoSystemResour; "No System Resources"
0x180060543  jmp     short loc_18006055E
0x180060545  lea     rdx, aInvalidParamet; "Invalid Parameter"
0x18006054c  jmp     short loc_18006055E
0x18006054e  lea     rdx, aAccessDenied; "Access Denied"
0x180060555  jmp     short loc_18006055E
0x180060557  lea     rdx, aInvalidFunctio; "Invalid Function"
0x18006055e  lea     rcx, [rbp+var_20]
0x180060562  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180060567  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 8
0x18006056e  jz      short loc_18006058C
0x180060570  mov     r9, [rbp+var_20]
0x180060574  mov     r8, [rbp+bstrString]
0x180060578  lea     rdx, Perf_CaptureState_Failed
0x18006057f  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x180060586  call    McTemplateU0zz_EventWriteTransfer
0x18006058b  nop
0x18006058c  lea     rcx, [rbp+var_20]; this
0x180060590  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180060595  nop
0x180060596  mov     rcx, [rbp+bstrString]; bstrString
0x18006059a  call    cs:__imp_SysFreeString
0x1800605a0  mov     rbx, [rsp+40h+arg_18]
0x1800605a5  add     rsp, 40h
0x1800605a9  pop     rbp
0x1800605aa  retn
```

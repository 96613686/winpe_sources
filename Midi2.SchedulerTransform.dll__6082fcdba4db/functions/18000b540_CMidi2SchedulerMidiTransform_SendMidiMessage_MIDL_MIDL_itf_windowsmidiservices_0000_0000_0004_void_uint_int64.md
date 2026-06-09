# CMidi2SchedulerMidiTransform::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x18000b540`
- end: `0x18000b95c`
- name: `?SendMidiMessage@CMidi2SchedulerMidiTransform@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `1052`
- prototype: `__int64 __fastcall(__int64, unsigned int, LARGE_INTEGER, unsigned int, LONGLONG)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800016dc`
- `0x1800017f4`
- `0x180007864`
- `0x1800096d8`
- `0x18000a518`
- `0x18000b540`
- `0x18000b964`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x18000b637`
- `msvcp_win!_Mtx_lock` at `0x18000b637`
- `msvcp_win!_Mtx_unlock` at `0x18000b6ad`
- `msvcp_win!_Mtx_unlock` at `0x18000b6ad`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b646`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b661`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b646`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b661`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18000b6d4`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18000b6d4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000b58e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000b58e`

## pseudocode

```c
__int64 __fastcall CMidi2SchedulerMidiTransform::SendMidiMessage(
        __int64 a1,
        unsigned int a2,
        LARGE_INTEGER a3,
        unsigned int a4,
        LONGLONG a5)
{
  __int64 v9; // rax
  __int64 result; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  volatile signed __int32 *v13; // r8
  __int64 v14; // rax
  _DWORD *v15; // rcx
  int v16; // r8d
  int v17; // r9d
  _QWORD *v18; // rax
  _DWORD *v19; // rcx
  int v20; // r8d
  int v21; // r9d
  const char *v22; // rax
  signed int v23; // edi
  _DWORD *v24; // rcx
  int v25; // r8d
  int v26; // r9d
  const char *v27; // rax
  int v28; // edi
  _DWORD *v29; // rcx
  int v30; // r8d
  int v31; // r9d
  _QWORD *v32; // rax
  _DWORD *v33; // rcx
  int v34; // r8d
  int v35; // r9d
  const char *v36; // rdx
  _QWORD *v37; // rax
  int v38; // [rsp+20h] [rbp-78h]
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-48h] BYREF
  const char *v40; // [rsp+58h] [rbp-40h] BYREF
  const wchar_t *v41; // [rsp+60h] [rbp-38h] BYREF
  const char *v42; // [rsp+68h] [rbp-30h] BYREF
  _QWORD v43[5]; // [rsp+70h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  _QWORD *v45; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v46; // [rsp+B8h] [rbp+20h] BYREF

  v46 = a4;
  v45 = (_QWORD *)a1;
  v9 = *(_QWORD *)(a1 + 248);
  if ( v9 && (*(_DWORD *)(v9 + 4) & 1) != 0 )
    return 0;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  if ( a5 && (unsigned __int64)a5 > PerformanceCount.QuadPart )
  {
    if ( (unsigned __int64)(a5 - PerformanceCount.QuadPart) <= *(_QWORD *)(a1 + 104) )
    {
      try
      {
        v11 = *(_QWORD *)(a1 + 96);
        v12 = *(_QWORD *)(a1 + 112);
        if ( a5 <= PerformanceCount.QuadPart + v12 + v11
          || PerformanceCount.QuadPart >= (unsigned __int64)(a5 - v12 - v11) )
        {
          v23 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))CMidi2SchedulerMidiTransform::SendMidiMessageNow)(
                  a1,
                  a2,
                  (LARGE_INTEGER)a3.QuadPart,
                  a4,
                  a5);
          if ( v23 < 0 )
          {
            v24 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
            if ( *v24 > 2u )
            {
              PerformanceCount.LowPart = v23;
              v27 = (const char *)(a1 + 16);
              if ( *(_QWORD *)(a1 + 40) > 7u )
                v27 = *(const char **)v27;
              v42 = v27;
              v41 = L"Error sending MIDI Message now (message timestamp older than window)";
              v40 = (const char *)a1;
              v43[0] = "CMidi2SchedulerMidiTransform::SendMidiMessage";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (_DWORD)v24,
                (unsigned int)byte_1800117C9,
                v25,
                v26,
                (__int64)v43,
                (__int64)&v40,
                (__int64)&v41,
                (__int64)&v42,
                (__int64)&PerformanceCount);
            }
            result = (unsigned int)v23;
          }
          else
          {
            result = 525825;
          }
        }
        else if ( a4 < 4 )
        {
          v19 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
          if ( *v19 > 2u )
          {
            v22 = (const char *)(a1 + 16);
            if ( *(_QWORD *)(a1 + 40) > 7u )
              v22 = *(const char **)v22;
            v42 = v22;
            v41 = L"Invalid message data size";
            v40 = (const char *)a1;
            PerformanceCount.QuadPart = (LONGLONG)"CMidi2SchedulerMidiTransform::SendMidiMessage";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v19,
              (unsigned int)byte_18001171B,
              v20,
              v21,
              (__int64)&PerformanceCount,
              (__int64)&v40,
              (__int64)&v41,
              (__int64)&v42);
          }
          result = 2148009506LL;
        }
        else if ( *(_QWORD *)(a1 + 80) >= 0x2710u )
        {
          v15 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
          if ( *v15 > 2u )
          {
            v18 = (_QWORD *)(a1 + 16);
            if ( *(_QWORD *)(a1 + 40) > 7u )
              v18 = (_QWORD *)*v18;
            PerformanceCount.QuadPart = (LONGLONG)v18;
            v40 = (const char *)L"Outbound message queue full";
            v41 = (const wchar_t *)a1;
            v42 = "CMidi2SchedulerMidiTransform::SendMidiMessage";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v15,
              (unsigned int)word_180011772,
              v16,
              v17,
              (__int64)&v42,
              (__int64)&v41,
              (__int64)&v40,
              (__int64)&PerformanceCount);
          }
          result = 2148009505LL;
        }
        else
        {
          v43[0] = a1 + 136;
          if ( _Mtx_lock((_Mtx_t)(a1 + 136)) )
            std::_Throw_Cpp_error(5);
          if ( *(_DWORD *)(a1 + 212) == 0x7FFFFFFF )
          {
            *(_DWORD *)(a1 + 212) = 2147483646;
            std::_Throw_Cpp_error(6);
          }
          v13 = (volatile signed __int32 *)(a1 + 216);
          if ( *(_QWORD *)(a1 + 80) )
            _InterlockedIncrement(v13);
          else
            _InterlockedExchange(v13, 0);
          PerformanceCount = a3;
          std::priority_queue<ScheduledUmpMessage,std::deque<ScheduledUmpMessage>,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>::emplace<__int64 &,std::atomic<unsigned int> &,unsigned int &,unsigned char *>(
            a1 + 48,
            (unsigned int)&a5,
            (_DWORD)v13,
            (unsigned int)&v46,
            (__int64)&PerformanceCount);
          _Mtx_unlock((_Mtx_t)(a1 + 136));
          v14 = *(_QWORD *)(a1 + 248);
          if ( !v14 || (*(_DWORD *)(v14 + 4) & 1) == 0 )
          {
            *(_DWORD *)(a1 + 260) = 1;
            WakeByAddressAll((PVOID)(a1 + 260));
          }
          result = 525826;
        }
      }
      catch ( ... )
      {
        v33 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
        if ( *v33 > 2u )
        {
          v36 = (const char *)v45;
          v37 = v45 + 2;
          if ( v45[5] > 7u )
            v37 = (_QWORD *)*v37;
          v45 = v37;
          v43[0] = L"Exception scheduling message";
          v42 = v36;
          v41 = (const wchar_t *)"CMidi2SchedulerMidiTransform::SendMidiMessage";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            (_DWORD)v33,
            (unsigned int)&dword_1800116C4,
            v34,
            v35,
            (__int64)&v41,
            (__int64)&v42,
            (__int64)v43,
            (__int64)&v45);
        }
        return 2147500037LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"avcore\\midi2\\transform\\schedulertransform\\midi2.schedulermiditransform.cpp",
        (const char *)0x80080623LL,
        v38);
      return 2148009507LL;
    }
  }
  else
  {
    v28 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))CMidi2SchedulerMidiTransform::SendMidiMessageNow)(
            a1,
            a2,
            (LARGE_INTEGER)a3.QuadPart,
            a4,
            a5);
    if ( v28 < 0 )
    {
      v29 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
      if ( *v29 > 2u )
      {
        LODWORD(v45) = v28;
        v32 = (_QWORD *)(a1 + 16);
        if ( *(_QWORD *)(a1 + 40) > 7u )
          v32 = (_QWORD *)*v32;
        v43[0] = v32;
        v42 = (const char *)L"Error sending MIDI Message now (bypass queue)";
        v41 = (const wchar_t *)a1;
        v40 = "CMidi2SchedulerMidiTransform::SendMidiMessage";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v29,
          (unsigned int)word_18001182A,
          v30,
          v31,
          (__int64)&v40,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)v43,
          (__int64)&v45);
      }
      return (unsigned int)v28;
    }
    else
    {
      return 525825;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b540  mov     [rsp+arg_8], rbx
0x18000b545  mov     [rsp+arg_18], r9d
0x18000b54a  mov     [rsp+arg_0], rcx
0x18000b54f  push    rsi
0x18000b550  push    rdi
0x18000b551  push    r14
0x18000b553  sub     rsp, 80h
0x18000b55a  mov     edi, r9d
0x18000b55d  mov     r14, r8
0x18000b560  mov     esi, edx
0x18000b562  mov     rbx, rcx
0x18000b565  mov     rax, [rcx+0F8h]
0x18000b56c  test    rax, rax
0x18000b56f  jz      short loc_18000B580
0x18000b571  mov     eax, [rax+4]
0x18000b574  nop
0x18000b575  test    al, 1
0x18000b577  jz      short loc_18000B580
0x18000b579  xor     eax, eax
0x18000b57b  jmp     loc_18000B947
0x18000b580  mov     qword ptr [rsp+98h+PerformanceCount], 0
0x18000b589  lea     rcx, [rsp+98h+PerformanceCount]; lpPerformanceCount
0x18000b58e  call    cs:__imp_QueryPerformanceCounter
0x18000b594  mov     rcx, [rsp+98h+arg_20]
0x18000b59c  test    rcx, rcx
0x18000b59f  jz      loc_18000B898
0x18000b5a5  mov     rdx, qword ptr [rsp+98h+PerformanceCount]
0x18000b5aa  cmp     rcx, rdx
0x18000b5ad  jbe     loc_18000B898
0x18000b5b3  mov     rax, rcx
0x18000b5b6  sub     rax, rdx
0x18000b5b9  cmp     rax, [rbx+68h]
0x18000b5bd  jbe     short loc_18000B5E7
0x18000b5bf  mov     rcx, [rsp+98h]; this
0x18000b5c7  mov     ebx, 80080623h
0x18000b5cc  mov     r9d, ebx; char *
0x18000b5cf  lea     r8, aAvcoreMidi2Tra_0; "avcore\\midi2\\transform\\schedulertran"...
0x18000b5d6  mov     edx, 135h; void *
0x18000b5db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5e0  mov     eax, ebx
0x18000b5e2  jmp     loc_18000B947
0x18000b5e7  mov     r8, [rbx+60h]
0x18000b5eb  mov     r9, [rbx+70h]
0x18000b5ef  lea     rax, [r9+r8]
0x18000b5f3  add     rax, rdx
0x18000b5f6  cmp     rcx, rax
0x18000b5f9  jle     loc_18000B7E0
0x18000b5ff  mov     rax, rcx
0x18000b602  sub     rax, r9
0x18000b605  sub     rax, r8
0x18000b608  cmp     rdx, rax
0x18000b60b  jnb     loc_18000B7E0
0x18000b611  cmp     edi, 4
0x18000b614  jb      loc_18000B762
0x18000b61a  cmp     qword ptr [rbx+50h], 2710h
0x18000b622  jnb     loc_18000B6E4
0x18000b628  lea     rdi, [rbx+88h]
0x18000b62f  mov     [rsp+98h+var_28], rdi
0x18000b634  mov     rcx, rdi; _Mtx_t
0x18000b637  call    cs:__imp__Mtx_lock
0x18000b63d  test    eax, eax
0x18000b63f  jz      short loc_18000B64C
0x18000b641  mov     ecx, 5
0x18000b646  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000b64c  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x18000b653  jnz     short loc_18000B668
0x18000b655  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x18000b65c  mov     ecx, 6
0x18000b661  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000b667  nop
0x18000b668  lea     r8, [rbx+0D8h]
0x18000b66f  cmp     qword ptr [rbx+50h], 0
0x18000b674  jnz     short loc_18000B67D
0x18000b676  xor     eax, eax
0x18000b678  xchg    eax, [r8]
0x18000b67b  jmp     short loc_18000B681
0x18000b67d  lock inc dword ptr [r8]
0x18000b681  mov     qword ptr [rsp+98h+PerformanceCount], r14
0x18000b686  lea     rax, [rsp+98h+PerformanceCount]
0x18000b68b  mov     [rsp+98h+var_78], rax
0x18000b690  lea     r9, [rsp+98h+arg_18]
0x18000b698  lea     rdx, [rsp+98h+arg_20]
0x18000b6a0  lea     rcx, [rbx+30h]
0x18000b6a4  call    ??$emplace@AEA_JAEAU?$atomic@I@std@@AEAIPEAE@?$priority_queue@UScheduledUmpMessage@@V?$deque@UScheduledUmpMessage@@V?$allocator@UScheduledUmpMessage@@@std@@@std@@P6A_NAEAU1@0@Z@std@@QEAAXAEA_JAEAU?$atomic@I@1@AEAI$$QEAPEAE@Z; std::priority_queue<ScheduledUmpMessage,std::deque<ScheduledUmpMessage>,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>::emplace<__int64 &,std::atomic<uint> &,uint &,uchar *>(__int64 &,std::atomic<uint> &,uint &,uchar * &&)
0x18000b6a9  nop
0x18000b6aa  mov     rcx, rdi; _Mtx_t
0x18000b6ad  call    cs:__imp__Mtx_unlock
0x18000b6b3  mov     rax, [rbx+0F8h]
0x18000b6ba  test    rax, rax
0x18000b6bd  jz      short loc_18000B6C7
0x18000b6bf  mov     eax, [rax+4]
0x18000b6c2  nop
0x18000b6c3  test    al, 1
0x18000b6c5  jnz     short loc_18000B6DA
0x18000b6c7  lea     rcx, [rbx+104h]; Address
0x18000b6ce  mov     dword ptr [rcx], 1
0x18000b6d4  call    cs:__imp_WakeByAddressAll
0x18000b6da  mov     eax, 80602h
0x18000b6df  jmp     loc_18000B947
0x18000b6e4  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000b6e9  mov     rcx, [rax+8]
0x18000b6ed  mov     eax, [rcx]
0x18000b6ef  cmp     eax, 2
0x18000b6f2  jbe     short loc_18000B758
0x18000b6f4  lea     rax, [rbx+10h]
0x18000b6f8  cmp     qword ptr [rax+18h], 7
0x18000b6fd  jbe     short loc_18000B702
0x18000b6ff  mov     rax, [rax]
0x18000b702  mov     qword ptr [rsp+98h+PerformanceCount], rax
0x18000b707  lea     rax, aOutboundMessag; "Outbound message queue full"
0x18000b70e  mov     [rsp+98h+var_40], rax
0x18000b713  mov     [rsp+98h+var_38], rbx
0x18000b718  lea     rax, aCmidi2schedule_0; "CMidi2SchedulerMidiTransform::SendMidiM"...
0x18000b71f  mov     [rsp+98h+var_30], rax
0x18000b724  lea     rax, [rsp+98h+PerformanceCount]
0x18000b729  mov     [rsp+98h+var_60], rax
0x18000b72e  lea     rax, [rsp+98h+var_40]
0x18000b733  mov     [rsp+98h+var_68], rax
0x18000b738  lea     rax, [rsp+98h+var_38]
0x18000b73d  mov     [rsp+98h+var_70], rax
0x18000b742  lea     rax, [rsp+98h+var_30]
0x18000b747  mov     [rsp+98h+var_78], rax
0x18000b74c  lea     rdx, word_180011772
0x18000b753  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000b758  mov     eax, 80080621h
0x18000b75d  jmp     loc_18000B947
0x18000b762  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000b767  mov     rcx, [rax+8]
0x18000b76b  mov     eax, [rcx]
0x18000b76d  cmp     eax, 2
0x18000b770  jbe     short loc_18000B7D6
0x18000b772  lea     rax, [rbx+10h]
0x18000b776  cmp     qword ptr [rax+18h], 7
0x18000b77b  jbe     short loc_18000B780
0x18000b77d  mov     rax, [rax]
0x18000b780  mov     [rsp+98h+var_30], rax
0x18000b785  lea     rax, aInvalidMessage; "Invalid message data size"
0x18000b78c  mov     [rsp+98h+var_38], rax
0x18000b791  mov     [rsp+98h+var_40], rbx
0x18000b796  lea     rax, aCmidi2schedule_0; "CMidi2SchedulerMidiTransform::SendMidiM"...
0x18000b79d  mov     qword ptr [rsp+98h+PerformanceCount], rax
0x18000b7a2  lea     rax, [rsp+98h+var_30]
0x18000b7a7  mov     [rsp+98h+var_60], rax
0x18000b7ac  lea     rax, [rsp+98h+var_38]
0x18000b7b1  mov     [rsp+98h+var_68], rax
0x18000b7b6  lea     rax, [rsp+98h+var_40]
0x18000b7bb  mov     [rsp+98h+var_70], rax
0x18000b7c0  lea     rax, [rsp+98h+PerformanceCount]
0x18000b7c5  mov     [rsp+98h+var_78], rax
0x18000b7ca  lea     rdx, byte_18001171B
0x18000b7d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000b7d6  mov     eax, 80080622h
0x18000b7db  jmp     loc_18000B947
0x18000b7e0  mov     [rsp+98h+var_78], rcx
0x18000b7e5  mov     r9d, edi
0x18000b7e8  mov     r8, r14
0x18000b7eb  mov     edx, esi
0x18000b7ed  mov     rcx, rbx
0x18000b7f0  call    ?SendMidiMessageNow@CMidi2SchedulerMidiTransform@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidi2SchedulerMidiTransform::SendMidiMessageNow(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x18000b7f5  mov     edi, eax
0x18000b7f7  test    eax, eax
0x18000b7f9  js      short loc_18000B805
0x18000b7fb  mov     eax, 80601h
0x18000b800  jmp     loc_18000B947
0x18000b805  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000b80a  mov     rcx, [rax+8]
0x18000b80e  mov     eax, [rcx]
0x18000b810  cmp     eax, 2
0x18000b813  jbe     short loc_18000B887
0x18000b815  mov     dword ptr [rsp+98h+PerformanceCount], edi
0x18000b819  lea     rax, [rbx+10h]
0x18000b81d  cmp     qword ptr [rax+18h], 7
0x18000b822  jbe     short loc_18000B827
0x18000b824  mov     rax, [rax]
0x18000b827  mov     [rsp+98h+var_30], rax
0x18000b82c  lea     rax, aErrorSendingMi; "Error sending MIDI Message now (message"...
0x18000b833  mov     [rsp+98h+var_38], rax
0x18000b838  mov     [rsp+98h+var_40], rbx
0x18000b83d  lea     rax, aCmidi2schedule_0; "CMidi2SchedulerMidiTransform::SendMidiM"...
0x18000b844  mov     [rsp+98h+var_28], rax
0x18000b849  lea     rax, [rsp+98h+PerformanceCount]
0x18000b84e  mov     [rsp+98h+var_58], rax
0x18000b853  lea     rax, [rsp+98h+var_30]
0x18000b858  mov     [rsp+98h+var_60], rax
0x18000b85d  lea     rax, [rsp+98h+var_38]
0x18000b862  mov     [rsp+98h+var_68], rax
0x18000b867  lea     rax, [rsp+98h+var_40]
0x18000b86c  mov     [rsp+98h+var_70], rax
0x18000b871  lea     rax, [rsp+98h+var_28]
0x18000b876  mov     [rsp+98h+var_78], rax
0x18000b87b  lea     rdx, byte_1800117C9
0x18000b882  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000b887  mov     eax, edi
0x18000b889  jmp     loc_18000B947
0x18000b88e  mov     eax, 80004005h
0x18000b893  jmp     loc_18000B947
0x18000b898  mov     [rsp+98h+var_78], rcx
0x18000b89d  mov     r9d, edi
0x18000b8a0  mov     r8, r14
0x18000b8a3  mov     edx, esi
0x18000b8a5  mov     rcx, rbx
0x18000b8a8  call    ?SendMidiMessageNow@CMidi2SchedulerMidiTransform@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidi2SchedulerMidiTransform::SendMidiMessageNow(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x18000b8ad  mov     edi, eax
0x18000b8af  test    eax, eax
0x18000b8b1  js      short loc_18000B8BD
0x18000b8b3  mov     eax, 80601h
0x18000b8b8  jmp     loc_18000B947
0x18000b8bd  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000b8c2  mov     rcx, [rax+8]
0x18000b8c6  mov     eax, [rcx]
0x18000b8c8  cmp     eax, 2
0x18000b8cb  jbe     short loc_18000B945
0x18000b8cd  mov     dword ptr [rsp+98h+arg_0], edi
0x18000b8d4  lea     rax, [rbx+10h]
0x18000b8d8  cmp     qword ptr [rax+18h], 7
0x18000b8dd  jbe     short loc_18000B8E2
0x18000b8df  mov     rax, [rax]
0x18000b8e2  mov     [rsp+98h+var_28], rax
0x18000b8e7  lea     rax, aErrorSendingMi_0; "Error sending MIDI Message now (bypass "...
0x18000b8ee  mov     [rsp+98h+var_30], rax
0x18000b8f3  mov     [rsp+98h+var_38], rbx
0x18000b8f8  lea     rax, aCmidi2schedule_0; "CMidi2SchedulerMidiTransform::SendMidiM"...
0x18000b8ff  mov     [rsp+98h+var_40], rax
0x18000b904  lea     rax, [rsp+98h+arg_0]
0x18000b90c  mov     [rsp+98h+var_58], rax
0x18000b911  lea     rax, [rsp+98h+var_28]
0x18000b916  mov     [rsp+98h+var_60], rax
0x18000b91b  lea     rax, [rsp+98h+var_30]
0x18000b920  mov     [rsp+98h+var_68], rax
0x18000b925  lea     rax, [rsp+98h+var_38]
0x18000b92a  mov     [rsp+98h+var_70], rax
0x18000b92f  lea     rax, [rsp+98h+var_40]
0x18000b934  mov     [rsp+98h+var_78], rax
0x18000b939  lea     rdx, word_18001182A
0x18000b940  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000b945  mov     eax, edi
0x18000b947  mov     rbx, [rsp+98h+arg_8]
0x18000b94f  add     rsp, 80h
0x18000b956  pop     r14
0x18000b958  pop     rdi
0x18000b959  pop     rsi
0x18000b95a  retn
```

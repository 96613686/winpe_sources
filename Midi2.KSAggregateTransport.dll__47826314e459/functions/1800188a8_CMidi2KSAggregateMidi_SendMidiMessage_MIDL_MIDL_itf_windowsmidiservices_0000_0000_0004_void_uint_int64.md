# CMidi2KSAggregateMidi::SendMidiMessage(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)

- ea: `0x1800188a8`
- end: `0x180018c7b`
- name: `?SendMidiMessage@CMidi2KSAggregateMidi@@QEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18001af20`

## callees

- `0x18000163c`
- `0x180001d3c`
- `0x180001e28`
- `0x180005020`
- `0x18000b394`
- `0x1800117d8`
- `0x180015630`
- `0x1800188a8`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018974`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018974`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018b33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018bda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018c49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018b33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018bda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018c49`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMidi2KSAggregateMidi::SendMidiMessage(
        struct _RTL_CRITICAL_SECTION *a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  unsigned __int64 v5; // rdi
  _DWORD *v9; // rcx
  int v10; // r8d
  int v11; // r9d
  unsigned __int8 v12; // r13
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // rdi
  int v16; // esi
  unsigned __int8 v17; // al
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  _QWORD *LockSemaphore; // rdx
  __int64 v25; // r8
  _QWORD **v26; // rcx
  __int64 *v27; // rax
  int v28; // eax
  unsigned int v29; // esi
  _DWORD *v31; // rcx
  _DWORD *v32; // rcx
  int v33; // r8d
  int v34; // r9d
  char v35; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v36; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  const char *v38; // [rsp+70h] [rbp-90h] BYREF
  struct _RTL_CRITICAL_SECTION *v39; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v40[3]; // [rsp+80h] [rbp-80h] BYREF
  int v41; // [rsp+98h] [rbp-68h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v44; // [rsp+B0h] [rbp-50h] BYREF
  int v45; // [rsp+C4h] [rbp-3Ch]
  struct _EVENT_DATA_DESCRIPTOR v46; // [rsp+D0h] [rbp-30h] BYREF
  const char *v47; // [rsp+F0h] [rbp-10h]
  __int64 v48; // [rsp+F8h] [rbp-8h]
  const char **v49; // [rsp+100h] [rbp+0h]
  __int64 v50; // [rsp+108h] [rbp+8h]
  const wchar_t *v51; // [rsp+110h] [rbp+10h]
  __int64 v52; // [rsp+118h] [rbp+18h]
  char *v53; // [rsp+120h] [rbp+20h]
  __int64 v54; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v5 = a4;
  v36 = a2;
  v9 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v9 > 5u )
  {
    v43 = a5;
    v41 = v5;
    v44 = a3;
    LODWORD(v37) = a2;
    v42 = (const char *)L"Received UMP message to translate and send";
    v39 = a1;
    v38 = "CMidi2KSAggregateMidi::SendMidiMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (_DWORD)v9,
      (unsigned int)&dword_1800886FC,
      v10,
      v11,
      (__int64)&v38,
      (__int64)&v39,
      (__int64)&v42,
      (__int64)&v37,
      (__int64)&v44,
      (__int64)&v41,
      (__int64)&v43);
  }
  EnterCriticalSection(a1);
  v39 = a1;
  if ( (unsigned int)v5 < 4 )
  {
    v32 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
    if ( *v32 > 2u )
    {
      v36 = v5;
      v38 = (const char *)L"Invalid data length";
      v39 = a1;
      v42 = "CMidi2KSAggregateMidi::SendMidiMessage";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v32,
        (unsigned int)word_180088672,
        v33,
        v34,
        (__int64)&v42,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v36);
    }
    if ( a1 )
      LeaveCriticalSection(a1);
    return 2205548546LL;
  }
  else
  {
    v12 = 0;
    v13 = a3 + 4 * (v5 >> 2);
    v37 = v13;
    v14 = a3;
    v15 = a3;
    v40[0] = a3;
    v40[1] = a3;
    v40[2] = v13;
LABEL_5:
    v16 = 0;
LABEL_6:
    v35 = 0;
    while ( v15 < v13 )
    {
      v17 = WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)v40);
      if ( (unsigned int)((__int64)(v37 - v15) >> 2) < v17 )
      {
        v15 += 4LL
             * WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)v40);
        v40[0] = v15;
        if ( !v16 )
          break;
        goto LABEL_27;
      }
      v18 = *(_DWORD *)v15 >> 28;
      if ( !v18
        || (v19 = v18 - 1) != 0
        && (v20 = v19 - 1) != 0
        && (v21 = v20 - 1) != 0
        && (v22 = v21 - 1) != 0
        && (v23 = v22 - 1) != 0
        && v23 != 8 )
      {
        v15 += 4LL
             * WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)v40);
        v40[0] = v15;
        v14 = v15;
        if ( v16 )
          goto LABEL_27;
        a3 = v15;
      }
      else
      {
        if ( v16 && (HIBYTE(*(_DWORD *)v15) & 0xF) != v12 )
        {
          v14 = v15;
LABEL_27:
          LockSemaphore = a1[1].LockSemaphore;
          v25 = LockSemaphore[1];
          v45 = 0;
          v26 = (_QWORD **)LockSemaphore;
          while ( !*(_BYTE *)(v25 + 25) )
          {
            if ( *(_BYTE *)(v25 + 32) >= v12 )
              v26 = (_QWORD **)v25;
            v27 = (__int64 *)(v25 + 16);
            if ( *(_BYTE *)(v25 + 32) >= v12 )
              v27 = (__int64 *)v25;
            v25 = *v27;
          }
          if ( *((_BYTE *)v26 + 25) || v12 < *((_BYTE *)v26 + 32) || v26 == LockSemaphore )
          {
            v31 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
            if ( *v31 > 3u )
            {
              v35 = v12;
              v38 = (const char *)a1;
              v53 = &v35;
              v54 = 1;
              v51 = L"Group not found in group to pin map. Silently dropping message.";
              v52 = 128;
              v49 = &v38;
              v50 = 8;
              v47 = "CMidi2KSAggregateMidi::SendMidiMessage";
              v48 = 39;
              tlgWriteTransfer_EventWriteTransfer((__int64)v31, (unsigned __int8 *)byte_1800886AD, 0, 0, 6u, &v46);
            }
          }
          else
          {
            v28 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64, _QWORD))(*v26[5] + 40LL))(
                    v26[5],
                    v36,
                    a3,
                    (unsigned int)(4 * v16));
            v29 = v28;
            if ( v28 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x24E,
                (unsigned int)"avcore\\midi2\\transport\\ksaggregatetransport\\midi2.ksaggregatemidi.cpp",
                (const char *)(unsigned int)v28,
                a5);
              LeaveCriticalSection(a1);
              return v29;
            }
          }
          a3 = v14;
          v13 = v37;
          goto LABEL_5;
        }
        v16 += WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)v40);
        v12 = *(_BYTE *)(v15 + 3) & 0xF;
        v15 += 4LL
             * WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)v40);
        v40[0] = v15;
      }
      v13 = v37;
      if ( !v35 && v15 < v37 )
        goto LABEL_6;
      v35 = 1;
      if ( v16 )
        goto LABEL_27;
    }
    if ( a1 )
      LeaveCriticalSection(a1);
    return 0;
  }
}

```

## disassembly

```asm
0x1800188a8  mov     [rsp-8+arg_10], rbx
0x1800188ad  push    rbp
0x1800188ae  push    rsi
0x1800188af  push    rdi
0x1800188b0  push    r12
0x1800188b2  push    r13
0x1800188b4  push    r14
0x1800188b6  push    r15
0x1800188b8  lea     rbp, [rsp-40h]
0x1800188bd  sub     rsp, 140h
0x1800188c4  mov     rax, cs:__security_cookie
0x1800188cb  xor     rax, rsp
0x1800188ce  mov     [rbp+70h+var_40], rax
0x1800188d2  mov     edi, r9d
0x1800188d5  mov     r14, r8
0x1800188d8  mov     ebx, edx
0x1800188da  mov     [rsp+170h+var_10C], edx
0x1800188de  mov     r15, rcx
0x1800188e1  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x1800188e6  mov     rcx, [rax+8]
0x1800188ea  mov     eax, [rcx]
0x1800188ec  lea     rsi, aCmidi2ksaggreg_38; "CMidi2KSAggregateMidi::SendMidiMessage"
0x1800188f3  cmp     eax, 5
0x1800188f6  jbe     short loc_180018971
0x1800188f8  mov     rax, qword ptr [rbp+70h+arg_20]
0x1800188ff  mov     [rbp+70h+var_C8], rax
0x180018903  mov     [rbp+70h+var_D8], edi
0x180018906  mov     [rbp+70h+var_C0], r14
0x18001890a  mov     dword ptr [rsp+170h+var_108], ebx
0x18001890e  lea     rax, aReceivedUmpMes; "Received UMP message to translate and s"...
0x180018915  mov     [rbp+70h+var_D0], rax
0x180018919  mov     [rsp+170h+var_F8], r15
0x18001891e  mov     [rsp+170h+var_100], rsi
0x180018923  lea     rax, [rbp+70h+var_C8]
0x180018927  mov     [rsp+170h+var_120], rax
0x18001892c  lea     rax, [rbp+70h+var_D8]
0x180018930  mov     [rsp+170h+var_128], rax
0x180018935  lea     rax, [rbp+70h+var_C0]
0x180018939  mov     [rsp+170h+var_130], rax
0x18001893e  lea     rax, [rsp+170h+var_108]
0x180018943  mov     [rsp+170h+var_138], rax
0x180018948  lea     rax, [rbp+70h+var_D0]
0x18001894c  mov     [rsp+170h+var_140], rax
0x180018951  lea     rax, [rsp+170h+var_F8]
0x180018956  mov     [rsp+170h+var_148], rax
0x18001895b  lea     rax, [rsp+170h+var_100]
0x180018960  mov     qword ptr [rsp+170h+var_150], rax
0x180018965  lea     rdx, dword_1800886FC
0x18001896c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@464@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180018971  mov     rcx, r15; lpCriticalSection
0x180018974  call    cs:__imp_EnterCriticalSection
0x18001897a  mov     [rsp+170h+var_F8], r15
0x18001897f  cmp     edi, 4
0x180018982  jb      loc_180018BE4
0x180018988  xor     ebx, ebx
0x18001898a  mov     r13b, bl
0x18001898d  mov     rax, rdi
0x180018990  shr     rax, 2
0x180018994  lea     rax, [r14+rax*4]
0x180018998  mov     [rsp+170h+var_108], rax
0x18001899d  mov     r12, r14
0x1800189a0  mov     rdi, r14
0x1800189a3  mov     [rbp+70h+var_F0], r14
0x1800189a7  mov     [rbp+70h+var_E8], r14
0x1800189ab  mov     [rbp+70h+var_E0], rax
0x1800189af  mov     esi, ebx
0x1800189b1  mov     [rsp+170h+var_110], bl
0x1800189b5  cmp     rdi, rax
0x1800189b8  jnb     loc_180018BD2
0x1800189be  lea     rcx, [rbp+70h+var_F0]; this
0x1800189c2  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x1800189c7  movzx   ecx, al
0x1800189ca  mov     rax, [rsp+170h+var_108]
0x1800189cf  sub     rax, rdi
0x1800189d2  sar     rax, 2
0x1800189d6  cmp     eax, ecx
0x1800189d8  jb      loc_180018A8B
0x1800189de  mov     edx, [rdi]
0x1800189e0  mov     ecx, edx
0x1800189e2  shr     ecx, 1Ch
0x1800189e5  test    ecx, ecx
0x1800189e7  jz      short loc_180018A4A
0x1800189e9  sub     ecx, 1
0x1800189ec  jz      short loc_180018A07
0x1800189ee  sub     ecx, 1
0x1800189f1  jz      short loc_180018A07
0x1800189f3  sub     ecx, 1
0x1800189f6  jz      short loc_180018A07
0x1800189f8  sub     ecx, 1
0x1800189fb  jz      short loc_180018A07
0x1800189fd  sub     ecx, 1
0x180018a00  jz      short loc_180018A07
0x180018a02  cmp     ecx, 8
0x180018a05  jnz     short loc_180018A4A
0x180018a07  test    esi, esi
0x180018a09  jz      short loc_180018A1E
0x180018a0b  shr     edx, 18h
0x180018a0e  and     dl, 0Fh
0x180018a11  cmp     dl, r13b
0x180018a14  jz      short loc_180018A1E
0x180018a16  mov     r12, rdi
0x180018a19  jmp     loc_180018AA7
0x180018a1e  lea     rcx, [rbp+70h+var_F0]; this
0x180018a22  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x180018a27  movzx   eax, al
0x180018a2a  add     esi, eax
0x180018a2c  mov     r13b, [rdi+3]
0x180018a30  and     r13b, 0Fh
0x180018a34  lea     rcx, [rbp+70h+var_F0]; this
0x180018a38  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x180018a3d  movzx   eax, al
0x180018a40  lea     rdi, [rdi+rax*4]
0x180018a44  mov     [rbp+70h+var_F0], rdi
0x180018a48  jmp     short loc_180018A68
0x180018a4a  lea     rcx, [rbp+70h+var_F0]; this
0x180018a4e  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x180018a53  movzx   eax, al
0x180018a56  lea     rdi, [rdi+rax*4]
0x180018a5a  mov     [rbp+70h+var_F0], rdi
0x180018a5e  mov     r12, rdi
0x180018a61  test    esi, esi
0x180018a63  jnz     short loc_180018AA7
0x180018a65  mov     r14, rdi
0x180018a68  mov     rax, [rsp+170h+var_108]
0x180018a6d  cmp     [rsp+170h+var_110], bl
0x180018a71  jnz     short loc_180018A7C
0x180018a73  cmp     rdi, rax
0x180018a76  jb      loc_1800189B1
0x180018a7c  mov     [rsp+170h+var_110], 1
0x180018a81  test    esi, esi
0x180018a83  jz      loc_1800189B5
0x180018a89  jmp     short loc_180018AA7
0x180018a8b  lea     rcx, [rbp+70h+var_F0]; this
0x180018a8f  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x180018a94  movzx   eax, al
0x180018a97  lea     rdi, [rdi+rax*4]
0x180018a9b  mov     [rbp+70h+var_F0], rdi
0x180018a9f  test    esi, esi
0x180018aa1  jz      loc_180018BD2
0x180018aa7  mov     rdx, [r15+40h]
0x180018aab  mov     r8, [rdx+8]
0x180018aaf  xor     eax, eax
0x180018ab1  mov     [rbp+70h+var_AC], eax
0x180018ab4  mov     rcx, rdx
0x180018ab7  jmp     short loc_180018ACC
0x180018ab9  cmp     [r8+20h], r13b
0x180018abd  cmovnb  rcx, r8
0x180018ac1  lea     rax, [r8+10h]
0x180018ac5  cmovnb  rax, r8
0x180018ac9  mov     r8, [rax]
0x180018acc  cmp     [r8+19h], bl
0x180018ad0  jz      short loc_180018AB9
0x180018ad2  cmp     [rcx+19h], bl
0x180018ad5  jnz     short loc_180018B40
0x180018ad7  cmp     r13b, [rcx+20h]
0x180018adb  jb      short loc_180018B40
0x180018add  cmp     rcx, rdx
0x180018ae0  jz      short loc_180018B40
0x180018ae2  mov     rcx, [rcx+28h]
0x180018ae6  mov     rax, [rcx]
0x180018ae9  lea     r9d, ds:0[rsi*4]
0x180018af1  mov     rdx, qword ptr [rbp+70h+arg_20]
0x180018af8  mov     qword ptr [rsp+170h+var_150], rdx; int
0x180018afd  mov     r8, r14
0x180018b00  mov     edx, [rsp+170h+var_10C]
0x180018b04  mov     rax, [rax+28h]
0x180018b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b0d  mov     esi, eax
0x180018b0f  test    eax, eax
0x180018b11  jns     loc_180018BC5
0x180018b17  mov     rcx, [rbp+78h]; this
0x180018b1b  mov     r9d, eax; char *
0x180018b1e  lea     r8, aAvcoreMidi2Tra_7; "avcore\\midi2\\transport\\ksaggregatetr"...
0x180018b25  mov     edx, 24Eh; void *
0x180018b2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018b2f  nop
0x180018b30  mov     rcx, r15; lpCriticalSection
0x180018b33  call    cs:__imp_LeaveCriticalSection
0x180018b39  mov     eax, esi
0x180018b3b  jmp     loc_180018C54
0x180018b40  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180018b45  mov     rcx, [rax+8]
0x180018b49  mov     eax, [rcx]
0x180018b4b  cmp     eax, 3
0x180018b4e  jbe     short loc_180018BC5
0x180018b50  mov     [rsp+170h+var_110], r13b
0x180018b55  mov     [rsp+170h+var_100], r15
0x180018b5a  lea     rax, [rsp+170h+var_110]
0x180018b5f  mov     [rbp+70h+var_50], rax
0x180018b63  mov     [rbp+70h+var_48], 1
0x180018b6b  lea     rax, aGroupNotFoundI; "Group not found in group to pin map. Si"...
0x180018b72  mov     [rbp+70h+var_60], rax
0x180018b76  mov     [rbp+70h+var_58], 80h
0x180018b7e  lea     rax, [rsp+170h+var_100]
0x180018b83  mov     [rbp+70h+var_70], rax
0x180018b87  mov     [rbp+70h+var_68], 8
0x180018b8f  lea     rax, aCmidi2ksaggreg_38; "CMidi2KSAggregateMidi::SendMidiMessage"
0x180018b96  mov     [rbp+70h+var_80], rax
0x180018b9a  mov     [rbp+70h+var_78], 27h ; '''
0x180018ba2  lea     rax, [rbp+70h+var_A0]
0x180018ba6  mov     [rsp+170h+var_148], rax
0x180018bab  mov     [rsp+170h+var_150], 6
0x180018bb3  xor     r9d, r9d
0x180018bb6  xor     r8d, r8d
0x180018bb9  lea     rdx, byte_1800886AD
0x180018bc0  call    _tlgWriteTransfer_EventWriteTransfer
0x180018bc5  mov     r14, r12
0x180018bc8  mov     rax, [rsp+170h+var_108]
0x180018bcd  jmp     loc_1800189AF
0x180018bd2  test    r15, r15
0x180018bd5  jz      short loc_180018BE0
0x180018bd7  mov     rcx, r15; lpCriticalSection
0x180018bda  call    cs:__imp_LeaveCriticalSection
0x180018be0  xor     eax, eax
0x180018be2  jmp     short loc_180018C54
0x180018be4  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x180018be9  mov     rcx, [rax+8]
0x180018bed  mov     eax, [rcx]
0x180018bef  cmp     eax, 2
0x180018bf2  jbe     short loc_180018C41
0x180018bf4  mov     [rsp+170h+var_10C], edi
0x180018bf8  lea     rax, aInvalidDataLen; "Invalid data length"
0x180018bff  mov     [rsp+170h+var_100], rax
0x180018c04  mov     [rsp+170h+var_F8], r15
0x180018c09  mov     [rbp+70h+var_D0], rsi
0x180018c0d  lea     rax, [rsp+170h+var_10C]
0x180018c12  mov     [rsp+170h+var_138], rax
0x180018c17  lea     rax, [rsp+170h+var_100]
0x180018c1c  mov     [rsp+170h+var_140], rax
0x180018c21  lea     rax, [rsp+170h+var_F8]
0x180018c26  mov     [rsp+170h+var_148], rax
0x180018c2b  lea     rax, [rbp+70h+var_D0]
0x180018c2f  mov     qword ptr [rsp+170h+var_150], rax
0x180018c34  lea     rdx, word_180088672
0x180018c3b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180018c40  nop
0x180018c41  test    r15, r15
0x180018c44  jz      short loc_180018C4F
0x180018c46  mov     rcx, r15; lpCriticalSection
0x180018c49  call    cs:__imp_LeaveCriticalSection
0x180018c4f  mov     eax, 83760002h
0x180018c54  mov     rcx, [rbp+70h+var_40]
0x180018c58  xor     rcx, rsp; StackCookie
0x180018c5b  call    __security_check_cookie
0x180018c60  mov     rbx, [rsp+170h+arg_10]
0x180018c68  add     rsp, 140h
0x180018c6f  pop     r15
0x180018c71  pop     r14
0x180018c73  pop     r13
0x180018c75  pop     r12
0x180018c77  pop     rdi
0x180018c78  pop     rsi
0x180018c79  pop     rbp
0x180018c7a  retn
```

# CMidiPipe::Callback(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64,__int64)

- ea: `0x140015020`
- end: `0x140015243`
- name: `?Callback@CMidiPipe@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J2@Z`
- size: `547`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned int, __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x140002270`
- `0x14000984c`
- `0x14000c598`
- `0x140015020`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140015220`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140015220`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400150e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1400150e8`

## string_xrefs

- `0x1400151ab`: `avcore\midi2\service\Inc\MidiPipe.h`

## pseudocode

```c
__int64 __fastcall CMidiPipe::Callback(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned __int64 a6)
{
  _DWORD *v10; // rcx
  int v11; // r8d
  int v12; // r9d
  int v13; // edi
  __int64 v14; // r14
  int v15; // esi
  __int64 *v16; // rbx
  unsigned __int8 v17; // al
  int v18; // eax
  __int64 v19; // rdx
  __int64 **v20; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  int v24; // [rsp+20h] [rbp-59h]
  __int64 v25; // [rsp+60h] [rbp-19h] BYREF
  __int64 v26; // [rsp+68h] [rbp-11h] BYREF
  const wchar_t *v27; // [rsp+70h] [rbp-9h] BYREF
  __int64 v28; // [rsp+78h] [rbp-1h] BYREF
  const char *v29; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp+57h] BYREF
  unsigned int v32; // [rsp+D8h] [rbp+5Fh] BYREF
  __int64 v33; // [rsp+E0h] [rbp+67h]

  v33 = a3;
  v10 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v10 > 5u )
  {
    v25 = a5;
    v27 = L"Sending MIDI Message from callback.";
    v29 = "CMidiPipe::Callback";
    v32 = a4;
    v26 = a3;
    LODWORD(SRWLock) = a2;
    v28 = a1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (_DWORD)v10,
      (unsigned int)byte_1400878AD,
      v11,
      v12,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&SRWLock,
      (__int64)&v26,
      (__int64)&v32,
      (__int64)&v25);
  }
  SRWLock = (PSRWLOCK)(a1 + 64);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 64));
  v13 = 0;
  v14 = v33;
  v15 = 0;
  v16 = **(__int64 ***)(a1 + 72);
  while ( !*((_BYTE *)v16 + 25) )
  {
    if ( (a2 & 2) != 0 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v16[5] + 136LL))(v16[5]) && a6 <= 0xF )
    {
      v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16[5] + 144LL))(v16[5]);
      if ( v17 == (_DWORD)a6 )
      {
        v24 = a5;
        v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v16[5] + 72LL))(
                v16[5],
                a2 & 0xFFFFFFFD,
                v14,
                a4);
        v13 = v18;
        if ( v18 < 0 )
        {
          v19 = 145;
LABEL_13:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"avcore\\midi2\\service\\Inc\\MidiPipe.h",
            (const char *)(unsigned int)v18,
            v24);
        }
      }
    }
    else
    {
      v24 = a5;
      v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v16[5] + 72LL))(
              v16[5],
              a2 & 0xFFFFFFFD,
              v14,
              a4);
      v13 = v18;
      if ( v18 < 0 )
      {
        v19 = 150;
        goto LABEL_13;
      }
    }
    if ( v15 >= 0 && v13 < 0 )
      v15 = v13;
    v20 = (__int64 **)v16[2];
    v13 = 0;
    if ( *((_BYTE *)v20 + 25) )
    {
      for ( i = (__int64 *)v16[1]; !*((_BYTE *)i + 25) && v16 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v16 = i;
      v16 = i;
    }
    else
    {
      v16 = (__int64 *)v16[2];
      for ( j = *v20; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v16 = j;
    }
  }
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140015020  mov     [rsp-8+arg_18], rbx
0x140015025  mov     [rsp-8+arg_10], r8
0x14001502a  push    rbp
0x14001502b  push    rsi
0x14001502c  push    rdi
0x14001502d  push    r12
0x14001502f  push    r13
0x140015031  push    r14
0x140015033  push    r15
0x140015035  lea     rbp, [rsp-17h]
0x14001503a  sub     rsp, 90h
0x140015041  mov     r13d, r9d
0x140015044  mov     rdi, r8
0x140015047  mov     r12d, edx
0x14001504a  mov     rbx, rcx
0x14001504d  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140015052  mov     rcx, [rax+8]
0x140015056  mov     eax, [rcx]
0x140015058  cmp     eax, 5
0x14001505b  jbe     short loc_1400150D6
0x14001505d  mov     rax, [rbp+47h+arg_20]
0x140015061  lea     rdx, byte_1400878AD
0x140015068  mov     [rbp+47h+var_60], rax
0x14001506c  lea     rax, aSendingMidiMes; "Sending MIDI Message from callback."
0x140015073  mov     [rbp+47h+var_50], rax
0x140015077  lea     rax, aCmidipipeCallb; "CMidiPipe::Callback"
0x14001507e  mov     [rbp+47h+var_40], rax
0x140015082  lea     rax, [rbp+47h+var_60]
0x140015086  mov     [rsp+0C0h+var_70], rax
0x14001508b  lea     rax, [rbp+47h+arg_8]
0x14001508f  mov     [rsp+0C0h+var_78], rax
0x140015094  lea     rax, [rbp+47h+var_58]
0x140015098  mov     [rsp+0C0h+var_80], rax
0x14001509d  lea     rax, [rbp+47h+SRWLock]
0x1400150a1  mov     [rsp+0C0h+var_88], rax
0x1400150a6  lea     rax, [rbp+47h+var_50]
0x1400150aa  mov     [rsp+0C0h+var_90], rax
0x1400150af  lea     rax, [rbp+47h+var_48]
0x1400150b3  mov     [rsp+0C0h+var_98], rax
0x1400150b8  lea     rax, [rbp+47h+var_40]
0x1400150bc  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1400150c1  mov     [rbp+47h+arg_8], r13d
0x1400150c5  mov     [rbp+47h+var_58], rdi
0x1400150c9  mov     dword ptr [rbp+47h+SRWLock], r12d
0x1400150cd  mov     [rbp+47h+var_48], rbx
0x1400150d1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@464@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400150d6  lea     r14, [rbx+40h]
0x1400150da  mov     r15d, r12d
0x1400150dd  mov     rcx, r14; SRWLock
0x1400150e0  mov     [rbp+47h+SRWLock], r14
0x1400150e4  and     r15d, 2
0x1400150e8  call    cs:__imp_AcquireSRWLockShared
0x1400150ee  mov     rbx, [rbx+48h]
0x1400150f2  xor     edi, edi
0x1400150f4  mov     r14, [rbp+47h+arg_10]
0x1400150f8  mov     esi, edi
0x1400150fa  mov     rbx, [rbx]
0x1400150fd  cmp     [rbx+19h], dil
0x140015101  jnz     loc_140015214
0x140015107  test    r15d, r15d
0x14001510a  jz      short loc_140015177
0x14001510c  mov     rcx, [rbx+28h]
0x140015110  mov     rax, [rcx]
0x140015113  mov     rax, [rax+88h]
0x14001511a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001511f  test    eax, eax
0x140015121  jz      short loc_140015177
0x140015123  cmp     [rbp+47h+arg_28], 0Fh
0x140015128  ja      short loc_140015177
0x14001512a  mov     rcx, [rbx+28h]
0x14001512e  mov     rax, [rcx]
0x140015131  mov     rax, [rax+90h]
0x140015138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001513d  movzx   eax, al
0x140015140  cmp     eax, dword ptr [rbp+47h+arg_28]
0x140015143  jnz     short loc_1400151BA
0x140015145  mov     rcx, [rbx+28h]
0x140015149  mov     edx, r12d
0x14001514c  mov     r8, [rbp+47h+arg_20]
0x140015150  and     edx, 0FFFFFFFDh
0x140015153  mov     qword ptr [rsp+0C0h+var_A0], r8
0x140015158  mov     r9d, r13d
0x14001515b  mov     r8, r14
0x14001515e  mov     rax, [rcx]
0x140015161  mov     rax, [rax+48h]
0x140015165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001516a  mov     edi, eax
0x14001516c  test    eax, eax
0x14001516e  jns     short loc_1400151BA
0x140015170  mov     edx, 91h
0x140015175  jmp     short loc_1400151A7
0x140015177  mov     rcx, [rbx+28h]
0x14001517b  mov     edx, r12d
0x14001517e  mov     r8, [rbp+47h+arg_20]
0x140015182  and     edx, 0FFFFFFFDh
0x140015185  mov     qword ptr [rsp+0C0h+var_A0], r8; int
0x14001518a  mov     r9d, r13d
0x14001518d  mov     r8, r14
0x140015190  mov     rax, [rcx]
0x140015193  mov     rax, [rax+48h]
0x140015197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001519c  mov     edi, eax
0x14001519e  test    eax, eax
0x1400151a0  jns     short loc_1400151BA
0x1400151a2  mov     edx, 96h; void *
0x1400151a7  mov     rcx, [rbp+4Fh]; this
0x1400151ab  lea     r8, aAvcoreMidi2Ser_3; "avcore\\midi2\\service\\Inc\\MidiPipe.h"
0x1400151b2  mov     r9d, eax; char *
0x1400151b5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400151ba  test    esi, esi
0x1400151bc  js      short loc_1400151C3
0x1400151be  test    edi, edi
0x1400151c0  cmovs   esi, edi
0x1400151c3  mov     rcx, [rbx+10h]
0x1400151c7  xor     edi, edi
0x1400151c9  cmp     [rcx+19h], dil
0x1400151cd  jz      short loc_1400151F0
0x1400151cf  mov     rax, [rbx+8]
0x1400151d3  jmp     short loc_1400151E2
0x1400151d5  cmp     rbx, [rax+10h]
0x1400151d9  jnz     short loc_1400151E8
0x1400151db  mov     rbx, rax
0x1400151de  mov     rax, [rax+8]
0x1400151e2  cmp     [rax+19h], dil
0x1400151e6  jz      short loc_1400151D5
0x1400151e8  mov     rbx, rax
0x1400151eb  jmp     loc_1400150FD
0x1400151f0  mov     rbx, rcx
0x1400151f3  mov     rcx, [rcx]
0x1400151f6  cmp     [rcx+19h], dil
0x1400151fa  jnz     loc_1400150FD
0x140015200  mov     rax, [rcx]
0x140015203  mov     rbx, rcx
0x140015206  mov     rcx, rax
0x140015209  cmp     [rax+19h], dil
0x14001520d  jz      short loc_140015200
0x14001520f  jmp     loc_1400150FD
0x140015214  mov     r14, [rbp+47h+SRWLock]
0x140015218  test    r14, r14
0x14001521b  jz      short loc_140015226
0x14001521d  mov     rcx, r14; SRWLock
0x140015220  call    cs:__imp_ReleaseSRWLockShared
0x140015226  mov     rbx, [rsp+0C0h+arg_18]
0x14001522e  mov     eax, esi
0x140015230  add     rsp, 90h
0x140015237  pop     r15
0x140015239  pop     r14
0x14001523b  pop     r13
0x14001523d  pop     r12
0x14001523f  pop     rdi
0x140015240  pop     rsi
0x140015241  pop     rbp
0x140015242  retn
```

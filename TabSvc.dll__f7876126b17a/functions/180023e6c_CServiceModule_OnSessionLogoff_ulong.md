# CServiceModule::OnSessionLogoff(ulong)

- ea: `0x180023e6c`
- end: `0x180023f4b`
- name: `?OnSessionLogoff@CServiceModule@@QEAAXK@Z`
- size: `223`
- prototype: `void __fastcall(CServiceModule *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000fa00`

## callees

- `0x180001ec0`
- `0x180015630`
- `0x180023e6c`
- `0x180024f40`
- `0x1800286b0`
- `0x18002b3a8`

## string_xrefs

- `0x180023e9d`: `PENSERVICE_CServiceModule::OnSessionLogoff`
- `0x180023f23`: `PENSERVICE_CServiceModule::OnSessionLogoff`

## pseudocode

```c
void __fastcall CServiceModule::OnSessionLogoff(CServiceModule *this, unsigned int a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      104,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnSessionLogoff");
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v7 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v4,
      (int)word_180039A72,
      v5,
      v6,
      (__int64)&v7);
  }
  CServiceModule::_RemovePenProcessesWorker(this, 1, 8u, a2);
  CServiceModule::RemovePenSession(this, a2);
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      105,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::OnSessionLogoff");
}

```

## disassembly

```asm
0x180023e6c  mov     [rsp+arg_0], rbx
0x180023e71  mov     [rsp+arg_8], rsi
0x180023e76  push    rdi
0x180023e77  sub     rsp, 30h
0x180023e7b  mov     ebx, edx
0x180023e7d  mov     rdi, rcx
0x180023e80  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e87  lea     rsi, WPP_GLOBAL_Control
0x180023e8e  cmp     rcx, rsi
0x180023e91  jz      short loc_180023EB5
0x180023e93  test    byte ptr [rcx+1Ch], 10h
0x180023e97  jz      short loc_180023EB5
0x180023e99  mov     rcx, [rcx+10h]
0x180023e9d  lea     r9, aPenserviceCser_26; "PENSERVICE_CServiceModule::OnSessionLog"...
0x180023ea4  mov     edx, 68h ; 'h'
0x180023ea9  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180023eb0  call    WPP_SF_s
0x180023eb5  mov     eax, cs:dword_1800411A8
0x180023ebb  cmp     eax, 5
0x180023ebe  jbe     short loc_180023EEF
0x180023ec0  mov     edx, 4000000h
0x180023ec5  lea     rcx, dword_1800411A8
0x180023ecc  call    _tlgKeywordOn
0x180023ed1  test    al, al
0x180023ed3  jz      short loc_180023EEF
0x180023ed5  lea     rax, [rsp+38h+arg_10]
0x180023eda  mov     [rsp+38h+arg_10], ebx
0x180023ede  lea     rdx, word_180039A72
0x180023ee5  mov     [rsp+38h+var_18], rax
0x180023eea  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023eef  mov     edx, 1; unsigned int
0x180023ef4  mov     r9d, ebx; unsigned int
0x180023ef7  mov     rcx, rdi; this
0x180023efa  lea     r8d, [rdx+7]; unsigned int
0x180023efe  call    ?_RemovePenProcessesWorker@CServiceModule@@AEAAXKKK@Z; CServiceModule::_RemovePenProcessesWorker(ulong,ulong,ulong)
0x180023f03  mov     edx, ebx; unsigned int
0x180023f05  mov     rcx, rdi; this
0x180023f08  call    ?RemovePenSession@CServiceModule@@QEAAXK@Z; CServiceModule::RemovePenSession(ulong)
0x180023f0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f14  cmp     rcx, rsi
0x180023f17  jz      short loc_180023F3B
0x180023f19  test    byte ptr [rcx+1Ch], 10h
0x180023f1d  jz      short loc_180023F3B
0x180023f1f  mov     rcx, [rcx+10h]
0x180023f23  lea     r9, aPenserviceCser_26; "PENSERVICE_CServiceModule::OnSessionLog"...
0x180023f2a  mov     edx, 69h ; 'i'
0x180023f2f  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180023f36  call    WPP_SF_s
0x180023f3b  mov     rbx, [rsp+38h+arg_0]
0x180023f40  mov     rsi, [rsp+38h+arg_8]
0x180023f45  add     rsp, 30h
0x180023f49  pop     rdi
0x180023f4a  retn
```

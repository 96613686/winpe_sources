# CServiceModule::RemovePenSession(ulong)

- ea: `0x180024f40`
- end: `0x180025072`
- name: `?RemovePenSession@CServiceModule@@QEAAXK@Z`
- size: `306`
- prototype: `void __fastcall(CServiceModule *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180023e6c`

## callees

- `0x180001ec0`
- `0x1800134f0`
- `0x180015630`
- `0x18001f484`
- `0x180024f40`
- `0x18002b3a8`
- `0x18002b404`
- `0x18002fb4c`

## string_xrefs

- `0x180024f71`: `PENSERVICE_CServiceModule::RemovePenSession`
- `0x18002504a`: `PENSERVICE_CServiceModule::RemovePenSession`

## pseudocode

```c
void __fastcall CServiceModule::RemovePenSession(CServiceModule *this, int a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int PenSession; // eax
  unsigned int v8; // edx
  __int64 v9; // r9
  CPenSession **v10; // rcx
  CPenSession *v11; // rdi
  int v12; // r8d
  int v13; // [rsp+50h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      38,
      (unsigned int)WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      (unsigned int)"PENSERVICE_CServiceModule::RemovePenSession",
      a2);
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v13 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v4,
      (int)byte_180039C61,
      v5,
      v6,
      (__int64)&v13);
  }
  PenSession = CServiceModule::FindPenSession(this, a2);
  v8 = PenSession;
  if ( PenSession != -1 )
  {
    v9 = *((_QWORD *)this + 34);
    v10 = (CPenSession **)(v9 + 8LL * PenSession);
    v11 = *v10;
    if ( *v10 )
    {
      if ( *((_BYTE *)v11 + 8) )
        --*((_DWORD *)this + 21);
      v12 = *((_DWORD *)this + 71);
      if ( PenSession < v12 - 1 )
        memcpy_0(v10, (const void *)(v9 + 8LL * (PenSession + 1)), 8 * (v12 - PenSession) - 8);
      --*((_DWORD *)this + 71);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11, 0xFFFFFFFF) == 1 )
        CPenSession::`scalar deleting destructor'(v11, v8);
    }
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      39,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::RemovePenSession");
}

```

## disassembly

```asm
0x180024f40  mov     [rsp+arg_0], rbx
0x180024f45  mov     [rsp+arg_8], rbp
0x180024f4a  push    rdi
0x180024f4b  sub     rsp, 30h
0x180024f4f  mov     edi, edx
0x180024f51  mov     rbx, rcx
0x180024f54  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f5b  lea     rbp, WPP_GLOBAL_Control
0x180024f62  cmp     rcx, rbp
0x180024f65  jz      short loc_180024F8D
0x180024f67  test    byte ptr [rcx+1Ch], 10h
0x180024f6b  jz      short loc_180024F8D
0x180024f6d  mov     rcx, [rcx+10h]
0x180024f71  lea     r9, aPenserviceCser_6; "PENSERVICE_CServiceModule::RemovePenSes"...
0x180024f78  mov     edx, 26h ; '&'
0x180024f7d  mov     dword ptr [rsp+38h+var_18], edi
0x180024f81  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180024f88  call    WPP_SF_sd
0x180024f8d  mov     eax, cs:dword_1800411A8
0x180024f93  cmp     eax, 5
0x180024f96  jbe     short loc_180024FC7
0x180024f98  mov     edx, 4000000h
0x180024f9d  lea     rcx, dword_1800411A8
0x180024fa4  call    _tlgKeywordOn
0x180024fa9  test    al, al
0x180024fab  jz      short loc_180024FC7
0x180024fad  lea     rax, [rsp+38h+arg_10]
0x180024fb2  mov     [rsp+38h+arg_10], edi
0x180024fb6  lea     rdx, byte_180039C61
0x180024fbd  mov     [rsp+38h+var_18], rax
0x180024fc2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180024fc7  mov     edx, edi; unsigned int
0x180024fc9  mov     rcx, rbx; this
0x180024fcc  call    ?FindPenSession@CServiceModule@@QEAAHK@Z; CServiceModule::FindPenSession(ulong)
0x180024fd1  mov     edx, eax
0x180024fd3  cmp     eax, 0FFFFFFFFh
0x180024fd6  jz      short loc_180025034
0x180024fd8  mov     r9, [rbx+110h]
0x180024fdf  lea     rcx, [r9+rdx*8]; void *
0x180024fe3  mov     rdi, [rcx]
0x180024fe6  test    rdi, rdi
0x180024fe9  jz      short loc_180025034
0x180024feb  cmp     byte ptr [rdi+8], 0
0x180024fef  jz      short loc_180024FF4
0x180024ff1  dec     dword ptr [rbx+54h]
0x180024ff4  mov     r8d, [rbx+11Ch]
0x180024ffb  lea     eax, [r8-1]
0x180024fff  cmp     edx, eax
0x180025001  jnb     short loc_18002501A
0x180025003  sub     r8d, edx
0x180025006  lea     eax, [rdx+1]
0x180025009  lea     rdx, [r9+rax*8]; Src
0x18002500d  lea     r8d, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x180025015  call    memcpy_0
0x18002501a  dec     dword ptr [rbx+11Ch]
0x180025020  or      eax, 0FFFFFFFFh
0x180025023  lock xadd [rdi], eax
0x180025027  cmp     eax, 1
0x18002502a  jnz     short loc_180025034
0x18002502c  mov     rcx, rdi; this
0x18002502f  call    ??_GCPenSession@@QEAAPEAXI@Z; CPenSession::`scalar deleting destructor'(uint)
0x180025034  mov     rcx, cs:WPP_GLOBAL_Control
0x18002503b  cmp     rcx, rbp
0x18002503e  jz      short loc_180025062
0x180025040  test    byte ptr [rcx+1Ch], 10h
0x180025044  jz      short loc_180025062
0x180025046  mov     rcx, [rcx+10h]
0x18002504a  lea     r9, aPenserviceCser_6; "PENSERVICE_CServiceModule::RemovePenSes"...
0x180025051  mov     edx, 27h ; '''
0x180025056  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x18002505d  call    WPP_SF_s
0x180025062  mov     rbx, [rsp+38h+arg_0]
0x180025067  mov     rbp, [rsp+38h+arg_8]
0x18002506c  add     rsp, 30h
0x180025070  pop     rdi
0x180025071  retn
```

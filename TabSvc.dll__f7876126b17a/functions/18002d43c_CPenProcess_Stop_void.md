# CPenProcess::Stop(void)

- ea: `0x18002d43c`
- end: `0x18002d553`
- name: `?Stop@CPenProcess@@QEAAHXZ`
- size: `279`
- prototype: `__int64 __fastcall(CPenProcess *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800286b0`

## callees

- `0x18000256c`
- `0x180015630`
- `0x18002b3a8`
- `0x18002d378`
- `0x18002d43c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002d538`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18002d538`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d513`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d513`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d525`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002d525`

## string_xrefs

- `0x18002d4f4`: `PENSERVICE_CPenProcess::Stop`

## pseudocode

```c
__int64 __fastcall CPenProcess::Stop(CPenProcess *this)
{
  __int64 v2; // rcx
  const WCHAR *v3; // r8
  __int64 v4; // r9
  int v6; // [rsp+50h] [rbp+8h] BYREF
  int v7; // [rsp+58h] [rbp+10h] BYREF
  const WCHAR *v8; // [rsp+60h] [rbp+18h] BYREF

  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    v6 = *((_DWORD *)this + 271);
    v7 = *((_DWORD *)this + 8);
    v8 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v2,
      (int)byte_18003AE01,
      (__int64)v3,
      v4,
      (__int64)&v7,
      &v8,
      (__int64)&v6);
  }
  CPenProcess::ShutdownWatchDogThread(this);
  if ( *((_QWORD *)this + 139) && *((_QWORD *)this + 140) )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
      WPP_SF_s(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        19,
        WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
        "PENSERVICE_CPenProcess::Stop");
    SetEvent(*((HANDLE *)this + 139));
    if ( WaitForSingleObject(*((HANDLE *)this + 136), 0xBB8u) )
      TerminateProcess(*((HANDLE *)this + 136), 0);
  }
  *((_DWORD *)this + 270) = 2;
  return 1;
}

```

## disassembly

```asm
0x18002d43c  push    rbx
0x18002d43e  sub     rsp, 40h
0x18002d442  mov     rax, [rcx]
0x18002d445  lea     r8, aUnknown; "(unknown)"
0x18002d44c  mov     rbx, rcx
0x18002d44f  test    rax, rax
0x18002d452  jz      short loc_18002D45B
0x18002d454  mov     r8, [rax+220h]
0x18002d45b  mov     eax, cs:dword_1800411A8
0x18002d461  cmp     eax, 5
0x18002d464  jbe     short loc_18002D4BB
0x18002d466  mov     edx, 4000000h
0x18002d46b  lea     rcx, dword_1800411A8
0x18002d472  call    _tlgKeywordOn
0x18002d477  test    al, al
0x18002d479  jz      short loc_18002D4BB
0x18002d47b  mov     eax, [rbx+43Ch]
0x18002d481  lea     rdx, byte_18003AE01
0x18002d488  mov     [rsp+48h+arg_0], eax
0x18002d48c  mov     eax, [rbx+20h]
0x18002d48f  mov     [rsp+48h+arg_8], eax
0x18002d493  lea     rax, [rsp+48h+arg_0]
0x18002d498  mov     [rsp+48h+var_18], rax
0x18002d49d  lea     rax, [rsp+48h+arg_10]
0x18002d4a2  mov     [rsp+48h+var_20], rax
0x18002d4a7  lea     rax, [rsp+48h+arg_8]
0x18002d4ac  mov     [rsp+48h+var_28], rax
0x18002d4b1  mov     [rsp+48h+arg_10], r8
0x18002d4b6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002d4bb  mov     rcx, rbx; this
0x18002d4be  call    ?ShutdownWatchDogThread@CPenProcess@@AEAAXXZ; CPenProcess::ShutdownWatchDogThread(void)
0x18002d4c3  cmp     qword ptr [rbx+458h], 0
0x18002d4cb  jz      short loc_18002D53E
0x18002d4cd  cmp     qword ptr [rbx+460h], 0
0x18002d4d5  jz      short loc_18002D53E
0x18002d4d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4de  lea     rax, WPP_GLOBAL_Control
0x18002d4e5  cmp     rcx, rax
0x18002d4e8  jz      short loc_18002D50C
0x18002d4ea  test    byte ptr [rcx+1Ch], 10h
0x18002d4ee  jz      short loc_18002D50C
0x18002d4f0  mov     rcx, [rcx+10h]
0x18002d4f4  lea     r9, aPenserviceCpen_2; "PENSERVICE_CPenProcess::Stop"
0x18002d4fb  mov     edx, 13h
0x18002d500  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18002d507  call    WPP_SF_s
0x18002d50c  mov     rcx, [rbx+458h]; hEvent
0x18002d513  call    cs:__imp_SetEvent
0x18002d519  mov     rcx, [rbx+440h]; hHandle
0x18002d520  mov     edx, 0BB8h; dwMilliseconds
0x18002d525  call    cs:__imp_WaitForSingleObject
0x18002d52b  test    eax, eax
0x18002d52d  jz      short loc_18002D53E
0x18002d52f  mov     rcx, [rbx+440h]; hProcess
0x18002d536  xor     edx, edx; uExitCode
0x18002d538  call    cs:__imp_TerminateProcess
0x18002d53e  mov     dword ptr [rbx+438h], 2
0x18002d548  mov     eax, 1
0x18002d54d  add     rsp, 40h
0x18002d551  pop     rbx
0x18002d552  retn
```

# CPenProcess::CreateWatchDogThread(void)

- ea: `0x18002c744`
- end: `0x18002c8ec`
- name: `?CreateWatchDogThread@CPenProcess@@AEAAXXZ`
- size: `424`
- prototype: `void __fastcall(CPenProcess *this, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180013da0`

## callees

- `0x180001008`
- `0x1800022d4`
- `0x180012dc0`
- `0x180015630`
- `0x18002b3a8`
- `0x18002c744`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002c857`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18002c857`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c826`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002c826`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c7f2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002c7f2`

## string_xrefs

- `0x18002c882`: `PENSERVICE_CPenProcess::CreateWatchDogThread`
- `0x18002c8ba`: `Thread creation failed.`

## pseudocode

```c
void __fastcall CPenProcess::CreateWatchDogThread(CPenProcess *this, __int64 a2)
{
  const WCHAR *v2; // r8
  __int64 v4; // rcx
  __int64 v5; // r9
  void *v6; // rcx
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  const char *v12; // [rsp+60h] [rbp+8h] BYREF
  const WCHAR *v13; // [rsp+68h] [rbp+10h] BYREF
  const WCHAR *v14; // [rsp+70h] [rbp+18h] BYREF

  v2 = L"(unknown)";
  if ( *(_QWORD *)this )
    v2 = *(const WCHAR **)(*(_QWORD *)this + 544LL);
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
  {
    LODWORD(v12) = *((_DWORD *)this + 271);
    v14 = (const WCHAR *)((char *)this + 558);
    v13 = v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v4,
      (int)&dword_18003AC24,
      (__int64)v2,
      v5,
      &v14,
      &v13,
      (__int64)&v12);
  }
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64, const WCHAR *))(**(_QWORD **)this + 16LL))(
         *(_QWORD *)this,
         a2,
         v2) )
  {
    v6 = (void *)*((_QWORD *)this + 141);
    if ( !v6 || WaitForSingleObject(v6, 0) != 258 )
    {
      SH<void *,SH_HANDLE>::Reset((char *)this + 1128);
      SH<void *,SH_HANDLE>::Reset((char *)this + 1136);
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 142) = EventW;
      if ( EventW )
      {
        Thread = CreateThread(0, 0, CPenProcess::StaticWatchDogThreadProc, this, 0, 0);
        *((_QWORD *)this + 141) = Thread;
        if ( !Thread )
        {
          if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
            WPP_SF_s(
              *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
              38,
              WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
              "PENSERVICE_CPenProcess::CreateWatchDogThread");
          if ( (unsigned int)dword_1800411A8 > 5 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
            {
              v12 = "Thread creation failed.";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v9,
                (unsigned __int8 *)&dword_18003B0CC,
                v10,
                v11,
                (const unsigned __int16 **)&v12);
            }
          }
          SH<void *,SH_HANDLE>::Reset((char *)this + 1136);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18002c744  push    rbx
0x18002c746  push    rsi
0x18002c747  push    rdi
0x18002c748  sub     rsp, 40h
0x18002c74c  mov     rax, [rcx]
0x18002c74f  lea     r8, aUnknown; "(unknown)"
0x18002c756  mov     rbx, rcx
0x18002c759  test    rax, rax
0x18002c75c  jz      short loc_18002C765
0x18002c75e  mov     r8, [rax+220h]
0x18002c765  mov     eax, cs:dword_1800411A8
0x18002c76b  cmp     eax, 5
0x18002c76e  jbe     short loc_18002C7CA
0x18002c770  mov     edx, 4000000h
0x18002c775  lea     rcx, dword_1800411A8
0x18002c77c  call    _tlgKeywordOn
0x18002c781  test    al, al
0x18002c783  jz      short loc_18002C7CA
0x18002c785  mov     eax, [rbx+43Ch]
0x18002c78b  lea     rdx, dword_18003AC24
0x18002c792  mov     dword ptr [rsp+58h+arg_0], eax
0x18002c796  lea     rax, [rbx+22Eh]
0x18002c79d  mov     [rsp+58h+arg_10], rax
0x18002c7a2  lea     rax, [rsp+58h+arg_0]
0x18002c7a7  mov     [rsp+58h+var_28], rax
0x18002c7ac  lea     rax, [rsp+58h+arg_8]
0x18002c7b1  mov     [rsp+58h+lpThreadId], rax
0x18002c7b6  lea     rax, [rsp+58h+arg_10]
0x18002c7bb  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x18002c7c0  mov     [rsp+58h+arg_8], r8
0x18002c7c5  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002c7ca  mov     rcx, [rbx]
0x18002c7cd  mov     rax, [rcx]
0x18002c7d0  mov     rax, [rax+10h]
0x18002c7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7d9  test    al, al
0x18002c7db  jz      loc_18002C8E4
0x18002c7e1  lea     rdi, [rbx+468h]
0x18002c7e8  mov     rcx, [rdi]; hHandle
0x18002c7eb  test    rcx, rcx
0x18002c7ee  jz      short loc_18002C803
0x18002c7f0  xor     edx, edx; dwMilliseconds
0x18002c7f2  call    cs:__imp_WaitForSingleObject
0x18002c7f8  cmp     eax, 102h
0x18002c7fd  jz      loc_18002C8E4
0x18002c803  mov     rcx, rdi
0x18002c806  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18002c80b  lea     rsi, [rbx+470h]
0x18002c812  mov     rcx, rsi
0x18002c815  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18002c81a  xor     r9d, r9d; lpName
0x18002c81d  xor     r8d, r8d; bInitialState
0x18002c820  xor     ecx, ecx; lpEventAttributes
0x18002c822  lea     edx, [r9+1]; bManualReset
0x18002c826  call    cs:__imp_CreateEventW
0x18002c82c  mov     [rsi], rax
0x18002c82f  test    rax, rax
0x18002c832  jz      loc_18002C8E4
0x18002c838  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x18002c841  lea     r8, ?StaticWatchDogThreadProc@CPenProcess@@CAKPEAX@Z; lpStartAddress
0x18002c848  mov     r9, rbx; lpParameter
0x18002c84b  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x18002c853  xor     edx, edx; dwStackSize
0x18002c855  xor     ecx, ecx; lpThreadAttributes
0x18002c857  call    cs:__imp_CreateThread
0x18002c85d  mov     [rdi], rax
0x18002c860  test    rax, rax
0x18002c863  jnz     short loc_18002C8E4
0x18002c865  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c86c  lea     rax, WPP_GLOBAL_Control
0x18002c873  cmp     rcx, rax
0x18002c876  jz      short loc_18002C89A
0x18002c878  test    byte ptr [rcx+1Ch], 4
0x18002c87c  jz      short loc_18002C89A
0x18002c87e  mov     rcx, [rcx+10h]
0x18002c882  lea     r9, aPenserviceCpen_9; "PENSERVICE_CPenProcess::CreateWatchDogT"...
0x18002c889  mov     edx, 26h ; '&'
0x18002c88e  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18002c895  call    WPP_SF_s
0x18002c89a  mov     eax, cs:dword_1800411A8
0x18002c8a0  cmp     eax, 5
0x18002c8a3  jbe     short loc_18002C8DC
0x18002c8a5  mov     edx, 4000000h
0x18002c8aa  lea     rcx, dword_1800411A8
0x18002c8b1  call    _tlgKeywordOn
0x18002c8b6  test    al, al
0x18002c8b8  jz      short loc_18002C8DC
0x18002c8ba  lea     rax, aThreadCreation; "Thread creation failed."
0x18002c8c1  mov     [rsp+58h+arg_0], rax
0x18002c8c6  lea     rdx, dword_18003B0CC
0x18002c8cd  lea     rax, [rsp+58h+arg_0]
0x18002c8d2  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x18002c8d7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18002c8dc  mov     rcx, rsi
0x18002c8df  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x18002c8e4  add     rsp, 40h
0x18002c8e8  pop     rdi
0x18002c8e9  pop     rsi
0x18002c8ea  pop     rbx
0x18002c8eb  retn
```

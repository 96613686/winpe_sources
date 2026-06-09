# BthServRadioInterfaceWatcher::Start(void)

- ea: `0x1800131d0`
- end: `0x1800133b8`
- name: `?Start@BthServRadioInterfaceWatcher@@QEAAXXZ`
- size: `488`
- prototype: `void __fastcall(BthServRadioInterfaceWatcher *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800100c0`

## callees

- `0x180001cf0`
- `0x180001d58`
- `0x180004e60`
- `0x180010cac`
- `0x1800131d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001329b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001329b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013224`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013224`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180013291`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180013291`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180013267`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180013267`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18001321c`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18001321c`

## string_xrefs

- `0x1800133a3`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\radios.cpp`

## pseudocode

```c
void __fastcall BthServRadioInterfaceWatcher::Start(BthServRadioInterfaceWatcher *this)
{
  __int64 v2; // rsi
  DWORD LastError; // ebx
  int ObjectQuery; // eax
  unsigned int v5; // r8d
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  int CompareAddress; // [rsp+60h] [rbp+8h] BYREF

  if ( dword_180044E18 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180044E18);
    if ( dword_180044E18 == -1 )
    {
      *(DEVPROPKEY *)byte_180044388 = DEVPKEY_DeviceInterface_ClassGuid;
      qword_1800443B0 = (__int64)&GUID_BTHPORT_DEVICE_INTERFACE;
      *(DEVPROPKEY *)byte_1800443C0 = DEVPKEY_DeviceInterface_Enabled;
      qword_1800443E8 = (__int64)byte_18003BBB1;
      dword_18004439C = 0;
      qword_1800443A0 = 0;
      dword_1800443A8 = 13;
      dword_1800443AC = 16;
      dword_1800443B8 = 2;
      dword_1800443D4 = 0;
      qword_1800443D8 = 0;
      dword_1800443E0 = 17;
      dword_1800443E4 = 1;
      Init_thread_footer(&dword_180044E18);
    }
  }
  v2 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    DevCloseObjectQuery(v2);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  ObjectQuery = DevCreateObjectQuery(1, 1, 0);
  if ( ObjectQuery < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\radios.cpp",
      (const char *)(unsigned int)ObjectQuery,
      2);
  while ( !*((_DWORD *)this + 2) )
  {
    CompareAddress = 0;
    if ( !WaitOnAddress((char *)this + 8, &CompareAddress, 4u, 0xFFFFFFFF) )
    {
      if ( GetLastError() != 1460 )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xDBF, v5, v6);
      return;
    }
  }
}

```

## disassembly

```asm
0x1800131d0  mov     [rsp+arg_8], rbx
0x1800131d5  mov     [rsp+arg_10], rsi
0x1800131da  push    rdi
0x1800131db  sub     rsp, 50h
0x1800131df  mov     edx, cs:_tls_index
0x1800131e5  mov     rdi, rcx
0x1800131e8  mov     rax, gs:58h
0x1800131f1  mov     ecx, 4
0x1800131f6  mov     rax, [rax+rdx*8]
0x1800131fa  mov     eax, [rcx+rax]
0x1800131fd  cmp     cs:dword_180044E18, eax
0x180013203  jg      loc_1800132C8
0x180013209  mov     rsi, [rdi]
0x18001320c  test    rsi, rsi
0x18001320f  jz      short loc_18001322A
0x180013211  call    cs:__imp_GetLastError
0x180013217  mov     rcx, rsi
0x18001321a  mov     ebx, eax
0x18001321c  call    cs:__imp_DevCloseObjectQuery
0x180013222  mov     ecx, ebx; dwErrCode
0x180013224  call    cs:__imp_SetLastError
0x18001322a  mov     [rsp+58h+var_18], rdi
0x18001322f  lea     rax, ?DevQueryResultCallbackThunk@BthServRadioInterfaceWatcher@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; BthServRadioInterfaceWatcher::DevQueryResultCallbackThunk(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180013236  mov     [rsp+58h+var_20], rdi
0x18001323b  xor     r9d, r9d
0x18001323e  mov     [rsp+58h+var_28], rax
0x180013243  xor     r8d, r8d
0x180013246  lea     rax, qword_180044380
0x18001324d  mov     qword ptr [rdi], 0
0x180013254  mov     [rsp+58h+var_30], rax
0x180013259  lea     edx, [r9+1]
0x18001325d  mov     [rsp+58h+var_38], 2; int
0x180013265  mov     ecx, edx
0x180013267  call    cs:__imp_DevCreateObjectQuery
0x18001326d  test    eax, eax
0x18001326f  js      loc_18001339E
0x180013275  mov     eax, [rdi+8]
0x180013278  test    eax, eax
0x18001327a  jnz     short loc_1800132A8
0x18001327c  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180013280  mov     [rsp+58h+CompareAddress], eax
0x180013284  lea     r8d, [rax+4]; AddressSize
0x180013288  lea     rdx, [rsp+58h+CompareAddress]; CompareAddress
0x18001328d  lea     rcx, [rdi+8]; Address
0x180013291  call    cs:__imp_WaitOnAddress
0x180013297  test    eax, eax
0x180013299  jnz     short loc_180013275
0x18001329b  call    cs:__imp_GetLastError
0x1800132a1  cmp     eax, 5B4h
0x1800132a6  jnz     short loc_1800132B8
0x1800132a8  mov     rbx, [rsp+58h+arg_8]
0x1800132ad  mov     rsi, [rsp+58h+arg_10]
0x1800132b2  add     rsp, 50h
0x1800132b6  pop     rdi
0x1800132b7  retn
0x1800132b8  mov     rcx, [rsp+58h]; this
0x1800132bd  mov     edx, 0DBFh; void *
0x1800132c2  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x1800132c8  lea     rcx, dword_180044E18
0x1800132cf  call    _Init_thread_header
0x1800132d4  cmp     cs:dword_180044E18, 0FFFFFFFFh
0x1800132db  jnz     loc_180013209
0x1800132e1  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x1800132e8  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x1800132ee  lea     rcx, dword_180044E18
0x1800132f5  mov     dword ptr cs:byte_180044388+10h, eax
0x1800132fb  lea     rax, GUID_BTHPORT_DEVICE_INTERFACE
0x180013302  mov     cs:qword_1800443B0, rax
0x180013309  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x18001330f  movups  xmmword ptr cs:byte_180044388, xmm0
0x180013316  mov     dword ptr cs:byte_1800443C0+10h, eax
0x18001331c  lea     rax, byte_18003BBB1
0x180013323  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x18001332a  mov     cs:qword_1800443E8, rax
0x180013331  mov     cs:dword_18004439C, 0
0x18001333b  movaps  xmmword ptr cs:byte_1800443C0, xmm0
0x180013342  mov     cs:qword_1800443A0, 0
0x18001334d  mov     cs:dword_1800443A8, 0Dh
0x180013357  mov     cs:dword_1800443AC, 10h
0x180013361  mov     cs:dword_1800443B8, 2
0x18001336b  mov     cs:dword_1800443D4, 0
0x180013375  mov     cs:qword_1800443D8, 0
0x180013380  mov     cs:dword_1800443E0, 11h
0x18001338a  mov     cs:dword_1800443E4, 1
0x180013394  call    _Init_thread_footer
0x180013399  jmp     loc_180013209
0x18001339e  mov     rcx, [rsp+58h]; this
0x1800133a3  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x1800133aa  mov     r9d, eax; char *
0x1800133ad  mov     edx, 53h ; 'S'; void *
0x1800133b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

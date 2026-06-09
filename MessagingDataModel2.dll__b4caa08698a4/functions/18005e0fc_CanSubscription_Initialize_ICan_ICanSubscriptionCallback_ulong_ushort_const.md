# CanSubscription::Initialize(ICan *,ICanSubscriptionCallback *,ulong,ushort const *)

- ea: `0x18005e0fc`
- end: `0x18005e354`
- name: `?Initialize@CanSubscription@@QEAAJPEAUICan@@PEAUICanSubscriptionCallback@@KPEBG@Z`
- size: `600`
- prototype: `int(CanSubscription *__hidden this, struct ICan *, struct ICanSubscriptionCallback *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180055204`

## callees

- `0x180001cc4`
- `0x1800065c8`
- `0x18000b7d4`
- `0x18002416c`
- `0x18005db10`
- `0x18005db54`
- `0x18005e0fc`
- `0x18005e35c`
- `0x18005e38c`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18005e22c`
- `msvcrt!wcscpy_s` at `0x18005e22c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e192`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005e192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e1a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e1a9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005e216`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18005e216`

## pseudocode

```c
__int64 __fastcall CanSubscription::Initialize(
        CanSubscription *this,
        struct IUnknown *a2,
        struct IUnknown *a3,
        int a4,
        const unsigned __int16 *a5)
{
  bool v5; // zf
  unsigned int v9; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  struct IUnknownVtbl *lpVtbl; // r8
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v21; // [rsp+30h] [rbp-81h] BYREF
  _QWORD v22[2]; // [rsp+38h] [rbp-79h] BYREF
  __int64 v23; // [rsp+48h] [rbp-69h]
  CanSubscription *v24; // [rsp+50h] [rbp-61h] BYREF
  __int64 v25; // [rsp+58h] [rbp-59h]
  char *v26; // [rsp+60h] [rbp-51h] BYREF
  struct IUnknown *v27; // [rsp+68h] [rbp-49h] BYREF
  GUID rguid; // [rsp+70h] [rbp-41h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-31h] BYREF

  v5 = *((_DWORD *)this + 26) == 0;
  v27 = a2;
  if ( !v5 )
  {
    Log_AssertionEvent_30(this, a2, 27);
    if ( *((_DWORD *)this + 26) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  *((_DWORD *)this + 27) = a4;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 112,
                           a5) )
  {
    v9 = -2147024882;
LABEL_6:
    Log_HREvent_34(v9);
    return v9;
  }
  EventW = CreateEventW(0, 1, 1, 0);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::reset((char *)this + 272, EventW);
  if ( !*((_QWORD *)this + 34) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_6;
  }
  if ( *((struct IUnknown **)this + 9) != v27 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 9, v27);
  v12 = *((_QWORD *)this + 9);
  rguid = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v12 + 24LL))(v12, &rguid);
  if ( v13 < 0 )
    Log_HREvent_34(v13);
  StringFromGUID2(&rguid, sz, 39);
  wcscpy_s((wchar_t *)this + 72, 0x27u, sz);
  if ( *((struct IUnknown **)this + 12) != a3 )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 12, a3);
  v25 = 1;
  v24 = this;
  v14 = ((__int64 (__fastcall *)(struct IUnknown *, CanSubscription *))v27->lpVtbl[11].QueryInterface)(v27, this);
  v9 = v14;
  if ( v14 >= 0 )
  {
    v23 = 0;
    v22[0] = 0;
    v22[1] = this;
    lpVtbl = v27->lpVtbl;
    v22[0] = &v27;
    LOBYTE(v23) = 1;
    v16 = ((__int64 (__fastcall *)(struct IUnknown *, unsigned __int64))lpVtbl[2].AddRef)(
            v27,
            ((unsigned __int64)this + 8) & -(__int64)(this != 0));
    v9 = v16;
    if ( v16 >= 0 )
    {
      LOBYTE(v23) = 0;
      LOBYTE(v25) = 0;
      if ( (unsigned int)dword_1800FD5F0 > 4 )
      {
        v21 = *((_DWORD *)this + 27);
        v26 = (char *)this + 144;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v17,
          (unsigned int)&unk_1800EC4C0,
          v18,
          v19,
          (__int64)&v26,
          (__int64)&v21);
      }
      tlx::_UndoSolo__lambda_69cac4c46f708cf3000b75bb72d4622b___::__UndoSolo__lambda_69cac4c46f708cf3000b75bb72d4622b___(v22);
      v9 = 0;
    }
    else
    {
      Log_HREvent_34(v16);
      tlx::_UndoSolo__lambda_69cac4c46f708cf3000b75bb72d4622b___::__UndoSolo__lambda_69cac4c46f708cf3000b75bb72d4622b___(v22);
    }
  }
  else
  {
    Log_HREvent_34(v14);
  }
  tlx::_UndoSolo__lambda_cca97f39a3160f8fbe91efb2f5e073ed___::__UndoSolo__lambda_cca97f39a3160f8fbe91efb2f5e073ed___(&v24);
  return v9;
}

```

## disassembly

```asm
0x18005e0fc  mov     [rsp-8+arg_18], rbx
0x18005e101  push    rbp
0x18005e102  push    rsi
0x18005e103  push    rdi
0x18005e104  push    r14
0x18005e106  push    r15
0x18005e108  lea     rbp, [rsp-2Fh]
0x18005e10d  sub     rsp, 0E0h
0x18005e114  mov     rax, cs:__security_cookie
0x18005e11b  xor     rax, rsp
0x18005e11e  mov     [rbp+4Fh+var_30], rax
0x18005e122  cmp     dword ptr [rcx+68h], 0
0x18005e126  mov     ebx, r9d
0x18005e129  mov     rsi, [rbp+4Fh+arg_20]
0x18005e12d  mov     r15, r8
0x18005e130  mov     rdi, rcx
0x18005e133  mov     [rbp+4Fh+var_98], rdx
0x18005e137  jz      short loc_18005E14F
0x18005e139  mov     r8d, 1Bh
0x18005e13f  call    Log_AssertionEvent_30
0x18005e144  cmp     dword ptr [rdi+68h], 0
0x18005e148  jz      short loc_18005E14F
0x18005e14a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005e14f  lea     r14, [rdi+6Ch]
0x18005e153  mov     rdx, rsi
0x18005e156  lea     rcx, [rdi+70h]
0x18005e15a  mov     [r14], ebx
0x18005e15d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18005e162  test    al, al
0x18005e164  jnz     short loc_18005E17F
0x18005e166  mov     ebx, 8007000Eh
0x18005e16b  mov     r9d, 1Eh
0x18005e171  xor     edx, edx
0x18005e173  mov     ecx, ebx; int
0x18005e175  call    Log_HREvent_34
0x18005e17a  jmp     loc_18005E32F
0x18005e17f  xor     r9d, r9d; lpName
0x18005e182  lea     rbx, [rdi+110h]
0x18005e189  xor     ecx, ecx; lpEventAttributes
0x18005e18b  lea     edx, [r9+1]; bManualReset
0x18005e18f  mov     r8d, edx; bInitialState
0x18005e192  call    cs:__imp_CreateEventW
0x18005e198  mov     rdx, rax
0x18005e19b  mov     rcx, rbx
0x18005e19e  call    ?reset@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@QEAAXPEAX@Z; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::reset(void *)
0x18005e1a3  cmp     qword ptr [rbx], 0
0x18005e1a7  jnz     short loc_18005E1C6
0x18005e1a9  call    cs:__imp_GetLastError
0x18005e1af  mov     ebx, eax
0x18005e1b1  test    eax, eax
0x18005e1b3  jle     short loc_18005E1BE
0x18005e1b5  movzx   ebx, ax
0x18005e1b8  or      ebx, 80070000h
0x18005e1be  mov     r9d, 22h ; '"'
0x18005e1c4  jmp     short loc_18005E171
0x18005e1c6  mov     rdx, [rbp+4Fh+var_98]; struct IUnknown *
0x18005e1ca  lea     rbx, [rdi+48h]
0x18005e1ce  cmp     [rbx], rdx
0x18005e1d1  jz      short loc_18005E1DB
0x18005e1d3  mov     rcx, rbx; struct IUnknown **
0x18005e1d6  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18005e1db  mov     rcx, [rbx]
0x18005e1de  lea     rdx, [rbp+4Fh+rguid]
0x18005e1e2  xorps   xmm0, xmm0
0x18005e1e5  movups  xmmword ptr [rbp+4Fh+rguid.Data1], xmm0
0x18005e1e9  mov     rax, [rcx]
0x18005e1ec  mov     rax, [rax+18h]
0x18005e1f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e1f5  test    eax, eax
0x18005e1f7  jns     short loc_18005E206
0x18005e1f9  xor     edx, edx
0x18005e1fb  mov     ecx, eax; int
0x18005e1fd  lea     r9d, [rdx+28h]
0x18005e201  call    Log_HREvent_34
0x18005e206  mov     ebx, 27h ; '''
0x18005e20b  lea     rdx, [rbp+4Fh+sz]; lpsz
0x18005e20f  mov     r8d, ebx; cchMax
0x18005e212  lea     rcx, [rbp+4Fh+rguid]; rguid
0x18005e216  call    cs:__imp_StringFromGUID2
0x18005e21c  lea     rsi, [rdi+90h]
0x18005e223  mov     edx, ebx; SizeInWords
0x18005e225  mov     rcx, rsi; Destination
0x18005e228  lea     r8, [rbp+4Fh+sz]; Source
0x18005e22c  call    cs:__imp_wcscpy_s
0x18005e232  lea     rcx, [rdi+60h]; struct IUnknown **
0x18005e236  cmp     [rcx], r15
0x18005e239  jz      short loc_18005E243
0x18005e23b  mov     rdx, r15; struct IUnknown *
0x18005e23e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18005e243  mov     rcx, [rbp+4Fh+var_98]
0x18005e247  xorps   xmm0, xmm0
0x18005e24a  movups  [rbp+4Fh+var_B0], xmm0
0x18005e24e  mov     rdx, rdi
0x18005e251  mov     qword ptr [rbp+4Fh+var_B0], rdi
0x18005e255  mov     byte ptr [rbp+4Fh+var_B0+8], 1
0x18005e259  mov     rax, [rcx]
0x18005e25c  mov     rax, [rax+108h]
0x18005e263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e268  mov     ebx, eax
0x18005e26a  test    eax, eax
0x18005e26c  jns     short loc_18005E283
0x18005e26e  mov     edx, 1
0x18005e273  mov     ecx, eax; int
0x18005e275  lea     r9d, [rdx+33h]
0x18005e279  call    Log_HREvent_34
0x18005e27e  jmp     loc_18005E326
0x18005e283  mov     rcx, [rbp+4Fh+var_98]
0x18005e287  xor     eax, eax
0x18005e289  mov     [rbp+4Fh+var_B8], rax
0x18005e28d  xorps   xmm0, xmm0
0x18005e290  movups  [rbp+4Fh+var_C8], xmm0
0x18005e294  lea     rax, [rbp+4Fh+var_98]
0x18005e298  mov     qword ptr [rbp+4Fh+var_C8+8], rdi
0x18005e29c  mov     r8, [rcx]
0x18005e29f  mov     qword ptr [rbp+4Fh+var_C8], rax
0x18005e2a3  lea     rax, [rdi+8]
0x18005e2a7  neg     rdi
0x18005e2aa  mov     byte ptr [rbp+4Fh+var_B8], 1
0x18005e2ae  sbb     rdx, rdx
0x18005e2b1  and     rdx, rax
0x18005e2b4  mov     rax, [r8+38h]
0x18005e2b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e2bd  mov     ebx, eax
0x18005e2bf  test    eax, eax
0x18005e2c1  jns     short loc_18005E2DE
0x18005e2c3  mov     edx, 1
0x18005e2c8  mov     ecx, eax; int
0x18005e2ca  lea     r9d, [rdx+39h]
0x18005e2ce  call    Log_HREvent_34
0x18005e2d3  lea     rcx, [rbp+4Fh+var_C8]
0x18005e2d7  call    tlx___UndoSolo__lambda_69cac4c46f708cf3000b75bb72d4622b_______UndoSolo__lambda_69cac4c46f708cf3000b75bb72d4622b___
0x18005e2dc  jmp     short loc_18005E326
0x18005e2de  mov     eax, cs:dword_1800FD5F0
0x18005e2e4  mov     byte ptr [rbp+4Fh+var_B8], 0
0x18005e2e8  mov     byte ptr [rbp+4Fh+var_B0+8], 0
0x18005e2ec  cmp     eax, 4
0x18005e2ef  jbe     short loc_18005E31B
0x18005e2f1  mov     eax, [r14]
0x18005e2f4  lea     rdx, unk_1800EC4C0
0x18005e2fb  mov     [rsp+100h+var_D0], eax
0x18005e2ff  lea     rax, [rsp+100h+var_D0]
0x18005e304  mov     [rsp+100h+var_D8], rax
0x18005e309  lea     rax, [rbp+4Fh+var_A0]
0x18005e30d  mov     [rsp+100h+var_E0], rax
0x18005e312  mov     [rbp+4Fh+var_A0], rsi
0x18005e316  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18005e31b  lea     rcx, [rbp+4Fh+var_C8]
0x18005e31f  call    tlx___UndoSolo__lambda_69cac4c46f708cf3000b75bb72d4622b_______UndoSolo__lambda_69cac4c46f708cf3000b75bb72d4622b___
0x18005e324  xor     ebx, ebx
0x18005e326  lea     rcx, [rbp+4Fh+var_B0]
0x18005e32a  call    tlx___UndoSolo__lambda_cca97f39a3160f8fbe91efb2f5e073ed_______UndoSolo__lambda_cca97f39a3160f8fbe91efb2f5e073ed___
0x18005e32f  mov     eax, ebx
0x18005e331  mov     rcx, [rbp+4Fh+var_30]
0x18005e335  xor     rcx, rsp; StackCookie
0x18005e338  call    __security_check_cookie
0x18005e33d  mov     rbx, [rsp+100h+arg_18]
0x18005e345  add     rsp, 0E0h
0x18005e34c  pop     r15
0x18005e34e  pop     r14
0x18005e350  pop     rdi
0x18005e351  pop     rsi
0x18005e352  pop     rbp
0x18005e353  retn
```

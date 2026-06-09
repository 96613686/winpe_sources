# DllMain

- ea: `0x18000b0a0`
- end: `0x18000b34a`
- name: `DllMain`
- size: `682`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180001754`

## callees

- `0x18000108c`
- `0x1800018e0`
- `0x180008c60`
- `0x1800090d4`
- `0x180009978`
- `0x180009cac`
- `0x18000b0a0`
- `0x180027010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000b181`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000b181`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000b325`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000b325`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b1e5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000b1e5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000b1a0`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000b1a0`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b0e4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b0f3`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b0e4`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b0f3`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  int v3; // ebx
  __int64 i; // rdi
  __int64 (*v5)(void); // rax
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  const GUID *v10; // r9
  REGHANDLE v11; // rcx
  GUID ProviderId; // [rsp+30h] [rbp-38h] BYREF

  v3 = 0;
  if ( !fdwReason )
  {
    CGlobalInitializer<1>::Done(hinstDLL, fdwReason, lpvReserved);
    g_activity = 2;
    if ( (unsigned int)dword_18002F170 > 5
      && (qword_18002F180 & 0x400000000000LL) != 0
      && (qword_18002F188 & 0x400000000000LL) == qword_18002F188 )
    {
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)&dword_18002F170,
        (unsigned __int8 *)byte_18002C315,
        &ActivityId,
        0,
        2u,
        (PEVENT_DATA_DESCRIPTOR)&ProviderId);
    }
    v11 = RegHandle;
    dword_18002F170 = 0;
    RegHandle = 0;
    EventUnregister(v11);
    return v3 >= 0;
  }
  if ( fdwReason != 1 )
    return v3 >= 0;
  COverriddenOperatorsSafeGuardT<CEmptyType>::OperatorsSafeGuardFunc(hinstDLL, fdwReason, lpvReserved);
  for ( i = CGlobalList<CGlobalInitializer<1>>::g_pFirst; ; i = *(_QWORD *)i )
  {
    if ( !i )
    {
      v3 = 0;
      goto LABEL_11;
    }
    if ( !*(_DWORD *)(i + 24) )
      break;
LABEL_8:
    ;
  }
  if ( !DecodePointer(*(PVOID *)(i + 8))
    || (v5 = (__int64 (*)(void))DecodePointer(*(PVOID *)(i + 8)), v6 = v5(), v3 = v6, v6 >= 0) )
  {
    *(_DWORD *)(i + 24) = 1;
    goto LABEL_8;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
  CGlobalInitializer<1>::Done(v8, v7, v9);
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v3 >= 0 )
  {
    ProviderId = (GUID)*((_OWORD *)off_18002F178 - 1);
    if ( RegHandle )
      __fastfail(5u);
    xmmword_18002F198 = 0;
    if ( !EventRegister(&ProviderId, (PENABLECALLBACK)tlgEnableCallback, &dword_18002F170, &RegHandle) )
      EventSetInformation(RegHandle, 2, off_18002F178, *(unsigned __int16 *)off_18002F178);
    if ( (unsigned int)dword_18002F170 > 5
      && (qword_18002F180 & 0x400000000000LL) != 0
      && (qword_18002F188 & 0x400000000000LL) == qword_18002F188 )
    {
      EventActivityIdControl(3u, &ActivityId);
    }
    else
    {
      ActivityId = 0;
    }
    g_activity = 1;
    if ( (unsigned int)dword_18002F170 > 5
      && (qword_18002F180 & 0x400000000000LL) != 0
      && (qword_18002F188 & 0x400000000000LL) == qword_18002F188 )
    {
      if ( byte_18002F8C4 && (dword_18002F8D8 || dword_18002F8DC || dword_18002F8E0 || dword_18002F8E4) )
        v10 = (const GUID *)&dword_18002F8D8;
      else
        v10 = 0;
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)&dword_18002F170,
        (unsigned __int8 *)&unk_18002C338,
        &ActivityId,
        v10,
        2u,
        (PEVENT_DATA_DESCRIPTOR)&ProviderId);
    }
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
  }
  return v3 >= 0;
}

```

## disassembly

```asm
0x18000b0a0  mov     [rsp+arg_0], rbx
0x18000b0a5  push    rdi
0x18000b0a6  sub     rsp, 60h
0x18000b0aa  mov     rax, cs:__security_cookie
0x18000b0b1  xor     rax, rsp
0x18000b0b4  mov     [rsp+68h+var_18], rax
0x18000b0b9  xor     ebx, ebx
0x18000b0bb  test    edx, edx
0x18000b0bd  jz      loc_18000B2A0
0x18000b0c3  cmp     edx, 1
0x18000b0c6  jnz     loc_18000B32B
0x18000b0cc  call    ?OperatorsSafeGuardFunc@?$COverriddenOperatorsSafeGuardT@VCEmptyType@@@@SAJXZ; COverriddenOperatorsSafeGuardT<CEmptyType>::OperatorsSafeGuardFunc(void)
0x18000b0d1  mov     rdi, cs:?g_pFirst@?$CGlobalList@V?$CGlobalInitializer@$00@@@@2PEAV?$CGlobalInitializer@$00@@EA; CGlobalInitializer<1> * CGlobalList<CGlobalInitializer<1>>::g_pFirst
0x18000b0d8  jmp     short loc_18000B10E
0x18000b0da  cmp     dword ptr [rdi+18h], 0
0x18000b0de  jnz     short loc_18000B10B
0x18000b0e0  mov     rcx, [rdi+8]; Ptr
0x18000b0e4  call    cs:__imp_DecodePointer
0x18000b0ea  test    rax, rax
0x18000b0ed  jz      short loc_18000B104
0x18000b0ef  mov     rcx, [rdi+8]; Ptr
0x18000b0f3  call    cs:__imp_DecodePointer
0x18000b0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0fe  mov     ebx, eax
0x18000b100  test    eax, eax
0x18000b102  js      short loc_18000B12C
0x18000b104  mov     dword ptr [rdi+18h], 1
0x18000b10b  mov     rdi, [rdi]
0x18000b10e  test    rdi, rdi
0x18000b111  jnz     short loc_18000B0DA
0x18000b113  xor     ebx, ebx
0x18000b115  mov     ecx, ebx
0x18000b117  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b11c  test    ebx, ebx
0x18000b11e  jns     short loc_18000B13A
0x18000b120  mov     ecx, ebx
0x18000b122  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b127  jmp     loc_18000B32B
0x18000b12c  mov     ecx, eax
0x18000b12e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b133  call    ?Done@?$CGlobalInitializer@$00@@SAJXZ; CGlobalInitializer<1>::Done(void)
0x18000b138  jmp     short loc_18000B115
0x18000b13a  cmp     cs:RegHandle, 0
0x18000b142  mov     rax, cs:off_18002F178
0x18000b149  movups  xmm0, xmmword ptr [rax-10h]
0x18000b14d  movdqu  xmmword ptr [rsp+68h+ProviderId.Data1], xmm0
0x18000b153  jz      short loc_18000B15C
0x18000b155  mov     ecx, 5
0x18000b15a  int     29h; Win8: RtlFailFast(ecx)
0x18000b15c  xorps   xmm0, xmm0
0x18000b15f  lea     r9, RegHandle; RegHandle
0x18000b166  lea     r8, dword_18002F170; CallbackContext
0x18000b16d  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000b174  lea     rcx, [rsp+68h+ProviderId]; ProviderId
0x18000b179  movdqu  cs:xmmword_18002F198, xmm0
0x18000b181  call    cs:__imp_EventRegister
0x18000b187  test    eax, eax
0x18000b189  jnz     short loc_18000B1A6
0x18000b18b  mov     r8, cs:off_18002F178
0x18000b192  lea     edx, [rax+2]
0x18000b195  mov     rcx, cs:RegHandle
0x18000b19c  movzx   r9d, word ptr [r8]
0x18000b1a0  call    cs:__imp_EventSetInformation
0x18000b1a6  mov     eax, cs:dword_18002F170
0x18000b1ac  mov     rdi, 400000000000h
0x18000b1b6  cmp     eax, 5
0x18000b1b9  jbe     short loc_18000B1ED
0x18000b1bb  mov     rcx, cs:qword_18002F188
0x18000b1c2  mov     rax, cs:qword_18002F180
0x18000b1c9  test    rdi, rax
0x18000b1cc  jz      short loc_18000B1ED
0x18000b1ce  mov     rax, rcx
0x18000b1d1  and     rax, rdi
0x18000b1d4  cmp     rax, rcx
0x18000b1d7  jnz     short loc_18000B1ED
0x18000b1d9  lea     rdx, ActivityId; ActivityId
0x18000b1e0  mov     ecx, 3; ControlCode
0x18000b1e5  call    cs:__imp_EventActivityIdControl
0x18000b1eb  jmp     short loc_18000B1F7
0x18000b1ed  xorps   xmm0, xmm0
0x18000b1f0  movups  xmmword ptr cs:ActivityId.Data1, xmm0
0x18000b1f7  mov     eax, cs:dword_18002F170
0x18000b1fd  mov     cs:?g_activity@@3V?$TraceLoggingActivity@$1?g_ChangePKTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@A, 1; TraceLoggingActivity<&_tlgProvider_t const * const g_ChangePKTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> g_activity
0x18000b207  cmp     eax, 5
0x18000b20a  jbe     loc_18000B32B
0x18000b210  mov     rcx, cs:qword_18002F188
0x18000b217  mov     rax, cs:qword_18002F180
0x18000b21e  test    rdi, rax
0x18000b221  jz      loc_18000B32B
0x18000b227  mov     rax, rcx
0x18000b22a  and     rax, rdi
0x18000b22d  cmp     rax, rcx
0x18000b230  jnz     loc_18000B32B
0x18000b236  cmp     cs:byte_18002F8C4, 0
0x18000b23d  jz      short loc_18000B26C
0x18000b23f  cmp     cs:dword_18002F8D8, 0
0x18000b246  jnz     short loc_18000B263
0x18000b248  cmp     cs:dword_18002F8DC, 0
0x18000b24f  jnz     short loc_18000B263
0x18000b251  cmp     cs:dword_18002F8E0, 0
0x18000b258  jnz     short loc_18000B263
0x18000b25a  cmp     cs:dword_18002F8E4, 0
0x18000b261  jz      short loc_18000B26C
0x18000b263  lea     r9, dword_18002F8D8
0x18000b26a  jmp     short loc_18000B26F
0x18000b26c  xor     r9d, r9d
0x18000b26f  lea     rax, [rsp+68h+ProviderId]
0x18000b274  mov     [rsp+68h+var_40], rax
0x18000b279  lea     r8, ActivityId
0x18000b280  lea     rdx, unk_18002C338
0x18000b287  mov     [rsp+68h+var_48], 2
0x18000b28f  lea     rcx, dword_18002F170
0x18000b296  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b29b  jmp     loc_18000B32B
0x18000b2a0  call    ?Done@?$CGlobalInitializer@$00@@SAJXZ; CGlobalInitializer<1>::Done(void)
0x18000b2a5  mov     eax, cs:dword_18002F170
0x18000b2ab  mov     cs:?g_activity@@3V?$TraceLoggingActivity@$1?g_ChangePKTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@A, 2; TraceLoggingActivity<&_tlgProvider_t const * const g_ChangePKTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> g_activity
0x18000b2b5  cmp     eax, 5
0x18000b2b8  jbe     short loc_18000B311
0x18000b2ba  mov     rcx, cs:qword_18002F188
0x18000b2c1  mov     rdi, 400000000000h
0x18000b2cb  mov     rax, cs:qword_18002F180
0x18000b2d2  test    rdi, rax
0x18000b2d5  jz      short loc_18000B311
0x18000b2d7  mov     rax, rcx
0x18000b2da  and     rax, rdi
0x18000b2dd  cmp     rax, rcx
0x18000b2e0  jnz     short loc_18000B311
0x18000b2e2  lea     rax, [rsp+68h+ProviderId]
0x18000b2e7  xor     r9d, r9d
0x18000b2ea  mov     [rsp+68h+var_40], rax
0x18000b2ef  lea     r8, ActivityId
0x18000b2f6  lea     rdx, byte_18002C315
0x18000b2fd  mov     [rsp+68h+var_48], 2
0x18000b305  lea     rcx, dword_18002F170
0x18000b30c  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b311  mov     rcx, cs:RegHandle; RegHandle
0x18000b318  mov     cs:dword_18002F170, ebx
0x18000b31e  mov     cs:RegHandle, rbx
0x18000b325  call    cs:__imp_EventUnregister
0x18000b32b  not     ebx
0x18000b32d  shr     ebx, 1Fh
0x18000b330  mov     eax, ebx
0x18000b332  mov     rcx, [rsp+68h+var_18]
0x18000b337  xor     rcx, rsp; StackCookie
0x18000b33a  call    __security_check_cookie
0x18000b33f  mov     rbx, [rsp+68h+arg_0]
0x18000b344  add     rsp, 60h
0x18000b348  pop     rdi
0x18000b349  retn
```

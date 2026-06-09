# CreateTimerWaitFlowEstablish

- ea: `0x140003dac`
- end: `0x140003f11`
- name: `CreateTimerWaitFlowEstablish`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400037a4`
- `0x140007280`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x140003dac`
- `0x14000a680`
- `0x14000a6c0`

## string_xrefs

- `0x140003e7e`: `Failed to create timer`

## pseudocode

```c
__int64 __fastcall CreateTimerWaitFlowEstablish(__int64 a1)
{
  int v2; // eax
  int v3; // r8d
  int v4; // r9d
  unsigned int v5; // ebx
  int v7; // [rsp+30h] [rbp-79h] BYREF
  const char *v8; // [rsp+38h] [rbp-71h] BYREF
  __int128 v9; // [rsp+40h] [rbp-69h] BYREF
  __int128 v10; // [rsp+50h] [rbp-59h]
  __int128 v11; // [rsp+60h] [rbp-49h]
  __int64 v12; // [rsp+70h] [rbp-39h]
  _QWORD v13[2]; // [rsp+78h] [rbp-31h] BYREF
  __int128 v14; // [rsp+88h] [rbp-21h]
  __int64 v15; // [rsp+98h] [rbp-11h]
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+A0h] [rbp-9h] BYREF
  const char **v17; // [rsp+C0h] [rbp+17h]
  __int64 v18; // [rsp+C8h] [rbp+1Fh]

  v15 = 0;
  v14 = 0;
  DWORD2(v14) = 0;
  v13[1] = EvtWdfTimerWaitFlowEstablish;
  v12 = 0;
  v10 = 0;
  v13[0] = 40;
  v9 = 0;
  v11 = *((unsigned __int64 *)RoutePolicyCallout::g_pCalloutContext + 3);
  LODWORD(v14) = 0;
  BYTE4(v14) = 1;
  LODWORD(v9) = 56;
  *((_QWORD *)&v10 + 1) = 0x100000001LL;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD *, __int128 *, __int64))(WdfFunctions_01015 + 2544))(
         WdfDriverGlobals,
         v13,
         &v9,
         a1 + 120);
  v5 = v2;
  if ( v2 >= 0 )
  {
    *(_BYTE *)(a1 + 128) = 1;
    if ( (unsigned int)dword_140012050 > 4 )
    {
      v8 = *(const char **)(a1 + 120);
      v18 = 8;
      v17 = &v8;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&byte_14000FF1B, 0, 0, 3u, &v16);
    }
  }
  else if ( (unsigned int)dword_140012050 > 2 )
  {
    v7 = v2;
    v8 = "Failed to create timer";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_140012050,
      (unsigned int)word_14000EB7A,
      v3,
      v4,
      (__int64)&v8,
      (__int64)&v7);
  }
  return v5;
}

```

## disassembly

```asm
0x140003dac  push    rbp
0x140003dae  push    rbx
0x140003daf  push    rsi
0x140003db0  push    rdi
0x140003db1  lea     rbp, [rsp-3Fh]
0x140003db6  sub     rsp, 0E8h
0x140003dbd  mov     rax, cs:__security_cookie
0x140003dc4  xor     rax, rsp
0x140003dc7  mov     [rbp+57h+var_30], rax
0x140003dcb  xor     eax, eax
0x140003dcd  lea     r8, [rbp+57h+var_C0]
0x140003dd1  mov     [rbp+57h+var_68], rax
0x140003dd5  lea     rdx, [rbp+57h+var_88]
0x140003dd9  xorps   xmm0, xmm0
0x140003ddc  lea     rax, EvtWdfTimerWaitFlowEstablish
0x140003de3  movups  [rbp+57h+var_78], xmm0
0x140003de7  mov     rdi, rcx
0x140003dea  mov     dword ptr [rbp+57h+var_78+8], 0
0x140003df1  movups  [rbp+57h+var_88], xmm0
0x140003df5  mov     qword ptr [rbp+57h+var_88+8], rax
0x140003df9  xor     eax, eax
0x140003dfb  mov     [rbp+57h+var_90], rax
0x140003dff  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140003e06  lea     r9, [rdi+78h]
0x140003e0a  movups  [rbp+57h+var_B0], xmm0
0x140003e0e  mov     dword ptr [rbp+57h+var_88], 28h ; '('
0x140003e15  movups  [rbp+57h+var_C0], xmm0
0x140003e19  mov     rcx, [rax+18h]
0x140003e1d  mov     rax, cs:WdfFunctions_01015
0x140003e24  movups  [rbp+57h+var_A0], xmm0
0x140003e28  mov     qword ptr [rbp+57h+var_A0], rcx
0x140003e2c  mov     rcx, cs:WdfDriverGlobals
0x140003e33  mov     dword ptr [rbp+57h+var_78], 0
0x140003e3a  mov     byte ptr [rbp+57h+var_78+4], 1
0x140003e3e  mov     dword ptr [rbp+57h+var_C0], 38h ; '8'
0x140003e45  mov     dword ptr [rbp+57h+var_B0+8], 1
0x140003e4c  mov     dword ptr [rbp+57h+var_B0+0Ch], 1
0x140003e53  mov     rax, [rax+9F0h]
0x140003e5a  call    _guard_dispatch_icall
0x140003e5f  mov     ebx, eax
0x140003e61  test    eax, eax
0x140003e63  jns     short loc_140003EA2
0x140003e65  mov     ecx, cs:dword_140012050
0x140003e6b  cmp     ecx, 2
0x140003e6e  jbe     loc_140003EF6
0x140003e74  mov     [rbp+57h+var_D0], eax
0x140003e77  lea     rdx, word_14000EB7A
0x140003e7e  lea     rax, aFailedToCreate; "Failed to create timer"
0x140003e85  mov     [rbp+57h+var_C8], rax
0x140003e89  lea     rax, [rbp+57h+var_D0]
0x140003e8d  mov     [rsp+100h+var_D8], rax
0x140003e92  lea     rax, [rbp+57h+var_C8]
0x140003e96  mov     qword ptr [rsp+100h+var_E0], rax
0x140003e9b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140003ea0  jmp     short loc_140003EF6
0x140003ea2  mov     byte ptr [rdi+80h], 1
0x140003ea9  mov     eax, cs:dword_140012050
0x140003eaf  cmp     eax, 4
0x140003eb2  jbe     short loc_140003EF6
0x140003eb4  mov     rax, [rdi+78h]
0x140003eb8  lea     rdx, byte_14000FF1B; int
0x140003ebf  mov     [rbp+57h+var_C8], rax
0x140003ec3  lea     rcx, dword_140012050; int
0x140003eca  lea     rax, [rbp+57h+var_C8]
0x140003ece  mov     [rbp+57h+var_38], 8
0x140003ed6  mov     [rbp+57h+var_40], rax
0x140003eda  xor     r9d, r9d; int
0x140003edd  lea     rax, [rbp+57h+var_60]
0x140003ee1  xor     r8d, r8d; int
0x140003ee4  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140003ee9  mov     [rsp+100h+var_E0], 3; ULONG
0x140003ef1  call    _tlgWriteTransfer_EtwWriteTransfer
0x140003ef6  mov     eax, ebx
0x140003ef8  mov     rcx, [rbp+57h+var_30]
0x140003efc  xor     rcx, rsp; StackCookie
0x140003eff  call    __security_check_cookie
0x140003f04  add     rsp, 0E8h
0x140003f0b  pop     rdi
0x140003f0c  pop     rsi
0x140003f0d  pop     rbx
0x140003f0e  pop     rbp
0x140003f0f  retn
```

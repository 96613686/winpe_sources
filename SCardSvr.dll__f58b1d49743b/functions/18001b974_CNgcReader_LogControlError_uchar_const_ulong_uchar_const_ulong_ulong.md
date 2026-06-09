# CNgcReader::LogControlError(uchar const *,ulong,uchar const *,ulong,ulong)

- ea: `0x18001b974`
- end: `0x18001bb76`
- name: `?LogControlError@CNgcReader@@IEAAXPEBEK0KK@Z`
- size: `514`
- prototype: `void __fastcall(CNgcReader *this, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014480`

## callees

- `0x1800022b0`
- `0x1800128a0`
- `0x18001b974`
- `0x18001bb7c`
- `0x18001bb98`
- `0x18002b6fc`
- `0x18002b764`
- `0x1800326d0`

## string_xrefs

- `0x18001b9ad`: `CNgcReader::LogControlError`
- `0x18001bac9`: `SET_PROTOCOL`

## pseudocode

```c
void __fastcall CNgcReader::LogControlError(
        CNgcReader *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  const unsigned __int16 *v15; // rbx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  const unsigned __int8 *v21; // rcx
  const unsigned __int16 *v22; // r9
  int CommandHeaderString; // [rsp+30h] [rbp-39h] BYREF
  int v24; // [rsp+34h] [rbp-35h] BYREF
  unsigned __int16 *v25; // [rsp+38h] [rbp-31h] BYREF
  _QWORD *v26; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v27[3]; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int16 **v28; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int16 *v29; // [rsp+68h] [rbp-1h] BYREF
  char v30; // [rsp+70h] [rbp+7h]
  char v31[32]; // [rsp+78h] [rbp+Fh] BYREF

  CommandHeaderString = 0;
  v24 = 0;
  strcpy(v31, "CNgcReader::LogControlError");
  v27[0] = v31;
  v27[1] = &v24;
  v27[2] = &CommandHeaderString;
  lambda_038bd138bd6a40c669c7e79edd05c446_::operator()(v27, a2);
  v24 = 1;
  v26 = v27;
  if ( a3 <= 0x310028 )
  {
    if ( a3 == 3211304 )
    {
      v15 = L"IS_PRESENT";
      goto LABEL_31;
    }
    v9 = a3 - 3211268;
    if ( !v9 )
    {
      v15 = L"POWER";
      goto LABEL_31;
    }
    v10 = v9 - 4;
    if ( !v10 )
    {
      v15 = L"GET_ATTRIBUTE";
      goto LABEL_31;
    }
    v11 = v10 - 4;
    if ( !v11 )
    {
      v15 = L"SET_ATTRIBUTE";
      goto LABEL_31;
    }
    v12 = v11 - 4;
    if ( !v12 )
    {
      v15 = L"CONFISCATE";
      goto LABEL_31;
    }
    v13 = v12 - 4;
    if ( !v13 )
    {
      v15 = L"TRANSMIT";
      goto LABEL_31;
    }
    v14 = v13 - 4;
    if ( !v14 )
    {
      v15 = L"EJECT";
      goto LABEL_31;
    }
    if ( v14 == 4 )
    {
      v15 = L"SWALLOW";
      goto LABEL_31;
    }
    goto LABEL_24;
  }
  v16 = a3 - 3211308;
  if ( v16 )
  {
    v17 = v16 - 4;
    if ( v17 )
    {
      v18 = v17 - 8;
      if ( v18 )
      {
        v19 = v18 - 4;
        if ( v19 )
        {
          v20 = v19 - 4;
          if ( v20 )
          {
            if ( v20 != 13536 )
            {
LABEL_24:
              v15 = L"* UNKNOWN *";
              goto LABEL_31;
            }
            v15 = L"GET_FEATURE_REQUEST";
          }
          else
          {
            v15 = L"GET_PERF_CNTR";
          }
        }
        else
        {
          v15 = L"GET_LAST_ERROR";
        }
      }
      else
      {
        v15 = L"GET_STATE";
      }
    }
    else
    {
      v15 = L"SET_PROTOCOL";
    }
  }
  else
  {
    v15 = L"IS_ABSENT";
  }
LABEL_31:
  v25 = 0;
  v28 = &v25;
  v29 = 0;
  v30 = 1;
  CommandHeaderString = GenerateCommandHeaderString(a4, a5, (const unsigned __int16 **)&v29);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short const *,void (*)(unsigned short const *),&void ConstStringHeapFree(unsigned short const *),wistd::integral_constant<unsigned __int64,0>,unsigned short const *,unsigned short const *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short const *,void (*)(unsigned short const *),&void ConstStringHeapFree(unsigned short const *),wistd::integral_constant<unsigned __int64,0>,unsigned short const *,unsigned short const *,0,std::nullptr_t>>>>(&v28);
  if ( !CommandHeaderString )
  {
    v22 = &Data;
    if ( *((_DWORD *)this + 7) )
      v22 = (const unsigned __int16 *)*((_QWORD *)this + 2);
    CalaisError(v21, 0x262u, a6, v22, v15, v25);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short const *,void (*)(unsigned short const *),&void ConstStringHeapFree(unsigned short const *),wistd::integral_constant<unsigned __int64,0>,unsigned short const *,unsigned short const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short const *,void (*)(unsigned short const *),&void ConstStringHeapFree(unsigned short const *),wistd::integral_constant<unsigned __int64,0>,unsigned short const *,unsigned short const *,0,std::nullptr_t>>(&v25);
  WppTraceUnwinder__lambda_038bd138bd6a40c669c7e79edd05c446____::_WppTraceUnwinder__lambda_038bd138bd6a40c669c7e79edd05c446____(&v26);
}

```

## disassembly

```asm
0x18001b974  mov     [rsp-8+arg_8], rbx
0x18001b979  push    rbp
0x18001b97a  push    rsi
0x18001b97b  push    rdi
0x18001b97c  lea     rbp, [rsp-37h]
0x18001b981  sub     rsp, 0A0h
0x18001b988  mov     rax, cs:__security_cookie
0x18001b98f  xor     rax, rsp
0x18001b992  mov     [rbp+47h+var_18], rax
0x18001b996  mov     rsi, r9
0x18001b999  mov     ebx, r8d
0x18001b99c  mov     rdi, rcx
0x18001b99f  mov     [rbp+47h+var_80], 0
0x18001b9a6  mov     [rbp+47h+var_7C], 0
0x18001b9ad  movups  xmm0, xmmword ptr cs:aCngcreaderLogc; "CNgcReader::LogControlError"
0x18001b9b4  movups  xmmword ptr [rbp+47h+var_38], xmm0
0x18001b9b8  movups  xmm1, xmmword ptr cs:aCngcreaderLogc+0Ch; "LogControlError"
0x18001b9bf  movups  xmmword ptr [rbp+47h+var_38+0Ch], xmm1
0x18001b9c3  lea     rax, [rbp+47h+var_38]
0x18001b9c7  mov     [rbp+47h+var_68], rax
0x18001b9cb  lea     rax, [rbp+47h+var_7C]
0x18001b9cf  mov     [rbp+47h+var_60], rax
0x18001b9d3  lea     rax, [rbp+47h+var_80]
0x18001b9d7  mov     [rbp+47h+var_58], rax
0x18001b9db  lea     rcx, [rbp+47h+var_68]
0x18001b9df  call    _lambda_038bd138bd6a40c669c7e79edd05c446___operator__
0x18001b9e4  mov     [rbp+47h+var_7C], 1
0x18001b9eb  lea     rax, [rbp+47h+var_68]
0x18001b9ef  mov     [rbp+47h+var_70], rax
0x18001b9f3  mov     eax, 310028h
0x18001b9f8  cmp     ebx, eax
0x18001b9fa  ja      short loc_18001BA78
0x18001b9fc  jz      short loc_18001BA6F
0x18001b9fe  sub     ebx, 310004h
0x18001ba04  jz      short loc_18001BA66
0x18001ba06  sub     ebx, 4
0x18001ba09  jz      short loc_18001BA5D
0x18001ba0b  sub     ebx, 4
0x18001ba0e  jz      short loc_18001BA54
0x18001ba10  sub     ebx, 4
0x18001ba13  jz      short loc_18001BA48
0x18001ba15  sub     ebx, 4
0x18001ba18  jz      short loc_18001BA3C
0x18001ba1a  sub     ebx, 4
0x18001ba1d  jz      short loc_18001BA30
0x18001ba1f  cmp     ebx, 4
0x18001ba22  jnz     short loc_18001BA9C
0x18001ba24  lea     rbx, aSwallow; "SWALLOW"
0x18001ba2b  jmp     loc_18001BAD9
0x18001ba30  lea     rbx, aEject; "EJECT"
0x18001ba37  jmp     loc_18001BAD9
0x18001ba3c  lea     rbx, aTransmit; "TRANSMIT"
0x18001ba43  jmp     loc_18001BAD9
0x18001ba48  lea     rbx, aConfiscate; "CONFISCATE"
0x18001ba4f  jmp     loc_18001BAD9
0x18001ba54  lea     rbx, aSetAttribute; "SET_ATTRIBUTE"
0x18001ba5b  jmp     short loc_18001BAD9
0x18001ba5d  lea     rbx, aGetAttribute; "GET_ATTRIBUTE"
0x18001ba64  jmp     short loc_18001BAD9
0x18001ba66  lea     rbx, aPower; "POWER"
0x18001ba6d  jmp     short loc_18001BAD9
0x18001ba6f  lea     rbx, aIsPresent; "IS_PRESENT"
0x18001ba76  jmp     short loc_18001BAD9
0x18001ba78  sub     ebx, 31002Ch
0x18001ba7e  jz      short loc_18001BAD2
0x18001ba80  sub     ebx, 4
0x18001ba83  jz      short loc_18001BAC9
0x18001ba85  sub     ebx, 8
0x18001ba88  jz      short loc_18001BAC0
0x18001ba8a  sub     ebx, 4
0x18001ba8d  jz      short loc_18001BAB7
0x18001ba8f  sub     ebx, 4
0x18001ba92  jz      short loc_18001BAAE
0x18001ba94  cmp     ebx, 34E0h
0x18001ba9a  jz      short loc_18001BAA5
0x18001ba9c  lea     rbx, aUnknown; "* UNKNOWN *"
0x18001baa3  jmp     short loc_18001BAD9
0x18001baa5  lea     rbx, aGetFeatureRequ; "GET_FEATURE_REQUEST"
0x18001baac  jmp     short loc_18001BAD9
0x18001baae  lea     rbx, aGetPerfCntr; "GET_PERF_CNTR"
0x18001bab5  jmp     short loc_18001BAD9
0x18001bab7  lea     rbx, aGetLastError; "GET_LAST_ERROR"
0x18001babe  jmp     short loc_18001BAD9
0x18001bac0  lea     rbx, aGetState; "GET_STATE"
0x18001bac7  jmp     short loc_18001BAD9
0x18001bac9  lea     rbx, aSetProtocol; "SET_PROTOCOL"
0x18001bad0  jmp     short loc_18001BAD9
0x18001bad2  lea     rbx, aIsAbsent; "IS_ABSENT"
0x18001bad9  mov     [rbp+47h+var_78], 0
0x18001bae1  lea     rax, [rbp+47h+var_78]
0x18001bae5  mov     [rbp+47h+var_50], rax
0x18001bae9  mov     [rbp+47h+var_48], 0
0x18001baf1  mov     [rbp+47h+var_40], 1
0x18001baf5  lea     r8, [rbp+47h+var_48]; unsigned __int16 **
0x18001baf9  mov     edx, [rbp+47h+arg_20]; unsigned int
0x18001bafc  mov     rcx, rsi; unsigned __int8 *
0x18001baff  call    ?GenerateCommandHeaderString@@YAKPEBEKPEAPEBG@Z; GenerateCommandHeaderString(uchar const *,ulong,ushort const * *)
0x18001bb04  mov     [rbp+47h+var_80], eax
0x18001bb07  lea     rcx, [rbp+47h+var_50]
0x18001bb0b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEBGP6AXPEBG@Z$1?ConstStringHeapFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEBGPEBG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort const *,void (*)(ushort const *),&ConstStringHeapFree(ushort const *),wistd::integral_constant<unsigned __int64,0>,ushort const *,ushort const *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort const *,void (*)(ushort const *),&ConstStringHeapFree(ushort const *),wistd::integral_constant<unsigned __int64,0>,ushort const *,ushort const *,0,std::nullptr_t>>>>(void)
0x18001bb10  cmp     [rbp+47h+var_80], 0
0x18001bb14  jnz     short loc_18001BB44
0x18001bb16  mov     rax, [rbp+47h+var_78]
0x18001bb1a  cmp     dword ptr [rdi+1Ch], 0
0x18001bb1e  lea     r9, Data
0x18001bb25  jbe     short loc_18001BB2B
0x18001bb27  mov     r9, [rdi+10h]; unsigned __int16 *
0x18001bb2b  mov     [rsp+0B0h+var_88], rax; unsigned __int16 *
0x18001bb30  mov     [rsp+0B0h+var_90], rbx; unsigned __int16 *
0x18001bb35  mov     r8d, [rbp+47h+arg_28]; unsigned int
0x18001bb39  mov     edx, 262h; unsigned int
0x18001bb3e  call    ?CalaisError@@YAXPEBEKKPEBG11@Z; CalaisError(uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *)
0x18001bb43  nop
0x18001bb44  lea     rcx, [rbp+47h+var_78]
0x18001bb48  call    ??1?$unique_storage@U?$resource_policy@PEBGP6AXPEBG@Z$1?ConstStringHeapFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEBGPEBG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort const *,void (*)(ushort const *),&ConstStringHeapFree(ushort const *),wistd::integral_constant<unsigned __int64,0>,ushort const *,ushort const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort const *,void (*)(ushort const *),&ConstStringHeapFree(ushort const *),wistd::integral_constant<unsigned __int64,0>,ushort const *,ushort const *,0,std::nullptr_t>>(void)
0x18001bb4d  nop
0x18001bb4e  lea     rcx, [rbp+47h+var_70]
0x18001bb52  call    WppTraceUnwinder__lambda_038bd138bd6a40c669c7e79edd05c446_______WppTraceUnwinder__lambda_038bd138bd6a40c669c7e79edd05c446____
0x18001bb57  mov     rcx, [rbp+47h+var_18]
0x18001bb5b  xor     rcx, rsp; StackCookie
0x18001bb5e  call    __security_check_cookie
0x18001bb63  mov     rbx, [rsp+0B0h+arg_8]
0x18001bb6b  add     rsp, 0A0h
0x18001bb72  pop     rdi
0x18001bb73  pop     rsi
0x18001bb74  pop     rbp
0x18001bb75  retn
```

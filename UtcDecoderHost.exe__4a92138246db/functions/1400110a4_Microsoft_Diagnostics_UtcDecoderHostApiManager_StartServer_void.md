# Microsoft::Diagnostics::UtcDecoderHostApiManager::StartServer(void)

- ea: `0x1400110a4`
- end: `0x14001118d`
- name: `?StartServer@UtcDecoderHostApiManager@Diagnostics@Microsoft@@QEAAJXZ`
- size: `233`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcDecoderHostApiManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14000d958`

## callees

- `0x1400088f4`
- `0x14000892c`
- `0x14000c434`
- `0x1400110a4`
- `0x140011c80`
- `0x140011ea4`
- `0x140012104`

## string_xrefs

- `0x1400110fa`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapimanager.cpp`
- `0x140011122`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapimanager.cpp`
- `0x14001115c`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapimanager.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Diagnostics::UtcDecoderHostApiManager::StartServer(
        Microsoft::Diagnostics::UtcDecoderHostApiManager *this)
{
  void *v2; // rax
  const char *v3; // r9
  void *v4; // rcx
  int started; // eax
  __int64 v7; // rcx
  unsigned int v8; // edi
  int v9; // eax
  unsigned int v10; // edi
  int v11[4]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *(_BYTE *)this || *((_QWORD *)this + 1) )
    gsl::details::terminate(this);
  try
  {
    v2 = operator new(1u);
    v4 = (void *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = v2;
    if ( v4 )
      operator delete(v4);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x31,
                           (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
                           v3);
  }
  if ( *((_QWORD *)this + 1) )
  {
    started = Microsoft::Diagnostics::UtcDecoderHostApiServer::StartRpcServer((Microsoft::Diagnostics::UtcDecoderHostApiServer *)v4);
    v8 = started;
    if ( started >= 0 )
    {
      *(_OWORD *)v11 = *(_OWORD *)&off_1400193F8;
      v9 = Microsoft::Diagnostics::UtcDecoderHostApiServer::RegisterInterface(v7, (__int64)v11);
      v10 = v9;
      if ( v9 >= 0 )
      {
        *(_BYTE *)this = 1;
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2F,
          (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
          (const char *)(unsigned int)v9);
        return v10;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
        (const char *)(unsigned int)started);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (int)"onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapimanager.cpp",
      (const char *)0x8007000ELL);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1400110a4  mov     [rsp+arg_8], rbx
0x1400110a9  push    rdi
0x1400110aa  sub     rsp, 30h
0x1400110ae  mov     rbx, rcx
0x1400110b1  cmp     byte ptr [rcx], 0
0x1400110b4  jnz     loc_140011187
0x1400110ba  cmp     qword ptr [rcx+8], 0
0x1400110bf  jnz     loc_140011187
0x1400110c5  mov     ecx, 1; Size
0x1400110ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400110cf  mov     rcx, [rbx+8]; void *
0x1400110d3  mov     [rbx+8], rax
0x1400110d7  test    rcx, rcx
0x1400110da  jz      short loc_1400110E6
0x1400110dc  mov     edx, 1; unsigned __int64
0x1400110e1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400110e6  cmp     qword ptr [rbx+8], 0
0x1400110eb  jnz     short loc_14001110F
0x1400110ed  mov     rcx, [rsp+38h]; this
0x1400110f2  mov     ebx, 8007000Eh
0x1400110f7  mov     r9d, ebx; char *
0x1400110fa  lea     r8, aOnecoreBaseTel_1; "onecore\\base\\telemetry\\utc\\service"...
0x140011101  mov     edx, 2Ch ; ','; void *
0x140011106  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001110b  mov     eax, ebx
0x14001110d  jmp     short loc_140011176
0x14001110f  call    ?StartRpcServer@UtcDecoderHostApiServer@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcDecoderHostApiServer::StartRpcServer(void)
0x140011114  mov     edi, eax
0x140011116  test    eax, eax
0x140011118  jns     short loc_140011137
0x14001111a  mov     rcx, [rsp+38h]; this
0x14001111f  mov     r9d, eax; char *
0x140011122  lea     r8, aOnecoreBaseTel_1; "onecore\\base\\telemetry\\utc\\service"...
0x140011129  mov     edx, 2Eh ; '.'; void *
0x14001112e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011133  mov     eax, edi
0x140011135  jmp     short loc_140011176
0x140011137  movups  xmm0, xmmword ptr cs:off_1400193F8; "D:(A;;GA;;;S-1-5-80-2620808479-21713800"...
0x14001113e  movdqu  xmmword ptr [rsp+38h+var_18], xmm0; int
0x140011144  lea     rdx, [rsp+38h+var_18]
0x140011149  call    ?RegisterInterface@UtcDecoderHostApiServer@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEAX@Z; Microsoft::Diagnostics::UtcDecoderHostApiServer::RegisterInterface(std::wstring_view,void *)
0x14001114e  mov     edi, eax
0x140011150  test    eax, eax
0x140011152  jns     short loc_140011171
0x140011154  mov     rcx, [rsp+38h]; this
0x140011159  mov     r9d, eax; char *
0x14001115c  lea     r8, aOnecoreBaseTel_1; "onecore\\base\\telemetry\\utc\\service"...
0x140011163  mov     edx, 2Fh ; '/'; void *
0x140011168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001116d  mov     eax, edi
0x14001116f  jmp     short loc_140011176
0x140011171  mov     byte ptr [rbx], 1
0x140011174  xor     eax, eax
0x140011176  mov     rbx, [rsp+38h+arg_8]
0x14001117b  add     rsp, 30h
0x14001117f  pop     rdi
0x140011180  retn
0x140011181  mov     eax, [rsp+38h+arg_0]
0x140011185  jmp     short loc_140011176
0x140011187  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```

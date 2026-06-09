# WcmCommon::details::TPEnvironment::TPEnvironment(ulong,ulong)

- ea: `0x180009f78`
- end: `0x18000a05f`
- name: `??0TPEnvironment@details@WcmCommon@@QEAA@KK@Z`
- size: `231`
- prototype: `__int64 __fastcall(WcmCommon::details::TPEnvironment *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000521c`
- `0x180009e14`

## callees

- `0x180006950`
- `0x180009f78`
- `0x18000df4c`
- `0x180019570`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18000a03f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18000a03f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18000a021`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18000a021`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180009ff2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x180009ff2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WcmCommon::details::TPEnvironment *__fastcall WcmCommon::details::TPEnvironment::TPEnvironment(
        WcmCommon::details::TPEnvironment *this)
{
  PTP_POOL *v2; // rdi
  PTP_POOL Threadpool; // rax
  unsigned int v4; // r8d
  const char *v5; // r9
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  memset_0(this, 0, 0x48u);
  v2 = (PTP_POOL *)((char *)this + 72);
  *((_QWORD *)this + 9) = 0;
  *(_DWORD *)this = 3;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_DWORD *)this + 15) = 1;
  *((_DWORD *)this + 16) = 72;
  Threadpool = CreateThreadpool(0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(
    (char *)this + 72,
    Threadpool);
  if ( !*((_QWORD *)this + 9) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6A, v4, v5);
  if ( !SetThreadpoolThreadMinimum(*v2, 0) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x6D, v6, v7);
  SetThreadpoolThreadMaximum(*v2, 1u);
  *((_QWORD *)this + 1) = *v2;
  return this;
}

```

## disassembly

```asm
0x180009f78  mov     [rsp+arg_8], rbx
0x180009f7d  mov     [rsp+arg_10], rsi
0x180009f82  mov     [rsp+arg_0], rcx
0x180009f87  push    rdi
0x180009f88  sub     rsp, 20h
0x180009f8c  mov     rbx, rcx
0x180009f8f  mov     esi, 48h ; 'H'
0x180009f94  mov     r8d, esi; Size
0x180009f97  xor     edx, edx; Val
0x180009f99  call    memset_0
0x180009f9e  lea     rdi, [rbx+48h]
0x180009fa2  mov     qword ptr [rdi], 0
0x180009fa9  mov     dword ptr [rbx], 3
0x180009faf  mov     qword ptr [rbx+8], 0
0x180009fb7  mov     qword ptr [rbx+10h], 0
0x180009fbf  mov     qword ptr [rbx+18h], 0
0x180009fc7  mov     qword ptr [rbx+20h], 0
0x180009fcf  mov     qword ptr [rbx+28h], 0
0x180009fd7  mov     qword ptr [rbx+30h], 0
0x180009fdf  mov     dword ptr [rbx+38h], 0
0x180009fe6  mov     dword ptr [rbx+3Ch], 1
0x180009fed  mov     [rbx+40h], esi
0x180009ff0  xor     ecx, ecx; reserved
0x180009ff2  call    cs:__imp_CreateThreadpool
0x180009ff8  mov     rdx, rax
0x180009ffb  mov     rcx, rdi
0x180009ffe  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)
0x18000a003  mov     rcx, [rsp+28h]; this
0x18000a008  cmp     qword ptr [rdi], 0
0x18000a00c  jnz     short loc_18000A017
0x18000a00e  lea     edx, [rsi+22h]; void *
0x18000a011  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000a017  mov     rsi, [rsp+28h]
0x18000a01c  xor     edx, edx; cthrdMic
0x18000a01e  mov     rcx, [rdi]; ptpp
0x18000a021  call    cs:__imp_SetThreadpoolThreadMinimum
0x18000a027  test    eax, eax
0x18000a029  jnz     short loc_18000A037
0x18000a02b  lea     edx, [rax+6Dh]; void *
0x18000a02e  mov     rcx, rsi; this
0x18000a031  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000a037  mov     edx, 1; cthrdMost
0x18000a03c  mov     rcx, [rdi]; ptpp
0x18000a03f  call    cs:__imp_SetThreadpoolThreadMaximum
0x18000a045  mov     rax, [rdi]
0x18000a048  mov     [rbx+8], rax
0x18000a04c  mov     rax, rbx
0x18000a04f  mov     rbx, [rsp+28h+arg_8]
0x18000a054  mov     rsi, [rsp+28h+arg_10]
0x18000a059  add     rsp, 20h
0x18000a05d  pop     rdi
0x18000a05e  retn
```

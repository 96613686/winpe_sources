# SerialThreadpool::Initialize(bool)

- ea: `0x18002d13c`
- end: `0x18002d231`
- name: `?Initialize@SerialThreadpool@@AEAAX_N@Z`
- size: `245`
- prototype: `void __fastcall(SerialThreadpool *__hidden this, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d55c`

## callees

- `0x18000f9f0`
- `0x18002d13c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002d14e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18002d14e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002d179`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18002d179`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002d187`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18002d187`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002d1f6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18002d1f6`

## string_xrefs

- `0x18002d161`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\sensors\threadpoolhelper.h`
- `0x18002d196`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\sensors\threadpoolhelper.h`
- `0x18002d20a`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\sensors\threadpoolhelper.h`

## pseudocode

```c
void __fastcall SerialThreadpool::Initialize(PTP_POOL *this, char a2)
{
  struct _TP_POOL *Threadpool; // rax
  const char *v5; // r9
  const char *v6; // r9
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Threadpool = CreateThreadpool(0);
  *this = Threadpool;
  if ( !Threadpool )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x30,
      (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\sensors\\threadpoolhelper.h",
      v5);
  SetThreadpoolThreadMaximum(Threadpool, 1u);
  if ( !SetThreadpoolThreadMinimum(*this, 1u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x33,
      (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\sensors\\threadpoolhelper.h",
      v6);
  *((_DWORD *)this + 4) = 3;
  this[4] = 0;
  this[5] = 0;
  this[6] = 0;
  this[7] = 0;
  this[8] = 0;
  *((_DWORD *)this + 18) = 0;
  *((_DWORD *)this + 19) = 1;
  *((_DWORD *)this + 20) = 72;
  this[3] = *this;
  if ( a2 )
  {
    ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
    this[1] = ThreadpoolCleanupGroup;
    if ( !ThreadpoolCleanupGroup )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x3B,
        (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\sensors\\threadpoolhelper.h",
        v8);
    this[4] = ThreadpoolCleanupGroup;
    this[5] = 0;
  }
}

```

## disassembly

```asm
0x18002d13c  mov     [rsp+arg_0], rbx
0x18002d141  push    rdi
0x18002d142  sub     rsp, 20h
0x18002d146  mov     rbx, rcx
0x18002d149  mov     dil, dl
0x18002d14c  xor     ecx, ecx; reserved
0x18002d14e  call    cs:__imp_CreateThreadpool
0x18002d154  mov     [rbx], rax
0x18002d157  test    rax, rax
0x18002d15a  jnz     short loc_18002D171
0x18002d15c  mov     rcx, [rsp+28h]; this
0x18002d161  lea     r8, aOnecoreInterna_6; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18002d168  lea     edx, [rax+30h]; void *
0x18002d16b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002d171  mov     edx, 1; cthrdMost
0x18002d176  mov     rcx, rax; ptpp
0x18002d179  call    cs:__imp_SetThreadpoolThreadMaximum
0x18002d17f  mov     rcx, [rbx]; ptpp
0x18002d182  mov     edx, 1; cthrdMic
0x18002d187  call    cs:__imp_SetThreadpoolThreadMinimum
0x18002d18d  test    eax, eax
0x18002d18f  jnz     short loc_18002D1A6
0x18002d191  mov     rcx, [rsp+28h]; this
0x18002d196  lea     r8, aOnecoreInterna_6; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18002d19d  lea     edx, [rax+33h]; void *
0x18002d1a0  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002d1a6  mov     dword ptr [rbx+10h], 3
0x18002d1ad  mov     qword ptr [rbx+20h], 0
0x18002d1b5  mov     qword ptr [rbx+28h], 0
0x18002d1bd  mov     qword ptr [rbx+30h], 0
0x18002d1c5  mov     qword ptr [rbx+38h], 0
0x18002d1cd  mov     qword ptr [rbx+40h], 0
0x18002d1d5  mov     dword ptr [rbx+48h], 0
0x18002d1dc  mov     dword ptr [rbx+4Ch], 1
0x18002d1e3  mov     dword ptr [rbx+50h], 48h ; 'H'
0x18002d1ea  mov     rax, [rbx]
0x18002d1ed  mov     [rbx+18h], rax
0x18002d1f1  test    dil, dil
0x18002d1f4  jz      short loc_18002D226
0x18002d1f6  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18002d1fc  mov     [rbx+8], rax
0x18002d200  test    rax, rax
0x18002d203  jnz     short loc_18002D21A
0x18002d205  mov     rcx, [rsp+28h]; this
0x18002d20a  lea     r8, aOnecoreInterna_6; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x18002d211  lea     edx, [rax+3Bh]; void *
0x18002d214  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002d21a  mov     [rbx+20h], rax
0x18002d21e  mov     qword ptr [rbx+28h], 0
0x18002d226  mov     rbx, [rsp+28h+arg_0]
0x18002d22b  add     rsp, 20h
0x18002d22f  pop     rdi
0x18002d230  retn
```

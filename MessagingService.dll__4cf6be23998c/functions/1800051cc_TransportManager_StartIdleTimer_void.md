# TransportManager::_StartIdleTimer(void)

- ea: `0x1800051cc`
- end: `0x18000535d`
- name: `?_StartIdleTimer@TransportManager@@AEAAJXZ`
- size: `401`
- prototype: `__int64 __fastcall(TransportManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004ad8`
- `0x180004ea0`

## callees

- `0x18000108c`
- `0x1800044dc`
- `0x1800051cc`
- `0x18000aa50`
- `0x18000c010`

## import_xrefs

- `PhoneUtil!OneShotTimer_CreateInstance` at `0x18000522b`
- `PhoneUtil!OneShotTimer_CreateInstance` at `0x18000522b`

## string_xrefs

- `0x18000524c`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`
- `0x1800052c0`: `onecoreuap\net\messaging\desktoptransport\service\transportmanager.cpp`

## pseudocode

```c
__int64 __fastcall TransportManager::_StartIdleTimer(TransportManager *this)
{
  _QWORD *v2; // rbx
  int v3; // esi
  int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+38h] [rbp-30h] BYREF

  v2 = (_QWORD *)((char *)this + 80);
  if ( *((_QWORD *)this + 10) )
    return 0;
  v7 = 0;
  (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)this + 8LL))(this);
  v3 = OneShotTimer_CreateInstance(
         *((unsigned int *)this + 22),
         ((unsigned __int64)this + 16) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
         0,
         &v7);
  (*(void (__fastcall **)(TransportManager *))(*(_QWORD *)this + 16LL))(this);
  if ( v3 < 0 )
  {
    Log_HREvent_0((unsigned int)v3, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    return (unsigned int)v3;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
  if ( v2 )
  {
    v6 = v7;
    *v2 = v7;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    v5 = 0;
  }
  else
  {
    v5 = -2147467261;
  }
  if ( v5 >= 0 )
  {
    if ( (unsigned int)dword_180013018 > 5 )
      tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&word_18001023E, 0, 0, 2u, &v8);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    return 0;
  }
  Log_HREvent_0((unsigned int)v5, 1, "onecoreuap\\net\\messaging\\desktoptransport\\service\\transportmanager.cpp");
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800051cc  mov     [rsp+arg_8], rbx
0x1800051d1  mov     [rsp+arg_10], rsi
0x1800051d6  push    rdi
0x1800051d7  sub     rsp, 60h
0x1800051db  mov     rax, cs:__security_cookie
0x1800051e2  xor     rax, rsp
0x1800051e5  mov     [rsp+68h+var_10], rax
0x1800051ea  mov     rdi, rcx
0x1800051ed  lea     rbx, [rcx+50h]
0x1800051f1  cmp     qword ptr [rbx], 0
0x1800051f5  jnz     loc_18000533C
0x1800051fb  mov     [rsp+68h+var_38], 0
0x180005204  mov     rax, [rcx]
0x180005207  mov     rax, [rax+8]
0x18000520b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005210  mov     rax, rdi
0x180005213  lea     r8, [rdi+10h]
0x180005217  neg     rax
0x18000521a  sbb     rdx, rdx
0x18000521d  and     rdx, r8
0x180005220  lea     r9, [rsp+68h+var_38]
0x180005225  xor     r8d, r8d
0x180005228  mov     ecx, [rdi+58h]
0x18000522b  call    cs:__imp_OneShotTimer_CreateInstance
0x180005231  mov     esi, eax
0x180005233  mov     rdx, [rdi]
0x180005236  mov     rcx, rdi
0x180005239  mov     rax, [rdx+10h]
0x18000523d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005242  test    esi, esi
0x180005244  jns     short loc_18000527D
0x180005246  mov     r9d, 41h ; 'A'
0x18000524c  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x180005253  lea     edx, [r9-40h]
0x180005257  mov     ecx, esi
0x180005259  call    Log_HREvent_0
0x18000525e  nop
0x18000525f  mov     rcx, [rsp+68h+var_38]
0x180005264  test    rcx, rcx
0x180005267  jz      short loc_180005276
0x180005269  mov     rax, [rcx]
0x18000526c  mov     rax, [rax+10h]
0x180005270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005275  nop
0x180005276  mov     eax, esi
0x180005278  jmp     loc_18000533E
0x18000527d  mov     rcx, [rsp+68h+var_38]
0x180005282  mov     rax, [rcx]
0x180005285  mov     rax, [rax+18h]
0x180005289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528e  nop
0x18000528f  test    rbx, rbx
0x180005292  jnz     short loc_18000529B
0x180005294  mov     ebx, 80004003h
0x180005299  jmp     short loc_1800052B6
0x18000529b  mov     rcx, [rsp+68h+var_38]
0x1800052a0  mov     [rbx], rcx
0x1800052a3  test    rcx, rcx
0x1800052a6  jz      short loc_1800052B4
0x1800052a8  mov     rax, [rcx]
0x1800052ab  mov     rax, [rax+8]
0x1800052af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052b4  xor     ebx, ebx
0x1800052b6  test    ebx, ebx
0x1800052b8  jns     short loc_1800052EE
0x1800052ba  mov     r9d, 45h ; 'E'
0x1800052c0  lea     r8, aOnecoreuapNetM_6; "onecoreuap\\net\\messaging\\desktoptran"...
0x1800052c7  lea     edx, [r9-44h]
0x1800052cb  mov     ecx, ebx
0x1800052cd  call    Log_HREvent_0
0x1800052d2  nop
0x1800052d3  mov     rcx, [rsp+68h+var_38]
0x1800052d8  test    rcx, rcx
0x1800052db  jz      short loc_1800052EA
0x1800052dd  mov     rdx, [rcx]
0x1800052e0  mov     rax, [rdx+10h]
0x1800052e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e9  nop
0x1800052ea  mov     eax, ebx
0x1800052ec  jmp     short loc_18000533E
0x1800052ee  mov     eax, cs:dword_180013018
0x1800052f4  cmp     eax, 5
0x1800052f7  jbe     short loc_180005325
0x1800052f9  lea     rax, [rsp+68h+var_30]
0x1800052fe  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x180005303  mov     [rsp+68h+var_48], 2; ULONG
0x18000530b  xor     r9d, r9d; int
0x18000530e  xor     r8d, r8d; int
0x180005311  lea     rdx, word_18001023E; int
0x180005318  lea     rcx, dword_180013018; int
0x18000531f  call    _tlgWriteTransfer_EventWriteTransfer
0x180005324  nop
0x180005325  mov     rcx, [rsp+68h+var_38]
0x18000532a  test    rcx, rcx
0x18000532d  jz      short loc_18000533C
0x18000532f  mov     rax, [rcx]
0x180005332  mov     rax, [rax+10h]
0x180005336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000533b  nop
0x18000533c  xor     eax, eax
0x18000533e  mov     rcx, [rsp+68h+var_10]
0x180005343  xor     rcx, rsp; StackCookie
0x180005346  call    __security_check_cookie
0x18000534b  lea     r11, [rsp+68h+var_8]
0x180005350  mov     rbx, [r11+18h]
0x180005354  mov     rsi, [r11+20h]
0x180005358  mov     rsp, r11
0x18000535b  pop     rdi
0x18000535c  retn
```

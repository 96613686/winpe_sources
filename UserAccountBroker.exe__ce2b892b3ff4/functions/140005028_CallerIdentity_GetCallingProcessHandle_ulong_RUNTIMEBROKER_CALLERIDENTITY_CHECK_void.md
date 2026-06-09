# CallerIdentity::GetCallingProcessHandle(ulong,RUNTIMEBROKER_CALLERIDENTITY_CHECK,void * *)

- ea: `0x140005028`
- end: `0x140005111`
- name: `?GetCallingProcessHandle@CallerIdentity@@YAJKW4RUNTIMEBROKER_CALLERIDENTITY_CHECK@@PEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, __int64, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000384c`

## callees

- `0x140005028`
- `0x140006314`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140005051`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140005051`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400050a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400050a0`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetCallingProcessHandle(__int64 a1, __int64 a2, HANDLE *a3)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  void *v6; // rcx
  void (*v7)(void); // rax
  void *v8; // rcx
  void *v10; // rcx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *ppInterface; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  ppInterface = 0;
  v4 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( v4 != -2147417833 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
        (const char *)(unsigned int)v4,
        v11);
      v10 = ppInterface;
      if ( ppInterface )
      {
        ppInterface = 0;
        v7 = *(void (**)(void))(*(_QWORD *)v10 + 16LL);
        goto LABEL_12;
      }
      return v5;
    }
    *a3 = GetCurrentProcess();
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL))(
           ppInterface,
           0x100000,
           a3);
    if ( (v5 & 0x80000000) != 0 )
    {
      v6 = ppInterface;
      if ( ppInterface )
      {
        ppInterface = 0;
        v7 = *(void (**)(void))(*(_QWORD *)v6 + 16LL);
LABEL_12:
        v7();
        return v5;
      }
      return v5;
    }
  }
  v8 = ppInterface;
  if ( ppInterface )
  {
    ppInterface = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x140005028  mov     [rsp+arg_0], rbx
0x14000502d  push    rdi; int
0x14000502e  sub     rsp, 20h
0x140005032  lea     rdx, [rsp+28h+ppInterface]; ppInterface
0x140005037  mov     qword ptr [r8], 0
0x14000503e  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x140005045  mov     [rsp+28h+ppInterface], 0
0x14000504e  mov     rdi, r8
0x140005051  call    cs:__imp_CoGetCallContext
0x140005057  mov     ebx, eax
0x140005059  test    eax, eax
0x14000505b  js      short loc_140005098
0x14000505d  mov     rcx, [rsp+28h+ppInterface]
0x140005062  mov     r8, rdi
0x140005065  mov     edx, 100000h
0x14000506a  mov     rax, [rcx]
0x14000506d  mov     rax, [rax+18h]
0x140005071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005076  mov     ebx, eax
0x140005078  test    eax, eax
0x14000507a  jns     short loc_1400050A9
0x14000507c  mov     rcx, [rsp+28h+ppInterface]
0x140005081  test    rcx, rcx
0x140005084  jz      short loc_140005104
0x140005086  mov     [rsp+28h+ppInterface], 0
0x14000508f  mov     rdx, [rcx]
0x140005092  mov     rax, [rdx+10h]
0x140005096  jmp     short loc_1400050FF
0x140005098  cmp     ebx, 80010117h
0x14000509e  jnz     short loc_1400050CC
0x1400050a0  call    cs:__imp_GetCurrentProcess
0x1400050a6  mov     [rdi], rax
0x1400050a9  mov     rcx, [rsp+28h+ppInterface]
0x1400050ae  test    rcx, rcx
0x1400050b1  jz      short loc_1400050C8
0x1400050b3  mov     [rsp+28h+ppInterface], 0
0x1400050bc  mov     rax, [rcx]
0x1400050bf  mov     rax, [rax+10h]
0x1400050c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050c8  xor     eax, eax
0x1400050ca  jmp     short loc_140005106
0x1400050cc  mov     rcx, [rsp+28h]; this
0x1400050d1  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1400050d8  mov     r9d, ebx; char *
0x1400050db  mov     edx, 58h ; 'X'; void *
0x1400050e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400050e5  mov     rcx, [rsp+28h+ppInterface]
0x1400050ea  test    rcx, rcx
0x1400050ed  jz      short loc_140005104
0x1400050ef  mov     [rsp+28h+ppInterface], 0
0x1400050f8  mov     rax, [rcx]
0x1400050fb  mov     rax, [rax+10h]
0x1400050ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005104  mov     eax, ebx
0x140005106  mov     rbx, [rsp+28h+arg_0]
0x14000510b  add     rsp, 20h
0x14000510f  pop     rdi
0x140005110  retn
```

# CMidiEndpointProtocolWorker::CheckIfDiscoveryComplete(void)

- ea: `0x140041670`
- end: `0x140041721`
- name: `?CheckIfDiscoveryComplete@CMidiEndpointProtocolWorker@@AEAAJXZ`
- size: `177`
- prototype: `__int64 __fastcall(CMidiEndpointProtocolWorker *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400412c0`

## callees

- `0x140008b34`
- `0x14000c55c`
- `0x140041670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400416b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400416d0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400416b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400416d0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400416e3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400416e3`

## string_xrefs

- `0x14004170f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::CheckIfDiscoveryComplete(CMidiEndpointProtocolWorker *this)
{
  __int64 v2; // rax
  void *v3; // rdi
  DWORD v4; // eax
  const char *v5; // r9
  __int64 v6; // r8
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_BYTE *)this + 317) )
  {
    if ( *((_BYTE *)this + 319) )
    {
      v2 = *((unsigned __int8 *)this + 323);
      if ( *((_QWORD *)this + 38) == v2 && *((_QWORD *)this + 36) == v2 )
      {
        v3 = (void *)*((_QWORD *)this + 19);
        v4 = WaitForSingleObjectEx(v3, 0, 0);
        if ( v4 == 258 )
        {
          if ( !SetEvent(*((HANDLE *)this + 19)) )
            wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v6, v7);
        }
        else if ( v4 || WaitForSingleObjectEx(v3, 0, 0) )
        {
          wil::details::in1diag3::FailFast_Unexpected(
            retaddr,
            (void *)0xB07,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v5);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140041670  mov     [rsp+arg_0], rbx
0x140041675  push    rdi
0x140041676  sub     rsp, 20h
0x14004167a  cmp     byte ptr [rcx+13Dh], 0
0x140041681  mov     rbx, rcx
0x140041684  jz      short loc_1400416ED
0x140041686  cmp     byte ptr [rcx+13Fh], 0
0x14004168d  jz      short loc_1400416ED
0x14004168f  movzx   eax, byte ptr [rcx+143h]
0x140041696  cmp     [rcx+130h], rax
0x14004169d  jnz     short loc_1400416ED
0x14004169f  cmp     [rcx+120h], rax
0x1400416a6  jnz     short loc_1400416ED
0x1400416a8  mov     rdi, [rcx+98h]
0x1400416af  xor     r8d, r8d; bAlertable
0x1400416b2  mov     rcx, rdi; hHandle
0x1400416b5  xor     edx, edx; dwMilliseconds
0x1400416b7  call    cs:__imp_WaitForSingleObjectEx
0x1400416bd  cmp     eax, 102h
0x1400416c2  jz      short loc_1400416DC
0x1400416c4  test    eax, eax
0x1400416c6  jnz     short loc_14004170A
0x1400416c8  xor     r8d, r8d; bAlertable
0x1400416cb  xor     edx, edx; dwMilliseconds
0x1400416cd  mov     rcx, rdi; hHandle
0x1400416d0  call    cs:__imp_WaitForSingleObjectEx
0x1400416d6  test    eax, eax
0x1400416d8  jnz     short loc_14004170A
0x1400416da  jmp     short loc_1400416ED
0x1400416dc  mov     rcx, [rbx+98h]; hEvent
0x1400416e3  call    cs:__imp_SetEvent
0x1400416e9  test    eax, eax
0x1400416eb  jz      short loc_1400416FA
0x1400416ed  mov     rbx, [rsp+28h+arg_0]
0x1400416f2  xor     eax, eax
0x1400416f4  add     rsp, 20h
0x1400416f8  pop     rdi
0x1400416f9  retn
0x1400416fa  mov     rcx, [rsp+28h]; this
0x1400416ff  mov     edx, 0A01h; void *
0x140041704  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14004170a  mov     rcx, [rsp+28h]; this
0x14004170f  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140041716  mov     edx, 0B07h; void *
0x14004171b  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```

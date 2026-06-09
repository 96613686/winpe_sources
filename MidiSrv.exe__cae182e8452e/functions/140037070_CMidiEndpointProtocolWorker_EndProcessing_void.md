# CMidiEndpointProtocolWorker::EndProcessing(void)

- ea: `0x140037070`
- end: `0x1400370f9`
- name: `?EndProcessing@CMidiEndpointProtocolWorker@@QEAAXXZ`
- size: `137`
- prototype: `void __fastcall(CMidiEndpointProtocolWorker *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140037dd0`
- `0x1400435a0`

## callees

- `0x140008b34`
- `0x14000c55c`
- `0x140037070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140037091`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400370aa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140037091`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400370aa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400370bd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400370bd`

## string_xrefs

- `0x1400370e7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall CMidiEndpointProtocolWorker::EndProcessing(CMidiEndpointProtocolWorker *this)
{
  void *v1; // rbx
  DWORD v3; // eax
  const char *v4; // r9
  __int64 v5; // r8
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (void *)*((_QWORD *)this + 18);
  if ( v1 )
  {
    v3 = WaitForSingleObjectEx(*((HANDLE *)this + 18), 0, 0);
    if ( v3 == 258 )
    {
      if ( !SetEvent(*((HANDLE *)this + 18)) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v5, v6);
    }
    else if ( v3 || WaitForSingleObjectEx(v1, 0, 0) )
    {
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xB07,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    }
  }
}

```

## disassembly

```asm
0x140037070  mov     [rsp+arg_0], rbx
0x140037075  push    rdi
0x140037076  sub     rsp, 20h
0x14003707a  mov     rbx, [rcx+90h]
0x140037081  mov     rdi, rcx
0x140037084  test    rbx, rbx
0x140037087  jz      short loc_1400370C7
0x140037089  xor     r8d, r8d; bAlertable
0x14003708c  xor     edx, edx; dwMilliseconds
0x14003708e  mov     rcx, rbx; hHandle
0x140037091  call    cs:__imp_WaitForSingleObjectEx
0x140037097  cmp     eax, 102h
0x14003709c  jz      short loc_1400370B6
0x14003709e  test    eax, eax
0x1400370a0  jnz     short loc_1400370E2
0x1400370a2  xor     r8d, r8d; bAlertable
0x1400370a5  xor     edx, edx; dwMilliseconds
0x1400370a7  mov     rcx, rbx; hHandle
0x1400370aa  call    cs:__imp_WaitForSingleObjectEx
0x1400370b0  test    eax, eax
0x1400370b2  jnz     short loc_1400370E2
0x1400370b4  jmp     short loc_1400370C7
0x1400370b6  mov     rcx, [rdi+90h]; hEvent
0x1400370bd  call    cs:__imp_SetEvent
0x1400370c3  test    eax, eax
0x1400370c5  jz      short loc_1400370D2
0x1400370c7  mov     rbx, [rsp+28h+arg_0]
0x1400370cc  add     rsp, 20h
0x1400370d0  pop     rdi
0x1400370d1  retn
0x1400370d2  mov     rcx, [rsp+28h]; this
0x1400370d7  mov     edx, 0A01h; void *
0x1400370dc  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400370e2  mov     rcx, [rsp+28h]; this
0x1400370e7  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400370ee  mov     edx, 0B07h; void *
0x1400370f3  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```

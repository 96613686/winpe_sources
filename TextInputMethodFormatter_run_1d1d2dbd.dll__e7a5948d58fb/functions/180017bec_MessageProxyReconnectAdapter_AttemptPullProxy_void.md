# MessageProxyReconnectAdapter::AttemptPullProxy(void)

- ea: `0x180017bec`
- end: `0x180017d1c`
- name: `?AttemptPullProxy@MessageProxyReconnectAdapter@@AEAAJXZ`
- size: `304`
- prototype: `__int64 __fastcall(MessageProxyReconnectAdapter *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800183d0`
- `0x180018860`

## callees

- `0x180006a14`
- `0x1800167f8`
- `0x180017bec`
- `0x180017d24`
- `0x18001800c`
- `0x1800180c8`
- `0x1800187b8`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017ce0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017ce0`

## pseudocode

```c
__int64 __fastcall MessageProxyReconnectAdapter::AttemptPullProxy(MessageProxyReconnectAdapter *this)
{
  unsigned int RemoteProxy; // eax
  int v3; // edi
  __int64 v4; // rdx
  unsigned int v6; // eax
  const char *StringRawBuffer; // rax
  int v8; // [rsp+20h] [rbp-18h]
  int v9; // [rsp+20h] [rbp-18h]
  const char *v10; // [rsp+30h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  LOBYTE(v8) = *((_QWORD *)this + 8) != 0;
  wil::details::in1diag3::Log_HrIfMsg(
    retaddr,
    (void *)0xBA,
    (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
    (const char *)0x8000FFFFLL,
    v8,
    (bool)"Not expecting to pull a proxy when we have one",
    v10);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
  ++*((_DWORD *)this + 10);
  RemoteProxy = MessageProxyReconnectAdapter::CreateRemoteProxy(this);
  v3 = RemoteProxy;
  if ( RemoteProxy )
  {
    if ( ((RemoteProxy + 2018375675) & 0xFFFFFFFB) != 0 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xF1,
        (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
        (const char *)RemoteProxy,
        v9);
    }
    else
    {
      v6 = *((_DWORD *)this + 25);
      if ( *((_DWORD *)this + 10) >= v6 && v6 )
      {
        MessageProxyReconnectAdapter::StopConnectionRetryTimer(this);
        if ( *((_BYTE *)this + 104) )
        {
          StringRawBuffer = (const char *)WindowsGetStringRawBuffer(*((HSTRING *)this + 11), 0);
          wil::details::in1diag3::FailFast_IfFailedMsg(
            retaddr,
            (void *)0xE7,
            (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
            (const char *)(unsigned int)v3,
            (int)"Proxy connection failed: %ls",
            StringRawBuffer);
        }
        else if ( v3 < 0 )
        {
          v4 = 235;
          goto LABEL_4;
        }
      }
    }
  }
  else
  {
    v3 = MessageProxyReconnectAdapter::StopConnectionRetryTimer(this);
    if ( v3 < 0 )
    {
      v4 = 212;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"mincore\\textinput\\dev\\sharedlibs\\messageproxyreconnectadapter\\messageproxyreconnectadapter.cpp",
        (const char *)(unsigned int)v3,
        v9);
      return (unsigned int)v3;
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 16LL))(*((_QWORD *)this + 6));
  return 0;
}

```

## disassembly

```asm
0x180017bec  mov     [rsp+arg_0], rbx
0x180017bf1  mov     [rsp+arg_8], rsi
0x180017bf6  push    rdi; char *
0x180017bf7  sub     rsp, 30h
0x180017bfb  cmp     qword ptr [rcx+40h], 0
0x180017c00  lea     rdx, aNotExpectingTo; "Not expecting to pull a proxy when we h"...
0x180017c07  mov     [rsp+38h+var_10], rdx; bool
0x180017c0c  lea     rsi, aMincoreTextinp_8; "mincore\\textinput\\dev\\sharedlibs\\me"...
0x180017c13  setnz   al
0x180017c16  mov     rbx, rcx
0x180017c19  mov     rcx, [rsp+38h]; this
0x180017c1e  mov     r9d, 8000FFFFh; char *
0x180017c24  mov     r8, rsi; unsigned int
0x180017c27  mov     byte ptr [rsp+38h+var_18], al; int
0x180017c2b  mov     edx, 0BAh; void *
0x180017c30  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180017c35  mov     rcx, [rbx+30h]
0x180017c39  mov     rax, [rcx]
0x180017c3c  mov     rax, [rax+8]
0x180017c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c45  inc     dword ptr [rbx+28h]
0x180017c48  mov     rcx, rbx; this
0x180017c4b  call    ?CreateRemoteProxy@MessageProxyReconnectAdapter@@AEAAJXZ; MessageProxyReconnectAdapter::CreateRemoteProxy(void)
0x180017c50  mov     edi, eax
0x180017c52  test    eax, eax
0x180017c54  jnz     short loc_180017C7D
0x180017c56  mov     rcx, rbx; this
0x180017c59  call    ?StopConnectionRetryTimer@MessageProxyReconnectAdapter@@AEAAJXZ; MessageProxyReconnectAdapter::StopConnectionRetryTimer(void)
0x180017c5e  mov     edi, eax
0x180017c60  test    eax, eax
0x180017c62  jns     short loc_180017C9E
0x180017c64  mov     edx, 0D4h; void *
0x180017c69  mov     rcx, [rsp+38h]; this
0x180017c6e  mov     r8, rsi; unsigned int
0x180017c71  mov     r9d, edi; char *
0x180017c74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c79  mov     eax, edi
0x180017c7b  jmp     short loc_180017CB0
0x180017c7d  add     eax, 784DF7FBh
0x180017c82  test    eax, 0FFFFFFFBh
0x180017c87  jz      short loc_180017CC0
0x180017c89  mov     rcx, [rsp+38h]; this
0x180017c8e  mov     r9d, edi; char *
0x180017c91  mov     r8, rsi; unsigned int
0x180017c94  mov     edx, 0F1h; void *
0x180017c99  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180017c9e  mov     rcx, [rbx+30h]
0x180017ca2  mov     rax, [rcx]
0x180017ca5  mov     rax, [rax+10h]
0x180017ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cae  xor     eax, eax
0x180017cb0  mov     rbx, [rsp+38h+arg_0]
0x180017cb5  mov     rsi, [rsp+38h+arg_8]
0x180017cba  add     rsp, 30h
0x180017cbe  pop     rdi
0x180017cbf  retn
0x180017cc0  mov     eax, [rbx+64h]
0x180017cc3  cmp     [rbx+28h], eax
0x180017cc6  jb      short loc_180017C9E
0x180017cc8  test    eax, eax
0x180017cca  jz      short loc_180017C9E
0x180017ccc  mov     rcx, rbx; this
0x180017ccf  call    ?StopConnectionRetryTimer@MessageProxyReconnectAdapter@@AEAAJXZ; MessageProxyReconnectAdapter::StopConnectionRetryTimer(void)
0x180017cd4  cmp     byte ptr [rbx+68h], 0
0x180017cd8  jz      short loc_180017D0E
0x180017cda  mov     rcx, [rbx+58h]; string
0x180017cde  xor     edx, edx; length
0x180017ce0  call    cs:__imp_WindowsGetStringRawBuffer
0x180017ce6  mov     rcx, [rsp+38h]; this
0x180017ceb  mov     r9d, edi; char *
0x180017cee  mov     [rsp+38h+var_10], rax; char *
0x180017cf3  mov     r8, rsi; unsigned int
0x180017cf6  lea     rax, aProxyConnectio; "Proxy connection failed: %ls"
0x180017cfd  mov     edx, 0E7h; void *
0x180017d02  mov     qword ptr [rsp+38h+var_18], rax; int
0x180017d07  call    ?FailFast_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180017d0c  jmp     short loc_180017C9E
0x180017d0e  test    edi, edi
0x180017d10  jns     short loc_180017C9E
0x180017d12  mov     edx, 0EBh
0x180017d17  jmp     loc_180017C69
```

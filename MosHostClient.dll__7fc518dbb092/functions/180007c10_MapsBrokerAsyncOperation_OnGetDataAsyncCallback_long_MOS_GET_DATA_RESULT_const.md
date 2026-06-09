# MapsBrokerAsyncOperation::OnGetDataAsyncCallback(long,MOS_GET_DATA_RESULT const &)

- ea: `0x180007c10`
- end: `0x180007cdd`
- name: `?OnGetDataAsyncCallback@MapsBrokerAsyncOperation@@QEAAXJAEBUMOS_GET_DATA_RESULT@@@Z`
- size: `205`
- prototype: `void __fastcall(MapsBrokerAsyncOperation *__hidden this, int, const struct MOS_GET_DATA_RESULT *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009f30`
- `0x18000a3f0`
- `0x18000be20`

## callees

- `0x1800047f0`
- `0x180007158`
- `0x180007bc0`
- `0x180007c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007ca1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007ca1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007cbb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007c78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007c91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007c78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007c91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007c2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007c2d`

## pseudocode

```c
void __fastcall MapsBrokerAsyncOperation::OnGetDataAsyncCallback(
        MapsBrokerAsyncOperation *this,
        int a2,
        const struct MOS_GET_DATA_RESULT *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbp
  void *v7; // rbx
  DWORD v8; // eax
  int v9; // r8d
  const char *v10; // r9
  __int64 v11; // r8
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 24) = a2;
  *(_OWORD *)((char *)this + 104) = *(_OWORD *)a3;
  *(_OWORD *)((char *)this + 120) = *((_OWORD *)a3 + 1);
  *(_OWORD *)((char *)this + 136) = *((_OWORD *)a3 + 2);
  if ( *((_QWORD *)this + 8) )
    MapsBrokerAsyncOperation::InvokeCallback(this);
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 11);
  v8 = WaitForSingleObjectEx(v7, 0, 0);
  if ( v8 != 258 )
  {
    if ( v8 || WaitForSingleObjectEx(v7, 0, 0) )
      wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB07, v9, v10);
    __int2c();
  }
  if ( !SetEvent(*((HANDLE *)this + 11)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v11, v12);
  LeaveCriticalSection(v6);
}

```

## disassembly

```asm
0x180007c10  push    rbx
0x180007c12  push    rbp
0x180007c13  push    rsi
0x180007c14  push    rdi
0x180007c15  sub     rsp, 38h
0x180007c19  mov     rdi, r8
0x180007c1c  mov     ebx, edx
0x180007c1e  mov     rsi, rcx
0x180007c21  lea     rbp, [rcx+10h]
0x180007c25  mov     [rsp+58h+var_38], rbp
0x180007c2a  mov     rcx, rbp; lpCriticalSection
0x180007c2d  call    cs:__imp_EnterCriticalSection
0x180007c33  mov     [rsp+58h+var_30], 1
0x180007c38  mov     [rsi+60h], ebx
0x180007c3b  movups  xmm0, xmmword ptr [rdi]
0x180007c3e  movups  xmmword ptr [rsi+68h], xmm0
0x180007c42  movups  xmm1, xmmword ptr [rdi+10h]
0x180007c46  movups  xmmword ptr [rsi+78h], xmm1
0x180007c4a  movups  xmm0, xmmword ptr [rdi+20h]
0x180007c4e  movups  xmmword ptr [rsi+88h], xmm0
0x180007c55  cmp     qword ptr [rsi+40h], 0
0x180007c5a  jz      short loc_180007C64
0x180007c5c  mov     rcx, rsi; this
0x180007c5f  call    ?InvokeCallback@MapsBrokerAsyncOperation@@AEAAXXZ; MapsBrokerAsyncOperation::InvokeCallback(void)
0x180007c64  mov     qword ptr [rsi+38h], 0
0x180007c6c  mov     rbx, [rsi+58h]
0x180007c70  xor     r8d, r8d; bAlertable
0x180007c73  xor     edx, edx; dwMilliseconds
0x180007c75  mov     rcx, rbx; hHandle
0x180007c78  call    cs:__imp_WaitForSingleObjectEx
0x180007c7e  cmp     eax, 102h
0x180007c83  jz      short loc_180007C9D
0x180007c85  test    eax, eax
0x180007c87  jnz     short loc_180007CC2
0x180007c89  xor     r8d, r8d; bAlertable
0x180007c8c  xor     edx, edx; dwMilliseconds
0x180007c8e  mov     rcx, rbx; hHandle
0x180007c91  call    cs:__imp_WaitForSingleObjectEx
0x180007c97  test    eax, eax
0x180007c99  jnz     short loc_180007CC2
0x180007c9b  int     2Ch; Windows NT - assertion failure
0x180007c9d  mov     rcx, [rsi+58h]; hEvent
0x180007ca1  call    cs:__imp_SetEvent
0x180007ca7  mov     rcx, [rsp+58h]; this
0x180007cac  test    eax, eax
0x180007cae  jz      short loc_180007CD2
0x180007cb0  mov     rcx, rbp
0x180007cb3  add     rsp, 38h
0x180007cb7  pop     rdi
0x180007cb8  pop     rsi
0x180007cb9  pop     rbp
0x180007cba  pop     rbx
0x180007cbb  jmp     cs:__imp_LeaveCriticalSection
0x180007cc2  mov     rcx, [rsp+58h]; this
0x180007cc7  mov     edx, 0B07h; void *
0x180007ccc  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180007cd2  mov     edx, 0A01h; void *
0x180007cd7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

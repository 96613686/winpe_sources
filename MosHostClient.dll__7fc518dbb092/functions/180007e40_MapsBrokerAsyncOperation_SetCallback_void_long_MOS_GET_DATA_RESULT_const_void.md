# MapsBrokerAsyncOperation::SetCallback(void (*)(long,MOS_GET_DATA_RESULT const &),void *)

- ea: `0x180007e40`
- end: `0x180007f05`
- name: `?SetCallback@MapsBrokerAsyncOperation@@UEAAJP6AXJAEBUMOS_GET_DATA_RESULT@@@ZPEAX@Z`
- size: `197`
- prototype: `__int64 __fastcall(MapsBrokerAsyncOperation *__hidden this, void (*)(int, const struct MOS_GET_DATA_RESULT *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800047f0`
- `0x180006214`
- `0x180007bc0`
- `0x180007e40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007ee4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007ee4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007eb5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007ece`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007eb5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007ece`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e5e`

## string_xrefs

- `0x180007e7b`: `onecoreuap\windows\maps\moshost\client\mapsbrokerasyncoperation.cpp`

## pseudocode

```c
__int64 __fastcall MapsBrokerAsyncOperation::SetCallback(
        MapsBrokerAsyncOperation *this,
        void (*a2)(int, const struct MOS_GET_DATA_RESULT *),
        void *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  void *v8; // rsi
  DWORD v9; // eax
  int v10; // r8d
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    if ( *((_QWORD *)this + 8) )
      __int2c();
    *((_QWORD *)this + 8) = a2;
    *((_QWORD *)this + 10) = a3;
    v8 = (void *)*((_QWORD *)this + 11);
    v9 = WaitForSingleObjectEx(v8, 0, 0);
    if ( v9 != 258 )
    {
      if ( v9 || WaitForSingleObjectEx(v8, 0, 0) )
        wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB07, v10, v11);
      MapsBrokerAsyncOperation::InvokeCallback(this);
    }
    LeaveCriticalSection(v6);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (int)"onecoreuap\\windows\\maps\\moshost\\client\\mapsbrokerasyncoperation.cpp",
      (const char *)0x80070057LL);
    LeaveCriticalSection(v6);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180007e40  push    rbx
0x180007e42  push    rbp
0x180007e43  push    rsi
0x180007e44  push    rdi
0x180007e45  sub     rsp, 38h
0x180007e49  mov     rbp, r8
0x180007e4c  mov     rsi, rdx
0x180007e4f  mov     rbx, rcx
0x180007e52  lea     rdi, [rcx+10h]
0x180007e56  mov     qword ptr [rsp+58h+var_38], rdi; int
0x180007e5b  mov     rcx, rdi; lpCriticalSection
0x180007e5e  call    cs:__imp_EnterCriticalSection
0x180007e64  mov     [rsp+58h+var_30], 1
0x180007e69  test    rsi, rsi
0x180007e6c  jnz     short loc_180007E98
0x180007e6e  mov     rcx, [rsp+58h]; this
0x180007e73  mov     ebx, 80070057h
0x180007e78  mov     r9d, ebx; char *
0x180007e7b  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180007e82  lea     edx, [rsi+3Bh]; void *
0x180007e85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e8a  nop
0x180007e8b  mov     rcx, rdi; lpCriticalSection
0x180007e8e  call    cs:__imp_LeaveCriticalSection
0x180007e94  mov     eax, ebx
0x180007e96  jmp     short loc_180007EEC
0x180007e98  cmp     qword ptr [rbx+40h], 0
0x180007e9d  jz      short loc_180007EA1
0x180007e9f  int     2Ch; Windows NT - assertion failure
0x180007ea1  mov     [rbx+40h], rsi
0x180007ea5  mov     [rbx+50h], rbp
0x180007ea9  mov     rsi, [rbx+58h]
0x180007ead  xor     r8d, r8d; bAlertable
0x180007eb0  xor     edx, edx; dwMilliseconds
0x180007eb2  mov     rcx, rsi; hHandle
0x180007eb5  call    cs:__imp_WaitForSingleObjectEx
0x180007ebb  cmp     eax, 102h
0x180007ec0  jz      short loc_180007EE1
0x180007ec2  test    eax, eax
0x180007ec4  jnz     short loc_180007EF5
0x180007ec6  xor     r8d, r8d; bAlertable
0x180007ec9  xor     edx, edx; dwMilliseconds
0x180007ecb  mov     rcx, rsi; hHandle
0x180007ece  call    cs:__imp_WaitForSingleObjectEx
0x180007ed4  test    eax, eax
0x180007ed6  jnz     short loc_180007EF5
0x180007ed8  mov     rcx, rbx; this
0x180007edb  call    ?InvokeCallback@MapsBrokerAsyncOperation@@AEAAXXZ; MapsBrokerAsyncOperation::InvokeCallback(void)
0x180007ee0  nop
0x180007ee1  mov     rcx, rdi; lpCriticalSection
0x180007ee4  call    cs:__imp_LeaveCriticalSection
0x180007eea  xor     eax, eax
0x180007eec  add     rsp, 38h
0x180007ef0  pop     rdi
0x180007ef1  pop     rsi
0x180007ef2  pop     rbp
0x180007ef3  pop     rbx
0x180007ef4  retn
0x180007ef5  mov     rcx, [rsp+58h]; this
0x180007efa  mov     edx, 0B07h; void *
0x180007eff  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```

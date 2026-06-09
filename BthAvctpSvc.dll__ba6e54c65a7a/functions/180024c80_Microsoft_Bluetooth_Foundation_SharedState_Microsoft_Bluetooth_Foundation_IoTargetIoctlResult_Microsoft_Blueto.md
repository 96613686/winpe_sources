# Microsoft::Bluetooth::Foundation::SharedState<Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>>::GetResult(void)

- ea: `0x180024c80`
- end: `0x180024d6d`
- name: `?GetResult@?$SharedState@U?$IoTargetIoctlResult@V?$RequestBufferView@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T@Foundation@Bluetooth@Microsoft@@@Foundation@Bluetooth@Microsoft@@QEAA?AU?$IoTargetIoctlResult@V?$RequestBufferView@UKSIDENTIFIER@@@Foundation@Bluetooth@Microsoft@@$$T@234@XZ`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024e90`
- `0x180043d98`

## callees

- `0x180004bd8`
- `0x18001f460`
- `0x180024c80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ce9`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180024cdf`
- `api-ms-win-core-synch-l1-2-0!WaitOnAddress` at `0x180024cdf`

## string_xrefs

- `0x180024d5b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall Microsoft::Bluetooth::Foundation::SharedState<Microsoft::Bluetooth::Foundation::IoTargetIoctlResult<Microsoft::Bluetooth::Foundation::RequestBufferView<KSIDENTIFIER>,std::nullptr_t>>::GetResult(
        __int64 a1,
        _QWORD *a2)
{
  signed __int32 v4; // eax
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int32 Address; // [rsp+30h] [rbp+8h] BYREF
  int CompareAddress; // [rsp+40h] [rbp+18h] BYREF

  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), 4, 2) != 2 )
  {
    Address = 0;
    *(_QWORD *)a1 = &Address;
    v4 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), 1, 0);
    if ( v4 )
    {
      *(_QWORD *)a1 = 0;
      if ( v4 != 2 )
      {
        a2[4] = 0;
        *a2 = 0;
        a2[1] = 0;
        a2[3] = 0;
        a2[2] = 0;
        return a2;
      }
      _InterlockedExchange((volatile __int32 *)(a1 + 8), 4);
    }
    else
    {
      while ( !_InterlockedExchange(&Address, 0) )
      {
        CompareAddress = 0;
        if ( !WaitOnAddress(&Address, &CompareAddress, 4u, 0xFFFFFFFF) )
        {
          if ( GetLastError() != 1460 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xDBF,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v5);
          break;
        }
      }
    }
  }
  if ( !*(_BYTE *)(a1 + 56) )
    std::_Throw_bad_optional_access();
  *(_OWORD *)a2 = *(_OWORD *)(a1 + 16);
  *((_OWORD *)a2 + 1) = *(_OWORD *)(a1 + 32);
  a2[4] = *(_QWORD *)(a1 + 48);
  return a2;
}

```

## disassembly

```asm
0x180024c80  mov     [rsp+arg_8], rbx
0x180024c85  mov     [rsp+arg_18], rsi
0x180024c8a  push    rdi
0x180024c8b  sub     rsp, 20h
0x180024c8f  mov     rbx, rdx
0x180024c92  mov     rdi, rcx
0x180024c95  mov     esi, 4
0x180024c9a  lea     eax, [rsi-2]
0x180024c9d  lock cmpxchg [rcx+8], esi
0x180024ca2  jz      short loc_180024D07
0x180024ca4  mov     [rsp+28h+Address], 0
0x180024cac  lea     rax, [rsp+28h+Address]
0x180024cb1  mov     [rcx], rax
0x180024cb4  lea     ecx, [rsi-3]
0x180024cb7  xor     eax, eax
0x180024cb9  lock cmpxchg [rdi+8], ecx
0x180024cbe  jnz     short loc_180024CF8
0x180024cc0  xor     eax, eax
0x180024cc2  xchg    eax, [rsp+28h+Address]
0x180024cc6  test    eax, eax
0x180024cc8  jnz     short loc_180024D07
0x180024cca  mov     [rsp+28h+CompareAddress], eax
0x180024cce  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180024cd2  mov     r8, rsi; AddressSize
0x180024cd5  lea     rdx, [rsp+28h+CompareAddress]; CompareAddress
0x180024cda  lea     rcx, [rsp+28h+Address]; Address
0x180024cdf  call    cs:__imp_WaitOnAddress
0x180024ce5  test    eax, eax
0x180024ce7  jnz     short loc_180024CC0
0x180024ce9  call    cs:__imp_GetLastError
0x180024cef  cmp     eax, 5B4h
0x180024cf4  jnz     short loc_180024D56
0x180024cf6  jmp     short loc_180024D07
0x180024cf8  mov     qword ptr [rdi], 0
0x180024cff  cmp     eax, 2
0x180024d02  jnz     short loc_180024D39
0x180024d04  xchg    esi, [rdi+8]
0x180024d07  cmp     byte ptr [rdi+38h], 0
0x180024d0b  jz      short loc_180024D50
0x180024d0d  movups  xmm0, xmmword ptr [rdi+10h]
0x180024d11  movups  xmmword ptr [rbx], xmm0
0x180024d14  movups  xmm1, xmmword ptr [rdi+20h]
0x180024d18  movups  xmmword ptr [rbx+10h], xmm1
0x180024d1c  movsd   xmm0, qword ptr [rdi+30h]
0x180024d21  movsd   qword ptr [rbx+20h], xmm0
0x180024d26  mov     rax, rbx
0x180024d29  mov     rbx, [rsp+28h+arg_8]
0x180024d2e  mov     rsi, [rsp+28h+arg_18]
0x180024d33  add     rsp, 20h
0x180024d37  pop     rdi
0x180024d38  retn
0x180024d39  xor     eax, eax
0x180024d3b  mov     [rdx+20h], rax
0x180024d3f  mov     [rdx], rax
0x180024d42  mov     [rdx+8], rax
0x180024d46  mov     [rdx+18h], rax
0x180024d4a  mov     [rdx+10h], rax
0x180024d4e  jmp     short loc_180024D26
0x180024d50  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x180024d56  mov     rcx, [rsp+28h]; this
0x180024d5b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024d62  mov     edx, 0DBFh; void *
0x180024d67  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

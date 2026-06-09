# Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::operator=(Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation &&)

- ea: `0x18002abd0`
- end: `0x18002ac59`
- name: `??4RequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@QEAAAEAV012345@$$QEAV012345@@Z`
- size: `137`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002a8ec`

## callees

- `0x18002abd0`
- `0x18002acf4`
- `0x18002adb0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002abf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002abf5`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::operator=(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rbx
  __int64 *v5; // r14
  __int64 *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx

  if ( a2 != a1 )
  {
    v4 = *(_QWORD *)(a2 + 24);
    *(_QWORD *)(a2 + 24) = 0;
    WindowsDeleteString(*(HSTRING *)(a1 + 24));
    *(_QWORD *)(a1 + 24) = v4;
    v5 = (__int64 *)(a2 + 32);
    v6 = (__int64 *)(a1 + 32);
    *(_QWORD *)a1 = *(_QWORD *)a2;
    *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
    *(_BYTE *)(a1 + 16) = *(_BYTE *)(a2 + 16);
    if ( a1 + 32 != a2 + 32 )
    {
      std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::clear(a1 + 32);
      v7 = *v6;
      *v6 = *v5;
      v8 = *(_QWORD *)(a2 + 40);
      *v5 = v7;
      v9 = *(_QWORD *)(a1 + 40);
      *(_QWORD *)(a1 + 40) = v8;
      *(_QWORD *)(a2 + 40) = v9;
    }
    Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::Reset((Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *)a2);
  }
  return a1;
}

```

## disassembly

```asm
0x18002abd0  push    rbx
0x18002abd2  push    rsi
0x18002abd3  push    rdi
0x18002abd4  push    r14
0x18002abd6  sub     rsp, 28h
0x18002abda  mov     rsi, rdx
0x18002abdd  mov     rdi, rcx
0x18002abe0  cmp     rdx, rcx
0x18002abe3  jz      short loc_18002AC4C
0x18002abe5  mov     rbx, [rdx+18h]
0x18002abe9  mov     qword ptr [rdx+18h], 0
0x18002abf1  mov     rcx, [rcx+18h]; string
0x18002abf5  call    cs:__imp_WindowsDeleteString
0x18002abfb  mov     [rdi+18h], rbx
0x18002abff  lea     r14, [rsi+20h]
0x18002ac03  mov     rax, [rsi]
0x18002ac06  lea     rbx, [rdi+20h]
0x18002ac0a  mov     [rdi], rax
0x18002ac0d  mov     rax, [rsi+8]
0x18002ac11  mov     [rdi+8], rax
0x18002ac15  mov     al, [rsi+10h]
0x18002ac18  mov     [rdi+10h], al
0x18002ac1b  cmp     rbx, r14
0x18002ac1e  jz      short loc_18002AC44
0x18002ac20  mov     rcx, rbx
0x18002ac23  call    ?clear@?$list@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@V?$allocator@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAXXZ; std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::clear(void)
0x18002ac28  mov     rax, [r14]
0x18002ac2b  mov     rcx, [rbx]
0x18002ac2e  mov     [rbx], rax
0x18002ac31  mov     rax, [r14+8]
0x18002ac35  mov     [r14], rcx
0x18002ac38  mov     rcx, [rbx+8]
0x18002ac3c  mov     [rbx+8], rax
0x18002ac40  mov     [r14+8], rcx
0x18002ac44  mov     rcx, rsi; this
0x18002ac47  call    ?Reset@RequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::Reset(void)
0x18002ac4c  mov     rax, rdi
0x18002ac4f  add     rsp, 28h
0x18002ac53  pop     r14
0x18002ac55  pop     rdi
0x18002ac56  pop     rsi
0x18002ac57  pop     rbx
0x18002ac58  retn
```

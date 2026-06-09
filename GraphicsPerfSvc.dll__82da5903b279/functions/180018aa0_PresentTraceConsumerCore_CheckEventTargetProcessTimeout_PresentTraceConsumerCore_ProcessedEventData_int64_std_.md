# PresentTraceConsumerCore::CheckEventTargetProcessTimeout(PresentTraceConsumerCore::ProcessedEventData &,__int64,std::vector<std::pair<PresentTraceConsumerCore::TimeoutReason,std::shared_ptr<IPresentEventConsumer>>,std::allocator<std::pair<PresentTraceConsumerCore::TimeoutReason,std::shared_ptr<IPresentEventConsumer>>>> &)

- ea: `0x180018aa0`
- end: `0x180018b70`
- name: `?CheckEventTargetProcessTimeout@PresentTraceConsumerCore@@AEAAXAEAUProcessedEventData@1@_JAEAV?$vector@U?$pair@W4TimeoutReason@PresentTraceConsumerCore@@V?$shared_ptr@UIPresentEventConsumer@@@std@@@std@@V?$allocator@U?$pair@W4TimeoutReason@PresentTraceConsumerCore@@V?$shared_ptr@UIPresentEventConsumer@@@std@@@std@@@2@@std@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001a580`

## callees

- `0x1800175e4`
- `0x180018aa0`
- `0x180031010`

## string_xrefs

- `0x180018b2f`: `Timeout: present completed timeout.`

## pseudocode

```c
__int64 __fastcall PresentTraceConsumerCore::CheckEventTargetProcessTimeout(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 result; // rax
  _QWORD *v9; // rbp
  _QWORD *i; // r14
  _QWORD *v11; // rcx
  _QWORD *v12; // rdi
  _QWORD *j; // rbx
  int v14; // [rsp+60h] [rbp+8h] BYREF

  result = a2[1];
  if ( result != *(_QWORD *)(a1 + 200) )
  {
    *(_QWORD *)(result + 40) = a3;
    ++*(_DWORD *)(a1 + 396);
    result = a2[1];
    v9 = *(_QWORD **)(result + 64);
    for ( i = *(_QWORD **)(result + 56); i != v9; i += 2 )
      result = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*i + 112LL))(*i, *a2);
    v11 = (_QWORD *)a2[1];
    if ( v11[6] )
    {
      result = *(_QWORD *)(a1 + 112) * *(unsigned int *)(a1 + 276);
      if ( a3 - v11[6] > result )
      {
        v12 = (_QWORD *)v11[8];
        for ( j = (_QWORD *)v11[7]; j != v12; j += 2 )
        {
          (*(void (__fastcall **)(_QWORD, const wchar_t *))(*(_QWORD *)*j + 120LL))(
            *j,
            L"Timeout: present completed timeout.");
          v14 = 1;
          result = std::vector<std::pair<enum PresentTraceConsumerCore::TimeoutReason,std::shared_ptr<IPresentEventConsumer>>>::emplace_back<enum PresentTraceConsumerCore::TimeoutReason,std::shared_ptr<IPresentEventConsumer> &>(
                     a4,
                     &v14,
                     j);
        }
      }
    }
    else
    {
      v11[6] = a3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018aa0  push    rbx
0x180018aa2  push    rbp
0x180018aa3  push    rsi
0x180018aa4  push    rdi
0x180018aa5  push    r14
0x180018aa7  push    r15
0x180018aa9  sub     rsp, 28h
0x180018aad  mov     rax, [rdx+8]
0x180018ab1  mov     r15, r9
0x180018ab4  mov     rbx, r8
0x180018ab7  mov     rsi, rdx
0x180018aba  mov     rdi, rcx
0x180018abd  cmp     rax, [rcx+0C8h]
0x180018ac4  jz      loc_180018B63
0x180018aca  mov     [rax+28h], rbx
0x180018ace  inc     dword ptr [rcx+18Ch]
0x180018ad4  mov     rax, [rdx+8]
0x180018ad8  mov     rbp, [rax+40h]
0x180018adc  mov     r14, [rax+38h]
0x180018ae0  jmp     short loc_180018AF8
0x180018ae2  mov     rcx, [r14]
0x180018ae5  mov     rdx, [rsi]
0x180018ae8  mov     rax, [rcx]
0x180018aeb  mov     rax, [rax+70h]
0x180018aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018af4  add     r14, 10h
0x180018af8  cmp     r14, rbp
0x180018afb  jnz     short loc_180018AE2
0x180018afd  mov     rcx, [rsi+8]
0x180018b01  cmp     qword ptr [rcx+30h], 0
0x180018b06  jnz     short loc_180018B0E
0x180018b08  mov     [rcx+30h], rbx
0x180018b0c  jmp     short loc_180018B63
0x180018b0e  mov     eax, [rdi+114h]
0x180018b14  imul    rax, [rdi+70h]
0x180018b19  sub     rbx, [rcx+30h]
0x180018b1d  cmp     rbx, rax
0x180018b20  jle     short loc_180018B63
0x180018b22  mov     rdi, [rcx+40h]
0x180018b26  mov     rbx, [rcx+38h]
0x180018b2a  jmp     short loc_180018B5E
0x180018b2c  mov     rcx, [rbx]
0x180018b2f  lea     rdx, aTimeoutPresent; "Timeout: present completed timeout."
0x180018b36  mov     rax, [rcx]
0x180018b39  mov     rax, [rax+78h]
0x180018b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b42  mov     r8, rbx
0x180018b45  mov     [rsp+58h+arg_0], 1
0x180018b4d  lea     rdx, [rsp+58h+arg_0]
0x180018b52  mov     rcx, r15
0x180018b55  call    ??$emplace_back@W4TimeoutReason@PresentTraceConsumerCore@@AEAV?$shared_ptr@UIPresentEventConsumer@@@std@@@?$vector@U?$pair@W4TimeoutReason@PresentTraceConsumerCore@@V?$shared_ptr@UIPresentEventConsumer@@@std@@@std@@V?$allocator@U?$pair@W4TimeoutReason@PresentTraceConsumerCore@@V?$shared_ptr@UIPresentEventConsumer@@@std@@@std@@@2@@std@@QEAAAEAU?$pair@W4TimeoutReason@PresentTraceConsumerCore@@V?$shared_ptr@UIPresentEventConsumer@@@std@@@1@$$QEAW4TimeoutReason@PresentTraceConsumerCore@@AEAV?$shared_ptr@UIPresentEventConsumer@@@1@@Z; std::vector<std::pair<PresentTraceConsumerCore::TimeoutReason,std::shared_ptr<IPresentEventConsumer>>>::emplace_back<PresentTraceConsumerCore::TimeoutReason,std::shared_ptr<IPresentEventConsumer> &>(PresentTraceConsumerCore::TimeoutReason &&,std::shared_ptr<IPresentEventConsumer> &)
0x180018b5a  add     rbx, 10h
0x180018b5e  cmp     rbx, rdi
0x180018b61  jnz     short loc_180018B2C
0x180018b63  add     rsp, 28h
0x180018b67  pop     r15
0x180018b69  pop     r14
0x180018b6b  pop     rdi
0x180018b6c  pop     rsi
0x180018b6d  pop     rbp
0x180018b6e  pop     rbx
0x180018b6f  retn
```

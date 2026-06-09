# std::_Func_impl_no_alloc__lambda_4bc228a33a7adc1015eb6bff6e85dd8e__long_DiagHubCommon::AutoEvent_const_&_void___::_Do_call

- ea: `0x140009030`
- end: `0x1400090a3`
- name: `std::_Func_impl_no_alloc__lambda_4bc228a33a7adc1015eb6bff6e85dd8e__long_DiagHubCommon::AutoEvent_const_&_void___::_Do_call`
- size: `115`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x140008434`
- `0x1400086fc`
- `0x140008b1c`
- `0x140009030`

## pseudocode

```c
__int64 __fastcall std::_Func_impl_no_alloc__lambda_4bc228a33a7adc1015eb6bff6e85dd8e__long_DiagHubCommon::AutoEvent_const___void___::_Do_call(
        __int64 a1)
{
  _DWORD *v2; // rbx
  __int64 v3; // rdx
  int v4; // ebx
  _DWORD *v5; // rbx
  __int128 v7; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]

  v7 = 0;
  v8 = 0;
  v2 = *(_DWORD **)(a1 + 8);
  *v2 = CStandardCollectorService::MarshallCollectorService(*(_QWORD *)(a1 + 16), &v7);
  v4 = **(_DWORD **)(a1 + 8);
  if ( v4 >= 0 )
  {
    v5 = *(_DWORD **)(a1 + 8);
    *v5 = CStandardCollectorService::SendBytesToNamedPipe(*(_QWORD *)(a1 + 16), v3, &v7);
    v4 = **(_DWORD **)(a1 + 8);
    if ( v4 >= 0 )
      v4 = 0;
  }
  std::vector<unsigned char>::~vector<unsigned char>(&v7);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140009030  mov     [rsp+arg_8], rbx
0x140009035  push    rdi
0x140009036  sub     rsp, 40h
0x14000903a  mov     rdi, rcx
0x14000903d  xor     eax, eax
0x14000903f  xorps   xmm1, xmm1
0x140009042  movdqu  [rsp+48h+var_28], xmm1
0x140009048  mov     [rsp+48h+var_18], rax
0x14000904d  mov     rbx, [rcx+8]
0x140009051  lea     rdx, [rsp+48h+var_28]
0x140009056  mov     rcx, [rcx+10h]
0x14000905a  call    ?MarshallCollectorService@CStandardCollectorService@@AEAAJAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; CStandardCollectorService::MarshallCollectorService(std::vector<uchar> &)
0x14000905f  mov     [rbx], eax
0x140009061  mov     rax, [rdi+8]
0x140009065  mov     ebx, [rax]
0x140009067  test    ebx, ebx
0x140009069  jns     short loc_14000906D
0x14000906b  jmp     short loc_14000908C
0x14000906d  mov     rbx, rax
0x140009070  lea     r8, [rsp+48h+var_28]
0x140009075  mov     rcx, [rdi+10h]
0x140009079  call    ?SendBytesToNamedPipe@CStandardCollectorService@@AEAAJPEBGAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; CStandardCollectorService::SendBytesToNamedPipe(ushort const *,std::vector<uchar> const &)
0x14000907e  mov     [rbx], eax
0x140009080  mov     rax, [rdi+8]
0x140009084  mov     ebx, [rax]
0x140009086  test    ebx, ebx
0x140009088  js      short loc_14000908C
0x14000908a  xor     ebx, ebx
0x14000908c  lea     rcx, [rsp+48h+var_28]
0x140009091  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140009096  mov     eax, ebx
0x140009098  mov     rbx, [rsp+48h+arg_8]
0x14000909d  add     rsp, 40h
0x1400090a1  pop     rdi
0x1400090a2  retn
```

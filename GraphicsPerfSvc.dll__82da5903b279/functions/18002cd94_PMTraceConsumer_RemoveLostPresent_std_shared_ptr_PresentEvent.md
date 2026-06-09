# PMTraceConsumer::RemoveLostPresent(std::shared_ptr<PresentEvent>)

- ea: `0x18002cd94`
- end: `0x18002ceba`
- name: `?RemoveLostPresent@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@@Z`
- size: `294`
- prototype: ``
- caller_count: `9`
- callee_count: `7`
- tags: ``

## callers

- `0x180029254`
- `0x18002a8c8`
- `0x18002bc2c`
- `0x18002bd70`
- `0x18002c13c`
- `0x18002c7b0`
- `0x18002cd94`
- `0x18002d550`
- `0x18002d628`

## callees

- `0x18000d67c`
- `0x18000e3e4`
- `0x180011430`
- `0x18001c088`
- `0x180027b78`
- `0x18002cd94`
- `0x18002cec0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18002ce92`
- `msvcp_win!_Mtx_unlock` at `0x18002ce92`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PMTraceConsumer::RemoveLostPresent(_QWORD *a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  __int64 v6; // rdi
  __int64 v7; // r14
  _QWORD *v8; // rdx
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // r9
  std::_Ref_count_base *v12; // rcx
  _QWORD v13[5]; // [rsp+20h] [rbp-28h] BYREF

  v4 = *a2;
  if ( *(_BYTE *)(*a2 + 170) && *(_DWORD *)(v4 + 160) != 1 )
    *(_DWORD *)(v4 + 160) = 3;
  v5 = *a2;
  v6 = *(_QWORD *)(*a2 + 240);
  v7 = v6 + *(_QWORD *)(*a2 + 248);
  while ( v6 != v7 )
  {
    v8 = *(_QWORD **)(*(_QWORD *)(v5 + 224) + 8 * (v6 & (*(_QWORD *)(v5 + 232) - 1LL)));
    if ( !*(_BYTE *)(*v8 + 171LL) )
    {
      v9 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(v13, v8);
      PMTraceConsumer::RemoveLostPresent(a1, v9);
    }
    ++v6;
  }
  std::deque<std::shared_ptr<PresentEvent>>::_Tidy(*a2 + 216);
  PMTraceConsumer::RemovePresentFromTemporaryTrackingCollections(a1, a2);
  *(_BYTE *)(*a2 + 171) = 1;
  std::_Mutex_base::lock((std::_Mutex_base *)(a1 + 22));
  v10 = (_QWORD *)a1[33];
  if ( v10 == (_QWORD *)a1[34] )
  {
    std::vector<std::shared_ptr<PresentEvent>>::_Emplace_reallocate<std::shared_ptr<PresentEvent> const &>(
      a1 + 32,
      a1[33],
      a2);
  }
  else
  {
    std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(v10, a2);
    *(_QWORD *)(v11 + 8) += 16LL;
  }
  _Mtx_unlock((_Mtx_t)(a1 + 22));
  v12 = (std::_Ref_count_base *)a2[1];
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
}

```

## disassembly

```asm
0x18002cd94  mov     [rsp+arg_10], rbx
0x18002cd99  mov     [rsp+arg_18], rbp
0x18002cd9e  mov     [rsp+arg_8], rdx
0x18002cda3  push    rsi
0x18002cda4  push    rdi
0x18002cda5  push    r14
0x18002cda7  sub     rsp, 30h
0x18002cdab  mov     rbx, rdx
0x18002cdae  mov     rbp, rcx
0x18002cdb1  mov     rax, [rdx]
0x18002cdb4  cmp     byte ptr [rax+0AAh], 0
0x18002cdbb  jz      short loc_18002CDD0
0x18002cdbd  cmp     dword ptr [rax+0A0h], 1
0x18002cdc4  jz      short loc_18002CDD0
0x18002cdc6  mov     dword ptr [rax+0A0h], 3
0x18002cdd0  mov     rsi, [rdx]
0x18002cdd3  mov     rdi, [rsi+0F0h]
0x18002cdda  mov     r14, [rsi+0F8h]
0x18002cde1  add     r14, rdi
0x18002cde4  cmp     rdi, r14
0x18002cde7  jz      short loc_18002CE27
0x18002cde9  mov     rcx, [rsi+0E8h]
0x18002cdf0  dec     rcx
0x18002cdf3  and     rcx, rdi
0x18002cdf6  mov     rax, [rsi+0E0h]
0x18002cdfd  mov     rdx, [rax+rcx*8]
0x18002ce01  mov     rax, [rdx]
0x18002ce04  cmp     byte ptr [rax+0ABh], 0
0x18002ce0b  jnz     short loc_18002CE22
0x18002ce0d  lea     rcx, [rsp+48h+var_28]
0x18002ce12  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002ce17  mov     rdx, rax
0x18002ce1a  mov     rcx, rbp
0x18002ce1d  call    ?RemoveLostPresent@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@@Z; PMTraceConsumer::RemoveLostPresent(std::shared_ptr<PresentEvent>)
0x18002ce22  inc     rdi
0x18002ce25  jmp     short loc_18002CDE4
0x18002ce27  mov     rcx, [rbx]
0x18002ce2a  add     rcx, 0D8h
0x18002ce31  call    ?_Tidy@?$deque@V?$shared_ptr@UPresentEvent@@@std@@V?$allocator@V?$shared_ptr@UPresentEvent@@@std@@@2@@std@@AEAAXXZ; std::deque<std::shared_ptr<PresentEvent>>::_Tidy(void)
0x18002ce36  mov     rdx, rbx
0x18002ce39  mov     rcx, rbp
0x18002ce3c  call    ?RemovePresentFromTemporaryTrackingCollections@PMTraceConsumer@@QEAAXAEAV?$shared_ptr@UPresentEvent@@@std@@@Z; PMTraceConsumer::RemovePresentFromTemporaryTrackingCollections(std::shared_ptr<PresentEvent> &)
0x18002ce41  mov     rax, [rbx]
0x18002ce44  mov     byte ptr [rax+0ABh], 1
0x18002ce4b  lea     rdi, [rbp+0B0h]
0x18002ce52  mov     [rsp+48h+arg_0], rdi
0x18002ce57  mov     rcx, rdi; this
0x18002ce5a  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18002ce5f  nop
0x18002ce60  lea     r9, [rbp+100h]
0x18002ce67  mov     rcx, [r9+8]
0x18002ce6b  cmp     rcx, [r9+10h]
0x18002ce6f  jz      short loc_18002CE80
0x18002ce71  mov     rdx, rbx
0x18002ce74  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002ce79  add     qword ptr [r9+8], 10h
0x18002ce7e  jmp     short loc_18002CE8F
0x18002ce80  mov     r8, rbx
0x18002ce83  mov     rdx, rcx
0x18002ce86  mov     rcx, r9
0x18002ce89  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@UPresentEvent@@@std@@@?$vector@V?$shared_ptr@UPresentEvent@@@std@@V?$allocator@V?$shared_ptr@UPresentEvent@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@UPresentEvent@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<PresentEvent>>::_Emplace_reallocate<std::shared_ptr<PresentEvent> const &>(std::shared_ptr<PresentEvent> * const,std::shared_ptr<PresentEvent> const &)
0x18002ce8e  nop
0x18002ce8f  mov     rcx, rdi; _Mtx_t
0x18002ce92  call    cs:__imp__Mtx_unlock
0x18002ce98  nop
0x18002ce99  mov     rcx, [rbx+8]; this
0x18002ce9d  test    rcx, rcx
0x18002cea0  jz      short loc_18002CEA7
0x18002cea2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002cea7  mov     rbx, [rsp+48h+arg_10]
0x18002ceac  mov     rbp, [rsp+48h+arg_18]
0x18002ceb1  add     rsp, 30h
0x18002ceb5  pop     r14
0x18002ceb7  pop     rdi
0x18002ceb8  pop     rsi
0x18002ceb9  retn
```

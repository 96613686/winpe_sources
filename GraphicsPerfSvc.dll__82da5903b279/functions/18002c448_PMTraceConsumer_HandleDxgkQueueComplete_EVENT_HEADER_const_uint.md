# PMTraceConsumer::HandleDxgkQueueComplete(_EVENT_HEADER const &,uint)

- ea: `0x18002c448`
- end: `0x18002c536`
- name: `?HandleDxgkQueueComplete@PMTraceConsumer@@QEAAXAEBU_EVENT_HEADER@@I@Z`
- size: `238`
- prototype: `void __fastcall(PMTraceConsumer *__hidden this, const struct _EVENT_HEADER *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002a8c8`

## callees

- `0x18000d67c`
- `0x18000e3e4`
- `0x18001139c`
- `0x180029130`
- `0x18002c448`
- `0x18002de70`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PMTraceConsumer::HandleDxgkQueueComplete(PMTraceConsumer *this, const struct _EVENT_HEADER *a2, int a3)
{
  _QWORD *v5; // rbx
  __int64 v6; // rdx
  int v7; // eax
  _QWORD *v8; // rax
  __int64 v9; // [rsp+20h] [rbp-20h] BYREF
  std::_Ref_count_base *v10; // [rsp+28h] [rbp-18h]
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF
  int v13; // [rsp+70h] [rbp+30h] BYREF

  v13 = a3;
  v5 = (_QWORD *)((char *)this + 448);
  std::_Tree<std::_Tmap_traits<unsigned long,PresentTraceConsumerCore::ProcessInfo,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(
    (char *)this + 448,
    &v12,
    &v13);
  if ( v12 != *v5 )
  {
    std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v9, (_QWORD *)(v12 + 40));
    v6 = v9;
    v7 = *(_DWORD *)(v9 + 156);
    if ( v7 == 9 )
    {
      if ( *(_QWORD *)(v9 + 176) )
      {
        *(_QWORD *)(v9 + 32) = a2->TimeStamp.QuadPart;
        std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<PresentEvent>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<PresentEvent>>>,0>>::erase(
          v5,
          &v13);
      }
    }
    else if ( v7 == 2 || v7 == 1 && !*(_BYTE *)(v9 + 165) )
    {
      *(_QWORD *)(v9 + 32) = a2->TimeStamp.QuadPart;
      *(_QWORD *)(v6 + 40) = a2->TimeStamp.QuadPart;
      *(_DWORD *)(v6 + 160) = 1;
      if ( *(_BYTE *)(v6 + 166) || *(_DWORD *)(v6 + 156) != 2 )
      {
        v8 = std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(&v11, &v9);
        PMTraceConsumer::CompletePresent((__int64)this, v8);
      }
    }
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
  }
}

```

## disassembly

```asm
0x18002c448  mov     [rsp-18h+arg_8], rbx
0x18002c44d  mov     [rsp-18h+arg_10], r8d
0x18002c452  push    rbp
0x18002c453  push    rsi
0x18002c454  push    rdi
0x18002c455  mov     rbp, rsp
0x18002c458  sub     rsp, 40h
0x18002c45c  mov     rdi, rdx
0x18002c45f  mov     rsi, rcx
0x18002c462  lea     rbx, [rcx+1C0h]
0x18002c469  lea     r8, [rbp+arg_10]
0x18002c46d  lea     rdx, [rbp+arg_0]
0x18002c471  mov     rcx, rbx
0x18002c474  call    ?find@?$_Tree@V?$_Tmap_traits@KUProcessInfo@PresentTraceConsumerCore@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUProcessInfo@PresentTraceConsumerCore@@@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,PresentTraceConsumerCore::ProcessInfo,std::less<ulong>,std::allocator<std::pair<ulong const,PresentTraceConsumerCore::ProcessInfo>>,0>>::find(ulong const &)
0x18002c479  mov     rdx, [rbp+arg_0]
0x18002c47d  cmp     rdx, [rbx]
0x18002c480  jz      loc_18002C529
0x18002c486  add     rdx, 28h ; '('
0x18002c48a  lea     rcx, [rbp+var_20]
0x18002c48e  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002c493  nop
0x18002c494  mov     rdx, [rbp+var_20]
0x18002c498  mov     eax, [rdx+9Ch]
0x18002c49e  cmp     eax, 9
0x18002c4a1  jnz     short loc_18002C4C3
0x18002c4a3  cmp     qword ptr [rdx+0B0h], 0
0x18002c4ab  jz      short loc_18002C51B
0x18002c4ad  mov     rax, [rdi+10h]
0x18002c4b1  mov     [rdx+20h], rax
0x18002c4b5  lea     rdx, [rbp+arg_10]
0x18002c4b9  mov     rcx, rbx
0x18002c4bc  call    ?erase@?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UPresentEvent@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBI@Z; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<PresentEvent>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<PresentEvent>>>,0>>::erase(uint const &)
0x18002c4c1  jmp     short loc_18002C51B
0x18002c4c3  cmp     eax, 2
0x18002c4c6  jz      short loc_18002C4D6
0x18002c4c8  cmp     eax, 1
0x18002c4cb  jnz     short loc_18002C51B
0x18002c4cd  cmp     byte ptr [rdx+0A5h], 0
0x18002c4d4  jnz     short loc_18002C51B
0x18002c4d6  mov     rax, [rdi+10h]
0x18002c4da  mov     [rdx+20h], rax
0x18002c4de  mov     rax, [rdi+10h]
0x18002c4e2  mov     [rdx+28h], rax
0x18002c4e6  mov     dword ptr [rdx+0A0h], 1
0x18002c4f0  cmp     byte ptr [rdx+0A6h], 0
0x18002c4f7  jnz     short loc_18002C502
0x18002c4f9  cmp     dword ptr [rdx+9Ch], 2
0x18002c500  jz      short loc_18002C51B
0x18002c502  lea     rdx, [rbp+var_20]
0x18002c506  lea     rcx, [rbp+var_10]
0x18002c50a  call    ??0?$shared_ptr@UPresentEvent@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PresentEvent>::shared_ptr<PresentEvent>(std::shared_ptr<PresentEvent> const &)
0x18002c50f  mov     rdx, rax
0x18002c512  mov     rcx, rsi
0x18002c515  call    ?CompletePresent@PMTraceConsumer@@QEAAXV?$shared_ptr@UPresentEvent@@@std@@@Z; PMTraceConsumer::CompletePresent(std::shared_ptr<PresentEvent>)
0x18002c51a  nop
0x18002c51b  mov     rcx, [rbp+var_18]; this
0x18002c51f  test    rcx, rcx
0x18002c522  jz      short loc_18002C529
0x18002c524  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002c529  mov     rbx, [rsp+40h+arg_8]
0x18002c52e  add     rsp, 40h
0x18002c532  pop     rdi
0x18002c533  pop     rsi
0x18002c534  pop     rbp
0x18002c535  retn
```

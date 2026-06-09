# Broker::TimeBroker::OnDeleteEvent(_BR_EVENT_CALL_REASON,_BROKER *,_BROKERED_EVENT *,void *)

- ea: `0x1800159b0`
- end: `0x180015abd`
- name: `?OnDeleteEvent@TimeBroker@Broker@@CAKW4_BR_EVENT_CALL_REASON@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@PEAX@Z`
- size: `269`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003800`
- `0x180003840`
- `0x180005b30`
- `0x18000bd30`
- `0x1800131e4`
- `0x1800159b0`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnDeleteEvent(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  std::_Ref_count_base *v7; // rcx
  __int64 v9; // [rsp+38h] [rbp-20h] BYREF
  std::_Ref_count_base *v10; // [rsp+40h] [rbp-18h]
  unsigned int v11; // [rsp+68h] [rbp+10h]

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
  Broker::TimeBroker::GetInstance(&v9);
  if ( a2 && a3 && a4 )
  {
    if ( v9 )
    {
      if ( *(_QWORD *)(v9 + 192) == a2 )
      {
        v7 = (std::_Ref_count_base *)a4[1];
        if ( v7 )
          std::_Ref_count_base::_Decref(v7);
        operator delete(a4, 0x10u);
        v11 = 0;
      }
      else
      {
        v11 = 5;
      }
    }
    else
    {
      v11 = 21;
    }
  }
  else
  {
    v11 = 87;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids, v11);
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  return v11;
}

```

## disassembly

```asm
0x1800159b0  mov     [rsp+arg_0], rbx
0x1800159b5  mov     [rsp+arg_10], rsi
0x1800159ba  push    rdi
0x1800159bb  sub     rsp, 50h
0x1800159bf  mov     rbx, r9
0x1800159c2  mov     rsi, r8
0x1800159c5  mov     rdi, rdx
0x1800159c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159cf  test    byte ptr [rcx+1Ch], 1
0x1800159d3  jz      short loc_1800159F0
0x1800159d5  cmp     byte ptr [rcx+19h], 4
0x1800159d9  jb      short loc_1800159F0
0x1800159db  mov     edx, 68h ; 'h'
0x1800159e0  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x1800159e7  mov     rcx, [rcx+10h]
0x1800159eb  call    WPP_SF_
0x1800159f0  lea     rcx, [rsp+58h+var_20]
0x1800159f5  call    ?GetInstance@TimeBroker@Broker@@SA?AV?$shared_ptr@VTimeBroker@Broker@@@std@@XZ; Broker::TimeBroker::GetInstance(void)
0x1800159fa  nop
0x1800159fb  test    rdi, rdi
0x1800159fe  jz      short loc_180015A64
0x180015a00  test    rsi, rsi
0x180015a03  jz      short loc_180015A64
0x180015a05  test    rbx, rbx
0x180015a08  jz      short loc_180015A64
0x180015a0a  mov     rax, [rsp+58h+var_20]
0x180015a0f  test    rax, rax
0x180015a12  jnz     short loc_180015A1E
0x180015a14  mov     [rsp+58h+arg_8], 15h
0x180015a1c  jmp     short loc_180015A6C
0x180015a1e  cmp     [rax+0C0h], rdi
0x180015a25  jz      short loc_180015A31
0x180015a27  mov     [rsp+58h+arg_8], 5
0x180015a2f  jmp     short loc_180015A6C
0x180015a31  mov     rcx, [rbx+8]; this
0x180015a35  test    rcx, rcx
0x180015a38  jz      short loc_180015A3F
0x180015a3a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015a3f  mov     edx, 10h; unsigned __int64
0x180015a44  mov     rcx, rbx; void *
0x180015a47  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015a4c  mov     [rsp+58h+arg_8], 0
0x180015a54  jmp     short loc_180015A6C
0x180015a56  jmp     short loc_180015A6C
0x180015a58  jmp     short loc_180015A6C
0x180015a5a  jmp     short loc_180015A6C
0x180015a5c  jmp     short loc_180015A6C
0x180015a5e  jmp     short loc_180015A6C
0x180015a60  jmp     short loc_180015A6C
0x180015a62  jmp     short loc_180015A6C
0x180015a64  mov     [rsp+58h+arg_8], 57h ; 'W'
0x180015a6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a73  test    byte ptr [rcx+1Ch], 1
0x180015a77  jz      short loc_180015A9A
0x180015a79  cmp     byte ptr [rcx+19h], 4
0x180015a7d  jb      short loc_180015A9A
0x180015a7f  mov     edx, 6Bh ; 'k'
0x180015a84  mov     r9d, [rsp+58h+arg_8]
0x180015a89  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180015a90  mov     rcx, [rcx+10h]
0x180015a94  call    WPP_SF_d
0x180015a99  nop
0x180015a9a  mov     rcx, [rsp+58h+var_18]; this
0x180015a9f  test    rcx, rcx
0x180015aa2  jz      short loc_180015AA9
0x180015aa4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015aa9  mov     eax, [rsp+58h+arg_8]
0x180015aad  mov     rbx, [rsp+58h+arg_0]
0x180015ab2  mov     rsi, [rsp+58h+arg_10]
0x180015ab7  add     rsp, 50h
0x180015abb  pop     rdi
0x180015abc  retn
```

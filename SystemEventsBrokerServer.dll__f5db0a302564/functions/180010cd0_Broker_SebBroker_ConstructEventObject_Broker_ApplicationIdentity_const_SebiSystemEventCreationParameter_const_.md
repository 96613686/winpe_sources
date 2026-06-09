# Broker::SebBroker::ConstructEventObject(Broker::ApplicationIdentity const &,_SebiSystemEventCreationParameter const &,_SebiSystemEventFilterParameter const *,_BROKER *,_BROKERED_EVENT *)

- ea: `0x180010cd0`
- end: `0x180010e3f`
- name: `?ConstructEventObject@SebBroker@Broker@@AEAA?AV?$unique_ptr@VSebEvent@Broker@@U?$default_delete@VSebEvent@Broker@@@std@@@std@@AEBUApplicationIdentity@2@AEBU_SebiSystemEventCreationParameter@@PEBU_SebiSystemEventFilterParameter@@PEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z`
- size: `367`
- prototype: `__int64 *__fastcall(__int64, __int64 *, _QWORD *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010560`

## callees

- `0x180009070`
- `0x180010cd0`
- `0x18001cf74`
- `0x180027010`

## pseudocode

```c
__int64 *__fastcall Broker::SebBroker::ConstructEventObject(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  int v10; // ebp
  unsigned int v11; // r15d
  __int64 v12; // r12
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rax
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  void *v19; // [rsp+78h] [rbp-40h]
  int v21; // [rsp+D8h] [rbp+20h]
  int v22; // [rsp+E0h] [rbp+28h]

  *a2 = 0;
  v21 = *(_DWORD *)(a4 + 20);
  v10 = 0;
  v11 = 0;
  v12 = 0;
  if ( a5 )
  {
    v10 = qword_180035128[6 * *(int *)(a4 + 8)];
    v12 = *(_QWORD *)(a5 + 8);
    v11 = *(_DWORD *)(a5 + 4);
  }
  v13 = (unsigned int)(*(_DWORD *)(a4 + 8) - 14);
  v22 = 0;
  if ( (unsigned int)v13 <= 0x3D )
  {
    v14 = 0x3FD7D87934DC08D9LL;
    if ( _bittest64(&v14, v13) )
      v22 = 1;
  }
  v15 = *(_QWORD *)a4;
  v19 = operator new(0xE8u);
  v16 = Broker::SebEvent::SebEvent(
          (__int64)v19,
          a3,
          v15,
          *(_DWORD *)(a4 + 8),
          *(_DWORD *)(a4 + 12),
          v10,
          v12,
          v11,
          v21 != 0,
          *(_DWORD *)(a4 + 16),
          v22,
          a1,
          a6,
          a7);
  v17 = (void (__fastcall ***)(_QWORD, __int64))*a2;
  *a2 = v16;
  if ( v17 )
    (**v17)(v17, 1);
  return a2;
}

```

## disassembly

```asm
0x180010cd0  mov     [rsp+arg_10], rbx
0x180010cd5  mov     [rsp+arg_8], rdx
0x180010cda  mov     [rsp+arg_0], rcx
0x180010cdf  push    rbp
0x180010ce0  push    rsi
0x180010ce1  push    rdi
0x180010ce2  push    r12
0x180010ce4  push    r13
0x180010ce6  push    r14
0x180010ce8  push    r15
0x180010cea  sub     rsp, 80h
0x180010cf1  mov     r14, r9
0x180010cf4  mov     r13, r8
0x180010cf7  mov     rsi, rdx
0x180010cfa  xor     r8d, r8d
0x180010cfd  mov     [rsp+0B8h+var_48], r8d
0x180010d02  mov     [rdx], r8
0x180010d05  mov     [rsp+0B8h+var_48], 1
0x180010d0d  mov     eax, [r9+14h]
0x180010d11  mov     [rsp+0B8h+arg_18], eax
0x180010d18  mov     ebp, r8d
0x180010d1b  mov     r15d, r8d
0x180010d1e  mov     r12d, r8d
0x180010d21  mov     rdx, [rsp+0B8h+arg_20]
0x180010d29  test    rdx, rdx
0x180010d2c  jz      short loc_180010D4C
0x180010d2e  movsxd  rax, dword ptr [r9+8]
0x180010d32  lea     rcx, [rax+rax*2]
0x180010d36  add     rcx, rcx
0x180010d39  lea     rbp, qword_180035128
0x180010d40  mov     ebp, [rbp+rcx*8+0]
0x180010d44  mov     r12, [rdx+8]
0x180010d48  mov     r15d, [rdx+4]
0x180010d4c  mov     eax, [r9+8]
0x180010d50  add     eax, 0FFFFFFF2h
0x180010d53  cmp     eax, 3Dh ; '='
0x180010d56  ja      short loc_180010D75
0x180010d58  mov     rcx, 3FD7D87934DC08D9h
0x180010d62  bt      rcx, rax
0x180010d66  jnb     short loc_180010D75
0x180010d68  mov     dword ptr [rsp+0B8h+arg_20], 1
0x180010d73  jmp     short loc_180010D7D
0x180010d75  mov     dword ptr [rsp+0B8h+arg_20], r8d
0x180010d7d  mov     rbx, [r9]
0x180010d80  mov     ecx, 0E8h; Size
0x180010d85  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010d8a  mov     r10, rax
0x180010d8d  mov     [rsp+0B8h+var_40], rax
0x180010d92  xor     edx, edx
0x180010d94  cmp     [rsp+0B8h+arg_18], edx
0x180010d9b  setnz   dl
0x180010d9e  mov     rcx, [rsp+0B8h+arg_30]
0x180010da6  mov     [rsp+0B8h+var_50], rcx
0x180010dab  mov     rcx, [rsp+0B8h+arg_28]
0x180010db3  mov     [rsp+0B8h+var_58], rcx
0x180010db8  mov     rax, [rsp+0B8h+arg_0]
0x180010dc0  mov     [rsp+0B8h+var_60], rax
0x180010dc5  mov     eax, dword ptr [rsp+0B8h+arg_20]
0x180010dcc  mov     [rsp+0B8h+var_68], eax
0x180010dd0  mov     ecx, [r14+10h]
0x180010dd4  mov     [rsp+0B8h+var_70], ecx
0x180010dd8  mov     [rsp+0B8h+var_78], edx
0x180010ddc  mov     [rsp+0B8h+var_80], r15d
0x180010de1  mov     [rsp+0B8h+var_88], r12
0x180010de6  mov     [rsp+0B8h+var_90], ebp
0x180010dea  mov     eax, [r14+0Ch]
0x180010dee  mov     [rsp+0B8h+var_98], eax
0x180010df2  mov     r9d, [r14+8]
0x180010df6  mov     r8, rbx
0x180010df9  mov     rdx, r13
0x180010dfc  mov     rcx, r10
0x180010dff  call    ??0SebEvent@Broker@@QEAA@AEBUApplicationIdentity@1@U_WNF_STATE_NAME@@W4_SebiEventType@@W4_SebiTriggerType@@W4_SebiFilterType@@PEBEKHHHPEAVSebBroker@1@PEAU_BROKER@@PEAU_BROKERED_EVENT@@@Z; Broker::SebEvent::SebEvent(Broker::ApplicationIdentity const &,_WNF_STATE_NAME,_SebiEventType,_SebiTriggerType,_SebiFilterType,uchar const *,ulong,int,int,int,Broker::SebBroker *,_BROKER *,_BROKERED_EVENT *)
0x180010e04  nop
0x180010e05  mov     rcx, [rsi]
0x180010e08  mov     [rsi], rax
0x180010e0b  test    rcx, rcx
0x180010e0e  jz      short loc_180010E20
0x180010e10  mov     rax, [rcx]
0x180010e13  mov     edx, 1
0x180010e18  mov     rax, [rax]
0x180010e1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e20  mov     rax, rsi
0x180010e23  mov     rbx, [rsp+0B8h+arg_10]
0x180010e2b  add     rsp, 80h
0x180010e32  pop     r15
0x180010e34  pop     r14
0x180010e36  pop     r13
0x180010e38  pop     r12
0x180010e3a  pop     rdi
0x180010e3b  pop     rsi
0x180010e3c  pop     rbp
0x180010e3d  retn
```

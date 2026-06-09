# DeviceCommandScheduler::ProcessCtlPlaneSendCommandCompleteEvent(ulong,_WFC_MESSAGE_METADATA *,IWdiMessageMemoryManager *)

- ea: `0x14001e680`
- end: `0x14001e815`
- name: `?ProcessCtlPlaneSendCommandCompleteEvent@DeviceCommandScheduler@@IEAAXKPEAU_WFC_MESSAGE_METADATA@@PEAVIWdiMessageMemoryManager@@@Z`
- size: `405`
- prototype: `void __fastcall(DeviceCommandScheduler *__hidden this, unsigned int, struct _WFC_MESSAGE_METADATA *, struct IWdiMessageMemoryManager *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140024800`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x14001e680`
- `0x14001e81c`
- `0x140024a20`
- `0x1400dfd40`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14001e794`
- `ntoskrnl!DbgPrintEx` at `0x14001e794`

## string_xrefs

- `0x14001e789`: `HungCommand id %d finally returned, drop it\n`

## pseudocode

```c
void __fastcall DeviceCommandScheduler::ProcessCtlPlaneSendCommandCompleteEvent(
        DeviceCommandScheduler *this,
        unsigned int a2,
        struct _WFC_MESSAGE_METADATA *a3,
        struct IWdiMessageMemoryManager *a4)
{
  unsigned int v6; // ebp
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // [rsp+28h] [rbp-50h]
  int v11; // [rsp+28h] [rbp-50h]

  v6 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      27,
      (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids);
  }
  v8 = *((_QWORD *)this + 4);
  LOBYTE(a2) = 4;
  if ( *(_DWORD *)(v8 + 16)
    && (*((_DWORD *)a3 + 2) & 4) == 0
    && (++*(_DWORD *)(v8 + 24), *(_DWORD *)(*((_QWORD *)this + 4) + 20LL) == *(_DWORD *)(v8 + 24)) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_Ld(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        (_DWORD)a3,
        28,
        (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids,
        *(_DWORD *)a3,
        *((_DWORD *)a3 + 3));
    }
  }
  else if ( *(int *)(*((_QWORD *)this + 22) + 5364LL) > 0
         && (v9 = *((_DWORD *)this + 13)) != 0
         && *((_DWORD *)a3 + 10) == v9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v11 = *((_DWORD *)this + 13);
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        29,
        (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids,
        v11);
    }
    DbgPrintEx(0, 0, "HungCommand id %d finally returned, drop it\n", *((_DWORD *)this + 13));
    *((_DWORD *)this + 13) = 0;
  }
  else
  {
    DeviceCommandScheduler::CompleteSendCommand_PostHangCheck(this, v6, a3);
  }
  if ( a4 )
    (**(void (__fastcall ***)(struct IWdiMessageMemoryManager *, struct _WFC_MESSAGE_METADATA *))a4)(a4, a3);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v10) = 0;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      30,
      (__int64)WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids,
      v10);
  }
}

```

## disassembly

```asm
0x14001e680  push    rbx
0x14001e682  push    rbp
0x14001e683  push    rsi
0x14001e684  push    rdi
0x14001e685  push    r12
0x14001e687  push    r14
0x14001e689  push    r15
0x14001e68b  sub     rsp, 40h
0x14001e68f  mov     rsi, r9
0x14001e692  mov     rdi, r8
0x14001e695  mov     ebp, edx
0x14001e697  mov     rbx, rcx
0x14001e69a  lea     r15, WPP_RECORDER_INITIALIZED
0x14001e6a1  xor     r14d, r14d
0x14001e6a4  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001e6ab  lea     r12, WPP_3bb8d2971cd43c91344f8db0313028b5_Traceguids
0x14001e6b2  jz      short loc_14001E6E2
0x14001e6b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e6bb  cmp     byte ptr [rcx+29h], 5
0x14001e6bf  jnb     short loc_14001E6C8
0x14001e6c1  cmp     [rcx+48h], r14w
0x14001e6c6  jz      short loc_14001E6E2
0x14001e6c8  mov     rcx, [rcx+40h]
0x14001e6cc  mov     r9d, 1Bh
0x14001e6d2  mov     dl, 5
0x14001e6d4  mov     [rsp+78h+var_58], r12
0x14001e6d9  lea     r8d, [r9-1Ah]
0x14001e6dd  call    WPP_RECORDER_SF_
0x14001e6e2  mov     rcx, [rbx+20h]
0x14001e6e6  mov     dl, 4
0x14001e6e8  cmp     [rcx+10h], r14d
0x14001e6ec  jz      short loc_14001E73D
0x14001e6ee  mov     eax, [rdi+8]
0x14001e6f1  test    dl, al
0x14001e6f3  jnz     short loc_14001E73D
0x14001e6f5  inc     dword ptr [rcx+18h]
0x14001e6f8  mov     rax, [rbx+20h]
0x14001e6fc  mov     ecx, [rcx+18h]
0x14001e6ff  cmp     [rax+14h], ecx
0x14001e702  jnz     short loc_14001E73D
0x14001e704  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001e70b  jz      loc_14001E7B3
0x14001e711  mov     eax, [rdi+0Ch]
0x14001e714  mov     r9d, 1Ch
0x14001e71a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e721  mov     dl, 2
0x14001e723  mov     [rsp+78h+var_48], eax
0x14001e727  mov     eax, [rdi]
0x14001e729  mov     dword ptr [rsp+78h+var_50], eax
0x14001e72d  mov     rcx, [rcx+40h]
0x14001e731  mov     [rsp+78h+var_58], r12
0x14001e736  call    WPP_RECORDER_SF_Ld
0x14001e73b  jmp     short loc_14001E7B3
0x14001e73d  mov     rax, [rbx+0B0h]
0x14001e744  cmp     [rax+14F4h], r14d
0x14001e74b  jle     short loc_14001E7A6
0x14001e74d  mov     eax, [rbx+34h]
0x14001e750  test    eax, eax
0x14001e752  jz      short loc_14001E7A6
0x14001e754  cmp     [rdi+28h], eax
0x14001e757  jnz     short loc_14001E7A6
0x14001e759  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001e760  jz      short loc_14001E785
0x14001e762  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e769  mov     r9d, 1Dh
0x14001e76f  mov     dword ptr [rsp+78h+var_50], eax
0x14001e773  mov     [rsp+78h+var_58], r12
0x14001e778  mov     rcx, [rcx+40h]
0x14001e77c  lea     r8d, [r9-1Ch]
0x14001e780  call    WPP_RECORDER_SF_d
0x14001e785  mov     r9d, [rbx+34h]
0x14001e789  lea     r8, Format; "HungCommand id %d finally returned, dro"...
0x14001e790  xor     edx, edx; Level
0x14001e792  xor     ecx, ecx; ComponentId
0x14001e794  call    cs:__imp_DbgPrintEx
0x14001e79b  nop     dword ptr [rax+rax+00h]
0x14001e7a0  mov     [rbx+34h], r14d
0x14001e7a4  jmp     short loc_14001E7B3
0x14001e7a6  mov     r8, rdi; struct _WFC_MESSAGE_METADATA *
0x14001e7a9  mov     edx, ebp; unsigned int
0x14001e7ab  mov     rcx, rbx; this
0x14001e7ae  call    ?CompleteSendCommand_PostHangCheck@DeviceCommandScheduler@@IEAAXKPEAU_WFC_MESSAGE_METADATA@@@Z; DeviceCommandScheduler::CompleteSendCommand_PostHangCheck(ulong,_WFC_MESSAGE_METADATA *)
0x14001e7b3  test    rsi, rsi
0x14001e7b6  jz      short loc_14001E7C9
0x14001e7b8  mov     rax, [rsi]
0x14001e7bb  mov     rdx, rdi
0x14001e7be  mov     rcx, rsi
0x14001e7c1  mov     rax, [rax]
0x14001e7c4  call    _guard_dispatch_icall
0x14001e7c9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14001e7d0  jz      short loc_14001E805
0x14001e7d2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e7d9  cmp     byte ptr [rcx+29h], 5
0x14001e7dd  jnb     short loc_14001E7E6
0x14001e7df  cmp     [rcx+48h], r14w
0x14001e7e4  jz      short loc_14001E805
0x14001e7e6  mov     rcx, [rcx+40h]
0x14001e7ea  mov     r9d, 1Eh
0x14001e7f0  mov     dword ptr [rsp+78h+var_50], r14d
0x14001e7f5  mov     dl, 5
0x14001e7f7  mov     [rsp+78h+var_58], r12
0x14001e7fc  lea     r8d, [r9-1Dh]
0x14001e800  call    WPP_RECORDER_SF_d
0x14001e805  add     rsp, 40h
0x14001e809  pop     r15
0x14001e80b  pop     r14
0x14001e80d  pop     r12
0x14001e80f  pop     rdi
0x14001e810  pop     rsi
0x14001e811  pop     rbp
0x14001e812  pop     rbx
0x14001e813  retn
```

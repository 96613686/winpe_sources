# Broker::SystemTimer::SetTimer(__int64)

- ea: `0x18000d2a8`
- end: `0x18000d381`
- name: `?SetTimer@SystemTimer@Broker@@QEAAX_J@Z`
- size: `217`
- prototype: `void __fastcall(union _LARGE_INTEGER *this, union _LARGE_INTEGER, int, void (*)(void *, unsigned int, unsigned int))`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001c14`
- `0x180016190`

## callees

- `0x18000809c`
- `0x180008168`
- `0x18000a474`
- `0x18000b9c0`
- `0x18000d2a8`
- `0x18000e5f0`
- `0x18000ec10`

## pseudocode

```c
void __fastcall Broker::SystemTimer::SetTimer(
        union _LARGE_INTEGER *this,
        union _LARGE_INTEGER a2,
        int a3,
        void (*a4)(void *, unsigned int, unsigned int))
{
  const wchar_t *v6; // r9
  const wchar_t *v7; // r9

  this[2].QuadPart = 0x7FFFFFFFFFFFFFFFLL;
  if ( a2.QuadPart )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v6 = L"Set";
      if ( !LOBYTE(this[3].LowPart) )
        v6 = L"Not Set";
      WPP_SF_iS(*((_QWORD *)WPP_GLOBAL_Control + 2), a2.LowPart, a3, a2.LowPart, (__int64)v6);
    }
    if ( LOBYTE(this[3].LowPart) )
      Broker::SystemTimer::SetWakeEnabledTimer((Broker::SystemTimer *)this, a2);
    else
      Broker::SystemTimer::SetNonWakeEnabledTimer((void **)this, a2, a3, a4);
  }
  else
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v7 = L"Set";
      if ( !LOBYTE(this[3].LowPart) )
        v7 = L"Not Set";
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids, v7);
    }
    if ( LOBYTE(this[3].LowPart) )
      Broker::SystemTimer::ClearWakeEnabledTimer((void **)this);
    else
      Broker::SystemTimer::ClearNonWakeEnabledTimer((void **)this);
  }
  this[2] = a2;
}

```

## disassembly

```asm
0x18000d2a8  mov     [rsp+arg_0], rbx
0x18000d2ad  push    rdi
0x18000d2ae  sub     rsp, 30h
0x18000d2b2  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000d2bc  mov     rdi, rdx
0x18000d2bf  mov     [rcx+10h], rax
0x18000d2c3  mov     rbx, rcx
0x18000d2c6  test    rdx, rdx
0x18000d2c9  jz      short loc_18000D31F
0x18000d2cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2d2  test    byte ptr [rcx+1Ch], 4
0x18000d2d6  jz      short loc_18000D305
0x18000d2d8  cmp     byte ptr [rcx+19h], 5
0x18000d2dc  jb      short loc_18000D305
0x18000d2de  cmp     byte ptr [rbx+18h], 0
0x18000d2e2  lea     rax, aNotSet; "Not Set"
0x18000d2e9  mov     rcx, [rcx+10h]
0x18000d2ed  lea     r9, aSet; "Set"
0x18000d2f4  cmovz   r9, rax
0x18000d2f8  mov     [rsp+38h+var_18], r9
0x18000d2fd  mov     r9, rdx
0x18000d300  call    WPP_SF_iS
0x18000d305  cmp     byte ptr [rbx+18h], 0
0x18000d309  mov     rdx, rdi; union _LARGE_INTEGER
0x18000d30c  mov     rcx, rbx; this
0x18000d30f  jz      short loc_18000D318
0x18000d311  call    ?SetWakeEnabledTimer@SystemTimer@Broker@@AEAAXT_LARGE_INTEGER@@@Z; Broker::SystemTimer::SetWakeEnabledTimer(_LARGE_INTEGER)
0x18000d316  jmp     short loc_18000D372
0x18000d318  call    ?SetNonWakeEnabledTimer@SystemTimer@Broker@@AEAAXT_LARGE_INTEGER@@@Z; Broker::SystemTimer::SetNonWakeEnabledTimer(_LARGE_INTEGER)
0x18000d31d  jmp     short loc_18000D372
0x18000d31f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d326  test    byte ptr [rcx+1Ch], 4
0x18000d32a  jz      short loc_18000D35D
0x18000d32c  cmp     byte ptr [rcx+19h], 5
0x18000d330  jb      short loc_18000D35D
0x18000d332  cmp     byte ptr [rbx+18h], 0
0x18000d336  lea     rax, aNotSet; "Not Set"
0x18000d33d  mov     rcx, [rcx+10h]
0x18000d341  lea     r9, aSet; "Set"
0x18000d348  cmovz   r9, rax
0x18000d34c  lea     r8, WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids
0x18000d353  mov     edx, 0Dh
0x18000d358  call    WPP_SF_S
0x18000d35d  cmp     byte ptr [rbx+18h], 0
0x18000d361  mov     rcx, rbx; this
0x18000d364  jz      short loc_18000D36D
0x18000d366  call    ?ClearWakeEnabledTimer@SystemTimer@Broker@@AEAAXXZ; Broker::SystemTimer::ClearWakeEnabledTimer(void)
0x18000d36b  jmp     short loc_18000D372
0x18000d36d  call    ?ClearNonWakeEnabledTimer@SystemTimer@Broker@@AEAAXXZ; Broker::SystemTimer::ClearNonWakeEnabledTimer(void)
0x18000d372  mov     [rbx+10h], rdi
0x18000d376  mov     rbx, [rsp+38h+arg_0]
0x18000d37b  add     rsp, 30h
0x18000d37f  pop     rdi
0x18000d380  retn
```

# Broker::TimeEvent::OnDelete(void)

- ea: `0x1800087d0`
- end: `0x180008863`
- name: `?OnDelete@TimeEvent@Broker@@QEAAXXZ`
- size: `147`
- prototype: `void __fastcall(Broker::TimeEvent *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000874c`

## callees

- `0x1800087d0`
- `0x180009710`
- `0x180009f10`
- `0x180014168`

## pseudocode

```c
void __fastcall Broker::TimeEvent::OnDelete(Broker::TimeEvent *this, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, a3, *((_QWORD *)this + 31));
      v4 = WPP_GLOBAL_Control;
    }
    if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 4u )
      WPP_SF__guid_ll(v4[2], a2, a3, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 3);
  }
  if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
    McTemplateU0jqq_EventWriteTransfer((_DWORD)v4, a2, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 3);
  *((_DWORD *)this + 22) = 3;
}

```

## disassembly

```asm
0x1800087d0  push    rbx
0x1800087d2  sub     rsp, 30h
0x1800087d6  mov     rbx, rcx
0x1800087d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087e0  test    byte ptr [rcx+1Ch], 40h
0x1800087e4  jz      short loc_180008833
0x1800087e6  cmp     byte ptr [rcx+19h], 5
0x1800087ea  jb      short loc_180008808
0x1800087ec  mov     r9, [rbx+0F8h]
0x1800087f3  mov     edx, 0Eh
0x1800087f8  mov     rcx, [rcx+10h]
0x1800087fc  call    WPP_SF__guid_
0x180008801  mov     rcx, cs:WPP_GLOBAL_Control
0x180008808  test    byte ptr [rcx+1Ch], 40h
0x18000880c  jz      short loc_180008833
0x18000880e  cmp     byte ptr [rcx+19h], 4
0x180008812  jb      short loc_180008833
0x180008814  mov     eax, [rbx+58h]
0x180008817  mov     r9, [rbx+0F8h]
0x18000881e  mov     rcx, [rcx+10h]
0x180008822  mov     [rsp+38h+var_10], 3
0x18000882a  mov     [rsp+38h+var_18], eax
0x18000882e  call    WPP_SF__guid_ll
0x180008833  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x18000883a  jnz     short loc_180008849
0x18000883c  mov     dword ptr [rbx+58h], 3
0x180008843  add     rsp, 30h
0x180008847  pop     rbx
0x180008848  retn
0x180008849  mov     r9d, [rbx+58h]
0x18000884d  mov     r8, [rbx+0F8h]
0x180008854  mov     [rsp+38h+var_18], 3
0x18000885c  call    McTemplateU0jqq_EventWriteTransfer
0x180008861  jmp     short loc_18000883C
```

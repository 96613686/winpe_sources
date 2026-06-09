# Broker::TimeEvent::OnDisable(void)

- ea: `0x180009670`
- end: `0x180009702`
- name: `?OnDisable@TimeEvent@Broker@@QEAAXXZ`
- size: `146`
- prototype: `void __fastcall(Broker::TimeEvent *this, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000874c`
- `0x18000f6f0`

## callees

- `0x180009670`
- `0x180009710`
- `0x180009f10`
- `0x180014168`

## pseudocode

```c
void __fastcall Broker::TimeEvent::OnDisable(Broker::TimeEvent *this, __int64 a2, __int64 a3)
{
  _QWORD *v4; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, a3, *((_QWORD *)this + 31));
    v4 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 && *((_BYTE *)v4 + 25) >= 4u )
    WPP_SF__guid_ll(v4[2], a2, a3, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 0);
  if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
    McTemplateU0jqq_EventWriteTransfer((_DWORD)v4, a2, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 0);
  *((_DWORD *)this + 22) = 0;
}

```

## disassembly

```asm
0x180009670  mov     [rsp+arg_8], rbx
0x180009675  push    rdi
0x180009676  sub     rsp, 30h
0x18000967a  mov     rbx, rcx
0x18000967d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009684  test    byte ptr [rcx+1Ch], 40h
0x180009688  jz      short loc_1800096AC
0x18000968a  cmp     byte ptr [rcx+19h], 5
0x18000968e  jb      short loc_1800096AC
0x180009690  mov     r9, [rbx+0F8h]
0x180009697  mov     edx, 0Dh
0x18000969c  mov     rcx, [rcx+10h]
0x1800096a0  call    WPP_SF__guid_
0x1800096a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800096ac  xor     edi, edi
0x1800096ae  test    byte ptr [rcx+1Ch], 40h
0x1800096b2  jz      short loc_1800096D5
0x1800096b4  cmp     byte ptr [rcx+19h], 4
0x1800096b8  jb      short loc_1800096D5
0x1800096ba  mov     eax, [rbx+58h]
0x1800096bd  mov     r9, [rbx+0F8h]
0x1800096c4  mov     rcx, [rcx+10h]
0x1800096c8  mov     [rsp+38h+var_10], edi
0x1800096cc  mov     [rsp+38h+var_18], eax
0x1800096d0  call    WPP_SF__guid_ll
0x1800096d5  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x1800096dc  jnz     short loc_1800096EC
0x1800096de  mov     [rbx+58h], edi
0x1800096e1  mov     rbx, [rsp+38h+arg_8]
0x1800096e6  add     rsp, 30h
0x1800096ea  pop     rdi
0x1800096eb  retn
0x1800096ec  mov     r9d, [rbx+58h]
0x1800096f0  mov     r8, [rbx+0F8h]
0x1800096f7  mov     [rsp+38h+var_18], edi
0x1800096fb  call    McTemplateU0jqq_EventWriteTransfer
0x180009700  jmp     short loc_1800096DE
```

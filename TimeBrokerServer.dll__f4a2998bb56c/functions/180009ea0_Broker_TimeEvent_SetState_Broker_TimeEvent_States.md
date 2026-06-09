# Broker::TimeEvent::SetState(Broker::TimeEvent::States)

- ea: `0x180009ea0`
- end: `0x180009f0a`
- name: `?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z`
- size: `106`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009750`
- `0x18000a100`
- `0x18000a270`
- `0x18000a540`
- `0x180010490`
- `0x180016b40`
- `0x180017040`

## callees

- `0x180009ea0`
- `0x180009f10`
- `0x180014168`

## pseudocode

```c
__int64 __fastcall Broker::TimeEvent::SetState(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // edi
  int v5; // ecx
  __int64 result; // rax

  v3 = a2;
  v5 = (int)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    result = WPP_SF__guid_ll(
               *((_QWORD *)WPP_GLOBAL_Control + 2),
               a2,
               a3,
               *(_QWORD *)(a1 + 248),
               *(_DWORD *)(a1 + 88),
               a2);
  if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
    result = McTemplateU0jqq_EventWriteTransfer(v5, a2, *(_QWORD *)(a1 + 248), *(_DWORD *)(a1 + 88), v3);
  *(_DWORD *)(a1 + 88) = v3;
  return result;
}

```

## disassembly

```asm
0x180009ea0  mov     [rsp+arg_0], rbx
0x180009ea5  push    rdi
0x180009ea6  sub     rsp, 30h
0x180009eaa  mov     edi, edx
0x180009eac  mov     rbx, rcx
0x180009eaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eb6  test    byte ptr [rcx+1Ch], 40h
0x180009eba  jz      short loc_180009EDD
0x180009ebc  cmp     byte ptr [rcx+19h], 4
0x180009ec0  jb      short loc_180009EDD
0x180009ec2  mov     eax, [rbx+58h]
0x180009ec5  mov     r9, [rbx+0F8h]
0x180009ecc  mov     rcx, [rcx+10h]
0x180009ed0  mov     [rsp+38h+var_10], edx
0x180009ed4  mov     [rsp+38h+var_18], eax
0x180009ed8  call    WPP_SF__guid_ll
0x180009edd  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x180009ee4  jnz     short loc_180009EF4
0x180009ee6  mov     [rbx+58h], edi
0x180009ee9  mov     rbx, [rsp+38h+arg_0]
0x180009eee  add     rsp, 30h
0x180009ef2  pop     rdi
0x180009ef3  retn
0x180009ef4  mov     r9d, [rbx+58h]
0x180009ef8  mov     r8, [rbx+0F8h]
0x180009eff  mov     [rsp+38h+var_18], edi
0x180009f03  call    McTemplateU0jqq_EventWriteTransfer
0x180009f08  jmp     short loc_180009EE6
```

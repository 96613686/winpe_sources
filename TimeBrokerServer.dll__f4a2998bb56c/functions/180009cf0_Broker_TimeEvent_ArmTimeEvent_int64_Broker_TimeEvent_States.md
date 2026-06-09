# Broker::TimeEvent::ArmTimeEvent(__int64,Broker::TimeEvent::States)

- ea: `0x180009cf0`
- end: `0x180009e2c`
- name: `?ArmTimeEvent@TimeEvent@Broker@@IEAAX_JW4States@12@@Z`
- size: `316`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180008c70`
- `0x180009200`
- `0x18000a100`
- `0x18000a270`
- `0x180016b40`
- `0x1800181d8`

## callees

- `0x180009cf0`
- `0x180009e40`
- `0x180009f10`
- `0x180012dd0`
- `0x1800140f4`
- `0x180014168`

## pseudocode

```c
char __fastcall Broker::TimeEvent::ArmTimeEvent(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // r8
  __int64 v5; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  char result; // al
  __int64 v9; // rax
  __int128 *v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+38h] [rbp-30h] BYREF
  __int128 v15; // [rsp+40h] [rbp-28h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v3 = a2;
  *(_QWORD *)(a1 + 80) = 0;
  v5 = v2 / 2;
  v6 = a2 - v5;
  *(_QWORD *)(a1 + 24) = v6;
  *(_QWORD *)(a1 + 32) = v5 + v3;
  v7 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF__guid_ii(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v3, *(_QWORD *)(a1 + 248), v6, v5 + v3);
    v7 = WPP_GLOBAL_Control;
  }
  result = Microsoft_Windows_TimeBrokerEnableBits & 1;
  LOBYTE(v13) = Microsoft_Windows_TimeBrokerEnableBits & 1;
  if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
  {
    v9 = *(_QWORD *)(a1 + 248);
    v10 = &v15;
    v11 = *(_QWORD *)(a1 + 32);
    v12 = *(_QWORD *)(a1 + 24);
    v14 = v12;
    if ( v9 )
      LODWORD(v10) = v9;
    v13 = v11;
    v15 = 0;
    result = McTemplateU0jmm_EventWriteTransfer(v12, v11, (_DWORD)v10, (unsigned int)&v14, (__int64)&v13);
    v7 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 4u )
    result = WPP_SF__guid_ll(v7[2], v6, v3, *(_QWORD *)(a1 + 248), *(_DWORD *)(a1 + 88), 1);
  if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
    result = McTemplateU0jqq_EventWriteTransfer((_DWORD)v7, v6, *(_QWORD *)(a1 + 248), *(_DWORD *)(a1 + 88), 1);
  *(_DWORD *)(a1 + 88) = 1;
  return result;
}

```

## disassembly

```asm
0x180009cf0  push    rbx
0x180009cf2  sub     rsp, 60h
0x180009cf6  mov     rax, cs:__security_cookie
0x180009cfd  xor     rax, rsp
0x180009d00  mov     [rsp+68h+var_18], rax
0x180009d05  mov     rax, [rcx+38h]
0x180009d09  mov     r8, rdx
0x180009d0c  cqo
0x180009d0e  mov     qword ptr [rcx+50h], 0
0x180009d16  sub     rax, rdx
0x180009d19  mov     rbx, rcx
0x180009d1c  sar     rax, 1
0x180009d1f  mov     rdx, r8
0x180009d22  sub     rdx, rax
0x180009d25  mov     [rcx+18h], rdx
0x180009d29  lea     r9, [rax+r8]
0x180009d2d  mov     [rcx+20h], r9
0x180009d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d38  test    byte ptr [rcx+1Ch], 40h
0x180009d3c  jz      short loc_180009D65
0x180009d3e  cmp     byte ptr [rcx+19h], 4
0x180009d42  jb      short loc_180009D65
0x180009d44  mov     rcx, [rcx+10h]
0x180009d48  mov     [rsp+68h+var_40], r9
0x180009d4d  mov     r9, [rbx+0F8h]
0x180009d54  mov     [rsp+68h+var_48], rdx
0x180009d59  call    WPP_SF__guid_ii
0x180009d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d65  movzx   eax, cs:Microsoft_Windows_TimeBrokerEnableBits
0x180009d6c  and     al, 1
0x180009d6e  mov     byte ptr [rsp+68h+var_38], al
0x180009d72  jnz     short loc_180009DC2
0x180009d74  test    byte ptr [rcx+1Ch], 40h
0x180009d78  jz      short loc_180009D9F
0x180009d7a  cmp     byte ptr [rcx+19h], 4
0x180009d7e  jb      short loc_180009D9F
0x180009d80  mov     eax, [rbx+58h]
0x180009d83  mov     r9, [rbx+0F8h]
0x180009d8a  mov     rcx, [rcx+10h]
0x180009d8e  mov     dword ptr [rsp+68h+var_40], 1
0x180009d96  mov     dword ptr [rsp+68h+var_48], eax
0x180009d9a  call    WPP_SF__guid_ll
0x180009d9f  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x180009da6  jnz     short loc_180009E0F
0x180009da8  mov     dword ptr [rbx+58h], 1
0x180009daf  mov     rcx, [rsp+68h+var_18]
0x180009db4  xor     rcx, rsp; StackCookie
0x180009db7  call    __security_check_cookie
0x180009dbc  add     rsp, 60h
0x180009dc0  pop     rbx
0x180009dc1  retn
0x180009dc2  mov     rax, [rbx+0F8h]
0x180009dc9  lea     r8, [rsp+68h+var_28]
0x180009dce  mov     rdx, [rbx+20h]
0x180009dd2  lea     r9, [rsp+68h+var_30]
0x180009dd7  mov     rcx, [rbx+18h]
0x180009ddb  test    rax, rax
0x180009dde  xorps   xmm0, xmm0
0x180009de1  mov     [rsp+68h+var_30], rcx
0x180009de6  cmovnz  r8, rax
0x180009dea  mov     [rsp+68h+var_38], rdx
0x180009def  lea     rax, [rsp+68h+var_38]
0x180009df4  mov     [rsp+68h+var_48], rax
0x180009df9  movups  [rsp+68h+var_28], xmm0
0x180009dfe  call    McTemplateU0jmm_EventWriteTransfer
0x180009e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e0a  jmp     loc_180009D74
0x180009e0f  mov     r9d, [rbx+58h]
0x180009e13  mov     r8, [rbx+0F8h]
0x180009e1a  mov     dword ptr [rsp+68h+var_48], 1
0x180009e22  call    McTemplateU0jqq_EventWriteTransfer
0x180009e27  jmp     loc_180009DA8
```

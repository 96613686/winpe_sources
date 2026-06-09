# CxsWlanServiceNotification(void *)

- ea: `0x18000a9c0`
- end: `0x18000aa31`
- name: `?CxsWlanServiceNotification@@YAXPEAX@Z`
- size: `113`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a36c`

## callees

- `0x180002b70`
- `0x18000a1b4`
- `0x18000a540`
- `0x18000a9c0`

## pseudocode

```c
void __fastcall CxsWlanServiceNotification(_DWORD *a1)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids,
      (unsigned int)a1[8]);
  }
  if ( a1[8] == 1 )
  {
    CxsUnregisterWlanNotification((struct _GIP_WLAN_CLIENT *)(a1 - 22));
  }
  else if ( a1[8] == 4 )
  {
    CxsRegisterWlanNotification((struct _GIP_WLAN_CLIENT *)(a1 - 22));
  }
}

```

## disassembly

```asm
0x18000a9c0  mov     [rsp+arg_0], rbx
0x18000a9c5  push    rdi
0x18000a9c6  sub     rsp, 20h
0x18000a9ca  mov     rbx, rcx
0x18000a9cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9d4  lea     rax, WPP_GLOBAL_Control
0x18000a9db  cmp     rcx, rax
0x18000a9de  jz      short loc_18000AA05
0x18000a9e0  test    byte ptr [rcx+1Ch], 4
0x18000a9e4  jz      short loc_18000AA05
0x18000a9e6  cmp     byte ptr [rcx+19h], 4
0x18000a9ea  jb      short loc_18000AA05
0x18000a9ec  mov     r9d, [rbx+20h]
0x18000a9f0  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000a9f7  mov     rcx, [rcx+10h]
0x18000a9fb  mov     edx, 24h ; '$'
0x18000aa00  call    WPP_SF_D
0x18000aa05  mov     edx, [rbx+20h]
0x18000aa08  sub     edx, 1
0x18000aa0b  jz      short loc_18000AA1D
0x18000aa0d  cmp     edx, 3
0x18000aa10  jnz     short loc_18000AA26
0x18000aa12  lea     rcx, [rbx-58h]; struct _GIP_WLAN_CLIENT *
0x18000aa16  call    ?CxsRegisterWlanNotification@@YAKPEAU_GIP_WLAN_CLIENT@@@Z; CxsRegisterWlanNotification(_GIP_WLAN_CLIENT *)
0x18000aa1b  jmp     short loc_18000AA26
0x18000aa1d  lea     rcx, [rbx-58h]; struct _GIP_WLAN_CLIENT *
0x18000aa21  call    ?CxsUnregisterWlanNotification@@YAKPEAU_GIP_WLAN_CLIENT@@@Z; CxsUnregisterWlanNotification(_GIP_WLAN_CLIENT *)
0x18000aa26  mov     rbx, [rsp+28h+arg_0]
0x18000aa2b  add     rsp, 20h
0x18000aa2f  pop     rdi
0x18000aa30  retn
```

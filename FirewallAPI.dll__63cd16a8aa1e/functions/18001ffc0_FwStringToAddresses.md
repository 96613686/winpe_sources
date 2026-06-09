# FwStringToAddresses

- ea: `0x18001ffc0`
- end: `0x180020085`
- name: `FwStringToAddresses`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005954`
- `0x18001ffc0`
- `0x1800277b0`

## import_xrefs

- `fwbase!FwBaseFree` at `0x180020065`
- `fwbase!FwBaseFree` at `0x180020065`
- `fwbase!FwStringCopy` at `0x18001ffea`
- `fwbase!FwStringCopy` at `0x18001ffea`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18002001e`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18002001e`

## pseudocode

```c
__int64 __fastcall FwStringToAddresses(__int64 a1, __int64 a2)
{
  int v3; // ebx
  FwPolicy2 *v4; // rcx
  __int64 v5; // rdx
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = 0;
  v3 = FwStringCopy(a1, &v7);
  if ( v3 >= 0 )
  {
    v3 = StringToOpenPortOrAuthAppAddress(v7, a2);
    if ( v3 < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 570;
        goto LABEL_9;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 569;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, (unsigned int)v3);
    }
  }
  if ( v7 )
    FwBaseFree(v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001ffc0  mov     [rsp+arg_10], rbx
0x18001ffc5  push    rdi
0x18001ffc6  sub     rsp, 30h
0x18001ffca  mov     rax, cs:__security_cookie
0x18001ffd1  xor     rax, rsp
0x18001ffd4  mov     [rsp+38h+var_10], rax
0x18001ffd9  mov     rdi, rdx
0x18001ffdc  mov     [rsp+38h+var_18], 0
0x18001ffe5  lea     rdx, [rsp+38h+var_18]
0x18001ffea  call    cs:__imp_FwStringCopy
0x18001fff0  mov     ebx, eax
0x18001fff2  test    eax, eax
0x18001fff4  jns     short loc_180020016
0x18001fff6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fffd  lea     rax, WPP_GLOBAL_Control
0x180020004  cmp     rcx, rax
0x180020007  jz      short loc_18002005B
0x180020009  test    byte ptr [rcx+1Ch], 1
0x18002000d  jz      short loc_18002005B
0x18002000f  mov     edx, 239h
0x180020014  jmp     short loc_180020048
0x180020016  mov     rcx, [rsp+38h+var_18]
0x18002001b  mov     rdx, rdi
0x18002001e  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x180020024  mov     ebx, eax
0x180020026  test    eax, eax
0x180020028  jns     short loc_18002005B
0x18002002a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020031  lea     rax, WPP_GLOBAL_Control
0x180020038  cmp     rcx, rax
0x18002003b  jz      short loc_18002005B
0x18002003d  test    byte ptr [rcx+1Ch], 1
0x180020041  jz      short loc_18002005B
0x180020043  mov     edx, 23Ah
0x180020048  mov     rcx, [rcx+10h]
0x18002004c  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180020053  mov     r9d, ebx
0x180020056  call    WPP_SF_d
0x18002005b  mov     rcx, [rsp+38h+var_18]
0x180020060  test    rcx, rcx
0x180020063  jz      short loc_18002006B
0x180020065  call    cs:__imp_FwBaseFree
0x18002006b  mov     eax, ebx
0x18002006d  mov     rcx, [rsp+38h+var_10]
0x180020072  xor     rcx, rsp; StackCookie
0x180020075  call    __security_check_cookie
0x18002007a  mov     rbx, [rsp+38h+arg_10]
0x18002007f  add     rsp, 30h
0x180020083  pop     rdi
0x180020084  retn
```

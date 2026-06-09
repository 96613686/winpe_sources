# PluginInvokeCallback

- ea: `0x140022c20`
- end: `0x140022d4f`
- name: `PluginInvokeCallback`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x140001010`
- `0x140001044`
- `0x140006a20`
- `0x140006a60`
- `0x140022c20`

## pseudocode

```c
__int64 __fastcall PluginInvokeCallback(__int64 a1, __int64 a2, __int64 *a3)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v10; // [rsp+50h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+60h] [rbp-9h] BYREF
  __int64 v12; // [rsp+80h] [rbp+17h]
  __int64 v13; // [rsp+88h] [rbp+1Fh]
  __int64 v14; // [rsp+90h] [rbp+27h]
  __int64 v15; // [rsp+98h] [rbp+2Fh]
  __int64 *v16; // [rsp+A0h] [rbp+37h]
  __int64 v17; // [rsp+A8h] [rbp+3Fh]

  if ( *(_QWORD *)a1 != *(_QWORD *)*a3 || *(_QWORD *)(a1 + 8) != *(_QWORD *)(*a3 + 8) )
    return 0;
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int64, __int64, __int64, __int64, __int64))(a1 + 40))(
         a3[1],
         *((unsigned int *)a3 + 4),
         a3[3],
         a3[4],
         a3[5],
         a3[6],
         a3[7],
         a3[8],
         a3[9]);
  v5 = v4;
  if ( v4 >= 0 )
    return *(unsigned int *)a3[9];
  if ( (unsigned int)dword_140019000 > 4 )
  {
    if ( (unsigned __int8)tlgKeywordOn((unsigned int)dword_140019000, 0x200000000000LL) )
    {
      v12 = *a3;
      v14 = a3[1];
      v16 = &v10;
      v13 = 16;
      v15 = 16;
      v10 = v5;
      v17 = 8;
      tlgWriteTransfer_EtwWriteTransfer(v6, (unsigned __int8 *)&unk_140016028, v7, v8, 5u, &v11);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140022c20  mov     [rsp-8+arg_8], rbx
0x140022c25  mov     [rsp-8+arg_18], rdi
0x140022c2a  push    rbp
0x140022c2b  lea     rbp, [rsp-57h]
0x140022c30  sub     rsp, 0C0h
0x140022c37  mov     rax, cs:__security_cookie
0x140022c3e  xor     rax, rsp
0x140022c41  mov     [rbp+57h+var_10], rax
0x140022c45  mov     rdx, [r8]
0x140022c48  mov     rbx, r8
0x140022c4b  mov     rax, [rcx]
0x140022c4e  cmp     rax, [rdx]
0x140022c51  jnz     loc_140022D2B
0x140022c57  mov     rax, [rcx+8]
0x140022c5b  cmp     rax, [rdx+8]
0x140022c5f  jnz     loc_140022D2B
0x140022c65  mov     rax, [rcx+28h]
0x140022c69  mov     rcx, [r8+48h]
0x140022c6d  mov     r9, [r8+20h]
0x140022c71  mov     edx, [rbx+10h]
0x140022c74  mov     [rsp+0C0h+var_80], rcx
0x140022c79  mov     rcx, [r8+40h]
0x140022c7d  mov     [rsp+0C0h+var_88], rcx
0x140022c82  mov     rcx, [r8+38h]
0x140022c86  mov     [rsp+0C0h+var_90], rcx
0x140022c8b  mov     rcx, [r8+30h]
0x140022c8f  mov     [rsp+0C0h+var_98], rcx
0x140022c94  mov     rcx, [r8+28h]
0x140022c98  mov     r8, [r8+18h]
0x140022c9c  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x140022ca1  mov     rcx, [rbx+8]
0x140022ca5  call    _guard_dispatch_icall
0x140022caa  movsxd  rdi, eax
0x140022cad  test    eax, eax
0x140022caf  jns     short loc_140022D23
0x140022cb1  mov     ecx, cs:dword_140019000
0x140022cb7  cmp     ecx, 4
0x140022cba  jbe     short loc_140022D1F
0x140022cbc  mov     rdx, 200000000000h
0x140022cc6  call    _tlgKeywordOn
0x140022ccb  test    al, al
0x140022ccd  jz      short loc_140022D1F
0x140022ccf  mov     rax, [rbx]
0x140022cd2  lea     rdx, unk_140016028; int
0x140022cd9  mov     [rbp+57h+var_40], rax
0x140022cdd  mov     rax, [rbx+8]
0x140022ce1  mov     [rbp+57h+var_30], rax
0x140022ce5  lea     rax, [rbp+57h+var_70]
0x140022ce9  mov     [rbp+57h+var_20], rax
0x140022ced  lea     rax, [rbp+57h+var_60]
0x140022cf1  mov     [rsp+0C0h+var_98], rax; __int64
0x140022cf6  mov     [rsp+0C0h+var_A0], 5; ULONG
0x140022cfe  mov     [rbp+57h+var_38], 10h
0x140022d06  mov     [rbp+57h+var_28], 10h
0x140022d0e  mov     [rbp+57h+var_70], rdi
0x140022d12  mov     [rbp+57h+var_18], 8
0x140022d1a  call    _tlgWriteTransfer_EtwWriteTransfer
0x140022d1f  mov     eax, edi
0x140022d21  jmp     short loc_140022D2D
0x140022d23  mov     rax, [rbx+48h]
0x140022d27  mov     eax, [rax]
0x140022d29  jmp     short loc_140022D2D
0x140022d2b  xor     eax, eax
0x140022d2d  mov     rcx, [rbp+57h+var_10]
0x140022d31  xor     rcx, rsp; StackCookie
0x140022d34  call    __security_check_cookie
0x140022d39  lea     r11, [rsp+0C0h+var_s0]
0x140022d41  mov     rbx, [r11+18h]
0x140022d45  mov     rdi, [r11+28h]
0x140022d49  mov     rsp, r11
0x140022d4c  pop     rbp
0x140022d4d  retn
```

# Broker::SebEvent::Dump(unsigned __int64)

- ea: `0x180019c1c`
- end: `0x180019da6`
- name: `?Dump@SebEvent@Broker@@QEAAX_K@Z`
- size: `394`
- prototype: `void __fastcall(Broker::SebEvent *this, TRACEHANDLE)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800198e0`

## callees

- `0x1800016c4`
- `0x1800030e0`
- `0x180003950`
- `0x180005a50`
- `0x180008c00`
- `0x180019c1c`
- `0x18001f36c`

## pseudocode

```c
void __fastcall Broker::SebEvent::Dump(Broker::SebEvent *this, TRACEHANDLE a2)
{
  __int64 v2; // rbx
  int v4; // eax
  BOOL v6; // ebp
  _QWORD *v7; // r9
  _QWORD *v8; // r9

  v2 = *(_QWORD *)((char *)this + 124);
  v4 = *((_DWORD *)this + 33);
  v6 = v4 && v4 != 3;
  WPP_SF__guid_(a2, 37, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((_QWORD *)this + 28));
  WPP_SF__sid_(a2);
  if ( *((_QWORD *)this + 10) )
  {
    v7 = (_QWORD *)((char *)this + 64);
    if ( *((_QWORD *)this + 11) > 7u )
      v7 = (_QWORD *)*v7;
    WPP_SF_S(a2, 39, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, v7);
  }
  else
  {
    WPP_SF_(a2, 40, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids);
  }
  if ( *((_QWORD *)this + 6) )
  {
    v8 = (_QWORD *)((char *)this + 32);
    if ( *((_QWORD *)this + 7) > 7u )
      v8 = (_QWORD *)*v8;
    WPP_SF_S(a2, 41, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, v8);
  }
  else
  {
    WPP_SF_(a2, 42, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids);
  }
  WPP_SF_d(a2, 43, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((unsigned int *)this + 24));
  WPP_SF_d(a2, 44, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((unsigned int *)this + 25));
  WPP_SF_DD(a2, 45, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, (unsigned int)v2, HIDWORD(v2));
  WPP_SF_d(a2, 46, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((unsigned int *)this + 34));
  WPP_SF_d(a2, 47, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((unsigned int *)this + 30));
  if ( *((_DWORD *)this + 25) == 1 )
    WPP_SF_d(a2, 48, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, *((unsigned __int8 *)this + 168));
  WPP_SF_d(a2, 49, &WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids, v6);
}

```

## disassembly

```asm
0x180019c1c  mov     [rsp+arg_8], rbx
0x180019c21  mov     [rsp+arg_10], rbp
0x180019c26  push    rsi
0x180019c27  push    rdi
0x180019c28  push    r14
0x180019c2a  sub     rsp, 30h
0x180019c2e  mov     rbx, [rcx+7Ch]
0x180019c32  mov     rsi, rdx
0x180019c35  mov     eax, [rcx+84h]
0x180019c3b  mov     rdi, rcx
0x180019c3e  mov     [rsp+48h+arg_0], rbx
0x180019c43  test    eax, eax
0x180019c45  jz      short loc_180019C53
0x180019c47  cmp     eax, 3
0x180019c4a  jz      short loc_180019C53
0x180019c4c  mov     ebp, 1
0x180019c51  jmp     short loc_180019C55
0x180019c53  xor     ebp, ebp
0x180019c55  mov     r9, [rcx+0E0h]
0x180019c5c  lea     r14, WPP_9df6945760b0344b8172a1c9d53360ec_Traceguids
0x180019c63  mov     r8, r14
0x180019c66  mov     edx, 25h ; '%'
0x180019c6b  mov     rcx, rsi
0x180019c6e  call    WPP_SF__guid_
0x180019c73  mov     r9, [rdi+8]
0x180019c77  mov     edx, 26h ; '&'
0x180019c7c  mov     r8, r14
0x180019c7f  mov     rcx, rsi; LoggerHandle
0x180019c82  call    WPP_SF__sid_
0x180019c87  cmp     qword ptr [rdi+50h], 0
0x180019c8c  jz      short loc_180019CAE
0x180019c8e  lea     r9, [rdi+40h]
0x180019c92  cmp     qword ptr [r9+18h], 7
0x180019c97  jbe     short loc_180019C9C
0x180019c99  mov     r9, [r9]
0x180019c9c  mov     edx, 27h ; '''
0x180019ca1  mov     r8, r14
0x180019ca4  mov     rcx, rsi
0x180019ca7  call    WPP_SF_S
0x180019cac  jmp     short loc_180019CBE
0x180019cae  mov     edx, 28h ; '('
0x180019cb3  mov     r8, r14
0x180019cb6  mov     rcx, rsi
0x180019cb9  call    WPP_SF_
0x180019cbe  cmp     qword ptr [rdi+30h], 0
0x180019cc3  jz      short loc_180019CE5
0x180019cc5  lea     r9, [rdi+20h]
0x180019cc9  cmp     qword ptr [r9+18h], 7
0x180019cce  jbe     short loc_180019CD3
0x180019cd0  mov     r9, [r9]
0x180019cd3  mov     edx, 29h ; ')'
0x180019cd8  mov     r8, r14
0x180019cdb  mov     rcx, rsi
0x180019cde  call    WPP_SF_S
0x180019ce3  jmp     short loc_180019CF5
0x180019ce5  mov     edx, 2Ah ; '*'
0x180019cea  mov     r8, r14
0x180019ced  mov     rcx, rsi
0x180019cf0  call    WPP_SF_
0x180019cf5  mov     r9d, [rdi+60h]
0x180019cf9  mov     edx, 2Bh ; '+'
0x180019cfe  mov     r8, r14
0x180019d01  mov     rcx, rsi
0x180019d04  call    WPP_SF_d
0x180019d09  mov     r9d, [rdi+64h]
0x180019d0d  mov     edx, 2Ch ; ','
0x180019d12  mov     r8, r14
0x180019d15  mov     rcx, rsi
0x180019d18  call    WPP_SF_d
0x180019d1d  mov     eax, dword ptr [rsp+48h+arg_0+4]
0x180019d21  mov     edx, 2Dh ; '-'
0x180019d26  mov     r9d, ebx
0x180019d29  mov     [rsp+48h+var_28], eax
0x180019d2d  mov     r8, r14
0x180019d30  mov     rcx, rsi
0x180019d33  call    WPP_SF_DD
0x180019d38  mov     r9d, [rdi+88h]
0x180019d3f  mov     edx, 2Eh ; '.'
0x180019d44  mov     r8, r14
0x180019d47  mov     rcx, rsi
0x180019d4a  call    WPP_SF_d
0x180019d4f  mov     r9d, [rdi+78h]
0x180019d53  mov     edx, 2Fh ; '/'
0x180019d58  mov     r8, r14
0x180019d5b  mov     rcx, rsi
0x180019d5e  call    WPP_SF_d
0x180019d63  cmp     dword ptr [rdi+64h], 1
0x180019d67  jnz     short loc_180019D81
0x180019d69  movzx   r9d, byte ptr [rdi+0A8h]
0x180019d71  mov     edx, 30h ; '0'
0x180019d76  mov     r8, r14
0x180019d79  mov     rcx, rsi
0x180019d7c  call    WPP_SF_d
0x180019d81  mov     edx, 31h ; '1'
0x180019d86  mov     r9d, ebp
0x180019d89  mov     r8, r14
0x180019d8c  mov     rcx, rsi
0x180019d8f  mov     rbx, [rsp+48h+arg_8]
0x180019d94  mov     rbp, [rsp+48h+arg_10]
0x180019d99  add     rsp, 30h
0x180019d9d  pop     r14
0x180019d9f  pop     rdi
0x180019da0  pop     rsi
0x180019da1  jmp     WPP_SF_d
```

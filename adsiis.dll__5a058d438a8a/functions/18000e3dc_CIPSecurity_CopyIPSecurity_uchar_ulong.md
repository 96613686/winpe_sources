# CIPSecurity::CopyIPSecurity(uchar * *,ulong *)

- ea: `0x18000e3dc`
- end: `0x18000e488`
- name: `?CopyIPSecurity@CIPSecurity@@QEAAJPEAPEAEPEAK@Z`
- size: `172`
- prototype: `__int64 __fastcall(CIPSecurity *__hidden this, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180018f20`

## callees

- `0x18000e3dc`
- `0x18001c5f0`
- `0x18001cce0`
- `0x18001cd14`
- `0x18001cfcc`

## pseudocode

```c
__int64 __fastcall CIPSecurity::CopyIPSecurity(CIPSecurity *this, unsigned __int8 **a2, unsigned int *a3)
{
  ADDRESS_CHECK *v4; // rbx
  unsigned __int8 *v7; // rdx
  __int64 v8; // rax
  ADDRESS_CHECK *v9; // rcx
  unsigned int v10; // r8d
  int v11; // r9d
  int v12; // r10d
  int v14; // [rsp+50h] [rbp+8h] BYREF
  int v15; // [rsp+58h] [rbp+10h] BYREF

  v4 = (CIPSecurity *)((char *)this + 24);
  ADDRESS_CHECK::DeleteAllAddr((CIPSecurity *)((char *)this + 24), *((_DWORD *)this + 58));
  ADDRESS_CHECK::DeleteAllName(v4, *((_DWORD *)this + 58));
  if ( !*((_DWORD *)this + 58) )
  {
    v7 = *(unsigned __int8 **)v4;
    if ( !*(_QWORD *)v4 || (v8 = *((unsigned int *)v7 + 1), LODWORD(v8) = v8 & 0x7FFFFFFF, !*(_DWORD *)&v7[v8 + 4]) )
    {
      if ( !ADDRESS_CHECK::GetNbName(v4, 1) )
      {
        v14 = v11;
        v15 = -1;
        ADDRESS_CHECK::AddAddr(v9, v12, v10, (unsigned __int8 *)&v15, (unsigned __int8 *)&v14);
      }
    }
  }
  *a2 = *(unsigned __int8 **)v4;
  *a3 = *((_DWORD *)this + 9);
  return 0;
}

```

## disassembly

```asm
0x18000e3dc  mov     [rsp+arg_10], rbx
0x18000e3e1  push    rsi
0x18000e3e2  push    rdi
0x18000e3e3  push    r14
0x18000e3e5  sub     rsp, 30h
0x18000e3e9  mov     r14, rdx
0x18000e3ec  lea     rbx, [rcx+18h]
0x18000e3f0  mov     edx, [rcx+0E8h]; int
0x18000e3f6  mov     rdi, rcx
0x18000e3f9  mov     rcx, rbx; this
0x18000e3fc  mov     rsi, r8
0x18000e3ff  call    ?DeleteAllAddr@ADDRESS_CHECK@@QEAAHH@Z; ADDRESS_CHECK::DeleteAllAddr(int)
0x18000e404  mov     edx, [rdi+0E8h]; int
0x18000e40a  mov     rcx, rbx; this
0x18000e40d  call    ?DeleteAllName@ADDRESS_CHECK@@QEAAHH@Z; ADDRESS_CHECK::DeleteAllName(int)
0x18000e412  xor     r9d, r9d
0x18000e415  cmp     [rdi+0E8h], r9d
0x18000e41c  jnz     short loc_18000E46D
0x18000e41e  mov     rdx, [rbx]
0x18000e421  test    rdx, rdx
0x18000e424  jz      short loc_18000E434
0x18000e426  mov     eax, [rdx+4]
0x18000e429  btr     eax, 1Fh
0x18000e42d  cmp     [rax+rdx+4], r9d
0x18000e432  jnz     short loc_18000E46D
0x18000e434  mov     r10d, 1
0x18000e43a  mov     rcx, rbx; this
0x18000e43d  mov     edx, r10d; int
0x18000e440  call    ?GetNbName@ADDRESS_CHECK@@QEAAKH@Z; ADDRESS_CHECK::GetNbName(int)
0x18000e445  test    eax, eax
0x18000e447  jnz     short loc_18000E46D
0x18000e449  mov     [rsp+48h+arg_0], r9d
0x18000e44e  lea     rax, [rsp+48h+arg_0]
0x18000e453  lea     r9, [rsp+48h+arg_8]; unsigned __int8 *
0x18000e458  mov     [rsp+48h+var_28], rax; unsigned __int8 *
0x18000e45d  mov     edx, r10d; int
0x18000e460  mov     [rsp+48h+arg_8], 0FFFFFFFFh
0x18000e468  call    ?AddAddr@ADDRESS_CHECK@@QEAAHHKPEAE0@Z; ADDRESS_CHECK::AddAddr(int,ulong,uchar *,uchar *)
0x18000e46d  mov     rax, [rbx]
0x18000e470  mov     rbx, [rsp+48h+arg_10]
0x18000e475  mov     [r14], rax
0x18000e478  mov     eax, [rdi+24h]
0x18000e47b  mov     [rsi], eax
0x18000e47d  xor     eax, eax
0x18000e47f  add     rsp, 30h
0x18000e483  pop     r14
0x18000e485  pop     rdi
0x18000e486  pop     rsi
0x18000e487  retn
```

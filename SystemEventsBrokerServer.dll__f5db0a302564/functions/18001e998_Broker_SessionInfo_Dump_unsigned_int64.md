# Broker::_SessionInfo::Dump(unsigned __int64)

- ea: `0x18001e998`
- end: `0x18001ea67`
- name: `?Dump@_SessionInfo@Broker@@QEAAX_K@Z`
- size: `207`
- prototype: `void __fastcall(Broker::_SessionInfo *this, TRACEHANDLE)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800198e0`

## callees

- `0x1800030e0`
- `0x180003950`
- `0x18001f36c`

## pseudocode

```c
void __fastcall Broker::_SessionInfo::Dump(Broker::_SessionInfo *this, TRACEHANDLE a2)
{
  WPP_SF__sid_(a2);
  WPP_SF_d(a2, 106, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, *((unsigned __int8 *)this + 16));
  WPP_SF_d(a2, 107, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, *((unsigned __int8 *)this + 18));
  WPP_SF_d(a2, 108, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, *((unsigned __int8 *)this + 17));
  WPP_SF_DD(
    a2,
    109,
    &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
    *((unsigned int *)this + 16),
    *((_DWORD *)this + 17));
  WPP_SF_DD(
    a2,
    110,
    &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
    *((unsigned int *)this + 18),
    *((_DWORD *)this + 19));
  WPP_SF_DD(
    a2,
    111,
    &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids,
    *((unsigned int *)this + 20),
    *((_DWORD *)this + 21));
}

```

## disassembly

```asm
0x18001e998  mov     [rsp+arg_0], rbx
0x18001e99d  mov     [rsp+arg_8], rsi
0x18001e9a2  push    rdi
0x18001e9a3  sub     rsp, 30h
0x18001e9a7  mov     rdi, rdx
0x18001e9aa  mov     rbx, rcx
0x18001e9ad  mov     r9, [rcx]
0x18001e9b0  lea     rsi, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001e9b7  mov     r8, rsi
0x18001e9ba  mov     edx, 69h ; 'i'
0x18001e9bf  mov     rcx, rdi; LoggerHandle
0x18001e9c2  call    WPP_SF__sid_
0x18001e9c7  movzx   r9d, byte ptr [rbx+10h]
0x18001e9cc  mov     edx, 6Ah ; 'j'
0x18001e9d1  mov     r8, rsi
0x18001e9d4  mov     rcx, rdi
0x18001e9d7  call    WPP_SF_d
0x18001e9dc  movzx   r9d, byte ptr [rbx+12h]
0x18001e9e1  mov     edx, 6Bh ; 'k'
0x18001e9e6  mov     r8, rsi
0x18001e9e9  mov     rcx, rdi
0x18001e9ec  call    WPP_SF_d
0x18001e9f1  movzx   r9d, byte ptr [rbx+11h]
0x18001e9f6  mov     edx, 6Ch ; 'l'
0x18001e9fb  mov     r8, rsi
0x18001e9fe  mov     rcx, rdi
0x18001ea01  call    WPP_SF_d
0x18001ea06  mov     eax, [rbx+44h]
0x18001ea09  mov     edx, 6Dh ; 'm'
0x18001ea0e  mov     r9d, [rbx+40h]
0x18001ea12  mov     r8, rsi
0x18001ea15  mov     rcx, rdi
0x18001ea18  mov     [rsp+38h+var_18], eax
0x18001ea1c  call    WPP_SF_DD
0x18001ea21  mov     eax, [rbx+4Ch]
0x18001ea24  mov     edx, 6Eh ; 'n'
0x18001ea29  mov     r9d, [rbx+48h]
0x18001ea2d  mov     r8, rsi
0x18001ea30  mov     rcx, rdi
0x18001ea33  mov     [rsp+38h+var_18], eax
0x18001ea37  call    WPP_SF_DD
0x18001ea3c  mov     eax, [rbx+54h]
0x18001ea3f  mov     edx, 6Fh ; 'o'
0x18001ea44  mov     r9d, [rbx+50h]
0x18001ea48  mov     r8, rsi
0x18001ea4b  mov     rcx, rdi
0x18001ea4e  mov     [rsp+38h+var_18], eax
0x18001ea52  call    WPP_SF_DD
0x18001ea57  mov     rbx, [rsp+38h+arg_0]
0x18001ea5c  mov     rsi, [rsp+38h+arg_8]
0x18001ea61  add     rsp, 30h
0x18001ea65  pop     rdi
0x18001ea66  retn
```

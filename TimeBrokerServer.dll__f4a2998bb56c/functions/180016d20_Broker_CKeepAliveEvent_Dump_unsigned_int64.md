# Broker::CKeepAliveEvent::Dump(unsigned __int64)

- ea: `0x180016d20`
- end: `0x180016e63`
- name: `?Dump@CKeepAliveEvent@Broker@@UEAAX_K@Z`
- size: `323`
- prototype: `void __fastcall(Broker::CKeepAliveEvent *this, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180009f70`
- `0x180009fc0`
- `0x18000e5f0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Broker::CKeepAliveEvent::Dump(Broker::CKeepAliveEvent *this, __int64 a2)
{
  char v4; // al

  WPP_SF_DD(
    a2,
    37,
    &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
    *(_QWORD *)(*((_QWORD *)this + 31) + 16LL),
    HIDWORD(*(_QWORD *)(*((_QWORD *)this + 31) + 16LL)));
  WPP_SF_S(a2, 38, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, *(_QWORD *)(*((_QWORD *)this + 31) + 24LL));
  WPP_SF_d(a2, 39, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, *((unsigned int *)this + 18));
  WPP_SF_i(a2, 40, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, *((_QWORD *)this + 8) / 10000000LL);
  WPP_SF_i(a2, 41, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, *((_QWORD *)this + 3));
  WPP_SF_i(a2, 42, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, *((_QWORD *)this + 4));
  v4 = (*(__int64 (__fastcall **)(Broker::CKeepAliveEvent *))(*(_QWORD *)this + 48LL))(this);
  WPP_SF_d(a2, 43, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, v4 != 0);
  WPP_SF_i(a2, 44, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, *((_QWORD *)this + 7) / 10000000LL);
  WPP_SF_d(a2, 45, &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids, *((_BYTE *)this + 314) != 0);
}

```

## disassembly

```asm
0x180016d20  push    rbx
0x180016d22  push    rbp
0x180016d23  push    rsi
0x180016d24  push    rdi
0x180016d25  sub     rsp, 38h
0x180016d29  mov     r9, [rcx+0F8h]
0x180016d30  mov     rdi, rdx
0x180016d33  mov     rbx, rcx
0x180016d36  mov     r9, [r9+10h]
0x180016d3a  mov     rax, r9
0x180016d3d  lea     rbp, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180016d44  shr     rax, 20h
0x180016d48  mov     edx, 25h ; '%'
0x180016d4d  mov     r8, rbp
0x180016d50  mov     [rsp+58h+var_38], eax
0x180016d54  mov     rcx, rdi
0x180016d57  call    WPP_SF_DD
0x180016d5c  mov     r9, [rbx+0F8h]
0x180016d63  mov     edx, 26h ; '&'
0x180016d68  mov     r8, rbp
0x180016d6b  mov     rcx, rdi
0x180016d6e  mov     r9, [r9+18h]
0x180016d72  call    WPP_SF_S
0x180016d77  mov     r9d, [rbx+48h]
0x180016d7b  mov     edx, 27h ; '''
0x180016d80  mov     r8, rbp
0x180016d83  mov     rcx, rdi
0x180016d86  call    WPP_SF_d
0x180016d8b  mov     rsi, 0D6BF94D5E57A42BDh
0x180016d95  mov     r8, rbp
0x180016d98  mov     rax, rsi
0x180016d9b  mov     rcx, rdi
0x180016d9e  imul    qword ptr [rbx+40h]
0x180016da2  mov     r9, rdx
0x180016da5  mov     edx, 28h ; '('
0x180016daa  add     r9, [rbx+40h]
0x180016dae  sar     r9, 17h
0x180016db2  mov     rax, r9
0x180016db5  shr     rax, 3Fh
0x180016db9  add     r9, rax
0x180016dbc  call    WPP_SF_i
0x180016dc1  mov     r9, [rbx+18h]
0x180016dc5  mov     edx, 29h ; ')'
0x180016dca  mov     r8, rbp
0x180016dcd  mov     rcx, rdi
0x180016dd0  call    WPP_SF_i
0x180016dd5  mov     r9, [rbx+20h]
0x180016dd9  mov     edx, 2Ah ; '*'
0x180016dde  mov     r8, rbp
0x180016de1  mov     rcx, rdi
0x180016de4  call    WPP_SF_i
0x180016de9  mov     rax, [rbx]
0x180016dec  mov     rcx, rbx
0x180016def  mov     rax, [rax+30h]
0x180016df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016df8  xor     r9d, r9d
0x180016dfb  mov     edx, 2Bh ; '+'
0x180016e00  test    al, al
0x180016e02  mov     r8, rbp
0x180016e05  mov     rcx, rdi
0x180016e08  setnz   r9b
0x180016e0c  call    WPP_SF_d
0x180016e11  mov     rax, rsi
0x180016e14  mov     r8, rbp
0x180016e17  imul    qword ptr [rbx+38h]
0x180016e1b  mov     rcx, rdi
0x180016e1e  mov     r9, rdx
0x180016e21  mov     edx, 2Ch ; ','
0x180016e26  add     r9, [rbx+38h]
0x180016e2a  sar     r9, 17h
0x180016e2e  mov     rax, r9
0x180016e31  shr     rax, 3Fh
0x180016e35  add     r9, rax
0x180016e38  call    WPP_SF_i
0x180016e3d  xor     r9d, r9d
0x180016e40  mov     edx, 2Dh ; '-'
0x180016e45  cmp     [rbx+13Ah], r9b
0x180016e4c  mov     r8, rbp
0x180016e4f  mov     rcx, rdi
0x180016e52  setnz   r9b
0x180016e56  add     rsp, 38h
0x180016e5a  pop     rdi
0x180016e5b  pop     rsi
0x180016e5c  pop     rbp
0x180016e5d  pop     rbx
0x180016e5e  jmp     WPP_SF_d
```

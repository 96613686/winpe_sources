# Broker::CAlarmTimeEvent::Dump(unsigned __int64)

- ea: `0x180017b90`
- end: `0x180017cd3`
- name: `?Dump@CAlarmTimeEvent@Broker@@UEAAX_K@Z`
- size: `323`
- prototype: `void __fastcall(Broker::CAlarmTimeEvent *this, __int64)`
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
void __fastcall Broker::CAlarmTimeEvent::Dump(Broker::CAlarmTimeEvent *this, __int64 a2)
{
  char v4; // al

  WPP_SF_DD(
    a2,
    29,
    &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
    *(_QWORD *)(*((_QWORD *)this + 31) + 16LL),
    HIDWORD(*(_QWORD *)(*((_QWORD *)this + 31) + 16LL)));
  WPP_SF_S(a2, 30, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, *(_QWORD *)(*((_QWORD *)this + 31) + 24LL));
  WPP_SF_d(a2, 31, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, *((unsigned int *)this + 18));
  WPP_SF_i(a2, 32, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, *((_QWORD *)this + 8) / 10000000LL);
  WPP_SF_i(a2, 33, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, *((_QWORD *)this + 3));
  WPP_SF_i(a2, 34, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, *((_QWORD *)this + 4));
  v4 = (*(__int64 (__fastcall **)(Broker::CAlarmTimeEvent *))(*(_QWORD *)this + 48LL))(this);
  WPP_SF_d(a2, 35, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, v4 != 0);
  WPP_SF_i(a2, 36, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, *((_QWORD *)this + 7) / 10000000LL);
  WPP_SF_d(a2, 37, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, *((_BYTE *)this + 321) != 0);
}

```

## disassembly

```asm
0x180017b90  push    rbx
0x180017b92  push    rbp
0x180017b93  push    rsi
0x180017b94  push    rdi
0x180017b95  sub     rsp, 38h
0x180017b99  mov     r9, [rcx+0F8h]
0x180017ba0  mov     rdi, rdx
0x180017ba3  mov     rbx, rcx
0x180017ba6  mov     r9, [r9+10h]
0x180017baa  mov     rax, r9
0x180017bad  lea     rbp, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x180017bb4  shr     rax, 20h
0x180017bb8  mov     edx, 1Dh
0x180017bbd  mov     r8, rbp
0x180017bc0  mov     [rsp+58h+var_38], eax
0x180017bc4  mov     rcx, rdi
0x180017bc7  call    WPP_SF_DD
0x180017bcc  mov     r9, [rbx+0F8h]
0x180017bd3  mov     edx, 1Eh
0x180017bd8  mov     r8, rbp
0x180017bdb  mov     rcx, rdi
0x180017bde  mov     r9, [r9+18h]
0x180017be2  call    WPP_SF_S
0x180017be7  mov     r9d, [rbx+48h]
0x180017beb  mov     edx, 1Fh
0x180017bf0  mov     r8, rbp
0x180017bf3  mov     rcx, rdi
0x180017bf6  call    WPP_SF_d
0x180017bfb  mov     rsi, 0D6BF94D5E57A42BDh
0x180017c05  mov     r8, rbp
0x180017c08  mov     rax, rsi
0x180017c0b  mov     rcx, rdi
0x180017c0e  imul    qword ptr [rbx+40h]
0x180017c12  mov     r9, rdx
0x180017c15  mov     edx, 20h ; ' '
0x180017c1a  add     r9, [rbx+40h]
0x180017c1e  sar     r9, 17h
0x180017c22  mov     rax, r9
0x180017c25  shr     rax, 3Fh
0x180017c29  add     r9, rax
0x180017c2c  call    WPP_SF_i
0x180017c31  mov     r9, [rbx+18h]
0x180017c35  mov     edx, 21h ; '!'
0x180017c3a  mov     r8, rbp
0x180017c3d  mov     rcx, rdi
0x180017c40  call    WPP_SF_i
0x180017c45  mov     r9, [rbx+20h]
0x180017c49  mov     edx, 22h ; '"'
0x180017c4e  mov     r8, rbp
0x180017c51  mov     rcx, rdi
0x180017c54  call    WPP_SF_i
0x180017c59  mov     rax, [rbx]
0x180017c5c  mov     rcx, rbx
0x180017c5f  mov     rax, [rax+30h]
0x180017c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c68  xor     r9d, r9d
0x180017c6b  mov     edx, 23h ; '#'
0x180017c70  test    al, al
0x180017c72  mov     r8, rbp
0x180017c75  mov     rcx, rdi
0x180017c78  setnz   r9b
0x180017c7c  call    WPP_SF_d
0x180017c81  mov     rax, rsi
0x180017c84  mov     r8, rbp
0x180017c87  imul    qword ptr [rbx+38h]
0x180017c8b  mov     rcx, rdi
0x180017c8e  mov     r9, rdx
0x180017c91  mov     edx, 24h ; '$'
0x180017c96  add     r9, [rbx+38h]
0x180017c9a  sar     r9, 17h
0x180017c9e  mov     rax, r9
0x180017ca1  shr     rax, 3Fh
0x180017ca5  add     r9, rax
0x180017ca8  call    WPP_SF_i
0x180017cad  xor     r9d, r9d
0x180017cb0  mov     edx, 25h ; '%'
0x180017cb5  cmp     [rbx+141h], r9b
0x180017cbc  mov     r8, rbp
0x180017cbf  mov     rcx, rdi
0x180017cc2  setnz   r9b
0x180017cc6  add     rsp, 38h
0x180017cca  pop     rdi
0x180017ccb  pop     rsi
0x180017ccc  pop     rbp
0x180017ccd  pop     rbx
0x180017cce  jmp     WPP_SF_d
```

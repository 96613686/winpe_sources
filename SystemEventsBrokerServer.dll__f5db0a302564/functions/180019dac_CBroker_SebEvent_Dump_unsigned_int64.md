# CBroker::SebEvent::Dump(unsigned __int64)

- ea: `0x180019dac`
- end: `0x180019f1d`
- name: `?Dump@SebEvent@CBroker@@QEAAX_K@Z`
- size: `369`
- prototype: `void __fastcall(CBroker::SebEvent *this, TRACEHANDLE)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019b60`

## callees

- `0x1800016c4`
- `0x1800030e0`
- `0x180003950`
- `0x180005a50`
- `0x180019dac`
- `0x18001f36c`

## pseudocode

```c
void __fastcall CBroker::SebEvent::Dump(CBroker::SebEvent *this, TRACEHANDLE a2)
{
  __int64 v2; // rbx
  _QWORD *v5; // r9
  _QWORD *v6; // r9

  v2 = *((_QWORD *)this + 13);
  WPP_SF_DD(
    a2,
    70,
    &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids,
    *((unsigned int *)this + 28),
    *((_DWORD *)this + 29));
  WPP_SF__sid_(a2);
  if ( *((_QWORD *)this + 10) )
  {
    v5 = (_QWORD *)((char *)this + 64);
    if ( *((_QWORD *)this + 11) > 7u )
      v5 = (_QWORD *)*v5;
    WPP_SF_S(a2, 72, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, v5);
  }
  else
  {
    WPP_SF_(a2, 73, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids);
  }
  if ( *((_QWORD *)this + 6) )
  {
    v6 = (_QWORD *)((char *)this + 32);
    if ( *((_QWORD *)this + 7) > 7u )
      v6 = (_QWORD *)*v6;
    WPP_SF_S(a2, 74, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, v6);
  }
  else
  {
    WPP_SF_(a2, 75, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids);
  }
  WPP_SF_d(a2, 76, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, *((unsigned int *)this + 24));
  WPP_SF_d(a2, 77, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, *((unsigned int *)this + 25));
  WPP_SF_DD(a2, 78, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, (unsigned int)v2, HIDWORD(v2));
  WPP_SF_d(a2, 79, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, *((unsigned int *)this + 39));
  if ( *((_DWORD *)this + 25) == 1 || *((_DWORD *)this + 25) == 4 )
  {
    WPP_SF_d(a2, 80, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, *((unsigned __int8 *)this + 160));
    WPP_SF_d(a2, 81, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, *((unsigned int *)this + 52));
    WPP_SF_d(a2, 82, &WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids, *((unsigned int *)this + 62));
  }
}

```

## disassembly

```asm
0x180019dac  push    rbx
0x180019dae  push    rbp
0x180019daf  push    rsi
0x180019db0  push    rdi
0x180019db1  sub     rsp, 38h
0x180019db5  mov     rbx, [rcx+68h]
0x180019db9  mov     rsi, rdx
0x180019dbc  mov     [rsp+58h+arg_0], rbx
0x180019dc1  mov     rdi, rcx
0x180019dc4  mov     eax, [rcx+74h]
0x180019dc7  lea     rbp, WPP_cc51fffcd96c3cbd275ce3957bb544ce_Traceguids
0x180019dce  mov     r9d, [rcx+70h]
0x180019dd2  mov     r8, rbp
0x180019dd5  mov     edx, 46h ; 'F'
0x180019dda  mov     [rsp+58h+var_38], eax
0x180019dde  mov     rcx, rsi
0x180019de1  call    WPP_SF_DD
0x180019de6  mov     r9, [rdi+8]
0x180019dea  mov     edx, 47h ; 'G'
0x180019def  mov     r8, rbp
0x180019df2  mov     rcx, rsi; LoggerHandle
0x180019df5  call    WPP_SF__sid_
0x180019dfa  cmp     qword ptr [rdi+50h], 0
0x180019dff  jz      short loc_180019E21
0x180019e01  lea     r9, [rdi+40h]
0x180019e05  cmp     qword ptr [r9+18h], 7
0x180019e0a  jbe     short loc_180019E0F
0x180019e0c  mov     r9, [r9]
0x180019e0f  mov     edx, 48h ; 'H'
0x180019e14  mov     r8, rbp
0x180019e17  mov     rcx, rsi
0x180019e1a  call    WPP_SF_S
0x180019e1f  jmp     short loc_180019E31
0x180019e21  mov     edx, 49h ; 'I'
0x180019e26  mov     r8, rbp
0x180019e29  mov     rcx, rsi
0x180019e2c  call    WPP_SF_
0x180019e31  cmp     qword ptr [rdi+30h], 0
0x180019e36  jz      short loc_180019E58
0x180019e38  lea     r9, [rdi+20h]
0x180019e3c  cmp     qword ptr [r9+18h], 7
0x180019e41  jbe     short loc_180019E46
0x180019e43  mov     r9, [r9]
0x180019e46  mov     edx, 4Ah ; 'J'
0x180019e4b  mov     r8, rbp
0x180019e4e  mov     rcx, rsi
0x180019e51  call    WPP_SF_S
0x180019e56  jmp     short loc_180019E68
0x180019e58  mov     edx, 4Bh ; 'K'
0x180019e5d  mov     r8, rbp
0x180019e60  mov     rcx, rsi
0x180019e63  call    WPP_SF_
0x180019e68  mov     r9d, [rdi+60h]
0x180019e6c  mov     edx, 4Ch ; 'L'
0x180019e71  mov     r8, rbp
0x180019e74  mov     rcx, rsi
0x180019e77  call    WPP_SF_d
0x180019e7c  mov     r9d, [rdi+64h]
0x180019e80  mov     edx, 4Dh ; 'M'
0x180019e85  mov     r8, rbp
0x180019e88  mov     rcx, rsi
0x180019e8b  call    WPP_SF_d
0x180019e90  mov     eax, dword ptr [rsp+58h+arg_0+4]
0x180019e94  mov     edx, 4Eh ; 'N'
0x180019e99  mov     r9d, ebx
0x180019e9c  mov     [rsp+58h+var_38], eax
0x180019ea0  mov     r8, rbp
0x180019ea3  mov     rcx, rsi
0x180019ea6  call    WPP_SF_DD
0x180019eab  mov     r9d, [rdi+9Ch]
0x180019eb2  mov     edx, 4Fh ; 'O'
0x180019eb7  mov     r8, rbp
0x180019eba  mov     rcx, rsi
0x180019ebd  call    WPP_SF_d
0x180019ec2  cmp     dword ptr [rdi+64h], 1
0x180019ec6  jz      short loc_180019ECE
0x180019ec8  cmp     dword ptr [rdi+64h], 4
0x180019ecc  jnz     short loc_180019F14
0x180019ece  movzx   r9d, byte ptr [rdi+0A0h]
0x180019ed6  mov     edx, 50h ; 'P'
0x180019edb  mov     r8, rbp
0x180019ede  mov     rcx, rsi
0x180019ee1  call    WPP_SF_d
0x180019ee6  mov     r9d, [rdi+0D0h]
0x180019eed  mov     edx, 51h ; 'Q'
0x180019ef2  mov     r8, rbp
0x180019ef5  mov     rcx, rsi
0x180019ef8  call    WPP_SF_d
0x180019efd  mov     r9d, [rdi+0F8h]
0x180019f04  mov     edx, 52h ; 'R'
0x180019f09  mov     r8, rbp
0x180019f0c  mov     rcx, rsi
0x180019f0f  call    WPP_SF_d
0x180019f14  add     rsp, 38h
0x180019f18  pop     rdi
0x180019f19  pop     rsi
0x180019f1a  pop     rbp
0x180019f1b  pop     rbx
0x180019f1c  retn
```

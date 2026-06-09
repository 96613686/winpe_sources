# Broker::CAlarmTimeEvent::SignalEvent(__int64)

- ea: `0x180008870`
- end: `0x180008b5a`
- name: `?SignalEvent@CAlarmTimeEvent@Broker@@MEAAX_J@Z`
- size: `746`
- prototype: `void __fastcall(Broker::CAlarmTimeEvent *this, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180008870`
- `0x180008b60`
- `0x180009f70`
- `0x1800177d0`
- `0x180017dc4`

## import_xrefs

- `BrokerLib!BrSignalBrokerEvent2` at `0x18000891f`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180008b07`
- `BrokerLib!BrSignalBrokerEvent2` at `0x18000891f`
- `BrokerLib!BrSignalBrokerEvent2` at `0x180008b07`

## pseudocode

```c
void __fastcall Broker::CAlarmTimeEvent::SignalEvent(Broker::CAlarmTimeEvent *this, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  __int64 v4; // r14
  int v7; // r15d
  __int64 v8; // rbx
  _QWORD *v9; // r10
  int v10; // r12d
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  int v13; // eax
  __int128 v14; // rax
  int v15; // eax
  unsigned __int8 v16; // [rsp+80h] [rbp+8h] BYREF
  __int64 v17; // [rsp+88h] [rbp+10h]

  v3 = 0;
  v4 = 0;
  v7 = 0;
  v8 = *(_QWORD *)(*((_QWORD *)this + 31) + 16LL);
  v17 = v8;
  v16 = 1;
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
      (unsigned int)v8,
      HIDWORD(v8));
    v9 = WPP_GLOBAL_Control;
  }
  v10 = HIDWORD(v17);
  if ( (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 5u )
  {
    v14 = (__int64)(*((_QWORD *)this + 3) + *((_QWORD *)this + 4));
    WPP_SF_DDiLidd(
      v9[2],
      *((_QWORD *)&v14 + 1),
      *((_QWORD *)this + 7) / 10000000LL,
      (unsigned int)v8,
      HIDWORD(v17),
      a2,
      *((_DWORD *)this + 18),
      (__int64)v14 / 2,
      *((_QWORD *)this + 7) / 10000000LL,
      (int)*((_QWORD *)this + 6) / 600000000);
    v9 = WPP_GLOBAL_Control;
  }
  v11 = *((_QWORD *)this + 32);
  v12 = *((_QWORD *)this + 33) - v11;
  if ( v12 > 0x10 )
  {
    v3 = *((_QWORD *)this + 32);
    v4 = v11 + 16;
    v7 = v12 - 16;
  }
  if ( *((_BYTE *)this + 321) )
  {
    if ( *((_BYTE *)this + 320) )
      v16 = 0;
    if ( (*((_BYTE *)v9 + 28) & 0x40) != 0 && *((_BYTE *)v9 + 25) >= 4u )
      WPP_SF_dDD(v9[2], a2, a3, v16, v8, v10);
    v15 = BrSignalBrokerEvent2(*((_QWORD *)this + 30), *((_QWORD *)this + 31), &v16, v3, v7, v4);
    if ( v15 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
        (unsigned int)v8,
        v10,
        v15);
    *((_BYTE *)this + 320) = *((_BYTE *)this + 320) == 0;
  }
  else
  {
    v13 = BrSignalBrokerEvent2(*((_QWORD *)this + 30), *((_QWORD *)this + 31), &v16, v3, v7, v4);
    if ( v13 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
        (unsigned int)v8,
        v10,
        v13);
  }
  *((_QWORD *)this + 39) = a2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
      (unsigned int)v8,
      v10);
}

```

## disassembly

```asm
0x180008870  mov     [rsp+arg_10], rbx
0x180008875  mov     [rsp+arg_18], rbp
0x18000887a  push    rsi
0x18000887b  push    rdi
0x18000887c  push    r12
0x18000887e  push    r14
0x180008880  push    r15
0x180008882  sub     rsp, 50h
0x180008886  mov     rbx, [rcx+0F8h]
0x18000888d  xor     ebp, ebp
0x18000888f  xor     r14d, r14d
0x180008892  mov     rsi, rdx
0x180008895  mov     rdi, rcx
0x180008898  xor     r15d, r15d
0x18000889b  mov     rbx, [rbx+10h]
0x18000889f  mov     [rsp+78h+arg_8], rbx
0x1800088a7  mov     [rsp+78h+arg_0], 1
0x1800088af  mov     r10, cs:WPP_GLOBAL_Control
0x1800088b6  test    byte ptr [r10+1Ch], 40h
0x1800088bb  jnz     loc_1800089F3
0x1800088c1  test    byte ptr [r10+1Ch], 40h
0x1800088c6  mov     r12d, dword ptr [rsp+78h+arg_8+4]
0x1800088ce  jnz     loc_18000895E
0x1800088d4  mov     rcx, [rdi+100h]
0x1800088db  mov     rax, [rdi+108h]
0x1800088e2  sub     rax, rcx
0x1800088e5  cmp     rax, 10h
0x1800088e9  ja      loc_180008A59
0x1800088ef  cmp     byte ptr [rdi+141h], 0
0x1800088f6  jnz     loc_180008AAA
0x1800088fc  mov     rdx, [rdi+0F8h]
0x180008903  lea     r8, [rsp+78h+arg_0]
0x18000890b  mov     rcx, [rdi+0F0h]
0x180008912  mov     r9, rbp
0x180008915  mov     [rsp+78h+var_50], r14
0x18000891a  mov     [rsp+78h+var_58], r15d
0x18000891f  call    cs:__imp_BrSignalBrokerEvent2
0x180008925  test    eax, eax
0x180008927  jnz     loc_180008A69
0x18000892d  mov     [rdi+138h], rsi
0x180008934  mov     rcx, cs:WPP_GLOBAL_Control
0x18000893b  test    byte ptr [rcx+1Ch], 40h
0x18000893f  jnz     loc_180008A2D
0x180008945  lea     r11, [rsp+78h+var_28]
0x18000894a  mov     rbx, [r11+40h]
0x18000894e  mov     rbp, [r11+48h]
0x180008952  mov     rsp, r11
0x180008955  pop     r15
0x180008957  pop     r14
0x180008959  pop     r12
0x18000895b  pop     rdi
0x18000895c  pop     rsi
0x18000895d  retn
0x18000895e  cmp     byte ptr [r10+19h], 5
0x180008963  jb      loc_1800088D4
0x180008969  mov     rcx, [rdi+38h]
0x18000896d  mov     rax, 1CA213D840BAF7D5h
0x180008977  imul    qword ptr [rdi+30h]
0x18000897b  mov     r9, rdx
0x18000897e  sar     r9, 1Ah
0x180008982  mov     rax, r9
0x180008985  shr     rax, 3Fh
0x180008989  add     r9, rax
0x18000898c  mov     rax, 0D6BF94D5E57A42BDh
0x180008996  imul    rcx
0x180008999  mov     [rsp+78h+var_30], r9d
0x18000899e  mov     r9d, ebx
0x1800089a1  lea     r8, [rcx+rdx]
0x1800089a5  mov     rcx, [r10+10h]
0x1800089a9  sar     r8, 17h
0x1800089ad  mov     rax, r8
0x1800089b0  shr     rax, 3Fh
0x1800089b4  add     r8, rax
0x1800089b7  mov     rax, [rdi+20h]
0x1800089bb  add     rax, [rdi+18h]
0x1800089bf  mov     [rsp+78h+var_38], r8d
0x1800089c4  cqo
0x1800089c6  sub     rax, rdx
0x1800089c9  sar     rax, 1
0x1800089cc  mov     [rsp+78h+var_40], rax
0x1800089d1  mov     eax, [rdi+48h]
0x1800089d4  mov     [rsp+78h+var_48], eax
0x1800089d8  mov     [rsp+78h+var_50], rsi
0x1800089dd  mov     [rsp+78h+var_58], r12d
0x1800089e2  call    WPP_SF_DDiLidd
0x1800089e7  mov     r10, cs:WPP_GLOBAL_Control
0x1800089ee  jmp     loc_1800088D4
0x1800089f3  cmp     byte ptr [r10+19h], 4
0x1800089f8  jb      loc_1800088C1
0x1800089fe  mov     rcx, [r10+10h]
0x180008a02  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x180008a09  mov     rax, rbx
0x180008a0c  mov     edx, 13h
0x180008a11  shr     rax, 20h
0x180008a15  mov     r9d, ebx
0x180008a18  mov     [rsp+78h+var_58], eax
0x180008a1c  call    WPP_SF_DD
0x180008a21  mov     r10, cs:WPP_GLOBAL_Control
0x180008a28  jmp     loc_1800088C1
0x180008a2d  cmp     byte ptr [rcx+19h], 4
0x180008a31  jb      loc_180008945
0x180008a37  mov     rcx, [rcx+10h]
0x180008a3b  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x180008a42  mov     edx, 18h
0x180008a47  mov     [rsp+78h+var_58], r12d
0x180008a4c  mov     r9d, ebx
0x180008a4f  call    WPP_SF_DD
0x180008a54  jmp     loc_180008945
0x180008a59  mov     rbp, rcx
0x180008a5c  lea     r14, [rcx+10h]
0x180008a60  lea     r15d, [rax-10h]
0x180008a64  jmp     loc_1800088EF
0x180008a69  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a70  test    byte ptr [rcx+1Ch], 40h
0x180008a74  jz      loc_18000892D
0x180008a7a  cmp     byte ptr [rcx+19h], 2
0x180008a7e  jb      loc_18000892D
0x180008a84  mov     rcx, [rcx+10h]
0x180008a88  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x180008a8f  mov     dword ptr [rsp+78h+var_50], eax
0x180008a93  mov     edx, 15h
0x180008a98  mov     r9d, ebx
0x180008a9b  mov     [rsp+78h+var_58], r12d
0x180008aa0  call    WPP_SF_DDD
0x180008aa5  jmp     loc_18000892D
0x180008aaa  cmp     byte ptr [rdi+140h], 0
0x180008ab1  jz      short loc_180008ABB
0x180008ab3  mov     [rsp+78h+arg_0], 0
0x180008abb  test    byte ptr [r10+1Ch], 40h
0x180008ac0  jz      short loc_180008AE4
0x180008ac2  cmp     byte ptr [r10+19h], 4
0x180008ac7  jb      short loc_180008AE4
0x180008ac9  movzx   r9d, [rsp+78h+arg_0]
0x180008ad2  mov     rcx, [r10+10h]
0x180008ad6  mov     dword ptr [rsp+78h+var_50], r12d
0x180008adb  mov     [rsp+78h+var_58], ebx
0x180008adf  call    WPP_SF_dDD
0x180008ae4  mov     rdx, [rdi+0F8h]
0x180008aeb  lea     r8, [rsp+78h+arg_0]
0x180008af3  mov     rcx, [rdi+0F0h]
0x180008afa  mov     r9, rbp
0x180008afd  mov     [rsp+78h+var_50], r14
0x180008b02  mov     [rsp+78h+var_58], r15d
0x180008b07  call    cs:__imp_BrSignalBrokerEvent2
0x180008b0d  test    eax, eax
0x180008b0f  jz      short loc_180008B45
0x180008b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180008b18  test    byte ptr [rcx+1Ch], 40h
0x180008b1c  jz      short loc_180008B45
0x180008b1e  cmp     byte ptr [rcx+19h], 2
0x180008b22  jb      short loc_180008B45
0x180008b24  mov     rcx, [rcx+10h]
0x180008b28  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x180008b2f  mov     dword ptr [rsp+78h+var_50], eax
0x180008b33  mov     edx, 17h
0x180008b38  mov     r9d, ebx
0x180008b3b  mov     [rsp+78h+var_58], r12d
0x180008b40  call    WPP_SF_DDD
0x180008b45  cmp     byte ptr [rdi+140h], 0
0x180008b4c  setz    al
0x180008b4f  mov     [rdi+140h], al
0x180008b55  jmp     loc_18000892D
```

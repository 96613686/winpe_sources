# Broker::CAlarmTimeEvent::OnSystemTimeChange(__int64,__int64)

- ea: `0x1800090a0`
- end: `0x1800091ee`
- name: `?OnSystemTimeChange@CAlarmTimeEvent@Broker@@UEAAX_J0@Z`
- size: `334`
- prototype: `void __fastcall(Broker::CAlarmTimeEvent *__hidden this, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800090a0`
- `0x180009f70`
- `0x18000a0b0`
- `0x18001c010`

## pseudocode

```c
void __fastcall Broker::CAlarmTimeEvent::OnSystemTimeChange(Broker::CAlarmTimeEvent *this, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  _QWORD *v7; // rcx

  v6 = *(_QWORD *)(*((_QWORD *)this + 31) + 16LL);
  v7 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
      (unsigned int)v6,
      HIDWORD(v6));
    v7 = WPP_GLOBAL_Control;
  }
  if ( a2 < 0 )
  {
    if ( a3 < *((_QWORD *)this + 4) - *((_QWORD *)this + 7) )
    {
      *((_BYTE *)this + 320) = 0;
      v7 = WPP_GLOBAL_Control;
    }
LABEL_6:
    if ( (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 5u )
      WPP_SF__guid_d(
        v7[2],
        18,
        &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids,
        *((_QWORD *)this + 31),
        (int)a2 / 10000000);
    *((_QWORD *)this + 10) += a2;
    if ( *((_DWORD *)this + 22) != 1 || -*((_QWORD *)this + 10) <= *((_QWORD *)this + 8) )
      goto LABEL_11;
    goto LABEL_19;
  }
  if ( a2 )
    goto LABEL_6;
  if ( *((_BYTE *)this + 322) )
  {
LABEL_19:
    (*(void (__fastcall **)(Broker::CAlarmTimeEvent *, __int64))(*(_QWORD *)this + 72LL))(this, a3);
LABEL_11:
    v7 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v7 + 28) & 0x40) != 0 && *((_BYTE *)v7 + 25) >= 4u )
    WPP_SF_DD(v7[2], 15, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, (unsigned int)v6, HIDWORD(v6));
}

```

## disassembly

```asm
0x1800090a0  push    rbx
0x1800090a2  push    rbp
0x1800090a3  push    rsi
0x1800090a4  push    rdi
0x1800090a5  sub     rsp, 38h
0x1800090a9  mov     rbx, [rcx+0F8h]
0x1800090b0  mov     rbp, r8
0x1800090b3  mov     rsi, rdx
0x1800090b6  mov     rdi, rcx
0x1800090b9  mov     rbx, [rbx+10h]
0x1800090bd  mov     [rsp+58h+arg_0], rbx
0x1800090c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090c9  test    byte ptr [rcx+1Ch], 40h
0x1800090cd  jz      short loc_1800090FF
0x1800090cf  cmp     byte ptr [rcx+19h], 4
0x1800090d3  jb      short loc_1800090FF
0x1800090d5  mov     rcx, [rcx+10h]
0x1800090d9  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x1800090e0  mov     rax, rbx
0x1800090e3  mov     edx, 0Eh
0x1800090e8  shr     rax, 20h
0x1800090ec  mov     r9d, ebx
0x1800090ef  mov     [rsp+58h+var_38], eax
0x1800090f3  call    WPP_SF_DD
0x1800090f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090ff  test    rsi, rsi
0x180009102  js      loc_1800091AD
0x180009108  jz      loc_1800091D1
0x18000910e  test    byte ptr [rcx+1Ch], 40h
0x180009112  jz      short loc_18000915A
0x180009114  cmp     byte ptr [rcx+19h], 5
0x180009118  jb      short loc_18000915A
0x18000911a  mov     r9, [rdi+0F8h]
0x180009121  mov     rax, 0D6BF94D5E57A42BDh
0x18000912b  mov     rcx, [rcx+10h]
0x18000912f  imul    rsi
0x180009132  lea     r8, [rsi+rdx]
0x180009136  mov     edx, 12h
0x18000913b  sar     r8, 17h
0x18000913f  mov     rax, r8
0x180009142  shr     rax, 3Fh
0x180009146  add     r8, rax
0x180009149  mov     [rsp+58h+var_38], r8d
0x18000914e  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x180009155  call    WPP_SF__guid_d
0x18000915a  add     [rdi+50h], rsi
0x18000915e  cmp     dword ptr [rdi+58h], 1
0x180009162  mov     rax, [rdi+50h]
0x180009166  jnz     short loc_180009171
0x180009168  neg     rax
0x18000916b  cmp     rax, [rdi+40h]
0x18000916f  jg      short loc_1800091DA
0x180009171  mov     rcx, cs:WPP_GLOBAL_Control
0x180009178  test    byte ptr [rcx+1Ch], 40h
0x18000917c  jz      short loc_1800091A4
0x18000917e  cmp     byte ptr [rcx+19h], 4
0x180009182  jb      short loc_1800091A4
0x180009184  mov     eax, dword ptr [rsp+58h+arg_0+4]
0x180009188  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x18000918f  mov     rcx, [rcx+10h]
0x180009193  mov     edx, 0Fh
0x180009198  mov     r9d, ebx
0x18000919b  mov     [rsp+58h+var_38], eax
0x18000919f  call    WPP_SF_DD
0x1800091a4  add     rsp, 38h
0x1800091a8  pop     rdi
0x1800091a9  pop     rsi
0x1800091aa  pop     rbp
0x1800091ab  pop     rbx
0x1800091ac  retn
0x1800091ad  mov     rax, [rdi+20h]
0x1800091b1  sub     rax, [rdi+38h]
0x1800091b5  cmp     rbp, rax
0x1800091b8  jge     loc_18000910E
0x1800091be  mov     byte ptr [rdi+140h], 0
0x1800091c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091cc  jmp     loc_18000910E
0x1800091d1  cmp     byte ptr [rdi+142h], 0
0x1800091d8  jz      short loc_180009178
0x1800091da  mov     rax, [rdi]
0x1800091dd  mov     rdx, rbp
0x1800091e0  mov     rcx, rdi
0x1800091e3  mov     rax, [rax+48h]
0x1800091e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091ec  jmp     short loc_180009171
```

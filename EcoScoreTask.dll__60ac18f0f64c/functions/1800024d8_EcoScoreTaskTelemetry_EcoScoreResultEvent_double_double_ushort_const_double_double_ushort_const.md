# EcoScoreTaskTelemetry::EcoScoreResultEvent<double &,double &,ushort const *>(double &,double &,ushort const * &&)

- ea: `0x1800024d8`
- end: `0x1800025fd`
- name: `??$EcoScoreResultEvent@AEANAEANPEBG@EcoScoreTaskTelemetry@@SAXAEAN0$$QEAPEBG@Z`
- size: `293`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, int **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800073f0`

## callees

- `0x1800018dc`
- `0x1800024d8`
- `0x180005760`
- `0x180007c90`

## pseudocode

```c
__int64 __fastcall EcoScoreTaskTelemetry::EcoScoreResultEvent<double &,double &,unsigned short const *>(
        __int64 *a1,
        __int64 *a2,
        int **a3)
{
  __int64 result; // rax
  __int64 v7; // r10
  int *v8; // rcx
  __int64 v9; // xmm1_8
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // [rsp+30h] [rbp-59h] BYREF
  __int64 v13; // [rsp+38h] [rbp-51h] BYREF
  __int64 v14; // [rsp+40h] [rbp-49h] BYREF
  _BYTE v15[32]; // [rsp+50h] [rbp-39h] BYREF
  __int64 *v16; // [rsp+70h] [rbp-19h]
  __int64 v17; // [rsp+78h] [rbp-11h]
  __int64 *v18; // [rsp+80h] [rbp-9h]
  __int64 v19; // [rsp+88h] [rbp-1h]
  int *v20; // [rsp+90h] [rbp+7h]
  int v21; // [rsp+98h] [rbp+Fh]
  int v22; // [rsp+9Ch] [rbp+13h]
  __int64 *v23; // [rsp+A0h] [rbp+17h]
  __int64 v24; // [rsp+A8h] [rbp+1Fh]

  result = (__int64)EcoScoreTaskTelemetry::Provider();
  v7 = result;
  if ( *(_DWORD *)result > 5u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0 && (result & 0x200000000000LL) == result )
    {
      v8 = *a3;
      v9 = *a1;
      v13 = *a2;
      v14 = v9;
      v12 = 0x1000000;
      v23 = &v12;
      v24 = 8;
      if ( v8 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *((_WORD *)v8 + v10) );
        v11 = 2 * v10 + 2;
      }
      else
      {
        v8 = &dword_18000A6E4;
        v11 = 2;
      }
      v21 = v11;
      v20 = v8;
      v18 = &v13;
      v22 = 0;
      v16 = &v14;
      v19 = 8;
      v17 = 8;
      return tlgWriteTransfer_EventWriteTransfer(v7, byte_18000B28B, 0, 0, 6, v15);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800024d8  push    rbp
0x1800024da  push    rbx
0x1800024db  push    rsi
0x1800024dc  push    rdi
0x1800024dd  lea     rbp, [rsp-3Fh]
0x1800024e2  sub     rsp, 0C8h
0x1800024e9  mov     rax, cs:__security_cookie
0x1800024f0  xor     rax, rsp
0x1800024f3  mov     [rbp+57h+var_30], rax
0x1800024f7  mov     rbx, r8
0x1800024fa  mov     rdi, rdx
0x1800024fd  mov     rsi, rcx
0x180002500  call    ?Provider@EcoScoreTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; EcoScoreTaskTelemetry::Provider(void)
0x180002505  mov     r10, rax
0x180002508  mov     r9d, [rax]
0x18000250b  cmp     r9d, 5
0x18000250f  jbe     loc_1800025E5
0x180002515  mov     rax, [rax+18h]
0x180002519  mov     rdx, 200000000000h
0x180002523  mov     r9, [r10+10h]
0x180002527  test    rdx, r9
0x18000252a  jz      loc_1800025E5
0x180002530  mov     rcx, rax
0x180002533  and     rcx, rdx
0x180002536  cmp     rcx, rax
0x180002539  jnz     loc_1800025E5
0x18000253f  mov     rcx, [rbx]
0x180002542  lea     rax, [rbp+57h+var_B0]
0x180002546  movsd   xmm0, qword ptr [rdi]
0x18000254a  xor     edx, edx
0x18000254c  movsd   xmm1, qword ptr [rsi]
0x180002550  movsd   [rbp+57h+var_A8], xmm0
0x180002555  movsd   [rbp+57h+var_A0], xmm1
0x18000255a  mov     [rbp+57h+var_B0], 1000000h
0x180002562  mov     [rbp+57h+var_40], rax
0x180002566  mov     [rbp+57h+var_38], 8
0x18000256e  test    rcx, rcx
0x180002571  jz      short loc_180002589
0x180002573  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002577  inc     rax
0x18000257a  cmp     [rcx+rax*2], dx
0x18000257e  jnz     short loc_180002577
0x180002580  lea     eax, ds:2[rax*2]
0x180002587  jmp     short loc_180002595
0x180002589  lea     rcx, dword_18000A6E4
0x180002590  mov     eax, 2
0x180002595  mov     [rbp+57h+var_48], eax
0x180002598  xor     r9d, r9d
0x18000259b  lea     rax, [rbp+57h+var_A8]
0x18000259f  mov     [rbp+57h+var_50], rcx
0x1800025a3  mov     [rbp+57h+var_60], rax
0x1800025a7  xor     r8d, r8d
0x1800025aa  lea     rax, [rbp+57h+var_A0]
0x1800025ae  mov     [rbp+57h+var_44], edx
0x1800025b1  mov     [rbp+57h+var_70], rax
0x1800025b5  lea     rdx, byte_18000B28B
0x1800025bc  lea     rax, [rbp+57h+var_90]
0x1800025c0  mov     [rbp+57h+var_58], 8
0x1800025c8  mov     [rsp+0E0h+var_B8], rax
0x1800025cd  mov     rcx, r10
0x1800025d0  mov     [rsp+0E0h+var_C0], 6
0x1800025d8  mov     [rbp+57h+var_68], 8
0x1800025e0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800025e5  mov     rcx, [rbp+57h+var_30]
0x1800025e9  xor     rcx, rsp; StackCookie
0x1800025ec  call    __security_check_cookie
0x1800025f1  add     rsp, 0C8h
0x1800025f8  pop     rdi
0x1800025f9  pop     rsi
0x1800025fa  pop     rbx
0x1800025fb  pop     rbp
0x1800025fc  retn
```

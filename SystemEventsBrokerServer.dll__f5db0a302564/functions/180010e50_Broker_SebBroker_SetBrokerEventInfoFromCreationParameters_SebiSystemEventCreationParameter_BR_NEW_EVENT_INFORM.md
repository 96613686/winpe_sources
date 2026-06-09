# Broker::SebBroker::SetBrokerEventInfoFromCreationParameters(_SebiSystemEventCreationParameter,_BR_NEW_EVENT_INFORMATION *)

- ea: `0x180010e50`
- end: `0x18001117f`
- name: `?SetBrokerEventInfoFromCreationParameters@SebBroker@Broker@@CAXU_SebiSystemEventCreationParameter@@PEAU_BR_NEW_EVENT_INFORMATION@@@Z`
- size: `815`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010560`

## callees

- `0x180003170`
- `0x18000da40`
- `0x180010e50`
- `0x180014618`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall Broker::SebBroker::SetBrokerEventInfoFromCreationParameters(_DWORD *a1, __int64 a2)
{
  int *v3; // r14
  _DWORD *v4; // rsi
  int v5; // edi
  int result; // eax
  _DWORD *v7; // r12
  _DWORD *v8; // r13
  HANDLE v9[9]; // [rsp+30h] [rbp-48h] BYREF

  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  v3 = (int *)(a2 + 8);
  v4 = (_DWORD *)(a2 + 4);
  v5 = a1[2];
  *(_DWORD *)a2 = v5;
  switch ( v5 )
  {
    case 10:
LABEL_2:
      *v3 = 16424;
      break;
    case 25:
      *v3 = 1441864;
      break;
    case 4:
      *v3 = 16392;
      break;
    default:
      v7 = (_DWORD *)(a2 + 12);
      v8 = (_DWORD *)(a2 + 16);
      switch ( v5 )
      {
        case 5:
        case 24:
          *v3 = 8;
          goto LABEL_3;
        case 7:
          *v3 = 134234248;
          Broker::RpcClientToken::RpcClientToken((Broker::RpcClientToken *)v9);
          if ( Broker::RpcClientToken::CheckCapability((Broker::RpcClientToken *)v9, 2u, 1) )
            *v3 |= 0x2000u;
          Broker::RpcClientToken::~RpcClientToken(v9);
          goto LABEL_24;
        case 8:
        case 15:
        case 29:
        case 35:
        case 37:
        case 38:
        case 39:
        case 41:
        case 44:
        case 45:
        case 58:
        case 59:
        case 60:
        case 63:
        case 67:
          *v3 = 32;
          goto LABEL_3;
        case 9:
        case 68:
        case 69:
          *v3 = 40;
          goto LABEL_3;
        case 14:
        case 70:
          *v3 = 16456;
          goto LABEL_3;
        case 16:
          *v3 = 16;
          goto LABEL_3;
        case 20:
          goto LABEL_2;
        case 21:
          *v3 = 4096;
          goto LABEL_3;
        case 22:
          *v3 = 2;
          goto LABEL_3;
        case 26:
          *v3 = 72;
          goto LABEL_3;
        case 32:
        case 33:
          *v3 = 1179648;
          goto LABEL_3;
        case 36:
          *v3 = 262152;
          goto LABEL_3;
        case 40:
          *v3 = 2129920;
          goto LABEL_3;
        case 42:
          *v3 = 6324224;
          goto LABEL_3;
        case 43:
        case 64:
          *v3 = 0x8000;
          goto LABEL_3;
        case 46:
        case 51:
        case 74:
        case 75:
          *v3 = 128;
          goto LABEL_3;
        case 47:
        case 57:
        case 71:
        case 73:
          *v3 = 262176;
          goto LABEL_3;
        case 48:
          *v3 = 262272;
          goto LABEL_3;
        case 49:
        case 50:
        case 61:
          *v3 = 134217856;
LABEL_24:
          *v7 = 30000;
          *v8 = 900000;
          break;
        case 52:
          *v3 = 32776;
          break;
        case 53:
        case 54:
        case 55:
        case 56:
        case 62:
          *v3 = 64;
          break;
        case 72:
          *v3 = 128;
          *(_BYTE *)(a2 + 28) = 1;
          break;
        default:
          goto LABEL_3;
      }
      break;
  }
LABEL_3:
  if ( a1[3] == 1 )
  {
    *v3 |= 1u;
    *v4 |= 1u;
  }
  result = *v3;
  if ( !a1[5] )
  {
    result |= 0x200u;
    *v3 = result;
  }
  if ( !dword_180035120[12 * v5] )
  {
    result |= 0x400u;
    *v3 = result;
  }
  if ( a1[4] )
  {
    result |= 4u;
    *v3 = result;
  }
  if ( (result & 0x60) != 0 )
    *v4 |= 2u;
  return result;
}

```

## disassembly

```asm
0x180010e50  mov     [rsp+arg_0], rcx
0x180010e55  push    rbx
0x180010e56  push    rsi
0x180010e57  push    rdi
0x180010e58  push    r12
0x180010e5a  push    r13
0x180010e5c  push    r14
0x180010e5e  push    r15
0x180010e60  sub     rsp, 40h
0x180010e64  mov     rbx, rcx
0x180010e67  xorps   xmm0, xmm0
0x180010e6a  movups  xmmword ptr [rdx], xmm0
0x180010e6d  movups  xmmword ptr [rdx+10h], xmm0
0x180010e71  lea     r14, [rdx+8]
0x180010e75  mov     [rsp+78h+arg_10], r14
0x180010e7d  lea     rsi, [rdx+4]
0x180010e81  mov     [rsp+78h+arg_18], rsi
0x180010e89  mov     edi, [rcx+8]
0x180010e8c  mov     [rsp+78h+arg_8], edi
0x180010e93  mov     [rdx], edi
0x180010e95  lea     r15, __ImageBase
0x180010e9c  cmp     edi, 0Ah
0x180010e9f  jnz     short loc_180010EF8
0x180010ea1  mov     dword ptr [r14], 4028h; jumptable 0000000180010F4D case 20
0x180010ea8  cmp     dword ptr [rbx+0Ch], 1; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180010eac  jz      short loc_180010F14
0x180010eae  mov     eax, [r14]
0x180010eb1  cmp     dword ptr [rbx+14h], 0
0x180010eb5  jnz     short loc_180010EBE
0x180010eb7  bts     eax, 9
0x180010ebb  mov     [r14], eax
0x180010ebe  movsxd  rcx, edi
0x180010ec1  lea     rdx, [rcx+rcx*2]
0x180010ec5  add     rdx, rdx
0x180010ec8  cmp     rva dword_180035120[r15+rdx*8], 0
0x180010ed1  jz      loc_1800110C4
0x180010ed7  cmp     dword ptr [rbx+10h], 0
0x180010edb  jnz     loc_1800110D0
0x180010ee1  test    al, 60h
0x180010ee3  jz      short loc_180010EE8
0x180010ee5  or      dword ptr [rsi], 2
0x180010ee8  add     rsp, 40h
0x180010eec  pop     r15
0x180010eee  pop     r14
0x180010ef0  pop     r13
0x180010ef2  pop     r12
0x180010ef4  pop     rdi
0x180010ef5  pop     rsi
0x180010ef6  pop     rbx
0x180010ef7  retn
0x180010ef8  cmp     edi, 19h
0x180010efb  jz      short loc_180010F0B
0x180010efd  cmp     edi, 4
0x180010f00  jnz     short loc_180010F1D
0x180010f02  mov     dword ptr [r14], 4008h
0x180010f09  jmp     short def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180010f0b  mov     dword ptr [r14], 160048h
0x180010f12  jmp     short def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180010f14  or      dword ptr [r14], 1
0x180010f18  or      dword ptr [rsi], 1
0x180010f1b  jmp     short loc_180010EAE
0x180010f1d  lea     eax, [rdi-5]; switch 71 cases
0x180010f20  cmp     eax, 46h
0x180010f23  ja      short def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180010f25  lea     r12, [rdx+0Ch]
0x180010f29  mov     [rsp+78h+var_58], r12
0x180010f2e  lea     r13, [rdx+10h]
0x180010f32  mov     [rsp+78h+var_50], r13
0x180010f37  cdqe
0x180010f39  movzx   eax, ds:(byte_180011138 - 180000000h)[r15+rax]
0x180010f42  mov     ecx, ds:(jpt_180010F4D - 180000000h)[r15+rax*4]
0x180010f4a  add     rcx, r15
0x180010f4d  jmp     rcx; switch jump
0x180010f4f  mov     dword ptr [r14], 80h; jumptable 0000000180010F4D case 72
0x180010f56  mov     byte ptr [rdx+1Ch], 1
0x180010f5a  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180010f5f  mov     dword ptr [r14], 8004088h; jumptable 0000000180010F4D case 7
0x180010f66  lea     rcx, [rsp+78h+var_48]; this
0x180010f6b  call    ??0RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::RpcClientToken(void)
0x180010f70  nop
0x180010f71  mov     edx, 2; unsigned int
0x180010f76  mov     r8d, 1; int
0x180010f7c  lea     rcx, [rsp+78h+var_48]; this
0x180010f81  call    ?CheckCapability@RpcClientToken@Broker@@QEAA_NKH@Z; Broker::RpcClientToken::CheckCapability(ulong,int)
0x180010f86  test    al, al
0x180010f88  jz      short loc_180010F91
0x180010f8a  or      dword ptr [r14], 2000h
0x180010f91  lea     rcx, [rsp+78h+var_48]; this
0x180010f96  call    ??1RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::~RpcClientToken(void)
0x180010f9b  nop
0x180010f9c  jmp     short loc_180010FD7
0x180010f9e  lea     r15, __ImageBase
0x180010fa5  mov     rbx, [rsp+78h+arg_0]
0x180010fad  mov     r14, [rsp+78h+arg_10]
0x180010fb5  mov     rsi, [rsp+78h+arg_18]
0x180010fbd  mov     edi, [rsp+78h+arg_8]
0x180010fc4  mov     r12, [rsp+78h+var_58]
0x180010fc9  mov     r13, [rsp+78h+var_50]
0x180010fce  jmp     short loc_180010FD7
0x180010fd0  mov     dword ptr [r14], 8000080h; jumptable 0000000180010F4D cases 49,50,61
0x180010fd7  mov     dword ptr [r12], 7530h
0x180010fdf  mov     dword ptr [r13+0], 0DBBA0h
0x180010fe7  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180010fec  mov     dword ptr [r14], 8; jumptable 0000000180010F4D cases 5,24
0x180010ff3  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180010ff8  mov     dword ptr [r14], 4048h; jumptable 0000000180010F4D cases 14,70
0x180010fff  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180011004  mov     dword ptr [r14], 2; jumptable 0000000180010F4D case 22
0x18001100b  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180011010  mov     dword ptr [r14], 10h; jumptable 0000000180010F4D case 16
0x180011017  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x18001101c  mov     dword ptr [r14], 28h ; '('; jumptable 0000000180010F4D cases 9,68,69
0x180011023  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180011028  mov     dword ptr [r14], 1000h; jumptable 0000000180010F4D case 21
0x18001102f  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180011034  mov     dword ptr [r14], 48h ; 'H'; jumptable 0000000180010F4D case 26
0x18001103b  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180011040  mov     dword ptr [r14], 120000h; jumptable 0000000180010F4D cases 32,33
0x180011047  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x18001104c  mov     dword ptr [r14], 40008h; jumptable 0000000180010F4D case 36
0x180011053  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180011058  mov     dword ptr [r14], 208000h; jumptable 0000000180010F4D case 40
0x18001105f  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180011064  mov     dword ptr [r14], 608000h; jumptable 0000000180010F4D case 42
0x18001106b  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180011070  mov     dword ptr [r14], 8000h; jumptable 0000000180010F4D cases 43,64
0x180011077  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x18001107c  mov     dword ptr [r14], 8008h; jumptable 0000000180010F4D case 52
0x180011083  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180011088  mov     dword ptr [r14], 40h ; '@'; jumptable 0000000180010F4D cases 53-56,62
0x18001108f  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x180011094  mov     dword ptr [r14], 20h ; ' '; jumptable 0000000180010F4D cases 8,15,29,35,37-39,41,44,45,58-60,63,67
0x18001109b  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x1800110a0  mov     dword ptr [r14], 80h; jumptable 0000000180010F4D cases 46,51,74,75
0x1800110a7  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x1800110ac  mov     dword ptr [r14], 40020h; jumptable 0000000180010F4D cases 47,57,71,73
0x1800110b3  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x1800110b8  mov     dword ptr [r14], 40080h; jumptable 0000000180010F4D case 48
0x1800110bf  jmp     def_180010F4D; jumptable 0000000180010F4D default case, cases 6,10-13,17-19,23,25,27,28,30,31,34,65,66
0x1800110c4  bts     eax, 0Ah
0x1800110c8  mov     [r14], eax
0x1800110cb  jmp     loc_180010ED7
0x1800110d0  or      eax, 4
0x1800110d3  mov     [r14], eax
0x1800110d6  jmp     loc_180010EE1
```

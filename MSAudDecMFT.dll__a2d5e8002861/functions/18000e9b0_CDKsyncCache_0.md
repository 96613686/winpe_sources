# CDKsyncCache_0

- ea: `0x18000e9b0`
- end: `0x18000eb60`
- name: `CDKsyncCache_0`
- size: `432`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `53`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a1a0`
- `0x18000a338`
- `0x18000e61c`
- `0x18000e684`
- `0x180010008`
- `0x1800100ac`
- `0x1800103a0`
- `0x180010838`
- `0x18001115c`
- `0x180011234`
- `0x1800113bc`
- `0x180011b10`
- `0x180011da8`
- `0x180012264`
- `0x1800122cc`
- `0x180012580`
- `0x180012768`
- `0x180012d90`
- `0x1800130d8`
- `0x180013fd0`
- `0x180018214`
- `0x180019d84`
- `0x180019ec4`
- `0x18001a968`
- `0x18002b938`
- `0x18002bc98`
- `0x18002be3c`
- `0x18002ce0c`
- `0x1800471fc`
- `0x18004afa0`
- `0x1800710ac`
- `0x1800712d4`
- `0x180077570`
- `0x1800777bc`
- `0x180078914`
- `0x180078b60`
- `0x180078c50`
- `0x1800793b8`
- `0x180079784`
- `0x180079f58`
- `0x18007a198`
- `0x18007a4ac`
- `0x18007ba08`
- `0x18007baf4`
- `0x18007c55c`
- `0x18007cb98`
- `0x18007cc98`
- `0x18007d4f4`
- `0x18007d75c`
- `0x180089140`

## callees

- `0x18000e9b0`

## pseudocode

```c
int *__fastcall CDKsyncCache_0(int *a1)
{
  int *result; // rax
  __int64 v2; // rbp
  unsigned int v3; // r8d
  int v4; // edx
  int v5; // r13d
  int v6; // r15d
  char v7; // r14
  __int64 v8; // r12
  __int64 v9; // rdx
  _BYTE *v10; // rbx
  __int64 v11; // rsi
  __int64 v12; // rdi
  __int64 v13; // r11
  _BYTE *v14; // r10

  result = a1;
  v2 = (unsigned int)a1[1];
  if ( a1[10] )
  {
    if ( (_DWORD)v2 )
    {
      v3 = a1[5];
      v4 = a1[9];
      v5 = a1[8] - 1;
      v6 = *a1;
      v7 = v3 & 7;
      a1[2] += v2;
      v8 = v3 >> 3;
      a1[5] = (v3 + v2) & (v4 - 1);
      v9 = *((_QWORD *)a1 + 3);
      v10 = (_BYTE *)(v8 + v9);
      v11 = v5 & (unsigned int)(v8 + 1);
      v12 = v5 & (unsigned int)(v8 + 2);
      v13 = v5 & (unsigned int)(v8 + 3);
      LODWORD(v9) = ((unsigned int)(v6 << (32 - v2)) >> v7)
                  | ~((unsigned int)(BitMask[v2] << (32 - v2)) >> v7)
                  & (*(unsigned __int8 *)(v9 + v13)
                   | ((*(unsigned __int8 *)(v9 + v12)
                     | (((*(unsigned __int8 *)(v8 + v9) << 8) | *(unsigned __int8 *)(v9 + v11)) << 8)) << 8));
      *v10 = BYTE3(v9);
      *(_BYTE *)(v11 + *((_QWORD *)a1 + 3)) = BYTE2(v9);
      *(_BYTE *)(v12 + *((_QWORD *)a1 + 3)) = BYTE1(v9);
      *(_BYTE *)(v13 + *((_QWORD *)a1 + 3)) = v9;
      if ( (v3 & 7) + (unsigned int)v2 > 0x20 )
      {
        v14 = (_BYTE *)(*((_QWORD *)a1 + 3) + (v5 & (unsigned int)(v8 + 4)));
        *v14 = ((_BYTE)v6 << (8 - ((v7 + v2) & 7)))
             | *v14 & ~(LOBYTE(BitMask[(v7 + (_BYTE)v2) & 7]) << (8 - ((v7 + v2) & 7)));
      }
      *(_QWORD *)a1 = 0;
    }
    else
    {
      *(_QWORD *)a1 = 0;
    }
  }
  else
  {
    a1[2] += v2;
    a1[5] = (a1[5] - v2) & (a1[9] - 1);
    *(_QWORD *)a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000e9b0  push    rbp
0x18000e9b2  sub     rsp, 20h
0x18000e9b6  cmp     dword ptr [rcx+28h], 0
0x18000e9ba  mov     rax, rcx
0x18000e9bd  mov     ebp, [rcx+4]
0x18000e9c0  jnz     short loc_18000E9E2
0x18000e9c2  add     [rcx+8], ebp
0x18000e9c5  mov     edx, [rcx+24h]
0x18000e9c8  mov     ecx, [rcx+14h]
0x18000e9cb  dec     edx
0x18000e9cd  sub     ecx, ebp
0x18000e9cf  and     edx, ecx
0x18000e9d1  mov     [rax+14h], edx
0x18000e9d4  mov     qword ptr [rax], 0
0x18000e9db  add     rsp, 20h
0x18000e9df  pop     rbp
0x18000e9e0  retn
0x18000e9e2  test    ebp, ebp
0x18000e9e4  jnz     short loc_18000E9EF
0x18000e9e6  mov     qword ptr [rcx], 0
0x18000e9ed  jmp     short loc_18000E9DB
0x18000e9ef  mov     r8d, [rcx+14h]
0x18000e9f3  mov     r9d, 20h ; ' '
0x18000e9f9  mov     edx, [rcx+24h]
0x18000e9fc  sub     r9d, ebp
0x18000e9ff  mov     [rsp+28h+arg_0], rbx
0x18000ea04  dec     edx
0x18000ea06  mov     [rsp+28h+arg_8], rsi
0x18000ea0b  mov     [rsp+28h+arg_10], rdi
0x18000ea10  mov     [rsp+28h+var_10], r12
0x18000ea15  mov     r12d, r8d
0x18000ea18  mov     [rsp+28h+var_18], r13
0x18000ea1d  mov     r13d, [rax+20h]
0x18000ea21  mov     [rsp+28h+var_20], r14
0x18000ea26  dec     r13d
0x18000ea29  mov     r14d, r8d
0x18000ea2c  mov     [rsp+28h+var_28], r15
0x18000ea30  mov     r15d, [rcx]
0x18000ea33  and     r14d, 7
0x18000ea37  add     [rax+8], ebp
0x18000ea3a  lea     ecx, [r8+rbp]
0x18000ea3e  and     edx, ecx
0x18000ea40  shr     r12d, 3
0x18000ea44  mov     [rax+14h], edx
0x18000ea47  lea     r8, BitMask
0x18000ea4e  mov     rdx, [rax+18h]
0x18000ea52  mov     r8d, [r8+rbp*4]
0x18000ea56  lea     rbx, [r12+rdx]
0x18000ea5a  mov     ecx, r13d
0x18000ea5d  lea     esi, [r12+1]
0x18000ea62  and     rsi, rcx
0x18000ea65  lea     edi, [r12+2]
0x18000ea6a  mov     ecx, r13d
0x18000ea6d  lea     r11d, [r12+3]
0x18000ea72  and     rdi, rcx
0x18000ea75  mov     ecx, r13d
0x18000ea78  and     r11, rcx
0x18000ea7b  movzx   ecx, byte ptr [rbx]
0x18000ea7e  movzx   r10d, byte ptr [rdx+rsi]
0x18000ea83  shl     ecx, 8
0x18000ea86  or      r10d, ecx
0x18000ea89  movzx   ecx, byte ptr [rdx+rdi]
0x18000ea8d  movzx   edx, byte ptr [rdx+r11]
0x18000ea92  shl     r10d, 8
0x18000ea96  or      r10d, ecx
0x18000ea99  mov     ecx, r9d
0x18000ea9c  shl     r8d, cl
0x18000ea9f  mov     ecx, r14d
0x18000eaa2  shr     r8d, cl
0x18000eaa5  mov     ecx, r9d
0x18000eaa8  shl     r10d, 8
0x18000eaac  not     r8d
0x18000eaaf  or      r10d, edx
0x18000eab2  mov     edx, r15d
0x18000eab5  shl     edx, cl
0x18000eab7  and     r10d, r8d
0x18000eaba  mov     ecx, r14d
0x18000eabd  shr     edx, cl
0x18000eabf  or      r10d, edx
0x18000eac2  mov     ecx, r10d
0x18000eac5  mov     edx, r10d
0x18000eac8  shr     ecx, 18h
0x18000eacb  mov     [rbx], cl
0x18000eacd  mov     rcx, [rax+18h]
0x18000ead1  mov     rbx, [rsp+28h+arg_0]
0x18000ead6  shr     edx, 10h
0x18000ead9  mov     [rsi+rcx], dl
0x18000eadc  mov     edx, r10d
0x18000eadf  mov     rcx, [rax+18h]
0x18000eae3  mov     rsi, [rsp+28h+arg_8]
0x18000eae8  shr     edx, 8
0x18000eaeb  mov     [rdi+rcx], dl
0x18000eaee  mov     rcx, [rax+18h]
0x18000eaf2  mov     rdi, [rsp+28h+arg_10]
0x18000eaf7  mov     [r11+rcx], r10b
0x18000eafb  lea     ecx, [r14+rbp]
0x18000eaff  mov     r14, [rsp+28h+var_20]
0x18000eb04  cmp     ecx, 20h ; ' '
0x18000eb07  jbe     short loc_18000EB46
0x18000eb09  and     ecx, 7
0x18000eb0c  mov     edx, r13d
0x18000eb0f  mov     r9d, ecx
0x18000eb12  lea     r10d, [r12+4]
0x18000eb17  and     r10, rdx
0x18000eb1a  mov     r11d, 8
0x18000eb20  add     r10, [rax+18h]
0x18000eb24  lea     rdx, BitMask
0x18000eb2b  sub     r11d, ecx
0x18000eb2e  movzx   edx, byte ptr [rdx+r9*4]
0x18000eb33  mov     ecx, r11d
0x18000eb36  shl     dl, cl
0x18000eb38  not     dl
0x18000eb3a  shl     r15b, cl
0x18000eb3d  and     dl, [r10]
0x18000eb40  or      dl, r15b
0x18000eb43  mov     [r10], dl
0x18000eb46  mov     r13, [rsp+28h+var_18]
0x18000eb4b  mov     r12, [rsp+28h+var_10]
0x18000eb50  mov     r15, [rsp+28h+var_28]
0x18000eb54  mov     qword ptr [rax], 0
0x18000eb5b  jmp     loc_18000E9DB
```

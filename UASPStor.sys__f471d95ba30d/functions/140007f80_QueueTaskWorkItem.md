# QueueTaskWorkItem

- ea: `0x140007f80`
- end: `0x1400081d3`
- name: `QueueTaskWorkItem`
- size: `595`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x140001020`
- `0x140005358`
- `0x14000785c`
- `0x140007cc0`
- `0x140007ee4`
- `0x140007f80`
- `0x140009b78`

## import_xrefs

- `storport!StorPortNotification` at `0x1400080d2`
- `storport!StorPortNotification` at `0x1400080d2`

## pseudocode

```c
__int64 __fastcall QueueTaskWorkItem(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rdi
  __int64 v3; // r14
  __int64 v4; // rcx
  int NextFree; // eax
  __int64 v7; // r9
  char v8; // bp
  __int64 v9; // r12
  __int64 v10; // rsi
  __int16 v11; // r13
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rax
  int v17; // r9d
  int v18; // eax
  __int64 v20; // [rsp+50h] [rbp-48h]
  unsigned __int16 v21; // [rsp+A8h] [rbp+10h] BYREF
  int v22; // [rsp+B0h] [rbp+18h]
  __int64 v23; // [rsp+B8h] [rbp+20h]

  v2 = *a2;
  v3 = a2[1];
  v4 = *a2;
  v21 = 0;
  v22 = *((_DWORD *)a2 + 4);
  QueueCancel(v4);
  NextFree = QueueFindNextFree(v2, &v21, v3, 0);
  if ( NextFree >= 0 || NextFree == -2147483631 && (LOBYTE(v7) = 1, (int)QueueFindNextFree(v2, &v21, v3, v7) >= 0) )
  {
    v8 = 4;
    v9 = v21;
    v10 = 224LL * v21 + *(_QWORD *)(v2 + 1176);
    v20 = 224LL * v21;
    v11 = __ROR2__(v21 + 1, 8);
    *(_DWORD *)(v10 + 24) = 2;
    *(_QWORD *)(v10 + 32) = v3;
    v23 = *(_QWORD *)(v2 + 1208);
    v12 = **(_QWORD **)(v10 + 208);
    *(_BYTE *)v12 = 4;
    *(_WORD *)(v12 + 2) = v11;
    *(_DWORD *)(v10 + 16) = 2;
    a2[1] = 0;
    if ( (int)IssueBulkRequest(
                v2,
                v10,
                3,
                (unsigned __int16)v9,
                v12,
                0,
                1024,
                1,
                (unsigned __int64)ResponseIUCompletion & -(__int64)(*(_BYTE *)(v2 + 986) != 0)) >= 0 )
    {
      v13 = 16 * v9 + v23;
      *(_BYTE *)v13 = 5;
      v14 = *(_QWORD *)(v2 + 1128);
      v15 = *(unsigned __int8 *)(v3 + 7);
      if ( v14 )
        v16 = *(_QWORD *)(32 * v15 + v14);
      else
        v16 = _byteswap_uint64(v15);
      v17 = v21;
      *(_QWORD *)(v13 + 8) = v16;
      *(_BYTE *)(v13 + 4) = v22;
      *(_WORD *)(v13 + 6) = 0;
      *(_WORD *)(v13 + 2) = v11;
      *(_DWORD *)(v10 + 8) = 2;
      v18 = IssueBulkRequest(v2, v10, 1, v17, v13, 0, 16, 0, (__int64)TaskIUCompletion);
      if ( v18 < 0 )
      {
        if ( v18 == -1073741810 )
        {
          v8 = 14;
        }
        else if ( v18 == -1073741764 )
        {
          v8 = 18;
        }
        *(_BYTE *)(v3 + 3) = v8;
        CancelStatusIrp(*(_QWORD *)(v2 + 1176) + v20);
      }
    }
    else
    {
      *(_BYTE *)(*(_QWORD *)(v10 + 32) + 3LL) = 4;
      StorPortNotification(0, v2, *(_QWORD *)(v10 + 32));
      QueueReleaseEntry(v10);
    }
  }
  return UaspCompleteWorkItem(a2);
}

```

## disassembly

```asm
0x140007f80  mov     r11, rsp
0x140007f83  mov     [r11+8], rbx
0x140007f87  push    rbp
0x140007f88  push    rsi
0x140007f89  push    rdi
0x140007f8a  push    r12
0x140007f8c  push    r13
0x140007f8e  push    r14
0x140007f90  push    r15
0x140007f92  sub     rsp, 60h
0x140007f96  mov     rdi, [rdx]
0x140007f99  xor     eax, eax
0x140007f9b  mov     r14, [rdx+8]
0x140007f9f  mov     rcx, rdi
0x140007fa2  mov     [r11+10h], ax
0x140007fa7  mov     r15, rdx
0x140007faa  mov     eax, [rdx+10h]
0x140007fad  mov     [rsp+98h+arg_10], eax
0x140007fb4  call    QueueCancel
0x140007fb9  xor     r9d, r9d
0x140007fbc  lea     rdx, [rsp+98h+arg_8]
0x140007fc4  mov     r8, r14
0x140007fc7  mov     rcx, rdi
0x140007fca  call    QueueFindNextFree
0x140007fcf  mov     ebx, eax
0x140007fd1  mov     r10d, 1
0x140007fd7  test    eax, eax
0x140007fd9  jns     short loc_14000800C
0x140007fdb  cmp     eax, 80000011h
0x140007fe0  jnz     loc_1400081B0
0x140007fe6  mov     r9b, r10b
0x140007fe9  lea     rdx, [rsp+98h+arg_8]
0x140007ff1  mov     r8, r14
0x140007ff4  mov     rcx, rdi
0x140007ff7  call    QueueFindNextFree
0x140007ffc  mov     ebx, eax
0x140007ffe  test    eax, eax
0x140008000  js      loc_1400081B0
0x140008006  mov     r10d, 1
0x14000800c  mov     rsi, [rdi+498h]
0x140008013  lea     r9, ResponseIUCompletion
0x14000801a  movzx   edx, [rsp+98h+arg_8]
0x140008022  mov     bpl, 4
0x140008025  imul    rcx, rdx, 0E0h
0x14000802c  lea     r13d, [r10+rdx]
0x140008030  mov     r12d, edx
0x140008033  add     rsi, rcx
0x140008036  mov     [rsp+98h+var_48], rcx
0x14000803b  mov     ecx, 2
0x140008040  ror     r13w, 8
0x140008045  mov     [rsi+18h], ecx
0x140008048  mov     [rsi+20h], r14
0x14000804c  mov     rax, [rdi+4B8h]
0x140008053  mov     [rsp+98h+arg_18], rax
0x14000805b  mov     rax, [rsi+0D0h]
0x140008062  mov     r8, [rax]
0x140008065  mov     [r8], bpl
0x140008068  mov     [r8+2], r13w
0x14000806d  mov     [rsi+10h], ecx
0x140008070  mov     qword ptr [r15+8], 0
0x140008078  mov     al, [rdi+3DAh]
0x14000807e  neg     al
0x140008080  sbb     rcx, rcx
0x140008083  and     rcx, r9
0x140008086  movzx   r9d, dx
0x14000808a  mov     [rsp+98h+var_58], rcx
0x14000808f  mov     rdx, rsi
0x140008092  mov     [rsp+98h+var_60], r10d
0x140008097  mov     rcx, rdi
0x14000809a  mov     [rsp+98h+var_68], 400h
0x1400080a2  mov     [rsp+98h+var_70], 0
0x1400080ab  mov     [rsp+98h+var_78], r8
0x1400080b0  mov     r8d, 3
0x1400080b6  call    IssueBulkRequest
0x1400080bb  mov     ebx, eax
0x1400080bd  test    eax, eax
0x1400080bf  jns     short loc_1400080EB
0x1400080c1  mov     rax, [rsi+20h]
0x1400080c5  mov     rdx, rdi
0x1400080c8  xor     ecx, ecx
0x1400080ca  mov     [rax+3], bpl
0x1400080ce  mov     r8, [rsi+20h]
0x1400080d2  call    cs:__imp_StorPortNotification
0x1400080d9  nop     dword ptr [rax+rax+00h]
0x1400080de  mov     rcx, rsi
0x1400080e1  call    QueueReleaseEntry
0x1400080e6  jmp     loc_1400081B0
0x1400080eb  mov     rcx, [rsp+98h+arg_18]
0x1400080f3  shl     r12, 4
0x1400080f7  add     rcx, r12
0x1400080fa  mov     byte ptr [rcx], 5
0x1400080fd  mov     rdx, [rdi+468h]
0x140008104  movzx   eax, byte ptr [r14+7]
0x140008109  test    rdx, rdx
0x14000810c  jz      short loc_140008118
0x14000810e  shl     rax, 5
0x140008112  mov     rax, [rax+rdx]
0x140008116  jmp     short loc_14000811B
0x140008118  bswap   rax
0x14000811b  movzx   r9d, [rsp+98h+arg_8]
0x140008124  mov     r8d, 1
0x14000812a  mov     [rcx+8], rax
0x14000812e  mov     rdx, rsi
0x140008131  mov     eax, [rsp+98h+arg_10]
0x140008138  mov     [rcx+4], al
0x14000813b  xor     eax, eax
0x14000813d  mov     [rcx+6], ax
0x140008141  lea     rax, TaskIUCompletion
0x140008148  mov     [rsp+98h+var_58], rax
0x14000814d  mov     [rsp+98h+var_60], 0
0x140008155  mov     [rcx+2], r13w
0x14000815a  mov     [rsp+98h+var_68], 10h
0x140008162  mov     [rsp+98h+var_70], 0
0x14000816b  mov     [rsp+98h+var_78], rcx
0x140008170  mov     rcx, rdi
0x140008173  mov     dword ptr [rsi+8], 2
0x14000817a  call    IssueBulkRequest
0x14000817f  mov     ebx, eax
0x140008181  test    eax, eax
0x140008183  jns     short loc_1400081B0
0x140008185  cmp     eax, 0C000000Eh
0x14000818a  jz      short loc_140008198
0x14000818c  cmp     eax, 0C000003Ch
0x140008191  jnz     short loc_14000819B
0x140008193  mov     bpl, 12h
0x140008196  jmp     short loc_14000819B
0x140008198  mov     bpl, 0Eh
0x14000819b  mov     rcx, [rsp+98h+var_48]
0x1400081a0  mov     [r14+3], bpl
0x1400081a4  add     rcx, [rdi+498h]
0x1400081ab  call    CancelStatusIrp
0x1400081b0  mov     edx, ebx
0x1400081b2  mov     rcx, r15; P
0x1400081b5  call    UaspCompleteWorkItem
0x1400081ba  mov     rbx, [rsp+98h+arg_0]
0x1400081c2  add     rsp, 60h
0x1400081c6  pop     r15
0x1400081c8  pop     r14
0x1400081ca  pop     r13
0x1400081cc  pop     r12
0x1400081ce  pop     rdi
0x1400081cf  pop     rsi
0x1400081d0  pop     rbp
0x1400081d1  retn
```

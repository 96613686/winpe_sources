# Callback

- ea: `0x1400083f0`
- end: `0x14000855e`
- name: `Callback`
- size: `366`
- prototype: `void __stdcall(PVOID CallerContext, PMIB_UNICASTIPADDRESS_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400083f0`
- `0x140009e9c`
- `0x14000d650`

## import_xrefs

- `NDIS!NdisReleaseReadWriteLock` at `0x1400084a8`
- `NDIS!NdisReleaseReadWriteLock` at `0x140008541`
- `NDIS!NdisReleaseReadWriteLock` at `0x1400084a8`
- `NDIS!NdisReleaseReadWriteLock` at `0x140008541`
- `NDIS!NdisAcquireReadWriteLock` at `0x140008457`
- `NDIS!NdisAcquireReadWriteLock` at `0x1400084d3`
- `NDIS!NdisAcquireReadWriteLock` at `0x140008512`
- `NDIS!NdisAcquireReadWriteLock` at `0x140008457`
- `NDIS!NdisAcquireReadWriteLock` at `0x1400084d3`
- `NDIS!NdisAcquireReadWriteLock` at `0x140008512`
- `NETIO!FreeMibTable` at `0x1400084b8`
- `NETIO!FreeMibTable` at `0x1400084b8`
- `NETIO!GetUnicastIpAddressTable` at `0x140008439`
- `NETIO!GetUnicastIpAddressTable` at `0x140008439`

## pseudocode

```c
void __fastcall Callback(char *CallerContext, PMIB_UNICASTIPADDRESS_ROW Row, MIB_NOTIFICATION_TYPE NotificationType)
{
  int v5; // r8d
  int v6; // r8d
  PMIB_UNICASTIPADDRESS_TABLE v7; // r8
  __int64 i; // rbx
  __int128 v9; // xmm1
  __int128 v10; // xmm1
  __int128 v11; // xmm1
  _OWORD v12[2]; // [rsp+20h] [rbp-40h] BYREF
  _OWORD v13[2]; // [rsp+40h] [rbp-20h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+80h] [rbp+20h] BYREF
  struct _LOCK_STATE LockState; // [rsp+90h] [rbp+30h] BYREF

  Table = 0;
  LockState = 0;
  v5 = NotificationType - 1;
  if ( !v5 )
  {
    NdisAcquireReadWriteLock((PNDIS_RW_LOCK)(CallerContext + 56), 1u, &LockState);
    v11 = *(_OWORD *)(&Row->Address.si_family + 6);
    v13[0] = Row->Address.Ipv4;
    *(_OWORD *)((char *)v13 + 12) = v11;
    sub_140009E9C(CallerContext, v13);
    goto LABEL_10;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    NdisAcquireReadWriteLock((PNDIS_RW_LOCK)(CallerContext + 56), 1u, &LockState);
    v10 = *(_OWORD *)(&Row->Address.si_family + 6);
    v12[0] = Row->Address.Ipv4;
    *(_OWORD *)((char *)v12 + 12) = v10;
    sub_14000D650((__int64)CallerContext);
LABEL_10:
    NdisReleaseReadWriteLock((PNDIS_RW_LOCK)(CallerContext + 56), &LockState);
    return;
  }
  if ( v6 == 1 && !GetUnicastIpAddressTable(*(_WORD *)CallerContext, &Table) )
  {
    NdisAcquireReadWriteLock((PNDIS_RW_LOCK)(CallerContext + 56), 1u, &LockState);
    v7 = Table;
    for ( i = 0; (unsigned int)i < Table->NumEntries; i = (unsigned int)(i + 1) )
    {
      v9 = *(_OWORD *)(&v7->Table[i].Address.si_family + 6);
      v12[0] = v7->Table[i].Address.Ipv4;
      *(_OWORD *)((char *)v12 + 12) = v9;
      sub_140009E9C(CallerContext, v12);
      v7 = Table;
    }
    NdisReleaseReadWriteLock((PNDIS_RW_LOCK)(CallerContext + 56), &LockState);
    FreeMibTable(Table);
  }
}

```

## disassembly

```asm
0x1400083f0  mov     [rsp-18h+arg_8], rbx
0x1400083f5  push    rbp
0x1400083f6  push    rsi
0x1400083f7  push    rdi
0x1400083f8  mov     rbp, rsp
0x1400083fb  sub     rsp, 60h
0x1400083ff  mov     [rbp+Table], 0
0x140008407  mov     rsi, rdx
0x14000840a  mov     dword ptr [rbp+LockState.LockState], 0
0x140008411  mov     rdi, rcx
0x140008414  sub     r8d, 1
0x140008418  jz      loc_140008508
0x14000841e  sub     r8d, 1
0x140008422  jz      loc_1400084C9
0x140008428  cmp     r8d, 1
0x14000842c  jnz     loc_14000854D
0x140008432  movzx   ecx, word ptr [rcx]; Family
0x140008435  lea     rdx, [rbp+Table]; Table
0x140008439  call    cs:GetUnicastIpAddressTable
0x140008440  nop     dword ptr [rax+rax+00h]
0x140008445  test    eax, eax
0x140008447  jnz     loc_14000854D
0x14000844d  lea     r8, [rbp+LockState]; LockState
0x140008451  mov     dl, 1; fWrite
0x140008453  lea     rcx, [rdi+38h]; Lock
0x140008457  call    cs:NdisAcquireReadWriteLock
0x14000845e  nop     dword ptr [rax+rax+00h]
0x140008463  mov     r8, [rbp+Table]
0x140008467  xor     ebx, ebx
0x140008469  cmp     [r8], ebx
0x14000846c  jbe     short loc_1400084A0
0x14000846e  lea     rdx, [rbx+rbx*4]
0x140008472  mov     rcx, rdi
0x140008475  add     rdx, rdx
0x140008478  movups  xmm0, xmmword ptr [r8+rdx*8+8]
0x14000847e  movups  xmm1, xmmword ptr [r8+rdx*8+14h]
0x140008484  lea     rdx, [rbp+var_40]
0x140008488  movaps  xmmword ptr [rbp+var_40], xmm0
0x14000848c  movups  xmmword ptr [rbp+var_40+0Ch], xmm1
0x140008490  call    sub_140009E9C
0x140008495  mov     r8, [rbp+Table]
0x140008499  inc     ebx
0x14000849b  cmp     ebx, [r8]
0x14000849e  jb      short loc_14000846E
0x1400084a0  lea     rdx, [rbp+LockState]; LockState
0x1400084a4  lea     rcx, [rdi+38h]; Lock
0x1400084a8  call    cs:NdisReleaseReadWriteLock
0x1400084af  nop     dword ptr [rax+rax+00h]
0x1400084b4  mov     rcx, [rbp+Table]; Memory
0x1400084b8  call    cs:FreeMibTable
0x1400084bf  nop     dword ptr [rax+rax+00h]
0x1400084c4  jmp     loc_14000854D
0x1400084c9  lea     r8, [rbp+LockState]; LockState
0x1400084cd  mov     dl, 1; fWrite
0x1400084cf  add     rcx, 38h ; '8'; Lock
0x1400084d3  call    cs:NdisAcquireReadWriteLock
0x1400084da  nop     dword ptr [rax+rax+00h]
0x1400084df  movups  xmm0, xmmword ptr [rsi]
0x1400084e2  cmp     word ptr [rdi], 2
0x1400084e6  lea     rax, [rbp+var_40+4]
0x1400084ea  movups  xmm1, xmmword ptr [rsi+0Ch]
0x1400084ee  lea     rdx, [rbp+var_40+8]
0x1400084f2  mov     rcx, rdi
0x1400084f5  movaps  xmmword ptr [rbp+var_40], xmm0
0x1400084f9  cmovz   rdx, rax
0x1400084fd  movups  xmmword ptr [rbp+var_40+0Ch], xmm1
0x140008501  call    sub_14000D650
0x140008506  jmp     short loc_140008539
0x140008508  lea     r8, [rbp+LockState]; LockState
0x14000850c  mov     dl, 1; fWrite
0x14000850e  add     rcx, 38h ; '8'; Lock
0x140008512  call    cs:NdisAcquireReadWriteLock
0x140008519  nop     dword ptr [rax+rax+00h]
0x14000851e  movups  xmm0, xmmword ptr [rsi]
0x140008521  lea     rdx, [rbp+var_20]
0x140008525  mov     rcx, rdi
0x140008528  movups  xmm1, xmmword ptr [rsi+0Ch]
0x14000852c  movaps  xmmword ptr [rbp+var_20], xmm0
0x140008530  movups  xmmword ptr [rbp+var_20+0Ch], xmm1
0x140008534  call    sub_140009E9C
0x140008539  lea     rdx, [rbp+LockState]; LockState
0x14000853d  lea     rcx, [rdi+38h]; Lock
0x140008541  call    cs:NdisReleaseReadWriteLock
0x140008548  nop     dword ptr [rax+rax+00h]
0x14000854d  mov     rbx, [rsp+60h+arg_8]
0x140008555  add     rsp, 60h
0x140008559  pop     rdi
0x14000855a  pop     rsi
0x14000855b  pop     rbp
0x14000855c  retn
```

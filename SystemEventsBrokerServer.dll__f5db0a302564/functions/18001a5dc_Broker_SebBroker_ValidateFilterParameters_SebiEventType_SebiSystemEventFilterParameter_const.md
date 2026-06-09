# Broker::SebBroker::ValidateFilterParameters(_SebiEventType,_SebiSystemEventFilterParameter const *)

- ea: `0x18001a5dc`
- end: `0x18001a7b5`
- name: `?ValidateFilterParameters@SebBroker@Broker@@CAXW4_SebiEventType@@PEBU_SebiSystemEventFilterParameter@@@Z`
- size: `473`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010560`
- `0x180011190`

## callees

- `0x1800030e0`
- `0x180005a50`
- `0x18001a5dc`
- `0x18001d9ac`

## pseudocode

```c
__int64 *__fastcall Broker::SebBroker::ValidateFilterParameters(int a1, __int64 a2)
{
  __int64 v3; // rdi
  _QWORD *v4; // r10
  __int64 *result; // rax
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  __int128 v7; // [rsp+28h] [rbp-20h]
  int v8; // [rsp+38h] [rbp-10h]

  v3 = a1;
  v4 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  result = qword_180035128;
  if ( LODWORD(qword_180035128[6 * v3]) )
  {
    if ( !a2 )
    {
      if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
        WPP_SF_d(v4[2], 95, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids, (unsigned int)v3);
      v8 = 4;
      pExceptionObject = &Broker::InvalidParameter::`vftable';
      v7 = 0;
      throw (Broker::InvalidParameter *)&pExceptionObject;
    }
  }
  else if ( !a2 )
  {
    goto LABEL_27;
  }
  if ( *(_DWORD *)a2 > 1u )
  {
    if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_(v4[2], 96, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v8 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v7 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  if ( !*(_QWORD *)(a2 + 8) || !*(_DWORD *)(a2 + 4) )
  {
    if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_(v4[2], 97, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v8 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v7 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
  if ( *(_DWORD *)(a2 + 4) > 0x1000u )
  {
    if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_(v4[2], 98, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
    v8 = 4;
    pExceptionObject = &Broker::InvalidParameter::`vftable';
    v7 = 0;
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
LABEL_27:
  if ( (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 4u )
    return (__int64 *)WPP_SF_(v4[2], 99, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18001a5dc  push    rbp
0x18001a5de  push    rbx
0x18001a5df  push    rdi
0x18001a5e0  push    r15
0x18001a5e2  mov     rbp, rsp
0x18001a5e5  sub     rsp, 48h
0x18001a5e9  mov     rbx, rdx
0x18001a5ec  movsxd  rdi, ecx
0x18001a5ef  mov     r10, cs:WPP_GLOBAL_Control
0x18001a5f6  lea     r15, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001a5fd  test    byte ptr [r10+1Ch], 1
0x18001a602  jz      short loc_18001A623
0x18001a604  cmp     byte ptr [r10+19h], 4
0x18001a609  jb      short loc_18001A623
0x18001a60b  mov     rcx, [r10+10h]
0x18001a60f  mov     edx, 5Eh ; '^'
0x18001a614  mov     r8, r15
0x18001a617  call    WPP_SF_
0x18001a61c  mov     r10, cs:WPP_GLOBAL_Control
0x18001a623  lea     rcx, [rdi+rdi*2]
0x18001a627  xor     edx, edx
0x18001a629  add     rcx, rcx
0x18001a62c  lea     rax, qword_180035128
0x18001a633  cmp     [rax+rcx*8], edx
0x18001a636  jz      short loc_18001A687
0x18001a638  test    rbx, rbx
0x18001a63b  jnz     short loc_18001A690
0x18001a63d  test    byte ptr [r10+1Ch], 1
0x18001a642  jz      short loc_18001A65D
0x18001a644  cmp     byte ptr [r10+19h], 2
0x18001a649  jb      short loc_18001A65D
0x18001a64b  mov     rcx, [r10+10h]
0x18001a64f  lea     edx, [rbx+5Fh]
0x18001a652  mov     r9d, edi
0x18001a655  mov     r8, r15
0x18001a658  call    WPP_SF_d
0x18001a65d  xorps   xmm0, xmm0
0x18001a660  mov     [rbp+var_10], 4
0x18001a667  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18001a66e  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18001a675  mov     [rbp+pExceptionObject], rax
0x18001a679  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a67d  movups  [rbp+var_20], xmm0
0x18001a681  call    _CxxThrowException_0
0x18001a687  test    rbx, rbx
0x18001a68a  jz      loc_18001A78C
0x18001a690  cmp     dword ptr [rbx], 1
0x18001a693  ja      loc_18001A743
0x18001a699  cmp     [rbx+8], rdx
0x18001a69d  jz      short loc_18001A6FA
0x18001a69f  cmp     [rbx+4], edx
0x18001a6a2  jz      short loc_18001A6FA
0x18001a6a4  cmp     dword ptr [rbx+4], 1000h
0x18001a6ab  jbe     loc_18001A78C
0x18001a6b1  test    byte ptr [r10+1Ch], 1
0x18001a6b6  jz      short loc_18001A6D0
0x18001a6b8  cmp     byte ptr [r10+19h], 2
0x18001a6bd  jb      short loc_18001A6D0
0x18001a6bf  mov     rcx, [r10+10h]
0x18001a6c3  mov     edx, 62h ; 'b'
0x18001a6c8  mov     r8, r15
0x18001a6cb  call    WPP_SF_
0x18001a6d0  xorps   xmm0, xmm0
0x18001a6d3  mov     [rbp+var_10], 4
0x18001a6da  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18001a6e1  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18001a6e8  mov     [rbp+pExceptionObject], rax
0x18001a6ec  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a6f0  movups  [rbp+var_20], xmm0
0x18001a6f4  call    _CxxThrowException_0
0x18001a6fa  test    byte ptr [r10+1Ch], 1
0x18001a6ff  jz      short loc_18001A719
0x18001a701  cmp     byte ptr [r10+19h], 2
0x18001a706  jb      short loc_18001A719
0x18001a708  mov     rcx, [r10+10h]
0x18001a70c  mov     edx, 61h ; 'a'
0x18001a711  mov     r8, r15
0x18001a714  call    WPP_SF_
0x18001a719  xorps   xmm0, xmm0
0x18001a71c  mov     [rbp+var_10], 4
0x18001a723  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18001a72a  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18001a731  mov     [rbp+pExceptionObject], rax
0x18001a735  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a739  movups  [rbp+var_20], xmm0
0x18001a73d  call    _CxxThrowException_0
0x18001a743  test    byte ptr [r10+1Ch], 1
0x18001a748  jz      short loc_18001A762
0x18001a74a  cmp     byte ptr [r10+19h], 2
0x18001a74f  jb      short loc_18001A762
0x18001a751  mov     rcx, [r10+10h]
0x18001a755  mov     edx, 60h ; '`'
0x18001a75a  mov     r8, r15
0x18001a75d  call    WPP_SF_
0x18001a762  xorps   xmm0, xmm0
0x18001a765  mov     [rbp+var_10], 4
0x18001a76c  lea     rax, ??_7InvalidParameter@Broker@@6B@; const Broker::InvalidParameter::`vftable'
0x18001a773  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x18001a77a  mov     [rbp+pExceptionObject], rax
0x18001a77e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18001a782  movups  [rbp+var_20], xmm0
0x18001a786  call    _CxxThrowException_0
0x18001a78c  test    byte ptr [r10+1Ch], 1
0x18001a791  jz      short loc_18001A7AB
0x18001a793  cmp     byte ptr [r10+19h], 4
0x18001a798  jb      short loc_18001A7AB
0x18001a79a  mov     rcx, [r10+10h]
0x18001a79e  mov     edx, 63h ; 'c'
0x18001a7a3  mov     r8, r15
0x18001a7a6  call    WPP_SF_
0x18001a7ab  add     rsp, 48h
0x18001a7af  pop     r15
0x18001a7b1  pop     rdi
0x18001a7b2  pop     rbx
0x18001a7b3  pop     rbp
0x18001a7b4  retn
```

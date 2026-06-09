# ATL::CRBTree<ulong,ulong,ATL::CElementTraits<ulong>,ATL::CElementTraits<ulong>>::Find(ulong)

- ea: `0x180003e94`
- end: `0x180003f28`
- name: `?Find@?$CRBTree@KKV?$CElementTraits@K@ATL@@V12@@ATL@@IEBAPEAVCNode@12@K@Z`
- size: `148`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003550`
- `0x180003aec`
- `0x180003c38`
- `0x1800064f0`

## callees

- `0x180003e94`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<unsigned long,unsigned long,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<unsigned long>>::Find(
        __int64 *a1,
        unsigned int a2)
{
  __int64 v2; // rax
  __int64 v4; // r9
  __int64 v5; // r8
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  char v10; // dl

  v2 = *a1;
  v4 = a1[5];
  v5 = 0;
  while ( v2 != v4 )
  {
    if ( v5 )
      goto LABEL_11;
    if ( a2 < *(_DWORD *)v2 )
    {
      v2 = *(_QWORD *)(v2 + 16);
    }
    else if ( a2 == *(_DWORD *)v2 )
    {
      v5 = v2;
    }
    else
    {
      v2 = *(_QWORD *)(v2 + 24);
    }
  }
  if ( !v5 )
    return 0;
  while ( 1 )
  {
LABEL_11:
    v7 = *(_QWORD *)(v5 + 16);
    if ( v7 == v4 )
    {
      v8 = *(_QWORD *)(v5 + 32);
      v9 = v5;
      while ( v8 != v4 )
      {
        if ( v9 != *(_QWORD *)(v8 + 16) )
        {
          v10 = 0;
          goto LABEL_21;
        }
        v9 = v8;
        v8 = *(_QWORD *)(v8 + 32);
      }
      v10 = 1;
LABEL_21:
      v7 = 0;
      if ( !v10 )
        v7 = v8;
    }
    else if ( v7 )
    {
      while ( *(_QWORD *)(v7 + 24) != v4 )
        v7 = *(_QWORD *)(v7 + 24);
    }
    if ( !v7 || a2 != *(_DWORD *)v7 )
      return v5;
    v5 = v7;
  }
}

```

## disassembly

```asm
0x180003e94  mov     rax, [rcx]
0x180003e97  mov     r10d, edx
0x180003e9a  mov     r9, [rcx+28h]
0x180003e9e  xor     r8d, r8d
0x180003ea1  cmp     rax, r9
0x180003ea4  jz      short loc_180003EC3
0x180003ea6  test    r8, r8
0x180003ea9  jnz     short loc_180003ED0
0x180003eab  cmp     r10d, [rax]
0x180003eae  jb      short loc_180003EBD
0x180003eb0  jnz     short loc_180003EB7
0x180003eb2  mov     r8, rax
0x180003eb5  jmp     short loc_180003EA1
0x180003eb7  mov     rax, [rax+18h]
0x180003ebb  jmp     short loc_180003EA1
0x180003ebd  mov     rax, [rax+10h]
0x180003ec1  jmp     short loc_180003EA1
0x180003ec3  test    r8, r8
0x180003ec6  jnz     short loc_180003ED0
0x180003ec8  xor     eax, eax
0x180003eca  retn
0x180003ecb  test    r8, r8
0x180003ece  jz      short loc_180003F24
0x180003ed0  mov     rax, [r8+10h]
0x180003ed4  cmp     rax, r9
0x180003ed7  jz      short loc_180003EEC
0x180003ed9  test    rax, rax
0x180003edc  jz      short loc_180003F15
0x180003ede  mov     rcx, [rax+18h]
0x180003ee2  cmp     rcx, r9
0x180003ee5  jz      short loc_180003F15
0x180003ee7  mov     rax, rcx
0x180003eea  jmp     short loc_180003EDE
0x180003eec  mov     rcx, [r8+20h]
0x180003ef0  mov     rax, r8
0x180003ef3  cmp     rcx, r9
0x180003ef6  jz      short loc_180003F0B
0x180003ef8  cmp     rax, [rcx+10h]
0x180003efc  jnz     short loc_180003F07
0x180003efe  mov     rax, rcx
0x180003f01  mov     rcx, [rcx+20h]
0x180003f05  jmp     short loc_180003EF3
0x180003f07  xor     dl, dl
0x180003f09  jmp     short loc_180003F0D
0x180003f0b  mov     dl, 1
0x180003f0d  xor     eax, eax
0x180003f0f  test    dl, dl
0x180003f11  cmovz   rax, rcx
0x180003f15  test    rax, rax
0x180003f18  jz      short loc_180003F24
0x180003f1a  cmp     r10d, [rax]
0x180003f1d  jnz     short loc_180003F24
0x180003f1f  mov     r8, rax
0x180003f22  jmp     short loc_180003ECB
0x180003f24  mov     rax, r8
0x180003f27  retn
```

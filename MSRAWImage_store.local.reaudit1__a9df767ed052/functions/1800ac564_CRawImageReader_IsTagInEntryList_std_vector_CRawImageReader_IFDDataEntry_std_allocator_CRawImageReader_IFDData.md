# CRawImageReader::IsTagInEntryList(std::vector<CRawImageReader::IFDDataEntry,std::allocator<CRawImageReader::IFDDataEntry>> *,ushort)

- ea: `0x1800ac564`
- end: `0x1800ac5f8`
- name: `?IsTagInEntryList@CRawImageReader@@AEAA_NPEAV?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@G@Z`
- size: `148`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a58b4`
- `0x1800a5b90`
- `0x1800a6a40`

## callees

- `0x1800ac564`
- `0x1800ad23c`
- `0x1800af388`

## pseudocode

```c
char __fastcall CRawImageReader::IsTagInEntryList(__int64 a1, _QWORD *a2, __int16 a3)
{
  char v3; // di
  unsigned int i; // esi
  char v8; // bl
  unsigned __int8 *v9; // rax
  unsigned __int16 v11; // [rsp+48h] [rbp+10h] BYREF

  v3 = 0;
  for ( i = 0; i < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(a2[1] - *a2) >> 3); ++i )
  {
    v8 = *(_BYTE *)(a1 + 107);
    v11 = 0;
    v9 = (unsigned __int8 *)std::vector<CRawImageReader::IFDDataEntry>::at(a2, i);
    Read2Bytes(v9, &v11, v8);
    if ( v11 == a3 )
      return 1;
  }
  return v3;
}

```

## disassembly

```asm
0x1800ac564  mov     [rsp+arg_0], rbx
0x1800ac569  mov     [rsp+arg_10], rbp
0x1800ac56e  mov     [rsp+arg_18], rsi
0x1800ac573  push    rdi
0x1800ac574  push    r14
0x1800ac576  push    r15
0x1800ac578  sub     rsp, 20h
0x1800ac57c  xor     edi, edi
0x1800ac57e  movzx   r14d, r8w
0x1800ac582  mov     esi, edi
0x1800ac584  mov     rbp, rdx
0x1800ac587  mov     r15, rcx
0x1800ac58a  mov     rax, [rbp+8]
0x1800ac58e  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1800ac598  sub     rax, [rbp+0]
0x1800ac59c  sar     rax, 3
0x1800ac5a0  imul    rax, rcx
0x1800ac5a4  mov     edx, esi
0x1800ac5a6  cmp     rdx, rax
0x1800ac5a9  jnb     short loc_1800AC5DB
0x1800ac5ab  mov     bl, [r15+6Bh]
0x1800ac5af  mov     rcx, rbp
0x1800ac5b2  mov     [rsp+38h+arg_8], di
0x1800ac5b7  call    ?at@?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@QEAAAEAUIFDDataEntry@CRawImageReader@@_K@Z; std::vector<CRawImageReader::IFDDataEntry>::at(unsigned __int64)
0x1800ac5bc  mov     r8b, bl; bool
0x1800ac5bf  lea     rdx, [rsp+38h+arg_8]; unsigned __int16 *
0x1800ac5c4  mov     rcx, rax; unsigned __int8 *
0x1800ac5c7  call    ?Read2Bytes@@YAXPEAEPEAG_N@Z; Read2Bytes(uchar *,ushort *,bool)
0x1800ac5cc  cmp     [rsp+38h+arg_8], r14w
0x1800ac5d2  jz      short loc_1800AC5D8
0x1800ac5d4  inc     esi
0x1800ac5d6  jmp     short loc_1800AC58A
0x1800ac5d8  mov     dil, 1
0x1800ac5db  mov     rbx, [rsp+38h+arg_0]
0x1800ac5e0  mov     al, dil
0x1800ac5e3  mov     rbp, [rsp+38h+arg_10]
0x1800ac5e8  mov     rsi, [rsp+38h+arg_18]
0x1800ac5ed  add     rsp, 20h
0x1800ac5f1  pop     r15
0x1800ac5f3  pop     r14
0x1800ac5f5  pop     rdi
0x1800ac5f6  retn
```

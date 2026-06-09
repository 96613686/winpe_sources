# bond::DeserializeElements<std::vector<Windows::Data::Shell::FocusSession,std::allocator<Windows::Data::Shell::FocusSession>>,bond::value<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(std::vector<Windows::Data::Shell::FocusSession,std::allocator<Windows::Data::Shell::FocusSession>> &,bond::value<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &,uint)

- ea: `0x18001b298`
- end: `0x18001b3a5`
- name: `??$DeserializeElements@V?$vector@UFocusSession@Shell@Data@Windows@@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@V?$value@UFocusSession@Shell@Data@Windows@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@bond@@YAXAEAV?$vector@UFocusSession@Shell@Data@Windows@@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@AEBV?$value@UFocusSession@Shell@Data@Windows@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@0@I@Z`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ba7c`

## callees

- `0x1800133f0`
- `0x18001aa78`
- `0x18001b298`
- `0x18001d5e8`
- `0x18001d710`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall bond::DeserializeElements<std::vector<Windows::Data::Shell::FocusSession>,bond::value<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
        __int64 *a1,
        __int64 *a2,
        unsigned int a3)
{
  __int64 v5; // r9
  unsigned __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rax
  _BYTE v11[8]; // [rsp+20h] [rbp-39h] BYREF
  __int64 v12; // [rsp+28h] [rbp-31h]
  __int64 v13; // [rsp+30h] [rbp-29h] BYREF
  __int64 v14; // [rsp+38h] [rbp-21h]
  __int64 v15; // [rsp+40h] [rbp-19h]
  __int64 v16; // [rsp+48h] [rbp-11h]
  __int64 v17; // [rsp+50h] [rbp-9h]
  _OWORD v18[2]; // [rsp+58h] [rbp-1h] BYREF
  __int64 v19; // [rsp+78h] [rbp+1Fh]
  __int16 v20; // [rsp+80h] [rbp+27h]

  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v5 = *a1;
  v6 = 0xCCCCCCCCCCCCCCCDuLL * ((a1[1] - *a1) >> 3);
  if ( a3 >= v6 )
  {
    if ( a3 > v6 )
    {
      if ( a3 <= 0xCCCCCCCCCCCCCCCDuLL * ((a1[2] - v5) >> 3) )
        a1[1] = std::_Uninitialized_fill_n<std::allocator<Windows::Data::Shell::FocusSession>>(a1[1], a3 - v6, &v13, a1);
      else
        std::vector<Windows::Data::Shell::FocusSession>::_Resize_reallocate<Windows::Data::Shell::FocusSession>(
          a1,
          a3,
          &v13);
    }
  }
  else
  {
    a1[1] = v5 + 40LL * a3;
  }
  v7 = *a1;
  v8 = a1[1];
  while ( v7 != v8 )
  {
    v9 = v7;
    v7 += 40;
    *((_BYTE *)a2 + 8) = 0;
    v10 = *a2;
    memset(v18, 0, sizeof(v18));
    v19 = v10;
    v20 = 0;
    v12 = v9;
    v13 = v10;
    LOBYTE(v14) = 0;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Shell::FocusSession::Schema,bond::To<Windows::Data::Shell::FocusSession,bond::RequiredFieldValiadator<Windows::Data::Shell::FocusSession>>>(
      &v13,
      v11);
    bond::bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>::~bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>((__int64)v18);
  }
}

```

## disassembly

```asm
0x18001b298  push    rbp
0x18001b29a  push    rbx
0x18001b29b  push    rsi
0x18001b29c  push    rdi
0x18001b29d  lea     rbp, [rsp-3Fh]
0x18001b2a2  sub     rsp, 98h
0x18001b2a9  mov     rsi, rdx
0x18001b2ac  mov     rbx, rcx
0x18001b2af  mov     [rbp+57h+var_80], 0
0x18001b2b7  mov     [rbp+57h+var_78], 0
0x18001b2bf  mov     [rbp+57h+var_70], 0
0x18001b2c7  mov     [rbp+57h+var_68], 0
0x18001b2cf  mov     [rbp+57h+var_60], 0
0x18001b2d7  mov     r9, [rcx]
0x18001b2da  mov     rcx, [rcx+8]
0x18001b2de  sub     rcx, r9
0x18001b2e1  sar     rcx, 3
0x18001b2e5  mov     r10, 0CCCCCCCCCCCCCCCDh
0x18001b2ef  imul    rcx, r10
0x18001b2f3  mov     edx, r8d
0x18001b2f6  cmp     rdx, rcx
0x18001b2f9  jnb     short loc_18001B309
0x18001b2fb  lea     rax, [rdx+rdx*4]
0x18001b2ff  lea     rcx, [r9+rax*8]
0x18001b303  mov     [rbx+8], rcx
0x18001b307  jmp     short loc_18001B340
0x18001b309  jbe     short loc_18001B340
0x18001b30b  mov     rax, [rbx+10h]
0x18001b30f  sub     rax, r9
0x18001b312  sar     rax, 3
0x18001b316  imul    rax, r10
0x18001b31a  lea     r8, [rbp+57h+var_80]
0x18001b31e  cmp     rdx, rax
0x18001b321  jbe     short loc_18001B32D
0x18001b323  mov     rcx, rbx
0x18001b326  call    ??$_Resize_reallocate@UFocusSession@Shell@Data@Windows@@@?$vector@UFocusSession@Shell@Data@Windows@@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@AEAAX_KAEBUFocusSession@Shell@Data@Windows@@@Z; std::vector<Windows::Data::Shell::FocusSession>::_Resize_reallocate<Windows::Data::Shell::FocusSession>(unsigned __int64,Windows::Data::Shell::FocusSession const &)
0x18001b32b  jmp     short loc_18001B340
0x18001b32d  sub     rdx, rcx
0x18001b330  mov     r9, rbx
0x18001b333  mov     rcx, [rbx+8]
0x18001b337  call    ??$_Uninitialized_fill_n@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@YAPEAUFocusSession@Shell@Data@Windows@@PEAU1234@_KAEBU1234@AEAV?$allocator@UFocusSession@Shell@Data@Windows@@@0@@Z; std::_Uninitialized_fill_n<std::allocator<Windows::Data::Shell::FocusSession>>(Windows::Data::Shell::FocusSession *,unsigned __int64,Windows::Data::Shell::FocusSession const &,std::allocator<Windows::Data::Shell::FocusSession> &)
0x18001b33c  mov     [rbx+8], rax
0x18001b340  mov     rdi, [rbx]
0x18001b343  mov     rbx, [rbx+8]
0x18001b347  cmp     rdi, rbx
0x18001b34a  jz      short loc_18001B399
0x18001b34c  mov     rcx, rdi
0x18001b34f  add     rdi, 28h ; '('
0x18001b353  mov     byte ptr [rsi+8], 0
0x18001b357  mov     rax, [rsi]
0x18001b35a  xorps   xmm0, xmm0
0x18001b35d  movdqu  [rbp+57h+var_58], xmm0
0x18001b362  xorps   xmm1, xmm1
0x18001b365  movdqu  [rbp+57h+var_48], xmm1
0x18001b36a  mov     [rbp+57h+var_38], rax
0x18001b36e  mov     [rbp+57h+var_30], 0
0x18001b374  mov     [rbp+57h+var_88], rcx
0x18001b378  mov     [rbp+57h+var_80], rax
0x18001b37c  mov     byte ptr [rbp+57h+var_78], 0
0x18001b380  lea     rdx, [rbp+57h+var_90]
0x18001b384  lea     rcx, [rbp+57h+var_80]
0x18001b388  call    ??$Apply@USchema@FocusSession@Shell@Data@Windows@@V?$To@UFocusSession@Shell@Data@Windows@@V?$RequiredFieldValiadator@UFocusSession@Shell@Data@Windows@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA_NAEBV?$To@UFocusSession@Shell@Data@Windows@@V?$RequiredFieldValiadator@UFocusSession@Shell@Data@Windows@@@bond@@@1@AEBUSchema@FocusSession@Shell@Data@Windows@@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Shell::FocusSession::Schema,bond::To<Windows::Data::Shell::FocusSession,bond::RequiredFieldValiadator<Windows::Data::Shell::FocusSession>>>(bond::To<Windows::Data::Shell::FocusSession,bond::RequiredFieldValiadator<Windows::Data::Shell::FocusSession>> const &,Windows::Data::Shell::FocusSession::Schema const &)
0x18001b38d  nop
0x18001b38e  lea     rcx, [rbp+57h+var_58]
0x18001b392  call    ??1?$bonded@UFocusSession@Shell@Data@Windows@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>::~bonded<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001b397  jmp     short loc_18001B347
0x18001b399  add     rsp, 98h
0x18001b3a0  pop     rdi
0x18001b3a1  pop     rsi
0x18001b3a2  pop     rbx
0x18001b3a3  pop     rbp
0x18001b3a4  retn
```

# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)

- ea: `0x180011d4c`
- end: `0x180011e16`
- name: `?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z`
- size: `202`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011820`

## callees

- `0x1800053a8`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5,
        int a6)
{
  int v7; // [rsp+20h] [rbp-A8h]
  int v8; // [rsp+28h] [rbp-A0h]
  int v9; // [rsp+30h] [rbp-98h]
  int v10; // [rsp+38h] [rbp-90h]
  int v11; // [rsp+40h] [rbp-88h]
  int v12; // [rsp+48h] [rbp-80h]
  int v13; // [rsp+50h] [rbp-78h]
  int v14; // [rsp+58h] [rbp-70h]
  int v15; // [rsp+60h] [rbp-68h]
  int v16; // [rsp+68h] [rbp-60h]
  int v17; // [rsp+70h] [rbp-58h]

  v17 = *((unsigned __int8 *)a5 + 15);
  v16 = *((unsigned __int8 *)a5 + 14);
  v15 = *((unsigned __int8 *)a5 + 13);
  v14 = *((unsigned __int8 *)a5 + 12);
  v13 = *((unsigned __int8 *)a5 + 11);
  v12 = *((unsigned __int8 *)a5 + 10);
  v11 = *((unsigned __int8 *)a5 + 9);
  v10 = *((unsigned __int8 *)a5 + 8);
  v9 = *((unsigned __int16 *)a5 + 3);
  v8 = *((unsigned __int16 *)a5 + 2);
  v7 = *a5;
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
           a2,
           L"%ws\\%hs\\%08x%04x%04x%02x%02x%02x%02x%02x%02x%02x%02x%x",
           a3,
           a4,
           v7,
           v8,
           v9,
           v10,
           v11,
           v12,
           v13,
           v14,
           v15,
           v16,
           v17,
           a6);
}

```

## disassembly

```asm
0x180011d4c  mov     [rsp+arg_8], rdx
0x180011d51  push    rbx
0x180011d52  push    rbp
0x180011d53  push    rsi
0x180011d54  push    rdi
0x180011d55  push    r12
0x180011d57  push    r13
0x180011d59  push    r14
0x180011d5b  push    r15
0x180011d5d  sub     rsp, 88h
0x180011d64  mov     r12, [rsp+0C8h+arg_20]
0x180011d6c  lea     rdx, aWsHs08x04x04x0; "%ws\\%hs\\%08x%04x%04x%02x%02x%02x%02x%"...
0x180011d73  mov     eax, [rsp+0C8h+arg_28]
0x180011d7a  mov     r13, r9
0x180011d7d  mov     [rsp+0C8h+var_50], eax
0x180011d81  movzx   ecx, byte ptr [r12+0Fh]
0x180011d87  movzx   r9d, word ptr [r12+4]
0x180011d8d  movzx   r10d, byte ptr [r12+0Eh]
0x180011d93  movzx   r11d, byte ptr [r12+0Dh]
0x180011d99  movzx   ebx, byte ptr [r12+0Ch]
0x180011d9f  movzx   edi, byte ptr [r12+0Bh]
0x180011da5  movzx   esi, byte ptr [r12+0Ah]
0x180011dab  movzx   ebp, byte ptr [r12+9]
0x180011db1  movzx   r14d, byte ptr [r12+8]
0x180011db7  movzx   r15d, word ptr [r12+6]
0x180011dbd  mov     eax, [r12]
0x180011dc1  mov     [rsp+0C8h+var_58], ecx
0x180011dc5  mov     rcx, [rsp+0C8h+arg_8]
0x180011dcd  mov     [rsp+0C8h+var_60], r10d
0x180011dd2  mov     [rsp+0C8h+var_68], r11d
0x180011dd7  mov     [rsp+0C8h+var_70], ebx
0x180011ddb  mov     [rsp+0C8h+var_78], edi
0x180011ddf  mov     [rsp+0C8h+var_80], esi
0x180011de3  mov     [rsp+0C8h+var_88], ebp
0x180011de7  mov     [rsp+0C8h+var_90], r14d
0x180011dec  mov     [rsp+0C8h+var_98], r15d
0x180011df1  mov     [rsp+0C8h+var_A0], r9d
0x180011df6  mov     r9, r13
0x180011df9  mov     [rsp+0C8h+var_A8], eax
0x180011dfd  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180011e02  add     rsp, 88h
0x180011e09  pop     r15
0x180011e0b  pop     r14
0x180011e0d  pop     r13
0x180011e0f  pop     r12
0x180011e11  pop     rdi
0x180011e12  pop     rsi
0x180011e13  pop     rbp
0x180011e14  pop     rbx
0x180011e15  retn
```

# Microsoft::Windows::Performance::CImageIdEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_GUID const &,ulong)

- ea: `0x18000bbb4`
- end: `0x18000bc96`
- name: `?CreatePathToPdbFromStoreRoot@CImageIdEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_GUID@@K@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bc98`

## callees

- `0x180012df4`

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
  int v7; // [rsp+20h] [rbp-88h]
  int v8; // [rsp+28h] [rbp-80h]
  int v9; // [rsp+30h] [rbp-78h]
  int v10; // [rsp+38h] [rbp-70h]
  int v11; // [rsp+40h] [rbp-68h]
  int v12; // [rsp+48h] [rbp-60h]
  int v13; // [rsp+50h] [rbp-58h]
  int v14; // [rsp+58h] [rbp-50h]
  int v15; // [rsp+60h] [rbp-48h]
  int v16; // [rsp+68h] [rbp-40h]
  int v17; // [rsp+70h] [rbp-38h]

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
0x18000bbb4  mov     rax, rsp
0x18000bbb7  mov     [rax+8], rbx
0x18000bbbb  mov     [rax+18h], rbp
0x18000bbbf  mov     [rax+20h], rsi
0x18000bbc3  mov     [rax+10h], rdx
0x18000bbc7  push    rdi
0x18000bbc8  push    r12
0x18000bbca  push    r13
0x18000bbcc  push    r14
0x18000bbce  push    r15
0x18000bbd0  sub     rsp, 80h
0x18000bbd7  mov     r12, [rsp+0A8h+arg_20]
0x18000bbdf  lea     rdx, aWsHs08x04x04x0; "%ws\\%hs\\%08x%04x%04x%02x%02x%02x%02x%"...
0x18000bbe6  mov     eax, [rsp+0A8h+arg_28]
0x18000bbed  mov     r13, r9
0x18000bbf0  mov     [rsp+0A8h+var_30], eax
0x18000bbf4  movzx   ecx, byte ptr [r12+0Fh]
0x18000bbfa  movzx   r9d, word ptr [r12+4]
0x18000bc00  movzx   r10d, byte ptr [r12+0Eh]
0x18000bc06  movzx   r11d, byte ptr [r12+0Dh]
0x18000bc0c  movzx   ebx, byte ptr [r12+0Ch]
0x18000bc12  movzx   edi, byte ptr [r12+0Bh]
0x18000bc18  movzx   esi, byte ptr [r12+0Ah]
0x18000bc1e  movzx   ebp, byte ptr [r12+9]
0x18000bc24  movzx   r14d, byte ptr [r12+8]
0x18000bc2a  movzx   r15d, word ptr [r12+6]
0x18000bc30  mov     eax, [r12]
0x18000bc34  mov     [rsp+0A8h+var_38], ecx
0x18000bc38  mov     rcx, [rsp+0A8h+arg_8]
0x18000bc40  mov     [rsp+0A8h+var_40], r10d
0x18000bc45  mov     [rsp+0A8h+var_48], r11d
0x18000bc4a  mov     [rsp+0A8h+var_50], ebx
0x18000bc4e  mov     [rsp+0A8h+var_58], edi
0x18000bc52  mov     [rsp+0A8h+var_60], esi
0x18000bc56  mov     [rsp+0A8h+var_68], ebp
0x18000bc5a  mov     [rsp+0A8h+var_70], r14d
0x18000bc5f  mov     [rsp+0A8h+var_78], r15d
0x18000bc64  mov     [rsp+0A8h+var_80], r9d
0x18000bc69  mov     r9, r13
0x18000bc6c  mov     [rsp+0A8h+var_88], eax
0x18000bc70  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18000bc75  lea     r11, [rsp+0A8h+var_28]
0x18000bc7d  mov     rbx, [r11+30h]
0x18000bc81  mov     rbp, [r11+40h]
0x18000bc85  mov     rsi, [r11+48h]
0x18000bc89  mov     rsp, r11
0x18000bc8c  pop     r15
0x18000bc8e  pop     r14
0x18000bc90  pop     r13
0x18000bc92  pop     r12
0x18000bc94  pop     rdi
0x18000bc95  retn
```

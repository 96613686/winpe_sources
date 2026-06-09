# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)

- ea: `0x1800155bc`
- end: `0x180015691`
- name: `?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800150e8`
- `0x1800153f0`

## callees

- `0x180012df4`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v6; // [rsp+20h] [rbp-88h]
  int v7; // [rsp+28h] [rbp-80h]
  int v8; // [rsp+30h] [rbp-78h]
  int v9; // [rsp+38h] [rbp-70h]
  int v10; // [rsp+40h] [rbp-68h]
  int v11; // [rsp+48h] [rbp-60h]
  int v12; // [rsp+50h] [rbp-58h]
  int v13; // [rsp+58h] [rbp-50h]
  int v14; // [rsp+60h] [rbp-48h]
  int v15; // [rsp+68h] [rbp-40h]
  int v16; // [rsp+70h] [rbp-38h]
  int v17; // [rsp+78h] [rbp-30h]

  v17 = *(_DWORD *)(a5 + 20);
  v16 = *(unsigned __int8 *)(a5 + 19);
  v15 = *(unsigned __int8 *)(a5 + 18);
  v14 = *(unsigned __int8 *)(a5 + 17);
  v13 = *(unsigned __int8 *)(a5 + 16);
  v12 = *(unsigned __int8 *)(a5 + 15);
  v11 = *(unsigned __int8 *)(a5 + 14);
  v10 = *(unsigned __int8 *)(a5 + 13);
  v9 = *(unsigned __int8 *)(a5 + 12);
  v8 = *(unsigned __int16 *)(a5 + 10);
  v7 = *(unsigned __int16 *)(a5 + 8);
  v6 = *(_DWORD *)(a5 + 4);
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
           a2,
           L"%ws\\%hs\\%08x%04x%04x%02x%02x%02x%02x%02x%02x%02x%02x%x",
           a3,
           a4,
           v6,
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
           v17);
}

```

## disassembly

```asm
0x1800155bc  mov     rax, rsp
0x1800155bf  mov     [rax+8], rbx
0x1800155c3  mov     [rax+18h], rbp
0x1800155c7  mov     [rax+20h], rsi
0x1800155cb  mov     [rax+10h], rdx
0x1800155cf  push    rdi
0x1800155d0  push    r12
0x1800155d2  push    r13
0x1800155d4  push    r14
0x1800155d6  push    r15
0x1800155d8  sub     rsp, 80h
0x1800155df  mov     r13, [rsp+0A8h+arg_20]
0x1800155e7  lea     rdx, aWsHs08x04x04x0; "%ws\\%hs\\%08x%04x%04x%02x%02x%02x%02x%"...
0x1800155ee  mov     r12, r9
0x1800155f1  movzx   ecx, byte ptr [r13+13h]
0x1800155f6  mov     eax, [r13+14h]
0x1800155fa  movzx   r9d, word ptr [r13+8]
0x1800155ff  movzx   r10d, byte ptr [r13+12h]
0x180015604  movzx   r11d, byte ptr [r13+11h]
0x180015609  movzx   ebx, byte ptr [r13+10h]
0x18001560e  movzx   edi, byte ptr [r13+0Fh]
0x180015613  movzx   esi, byte ptr [r13+0Eh]
0x180015618  movzx   ebp, byte ptr [r13+0Dh]
0x18001561d  movzx   r14d, byte ptr [r13+0Ch]
0x180015622  movzx   r15d, word ptr [r13+0Ah]
0x180015627  mov     [rsp+0A8h+var_30], eax
0x18001562b  mov     eax, [r13+4]
0x18001562f  mov     [rsp+0A8h+var_38], ecx
0x180015633  mov     rcx, [rsp+0A8h+arg_8]
0x18001563b  mov     [rsp+0A8h+var_40], r10d
0x180015640  mov     [rsp+0A8h+var_48], r11d
0x180015645  mov     [rsp+0A8h+var_50], ebx
0x180015649  mov     [rsp+0A8h+var_58], edi
0x18001564d  mov     [rsp+0A8h+var_60], esi
0x180015651  mov     [rsp+0A8h+var_68], ebp
0x180015655  mov     [rsp+0A8h+var_70], r14d
0x18001565a  mov     [rsp+0A8h+var_78], r15d
0x18001565f  mov     [rsp+0A8h+var_80], r9d
0x180015664  mov     r9, r12
0x180015667  mov     [rsp+0A8h+var_88], eax
0x18001566b  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180015670  lea     r11, [rsp+0A8h+var_28]
0x180015678  mov     rbx, [r11+30h]
0x18001567c  mov     rbp, [r11+40h]
0x180015680  mov     rsi, [r11+48h]
0x180015684  mov     rsp, r11
0x180015687  pop     r15
0x180015689  pop     r14
0x18001568b  pop     r13
0x18001568d  pop     r12
0x18001568f  pop     rdi
0x180015690  retn
```

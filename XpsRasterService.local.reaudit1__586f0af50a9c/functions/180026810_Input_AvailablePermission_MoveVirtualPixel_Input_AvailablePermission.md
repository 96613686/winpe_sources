# Input::AvailablePermission::MoveVirtualPixel(Input::AvailablePermission &)

- ea: `0x180026810`
- end: `0x180027353`
- name: `?MoveVirtualPixel@AvailablePermission@Input@@SA_NAEAV12@@Z`
- size: `2883`
- prototype: `bool __fastcall(struct Input::AvailablePermission *this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e4b0`
- `0x180026810`
- `0x1800273b0`
- `0x1800bf3b0`

## pseudocode

```c
bool __fastcall Input::AvailablePermission::MoveVirtualPixel(struct Input::AvailablePermission *this)
{
  __int64 v2; // rcx
  int v3; // r8d
  int v4; // ecx
  __int64 v5; // rcx
  char *v6; // r9
  bool v7; // sf
  __int64 v8; // r8
  void (__fastcall *MixedProvider)(bool (__fastcall *)(struct Input::AvailablePermission *), unsigned __int64, __int64); // rax
  int v11; // [rsp+28h] [rbp-38h]
  int v12; // [rsp+50h] [rbp-10h]
  int v13; // [rsp+58h] [rbp-8h]
  int v14; // [rsp+58h] [rbp-8h]
  int v15; // [rsp+58h] [rbp-8h]
  unsigned __int8 *retaddr; // [rsp+68h] [rbp+8h]

  if ( ~(~(~(~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) | 0x1C190718)
           | ~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) ^ 0x1C190718
             | ~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) | 0x1C190718)))
         | 0x21000)
       | ~(~(~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) | 0x1C190718)
           | ~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) ^ 0x1C190718
             | ~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) | 0x1C190718)))
         ^ 0x21000
         | ~(~(~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) | 0x1C190718)
             | ~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) ^ 0x1C190718
               | ~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) | 0x1C190718)))
           | 0x21000))) == ~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) ^ 0x1C1B1718
                           | ~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) | 0x1C1B1718))
                         + ((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) ^ 0x1C1B1718
                          | ~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) ^ 0x1C1B1718
                            | ~((2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic)
                              | 0x1C1B1718)))
                         - 2311458 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic
                         - 471537432 )
    goto LABEL_17;
  v11 = 4339808 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic;
  if ( ~(~(~(~(v11 & 0x3C440A40) ^ (v11 | 0x3C440A40) | ~(~(v11 & 0x3C440A40) | v11 | 0x3C440A40)) & 0x14520)
       ^ (~(~(v11 & 0x3C440A40) ^ (v11 | 0x3C440A40) | ~(~(v11 & 0x3C440A40) | v11 | 0x3C440A40)) | 0x14520)
       | ~(~(~(~(v11 & 0x3C440A40) ^ (v11 | 0x3C440A40) | ~(~(v11 & 0x3C440A40) | v11 | 0x3C440A40)) & 0x14520)
         | ~(~(v11 & 0x3C440A40) ^ (v11 | 0x3C440A40) | ~(~(v11 & 0x3C440A40) | v11 | 0x3C440A40))
         | 0x14520)) == ~(v11 ^ 0x3C454F60 | ~(v11 | 0x3C454F60))
                      + (v11 ^ 0x3C454F60 ^ v11 & 0x3C454F60 | (v11 ^ 0x3C454F60) & v11 & 0x3C454F60)
                      - v11
                      - 1011175264 )
  {
    v2 = *(int *)((char *)Input::AvailablePermission::SwapLongTermTopic + 1);
    if ( v2 <= 0 )
    {
      if ( v2 < 0 && (__int64)&loc_1800273B4 + 1 < (__int64)(0x8000000000000000uLL - v2) )
        goto LABEL_18;
    }
    else if ( (__int64)&loc_1800273B4 + 1 > 0x7FFFFFFFFFFFFFFFLL - v2 )
    {
      goto LABEL_18;
    }
    v13 = *((unsigned __int8 *)&loc_1800273B4 + v2 + 1);
    v3 = ~(~(~((2311458 * v13) | 0x1C190718) | (2311458 * v13) & 0x1C190718) | 0x21000)
       | ~(~((2311458 * v13) | 0x1C190718) | (2311458 * v13) & 0x1C190718) & 0x21000;
    v12 = 471537432;
    v4 = 2311458 * v13;
    goto LABEL_16;
  }
  if ( (~(~((1553828 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) & 0x1581858C)
        & ((1553828 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) | 0x1581858C)
        & 0x423800)
      & (~((1553828 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) & 0x1581858C)
       & ((1553828 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) | 0x1581858C)
       | 0x423800)) == ~((1553828 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) ^ 0x15C3BD8C
                       | ~((1553828 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) | 0x15C3BD8C))
                     + ((1553828 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) ^ 0x15C3BD8C
                      | (1553828 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic) & 0x15C3BD8C)
                     - 1553828 * *(unsigned __int8 *)Input::AvailablePermission::SwapLongTermTopic
                     - 365149580 )
  {
    v5 = *((char *)Input::AvailablePermission::SwapLongTermTopic + 1);
    v6 = (char *)Input::AvailablePermission::SwapLongTermTopic + 2;
    v7 = (v5 & 0x80u) != 0LL;
    if ( (char)v5 > 0 )
    {
      if ( (__int64)v6 > 0x7FFFFFFFFFFFFFFFLL - v5 )
        goto LABEL_18;
      v7 = (v5 & 0x80u) != 0LL;
    }
    if ( !v7 || (__int64)v6 >= (__int64)(0x8000000000000000uLL - v5) )
    {
      v14 = (unsigned __int8)v6[v5];
      v3 = ~(~(~((4339808 * v14) | 0x34C0EC80) | (4339808 * v14) & 0x34C0EC80) | 0x40000)
         | ~(~((4339808 * v14) | 0x34C0EC80) | (4339808 * v14) & 0x34C0EC80) & 0x40000;
      v12 = 885320832;
      v4 = 4339808 * v14;
LABEL_16:
      if ( ~v3 == ~(v12 ^ v4 | ~(v12 | v4)) + (v12 ^ v4 | v12 & v4) - v4 - v12 )
LABEL_17:
        ++IntegralRelation::OddMap;
    }
  }
LABEL_18:
  v15 = *retaddr;
  v8 = ~(~(~(~((10055407 * v15) | 0x7A442200) | (10055407 * v15) & 0x7A442200) | 0x4474)
       | ~(~((10055407 * v15) | 0x7A442200) | (10055407 * v15) & 0x7A442200) & 0x4474u);
  if ( (_DWORD)v8 == ~((10055407 * v15) ^ 0x7A446674 | ~((10055407 * v15) | 0x7A446674))
                   + ((10055407 * v15) ^ 0x7A446674 | (10055407 * v15) & 0x7A446674)
                   - 10055407 * v15
                   - 2051303028
    || (IntegralRelation::OddMap ^ 0xF4285559) > 0xFED390A )
  {
    ++IntegralRelation::OddMap;
  }
  MixedProvider = (void (__fastcall *)(bool (__fastcall *)(struct Input::AvailablePermission *), unsigned __int64, __int64))GenerateMixedProvider(0x2F9FDFBFE0603010LL, 3240370282LL, v8);
  MixedProvider(
    Input::AvailablePermission::MoveVirtualPixel,
    (unsigned __int64)Input::AvailablePermission::MoveVirtualPixel ^ 0x18B694,
    571012);
  return Input::AvailablePermission::SwapLongTermTopic(this);
}

```

## disassembly

```asm
0x180026810  mov     [rsp-8+arg_8], rbx
0x180026815  push    rbp
0x180026816  mov     rbp, rsp
0x180026819  sub     rsp, 60h
0x18002681d  mov     rbx, rcx
0x180026820  mov     [rbp+var_18], 1C190718h
0x180026827  lea     r9, ?SwapLongTermTopic@AvailablePermission@Input@@QEAA_NXZ; Input::AvailablePermission::SwapLongTermTopic(void)
0x18002682e  movzx   eax, byte ptr [r9]
0x180026832  mov     [rbp+var_8], eax
0x180026835  mov     eax, [rbp+var_8]
0x180026838  imul    ecx, eax, 234522h
0x18002683e  mov     eax, [rbp+var_18]
0x180026841  mov     [rbp+var_30], eax
0x180026844  mov     [rbp+var_10], ecx
0x180026847  mov     eax, [rbp+var_10]
0x18002684a  mov     [rbp+var_28], eax
0x18002684d  mov     ecx, [rbp+var_28]
0x180026850  mov     eax, [rbp+var_30]
0x180026853  or      ecx, eax
0x180026855  mov     eax, [rbp+var_18]
0x180026858  not     ecx
0x18002685a  mov     [rbp+var_18], eax
0x18002685d  mov     eax, [rbp+var_10]
0x180026860  mov     [rbp+var_38], ecx
0x180026863  mov     [rbp+var_10], eax
0x180026866  mov     eax, [rbp+var_18]
0x180026869  mov     [rbp+var_30], eax
0x18002686c  mov     eax, [rbp+var_10]
0x18002686f  mov     [rbp+var_28], eax
0x180026872  mov     ecx, [rbp+var_28]
0x180026875  mov     eax, [rbp+var_30]
0x180026878  xor     ecx, eax
0x18002687a  mov     eax, [rbp+var_18]
0x18002687d  mov     [rbp+var_20], ecx
0x180026880  mov     [rbp+var_30], eax
0x180026883  mov     eax, [rbp+var_10]
0x180026886  mov     [rbp+var_28], eax
0x180026889  mov     ecx, [rbp+var_28]
0x18002688c  mov     eax, [rbp+var_30]
0x18002688f  or      ecx, eax
0x180026891  not     ecx
0x180026893  mov     [rbp+var_18], 21000h
0x18002689a  mov     [rbp+var_28], ecx
0x18002689d  mov     ecx, [rbp+var_28]
0x1800268a0  mov     eax, [rbp+var_20]
0x1800268a3  or      ecx, eax
0x1800268a5  not     ecx
0x1800268a7  mov     [rbp+var_20], ecx
0x1800268aa  mov     ecx, [rbp+var_20]
0x1800268ad  mov     eax, [rbp+var_38]
0x1800268b0  or      ecx, eax
0x1800268b2  mov     eax, [rbp+var_18]
0x1800268b5  not     ecx
0x1800268b7  mov     [rbp+var_10], ecx
0x1800268ba  mov     [rbp+var_20], eax
0x1800268bd  mov     eax, [rbp+var_10]
0x1800268c0  mov     [rbp+var_38], eax
0x1800268c3  mov     ecx, [rbp+var_38]
0x1800268c6  mov     eax, [rbp+var_20]
0x1800268c9  or      ecx, eax
0x1800268cb  mov     eax, [rbp+var_18]
0x1800268ce  not     ecx
0x1800268d0  mov     [rbp+var_18], eax
0x1800268d3  mov     eax, [rbp+var_10]
0x1800268d6  mov     [rbp+var_10], eax
0x1800268d9  mov     eax, [rbp+var_18]
0x1800268dc  mov     [rbp+var_20], eax
0x1800268df  mov     eax, [rbp+var_10]
0x1800268e2  mov     [rbp+var_38], eax
0x1800268e5  mov     [rbp+var_30], ecx
0x1800268e8  mov     ecx, [rbp+var_38]
0x1800268eb  mov     eax, [rbp+var_20]
0x1800268ee  xor     ecx, eax
0x1800268f0  mov     eax, [rbp+var_18]
0x1800268f3  mov     [rbp+var_28], ecx
0x1800268f6  mov     [rbp+var_20], eax
0x1800268f9  mov     eax, [rbp+var_10]
0x1800268fc  mov     [rbp+var_38], eax
0x1800268ff  mov     ecx, [rbp+var_38]
0x180026902  mov     eax, [rbp+var_20]
0x180026905  or      ecx, eax
0x180026907  not     ecx
0x180026909  mov     [rbp+var_38], ecx
0x18002690c  mov     ecx, [rbp+var_38]
0x18002690f  mov     eax, [rbp+var_28]
0x180026912  or      ecx, eax
0x180026914  mov     [rbp+var_18], 1C190718h
0x18002691b  not     ecx
0x18002691d  mov     [rbp+var_10], 21000h
0x180026924  mov     [rbp+var_38], ecx
0x180026927  mov     r8d, [rbp+var_38]
0x18002692b  mov     eax, [rbp+var_30]
0x18002692e  or      r8d, eax
0x180026931  mov     eax, [rbp+var_18]
0x180026934  not     r8d
0x180026937  mov     [rbp+var_20], eax
0x18002693a  mov     eax, [rbp+var_10]
0x18002693d  mov     [rbp+var_38], eax
0x180026940  mov     ecx, [rbp+var_38]
0x180026943  mov     eax, [rbp+var_20]
0x180026946  or      ecx, eax
0x180026948  mov     eax, [rbp+var_18]
0x18002694b  not     ecx
0x18002694d  mov     [rbp+var_18], eax
0x180026950  mov     eax, [rbp+var_10]
0x180026953  mov     [rbp+var_10], eax
0x180026956  mov     eax, [rbp+var_18]
0x180026959  mov     [rbp+var_20], eax
0x18002695c  mov     eax, [rbp+var_10]
0x18002695f  mov     [rbp+var_38], eax
0x180026962  mov     [rbp+var_30], ecx
0x180026965  mov     ecx, [rbp+var_38]
0x180026968  mov     eax, [rbp+var_20]
0x18002696b  xor     ecx, eax
0x18002696d  mov     eax, [rbp+var_18]
0x180026970  mov     [rbp+var_20], eax
0x180026973  mov     eax, [rbp+var_10]
0x180026976  mov     [rbp+var_38], eax
0x180026979  mov     [rbp+var_28], ecx
0x18002697c  mov     ecx, [rbp+var_38]
0x18002697f  mov     eax, [rbp+var_20]
0x180026982  or      ecx, eax
0x180026984  not     ecx
0x180026986  mov     [rbp+var_38], ecx
0x180026989  mov     ecx, [rbp+var_38]
0x18002698c  mov     eax, [rbp+var_28]
0x18002698f  or      ecx, eax
0x180026991  not     ecx
0x180026993  mov     [rbp+var_38], ecx
0x180026996  mov     ecx, [rbp+var_38]
0x180026999  mov     eax, [rbp+var_30]
0x18002699c  or      ecx, eax
0x18002699e  mov     eax, [rbp+var_8]
0x1800269a1  not     ecx
0x1800269a3  mov     [rbp+var_18], ecx
0x1800269a6  imul    ecx, eax, 234522h
0x1800269ac  mov     eax, [rbp+var_18]
0x1800269af  mov     [rbp+var_8], eax
0x1800269b2  mov     [rbp+var_10], ecx
0x1800269b5  mov     eax, [rbp+var_10]
0x1800269b8  mov     [rbp+var_30], eax
0x1800269bb  mov     eax, [rbp+var_8]
0x1800269be  mov     [rbp+var_20], eax
0x1800269c1  mov     eax, [rbp+var_30]
0x1800269c4  mov     [rbp+var_38], eax
0x1800269c7  mov     ecx, [rbp+var_38]
0x1800269ca  mov     eax, [rbp+var_20]
0x1800269cd  xor     ecx, eax
0x1800269cf  mov     eax, [rbp+var_8]
0x1800269d2  mov     [rbp+var_8], eax
0x1800269d5  mov     eax, [rbp+var_30]
0x1800269d8  mov     [rbp+var_30], eax
0x1800269db  mov     eax, [rbp+var_8]
0x1800269de  mov     [rbp+var_20], eax
0x1800269e1  mov     eax, [rbp+var_30]
0x1800269e4  mov     [rbp+var_38], eax
0x1800269e7  mov     [rbp+var_40], ecx
0x1800269ea  mov     ecx, [rbp+var_38]
0x1800269ed  mov     eax, [rbp+var_20]
0x1800269f0  xor     ecx, eax
0x1800269f2  mov     eax, [rbp+var_8]
0x1800269f5  mov     [rbp+var_20], eax
0x1800269f8  mov     eax, [rbp+var_30]
0x1800269fb  mov     [rbp+var_38], eax
0x1800269fe  mov     [rbp+var_28], ecx
0x180026a01  mov     ecx, [rbp+var_38]
0x180026a04  mov     eax, [rbp+var_20]
0x180026a07  or      ecx, eax
0x180026a09  not     ecx
0x180026a0b  mov     [rbp+var_38], ecx
0x180026a0e  mov     ecx, [rbp+var_38]
0x180026a11  mov     eax, [rbp+var_28]
0x180026a14  or      ecx, eax
0x180026a16  not     ecx
0x180026a18  mov     [rbp+var_38], ecx
0x180026a1b  mov     edx, [rbp+var_38]
0x180026a1e  mov     eax, [rbp+var_40]
0x180026a21  or      edx, eax
0x180026a23  mov     eax, [rbp+var_18]
0x180026a26  mov     [rbp+var_30], eax
0x180026a29  mov     eax, [rbp+var_10]
0x180026a2c  mov     [rbp+var_8], eax
0x180026a2f  mov     eax, [rbp+var_30]
0x180026a32  mov     [rbp+var_38], eax
0x180026a35  mov     eax, [rbp+var_8]
0x180026a38  mov     [rbp+var_40], eax
0x180026a3b  mov     ecx, [rbp+var_40]
0x180026a3e  mov     eax, [rbp+var_38]
0x180026a41  xor     ecx, eax
0x180026a43  mov     eax, [rbp+var_30]
0x180026a46  mov     [rbp+var_20], ecx
0x180026a49  mov     [rbp+var_38], eax
0x180026a4c  mov     eax, [rbp+var_8]
0x180026a4f  mov     [rbp+var_40], eax
0x180026a52  mov     ecx, [rbp+var_40]
0x180026a55  mov     eax, [rbp+var_38]
0x180026a58  or      ecx, eax
0x180026a5a  not     ecx
0x180026a5c  mov     [rbp+var_40], ecx
0x180026a5f  mov     ecx, [rbp+var_40]
0x180026a62  mov     eax, [rbp+var_20]
0x180026a65  or      ecx, eax
0x180026a67  mov     eax, [rbp+var_10]
0x180026a6a  not     ecx
0x180026a6c  add     edx, ecx
0x180026a6e  sub     edx, eax
0x180026a70  mov     eax, [rbp+var_18]
0x180026a73  sub     edx, eax
0x180026a75  cmp     r8d, edx
0x180026a78  jz      loc_18002715C
0x180026a7e  movzx   eax, byte ptr [r9]
0x180026a82  mov     [rbp+var_28], eax
0x180026a85  mov     eax, [rbp+var_28]
0x180026a88  imul    ecx, eax, 423860h
0x180026a8e  mov     [rbp+var_30], 3C440A40h
0x180026a95  mov     eax, [rbp+var_30]
0x180026a98  mov     [rbp+var_38], eax
0x180026a9b  mov     [rbp+var_8], ecx
0x180026a9e  mov     eax, [rbp+var_8]
0x180026aa1  mov     [rbp+var_40], eax
0x180026aa4  mov     ecx, [rbp+var_40]
0x180026aa7  mov     eax, [rbp+var_38]
0x180026aaa  and     ecx, eax
0x180026aac  mov     eax, [rbp+var_30]
0x180026aaf  not     ecx
0x180026ab1  mov     [rbp+var_18], ecx
0x180026ab4  mov     [rbp+var_38], eax
0x180026ab7  mov     eax, [rbp+var_8]
0x180026aba  mov     [rbp+var_40], eax
0x180026abd  mov     ecx, [rbp+var_40]
0x180026ac0  mov     eax, [rbp+var_38]
0x180026ac3  or      ecx, eax
0x180026ac5  mov     eax, [rbp+var_18]
0x180026ac8  mov     [rbp+var_30], ecx
0x180026acb  mov     [rbp+var_38], eax
0x180026ace  mov     eax, [rbp+var_30]
0x180026ad1  mov     [rbp+var_40], eax
0x180026ad4  mov     ecx, [rbp+var_40]
0x180026ad7  mov     eax, [rbp+var_38]
0x180026ada  xor     ecx, eax
0x180026adc  mov     eax, [rbp+var_18]
0x180026adf  mov     [rbp+var_20], ecx
0x180026ae2  mov     [rbp+var_38], eax
0x180026ae5  mov     eax, [rbp+var_30]
0x180026ae8  mov     [rbp+var_40], eax
0x180026aeb  mov     ecx, [rbp+var_40]
0x180026aee  mov     eax, [rbp+var_38]
0x180026af1  or      ecx, eax
0x180026af3  not     ecx
0x180026af5  mov     [rbp+var_30], 14520h
0x180026afc  mov     [rbp+var_40], ecx
0x180026aff  mov     ecx, [rbp+var_40]
0x180026b02  mov     eax, [rbp+var_20]
0x180026b05  or      ecx, eax
0x180026b07  mov     eax, [rbp+var_30]
0x180026b0a  not     ecx
0x180026b0c  mov     [rbp+var_8], ecx
0x180026b0f  mov     [rbp+var_38], eax
0x180026b12  mov     eax, [rbp+var_8]
0x180026b15  mov     [rbp+var_40], eax
0x180026b18  mov     ecx, [rbp+var_40]
0x180026b1b  mov     eax, [rbp+var_38]
0x180026b1e  and     ecx, eax
0x180026b20  mov     eax, [rbp+var_30]
0x180026b23  not     ecx
0x180026b25  mov     [rbp+var_38], eax
0x180026b28  mov     eax, [rbp+var_8]
0x180026b2b  mov     [rbp+var_40], eax
0x180026b2e  mov     [rbp+var_18], ecx
0x180026b31  mov     ecx, [rbp+var_40]
0x180026b34  mov     eax, [rbp+var_38]
0x180026b37  or      ecx, eax
0x180026b39  mov     eax, [rbp+var_18]
0x180026b3c  mov     [rbp+var_30], ecx
0x180026b3f  mov     [rbp+var_38], eax
0x180026b42  mov     eax, [rbp+var_30]
0x180026b45  mov     [rbp+var_40], eax
0x180026b48  mov     ecx, [rbp+var_40]
0x180026b4b  mov     eax, [rbp+var_38]
0x180026b4e  xor     ecx, eax
0x180026b50  mov     eax, [rbp+var_18]
0x180026b53  mov     [rbp+var_20], ecx
0x180026b56  mov     [rbp+var_38], eax
0x180026b59  mov     eax, [rbp+var_30]
0x180026b5c  mov     [rbp+var_40], eax
0x180026b5f  mov     ecx, [rbp+var_40]
0x180026b62  mov     eax, [rbp+var_38]
0x180026b65  or      ecx, eax
0x180026b67  not     ecx
0x180026b69  mov     [rbp+var_40], ecx
0x180026b6c  mov     r8d, [rbp+var_40]
0x180026b70  mov     eax, [rbp+var_20]
0x180026b73  or      r8d, eax
0x180026b76  mov     [rbp+var_30], 3C440A40h
0x180026b7d  not     r8d
0x180026b80  mov     eax, [rbp+var_30]
0x180026b83  mov     [rbp+var_38], eax
0x180026b86  mov     [rbp+var_8], 14520h
0x180026b8d  mov     eax, [rbp+var_8]
0x180026b90  mov     [rbp+var_40], eax
  ... truncated ...
```

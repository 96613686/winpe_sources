# Input::CreateMessage::ReceiveOddData(Input::CreateMessage &,Input::GeneralEvent &)

- ea: `0x180024740`
- end: `0x1800251d3`
- name: `?ReceiveOddData@CreateMessage@Input@@SAXAEAV12@AEAVGeneralEvent@2@@Z`
- size: `2707`
- prototype: `void __fastcall(struct Input::CreateMessage *this, struct Input::GeneralEvent *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e4b0`
- `0x180024380`
- `0x180024740`
- `0x1800bf3b0`

## pseudocode

```c
void __fastcall Input::CreateMessage::ReceiveOddData(struct Input::CreateMessage *this, struct Input::GeneralEvent *a2)
{
  void (__fastcall *v3)(Input::CreateMessage *__hidden, struct Input::GeneralEvent *); // r9
  __int64 v5; // rcx
  __int64 v6; // r8
  void (__fastcall *MixedProvider)(void (__fastcall *)(struct Input::CreateMessage *, struct Input::GeneralEvent *), unsigned __int64, __int64); // rax
  __int64 v8; // rcx
  bool v9; // sf
  int v10; // [rsp+30h] [rbp-30h]
  int v11; // [rsp+30h] [rbp-30h]
  int v12; // [rsp+30h] [rbp-30h]
  _BYTE *retaddr; // [rsp+68h] [rbp+8h]

  v3 = Input::CreateMessage::PaintFlatLocation;
  if ( ~(~(~(~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0x15810018)
           | ~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) ^ 0x15810018
             | ~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0x15810018)))
         | 0x620220)
       | ~(~(~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0x15810018)
           | ~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) ^ 0x15810018
             | ~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0x15810018)))
         ^ 0x620220
         | ~(~(~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0x15810018)
             | ~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) ^ 0x15810018
               | ~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0x15810018)))
           | 0x620220))) == ~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) ^ 0x15E30238
                            | ~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0x15E30238))
                          + ((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) ^ 0x15E30238
                           | ~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) ^ 0x15E30238
                             | ~((1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0x15E30238)))
                          - 1799994 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation
                          - 367198776 )
    goto LABEL_9;
  v10 = 8007648 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation;
  if ( ~(~(~(~(v10 & 0x6F2480C0) ^ (v10 | 0x6F2480C0) | ~(~(v10 & 0x6F2480C0) | v10 | 0x6F2480C0)) & 0x111220)
       ^ (~(~(v10 & 0x6F2480C0) ^ (v10 | 0x6F2480C0) | ~(~(v10 & 0x6F2480C0) | v10 | 0x6F2480C0)) | 0x111220)
       | ~(~(~(~(v10 & 0x6F2480C0) ^ (v10 | 0x6F2480C0) | ~(~(v10 & 0x6F2480C0) | v10 | 0x6F2480C0)) & 0x111220)
         | ~(~(v10 & 0x6F2480C0) ^ (v10 | 0x6F2480C0) | ~(~(v10 & 0x6F2480C0) | v10 | 0x6F2480C0))
         | 0x111220)) != ~(v10 ^ 0x6F3592E0 | ~(v10 | 0x6F3592E0))
                       + (v10 ^ 0x6F3592E0 ^ v10 & 0x6F3592E0 | (v10 ^ 0x6F3592E0) & v10 & 0x6F3592E0)
                       - v10
                       - 1865781984 )
  {
    if ( (~(~((977145 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) & 0xD85D013)
          & ((977145 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0xD85D013)
          & 0x2A0C80)
        & (~((977145 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) & 0xD85D013)
         & ((977145 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0xD85D013)
         | 0x2A0C80)) == ~((977145 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) ^ 0xDAFDC93
                         | ~((977145 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) | 0xDAFDC93))
                       + ((977145 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) ^ 0xDAFDC93
                        | (977145 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation) & 0xDAFDC93)
                       - 977145 * *(unsigned __int8 *)Input::CreateMessage::PaintFlatLocation
                       - 229629075 )
    {
      v8 = *((char *)Input::CreateMessage::PaintFlatLocation + 1);
      v3 = (void (__fastcall *)(Input::CreateMessage *__hidden, struct Input::GeneralEvent *))((char *)Input::CreateMessage::PaintFlatLocation
                                                                                             + 2);
      v9 = (v8 & 0x80u) != 0LL;
      if ( (char)v8 > 0 )
      {
        if ( (__int64)v3 > 0x7FFFFFFFFFFFFFFFLL - v8 )
          goto LABEL_21;
        v9 = (v8 & 0x80u) != 0LL;
      }
      if ( !v9 || (__int64)v3 >= (__int64)(0x8000000000000000uLL - v8) )
      {
        v12 = 8007648 * *((unsigned __int8 *)v3 + v8);
        if ( ~(~(~(~(v12 | 0x61560000) | v12 & 0x61560000) | 0x82680)
             | ~(~(v12 | 0x61560000) | v12 & 0x61560000) & 0x82680) == ~(v12 ^ 0x615E2680 | ~(v12 | 0x615E2680))
                                                                     + (v12 ^ 0x615E2680 | v12 & 0x615E2680)
                                                                     - v12
                                                                     - 1633560192 )
          goto LABEL_9;
      }
    }
LABEL_21:
    v6 = IntegralRelation::OddMap;
    goto LABEL_10;
  }
  v5 = *(int *)((char *)Input::CreateMessage::PaintFlatLocation + 1);
  v3 = (void (__fastcall *)(Input::CreateMessage *__hidden, struct Input::GeneralEvent *))&loc_180024385;
  if ( v5 <= 0 )
  {
    if ( v5 < 0 && (__int64)&loc_180024385 < (__int64)(0x8000000000000000uLL - v5) )
      goto LABEL_21;
    goto LABEL_8;
  }
  if ( (__int64)&loc_180024385 <= 0x7FFFFFFFFFFFFFFFLL - v5 )
  {
LABEL_8:
    v11 = 1799994 * *((unsigned __int8 *)&loc_180024385 + v5);
    if ( ~(~(~(~(v11 | 0x15810018) | v11 & 0x15810018) | 0x620220) | ~(~(v11 | 0x15810018) | v11 & 0x15810018)
                                                                   & 0x620220) == ~(v11 ^ 0x15E30238
                                                                                  | ~(v11 | 0x15E30238))
                                                                                + (v11 ^ 0x15E30238 | v11 & 0x15E30238)
                                                                                - v11
                                                                                - 367198776 )
    {
LABEL_9:
      v6 = ++IntegralRelation::OddMap;
      goto LABEL_10;
    }
    goto LABEL_21;
  }
  v6 = IntegralRelation::OddMap;
LABEL_10:
  if ( *retaddr == (unsigned __int8)(((unsigned int)v6 ^ 0xAF09F92F) / 0x6A6A25)
    || ((unsigned int)v6 ^ 0xFB878673) != 0x42EA20 )
  {
    v6 = (unsigned int)(v6 + 1);
    IntegralRelation::OddMap = v6;
  }
  MixedProvider = (void (__fastcall *)(void (__fastcall *)(struct Input::CreateMessage *, struct Input::GeneralEvent *), unsigned __int64, __int64))GenerateMixedProvider(0xBF1F9F5FA080C050uLL, 1369727114, v6, v3);
  MixedProvider(
    Input::CreateMessage::ReceiveOddData,
    (unsigned __int64)Input::CreateMessage::ReceiveOddData ^ 0x123822,
    145426);
  Input::CreateMessage::PaintFlatLocation(this, a2);
}

```

## disassembly

```asm
0x180024740  mov     [rsp-8+arg_10], rbx
0x180024745  mov     [rsp-8+arg_18], rdi
0x18002474a  push    rbp
0x18002474b  mov     rbp, rsp
0x18002474e  sub     rsp, 60h
0x180024752  mov     rbx, rcx
0x180024755  mov     [rbp+var_18], 15810018h
0x18002475c  lea     r9, ?PaintFlatLocation@CreateMessage@Input@@QEAAXAEAVGeneralEvent@2@@Z; Input::CreateMessage::PaintFlatLocation(Input::GeneralEvent &)
0x180024763  mov     rdi, rdx
0x180024766  movzx   eax, byte ptr [r9]
0x18002476a  mov     [rbp+var_8], eax
0x18002476d  mov     eax, [rbp+var_8]
0x180024770  imul    ecx, eax, 1B773Ah
0x180024776  mov     eax, [rbp+var_18]
0x180024779  mov     [rbp+var_30], eax
0x18002477c  mov     [rbp+var_10], ecx
0x18002477f  mov     eax, [rbp+var_10]
0x180024782  mov     [rbp+var_28], eax
0x180024785  mov     ecx, [rbp+var_28]
0x180024788  mov     eax, [rbp+var_30]
0x18002478b  or      ecx, eax
0x18002478d  mov     eax, [rbp+var_18]
0x180024790  not     ecx
0x180024792  mov     [rbp+var_38], ecx
0x180024795  mov     [rbp+var_18], eax
0x180024798  mov     eax, [rbp+var_10]
0x18002479b  mov     [rbp+var_10], eax
0x18002479e  mov     eax, [rbp+var_18]
0x1800247a1  mov     [rbp+var_30], eax
0x1800247a4  mov     eax, [rbp+var_10]
0x1800247a7  mov     [rbp+var_28], eax
0x1800247aa  mov     ecx, [rbp+var_28]
0x1800247ad  mov     eax, [rbp+var_30]
0x1800247b0  xor     ecx, eax
0x1800247b2  mov     eax, [rbp+var_18]
0x1800247b5  mov     [rbp+var_20], ecx
0x1800247b8  mov     [rbp+var_30], eax
0x1800247bb  mov     eax, [rbp+var_10]
0x1800247be  mov     [rbp+var_28], eax
0x1800247c1  mov     ecx, [rbp+var_28]
0x1800247c4  mov     eax, [rbp+var_30]
0x1800247c7  or      ecx, eax
0x1800247c9  not     ecx
0x1800247cb  mov     [rbp+var_18], 620220h
0x1800247d2  mov     [rbp+var_28], ecx
0x1800247d5  mov     ecx, [rbp+var_28]
0x1800247d8  mov     eax, [rbp+var_20]
0x1800247db  or      ecx, eax
0x1800247dd  not     ecx
0x1800247df  mov     [rbp+var_20], ecx
0x1800247e2  mov     ecx, [rbp+var_20]
0x1800247e5  mov     eax, [rbp+var_38]
0x1800247e8  or      ecx, eax
0x1800247ea  mov     eax, [rbp+var_18]
0x1800247ed  not     ecx
0x1800247ef  mov     [rbp+var_10], ecx
0x1800247f2  mov     [rbp+var_20], eax
0x1800247f5  mov     eax, [rbp+var_10]
0x1800247f8  mov     [rbp+var_38], eax
0x1800247fb  mov     ecx, [rbp+var_38]
0x1800247fe  mov     eax, [rbp+var_20]
0x180024801  or      ecx, eax
0x180024803  mov     eax, [rbp+var_18]
0x180024806  not     ecx
0x180024808  mov     [rbp+var_18], eax
0x18002480b  mov     eax, [rbp+var_10]
0x18002480e  mov     [rbp+var_10], eax
0x180024811  mov     eax, [rbp+var_18]
0x180024814  mov     [rbp+var_20], eax
0x180024817  mov     eax, [rbp+var_10]
0x18002481a  mov     [rbp+var_38], eax
0x18002481d  mov     [rbp+var_30], ecx
0x180024820  mov     ecx, [rbp+var_38]
0x180024823  mov     eax, [rbp+var_20]
0x180024826  xor     ecx, eax
0x180024828  mov     eax, [rbp+var_18]
0x18002482b  mov     [rbp+var_28], ecx
0x18002482e  mov     [rbp+var_20], eax
0x180024831  mov     eax, [rbp+var_10]
0x180024834  mov     [rbp+var_38], eax
0x180024837  mov     ecx, [rbp+var_38]
0x18002483a  mov     eax, [rbp+var_20]
0x18002483d  or      ecx, eax
0x18002483f  not     ecx
0x180024841  mov     [rbp+var_38], ecx
0x180024844  mov     ecx, [rbp+var_38]
0x180024847  mov     eax, [rbp+var_28]
0x18002484a  or      ecx, eax
0x18002484c  not     ecx
0x18002484e  mov     [rbp+var_18], 15810018h
0x180024855  mov     [rbp+var_38], ecx
0x180024858  mov     r8d, [rbp+var_38]
0x18002485c  mov     eax, [rbp+var_30]
0x18002485f  or      r8d, eax
0x180024862  mov     eax, [rbp+var_18]
0x180024865  not     r8d
0x180024868  mov     [rbp+var_20], eax
0x18002486b  mov     [rbp+var_10], 620220h
0x180024872  mov     eax, [rbp+var_10]
0x180024875  mov     [rbp+var_38], eax
0x180024878  mov     ecx, [rbp+var_38]
0x18002487b  mov     eax, [rbp+var_20]
0x18002487e  or      ecx, eax
0x180024880  mov     eax, [rbp+var_18]
0x180024883  not     ecx
0x180024885  mov     [rbp+var_18], eax
0x180024888  mov     eax, [rbp+var_10]
0x18002488b  mov     [rbp+var_10], eax
0x18002488e  mov     eax, [rbp+var_18]
0x180024891  mov     [rbp+var_20], eax
0x180024894  mov     eax, [rbp+var_10]
0x180024897  mov     [rbp+var_38], eax
0x18002489a  mov     [rbp+var_30], ecx
0x18002489d  mov     ecx, [rbp+var_38]
0x1800248a0  mov     eax, [rbp+var_20]
0x1800248a3  xor     ecx, eax
0x1800248a5  mov     eax, [rbp+var_18]
0x1800248a8  mov     [rbp+var_20], eax
0x1800248ab  mov     eax, [rbp+var_10]
0x1800248ae  mov     [rbp+var_38], eax
0x1800248b1  mov     [rbp+var_28], ecx
0x1800248b4  mov     ecx, [rbp+var_38]
0x1800248b7  mov     eax, [rbp+var_20]
0x1800248ba  or      ecx, eax
0x1800248bc  not     ecx
0x1800248be  mov     [rbp+var_38], ecx
0x1800248c1  mov     ecx, [rbp+var_38]
0x1800248c4  mov     eax, [rbp+var_28]
0x1800248c7  or      ecx, eax
0x1800248c9  not     ecx
0x1800248cb  mov     [rbp+var_38], ecx
0x1800248ce  mov     ecx, [rbp+var_38]
0x1800248d1  mov     eax, [rbp+var_30]
0x1800248d4  or      ecx, eax
0x1800248d6  mov     eax, [rbp+var_8]
0x1800248d9  not     ecx
0x1800248db  mov     [rbp+var_18], ecx
0x1800248de  imul    ecx, eax, 1B773Ah
0x1800248e4  mov     eax, [rbp+var_18]
0x1800248e7  mov     [rbp+var_8], eax
0x1800248ea  mov     [rbp+var_10], ecx
0x1800248ed  mov     eax, [rbp+var_10]
0x1800248f0  mov     [rbp+var_30], eax
0x1800248f3  mov     eax, [rbp+var_8]
0x1800248f6  mov     [rbp+var_20], eax
0x1800248f9  mov     eax, [rbp+var_30]
0x1800248fc  mov     [rbp+var_38], eax
0x1800248ff  mov     ecx, [rbp+var_38]
0x180024902  mov     eax, [rbp+var_20]
0x180024905  xor     ecx, eax
0x180024907  mov     eax, [rbp+var_8]
0x18002490a  mov     [rbp+var_8], eax
0x18002490d  mov     eax, [rbp+var_30]
0x180024910  mov     [rbp+var_30], eax
0x180024913  mov     eax, [rbp+var_8]
0x180024916  mov     [rbp+var_20], eax
0x180024919  mov     eax, [rbp+var_30]
0x18002491c  mov     [rbp+var_38], eax
0x18002491f  mov     [rbp+var_40], ecx
0x180024922  mov     ecx, [rbp+var_38]
0x180024925  mov     eax, [rbp+var_20]
0x180024928  xor     ecx, eax
0x18002492a  mov     eax, [rbp+var_8]
0x18002492d  mov     [rbp+var_20], eax
0x180024930  mov     eax, [rbp+var_30]
0x180024933  mov     [rbp+var_38], eax
0x180024936  mov     [rbp+var_28], ecx
0x180024939  mov     ecx, [rbp+var_38]
0x18002493c  mov     eax, [rbp+var_20]
0x18002493f  or      ecx, eax
0x180024941  not     ecx
0x180024943  mov     [rbp+var_38], ecx
0x180024946  mov     ecx, [rbp+var_38]
0x180024949  mov     eax, [rbp+var_28]
0x18002494c  or      ecx, eax
0x18002494e  not     ecx
0x180024950  mov     [rbp+var_38], ecx
0x180024953  mov     edx, [rbp+var_38]
0x180024956  mov     eax, [rbp+var_40]
0x180024959  or      edx, eax
0x18002495b  mov     eax, [rbp+var_18]
0x18002495e  mov     [rbp+var_30], eax
0x180024961  mov     eax, [rbp+var_10]
0x180024964  mov     [rbp+var_8], eax
0x180024967  mov     eax, [rbp+var_30]
0x18002496a  mov     [rbp+var_38], eax
0x18002496d  mov     eax, [rbp+var_8]
0x180024970  mov     [rbp+var_40], eax
0x180024973  mov     ecx, [rbp+var_40]
0x180024976  mov     eax, [rbp+var_38]
0x180024979  xor     ecx, eax
0x18002497b  mov     eax, [rbp+var_30]
0x18002497e  mov     [rbp+var_20], ecx
0x180024981  mov     [rbp+var_38], eax
0x180024984  mov     eax, [rbp+var_8]
0x180024987  mov     [rbp+var_40], eax
0x18002498a  mov     ecx, [rbp+var_40]
0x18002498d  mov     eax, [rbp+var_38]
0x180024990  or      ecx, eax
0x180024992  not     ecx
0x180024994  mov     [rbp+var_40], ecx
0x180024997  mov     ecx, [rbp+var_40]
0x18002499a  mov     eax, [rbp+var_20]
0x18002499d  or      ecx, eax
0x18002499f  mov     eax, [rbp+var_10]
0x1800249a2  not     ecx
0x1800249a4  add     edx, ecx
0x1800249a6  sub     edx, eax
0x1800249a8  mov     eax, [rbp+var_18]
0x1800249ab  sub     edx, eax
0x1800249ad  cmp     r8d, edx
0x1800249b0  jz      loc_180024DD6
0x1800249b6  movzx   eax, byte ptr [r9]
0x1800249ba  mov     [rbp+var_28], eax
0x1800249bd  mov     eax, [rbp+var_28]
0x1800249c0  imul    ecx, eax, 7A2FE0h
0x1800249c6  mov     [rbp+var_30], 6F2480C0h
0x1800249cd  mov     eax, [rbp+var_30]
0x1800249d0  mov     [rbp+var_38], eax
0x1800249d3  mov     [rbp+var_8], ecx
0x1800249d6  mov     eax, [rbp+var_8]
0x1800249d9  mov     [rbp+var_40], eax
0x1800249dc  mov     ecx, [rbp+var_40]
0x1800249df  mov     eax, [rbp+var_38]
0x1800249e2  and     ecx, eax
0x1800249e4  mov     eax, [rbp+var_30]
0x1800249e7  not     ecx
0x1800249e9  mov     [rbp+var_18], ecx
0x1800249ec  mov     [rbp+var_38], eax
0x1800249ef  mov     eax, [rbp+var_8]
0x1800249f2  mov     [rbp+var_40], eax
0x1800249f5  mov     ecx, [rbp+var_40]
0x1800249f8  mov     eax, [rbp+var_38]
0x1800249fb  or      ecx, eax
0x1800249fd  mov     eax, [rbp+var_18]
0x180024a00  mov     [rbp+var_30], ecx
0x180024a03  mov     [rbp+var_38], eax
0x180024a06  mov     eax, [rbp+var_30]
0x180024a09  mov     [rbp+var_40], eax
0x180024a0c  mov     ecx, [rbp+var_40]
0x180024a0f  mov     eax, [rbp+var_38]
0x180024a12  xor     ecx, eax
0x180024a14  mov     eax, [rbp+var_18]
0x180024a17  mov     [rbp+var_20], ecx
0x180024a1a  mov     [rbp+var_38], eax
0x180024a1d  mov     eax, [rbp+var_30]
0x180024a20  mov     [rbp+var_40], eax
0x180024a23  mov     ecx, [rbp+var_40]
0x180024a26  mov     eax, [rbp+var_38]
0x180024a29  or      ecx, eax
0x180024a2b  not     ecx
0x180024a2d  mov     [rbp+var_30], 111220h
0x180024a34  mov     [rbp+var_40], ecx
0x180024a37  mov     ecx, [rbp+var_40]
0x180024a3a  mov     eax, [rbp+var_20]
0x180024a3d  or      ecx, eax
0x180024a3f  mov     eax, [rbp+var_30]
0x180024a42  not     ecx
0x180024a44  mov     [rbp+var_8], ecx
0x180024a47  mov     [rbp+var_38], eax
0x180024a4a  mov     eax, [rbp+var_8]
0x180024a4d  mov     [rbp+var_40], eax
0x180024a50  mov     ecx, [rbp+var_40]
0x180024a53  mov     eax, [rbp+var_38]
0x180024a56  and     ecx, eax
0x180024a58  mov     eax, [rbp+var_30]
0x180024a5b  not     ecx
0x180024a5d  mov     [rbp+var_38], eax
0x180024a60  mov     eax, [rbp+var_8]
0x180024a63  mov     [rbp+var_40], eax
0x180024a66  mov     [rbp+var_18], ecx
0x180024a69  mov     ecx, [rbp+var_40]
0x180024a6c  mov     eax, [rbp+var_38]
0x180024a6f  or      ecx, eax
0x180024a71  mov     eax, [rbp+var_18]
0x180024a74  mov     [rbp+var_30], ecx
0x180024a77  mov     [rbp+var_38], eax
0x180024a7a  mov     eax, [rbp+var_30]
0x180024a7d  mov     [rbp+var_40], eax
0x180024a80  mov     ecx, [rbp+var_40]
0x180024a83  mov     eax, [rbp+var_38]
0x180024a86  xor     ecx, eax
0x180024a88  mov     eax, [rbp+var_18]
0x180024a8b  mov     [rbp+var_20], ecx
0x180024a8e  mov     [rbp+var_38], eax
0x180024a91  mov     eax, [rbp+var_30]
0x180024a94  mov     [rbp+var_40], eax
0x180024a97  mov     ecx, [rbp+var_40]
0x180024a9a  mov     eax, [rbp+var_38]
0x180024a9d  or      ecx, eax
0x180024a9f  not     ecx
0x180024aa1  mov     [rbp+var_40], ecx
0x180024aa4  mov     r8d, [rbp+var_40]
0x180024aa8  mov     eax, [rbp+var_20]
0x180024aab  or      r8d, eax
0x180024aae  mov     [rbp+var_30], 6F2480C0h
0x180024ab5  not     r8d
0x180024ab8  mov     eax, [rbp+var_30]
0x180024abb  mov     [rbp+var_38], eax
0x180024abe  mov     [rbp+var_8], 111220h
  ... truncated ...
```

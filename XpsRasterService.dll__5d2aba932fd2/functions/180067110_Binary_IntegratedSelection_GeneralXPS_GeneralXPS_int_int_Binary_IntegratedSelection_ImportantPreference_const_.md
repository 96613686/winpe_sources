# Binary::IntegratedSelection::GeneralXPS::GeneralXPS(int,int,Binary::IntegratedSelection::ImportantPreference const &,Data::ShortTermResolution<int>,Binary::IntegratedSelection::ComplexService &)

- ea: `0x180067110`
- end: `0x1800672ed`
- name: `??0GeneralXPS@IntegratedSelection@Binary@@QEAA@HHAEBVImportantPreference@12@V?$ShortTermResolution@H@Data@@AEAVComplexService@12@@Z`
- size: `477`
- prototype: `__int64 __fastcall(__int64, int, int, int *, _DWORD *, _DWORD *)`
- caller_count: `38`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005a960`
- `0x18005add0`
- `0x18005b400`
- `0x18005b880`
- `0x18005bcd0`
- `0x18005c120`
- `0x18005c580`
- `0x18005cb30`
- `0x18005cfb0`
- `0x18005d3f0`
- `0x18005d840`
- `0x18005e010`
- `0x18005ecd0`
- `0x18005f4b0`
- `0x18005fbd0`
- `0x1800602f0`
- `0x180060920`
- `0x180061270`
- `0x1800618c0`
- `0x180061ec0`
- `0x1800964d0`
- `0x1800968e0`
- `0x180096d90`
- `0x1800971d0`
- `0x1800978a0`
- `0x180097fa0`
- `0x180098460`
- `0x180098c30`
- `0x180099540`
- `0x180099c50`
- `0x18009a050`
- `0x18009a520`
- `0x18009a970`
- `0x18009b000`
- `0x18009b6e0`
- `0x18009bbc0`
- `0x18009c440`
- `0x18009ce70`

## callees

- `0x1800541e0`
- `0x180067110`
- `0x180069c60`
- `0x180069e80`
- `0x180096070`

## pseudocode

```c
__int64 __fastcall Binary::IntegratedSelection::GeneralXPS::GeneralXPS(
        __int64 a1,
        int a2,
        int a3,
        int *a4,
        _DWORD *a5,
        _DWORD *a6)
{
  __int64 v11; // r8
  __int64 v12; // rdx
  int v13; // ebp
  __int64 v14; // rdi
  int v15; // ebx
  int v16; // ebx
  int v17; // edx
  __int64 v18; // rcx
  char v19; // al
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rdx
  __int64 result; // rax
  int v24; // [rsp+40h] [rbp-68h] BYREF
  char v25; // [rsp+44h] [rbp-64h]
  int v26; // [rsp+48h] [rbp-60h]
  char v27; // [rsp+4Ch] [rbp-5Ch]
  int v28; // [rsp+50h] [rbp-58h] BYREF
  char v29; // [rsp+54h] [rbp-54h]
  int v30; // [rsp+58h] [rbp-50h] BYREF
  char v31; // [rsp+5Ch] [rbp-4Ch]

  v11 = (unsigned int)a5[2];
  v12 = (unsigned int)a5[3];
  *(_DWORD *)a1 = a6[2];
  *(_DWORD *)(a1 + 4) = a6[3];
  Binary::IntegratedSelection::SmoothControl::SmoothControl(a1 + 16, v12, v11, 8, a4);
  v13 = 1;
  *(_DWORD *)(a1 + 1564) = 1;
  v14 = 0;
  *(_QWORD *)(a1 + 1556) = 0;
  *(_QWORD *)(a1 + 1576) = 1;
  *(_QWORD *)(a1 + 1568) = 0;
  Binary::IntegratedSelection::GeneralXPS::DrawEvenArticle(a1, (unsigned int)&v24, a2, a3, a6[14], a6[15], (__int64)a6);
  Binary::IntegratedSelection::GeneralXPS::ExchangeEasyAPI(a1, &v24, (unsigned int)a6[14], (unsigned int)a6[15]);
  v15 = 0;
  v28 = a3;
  if ( v27 )
    v15 = v26;
  v30 = v15;
  v29 = 1;
  v31 = 1;
  Data::FillClearSkill(&v24, &v30, &v28);
  if ( v25 == 1 )
    v16 = v15 - v24 * a3;
  else
    v16 = 0;
  *(_DWORD *)(a1 + 1580) = v16;
  v17 = *(_DWORD *)(a1 + 1568);
  if ( a3 > 0 )
    v13 = a3;
  *(_DWORD *)(a1 + 1576) = v13;
  if ( v17 < 0 || v17 >= v13 )
  {
    v17 %= v13;
    *(_DWORD *)(a1 + 1568) = v17;
    if ( v17 >= 0 )
      goto LABEL_13;
    v17 += v13;
  }
  *(_DWORD *)(a1 + 1568) = v17;
LABEL_13:
  *(_DWORD *)(a1 + 1572) = v17;
  v18 = a4[1] * (__int64)(a6[1] - a5[1]);
  if ( (unsigned __int64)(v18 + 0x80000000LL) > 0xFFFFFFFF )
  {
    v18 = 0;
    v19 = 0;
  }
  else
  {
    v18 = (int)v18;
    v19 = 1;
  }
  if ( !v19 )
    v18 = 0;
  v20 = *a4 * (__int64)(*a6 - *a5);
  if ( (unsigned __int64)(v20 + 0x80000000LL) > 0xFFFFFFFF )
  {
    v21 = 0;
    v22 = v18;
  }
  else
  {
    v14 = (int)v20;
    v21 = v14;
    v22 = v18 + (int)v20;
    if ( v14 < 0 )
    {
      if ( v18 < 0 && v22 > v14 )
        goto LABEL_27;
LABEL_26:
      v21 = v22;
      goto LABEL_27;
    }
  }
  if ( v18 < 0 || v22 >= v14 )
    goto LABEL_26;
LABEL_27:
  *(_QWORD *)(a1 + 8) = v21;
  result = a1;
  *(_DWORD *)(a1 + 56) = a6[4];
  return result;
}

```

## disassembly

```asm
0x180067110  push    rbx
0x180067112  push    rbp
0x180067113  push    rsi
0x180067114  push    rdi
0x180067115  push    r12
0x180067117  push    r13
0x180067119  push    r14
0x18006711b  push    r15
0x18006711d  sub     rsp, 68h
0x180067121  mov     r14, [rsp+0A8h+arg_28]
0x180067129  mov     r12, r9
0x18006712c  mov     r13, [rsp+0A8h+arg_20]
0x180067134  mov     r15d, r8d
0x180067137  mov     ebx, edx
0x180067139  mov     [rsp+0A8h+var_88], r9
0x18006713e  mov     rsi, rcx
0x180067141  mov     r9d, 8
0x180067147  mov     eax, [r14+8]
0x18006714b  mov     r8d, [r13+8]
0x18006714f  mov     edx, [r13+0Ch]
0x180067153  mov     [rcx], eax
0x180067155  mov     eax, [r14+0Ch]
0x180067159  mov     [rcx+4], eax
0x18006715c  add     rcx, 10h
0x180067160  call    ??0SmoothControl@IntegratedSelection@Binary@@QEAA@HHW4ActiveEntry@12@AEBVImportantPreference@12@@Z; Binary::IntegratedSelection::SmoothControl::SmoothControl(int,int,Binary::IntegratedSelection::ActiveEntry,Binary::IntegratedSelection::ImportantPreference const &)
0x180067165  mov     ebp, 1
0x18006716a  mov     [rsp+0A8h+var_78], r14
0x18006716f  mov     [rsi+61Ch], ebp
0x180067175  lea     rdx, [rsp+0A8h+var_68]
0x18006717a  xor     edi, edi
0x18006717c  mov     r9d, r15d
0x18006717f  mov     [rsi+614h], rdi
0x180067186  mov     r8d, ebx
0x180067189  mov     [rsi+628h], rbp
0x180067190  mov     rcx, rsi
0x180067193  mov     [rsi+620h], rdi
0x18006719a  mov     eax, [r14+3Ch]
0x18006719e  mov     [rsp+0A8h+var_80], eax
0x1800671a2  mov     eax, [r14+38h]
0x1800671a6  mov     dword ptr [rsp+0A8h+var_88], eax
0x1800671aa  call    ?DrawEvenArticle@GeneralXPS@IntegratedSelection@Binary@@IEAA?AU?$OddPlatform@H@123@HHHHAEAV?$ShortTermResolution@H@Data@@@Z; Binary::IntegratedSelection::GeneralXPS::DrawEvenArticle(int,int,int,int,Data::ShortTermResolution<int> &)
0x1800671af  mov     r9d, [r14+3Ch]
0x1800671b3  lea     rdx, [rsp+0A8h+var_68]
0x1800671b8  mov     r8d, [r14+38h]
0x1800671bc  mov     rcx, rsi
0x1800671bf  call    ?ExchangeEasyAPI@GeneralXPS@IntegratedSelection@Binary@@IEAAXAEAV?$NullDefinition@H@Data@@HH@Z; Binary::IntegratedSelection::GeneralXPS::ExchangeEasyAPI(Data::NullDefinition<int> &,int,int)
0x1800671c4  cmp     [rsp+0A8h+var_5C], dil
0x1800671c9  lea     r8, [rsp+0A8h+var_58]
0x1800671ce  mov     ebx, edi
0x1800671d0  mov     [rsp+0A8h+var_58], r15d
0x1800671d5  cmovnz  ebx, [rsp+0A8h+var_60]
0x1800671da  lea     rdx, [rsp+0A8h+var_50]
0x1800671df  lea     rcx, [rsp+0A8h+var_68]
0x1800671e4  mov     [rsp+0A8h+var_50], ebx
0x1800671e8  mov     [rsp+0A8h+var_54], bpl
0x1800671ed  mov     [rsp+0A8h+var_4C], bpl
0x1800671f2  call    ?FillClearSkill@Data@@YA?AV?$NullDefinition@H@1@AEBV21@0@Z; Data::FillClearSkill(Data::NullDefinition<int> const &,Data::NullDefinition<int> const &)
0x1800671f7  cmp     [rsp+0A8h+var_64], bpl
0x1800671fc  jnz     short loc_18006720A
0x1800671fe  mov     eax, r15d
0x180067201  imul    eax, [rsp+0A8h+var_68]
0x180067206  sub     ebx, eax
0x180067208  jmp     short loc_18006720C
0x18006720a  mov     ebx, edi
0x18006720c  test    r15d, r15d
0x18006720f  mov     [rsi+62Ch], ebx
0x180067215  mov     edx, [rsi+620h]
0x18006721b  cmovg   ebp, r15d
0x18006721f  mov     [rsi+628h], ebp
0x180067225  test    edx, edx
0x180067227  js      short loc_18006722D
0x180067229  cmp     edx, ebp
0x18006722b  jl      short loc_18006723E
0x18006722d  mov     eax, edx
0x18006722f  cdq
0x180067230  idiv    ebp
0x180067232  mov     [rsi+620h], edx
0x180067238  test    edx, edx
0x18006723a  jns     short loc_180067244
0x18006723c  add     edx, ebp
0x18006723e  mov     [rsi+620h], edx
0x180067244  mov     [rsi+624h], edx
0x18006724a  mov     r8d, 80000000h
0x180067250  mov     eax, [r14+4]
0x180067254  mov     r9d, 0FFFFFFFFh
0x18006725a  sub     eax, [r13+4]
0x18006725e  movsxd  rcx, eax
0x180067261  movsxd  rax, dword ptr [r12+4]
0x180067266  imul    rcx, rax
0x18006726a  lea     rax, [rcx+r8]
0x18006726e  cmp     rax, r9
0x180067271  ja      short loc_18006727A
0x180067273  movsxd  rcx, ecx
0x180067276  mov     al, 1
0x180067278  jmp     short loc_18006727F
0x18006727a  mov     rcx, rdi
0x18006727d  xor     al, al
0x18006727f  test    al, al
0x180067281  mov     eax, [r14]
0x180067284  cmovz   rcx, rdi
0x180067288  sub     eax, [r13+0]
0x18006728c  movsxd  rdx, eax
0x18006728f  movsxd  rax, dword ptr [r12]
0x180067293  imul    rdx, rax
0x180067297  lea     rax, [rdx+r8]
0x18006729b  cmp     rax, r9
0x18006729e  ja      short loc_1800672BB
0x1800672a0  movsxd  rdi, edx
0x1800672a3  mov     rax, rdi
0x1800672a6  lea     rdx, [rcx+rdi]
0x1800672aa  test    rdi, rdi
0x1800672ad  jns     short loc_1800672C1
0x1800672af  test    rcx, rcx
0x1800672b2  jns     short loc_1800672CB
0x1800672b4  cmp     rdx, rdi
0x1800672b7  jle     short loc_1800672CB
0x1800672b9  jmp     short loc_1800672CE
0x1800672bb  mov     rax, rdi
0x1800672be  mov     rdx, rcx
0x1800672c1  test    rcx, rcx
0x1800672c4  js      short loc_1800672CB
0x1800672c6  cmp     rdx, rdi
0x1800672c9  jl      short loc_1800672CE
0x1800672cb  mov     rax, rdx
0x1800672ce  mov     [rsi+8], rax
0x1800672d2  mov     rax, rsi
0x1800672d5  mov     ecx, [r14+10h]
0x1800672d9  mov     [rsi+38h], ecx
0x1800672dc  add     rsp, 68h
0x1800672e0  pop     r15
0x1800672e2  pop     r14
0x1800672e4  pop     r13
0x1800672e6  pop     r12
0x1800672e8  pop     rdi
0x1800672e9  pop     rsi
0x1800672ea  pop     rbp
0x1800672eb  pop     rbx
0x1800672ec  retn
```

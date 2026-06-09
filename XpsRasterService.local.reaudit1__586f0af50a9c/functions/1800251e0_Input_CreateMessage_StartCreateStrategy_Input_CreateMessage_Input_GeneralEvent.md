# Input::CreateMessage::StartCreateStrategy(Input::CreateMessage &,Input::GeneralEvent &)

- ea: `0x1800251e0`
- end: `0x180025cc1`
- name: `?StartCreateStrategy@CreateMessage@Input@@SAXAEAV12@AEAVGeneralEvent@2@@Z`
- size: `2785`
- prototype: `void __fastcall(struct Input::CreateMessage *this, struct Input::GeneralEvent *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e4b0`
- `0x180023fd0`
- `0x1800251e0`
- `0x1800bf3b0`

## pseudocode

```c
void __fastcall Input::CreateMessage::StartCreateStrategy(
        struct Input::CreateMessage *this,
        struct Input::GeneralEvent *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  void (__fastcall *MixedProvider)(void (__fastcall *)(struct Input::CreateMessage *, struct Input::GeneralEvent *), unsigned __int64, __int64); // rax
  __int64 v7; // rcx
  char *v8; // r9
  bool v9; // sf
  int v10; // [rsp+38h] [rbp-28h]
  int v11; // [rsp+40h] [rbp-20h]
  int v12; // [rsp+48h] [rbp-18h]
  int v13; // [rsp+48h] [rbp-18h]
  _BYTE *retaddr; // [rsp+68h] [rbp+8h]

  if ( ~(~(~(~((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) & 0x49901400)
           ^ ((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) | 0x49901400)
           | ~(~((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) & 0x49901400)
             | (6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality)
             | 0x49901400))
         & 0x236820)
       ^ (~(~((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) & 0x49901400)
          ^ ((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) | 0x49901400)
          | ~(~((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) & 0x49901400)
            | (6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality)
            | 0x49901400))
        | 0x236820)
       | ~(~(~(~((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) & 0x49901400)
             ^ ((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) | 0x49901400)
             | ~(~((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) & 0x49901400)
               | (6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality)
               | 0x49901400))
           & 0x236820)
         | ~(~((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) & 0x49901400)
           ^ ((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) | 0x49901400)
           | ~(~((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) & 0x49901400)
             | (6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality)
             | 0x49901400))
         | 0x236820)) == ~((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) ^ 0x49B37C20
                         | ~((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality) | 0x49B37C20))
                       + ((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality)
                        ^ 0x49B37C20
                        ^ (6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality)
                        & 0x49B37C20
                        | ((6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality)
                         ^ 0x49B37C20)
                        & (6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality)
                        & 0x49B37C20)
                       - 6061272 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality
                       - 1236499488 )
    goto LABEL_9;
  v11 = 2583086 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality;
  if ( ~(~(~(~(v11 | 0x23838306) | ~(v11 ^ 0x23838306 | ~(v11 | 0x23838306))) | 0x5C20D8)
       | ~(~(~(v11 | 0x23838306) | ~(v11 ^ 0x23838306 | ~(v11 | 0x23838306))) ^ 0x5C20D8
         | ~(~(~(v11 | 0x23838306) | ~(v11 ^ 0x23838306 | ~(v11 | 0x23838306))) | 0x5C20D8))) != ~(v11 ^ 0x23DFA3DE
                                                                                                 | ~(v11 | 0x23DFA3DE))
                                                                                               + (v11 ^ 0x23DFA3DE
                                                                                                | ~(v11 ^ 0x23DFA3DE
                                                                                                  | ~(v11 | 0x23DFA3DE)))
                                                                                               - v11
                                                                                               - 601859038 )
  {
    v10 = 1677407 * *(unsigned __int8 *)Input::CreateMessage::FormulateImportantQuality;
    if ( ~(~(~(~(v10 | 0x17589511) | v10 & 0x17589511) | 0x264A24) | ~(~(v10 | 0x17589511) | v10 & 0x17589511)
                                                                   & 0x264A24) == ~(v10 ^ 0x177EDF35
                                                                                  | ~(v10 | 0x177EDF35))
                                                                                + (v10 ^ 0x177EDF35 | v10 & 0x177EDF35)
                                                                                - v10
                                                                                - 394190645 )
    {
      v7 = *((char *)Input::CreateMessage::FormulateImportantQuality + 1);
      v8 = (char *)Input::CreateMessage::FormulateImportantQuality + 2;
      v9 = (v7 & 0x80u) != 0LL;
      if ( (char)v7 > 0 )
      {
        if ( (__int64)v8 > 0x7FFFFFFFFFFFFFFFLL - v7 )
          goto LABEL_21;
        v9 = (v7 & 0x80u) != 0LL;
      }
      if ( !v9 || (__int64)v8 >= (__int64)(0x8000000000000000uLL - v7) )
      {
        v13 = (unsigned __int8)v8[v7];
        if ( ~(~(~(~((2583086 * v13) | 0x1F6898A8) | (2583086 * v13) & 0x1F6898A8) | 0x400)
             | ~(~((2583086 * v13) | 0x1F6898A8) | (2583086 * v13) & 0x1F6898A8) & 0x400) == ~((2583086 * v13)
                                                                                             ^ 0x1F689CA8
                                                                                             | ~((2583086 * v13)
                                                                                               | 0x1F689CA8))
                                                                                           + ((2583086 * v13)
                                                                                            ^ 0x1F689CA8
                                                                                            | (2583086 * v13)
                                                                                            & 0x1F689CA8)
                                                                                           - 2583086 * v13
                                                                                           - 526949544 )
          goto LABEL_9;
      }
    }
LABEL_21:
    v5 = IntegralRelation::OddMap;
    goto LABEL_10;
  }
  v4 = *(int *)((char *)Input::CreateMessage::FormulateImportantQuality + 1);
  if ( v4 <= 0 )
  {
    if ( v4 < 0 && (__int64)&loc_180023FD5 < (__int64)(0x8000000000000000uLL - v4) )
      goto LABEL_21;
    goto LABEL_8;
  }
  if ( (__int64)&loc_180023FD5 <= 0x7FFFFFFFFFFFFFFFLL - v4 )
  {
LABEL_8:
    v12 = *((unsigned __int8 *)&loc_180023FD5 + v4);
    if ( ~(~(~(~((6061272 * v12) | 0x49901400) | (6061272 * v12) & 0x49901400) | 0x236820)
         | ~(~((6061272 * v12) | 0x49901400) | (6061272 * v12) & 0x49901400) & 0x236820) == ~((6061272 * v12)
                                                                                            ^ 0x49B37C20
                                                                                            | ~((6061272 * v12)
                                                                                              | 0x49B37C20))
                                                                                          + ((6061272 * v12)
                                                                                           ^ 0x49B37C20
                                                                                           | (6061272 * v12)
                                                                                           & 0x49B37C20)
                                                                                          - 6061272 * v12
                                                                                          - 1236499488 )
    {
LABEL_9:
      v5 = ++IntegralRelation::OddMap;
      goto LABEL_10;
    }
    goto LABEL_21;
  }
  v5 = IntegralRelation::OddMap;
LABEL_10:
  if ( *retaddr == (unsigned __int8)(((unsigned int)v5 ^ 0xDE609EFB) / 0x2F3EAE)
    || ((unsigned int)v5 ^ 0xFB432427) != 0x864874 )
  {
    v5 = (unsigned int)(v5 + 1);
    IntegralRelation::OddMap = v5;
  }
  MixedProvider = (void (__fastcall *)(void (__fastcall *)(struct Input::CreateMessage *, struct Input::GeneralEvent *), unsigned __int64, __int64))GenerateMixedProvider(0xFBF5FBFE060D040LL, 3775176810LL, v5);
  MixedProvider(
    Input::CreateMessage::StartCreateStrategy,
    (unsigned __int64)Input::CreateMessage::StartCreateStrategy ^ 0x178113,
    491779);
  Input::CreateMessage::FormulateImportantQuality(this, a2);
}

```

## disassembly

```asm
0x1800251e0  mov     [rsp-8+arg_10], rbx
0x1800251e5  mov     [rsp-8+arg_18], rdi
0x1800251ea  push    rbp
0x1800251eb  mov     rbp, rsp
0x1800251ee  sub     rsp, 60h
0x1800251f2  mov     rbx, rcx
0x1800251f5  mov     [rbp+var_20], 49901400h
0x1800251fc  lea     r9, ?FormulateImportantQuality@CreateMessage@Input@@QEAAXAEAVGeneralEvent@2@@Z; Input::CreateMessage::FormulateImportantQuality(Input::GeneralEvent &)
0x180025203  mov     rdi, rdx
0x180025206  movzx   eax, byte ptr [r9]
0x18002520a  mov     [rbp+var_28], eax
0x18002520d  mov     eax, [rbp+var_28]
0x180025210  imul    ecx, eax, 5C7CD8h
0x180025216  mov     eax, [rbp+var_20]
0x180025219  mov     [rbp+var_18], eax
0x18002521c  mov     [rbp+var_10], ecx
0x18002521f  mov     eax, [rbp+var_10]
0x180025222  mov     [rbp+var_38], eax
0x180025225  mov     ecx, [rbp+var_38]
0x180025228  mov     eax, [rbp+var_18]
0x18002522b  and     ecx, eax
0x18002522d  mov     eax, [rbp+var_20]
0x180025230  not     ecx
0x180025232  mov     [rbp+var_20], eax
0x180025235  mov     eax, [rbp+var_10]
0x180025238  mov     [rbp+var_38], eax
0x18002523b  mov     [rbp+var_18], ecx
0x18002523e  mov     ecx, [rbp+var_38]
0x180025241  mov     eax, [rbp+var_20]
0x180025244  or      ecx, eax
0x180025246  mov     eax, [rbp+var_18]
0x180025249  mov     [rbp+var_20], ecx
0x18002524c  mov     [rbp+var_10], eax
0x18002524f  mov     eax, [rbp+var_20]
0x180025252  mov     [rbp+var_38], eax
0x180025255  mov     ecx, [rbp+var_38]
0x180025258  mov     eax, [rbp+var_10]
0x18002525b  xor     ecx, eax
0x18002525d  mov     eax, [rbp+var_18]
0x180025260  mov     [rbp+var_10], ecx
0x180025263  mov     [rbp+var_18], eax
0x180025266  mov     eax, [rbp+var_20]
0x180025269  mov     [rbp+var_38], eax
0x18002526c  mov     ecx, [rbp+var_38]
0x18002526f  mov     eax, [rbp+var_18]
0x180025272  or      ecx, eax
0x180025274  not     ecx
0x180025276  mov     [rbp+var_18], 236820h
0x18002527d  mov     [rbp+var_38], ecx
0x180025280  mov     ecx, [rbp+var_38]
0x180025283  mov     eax, [rbp+var_10]
0x180025286  or      ecx, eax
0x180025288  mov     eax, [rbp+var_18]
0x18002528b  not     ecx
0x18002528d  mov     [rbp+var_20], ecx
0x180025290  mov     [rbp+var_10], eax
0x180025293  mov     eax, [rbp+var_20]
0x180025296  mov     [rbp+var_38], eax
0x180025299  mov     ecx, [rbp+var_38]
0x18002529c  mov     eax, [rbp+var_10]
0x18002529f  and     ecx, eax
0x1800252a1  mov     eax, [rbp+var_18]
0x1800252a4  not     ecx
0x1800252a6  mov     [rbp+var_18], eax
0x1800252a9  mov     eax, [rbp+var_20]
0x1800252ac  mov     [rbp+var_38], eax
0x1800252af  mov     [rbp+var_10], ecx
0x1800252b2  mov     ecx, [rbp+var_38]
0x1800252b5  mov     eax, [rbp+var_18]
0x1800252b8  or      ecx, eax
0x1800252ba  mov     eax, [rbp+var_10]
0x1800252bd  mov     [rbp+var_18], ecx
0x1800252c0  mov     [rbp+var_20], eax
0x1800252c3  mov     eax, [rbp+var_18]
0x1800252c6  mov     [rbp+var_38], eax
0x1800252c9  mov     ecx, [rbp+var_38]
0x1800252cc  mov     eax, [rbp+var_20]
0x1800252cf  xor     ecx, eax
0x1800252d1  mov     eax, [rbp+var_10]
0x1800252d4  mov     [rbp+var_20], eax
0x1800252d7  mov     eax, [rbp+var_18]
0x1800252da  mov     [rbp+var_38], eax
0x1800252dd  mov     [rbp+var_40], ecx
0x1800252e0  mov     ecx, [rbp+var_38]
0x1800252e3  mov     eax, [rbp+var_20]
0x1800252e6  or      ecx, eax
0x1800252e8  not     ecx
0x1800252ea  mov     [rbp+var_18], 49901400h
0x1800252f1  mov     [rbp+var_38], ecx
0x1800252f4  mov     r8d, [rbp+var_38]
0x1800252f8  mov     eax, [rbp+var_40]
0x1800252fb  or      r8d, eax
0x1800252fe  mov     eax, [rbp+var_18]
0x180025301  not     r8d
0x180025304  mov     [rbp+var_38], eax
0x180025307  mov     [rbp+var_20], 236820h
0x18002530e  mov     eax, [rbp+var_20]
0x180025311  mov     [rbp+var_40], eax
0x180025314  mov     ecx, [rbp+var_40]
0x180025317  mov     eax, [rbp+var_38]
0x18002531a  and     ecx, eax
0x18002531c  mov     eax, [rbp+var_18]
0x18002531f  not     ecx
0x180025321  mov     [rbp+var_38], eax
0x180025324  mov     eax, [rbp+var_20]
0x180025327  mov     [rbp+var_40], eax
0x18002532a  mov     [rbp+var_10], ecx
0x18002532d  mov     ecx, [rbp+var_40]
0x180025330  mov     eax, [rbp+var_38]
0x180025333  or      ecx, eax
0x180025335  mov     eax, [rbp+var_10]
0x180025338  mov     [rbp+var_38], eax
0x18002533b  mov     [rbp+var_18], ecx
0x18002533e  mov     eax, [rbp+var_18]
0x180025341  mov     [rbp+var_40], eax
0x180025344  mov     ecx, [rbp+var_40]
0x180025347  mov     eax, [rbp+var_38]
0x18002534a  xor     ecx, eax
0x18002534c  mov     eax, [rbp+var_10]
0x18002534f  mov     [rbp+var_38], eax
0x180025352  mov     eax, [rbp+var_18]
0x180025355  mov     [rbp+var_40], eax
0x180025358  mov     [rbp+var_20], ecx
0x18002535b  mov     ecx, [rbp+var_40]
0x18002535e  mov     eax, [rbp+var_38]
0x180025361  or      ecx, eax
0x180025363  not     ecx
0x180025365  mov     [rbp+var_40], ecx
0x180025368  mov     ecx, [rbp+var_40]
0x18002536b  mov     eax, [rbp+var_20]
0x18002536e  or      ecx, eax
0x180025370  mov     eax, [rbp+var_28]
0x180025373  not     ecx
0x180025375  mov     [rbp+var_20], ecx
0x180025378  imul    ecx, eax, 5C7CD8h
0x18002537e  mov     eax, [rbp+var_20]
0x180025381  mov     [rbp+var_28], eax
0x180025384  mov     [rbp+var_10], ecx
0x180025387  mov     eax, [rbp+var_10]
0x18002538a  mov     [rbp+var_18], eax
0x18002538d  mov     eax, [rbp+var_28]
0x180025390  mov     [rbp+var_38], eax
0x180025393  mov     eax, [rbp+var_18]
0x180025396  mov     [rbp+var_40], eax
0x180025399  mov     ecx, [rbp+var_40]
0x18002539c  mov     eax, [rbp+var_38]
0x18002539f  xor     ecx, eax
0x1800253a1  mov     eax, [rbp+var_28]
0x1800253a4  mov     [rbp+var_28], eax
0x1800253a7  mov     eax, [rbp+var_18]
0x1800253aa  mov     [rbp+var_40], eax
0x1800253ad  mov     [rbp+var_38], ecx
0x1800253b0  mov     ecx, [rbp+var_40]
0x1800253b3  mov     eax, [rbp+var_28]
0x1800253b6  and     ecx, eax
0x1800253b8  mov     eax, [rbp+var_38]
0x1800253bb  mov     [rbp+var_18], eax
0x1800253be  mov     [rbp+var_28], ecx
0x1800253c1  mov     eax, [rbp+var_28]
0x1800253c4  mov     [rbp+var_40], eax
0x1800253c7  mov     ecx, [rbp+var_40]
0x1800253ca  mov     eax, [rbp+var_18]
0x1800253cd  xor     ecx, eax
0x1800253cf  mov     eax, [rbp+var_38]
0x1800253d2  mov     [rbp+var_38], eax
0x1800253d5  mov     eax, [rbp+var_28]
0x1800253d8  mov     [rbp+var_18], ecx
0x1800253db  mov     [rbp+var_40], eax
0x1800253de  mov     ecx, [rbp+var_40]
0x1800253e1  mov     eax, [rbp+var_38]
0x1800253e4  and     ecx, eax
0x1800253e6  mov     [rbp+var_40], ecx
0x1800253e9  mov     edx, [rbp+var_40]
0x1800253ec  mov     eax, [rbp+var_18]
0x1800253ef  or      edx, eax
0x1800253f1  mov     eax, [rbp+var_20]
0x1800253f4  mov     [rbp+var_38], eax
0x1800253f7  mov     eax, [rbp+var_10]
0x1800253fa  mov     [rbp+var_28], eax
0x1800253fd  mov     eax, [rbp+var_38]
0x180025400  mov     [rbp+var_18], eax
0x180025403  mov     eax, [rbp+var_28]
0x180025406  mov     [rbp+var_40], eax
0x180025409  mov     ecx, [rbp+var_40]
0x18002540c  mov     eax, [rbp+var_18]
0x18002540f  xor     ecx, eax
0x180025411  mov     eax, [rbp+var_38]
0x180025414  mov     [rbp+var_18], ecx
0x180025417  mov     [rbp+var_38], eax
0x18002541a  mov     eax, [rbp+var_28]
0x18002541d  mov     [rbp+var_40], eax
0x180025420  mov     ecx, [rbp+var_40]
0x180025423  mov     eax, [rbp+var_38]
0x180025426  or      ecx, eax
0x180025428  not     ecx
0x18002542a  mov     [rbp+var_40], ecx
0x18002542d  mov     ecx, [rbp+var_40]
0x180025430  mov     eax, [rbp+var_18]
0x180025433  or      ecx, eax
0x180025435  mov     eax, [rbp+var_10]
0x180025438  not     ecx
0x18002543a  add     edx, ecx
0x18002543c  sub     edx, eax
0x18002543e  mov     eax, [rbp+var_20]
0x180025441  sub     edx, eax
0x180025443  cmp     r8d, edx
0x180025446  jz      loc_1800258BD
0x18002544c  movzx   eax, byte ptr [r9]
0x180025450  mov     [rbp+var_18], eax
0x180025453  mov     eax, [rbp+var_18]
0x180025456  imul    ecx, eax, 276A2Eh
0x18002545c  mov     [rbp+var_38], 23838306h
0x180025463  mov     eax, [rbp+var_38]
0x180025466  mov     [rbp+var_20], eax
0x180025469  mov     [rbp+var_28], ecx
0x18002546c  mov     eax, [rbp+var_28]
0x18002546f  mov     [rbp+var_40], eax
0x180025472  mov     ecx, [rbp+var_40]
0x180025475  mov     eax, [rbp+var_20]
0x180025478  or      ecx, eax
0x18002547a  mov     eax, [rbp+var_38]
0x18002547d  not     ecx
0x18002547f  mov     [rbp+var_38], eax
0x180025482  mov     eax, [rbp+var_28]
0x180025485  mov     [rbp+var_28], eax
0x180025488  mov     eax, [rbp+var_38]
0x18002548b  mov     [rbp+var_20], eax
0x18002548e  mov     eax, [rbp+var_28]
0x180025491  mov     [rbp+var_40], eax
0x180025494  mov     [rbp+var_10], ecx
0x180025497  mov     ecx, [rbp+var_40]
0x18002549a  mov     eax, [rbp+var_20]
0x18002549d  xor     ecx, eax
0x18002549f  mov     eax, [rbp+var_38]
0x1800254a2  mov     [rbp+var_38], eax
0x1800254a5  mov     eax, [rbp+var_28]
0x1800254a8  mov     [rbp+var_40], eax
0x1800254ab  mov     [rbp+var_20], ecx
0x1800254ae  mov     ecx, [rbp+var_40]
0x1800254b1  mov     eax, [rbp+var_38]
0x1800254b4  or      ecx, eax
0x1800254b6  not     ecx
0x1800254b8  mov     [rbp+var_40], ecx
0x1800254bb  mov     ecx, [rbp+var_40]
0x1800254be  mov     eax, [rbp+var_20]
0x1800254c1  or      ecx, eax
0x1800254c3  mov     eax, [rbp+var_10]
0x1800254c6  not     ecx
0x1800254c8  mov     [rbp+var_38], eax
0x1800254cb  mov     [rbp+var_40], ecx
0x1800254ce  mov     eax, [rbp+var_40]
0x1800254d1  mov     [rbp+var_40], eax
0x1800254d4  mov     ecx, [rbp+var_40]
0x1800254d7  mov     eax, [rbp+var_38]
0x1800254da  or      ecx, eax
0x1800254dc  mov     [rbp+var_40], ecx
0x1800254df  mov     eax, [rbp+var_40]
0x1800254e2  not     eax
0x1800254e4  mov     [rbp+var_38], 5C20D8h
0x1800254eb  mov     [rbp+var_28], eax
0x1800254ee  mov     eax, [rbp+var_38]
0x1800254f1  mov     [rbp+var_20], eax
0x1800254f4  mov     eax, [rbp+var_28]
0x1800254f7  mov     [rbp+var_40], eax
0x1800254fa  mov     ecx, [rbp+var_40]
0x1800254fd  mov     eax, [rbp+var_20]
0x180025500  or      ecx, eax
0x180025502  mov     eax, [rbp+var_38]
0x180025505  not     ecx
0x180025507  mov     [rbp+var_38], eax
0x18002550a  mov     eax, [rbp+var_28]
0x18002550d  mov     [rbp+var_28], eax
0x180025510  mov     eax, [rbp+var_38]
0x180025513  mov     [rbp+var_20], eax
0x180025516  mov     eax, [rbp+var_28]
0x180025519  mov     [rbp+var_40], eax
0x18002551c  mov     [rbp+var_10], ecx
0x18002551f  mov     ecx, [rbp+var_40]
0x180025522  mov     eax, [rbp+var_20]
0x180025525  xor     ecx, eax
0x180025527  mov     eax, [rbp+var_38]
0x18002552a  mov     [rbp+var_38], eax
0x18002552d  mov     eax, [rbp+var_28]
0x180025530  mov     [rbp+var_40], eax
0x180025533  mov     [rbp+var_20], ecx
0x180025536  mov     ecx, [rbp+var_40]
0x180025539  mov     eax, [rbp+var_38]
0x18002553c  or      ecx, eax
0x18002553e  not     ecx
0x180025540  mov     [rbp+var_28], 5C20D8h
0x180025547  mov     [rbp+var_40], ecx
0x18002554a  mov     ecx, [rbp+var_40]
0x18002554d  mov     eax, [rbp+var_20]
0x180025550  or      ecx, eax
0x180025552  mov     eax, [rbp+var_10]
0x180025555  not     ecx
0x180025557  mov     [rbp+var_38], eax
0x18002555a  mov     [rbp+var_40], ecx
0x18002555d  mov     eax, [rbp+var_40]
0x180025560  mov     [rbp+var_40], eax
  ... truncated ...
```

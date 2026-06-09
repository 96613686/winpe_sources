# AnchoredPopupPositioningBehavior::CalculateWindowRect(tagPOINT,AnchorPointType,winrt::Windows::Foundation::Size)

- ea: `0x180022ff8`
- end: `0x1800232ae`
- name: `?CalculateWindowRect@AnchoredPopupPositioningBehavior@@AEAA?AUtagRECT@@UtagPOINT@@W4AnchorPointType@@USize@Foundation@Windows@winrt@@@Z`
- size: `694`
- prototype: `struct tagRECT __high(struct tagPOINT, enum AnchorPointType, struct winrt::Windows::Foundation::Size)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180026120`

## callees

- `0x180002ae8`
- `0x1800228f4`
- `0x180022ff8`
- `0x180023814`
- `0x1800271a0`
- `0x18002cc80`

## import_xrefs

- `USER32!MonitorFromPoint` at `0x18002302d`
- `USER32!MonitorFromPoint` at `0x18002302d`

## string_xrefs

- `0x18002313a`: `pcshell\shell\uxframe\dll\WindowPositioningBehavior.h`

## pseudocode

```c
__int64 __fastcall AnchoredPopupPositioningBehavior::CalculateWindowRect(
        __int64 a1,
        __int64 a2,
        POINT a3,
        unsigned int a4,
        unsigned __int64 a5)
{
  HMONITOR v8; // rax
  int v9; // r14d
  int v10; // r15d
  unsigned int v11; // esi
  unsigned int v12; // esi
  unsigned int v13; // esi
  unsigned int v14; // esi
  unsigned int v15; // esi
  unsigned int v16; // esi
  int v17; // esi
  int v18; // ecx
  LONG y; // edx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // eax
  int v24; // ecx
  LONG v25; // ecx
  LONG v26; // eax
  const char *v28; // [rsp+28h] [rbp-40h]
  char v29; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  POINT v31; // [rsp+70h] [rbp+8h] BYREF
  POINT v32; // [rsp+80h] [rbp+18h]

  v32 = a3;
  v31.y = HIDWORD(a1);
  v31.x = 0;
  v8 = MonitorFromPoint(a3, 0);
  GetWorkAreaAndDpiForMonitorWithFallback(v8, 0, (unsigned int *)&v31);
  *(_OWORD *)a2 = 0;
  v9 = (int)o_roundf_0();
  v10 = (int)o_roundf_0();
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetImpl'::`2'::impl) )
  {
    if ( !a4 )
    {
      v18 = v10 + v32.y;
      *(POINT *)a2 = a3;
      goto LABEL_25;
    }
    v11 = a4 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                v17 = v16 - 1;
                if ( !v17 )
                {
                  y = v32.y;
                  *(_DWORD *)(a2 + 12) = v32.y;
                  *(_DWORD *)a2 = a3.x - v9 / 2;
                  *(_DWORD *)(a2 + 4) = y - v10;
                  *(_DWORD *)(a2 + 8) = a3.x + v9 / 2;
                  return a2;
                }
                if ( v17 != 1 )
                  wil::details::in1diag3::FailFast_HrMsg(
                    retaddr,
                    (void *)0x1CC,
                    (unsigned int)"pcshell\\shell\\uxframe\\dll\\WindowPositioningBehavior.h",
                    (const char *)0x80070057LL,
                    (int)"Invalid AnchorPointType provided",
                    v28);
                v18 = v32.y;
                *(_DWORD *)(a2 + 8) = a3.x;
                *(_DWORD *)a2 = a3.x - v9;
                *(_DWORD *)(a2 + 4) = v18 - v10;
LABEL_26:
                *(_DWORD *)(a2 + 12) = v18;
                return a2;
              }
              v18 = v32.y;
              v20 = v32.y - v10;
              *(_DWORD *)a2 = a3.x;
              *(_DWORD *)(a2 + 4) = v20;
LABEL_25:
              *(_DWORD *)(a2 + 8) = v9 + a3.x;
              goto LABEL_26;
            }
            *(_DWORD *)(a2 + 8) = a3.x;
            *(_DWORD *)a2 = a3.x - v9;
            v21 = v32.y - v10 / 2;
            v22 = v32.y + v10 / 2;
            goto LABEL_22;
          }
          *(_DWORD *)a2 = a3.x - v9 / 2;
          v23 = v10 / 2;
          *(_DWORD *)(a2 + 4) = v32.y - v10 / 2;
          v24 = v9 / 2 + a3.x;
        }
        else
        {
          v25 = v32.y;
          *(_DWORD *)a2 = a3.x;
          v23 = v10 / 2;
          *(_DWORD *)(a2 + 4) = v25 - v10 / 2;
          v24 = v9 + a3.x;
        }
        v22 = v32.y + v23;
        *(_DWORD *)(a2 + 8) = v24;
      }
      else
      {
        *(_DWORD *)(a2 + 8) = a3.x;
        *(_DWORD *)a2 = a3.x - v9;
        v26 = v32.y;
        *(_DWORD *)(a2 + 4) = v32.y;
        v22 = v10 + v26;
      }
LABEL_23:
      *(_DWORD *)(a2 + 12) = v22;
      return a2;
    }
    *(_DWORD *)a2 = a3.x - v9 / 2;
    v21 = v32.y;
    *(_DWORD *)(a2 + 8) = a3.x + v9 / 2;
    v22 = v10 + v21;
LABEL_22:
    *(_DWORD *)(a2 + 4) = v21;
    goto LABEL_23;
  }
  a5 = __PAIR64__(v10, v9);
  v31 = a3;
  *(_OWORD *)a2 = *(_OWORD *)AlignToAnchorPoint(&v29, &v31, a4, &a5);
  return a2;
}

```

## disassembly

```asm
0x180022ff8  mov     rax, rsp
0x180022ffb  mov     [rax+10h], rbx
0x180022fff  mov     [rax+20h], rsi
0x180023003  mov     [rax+18h], r8
0x180023007  mov     [rax+8], rcx
0x18002300b  push    rdi
0x18002300c  push    r14
0x18002300e  push    r15
0x180023010  sub     rsp, 50h
0x180023014  mov     rdi, rdx
0x180023017  movaps  xmmword ptr [rax-28h], xmm7
0x18002301b  xor     edx, edx; dwFlags
0x18002301d  mov     dword ptr [rax+8], 0
0x180023024  mov     rcx, r8; pt
0x180023027  mov     esi, r9d
0x18002302a  mov     rbx, r8
0x18002302d  call    cs:__imp_MonitorFromPoint
0x180023033  lea     r8, [rsp+68h+arg_0]; unsigned int *
0x180023038  xor     edx, edx; struct tagRECT *
0x18002303a  mov     rcx, rax; HMONITOR
0x18002303d  call    ?GetWorkAreaAndDpiForMonitorWithFallback@@YAXPEAUHMONITOR__@@PEAUtagRECT@@PEAI@Z; GetWorkAreaAndDpiForMonitorWithFallback(HMONITOR__ *,tagRECT *,uint *)
0x180023042  mov     eax, dword ptr [rsp+68h+arg_0]
0x180023046  xorps   xmm0, xmm0
0x180023049  movups  xmmword ptr [rdi], xmm0
0x18002304c  xorps   xmm7, xmm7
0x18002304f  cvtsi2ss xmm7, rax
0x180023054  movaps  xmm0, xmm7
0x180023057  mulss   xmm0, [rsp+68h+arg_20]
0x180023060  divss   xmm0, cs:__real@42c00000
0x180023068  call    _o_roundf_0
0x18002306d  mulss   xmm7, [rsp+68h+arg_24]
0x180023076  cvttss2si r14d, xmm0
0x18002307b  divss   xmm7, cs:__real@42c00000
0x180023083  movaps  xmm0, xmm7
0x180023086  call    _o_roundf_0
0x18002308b  cvttss2si r15d, xmm0
0x180023090  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior> `wil::Feature<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::GetImpl(void)'::`2'::impl
0x180023097  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OverlappedWindowBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OverlappedWindowBehavior>::__private_IsEnabled(void)
0x18002309c  test    al, al
0x18002309e  jz      short loc_1800230DB
0x1800230a0  lea     r9, [rsp+68h+arg_20]
0x1800230a8  mov     [rsp+68h+arg_20], r14d
0x1800230b0  mov     r8d, esi
0x1800230b3  mov     [rsp+68h+arg_24], r15d
0x1800230bb  lea     rdx, [rsp+68h+arg_0]
0x1800230c0  mov     [rsp+68h+arg_0], rbx
0x1800230c5  lea     rcx, [rsp+68h+var_38]
0x1800230ca  call    ?AlignToAnchorPoint@@YA?AUCRect@Geometry@@AEBUCPoint@2@W4AnchorPointType@@AEBUCSize@2@@Z; AlignToAnchorPoint(Geometry::CPoint const &,AnchorPointType,Geometry::CSize const &)
0x1800230cf  movups  xmm0, xmmword ptr [rax]
0x1800230d2  movdqu  xmmword ptr [rdi], xmm0
0x1800230d6  jmp     loc_180023290
0x1800230db  test    esi, esi
0x1800230dd  jz      loc_180023279
0x1800230e3  sub     esi, 1
0x1800230e6  jz      loc_18002324E
0x1800230ec  sub     esi, 1
0x1800230ef  jz      loc_180023235
0x1800230f5  sub     esi, 1
0x1800230f8  jz      loc_18002320A
0x1800230fe  sub     esi, 1
0x180023101  jz      loc_1800231DB
0x180023107  sub     esi, 1
0x18002310a  jz      loc_1800231AF
0x180023110  sub     esi, 1
0x180023113  jz      loc_180023199
0x180023119  sub     esi, 1
0x18002311c  jz      short loc_18002316A
0x18002311e  cmp     esi, 1
0x180023121  jz      short loc_18002314C
0x180023123  mov     rcx, [rsp+68h]; this
0x180023128  lea     rax, aInvalidAnchorp_0; "Invalid AnchorPointType provided"
0x18002312f  mov     r9d, 80070057h; char *
0x180023135  mov     qword ptr [rsp+68h+var_48], rax; int
0x18002313a  lea     r8, aPcshellShellUx_1; "pcshell\\shell\\uxframe\\dll\\WindowPos"...
0x180023141  mov     edx, 1CCh; void *
0x180023146  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002314c  mov     ecx, [rsp+68h+arg_14]
0x180023153  mov     eax, ebx
0x180023155  sub     eax, r14d
0x180023158  mov     [rdi+8], ebx
0x18002315b  mov     [rdi], eax
0x18002315d  mov     eax, ecx
0x18002315f  sub     eax, r15d
0x180023162  mov     [rdi+4], eax
0x180023165  jmp     loc_18002328D
0x18002316a  mov     eax, r14d
0x18002316d  mov     r9d, 2
0x180023173  cdq
0x180023174  mov     ecx, ebx
0x180023176  idiv    r9d
0x180023179  mov     edx, [rsp+68h+arg_14]
0x180023180  sub     ecx, eax
0x180023182  mov     [rdi+0Ch], edx
0x180023185  mov     [rdi], ecx
0x180023187  mov     ecx, edx
0x180023189  sub     ecx, r15d
0x18002318c  add     eax, ebx
0x18002318e  mov     [rdi+4], ecx
0x180023191  mov     [rdi+8], eax
0x180023194  jmp     loc_180023290
0x180023199  mov     ecx, [rsp+68h+arg_14]
0x1800231a0  mov     eax, ecx
0x1800231a2  sub     eax, r15d
0x1800231a5  mov     [rdi], ebx
0x1800231a7  mov     [rdi+4], eax
0x1800231aa  jmp     loc_180023286
0x1800231af  mov     eax, r15d
0x1800231b2  mov     [rdi+8], ebx
0x1800231b5  cdq
0x1800231b6  mov     r9d, 2
0x1800231bc  idiv    r9d
0x1800231bf  mov     ecx, ebx
0x1800231c1  sub     ecx, r14d
0x1800231c4  mov     [rdi], ecx
0x1800231c6  mov     ecx, [rsp+68h+arg_14]
0x1800231cd  sub     ecx, eax
0x1800231cf  add     eax, [rsp+68h+arg_14]
0x1800231d6  jmp     loc_180023271
0x1800231db  mov     r9d, 2
0x1800231e1  mov     eax, r14d
0x1800231e4  cdq
0x1800231e5  mov     ecx, ebx
0x1800231e7  idiv    r9d
0x1800231ea  sub     ecx, eax
0x1800231ec  mov     r8d, eax
0x1800231ef  mov     [rdi], ecx
0x1800231f1  mov     eax, r15d
0x1800231f4  mov     ecx, [rsp+68h+arg_14]
0x1800231fb  cdq
0x1800231fc  idiv    r9d
0x1800231ff  sub     ecx, eax
0x180023201  mov     [rdi+4], ecx
0x180023204  lea     ecx, [r8+rbx]
0x180023208  jmp     short loc_180023229
0x18002320a  mov     ecx, [rsp+68h+arg_14]
0x180023211  mov     eax, r15d
0x180023214  cdq
0x180023215  mov     [rdi], ebx
0x180023217  mov     r9d, 2
0x18002321d  idiv    r9d
0x180023220  sub     ecx, eax
0x180023222  mov     [rdi+4], ecx
0x180023225  lea     ecx, [r14+rbx]
0x180023229  add     eax, [rsp+68h+arg_14]
0x180023230  mov     [rdi+8], ecx
0x180023233  jmp     short loc_180023274
0x180023235  mov     eax, ebx
0x180023237  mov     [rdi+8], ebx
0x18002323a  sub     eax, r14d
0x18002323d  mov     [rdi], eax
0x18002323f  mov     eax, [rsp+68h+arg_14]
0x180023246  mov     [rdi+4], eax
0x180023249  add     eax, r15d
0x18002324c  jmp     short loc_180023274
0x18002324e  mov     eax, r14d
0x180023251  mov     r9d, 2
0x180023257  cdq
0x180023258  mov     ecx, ebx
0x18002325a  idiv    r9d
0x18002325d  sub     ecx, eax
0x18002325f  add     eax, ebx
0x180023261  mov     [rdi], ecx
0x180023263  mov     ecx, [rsp+68h+arg_14]
0x18002326a  mov     [rdi+8], eax
0x18002326d  lea     eax, [r15+rcx]
0x180023271  mov     [rdi+4], ecx
0x180023274  mov     [rdi+0Ch], eax
0x180023277  jmp     short loc_180023290
0x180023279  mov     ecx, [rsp+68h+arg_14]
0x180023280  add     ecx, r15d
0x180023283  mov     [rdi], rbx
0x180023286  lea     eax, [r14+rbx]
0x18002328a  mov     [rdi+8], eax
0x18002328d  mov     [rdi+0Ch], ecx
0x180023290  movaps  xmm7, [rsp+68h+var_28]
0x180023295  lea     r11, [rsp+68h+var_18]
0x18002329a  mov     rbx, [r11+28h]
0x18002329e  mov     rax, rdi
0x1800232a1  mov     rsi, [r11+38h]
0x1800232a5  mov     rsp, r11
0x1800232a8  pop     r15
0x1800232aa  pop     r14
0x1800232ac  pop     rdi
0x1800232ad  retn
```

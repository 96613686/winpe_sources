# LineScroller::_LayoutContent(OFFSCREENCONTENT)

- ea: `0x1800126dc`
- end: `0x180012cc3`
- name: `?_LayoutContent@LineScroller@@AEAAXW4OFFSCREENCONTENT@@@Z`
- size: `1511`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180011200`
- `0x18004a194`
- `0x18004af64`
- `0x1801e93ac`

## callees

- `0x1800125f8`
- `0x180012640`
- `0x1800126dc`
- `0x180012e50`
- `0x180013b44`
- `0x1800141d0`
- `0x180014630`
- `0x180016790`
- `0x180047410`
- `0x1800a0660`
- `0x1800a0b88`
- `0x1800d14dc`
- `0x18013f7d0`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x180012a4d`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x180012a4d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001287c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800129b7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800129fa`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001287c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800129b7`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800129fa`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001286c`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800129aa`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800129ed`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18001286c`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800129aa`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800129ed`
- `DUI70!?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z` at `0x180012a6b`
- `DUI70!?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z` at `0x180012a6b`
- `DUI70!?_UpdateLayoutSize@Element@DirectUI@@QEAAXHH@Z` at `0x180012823`
- `DUI70!?_UpdateLayoutSize@Element@DirectUI@@QEAAXHH@Z` at `0x180012823`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180012860`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001299e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800129e1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180012860`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18001299e`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800129e1`
- `DUI70!?IsHosted@Element@DirectUI@@QEAA_NXZ` at `0x1800127b4`
- `DUI70!?IsHosted@Element@DirectUI@@QEAA_NXZ` at `0x1800127b4`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x1800127dc`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x1800127dc`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180012753`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180012753`
- `DUI70!?GetDeferObject@Element@DirectUI@@QEAAPEAVDeferCycle@2@XZ` at `0x18001282c`
- `DUI70!?GetDeferObject@Element@DirectUI@@QEAAPEAVDeferCycle@2@XZ` at `0x18001282c`
- `DUI70!?_FlushLayout@Element@DirectUI@@KAXPEAV12@PEAVDeferCycle@2@@Z` at `0x18001283c`
- `DUI70!?_FlushLayout@Element@DirectUI@@KAXPEAV12@PEAVDeferCycle@2@@Z` at `0x18001283c`

## pseudocode

```c
__int64 __fastcall LineScroller::_LayoutContent(__int64 a1, int a2, __int64 a3)
{
  DirectUI::Element *v5; // rcx
  int v6; // r15d
  __int64 v7; // rbx
  int v8; // esi
  int v9; // r13d
  int v10; // ebx
  const struct tagSIZE *DesiredSize; // rax
  LONG cx; // ebx
  int ScrollableContentWidth; // eax
  int v14; // ecx
  int v15; // r15d
  int v16; // r12d
  struct DirectUI::DeferCycle *DeferObject; // rax
  DirectUI::Value *Value; // rbx
  int RealXAnchor; // r14d
  int v20; // edx
  int v21; // r8d
  int v22; // ebx
  int v23; // r14d
  __int64 v24; // r9
  int v25; // r9d
  int v26; // r10d
  int v27; // edx
  int v28; // r8d
  int v29; // r14d
  int RealYAnchor; // eax
  int v31; // esi
  DirectUI::Value *v32; // rbx
  int RealYTarget; // eax
  int v34; // esi
  DirectUI::Value *v35; // rbx
  int RealXTarget; // eax
  int v37; // r14d
  int v38; // eax
  int v39; // ebx
  int v40; // esi
  int v41; // r12d
  __int64 result; // rax
  int v43; // r12d
  int v44; // eax
  int v45; // ecx
  struct DirectUI::Element *v46; // rsi
  struct DirectUI::Element *v47; // rax
  int v48; // r14d
  int v49; // [rsp+30h] [rbp-D0h]
  int Int; // [rsp+30h] [rbp-D0h]
  int v51; // [rsp+30h] [rbp-D0h]
  struct DirectUI::Value *v52; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v53; // [rsp+40h] [rbp-C0h]
  __int128 v54; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v55; // [rsp+60h] [rbp-A0h]
  _OWORD v56[3]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v57; // [rsp+A0h] [rbp-60h]
  int v58; // [rsp+A8h] [rbp-58h]
  __int64 v59; // [rsp+ACh] [rbp-54h]
  int v60; // [rsp+B8h] [rbp-48h]
  int v61; // [rsp+C0h] [rbp-40h]
  struct DirectUI::Element *v62[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v63; // [rsp+E0h] [rbp-20h]
  __int128 v64; // [rsp+F0h] [rbp-10h]
  __int128 v65; // [rsp+100h] [rbp+0h]
  __int128 v66; // [rsp+110h] [rbp+10h]
  __int64 v67; // [rsp+120h] [rbp+20h]
  int v68; // [rsp+128h] [rbp+28h]
  __int64 v69; // [rsp+12Ch] [rbp+2Ch]
  __int128 v70; // [rsp+150h] [rbp+50h] BYREF
  int v71; // [rsp+160h] [rbp+60h]

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ItemsView_LineScroller_LayoutPass_Start,
      a3,
      1);
  v53 = *(_DWORD *)(a1 + 564);
  v5 = *(DirectUI::Element **)(a1 + 272);
  *(_DWORD *)(a1 + 564) = 1;
  if ( v5 )
  {
    v6 = *(_DWORD *)(a1 + 608);
    v49 = v6;
    v52 = 0;
    v7 = (__int64)*DirectUI::Element::GetExtent(v5, &v52);
    *(_QWORD *)&v70 = v7;
    CValuePtr::~CValuePtr((CValuePtr *)&v52);
    v8 = DWORD1(v70);
    v9 = v7;
    if ( v6 != 1 )
    {
      v9 = DWORD1(v70);
      v8 = v7;
    }
    if ( v8 > 0 && v9 > 0 && *(int *)(a1 + 488) > 0 )
    {
      if ( *(_QWORD *)(a1 + 304) )
      {
        LineScroller::_RealizeContent(a1, a2, a3);
        if ( DirectUI::Element::IsHosted((DirectUI::Element *)a1) && *(int *)(a1 + 512) >= 0 )
        {
          v10 = *(_DWORD *)(a1 + 608);
          DesiredSize = DirectUI::Element::GetDesiredSize(*(DirectUI::Element **)(a1 + 304));
          if ( v10 != 1 )
            DesiredSize = (const struct tagSIZE *)((char *)DesiredSize + 4);
          cx = DesiredSize->cx;
          ScrollableContentWidth = LineScroller::GetScrollableContentWidth((LineScroller *)a1);
          v14 = v8;
          v15 = v9;
          if ( ScrollableContentWidth > v8 )
            v14 = ScrollableContentWidth;
          if ( cx > v9 )
            v15 = cx;
          if ( *(_DWORD *)(a1 + 608) == 1 )
          {
            v16 = v14;
          }
          else
          {
            v16 = v15;
            v15 = v14;
          }
          DirectUI::Element::_UpdateLayoutSize(*(DirectUI::Element **)(a1 + 304), v15, v16);
          DeferObject = DirectUI::Element::GetDeferObject((DirectUI::Element *)a1);
          DirectUI::Element::_FlushLayout(*(struct DirectUI::Element **)(a1 + 304), DeferObject);
          if ( *(_DWORD *)(a1 + 608) == 2 )
          {
            Value = DirectUI::Element::GetValue((DirectUI::Element *)a1, LineScroller::RealYAnchorProp, 1, 0);
            LODWORD(v52) = DirectUI::Value::GetInt(Value);
            RealXAnchor = (int)v52;
            DirectUI::Value::Release(Value);
          }
          else
          {
            RealXAnchor = LineScroller::GetRealXAnchor((LineScroller *)a1);
            LODWORD(v52) = RealXAnchor;
          }
          v20 = *(_DWORD *)(a1 + 488);
          v21 = v20 - 1;
          if ( v20 <= 0 )
            v21 = 0;
          v22 = RealXAnchor / 100;
          if ( RealXAnchor / 100 >= 0 )
          {
            v23 = RealXAnchor / 100;
            if ( v22 > v21 )
              v23 = v21;
          }
          else
          {
            v23 = 0;
          }
          v71 = 0;
          v70 = 0;
          memset_0(&v54, 0, 0x58u);
          v24 = *(_QWORD *)(a1 + 224);
          v59 = 0;
          DWORD2(v55) = -1;
          v58 = -1;
          LineScroller::_GetScrollRow<int>(
            a1,
            (unsigned int) IVirtualizedUI::`vcall'{72,{flat}},
            (unsigned int)s_StepInsideByTick,
            v24,
            v23,
            (__int64)&v54);
          if ( LODWORD(v56[0]) )
          {
            v25 = HIDWORD(v59) - v59;
            if ( HIDWORD(v59) - (int)v59 > 1 )
            {
              v48 = v23 - v59;
              v26 = v48 * (v61 - v60) / v25 + v60;
              v27 = v60 + (v61 - v60) * (v48 + 1) / v25;
            }
            else
            {
              v26 = v60;
              v27 = v61;
            }
            v28 = v26;
          }
          else
          {
            v27 = 0;
            v26 = 0;
            v28 = 0;
          }
          v29 = v28 + (v27 - v26) * ((int)v52 - 100 * v22) / 99;
          if ( v49 == 1 )
          {
            LODWORD(v52) = v8;
          }
          else
          {
            LODWORD(v52) = v9;
            v9 = v8;
          }
          if ( *(_DWORD *)(a1 + 608) == 2 )
            RealYAnchor = LineScroller::GetRealXAnchor((LineScroller *)a1);
          else
            RealYAnchor = LineScroller::GetRealYAnchor((LineScroller *)a1);
          v31 = RealYAnchor;
          if ( *(_DWORD *)(a1 + 608) == 2 )
          {
            v32 = DirectUI::Element::GetValue((DirectUI::Element *)a1, LineScroller::RealXTargetProp, 1, 0);
            Int = DirectUI::Value::GetInt(v32);
            DirectUI::Value::Release(v32);
            RealYTarget = Int;
          }
          else
          {
            RealYTarget = LineScroller::GetRealYTarget((LineScroller *)a1);
          }
          v34 = v31 - RealYTarget;
          if ( *(_DWORD *)(a1 + 608) == 2 )
          {
            v35 = DirectUI::Element::GetValue((DirectUI::Element *)a1, LineScroller::RealYTargetProp, 1, 0);
            v51 = DirectUI::Value::GetInt(v35);
            DirectUI::Value::Release(v35);
            RealXTarget = v51;
          }
          else
          {
            RealXTarget = LineScroller::GetRealXTarget((LineScroller *)a1);
          }
          v37 = v29 - RealXTarget;
          v38 = *(_DWORD *)(a1 + 608);
          if ( v38 == 1 )
          {
            v39 = v34;
          }
          else
          {
            if ( v38 == 2 )
            {
              v43 = v16 - (_DWORD)v52;
              v44 = 0;
              if ( v43 >= 0 )
                v44 = v43;
              if ( v37 >= 0 )
              {
                if ( v37 > v44 )
                  v37 = v44;
              }
              else
              {
                v37 = 0;
              }
              v45 = 0;
              v39 = v37;
              if ( v15 - v9 >= 0 )
                v45 = v15 - v9;
              if ( v34 >= 0 )
              {
                if ( v34 > v45 )
                  v34 = v45;
                goto LABEL_46;
              }
              goto LABEL_65;
            }
            v39 = v37;
            v37 = v34;
          }
          if ( v39 >= 0 )
          {
            if ( v39 > v16 )
              v39 = v16;
          }
          else
          {
            v39 = 0;
          }
          v40 = *(_DWORD *)(a1 + 492);
          v41 = v15;
          if ( *(_DWORD *)(a1 + 500) == v40 )
          {
            memset_0(v62, 0, 0x58u);
            v69 = 0;
            DWORD2(v63) = -1;
            v68 = -1;
            LineScroller::GetRowInfoForRow((LineScroller *)a1, v40 - 1, (struct RowInfo *)v62);
            if ( (_DWORD)v64 )
            {
              v46 = *(struct DirectUI::Element **)(a1 + 304);
              v55 = v63;
              v56[0] = v64;
              v71 = 0;
              v47 = v62[0];
              v56[1] = v65;
              v56[2] = v66;
              v57 = v67;
              v54 = *(_OWORD *)v62;
              v70 = 0;
              if ( v62[0] )
                v47 = (struct DirectUI::Element *)(*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v62[0] + 16LL))(v62[0]);
              DUI_MapElementRectV(v47, v46, (const struct RECTV *)((char *)v56 + 4), (struct RECTV *)&v70);
              v41 = v70;
              if ( v71 == 1 )
                v41 = DWORD1(v70);
            }
          }
          if ( v37 >= 0 )
          {
            v34 = v37;
            if ( v37 > v41 )
              v34 = v41;
            goto LABEL_46;
          }
LABEL_65:
          v34 = 0;
LABEL_46:
          if ( DirectUI::Element::IsRTL((DirectUI::Element *)a1) )
            v34 = v15 - v34 - v9;
          DirectUI::Element::_UpdateLayoutPosition(*(DirectUI::Element **)(a1 + 304), -v34, -v39);
        }
      }
    }
  }
  result = v53;
  *(_DWORD *)(a1 + 564) = v53;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 4) != 0 )
    return McGenEventWrite_EventWriteTransfer(
             &Microsoft_Windows_Shell_Core_Provider_Context,
             ItemsView_LineScroller_LayoutPass_Stop,
             a3,
             1);
  return result;
}

```

## disassembly

```asm
0x1800126dc  push    rbp
0x1800126de  push    rbx
0x1800126df  push    rsi
0x1800126e0  push    rdi
0x1800126e1  push    r12
0x1800126e3  push    r13
0x1800126e5  push    r14
0x1800126e7  push    r15
0x1800126e9  lea     rbp, [rsp-78h]
0x1800126ee  sub     rsp, 178h
0x1800126f5  mov     rax, cs:__security_cookie
0x1800126fc  xor     rax, rsp
0x1800126ff  mov     [rbp+0B0h+var_48], rax
0x180012703  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 4
0x18001270a  mov     r14d, edx
0x18001270d  mov     rdi, rcx
0x180012710  jnz     loc_180012B3D
0x180012716  mov     ecx, [rdi+234h]
0x18001271c  xor     r12d, r12d
0x18001271f  mov     [rsp+1B0h+var_170], ecx
0x180012723  mov     rcx, [rdi+110h]
0x18001272a  mov     dword ptr [rdi+234h], 1
0x180012734  test    rcx, rcx
0x180012737  jz      loc_180012A71
0x18001273d  mov     r15d, [rdi+260h]
0x180012744  lea     rdx, [rsp+1B0h+var_178]
0x180012749  mov     [rsp+1B0h+var_180], r15d
0x18001274e  mov     [rsp+1B0h+var_178], r12
0x180012753  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x180012759  lea     rcx, [rsp+1B0h+var_178]; this
0x18001275e  mov     rbx, [rax]
0x180012761  mov     qword ptr [rbp+0B0h+var_60], rbx
0x180012765  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x18001276a  mov     esi, dword ptr [rbp+0B0h+var_60+4]
0x18001276d  cmp     r15d, 1
0x180012771  mov     r13d, ebx
0x180012774  cmovnz  r13d, esi
0x180012778  cmovnz  esi, ebx
0x18001277b  test    esi, esi
0x18001277d  jle     loc_180012A71
0x180012783  test    r13d, r13d
0x180012786  jle     loc_180012A71
0x18001278c  cmp     [rdi+1E8h], r12d
0x180012793  jle     loc_180012A71
0x180012799  cmp     [rdi+130h], r12
0x1800127a0  jz      loc_180012A71
0x1800127a6  mov     edx, r14d
0x1800127a9  mov     rcx, rdi
0x1800127ac  call    ?_RealizeContent@LineScroller@@AEAAXW4OFFSCREENCONTENT@@@Z; LineScroller::_RealizeContent(OFFSCREENCONTENT)
0x1800127b1  mov     rcx, rdi
0x1800127b4  call    cs:__imp_?IsHosted@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsHosted(void)
0x1800127ba  test    al, al
0x1800127bc  jz      loc_180012A71
0x1800127c2  cmp     [rdi+200h], r12d
0x1800127c9  jl      loc_180012A71
0x1800127cf  mov     rcx, [rdi+130h]
0x1800127d6  mov     ebx, [rdi+260h]
0x1800127dc  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x1800127e2  cmp     ebx, 1
0x1800127e5  jnz     loc_180012B6E
0x1800127eb  mov     ebx, [rax]
0x1800127ed  mov     rcx, rdi; this
0x1800127f0  call    ?GetScrollableContentWidth@LineScroller@@QEAAHXZ; LineScroller::GetScrollableContentWidth(void)
0x1800127f5  cmp     eax, esi
0x1800127f7  mov     ecx, esi
0x1800127f9  mov     r15d, r13d
0x1800127fc  cmovg   ecx, eax
0x1800127ff  cmp     ebx, r13d
0x180012802  cmovg   r15d, ebx
0x180012806  cmp     dword ptr [rdi+260h], 1
0x18001280d  jnz     loc_180012C6E
0x180012813  mov     r12d, ecx
0x180012816  mov     rcx, [rdi+130h]
0x18001281d  mov     r8d, r12d
0x180012820  mov     edx, r15d
0x180012823  call    cs:__imp_?_UpdateLayoutSize@Element@DirectUI@@QEAAXHH@Z; DirectUI::Element::_UpdateLayoutSize(int,int)
0x180012829  mov     rcx, rdi
0x18001282c  call    cs:__imp_?GetDeferObject@Element@DirectUI@@QEAAPEAVDeferCycle@2@XZ; DirectUI::Element::GetDeferObject(void)
0x180012832  mov     rcx, [rdi+130h]
0x180012839  mov     rdx, rax
0x18001283c  call    cs:__imp_?_FlushLayout@Element@DirectUI@@KAXPEAV12@PEAVDeferCycle@2@@Z; DirectUI::Element::_FlushLayout(DirectUI::Element *,DirectUI::DeferCycle *)
0x180012842  cmp     dword ptr [rdi+260h], 2
0x180012849  mov     rcx, rdi; this
0x18001284c  jnz     loc_180012B2C
0x180012852  xor     r9d, r9d
0x180012855  lea     rdx, ?RealYAnchorProp@LineScroller@@SAPEBUPropertyInfo@DirectUI@@XZ; LineScroller::RealYAnchorProp(void)
0x18001285c  lea     r8d, [r9+1]
0x180012860  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180012866  mov     rcx, rax
0x180012869  mov     rbx, rax
0x18001286c  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180012872  mov     rcx, rbx
0x180012875  mov     dword ptr [rsp+1B0h+var_178], eax
0x180012879  mov     r14d, eax
0x18001287c  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180012882  mov     edx, [rdi+1E8h]
0x180012888  xor     ecx, ecx
0x18001288a  test    edx, edx
0x18001288c  mov     eax, 51EB851Fh
0x180012891  lea     r8d, [rdx-1]
0x180012895  cmovle  r8d, ecx
0x180012899  imul    r14d
0x18001289c  mov     ebx, edx
0x18001289e  sar     ebx, 5
0x1800128a1  mov     eax, ebx
0x1800128a3  shr     eax, 1Fh
0x1800128a6  add     ebx, eax
0x1800128a8  jns     loc_180012AA8
0x1800128ae  xor     r14d, r14d
0x1800128b1  xor     eax, eax
0x1800128b3  lea     rcx, [rsp+1B0h+var_160]; void *
0x1800128b8  xorps   xmm0, xmm0
0x1800128bb  mov     [rbp+0B0h+var_50], eax
0x1800128be  xor     edx, edx; Val
0x1800128c0  movups  [rbp+0B0h+var_60], xmm0
0x1800128c4  lea     r8d, [rax+58h]; Size
0x1800128c8  call    memset_0
0x1800128cd  mov     r9, [rdi+0E0h]
0x1800128d4  lea     r8, ?s_StepInsideByTick@@YAHAEBVSectionInfo@@H@Z; s_StepInsideByTick(SectionInfo const &,int)
0x1800128db  or      eax, 0FFFFFFFFh
0x1800128de  mov     [rbp+0B0h+var_104], 0
0x1800128e6  mov     [rsp+1B0h+var_148], eax
0x1800128ea  lea     rdx, ??_9IVirtualizedUI@@$BEI@AA; [thunk]: IVirtualizedUI::`vcall'{72,{flat}}
0x1800128f1  mov     [rbp+0B0h+var_108], eax
0x1800128f4  mov     rcx, rdi
0x1800128f7  lea     rax, [rsp+1B0h+var_160]
0x1800128fc  mov     [rsp+1B0h+var_188], rax
0x180012901  mov     dword ptr [rsp+1B0h+var_190], r14d
0x180012906  call    ??$_GetScrollRow@H@LineScroller@@AEAAXP8IVirtualizedUI@@EAAXHPEAVSectionInfo@@@ZP6AHAEBV2@H@ZPEAU1@HPEAVRowInfo@@@Z; LineScroller::_GetScrollRow<int>(void (IVirtualizedUI::*)(int,SectionInfo *),int (*)(SectionInfo const &,int),IVirtualizedUI *,int,RowInfo *)
0x18001290b  cmp     dword ptr [rsp+1B0h+var_140], 0
0x180012910  jz      loc_180012C79
0x180012916  mov     r9d, dword ptr [rbp+0B0h+var_104+4]
0x18001291a  sub     r9d, dword ptr [rbp+0B0h+var_104]
0x18001291e  cmp     r9d, 1
0x180012922  jg      loc_180012C86
0x180012928  mov     r10d, [rbp+0B0h+var_F8]
0x18001292c  mov     edx, [rbp+0B0h+var_F0]
0x18001292f  mov     r8d, r10d
0x180012932  mov     ecx, dword ptr [rsp+1B0h+var_178]
0x180012936  sub     edx, r10d
0x180012939  imul    eax, ebx, 64h ; 'd'
0x18001293c  sub     ecx, eax
0x18001293e  mov     eax, 0A57EB503h
0x180012943  imul    ecx, edx
0x180012946  imul    ecx
0x180012948  add     edx, ecx
0x18001294a  sar     edx, 6
0x18001294d  mov     r14d, edx
0x180012950  shr     r14d, 1Fh
0x180012954  add     r14d, edx
0x180012957  add     r14d, r8d
0x18001295a  cmp     [rsp+1B0h+var_180], 1
0x18001295f  jnz     loc_180012CB6
0x180012965  mov     dword ptr [rsp+1B0h+var_178], esi
0x180012969  cmp     dword ptr [rdi+260h], 2
0x180012970  mov     rcx, rdi; this
0x180012973  jnz     loc_180012B18
0x180012979  call    ?GetRealXAnchor@LineScroller@@QEAAHXZ; LineScroller::GetRealXAnchor(void)
0x18001297e  cmp     dword ptr [rdi+260h], 2
0x180012985  mov     esi, eax
0x180012987  mov     rcx, rdi; this
0x18001298a  jnz     loc_180012B22
0x180012990  xor     r9d, r9d
0x180012993  lea     rdx, ?RealXTargetProp@LineScroller@@SAPEBUPropertyInfo@DirectUI@@XZ; LineScroller::RealXTargetProp(void)
0x18001299a  lea     r8d, [r9+1]
0x18001299e  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800129a4  mov     rcx, rax
0x1800129a7  mov     rbx, rax
0x1800129aa  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800129b0  mov     rcx, rbx
0x1800129b3  mov     [rsp+1B0h+var_180], eax
0x1800129b7  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800129bd  mov     eax, [rsp+1B0h+var_180]
0x1800129c1  sub     esi, eax
0x1800129c3  mov     rcx, rdi; this
0x1800129c6  cmp     dword ptr [rdi+260h], 2
0x1800129cd  jnz     loc_180012B64
0x1800129d3  xor     r9d, r9d
0x1800129d6  lea     rdx, ?RealYTargetProp@LineScroller@@SAPEBUPropertyInfo@DirectUI@@XZ; LineScroller::RealYTargetProp(void)
0x1800129dd  lea     r8d, [r9+1]
0x1800129e1  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800129e7  mov     rcx, rax
0x1800129ea  mov     rbx, rax
0x1800129ed  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800129f3  mov     rcx, rbx
0x1800129f6  mov     [rsp+1B0h+var_180], eax
0x1800129fa  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180012a00  mov     eax, [rsp+1B0h+var_180]
0x180012a04  sub     r14d, eax
0x180012a07  mov     eax, [rdi+260h]
0x180012a0d  cmp     eax, 1
0x180012a10  jnz     loc_180012AC3
0x180012a16  mov     ebx, esi
0x180012a18  test    ebx, ebx
0x180012a1a  jns     loc_180012AB7
0x180012a20  xor     ebx, ebx
0x180012a22  mov     esi, [rdi+1ECh]
0x180012a28  mov     r12d, r15d
0x180012a2b  cmp     [rdi+1F4h], esi
0x180012a31  jz      loc_180012B77
0x180012a37  test    r14d, r14d
0x180012a3a  js      loc_180012AF3
0x180012a40  cmp     r14d, r12d
0x180012a43  mov     esi, r14d
0x180012a46  cmovg   esi, r12d
0x180012a4a  mov     rcx, rdi
0x180012a4d  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x180012a53  test    al, al
0x180012a55  jnz     loc_180012C60
0x180012a5b  mov     rcx, [rdi+130h]
0x180012a62  neg     ebx
0x180012a64  neg     esi
0x180012a66  mov     r8d, ebx
0x180012a69  mov     edx, esi
0x180012a6b  call    cs:__imp_?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z; DirectUI::Element::_UpdateLayoutPosition(int,int)
0x180012a71  mov     eax, [rsp+1B0h+var_170]
0x180012a75  mov     [rdi+234h], eax
0x180012a7b  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 4
0x180012a82  jnz     loc_180012C39
0x180012a88  mov     rcx, [rbp+0B0h+var_48]
0x180012a8c  xor     rcx, rsp; StackCookie
0x180012a8f  call    __security_check_cookie
0x180012a94  add     rsp, 178h
0x180012a9b  pop     r15
0x180012a9d  pop     r14
0x180012a9f  pop     r13
0x180012aa1  pop     r12
0x180012aa3  pop     rdi
0x180012aa4  pop     rsi
0x180012aa5  pop     rbx
0x180012aa6  pop     rbp
0x180012aa7  retn
0x180012aa8  cmp     ebx, r8d
0x180012aab  mov     r14d, ebx
0x180012aae  cmovg   r14d, r8d
0x180012ab2  jmp     loc_1800128B1
0x180012ab7  cmp     ebx, r12d
0x180012aba  cmovg   ebx, r12d
0x180012abe  jmp     loc_180012A22
0x180012ac3  cmp     eax, 2
0x180012ac6  jnz     short loc_180012AFA
0x180012ac8  sub     r12d, dword ptr [rsp+1B0h+var_178]
0x180012acd  mov     eax, 0
0x180012ad2  cmovns  eax, r12d
0x180012ad6  test    r14d, r14d
0x180012ad9  jns     short loc_180012B05
0x180012adb  xor     r14d, r14d
0x180012ade  mov     eax, r15d
0x180012ae1  mov     ecx, 0
0x180012ae6  sub     eax, r13d
0x180012ae9  mov     ebx, r14d
0x180012aec  cmovns  ecx, eax
0x180012aef  test    esi, esi
0x180012af1  jns     short loc_180012B0E
0x180012af3  xor     esi, esi
0x180012af5  jmp     loc_180012A4A
0x180012afa  mov     ebx, r14d
0x180012afd  mov     r14d, esi
0x180012b00  jmp     loc_180012A18
0x180012b05  cmp     r14d, eax
0x180012b08  cmovg   r14d, eax
0x180012b0c  jmp     short loc_180012ADE
0x180012b0e  cmp     esi, ecx
0x180012b10  cmovg   esi, ecx
0x180012b13  jmp     loc_180012A4A
0x180012b18  call    ?GetRealYAnchor@LineScroller@@QEAAHXZ; LineScroller::GetRealYAnchor(void)
0x180012b1d  jmp     loc_18001297E
0x180012b22  call    ?GetRealYTarget@LineScroller@@QEAAHXZ; LineScroller::GetRealYTarget(void)
0x180012b27  jmp     loc_1800129C1
0x180012b2c  call    ?GetRealXAnchor@LineScroller@@QEAAHXZ; LineScroller::GetRealXAnchor(void)
0x180012b31  mov     r14d, eax
0x180012b34  mov     dword ptr [rsp+1B0h+var_178], eax
0x180012b38  jmp     loc_180012882
0x180012b3d  lea     rax, [rbp+0B0h+var_60]
0x180012b41  mov     r9d, 1
0x180012b47  lea     rdx, ItemsView_LineScroller_LayoutPass_Start
0x180012b4e  mov     [rsp+1B0h+var_190], rax
0x180012b53  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180012b5a  call    McGenEventWrite_EventWriteTransfer
0x180012b5f  jmp     loc_180012716
0x180012b64  call    ?GetRealXTarget@LineScroller@@QEAAHXZ; LineScroller::GetRealXTarget(void)
0x180012b69  jmp     loc_180012A04
0x180012b6e  add     rax, 4
0x180012b72  jmp     loc_1800127EB
0x180012b77  xor     edx, edx; Val
0x180012b79  lea     rcx, [rbp+0B0h+var_E0]; void *
0x180012b7d  lea     r8d, [rdx+58h]; Size
0x180012b81  call    memset_0
0x180012b86  or      eax, 0FFFFFFFFh
0x180012b89  mov     [rbp+0B0h+var_84], 0
0x180012b91  lea     edx, [rsi-1]; int
0x180012b94  mov     [rbp+0B0h+var_C8], eax
0x180012b97  lea     r8, [rbp+0B0h+var_E0]; struct RowInfo *
0x180012b9b  mov     [rbp+0B0h+var_88], eax
0x180012b9e  mov     rcx, rdi; this
0x180012ba1  call    ?GetRowInfoForRow@LineScroller@@QEAAXHPEAVRowInfo@@@Z; LineScroller::GetRowInfoForRow(int,RowInfo *)
0x180012ba6  cmp     dword ptr [rbp+0B0h+var_C0], 0
0x180012baa  jz      loc_180012A37
0x180012bb0  movaps  xmm0, xmmword ptr [rbp-20h]
0x180012bb4  xor     eax, eax
  ... truncated ...
```

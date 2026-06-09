# StdTableView::PaintMultiLineRow(int,CDC *,CellStyle &,CRect &,int)

- ea: `0x1402f4660`
- end: `0x1402f6e28`
- name: `?PaintMultiLineRow@StdTableView@@MEAAHHPEAVCDC@@AEAUCellStyle@@AEAVCRect@@H@Z`
- size: `10184`
- prototype: `__int64 __usercall@<rax>(StdTableView *__hidden this@<rcx>, int@<edx>, struct CDC *@<r8>, struct CellStyle *@<r9>, struct CRect *, int)`
- caller_count: `1`
- callee_count: `85`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140e6a940`

## callees

- `0x1400448c0`
- `0x1400448e0`
- `0x140045170`
- `0x140047cfc`
- `0x14004a214`
- `0x14004aadc`
- `0x140052080`
- `0x1400980a4`
- `0x1400980d0`
- `0x1400d18fc`
- `0x1400d1d7c`
- `0x1400d2410`
- `0x1400d2680`
- `0x1400d3df0`
- `0x1400d3e20`
- `0x1400d4d1c`
- `0x1400dd0bc`
- `0x1400dd680`
- `0x1400dd710`
- `0x14010a050`
- `0x14010ab1c`
- `0x14010ab70`
- `0x14010af24`
- `0x140119844`
- `0x14011ae0c`
- `0x14011b0a4`
- `0x14011b150`
- `0x14011fe00`
- `0x1401201c0`
- `0x140121804`
- `0x140122424`
- `0x14012248c`
- `0x1401227c4`
- `0x140129190`
- `0x14012aee0`
- `0x14012afcc`
- `0x140147000`
- `0x140173524`
- `0x140173750`
- `0x1401a9dd8`
- `0x1401a9f64`
- `0x1401f48a0`
- `0x140213bf0`
- `0x140215f50`
- `0x140216018`
- `0x1402160b8`
- `0x140216244`
- `0x14024c4a0`
- `0x14024cde4`
- `0x1402558ac`

## import_xrefs

- `OLMAPI32!EtwTraceErrorTag` at `0x1402f4945`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f4e82`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f603c`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f68b5`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6a8d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6ae6`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6b57`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6bea`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6c7a`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6cec`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f4945`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f4e82`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f603c`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f68b5`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6a8d`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6ae6`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6b57`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6bea`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6c7a`
- `OLMAPI32!EtwTraceErrorTag` at `0x1402f6cec`
- `GDI32!SelectObject` at `0x1402f49a9`
- `GDI32!SelectObject` at `0x1402f49a9`
- `GDI32!GetCurrentObject` at `0x1402f4d45`
- `GDI32!GetCurrentObject` at `0x1402f4d45`
- `OLEAUT32!__imp_VariantInit` at `0x1402f4830`
- `OLEAUT32!__imp_VariantInit` at `0x1402f4830`
- `OLEAUT32!__imp_VariantClear` at `0x1402f497d`
- `OLEAUT32!__imp_VariantClear` at `0x1402f497d`
- `USER32!CopyRect` at `0x1402f4e09`
- `USER32!CopyRect` at `0x1402f4e1f`
- `USER32!CopyRect` at `0x1402f4f4f`
- `USER32!CopyRect` at `0x1402f50ef`
- `USER32!CopyRect` at `0x1402f5353`
- `USER32!CopyRect` at `0x1402f5c8c`
- `USER32!CopyRect` at `0x1402f5d9d`
- `USER32!CopyRect` at `0x1402f5eac`
- `USER32!CopyRect` at `0x1402f6517`
- `USER32!CopyRect` at `0x1402f4e09`
- `USER32!CopyRect` at `0x1402f4e1f`
- `USER32!CopyRect` at `0x1402f4f4f`
- `USER32!CopyRect` at `0x1402f50ef`
- `USER32!CopyRect` at `0x1402f5353`
- `USER32!CopyRect` at `0x1402f5c8c`
- `USER32!CopyRect` at `0x1402f5d9d`
- `USER32!CopyRect` at `0x1402f5eac`
- `USER32!CopyRect` at `0x1402f6517`
- `USER32!IsRectEmpty` at `0x1402f51f8`
- `USER32!IsRectEmpty` at `0x1402f55a0`
- `USER32!IsRectEmpty` at `0x1402f55d1`
- `USER32!IsRectEmpty` at `0x1402f5a63`
- `USER32!IsRectEmpty` at `0x1402f5b22`
- `USER32!IsRectEmpty` at `0x1402f5d1b`
- `USER32!IsRectEmpty` at `0x1402f63c5`
- `USER32!IsRectEmpty` at `0x1402f6553`
- `USER32!IsRectEmpty` at `0x1402f51f8`
- `USER32!IsRectEmpty` at `0x1402f55a0`
- `USER32!IsRectEmpty` at `0x1402f55d1`
- `USER32!IsRectEmpty` at `0x1402f5a63`
- `USER32!IsRectEmpty` at `0x1402f5b22`
- `USER32!IsRectEmpty` at `0x1402f5d1b`
- `USER32!IsRectEmpty` at `0x1402f63c5`
- `USER32!IsRectEmpty` at `0x1402f6553`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5aa9`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5ad8`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5af6`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5b0b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5bc1`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5bf5`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f60eb`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f6235`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f6d7f`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5aa9`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5ad8`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5af6`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5b0b`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5bc1`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f5bf5`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f60eb`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f6235`
- `mso40uiWin32Client!__imp_MsoCrCbvGet` at `0x1402f6d7f`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1402f5bae`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1402f5be2`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1402f5bae`
- `mso40uiWin32Client!__imp_?MsoFCbvHighContrast@@YAHXZ` at `0x1402f5be2`

## pseudocode

```c
__int64 __fastcall StdTableView::PaintMultiLineRow(
        StdTableView *this,
        unsigned int a2,
        struct CDC *a3,
        struct CellStyle *a4,
        RECT *a5,
        int a6)
{
  struct CDC *v7; // r12
  int v9; // r13d
  int v10; // esi
  RECT *v11; // r11
  __int64 v12; // rbx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  HDC v17; // rsi
  int v19; // eax
  bool v20; // si
  struct IPropertyAccess *Context; // rax
  RowPropAcc *v22; // rcx
  unsigned int (__fastcall *v23)(RowPropAcc *__hidden); // rax
  char AccessMethod; // al
  __int64 v25; // r9
  int v26; // eax
  void (__fastcall *v27)(StdTableView *, struct CellStyle *, __int64, _QWORD, bool, _BYTE, unsigned int *, unsigned int *); // rdi
  unsigned int v28; // eax
  __int64 v29; // r8
  unsigned int v30; // esi
  CGrid *v31; // rcx
  __int64 v32; // rdx
  int v33; // eax
  int v34; // esi
  int MultiLineTopMargin; // eax
  int v36; // eax
  int v37; // eax
  HDC v38; // rax
  int v39; // edx
  int v40; // ecx
  BOOL v41; // eax
  char *v42; // rdi
  char *v43; // rdx
  int *v44; // rdx
  void (__fastcall *v45)(struct CDC *, struct CFont *); // rdi
  struct CFont *RealizedFont; // rax
  int v47; // edi
  int v48; // esi
  LONG v49; // edi
  LONG v50; // edi
  LONG v51; // eax
  int v52; // edi
  int v53; // eax
  StdTableView *v54; // rcx
  int v55; // eax
  int v56; // esi
  LONG v57; // eax
  struct FieldInfo *v58; // r12
  char v59; // di
  void (__fastcall *v60)(struct CDC *, struct CFont *); // rsi
  struct CFont *v61; // rax
  int v62; // ecx
  LONG v63; // ecx
  int v64; // esi
  int v65; // r12d
  int v66; // edx
  FieldList *v67; // rsi
  struct CellStyle *v68; // rsi
  struct CDC *v69; // rdi
  LONG v70; // edi
  char v71; // al
  __int64 v72; // rdi
  int v73; // eax
  LONG v74; // edx
  LONG v75; // eax
  __int64 v76; // r8
  int v77; // edi
  int v78; // esi
  int v79; // eax
  int v80; // r9d
  int v81; // eax
  struct FieldInfo *FieldFromIVisible; // rax
  int v83; // eax
  LONG v84; // edi
  LONG v85; // edi
  LONG v86; // eax
  LONG top; // eax
  void (__fastcall *v88)(struct CDC *, struct CFont *); // rsi
  struct CFont *v89; // rax
  char CanShowCopilotInboxHeadline; // al
  LONG v91; // eax
  int ListLayoutMetrics; // eax
  int v93; // eax
  LONG v94; // ecx
  int v95; // eax
  void (__fastcall *v96)(struct CDC *, struct CFont *); // rdi
  struct CFont *v97; // rax
  int v98; // r12d
  void (__fastcall *v99)(struct CDC *, __int64); // rdi
  __int64 v100; // rdx
  struct IRenField *v101; // rax
  int v102; // eax
  int v103; // eax
  __int64 v104; // rax
  int v105; // eax
  int MultiLineBottomMargin; // eax
  int v107; // r12d
  int PreviewTopMargin; // edi
  int v109; // eax
  int PreviewBottomMargin; // eax
  LONG v111; // eax
  struct CDC *v112; // r12
  int v113; // eax
  LONG v114; // edx
  LONG v115; // eax
  bool v116; // al
  DpiScaler *v117; // rcx
  int v118; // eax
  LONG v119; // ecx
  __int64 v120; // rcx
  unsigned int v121; // eax
  FieldList *v122; // rsi
  signed int v123; // eax
  FieldInfo *v124; // rcx
  __int64 GridColor; // rdx
  void (__fastcall *v126)(struct CDC *, struct CFont *); // rdi
  struct CFont *v127; // rax
  int v128; // eax
  struct FieldInfo *v129; // rax
  int v130; // ecx
  int v131; // eax
  int v132; // eax
  unsigned __int64 v133; // rsi
  struct IUnknown *v134; // rdi
  MAPIRowRef *v135; // rcx
  void (*v136)(void); // rax
  MAPIRowRef *v137; // rcx
  void (*v138)(void); // rax
  MAPIRowRef *v139; // rcx
  void (*v140)(void); // rax
  int v141; // eax
  int v142; // edi
  int v143; // esi
  int *p_right; // r12
  struct FieldInfo *Field; // rax
  int v146; // eax
  LONG v147; // edx
  LONG right; // eax
  int v149; // eax
  int i; // edi
  int v151; // eax
  struct FieldInfo *v152; // rsi
  LONG v153; // edx
  int v154; // eax
  int v155; // ecx
  int v156; // eax
  int v157; // edi
  int v158; // eax
  int v159; // eax
  LONG v160; // ecx
  LONG bottom; // eax
  LONG v162; // edi
  LONG v163; // edi
  LONG v164; // eax
  int v165; // esi
  int v166; // edi
  int v167; // ecx
  int v168; // eax
  __int64 v169; // r8
  __int64 v170; // r9
  int v171; // eax
  const wchar_t *v172; // rdi
  const wchar_t *v173; // r9
  const wchar_t *v174; // r8
  int v175; // eax
  __int64 v176; // rcx
  int v177; // eax
  int v178; // eax
  int v179; // [rsp+20h] [rbp-698h]
  unsigned int v180; // [rsp+40h] [rbp-678h]
  int v181; // [rsp+58h] [rbp-660h]
  int v183; // [rsp+64h] [rbp-654h]
  bool v184; // [rsp+68h] [rbp-650h]
  unsigned int v185; // [rsp+6Ch] [rbp-64Ch] BYREF
  int v186; // [rsp+70h] [rbp-648h]
  char v187; // [rsp+74h] [rbp-644h]
  bool v188; // [rsp+75h] [rbp-643h]
  int v189; // [rsp+78h] [rbp-640h]
  struct CellStyle *v190; // [rsp+80h] [rbp-638h]
  int v191; // [rsp+88h] [rbp-630h]
  int v192; // [rsp+8Ch] [rbp-62Ch]
  int v193; // [rsp+90h] [rbp-628h]
  struct CDC *v194; // [rsp+98h] [rbp-620h]
  int v195; // [rsp+A0h] [rbp-618h]
  int v196; // [rsp+A4h] [rbp-614h]
  struct IPropertyAccess *v197; // [rsp+A8h] [rbp-610h]
  unsigned int v198; // [rsp+B0h] [rbp-608h] BYREF
  int v199; // [rsp+B4h] [rbp-604h]
  int v200; // [rsp+B8h] [rbp-600h]
  int v201; // [rsp+BCh] [rbp-5FCh]
  int v202; // [rsp+C0h] [rbp-5F8h] BYREF
  FieldList *v203; // [rsp+C8h] [rbp-5F0h]
  int v204; // [rsp+D0h] [rbp-5E8h]
  HDC v205; // [rsp+D8h] [rbp-5E0h]
  MAPIRowRef *v206[2]; // [rsp+E0h] [rbp-5D8h] BYREF
  int v207; // [rsp+F0h] [rbp-5C8h]
  struct IOlkObjectData *v208[2]; // [rsp+100h] [rbp-5B8h] BYREF
  int v209; // [rsp+110h] [rbp-5A8h]
  int v210; // [rsp+114h] [rbp-5A4h]
  RECT *lprcSrc; // [rsp+118h] [rbp-5A0h]
  MAPIRowRef *v212; // [rsp+120h] [rbp-598h] BYREF
  __int64 v213; // [rsp+128h] [rbp-590h] BYREF
  int v214; // [rsp+130h] [rbp-588h]
  int v215; // [rsp+134h] [rbp-584h]
  __int64 v216; // [rsp+138h] [rbp-580h] BYREF
  struct IPropertyAccess *v217; // [rsp+140h] [rbp-578h]
  StdTableView *v218; // [rsp+148h] [rbp-570h]
  HDC v219; // [rsp+150h] [rbp-568h]
  HGDIOBJ h; // [rsp+158h] [rbp-560h]
  RECT v221; // [rsp+160h] [rbp-558h] BYREF
  _QWORD v222[2]; // [rsp+170h] [rbp-548h] BYREF
  VARIANTARG pvarg; // [rsp+180h] [rbp-538h] BYREF
  __int64 v224; // [rsp+198h] [rbp-520h]
  __int64 v225; // [rsp+1A0h] [rbp-518h]
  char v226[16]; // [rsp+1B0h] [rbp-508h] BYREF
  struct tagRECT v227; // [rsp+1C0h] [rbp-4F8h] BYREF
  RECT rcSrc; // [rsp+1D0h] [rbp-4E8h] BYREF
  RECT v229; // [rsp+1E0h] [rbp-4D8h] BYREF
  RECT lprc; // [rsp+1F0h] [rbp-4C8h] BYREF
  struct tagRECT rcDst; // [rsp+200h] [rbp-4B8h] BYREF
  struct tagRECT v232; // [rsp+210h] [rbp-4A8h] BYREF
  RECT rc; // [rsp+220h] [rbp-498h] BYREF
  struct tagRECT v234; // [rsp+230h] [rbp-488h] BYREF
  struct tagRECT v235; // [rsp+240h] [rbp-478h] BYREF
  int v236; // [rsp+250h] [rbp-468h] BYREF
  _WORD v237[33]; // [rsp+254h] [rbp-464h] BYREF
  int v238; // [rsp+296h] [rbp-422h]
  int v239; // [rsp+29Ch] [rbp-41Ch]
  int v240; // [rsp+2A0h] [rbp-418h]
  char v241; // [rsp+2A4h] [rbp-414h]
  _WORD v242[33]; // [rsp+2A8h] [rbp-410h] BYREF
  int v243; // [rsp+2EAh] [rbp-3CEh]
  int v244; // [rsp+2F0h] [rbp-3C8h]
  int v245; // [rsp+2F4h] [rbp-3C4h]
  int v246; // [rsp+300h] [rbp-3B8h] BYREF
  __int16 v247; // [rsp+304h] [rbp-3B4h]
  __int16 v248; // [rsp+344h] [rbp-374h]
  int v249; // [rsp+346h] [rbp-372h]
  int v250; // [rsp+34Ch] [rbp-36Ch]
  int v251; // [rsp+350h] [rbp-368h]
  char v252; // [rsp+354h] [rbp-364h]
  __int16 v253; // [rsp+358h] [rbp-360h]
  __int16 v254; // [rsp+398h] [rbp-320h]
  int v255; // [rsp+39Ah] [rbp-31Eh]
  int v256; // [rsp+3A0h] [rbp-318h]
  int v257; // [rsp+3A4h] [rbp-314h]
  int v258; // [rsp+3B0h] [rbp-308h] BYREF
  __int16 v259; // [rsp+3B4h] [rbp-304h]
  __int16 v260; // [rsp+3F4h] [rbp-2C4h]
  int v261; // [rsp+3F6h] [rbp-2C2h]
  int v262; // [rsp+3FCh] [rbp-2BCh]
  int v263; // [rsp+400h] [rbp-2B8h]
  char v264; // [rsp+404h] [rbp-2B4h]
  __int16 v265; // [rsp+408h] [rbp-2B0h]
  __int16 v266; // [rsp+448h] [rbp-270h]
  int v267; // [rsp+44Ah] [rbp-26Eh]
  int v268; // [rsp+450h] [rbp-268h]
  int v269; // [rsp+454h] [rbp-264h]
  _BYTE v270[56]; // [rsp+460h] [rbp-258h] BYREF
  int v271; // [rsp+498h] [rbp-220h] BYREF
  _BYTE v272[84]; // [rsp+49Ch] [rbp-21Ch] BYREF
  char v273[120]; // [rsp+4F0h] [rbp-1C8h] BYREF
  int v274; // [rsp+568h] [rbp-150h]
  int v275; // [rsp+56Ch] [rbp-14Ch]
  __int128 v276; // [rsp+638h] [rbp-80h]
  __int128 v277; // [rsp+648h] [rbp-70h]

  v190 = a4;
  v7 = a3;
  v194 = a3;
  v218 = this;
  lprcSrc = a5;
  v9 = 0;
  GridAttr::GridAttr((GridAttr *)v270);
  v276 = 0;
  *(_QWORD *)&v277 = 0;
  v222[1] = 0;
  v222[0] = &CBrush::`vftable';
  v198 = 0;
  v185 = 0;
  v10 = 0;
  v183 = 0;
  v184 = 0;
  v219 = 0;
  v246 = 0;
  v248 = -1;
  v249 = 0;
  v250 = -1;
  v251 = 0;
  v247 = 0;
  v252 = 0;
  v254 = -1;
  v255 = 0;
  v256 = -1;
  v257 = 0;
  v253 = 0;
  v258 = 0;
  v260 = -1;
  v261 = 0;
  v262 = -1;
  v263 = 0;
  v259 = 0;
  v264 = 0;
  v266 = -1;
  v267 = 0;
  v268 = -1;
  v269 = 0;
  v265 = 0;
  v202 = 0;
  v197 = 0;
  v217 = 0;
  rcSrc = *v11;
  rc = 0;
  v12 = 0;
  v213 = 0;
  VariantInit(&pvarg);
  v209 = 0;
  v207 = 0;
  v216 = 0;
  v224 = 0;
  v225 = 0;
  if ( (*(_BYTE *)a4 & 0x40) != 0 )
  {
    v10 = (*((_DWORD *)a4 + 49) >> 10) & 1;
    v183 = v10;
  }
  if ( !v10 && IsRectEmpty(&rcSrc) )
    goto LABEL_9;
  v13 = *((_QWORD *)this + 289);
  v14 = *(_DWORD *)(v13 + 1948);
  v210 = v14;
  if ( v14 == 2 || (v196 = 0, v14 == 30) )
    v196 = 1;
  v200 = SretData::OutlineConversationType((SretData *)(v13 + 168), a2);
  GridAttr::DeepCopy((StdTableView *)((char *)this + 576), (struct GridAttr *)v270);
  v276 = *((_OWORD *)this + 101);
  v277 = *((_OWORD *)this + 102);
  v192 = v274;
  v191 = v275;
  SetupToplineGridFont((struct _structHGRIDFONT *)&v258, v190);
  v15 = *((_QWORD *)this + 289);
  if ( !v15 )
  {
    v16 = 1885890934;
LABEL_8:
    v9 = -2147467259;
    EtwTraceErrorTag(2147500037LL, v16);
LABEL_9:
    v17 = 0;
    goto LABEL_10;
  }
  v203 = *(FieldList **)(v15 + 1720);
  if ( !v203 )
  {
    v16 = 1751479861;
    goto LABEL_8;
  }
  v199 = StdTableView::IvisFirst(this);
  v201 = StdTableView::IvisSecond(this);
  AFX_EXCEPTION_LINK::AFX_EXCEPTION_LINK((AFX_EXCEPTION_LINK *)v226);
  v189 = SretData::OutlineDepthOfRow((SretData *)(*((_QWORD *)this + 289) + 168LL), a2);
  v19 = SretData::OutlineTypeOfRow((SretData *)(*((_QWORD *)this + 289) + 168LL), a2);
  v193 = v19;
  if ( !v189 || !v196 || (v186 = 1, v19) )
    v186 = 0;
  v20 = v19 == 1 || v19 == 3 && v200 >= 4;
  Context = StdRowEditingTable::GetContext(*((StdRowEditingTable **)this + 289), a2, 1);
  v22 = Context;
  v197 = Context;
  v217 = Context;
  if ( !Context )
  {
    v9 = -2147467259;
    EtwTraceErrorTag(2147500037LL, 1885890935);
    AfxTryCleanup();
    v17 = 0;
    goto LABEL_10;
  }
  if ( v183 )
  {
    v30 = a2;
    goto LABEL_39;
  }
  v23 = *(unsigned int (__fastcall **)(RowPropAcc *__hidden))(*(_QWORD *)Context + 24LL);
  if ( v23 == RowPropAcc::GetAccessMethod )
    AccessMethod = RowPropAcc::GetAccessMethod(v22);
  else
    AccessMethod = v23(v22);
  v25 = *(_QWORD *)v197;
  if ( (AccessMethod & 1) != 0 )
    v26 = (*(__int64 (__fastcall **)(struct IPropertyAccess *, __int64, VARIANTARG *))(v25 + 32))(v197, 6, &pvarg);
  else
    v26 = (*(__int64 (__fastcall **)(struct IPropertyAccess *, __int64, VARIANTARG *))(v25 + 40))(v197, 3591, &pvarg);
  if ( v26 >= 0 )
    v184 = (pvarg.bVal & 1) == 0;
  v27 = *(void (__fastcall **)(StdTableView *, struct CellStyle *, __int64, _QWORD, bool, _BYTE, unsigned int *, unsigned int *))(*(_QWORD *)this + 760LL);
  v28 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 13) + 736LL))((char *)this + 104, a2);
  LOBYTE(v29) = v184;
  v27(this, v190, v29, v28, v20, v186, &v198, &v185);
  v30 = a2;
  if ( (unsigned int)CGrid::GetActiveCell((StdTableView *)((char *)this + 104), (struct CCell *)&v216)
    && HIDWORD(v216) == a2
    && (*((_BYTE *)this + 116) & 2) != 0
    && (unsigned int)StdTableView::FMultilineInCellEdit(this, (const struct CCell *)&v216) )
  {
    v209 = 1;
    goto LABEL_38;
  }
  v209 = 0;
  if ( !(unsigned int)CGrid::FIsGridPrinting((StdTableView *)((char *)this + 104)) )
  {
    LODWORD(v206[0]) = CGrid::FirstNormalCol((StdTableView *)((char *)this + 104));
    HIDWORD(v206[0]) = a2;
    if ( LODWORD(v206[0]) == -1 )
    {
      if ( !*((_DWORD *)this + 145) )
      {
LABEL_35:
        v32 = 0;
        if ( v7 )
          v32 = *((_QWORD *)v7 + 1);
        (*(void (__fastcall **)(char *, __int64, struct tagRECT *, _QWORD))(*((_QWORD *)this + 13) + 880LL))(
          (char *)this + 104,
          v32,
          &v232,
          v198);
        goto LABEL_38;
      }
      LODWORD(v206[0]) = -65535;
    }
    if ( (unsigned int)CGrid::CellRect(v31, &v232, (const struct CCell *)v206, 0) )
    {
      v232.left = *((_DWORD *)this + 30);
      v232.right = *((_DWORD *)this + 32);
    }
    goto LABEL_35;
  }
LABEL_38:
  StdTableView::ShiftGridHLineForGroupView(this, v7, a2, v198);
LABEL_39:
  if ( v189 )
  {
    v79 = StdTableView::OffsetDepthOfRow(this, v189, v193);
    rcSrc.left += v274 * v79;
    if ( !v80 )
    {
      if ( IsRectEmpty(&rcSrc) )
        goto LABEL_208;
    }
  }
  v188 = StdTableView::FHasDraft(this, v30);
  v33 = CGrid::ScaleForX((StdTableView *)((char *)this + 104), 6);
  rcSrc.left += v33;
  if ( v196 )
  {
    if ( !(*(unsigned int (__fastcall **)(StdTableView *, _QWORD))(*(_QWORD *)this + 1032LL))(this, v30) )
    {
      CopyRect(&v235, &rcSrc);
      StdTableView::GetOutlineHandleRect(this, v30, 0, &v235, 0, 0);
      v104 = *((_QWORD *)this + 13);
      v227.left = 0;
      v227.top = v30;
      LOBYTE(v179) = 1;
      (*(void (__fastcall **)(char *, struct tagRECT *, struct CDC *, struct tagRECT *, int))(v104 + 312))(
        (char *)this + 104,
        &v227,
        v7,
        &v235,
        v179);
      v105 = CGrid::ScaleForX((StdTableView *)((char *)this + 104), 6);
      rcSrc.left = v235.right + v105;
      if ( !v183 )
      {
        if ( IsRectEmpty(&rcSrc) )
        {
LABEL_208:
          AfxTryCleanup();
          v17 = 0;
          goto LABEL_10;
        }
      }
    }
  }
  v34 = v200;
  MultiLineTopMargin = StdTableView::GetMultiLineTopMargin(this, v193, v200, v189);
  rcSrc.top += MultiLineTopMargin;
  if ( v196
    && ((unsigned int)(v193 - 2) <= 1
     || !v193
     && v189 < *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 289) + 1720LL) + 800LL)
             + (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 289) + 1720LL) + 816LL) != -1)
     || v193 == 1 && v34 == 1) )
  {
    MultiLineBottomMargin = StdTableView::GetMultiLineBottomMargin(this, v193, v34, v189);
    rcSrc.bottom -= MultiLineBottomMargin;
  }
  if ( !v186 )
    goto LABEL_43;
  v122 = v203;
  if ( *((int *)v203 + 190) < 1 || (int)StdTableView::IfldConvIndent(this) < 0 )
    goto LABEL_43;
  v123 = StdTableView::IfldConvIndent(this);
  if ( v123 < 0 || v123 > *((_DWORD *)v122 + 170) - 1 )
  {
    EventWriteGetFieldInfoNull(0, v123);
    v124 = 0;
  }
  else
  {
    v124 = (FieldInfo *)(*((_QWORD *)v122 + 83) + 352LL * (unsigned int)v123);
  }
  if ( !v124 )
  {
    v9 = -2147467259;
    EtwTraceErrorTag(2147500037LL, 594834444);
    AfxTryCleanup();
    v17 = 0;
    goto LABEL_10;
  }
  v101 = FieldInfo::PField(v124);
  v102 = COMSP<IRenIntegerField>::HrQueryFrom(&v213, v101);
  v9 = v102;
  if ( v102 < 0 )
  {
    EtwTraceErrorTag((unsigned int)v102, 1885890937);
    AfxTryCleanup();
    v12 = v213;
    v17 = 0;
    goto LABEL_10;
  }
  v12 = v213;
  if ( (*(int (__fastcall **)(__int64, struct IPropertyAccess *, int *))(*(_QWORD *)v213 + 32LL))(v213, v197, &v202) < 0 )
  {
    v36 = 0;
    v202 = 0;
  }
  else
  {
LABEL_43:
    v36 = v202;
  }
  if ( v36 )
  {
    if ( IsRectEmpty(&rcSrc) )
      goto LABEL_295;
    v227.left = StdTableView::IfldCategories(this);
    v227.top = StdTableView::IfldFlag(this);
    v142 = rcSrc.right - rcSrc.left;
    v204 = 1;
    v143 = 2;
    p_right = &v227.right;
    do
    {
      --v143;
      if ( *--p_right >= 0 )
      {
        Field = FieldList::GetField(v203, *p_right);
        if ( Field )
        {
          if ( *((_DWORD *)Field + 12) )
          {
            v149 = DpiScaler::Scale((StdTableView *)((char *)this + 5162), 19);
            if ( v142 < v149 )
              v149 = v142;
            v142 -= v149;
            if ( v204 )
              v204 = 0;
            else
              v142 -= DpiScaler::Scale((StdTableView *)((char *)this + 5160), 4);
          }
        }
      }
    }
    while ( v143 > 0 );
    v7 = v194;
    if ( v142 < 5 * v191 )
    {
LABEL_295:
      v146 = 0;
    }
    else
    {
      v146 = v142 / v191 - 5;
      if ( v202 < v146 )
        v146 = v202;
    }
    v202 = v146;
    v147 = rcSrc.left + v191 * (v146 - 1);
    right = rcSrc.right;
    if ( rcSrc.right >= v147 )
      right = v147;
    rcSrc.left = right;
  }
  v37 = CGrid::ScaleForX((StdTableView *)((char *)this + 104), 6);
  rcSrc.right -= v37;
  if ( !v196 && (*((_BYTE *)this + 3532) & 3) == 0 )
  {
    ListLayoutMetrics = DensityItemList<enum PeopleViewPrevLayoutEnum>::GetListLayoutMetrics((char *)this + 2816, 1);
    v93 = DpiScaler::Scale((StdTableView *)((char *)this + 5160), ListLayoutMetrics);
    rcSrc.left += v192 + v93;
  }
  if ( !v183 && IsRectEmpty(&rcSrc) )
    goto LABEL_208;
  v38 = 0;
  if ( v7 )
    v38 = (HDC)*((_QWORD *)v7 + 1);
  v205 = v38;
  h = GetCurrentObject(v38, 6u);
  if ( !h )
    ThrowRenExceptionTagRaw(0x646F3074u);
  v219 = v205;
  if ( !v183 )
    (*(void (__fastcall **)(struct CDC *, _QWORD))(*(_QWORD *)v7 + 104LL))(v7, v185);
  v39 = v186;
  if ( v196 && !v183 )
  {
    if ( v186 )
    {
      v130 = v199;
      if ( v199 != -1 )
      {
        if ( v201 != -1 )
        {
          v131 = StdTableView::IfldSubject(this);
          v132 = FieldList::IVisibleFromIField(v203, v131);
          v39 = v186;
          if ( v201 != v132 )
            goto LABEL_53;
          v130 = v199;
        }
        v201 = v130;
        v199 = -1;
      }
    }
    else
    {
      if ( (*(_DWORD *)(*((_QWORD *)this + 479) + 2044LL) & 0x400) != 0 )
        goto LABEL_54;
      v103 = v199;
      v199 = v201;
      v201 = v103;
    }
  }
LABEL_53:
  if ( v39 && !v183 )
    goto LABEL_251;
LABEL_54:
  v40 = 1;
  if ( v199 == -1 )
LABEL_251:
    v40 = 0;
  v195 = v40;
  v41 = (*((_DWORD *)this + 974) & 0x8000) == 0 && (!v40 || v201 != -1);
  v204 = v41;
  v191 = 0;
  if ( !v40 || !v196 || v193 != 2 && (v193 != 3 || v200 > 2) || (v214 = 1, v183) )
    v214 = 0;
  if ( !v41 || !v39 || v210 != 30 || (v192 = 1, v183) )
    v192 = 0;
  CopyRect(&rcDst, &rcSrc);
  CopyRect(&v229, &rcSrc);
  v42 = (char *)v190 + 20;
  v43 = (char *)&v271;
  if ( (*(_BYTE *)v190 & 8) != 0 )
    v43 = (char *)v190 + 20;
  _structHGRIDFONT::operator=(&v246, v43);
  if ( (*((_BYTE *)this + 3535) & 8) == 0 )
  {
    v44 = &v246;
    goto LABEL_73;
  }
  if ( !FIsAestheticMessageListFontsReadabilityEnabled() && (*(_BYTE *)v190 & 8) != 0 )
  {
    v44 = (int *)v42;
LABEL_73:
    _structHGRIDFONT::operator=(&v258, v44);
  }
  v215 = (*(__int64 (__fastcall **)(char *, int *, struct CDC *))(*((_QWORD *)this + 13) + 40LL))(
           (char *)this + 104,
           &v258,
           v7);
  v45 = *(void (__fastcall **)(struct CDC *, struct CFont *))(*(_QWORD *)v7 + 88LL);
  RealizedFont = CGrid::GetRealizedFont((StdTableView *)((char *)this + 104), (const struct _structHGRIDFONT *)&v258, 0);
  v45(v7, RealizedFont);
  v47 = v195;
  if ( v195 )
    v229.top += v215;
  CopyRect(&lprc, lprcSrc);
  v221 = lprc;
  v187 = StdTableView::FShouldVerticallyCenterIcons(
           this,
           (unsigned int)v193,
           (unsigned int)v200,
           (unsigned int)v189,
           &v221);
  if ( v187 )
  {
    v227.left = 0;
    v227.top = a2;
    CGrid::GetRightMarginRect((StdTableView *)((char *)this + 104), (const struct CCell *)&v227, 1, &v232);
    v157 = v232.bottom - v232.top;
    v158 = DpiScaler::Scale((StdTableView *)((char *)this + 5162), 19);
    lprc.top += v157 / 2 - v158 / 2;
    v159 = DpiScaler::Scale((StdTableView *)((char *)this + 5162), 19);
    v160 = lprc.top + v159;
    lprc.bottom = lprc.top + v159;
    v48 = a2;
    if ( !v195 )
    {
      bottom = v229.bottom;
      if ( v229.bottom <= v160 )
        bottom = v160;
      v229.bottom = bottom;
      StdTableView::PaintItemIcons(this, v197, v7, v190, v203, &v229, &lprc, v198, v185, 0, v183, a2);
      goto LABEL_79;
    }
    v52 = v183;
    StdTableView::PaintItemIcons(this, v197, v7, v190, v203, &rcDst, &lprc, v198, v185, 0, v183, a2);
    if ( (*((_BYTE *)this + 3535) & 8) != 0 )
    {
      v162 = lprcSrc->right;
      v163 = v162 - DpiScaler::Scale((StdTableView *)((char *)this + 5160), 80);
      v164 = rcDst.right;
      if ( rcDst.right >= v163 )
        v164 = v163;
      rcDst.right = v164;
      goto LABEL_82;
    }
  }
  else
  {
    if ( !v47 )
    {
      v48 = a2;
      StdTableView::PaintItemIcons(this, v197, v7, v190, v203, &v229, &lprc, v198, v185, 0, v183, a2);
LABEL_79:
      v49 = lprcSrc->right;
      v50 = v49 - DpiScaler::Scale((StdTableView *)((char *)this + 5160), 80);
      v51 = v229.right;
      if ( v229.right >= v50 )
        v51 = v50;
      v229.right = v51;
LABEL_82:
      v52 = v183;
      goto LABEL_83;
    }
    v83 = StdTableView::GetMultiLineTopMargin(this, v193, v200, v189);
    lprc.top += v83;
    v48 = a2;
    v52 = v183;
    StdTableView::PaintItemIcons(this, v197, v7, v190, v203, &rcDst, &lprc, v198, v185, 0, v183, a2);
    if ( (*((_BYTE *)this + 3535) & 8) != 0 )
    {
      v84 = lprcSrc->right;
      v85 = v84 - DpiScaler::Scale((StdTableView *)((char *)this + 5160), 80);
      v86 = rcDst.right;
      if ( rcDst.right >= v85 )
        v86 = v85;
      rcDst.right = v86;
      v52 = v183;
    }
    top = v229.top;
    if ( v229.top <= lprc.bottom )
      top = lprc.bottom;
    v229.top = top;
  }
LABEL_83:
  *(_QWORD *)&v227.left = 0;
  if ( !v204 )
    goto LABEL_84;
  if ( v186
    && (unsigned int)SretData::OutlineIsCrossFolder((SretData *)(*((_QWORD *)this + 289) + 168LL), v48)
    && (unsigned int)StdTableView::IfldInFolder(this) != -1 )
  {
    v141 = StdTableView::IfldInFolder(this);
    FieldFromIVisible = FieldList::GetField(v203, v141);
  }
  else
  {
    if ( (unsigned int)StdTableView::IvisDate(this) == -1 )
      goto LABEL_138;
    v81 = StdTableView::IvisDate(this);
    FieldFromIVisible = FieldList::GetFieldFromIVisible(v203, v81);
  }
  *(_QWORD *)&v227.left = FieldFromIVisible;
LABEL_138:
  if ( !v52 )
  {
    if ( (*((_DWORD *)this + 974) & 0x8000) != 0 )
    {
      v191 = 1;
    }
    else if ( v210 == 30 && v200 != 1 )
    {
      if ( v186 )
      {
        v206[0] = 0;
        v212 = 0;
        v208[0] = 0;
        v133 = *((_QWORD *)this + 289);
        v221 = (RECT)v133;
        v134 = 0;
        v191 = (*(int (__fastcall **)(struct IPropertyAccess *, MAPIRowRef **))(*(_QWORD *)v197 + 104LL))(v197, &v212) < 0
            || !v212
            || (v134 = (struct IUnknown *)SretTblLockManager::Lock(v133 + 32, 1),
                *(_QWORD *)&v221.right = v134,
                HrQueryInterface(v134, &IID_IThreadedMapiTable, (void **)v206) < 0)
            || (*(int (__fastcall **)(MAPIRowRef *, MAPIRowRef *, struct IOlkObjectData **))(*(_QWORD *)v206[0] + 56LL))(
                 v206[0],
                 v212,
                 v208) < 0
            || StdRowEditingTable::OutlineTypeOfRowByRowdata(*((StdRowEditingTable **)this + 289), v208[0]) == 3;
        if ( v134 )
          SretTblLockManager::Unlock(v133 + 32, 1);
        v135 = v208[0];
        v208[0] = 0;
        if ( v135 )
        {
          v136 = *(void (**)(void))(*(_QWORD *)v135 + 16LL);
          if ( (char *)v136 == (char *)MAPIRowRef::Release )
          {
            MAPIRowRef::Release(v135);
          }
          else if ( (char *)v136 == (char *)MAPIValRef::Release )
          {
            MAPIValRef::Release(v135);
          }
          else
          {
            v136();
          }
        }
        v137 = v212;
        v212 = 0;
        if ( v137 )
        {
          v138 = *(void (**)(void))(*(_QWORD *)v137 + 16LL);
          if ( (char *)v138 == (char *)MAPIRowRef::Release )
          {
            MAPIRowRef::Release(v137);
          }
          else if ( (char *)v138 == (char *)MAPIValRef::Release )
          {
            MAPIValRef::Release(v137);
          }
          else
          {
            v138();
          }
        }
        v139 = v206[0];
        v206[0] = 0;
        if ( v139 )
        {
          v140 = *(void (**)(void))(*(_QWORD *)v139 + 16LL);
          if ( (char *)v140 == (char *)MAPIRowRef::Release )
          {
            MAPIRowRef::Release(v139);
          }
          else if ( (char *)v140 == (char *)MAPIValRef::Release )
          {
            MAPIValRef::Release(v139);
          }
          else
          {
            v140();
          }
        }
        v48 = a2;
        v52 = v183;
      }
      else
      {
        if ( v193 != 3 )
        {
LABEL_84:
          v191 = 0;
          if ( v52 )
            goto LABEL_86;
          goto LABEL_85;
        }
        v191 = 1;
      }
    }
LABEL_85:
    v53 = StdTableView::OffsetDepthOfRow(this, v189, v193);
    StdTableView::PaintUnreadBarHelper(v54, v7, v184, v48, v274 * v53);
  }
LABEL_86:
  v55 = v195;
  if ( v195 )
  {
    v56 = 0;
    v189 = 0;
    v57 = rcDst.bottom;
    if ( rcDst.bottom >= rcDst.top + v215 )
      v57 = rcDst.top + v215;
    rcDst.bottom = v57;
    rcSrc.top = v57;
    if ( !v187 )
    {
      v94 = lprc.bottom;
      if ( v57 > lprc.bottom )
        v94 = v57;
      rcSrc.top = v94;
    }
    CopyRect(&v234, &rcDst);
    if ( v52 )
    {
      if ( a6 )
      {
        CopyRect(lprcSrc, &rcDst);
        AfxTryCleanup();
        v17 = v205;
        goto LABEL_10;
      }
      if ( v186 )
        v56 = 64;
    }
    if ( v214 )
    {
      v56 |= 0x18u;
      v189 = StdTableView::OutlineContentUnreadOfRow(this, a2);
    }
    if ( !v52 && (*(_BYTE *)v190 & 2) == 0 && !MsoFCbvHighContrast() )
    {
      v185 = MsoCrCbvGet(1606);
      (*(void (__fastcall **)(struct CDC *, _QWORD))(*(_QWORD *)v7 + 104LL))(v7, v185);
    }
    v58 = FieldList::GetFieldFromIVisible(v203, v199);
    if ( !v52
      && v184
      && (*(_BYTE *)v190 & 2) != 0
      && (v185 == (unsigned int)MsoCrCbvGet(3496) || v185 == (unsigned int)MsoCrCbvGet(3227)) )
    {
      v207 = 1;
      v99 = *(void (__fastcall **)(struct CDC *, __int64))(*(_QWORD *)v194 + 104LL);
      v100 = (unsigned int)MsoCrCbvGet(1604);
      v99(v194, v100);
      if ( v185 == (unsigned int)MsoCrCbvGet(3227) )
        v185 = MsoCrCbvGet(3496);
    }
    if ( v209 )
      v56 = 1;
    LOBYTE(v181) = v188;
    StdTableView::PaintTextField(this, a2, v58, v270, v190, v194, v197, &rcDst, v56, v189, 0, v181);
    v7 = v194;
    if ( !v183 )
    {
      if ( v207 )
        (*(void (__fastcall **)(struct CDC *, _QWORD))(*(_QWORD *)v194 + 104LL))(v194, v185);
      if ( IsRectEmpty(&rcSrc) )
      {
LABEL_102:
        AfxTryCleanup();
        v17 = v205;
        goto LABEL_10;
      }
    }
    v55 = v195;
  }
  if ( !v204 )
    goto LABEL_131;
  v236 = 0;
  v237[32] = -1;
  v238 = 0;
  v239 = -1;
  v240 = 0;
  v237[0] = 0;
  v241 = 0;
  v242[32] = -1;
  v243 = 0;
  v244 = -1;
  v245 = 0;
  v242[0] = 0;
  v59 = 0;
  if ( v55 )
    _structHGRIDFONT::operator=(&v246, &v271);
  _structHGRIDFONT::operator=(&v236, &v246);
  SetUnreadBoldFont((struct _structHGRIDFONT *)&v236);
  if ( v184 && (*((_BYTE *)this + 3535) & 8) != 0 )
  {
    v88 = *(void (__fastcall **)(struct CDC *, struct CFont *))(*(_QWORD *)v7 + 88LL);
    v89 = CGrid::GetRealizedFont((StdTableView *)((char *)this + 104), (const struct _structHGRIDFONT *)&v236, 0);
    v88(v7, v89);
    v62 = (*(__int64 (__fastcall **)(char *, int *, struct CDC *))(*((_QWORD *)this + 13) + 40LL))(
            (char *)this + 104,
            &v236,
            v7);
  }
  else
  {
    v60 = *(void (__fastcall **)(struct CDC *, struct CFont *))(*(_QWORD *)v7 + 88LL);
    v61 = CGrid::GetRealizedFont((StdTableView *)((char *)this + 104), (const struct _structHGRIDFONT *)&v246, 0);
    v60(v7, v61);
    v62 = (*(__int64 (__fastcall **)(char *, int *, struct CDC *))(*((_QWORD *)this + 13) + 40LL))(
            (char *)this + 104,
            &v246,
            v7);
  }
  v63 = v229.top + v62;
  v229.bottom = v63;
  rcSrc.top = v63;
  if ( !v187 && !v195 )
  {
    v91 = lprc.bottom;
    if ( v63 > lprc.bottom )
      v91 = v63;
    rcSrc.top = v91;
  }
  CopyRect(&v234, &v229);
  if ( v210 == 30 && v193 == 3 && v200 > 1 )
  {
    if ( v200 == 2 || v200 == 3 || v200 == 4 || (v59 = 1, v200 == 5) )
      v59 = 0;
  }
  v64 = v201;
  if ( v201 == -1 )
    goto LABEL_131;
  v65 = 0;
  v207 = 0;
  if ( v59 && v192 )
  {
    v65 = 8;
    v207 = StdTableView::OutlineContentUnreadOfRow(this, a2);
  }
  v66 = v64;
  v67 = v203;
  v206[0] = FieldList::GetFieldFromIVisible(v203, v66);
  if ( !FIsCopilotPrioritizeFlightEnabled()
    || !*((_BYTE *)this + 4357)
    || !*((_BYTE *)this + 4358)
    || FIsCopilotPrioritizeNotInOther() && *((_DWORD *)this + 1086) == 4
    || *((_BYTE *)this + 4359) && *(_DWORD *)(*((_QWORD *)this + 479) + 1604LL) )
  {
    v68 = v190;
    v69 = v194;
  }
  else
  {
    v192 = 0;
    CanShowCopilotInboxHeadline = StdTableView::CanShowCopilotInboxHeadline(this, v67, a2, 0, 0);
    v68 = v190;
    v69 = v194;
    if ( CanShowCopilotInboxHeadline )
    {
      *(RECT *)v208 = v229;
      HIDWORD(v208[1]) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)v229, 4))
                       + GetSingleLineTextHeight(*((HDC *)v194 + 1), *((_DWORD *)v190 + 49));
      StdTableView::PaintCopilotPrioritizeIcon(this, v69, *((_DWORD *)v68 + 49), (struct CRect *)v208, v197, v192);
      v229.left = (LONG)v208[0];
      v229.right = (LONG)v208[1];
    }
  }
  if ( !v183 && (*(_BYTE *)v68 & 2) == 0 && !MsoFCbvHighContrast() )
  {
    v185 = MsoCrCbvGet(3795);
    (*(void (__fastcall **)(struct CDC *, _QWORD))(*(_QWORD *)v69 + 104LL))(v69, v185);
  }
  v70 = lprcSrc->right;
  v229.right = v70 - DpiScaler::Scale((StdTableView *)((char *)this + 5160), 80);
  if ( !v188 || (v71 = 1, v195) )
    v71 = 0;
  LOBYTE(v181) = v71;
  v180 = v65;
  v7 = v194;
  StdTableView::PaintTextField(this, a2, v206[0], v270, v190, v194, v197, &v229, v180, v207, 0, v181);
  if ( v191 && !v183 )
    goto LABEL_217;
  v72 = *(_QWORD *)&v227.left;
  if ( *(_QWORD *)&v227.left )
  {
    v73 = DpiScaler::Scale((StdTableView *)((char *)this + 5160), 4);
    v74 = v73 + v229.right;
    v75 = v234.right;
    if ( v234.right >= v74 )
      v75 = v74;
    v234.left = v75;
    LOBYTE(v181) = 0;
    v76 = v72;
    v77 = a2;
    StdTableView::PaintTextField(this, a2, v76, v270, v190, v7, v197, &v234, 70, 0, 0, v181);
  }
  else
  {
LABEL_131:
    v77 = a2;
  }
  v78 = v183;
  if ( !v183 || v186 || !v196 )
  {
LABEL_124:
    if ( (unsigned int)StdTableView::NumVisExtra(this) || v78 && *((_DWORD *)this + 996) )
    {
      v95 = DpiScaler::Scale((StdTableView *)((char *)this + 5160), 0);
      rcSrc.top += v95;
      _structHGRIDFONT::operator=(&v246, &v271);
      v96 = *(void (__fastcall **)(struct CDC *, struct CFont *))(*(_QWORD *)v7 + 88LL);
      v97 = CGrid::GetRealizedFont((StdTableView *)((char *)this + 104), (const struct _structHGRIDFONT *)&v246, 0);
      v96(v7, v97);
      v98 = (*(__int64 (__fastcall **)(char *, int *, struct CDC *))(*((_QWORD *)this + 13) + 40LL))(
              (char *)this + 104,
              &v246,
              v7);
      if ( !v78 )
      {
        if ( IsRectEmpty(&rcSrc) )
          goto LABEL_102;
        if ( !*((_DWORD *)v190 + 53) && (*(_BYTE *)v190 & 2) == 0 )
        {
          v185 = MsoCrCbvGet(1613);
          (*(void (__fastcall **)(struct CDC *, _QWORD))(*(_QWORD *)v194 + 104LL))(v194, v185);
        }
      }
      for ( i = 0; ; ++i )
      {
        v151 = v78 ? *((_DWORD *)this + 996) : StdTableView::NumVisExtra(this);
        if ( i >= v151 )
          break;
        v152 = FieldList::GetFieldFromIVisible(v203, *(_DWORD *)(*((_QWORD *)this + 496) + 4LL * (unsigned int)i));
        if ( i < (int)StdTableView::NumVisExtra(this) )
        {
          CopyRect(&rc, &rcSrc);
          v153 = v98 + rc.top;
          if ( rcSrc.bottom < v98 + rc.top )
            v153 = rcSrc.bottom;
          rc.bottom = v153;
          rcSrc.top = v153;
          if ( !v183 )
          {
            if ( IsRectEmpty(&rc) )
              break;
          }
        }
        v154 = StdTableView::NumVisExtra(this);
        v155 = 96;
        if ( i < v154 )
          v155 = 32;
        v156 = v155;
        if ( !v183 && (*((_DWORD *)this + 974) & 0x8000) != 0 && !i )
          v156 = v155 | 0x80;
        LOBYTE(v181) = 0;
        StdTableView::PaintTextField(this, a2, v152, v270, v190, v194, v197, &rc, v156, 0, 0, v181);
        v78 = v183;
      }
    }
    if ( !StdTableView::FShouldShowFolderNameInSearchResults(this, (struct GridWndAttr *)v270, a2) )
    {
LABEL_127:
      v17 = v205;
      AfxTryCleanup();
      goto LABEL_10;
    }
    v236 = v271;
    FONTDESCR::FONTDESCR((FONTDESCR *)v237, (const struct FONTDESCR *)v272);
    v241 = v272[80];
    ThemedFont::ThemedFont((ThemedFont *)v242, (const struct ThemedFont *)v273);
    v107 = SretData::OutlineDepthOfRow((SretData *)(*((_QWORD *)this + 289) + 168LL), a2);
    CopyRect(&v227, &rcSrc);
    PreviewTopMargin = StdTableView::GetPreviewTopMargin(this, v107);
    v109 = DpiScaler::Scale((StdTableView *)((char *)this + 5160), 4);
    v227.top += PreviewTopMargin + v109;
    PreviewBottomMargin = StdTableView::GetPreviewBottomMargin(this, v107);
    v111 = v227.bottom + PreviewBottomMargin;
    v227.bottom = v111;
    if ( *((_QWORD *)this + 611) )
      v227.bottom = v111 + 1;
    v112 = v194;
    v113 = (*(__int64 (__fastcall **)(char *, int *, struct CDC *))(*((_QWORD *)this + 13) + 40LL))(
             (char *)this + 104,
             &v236,
             v194);
    v114 = v113 + v227.top;
    v115 = v227.bottom;
    if ( v227.bottom <= v114 )
      v115 = v114;
    v227.bottom = v115;
    v116 = StdTableView::FShouldPadForExpandedConversations(this, a2);
    v117 = (StdTableView *)((char *)this + 5160);
    if ( v116 )
    {
      v118 = DpiScaler::Scale(v117, 100);
      v119 = v234.right;
      v227.right = v234.right;
    }
    else
    {
      v118 = DpiScaler::Scale(v117, 100);
      v119 = v227.right;
    }
    v227.left = v119 - v118;
    if ( (BYTE8(v277) & 0x10) != 0 )
    {
      v120 = *((_QWORD *)this + 479);
      if ( !v120 )
      {
        GridColor = (unsigned int)CGrid::GetGridColor((char *)this + 104);
        goto LABEL_258;
      }
      v121 = CColorSpec::operator unsigned long(v120 + 1956);
    }
    else
    {
      v121 = MsoCrCbvGet(1614);
    }
    GridColor = v121;
LABEL_258:
    (*(void (__fastcall **)(struct CDC *, __int64))(*(_QWORD *)v112 + 104LL))(v112, GridColor);
    if ( v239 == -1 )
      HIWORD(v238) &= ~4u;
    else
      v239 = 400;
    v126 = *(void (__fastcall **)(struct CDC *, struct CFont *))(*(_QWORD *)v112 + 88LL);
    v127 = CGrid::GetRealizedFont((StdTableView *)((char *)this + 104), (const struct _structHGRIDFONT *)&v236, 0);
    v126(v112, v127);
    v128 = StdTableView::IfldInFolder(this);
    v129 = FieldList::GetField(v203, v128);
    LOBYTE(v181) = 0;
    StdTableView::PaintTextField(this, a2, v129, v270, v190, v112, v197, &v227, 198, 0, 0, v181);
    goto LABEL_127;
  }
  v208[0] = 0;
  v208[1] = 0;
  v206[0] = 0;
  v206[1] = 0;
  *(_QWORD *)&v227.left = 0;
  *(_QWORD *)&v227.right = 0;
  v165 = SretData::OutlineContentCountOfRow((SretData *)(*((_QWORD *)this + 289) + 168LL), v77);
  v166 = StdTableView::OutlineContentUnreadOfRow(this, v77);
  if ( (unsigned __int8)Outlook::Ripcord<7174086>::getValue() )
  {
    v168 = StdTableView::HrFormatCountAndUnread(v167, (unsigned int)&FullPath, v165, v166, (__int64)v206);
    v9 = v168;
    if ( v168 < 0 )
    {
LABEL_365:
      EtwTraceErrorTag((unsigned int)v168, 1651912825);
      VariableLengthBuffer<wchar_t>::Free(&v227);
      VariableLengthBuffer<wchar_t>::Free(v206);
      VariableLengthBuffer<wchar_t>::Free(v208);
      AfxTryCleanup();
      v17 = v205;
      goto LABEL_10;
    }
  }
  else
  {
    v168 = StdTableView::HrFormatCountAndUnread(v167, 0, v165, v166, (__int64)v206);
    v9 = v168;
    if ( v168 < 0 )
      goto LABEL_365;
  }
  v171 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrFormat(v208, 3080476, v169, v170);
  v9 = v171;
  if ( v171 < 0 )
  {
    EtwTraceErrorTag((unsigned int)v171, 1651912826);
    VariableLengthBuffer<wchar_t>::Free(&v227);
    VariableLengthBuffer<wchar_t>::Free(v206);
    VariableLengthBuffer<wchar_t>::Free(v208);
    AfxTryCleanup();
    v17 = v205;
    goto LABEL_10;
  }
  v172 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
  v173 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
  if ( v206[0] )
    v173 = (const wchar_t *)v206[0];
  v174 = &VariableLengthBuffer<wchar_t>::s_szEmpty;
  if ( v208[0] )
    v174 = (const wchar_t *)v208[0];
  v175 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrFormat(&v227, 1572896, v174, v173);
  v9 = v175;
  if ( v175 < 0 )
  {
    EtwTraceErrorTag((unsigned int)v175, 1651913008);
    VariableLengthBuffer<wchar_t>::Free(&v227);
    VariableLengthBuffer<wchar_t>::Free(v206);
    VariableLengthBuffer<wchar_t>::Free(v208);
    AfxTryCleanup();
    v17 = v205;
    goto LABEL_10;
  }
  VariableLengthBuffer<wchar_t>::EnsureLength(&v227);
  if ( !v227.bottom )
    goto LABEL_383;
  if ( !(unsigned int)StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::IsEmpty((char *)this + 4192) )
  {
    v177 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrAppend(v176, L"\r\n", 0xFFFFFFFFLL);
    v9 = v177;
    if ( v177 < 0 )
    {
      EtwTraceErrorTag((unsigned int)v177, 1651913009);
      VariableLengthBuffer<wchar_t>::Free(&v227);
      VariableLengthBuffer<wchar_t>::Free(v206);
      VariableLengthBuffer<wchar_t>::Free(v208);
      AfxTryCleanup();
      v17 = v205;
      goto LABEL_10;
    }
  }
  if ( *(_QWORD *)&v227.left )
    v172 = *(const wchar_t **)&v227.left;
  v178 = StringTemplate<wchar_t,VariableLengthBuffer<wchar_t>>::HrAppend((char *)this + 4192, v172, 0xFFFFFFFFLL);
  v9 = v178;
  if ( v178 >= 0 )
  {
LABEL_383:
    VariableLengthBuffer<wchar_t>::Free(&v227);
    VariableLengthBuffer<wchar_t>::Free(v206);
    VariableLengthBuffer<wchar_t>::Free(v208);
LABEL_217:
    v78 = v183;
    goto LABEL_124;
  }
  EtwTraceErrorTag((unsigned int)v178, 1651913010);
  VariableLengthBuffer<wchar_t>::Free(&v227);
  VariableLengthBuffer<wchar_t>::Free(v206);
  VariableLengthBuffer<wchar_t>::Free(v208);
  AfxTryCleanup();
  v17 = v205;
LABEL_10:
  StdRowEditingTable::ReleaseContext(*((StdRowEditingTable **)this + 289), v197);
  CheckOleResultTagRaw(v9, 0x70686A78u);
  VariantClear(&pvarg);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v17 )
    SelectObject(v17, h);
  v222[0] = &CGdiObject::`vftable';
  CGdiObject::DeleteObject((CGdiObject *)v222);
  GridAttr::~GridAttr((GridAttr *)v270);
  return 1;
}

```

## disassembly

```asm
0x1402f4660  mov     rax, rsp
0x1402f4663  push    rbx
0x1402f4664  push    rsi
0x1402f4665  push    rdi
0x1402f4666  push    r12
0x1402f4668  push    r13
0x1402f466a  push    r14
0x1402f466c  push    r15
0x1402f466e  sub     rsp, 680h
0x1402f4675  movaps  xmmword ptr [rax-48h], xmm6
0x1402f4679  mov     rax, cs:__security_cookie
0x1402f4680  xor     rax, rsp
0x1402f4683  mov     [rsp+6B8h+var_58], rax
0x1402f468b  mov     rdi, r9
0x1402f468e  mov     [rsp+6B8h+var_638], r9
0x1402f4696  mov     r12, r8
0x1402f4699  mov     [rsp+6B8h+var_620], r8
0x1402f46a1  mov     [rsp+6B8h+var_658], edx
0x1402f46a5  mov     r15, rcx
0x1402f46a8  mov     [rsp+6B8h+var_570], rcx
0x1402f46b0  mov     r11, [rsp+6B8h+arg_20]
0x1402f46b8  mov     [rsp+6B8h+lprcSrc], r11
0x1402f46c0  xor     r14d, r14d
0x1402f46c3  mov     r13d, r14d
0x1402f46c6  lea     rcx, [rsp+6B8h+var_258]; this
0x1402f46ce  call    ??0GridAttr@@QEAA@XZ; GridAttr::GridAttr(void)
0x1402f46d3  xorps   xmm0, xmm0
0x1402f46d6  xor     eax, eax
0x1402f46d8  movups  [rsp+6B8h+var_80], xmm0
0x1402f46e0  mov     qword ptr [rsp+6B8h+var_70], rax
0x1402f46e8  mov     [rsp+6B8h+var_540], r14
0x1402f46f0  lea     rax, ??_7CBrush@@6B@; const CBrush::`vftable'
0x1402f46f7  mov     [rsp+6B8h+var_548], rax
0x1402f46ff  mov     [rsp+6B8h+var_608], r14d
0x1402f4707  mov     [rsp+6B8h+var_64C], r14d
0x1402f470c  mov     esi, r14d
0x1402f470f  mov     [rsp+6B8h+var_654], r14d
0x1402f4714  mov     [rsp+6B8h+var_650], r14b
0x1402f4719  mov     [rsp+6B8h+var_568], r14
0x1402f4721  mov     [rsp+6B8h+var_3B8], r14d
0x1402f4729  mov     ecx, 0FFFFh
0x1402f472e  mov     [rsp+6B8h+var_374], cx
0x1402f4736  mov     [rsp+6B8h+var_372], r14d
0x1402f473e  or      eax, 0FFFFFFFFh
0x1402f4741  mov     [rsp+6B8h+var_36C], eax
0x1402f4748  mov     [rsp+6B8h+var_368], r14d
0x1402f4750  mov     [rsp+6B8h+var_3B4], r14w
0x1402f4759  mov     [rsp+6B8h+var_364], r14b
0x1402f4761  mov     [rsp+6B8h+var_320], cx
0x1402f4769  mov     [rsp+6B8h+var_31E], r14d
0x1402f4771  mov     [rsp+6B8h+var_318], eax
0x1402f4778  mov     [rsp+6B8h+var_314], r14d
0x1402f4780  mov     [rsp+6B8h+var_360], r14w
0x1402f4789  mov     [rsp+6B8h+var_308], r14d
0x1402f4791  mov     [rsp+6B8h+var_2C4], cx
0x1402f4799  mov     [rsp+6B8h+var_2C2], r14d
0x1402f47a1  mov     [rsp+6B8h+var_2BC], eax
0x1402f47a8  mov     [rsp+6B8h+var_2B8], r14d
0x1402f47b0  mov     [rsp+6B8h+var_304], r14w
0x1402f47b9  mov     [rsp+6B8h+var_2B4], r14b
0x1402f47c1  mov     [rsp+6B8h+var_270], cx
0x1402f47c9  mov     [rsp+6B8h+var_26E], r14d
0x1402f47d1  mov     [rsp+6B8h+var_268], eax
0x1402f47d8  mov     [rsp+6B8h+var_264], r14d
0x1402f47e0  mov     [rsp+6B8h+var_2B0], r14w
0x1402f47e9  mov     [rsp+6B8h+var_5F8], r14d
0x1402f47f1  mov     eax, r14d
0x1402f47f4  mov     [rsp+6B8h+var_610], rax
0x1402f47fc  mov     [rsp+6B8h+var_578], rax
0x1402f4804  movups  xmm0, xmmword ptr [r11]
0x1402f4808  movdqu  xmmword ptr [rsp+6B8h+rcSrc.left], xmm0
0x1402f4811  xorps   xmm1, xmm1
0x1402f4814  movdqu  xmmword ptr [rsp+6B8h+rc.left], xmm1
0x1402f481d  mov     ebx, r14d
0x1402f4820  mov     [rsp+6B8h+var_590], rbx
0x1402f4828  lea     rcx, [rsp+6B8h+pvarg]; pvarg
0x1402f4830  call    cs:__imp_VariantInit
0x1402f4836  mov     [rsp+6B8h+var_5A8], r14d
0x1402f483e  mov     [rsp+6B8h+var_5C8], r14d
0x1402f4846  mov     [rsp+6B8h+var_580], r14
0x1402f484e  mov     [rsp+6B8h+var_520], r14
0x1402f4856  mov     [rsp+6B8h+var_518], r14
0x1402f485e  lea     eax, [r14+40h]
0x1402f4862  test    [rdi], al
0x1402f4864  jnz     loc_1402F688A
0x1402f486a  lea     edi, [rax-3Fh]
0x1402f486d  test    esi, esi
0x1402f486f  jz      loc_1402F55C9
0x1402f4875  mov     rcx, [r15+908h]
0x1402f487c  mov     eax, [rcx+79Ch]
0x1402f4882  mov     [rsp+6B8h+var_5A4], eax
0x1402f4889  mov     edx, 2
0x1402f488e  cmp     eax, edx
0x1402f4890  jz      loc_1402F6071
0x1402f4896  cmp     eax, 1Eh
0x1402f4899  mov     [rsp+6B8h+var_614], r14d
0x1402f48a1  jz      loc_1402F6071
0x1402f48a7  add     rcx, 0A8h; this
0x1402f48ae  mov     esi, [rsp+6B8h+var_658]
0x1402f48b2  mov     edx, esi; int
0x1402f48b4  call    ?OutlineConversationType@SretData@@QEAAJH@Z; SretData::OutlineConversationType(int)
0x1402f48b9  mov     [rsp+6B8h+var_600], eax
0x1402f48c0  lea     rcx, [r15+240h]; struct GridAttr *
0x1402f48c7  lea     rdx, [rsp+6B8h+var_258]; struct GridAttr *
0x1402f48cf  call    ?DeepCopy@GridAttr@@SAXPEBV1@PEAV1@@Z; GridAttr::DeepCopy(GridAttr const *,GridAttr *)
0x1402f48d4  movups  xmm0, xmmword ptr [r15+650h]
0x1402f48dc  movups  [rsp+6B8h+var_80], xmm0
0x1402f48e4  movups  xmm1, xmmword ptr [r15+660h]
0x1402f48ec  movups  [rsp+6B8h+var_70], xmm1
0x1402f48f4  mov     eax, [rsp+6B8h+var_150]
0x1402f48fb  mov     [rsp+6B8h+var_62C], eax
0x1402f4902  mov     eax, [rsp+6B8h+var_14C]
0x1402f4909  mov     [rsp+6B8h+var_630], eax
0x1402f4910  mov     rdx, [rsp+6B8h+var_638]; struct CellStyle *
0x1402f4918  lea     rcx, [rsp+6B8h+var_308]; struct _structHGRIDFONT *
0x1402f4920  call    ?SetupToplineGridFont@@YAXAEAU_structHGRIDFONT@@PEAUCellStyle@@@Z; SetupToplineGridFont(_structHGRIDFONT &,CellStyle *)
0x1402f4925  mov     rax, [r15+908h]
0x1402f492c  test    rax, rax
0x1402f492f  jnz     loc_1402F4A06
0x1402f4935  mov     edx, 70686976h
0x1402f493a  mov     ecx, 80004005h
0x1402f493f  mov     r13d, 80004005h
0x1402f4945  call    cs:__imp_EtwTraceErrorTag
0x1402f494b  mov     rsi, r14
0x1402f494e  mov     edi, 1
0x1402f4953  mov     rdx, [rsp+6B8h+var_610]; struct IPropertyAccess *
0x1402f495b  mov     rcx, [r15+908h]; this
0x1402f4962  call    ?ReleaseContext@StdRowEditingTable@@QEAAXPEAUIPropertyAccess@@@Z; StdRowEditingTable::ReleaseContext(IPropertyAccess *)
0x1402f4967  mov     edx, 70686A78h; unsigned int
0x1402f496c  mov     ecx, r13d; int
0x1402f496f  call    ?CheckOleResultTagRaw@@YAJJK@Z; CheckOleResultTagRaw(long,ulong)
0x1402f4974  nop
0x1402f4975  lea     rcx, [rsp+6B8h+pvarg]; pvarg
0x1402f497d  call    cs:__imp_VariantClear
0x1402f4983  test    rbx, rbx
0x1402f4986  jz      short loc_1402F4999
0x1402f4988  mov     rax, [rbx]
0x1402f498b  mov     rcx, rbx
0x1402f498e  mov     rax, [rax+10h]
0x1402f4992  call    cs:__guard_dispatch_icall_fptr
0x1402f4998  nop
0x1402f4999  test    rsi, rsi
0x1402f499c  jz      short loc_1402F49B0
0x1402f499e  mov     rdx, [rsp+6B8h+h]; h
0x1402f49a6  mov     rcx, rsi; hdc
0x1402f49a9  call    cs:__imp_SelectObject
0x1402f49af  nop
0x1402f49b0  lea     rax, ??_7CGdiObject@@6B@; const CGdiObject::`vftable'
0x1402f49b7  mov     [rsp+6B8h+var_548], rax
0x1402f49bf  lea     rcx, [rsp+6B8h+var_548]; this
0x1402f49c7  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1402f49cc  lea     rcx, [rsp+6B8h+var_258]; this
0x1402f49d4  call    ??1GridAttr@@QEAA@XZ; GridAttr::~GridAttr(void)
0x1402f49d9  mov     eax, edi
0x1402f49db  mov     rcx, [rsp+6B8h+var_58]
0x1402f49e3  xor     rcx, rsp; StackCookie
0x1402f49e6  call    __security_check_cookie
0x1402f49eb  movaps  xmm6, [rsp+6B8h+var_48]
0x1402f49f3  add     rsp, 680h
0x1402f49fa  pop     r15
0x1402f49fc  pop     r14
0x1402f49fe  pop     r13
0x1402f4a00  pop     r12
0x1402f4a02  pop     rdi
0x1402f4a03  pop     rsi
0x1402f4a04  pop     rbx
0x1402f4a05  retn
0x1402f4a06  mov     rax, [rax+6B8h]
0x1402f4a0d  mov     [rsp+6B8h+var_5F0], rax
0x1402f4a15  test    rax, rax
0x1402f4a18  jnz     short loc_1402F4A24
0x1402f4a1a  mov     edx, 68657635h
0x1402f4a1f  jmp     loc_1402F493A
0x1402f4a24  mov     rcx, r15; this
0x1402f4a27  call    ?IvisFirst@StdTableView@@IEAAHXZ; StdTableView::IvisFirst(void)
0x1402f4a2c  mov     [rsp+6B8h+var_604], eax
0x1402f4a33  mov     rcx, r15; this
0x1402f4a36  call    ?IvisSecond@StdTableView@@IEAAHXZ; StdTableView::IvisSecond(void)
0x1402f4a3b  mov     [rsp+6B8h+var_5FC], eax
0x1402f4a42  lea     rcx, [rsp+6B8h+var_508]; this
0x1402f4a4a  call    ??0AFX_EXCEPTION_LINK@@QEAA@XZ; AFX_EXCEPTION_LINK::AFX_EXCEPTION_LINK(void)
0x1402f4a4f  nop
0x1402f4a50  mov     rcx, [r15+908h]
0x1402f4a57  add     rcx, 0A8h; this
0x1402f4a5e  mov     edx, esi; int
0x1402f4a60  call    ?OutlineDepthOfRow@SretData@@QEAAKH@Z; SretData::OutlineDepthOfRow(int)
0x1402f4a65  mov     [rsp+6B8h+var_640], eax
0x1402f4a69  mov     rcx, [r15+908h]
0x1402f4a70  add     rcx, 0A8h; this
0x1402f4a77  mov     edx, esi; int
0x1402f4a79  call    ?OutlineTypeOfRow@SretData@@QEAAKH@Z; SretData::OutlineTypeOfRow(int)
0x1402f4a7e  mov     [rsp+6B8h+var_628], eax
0x1402f4a85  cmp     [rsp+6B8h+var_640], r14d
0x1402f4a8a  jnz     loc_1402F4E9B
0x1402f4a90  mov     [rsp+6B8h+var_648], r14d
0x1402f4a95  cmp     eax, edi
0x1402f4a97  jnz     loc_1402F57BE
0x1402f4a9d  mov     sil, dil
0x1402f4aa0  mov     r8d, edi; int
0x1402f4aa3  mov     edx, [rsp+6B8h+var_658]; int
0x1402f4aa7  mov     rcx, [r15+908h]; this
0x1402f4aae  call    ?GetContext@StdRowEditingTable@@QEAAPEAUIPropertyAccess@@HH@Z; StdRowEditingTable::GetContext(int,int)
0x1402f4ab3  mov     rcx, rax; this
0x1402f4ab6  mov     [rsp+6B8h+var_610], rax
0x1402f4abe  mov     [rsp+6B8h+var_578], rax
0x1402f4ac6  test    rax, rax
0x1402f4ac9  jz      loc_1402F4E72
0x1402f4acf  mov     r9d, [rsp+6B8h+var_654]
0x1402f4ad4  test    r9d, r9d
0x1402f4ad7  jnz     loc_1402F4EBA
0x1402f4add  mov     rax, [rax]
0x1402f4ae0  mov     rax, [rax+18h]
0x1402f4ae4  lea     rdx, ?GetAccessMethod@RowPropAcc@@UEAAKXZ; RowPropAcc::GetAccessMethod(void)
0x1402f4aeb  cmp     rax, rdx
0x1402f4aee  jnz     loc_1402F68A3
0x1402f4af4  call    ?GetAccessMethod@RowPropAcc@@UEAAKXZ; RowPropAcc::GetAccessMethod(void)
0x1402f4af9  mov     rcx, [rsp+6B8h+var_610]
0x1402f4b01  mov     r9, [rcx]
0x1402f4b04  lea     r8, [rsp+6B8h+pvarg]
0x1402f4b0c  test    dil, al
0x1402f4b0f  jz      loc_1402F6844
0x1402f4b15  mov     edx, 6
0x1402f4b1a  mov     rax, [r9+20h]
0x1402f4b1e  call    cs:__guard_dispatch_icall_fptr
0x1402f4b24  test    eax, eax
0x1402f4b26  jns     loc_1402F57CF
0x1402f4b2c  mov     rax, [r15]
0x1402f4b2f  mov     rdi, [rax+2F8h]
0x1402f4b36  lea     rcx, [r15+68h]
0x1402f4b3a  mov     rax, [rcx]
0x1402f4b3d  mov     edx, [rsp+6B8h+var_658]
0x1402f4b41  mov     rax, [rax+2E0h]
0x1402f4b48  call    cs:__guard_dispatch_icall_fptr
0x1402f4b4e  lea     rcx, [rsp+6B8h+var_64C]
0x1402f4b53  mov     qword ptr [rsp+6B8h+var_680], rcx
0x1402f4b58  lea     rcx, [rsp+6B8h+var_608]
0x1402f4b60  mov     [rsp+6B8h+lprc], rcx
0x1402f4b65  mov     ecx, [rsp+6B8h+var_648]
0x1402f4b69  mov     byte ptr [rsp+6B8h+var_690], cl
0x1402f4b6d  mov     byte ptr [rsp+6B8h+var_698], sil
0x1402f4b72  mov     r9d, eax
0x1402f4b75  mov     r8b, [rsp+6B8h+var_650]
0x1402f4b7a  mov     rdx, [rsp+6B8h+var_638]
0x1402f4b82  mov     rcx, r15
0x1402f4b85  mov     rax, rdi
0x1402f4b88  call    cs:__guard_dispatch_icall_fptr
0x1402f4b8e  lea     rdx, [rsp+6B8h+var_580]; struct CCell *
0x1402f4b96  lea     rdi, [r15+68h]
0x1402f4b9a  mov     rcx, rdi; this
0x1402f4b9d  call    ?GetActiveCell@CGrid@@QEAAHPEAVCCell@@@Z; CGrid::GetActiveCell(CCell *)
0x1402f4ba2  mov     esi, [rsp+6B8h+var_658]
0x1402f4ba6  test    eax, eax
0x1402f4ba8  jz      short loc_1402F4BB7
0x1402f4baa  cmp     dword ptr [rsp+6B8h+var_580+4], esi
0x1402f4bb1  jz      loc_1402F60AE
0x1402f4bb7  mov     [rsp+6B8h+var_5A8], r14d
0x1402f4bbf  mov     rcx, rdi; this
0x1402f4bc2  call    ?FIsGridPrinting@CGrid@@QEAAHXZ; CGrid::FIsGridPrinting(void)
0x1402f4bc7  test    eax, eax
0x1402f4bc9  jnz     short loc_1402F4C4A
0x1402f4bcb  mov     rcx, rdi; this
0x1402f4bce  call    ?FirstNormalCol@CGrid@@QEBAHXZ; CGrid::FirstNormalCol(void)
0x1402f4bd3  mov     dword ptr [rsp+6B8h+var_5D8], eax
0x1402f4bda  mov     dword ptr [rsp+6B8h+var_5D8+4], esi
0x1402f4be1  cmp     eax, 0FFFFFFFFh
0x1402f4be4  jz      loc_1402F6827
0x1402f4bea  xor     r9d, r9d; unsigned int
0x1402f4bed  lea     r8, [rsp+6B8h+var_5D8]; struct CCell *
0x1402f4bf5  lea     rdx, [rsp+6B8h+var_4A8]; lprcDst
0x1402f4bfd  call    ?CellRect@CGrid@@QEBAHPEAUtagRECT@@AEBVCCell@@K@Z; CGrid::CellRect(tagRECT *,CCell const &,ulong)
0x1402f4c02  test    eax, eax
0x1402f4c04  jz      short loc_1402F4C1A
0x1402f4c06  mov     eax, [rdi+10h]
0x1402f4c09  mov     [rsp+6B8h+var_4A8.left], eax
0x1402f4c10  mov     eax, [rdi+18h]
0x1402f4c13  mov     [rsp+6B8h+var_4A8.right], eax
0x1402f4c1a  mov     rax, [rdi]
0x1402f4c1d  test    r12, r12
0x1402f4c20  mov     rdx, r14
0x1402f4c23  jz      short loc_1402F4C2A
0x1402f4c25  mov     rdx, [r12+8]
0x1402f4c2a  mov     r9d, [rsp+6B8h+var_608]
0x1402f4c32  lea     r8, [rsp+6B8h+var_4A8]
0x1402f4c3a  mov     rcx, rdi
0x1402f4c3d  mov     rax, [rax+370h]
0x1402f4c44  call    cs:__guard_dispatch_icall_fptr
0x1402f4c4a  mov     edi, 1
0x1402f4c4f  mov     r9d, [rsp+6B8h+var_608]; unsigned int
0x1402f4c57  mov     r8d, esi; int
0x1402f4c5a  mov     rdx, r12; struct CDC *
0x1402f4c5d  mov     rcx, r15; this
0x1402f4c60  call    ?ShiftGridHLineForGroupView@StdTableView@@IEAAXPEAVCDC@@HK@Z; StdTableView::ShiftGridHLineForGroupView(CDC *,int,ulong)
0x1402f4c65  mov     r9d, [rsp+6B8h+var_654]
0x1402f4c6a  mov     eax, [rsp+6B8h+var_640]
0x1402f4c6e  test    eax, eax
0x1402f4c70  jnz     loc_1402F556E
0x1402f4c76  mov     edx, esi; int
0x1402f4c78  mov     rcx, r15; this
0x1402f4c7b  call    ?FHasDraft@StdTableView@@QEAA_NH@Z; StdTableView::FHasDraft(int)
0x1402f4c80  mov     [rsp+6B8h+var_643], al
  ... truncated ...
```

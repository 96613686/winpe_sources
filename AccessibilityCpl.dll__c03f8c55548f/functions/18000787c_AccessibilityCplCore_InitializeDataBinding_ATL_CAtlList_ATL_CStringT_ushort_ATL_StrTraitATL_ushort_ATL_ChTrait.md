# AccessibilityCplCore::InitializeDataBinding(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)

- ea: `0x18000787c`
- end: `0x180007989`
- name: `?InitializeDataBinding@AccessibilityCplCore@@AEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180007a70`
- `0x1800198f4`

## callees

- `0x18000314c`
- `0x18000787c`
- `0x18001ee30`
- `0x18002501c`

## import_xrefs

- `DUI70!??0IDataEngine@DirectUI@@QEAA@XZ` at `0x1800078d6`
- `DUI70!??0IDataEngine@DirectUI@@QEAA@XZ` at `0x1800078d6`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000795a`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x18000795a`
- `DUI70!?SetDataEngine@Repeater@DirectUI@@QEAAXPEAUIDataEngine@2@@Z` at `0x180007978`
- `DUI70!?SetDataEngine@Repeater@DirectUI@@QEAAXPEAUIDataEngine@2@@Z` at `0x180007978`
- `DUI70!StrToID` at `0x180007896`
- `DUI70!StrToID` at `0x18000793b`
- `DUI70!StrToID` at `0x180007896`
- `DUI70!StrToID` at `0x18000793b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800078a2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180007947`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800078a2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180007947`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::InitializeDataBinding(__int64 a1, __int64 a2)
{
  DirectUI::Element *v2; // rbx
  unsigned __int16 v5; // ax
  unsigned __int64 v6; // rdx
  DirectUI::Repeater *Descendent; // rsi
  DirectUI::IDataEngine *v8; // rbx
  DirectUI::IDataEngine *v9; // rax
  DirectUI::Element *v10; // rbx
  unsigned __int16 v11; // ax
  DirectUI::Element *v12; // rax

  v2 = *(DirectUI::Element **)(a1 + 96);
  v5 = StrToID(L"atlist");
  Descendent = DirectUI::Element::FindDescendent(v2, v5);
  if ( Descendent )
  {
    v8 = *(DirectUI::IDataEngine **)(a1 + 24);
    if ( !v8 )
    {
      v9 = (DirectUI::IDataEngine *)DirectUI::HAllocAndZero((DirectUI *)0x188, v6);
      v8 = v9;
      if ( !v9 )
      {
        *(_QWORD *)(a1 + 24) = 0;
        return 2147942414LL;
      }
      DirectUI::IDataEngine::IDataEngine(v9);
      *(_QWORD *)v8 = &ATLogonDataManager::`vftable';
      ATManager::ATManager((DirectUI::IDataEngine *)((char *)v8 + 8));
      *((_QWORD *)v8 + 45) = 0;
      *((_QWORD *)v8 + 46) = 0;
      *((_QWORD *)v8 + 47) = 0;
      *((_DWORD *)v8 + 96) = 0;
      *(_QWORD *)(a1 + 24) = v8;
    }
    if ( (unsigned int)ATDataManager::Initialize(v8, a2) == 232 )
    {
      v10 = *(DirectUI::Element **)(a1 + 96);
      v11 = StrToID(L"otherprograms");
      v12 = DirectUI::Element::FindDescendent(v10, v11);
      if ( v12 )
        DirectUI::Element::SetLayoutPos(v12, -3);
    }
    else
    {
      DirectUI::Repeater::SetDataEngine(Descendent, *(struct DirectUI::IDataEngine **)(a1 + 24));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000787c  push    rbx
0x18000787e  push    rbp
0x18000787f  push    rsi
0x180007880  push    rdi
0x180007881  sub     rsp, 28h
0x180007885  mov     rbx, [rcx+60h]
0x180007889  mov     rdi, rcx
0x18000788c  lea     rcx, aAtlist; "atlist"
0x180007893  mov     rbp, rdx
0x180007896  call    cs:__imp_StrToID
0x18000789c  movzx   edx, ax
0x18000789f  mov     rcx, rbx
0x1800078a2  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800078a8  mov     rsi, rax
0x1800078ab  test    rax, rax
0x1800078ae  jz      loc_18000797E
0x1800078b4  mov     rbx, [rdi+18h]
0x1800078b8  test    rbx, rbx
0x1800078bb  jnz     short loc_18000791E
0x1800078bd  mov     ecx, 188h; this
0x1800078c2  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x1800078c7  mov     rbx, rax
0x1800078ca  test    rax, rax
0x1800078cd  jz      loc_180007962
0x1800078d3  mov     rcx, rax
0x1800078d6  call    cs:__imp_??0IDataEngine@DirectUI@@QEAA@XZ; DirectUI::IDataEngine::IDataEngine(void)
0x1800078dc  lea     rax, ??_7ATLogonDataManager@@6B@; const ATLogonDataManager::`vftable'
0x1800078e3  lea     rcx, [rbx+8]; this
0x1800078e7  mov     [rbx], rax
0x1800078ea  call    ??0ATManager@@QEAA@XZ; ATManager::ATManager(void)
0x1800078ef  mov     qword ptr [rbx+168h], 0
0x1800078fa  mov     qword ptr [rbx+170h], 0
0x180007905  mov     qword ptr [rbx+178h], 0
0x180007910  mov     dword ptr [rbx+180h], 0
0x18000791a  mov     [rdi+18h], rbx
0x18000791e  mov     rdx, rbp
0x180007921  mov     rcx, rbx
0x180007924  call    ?Initialize@ATDataManager@@QEAAJAEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; ATDataManager::Initialize(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x180007929  cmp     eax, 0E8h
0x18000792e  jnz     short loc_180007971
0x180007930  mov     rbx, [rdi+60h]
0x180007934  lea     rcx, aOtherprograms; "otherprograms"
0x18000793b  call    cs:__imp_StrToID
0x180007941  movzx   edx, ax
0x180007944  mov     rcx, rbx
0x180007947  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000794d  test    rax, rax
0x180007950  jz      short loc_18000797E
0x180007952  mov     edx, 0FFFFFFFDh
0x180007957  mov     rcx, rax
0x18000795a  call    cs:__imp_?SetLayoutPos@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetLayoutPos(int)
0x180007960  jmp     short loc_18000797E
0x180007962  mov     qword ptr [rdi+18h], 0
0x18000796a  mov     eax, 8007000Eh
0x18000796f  jmp     short loc_180007980
0x180007971  mov     rdx, [rdi+18h]
0x180007975  mov     rcx, rsi
0x180007978  call    cs:__imp_?SetDataEngine@Repeater@DirectUI@@QEAAXPEAUIDataEngine@2@@Z; DirectUI::Repeater::SetDataEngine(DirectUI::IDataEngine *)
0x18000797e  xor     eax, eax
0x180007980  add     rsp, 28h
0x180007984  pop     rdi
0x180007985  pop     rsi
0x180007986  pop     rbp
0x180007987  pop     rbx
0x180007988  retn
```

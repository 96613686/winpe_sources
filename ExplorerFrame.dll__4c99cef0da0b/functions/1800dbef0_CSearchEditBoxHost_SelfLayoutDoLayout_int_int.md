# CSearchEditBoxHost::_SelfLayoutDoLayout(int,int)

- ea: `0x1800dbef0`
- end: `0x1800dc09e`
- name: `?_SelfLayoutDoLayout@CSearchEditBoxHost@@MEAAXHH@Z`
- size: `430`
- prototype: `void __fastcall(CSearchEditBoxHost *__hidden this, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180040924`
- `0x1800dbef0`
- `0x1800dc0a4`
- `0x180210010`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800dbfac`
- `USER32!GetSystemMetrics` at `0x1800dbfac`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800dbf89`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800dbf89`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800dbfa1`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800dc057`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800dbfa1`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800dc057`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800dbf95`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800dbf95`
- `DUI70!?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z` at `0x1800dc027`
- `DUI70!?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z` at `0x1800dc08b`
- `DUI70!?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z` at `0x1800dc027`
- `DUI70!?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z` at `0x1800dc08b`
- `DUI70!?_UpdateLayoutSize@Element@DirectUI@@QEAAXHH@Z` at `0x1800dc03d`
- `DUI70!?_UpdateLayoutSize@Element@DirectUI@@QEAAXHH@Z` at `0x1800dc03d`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800dbf1b`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x1800dbf1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSearchEditBoxHost::_SelfLayoutDoLayout(CSearchEditBoxHost *this, int a2, int a3)
{
  _DWORD *Children; // rax
  DirectUI::Element *v7; // rdi
  DirectUI::Element *v8; // rdi
  __int64 v9; // rax
  DirectUI::Value *Value; // rbx
  int Int; // r15d
  int SystemMetrics; // r12d
  HWND v13; // rbx
  int v14; // esi
  DirectUI::Value *v15; // rcx
  DirectUI::Value *v16; // [rsp+20h] [rbp-38h] BYREF
  struct DirectUI::HWNDElement *v17; // [rsp+78h] [rbp+20h] BYREF

  v16 = 0;
  Children = (_DWORD *)DirectUI::Element::GetChildren(this, &v16);
  if ( Children )
  {
    v7 = (DirectUI::Element *)(Children + 2);
    if ( (*Children & 0x10000000) != 0 )
      v7 = *(DirectUI::Element **)v7;
    v8 = *(DirectUI::Element **)v7;
    if ( v8 )
    {
      v9 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v8 + 280LL))(v8);
      if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v9 + 80LL))(
             v9,
             CSearchEditBox::Class) )
      {
        Value = DirectUI::Element::GetValue(v8, (const struct DirectUI::PropertyInfo *)&off_180217BD0, 1, 0);
        Int = DirectUI::Value::GetInt(Value);
        DirectUI::Value::Release(Value);
        SystemMetrics = GetSystemMetrics(45);
        if ( *((_QWORD *)v8 + 80) )
        {
          DirectUI::Element::_UpdateLayoutPosition(v8, 2, (a3 - Int) / 2);
          v14 = a2 - (2 * SystemMetrics + 2);
        }
        else
        {
          v13 = 0;
          v17 = 0;
          if ( (int)DUI_GetElementRootHWNDElement(this, &v17) >= 0 )
            v13 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::HWNDElement *))(*(_QWORD *)v17 + 360LL))(v17);
          LODWORD(v17) = 0;
          SHLogicalToPhysicalDPIMetric(v13, 49, (int *)&v17);
          DirectUI::Element::_UpdateLayoutPosition(v8, 2 * SystemMetrics + 2, (a3 - Int) / 2);
          v14 = a2 - 2 * SystemMetrics - (_DWORD)v17 - 2;
        }
        DirectUI::Element::_UpdateLayoutSize(v8, v14, Int);
      }
    }
  }
  v15 = v16;
  if ( v16 )
  {
    v16 = 0;
    DirectUI::Value::Release(v15);
  }
}

```

## disassembly

```asm
0x1800dbef0  mov     rax, rsp
0x1800dbef3  mov     [rax+8], rbx
0x1800dbef7  mov     [rax+10h], rbp
0x1800dbefb  push    rsi
0x1800dbefc  push    rdi
0x1800dbefd  push    r12
0x1800dbeff  push    r14
0x1800dbf01  push    r15
0x1800dbf03  sub     rsp, 30h
0x1800dbf07  mov     r14d, r8d
0x1800dbf0a  mov     esi, edx
0x1800dbf0c  mov     rbp, rcx
0x1800dbf0f  mov     qword ptr [rax-38h], 0
0x1800dbf17  lea     rdx, [rax-38h]
0x1800dbf1b  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x1800dbf21  test    rax, rax
0x1800dbf24  jz      loc_1800DC044
0x1800dbf2a  lea     rdi, [rax+8]
0x1800dbf2e  test    dword ptr [rax], 10000000h
0x1800dbf34  jz      short loc_1800DBF39
0x1800dbf36  mov     rdi, [rdi]
0x1800dbf39  mov     rdi, [rdi]
0x1800dbf3c  test    rdi, rdi
0x1800dbf3f  jz      loc_1800DC044
0x1800dbf45  mov     rax, [rdi]
0x1800dbf48  mov     rcx, rdi
0x1800dbf4b  mov     rax, [rax+118h]
0x1800dbf52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbf57  mov     r8, rax
0x1800dbf5a  mov     rcx, [rax]
0x1800dbf5d  mov     rax, [rcx+50h]
0x1800dbf61  mov     rdx, cs:?Class@CSearchEditBox@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * CSearchEditBox::Class
0x1800dbf68  mov     rcx, r8
0x1800dbf6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbf70  test    al, al
0x1800dbf72  jz      loc_1800DC044
0x1800dbf78  xor     r9d, r9d
0x1800dbf7b  lea     r8d, [r9+1]
0x1800dbf7f  lea     rdx, off_180217BD0; "FontHeight"
0x1800dbf86  mov     rcx, rdi
0x1800dbf89  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800dbf8f  mov     rbx, rax
0x1800dbf92  mov     rcx, rax
0x1800dbf95  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800dbf9b  mov     r15d, eax
0x1800dbf9e  mov     rcx, rbx
0x1800dbfa1  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800dbfa7  mov     ecx, 2Dh ; '-'; nIndex
0x1800dbfac  call    cs:__imp_GetSystemMetrics
0x1800dbfb2  mov     r12d, eax
0x1800dbfb5  cmp     qword ptr [rdi+280h], 0
0x1800dbfbd  jnz     loc_1800DC075
0x1800dbfc3  xor     ebx, ebx
0x1800dbfc5  mov     [rsp+58h+arg_18], rbx
0x1800dbfca  lea     rdx, [rsp+58h+arg_18]; struct DirectUI::HWNDElement **
0x1800dbfcf  mov     rcx, rbp; struct DirectUI::Element *
0x1800dbfd2  call    ?DUI_GetElementRootHWNDElement@@YAJPEAVElement@DirectUI@@PEAPEAVHWNDElement@2@@Z; DUI_GetElementRootHWNDElement(DirectUI::Element *,DirectUI::HWNDElement * *)
0x1800dbfd7  test    eax, eax
0x1800dbfd9  js      short loc_1800DBFF2
0x1800dbfdb  mov     rcx, [rsp+58h+arg_18]
0x1800dbfe0  mov     rax, [rcx]
0x1800dbfe3  mov     rax, [rax+168h]
0x1800dbfea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbfef  mov     rbx, rax
0x1800dbff2  mov     dword ptr [rsp+58h+arg_18], 0
0x1800dbffa  lea     r8, [rsp+58h+arg_18]; int *
0x1800dbfff  mov     edx, 31h ; '1'; int
0x1800dc004  mov     rcx, rbx; HWND
0x1800dc007  call    ?SHLogicalToPhysicalDPIMetric@@YAXPEAUHWND__@@HPEAH@Z; SHLogicalToPhysicalDPIMetric(HWND__ *,int,int *)
0x1800dc00c  lea     ebx, [r12+r12]
0x1800dc010  sub     r14d, r15d
0x1800dc013  mov     eax, r14d
0x1800dc016  cdq
0x1800dc017  mov     ebp, 2
0x1800dc01c  idiv    ebp
0x1800dc01e  mov     r8d, eax
0x1800dc021  lea     edx, [rbx+2]
0x1800dc024  mov     rcx, rdi
0x1800dc027  call    cs:__imp_?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z; DirectUI::Element::_UpdateLayoutPosition(int,int)
0x1800dc02d  sub     esi, ebx
0x1800dc02f  sub     esi, dword ptr [rsp+58h+arg_18]
0x1800dc033  sub     esi, ebp
0x1800dc035  mov     r8d, r15d
0x1800dc038  mov     edx, esi
0x1800dc03a  mov     rcx, rdi
0x1800dc03d  call    cs:__imp_?_UpdateLayoutSize@Element@DirectUI@@QEAAXHH@Z; DirectUI::Element::_UpdateLayoutSize(int,int)
0x1800dc043  nop
0x1800dc044  mov     rcx, [rsp+58h+var_38]
0x1800dc049  test    rcx, rcx
0x1800dc04c  jz      short loc_1800DC05E
0x1800dc04e  mov     [rsp+58h+var_38], 0
0x1800dc057  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800dc05d  nop
0x1800dc05e  mov     rbx, [rsp+58h+arg_0]
0x1800dc063  mov     rbp, [rsp+58h+arg_8]
0x1800dc068  add     rsp, 30h
0x1800dc06c  pop     r15
0x1800dc06e  pop     r14
0x1800dc070  pop     r12
0x1800dc072  pop     rdi
0x1800dc073  pop     rsi
0x1800dc074  retn
0x1800dc075  sub     r14d, r15d
0x1800dc078  mov     eax, r14d
0x1800dc07b  cdq
0x1800dc07c  mov     ebp, 2
0x1800dc081  idiv    ebp
0x1800dc083  mov     r8d, eax
0x1800dc086  mov     edx, ebp
0x1800dc088  mov     rcx, rdi
0x1800dc08b  call    cs:__imp_?_UpdateLayoutPosition@Element@DirectUI@@QEAAXHH@Z; DirectUI::Element::_UpdateLayoutPosition(int,int)
0x1800dc091  lea     eax, ds:2[r12*2]
0x1800dc099  sub     esi, eax
0x1800dc09b  jmp     short loc_1800DC035
```

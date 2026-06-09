# UISmartPropertyCollection::_FillChildGrid(DirectUI::DynamicArray<DirectUI::Element *,0> *,CDSA<UISmartPropertyCollection::SmartColumnInfo> &,int *,int,int)

- ea: `0x18000e598`
- end: `0x18000e914`
- name: `?_FillChildGrid@UISmartPropertyCollection@@AEAAXPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@DirectUI@@AEAV?$CDSA@USmartColumnInfo@UISmartPropertyCollection@@@@PEAHHH@Z`
- size: `892`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000eec0`

## callees

- `0x18000e598`
- `0x18000ee1c`
- `0x18000fbf0`
- `0x18000fe5c`
- `0x1800471dc`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e881`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e8b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e881`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e8b5`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x18000e7ef`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x18000e7ef`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e638`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e66d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e6a0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e6d3`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e638`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e66d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e6a0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e6d3`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000e62c`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000e662`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000e690`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000e6c3`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000e62c`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000e662`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000e690`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000e6c3`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000e620`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000e656`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000e684`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000e6b7`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000e620`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000e656`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000e684`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000e6b7`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18000e8d7`
- `DUI70!?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x18000e8d7`

## pseudocode

```c
unsigned __int64 __fastcall UISmartPropertyCollection::_FillChildGrid(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3,
        char *a4,
        int a5,
        int a6)
{
  unsigned __int64 result; // rax
  unsigned int v9; // esi
  unsigned int v10; // r12d
  DirectUI::Element *v11; // r14
  DirectUI::Value *Value; // rbx
  int v13; // ebp
  DirectUI::Value *v14; // rdi
  int Int; // ebx
  DirectUI::Value *v16; // rdi
  DirectUI::Value *v17; // rdi
  int v18; // ebx
  HMODULE v19; // rcx
  __int64 v20; // rdi
  FARPROC ProcAddress; // rax
  __int64 v22; // rax
  _DWORD *v23; // rdi
  __int64 v24; // r8
  LONG v25; // edi
  UISmartProperty *v26; // rax
  LONG VisibleWidth; // ebp
  int v28; // edx
  __int64 v29; // rcx
  int v30; // eax
  unsigned int *v31; // rdi
  unsigned int v32; // [rsp+20h] [rbp-58h]
  __int64 v33; // [rsp+28h] [rbp-50h]
  int v34; // [rsp+80h] [rbp+8h]
  int v35; // [rsp+88h] [rbp+10h]
  int v38; // [rsp+A8h] [rbp+30h]

  result = (unsigned int)(a6 * a5);
  if ( (int)result > 0 )
    result = (unsigned __int64)memset_0(a4, -1, 4LL * (int)result);
  v9 = 0;
  v10 = *a2 & 0xFFFFFFF;
  v32 = v10;
  if ( v10 )
  {
    result = (unsigned __int64)(a2 + 2);
    do
    {
      if ( (*a2 & 0x10000000) != 0 )
        result = *(_QWORD *)result;
      v11 = (DirectUI::Element *)element_cast<UIProperty>(*(_QWORD *)(result + 8LL * v9));
      Value = DirectUI::Element::GetValue(v11, UIProperty::RowProp, 2, 0);
      v13 = DirectUI::Value::GetInt(Value) - 1;
      DirectUI::Value::Release(Value);
      v35 = v13;
      v14 = DirectUI::Element::GetValue(v11, UIProperty::ColumnProp, 2, 0);
      Int = DirectUI::Value::GetInt(v14);
      DirectUI::Value::Release(v14);
      v16 = DirectUI::Element::GetValue(v11, UIProperty::RowSpanCountProp, 2, 0);
      v34 = DirectUI::Value::GetInt(v16);
      DirectUI::Value::Release(v16);
      v17 = DirectUI::Element::GetValue(v11, UIProperty::ColumnSpanCountProp, 2, 0);
      v38 = DirectUI::Value::GetInt(v17);
      DirectUI::Value::Release(v17);
      if ( v13 >= 0 && v13 < a5 )
      {
        v18 = Int - 1;
        if ( v18 >= 0 && v18 < a6 && v34 > 0 && v13 + v34 <= a5 && v38 > 0 && v18 + v38 <= a6 )
        {
          v19 = g_hinstCC;
          v20 = *a3;
          ProcAddress = (FARPROC)qword_1802912B8;
          if ( qword_1802912B8 == -1 )
          {
            if ( g_hinstCC || (DelayLoadCC(0), (v19 = g_hinstCC) != 0) )
            {
              ProcAddress = GetProcAddress(v19, (LPCSTR)0x143);
              v19 = g_hinstCC;
            }
            else
            {
              ProcAddress = 0;
            }
            qword_1802912B8 = (__int64)ProcAddress;
          }
          if ( ProcAddress )
          {
            v22 = ((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(v20, (unsigned int)v18);
            v19 = g_hinstCC;
            v23 = (_DWORD *)v22;
            ProcAddress = (FARPROC)qword_1802912B8;
          }
          else
          {
            v23 = 0;
          }
          v24 = *a3;
          v33 = *a3;
          if ( ProcAddress == (FARPROC)-1LL )
          {
            if ( v19 || (DelayLoadCC(0), (v19 = g_hinstCC) != 0) )
              ProcAddress = GetProcAddress(v19, (LPCSTR)0x143);
            else
              ProcAddress = 0;
            v24 = v33;
            qword_1802912B8 = (__int64)ProcAddress;
          }
          if ( ProcAddress )
            ProcAddress = (FARPROC)((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(
                                     v24,
                                     (unsigned int)(v18 + v38 - 1));
          v25 = *((_DWORD *)ProcAddress + 1) - *v23 + *(_DWORD *)ProcAddress;
          v26 = (UISmartProperty *)element_cast<UISmartProperty>(v11);
          if ( v26 )
            VisibleWidth = UISmartProperty::GetVisibleWidth(v26);
          else
            VisibleWidth = v25;
          if ( (*(unsigned int (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v11 + 360LL))(v11)
            && v25 >= VisibleWidth
            && ((DirectUI::Element::GetContentAlign(v11) & 0x550) != 0
             || v25 >= DirectUI::Element::GetDesiredSize(v11)->cx) )
          {
            v28 = 0;
            do
            {
              v29 = v38;
              v30 = a6 * (v28 + v35);
              ++v28;
              v31 = (unsigned int *)&a4[4 * v18 + 4 * v30];
              while ( v29 )
              {
                *v31++ = v9;
                --v29;
              }
            }
            while ( v28 < v34 );
            v10 = v32;
          }
        }
      }
      ++v9;
      result = (unsigned __int64)(a2 + 2);
    }
    while ( v9 < v10 );
  }
  return result;
}

```

## disassembly

```asm
0x18000e598  mov     [rsp+arg_18], r9
0x18000e59d  mov     [rsp+arg_10], r8
0x18000e5a2  mov     [rsp+arg_0], rcx
0x18000e5a7  push    rbx
0x18000e5a8  push    rbp
0x18000e5a9  push    rsi
0x18000e5aa  push    rdi
0x18000e5ab  push    r12
0x18000e5ad  push    r13
0x18000e5af  push    r14
0x18000e5b1  push    r15
0x18000e5b3  sub     rsp, 38h
0x18000e5b7  mov     eax, [rsp+78h+arg_20]
0x18000e5be  mov     r13, rdx
0x18000e5c1  mov     r15d, [rsp+78h+arg_28]
0x18000e5c9  imul    eax, r15d
0x18000e5cd  test    eax, eax
0x18000e5cf  jg      loc_18000E8FD
0x18000e5d5  mov     r12d, [r13+0]
0x18000e5d9  mov     esi, 0
0x18000e5de  and     r12d, 0FFFFFFFh
0x18000e5e5  mov     [rsp+78h+var_58], r12d
0x18000e5ea  jbe     loc_18000E855
0x18000e5f0  lea     rax, [r13+8]
0x18000e5f4  test    dword ptr [r13+0], 10000000h
0x18000e5fc  jz      short loc_18000E601
0x18000e5fe  mov     rax, [rax]
0x18000e601  mov     ecx, esi
0x18000e603  mov     rcx, [rax+rcx*8]
0x18000e607  call    ??$element_cast@VUIProperty@@@@YAPEAVUIProperty@@PEAVElement@DirectUI@@@Z; element_cast<UIProperty>(DirectUI::Element *)
0x18000e60c  xor     r9d, r9d
0x18000e60f  lea     rdx, ?RowProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::RowProp(void)
0x18000e616  mov     rcx, rax
0x18000e619  mov     r14, rax
0x18000e61c  lea     r8d, [r9+2]
0x18000e620  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18000e626  mov     rcx, rax
0x18000e629  mov     rbx, rax
0x18000e62c  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18000e632  mov     rcx, rbx
0x18000e635  lea     ebp, [rax-1]
0x18000e638  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000e63e  xor     r9d, r9d
0x18000e641  mov     [rsp+78h+arg_8], ebp
0x18000e648  lea     rdx, ?ColumnProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::ColumnProp(void)
0x18000e64f  mov     rcx, r14
0x18000e652  lea     r8d, [r9+2]
0x18000e656  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18000e65c  mov     rcx, rax
0x18000e65f  mov     rdi, rax
0x18000e662  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18000e668  mov     rcx, rdi
0x18000e66b  mov     ebx, eax
0x18000e66d  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000e673  xor     r9d, r9d
0x18000e676  lea     rdx, ?RowSpanCountProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::RowSpanCountProp(void)
0x18000e67d  mov     rcx, r14
0x18000e680  lea     r8d, [r9+2]
0x18000e684  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18000e68a  mov     rcx, rax
0x18000e68d  mov     rdi, rax
0x18000e690  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18000e696  mov     rcx, rdi
0x18000e699  mov     dword ptr [rsp+78h+arg_0], eax
0x18000e6a0  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000e6a6  xor     r9d, r9d
0x18000e6a9  lea     rdx, ?ColumnSpanCountProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::ColumnSpanCountProp(void)
0x18000e6b0  mov     rcx, r14
0x18000e6b3  lea     r8d, [r9+2]
0x18000e6b7  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18000e6bd  mov     rcx, rax
0x18000e6c0  mov     rdi, rax
0x18000e6c3  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x18000e6c9  mov     rcx, rdi
0x18000e6cc  mov     [rsp+78h+arg_28], eax
0x18000e6d3  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000e6d9  test    ebp, ebp
0x18000e6db  js      loc_18000E846
0x18000e6e1  cmp     ebp, [rsp+78h+arg_20]
0x18000e6e8  jge     loc_18000E846
0x18000e6ee  sub     ebx, 1
0x18000e6f1  js      loc_18000E846
0x18000e6f7  cmp     ebx, r15d
0x18000e6fa  jge     loc_18000E846
0x18000e700  mov     eax, dword ptr [rsp+78h+arg_0]
0x18000e707  test    eax, eax
0x18000e709  jle     loc_18000E846
0x18000e70f  add     eax, ebp
0x18000e711  cmp     eax, [rsp+78h+arg_20]
0x18000e718  jg      loc_18000E846
0x18000e71e  mov     eax, [rsp+78h+arg_28]
0x18000e725  test    eax, eax
0x18000e727  jle     loc_18000E846
0x18000e72d  lea     ebp, [rbx+rax]
0x18000e730  cmp     ebp, r15d
0x18000e733  jg      loc_18000E846
0x18000e739  mov     rax, [rsp+78h+arg_10]
0x18000e741  mov     rcx, cs:g_hinstCC
0x18000e748  mov     rdi, [rax]
0x18000e74b  mov     rax, cs:qword_1802912B8
0x18000e752  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e756  jz      loc_18000E866
0x18000e75c  test    rax, rax
0x18000e75f  jz      loc_18000E8F1
0x18000e765  mov     edx, ebx
0x18000e767  mov     rcx, rdi
0x18000e76a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e76f  mov     rcx, cs:g_hinstCC
0x18000e776  mov     rdi, rax
0x18000e779  mov     rax, cs:qword_1802912B8
0x18000e780  mov     r8, [rsp+78h+arg_10]
0x18000e788  mov     r8, [r8]
0x18000e78b  mov     [rsp+78h+var_50], r8
0x18000e790  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e794  jz      loc_18000E89A
0x18000e79a  test    rax, rax
0x18000e79d  jz      loc_18000E8F8
0x18000e7a3  lea     edx, [rbp-1]
0x18000e7a6  mov     rcx, r8
0x18000e7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7ae  mov     ecx, [rax+4]
0x18000e7b1  sub     ecx, [rdi]
0x18000e7b3  mov     edi, [rax]
0x18000e7b5  add     edi, ecx
0x18000e7b7  mov     rcx, r14
0x18000e7ba  call    ??$element_cast@VUISmartProperty@@@@YAPEAVUISmartProperty@@PEAVElement@DirectUI@@@Z; element_cast<UISmartProperty>(DirectUI::Element *)
0x18000e7bf  test    rax, rax
0x18000e7c2  jz      loc_18000E8EA
0x18000e7c8  mov     rcx, rax; this
0x18000e7cb  call    ?GetVisibleWidth@UISmartProperty@@QEAAHXZ; UISmartProperty::GetVisibleWidth(void)
0x18000e7d0  mov     ebp, eax
0x18000e7d2  mov     rax, [r14]
0x18000e7d5  mov     rcx, r14
0x18000e7d8  mov     rax, [rax+168h]
0x18000e7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7e4  test    eax, eax
0x18000e7e6  jz      short loc_18000E846
0x18000e7e8  cmp     edi, ebp
0x18000e7ea  jl      short loc_18000E846
0x18000e7ec  mov     rcx, r14
0x18000e7ef  call    cs:__imp_?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x18000e7f5  test    eax, 550h
0x18000e7fa  jz      loc_18000E8D4
0x18000e800  mov     r8d, [rsp+78h+arg_8]
0x18000e808  xor     edx, edx
0x18000e80a  movsxd  r9, [rsp+78h+arg_28]
0x18000e812  mov     r10d, dword ptr [rsp+78h+arg_0]
0x18000e81a  mov     r12, [rsp+78h+arg_18]
0x18000e822  lea     eax, [rdx+r8]
0x18000e826  mov     rcx, r9
0x18000e829  imul    eax, r15d
0x18000e82d  inc     edx
0x18000e82f  add     eax, ebx
0x18000e831  cdqe
0x18000e833  lea     rdi, [r12+rax*4]
0x18000e837  movsxd  rax, esi
0x18000e83a  rep stosd
0x18000e83c  cmp     edx, r10d
0x18000e83f  jl      short loc_18000E822
0x18000e841  mov     r12d, [rsp+78h+var_58]
0x18000e846  inc     esi
0x18000e848  lea     rax, [r13+8]
0x18000e84c  cmp     esi, r12d
0x18000e84f  jb      loc_18000E5F4
0x18000e855  add     rsp, 38h
0x18000e859  pop     r15
0x18000e85b  pop     r14
0x18000e85d  pop     r13
0x18000e85f  pop     r12
0x18000e861  pop     rdi
0x18000e862  pop     rsi
0x18000e863  pop     rbp
0x18000e864  pop     rbx
0x18000e865  retn
0x18000e866  test    rcx, rcx
0x18000e869  jnz     short loc_18000E87C
0x18000e86b  call    DelayLoadCC
0x18000e870  mov     rcx, cs:g_hinstCC; hModule
0x18000e877  test    rcx, rcx
0x18000e87a  jz      short loc_18000E8CC
0x18000e87c  mov     edx, 143h; lpProcName
0x18000e881  call    cs:__imp_GetProcAddress
0x18000e887  mov     rcx, cs:g_hinstCC
0x18000e88e  mov     cs:qword_1802912B8, rax
0x18000e895  jmp     loc_18000E75C
0x18000e89a  test    rcx, rcx
0x18000e89d  jnz     short loc_18000E8B0
0x18000e89f  call    DelayLoadCC
0x18000e8a4  mov     rcx, cs:g_hinstCC; hModule
0x18000e8ab  test    rcx, rcx
0x18000e8ae  jz      short loc_18000E8D0
0x18000e8b0  mov     edx, 143h; lpProcName
0x18000e8b5  call    cs:__imp_GetProcAddress
0x18000e8bb  mov     r8, [rsp+78h+var_50]
0x18000e8c0  mov     cs:qword_1802912B8, rax
0x18000e8c7  jmp     loc_18000E79A
0x18000e8cc  xor     eax, eax
0x18000e8ce  jmp     short loc_18000E88E
0x18000e8d0  xor     eax, eax
0x18000e8d2  jmp     short loc_18000E8BB
0x18000e8d4  mov     rcx, r14
0x18000e8d7  call    cs:__imp_?GetDesiredSize@Element@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Element::GetDesiredSize(void)
0x18000e8dd  cmp     edi, [rax]
0x18000e8df  jl      loc_18000E846
0x18000e8e5  jmp     loc_18000E800
0x18000e8ea  mov     ebp, edi
0x18000e8ec  jmp     loc_18000E7D2
0x18000e8f1  xor     edi, edi
0x18000e8f3  jmp     loc_18000E780
0x18000e8f8  jmp     loc_18000E7AE
0x18000e8fd  movsxd  r8, eax
0x18000e900  or      edx, 0FFFFFFFFh; Val
0x18000e903  shl     r8, 2; Size
0x18000e907  mov     rcx, r9; void *
0x18000e90a  call    memset_0
0x18000e90f  jmp     loc_18000E5D5
```

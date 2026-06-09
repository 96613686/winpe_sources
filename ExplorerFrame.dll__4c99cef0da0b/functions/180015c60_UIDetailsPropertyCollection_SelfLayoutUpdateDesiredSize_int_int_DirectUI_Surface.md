# UIDetailsPropertyCollection::_SelfLayoutUpdateDesiredSize(int,int,DirectUI::Surface *)

- ea: `0x180015c60`
- end: `0x180015f03`
- name: `?_SelfLayoutUpdateDesiredSize@UIDetailsPropertyCollection@@EEAA?AUtagSIZE@@HHPEAVSurface@DirectUI@@@Z`
- size: `675`
- prototype: `struct tagSIZE __fastcall(UIDetailsPropertyCollection *__hidden this, int, int, struct DirectUI::Surface *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180015c60`
- `0x180016790`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `USER32!SetRectEmpty` at `0x180015d3a`
- `USER32!SetRectEmpty` at `0x180015d3a`
- `DUI70!?LastDSConstProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180015daa`
- `DUI70!?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x180015e0b`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180015cfb`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180015d82`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180015cfb`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180015d82`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180015e9d`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180015e9d`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180015e22`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180015e22`
- `DUI70!?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180015d5f`
- `DUI70!?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z` at `0x180015d5f`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180015d1d`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180015d1d`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180015db8`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180015e15`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180015db8`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180015e15`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180015e54`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x180015e54`
- `DUI70!?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180015dc5`
- `DUI70!?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180015dc5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct tagSIZE __fastcall UIDetailsPropertyCollection::_SelfLayoutUpdateDesiredSize(
        DirectUI::Element **this,
        int *a2,
        int a3,
        struct DirectUI::Surface *a4,
        DirectUI::Value *a5)
{
  int v5; // r15d
  struct DirectUI::IClassInfo *v8; // rdi
  DirectUI::Element *Parent; // rbx
  __int64 v10; // rax
  __int64 Children; // r12
  DirectUI::Element *v12; // rdi
  const struct tagRECT *Padding; // rax
  struct DirectUI::Element *v14; // rsi
  LONG cx; // esi
  int v16; // esi
  __int64 v17; // r14
  int v18; // ecx
  __int64 v19; // rdi
  DirectUI::Element *v20; // rdi
  int Int; // ebx
  int v22; // r8d
  int v23; // ecx
  DirectUI::Value *v24; // rcx
  int v25; // eax
  int v26; // eax
  unsigned int v28; // [rsp+30h] [rbp-41h]
  struct DirectUI::Value *Value; // [rsp+38h] [rbp-39h] BYREF
  int v30; // [rsp+40h] [rbp-31h]
  DirectUI::Value *v31; // [rsp+48h] [rbp-29h] BYREF
  DirectUI::Value *v32[2]; // [rsp+50h] [rbp-21h] BYREF
  struct tagRECT rc; // [rsp+60h] [rbp-11h] BYREF

  v28 = (unsigned int)a4;
  v5 = a3;
  v30 = a3;
  v32[1] = a5;
  *(_QWORD *)a2 = 0;
  if ( a3 > 0 && (int)a4 > 0 )
  {
    v8 = LineViewer::Class;
    Parent = (DirectUI::Element *)this;
    if ( this )
    {
      while ( 1 )
      {
        v10 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)Parent + 280LL))(Parent);
        if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v10 + 80LL))(
               v10,
               v8) )
        {
          break;
        }
        Parent = DirectUI::Element::GetParent(Parent);
        if ( !Parent )
          goto LABEL_22;
      }
      v31 = 0;
      Children = DirectUI::Element::GetChildren(this, &v31);
      if ( Children )
      {
        rc = 0;
        SetRectEmpty(&rc);
        v12 = (DirectUI::Element *)this;
        do
        {
          Value = 0;
          Padding = DirectUI::Element::GetPadding(v12, &Value);
          rc.top += Padding->top;
          rc.left += Padding->left;
          rc.right += Padding->right;
          rc.bottom += Padding->bottom;
          v14 = DirectUI::Element::GetParent(v12);
          CValuePtr::~CValuePtr((CValuePtr *)&Value);
          if ( v12 == Parent )
            break;
          v12 = v14;
        }
        while ( v14 );
        Value = DirectUI::Element::GetValue(
                  this[25],
                  (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::LastDSConstProp,
                  1,
                  0);
        cx = DirectUI::Value::GetSize(Value)->cx;
        CValuePtr::~CValuePtr((CValuePtr *)&Value);
        v16 = rc.left + cx - v5;
        v17 = 0;
        v18 = *(_DWORD *)Children;
        if ( (*(_DWORD *)Children & 0xFFFFFFF) != 0 )
        {
          do
          {
            if ( (v18 & 0x10000000) != 0 )
              v19 = *(_QWORD *)(Children + 8);
            else
              v19 = Children + 8;
            v20 = *(DirectUI::Element **)(v19 + 8 * v17);
            v32[0] = DirectUI::Element::GetValue(
                       v20,
                       (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::WidthProp,
                       1,
                       0);
            Int = DirectUI::Value::GetInt(v32[0]);
            CValuePtr::~CValuePtr((CValuePtr *)v32);
            v22 = Int - v16;
            if ( (_DWORD)v17 )
              v22 = Int;
            DirectUI::Element::_UpdateDesiredSize(v20, (unsigned int)&Value, v22, (struct DirectUI::Surface *)v28);
            *a2 += (int)Value;
            v23 = HIDWORD(Value);
            if ( a2[1] > SHIDWORD(Value) )
              v23 = a2[1];
            a2[1] = v23;
            v17 = (unsigned int)(v17 + 1);
            v18 = *(_DWORD *)Children;
          }
          while ( (unsigned int)v17 < (*(_DWORD *)Children & 0xFFFFFFFu) );
          v5 = v30;
        }
      }
      v24 = v31;
      if ( v31 )
      {
        v31 = 0;
        DirectUI::Value::Release(v24);
      }
LABEL_22:
      LODWORD(a4) = v28;
    }
    v25 = *a2;
    if ( *a2 < 0 )
    {
      v25 = 0;
    }
    else if ( v25 > v5 )
    {
      v25 = v5;
    }
    *a2 = v25;
    v26 = a2[1];
    if ( v26 < 0 )
    {
      v26 = 0;
    }
    else if ( v26 > (int)a4 )
    {
      v26 = (int)a4;
    }
    a2[1] = v26;
  }
  return (struct tagSIZE)a2;
}

```

## disassembly

```asm
0x180015c60  push    rbp
0x180015c62  push    rbx
0x180015c63  push    rsi
0x180015c64  push    rdi
0x180015c65  push    r12
0x180015c67  push    r13
0x180015c69  push    r14
0x180015c6b  push    r15
0x180015c6d  lea     rbp, [rsp-17h]
0x180015c72  sub     rsp, 88h
0x180015c79  mov     rax, cs:__security_cookie
0x180015c80  xor     rax, rsp
0x180015c83  mov     [rbp+4Fh+var_50], rax
0x180015c87  mov     [rbp+4Fh+var_90], r9d
0x180015c8b  mov     r15d, r8d
0x180015c8e  mov     [rbp+4Fh+var_80], r8d
0x180015c92  mov     r13, rdx
0x180015c95  mov     r14, rcx
0x180015c98  mov     rax, [rbp+4Fh+arg_20]
0x180015c9c  mov     [rbp+4Fh+var_68], rax
0x180015ca0  xor     eax, eax
0x180015ca2  mov     [rdx], rax
0x180015ca5  test    r8d, r8d
0x180015ca8  jle     loc_180015ECE
0x180015cae  test    r9d, r9d
0x180015cb1  jle     loc_180015ECE
0x180015cb7  mov     rdi, cs:?Class@LineViewer@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * LineViewer::Class
0x180015cbe  mov     rbx, rcx
0x180015cc1  test    rcx, rcx
0x180015cc4  jz      loc_180015EA8
0x180015cca  nop     word ptr [rax+rax+00h]
0x180015cd0  mov     rax, [rbx]
0x180015cd3  mov     rcx, rbx
0x180015cd6  mov     rax, [rax+118h]
0x180015cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ce2  mov     rcx, rax
0x180015ce5  mov     rax, [rax]
0x180015ce8  mov     rdx, rdi
0x180015ceb  mov     rax, [rax+50h]
0x180015cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cf4  test    al, al
0x180015cf6  jnz     short loc_180015D0E
0x180015cf8  mov     rcx, rbx
0x180015cfb  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x180015d01  mov     rbx, rax
0x180015d04  test    rax, rax
0x180015d07  jnz     short loc_180015CD0
0x180015d09  jmp     loc_180015EA4
0x180015d0e  mov     [rbp+4Fh+var_78], 0
0x180015d16  lea     rdx, [rbp+4Fh+var_78]
0x180015d1a  mov     rcx, r14
0x180015d1d  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180015d23  mov     r12, rax
0x180015d26  test    rax, rax
0x180015d29  jz      loc_180015E8C
0x180015d2f  xorps   xmm0, xmm0
0x180015d32  movups  xmmword ptr [rbp+4Fh+rc.left], xmm0
0x180015d36  lea     rcx, [rbp+4Fh+rc]; lprc
0x180015d3a  call    cs:__imp_SetRectEmpty
0x180015d40  mov     rdi, r14
0x180015d43  nop     dword ptr [rax+00h]
0x180015d47  nop     word ptr [rax+rax+00000000h]
0x180015d50  mov     [rbp+4Fh+var_88], 0
0x180015d58  lea     rdx, [rbp+4Fh+var_88]
0x180015d5c  mov     rcx, rdi
0x180015d5f  call    cs:__imp_?GetPadding@Element@DirectUI@@QEAAPEBUtagRECT@@PEAPEAVValue@2@@Z; DirectUI::Element::GetPadding(DirectUI::Value * *)
0x180015d65  mov     rcx, rax
0x180015d68  mov     eax, [rax+4]
0x180015d6b  add     [rbp+4Fh+rc.top], eax
0x180015d6e  mov     eax, [rcx]
0x180015d70  add     [rbp+4Fh+rc.left], eax
0x180015d73  mov     eax, [rcx+8]
0x180015d76  add     [rbp+4Fh+rc.right], eax
0x180015d79  mov     eax, [rcx+0Ch]
0x180015d7c  add     [rbp+4Fh+rc.bottom], eax
0x180015d7f  mov     rcx, rdi
0x180015d82  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x180015d88  mov     rsi, rax
0x180015d8b  lea     rcx, [rbp+4Fh+var_88]; this
0x180015d8f  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180015d94  cmp     rdi, rbx
0x180015d97  jz      short loc_180015DA1
0x180015d99  mov     rdi, rsi
0x180015d9c  test    rsi, rsi
0x180015d9f  jnz     short loc_180015D50
0x180015da1  xor     r9d, r9d
0x180015da4  mov     r8d, 1
0x180015daa  mov     rdx, cs:__imp_?LastDSConstProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::LastDSConstProp(void)
0x180015db1  mov     rcx, [r14+0C8h]
0x180015db8  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180015dbe  mov     [rbp+4Fh+var_88], rax
0x180015dc2  mov     rcx, rax
0x180015dc5  call    cs:__imp_?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ; DirectUI::Value::GetSize(void)
0x180015dcb  mov     esi, [rax]
0x180015dcd  lea     rcx, [rbp+4Fh+var_88]; this
0x180015dd1  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180015dd6  sub     esi, r15d
0x180015dd9  add     esi, [rbp+4Fh+rc.left]
0x180015ddc  xor     r14d, r14d
0x180015ddf  mov     ecx, [r12]
0x180015de3  test    ecx, 0FFFFFFFh
0x180015de9  jbe     loc_180015E8C
0x180015def  bt      ecx, 1Ch
0x180015df3  jnb     loc_180015EF1
0x180015df9  mov     rdi, [r12+8]
0x180015dfe  mov     rdi, [rdi+r14*8]
0x180015e02  xor     r9d, r9d
0x180015e05  mov     r8d, 1
0x180015e0b  mov     rdx, cs:__imp_?WidthProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::WidthProp(void)
0x180015e12  mov     rcx, rdi
0x180015e15  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180015e1b  mov     [rbp+4Fh+var_70], rax
0x180015e1f  mov     rcx, rax
0x180015e22  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180015e28  mov     ebx, eax
0x180015e2a  lea     rcx, [rbp+4Fh+var_70]; this
0x180015e2e  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x180015e33  mov     r8d, ebx
0x180015e36  sub     r8d, esi
0x180015e39  test    r14d, r14d
0x180015e3c  cmovnz  r8d, ebx
0x180015e40  mov     rax, [rbp+4Fh+var_68]
0x180015e44  mov     [rsp+0C0h+var_A0], rax
0x180015e49  mov     r9d, [rbp+4Fh+var_90]
0x180015e4d  lea     rdx, [rbp+4Fh+var_88]
0x180015e51  mov     rcx, rdi
0x180015e54  call    cs:__imp_?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_UpdateDesiredSize(int,int,DirectUI::Surface *)
0x180015e5a  mov     eax, dword ptr [rbp+4Fh+var_88]
0x180015e5d  add     [r13+0], eax
0x180015e61  mov     ecx, dword ptr [rbp+4Fh+var_88+4]
0x180015e64  cmp     [r13+4], ecx
0x180015e68  cmovg   ecx, [r13+4]
0x180015e6d  mov     [r13+4], ecx
0x180015e71  inc     r14d
0x180015e74  mov     ecx, [r12]
0x180015e78  mov     eax, ecx
0x180015e7a  and     eax, 0FFFFFFFh
0x180015e7f  cmp     r14d, eax
0x180015e82  jb      loc_180015DEF
0x180015e88  mov     r15d, [rbp+4Fh+var_80]
0x180015e8c  mov     rcx, [rbp+4Fh+var_78]
0x180015e90  test    rcx, rcx
0x180015e93  jz      short loc_180015EA4
0x180015e95  mov     [rbp+4Fh+var_78], 0
0x180015e9d  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180015ea3  nop
0x180015ea4  mov     r9d, [rbp+4Fh+var_90]
0x180015ea8  mov     eax, [r13+0]
0x180015eac  test    eax, eax
0x180015eae  js      short loc_180015EFB
0x180015eb0  cmp     eax, r15d
0x180015eb3  cmovg   eax, r15d
0x180015eb7  mov     [r13+0], eax
0x180015ebb  mov     eax, [r13+4]
0x180015ebf  test    eax, eax
0x180015ec1  js      short loc_180015EFF
0x180015ec3  cmp     eax, r9d
0x180015ec6  cmovg   eax, r9d
0x180015eca  mov     [r13+4], eax
0x180015ece  mov     rax, r13
0x180015ed1  mov     rcx, [rbp+4Fh+var_50]
0x180015ed5  xor     rcx, rsp; StackCookie
0x180015ed8  call    __security_check_cookie
0x180015edd  add     rsp, 88h
0x180015ee4  pop     r15
0x180015ee6  pop     r14
0x180015ee8  pop     r13
0x180015eea  pop     r12
0x180015eec  pop     rdi
0x180015eed  pop     rsi
0x180015eee  pop     rbx
0x180015eef  pop     rbp
0x180015ef0  retn
0x180015ef1  lea     rdi, [r12+8]
0x180015ef6  jmp     loc_180015DFE
0x180015efb  xor     eax, eax
0x180015efd  jmp     short loc_180015EB7
0x180015eff  xor     eax, eax
0x180015f01  jmp     short loc_180015ECA
```

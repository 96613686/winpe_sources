# AccessibilityCplCore::SetFocusToFirstElement(DirectUI::Element *,int)

- ea: `0x1800182d8`
- end: `0x180018443`
- name: `?SetFocusToFirstElement@AccessibilityCplCore@@AEAAHPEAVElement@DirectUI@@H@Z`
- size: `363`
- prototype: `__int64 __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Element *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007a70`
- `0x1800182d8`

## callees

- `0x1800182d8`
- `0x18002e010`

## import_xrefs

- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001842a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001842a`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x18001837a`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x18001837a`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180018305`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180018305`
- `DUI70!?GetClassInfoPtr@ScrollViewer@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18001835d`
- `DUI70!?GetClassInfoPtr@ScrollViewer@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x18001835d`
- `DUI70!?GetClassInfoPtr@CCSysLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1800183d9`
- `DUI70!?GetClassInfoPtr@CCSysLink@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1800183d9`
- `DUI70!?GetClassInfoPtr@CCCheckBox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1800183a5`
- `DUI70!?GetClassInfoPtr@CCCheckBox@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x1800183a5`

## pseudocode

```c
__int64 __fastcall AccessibilityCplCore::SetFocusToFirstElement(
        AccessibilityCplCore *this,
        struct DirectUI::Element *a2,
        int a3)
{
  unsigned int Element; // ebx
  _DWORD *Children; // r14
  __int64 i; // rbp
  _QWORD *v8; // rsi
  DirectUI::Element *v9; // rsi
  __int64 v10; // rdi
  unsigned __int8 (__fastcall *v11)(__int64, __int64); // rbx
  __int64 ClassInfoPtr; // rax
  __int64 v13; // rdi
  unsigned __int8 (__fastcall *v14)(__int64, __int64); // rbx
  __int64 v15; // rax
  __int64 v16; // rdi
  unsigned __int8 (__fastcall *v17)(__int64, __int64); // rbx
  __int64 v18; // rax
  DirectUI::Value *v20; // [rsp+88h] [rbp+20h] BYREF

  v20 = 0;
  Element = 0;
  Children = (_DWORD *)DirectUI::Element::GetChildren(a2, &v20);
  if ( Children )
  {
    for ( i = 0; (unsigned int)i < (*Children & 0xFFFFFFFu); i = (unsigned int)(i + 1) )
    {
      v8 = Children + 2;
      if ( (*Children & 0x10000000) != 0 )
        v8 = (_QWORD *)*v8;
      v9 = (DirectUI::Element *)v8[i];
      v10 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v9 + 280LL))(v9);
      v11 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 80LL);
      ClassInfoPtr = DirectUI::ScrollViewer::GetClassInfoPtr();
      if ( v11(v10, ClassInfoPtr) )
        a3 = 1;
      if ( DirectUI::Element::GetVisible(v9) )
      {
        if ( a3 )
        {
          v13 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v9 + 280LL))(v9);
          v14 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 80LL);
          v15 = DirectUI::CCCheckBox::GetClassInfoPtr();
          if ( v14(v13, v15)
            || (v16 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v9 + 280LL))(v9),
                v17 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 80LL),
                v18 = DirectUI::CCSysLink::GetClassInfoPtr(),
                v17(v16, v18)) )
          {
            (*(void (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v9 + 168LL))(v9);
            Element = 1;
            break;
          }
        }
      }
      Element = AccessibilityCplCore::SetFocusToFirstElement(this, v9, a3);
      if ( Element )
        break;
    }
    DirectUI::Value::Release(v20);
  }
  return Element;
}

```

## disassembly

```asm
0x1800182d8  mov     r11, rsp
0x1800182db  push    rbx
0x1800182dc  push    rbp
0x1800182dd  push    rsi
0x1800182de  push    rdi
0x1800182df  push    r12
0x1800182e1  push    r13
0x1800182e3  push    r14
0x1800182e5  push    r15
0x1800182e7  sub     rsp, 28h
0x1800182eb  mov     rax, rdx
0x1800182ee  mov     qword ptr [r11+20h], 0
0x1800182f6  mov     r12, rcx
0x1800182f9  lea     rdx, [r11+20h]
0x1800182fd  mov     rcx, rax
0x180018300  mov     r15d, r8d
0x180018303  xor     ebx, ebx
0x180018305  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x18001830b  mov     r14, rax
0x18001830e  test    rax, rax
0x180018311  jz      loc_180018430
0x180018317  xor     ebp, ebp
0x180018319  lea     r13d, [rbx+1]
0x18001831d  mov     eax, [r14]
0x180018320  and     eax, 0FFFFFFFh
0x180018325  cmp     ebp, eax
0x180018327  jnb     loc_180018422
0x18001832d  test    dword ptr [r14], 10000000h
0x180018334  lea     rsi, [r14+8]
0x180018338  jz      short loc_18001833D
0x18001833a  mov     rsi, [rsi]
0x18001833d  mov     rsi, [rsi+rbp*8]
0x180018341  mov     rcx, rsi
0x180018344  mov     rax, [rsi]
0x180018347  mov     rax, [rax+118h]
0x18001834e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018353  mov     rdi, rax
0x180018356  mov     rax, [rax]
0x180018359  mov     rbx, [rax+50h]
0x18001835d  call    cs:__imp_?GetClassInfoPtr@ScrollViewer@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::ScrollViewer::GetClassInfoPtr(void)
0x180018363  mov     rdx, rax
0x180018366  mov     rcx, rdi
0x180018369  mov     rax, rbx
0x18001836c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018371  test    al, al
0x180018373  mov     rcx, rsi
0x180018376  cmovnz  r15d, r13d
0x18001837a  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180018380  test    al, al
0x180018382  jz      short loc_1800183F1
0x180018384  test    r15d, r15d
0x180018387  jz      short loc_1800183F1
0x180018389  mov     rax, [rsi]
0x18001838c  mov     rcx, rsi
0x18001838f  mov     rax, [rax+118h]
0x180018396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001839b  mov     rdi, rax
0x18001839e  mov     rax, [rax]
0x1800183a1  mov     rbx, [rax+50h]
0x1800183a5  call    cs:__imp_?GetClassInfoPtr@CCCheckBox@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::CCCheckBox::GetClassInfoPtr(void)
0x1800183ab  mov     rdx, rax
0x1800183ae  mov     rcx, rdi
0x1800183b1  mov     rax, rbx
0x1800183b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183b9  test    al, al
0x1800183bb  jnz     short loc_18001840D
0x1800183bd  mov     rax, [rsi]
0x1800183c0  mov     rcx, rsi
0x1800183c3  mov     rax, [rax+118h]
0x1800183ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183cf  mov     rdi, rax
0x1800183d2  mov     rax, [rax]
0x1800183d5  mov     rbx, [rax+50h]
0x1800183d9  call    cs:__imp_?GetClassInfoPtr@CCSysLink@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::CCSysLink::GetClassInfoPtr(void)
0x1800183df  mov     rdx, rax
0x1800183e2  mov     rcx, rdi
0x1800183e5  mov     rax, rbx
0x1800183e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183ed  test    al, al
0x1800183ef  jnz     short loc_18001840D
0x1800183f1  mov     r8d, r15d; int
0x1800183f4  mov     rdx, rsi; struct DirectUI::Element *
0x1800183f7  mov     rcx, r12; this
0x1800183fa  call    ?SetFocusToFirstElement@AccessibilityCplCore@@AEAAHPEAVElement@DirectUI@@H@Z; AccessibilityCplCore::SetFocusToFirstElement(DirectUI::Element *,int)
0x1800183ff  mov     ebx, eax
0x180018401  test    eax, eax
0x180018403  jnz     short loc_180018422
0x180018405  add     ebp, r13d
0x180018408  jmp     loc_18001831D
0x18001840d  mov     rax, [rsi]
0x180018410  mov     rcx, rsi
0x180018413  mov     rax, [rax+0A8h]
0x18001841a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001841f  mov     ebx, r13d
0x180018422  mov     rcx, [rsp+68h+arg_18]
0x18001842a  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180018430  mov     eax, ebx
0x180018432  add     rsp, 28h
0x180018436  pop     r15
0x180018438  pop     r14
0x18001843a  pop     r13
0x18001843c  pop     r12
0x18001843e  pop     rdi
0x18001843f  pop     rsi
0x180018440  pop     rbp
0x180018441  pop     rbx
0x180018442  retn
```

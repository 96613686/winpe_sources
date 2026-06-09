# AccessibilityCplCore::DeleteShortCuts(DirectUI::Element *)

- ea: `0x180005a48`
- end: `0x180005bd6`
- name: `?DeleteShortCuts@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@@Z`
- size: `398`
- prototype: `void __fastcall(AccessibilityCplCore *__hidden this, struct DirectUI::Element *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005a48`
- `0x1800198f4`

## callees

- `0x180004310`
- `0x1800059b0`
- `0x180005a48`
- `0x1800063fc`
- `0x1800069a0`
- `0x180015780`
- `0x18002e010`

## import_xrefs

- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180005b94`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180005bbf`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180005b94`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180005bbf`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180005abb`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x180005abb`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180005a7e`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x180005a7e`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180005b78`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x180005b78`
- `DUI70!?SetShortcut@Element@DirectUI@@QEAAJH@Z` at `0x180005ace`
- `DUI70!?SetShortcut@Element@DirectUI@@QEAAJH@Z` at `0x180005ace`
- `DUI70!?GetClassInfoPtr@CCBase@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180005af5`
- `DUI70!?GetClassInfoPtr@CCBase@DirectUI@@SAPEAUIClassInfo@2@XZ` at `0x180005af5`

## pseudocode

```c
void __fastcall AccessibilityCplCore::DeleteShortCuts(AccessibilityCplCore *this, struct DirectUI::Element *a2)
{
  AccessibilityCplCore *v2; // rbx
  _DWORD *Children; // rax
  _DWORD *v4; // r14
  int v5; // ecx
  __int64 v6; // r15
  char v7; // r13
  _DWORD *v8; // rsi
  DirectUI::Element *v9; // rsi
  __int64 v10; // rdi
  unsigned __int8 (__fastcall *v11)(__int64, __int64); // rbx
  __int64 ClassInfoPtr; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  const unsigned __int16 *Buffer; // rax
  __int64 v18; // [rsp+78h] [rbp+50h] BYREF
  DirectUI::Value *v19; // [rsp+80h] [rbp+58h] BYREF
  DirectUI::Value *v20; // [rsp+88h] [rbp+60h] BYREF

  if ( a2 )
  {
    v20 = 0;
    v2 = this;
    Children = (_DWORD *)DirectUI::Element::GetChildren(a2, &v20);
    v4 = Children;
    if ( Children )
    {
      v5 = *Children;
      v6 = 0;
      v7 = 1;
      if ( (*Children & 0xFFFFFFF) != 0 )
      {
        do
        {
          if ( (v5 & 0x10000000) != 0 )
            v8 = (_DWORD *)*((_QWORD *)v4 + 1);
          else
            v8 = v4 + 2;
          v9 = *(DirectUI::Element **)&v8[2 * v6];
          if ( DirectUI::Element::GetVisible(v9) )
          {
            DirectUI::Element::SetShortcut(v9, 0);
            if ( v7 )
            {
              v10 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v9 + 280LL))(v9);
              v11 = *(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 80LL);
              ClassInfoPtr = DirectUI::CCBase::GetClassInfoPtr();
              if ( v11(v10, ClassInfoPtr) )
              {
                (*(void (__fastcall **)(DirectUI::Element *))(*(_QWORD *)v9 + 168LL))(v9);
                v7 = 0;
              }
              v2 = this;
            }
            v13 = *(_QWORD *)v9;
            v19 = 0;
            v14 = (*(__int64 (__fastcall **)(DirectUI::Element *, DirectUI::Value **))(v13 + 24))(v9, &v19);
            if ( v14 )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v18,
                v14);
              while ( 1 )
              {
                v15 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(&v18);
                if ( v15 == -1 )
                  break;
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Delete(
                  &v18,
                  v15);
              }
              Buffer = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v18);
              DirectUI::Element::SetContentString(v9, Buffer);
              ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
            }
            if ( v19 )
              DirectUI::Value::Release(v19);
          }
          AccessibilityCplCore::DeleteShortCuts(v2, v9);
          v5 = *v4;
          v6 = (unsigned int)(v6 + 1);
        }
        while ( (unsigned int)v6 < (*v4 & 0xFFFFFFFu) );
      }
      DirectUI::Value::Release(v20);
    }
  }
}

```

## disassembly

```asm
0x180005a48  test    rdx, rdx
0x180005a4b  jz      locret_180005BD5
0x180005a51  mov     [rsp-40h+arg_0], rcx
0x180005a56  push    rbp
0x180005a57  push    rbx
0x180005a58  push    rsi
0x180005a59  push    rdi
0x180005a5a  push    r12
0x180005a5c  push    r13
0x180005a5e  push    r14
0x180005a60  push    r15
0x180005a62  mov     rbp, rsp
0x180005a65  sub     rsp, 28h
0x180005a69  mov     rax, rdx
0x180005a6c  mov     [rbp+arg_18], 0
0x180005a74  mov     rbx, rcx
0x180005a77  lea     rdx, [rbp+arg_18]
0x180005a7b  mov     rcx, rax
0x180005a7e  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x180005a84  mov     r14, rax
0x180005a87  test    rax, rax
0x180005a8a  jz      loc_180005BC5
0x180005a90  mov     ecx, [rax]
0x180005a92  xor     r15d, r15d
0x180005a95  mov     r13b, 1
0x180005a98  test    ecx, 0FFFFFFFh
0x180005a9e  jbe     loc_180005BBB
0x180005aa4  bt      ecx, 1Ch
0x180005aa8  jnb     short loc_180005AB0
0x180005aaa  mov     rsi, [r14+8]
0x180005aae  jmp     short loc_180005AB4
0x180005ab0  lea     rsi, [r14+8]
0x180005ab4  mov     rsi, [rsi+r15*8]
0x180005ab8  mov     rcx, rsi
0x180005abb  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x180005ac1  test    al, al
0x180005ac3  jz      loc_180005B9A
0x180005ac9  xor     edx, edx
0x180005acb  mov     rcx, rsi
0x180005ace  call    cs:__imp_?SetShortcut@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetShortcut(int)
0x180005ad4  test    r13b, r13b
0x180005ad7  jz      short loc_180005B26
0x180005ad9  mov     rax, [rsi]
0x180005adc  mov     rcx, rsi
0x180005adf  mov     rax, [rax+118h]
0x180005ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005aeb  mov     rdi, rax
0x180005aee  mov     rcx, [rax]
0x180005af1  mov     rbx, [rcx+50h]
0x180005af5  call    cs:__imp_?GetClassInfoPtr@CCBase@DirectUI@@SAPEAUIClassInfo@2@XZ; DirectUI::CCBase::GetClassInfoPtr(void)
0x180005afb  mov     rdx, rax
0x180005afe  mov     rcx, rdi
0x180005b01  mov     rax, rbx
0x180005b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b09  test    al, al
0x180005b0b  jz      short loc_180005B22
0x180005b0d  mov     rax, [rsi]
0x180005b10  mov     rcx, rsi
0x180005b13  mov     rax, [rax+0A8h]
0x180005b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b1f  xor     r13b, r13b
0x180005b22  mov     rbx, [rbp+arg_0]
0x180005b26  mov     rax, [rsi]
0x180005b29  lea     rdx, [rbp+arg_10]
0x180005b2d  mov     rcx, rsi
0x180005b30  mov     [rbp+arg_10], 0
0x180005b38  mov     rax, [rax+18h]
0x180005b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b41  test    rax, rax
0x180005b44  jz      short loc_180005B8B
0x180005b46  mov     rdx, rax
0x180005b49  lea     rcx, [rbp+arg_8]
0x180005b4d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180005b52  jmp     short loc_180005B5B
0x180005b54  mov     edx, eax
0x180005b56  call    ?Delete@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Delete(int,int)
0x180005b5b  lea     rcx, [rbp+arg_8]
0x180005b5f  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort,int)
0x180005b64  lea     rcx, [rbp+arg_8]
0x180005b68  cmp     eax, 0FFFFFFFFh
0x180005b6b  jnz     short loc_180005B54
0x180005b6d  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180005b72  mov     rdx, rax
0x180005b75  mov     rcx, rsi
0x180005b78  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180005b7e  mov     rcx, [rbp+arg_8]
0x180005b82  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180005b86  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180005b8b  mov     rcx, [rbp+arg_10]
0x180005b8f  test    rcx, rcx
0x180005b92  jz      short loc_180005B9A
0x180005b94  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180005b9a  mov     rdx, rsi; struct DirectUI::Element *
0x180005b9d  mov     rcx, rbx; this
0x180005ba0  call    ?DeleteShortCuts@AccessibilityCplCore@@AEAAXPEAVElement@DirectUI@@@Z; AccessibilityCplCore::DeleteShortCuts(DirectUI::Element *)
0x180005ba5  mov     ecx, [r14]
0x180005ba8  inc     r15d
0x180005bab  mov     eax, ecx
0x180005bad  and     eax, 0FFFFFFFh
0x180005bb2  cmp     r15d, eax
0x180005bb5  jb      loc_180005AA4
0x180005bbb  mov     rcx, [rbp+arg_18]
0x180005bbf  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180005bc5  add     rsp, 28h
0x180005bc9  pop     r15
0x180005bcb  pop     r14
0x180005bcd  pop     r13
0x180005bcf  pop     r12
0x180005bd1  pop     rdi
0x180005bd2  pop     rsi
0x180005bd3  pop     rbx
0x180005bd4  pop     rbp
0x180005bd5  retn
```

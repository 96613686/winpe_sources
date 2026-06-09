# Jot::CTVIWithChildrenBaseListener::OnUpdate(void)

- ea: `0x140067a60`
- end: `0x140067d9c`
- name: `?OnUpdate@CTVIWithChildrenBaseListener@Jot@@MEAA_NXZ`
- size: `828`
- prototype: `bool __fastcall(Jot::CTVIWithChildrenBaseListener *__hidden this)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140067590`
- `0x140068620`
- `0x14013b760`

## callees

- `0x1400492bc`
- `0x140049970`
- `0x140057580`
- `0x1400679b0`
- `0x1400679fc`
- `0x140067a60`
- `0x140067d9c`
- `0x1400683b4`
- `0x1400943f0`

## import_xrefs

- `onmain!?ShadowCopilotSection@Jot@@YAAEBVTriggeredFeatureGate@Optimized@AB@Mso@@XZ` at `0x140067ac3`
- `onmain!?ShadowCopilotSection@Jot@@YAAEBVTriggeredFeatureGate@Optimized@AB@Mso@@XZ` at `0x140067ac3`
- `mso40uiWin32Client!__imp_?SetLayoutPos@Element@NetUI@@QEAAJH@Z` at `0x140067d0e`
- `mso40uiWin32Client!__imp_?SetLayoutPos@Element@NetUI@@QEAAJH@Z` at `0x140067d48`
- `mso40uiWin32Client!__imp_?SetLayoutPos@Element@NetUI@@QEAAJH@Z` at `0x140067d0e`
- `mso40uiWin32Client!__imp_?SetLayoutPos@Element@NetUI@@QEAAJH@Z` at `0x140067d48`
- `mso40uiWin32Client!__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x140067cf2`
- `mso40uiWin32Client!__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x140067d2c`
- `mso40uiWin32Client!__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x140067d60`
- `mso40uiWin32Client!__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x140067cf2`
- `mso40uiWin32Client!__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x140067d2c`
- `mso40uiWin32Client!__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x140067d60`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x140067cfe`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x140067d38`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x140067d6c`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x140067cfe`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x140067d38`
- `mso40uiWin32Client!__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z` at `0x140067d6c`
- `mso40uiWin32Client!__imp_?GetChildElement@Element@NetUI@@QEBAPEAV12@H@Z` at `0x140067a91`
- `mso40uiWin32Client!__imp_?GetChildElement@Element@NetUI@@QEBAPEAV12@H@Z` at `0x140067a9c`
- `mso40uiWin32Client!__imp_?GetChildElement@Element@NetUI@@QEBAPEAV12@H@Z` at `0x140067a91`
- `mso40uiWin32Client!__imp_?GetChildElement@Element@NetUI@@QEBAPEAV12@H@Z` at `0x140067a9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall Jot::CTVIWithChildrenBaseListener::OnUpdate(Jot::CTVIWithChildrenBaseListener *this)
{
  Jot::CTVIWithChildrenBaseListener *v1; // rdi
  NetUI::Element *ChildElement; // rax
  NetUI::Element *v3; // rbx
  unsigned int Level; // eax
  int v5; // r8d
  int IndentForLevel; // eax
  const struct Mso::AB::Optimized::TriggeredFeatureGate *v7; // rax
  void (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // r9
  __int64 v9; // rcx
  char v10; // al
  char v11; // al
  bool result; // al
  int v13; // r15d
  void (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  int v17; // r14d
  char v18; // si
  __int64 v19; // rcx
  int i; // ebx
  char v21; // al
  char v22; // bl
  bool v23; // si
  bool v24; // bl
  NetUI::Element *v25; // rcx
  NetUI::Node *v26; // r14
  const struct NetUI::PropertyInfo *v27; // rax
  NetUI::Element *v28; // rcx
  NetUI::Node *v29; // r14
  const struct NetUI::PropertyInfo *v30; // rax
  NetUI::Node *v31; // rbx
  const struct NetUI::PropertyInfo *v32; // rax
  __int64 v33; // [rsp+58h] [rbp+38h] BYREF
  __int64 v34; // [rsp+60h] [rbp+40h] BYREF

  v1 = this;
  if ( *((_BYTE *)Jot::CJotApp::s_pSingletonJotApp + 320) )
  {
    this = (Jot::CTVIWithChildrenBaseListener *)*((_QWORD *)this + 15);
    if ( this )
    {
      ChildElement = NetUI::Element::GetChildElement(this, 0);
      v3 = NetUI::Element::GetChildElement(ChildElement, 0);
      Level = NetUI::TreeViewItem::GetLevel(*((NetUI::TreeViewItem **)v1 + 2));
      IndentForLevel = Jot::GetIndentForLevel(*((Jot **)v1 + 2), (struct NetUI::Element *)Level, v5);
      NetUI::Element::SetIndentBy(v3, IndentForLevel);
    }
  }
  v7 = Jot::ShadowCopilotSection(this);
  if ( (unsigned __int8)Mso::AB::Optimized::TriggeredFeatureGate::operator bool(v7) )
  {
    v8 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v1 + 8);
    v9 = 0;
    v33 = 0;
    if ( v8 )
    {
      (**v8)(v8, &GUID_0b4dcfc3_4116_4b8e_89ed_1eadf16a0f50, &v33);
      v9 = v33;
    }
    v11 = 0;
    if ( v9 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 1016LL))(v9);
      v9 = v33;
      if ( v10 )
        v11 = 1;
    }
    if ( *((_BYTE *)v1 + 142) != v11 )
      *((_BYTE *)v1 + 141) = 0;
    if ( !*((_BYTE *)v1 + 141) )
    {
      Jot::CTVIWithChildrenBaseListener::UpdateChildren(v1);
      v9 = v33;
    }
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  result = Jot::CTVIBaseListener::OnUpdate(v1);
  if ( result )
  {
    v13 = *((_DWORD *)v1 + 22);
    v14 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v1 + 8);
    v15 = 0;
    v34 = 0;
    if ( v14 )
    {
      (**v14)(v14, &GUID_99ef15d2_44f5_4292_a5f8_f7280db20074, &v34);
      v15 = v34;
    }
    v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 544LL))(v15);
    v18 = 0;
    if ( v17 > 0 )
    {
      v19 = 0;
      v33 = 0;
      for ( i = 0; i < v17; ++i )
      {
        (*(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v34 + 552LL))(v34, (unsigned int)i, &v33);
        if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v33 + 448LL))(v33)
          && !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v33 + 464LL))(v33) )
        {
          v18 = 1;
          v19 = v33;
          break;
        }
        v16 = v33;
        v19 = 0;
        v33 = 0;
        if ( v16 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          v19 = v33;
        }
      }
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v18 )
        goto LABEL_34;
    }
    if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v34 + 472LL))(v34) > 0 )
LABEL_34:
      v21 = 1;
    else
      v21 = 0;
    if ( v13 == 2 && v21 )
    {
      v22 = 1;
      LOBYTE(v16) = 1;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 8) + 144LL))(
              *((_QWORD *)v1 + 8),
              v16)
        || !*((_BYTE *)v1 + 77) )
      {
        v23 = 1;
LABEL_42:
        LOBYTE(v16) = 1;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v1 + 8) + 144LL))(
               *((_QWORD *)v1 + 8),
               v16)
          && *((_BYTE *)v1 + 77) )
        {
          v24 = 1;
LABEL_46:
          v25 = (NetUI::Element *)*((_QWORD *)v1 + 13);
          if ( v25 )
          {
            NetUI::Element::SetIsVisible(v25, v23);
            v26 = (NetUI::Node *)*((_QWORD *)v1 + 13);
            if ( v23 )
            {
              v27 = (const struct NetUI::PropertyInfo *)NetUI::Element::LayoutPosPropInfo();
              NetUI::Node::RemoveLocalValue(v26, v27);
            }
            else
            {
              NetUI::Element::SetLayoutPos(*((NetUI::Element **)v1 + 13), 1);
            }
          }
          v28 = (NetUI::Element *)*((_QWORD *)v1 + 14);
          if ( v28 )
          {
            NetUI::Element::SetIsVisible(v28, v24);
            v29 = (NetUI::Node *)*((_QWORD *)v1 + 14);
            if ( v24 )
            {
              v30 = (const struct NetUI::PropertyInfo *)NetUI::Element::LayoutPosPropInfo();
              NetUI::Node::RemoveLocalValue(v29, v30);
            }
            else
            {
              NetUI::Element::SetLayoutPos(*((NetUI::Element **)v1 + 14), 1);
            }
          }
          if ( !v23 && !v24 )
          {
            v31 = (NetUI::Node *)*((_QWORD *)v1 + 13);
            if ( v31 )
            {
              v32 = (const struct NetUI::PropertyInfo *)NetUI::Element::LayoutPosPropInfo();
              NetUI::Node::RemoveLocalValue(v31, v32);
            }
          }
          if ( v34 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          return 1;
        }
LABEL_45:
        v24 = 0;
        goto LABEL_46;
      }
    }
    else
    {
      v22 = 0;
    }
    v23 = 0;
    if ( !v22 )
      goto LABEL_45;
    goto LABEL_42;
  }
  return result;
}

```

## disassembly

```asm
0x140067a60  mov     [rsp-28h+arg_0], rbx
0x140067a65  push    rbp
0x140067a66  push    rsi
0x140067a67  push    rdi
0x140067a68  push    r14
0x140067a6a  push    r15
0x140067a6c  mov     rbp, rsp
0x140067a6f  sub     rsp, 20h
0x140067a73  mov     rdi, rcx
0x140067a76  mov     rax, cs:?s_pSingletonJotApp@CJotApp@Jot@@0PEAV12@EA; Jot::CJotApp * Jot::CJotApp::s_pSingletonJotApp
0x140067a7d  cmp     byte ptr [rax+140h], 0
0x140067a84  jz      short loc_140067AC3
0x140067a86  mov     rcx, [rcx+78h]
0x140067a8a  test    rcx, rcx
0x140067a8d  jz      short loc_140067AC3
0x140067a8f  xor     edx, edx
0x140067a91  call    cs:__imp_?GetChildElement@Element@NetUI@@QEBAPEAV12@H@Z; NetUI::Element::GetChildElement(int)
0x140067a97  xor     edx, edx
0x140067a99  mov     rcx, rax
0x140067a9c  call    cs:__imp_?GetChildElement@Element@NetUI@@QEBAPEAV12@H@Z; NetUI::Element::GetChildElement(int)
0x140067aa2  mov     rbx, rax
0x140067aa5  mov     rcx, [rdi+10h]; this
0x140067aa9  call    ?GetLevel@TreeViewItem@NetUI@@QEBAHXZ; NetUI::TreeViewItem::GetLevel(void)
0x140067aae  mov     edx, eax; struct NetUI::Element *
0x140067ab0  mov     rcx, [rdi+10h]; this
0x140067ab4  call    ?GetIndentForLevel@Jot@@YAHPEAVElement@NetUI@@H@Z; Jot::GetIndentForLevel(NetUI::Element *,int)
0x140067ab9  mov     edx, eax; int
0x140067abb  mov     rcx, rbx; this
0x140067abe  call    ?SetIndentBy@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetIndentBy(int)
0x140067ac3  call    cs:__imp_?ShadowCopilotSection@Jot@@YAAEBVTriggeredFeatureGate@Optimized@AB@Mso@@XZ; Jot::ShadowCopilotSection(void)
0x140067ac9  mov     rcx, rax
0x140067acc  call    ??BTriggeredFeatureGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::TriggeredFeatureGate::operator bool(void)
0x140067ad1  test    al, al
0x140067ad3  jz      loc_140067B5F
0x140067ad9  mov     r9, [rdi+40h]
0x140067add  xor     ecx, ecx
0x140067adf  mov     [rbp+arg_8], rcx
0x140067ae3  test    r9, r9
0x140067ae6  jz      short loc_140067B06
0x140067ae8  mov     rax, [r9]
0x140067aeb  lea     r8, [rbp+arg_8]
0x140067aef  lea     rdx, _GUID_0b4dcfc3_4116_4b8e_89ed_1eadf16a0f50
0x140067af6  mov     rcx, r9
0x140067af9  mov     rax, [rax]
0x140067afc  call    cs:__guard_dispatch_icall_fptr
0x140067b02  mov     rcx, [rbp+arg_8]
0x140067b06  test    rcx, rcx
0x140067b09  jz      short loc_140067B27
0x140067b0b  mov     rax, [rcx]
0x140067b0e  mov     rax, [rax+3F8h]
0x140067b15  call    cs:__guard_dispatch_icall_fptr
0x140067b1b  mov     rcx, [rbp+arg_8]
0x140067b1f  test    al, al
0x140067b21  jz      short loc_140067B27
0x140067b23  mov     al, 1
0x140067b25  jmp     short loc_140067B29
0x140067b27  xor     al, al
0x140067b29  cmp     [rdi+8Eh], al
0x140067b2f  jz      short loc_140067B38
0x140067b31  mov     byte ptr [rdi+8Dh], 0
0x140067b38  cmp     byte ptr [rdi+8Dh], 0
0x140067b3f  jnz     short loc_140067B4D
0x140067b41  mov     rcx, rdi; this
0x140067b44  call    ?UpdateChildren@CTVIWithChildrenBaseListener@Jot@@IEAAXXZ; Jot::CTVIWithChildrenBaseListener::UpdateChildren(void)
0x140067b49  mov     rcx, [rbp+arg_8]
0x140067b4d  test    rcx, rcx
0x140067b50  jz      short loc_140067B5F
0x140067b52  mov     rax, [rcx]
0x140067b55  mov     rax, [rax+10h]
0x140067b59  call    cs:__guard_dispatch_icall_fptr
0x140067b5f  mov     rcx, rdi; this
0x140067b62  call    ?OnUpdate@CTVIBaseListener@Jot@@MEAA_NXZ; Jot::CTVIBaseListener::OnUpdate(void)
0x140067b67  test    al, al
0x140067b69  jz      loc_140067D8B
0x140067b6f  mov     r15d, [rdi+58h]
0x140067b73  mov     r9, [rdi+40h]
0x140067b77  xor     ecx, ecx
0x140067b79  mov     [rbp+arg_10], rcx
0x140067b7d  test    r9, r9
0x140067b80  jz      short loc_140067BA0
0x140067b82  mov     rax, [r9]
0x140067b85  lea     r8, [rbp+arg_10]
0x140067b89  lea     rdx, _GUID_99ef15d2_44f5_4292_a5f8_f7280db20074
0x140067b90  mov     rcx, r9
0x140067b93  mov     rax, [rax]
0x140067b96  call    cs:__guard_dispatch_icall_fptr
0x140067b9c  mov     rcx, [rbp+arg_10]
0x140067ba0  mov     rax, [rcx]
0x140067ba3  mov     rax, [rax+220h]
0x140067baa  call    cs:__guard_dispatch_icall_fptr
0x140067bb0  mov     r14d, eax
0x140067bb3  xor     sil, sil
0x140067bb6  test    eax, eax
0x140067bb8  jle     loc_140067C5A
0x140067bbe  xor     ecx, ecx
0x140067bc0  mov     [rbp+arg_8], rcx
0x140067bc4  xor     ebx, ebx
0x140067bc6  cmp     ebx, r14d
0x140067bc9  jge     short loc_140067C43
0x140067bcb  mov     rcx, [rbp+arg_10]
0x140067bcf  mov     rax, [rcx]
0x140067bd2  lea     r8, [rbp+arg_8]
0x140067bd6  mov     edx, ebx
0x140067bd8  mov     rax, [rax+228h]
0x140067bdf  call    cs:__guard_dispatch_icall_fptr
0x140067be5  mov     rcx, [rbp+arg_8]
0x140067be9  mov     rax, [rcx]
0x140067bec  mov     rax, [rax+1C0h]
0x140067bf3  call    cs:__guard_dispatch_icall_fptr
0x140067bf9  test    al, al
0x140067bfb  jnz     short loc_140067C15
0x140067bfd  mov     rcx, [rbp+arg_8]
0x140067c01  mov     rax, [rcx]
0x140067c04  mov     rax, [rax+1D0h]
0x140067c0b  call    cs:__guard_dispatch_icall_fptr
0x140067c11  test    al, al
0x140067c13  jz      short loc_140067C3C
0x140067c15  mov     rdx, [rbp+arg_8]
0x140067c19  xor     ecx, ecx
0x140067c1b  mov     [rbp+arg_8], rcx
0x140067c1f  test    rdx, rdx
0x140067c22  jz      short loc_140067C38
0x140067c24  mov     rax, [rdx]
0x140067c27  mov     rcx, rdx
0x140067c2a  mov     rax, [rax+10h]
0x140067c2e  call    cs:__guard_dispatch_icall_fptr
0x140067c34  mov     rcx, [rbp+arg_8]
0x140067c38  inc     ebx
0x140067c3a  jmp     short loc_140067BC6
0x140067c3c  mov     sil, 1
0x140067c3f  mov     rcx, [rbp+arg_8]
0x140067c43  test    rcx, rcx
0x140067c46  jz      short loc_140067C55
0x140067c48  mov     rax, [rcx]
0x140067c4b  mov     rax, [rax+10h]
0x140067c4f  call    cs:__guard_dispatch_icall_fptr
0x140067c55  test    sil, sil
0x140067c58  jnz     short loc_140067C76
0x140067c5a  mov     rcx, [rbp+arg_10]
0x140067c5e  mov     rax, [rcx]
0x140067c61  mov     rax, [rax+1D8h]
0x140067c68  call    cs:__guard_dispatch_icall_fptr
0x140067c6e  test    eax, eax
0x140067c70  jg      short loc_140067C76
0x140067c72  xor     al, al
0x140067c74  jmp     short loc_140067C78
0x140067c76  mov     al, 1
0x140067c78  cmp     r15d, 2
0x140067c7c  jnz     short loc_140067CA9
0x140067c7e  test    al, al
0x140067c80  jz      short loc_140067CA9
0x140067c82  mov     bl, 1
0x140067c84  mov     rcx, [rdi+40h]
0x140067c88  mov     rax, [rcx]
0x140067c8b  mov     dl, bl
0x140067c8d  mov     rax, [rax+90h]
0x140067c94  call    cs:__guard_dispatch_icall_fptr
0x140067c9a  test    al, al
0x140067c9c  jz      short loc_140067CA4
0x140067c9e  cmp     byte ptr [rdi+4Dh], 0
0x140067ca2  jnz     short loc_140067CAB
0x140067ca4  mov     sil, bl
0x140067ca7  jmp     short loc_140067CB2
0x140067ca9  xor     bl, bl
0x140067cab  xor     sil, sil
0x140067cae  test    bl, bl
0x140067cb0  jz      short loc_140067CD6
0x140067cb2  mov     rcx, [rdi+40h]
0x140067cb6  mov     rax, [rcx]
0x140067cb9  mov     dl, 1
0x140067cbb  mov     rax, [rax+90h]
0x140067cc2  call    cs:__guard_dispatch_icall_fptr
0x140067cc8  test    al, al
0x140067cca  jz      short loc_140067CD6
0x140067ccc  cmp     byte ptr [rdi+4Dh], 0
0x140067cd0  jz      short loc_140067CD6
0x140067cd2  mov     bl, 1
0x140067cd4  jmp     short loc_140067CD8
0x140067cd6  xor     bl, bl
0x140067cd8  mov     rcx, [rdi+68h]; this
0x140067cdc  test    rcx, rcx
0x140067cdf  jz      short loc_140067D14
0x140067ce1  mov     dl, sil; bool
0x140067ce4  call    ?SetIsVisible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsVisible(bool)
0x140067ce9  mov     r14, [rdi+68h]
0x140067ced  test    sil, sil
0x140067cf0  jz      short loc_140067D06
0x140067cf2  call    cs:__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::LayoutPosPropInfo(void)
0x140067cf8  mov     rdx, rax
0x140067cfb  mov     rcx, r14
0x140067cfe  call    cs:__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z; NetUI::Node::RemoveLocalValue(NetUI::PropertyInfo const *)
0x140067d04  jmp     short loc_140067D14
0x140067d06  mov     edx, 1
0x140067d0b  mov     rcx, r14
0x140067d0e  call    cs:__imp_?SetLayoutPos@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetLayoutPos(int)
0x140067d14  mov     rcx, [rdi+70h]; this
0x140067d18  test    rcx, rcx
0x140067d1b  jz      short loc_140067D4E
0x140067d1d  mov     dl, bl; bool
0x140067d1f  call    ?SetIsVisible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsVisible(bool)
0x140067d24  mov     r14, [rdi+70h]
0x140067d28  test    bl, bl
0x140067d2a  jz      short loc_140067D40
0x140067d2c  call    cs:__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::LayoutPosPropInfo(void)
0x140067d32  mov     rdx, rax
0x140067d35  mov     rcx, r14
0x140067d38  call    cs:__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z; NetUI::Node::RemoveLocalValue(NetUI::PropertyInfo const *)
0x140067d3e  jmp     short loc_140067D4E
0x140067d40  mov     edx, 1
0x140067d45  mov     rcx, r14
0x140067d48  call    cs:__imp_?SetLayoutPos@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetLayoutPos(int)
0x140067d4e  test    sil, sil
0x140067d51  jnz     short loc_140067D73
0x140067d53  test    bl, bl
0x140067d55  jnz     short loc_140067D73
0x140067d57  mov     rbx, [rdi+68h]
0x140067d5b  test    rbx, rbx
0x140067d5e  jz      short loc_140067D73
0x140067d60  call    cs:__imp_?LayoutPosPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::LayoutPosPropInfo(void)
0x140067d66  mov     rdx, rax
0x140067d69  mov     rcx, rbx
0x140067d6c  call    cs:__imp_?RemoveLocalValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@@Z; NetUI::Node::RemoveLocalValue(NetUI::PropertyInfo const *)
0x140067d72  nop
0x140067d73  mov     rcx, [rbp+arg_10]
0x140067d77  test    rcx, rcx
0x140067d7a  jz      short loc_140067D89
0x140067d7c  mov     rdx, [rcx]
0x140067d7f  mov     rax, [rdx+10h]
0x140067d83  call    cs:__guard_dispatch_icall_fptr
0x140067d89  mov     al, 1
0x140067d8b  mov     rbx, [rsp+20h+arg_0]
0x140067d90  add     rsp, 20h
0x140067d94  pop     r15
0x140067d96  pop     r14
0x140067d98  pop     rdi
0x140067d99  pop     rsi
0x140067d9a  pop     rbp
0x140067d9b  retn
```

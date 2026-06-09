# CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(CodeIntegrity::Management::AuthorizationToken &&)

- ea: `0x1800185a8`
- end: `0x180018717`
- name: `??0AuthorizationToken@Management@CodeIntegrity@@QEAA@$$QEAV012@@Z`
- size: `367`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013660`
- `0x180018774`
- `0x180018834`
- `0x18001b398`

## callees

- `0x180010cdc`
- `0x180016780`
- `0x180017170`
- `0x1800185a8`

## pseudocode

```c
__int64 __fastcall CodeIntegrity::Management::AuthorizationToken::AuthorizationToken(__int64 a1, __int64 a2)
{
  __int64 *v4; // r8
  __int64 *v5; // r11
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 *v9; // r9
  __int64 *v10; // r10
  __int64 *v11; // rdx
  __int16 v12; // cx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  char v20; // cl
  __int64 result; // rax

  CodeIntegrity::Management::detail::SbcpTokenView::SbcpTokenView(
    (CodeIntegrity::Management::detail::SbcpTokenView *)a1,
    a2 + 24,
    a2 + 56,
    a2 + 88);
  *(_QWORD *)a1 = &CodeIntegrity::Management::AuthorizationToken::`vftable';
  std::vector<_GUID>::vector<_GUID>((_QWORD *)(a1 + 136));
  std::vector<_GUID>::vector<_GUID>((_QWORD *)(a1 + 160));
  std::vector<_GUID>::vector<_GUID>((_QWORD *)(a1 + 184));
  v5 = (__int64 *)(a2 + 136);
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  if ( v4 != (__int64 *)(a2 + 136) )
  {
    v6 = *v4;
    *v4 = *v5;
    *v5 = v6;
    v7 = v4[1];
    v4[1] = *(_QWORD *)(a2 + 144);
    *(_QWORD *)(a2 + 144) = v7;
    v8 = v4[2];
    v4[2] = *(_QWORD *)(a2 + 152);
    *(_QWORD *)(a2 + 152) = v8;
  }
  std::swap<_GUID,std::default_delete<_GUID>,0>();
  std::swap<_GUID,std::default_delete<_GUID>,0>();
  v11 = (__int64 *)(a2 + 160);
  v12 = *(_WORD *)(a1 + 8);
  *(_WORD *)(a1 + 8) = *(_WORD *)(a2 + 8);
  *(_WORD *)(a2 + 8) = v12;
  if ( v10 != (__int64 *)(a2 + 160) )
  {
    v13 = *v10;
    *v10 = *v11;
    *v11 = v13;
    v14 = v10[1];
    v10[1] = *(_QWORD *)(a2 + 168);
    *(_QWORD *)(a2 + 168) = v14;
    v15 = v10[2];
    v10[2] = *(_QWORD *)(a2 + 176);
    *(_QWORD *)(a2 + 176) = v15;
  }
  v16 = (__int64 *)(a2 + 184);
  if ( v9 != (__int64 *)(a2 + 184) )
  {
    v17 = *v9;
    *v9 = *v16;
    *v16 = v17;
    v18 = v9[1];
    v9[1] = *(_QWORD *)(a2 + 192);
    *(_QWORD *)(a2 + 192) = v18;
    v19 = v9[2];
    v9[2] = *(_QWORD *)(a2 + 200);
    *(_QWORD *)(a2 + 200) = v19;
  }
  v20 = *(_BYTE *)(a1 + 224);
  *(_BYTE *)(a1 + 224) = *(_BYTE *)(a2 + 224);
  result = a1;
  *(_BYTE *)(a2 + 224) = v20;
  return result;
}

```

## disassembly

```asm
0x1800185a8  push    rbx
0x1800185aa  push    rsi
0x1800185ab  push    rdi
0x1800185ac  push    r14
0x1800185ae  sub     rsp, 28h
0x1800185b2  mov     rbx, rdx
0x1800185b5  lea     r9, [rdx+58h]
0x1800185b9  lea     r8, [rdx+38h]
0x1800185bd  mov     rdi, rcx
0x1800185c0  add     rdx, 18h
0x1800185c4  call    ??0SbcpTokenView@detail@Management@CodeIntegrity@@IEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$vector@EV?$allocator@E@std@@@5@@Z; CodeIntegrity::Management::detail::SbcpTokenView::SbcpTokenView(std::wstring const &,std::wstring const &,std::vector<uchar> const &)
0x1800185c9  lea     rax, ??_7AuthorizationToken@Management@CodeIntegrity@@6B@; const CodeIntegrity::Management::AuthorizationToken::`vftable'
0x1800185d0  lea     r8, [rdi+88h]
0x1800185d7  mov     [rdi], rax
0x1800185da  mov     rcx, r8
0x1800185dd  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800185e2  lea     r10, [rdi+0A0h]
0x1800185e9  mov     rcx, r10
0x1800185ec  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x1800185f1  lea     r9, [rdi+0B8h]
0x1800185f8  mov     rcx, r9
0x1800185fb  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180018600  lea     rsi, [rdi+0D0h]
0x180018607  lea     r11, [rbx+88h]
0x18001860e  mov     qword ptr [rsi], 0
0x180018615  lea     r14, [rdi+0D8h]
0x18001861c  mov     qword ptr [r14], 0
0x180018623  cmp     r8, r11
0x180018626  jz      short loc_180018654
0x180018628  mov     rax, [r11]
0x18001862b  mov     rcx, [r8]
0x18001862e  mov     [r8], rax
0x180018631  mov     [r11], rcx
0x180018634  mov     rax, [r11+8]
0x180018638  mov     rdx, [r8+8]
0x18001863c  mov     [r8+8], rax
0x180018640  mov     [r11+8], rdx
0x180018644  mov     rax, [r11+10h]
0x180018648  mov     rdx, [r8+10h]
0x18001864c  mov     [r8+10h], rax
0x180018650  mov     [r11+10h], rdx
0x180018654  lea     rdx, [rbx+0D0h]
0x18001865b  mov     rcx, rsi
0x18001865e  call    ??$swap@U_GUID@@U?$default_delete@U_GUID@@@std@@$0A@@std@@YAXAEAV?$unique_ptr@U_GUID@@U?$default_delete@U_GUID@@@std@@@0@0@Z; std::swap<_GUID,std::default_delete<_GUID>,0>(std::unique_ptr<_GUID> &,std::unique_ptr<_GUID> &)
0x180018663  lea     rdx, [rbx+0D8h]
0x18001866a  mov     rcx, r14
0x18001866d  call    ??$swap@U_GUID@@U?$default_delete@U_GUID@@@std@@$0A@@std@@YAXAEAV?$unique_ptr@U_GUID@@U?$default_delete@U_GUID@@@std@@@0@0@Z; std::swap<_GUID,std::default_delete<_GUID>,0>(std::unique_ptr<_GUID> &,std::unique_ptr<_GUID> &)
0x180018672  movzx   eax, word ptr [rbx+8]
0x180018676  lea     rdx, [rbx+0A0h]
0x18001867d  movzx   ecx, word ptr [rdi+8]
0x180018681  mov     [rdi+8], ax
0x180018685  mov     [rbx+8], cx
0x180018689  cmp     r10, rdx
0x18001868c  jz      short loc_1800186BA
0x18001868e  mov     rax, [rdx]
0x180018691  mov     rcx, [r10]
0x180018694  mov     [r10], rax
0x180018697  mov     [rdx], rcx
0x18001869a  mov     rax, [rdx+8]
0x18001869e  mov     rcx, [r10+8]
0x1800186a2  mov     [r10+8], rax
0x1800186a6  mov     [rdx+8], rcx
0x1800186aa  mov     rax, [rdx+10h]
0x1800186ae  mov     rcx, [r10+10h]
0x1800186b2  mov     [r10+10h], rax
0x1800186b6  mov     [rdx+10h], rcx
0x1800186ba  lea     rdx, [rbx+0B8h]
0x1800186c1  cmp     r9, rdx
0x1800186c4  jz      short loc_1800186F2
0x1800186c6  mov     rax, [rdx]
0x1800186c9  mov     rcx, [r9]
0x1800186cc  mov     [r9], rax
0x1800186cf  mov     [rdx], rcx
0x1800186d2  mov     rax, [rdx+8]
0x1800186d6  mov     rcx, [r9+8]
0x1800186da  mov     [r9+8], rax
0x1800186de  mov     [rdx+8], rcx
0x1800186e2  mov     rax, [rdx+10h]
0x1800186e6  mov     rcx, [r9+10h]
0x1800186ea  mov     [r9+10h], rax
0x1800186ee  mov     [rdx+10h], rcx
0x1800186f2  mov     al, [rbx+0E0h]
0x1800186f8  mov     cl, [rdi+0E0h]
0x1800186fe  mov     [rdi+0E0h], al
0x180018704  mov     rax, rdi
0x180018707  mov     [rbx+0E0h], cl
0x18001870d  add     rsp, 28h
0x180018711  pop     r14
0x180018713  pop     rdi
0x180018714  pop     rsi
0x180018715  pop     rbx
0x180018716  retn
```

# Jot::NavigationUI::UpdateFluentEDPIcon(NetUI::Element &,Jot::IUINotebook &,uchar,NetUI::FontIconSize)

- ea: `0x140051330`
- end: `0x1400516fd`
- name: `?UpdateFluentEDPIcon@NavigationUI@Jot@@YAXAEAVElement@NetUI@@AEAUIUINotebook@2@EW4FontIconSize@4@@Z`
- size: `973`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `file_ops, installer_update`

## callers

- `0x14004dcf0`
- `0x14005a70c`
- `0x140068620`
- `0x1400753cc`

## callees

- `0x140001180`
- `0x140019348`
- `0x140020ab0`
- `0x1400218f4`
- `0x1400229b4`
- `0x14002a850`
- `0x1400488d0`
- `0x14004921c`
- `0x140049304`
- `0x140049350`
- `0x140049374`
- `0x140049a30`
- `0x140051330`
- `0x140051700`
- `0x140056ac0`
- `0x140057580`
- `0x14006ba94`

## import_xrefs

- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x1400514e7`
- `mso40uiWin32Client!__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z` at `0x1400514e7`
- `mso40uiWin32Client!__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z` at `0x14005155b`
- `mso40uiWin32Client!__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z` at `0x14005157f`
- `mso40uiWin32Client!__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z` at `0x14005155b`
- `mso40uiWin32Client!__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z` at `0x14005157f`
- `mso40uiWin32Client!__imp_?SetValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@PEAVValue@2@@Z` at `0x1400515d2`
- `mso40uiWin32Client!__imp_?SetValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@PEAVValue@2@@Z` at `0x140051622`
- `mso40uiWin32Client!__imp_?SetValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@PEAVValue@2@@Z` at `0x1400515d2`
- `mso40uiWin32Client!__imp_?SetValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@PEAVValue@2@@Z` at `0x140051622`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x140051535`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14005169b`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400516ab`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x140051535`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x14005169b`
- `mso40uiWin32Client!__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400516ab`
- `mso40uiWin32Client!__imp_?ContentPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x1400515c1`
- `mso40uiWin32Client!__imp_?ContentPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x140051611`
- `mso40uiWin32Client!__imp_?ContentPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x1400515c1`
- `mso40uiWin32Client!__imp_?ContentPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ` at `0x140051611`
- `mso40uiWin32Client!__imp_?SetDirection@Element@NetUI@@QEAAJH@Z` at `0x140051527`
- `mso40uiWin32Client!__imp_?SetDirection@Element@NetUI@@QEAAJH@Z` at `0x140051527`
- `mso40uiWin32Client!__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z` at `0x140051465`
- `mso40uiWin32Client!__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z` at `0x140051465`
- `mso40uiWin32Client!__imp_?Remove@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400516f1`
- `mso40uiWin32Client!__imp_?Remove@Node@NetUI@@QEAAJPEAV12@@Z` at `0x1400516f1`
- `mso40uiWin32Client!__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z` at `0x1400514c8`
- `mso40uiWin32Client!__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z` at `0x1400514c8`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x1400515a3`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x1400515f3`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x1400515a3`
- `mso40uiWin32Client!__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z` at `0x1400515f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall Jot::NavigationUI::UpdateFluentEDPIcon(NetUI::Node *a1, __int64 a2, char a3, __int8 a4)
{
  __m128i si128; // xmm9
  const wchar_t *v9; // xmm8_8
  __m128i *v10; // rax
  __m128i v11; // xmm6
  __m128i v12; // xmm7
  const wchar_t *v13; // rdx
  const wchar_t *v14; // r9
  bool v15; // bl
  NetUI::Node *NodeSelfOrDescendent; // rax
  struct Node *v17; // rax
  NetUI::BaseValue *v18; // rax
  struct NetUI::Value *v19; // rdi
  NetUI::BaseValue *v20; // rax
  struct NetUI::Value *v21; // rbx
  const struct NetUI::PropertyInfo *v22; // rax
  const struct NetUI::PropertyInfo *v23; // rax
  __int64 v24; // rax
  unsigned int v25; // edi
  __int64 v26; // rax
  unsigned int v27; // ebx
  NetUI::Node *v29; // [rsp+28h] [rbp-99h] BYREF
  NetUI::Element *v30; // [rsp+30h] [rbp-91h] BYREF
  NetUI::Element *v31; // [rsp+38h] [rbp-89h] BYREF
  NetUI::BaseValue *v32; // [rsp+40h] [rbp-81h] BYREF
  NetUI::BaseValue *v33; // [rsp+48h] [rbp-79h] BYREF
  char v34[32]; // [rsp+50h] [rbp-71h] BYREF
  __m128i v35; // [rsp+70h] [rbp-51h] BYREF
  __m128i v36; // [rsp+80h] [rbp-41h]
  _OWORD v37[2]; // [rsp+90h] [rbp-31h] BYREF

  v35 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v36 = si128;
  v35.m128i_i16[0] = 0;
  v9 = (const wchar_t *)v35.m128i_i64[0];
  v37[0] = v35;
  v37[1] = si128;
  std::wstring::~wstring(&v35);
  v10 = (__m128i *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a2 + 408LL))(a2, v34);
  v11 = *v10;
  v35 = *v10;
  v12 = v10[1];
  v36 = v12;
  v10->m128i_i16[0] = 0;
  v10[1].m128i_i64[0] = 0;
  v10[1].m128i_i64[1] = 7;
  std::wstring::~wstring(v10);
  v13 = (const wchar_t *)v37;
  if ( _mm_srli_si128(si128, 8).m128i_u64[0] > 7 )
    v13 = v9;
  v14 = (const wchar_t *)&v35;
  if ( _mm_srli_si128(v12, 8).m128i_u64[0] > 7 )
    v14 = (const wchar_t *)v11.m128i_i64[0];
  if ( v12.m128i_i64[0] == si128.m128i_i64[0] )
  {
    if ( v12.m128i_i64[0] )
      v15 = wmemcmp(v14, v13, v12.m128i_u64[0]) == 0;
    else
      v15 = 1;
  }
  else
  {
    v15 = 0;
  }
  std::wstring::~wstring(&v35);
  std::wstring::~wstring(v37);
  if ( a1 )
  {
    NodeSelfOrDescendent = (NetUI::Node *)NetUI::Node::FindNodeSelfOrDescendent(a1, 0xF48u);
    v17 = (struct Node *)NetUI::nui_control_cast<NetUI::Element>(NodeSelfOrDescendent);
  }
  else
  {
    v17 = 0;
  }
  if ( v15 )
  {
    if ( v17 )
      LODWORD(v17) = NetUI::Node::Remove(a1, v17);
  }
  else if ( !v17 )
  {
    v29 = 0;
    NetUI::Element::Create(0, &v29);
    NetUI::Node::SetID(v29, 0xF48u);
    NetUI::Element::SetLayout(v29, 6);
    NetUI::Element::SetExpandToFillHoriz(v29, 1);
    NetUI::Element::SetExpandToFillVert(v29, 1);
    NetUI::Element::SetBackgroundColor(v29, 0);
    NetUI::Element::SetAlignChildren(v29, 6);
    NetUI::Element::SetDirection(v29, 0);
    NetUI::Node::Add(a1, (struct Node *)v29);
    v35.m128i_i8[1] = -1;
    v35.m128i_i32[1] = 2143289344;
    v36.m128i_i64[0] = 0;
    v35.m128i_i8[0] = a4;
    v35.m128i_i8[8] = 1;
    v18 = (NetUI::BaseValue *)NetUI::Value::CreateGraphicIcon(9038, &v35);
    v19 = v18;
    v32 = v18;
    if ( v18 )
      NetUI::BaseValue::AddRef(v18);
    v20 = (NetUI::BaseValue *)NetUI::Value::CreateGraphicIcon(9041, &v35);
    v21 = v20;
    v33 = v20;
    if ( v20 )
      NetUI::BaseValue::AddRef(v20);
    v31 = 0;
    NetUI::Image::Create(&v31);
    NetUI::Element::SetBackgroundColor(v31, 0);
    NetUI::Element::SetIsAccessible(v31, 0);
    v22 = (const struct NetUI::PropertyInfo *)NetUI::Element::ContentPropInfo();
    NetUI::Node::SetValue(v31, v22, v21);
    NetUI::Node::SetStyleClass(v31, L"ThemedIconImage");
    v30 = 0;
    NetUI::Image::Create(&v30);
    NetUI::Element::SetBackgroundColor(v30, 0);
    NetUI::Element::SetIsAccessible(v30, 0);
    v23 = (const struct NetUI::PropertyInfo *)NetUI::Element::ContentPropInfo();
    NetUI::Node::SetValue(v30, v23, v19);
    NetUI::Node::SetStyleClass(v30, L"ThemedIconMaskImage");
    if ( a3 )
    {
      v24 = ONColor::OneNoteNav_FluentColors_PrimaryBackgroundPalette();
      v25 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 16LL))(v24, 0);
      v26 = ONColor::OneNoteNav_FluentColors_PrimaryBackgroundPalette();
      v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 16LL))(v26, 6);
      NetUI::Element::SetForegroundColor(v30, v25);
      NetUI::Element::SetForegroundColor(v31, v27);
    }
    NetUI::Node::Add(v29, (struct Node *)v30);
    NetUI::Node::Add(v29, (struct Node *)v31);
    Mso::TCntPtr<NetUI::Value>::Clear(&v33);
    LODWORD(v17) = Mso::TCntPtr<NetUI::Value>::Clear(&v32);
  }
  return (int)v17;
}

```

## disassembly

```asm
0x140051330  mov     rax, rsp
0x140051333  mov     [rax+18h], rbx
0x140051337  push    rbp
0x140051338  push    rsi
0x140051339  push    rdi
0x14005133a  push    r14
0x14005133c  push    r15
0x14005133e  lea     rbp, [rax-5Fh]
0x140051342  sub     rsp, 0F0h
0x140051349  movaps  xmmword ptr [rax-38h], xmm6
0x14005134d  movaps  xmmword ptr [rax-48h], xmm7
0x140051351  movaps  xmmword ptr [rax-58h], xmm8
0x140051356  movaps  xmmword ptr [rax-68h], xmm9
0x14005135b  mov     rax, cs:__security_cookie
0x140051362  xor     rax, rsp
0x140051365  mov     [rbp+57h+var_68], rax
0x140051369  mov     sil, r9b
0x14005136c  mov     r14b, r8b
0x14005136f  mov     rbx, rdx
0x140051372  mov     rdi, rcx
0x140051375  xorps   xmm0, xmm0
0x140051378  movups  [rbp+57h+var_A8], xmm0
0x14005137c  movdqa  xmm9, cs:__xmm@00000000000000070000000000000000
0x140051385  movdqu  [rbp+57h+var_98], xmm9
0x14005138b  xor     r15d, r15d
0x14005138e  mov     word ptr [rbp+57h+var_A8], r15w
0x140051393  movups  xmm8, [rbp+57h+var_A8]
0x140051398  movups  [rbp+57h+var_88], xmm8
0x14005139d  movups  [rbp+57h+var_78], xmm9
0x1400513a2  lea     rcx, [rbp+57h+var_A8]; void *
0x1400513a6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400513ab  mov     rax, [rbx]
0x1400513ae  lea     rdx, [rbp+57h+var_C8]
0x1400513b2  mov     rcx, rbx
0x1400513b5  mov     rax, [rax+198h]
0x1400513bc  call    cs:__guard_dispatch_icall_fptr
0x1400513c2  movups  xmm6, xmmword ptr [rax]
0x1400513c5  movups  [rbp+57h+var_A8], xmm6
0x1400513c9  movups  xmm7, xmmword ptr [rax+10h]
0x1400513cd  movups  [rbp+57h+var_98], xmm7
0x1400513d1  mov     [rax], r15w
0x1400513d5  mov     [rax+10h], r15
0x1400513d9  mov     qword ptr [rax+18h], 7
0x1400513e1  mov     rcx, rax; void *
0x1400513e4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400513e9  lea     rdx, [rbp+57h+var_88]
0x1400513ed  movq    rcx, xmm8
0x1400513f2  movdqa  xmm0, xmm9
0x1400513f7  psrldq  xmm0, 8
0x1400513fc  movq    rax, xmm0
0x140051401  cmp     rax, 7
0x140051405  cmova   rdx, rcx; S2
0x140051409  movq    r8, xmm7; N
0x14005140e  lea     r9, [rbp+57h+var_A8]
0x140051412  movq    rcx, xmm6
0x140051417  psrldq  xmm7, 8
0x14005141c  movq    rax, xmm7
0x140051421  cmp     rax, 7
0x140051425  cmova   r9, rcx
0x140051429  movq    rax, xmm9
0x14005142e  cmp     r8, rax
0x140051431  jnz     loc_1400516E3
0x140051437  test    r8, r8
0x14005143a  jnz     loc_1400516D1
0x140051440  mov     bl, 1
0x140051442  lea     rcx, [rbp+57h+var_A8]; void *
0x140051446  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005144b  lea     rcx, [rbp+57h+var_88]; void *
0x14005144f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051454  test    rdi, rdi
0x140051457  jz      loc_1400516C9
0x14005145d  mov     edx, 0F48h
0x140051462  mov     rcx, rdi
0x140051465  call    cs:__imp_?FindNodeSelfOrDescendent@Node@NetUI@@QEBAPEBV12@G@Z; NetUI::Node::FindNodeSelfOrDescendent(ushort)
0x14005146b  mov     rcx, rax; this
0x14005146e  call    ??$nui_control_cast@VElement@NetUI@@@NetUI@@YAPEBVElement@0@PEBVNode@0@@Z; NetUI::nui_control_cast<NetUI::Element>(NetUI::Node const *)
0x140051473  test    bl, bl
0x140051475  jz      short loc_1400514B7
0x140051477  test    rax, rax
0x14005147a  jnz     loc_1400516EB
0x140051480  mov     rcx, [rbp+57h+var_68]
0x140051484  xor     rcx, rsp; StackCookie
0x140051487  call    __security_check_cookie
0x14005148c  lea     r11, [rsp+110h+var_20]
0x140051494  mov     rbx, [r11+40h]
0x140051498  movaps  xmm6, xmmword ptr [r11-10h]
0x14005149d  movaps  xmm7, xmmword ptr [r11-20h]
0x1400514a2  movaps  xmm8, xmmword ptr [r11-30h]
0x1400514a7  movaps  xmm9, xmmword ptr [r11-40h]
0x1400514ac  mov     rsp, r11
0x1400514af  pop     r15
0x1400514b1  pop     r14
0x1400514b3  pop     rdi
0x1400514b4  pop     rsi
0x1400514b5  pop     rbp
0x1400514b6  retn
0x1400514b7  test    rax, rax
0x1400514ba  jnz     short loc_140051480
0x1400514bc  mov     [rsp+110h+var_F0], r15
0x1400514c1  lea     rdx, [rsp+110h+var_F0]
0x1400514c6  xor     ecx, ecx
0x1400514c8  call    cs:__imp_?Create@Element@NetUI@@SAJIPEAPEAV12@@Z; NetUI::Element::Create(uint,NetUI::Element * *)
0x1400514ce  mov     edx, 0F48h; unsigned int
0x1400514d3  mov     rcx, [rsp+110h+var_F0]; this
0x1400514d8  call    ?SetID@Node@NetUI@@QEAAJI@Z; NetUI::Node::SetID(uint)
0x1400514dd  mov     edx, 6
0x1400514e2  mov     rcx, [rsp+110h+var_F0]
0x1400514e7  call    cs:__imp_?SetLayout@Element@NetUI@@QEAAJW4DALLayoutType@2@@Z; NetUI::Element::SetLayout(NetUI::DALLayoutType)
0x1400514ed  mov     dl, 1; bool
0x1400514ef  mov     rcx, [rsp+110h+var_F0]; this
0x1400514f4  call    ?SetExpandToFillHoriz@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillHoriz(bool)
0x1400514f9  mov     dl, 1; bool
0x1400514fb  mov     rcx, [rsp+110h+var_F0]; this
0x140051500  call    ?SetExpandToFillVert@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetExpandToFillVert(bool)
0x140051505  xor     edx, edx; unsigned int
0x140051507  mov     rcx, [rsp+110h+var_F0]; this
0x14005150c  call    ?SetBackgroundColor@Element@NetUI@@QEAAJK@Z; NetUI::Element::SetBackgroundColor(ulong)
0x140051511  mov     edx, 6; int
0x140051516  mov     rcx, [rsp+110h+var_F0]; this
0x14005151b  call    ?SetAlignChildren@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetAlignChildren(int)
0x140051520  xor     edx, edx
0x140051522  mov     rcx, [rsp+110h+var_F0]
0x140051527  call    cs:__imp_?SetDirection@Element@NetUI@@QEAAJH@Z; NetUI::Element::SetDirection(int)
0x14005152d  mov     rdx, [rsp+110h+var_F0]
0x140051532  mov     rcx, rdi
0x140051535  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x14005153b  mov     byte ptr [rbp+57h+var_A8+1], 0FFh
0x14005153f  mov     dword ptr [rbp+57h+var_A8+4], 7FC00000h
0x140051546  mov     qword ptr [rbp+57h+var_98], r15
0x14005154a  mov     byte ptr [rbp+57h+var_A8], sil
0x14005154e  mov     byte ptr [rbp+57h+var_A8+8], 1
0x140051552  lea     rdx, [rbp+57h+var_A8]
0x140051556  mov     ecx, 234Eh
0x14005155b  call    cs:__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z; NetUI::Value::CreateGraphicIcon(Mso::IconId,NetUI::CreateIconParams const &)
0x140051561  mov     rdi, rax
0x140051564  mov     [rsp+110h+var_D8], rax
0x140051569  test    rax, rax
0x14005156c  jz      short loc_140051576
0x14005156e  mov     rcx, rax; this
0x140051571  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x140051576  lea     rdx, [rbp+57h+var_A8]
0x14005157a  mov     ecx, 2351h
0x14005157f  call    cs:__imp_?CreateGraphicIcon@Value@NetUI@@SAPEAV12@W4IconId@Mso@@AEBUCreateIconParams@2@@Z; NetUI::Value::CreateGraphicIcon(Mso::IconId,NetUI::CreateIconParams const &)
0x140051585  mov     rbx, rax
0x140051588  mov     [rbp+57h+var_D0], rax
0x14005158c  test    rax, rax
0x14005158f  jz      short loc_140051599
0x140051591  mov     rcx, rax; this
0x140051594  call    ?AddRef@BaseValue@NetUI@@QEAAXXZ; NetUI::BaseValue::AddRef(void)
0x140051599  mov     [rsp+110h+var_E0], r15
0x14005159e  lea     rcx, [rsp+110h+var_E0]
0x1400515a3  call    cs:__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::Image::Create(NetUI::Element * *)
0x1400515a9  xor     edx, edx; unsigned int
0x1400515ab  mov     rcx, [rsp+110h+var_E0]; this
0x1400515b0  call    ?SetBackgroundColor@Element@NetUI@@QEAAJK@Z; NetUI::Element::SetBackgroundColor(ulong)
0x1400515b5  xor     edx, edx; bool
0x1400515b7  mov     rcx, [rsp+110h+var_E0]; this
0x1400515bc  call    ?SetIsAccessible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsAccessible(bool)
0x1400515c1  call    cs:__imp_?ContentPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::ContentPropInfo(void)
0x1400515c7  mov     r8, rbx
0x1400515ca  mov     rdx, rax
0x1400515cd  mov     rcx, [rsp+110h+var_E0]
0x1400515d2  call    cs:__imp_?SetValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@PEAVValue@2@@Z; NetUI::Node::SetValue(NetUI::PropertyInfo const *,NetUI::Value *)
0x1400515d8  lea     rdx, aThemediconimag; "ThemedIconImage"
0x1400515df  mov     rcx, [rsp+110h+var_E0]; this
0x1400515e4  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x1400515e9  mov     [rsp+110h+var_E8], r15
0x1400515ee  lea     rcx, [rsp+110h+var_E8]
0x1400515f3  call    cs:__imp_?Create@Image@NetUI@@SAJPEAPEAVElement@2@@Z; NetUI::Image::Create(NetUI::Element * *)
0x1400515f9  xor     edx, edx; unsigned int
0x1400515fb  mov     rcx, [rsp+110h+var_E8]; this
0x140051600  call    ?SetBackgroundColor@Element@NetUI@@QEAAJK@Z; NetUI::Element::SetBackgroundColor(ulong)
0x140051605  xor     edx, edx; bool
0x140051607  mov     rcx, [rsp+110h+var_E8]; this
0x14005160c  call    ?SetIsAccessible@Element@NetUI@@QEAAJ_N@Z; NetUI::Element::SetIsAccessible(bool)
0x140051611  call    cs:__imp_?ContentPropInfo@Element@NetUI@@SAPEBUPropertyInfo@2@XZ; NetUI::Element::ContentPropInfo(void)
0x140051617  mov     r8, rdi
0x14005161a  mov     rdx, rax
0x14005161d  mov     rcx, [rsp+110h+var_E8]
0x140051622  call    cs:__imp_?SetValue@Node@NetUI@@QEAAJPEBUPropertyInfo@2@PEAVValue@2@@Z; NetUI::Node::SetValue(NetUI::PropertyInfo const *,NetUI::Value *)
0x140051628  lea     rdx, aThemediconmask; "ThemedIconMaskImage"
0x14005162f  mov     rcx, [rsp+110h+var_E8]; this
0x140051634  call    ?SetStyleClass@Node@NetUI@@QEAAJPEB_W@Z; NetUI::Node::SetStyleClass(wchar_t const *)
0x140051639  test    r14b, r14b
0x14005163c  jz      short loc_140051691
0x14005163e  call    ?OneNoteNav_FluentColors_PrimaryBackgroundPalette@ONColor@@YAPEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@XZ; ONColor::OneNoteNav_FluentColors_PrimaryBackgroundPalette(void)
0x140051643  mov     r8, rax
0x140051646  mov     rcx, [rax]
0x140051649  mov     rax, [rcx+10h]
0x14005164d  xor     edx, edx
0x14005164f  mov     rcx, r8
0x140051652  call    cs:__guard_dispatch_icall_fptr
0x140051658  mov     edi, eax
0x14005165a  call    ?OneNoteNav_FluentColors_PrimaryBackgroundPalette@ONColor@@YAPEAU?$ITPalette@W4Swatch@UIColor@Mso@@@UIColor@Mso@@XZ; ONColor::OneNoteNav_FluentColors_PrimaryBackgroundPalette(void)
0x14005165f  mov     r8, rax
0x140051662  mov     rcx, [rax]
0x140051665  mov     rax, [rcx+10h]
0x140051669  mov     edx, 6
0x14005166e  mov     rcx, r8
0x140051671  call    cs:__guard_dispatch_icall_fptr
0x140051677  mov     ebx, eax
0x140051679  mov     edx, edi; unsigned int
0x14005167b  mov     rcx, [rsp+110h+var_E8]; this
0x140051680  call    ?SetForegroundColor@Element@NetUI@@QEAAJK@Z; NetUI::Element::SetForegroundColor(ulong)
0x140051685  mov     edx, ebx; unsigned int
0x140051687  mov     rcx, [rsp+110h+var_E0]; this
0x14005168c  call    ?SetForegroundColor@Element@NetUI@@QEAAJK@Z; NetUI::Element::SetForegroundColor(ulong)
0x140051691  mov     rdx, [rsp+110h+var_E8]
0x140051696  mov     rcx, [rsp+110h+var_F0]
0x14005169b  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1400516a1  mov     rdx, [rsp+110h+var_E0]
0x1400516a6  mov     rcx, [rsp+110h+var_F0]
0x1400516ab  call    cs:__imp_?Add@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Add(NetUI::Node *)
0x1400516b1  lea     rcx, [rbp+57h+var_D0]
0x1400516b5  call    ?Clear@?$TCntPtr@VValue@NetUI@@@Mso@@QEAAXXZ; Mso::TCntPtr<NetUI::Value>::Clear(void)
0x1400516ba  lea     rcx, [rsp+110h+var_D8]
0x1400516bf  call    ?Clear@?$TCntPtr@VValue@NetUI@@@Mso@@QEAAXXZ; Mso::TCntPtr<NetUI::Value>::Clear(void)
0x1400516c4  jmp     loc_140051480
0x1400516c9  mov     rax, r15
0x1400516cc  jmp     loc_140051473
0x1400516d1  mov     rcx, r9; S1
0x1400516d4  call    wmemcmp
0x1400516d9  test    eax, eax
0x1400516db  setz    bl
0x1400516de  jmp     loc_140051442
0x1400516e3  mov     bl, r15b
0x1400516e6  jmp     loc_140051442
0x1400516eb  mov     rdx, rax
0x1400516ee  mov     rcx, rdi
0x1400516f1  call    cs:__imp_?Remove@Node@NetUI@@QEAAJPEAV12@@Z; NetUI::Node::Remove(NetUI::Node *)
0x1400516f7  jmp     loc_140051480
```

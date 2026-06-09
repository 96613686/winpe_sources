# Art::FromOdfQuadraticCurveToSegment::AddTranslation(Art::Path2D &)

- ea: `0x1801491d0`
- end: `0x18014938c`
- name: `?AddTranslation@FromOdfQuadraticCurveToSegment@Art@@UEAAXAEAVPath2D@2@@Z`
- size: `444`
- prototype: `void __fastcall(Art::FromOdfQuadraticCurveToSegment *__hidden this, struct Art::Path2D *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180147170`
- `0x1801491d0`
- `0x1801a80e0`

## import_xrefs

- `oart!__imp_??1AdjPoint2D@Art@@QEAA@XZ` at `0x18014929c`
- `oart!__imp_??1AdjPoint2D@Art@@QEAA@XZ` at `0x1801492a6`
- `oart!__imp_??1AdjPoint2D@Art@@QEAA@XZ` at `0x18014929c`
- `oart!__imp_??1AdjPoint2D@Art@@QEAA@XZ` at `0x1801492a6`
- `oart!__imp_??0AdjPoint2D@Art@@QEAA@PEB_W0@Z` at `0x18014926b`
- `oart!__imp_??0AdjPoint2D@Art@@QEAA@PEB_W0@Z` at `0x180149280`
- `oart!__imp_??0AdjPoint2D@Art@@QEAA@PEB_W0@Z` at `0x18014926b`
- `oart!__imp_??0AdjPoint2D@Art@@QEAA@PEB_W0@Z` at `0x180149280`
- `oart!__imp_??1Path2DQuadBezierTo@Art@@QEAA@XZ` at `0x1801492cf`
- `oart!__imp_??1Path2DQuadBezierTo@Art@@QEAA@XZ` at `0x1801492cf`
- `oart!__imp_?NewTop@Path2D@Art@@QEAAAEAV?$Segment_@$0A@@Path2DData@2@XZ` at `0x1801492af`
- `oart!__imp_?NewTop@Path2D@Art@@QEAAAEAV?$Segment_@$0A@@Path2DData@2@XZ` at `0x1801492af`
- `oart!__imp_??0Path2DQuadBezierTo@Art@@QEAA@AEBVAdjPoint2D@1@0@Z` at `0x180149291`
- `oart!__imp_??0Path2DQuadBezierTo@Art@@QEAA@AEBVAdjPoint2D@1@0@Z` at `0x180149291`
- `oart!__imp_?Swap@Path2DQuadBezierTo@Art@@QEAAXAEAV12@@Z` at `0x1801492c4`
- `oart!__imp_?Swap@Path2DQuadBezierTo@Art@@QEAAXAEAV12@@Z` at `0x1801492c4`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801492fb`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180149323`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18014934b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180149373`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1801492fb`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180149323`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18014934b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180149373`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Art::FromOdfQuadraticCurveToSegment::AddTranslation(
        Art::FromOdfQuadraticCurveToSegment *this,
        struct Art::Path2D *a2)
{
  const struct Art::AdjPoint2D *v4; // rbx
  const struct Art::AdjPoint2D *v5; // rax
  __int64 v6; // rax
  Art::Path2DQuadBezierTo *v7; // rax
  void *v8; // rdx
  Mso::Memory *v9; // rcx
  Mso::Memory *v10; // rcx
  Mso::Memory *v11; // rcx
  Mso::Memory *v12; // rcx
  const wchar_t *v13; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v14[24]; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp-20h] BYREF
  const wchar_t *v17; // [rsp+A0h] [rbp+20h] BYREF
  const wchar_t *v18; // [rsp+B0h] [rbp+30h] BYREF
  const wchar_t *v19; // [rsp+B8h] [rbp+38h] BYREF

  v13 = &dword_1801DBD74;
  (*(void (__fastcall **)(_QWORD, const wchar_t **, _QWORD))(**((_QWORD **)this + 3) + 48LL))(
    *((_QWORD *)this + 3),
    &v13,
    0);
  v19 = &dword_1801DBD74;
  (*(void (__fastcall **)(_QWORD, const wchar_t **, _QWORD))(**((_QWORD **)this + 4) + 48LL))(
    *((_QWORD *)this + 4),
    &v19,
    0);
  v18 = &dword_1801DBD74;
  (*(void (__fastcall **)(_QWORD, const wchar_t **, _QWORD))(**((_QWORD **)this + 5) + 48LL))(
    *((_QWORD *)this + 5),
    &v18,
    0);
  v17 = &dword_1801DBD74;
  (*(void (__fastcall **)(_QWORD, const wchar_t **, _QWORD))(**((_QWORD **)this + 6) + 48LL))(
    *((_QWORD *)this + 6),
    &v17,
    0);
  v4 = (const struct Art::AdjPoint2D *)Art::AdjPoint2D::AdjPoint2D((Art::AdjPoint2D *)v16, v18, v17);
  v5 = (const struct Art::AdjPoint2D *)Art::AdjPoint2D::AdjPoint2D((Art::AdjPoint2D *)v15, v13, v19);
  Art::Path2DQuadBezierTo::Path2DQuadBezierTo((Art::Path2DQuadBezierTo *)v14, v5, v4);
  Art::AdjPoint2D::~AdjPoint2D((Art::AdjPoint2D *)v15);
  Art::AdjPoint2D::~AdjPoint2D((Art::AdjPoint2D *)v16);
  v6 = Art::Path2D::NewTop(a2);
  v7 = (Art::Path2DQuadBezierTo *)Art::Path2DData::Segment_<0>::SwitchToQuadBezierTo(v6);
  Art::Path2DQuadBezierTo::Swap(v7, (struct Art::Path2DQuadBezierTo *)v14);
  Art::Path2DQuadBezierTo::~Path2DQuadBezierTo((Art::Path2DQuadBezierTo *)v14);
  v9 = (Mso::Memory *)(v17 - 6);
  if ( *((_DWORD *)v17 - 2) && (*(_DWORD *)v9 == 1 || !_InterlockedDecrement((volatile signed __int32 *)v9)) && v9 )
    Mso::Memory::Free(v9, v8);
  v10 = (Mso::Memory *)(v18 - 6);
  if ( *((_DWORD *)v18 - 2) && (*(_DWORD *)v10 == 1 || !_InterlockedDecrement((volatile signed __int32 *)v10)) && v10 )
    Mso::Memory::Free(v10, v8);
  v11 = (Mso::Memory *)(v19 - 6);
  if ( *((_DWORD *)v19 - 2) && (*(_DWORD *)v11 == 1 || !_InterlockedDecrement((volatile signed __int32 *)v11)) && v11 )
    Mso::Memory::Free(v11, v8);
  v12 = (Mso::Memory *)(v13 - 6);
  if ( *((_DWORD *)v13 - 2) && (*(_DWORD *)v12 == 1 || !_InterlockedDecrement((volatile signed __int32 *)v12)) )
  {
    if ( v12 )
      Mso::Memory::Free(v12, v8);
  }
}

```

## disassembly

```asm
0x1801491d0  mov     [rsp-18h+arg_8], rbx
0x1801491d5  push    rbp
0x1801491d6  push    rsi
0x1801491d7  push    rdi
0x1801491d8  mov     rbp, rsp
0x1801491db  sub     rsp, 80h
0x1801491e2  mov     rdi, rdx
0x1801491e5  mov     rbx, rcx
0x1801491e8  lea     rsi, dword_1801DBD74
0x1801491ef  mov     [rbp+var_60], rsi
0x1801491f3  mov     rcx, [rcx+18h]
0x1801491f7  mov     rax, [rcx]
0x1801491fa  xor     r8d, r8d
0x1801491fd  lea     rdx, [rbp+var_60]
0x180149201  mov     rax, [rax+30h]
0x180149205  call    cs:__guard_dispatch_icall_fptr
0x18014920b  mov     [rbp+arg_18], rsi
0x18014920f  mov     rcx, [rbx+20h]
0x180149213  mov     rax, [rcx]
0x180149216  xor     r8d, r8d
0x180149219  lea     rdx, [rbp+arg_18]
0x18014921d  mov     rax, [rax+30h]
0x180149221  call    cs:__guard_dispatch_icall_fptr
0x180149227  mov     [rbp+arg_10], rsi
0x18014922b  mov     rcx, [rbx+28h]
0x18014922f  mov     rax, [rcx]
0x180149232  xor     r8d, r8d
0x180149235  lea     rdx, [rbp+arg_10]
0x180149239  mov     rax, [rax+30h]
0x18014923d  call    cs:__guard_dispatch_icall_fptr
0x180149243  mov     [rbp+arg_0], rsi
0x180149247  mov     rcx, [rbx+30h]
0x18014924b  mov     rax, [rcx]
0x18014924e  xor     r8d, r8d
0x180149251  lea     rdx, [rbp+arg_0]
0x180149255  mov     rax, [rax+30h]
0x180149259  call    cs:__guard_dispatch_icall_fptr
0x18014925f  mov     r8, [rbp+arg_0]
0x180149263  mov     rdx, [rbp+arg_10]
0x180149267  lea     rcx, [rbp+var_20]
0x18014926b  call    cs:__imp_??0AdjPoint2D@Art@@QEAA@PEB_W0@Z; Art::AdjPoint2D::AdjPoint2D(wchar_t const *,wchar_t const *)
0x180149271  mov     rbx, rax
0x180149274  mov     r8, [rbp+arg_18]
0x180149278  mov     rdx, [rbp+var_60]
0x18014927c  lea     rcx, [rbp+var_40]
0x180149280  call    cs:__imp_??0AdjPoint2D@Art@@QEAA@PEB_W0@Z; Art::AdjPoint2D::AdjPoint2D(wchar_t const *,wchar_t const *)
0x180149286  nop
0x180149287  mov     r8, rbx
0x18014928a  mov     rdx, rax
0x18014928d  lea     rcx, [rbp+var_58]
0x180149291  call    cs:__imp_??0Path2DQuadBezierTo@Art@@QEAA@AEBVAdjPoint2D@1@0@Z; Art::Path2DQuadBezierTo::Path2DQuadBezierTo(Art::AdjPoint2D const &,Art::AdjPoint2D const &)
0x180149297  nop
0x180149298  lea     rcx, [rbp+var_40]
0x18014929c  call    cs:__imp_??1AdjPoint2D@Art@@QEAA@XZ; Art::AdjPoint2D::~AdjPoint2D(void)
0x1801492a2  lea     rcx, [rbp+var_20]
0x1801492a6  call    cs:__imp_??1AdjPoint2D@Art@@QEAA@XZ; Art::AdjPoint2D::~AdjPoint2D(void)
0x1801492ac  mov     rcx, rdi
0x1801492af  call    cs:__imp_?NewTop@Path2D@Art@@QEAAAEAV?$Segment_@$0A@@Path2DData@2@XZ; Art::Path2D::NewTop(void)
0x1801492b5  mov     rcx, rax
0x1801492b8  call    ?SwitchToQuadBezierTo@?$Segment_@$0A@@Path2DData@Art@@QEAAAEAVPath2DQuadBezierTo@3@XZ; Art::Path2DData::Segment_<0>::SwitchToQuadBezierTo(void)
0x1801492bd  lea     rdx, [rbp+var_58]
0x1801492c1  mov     rcx, rax
0x1801492c4  call    cs:__imp_?Swap@Path2DQuadBezierTo@Art@@QEAAXAEAV12@@Z; Art::Path2DQuadBezierTo::Swap(Art::Path2DQuadBezierTo &)
0x1801492ca  nop
0x1801492cb  lea     rcx, [rbp+var_58]
0x1801492cf  call    cs:__imp_??1Path2DQuadBezierTo@Art@@QEAA@XZ; Art::Path2DQuadBezierTo::~Path2DQuadBezierTo(void)
0x1801492d5  mov     rcx, [rbp+arg_0]
0x1801492d9  add     rcx, 0FFFFFFFFFFFFFFF4h
0x1801492dd  or      ebx, 0FFFFFFFFh
0x1801492e0  xor     edi, edi
0x1801492e2  cmp     [rcx+4], edi
0x1801492e5  jz      short loc_180149302
0x1801492e7  cmp     dword ptr [rcx], 1
0x1801492ea  jz      short loc_1801492F6
0x1801492ec  mov     eax, ebx
0x1801492ee  lock xadd [rcx], eax
0x1801492f2  add     eax, ebx
0x1801492f4  jnz     short loc_180149302
0x1801492f6  test    rcx, rcx
0x1801492f9  jz      short loc_180149302
0x1801492fb  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180149301  nop
0x180149302  mov     rcx, [rbp+arg_10]
0x180149306  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18014930a  cmp     [rcx+4], edi
0x18014930d  jz      short loc_18014932A
0x18014930f  cmp     dword ptr [rcx], 1
0x180149312  jz      short loc_18014931E
0x180149314  mov     eax, ebx
0x180149316  lock xadd [rcx], eax
0x18014931a  add     eax, ebx
0x18014931c  jnz     short loc_18014932A
0x18014931e  test    rcx, rcx
0x180149321  jz      short loc_18014932A
0x180149323  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180149329  nop
0x18014932a  mov     rcx, [rbp+arg_18]
0x18014932e  add     rcx, 0FFFFFFFFFFFFFFF4h
0x180149332  cmp     [rcx+4], edi
0x180149335  jz      short loc_180149352
0x180149337  cmp     dword ptr [rcx], 1
0x18014933a  jz      short loc_180149346
0x18014933c  mov     eax, ebx
0x18014933e  lock xadd [rcx], eax
0x180149342  add     eax, ebx
0x180149344  jnz     short loc_180149352
0x180149346  test    rcx, rcx
0x180149349  jz      short loc_180149352
0x18014934b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180149351  nop
0x180149352  mov     rcx, [rbp+var_60]
0x180149356  add     rcx, 0FFFFFFFFFFFFFFF4h
0x18014935a  cmp     [rcx+4], edi
0x18014935d  jz      short loc_180149379
0x18014935f  cmp     dword ptr [rcx], 1
0x180149362  jz      short loc_18014936E
0x180149364  mov     eax, ebx
0x180149366  lock xadd [rcx], eax
0x18014936a  add     eax, ebx
0x18014936c  jnz     short loc_180149379
0x18014936e  test    rcx, rcx
0x180149371  jz      short loc_180149379
0x180149373  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180149379  mov     rbx, [rsp+80h+arg_8]
0x180149381  add     rsp, 80h
0x180149388  pop     rdi
0x180149389  pop     rsi
0x18014938a  pop     rbp
0x18014938b  retn
```

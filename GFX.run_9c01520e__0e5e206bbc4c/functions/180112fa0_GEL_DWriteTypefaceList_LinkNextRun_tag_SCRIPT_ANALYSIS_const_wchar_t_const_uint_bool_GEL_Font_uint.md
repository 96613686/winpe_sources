# GEL::DWriteTypefaceList::LinkNextRun(tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,GEL::Font &,uint &)

- ea: `0x180112fa0`
- end: `0x180113302`
- name: `?LinkNextRun@DWriteTypefaceList@GEL@@UEBAXAEBUtag_SCRIPT_ANALYSIS@@PEB_WI_NAEAUFont@2@AEAI@Z`
- size: `866`
- prototype: `void __usercall(GEL::DWriteTypefaceList *__hidden this@<rcx>, const struct tag_SCRIPT_ANALYSIS *@<rdx>, const wchar_t *@<r8>, unsigned int@<r9d>, bool, struct GEL::Font *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180112680`

## callees

- `0x180022798`
- `0x1800565ba`
- `0x1800578b0`
- `0x180057e70`
- `0x180090490`
- `0x1800904c8`
- `0x180091710`
- `0x1800aec60`
- `0x1800b0108`
- `0x180112fa0`
- `0x180113304`
- `0x180113438`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18011329c`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x18011329c`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x180113081`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x180113081`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801130d2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801130d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GEL::DWriteTypefaceList::LinkNextRun(
        GEL::DWriteTypefaceList *this,
        const struct tag_SCRIPT_ANALYSIS *a2,
        const wchar_t *a3,
        unsigned int a4,
        bool a5,
        struct GEL::Font *a6,
        unsigned int *a7)
{
  unsigned int v10; // r12d
  int v11; // r9d
  GEL::Typeface *v12; // rbx
  unsigned __int64 v13; // r14
  void (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v15; // edx
  const struct tagLOGFONTW *LogFontWithRunLength; // r15
  __int64 v17; // rdi
  int v18; // edi
  Mso::DWriteAssistant *v19; // rcx
  __int64 v20; // rax
  struct Mso::DWriteAssistant::ResourceManager *ResourceManagerInstance; // rax
  unsigned __int16 v22[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  int v24; // [rsp+60h] [rbp-A0h]
  void *v25; // [rsp+68h] [rbp-98h]
  GEL::Typeface *v26; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v27; // [rsp+78h] [rbp-88h]
  struct tagLOGFONTW v28; // [rsp+80h] [rbp-80h] BYREF
  __int128 v29; // [rsp+E0h] [rbp-20h] BYREF
  int v30; // [rsp+F0h] [rbp-10h]
  _QWORD v31[26]; // [rsp+100h] [rbp+0h] BYREF

  v27 = a7;
  *(_QWORD *)v22 = 0;
  *(_QWORD *)v22 = *(_WORD *)a2 & 0x3FF;
  v10 = *((_DWORD *)a6 + 5);
  v24 = Ofc::Round<long,float>();
  v25 = (void *)*((_QWORD *)a6 + 3);
  v12 = *(GEL::Typeface **)a6;
  if ( !*(_QWORD *)a6 || !v11 || (v10 & 0xFFFFFF00) != 0 )
  {
    Ofc::CInvalidParamException::ThrowTag(0x356681u);
    __debugbreak();
  }
  v26 = *(GEL::Typeface **)a6;
  (**(void (__fastcall ***)(GEL::Typeface *))v12)(v12);
  v13 = (unsigned __int64)a6 + 32;
  if ( *((_BYTE *)a6 + 32) <= 1u )
  {
    v29 = 0;
    v30 = 0;
    v14 = *(void (__fastcall ****)(_QWORD, GUID *, __int64 *))(Mso::DWriteAssistant::ResourceManager::GetInstance() + 72);
    v23 = 0;
    (**v14)(v14, &GUID_80dad800_e21f_4e83_96ce_bfcce500db7c, &v23);
    if ( (*(int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v23 + 112LL))(v23, *(_QWORD *)v22, &v29) < 0 )
    {
      CrashWithRecovery(0x5C82D4u, 0);
      __debugbreak();
    }
    if ( DWORD1(v29) == 160 )
    {
      *(_BYTE *)v13 = -78;
    }
    else if ( (_DWORD)v29 == 352 )
    {
      *(_BYTE *)v13 = -34;
    }
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  GEL::DWriteFontLinker::DWriteFontLinker((GEL::DWriteFontLinker *)v31, a3, a4, this, (const void **)a6);
  LogFontWithRunLength = GEL::DWriteFontLinker::GetLogFontWithRunLength((GEL::DWriteFontLinker *)v31, v15, v27);
  if ( LogFontWithRunLength )
  {
    v17 = 30;
    if ( LogFontWithRunLength->lfFaceName[0] != 64 )
      v17 = 28;
    memset_0(&v28, 0, sizeof(v28));
    GEL::Typeface::GetLOGFONT(
      v12,
      &v28,
      v24,
      v10,
      v25,
      this,
      (const unsigned __int8 *)(v13 & -(__int64)((*((_DWORD *)a6 + 5) & 0x20) != 0)),
      (const unsigned __int8 *)(((unsigned __int64)a6 + 44) & -(__int64)((*((_DWORD *)a6 + 5) & 0x80u) != 0)),
      v22,
      0);
    GEL::Typeface::Get((char *)LogFontWithRunLength + v17, &v26);
    v18 = -LogFontWithRunLength->lfHeight;
    if ( v28.lfHeight != -v24 )
    {
      LODWORD(v23) = v24;
      HIDWORD(v23) = -v28.lfHeight;
      v18 = Ofc::CRatio::operator*(&v23, (unsigned int)v18);
    }
    v12 = v26;
    GEL::Typeface::GetLOGFONT(
      v26,
      &v28,
      v18,
      v10,
      v25,
      this,
      (const unsigned __int8 *)(v13 & -(__int64)((*((_DWORD *)a6 + 5) & 0x20) != 0)),
      (const unsigned __int8 *)(((unsigned __int64)a6 + 44) & -(__int64)((*((_DWORD *)a6 + 5) & 0x80u) != 0)),
      v22,
      0);
    *((float *)a6 + 4) = (float)v18;
  }
  ARC::TPtr<ARC::ITexture const>::operator=(a6, v12);
  if ( v12 )
  {
    v20 = (*(__int64 (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v12 + 288LL))(v12);
    ARC::TPtr<ARC::ITexture const>::operator=((char *)a6 + 8, v20);
  }
  if ( v31[0] )
  {
    ResourceManagerInstance = Mso::DWriteAssistant::GetResourceManagerInstance(v19);
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)ResourceManagerInstance + 10) + 96LL))(
      *((_QWORD *)ResourceManagerInstance + 10),
      v31[0]);
  }
  if ( v12 )
    (*(void (__fastcall **)(GEL::Typeface *))(*(_QWORD *)v12 + 8LL))(v12);
}

```

## disassembly

```asm
0x180112fa0  mov     [rsp-8+arg_8], rbx
0x180112fa5  push    rbp
0x180112fa6  push    rsi
0x180112fa7  push    rdi
0x180112fa8  push    r12
0x180112faa  push    r13
0x180112fac  push    r14
0x180112fae  push    r15
0x180112fb0  lea     rbp, [rsp-0E0h]
0x180112fb8  sub     rsp, 1E0h
0x180112fbf  mov     rax, cs:__security_cookie
0x180112fc6  xor     rax, rsp
0x180112fc9  mov     [rbp+110h+var_40], rax
0x180112fd0  mov     edi, r9d
0x180112fd3  mov     r15, r8
0x180112fd6  mov     r13, rcx
0x180112fd9  mov     rsi, [rbp+110h+arg_28]
0x180112fe0  mov     rax, [rbp+110h+arg_30]
0x180112fe7  mov     [rsp+210h+var_198], rax
0x180112fec  xor     r8d, r8d
0x180112fef  mov     qword ptr [rsp+210h+var_1C0], r8
0x180112ff4  movzx   ecx, word ptr [rdx]
0x180112ff7  mov     eax, dword ptr [rsp+210h+var_1C0+4]
0x180112ffb  lea     edx, [r8+1]
0x180112fff  test    cx, cx
0x180113002  cmovs   eax, edx
0x180113005  mov     dword ptr [rsp+210h+var_1C0+4], eax
0x180113009  mov     eax, 3FFh
0x18011300e  and     cx, ax
0x180113011  mov     [rsp+210h+var_1C0], cx
0x180113016  mov     r12d, [rsi+14h]
0x18011301a  movss   xmm0, dword ptr [rsi+10h]
0x18011301f  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x180113024  mov     [rsp+210h+var_1B0], eax
0x180113028  mov     rax, [rsi+18h]
0x18011302c  mov     [rsp+210h+var_1A8], rax
0x180113031  mov     rbx, [rsi]
0x180113034  test    rbx, rbx
0x180113037  jz      loc_1801132F7
0x18011303d  test    r9d, r9d
0x180113040  jz      loc_1801132F7
0x180113046  test    r12d, 0FFFFFF00h
0x18011304d  jnz     loc_1801132F7
0x180113053  mov     [rsp+210h+var_1A0], rbx
0x180113058  mov     rax, [rbx]
0x18011305b  mov     rcx, rbx
0x18011305e  mov     rax, [rax]
0x180113061  call    cs:__guard_dispatch_icall_fptr
0x180113067  lea     r14, [rsi+20h]
0x18011306b  cmp     byte ptr [r14], 1
0x18011306f  ja      loc_18011310C
0x180113075  xorps   xmm0, xmm0
0x180113078  xor     eax, eax
0x18011307a  movups  [rbp+110h+var_130], xmm0
0x18011307e  mov     [rbp+110h+var_120], eax
0x180113081  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x180113087  mov     rcx, [rax+48h]
0x18011308b  mov     [rsp+210h+var_1B8], 0
0x180113094  mov     rax, [rcx]
0x180113097  lea     r8, [rsp+210h+var_1B8]
0x18011309c  lea     rdx, _GUID_80dad800_e21f_4e83_96ce_bfcce500db7c
0x1801130a3  mov     rax, [rax]
0x1801130a6  call    cs:__guard_dispatch_icall_fptr
0x1801130ac  mov     rcx, [rsp+210h+var_1B8]
0x1801130b1  mov     rax, [rcx]
0x1801130b4  lea     r8, [rbp+110h+var_130]
0x1801130b8  mov     rdx, qword ptr [rsp+210h+var_1C0]
0x1801130bd  mov     rax, [rax+70h]
0x1801130c1  call    cs:__guard_dispatch_icall_fptr
0x1801130c7  test    eax, eax
0x1801130c9  jns     short loc_1801130D9
0x1801130cb  xor     edx, edx
0x1801130cd  mov     ecx, 5C82D4h
0x1801130d2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801130d8  int     3; Trap to Debugger
0x1801130d9  cmp     dword ptr [rbp+110h+var_130+4], 0A0h
0x1801130e0  jnz     short loc_1801130E8
0x1801130e2  mov     byte ptr [r14], 0B2h
0x1801130e6  jmp     short loc_1801130F5
0x1801130e8  cmp     dword ptr [rbp+110h+var_130], 160h
0x1801130ef  jnz     short loc_1801130F5
0x1801130f1  mov     byte ptr [r14], 0DEh
0x1801130f5  mov     rcx, [rsp+210h+var_1B8]
0x1801130fa  test    rcx, rcx
0x1801130fd  jz      short loc_18011310C
0x1801130ff  mov     rax, [rcx]
0x180113102  mov     rax, [rax+10h]
0x180113106  call    cs:__guard_dispatch_icall_fptr
0x18011310c  mov     [rsp+210h+var_1F0], rsi; struct GEL::Font *
0x180113111  mov     r9, r13; struct GEL::DWriteTypefaceList *
0x180113114  mov     r8d, edi; unsigned int
0x180113117  mov     rdx, r15; wchar_t *
0x18011311a  lea     rcx, [rbp+110h+var_110]; this
0x18011311e  call    ??0DWriteFontLinker@GEL@@QEAA@PEB_WIAEBVDWriteTypefaceList@1@AEBUFont@1@I@Z; GEL::DWriteFontLinker::DWriteFontLinker(wchar_t const *,uint,GEL::DWriteTypefaceList const &,GEL::Font const &,uint)
0x180113123  mov     r8, [rsp+210h+var_198]; unsigned int *
0x180113128  lea     rcx, [rbp+110h+var_110]; this
0x18011312c  call    ?GetLogFontWithRunLength@DWriteFontLinker@GEL@@QEAAPEBUtagLOGFONTW@@IAEAI@Z; GEL::DWriteFontLinker::GetLogFontWithRunLength(uint,uint &)
0x180113131  mov     r15, rax
0x180113134  test    rax, rax
0x180113137  jz      loc_180113265
0x18011313d  mov     edi, 1Eh
0x180113142  lea     eax, [rdi-2]
0x180113145  cmp     word ptr [r15+1Ch], 40h ; '@'
0x18011314b  cmovnz  edi, eax
0x18011314e  add     rdi, r15
0x180113151  xor     edx, edx; Val
0x180113153  lea     r8d, [rax+40h]; Size
0x180113157  lea     rcx, [rbp+110h+var_190]; void *
0x18011315b  call    memset_0
0x180113160  mov     r8d, [rsi+14h]
0x180113164  mov     ecx, r8d
0x180113167  and     cl, 80h
0x18011316a  lea     rax, [rsi+2Ch]
0x18011316e  neg     cl
0x180113170  sbb     rdx, rdx
0x180113173  and     rdx, rax
0x180113176  and     r8b, 20h
0x18011317a  neg     r8b
0x18011317d  sbb     rax, rax
0x180113180  and     rax, r14
0x180113183  mov     [rsp+210h+var_1C8], 0; bool
0x180113188  lea     rcx, [rsp+210h+var_1C0]
0x18011318d  mov     [rsp+210h+var_1D0], rcx; unsigned __int16 *
0x180113192  mov     [rsp+210h+var_1D8], rdx; unsigned __int8 *
0x180113197  mov     [rsp+210h+var_1E0], rax; unsigned __int8 *
0x18011319c  mov     [rsp+210h+var_1E8], r13; struct GEL::ITypefaceList *
0x1801131a1  mov     rax, [rsp+210h+var_1A8]
0x1801131a6  mov     [rsp+210h+var_1F0], rax; void *
0x1801131ab  mov     r9d, r12d; unsigned int
0x1801131ae  mov     r8d, [rsp+210h+var_1B0]; int
0x1801131b3  lea     rdx, [rbp+110h+var_190]; struct tagLOGFONTW *
0x1801131b7  mov     rcx, rbx; this
0x1801131ba  call    ?GetLOGFONT@Typeface@GEL@@QEBAXAEAUtagLOGFONTW@@JIPEBXAEBUITypefaceList@2@PEBE3PEBG_N@Z; GEL::Typeface::GetLOGFONT(tagLOGFONTW &,long,uint,void const *,GEL::ITypefaceList const &,uchar const *,uchar const *,ushort const *,bool)
0x1801131bf  lea     rdx, [rsp+210h+var_1A0]
0x1801131c4  mov     rcx, rdi
0x1801131c7  call    ?Get@Typeface@GEL@@SAXPEB_WAEAV?$TCntPtr@VTypeface@GEL@@@Ofc@@@Z; GEL::Typeface::Get(wchar_t const *,Ofc::TCntPtr<GEL::Typeface> &)
0x1801131cc  mov     edi, [r15]
0x1801131cf  neg     edi
0x1801131d1  mov     edx, [rsp+210h+var_1B0]
0x1801131d5  mov     eax, edx
0x1801131d7  neg     eax
0x1801131d9  mov     ecx, [rbp+110h+var_190.lfHeight]
0x1801131dc  cmp     ecx, eax
0x1801131de  jz      short loc_1801131F8
0x1801131e0  neg     ecx
0x1801131e2  mov     dword ptr [rsp+210h+var_1B8], edx
0x1801131e6  mov     dword ptr [rsp+210h+var_1B8+4], ecx
0x1801131ea  mov     edx, edi
0x1801131ec  lea     rcx, [rsp+210h+var_1B8]
0x1801131f1  call    ??DCRatio@Ofc@@QEBAJJ@Z; Ofc::CRatio::operator*(long)
0x1801131f6  mov     edi, eax
0x1801131f8  mov     r8d, [rsi+14h]
0x1801131fc  mov     eax, r8d
0x1801131ff  and     al, 80h
0x180113201  lea     rcx, [rsi+2Ch]
0x180113205  neg     al
0x180113207  sbb     rdx, rdx
0x18011320a  and     rdx, rcx
0x18011320d  and     r8b, 20h
0x180113211  neg     r8b
0x180113214  sbb     rax, rax
0x180113217  and     rax, r14
0x18011321a  mov     [rsp+210h+var_1C8], 0; bool
0x18011321f  lea     rcx, [rsp+210h+var_1C0]
0x180113224  mov     [rsp+210h+var_1D0], rcx; unsigned __int16 *
0x180113229  mov     [rsp+210h+var_1D8], rdx; unsigned __int8 *
0x18011322e  mov     [rsp+210h+var_1E0], rax; unsigned __int8 *
0x180113233  mov     [rsp+210h+var_1E8], r13; struct GEL::ITypefaceList *
0x180113238  mov     rax, [rsp+210h+var_1A8]
0x18011323d  mov     [rsp+210h+var_1F0], rax; void *
0x180113242  mov     r9d, r12d; unsigned int
0x180113245  mov     r8d, edi; int
0x180113248  lea     rdx, [rbp+110h+var_190]; struct tagLOGFONTW *
0x18011324c  mov     rbx, [rsp+210h+var_1A0]
0x180113251  mov     rcx, rbx; this
0x180113254  call    ?GetLOGFONT@Typeface@GEL@@QEBAXAEAUtagLOGFONTW@@JIPEBXAEBUITypefaceList@2@PEBE3PEBG_N@Z; GEL::Typeface::GetLOGFONT(tagLOGFONTW &,long,uint,void const *,GEL::ITypefaceList const &,uchar const *,uchar const *,ushort const *,bool)
0x180113259  movd    xmm0, edi
0x18011325d  cvtdq2ps xmm0, xmm0
0x180113260  movss   dword ptr [rsi+10h], xmm0
0x180113265  mov     rdx, rbx
0x180113268  mov     rcx, rsi
0x18011326b  call    ??4?$TPtr@$$CBUITexture@ARC@@@ARC@@QEAAAEAV01@PEBUITexture@1@@Z; ARC::TPtr<ARC::ITexture const>::operator=(ARC::ITexture const *)
0x180113270  test    rbx, rbx
0x180113273  jz      short loc_180113295
0x180113275  mov     rax, [rbx]
0x180113278  mov     rcx, rbx
0x18011327b  mov     rax, [rax+120h]
0x180113282  call    cs:__guard_dispatch_icall_fptr
0x180113288  mov     rdx, rax
0x18011328b  lea     rcx, [rsi+8]
0x18011328f  call    ??4?$TPtr@$$CBUITexture@ARC@@@ARC@@QEAAAEAV01@PEBUITexture@1@@Z; ARC::TPtr<ARC::ITexture const>::operator=(ARC::ITexture const *)
0x180113294  nop
0x180113295  cmp     [rbp+110h+var_110], 0
0x18011329a  jz      short loc_1801132B8
0x18011329c  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x1801132a2  mov     rcx, [rax+50h]
0x1801132a6  mov     rax, [rcx]
0x1801132a9  mov     rdx, [rbp+110h+var_110]
0x1801132ad  mov     rax, [rax+60h]
0x1801132b1  call    cs:__guard_dispatch_icall_fptr
0x1801132b7  nop
0x1801132b8  test    rbx, rbx
0x1801132bb  jz      short loc_1801132CD
0x1801132bd  mov     rax, [rbx]
0x1801132c0  mov     rcx, rbx
0x1801132c3  mov     rax, [rax+8]
0x1801132c7  call    cs:__guard_dispatch_icall_fptr
0x1801132cd  mov     rcx, [rbp+110h+var_40]
0x1801132d4  xor     rcx, rsp; StackCookie
0x1801132d7  call    __security_check_cookie
0x1801132dc  mov     rbx, [rsp+210h+arg_8]
0x1801132e4  add     rsp, 1E0h
0x1801132eb  pop     r15
0x1801132ed  pop     r14
0x1801132ef  pop     r13
0x1801132f1  pop     r12
0x1801132f3  pop     rdi
0x1801132f4  pop     rsi
0x1801132f5  pop     rbp
0x1801132f6  retn
0x1801132f7  mov     ecx, 356681h; unsigned int
0x1801132fc  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180113301  int     3; Trap to Debugger
```

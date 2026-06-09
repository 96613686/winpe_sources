# GEL::DWriteTypefaceList::LinkNextRun(tag_SCRIPT_ANALYSIS const &,wchar_t const *,uint,bool,GEL::Font &,uint &)

- ea: `0x180117fd0`
- end: `0x180118332`
- name: `?LinkNextRun@DWriteTypefaceList@GEL@@UEBAXAEBUtag_SCRIPT_ANALYSIS@@PEB_WI_NAEAUFont@2@AEAI@Z`
- size: `866`
- prototype: `void __usercall(GEL::DWriteTypefaceList *__hidden this@<rcx>, const struct tag_SCRIPT_ANALYSIS *@<rdx>, const wchar_t *@<r8>, unsigned int@<r9d>, bool, struct GEL::Font *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180117560`

## callees

- `0x180022138`
- `0x180055b26`
- `0x180056ee0`
- `0x1800573f0`
- `0x1800774c0`
- `0x1800795e4`
- `0x18009aa90`
- `0x18009b7fc`
- `0x1800dc27c`
- `0x180117f24`
- `0x180117fd0`
- `0x180118334`

## import_xrefs

- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x1801182cc`
- `mso40uiWin32Client!__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ` at `0x1801182cc`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x1801180b1`
- `mso40uiWin32Client!__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ` at `0x1801180b1`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180118102`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180118102`

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
0x180117fd0  mov     [rsp-8+arg_8], rbx
0x180117fd5  push    rbp
0x180117fd6  push    rsi
0x180117fd7  push    rdi
0x180117fd8  push    r12
0x180117fda  push    r13
0x180117fdc  push    r14
0x180117fde  push    r15
0x180117fe0  lea     rbp, [rsp-0E0h]
0x180117fe8  sub     rsp, 1E0h
0x180117fef  mov     rax, cs:__security_cookie
0x180117ff6  xor     rax, rsp
0x180117ff9  mov     [rbp+110h+var_40], rax
0x180118000  mov     edi, r9d
0x180118003  mov     r15, r8
0x180118006  mov     r13, rcx
0x180118009  mov     rsi, [rbp+110h+arg_28]
0x180118010  mov     rax, [rbp+110h+arg_30]
0x180118017  mov     [rsp+210h+var_198], rax
0x18011801c  xor     r8d, r8d
0x18011801f  mov     qword ptr [rsp+210h+var_1C0], r8
0x180118024  movzx   ecx, word ptr [rdx]
0x180118027  mov     eax, dword ptr [rsp+210h+var_1C0+4]
0x18011802b  lea     edx, [r8+1]
0x18011802f  test    cx, cx
0x180118032  cmovs   eax, edx
0x180118035  mov     dword ptr [rsp+210h+var_1C0+4], eax
0x180118039  mov     eax, 3FFh
0x18011803e  and     cx, ax
0x180118041  mov     [rsp+210h+var_1C0], cx
0x180118046  mov     r12d, [rsi+14h]
0x18011804a  movss   xmm0, dword ptr [rsi+10h]
0x18011804f  call    ??$Round@JM@Ofc@@YAJM@Z; Ofc::Round<long,float>(float)
0x180118054  mov     [rsp+210h+var_1B0], eax
0x180118058  mov     rax, [rsi+18h]
0x18011805c  mov     [rsp+210h+var_1A8], rax
0x180118061  mov     rbx, [rsi]
0x180118064  test    rbx, rbx
0x180118067  jz      loc_180118327
0x18011806d  test    r9d, r9d
0x180118070  jz      loc_180118327
0x180118076  test    r12d, 0FFFFFF00h
0x18011807d  jnz     loc_180118327
0x180118083  mov     [rsp+210h+var_1A0], rbx
0x180118088  mov     rax, [rbx]
0x18011808b  mov     rcx, rbx
0x18011808e  mov     rax, [rax]
0x180118091  call    cs:__guard_dispatch_icall_fptr
0x180118097  lea     r14, [rsi+20h]
0x18011809b  cmp     byte ptr [r14], 1
0x18011809f  ja      loc_18011813C
0x1801180a5  xorps   xmm0, xmm0
0x1801180a8  xor     eax, eax
0x1801180aa  movups  [rbp+110h+var_130], xmm0
0x1801180ae  mov     [rbp+110h+var_120], eax
0x1801180b1  call    cs:__imp_?GetInstance@ResourceManager@DWriteAssistant@Mso@@SAAEAV123@XZ; Mso::DWriteAssistant::ResourceManager::GetInstance(void)
0x1801180b7  mov     rcx, [rax+48h]
0x1801180bb  mov     [rsp+210h+var_1B8], 0
0x1801180c4  mov     rax, [rcx]
0x1801180c7  lea     r8, [rsp+210h+var_1B8]
0x1801180cc  lea     rdx, _GUID_80dad800_e21f_4e83_96ce_bfcce500db7c
0x1801180d3  mov     rax, [rax]
0x1801180d6  call    cs:__guard_dispatch_icall_fptr
0x1801180dc  mov     rcx, [rsp+210h+var_1B8]
0x1801180e1  mov     rax, [rcx]
0x1801180e4  lea     r8, [rbp+110h+var_130]
0x1801180e8  mov     rdx, qword ptr [rsp+210h+var_1C0]
0x1801180ed  mov     rax, [rax+70h]
0x1801180f1  call    cs:__guard_dispatch_icall_fptr
0x1801180f7  test    eax, eax
0x1801180f9  jns     short loc_180118109
0x1801180fb  xor     edx, edx
0x1801180fd  mov     ecx, 5C82D4h
0x180118102  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180118108  int     3; Trap to Debugger
0x180118109  cmp     dword ptr [rbp+110h+var_130+4], 0A0h
0x180118110  jnz     short loc_180118118
0x180118112  mov     byte ptr [r14], 0B2h
0x180118116  jmp     short loc_180118125
0x180118118  cmp     dword ptr [rbp+110h+var_130], 160h
0x18011811f  jnz     short loc_180118125
0x180118121  mov     byte ptr [r14], 0DEh
0x180118125  mov     rcx, [rsp+210h+var_1B8]
0x18011812a  test    rcx, rcx
0x18011812d  jz      short loc_18011813C
0x18011812f  mov     rax, [rcx]
0x180118132  mov     rax, [rax+10h]
0x180118136  call    cs:__guard_dispatch_icall_fptr
0x18011813c  mov     [rsp+210h+var_1F0], rsi; struct GEL::Font *
0x180118141  mov     r9, r13; struct GEL::DWriteTypefaceList *
0x180118144  mov     r8d, edi; unsigned int
0x180118147  mov     rdx, r15; wchar_t *
0x18011814a  lea     rcx, [rbp+110h+var_110]; this
0x18011814e  call    ??0DWriteFontLinker@GEL@@QEAA@PEB_WIAEBVDWriteTypefaceList@1@AEBUFont@1@I@Z; GEL::DWriteFontLinker::DWriteFontLinker(wchar_t const *,uint,GEL::DWriteTypefaceList const &,GEL::Font const &,uint)
0x180118153  mov     r8, [rsp+210h+var_198]; unsigned int *
0x180118158  lea     rcx, [rbp+110h+var_110]; this
0x18011815c  call    ?GetLogFontWithRunLength@DWriteFontLinker@GEL@@QEAAPEBUtagLOGFONTW@@IAEAI@Z; GEL::DWriteFontLinker::GetLogFontWithRunLength(uint,uint &)
0x180118161  mov     r15, rax
0x180118164  test    rax, rax
0x180118167  jz      loc_180118295
0x18011816d  mov     edi, 1Eh
0x180118172  lea     eax, [rdi-2]
0x180118175  cmp     word ptr [r15+1Ch], 40h ; '@'
0x18011817b  cmovnz  edi, eax
0x18011817e  add     rdi, r15
0x180118181  xor     edx, edx; Val
0x180118183  lea     r8d, [rax+40h]; Size
0x180118187  lea     rcx, [rbp+110h+var_190]; void *
0x18011818b  call    memset_0
0x180118190  mov     r8d, [rsi+14h]
0x180118194  mov     ecx, r8d
0x180118197  and     cl, 80h
0x18011819a  lea     rax, [rsi+2Ch]
0x18011819e  neg     cl
0x1801181a0  sbb     rdx, rdx
0x1801181a3  and     rdx, rax
0x1801181a6  and     r8b, 20h
0x1801181aa  neg     r8b
0x1801181ad  sbb     rax, rax
0x1801181b0  and     rax, r14
0x1801181b3  mov     [rsp+210h+var_1C8], 0; bool
0x1801181b8  lea     rcx, [rsp+210h+var_1C0]
0x1801181bd  mov     [rsp+210h+var_1D0], rcx; unsigned __int16 *
0x1801181c2  mov     [rsp+210h+var_1D8], rdx; unsigned __int8 *
0x1801181c7  mov     [rsp+210h+var_1E0], rax; unsigned __int8 *
0x1801181cc  mov     [rsp+210h+var_1E8], r13; struct GEL::ITypefaceList *
0x1801181d1  mov     rax, [rsp+210h+var_1A8]
0x1801181d6  mov     [rsp+210h+var_1F0], rax; void *
0x1801181db  mov     r9d, r12d; unsigned int
0x1801181de  mov     r8d, [rsp+210h+var_1B0]; int
0x1801181e3  lea     rdx, [rbp+110h+var_190]; struct tagLOGFONTW *
0x1801181e7  mov     rcx, rbx; this
0x1801181ea  call    ?GetLOGFONT@Typeface@GEL@@QEBAXAEAUtagLOGFONTW@@JIPEBXAEBUITypefaceList@2@PEBE3PEBG_N@Z; GEL::Typeface::GetLOGFONT(tagLOGFONTW &,long,uint,void const *,GEL::ITypefaceList const &,uchar const *,uchar const *,ushort const *,bool)
0x1801181ef  lea     rdx, [rsp+210h+var_1A0]
0x1801181f4  mov     rcx, rdi
0x1801181f7  call    ?Get@Typeface@GEL@@SAXPEB_WAEAV?$TCntPtr@VTypeface@GEL@@@Ofc@@@Z; GEL::Typeface::Get(wchar_t const *,Ofc::TCntPtr<GEL::Typeface> &)
0x1801181fc  mov     edi, [r15]
0x1801181ff  neg     edi
0x180118201  mov     edx, [rsp+210h+var_1B0]
0x180118205  mov     eax, edx
0x180118207  neg     eax
0x180118209  mov     ecx, [rbp+110h+var_190.lfHeight]
0x18011820c  cmp     ecx, eax
0x18011820e  jz      short loc_180118228
0x180118210  neg     ecx
0x180118212  mov     dword ptr [rsp+210h+var_1B8], edx
0x180118216  mov     dword ptr [rsp+210h+var_1B8+4], ecx
0x18011821a  mov     edx, edi
0x18011821c  lea     rcx, [rsp+210h+var_1B8]
0x180118221  call    ??DCRatio@Ofc@@QEBAJJ@Z; Ofc::CRatio::operator*(long)
0x180118226  mov     edi, eax
0x180118228  mov     r8d, [rsi+14h]
0x18011822c  mov     eax, r8d
0x18011822f  and     al, 80h
0x180118231  lea     rcx, [rsi+2Ch]
0x180118235  neg     al
0x180118237  sbb     rdx, rdx
0x18011823a  and     rdx, rcx
0x18011823d  and     r8b, 20h
0x180118241  neg     r8b
0x180118244  sbb     rax, rax
0x180118247  and     rax, r14
0x18011824a  mov     [rsp+210h+var_1C8], 0; bool
0x18011824f  lea     rcx, [rsp+210h+var_1C0]
0x180118254  mov     [rsp+210h+var_1D0], rcx; unsigned __int16 *
0x180118259  mov     [rsp+210h+var_1D8], rdx; unsigned __int8 *
0x18011825e  mov     [rsp+210h+var_1E0], rax; unsigned __int8 *
0x180118263  mov     [rsp+210h+var_1E8], r13; struct GEL::ITypefaceList *
0x180118268  mov     rax, [rsp+210h+var_1A8]
0x18011826d  mov     [rsp+210h+var_1F0], rax; void *
0x180118272  mov     r9d, r12d; unsigned int
0x180118275  mov     r8d, edi; int
0x180118278  lea     rdx, [rbp+110h+var_190]; struct tagLOGFONTW *
0x18011827c  mov     rbx, [rsp+210h+var_1A0]
0x180118281  mov     rcx, rbx; this
0x180118284  call    ?GetLOGFONT@Typeface@GEL@@QEBAXAEAUtagLOGFONTW@@JIPEBXAEBUITypefaceList@2@PEBE3PEBG_N@Z; GEL::Typeface::GetLOGFONT(tagLOGFONTW &,long,uint,void const *,GEL::ITypefaceList const &,uchar const *,uchar const *,ushort const *,bool)
0x180118289  movd    xmm0, edi
0x18011828d  cvtdq2ps xmm0, xmm0
0x180118290  movss   dword ptr [rsi+10h], xmm0
0x180118295  mov     rdx, rbx
0x180118298  mov     rcx, rsi
0x18011829b  call    ??4?$TPtr@$$CBUITexture@ARC@@@ARC@@QEAAAEAV01@PEBUITexture@1@@Z; ARC::TPtr<ARC::ITexture const>::operator=(ARC::ITexture const *)
0x1801182a0  test    rbx, rbx
0x1801182a3  jz      short loc_1801182C5
0x1801182a5  mov     rax, [rbx]
0x1801182a8  mov     rcx, rbx
0x1801182ab  mov     rax, [rax+120h]
0x1801182b2  call    cs:__guard_dispatch_icall_fptr
0x1801182b8  mov     rdx, rax
0x1801182bb  lea     rcx, [rsi+8]
0x1801182bf  call    ??4?$TPtr@$$CBUITexture@ARC@@@ARC@@QEAAAEAV01@PEBUITexture@1@@Z; ARC::TPtr<ARC::ITexture const>::operator=(ARC::ITexture const *)
0x1801182c4  nop
0x1801182c5  cmp     [rbp+110h+var_110], 0
0x1801182ca  jz      short loc_1801182E8
0x1801182cc  call    cs:__imp_?GetResourceManagerInstance@DWriteAssistant@Mso@@YAAEAVResourceManager@12@XZ; Mso::DWriteAssistant::GetResourceManagerInstance(void)
0x1801182d2  mov     rcx, [rax+50h]
0x1801182d6  mov     rax, [rcx]
0x1801182d9  mov     rdx, [rbp+110h+var_110]
0x1801182dd  mov     rax, [rax+60h]
0x1801182e1  call    cs:__guard_dispatch_icall_fptr
0x1801182e7  nop
0x1801182e8  test    rbx, rbx
0x1801182eb  jz      short loc_1801182FD
0x1801182ed  mov     rax, [rbx]
0x1801182f0  mov     rcx, rbx
0x1801182f3  mov     rax, [rax+8]
0x1801182f7  call    cs:__guard_dispatch_icall_fptr
0x1801182fd  mov     rcx, [rbp+110h+var_40]
0x180118304  xor     rcx, rsp; StackCookie
0x180118307  call    __security_check_cookie
0x18011830c  mov     rbx, [rsp+210h+arg_8]
0x180118314  add     rsp, 1E0h
0x18011831b  pop     r15
0x18011831d  pop     r14
0x18011831f  pop     r13
0x180118321  pop     r12
0x180118323  pop     rdi
0x180118324  pop     rsi
0x180118325  pop     rbp
0x180118326  retn
0x180118327  mov     ecx, 356681h; unsigned int
0x18011832c  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x180118331  int     3; Trap to Debugger
```

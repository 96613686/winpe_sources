# ParseAndGetPropertyStore(IBindCtx *,wchar_t const *,bool,IFilterHost *,_GUID const &,void * *)

- ea: `0x1400215b8`
- end: `0x1400216de`
- name: `?ParseAndGetPropertyStore@@YAJPEAUIBindCtx@@PEB_W_NPEAUIFilterHost@@AEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: `__int64 __usercall@<rax>(IBindCtx *pbc@<rcx>, const wchar_t *this@<rdx>, bool@<r8b>, struct IFilterHost *@<r9>, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001263c`

## callees

- `0x14000e898`
- `0x1400215b8`
- `0x140028044`
- `0x140036508`
- `0x140070010`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400216a3`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x1400216a3`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x140021612`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x140021612`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x140021639`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x140021639`

## string_xrefs

- `0x1400216be`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrdaemon.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ParseAndGetPropertyStore(
        IBindCtx *pbc,
        wchar_t *this,
        unsigned __int8 a3,
        struct IFilterHost *a4,
        const struct _GUID *ppv,
        void **a6)
{
  int v7; // r15d
  int v10; // esi
  bool is_extended_length_path; // al
  HRESULT v12; // ebx
  int psfgaoOut; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  LPITEMIDLIST ppidl; // [rsp+88h] [rbp+40h] BYREF

  v7 = a3;
  v10 = (int)a6;
  *a6 = 0;
  ppidl = 0;
  is_extended_length_path = wil::is_extended_length_path((wil *)this, this);
  v12 = SHParseDisplayName(&this[4 * is_extended_length_path], pbc, &ppidl, 0, 0);
  if ( v12 < 0 )
    goto LABEL_7;
  ppv = 0;
  v12 = SHCreateItemFromIDList(ppidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&ppv);
  if ( v12 >= 0 )
  {
    a6 = 0;
    v12 = (**(__int64 (__fastcall ***)(const struct _GUID *, GUID *, void ***))&ppv->Data1)(
            ppv,
            &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
            &a6);
    if ( v12 >= 0 )
    {
      psfgaoOut = v10;
      v12 = (*((__int64 (__fastcall **)(void **, _QWORD, struct IFilterHost *, GUID *))*a6 + 9))(
              a6,
              (unsigned int)(8 * v7 + 720),
              a4,
              &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99);
    }
    TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&a6);
  }
  ILFree(ppidl);
  TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&ppv);
  if ( v12 < 0 )
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1654,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx",
      (const char *)(unsigned int)v12,
      psfgaoOut);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400215b8  push    rbp
0x1400215ba  push    rbx
0x1400215bb  push    rsi
0x1400215bc  push    rdi
0x1400215bd  push    r14
0x1400215bf  push    r15
0x1400215c1  mov     rbp, rsp
0x1400215c4  sub     rsp, 48h
0x1400215c8  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x1400215d0  mov     r14, r9
0x1400215d3  movzx   r15d, r8b
0x1400215d7  mov     rbx, rdx
0x1400215da  mov     rdi, rcx
0x1400215dd  mov     rsi, [rbp+arg_28]
0x1400215e1  mov     qword ptr [rsi], 0
0x1400215e8  mov     [rbp+ppidl], 0
0x1400215f0  mov     rcx, rdx; this
0x1400215f3  call    ?is_extended_length_path@wil@@YA_NPEB_W@Z; wil::is_extended_length_path(wchar_t const *)
0x1400215f8  movzx   eax, al
0x1400215fb  lea     rcx, [rbx+rax*8]; pszName
0x1400215ff  mov     qword ptr [rsp+48h+psfgaoOut], 0; psfgaoOut
0x140021608  xor     r9d, r9d; sfgaoIn
0x14002160b  lea     r8, [rbp+ppidl]; ppidl
0x14002160f  mov     rdx, rdi; pbc
0x140021612  call    cs:__imp_SHParseDisplayName
0x140021618  mov     ebx, eax
0x14002161a  test    eax, eax
0x14002161c  js      loc_1400216B7
0x140021622  mov     [rbp+ppv], 0
0x14002162a  lea     r8, [rbp+ppv]; ppv
0x14002162e  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x140021635  mov     rcx, [rbp+ppidl]; pidl
0x140021639  call    cs:__imp_SHCreateItemFromIDList
0x14002163f  mov     ebx, eax
0x140021641  test    eax, eax
0x140021643  js      short loc_14002169F
0x140021645  mov     [rbp+arg_28], 0
0x14002164d  mov     rcx, [rbp+ppv]
0x140021651  mov     rax, [rcx]
0x140021654  lea     r8, [rbp+arg_28]
0x140021658  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x14002165f  mov     rax, [rax]
0x140021662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021667  mov     ebx, eax
0x140021669  test    eax, eax
0x14002166b  js      short loc_140021696
0x14002166d  mov     rcx, [rbp+arg_28]
0x140021671  mov     rax, [rcx]
0x140021674  lea     edx, ds:2D0h[r15*8]
0x14002167c  mov     qword ptr [rsp+48h+psfgaoOut], rsi; int
0x140021681  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x140021688  mov     r8, r14
0x14002168b  mov     rax, [rax+48h]
0x14002168f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140021694  mov     ebx, eax
0x140021696  lea     rcx, [rbp+arg_28]
0x14002169a  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x14002169f  mov     rcx, [rbp+ppidl]; pidl
0x1400216a3  call    cs:__imp_ILFree
0x1400216a9  nop
0x1400216aa  lea     rcx, [rbp+ppv]
0x1400216ae  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x1400216b3  test    ebx, ebx
0x1400216b5  jns     short loc_1400216CF
0x1400216b7  mov     rcx, [rbp+30h]; this
0x1400216bb  mov     r9d, ebx; char *
0x1400216be  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\sea"...
0x1400216c5  mov     edx, 1654h; void *
0x1400216ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400216cf  mov     eax, ebx
0x1400216d1  add     rsp, 48h
0x1400216d5  pop     r15
0x1400216d7  pop     r14
0x1400216d9  pop     rdi
0x1400216da  pop     rsi
0x1400216db  pop     rbx
0x1400216dc  pop     rbp
0x1400216dd  retn
```

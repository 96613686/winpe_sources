# HostDispatch::Create(Js::ScriptContext *,tagVARIANT *,int)

- ea: `0x180197bf4`
- end: `0x180197ce5`
- name: `?Create@HostDispatch@@SAPEAV1@PEAVScriptContext@Js@@PEAUtagVARIANT@@H@Z`
- size: `241`
- prototype: `struct HostDispatch *__fastcall(struct Js::ScriptContext *, struct tagVARIANT *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180024310`
- `0x1801b0100`

## callees

- `0x180013070`
- `0x1800139a0`
- `0x180013cec`
- `0x180021e18`
- `0x180022508`
- `0x180068c64`
- `0x180197bf4`
- `0x1801b00b4`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180197c4a`
- `OLEAUT32!__imp_VariantInit` at `0x180197c4a`
- `OLEAUT32!__imp_VariantCopy` at `0x180197c6c`
- `OLEAUT32!__imp_VariantCopy` at `0x180197c6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct HostDispatch *__fastcall HostDispatch::Create(struct Js::ScriptContext *a1, struct tagVARIANT *a2, int a3)
{
  Recycler *v4; // rbp
  char *v5; // rsi
  HRESULT v6; // ebx
  HostDispatch *v7; // rax
  _BYTE v9[64]; // [rsp+28h] [rbp-40h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  v4 = (Recycler *)*((_QWORD *)a1 + 285);
  v5 = Recycler::AllocTrackedLeafInlined(v4, 0x28u);
  *(_QWORD *)v5 = &HostVariant::`vftable';
  *((_DWORD *)v5 + 2) = *((_DWORD *)v5 + 2) & 0xFFFFFFE1 | 2;
  VariantInit((VARIANTARG *)(v5 + 16));
  Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(v9, a1, retaddr);
  v6 = VariantCopy((VARIANTARG *)(v5 + 16), a2);
  ThreadContext::DisposeOnLeaveScript(*((ThreadContext **)a1 + 148));
  Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(v9);
  if ( v6 < 0 )
    Js::JavascriptError::ThrowError(a1, v6, 0);
  *((_DWORD *)v5 + 2) = (8 * a3) ^ (*((_DWORD *)v5 + 2) ^ (8 * a3)) & 0xFFFFFFF7;
  v7 = (HostDispatch *)Recycler::AllocFinalized(v4, 0x38u);
  return HostDispatch::HostDispatch(v7, (struct HostVariant *)v5, *(struct Js::StaticType **)(*(_QWORD *)a1 + 3440LL));
}

```

## disassembly

```asm
0x180197bf4  mov     rax, rsp
0x180197bf7  mov     [rax+18h], r8d
0x180197bfb  mov     [rax+10h], rdx
0x180197bff  mov     [rax+8], rcx
0x180197c03  push    rbp
0x180197c04  push    rsi
0x180197c05  push    rdi
0x180197c06  sub     rsp, 50h
0x180197c0a  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180197c12  mov     [rax+20h], rbx
0x180197c16  mov     rdi, rcx
0x180197c19  mov     rbp, [rcx+8E8h]
0x180197c20  mov     edx, 28h ; '('; unsigned __int64
0x180197c25  mov     rcx, rbp; this
0x180197c28  call    ?AllocTrackedLeafInlined@Recycler@@QEAAPEAD_K@Z; Recycler::AllocTrackedLeafInlined(unsigned __int64)
0x180197c2d  mov     rsi, rax
0x180197c30  lea     rax, ??_7HostVariant@@6B@; const HostVariant::`vftable'
0x180197c37  mov     [rsi], rax
0x180197c3a  mov     ecx, [rsi+8]
0x180197c3d  and     ecx, 0FFFFFFE3h
0x180197c40  or      ecx, 2
0x180197c43  mov     [rsi+8], ecx
0x180197c46  lea     rcx, [rsi+10h]; pvarg
0x180197c4a  call    cs:__imp_VariantInit
0x180197c50  mov     r8, [rsp+68h]
0x180197c55  mov     rdx, rdi
0x180197c58  lea     rcx, [rsp+68h+var_40]
0x180197c5d  call    ??0?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@QEAVScriptContext@1@QEAX@Z; Js::LeaveScriptObject<1,1,0>::LeaveScriptObject<1,1,0>(Js::ScriptContext * const,void * const)
0x180197c62  nop
0x180197c63  mov     rdx, [rsp+68h+pvargSrc]; pvargSrc
0x180197c68  lea     rcx, [rsi+10h]; pvargDest
0x180197c6c  call    cs:__imp_VariantCopy
0x180197c72  mov     ebx, eax
0x180197c74  mov     rcx, [rdi+4A0h]; this
0x180197c7b  call    ?DisposeOnLeaveScript@ThreadContext@@QEAAXXZ; ThreadContext::DisposeOnLeaveScript(void)
0x180197c80  nop
0x180197c81  lea     rcx, [rsp+68h+var_40]
0x180197c86  call    ??1?$LeaveScriptObject@$00$00$0A@@Js@@QEAA@XZ; Js::LeaveScriptObject<1,1,0>::~LeaveScriptObject<1,1,0>(void)
0x180197c8b  test    ebx, ebx
0x180197c8d  jns     short loc_180197C9D
0x180197c8f  xor     r8d, r8d; unsigned __int16 *
0x180197c92  mov     edx, ebx; int
0x180197c94  mov     rcx, rdi; struct Js::ScriptContext *
0x180197c97  call    ?ThrowError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowError(Js::ScriptContext *,long,ushort const *)
0x180197c9d  mov     eax, [rsp+68h+arg_10]
0x180197ca4  shl     eax, 3
0x180197ca7  mov     edx, eax
0x180197ca9  xor     edx, [rsi+8]
0x180197cac  and     edx, 0FFFFFFF7h
0x180197caf  xor     edx, eax
0x180197cb1  mov     [rsi+8], edx
0x180197cb4  mov     edx, 38h ; '8'; unsigned __int64
0x180197cb9  mov     rcx, rbp; this
0x180197cbc  call    ?AllocFinalized@Recycler@@QEAAPEAD_K@Z; Recycler::AllocFinalized(unsigned __int64)
0x180197cc1  mov     r8, [rdi]
0x180197cc4  mov     r8, [r8+0D70h]; struct Js::StaticType *
0x180197ccb  mov     rdx, rsi; struct HostVariant *
0x180197cce  mov     rcx, rax; this
0x180197cd1  mov     rbx, [rsp+68h+arg_18]
0x180197cd9  add     rsp, 50h
0x180197cdd  pop     rdi
0x180197cde  pop     rsi
0x180197cdf  pop     rbp
0x180197ce0  jmp     ??0HostDispatch@@IEAA@PEAVHostVariant@@PEAVStaticType@Js@@@Z; HostDispatch::HostDispatch(HostVariant *,Js::StaticType *)
```

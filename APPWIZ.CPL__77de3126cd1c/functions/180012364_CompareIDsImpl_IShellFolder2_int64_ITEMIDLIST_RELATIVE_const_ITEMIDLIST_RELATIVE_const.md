# CompareIDsImpl(IShellFolder2 *,__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x180012364`
- end: `0x18001258f`
- name: `?CompareIDsImpl@@YAJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST_RELATIVE@@2@Z`
- size: `555`
- prototype: `int(struct IShellFolder2 *, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180012170`
- `0x1800427f0`

## callees

- `0x180012364`
- `0x1800144e0`
- `0x180016f70`
- `0x180017300`
- `0x180051500`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `PROPSYS!VariantCompare` at `0x180012517`
- `PROPSYS!VariantCompare` at `0x180012517`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180012479`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800124fb`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180012479`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800124fb`
- `SHELL32!__imp_ILFree` at `0x18001255e`
- `SHELL32!__imp_ILFree` at `0x180012567`
- `SHELL32!__imp_ILFree` at `0x18001255e`
- `SHELL32!__imp_ILFree` at `0x180012567`
- `OLEAUT32!__imp_VariantClear` at `0x18001254b`
- `OLEAUT32!__imp_VariantClear` at `0x180012555`
- `OLEAUT32!__imp_VariantClear` at `0x18001254b`
- `OLEAUT32!__imp_VariantClear` at `0x180012555`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180012509`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180012509`

## pseudocode

```c
__int64 __fastcall CompareIDsImpl(
        struct IShellFolder2 *a1,
        __int64 a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  ITEMIDLIST *v4; // r15
  int v8; // ebx
  ITEMIDLIST *v9; // r14
  const struct _ITEMIDLIST_RELATIVE *v10; // rcx
  struct _ITEMID_CHILD *v11; // r12
  const struct _ITEMIDLIST_RELATIVE *v12; // rcx
  struct IShellFolder2Vtbl *lpVtbl; // rax
  int v14; // ebx
  struct IShellFolder2Vtbl *v15; // rax
  int v16; // eax
  struct _ITEMID_CHILD *v18; // [rsp+30h] [rbp-49h] BYREF
  __int64 v19; // [rsp+38h] [rbp-41h]
  VARIANT var2; // [rsp+40h] [rbp-39h] BYREF
  VARIANT var1; // [rsp+58h] [rbp-21h] BYREF
  __int128 v22; // [rsp+70h] [rbp-9h] BYREF
  int v23; // [rsp+80h] [rbp+7h]

  v4 = 0;
  v19 = a2;
  v8 = -2147024809;
  if ( a3 && a4 && *(_WORD *)a3 && *(_WORD *)a4 )
  {
    if ( a3 == a4 )
      return 0;
    v18 = 0;
    v9 = 0;
    if ( (unsigned int)ILIsChild(a3) )
    {
      v11 = a3;
    }
    else
    {
      v8 = SHILCloneFirst(v10, &v18);
      if ( v8 < 0 )
        return (unsigned int)v8;
      v9 = (ITEMIDLIST *)v18;
      v11 = v18;
    }
    v18 = 0;
    if ( (unsigned int)ILIsChild(a4) )
    {
      v18 = a4;
    }
    else
    {
      v8 = SHILCloneFirst(v12, &v18);
      if ( v8 < 0 )
      {
LABEL_32:
        ILFree(v9);
        return (unsigned int)v8;
      }
      v4 = (ITEMIDLIST *)v18;
    }
    v23 = 0;
    lpVtbl = a1->lpVtbl;
    v22 = 0;
    v8 = ((__int64 (__fastcall *)(struct IShellFolder2 *, _QWORD, __int128 *))lpVtbl->MapColumnToSCID)(
           a1,
           (unsigned __int16)v19,
           &v22);
    if ( v8 >= 0 )
    {
      memset(&var1, 0, sizeof(var1));
      v14 = 0;
      if ( (unsigned int)IsAppCompatModeEnabled(25) )
        v14 = SHCoInitialize();
      if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANT *))a1->lpVtbl->GetDetailsEx)(
             a1,
             v11,
             &v22,
             &var1) < 0 )
        memset(&var1, 0, sizeof(var1));
      v15 = a1->lpVtbl;
      memset(&var2, 0, sizeof(var2));
      if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANT *))v15->GetDetailsEx)(
             a1,
             v18,
             &v22,
             &var2) < 0 )
        memset(&var2, 0, sizeof(var2));
      if ( (unsigned int)IsAppCompatModeEnabled(25) && !v14 )
        CoUninitialize();
      v16 = VariantCompare(&var1, &var2);
      if ( v16 )
      {
        if ( v16 >= 0 )
          v8 = v16 > 0;
        else
          v8 = 0xFFFF;
      }
      else
      {
        v8 = ILCompareRelIDs(a1, a3, a4, v19);
      }
      VariantClear(&var2);
      VariantClear(&var1);
    }
    ILFree(v4);
    goto LABEL_32;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012364  push    rbp
0x180012366  push    rbx
0x180012367  push    rsi
0x180012368  push    rdi
0x180012369  push    r12
0x18001236b  push    r13
0x18001236d  push    r14
0x18001236f  push    r15
0x180012371  lea     rbp, [rsp-1Fh]
0x180012376  sub     rsp, 98h
0x18001237d  mov     rax, cs:__security_cookie
0x180012384  xor     rax, rsp
0x180012387  mov     [rbp+57h+var_48], rax
0x18001238b  xor     r15d, r15d
0x18001238e  mov     [rbp+57h+var_98], rdx
0x180012392  mov     rdi, r9
0x180012395  mov     rsi, r8
0x180012398  mov     r13, rcx
0x18001239b  mov     ebx, 80070057h
0x1800123a0  test    r8, r8
0x1800123a3  jz      loc_18001256D
0x1800123a9  test    r9, r9
0x1800123ac  jz      loc_18001256D
0x1800123b2  cmp     [r8], r15w
0x1800123b6  jz      loc_18001256D
0x1800123bc  cmp     [r9], r15w
0x1800123c0  jz      loc_18001256D
0x1800123c6  cmp     r8, r9
0x1800123c9  jnz     short loc_1800123D3
0x1800123cb  mov     ebx, r15d
0x1800123ce  jmp     loc_18001256D
0x1800123d3  mov     rcx, rsi; struct _ITEMIDLIST_RELATIVE *
0x1800123d6  mov     [rbp+57h+var_A0], r15
0x1800123da  mov     r14, r15
0x1800123dd  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x1800123e2  test    eax, eax
0x1800123e4  jz      short loc_1800123EB
0x1800123e6  mov     r12, rsi
0x1800123e9  jmp     short loc_180012405
0x1800123eb  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x1800123ef  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x1800123f4  mov     ebx, eax
0x1800123f6  test    eax, eax
0x1800123f8  js      loc_18001256D
0x1800123fe  mov     r14, [rbp+57h+var_A0]
0x180012402  mov     r12, r14
0x180012405  mov     rcx, rdi; struct _ITEMIDLIST_RELATIVE *
0x180012408  mov     [rbp+57h+var_A0], r15
0x18001240c  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x180012411  test    eax, eax
0x180012413  jz      short loc_18001241B
0x180012415  mov     [rbp+57h+var_A0], rdi
0x180012419  jmp     short loc_180012436
0x18001241b  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x18001241f  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x180012424  mov     ebx, eax
0x180012426  test    eax, eax
0x180012428  js      loc_180012564
0x18001242e  mov     r15, [rbp+57h+var_A0]
0x180012432  mov     [rbp+57h+var_A0], r15
0x180012436  movzx   edx, word ptr [rbp+57h+var_98]
0x18001243a  lea     r8, [rbp+57h+var_60]
0x18001243e  xor     eax, eax
0x180012440  xorps   xmm0, xmm0
0x180012443  mov     [rbp+57h+var_50], eax
0x180012446  mov     rcx, r13
0x180012449  mov     rax, [r13+0]
0x18001244d  movups  [rbp+57h+var_60], xmm0
0x180012451  mov     rax, [rax+98h]
0x180012458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001245d  mov     ebx, eax
0x18001245f  test    eax, eax
0x180012461  js      loc_18001255B
0x180012467  xor     eax, eax
0x180012469  xorps   xmm0, xmm0
0x18001246c  movups  xmmword ptr [rbp+57h+var1], xmm0
0x180012470  mov     qword ptr [rbp+57h+var1+10h], rax
0x180012474  xor     ebx, ebx
0x180012476  lea     ecx, [rax+19h]
0x180012479  call    cs:__imp_IsAppCompatModeEnabled
0x18001247f  test    eax, eax
0x180012481  jz      short loc_18001248A
0x180012483  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180012488  mov     ebx, eax
0x18001248a  mov     rcx, [r13+0]
0x18001248e  lea     r9, [rbp+57h+var1]
0x180012492  lea     r8, [rbp+57h+var_60]
0x180012496  mov     rdx, r12
0x180012499  mov     rax, [rcx+88h]
0x1800124a0  mov     rcx, r13
0x1800124a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124a8  test    eax, eax
0x1800124aa  jns     short loc_1800124B9
0x1800124ac  xorps   xmm0, xmm0
0x1800124af  xor     eax, eax
0x1800124b1  movups  xmmword ptr [rbp+57h+var1], xmm0
0x1800124b5  mov     qword ptr [rbp+57h+var1+10h], rax
0x1800124b9  mov     rdx, [rbp+57h+var_A0]
0x1800124bd  lea     r9, [rbp+57h+var2]
0x1800124c1  xor     eax, eax
0x1800124c3  lea     r8, [rbp+57h+var_60]
0x1800124c7  mov     qword ptr [rbp+57h+var2+10h], rax
0x1800124cb  xorps   xmm0, xmm0
0x1800124ce  mov     rax, [r13+0]
0x1800124d2  mov     rcx, r13
0x1800124d5  movups  xmmword ptr [rbp+57h+var2], xmm0
0x1800124d9  mov     rax, [rax+88h]
0x1800124e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124e5  test    eax, eax
0x1800124e7  jns     short loc_1800124F6
0x1800124e9  xorps   xmm0, xmm0
0x1800124ec  xor     eax, eax
0x1800124ee  movups  xmmword ptr [rbp+57h+var2], xmm0
0x1800124f2  mov     qword ptr [rbp+57h+var2+10h], rax
0x1800124f6  mov     ecx, 19h
0x1800124fb  call    cs:__imp_IsAppCompatModeEnabled
0x180012501  test    eax, eax
0x180012503  jz      short loc_18001250F
0x180012505  test    ebx, ebx
0x180012507  jnz     short loc_18001250F
0x180012509  call    cs:__imp_CoUninitialize
0x18001250f  lea     rdx, [rbp+57h+var2]; var2
0x180012513  lea     rcx, [rbp+57h+var1]; var1
0x180012517  call    cs:__imp_VariantCompare
0x18001251d  test    eax, eax
0x18001251f  jz      short loc_180012533
0x180012521  jns     short loc_18001252A
0x180012523  mov     ebx, 0FFFFh
0x180012528  jmp     short loc_180012547
0x18001252a  xor     ebx, ebx
0x18001252c  test    eax, eax
0x18001252e  setnle  bl
0x180012531  jmp     short loc_180012547
0x180012533  mov     r9, [rbp+57h+var_98]
0x180012537  mov     r8, rdi
0x18001253a  mov     rdx, rsi
0x18001253d  mov     rcx, r13
0x180012540  call    ILCompareRelIDs
0x180012545  mov     ebx, eax
0x180012547  lea     rcx, [rbp+57h+var2]; pvarg
0x18001254b  call    cs:__imp_VariantClear
0x180012551  lea     rcx, [rbp+57h+var1]; pvarg
0x180012555  call    cs:__imp_VariantClear
0x18001255b  mov     rcx, r15; pidl
0x18001255e  call    cs:__imp_ILFree
0x180012564  mov     rcx, r14; pidl
0x180012567  call    cs:__imp_ILFree
0x18001256d  mov     eax, ebx
0x18001256f  mov     rcx, [rbp+57h+var_48]
0x180012573  xor     rcx, rsp; StackCookie
0x180012576  call    __security_check_cookie
0x18001257b  add     rsp, 98h
0x180012582  pop     r15
0x180012584  pop     r14
0x180012586  pop     r13
0x180012588  pop     r12
0x18001258a  pop     rdi
0x18001258b  pop     rsi
0x18001258c  pop     rbx
0x18001258d  pop     rbp
0x18001258e  retn
```

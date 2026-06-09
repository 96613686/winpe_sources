# CompareIDsImpl(IShellFolder2 *,__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x1800c2584`
- end: `0x1800c27b4`
- name: `?CompareIDsImpl@@YAJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST_RELATIVE@@2@Z`
- size: `560`
- prototype: `int(struct IShellFolder2 *, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800c2350`

## callees

- `0x18002fe18`
- `0x18002ff00`
- `0x1800423cc`
- `0x180042530`
- `0x180071dc0`
- `0x1800c1e2c`
- `0x1800c2584`
- `0x1800ea010`

## import_xrefs

- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800c26a4`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800c2720`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800c26a4`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800c2720`
- `Windows.Storage!ILFree` at `0x1800c2783`
- `Windows.Storage!ILFree` at `0x1800c278c`
- `Windows.Storage!ILFree` at `0x1800c2783`
- `Windows.Storage!ILFree` at `0x1800c278c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c272e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800c272e`
- `PROPSYS!VariantCompare` at `0x1800c273c`
- `PROPSYS!VariantCompare` at `0x1800c273c`
- `OLEAUT32!__imp_VariantInit` at `0x1800c26db`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2715`
- `OLEAUT32!__imp_VariantInit` at `0x1800c26db`
- `OLEAUT32!__imp_VariantInit` at `0x1800c2715`
- `OLEAUT32!__imp_VariantClear` at `0x1800c2770`
- `OLEAUT32!__imp_VariantClear` at `0x1800c277a`
- `OLEAUT32!__imp_VariantClear` at `0x1800c2770`
- `OLEAUT32!__imp_VariantClear` at `0x1800c277a`

## pseudocode

```c
__int64 __fastcall CompareIDsImpl(
        struct IShellFolder2 *a1,
        __int64 a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  int v7; // ebx
  const struct _ITEMIDLIST_RELATIVE *v8; // r9
  __int64 v9; // r8
  __int64 v10; // r9
  ITEMIDLIST *v11; // r14
  const struct _ITEMIDLIST_RELATIVE *v12; // rcx
  struct _ITEMID_CHILD *v13; // r12
  ITEMIDLIST *v14; // r15
  const struct _ITEMIDLIST_RELATIVE *v15; // rcx
  struct IShellFolder2Vtbl *lpVtbl; // rax
  int v17; // ebx
  struct IShellFolder2Vtbl *v18; // rax
  int v19; // eax
  struct _ITEMID_CHILD *v21; // [rsp+30h] [rbp-49h] BYREF
  __int64 v22; // [rsp+38h] [rbp-41h]
  VARIANTARG var2; // [rsp+40h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-21h] BYREF
  __int128 v25; // [rsp+70h] [rbp-9h] BYREF
  int v26; // [rsp+80h] [rbp+7h]

  v22 = a2;
  v7 = -2147024809;
  if ( a3 && a4 && !(unsigned int)ILIsEmpty(a3) && !(unsigned int)ILIsEmpty(v8) )
  {
    if ( v9 == v10 )
      return 0;
    v11 = 0;
    v21 = 0;
    if ( (unsigned int)ILIsChild(a3) )
    {
      v13 = a3;
    }
    else
    {
      v7 = SHILCloneFirst(v12, &v21);
      if ( v7 < 0 )
        return (unsigned int)v7;
      v11 = (ITEMIDLIST *)v21;
      v13 = v21;
    }
    v14 = 0;
    v21 = 0;
    if ( (unsigned int)ILIsChild(a4) )
    {
      v21 = a4;
    }
    else
    {
      v7 = SHILCloneFirst(v15, &v21);
      if ( v7 < 0 )
      {
LABEL_32:
        ILFree(v11);
        return (unsigned int)v7;
      }
      v14 = (ITEMIDLIST *)v21;
    }
    v26 = 0;
    lpVtbl = a1->lpVtbl;
    v25 = 0;
    v7 = ((__int64 (__fastcall *)(struct IShellFolder2 *, _QWORD, __int128 *))lpVtbl->MapColumnToSCID)(
           a1,
           (unsigned __int16)v22,
           &v25);
    if ( v7 >= 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      v17 = 0;
      if ( (unsigned int)IsAppCompatModeEnabled(25) )
        v17 = SHCoInitialize();
      if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANTARG *))a1->lpVtbl->GetDetailsEx)(
             a1,
             v13,
             &v25,
             &pvarg) < 0 )
        VariantInit(&pvarg);
      v18 = a1->lpVtbl;
      memset(&var2, 0, sizeof(var2));
      if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANTARG *))v18->GetDetailsEx)(
             a1,
             v21,
             &v25,
             &var2) < 0 )
        VariantInit(&var2);
      if ( (unsigned int)IsAppCompatModeEnabled(25) && !v17 )
        CoUninitialize();
      v19 = VariantCompare(&pvarg, &var2);
      if ( v19 )
      {
        if ( v19 >= 0 )
          v7 = v19 > 0;
        else
          v7 = 0xFFFF;
      }
      else
      {
        v7 = ILCompareRelIDs(a1, a3, a4, v22);
      }
      VariantClear(&var2);
      VariantClear(&pvarg);
    }
    ILFree(v14);
    goto LABEL_32;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800c2584  push    rbp
0x1800c2586  push    rbx
0x1800c2587  push    rsi
0x1800c2588  push    rdi
0x1800c2589  push    r12
0x1800c258b  push    r13
0x1800c258d  push    r14
0x1800c258f  push    r15
0x1800c2591  lea     rbp, [rsp-1Fh]
0x1800c2596  sub     rsp, 98h
0x1800c259d  mov     rax, cs:__security_cookie
0x1800c25a4  xor     rax, rsp
0x1800c25a7  mov     [rbp+57h+var_48], rax
0x1800c25ab  mov     [rbp+57h+var_98], rdx
0x1800c25af  mov     rdi, r9
0x1800c25b2  mov     rsi, r8
0x1800c25b5  mov     r13, rcx
0x1800c25b8  mov     ebx, 80070057h
0x1800c25bd  test    r8, r8
0x1800c25c0  jz      loc_1800C2792
0x1800c25c6  test    r9, r9
0x1800c25c9  jz      loc_1800C2792
0x1800c25cf  mov     rcx, r8; struct _ITEMIDLIST_RELATIVE *
0x1800c25d2  call    ?ILIsEmpty@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsEmpty(_ITEMIDLIST_RELATIVE const *)
0x1800c25d7  test    eax, eax
0x1800c25d9  jnz     loc_1800C2792
0x1800c25df  mov     rcx, r9; struct _ITEMIDLIST_RELATIVE *
0x1800c25e2  call    ?ILIsEmpty@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsEmpty(_ITEMIDLIST_RELATIVE const *)
0x1800c25e7  test    eax, eax
0x1800c25e9  jnz     loc_1800C2792
0x1800c25ef  cmp     r8, r9
0x1800c25f2  jnz     short loc_1800C25FB
0x1800c25f4  xor     ebx, ebx
0x1800c25f6  jmp     loc_1800C2792
0x1800c25fb  xor     r14d, r14d
0x1800c25fe  mov     rcx, rsi; struct _ITEMIDLIST_RELATIVE *
0x1800c2601  mov     [rbp+57h+var_A0], r14
0x1800c2605  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x1800c260a  test    eax, eax
0x1800c260c  jz      short loc_1800C2613
0x1800c260e  mov     r12, rsi
0x1800c2611  jmp     short loc_1800C262D
0x1800c2613  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x1800c2617  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x1800c261c  mov     ebx, eax
0x1800c261e  test    eax, eax
0x1800c2620  js      loc_1800C2792
0x1800c2626  mov     r14, [rbp+57h+var_A0]
0x1800c262a  mov     r12, r14
0x1800c262d  xor     r15d, r15d
0x1800c2630  mov     rcx, rdi; struct _ITEMIDLIST_RELATIVE *
0x1800c2633  mov     [rbp+57h+var_A0], r15
0x1800c2637  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x1800c263c  test    eax, eax
0x1800c263e  jz      short loc_1800C2646
0x1800c2640  mov     [rbp+57h+var_A0], rdi
0x1800c2644  jmp     short loc_1800C2661
0x1800c2646  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x1800c264a  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x1800c264f  mov     ebx, eax
0x1800c2651  test    eax, eax
0x1800c2653  js      loc_1800C2789
0x1800c2659  mov     r15, [rbp+57h+var_A0]
0x1800c265d  mov     [rbp+57h+var_A0], r15
0x1800c2661  movzx   edx, word ptr [rbp+57h+var_98]
0x1800c2665  lea     r8, [rbp+57h+var_60]
0x1800c2669  xor     eax, eax
0x1800c266b  xorps   xmm0, xmm0
0x1800c266e  mov     [rbp+57h+var_50], eax
0x1800c2671  mov     rcx, r13
0x1800c2674  mov     rax, [r13+0]
0x1800c2678  movups  [rbp+57h+var_60], xmm0
0x1800c267c  mov     rax, [rax+98h]
0x1800c2683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2688  mov     ebx, eax
0x1800c268a  test    eax, eax
0x1800c268c  js      loc_1800C2780
0x1800c2692  xor     eax, eax
0x1800c2694  xorps   xmm0, xmm0
0x1800c2697  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800c269b  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800c269f  xor     ebx, ebx
0x1800c26a1  lea     ecx, [rax+19h]
0x1800c26a4  call    cs:__imp_IsAppCompatModeEnabled
0x1800c26aa  test    eax, eax
0x1800c26ac  jz      short loc_1800C26B5
0x1800c26ae  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x1800c26b3  mov     ebx, eax
0x1800c26b5  mov     rcx, [r13+0]
0x1800c26b9  lea     r9, [rbp+57h+pvarg]
0x1800c26bd  lea     r8, [rbp+57h+var_60]
0x1800c26c1  mov     rdx, r12
0x1800c26c4  mov     rax, [rcx+88h]
0x1800c26cb  mov     rcx, r13
0x1800c26ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c26d3  test    eax, eax
0x1800c26d5  jns     short loc_1800C26E1
0x1800c26d7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800c26db  call    cs:__imp_VariantInit
0x1800c26e1  mov     rdx, [rbp+57h+var_A0]
0x1800c26e5  lea     r9, [rbp+57h+var2]
0x1800c26e9  xor     eax, eax
0x1800c26eb  lea     r8, [rbp+57h+var_60]
0x1800c26ef  mov     qword ptr [rbp+57h+var2+10h], rax
0x1800c26f3  xorps   xmm0, xmm0
0x1800c26f6  mov     rax, [r13+0]
0x1800c26fa  mov     rcx, r13
0x1800c26fd  movups  xmmword ptr [rbp+57h+var2], xmm0
0x1800c2701  mov     rax, [rax+88h]
0x1800c2708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c270d  test    eax, eax
0x1800c270f  jns     short loc_1800C271B
0x1800c2711  lea     rcx, [rbp+57h+var2]; pvarg
0x1800c2715  call    cs:__imp_VariantInit
0x1800c271b  mov     ecx, 19h
0x1800c2720  call    cs:__imp_IsAppCompatModeEnabled
0x1800c2726  test    eax, eax
0x1800c2728  jz      short loc_1800C2734
0x1800c272a  test    ebx, ebx
0x1800c272c  jnz     short loc_1800C2734
0x1800c272e  call    cs:__imp_CoUninitialize
0x1800c2734  lea     rdx, [rbp+57h+var2]; var2
0x1800c2738  lea     rcx, [rbp+57h+pvarg]; var1
0x1800c273c  call    cs:__imp_VariantCompare
0x1800c2742  test    eax, eax
0x1800c2744  jz      short loc_1800C2758
0x1800c2746  jns     short loc_1800C274F
0x1800c2748  mov     ebx, 0FFFFh
0x1800c274d  jmp     short loc_1800C276C
0x1800c274f  xor     ebx, ebx
0x1800c2751  test    eax, eax
0x1800c2753  setnle  bl
0x1800c2756  jmp     short loc_1800C276C
0x1800c2758  mov     r9, [rbp+57h+var_98]
0x1800c275c  mov     r8, rdi
0x1800c275f  mov     rdx, rsi
0x1800c2762  mov     rcx, r13
0x1800c2765  call    ILCompareRelIDs
0x1800c276a  mov     ebx, eax
0x1800c276c  lea     rcx, [rbp+57h+var2]; pvarg
0x1800c2770  call    cs:__imp_VariantClear
0x1800c2776  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800c277a  call    cs:__imp_VariantClear
0x1800c2780  mov     rcx, r15; pidl
0x1800c2783  call    cs:__imp_ILFree
0x1800c2789  mov     rcx, r14; pidl
0x1800c278c  call    cs:__imp_ILFree
0x1800c2792  mov     eax, ebx
0x1800c2794  mov     rcx, [rbp+57h+var_48]
0x1800c2798  xor     rcx, rsp; StackCookie
0x1800c279b  call    __security_check_cookie
0x1800c27a0  add     rsp, 98h
0x1800c27a7  pop     r15
0x1800c27a9  pop     r14
0x1800c27ab  pop     r13
0x1800c27ad  pop     r12
0x1800c27af  pop     rdi
0x1800c27b0  pop     rsi
0x1800c27b1  pop     rbx
0x1800c27b2  pop     rbp
0x1800c27b3  retn
```

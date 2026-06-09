# CompareIDsImpl(IShellFolder2 *,__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x1800325e4`
- end: `0x180032809`
- name: `?CompareIDsImpl@@YAJPEAUIShellFolder2@@_JPEFBU_ITEMIDLIST_RELATIVE@@2@Z`
- size: `549`
- prototype: `int(struct IShellFolder2 *, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800324b0`
- `0x180039230`
- `0x18003f44c`
- `0x18004087c`
- `0x18004fd70`

## callees

- `0x18002fc24`
- `0x1800325e4`
- `0x180033da4`
- `0x1800347e0`
- `0x18004f070`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x1800327d8`
- `SHELL32!__imp_ILFree` at `0x1800327e1`
- `SHELL32!__imp_ILFree` at `0x1800327d8`
- `SHELL32!__imp_ILFree` at `0x1800327e1`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x1800326f9`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x180032775`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x1800326f9`
- `SHLWAPI!__imp_IsAppCompatModeEnabled` at `0x180032775`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180032783`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180032783`
- `PROPSYS!VariantCompare` at `0x180032791`
- `PROPSYS!VariantCompare` at `0x180032791`
- `OLEAUT32!__imp_VariantInit` at `0x180032730`
- `OLEAUT32!__imp_VariantInit` at `0x18003276a`
- `OLEAUT32!__imp_VariantInit` at `0x180032730`
- `OLEAUT32!__imp_VariantInit` at `0x18003276a`
- `OLEAUT32!__imp_VariantClear` at `0x1800327c5`
- `OLEAUT32!__imp_VariantClear` at `0x1800327cf`
- `OLEAUT32!__imp_VariantClear` at `0x1800327c5`
- `OLEAUT32!__imp_VariantClear` at `0x1800327cf`

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
  const WCHAR *v14; // rdx
  int v15; // ebx
  struct IShellFolder2Vtbl *v16; // rax
  const WCHAR *v17; // rdx
  int v18; // eax
  struct _ITEMID_CHILD *v20; // [rsp+30h] [rbp-49h] BYREF
  __int64 v21; // [rsp+38h] [rbp-41h]
  VARIANTARG var2; // [rsp+40h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-21h] BYREF
  __int128 v24; // [rsp+70h] [rbp-9h] BYREF
  int v25; // [rsp+80h] [rbp+7h]

  v4 = 0;
  v21 = a2;
  v8 = -2147024809;
  if ( a3 && a4 && *(_WORD *)a3 && *(_WORD *)a4 )
  {
    if ( a3 == a4 )
      return 0;
    v20 = 0;
    v9 = 0;
    if ( (unsigned int)ILIsChild(a3) )
    {
      v11 = a3;
    }
    else
    {
      v8 = SHILCloneFirst(v10, &v20);
      if ( v8 < 0 )
        return (unsigned int)v8;
      v9 = (ITEMIDLIST *)v20;
      v11 = v20;
    }
    v20 = 0;
    if ( (unsigned int)ILIsChild(a4) )
    {
      v20 = a4;
    }
    else
    {
      v8 = SHILCloneFirst(v12, &v20);
      if ( v8 < 0 )
      {
LABEL_32:
        ILFree(v9);
        return (unsigned int)v8;
      }
      v4 = (ITEMIDLIST *)v20;
    }
    v25 = 0;
    lpVtbl = a1->lpVtbl;
    v24 = 0;
    v8 = ((__int64 (__fastcall *)(struct IShellFolder2 *, _QWORD, __int128 *))lpVtbl->MapColumnToSCID)(
           a1,
           (unsigned __int16)v21,
           &v24);
    if ( v8 >= 0 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      v15 = 0;
      if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v14) )
        v15 = SHCoInitialize();
      if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANTARG *))a1->lpVtbl->GetDetailsEx)(
             a1,
             v11,
             &v24,
             &pvarg) < 0 )
        VariantInit(&pvarg);
      v16 = a1->lpVtbl;
      memset(&var2, 0, sizeof(var2));
      if ( ((int (__fastcall *)(struct IShellFolder2 *, struct _ITEMID_CHILD *, __int128 *, VARIANTARG *))v16->GetDetailsEx)(
             a1,
             v20,
             &v24,
             &var2) < 0 )
        VariantInit(&var2);
      if ( IsAppCompatModeEnabled((LPCWSTR)0x19, v17) && !v15 )
        CoUninitialize();
      v18 = VariantCompare(&pvarg, &var2);
      if ( v18 )
      {
        if ( v18 >= 0 )
          v8 = v18 > 0;
        else
          v8 = 0xFFFF;
      }
      else
      {
        v8 = ILCompareRelIDs(a1, a3, a4, v21);
      }
      VariantClear(&var2);
      VariantClear(&pvarg);
    }
    ILFree(v4);
    goto LABEL_32;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800325e4  push    rbp
0x1800325e6  push    rbx
0x1800325e7  push    rsi
0x1800325e8  push    rdi
0x1800325e9  push    r12
0x1800325eb  push    r13
0x1800325ed  push    r14
0x1800325ef  push    r15
0x1800325f1  lea     rbp, [rsp-1Fh]
0x1800325f6  sub     rsp, 98h
0x1800325fd  mov     rax, cs:__security_cookie
0x180032604  xor     rax, rsp
0x180032607  mov     [rbp+57h+var_48], rax
0x18003260b  xor     r15d, r15d
0x18003260e  mov     [rbp+57h+var_98], rdx
0x180032612  mov     rdi, r9
0x180032615  mov     rsi, r8
0x180032618  mov     r13, rcx
0x18003261b  mov     ebx, 80070057h
0x180032620  test    r8, r8
0x180032623  jz      loc_1800327E7
0x180032629  test    r9, r9
0x18003262c  jz      loc_1800327E7
0x180032632  cmp     [r8], r15w
0x180032636  jz      loc_1800327E7
0x18003263c  cmp     [r9], r15w
0x180032640  jz      loc_1800327E7
0x180032646  cmp     r8, r9
0x180032649  jnz     short loc_180032653
0x18003264b  mov     ebx, r15d
0x18003264e  jmp     loc_1800327E7
0x180032653  mov     rcx, rsi; struct _ITEMIDLIST_RELATIVE *
0x180032656  mov     [rbp+57h+var_A0], r15
0x18003265a  mov     r14, r15
0x18003265d  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x180032662  test    eax, eax
0x180032664  jz      short loc_18003266B
0x180032666  mov     r12, rsi
0x180032669  jmp     short loc_180032685
0x18003266b  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x18003266f  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x180032674  mov     ebx, eax
0x180032676  test    eax, eax
0x180032678  js      loc_1800327E7
0x18003267e  mov     r14, [rbp+57h+var_A0]
0x180032682  mov     r12, r14
0x180032685  mov     rcx, rdi; struct _ITEMIDLIST_RELATIVE *
0x180032688  mov     [rbp+57h+var_A0], r15
0x18003268c  call    ?ILIsChild@@YAHPEFBU_ITEMIDLIST_RELATIVE@@@Z; ILIsChild(_ITEMIDLIST_RELATIVE const *)
0x180032691  test    eax, eax
0x180032693  jz      short loc_18003269B
0x180032695  mov     [rbp+57h+var_A0], rdi
0x180032699  jmp     short loc_1800326B6
0x18003269b  lea     rdx, [rbp+57h+var_A0]; struct _ITEMID_CHILD **
0x18003269f  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x1800326a4  mov     ebx, eax
0x1800326a6  test    eax, eax
0x1800326a8  js      loc_1800327DE
0x1800326ae  mov     r15, [rbp+57h+var_A0]
0x1800326b2  mov     [rbp+57h+var_A0], r15
0x1800326b6  movzx   edx, word ptr [rbp+57h+var_98]
0x1800326ba  lea     r8, [rbp+57h+var_60]
0x1800326be  xor     eax, eax
0x1800326c0  xorps   xmm0, xmm0
0x1800326c3  mov     [rbp+57h+var_50], eax
0x1800326c6  mov     rcx, r13
0x1800326c9  mov     rax, [r13+0]
0x1800326cd  movups  [rbp+57h+var_60], xmm0
0x1800326d1  mov     rax, [rax+98h]
0x1800326d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800326dd  mov     ebx, eax
0x1800326df  test    eax, eax
0x1800326e1  js      loc_1800327D5
0x1800326e7  xor     eax, eax
0x1800326e9  xorps   xmm0, xmm0
0x1800326ec  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800326f0  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800326f4  xor     ebx, ebx
0x1800326f6  lea     ecx, [rax+19h]; pszPath
0x1800326f9  call    cs:__imp_IsAppCompatModeEnabled
0x1800326ff  test    eax, eax
0x180032701  jz      short loc_18003270A
0x180032703  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180032708  mov     ebx, eax
0x18003270a  mov     rcx, [r13+0]
0x18003270e  lea     r9, [rbp+57h+pvarg]
0x180032712  lea     r8, [rbp+57h+var_60]
0x180032716  mov     rdx, r12
0x180032719  mov     rax, [rcx+88h]
0x180032720  mov     rcx, r13
0x180032723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032728  test    eax, eax
0x18003272a  jns     short loc_180032736
0x18003272c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180032730  call    cs:__imp_VariantInit
0x180032736  mov     rdx, [rbp+57h+var_A0]
0x18003273a  lea     r9, [rbp+57h+var2]
0x18003273e  xor     eax, eax
0x180032740  lea     r8, [rbp+57h+var_60]
0x180032744  mov     qword ptr [rbp+57h+var2+10h], rax
0x180032748  xorps   xmm0, xmm0
0x18003274b  mov     rax, [r13+0]
0x18003274f  mov     rcx, r13
0x180032752  movups  xmmword ptr [rbp+57h+var2], xmm0
0x180032756  mov     rax, [rax+88h]
0x18003275d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032762  test    eax, eax
0x180032764  jns     short loc_180032770
0x180032766  lea     rcx, [rbp+57h+var2]; pvarg
0x18003276a  call    cs:__imp_VariantInit
0x180032770  mov     ecx, 19h; pszPath
0x180032775  call    cs:__imp_IsAppCompatModeEnabled
0x18003277b  test    eax, eax
0x18003277d  jz      short loc_180032789
0x18003277f  test    ebx, ebx
0x180032781  jnz     short loc_180032789
0x180032783  call    cs:__imp_CoUninitialize
0x180032789  lea     rdx, [rbp+57h+var2]; var2
0x18003278d  lea     rcx, [rbp+57h+pvarg]; var1
0x180032791  call    cs:__imp_VariantCompare
0x180032797  test    eax, eax
0x180032799  jz      short loc_1800327AD
0x18003279b  jns     short loc_1800327A4
0x18003279d  mov     ebx, 0FFFFh
0x1800327a2  jmp     short loc_1800327C1
0x1800327a4  xor     ebx, ebx
0x1800327a6  test    eax, eax
0x1800327a8  setnle  bl
0x1800327ab  jmp     short loc_1800327C1
0x1800327ad  mov     r9, [rbp+57h+var_98]
0x1800327b1  mov     r8, rdi
0x1800327b4  mov     rdx, rsi
0x1800327b7  mov     rcx, r13
0x1800327ba  call    ILCompareRelIDs
0x1800327bf  mov     ebx, eax
0x1800327c1  lea     rcx, [rbp+57h+var2]; pvarg
0x1800327c5  call    cs:__imp_VariantClear
0x1800327cb  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800327cf  call    cs:__imp_VariantClear
0x1800327d5  mov     rcx, r15; pidl
0x1800327d8  call    cs:__imp_ILFree
0x1800327de  mov     rcx, r14; pidl
0x1800327e1  call    cs:__imp_ILFree
0x1800327e7  mov     eax, ebx
0x1800327e9  mov     rcx, [rbp+57h+var_48]
0x1800327ed  xor     rcx, rsp; StackCookie
0x1800327f0  call    __security_check_cookie
0x1800327f5  add     rsp, 98h
0x1800327fc  pop     r15
0x1800327fe  pop     r14
0x180032800  pop     r13
0x180032802  pop     r12
0x180032804  pop     rdi
0x180032805  pop     rsi
0x180032806  pop     rbx
0x180032807  pop     rbp
0x180032808  retn
```

# TaskManager::GetTaskFolder(ITaskService *,ushort const *,bool,ITaskFolder * *)

- ea: `0x140014174`
- end: `0x14001435a`
- name: `?GetTaskFolder@TaskManager@@CAJPEAUITaskService@@PEBG_NPEAPEAUITaskFolder@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(struct ITaskService *, const unsigned __int16 *, char, struct ITaskFolder **)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140013e20`
- `0x140013f34`
- `0x140014038`
- `0x140014488`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x140014174`
- `0x14001c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400141e3`
- `OLEAUT32!__imp_SysAllocString` at `0x14001420c`
- `OLEAUT32!__imp_SysAllocString` at `0x140014243`
- `OLEAUT32!__imp_SysAllocString` at `0x1400141e3`
- `OLEAUT32!__imp_SysAllocString` at `0x14001420c`
- `OLEAUT32!__imp_SysAllocString` at `0x140014243`
- `OLEAUT32!__imp_SysFreeString` at `0x140014314`
- `OLEAUT32!__imp_SysFreeString` at `0x14001431d`
- `OLEAUT32!__imp_SysFreeString` at `0x140014314`
- `OLEAUT32!__imp_SysFreeString` at `0x14001431d`
- `OLEAUT32!__imp_VariantInit` at `0x1400141bf`
- `OLEAUT32!__imp_VariantInit` at `0x1400141bf`
- `OLEAUT32!__imp_VariantClear` at `0x140014327`
- `OLEAUT32!__imp_VariantClear` at `0x140014327`

## string_xrefs

- `0x1400142a9`: `Failed to create task folder.  Error = 0x%1!x!.`
- `0x1400142bf`: `Failed to get the task folder.  Error = 0x%1!x!.`
- `0x140014333`: `GetTaskFolder() failed.  Error = 0x%1!x!.`

## pseudocode

```c
__int64 __fastcall TaskManager::GetTaskFolder(
        struct ITaskService *a1,
        const unsigned __int16 *a2,
        char a3,
        struct ITaskFolder **a4)
{
  OLECHAR *v8; // r14
  OLECHAR *v9; // rsi
  int v10; // ebx
  BSTR v11; // rax
  BSTR v12; // rax
  int v13; // eax
  int v14; // edi
  __int64 v15; // rax
  __int64 *v17; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v19; // [rsp+50h] [rbp-20h] BYREF
  struct ITaskFolder *v20; // [rsp+A0h] [rbp+30h] BYREF

  v17 = 0;
  v20 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v8 = 0;
  v9 = 0;
  VariantInit(&pvarg);
  if ( !a1 || !a2 )
  {
    v10 = -2147024809;
    goto LABEL_18;
  }
  *a4 = 0;
  pvarg.llVal = (LONGLONG)SysAllocString(&word_14001E5B4);
  if ( !pvarg.llVal )
    goto LABEL_5;
  pvarg.vt = 8;
  v11 = SysAllocString(L"\\");
  v8 = v11;
  if ( !v11 )
    goto LABEL_5;
  v10 = ((__int64 (__fastcall *)(struct ITaskService *, BSTR, __int64 **))a1->lpVtbl->GetFolder)(a1, v11, &v17);
  if ( v10 < 0 )
    goto LABEL_18;
  if ( !v17 || (v12 = SysAllocString(a2), (v9 = v12) == 0) )
  {
LABEL_5:
    v10 = -2147024882;
    goto LABEL_18;
  }
  v13 = (*(__int64 (__fastcall **)(__int64 *, BSTR, struct ITaskFolder **))(*v17 + 72))(v17, v12, &v20);
  v14 = v13;
  if ( a3 && v13 == -2147024894 )
  {
    v15 = *v17;
    v19 = pvarg;
    v14 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, VARIANTARG *, struct ITaskFolder **))(v15 + 88))(
            v17,
            v9,
            &v19,
            &v20);
    if ( v14 < 0 )
    {
      LogInfo(L"Failed to create task folder.  Error = 0x%1!x!.", (unsigned int)v14);
LABEL_14:
      v10 = v14;
      goto LABEL_18;
    }
  }
  else if ( v13 < 0 )
  {
    LogInfo(L"Failed to get the task folder.  Error = 0x%1!x!.", (unsigned int)v13);
    goto LABEL_14;
  }
  *a4 = v20;
  v20 = 0;
LABEL_18:
  if ( v20 )
  {
    ((void (__fastcall *)(struct ITaskFolder *))v20->lpVtbl->Release)(v20);
    v20 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
    v17 = 0;
  }
  SysFreeString(v8);
  SysFreeString(v9);
  VariantClear(&pvarg);
  if ( v10 < 0 )
    LogError(L"GetTaskFolder() failed.  Error = 0x%1!x!.", (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140014174  mov     [rsp-28h+arg_8], rbx
0x140014179  mov     [rsp-28h+arg_10], rsi
0x14001417e  push    rbp
0x14001417f  push    rdi
0x140014180  push    r12
0x140014182  push    r14
0x140014184  push    r15
0x140014186  mov     rbp, rsp
0x140014189  sub     rsp, 70h
0x14001418d  mov     rbx, rcx
0x140014190  mov     [rbp+var_40], 0
0x140014198  xorps   xmm0, xmm0
0x14001419b  mov     [rbp+arg_0], 0
0x1400141a3  xor     eax, eax
0x1400141a5  lea     rcx, [rbp+pvarg]; pvarg
0x1400141a9  movups  xmmword ptr [rbp+pvarg], xmm0
0x1400141ad  mov     qword ptr [rbp+pvarg+10h], rax
0x1400141b1  mov     r15, r9
0x1400141b4  mov     r12b, r8b
0x1400141b7  mov     rdi, rdx
0x1400141ba  xor     r14d, r14d
0x1400141bd  xor     esi, esi
0x1400141bf  call    cs:__imp_VariantInit
0x1400141c5  test    rbx, rbx
0x1400141c8  jnz     short loc_1400141D4
0x1400141ca  mov     ebx, 80070057h
0x1400141cf  jmp     loc_1400142D7
0x1400141d4  test    rdi, rdi
0x1400141d7  jz      short loc_1400141CA
0x1400141d9  lea     rcx, word_14001E5B4; psz
0x1400141e0  mov     [r15], rsi
0x1400141e3  call    cs:__imp_SysAllocString
0x1400141e9  mov     qword ptr [rbp+pvarg+8], rax
0x1400141ed  test    rax, rax
0x1400141f0  jnz     short loc_1400141FC
0x1400141f2  mov     ebx, 8007000Eh
0x1400141f7  jmp     loc_1400142D7
0x1400141fc  mov     eax, 8
0x140014201  lea     rcx, asc_140022784; "\\"
0x140014208  mov     word ptr [rbp+pvarg], ax
0x14001420c  call    cs:__imp_SysAllocString
0x140014212  mov     r14, rax
0x140014215  test    rax, rax
0x140014218  jz      short loc_1400141F2
0x14001421a  mov     rax, [rbx]
0x14001421d  lea     r8, [rbp+var_40]
0x140014221  mov     rdx, r14
0x140014224  mov     rcx, rbx
0x140014227  mov     rax, [rax+38h]
0x14001422b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014230  mov     ebx, eax
0x140014232  test    eax, eax
0x140014234  js      loc_1400142D7
0x14001423a  cmp     [rbp+var_40], rsi
0x14001423e  jz      short loc_1400141F2
0x140014240  mov     rcx, rdi; psz
0x140014243  call    cs:__imp_SysAllocString
0x140014249  mov     rsi, rax
0x14001424c  test    rax, rax
0x14001424f  jz      short loc_1400141F2
0x140014251  mov     rcx, [rbp+var_40]
0x140014255  lea     r8, [rbp+arg_0]
0x140014259  mov     rdx, rsi
0x14001425c  mov     rax, [rcx]
0x14001425f  mov     rax, [rax+48h]
0x140014263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014268  mov     edi, eax
0x14001426a  test    r12b, r12b
0x14001426d  jz      short loc_1400142BB
0x14001426f  cmp     eax, 80070002h
0x140014274  jnz     short loc_1400142BB
0x140014276  mov     rcx, [rbp+var_40]
0x14001427a  lea     r9, [rbp+arg_0]
0x14001427e  movups  xmm0, xmmword ptr [rbp+pvarg]
0x140014282  lea     r8, [rbp+var_20]
0x140014286  mov     rdx, rsi
0x140014289  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x14001428e  mov     rax, [rcx]
0x140014291  movaps  [rbp+var_20], xmm0
0x140014295  movsd   [rbp+var_10], xmm1
0x14001429a  mov     rax, [rax+58h]
0x14001429e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400142a3  mov     edi, eax
0x1400142a5  test    eax, eax
0x1400142a7  jns     short loc_1400142C8
0x1400142a9  lea     rcx, aFailedToCreate_5; "Failed to create task folder.  Error = "...
0x1400142b0  mov     edx, edi
0x1400142b2  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x1400142b7  mov     ebx, edi
0x1400142b9  jmp     short loc_1400142D7
0x1400142bb  test    edi, edi
0x1400142bd  jns     short loc_1400142C8
0x1400142bf  lea     rcx, aFailedToGetThe; "Failed to get the task folder.  Error ="...
0x1400142c6  jmp     short loc_1400142B0
0x1400142c8  mov     rax, [rbp+arg_0]
0x1400142cc  mov     [r15], rax
0x1400142cf  mov     [rbp+arg_0], 0
0x1400142d7  mov     rcx, [rbp+arg_0]
0x1400142db  test    rcx, rcx
0x1400142de  jz      short loc_1400142F4
0x1400142e0  mov     rax, [rcx]
0x1400142e3  mov     rax, [rax+10h]
0x1400142e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400142ec  mov     [rbp+arg_0], 0
0x1400142f4  mov     rcx, [rbp+var_40]
0x1400142f8  test    rcx, rcx
0x1400142fb  jz      short loc_140014311
0x1400142fd  mov     rax, [rcx]
0x140014300  mov     rax, [rax+10h]
0x140014304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014309  mov     [rbp+var_40], 0
0x140014311  mov     rcx, r14; bstrString
0x140014314  call    cs:__imp_SysFreeString
0x14001431a  mov     rcx, rsi; bstrString
0x14001431d  call    cs:__imp_SysFreeString
0x140014323  lea     rcx, [rbp+pvarg]; pvarg
0x140014327  call    cs:__imp_VariantClear
0x14001432d  test    ebx, ebx
0x14001432f  jns     short loc_14001433F
0x140014331  mov     edx, ebx
0x140014333  lea     rcx, aGettaskfolderF; "GetTaskFolder() failed.  Error = 0x%1!x"...
0x14001433a  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14001433f  lea     r11, [rsp+70h+var_s0]
0x140014344  mov     eax, ebx
0x140014346  mov     rbx, [r11+38h]
0x14001434a  mov     rsi, [r11+40h]
0x14001434e  mov     rsp, r11
0x140014351  pop     r15
0x140014353  pop     r14
0x140014355  pop     r12
0x140014357  pop     rdi
0x140014358  pop     rbp
0x140014359  retn
```

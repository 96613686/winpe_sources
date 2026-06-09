# MapIIDToFusionTypeInfo(_GUID const &,ITypeInfo * *)

- ea: `0x1800128fc`
- end: `0x180012ac0`
- name: `?MapIIDToFusionTypeInfo@@YAJAEBU_GUID@@PEAPEAUITypeInfo@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(const struct _GUID *, struct ITypeInfo **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012020`

## callees

- `0x1800128fc`
- `0x180012b70`
- `0x18004d900`
- `0x18004d924`
- `0x18004dd00`
- `0x18004ebb0`
- `0x18009c010`

## import_xrefs

- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapIIDToTLBPath` at `0x180012974`
- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapIIDToTLBPath` at `0x180012a95`
- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapIIDToTLBPath` at `0x180012974`
- `ext-ms-win-sxs-oleautomation-l1-1-0!SxsOleAut32MapIIDToTLBPath` at `0x180012a95`

## pseudocode

```c
__int64 __fastcall MapIIDToFusionTypeInfo(const struct _GUID *a1, struct ITypeInfo **a2)
{
  ITypeLib *v4; // rdi
  OLECHAR *v5; // r14
  unsigned __int64 v6; // rdx
  int v7; // ebx
  OLECHAR *v8; // rsi
  struct ITypeInfo *v9; // rcx
  HRESULT v11; // eax
  unsigned __int64 v12; // rbx
  OLECHAR *v13; // rax
  struct ITypeInfo *v14; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v15; // [rsp+28h] [rbp-D8h] BYREF
  ITypeLib *pptlib; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR szFile[264]; // [rsp+40h] [rbp-C0h] BYREF

  v14 = 0;
  v15 = 0;
  if ( !(unsigned __int8)IsSxsOleAut32MapConfiguredClsidToReferenceClsidPresent(a1) )
    return 1;
  v4 = 0;
  pptlib = 0;
  v14 = 0;
  v5 = 0;
  v7 = SxsOleAut32MapIIDToTLBPath(a1, 260, szFile, &v15);
  if ( v7 == -2147024774 )
  {
    v12 = v15;
    v13 = (OLECHAR *)operator new[](saturated_mul(v15, 2u));
    v8 = v13;
    if ( !v13 )
    {
      v7 = -2147024882;
      goto LABEL_5;
    }
    v5 = v13;
    v7 = SxsOleAut32MapIIDToTLBPath(a1, v12, v13, &v15);
  }
  else
  {
    v8 = szFile;
  }
  if ( v7 >= 0 && v7 != 1 )
  {
    v11 = LoadTypeLibEx(v8, REGKIND_DEFAULT, &pptlib);
    v4 = pptlib;
    v7 = v11;
    if ( v11 >= 0 )
    {
      v7 = ((__int64 (__fastcall *)(ITypeLib *, const struct _GUID *, struct ITypeInfo **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
             pptlib,
             a1,
             &v14);
      if ( v7 >= 0 )
      {
        v9 = 0;
        *a2 = v14;
        v7 = 0;
        v14 = 0;
        goto LABEL_6;
      }
    }
  }
LABEL_5:
  v9 = v14;
LABEL_6:
  if ( v9 )
    ((void (__fastcall *)(struct ITypeInfo *))v9->lpVtbl->Release)(v9);
  if ( v4 )
    ((void (__fastcall *)(ITypeLib *))v4->lpVtbl->Release)(v4);
  if ( v5 )
    operator delete(v5, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800128fc  mov     [rsp-8+arg_10], rbx
0x180012901  mov     [rsp-8+arg_18], rsi
0x180012906  push    rbp
0x180012907  push    rdi
0x180012908  push    r12
0x18001290a  push    r14
0x18001290c  push    r15
0x18001290e  lea     rbp, [rsp-160h]
0x180012916  sub     rsp, 260h
0x18001291d  mov     rax, cs:__security_cookie
0x180012924  xor     rax, rsp
0x180012927  mov     [rbp+180h+var_30], rax
0x18001292e  mov     r12, rdx
0x180012931  mov     [rsp+280h+var_260], 0
0x18001293a  mov     r15, rcx
0x18001293d  mov     [rsp+280h+var_258], 0
0x180012946  call    IsSxsOleAut32MapConfiguredClsidToReferenceClsidPresent
0x18001294b  test    al, al
0x18001294d  jz      loc_180012A48
0x180012953  xor     edi, edi
0x180012955  lea     r9, [rsp+280h+var_258]
0x18001295a  lea     r8, [rsp+280h+szFile]
0x18001295f  mov     [rsp+280h+pptlib], rdi
0x180012964  mov     edx, 104h
0x180012969  mov     [rsp+280h+var_260], rdi
0x18001296e  mov     rcx, r15
0x180012971  xor     r14d, r14d
0x180012974  call    cs:__imp_SxsOleAut32MapIIDToTLBPath
0x18001297a  mov     ebx, eax
0x18001297c  cmp     eax, 8007007Ah
0x180012981  jz      loc_180012A52
0x180012987  lea     rsi, [rsp+280h+szFile]
0x18001298c  test    ebx, ebx
0x18001298e  jns     short loc_1800129DD
0x180012990  mov     rcx, [rsp+280h+var_260]
0x180012995  test    rcx, rcx
0x180012998  jnz     loc_180012AA2
0x18001299e  test    rdi, rdi
0x1800129a1  jnz     loc_180012A34
0x1800129a7  test    r14, r14
0x1800129aa  jnz     loc_180012AB3
0x1800129b0  mov     eax, ebx
0x1800129b2  mov     rcx, [rbp+180h+var_30]
0x1800129b9  xor     rcx, rsp; StackCookie
0x1800129bc  call    __security_check_cookie
0x1800129c1  lea     r11, [rsp+280h+var_20]
0x1800129c9  mov     rbx, [r11+40h]
0x1800129cd  mov     rsi, [r11+48h]
0x1800129d1  mov     rsp, r11
0x1800129d4  pop     r15
0x1800129d6  pop     r14
0x1800129d8  pop     r12
0x1800129da  pop     rdi
0x1800129db  pop     rbp
0x1800129dc  retn
0x1800129dd  cmp     ebx, 1
0x1800129e0  jz      short loc_180012990
0x1800129e2  lea     r8, [rsp+280h+pptlib]; pptlib
0x1800129e7  xor     edx, edx; regkind
0x1800129e9  mov     rcx, rsi; szFile
0x1800129ec  call    LoadTypeLibEx
0x1800129f1  mov     rdi, [rsp+280h+pptlib]
0x1800129f6  mov     ebx, eax
0x1800129f8  test    eax, eax
0x1800129fa  js      short loc_180012990
0x1800129fc  mov     rax, [rdi]
0x1800129ff  lea     r8, [rsp+280h+var_260]
0x180012a04  mov     rdx, r15
0x180012a07  mov     rcx, rdi
0x180012a0a  mov     rax, [rax+30h]
0x180012a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a13  mov     ebx, eax
0x180012a15  test    eax, eax
0x180012a17  js      loc_180012990
0x180012a1d  mov     rax, [rsp+280h+var_260]
0x180012a22  xor     ecx, ecx
0x180012a24  mov     [r12], rax
0x180012a28  xor     ebx, ebx
0x180012a2a  mov     [rsp+280h+var_260], rcx
0x180012a2f  jmp     loc_180012995
0x180012a34  mov     rax, [rdi]
0x180012a37  mov     rcx, rdi
0x180012a3a  mov     rax, [rax+10h]
0x180012a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a43  jmp     loc_1800129A7
0x180012a48  mov     eax, 1
0x180012a4d  jmp     loc_1800129B2
0x180012a52  mov     rbx, [rsp+280h+var_258]
0x180012a57  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180012a5e  mov     eax, 2
0x180012a63  mul     rbx
0x180012a66  cmovb   rax, rcx
0x180012a6a  mov     rcx, rax; unsigned __int64
0x180012a6d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012a72  mov     rsi, rax
0x180012a75  test    rax, rax
0x180012a78  jnz     short loc_180012A84
0x180012a7a  mov     ebx, 8007000Eh
0x180012a7f  jmp     loc_180012990
0x180012a84  lea     r9, [rsp+280h+var_258]
0x180012a89  mov     r8, rax
0x180012a8c  mov     rdx, rbx
0x180012a8f  mov     rcx, r15
0x180012a92  mov     r14, rax
0x180012a95  call    cs:__imp_SxsOleAut32MapIIDToTLBPath
0x180012a9b  mov     ebx, eax
0x180012a9d  jmp     loc_18001298C
0x180012aa2  mov     rax, [rcx]
0x180012aa5  mov     rax, [rax+10h]
0x180012aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012aae  jmp     loc_18001299E
0x180012ab3  mov     rcx, r14; void *
0x180012ab6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012abb  jmp     loc_1800129B0
```

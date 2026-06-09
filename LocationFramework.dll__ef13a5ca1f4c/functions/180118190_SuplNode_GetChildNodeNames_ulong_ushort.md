# SuplNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180118190`
- end: `0x18011831d`
- name: `?GetChildNodeNames@SuplNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `397`
- prototype: `__int64 __fastcall(SuplNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800a98c0`
- `0x1800aa5ac`
- `0x180118190`
- `0x18011885c`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18011829f`
- `OLEAUT32!__imp_SysAllocString` at `0x18011829f`
- `OLEAUT32!__imp_SysFreeString` at `0x1801182cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1801182cd`
- `OLEAUT32!__imp_VariantInit` at `0x18011826c`
- `OLEAUT32!__imp_VariantInit` at `0x18011826c`
- `OLEAUT32!__imp_VariantClear` at `0x180118289`
- `OLEAUT32!__imp_VariantClear` at `0x180118289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801181fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801181fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801182df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801182df`

## pseudocode

```c
__int64 __fastcall SuplNode::GetChildNodeNames(SuplNode *this, unsigned int *a2, unsigned __int16 ***a3)
{
  unsigned int v3; // r12d
  unsigned int i; // ebx
  unsigned __int64 v8; // rbp
  unsigned __int16 **v9; // rax
  unsigned __int16 **v10; // rdi
  unsigned int v11; // esi
  wchar_t **v12; // rbx
  SuplNode *v13; // rcx
  int Value; // ebx
  BSTR v15; // rax
  __int64 v16; // rsi
  wchar_t **v18; // [rsp+20h] [rbp-68h]
  VARIANTARG pvarg; // [rsp+28h] [rbp-60h] BYREF

  v3 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v8 = *(_QWORD *)(*((_QWORD *)this + 8) + 24LL);
  *a2 = 0;
  *a3 = 0;
  if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 24LL) )
    return (unsigned int)-2046820335;
  v9 = (unsigned __int16 **)CoTaskMemAlloc(8 * v8);
  v10 = v9;
  if ( !v9 )
    return (unsigned int)-2147024882;
  v11 = 0;
  memset_0(v9, 0, 8 * v8);
  while ( 1 )
  {
    if ( v3 >= v8 )
    {
      *a2 = v11;
      i = 0;
      *a3 = v10;
      return i;
    }
    v12 = &(&off_1801691B0)[10 * *(int *)(*(_QWORD *)(*((_QWORD *)this + 8) + 16LL) + 4LL * v3)];
    v18 = v12;
    if ( !v12[3] )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      Value = SuplNode::InternalGetValue(v13, (const struct SUPLNODEINFO *)v12, 0, &pvarg);
      VariantClear(&pvarg);
      if ( Value == -2046820350 )
        goto LABEL_14;
      v12 = v18;
    }
    v15 = SysAllocString(*v12);
    v10[v11] = v15;
    if ( !v15 )
      break;
    ++v11;
LABEL_14:
    ++v3;
  }
  v16 = 0;
  for ( i = -2147024882; (unsigned int)v16 < v8; v16 = (unsigned int)(v16 + 1) )
    SysFreeString(v10[v16]);
  CoTaskMemFree(v10);
  return i;
}

```

## disassembly

```asm
0x180118190  mov     [rsp+arg_18], rbx
0x180118195  push    rbp
0x180118196  push    rsi
0x180118197  push    rdi
0x180118198  push    r12
0x18011819a  push    r13
0x18011819c  push    r14
0x18011819e  push    r15
0x1801181a0  sub     rsp, 50h
0x1801181a4  mov     rax, cs:__security_cookie
0x1801181ab  xor     rax, rsp
0x1801181ae  mov     [rsp+88h+var_48], rax
0x1801181b3  xor     r12d, r12d
0x1801181b6  mov     r14, r8
0x1801181b9  mov     r15, rdx
0x1801181bc  mov     r13, rcx
0x1801181bf  test    rdx, rdx
0x1801181c2  jnz     short loc_1801181CE
0x1801181c4  mov     ebx, 80070057h
0x1801181c9  jmp     loc_1801182F6
0x1801181ce  test    r14, r14
0x1801181d1  jz      short loc_1801181C4
0x1801181d3  mov     rax, [rcx+40h]
0x1801181d7  mov     rbp, [rax+18h]
0x1801181db  mov     [rdx], r12d
0x1801181de  mov     [r8], r12
0x1801181e1  mov     rax, [rcx+40h]
0x1801181e5  cmp     [rax+18h], r12
0x1801181e9  jz      loc_1801182F1
0x1801181ef  lea     rbx, ds:0[rbp*8]
0x1801181f7  mov     rcx, rbx; cb
0x1801181fa  call    cs:__imp_CoTaskMemAlloc
0x180118200  mov     rdi, rax
0x180118203  test    rax, rax
0x180118206  jnz     short loc_180118212
0x180118208  mov     ebx, 8007000Eh
0x18011820d  jmp     loc_1801182F6
0x180118212  mov     r8, rbx; Size
0x180118215  xor     edx, edx; Val
0x180118217  mov     rcx, rdi; void *
0x18011821a  mov     esi, r12d
0x18011821d  call    memset_0
0x180118222  mov     edx, r12d
0x180118225  cmp     rdx, rbp
0x180118228  jnb     loc_1801182E7
0x18011822e  mov     rax, [r13+40h]
0x180118232  mov     rcx, [rax+10h]
0x180118236  movsxd  rax, dword ptr [rcx+rdx*4]
0x18011823a  lea     rbx, [rax+rax*4]
0x18011823e  shl     rbx, 4
0x180118242  lea     rax, off_1801691B0; "SUPL"
0x180118249  add     rbx, rax
0x18011824c  mov     [rsp+88h+var_68], rbx
0x180118251  cmp     qword ptr [rbx+18h], 0
0x180118256  jnz     short loc_18011829C
0x180118258  xorps   xmm0, xmm0
0x18011825b  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180118260  xor     eax, eax
0x180118262  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x180118267  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x18011826c  call    cs:__imp_VariantInit
0x180118272  lea     r9, [rsp+88h+pvarg]; struct tagVARIANT *
0x180118277  xor     r8d, r8d; unsigned __int16 *
0x18011827a  mov     rdx, rbx; struct SUPLNODEINFO *
0x18011827d  call    ?InternalGetValue@SuplNode@@AEAAJPEBUSUPLNODEINFO@@PEBGPEAUtagVARIANT@@@Z; SuplNode::InternalGetValue(SUPLNODEINFO const *,ushort const *,tagVARIANT *)
0x180118282  lea     rcx, [rsp+88h+pvarg]; pvarg
0x180118287  mov     ebx, eax
0x180118289  call    cs:__imp_VariantClear
0x18011828f  cmp     ebx, 86000002h
0x180118295  jz      short loc_1801182B5
0x180118297  mov     rbx, [rsp+88h+var_68]
0x18011829c  mov     rcx, [rbx]; psz
0x18011829f  call    cs:__imp_SysAllocString
0x1801182a5  mov     rcx, rax
0x1801182a8  mov     eax, esi
0x1801182aa  mov     [rdi+rax*8], rcx
0x1801182ae  test    rcx, rcx
0x1801182b1  jz      short loc_1801182BD
0x1801182b3  inc     esi
0x1801182b5  inc     r12d
0x1801182b8  jmp     loc_180118222
0x1801182bd  xor     esi, esi
0x1801182bf  mov     ebx, 8007000Eh
0x1801182c4  test    rbp, rbp
0x1801182c7  jz      short loc_1801182DC
0x1801182c9  mov     rcx, [rdi+rsi*8]; bstrString
0x1801182cd  call    cs:__imp_SysFreeString
0x1801182d3  inc     esi
0x1801182d5  mov     eax, esi
0x1801182d7  cmp     rax, rbp
0x1801182da  jb      short loc_1801182C9
0x1801182dc  mov     rcx, rdi; pv
0x1801182df  call    cs:__imp_CoTaskMemFree
0x1801182e5  jmp     short loc_1801182F6
0x1801182e7  mov     [r15], esi
0x1801182ea  xor     ebx, ebx
0x1801182ec  mov     [r14], rdi
0x1801182ef  jmp     short loc_1801182F6
0x1801182f1  mov     ebx, 86000011h
0x1801182f6  mov     eax, ebx
0x1801182f8  mov     rcx, [rsp+88h+var_48]
0x1801182fd  xor     rcx, rsp; StackCookie
0x180118300  call    __security_check_cookie
0x180118305  mov     rbx, [rsp+88h+arg_18]
0x18011830d  add     rsp, 50h
0x180118311  pop     r15
0x180118313  pop     r14
0x180118315  pop     r13
0x180118317  pop     r12
0x180118319  pop     rdi
0x18011831a  pop     rsi
0x18011831b  pop     rbp
0x18011831c  retn
```

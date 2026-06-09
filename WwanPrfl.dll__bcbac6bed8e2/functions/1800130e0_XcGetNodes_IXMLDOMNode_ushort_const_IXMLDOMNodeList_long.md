# XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)

- ea: `0x1800130e0`
- end: `0x1800131de`
- name: `?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z`
- size: `254`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMNodeList **, int *)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b880`
- `0x18000c050`
- `0x18000c280`
- `0x18000f510`
- `0x180010820`
- `0x180010a24`
- `0x1800114a0`
- `0x180011974`
- `0x1800131e4`

## callees

- `0x1800030fc`
- `0x1800130e0`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180013112`
- `OLEAUT32!__imp_SysAllocString` at `0x180013112`
- `OLEAUT32!__imp_SysFreeString` at `0x180013109`
- `OLEAUT32!__imp_SysFreeString` at `0x180013126`
- `OLEAUT32!__imp_SysFreeString` at `0x1800131cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180013109`
- `OLEAUT32!__imp_SysFreeString` at `0x180013126`
- `OLEAUT32!__imp_SysFreeString` at `0x1800131cc`

## pseudocode

```c
__int64 __fastcall XcGetNodes(struct IXMLDOMNode *a1, const unsigned __int16 *a2, struct IXMLDOMNodeList **a3, int *a4)
{
  OLECHAR *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  struct IXMLDOMNodeList *v12; // rax
  int v14; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v15[6]; // [rsp+28h] [rbp-30h] BYREF

  v15[0] = 0;
  v14 = 0;
  SysFreeString(0);
  v8 = SysAllocString(a2);
  if ( !v8 )
  {
    v8 = 0;
    v10 = 14;
    goto LABEL_16;
  }
  SysFreeString(0);
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, _QWORD *))a1->lpVtbl->selectNodes)(a1, v8, v15);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v10 = (unsigned __int16)v9;
    if ( v10 )
      goto LABEL_16;
  }
  else
  {
    v10 = 0;
  }
  if ( !a4 )
    goto LABEL_13;
  v11 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v15[0] + 64LL))(v15[0], &v14);
  v10 = v11;
  if ( v11 >= 0 )
  {
    v10 = 0;
LABEL_13:
    v12 = (struct IXMLDOMNodeList *)v15[0];
    v15[0] = 0;
    *a3 = v12;
    if ( a4 )
      *a4 = v14;
    goto LABEL_16;
  }
  if ( (v11 & 0x1FFF0000) == 0x70000 )
    v10 = (unsigned __int16)v11;
  if ( !v10 )
    goto LABEL_13;
LABEL_16:
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(v15);
  SysFreeString(v8);
  return v10;
}

```

## disassembly

```asm
0x1800130e0  push    rbx
0x1800130e2  push    rsi
0x1800130e3  push    rdi
0x1800130e4  push    r14
0x1800130e6  sub     rsp, 38h
0x1800130ea  mov     rsi, r9
0x1800130ed  mov     r14, r8
0x1800130f0  mov     rbx, rdx
0x1800130f3  mov     rdi, rcx
0x1800130f6  mov     [rsp+58h+var_30], 0
0x1800130ff  mov     [rsp+58h+var_38], 0
0x180013107  xor     ecx, ecx; bstrString
0x180013109  call    cs:__imp_SysFreeString
0x18001310f  mov     rcx, rbx; psz
0x180013112  call    cs:__imp_SysAllocString
0x180013118  mov     rbx, rax
0x18001311b  test    rax, rax
0x18001311e  jz      loc_1800131B9
0x180013124  xor     ecx, ecx; bstrString
0x180013126  call    cs:__imp_SysFreeString
0x18001312c  mov     rax, [rdi]
0x18001312f  lea     r8, [rsp+58h+var_30]
0x180013134  mov     rdx, rbx
0x180013137  mov     rcx, rdi
0x18001313a  mov     rax, [rax+120h]
0x180013141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013146  mov     edi, eax
0x180013148  test    eax, eax
0x18001314a  js      short loc_180013150
0x18001314c  xor     edi, edi
0x18001314e  jmp     short loc_180013163
0x180013150  and     eax, 1FFF0000h
0x180013155  cmp     eax, 70000h
0x18001315a  jnz     short loc_18001315F
0x18001315c  movzx   edi, di
0x18001315f  test    edi, edi
0x180013161  jnz     short loc_1800131BE
0x180013163  test    rsi, rsi
0x180013166  jz      short loc_18001319B
0x180013168  mov     rcx, [rsp+58h+var_30]
0x18001316d  mov     rax, [rcx]
0x180013170  lea     rdx, [rsp+58h+var_38]
0x180013175  mov     rax, [rax+40h]
0x180013179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001317e  mov     edi, eax
0x180013180  test    eax, eax
0x180013182  js      short loc_180013188
0x180013184  xor     edi, edi
0x180013186  jmp     short loc_18001319B
0x180013188  and     eax, 1FFF0000h
0x18001318d  cmp     eax, 70000h
0x180013192  jnz     short loc_180013197
0x180013194  movzx   edi, di
0x180013197  test    edi, edi
0x180013199  jnz     short loc_1800131BE
0x18001319b  mov     rax, [rsp+58h+var_30]
0x1800131a0  mov     [rsp+58h+var_30], 0
0x1800131a9  mov     [r14], rax
0x1800131ac  test    rsi, rsi
0x1800131af  jz      short loc_1800131BE
0x1800131b1  mov     eax, [rsp+58h+var_38]
0x1800131b5  mov     [rsi], eax
0x1800131b7  jmp     short loc_1800131BE
0x1800131b9  xor     ebx, ebx
0x1800131bb  lea     edi, [rbx+0Eh]
0x1800131be  lea     rcx, [rsp+58h+var_30]
0x1800131c3  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x1800131c8  nop
0x1800131c9  mov     rcx, rbx; bstrString
0x1800131cc  call    cs:__imp_SysFreeString
0x1800131d2  mov     eax, edi
0x1800131d4  add     rsp, 38h
0x1800131d8  pop     r14
0x1800131da  pop     rdi
0x1800131db  pop     rsi
0x1800131dc  pop     rbx
0x1800131dd  retn
```

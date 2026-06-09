# CModelDownloadComponent::GetNamedAttributeTextFromNode(IXMLDOMNode *,ushort const *,ushort * *)

- ea: `0x14000f560`
- end: `0x14000f6e4`
- name: `?GetNamedAttributeTextFromNode@CModelDownloadComponent@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAG@Z`
- size: `388`
- prototype: `__int64 __fastcall(CModelDownloadComponent *this, struct IXMLDOMNode *, OLECHAR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400104b0`

## callees

- `0x14000985c`
- `0x14000c3ac`
- `0x14000f560`
- `0x14001d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14000f5e2`
- `OLEAUT32!__imp_SysAllocString` at `0x14000f5e2`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f612`
- `OLEAUT32!__imp_SysFreeString` at `0x14000f612`

## string_xrefs

- `0x14000f671`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(904)`
- `0x14000f681`: `CModelDownloadComponent::GetNamedAttributeTextFromNode`
- `0x14000f5bd`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(907)`
- `0x14000f621`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(908)`
- `0x14000f663`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(912)`
- `0x14000f655`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(915)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::GetNamedAttributeTextFromNode(
        CModelDownloadComponent *this,
        struct IXMLDOMNode *a2,
        OLECHAR *a3,
        unsigned __int16 **a4)
{
  int v6; // eax
  int v7; // edi
  __int64 *v8; // rdi
  __int64 v9; // rbp
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rax
  int v12; // ecx
  const wchar_t *v13; // rax
  int v14; // eax
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF
  __int64 *v17; // [rsp+68h] [rbp+10h] BYREF

  v17 = 0;
  v16 = 0;
  if ( !a2 || !a4 )
  {
    v7 = -2147024809;
    v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(904)";
    goto LABEL_17;
  }
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 **))a2->lpVtbl->get_attributes)(a2, &v17);
  v7 = v6;
  if ( v6 < 0 )
  {
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::GetNamedAttributeTextFromNode",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(907)",
      v6);
    goto LABEL_18;
  }
  v8 = v17;
  v9 = *v17;
  if ( a3 )
  {
    v11 = SysAllocString(a3);
    a3 = (OLECHAR *)v11;
    if ( !v11 )
      ATL::AtlThrowImpl(v12);
    v10 = v11;
  }
  else
  {
    v10 = 0;
  }
  v7 = (*(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, __int64 *))(v9 + 56))(v8, v10, &v16);
  SysFreeString(a3);
  if ( v7 < 0 )
  {
    v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(908)";
LABEL_17:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::GetNamedAttributeTextFromNode",
      v13,
      v7);
    goto LABEL_18;
  }
  if ( v7 == 1 || !v16 )
  {
    v7 = -2147200966;
    v13 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(912)";
    goto LABEL_17;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v16 + 208LL))(v16, a4);
  v7 = v14;
  if ( v14 < 0 )
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::GetNamedAttributeTextFromNode",
      L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(915)",
      v14);
LABEL_18:
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( v17 )
    (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14000f560  mov     r11, rsp
0x14000f563  mov     [r11+18h], rbx
0x14000f567  mov     [r11+8], rcx
0x14000f56b  push    rbp
0x14000f56c  push    rsi
0x14000f56d  push    rdi
0x14000f56e  sub     rsp, 40h
0x14000f572  mov     rsi, r9
0x14000f575  mov     rbx, r8
0x14000f578  mov     r10, rdx
0x14000f57b  mov     qword ptr [r11+10h], 0
0x14000f583  mov     qword ptr [r11+8], 0
0x14000f58b  test    rdx, rdx
0x14000f58e  jz      loc_14000F66C
0x14000f594  test    r9, r9
0x14000f597  jz      loc_14000F66C
0x14000f59d  mov     rax, [rdx]
0x14000f5a0  lea     rdx, [r11+10h]
0x14000f5a4  mov     rcx, r10
0x14000f5a7  mov     rax, [rax+88h]
0x14000f5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f5b3  mov     edi, eax
0x14000f5b5  test    eax, eax
0x14000f5b7  jns     short loc_14000F5C9
0x14000f5b9  mov     [rsp+58h+var_30], eax
0x14000f5bd  lea     rax, aOnecoreuapEndu; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f5c4  jmp     loc_14000F67C
0x14000f5c9  mov     rdi, [rsp+58h+arg_8]
0x14000f5ce  mov     rbp, [rdi]
0x14000f5d1  test    rbx, rbx
0x14000f5d4  jnz     short loc_14000F5DF
0x14000f5d6  mov     [rsp+58h+var_28], rbx
0x14000f5db  xor     edx, edx
0x14000f5dd  jmp     short loc_14000F5FC
0x14000f5df  mov     rcx, rbx; psz
0x14000f5e2  call    cs:__imp_SysAllocString
0x14000f5e8  mov     rbx, rax
0x14000f5eb  mov     [rsp+58h+var_28], rax
0x14000f5f0  test    rax, rax
0x14000f5f3  jz      loc_14000F6DE
0x14000f5f9  mov     rdx, rax
0x14000f5fc  lea     r8, [rsp+58h+arg_0]
0x14000f601  mov     rcx, rdi
0x14000f604  mov     rax, [rbp+38h]
0x14000f608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f60d  mov     edi, eax
0x14000f60f  mov     rcx, rbx; bstrString
0x14000f612  call    cs:__imp_SysFreeString
0x14000f618  mov     eax, edi
0x14000f61a  shr     eax, 1Fh
0x14000f61d  test    al, al
0x14000f61f  jz      short loc_14000F62A
0x14000f621  lea     rax, aOnecoreuapEndu_132; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f628  jmp     short loc_14000F678
0x14000f62a  cmp     edi, 1
0x14000f62d  jz      short loc_14000F65E
0x14000f62f  mov     rcx, [rsp+58h+arg_0]
0x14000f634  test    rcx, rcx
0x14000f637  jz      short loc_14000F65E
0x14000f639  mov     rax, [rcx]
0x14000f63c  mov     rdx, rsi
0x14000f63f  mov     rax, [rax+0D0h]
0x14000f646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f64b  mov     edi, eax
0x14000f64d  test    eax, eax
0x14000f64f  jns     short loc_14000F6A1
0x14000f651  mov     [rsp+58h+var_30], eax
0x14000f655  lea     rax, aOnecoreuapEndu_95; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f65c  jmp     short loc_14000F67C
0x14000f65e  mov     edi, 8004503Ah
0x14000f663  lea     rax, aOnecoreuapEndu_91; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f66a  jmp     short loc_14000F678
0x14000f66c  mov     edi, 80070057h
0x14000f671  lea     rax, aOnecoreuapEndu_41; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f678  mov     [rsp+58h+var_30], edi
0x14000f67c  mov     [rsp+58h+var_38], rax
0x14000f681  lea     r9, aCmodeldownload_0; "CModelDownloadComponent::GetNamedAttrib"...
0x14000f688  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000f68f  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000f696  mov     ecx, 2; int
0x14000f69b  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000f6a0  nop
0x14000f6a1  mov     rcx, [rsp+58h+arg_0]
0x14000f6a6  test    rcx, rcx
0x14000f6a9  jz      short loc_14000F6B8
0x14000f6ab  mov     rax, [rcx]
0x14000f6ae  mov     rax, [rax+10h]
0x14000f6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6b7  nop
0x14000f6b8  mov     rcx, [rsp+58h+arg_8]
0x14000f6bd  test    rcx, rcx
0x14000f6c0  jz      short loc_14000F6CF
0x14000f6c2  mov     rax, [rcx]
0x14000f6c5  mov     rax, [rax+10h]
0x14000f6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f6ce  nop
0x14000f6cf  mov     eax, edi
0x14000f6d1  mov     rbx, [rsp+58h+arg_10]
0x14000f6d6  add     rsp, 40h
0x14000f6da  pop     rdi
0x14000f6db  pop     rsi
0x14000f6dc  pop     rbp
0x14000f6dd  retn
0x14000f6de  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

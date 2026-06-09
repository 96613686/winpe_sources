# UiaNode::GetProviderInfoString(ushort * *)

- ea: `0x1800c88bc`
- end: `0x1800c8c9d`
- name: `?GetProviderInfoString@UiaNode@@AEAAJPEAPEAG@Z`
- size: `993`
- prototype: `__int64 __fastcall(UiaNode *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180047b90`
- `0x180049c30`

## callees

- `0x18002f580`
- `0x18003c820`
- `0x180061630`
- `0x1800975b0`
- `0x1800b8210`
- `0x1800c2008`
- `0x1800c74a0`
- `0x1800c88bc`
- `0x1800c8ca4`
- `0x1800c8d60`
- `0x1800c9a18`
- `0x1801e8320`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c8919`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c8919`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c8a4b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c8b21`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c8a4b`
- `OLEAUT32!__imp_SysStringLen` at `0x1800c8b21`
- `OLEAUT32!__imp_VariantInit` at `0x1800c89e4`
- `OLEAUT32!__imp_VariantInit` at `0x1800c8ac7`
- `OLEAUT32!__imp_VariantInit` at `0x1800c89e4`
- `OLEAUT32!__imp_VariantInit` at `0x1800c8ac7`
- `OLEAUT32!__imp_VariantClear` at `0x1800c8b7a`
- `OLEAUT32!__imp_VariantClear` at `0x1800c8c04`
- `OLEAUT32!__imp_VariantClear` at `0x1800c8b7a`
- `OLEAUT32!__imp_VariantClear` at `0x1800c8c04`

## string_xrefs

- `0x1800c894b`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c8bcb`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c8bed`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c8c21`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c8987`: `(parent link)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UiaNode::GetProviderInfoString(UiaNode *this, unsigned __int16 **a2)
{
  ProviderEntryPoint *v4; // rcx
  int ShortId; // ebx
  DWORD CurrentProcessId; // eax
  int appended; // ebx
  __int64 v8; // rdx
  unsigned int i; // edi
  int SlotType; // eax
  const wchar_t *v12; // rcx
  unsigned int v13; // edx
  struct IRawElementProviderSimple *SlotAsProvider; // r14
  int PropertyValue; // eax
  unsigned __int16 *ProviderInfo; // rbx
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  struct IUiaNode *SlotAsNode; // rbx
  int v22; // ebx
  int v23; // eax
  __int64 v24; // rdx
  int v25; // [rsp+20h] [rbp-E0h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v27; // [rsp+58h] [rbp-A8h] BYREF
  int v28[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v29[1024]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8A8h] [rbp+7A8h]

  *a2 = 0;
  v29[0] = 0;
  v4 = (ProviderEntryPoint *)*((_QWORD *)this + 32);
  if ( v4 )
    ShortId = ProviderEntryPoint::GetShortId(v4);
  else
    ShortId = 0;
  CurrentProcessId = GetCurrentProcessId();
  v25 = ShortId;
  appended = AppendStr(v29, 0x400u, L"[pid:%d,providerId:0x%lX ", CurrentProcessId);
  if ( appended >= 0 )
  {
    for ( i = 0; i < *((_DWORD *)this + 60); ++i )
    {
      SlotType = UiaNode::GetSlotType(this, i);
      v12 = L"(parent link)";
      if ( *((_DWORD *)this + 61) != i )
        v12 = &word_180313900;
      appended = AppendStr(v29, 0x400u, L"%s%s:", (&ProviderInfoRoleTable)[SlotType], v12);
      if ( appended < 0 )
      {
        v8 = 5457;
        goto LABEL_6;
      }
      SlotAsProvider = UiaNode::GetSlotAsProvider(this, i);
      if ( SlotAsProvider )
      {
        VariantInit(&pvarg);
        pvarg.llVal = 0;
        PropertyValue = ProviderCallouts::GetPropertyValue(
                          SlotAsProvider,
                          8u,
                          *((struct ProviderEntryPoint **)this + 32),
                          30107,
                          &pvarg);
        appended = PropertyValue;
        if ( PropertyValue < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1558,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
            (const char *)(unsigned int)PropertyValue,
            v25);
          goto LABEL_35;
        }
        ProviderInfo = GetProviderInfo((struct IUnknown *)SlotAsProvider);
        v27 = ProviderInfo;
        if ( !ProviderInfo )
        {
          appended = -2147024882;
          v18 = 2147942414LL;
          v19 = 5466;
LABEL_33:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
            (const char *)v18,
            v25);
          AutoCleanupInfo<unsigned short *>::SafeRelease(&v27);
LABEL_35:
          VariantClear(&pvarg);
          return (unsigned int)appended;
        }
        if ( pvarg.vt == 8 && SysStringLen(pvarg.bstrVal) )
        {
          v25 = (int)ProviderInfo;
          v17 = AppendStr(v29, 0x400u, L"%s %s", pvarg.llVal);
          appended = v17;
          if ( v17 < 0 )
          {
            v18 = (unsigned int)v17;
            v19 = 5470;
            goto LABEL_33;
          }
        }
        else
        {
          v20 = AppendStr(v29, 0x400u, L"Unidentified Provider %s", ProviderInfo);
          appended = v20;
          if ( v20 < 0 )
          {
            v18 = (unsigned int)v20;
            v19 = 5474;
            goto LABEL_33;
          }
        }
        AutoCleanupInfo<unsigned short *>::SafeRelease(&v27);
      }
      else
      {
        SlotAsNode = UiaNode::GetSlotAsNode(this, v13);
        VariantInit(&pvarg);
        pvarg.llVal = 0;
        v28[0] = 30107;
        v25 = 0;
        v22 = (*(__int64 (__fastcall **)(struct IUiaNode *, _QWORD, __int64, int *))(*(_QWORD *)SlotAsNode + 64LL))(
                SlotAsNode,
                0,
                1,
                v28);
        if ( v22 >= 0 && pvarg.vt == 8 && SysStringLen(pvarg.bstrVal) )
        {
          v23 = AppendStr(v29, 0x400u, L"Nested %s", pvarg.llVal);
          appended = v23;
          if ( v23 < 0 )
          {
            v24 = 5491;
            goto LABEL_38;
          }
        }
        else
        {
          v23 = AppendStr(v29, 0x400u, L"Nested [hr=0x%08lx]", (unsigned int)v22);
          appended = v23;
          if ( v23 < 0 )
          {
            v24 = 5487;
LABEL_38:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v24,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
              (const char *)(unsigned int)v23,
              0);
            goto LABEL_35;
          }
        }
      }
      VariantClear(&pvarg);
      if ( i < *((_DWORD *)this + 60) - 1 )
      {
        appended = AppendStr(v29, 0x400u, L"; ");
        if ( appended < 0 )
        {
          v8 = 5497;
          goto LABEL_6;
        }
      }
    }
    appended = AppendStr(v29, 0x400u, L"]");
    if ( appended < 0 )
    {
      v8 = 5501;
      goto LABEL_6;
    }
    return HrSysAllocString(v29, a2);
  }
  else
  {
    v8 = 5450;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
      (const char *)(unsigned int)appended,
      v25);
    return (unsigned int)appended;
  }
}

```

## disassembly

```asm
0x1800c88bc  mov     [rsp-8+arg_10], rbx
0x1800c88c1  mov     [rsp-8+arg_18], rsi
0x1800c88c6  push    rbp
0x1800c88c7  push    rdi
0x1800c88c8  push    r13
0x1800c88ca  push    r14
0x1800c88cc  push    r15
0x1800c88ce  lea     rbp, [rsp-780h]
0x1800c88d6  sub     rsp, 880h
0x1800c88dd  mov     rax, cs:__security_cookie
0x1800c88e4  xor     rax, rsp
0x1800c88e7  mov     [rbp+7A0h+var_30], rax
0x1800c88ee  mov     r15, rdx
0x1800c88f1  mov     rsi, rcx
0x1800c88f4  mov     qword ptr [rdx], 0
0x1800c88fb  xor     eax, eax
0x1800c88fd  mov     [rsp+8A0h+var_830], ax
0x1800c8902  mov     rcx, [rcx+100h]; this
0x1800c8909  test    rcx, rcx
0x1800c890c  jz      short loc_1800C8917
0x1800c890e  call    ?GetShortId@ProviderEntryPoint@@QEBAHXZ; ProviderEntryPoint::GetShortId(void)
0x1800c8913  mov     ebx, eax
0x1800c8915  jmp     short loc_1800C8919
0x1800c8917  xor     ebx, ebx
0x1800c8919  call    cs:__imp_GetCurrentProcessId
0x1800c891f  mov     r9d, eax
0x1800c8922  mov     dword ptr [rsp+8A0h+var_880], ebx; int
0x1800c8926  lea     r8, aPidDProviderid; "[pid:%d,providerId:0x%lX "
0x1800c892d  mov     r13d, 400h
0x1800c8933  mov     edx, r13d; unsigned __int64
0x1800c8936  lea     rcx, [rsp+8A0h+var_830]; unsigned __int16 *
0x1800c893b  call    ?AppendStr@@YAJPEAG_KPEBGZZ; AppendStr(ushort *,unsigned __int64,ushort const *,...)
0x1800c8940  mov     ebx, eax
0x1800c8942  test    eax, eax
0x1800c8944  jns     short loc_1800C8968
0x1800c8946  mov     edx, 154Ah; void *
0x1800c894b  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x1800c8952  mov     r9d, ebx; char *
0x1800c8955  mov     rcx, [rbp+7A8h]; this
0x1800c895c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8961  mov     eax, ebx
0x1800c8963  jmp     loc_1800C8C72
0x1800c8968  xor     edi, edi
0x1800c896a  cmp     edi, [rsi+0F0h]
0x1800c8970  jnb     loc_1800C8C41
0x1800c8976  mov     edx, edi
0x1800c8978  mov     rcx, rsi
0x1800c897b  call    ?GetSlotType@UiaNode@@AEBA?AW4ProviderRole@@I@Z; UiaNode::GetSlotType(uint)
0x1800c8980  lea     rdx, word_180313900
0x1800c8987  lea     rcx, aParentLink; "(parent link)"
0x1800c898e  cmp     [rsi+0F4h], edi
0x1800c8994  cmovnz  rcx, rdx
0x1800c8998  movsxd  r9, eax
0x1800c899b  lea     rax, ?ProviderInfoRoleTable@@3PAPEBGA; ushort const * near * ProviderInfoRoleTable
0x1800c89a2  mov     [rsp+8A0h+var_880], rcx
0x1800c89a7  mov     r9, [rax+r9*8]
0x1800c89ab  lea     r8, aSS_0; "%s%s:"
0x1800c89b2  mov     rdx, r13; unsigned __int64
0x1800c89b5  lea     rcx, [rsp+8A0h+var_830]; unsigned __int16 *
0x1800c89ba  call    ?AppendStr@@YAJPEAG_KPEBGZZ; AppendStr(ushort *,unsigned __int64,ushort const *,...)
0x1800c89bf  mov     ebx, eax
0x1800c89c1  test    eax, eax
0x1800c89c3  js      loc_1800C8C37
0x1800c89c9  mov     edx, edi; unsigned int
0x1800c89cb  mov     rcx, rsi; this
0x1800c89ce  call    ?GetSlotAsProvider@UiaNode@@AEAAPEAUIRawElementProviderSimple@@I@Z; UiaNode::GetSlotAsProvider(uint)
0x1800c89d3  mov     r14, rax
0x1800c89d6  test    rax, rax
0x1800c89d9  jz      loc_1800C8AB7
0x1800c89df  lea     rcx, [rsp+8A0h+pvarg]; pvarg
0x1800c89e4  call    cs:__imp_VariantInit
0x1800c89ea  mov     qword ptr [rsp+8A0h+pvarg+8], 0
0x1800c89f3  mov     edx, 8; unsigned __int16
0x1800c89f8  lea     rax, [rsp+8A0h+pvarg]
0x1800c89fd  mov     [rsp+8A0h+var_880], rax; int
0x1800c8a02  mov     r9d, 759Bh; int
0x1800c8a08  mov     r8, [rsi+100h]; struct ProviderEntryPoint *
0x1800c8a0f  mov     rcx, r14; struct IRawElementProviderSimple *
0x1800c8a12  call    ?GetPropertyValue@ProviderCallouts@@SAJPEAUIRawElementProviderSimple@@GPEAVProviderEntryPoint@@HPEAUtagVARIANT@@@Z; ProviderCallouts::GetPropertyValue(IRawElementProviderSimple *,ushort,ProviderEntryPoint *,int,tagVARIANT *)
0x1800c8a17  mov     ebx, eax
0x1800c8a19  test    eax, eax
0x1800c8a1b  js      loc_1800C8BE3
0x1800c8a21  mov     rcx, r14; struct IUnknown *
0x1800c8a24  call    ?GetProviderInfo@@YAPEAGPEAUIUnknown@@@Z; GetProviderInfo(IUnknown *)
0x1800c8a29  mov     rbx, rax
0x1800c8a2c  mov     [rsp+8A0h+var_848], rax
0x1800c8a31  test    rax, rax
0x1800c8a34  jz      loc_1800C8BB7
0x1800c8a3a  mov     eax, 8
0x1800c8a3f  cmp     word ptr [rsp+8A0h+pvarg], ax
0x1800c8a44  jnz     short loc_1800C8A86
0x1800c8a46  mov     rcx, qword ptr [rsp+8A0h+pvarg+8]; pbstr
0x1800c8a4b  call    cs:__imp_SysStringLen
0x1800c8a51  test    eax, eax
0x1800c8a53  jz      short loc_1800C8A86
0x1800c8a55  mov     [rsp+8A0h+var_880], rbx
0x1800c8a5a  mov     r9, qword ptr [rsp+8A0h+pvarg+8]
0x1800c8a5f  lea     r8, aSS; "%s %s"
0x1800c8a66  mov     rdx, r13; unsigned __int64
0x1800c8a69  lea     rcx, [rsp+8A0h+var_830]; unsigned __int16 *
0x1800c8a6e  call    ?AppendStr@@YAJPEAG_KPEBGZZ; AppendStr(ushort *,unsigned __int64,ushort const *,...)
0x1800c8a73  mov     ebx, eax
0x1800c8a75  test    eax, eax
0x1800c8a77  jns     short loc_1800C8AA7
0x1800c8a79  mov     r9d, eax
0x1800c8a7c  mov     edx, 155Eh
0x1800c8a81  jmp     loc_1800C8BC4
0x1800c8a86  mov     r9, rbx
0x1800c8a89  lea     r8, aUnidentifiedPr; "Unidentified Provider %s"
0x1800c8a90  mov     rdx, r13; unsigned __int64
0x1800c8a93  lea     rcx, [rsp+8A0h+var_830]; unsigned __int16 *
0x1800c8a98  call    ?AppendStr@@YAJPEAG_KPEBGZZ; AppendStr(ushort *,unsigned __int64,ushort const *,...)
0x1800c8a9d  mov     ebx, eax
0x1800c8a9f  test    eax, eax
0x1800c8aa1  js      loc_1800C8BAD
0x1800c8aa7  lea     rcx, [rsp+8A0h+var_848]
0x1800c8aac  call    ?SafeRelease@?$AutoCleanupInfo@PEAG@@SAXAEAPEAG@Z; AutoCleanupInfo<ushort *>::SafeRelease(ushort * &)
0x1800c8ab1  nop
0x1800c8ab2  jmp     loc_1800C8B75
0x1800c8ab7  mov     rcx, rsi; this
0x1800c8aba  call    ?GetSlotAsNode@UiaNode@@AEAAPEAVIUiaNode@@I@Z; UiaNode::GetSlotAsNode(uint)
0x1800c8abf  mov     rbx, rax
0x1800c8ac2  lea     rcx, [rsp+8A0h+pvarg]; pvarg
0x1800c8ac7  call    cs:__imp_VariantInit
0x1800c8acd  mov     qword ptr [rsp+8A0h+pvarg+8], 0
0x1800c8ad6  mov     [rsp+8A0h+var_840], 759Bh
0x1800c8ade  mov     rcx, [rbx]
0x1800c8ae1  mov     rax, [rcx+40h]
0x1800c8ae5  lea     rcx, [rsp+8A0h+pvarg]
0x1800c8aea  mov     [rsp+8A0h+var_878], rcx
0x1800c8aef  mov     dword ptr [rsp+8A0h+var_880], 0; int
0x1800c8af7  lea     r9, [rsp+8A0h+var_840]
0x1800c8afc  xor     edx, edx
0x1800c8afe  lea     r8d, [rdx+1]
0x1800c8b02  mov     rcx, rbx
0x1800c8b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8b0a  mov     ebx, eax
0x1800c8b0c  test    eax, eax
0x1800c8b0e  js      short loc_1800C8B54
0x1800c8b10  mov     eax, 8
0x1800c8b15  cmp     word ptr [rsp+8A0h+pvarg], ax
0x1800c8b1a  jnz     short loc_1800C8B54
0x1800c8b1c  mov     rcx, qword ptr [rsp+8A0h+pvarg+8]; pbstr
0x1800c8b21  call    cs:__imp_SysStringLen
0x1800c8b27  test    eax, eax
0x1800c8b29  jz      short loc_1800C8B54
0x1800c8b2b  mov     r9, qword ptr [rsp+8A0h+pvarg+8]
0x1800c8b30  lea     r8, aNestedS; "Nested %s"
0x1800c8b37  mov     rdx, r13; unsigned __int64
0x1800c8b3a  lea     rcx, [rsp+8A0h+var_830]; unsigned __int16 *
0x1800c8b3f  call    ?AppendStr@@YAJPEAG_KPEBGZZ; AppendStr(ushort *,unsigned __int64,ushort const *,...)
0x1800c8b44  mov     ebx, eax
0x1800c8b46  test    eax, eax
0x1800c8b48  jns     short loc_1800C8B75
0x1800c8b4a  mov     edx, 1573h
0x1800c8b4f  jmp     loc_1800C8C1E
0x1800c8b54  mov     r9d, ebx
0x1800c8b57  lea     r8, aNestedHr0x08lx; "Nested [hr=0x%08lx]"
0x1800c8b5e  mov     rdx, r13; unsigned __int64
0x1800c8b61  lea     rcx, [rsp+8A0h+var_830]; unsigned __int16 *
0x1800c8b66  call    ?AppendStr@@YAJPEAG_KPEBGZZ; AppendStr(ushort *,unsigned __int64,ushort const *,...)
0x1800c8b6b  mov     ebx, eax
0x1800c8b6d  test    eax, eax
0x1800c8b6f  js      loc_1800C8C19
0x1800c8b75  lea     rcx, [rsp+8A0h+pvarg]; pvarg
0x1800c8b7a  call    cs:__imp_VariantClear
0x1800c8b80  mov     eax, [rsi+0F0h]
0x1800c8b86  dec     eax
0x1800c8b88  cmp     edi, eax
0x1800c8b8a  jnb     short loc_1800C8BA6
0x1800c8b8c  lea     r8, asc_18032F854; "; "
0x1800c8b93  mov     rdx, r13; unsigned __int64
0x1800c8b96  lea     rcx, [rsp+8A0h+var_830]; unsigned __int16 *
0x1800c8b9b  call    ?AppendStr@@YAJPEAG_KPEBGZZ; AppendStr(ushort *,unsigned __int64,ushort const *,...)
0x1800c8ba0  mov     ebx, eax
0x1800c8ba2  test    eax, eax
0x1800c8ba4  js      short loc_1800C8C0F
0x1800c8ba6  inc     edi
0x1800c8ba8  jmp     loc_1800C896A
0x1800c8bad  mov     r9d, eax
0x1800c8bb0  mov     edx, 1562h
0x1800c8bb5  jmp     short loc_1800C8BC4
0x1800c8bb7  mov     ebx, 8007000Eh
0x1800c8bbc  mov     r9d, ebx; char *
0x1800c8bbf  mov     edx, 155Ah; void *
0x1800c8bc4  mov     rcx, [rbp+7A8h]; this
0x1800c8bcb  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x1800c8bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8bd7  lea     rcx, [rsp+8A0h+var_848]
0x1800c8bdc  call    ?SafeRelease@?$AutoCleanupInfo@PEAG@@SAXAEAPEAG@Z; AutoCleanupInfo<ushort *>::SafeRelease(ushort * &)
0x1800c8be1  jmp     short loc_1800C8BFF
0x1800c8be3  mov     rcx, [rbp+7A8h]; this
0x1800c8bea  mov     r9d, eax; char *
0x1800c8bed  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x1800c8bf4  mov     edx, 1558h; void *
0x1800c8bf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8bfe  nop
0x1800c8bff  lea     rcx, [rsp+8A0h+pvarg]; pvarg
0x1800c8c04  call    cs:__imp_VariantClear
0x1800c8c0a  jmp     loc_1800C8961
0x1800c8c0f  mov     edx, 1579h
0x1800c8c14  jmp     loc_1800C894B
0x1800c8c19  mov     edx, 156Fh; void *
0x1800c8c1e  mov     r9d, eax; char *
0x1800c8c21  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x1800c8c28  mov     rcx, [rbp+7A8h]; this
0x1800c8c2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8c34  nop
0x1800c8c35  jmp     short loc_1800C8BFF
0x1800c8c37  mov     edx, 1551h
0x1800c8c3c  jmp     loc_1800C894B
0x1800c8c41  lea     r8, asc_18032F850; "]"
0x1800c8c48  mov     rdx, r13; unsigned __int64
0x1800c8c4b  lea     rcx, [rsp+8A0h+var_830]; unsigned __int16 *
0x1800c8c50  call    ?AppendStr@@YAJPEAG_KPEBGZZ; AppendStr(ushort *,unsigned __int64,ushort const *,...)
0x1800c8c55  mov     ebx, eax
0x1800c8c57  test    eax, eax
0x1800c8c59  jns     short loc_1800C8C65
0x1800c8c5b  mov     edx, 157Dh
0x1800c8c60  jmp     loc_1800C894B
0x1800c8c65  mov     rdx, r15; unsigned __int16 **
0x1800c8c68  lea     rcx, [rsp+8A0h+var_830]; unsigned __int16 *
0x1800c8c6d  call    ?HrSysAllocString@@YAJPEBGPEAPEAG@Z; HrSysAllocString(ushort const *,ushort * *)
0x1800c8c72  mov     rcx, [rbp+7A0h+var_30]
0x1800c8c79  xor     rcx, rsp; StackCookie
0x1800c8c7c  call    __security_check_cookie
0x1800c8c81  lea     r11, [rsp+8A0h+var_20]
0x1800c8c89  mov     rbx, [r11+40h]
0x1800c8c8d  mov     rsi, [r11+48h]
0x1800c8c91  mov     rsp, r11
0x1800c8c94  pop     r15
0x1800c8c96  pop     r14
0x1800c8c98  pop     r13
0x1800c8c9a  pop     rdi
0x1800c8c9b  pop     rbp
0x1800c8c9c  retn
```

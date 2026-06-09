# CRadcXmlIcon::PopulateType(IXMLDOMNode *)

- ea: `0x18006d548`
- end: `0x18006d7b5`
- name: `?PopulateType@CRadcXmlIcon@@IEAAJPEAUIXMLDOMNode@@@Z`
- size: `621`
- prototype: `int(CRadcXmlIcon *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006cfdc`

## callees

- `0x18000b1d8`
- `0x18000ece0`
- `0x180010ba4`
- `0x18004f09c`
- `0x180062a08`
- `0x1800651b0`
- `0x18006d548`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18006d794`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d7a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d794`
- `OLEAUT32!__imp_SysFreeString` at `0x18006d7a0`
- `OLEAUT32!__imp_SysStringLen` at `0x18006d6e0`
- `OLEAUT32!__imp_SysStringLen` at `0x18006d6e0`
- `KERNEL32!CompareStringEx` at `0x18006d721`
- `KERNEL32!CompareStringEx` at `0x18006d721`

## string_xrefs

- `0x18006d620`: `CComBSTR::Append failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRadcXmlIcon::PopulateType(CRadcXmlIcon *this, struct IXMLDOMNode *a2)
{
  OLECHAR *v4; // rbx
  unsigned int v5; // eax
  int NamedAttributeValue; // edi
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // esi
  const WCHAR *lpString2; // rdi
  UINT v11; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  BSTR pbstr; // [rsp+50h] [rbp-58h] BYREF
  BSTR bstrString[10]; // [rsp+58h] [rbp-50h] BYREF

  bstrString[1] = (BSTR)-2LL;
  bstrString[0] = 0;
  v4 = 0;
  pbstr = 0;
  if ( a2 )
  {
    NamedAttributeValue = ATL::CComBSTR::Append((ATL::CComBSTR *)bstrString, L"FileType");
    if ( NamedAttributeValue >= 0 )
    {
      NamedAttributeValue = GetNamedAttributeValue(a2, bstrString[0], &pbstr);
      if ( NamedAttributeValue >= 0 )
      {
        v9 = 0;
        v4 = pbstr;
        while ( v9 < 2 )
        {
          lpString2 = (&off_1800AB900)[2 * v9];
          v11 = SysStringLen(v4);
          if ( CompareStringEx(&LocaleName, 1u, v4, v11 + 1, lpString2, -1, 0, 0, 0) == 2 )
          {
            *((_DWORD *)this + 12) = *((_DWORD *)&off_1800AB900 + 4 * v9 + 2);
            NamedAttributeValue = 0;
            goto LABEL_28;
          }
          ++v9;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)WPP_efd74bc97fe6331538e08afa25b3de18_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)v4,
            0);
        }
        NamedAttributeValue = -2147220736;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)WPP_efd74bc97fe6331538e08afa25b3de18_Traceguids,
            v8,
            (__int64)"GetNamedAttributeValue failed",
            NamedAttributeValue);
        }
        v4 = pbstr;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_efd74bc97fe6331538e08afa25b3de18_Traceguids,
        v7,
        (__int64)"CComBSTR::Append failed",
        NamedAttributeValue);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_efd74bc97fe6331538e08afa25b3de18_Traceguids,
        v5,
        (__int64)"pIconNode");
    }
    NamedAttributeValue = -2147467261;
  }
LABEL_28:
  SysFreeString(v4);
  SysFreeString(bstrString[0]);
  return (unsigned int)NamedAttributeValue;
}

```

## disassembly

```asm
0x18006d548  push    rbx
0x18006d54a  push    rbp
0x18006d54b  push    rsi
0x18006d54c  push    rdi
0x18006d54d  push    r12
0x18006d54f  push    r14
0x18006d551  sub     rsp, 78h
0x18006d555  mov     [rsp+0A8h+var_48], 0FFFFFFFFFFFFFFFEh
0x18006d55e  mov     rsi, rdx
0x18006d561  mov     rbp, rcx
0x18006d564  mov     [rsp+0A8h+bstrString], 0
0x18006d56d  xor     ebx, ebx
0x18006d56f  mov     [rsp+0A8h+pbstr], rbx
0x18006d574  test    rdx, rdx
0x18006d577  jnz     short loc_18006D5D0
0x18006d579  lea     rax, WPP_GLOBAL_Control
0x18006d580  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d587  cmp     rcx, rax
0x18006d58a  jz      short loc_18006D5C6
0x18006d58c  test    byte ptr [rcx+1Ch], 8
0x18006d590  jz      short loc_18006D5C6
0x18006d592  cmp     byte ptr [rcx+19h], 2
0x18006d596  jb      short loc_18006D5C6
0x18006d598  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006d59d  lea     edx, [rsi+13h]
0x18006d5a0  lea     rcx, aPiconnode; "pIconNode"
0x18006d5a7  mov     [rsp+0A8h+lpString2], rcx
0x18006d5ac  mov     r9d, eax
0x18006d5af  lea     r8, WPP_efd74bc97fe6331538e08afa25b3de18_Traceguids
0x18006d5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d5bd  mov     rcx, [rcx+10h]
0x18006d5c1  call    WPP_SF_Ds
0x18006d5c6  mov     edi, 80004003h
0x18006d5cb  jmp     loc_18006D791
0x18006d5d0  lea     rdx, aFiletype; "FileType"
0x18006d5d7  lea     rcx, [rsp+0A8h+bstrString]; this
0x18006d5dc  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18006d5e1  mov     edi, eax
0x18006d5e3  test    eax, eax
0x18006d5e5  jns     short loc_18006D64B
0x18006d5e7  lea     rax, WPP_GLOBAL_Control
0x18006d5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d5f5  cmp     rcx, rax
0x18006d5f8  jz      loc_18006D791
0x18006d5fe  test    byte ptr [rcx+1Ch], 8
0x18006d602  jz      loc_18006D791
0x18006d608  cmp     byte ptr [rcx+19h], 2
0x18006d60c  jb      loc_18006D791
0x18006d612  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006d617  mov     edx, 14h
0x18006d61c  mov     [rsp+0A8h+cchCount2], edi
0x18006d620  lea     rcx, aCcombstrAppend_0; "CComBSTR::Append failed"
0x18006d627  mov     [rsp+0A8h+lpString2], rcx
0x18006d62c  mov     r9d, eax
0x18006d62f  lea     r8, WPP_efd74bc97fe6331538e08afa25b3de18_Traceguids
0x18006d636  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d63d  mov     rcx, [rcx+10h]
0x18006d641  call    WPP_SF_DsD
0x18006d646  jmp     loc_18006D791
0x18006d64b  lea     r8, [rsp+0A8h+pbstr]; unsigned __int16 **
0x18006d650  mov     rdx, [rsp+0A8h+bstrString]; unsigned __int16 *
0x18006d655  mov     rcx, rsi; struct IXMLDOMNode *
0x18006d658  call    ?GetNamedAttributeValue@@YAJPEAUIXMLDOMNode@@PEAGPEAPEAG@Z; GetNamedAttributeValue(IXMLDOMNode *,ushort *,ushort * *)
0x18006d65d  mov     edi, eax
0x18006d65f  test    eax, eax
0x18006d661  jns     short loc_18006D6C0
0x18006d663  lea     rax, WPP_GLOBAL_Control
0x18006d66a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d671  cmp     rcx, rax
0x18006d674  jz      short loc_18006D6B6
0x18006d676  test    byte ptr [rcx+1Ch], 8
0x18006d67a  jz      short loc_18006D6B6
0x18006d67c  cmp     byte ptr [rcx+19h], 2
0x18006d680  jb      short loc_18006D6B6
0x18006d682  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006d687  mov     edx, 15h
0x18006d68c  mov     [rsp+0A8h+cchCount2], edi
0x18006d690  lea     rcx, aGetnamedattrib_9; "GetNamedAttributeValue failed"
0x18006d697  mov     [rsp+0A8h+lpString2], rcx
0x18006d69c  mov     r9d, eax
0x18006d69f  lea     r8, WPP_efd74bc97fe6331538e08afa25b3de18_Traceguids
0x18006d6a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d6ad  mov     rcx, [rcx+10h]
0x18006d6b1  call    WPP_SF_DsD
0x18006d6b6  mov     rbx, [rsp+0A8h+pbstr]
0x18006d6bb  jmp     loc_18006D791
0x18006d6c0  xor     esi, esi
0x18006d6c2  lea     r12, off_1800AB900; "Ico"
0x18006d6c9  mov     rbx, [rsp+0A8h+pbstr]
0x18006d6ce  cmp     esi, 2
0x18006d6d1  jnb     short loc_18006D73C
0x18006d6d3  mov     r14d, esi
0x18006d6d6  add     r14, r14
0x18006d6d9  mov     rdi, [r12+r14*8]
0x18006d6dd  mov     rcx, rbx; pbstr
0x18006d6e0  call    cs:__imp_SysStringLen
0x18006d6e6  lea     r9d, [rax+1]; cchCount1
0x18006d6ea  mov     [rsp+0A8h+lParam], 0; lParam
0x18006d6f3  mov     [rsp+0A8h+lpReserved], 0; lpReserved
0x18006d6fc  mov     [rsp+0A8h+lpVersionInformation], 0; lpVersionInformation
0x18006d705  mov     [rsp+0A8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18006d70d  mov     [rsp+0A8h+lpString2], rdi; lpString2
0x18006d712  mov     r8, rbx; lpString1
0x18006d715  mov     edx, 1; dwCmpFlags
0x18006d71a  lea     rcx, LocaleName; lpLocaleName
0x18006d721  call    cs:__imp_CompareStringEx
0x18006d727  cmp     eax, 2
0x18006d72a  jz      short loc_18006D730
0x18006d72c  inc     esi
0x18006d72e  jmp     short loc_18006D6CE
0x18006d730  mov     eax, [r12+r14*8+8]
0x18006d735  mov     [rbp+30h], eax
0x18006d738  xor     edi, edi
0x18006d73a  jmp     short loc_18006D791
0x18006d73c  lea     rax, WPP_GLOBAL_Control
0x18006d743  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d74a  cmp     rcx, rax
0x18006d74d  jz      short loc_18006D78C
0x18006d74f  test    byte ptr [rcx+1Ch], 8
0x18006d753  jz      short loc_18006D78C
0x18006d755  cmp     byte ptr [rcx+19h], 2
0x18006d759  jb      short loc_18006D78C
0x18006d75b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006d760  mov     edx, 16h
0x18006d765  mov     [rsp+0A8h+cchCount2], 80040300h
0x18006d76d  mov     [rsp+0A8h+lpString2], rbx
0x18006d772  mov     r9d, eax
0x18006d775  lea     r8, WPP_efd74bc97fe6331538e08afa25b3de18_Traceguids
0x18006d77c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d783  mov     rcx, [rcx+10h]
0x18006d787  call    WPP_SF_DSD
0x18006d78c  mov     edi, 80040300h
0x18006d791  mov     rcx, rbx; bstrString
0x18006d794  call    cs:__imp_SysFreeString
0x18006d79a  nop
0x18006d79b  mov     rcx, [rsp+0A8h+bstrString]; bstrString
0x18006d7a0  call    cs:__imp_SysFreeString
0x18006d7a6  mov     eax, edi
0x18006d7a8  add     rsp, 78h
0x18006d7ac  pop     r14
0x18006d7ae  pop     r12
0x18006d7b0  pop     rdi
0x18006d7b1  pop     rsi
0x18006d7b2  pop     rbp
0x18006d7b3  pop     rbx
0x18006d7b4  retn
```

# SdpXmlGetNodes(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNodeList * *)

- ea: `0x180025158`
- end: `0x180025275`
- name: `?SdpXmlGetNodes@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAUIXMLDOMNodeList@@@Z`
- size: `285`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IXMLDOMNodeList **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800209e0`
- `0x180021270`

## callees

- `0x180024ce8`
- `0x180025158`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800251c6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800251c6`
- `OLEAUT32!__imp_SysFreeString` at `0x18002524d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002524d`

## string_xrefs

- `0x18002518a`: `SdpXmlGetNodes`
- `0x18002521c`: `SdpXmlGetNodes`

## pseudocode

```c
__int64 __fastcall SdpXmlGetNodes(
        const unsigned __int16 *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMDocument2 *a3,
        struct IXMLDOMNodeList **a4)
{
  __int64 v7; // r9
  unsigned int v8; // ebx
  BSTR v9; // rax
  OLECHAR *v10; // rdi
  BSTR v11; // rdx
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  struct IXMLDOMDocument2 *v13; // rcx
  int v14; // eax
  struct IXMLDOMNodeList *v15; // rcx
  int v17; // [rsp+20h] [rbp-38h]
  struct IXMLDOMNodeList *v18; // [rsp+60h] [rbp+8h] BYREF

  v18 = 0;
  if ( !a1 )
  {
    v7 = 567;
LABEL_3:
    v8 = -2147024809;
    v17 = -2147024809;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v7 = 568;
    goto LABEL_3;
  }
  if ( !a2 && !a3 )
  {
    v7 = 572;
    goto LABEL_3;
  }
  v9 = SysAllocString(a1);
  v10 = v9;
  if ( v9 )
  {
    v11 = v9;
    if ( a2 )
    {
      lpVtbl = a2->lpVtbl;
      v13 = a2;
    }
    else
    {
      lpVtbl = a3->lpVtbl;
      v13 = a3;
    }
    v14 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, struct IXMLDOMNodeList **))lpVtbl->selectNodes)(
            v13,
            v11,
            &v18);
    v8 = v14;
    if ( v14 >= 0 )
    {
      v15 = v18;
      *a4 = v18;
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v15->lpVtbl->AddRef)(v15);
    }
    else
    {
      SdpDebugPrint(1u, "SDIAG: %ws:%d - hr = 0x%08X\n", L"SdpXmlGetNodes", 585, v14);
    }
    SysFreeString(v10);
    goto LABEL_19;
  }
  v8 = -2147024882;
  v7 = 576;
  v17 = -2147024882;
LABEL_4:
  SdpDebugPrint(1u, "SDIAG: %ws:%d - hr = 0x%08X\n", L"SdpXmlGetNodes", v7, v17);
LABEL_19:
  if ( v18 )
    ((void (__fastcall *)(struct IXMLDOMNodeList *))v18->lpVtbl->Release)(v18);
  return v8;
}

```

## disassembly

```asm
0x180025158  push    rbx
0x18002515a  push    rsi
0x18002515b  push    rdi
0x18002515c  push    r14
0x18002515e  sub     rsp, 38h
0x180025162  mov     [rsp+58h+arg_0], 0
0x18002516b  mov     r14, r9
0x18002516e  mov     rsi, r8
0x180025171  mov     rbx, rdx
0x180025174  test    rcx, rcx
0x180025177  jnz     short loc_1800251A7
0x180025179  mov     r9d, 237h
0x18002517f  mov     eax, 80070057h
0x180025184  mov     ebx, eax
0x180025186  mov     [rsp+58h+var_38], eax
0x18002518a  lea     r8, aSdpxmlgetnodes; "SdpXmlGetNodes"
0x180025191  mov     ecx, 1; Level
0x180025196  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x18002519d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1800251a2  jmp     loc_180025253
0x1800251a7  test    r14, r14
0x1800251aa  jnz     short loc_1800251B4
0x1800251ac  mov     r9d, 238h
0x1800251b2  jmp     short loc_18002517F
0x1800251b4  test    rbx, rbx
0x1800251b7  jnz     short loc_1800251C6
0x1800251b9  test    rsi, rsi
0x1800251bc  jnz     short loc_1800251C6
0x1800251be  mov     r9d, 23Ch
0x1800251c4  jmp     short loc_18002517F
0x1800251c6  call    cs:__imp_SysAllocString
0x1800251cc  mov     rdi, rax
0x1800251cf  test    rax, rax
0x1800251d2  jnz     short loc_1800251E5
0x1800251d4  mov     ebx, 8007000Eh
0x1800251d9  mov     r9d, 240h
0x1800251df  mov     [rsp+58h+var_38], ebx
0x1800251e3  jmp     short loc_18002518A
0x1800251e5  lea     r8, [rsp+58h+arg_0]
0x1800251ea  mov     rdx, rdi
0x1800251ed  test    rbx, rbx
0x1800251f0  jz      short loc_1800251FA
0x1800251f2  mov     rax, [rbx]
0x1800251f5  mov     rcx, rbx
0x1800251f8  jmp     short loc_180025200
0x1800251fa  mov     rax, [rsi]
0x1800251fd  mov     rcx, rsi
0x180025200  mov     rax, [rax+120h]
0x180025207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002520c  mov     ebx, eax
0x18002520e  test    eax, eax
0x180025210  jns     short loc_180025236
0x180025212  mov     r9d, 249h
0x180025218  mov     [rsp+58h+var_38], eax
0x18002521c  lea     r8, aSdpxmlgetnodes; "SdpXmlGetNodes"
0x180025223  mov     ecx, 1; Level
0x180025228  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x18002522f  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x180025234  jmp     short loc_18002524A
0x180025236  mov     rcx, [rsp+58h+arg_0]
0x18002523b  mov     [r14], rcx
0x18002523e  mov     rax, [rcx]
0x180025241  mov     rax, [rax+8]
0x180025245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002524a  mov     rcx, rdi; bstrString
0x18002524d  call    cs:__imp_SysFreeString
0x180025253  mov     rcx, [rsp+58h+arg_0]
0x180025258  test    rcx, rcx
0x18002525b  jz      short loc_180025269
0x18002525d  mov     rax, [rcx]
0x180025260  mov     rax, [rax+10h]
0x180025264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025269  mov     eax, ebx
0x18002526b  add     rsp, 38h
0x18002526f  pop     r14
0x180025271  pop     rdi
0x180025272  pop     rsi
0x180025273  pop     rbx
0x180025274  retn
```

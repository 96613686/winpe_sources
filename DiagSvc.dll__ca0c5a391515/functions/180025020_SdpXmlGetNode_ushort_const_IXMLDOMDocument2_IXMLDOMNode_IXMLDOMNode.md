# SdpXmlGetNode(ushort const *,IXMLDOMDocument2 *,IXMLDOMNode *,IXMLDOMNode * *)

- ea: `0x180025020`
- end: `0x180025152`
- name: `?SdpXmlGetNode@@YAJPEBGPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEAPEAU2@@Z`
- size: `306`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *, struct IXMLDOMNode **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800209e0`

## callees

- `0x180024ce8`
- `0x180025020`
- `0x180027010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002508f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002508f`
- `OLEAUT32!__imp_SysFreeString` at `0x180025124`
- `OLEAUT32!__imp_SysFreeString` at `0x180025124`

## string_xrefs

- `0x180025058`: `SdpXmlGetNode`
- `0x180025109`: `SdpXmlGetNode`

## pseudocode

```c
__int64 __fastcall SdpXmlGetNode(
        const unsigned __int16 *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3,
        struct IXMLDOMNode **a4)
{
  __int64 v6; // r9
  unsigned int v7; // ebx
  BSTR v8; // rax
  OLECHAR *v9; // rdi
  int v10; // eax
  __int64 v11; // r9
  struct IXMLDOMNode *v12; // rcx
  int v14; // [rsp+20h] [rbp-18h]
  int v15; // [rsp+20h] [rbp-18h]
  struct IXMLDOMNode *v16; // [rsp+48h] [rbp+10h] BYREF

  v16 = 0;
  if ( !a1 )
  {
    v6 = 498;
LABEL_3:
    v7 = -2147024809;
    v14 = -2147024809;
LABEL_4:
    SdpDebugPrint(1u, "SDIAG: %ws:%d - hr = 0x%08X\n", L"SdpXmlGetNode", v6, v14);
    goto LABEL_19;
  }
  if ( !a4 )
  {
    v6 = 499;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v6 = 502;
    goto LABEL_3;
  }
  v8 = SysAllocString(a1);
  v9 = v8;
  if ( !v8 )
  {
    v7 = -2147024882;
    v6 = 506;
    v14 = -2147024882;
    goto LABEL_4;
  }
  v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR, struct IXMLDOMNode **))a3->lpVtbl->selectSingleNode)(
          a3,
          v8,
          &v16);
  v7 = v10;
  if ( v10 < 0 )
  {
    v15 = v10;
    v11 = 515;
LABEL_17:
    SdpDebugPrint(1u, "SDIAG: %ws:%d - hr = 0x%08X\n", L"SdpXmlGetNode", v11, v15);
    goto LABEL_18;
  }
  if ( v10 == 1 || (v12 = v16) == 0 )
  {
    v7 = -2147467259;
    v11 = 516;
    v15 = -2147467259;
    goto LABEL_17;
  }
  *a4 = v16;
  ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->AddRef)(v12);
LABEL_18:
  SysFreeString(v9);
LABEL_19:
  if ( v16 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v16->lpVtbl->Release)(v16);
  return v7;
}

```

## disassembly

```asm
0x180025020  mov     rax, rsp
0x180025023  mov     [rax+8], rbx
0x180025027  mov     [rax+18h], rsi
0x18002502b  mov     [rax+10h], rdx
0x18002502f  push    rdi
0x180025030  sub     rsp, 30h
0x180025034  mov     qword ptr [rax+10h], 0
0x18002503c  mov     rsi, r9
0x18002503f  mov     rbx, r8
0x180025042  test    rcx, rcx
0x180025045  jnz     short loc_180025075
0x180025047  mov     r9d, 1F2h
0x18002504d  mov     eax, 80070057h
0x180025052  mov     ebx, eax
0x180025054  mov     [rsp+38h+var_18], eax
0x180025058  lea     r8, aSdpxmlgetnode; "SdpXmlGetNode"
0x18002505f  mov     ecx, 1; Level
0x180025064  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x18002506b  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x180025070  jmp     loc_18002512A
0x180025075  test    rsi, rsi
0x180025078  jnz     short loc_180025082
0x18002507a  mov     r9d, 1F3h
0x180025080  jmp     short loc_18002504D
0x180025082  test    rbx, rbx
0x180025085  jnz     short loc_18002508F
0x180025087  mov     r9d, 1F6h
0x18002508d  jmp     short loc_18002504D
0x18002508f  call    cs:__imp_SysAllocString
0x180025095  mov     rdi, rax
0x180025098  test    rax, rax
0x18002509b  jnz     short loc_1800250AE
0x18002509d  mov     ebx, 8007000Eh
0x1800250a2  mov     r9d, 1FAh
0x1800250a8  mov     [rsp+38h+var_18], ebx
0x1800250ac  jmp     short loc_180025058
0x1800250ae  mov     rax, [rbx]
0x1800250b1  lea     r8, [rsp+38h+arg_8]
0x1800250b6  mov     rdx, rdi
0x1800250b9  mov     rcx, rbx
0x1800250bc  mov     rax, [rax+128h]
0x1800250c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250c8  mov     ebx, eax
0x1800250ca  test    eax, eax
0x1800250cc  jns     short loc_1800250DA
0x1800250ce  mov     [rsp+38h+var_18], eax
0x1800250d2  mov     r9d, 203h
0x1800250d8  jmp     short loc_180025109
0x1800250da  cmp     eax, 1
0x1800250dd  jz      short loc_1800250FA
0x1800250df  mov     rcx, [rsp+38h+arg_8]
0x1800250e4  test    rcx, rcx
0x1800250e7  jz      short loc_1800250FA
0x1800250e9  mov     [rsi], rcx
0x1800250ec  mov     rax, [rcx]
0x1800250ef  mov     rax, [rax+8]
0x1800250f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250f8  jmp     short loc_180025121
0x1800250fa  mov     ebx, 80004005h
0x1800250ff  mov     r9d, 204h
0x180025105  mov     [rsp+38h+var_18], ebx
0x180025109  lea     r8, aSdpxmlgetnode; "SdpXmlGetNode"
0x180025110  mov     ecx, 1; Level
0x180025115  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x18002511c  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x180025121  mov     rcx, rdi; bstrString
0x180025124  call    cs:__imp_SysFreeString
0x18002512a  mov     rcx, [rsp+38h+arg_8]
0x18002512f  test    rcx, rcx
0x180025132  jz      short loc_180025140
0x180025134  mov     rax, [rcx]
0x180025137  mov     rax, [rax+10h]
0x18002513b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025140  mov     rsi, [rsp+38h+arg_10]
0x180025145  mov     eax, ebx
0x180025147  mov     rbx, [rsp+38h+arg_0]
0x18002514c  add     rsp, 30h
0x180025150  pop     rdi
0x180025151  retn
```

# SHCreatePostEnumOpBindCtx(IBindCtx *,tagENUMHINTINFO const *,IBindCtx * *)

- ea: `0x1800c0fe0`
- end: `0x1800c115b`
- name: `?SHCreatePostEnumOpBindCtx@@YAJPEAUIBindCtx@@PEBUtagENUMHINTINFO@@PEAPEAU1@@Z`
- size: `379`
- prototype: `__int64 __fastcall(struct IBindCtx *, const struct tagENUMHINTINFO *, struct IBindCtx **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800c1908`

## callees

- `0x180071dc0`
- `0x1800c0fe0`
- `0x1800ea010`

## import_xrefs

- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800c1082`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800c10a6`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800c1082`
- `PROPSYS!PSPropertyBag_WriteUnknown` at `0x1800c10a6`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800c1040`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800c1040`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1800c105e`
- `PROPSYS!PSPropertyBag_WriteDWORD` at `0x1800c105e`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800c101d`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800c101d`

## pseudocode

```c
__int64 __fastcall SHCreatePostEnumOpBindCtx(struct IBindCtx *a1, DWORD *a2, struct IBindCtx **a3)
{
  HRESULT v5; // ebx
  IUnknown *v6; // r8
  IUnknown *v7; // r8
  LPBC v8; // rcx
  void *ppv; // [rsp+20h] [rbp-29h] BYREF
  LPBC ppbc; // [rsp+28h] [rbp-21h] BYREF
  _OWORD v12[4]; // [rsp+30h] [rbp-19h] BYREF
  unsigned __int16 v13; // [rsp+70h] [rbp+27h]

  *a3 = 0;
  ppbc = 0;
  v5 = CreateBindCtx(0, &ppbc);
  if ( v5 >= 0 )
  {
    ppv = 0;
    v5 = PSCreateMemoryPropertyStore(&GUID_55272a00_42cb_11ce_8135_00aa004bb851, &ppv);
    if ( v5 >= 0 )
    {
      v5 = PSPropertyBag_WriteDWORD((IPropertyBag *)ppv, L"Max Results", *a2);
      if ( v5 >= 0 )
      {
        v6 = (IUnknown *)*((_QWORD *)a2 + 1);
        if ( !v6 || (v5 = PSPropertyBag_WriteUnknown((IPropertyBag *)ppv, L"Sort Columns", v6), v5 >= 0) )
        {
          v7 = (IUnknown *)*((_QWORD *)a2 + 2);
          if ( v7 )
            v5 = PSPropertyBag_WriteUnknown((IPropertyBag *)ppv, L"Prop List", v7);
          if ( v5 >= 0 )
          {
            v12[0] = *(_OWORD *)L"Post Enumeration Operation Hints";
            v12[1] = *(_OWORD *)L"meration Operation Hints";
            v13 = aPostEnumeratio[32];
            v12[2] = *(_OWORD *)L" Operation Hints";
            v12[3] = *(_OWORD *)L"on Hints";
            v5 = ((__int64 (__fastcall *)(LPBC, _OWORD *, void *))ppbc->lpVtbl->RegisterObjectParam)(ppbc, v12, ppv);
            if ( v5 >= 0 )
            {
              v8 = ppbc;
              *a3 = ppbc;
              ((void (__fastcall *)(LPBC))v8->lpVtbl->AddRef)(v8);
            }
          }
        }
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800c0fe0  mov     [rsp-8+arg_0], rbx
0x1800c0fe5  push    rbp
0x1800c0fe6  push    rsi
0x1800c0fe7  push    rdi
0x1800c0fe8  lea     rbp, [rsp-47h]
0x1800c0fed  sub     rsp, 90h
0x1800c0ff4  mov     rax, cs:__security_cookie
0x1800c0ffb  xor     rax, rsp
0x1800c0ffe  mov     [rbp+57h+var_20], rax
0x1800c1002  mov     rdi, rdx
0x1800c1005  mov     qword ptr [r8], 0
0x1800c100c  lea     rdx, [rbp+57h+ppbc]; ppbc
0x1800c1010  mov     [rbp+57h+ppbc], 0
0x1800c1018  xor     ecx, ecx; reserved
0x1800c101a  mov     rsi, r8
0x1800c101d  call    cs:__imp_CreateBindCtx
0x1800c1023  mov     ebx, eax
0x1800c1025  test    eax, eax
0x1800c1027  js      loc_1800C113A
0x1800c102d  lea     rdx, [rbp+57h+ppv]; ppv
0x1800c1031  mov     [rbp+57h+ppv], 0
0x1800c1039  lea     rcx, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x1800c1040  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800c1046  mov     ebx, eax
0x1800c1048  test    eax, eax
0x1800c104a  js      loc_1800C112A
0x1800c1050  mov     r8d, [rdi]; value
0x1800c1053  lea     rdx, aMaxResults; "Max Results"
0x1800c105a  mov     rcx, [rbp+57h+ppv]; propBag
0x1800c105e  call    cs:__imp_PSPropertyBag_WriteDWORD
0x1800c1064  mov     ebx, eax
0x1800c1066  test    eax, eax
0x1800c1068  js      loc_1800C111A
0x1800c106e  mov     r8, [rdi+8]; punk
0x1800c1072  test    r8, r8
0x1800c1075  jz      short loc_1800C1092
0x1800c1077  mov     rcx, [rbp+57h+ppv]; propBag
0x1800c107b  lea     rdx, aSortColumns; "Sort Columns"
0x1800c1082  call    cs:__imp_PSPropertyBag_WriteUnknown
0x1800c1088  mov     ebx, eax
0x1800c108a  test    eax, eax
0x1800c108c  js      loc_1800C111A
0x1800c1092  mov     r8, [rdi+10h]; punk
0x1800c1096  test    r8, r8
0x1800c1099  jz      short loc_1800C10AE
0x1800c109b  mov     rcx, [rbp+57h+ppv]; propBag
0x1800c109f  lea     rdx, aPropList; "Prop List"
0x1800c10a6  call    cs:__imp_PSPropertyBag_WriteUnknown
0x1800c10ac  mov     ebx, eax
0x1800c10ae  test    ebx, ebx
0x1800c10b0  js      short loc_1800C111A
0x1800c10b2  movaps  xmm0, xmmword ptr cs:aPostEnumeratio; "Post Enumeration Operation Hints"
0x1800c10b9  lea     rdx, [rbp+57h+var_70]
0x1800c10bd  movaps  xmm1, xmmword ptr cs:aPostEnumeratio+10h; "meration Operation Hints"
0x1800c10c4  movzx   eax, word ptr cs:aPostEnumeratio+40h; ""
0x1800c10cb  mov     rcx, [rbp+57h+ppbc]
0x1800c10cf  mov     r8, [rbp+57h+ppv]
0x1800c10d3  movaps  [rbp+57h+var_70], xmm0
0x1800c10d7  movaps  xmm0, xmmword ptr cs:aPostEnumeratio+20h; " Operation Hints"
0x1800c10de  movaps  [rbp+57h+var_60], xmm1
0x1800c10e2  movaps  xmm1, xmmword ptr cs:aPostEnumeratio+30h; "on Hints"
0x1800c10e9  mov     [rbp+57h+var_30], ax
0x1800c10ed  movaps  [rbp+57h+var_50], xmm0
0x1800c10f1  movaps  [rbp+57h+var_40], xmm1
0x1800c10f5  mov     rax, [rcx]
0x1800c10f8  mov     rax, [rax+48h]
0x1800c10fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1101  mov     ebx, eax
0x1800c1103  test    eax, eax
0x1800c1105  js      short loc_1800C111A
0x1800c1107  mov     rcx, [rbp+57h+ppbc]
0x1800c110b  mov     [rsi], rcx
0x1800c110e  mov     rax, [rcx]
0x1800c1111  mov     rax, [rax+8]
0x1800c1115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c111a  mov     rcx, [rbp+57h+ppv]
0x1800c111e  mov     rax, [rcx]
0x1800c1121  mov     rax, [rax+10h]
0x1800c1125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c112a  mov     rcx, [rbp+57h+ppbc]
0x1800c112e  mov     rax, [rcx]
0x1800c1131  mov     rax, [rax+10h]
0x1800c1135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c113a  mov     eax, ebx
0x1800c113c  mov     rcx, [rbp+57h+var_20]
0x1800c1140  xor     rcx, rsp; StackCookie
0x1800c1143  call    __security_check_cookie
0x1800c1148  mov     rbx, [rsp+0A0h+arg_0]
0x1800c1150  add     rsp, 90h
0x1800c1157  pop     rdi
0x1800c1158  pop     rsi
0x1800c1159  pop     rbp
0x1800c115a  retn
```

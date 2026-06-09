# XcAddWhitespace(IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x1800124bc`
- end: `0x18001259d`
- name: `?XcAddWhitespace@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `225`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011f90`

## callees

- `0x1800124bc`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800124e9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800124e9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180012585`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800124f9`
- `OLEAUT32!__imp_SysFreeString` at `0x180012585`

## pseudocode

```c
__int64 __fastcall XcAddWhitespace(struct IXMLDOMDocument2 *a1, struct IXMLDOMNode *a2)
{
  OLECHAR *v4; // rbx
  int v5; // eax
  unsigned int v6; // edi
  int v7; // eax
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  SysFreeString(0);
  v4 = SysAllocString(L"\n");
  if ( v4 )
  {
    SysFreeString(0);
    v5 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, __int64 *))a1->lpVtbl->createTextNode)(
           a1,
           v4,
           &v9);
    v6 = v5;
    if ( v5 >= 0 )
      goto LABEL_6;
    if ( (v5 & 0x1FFF0000) == 0x70000 )
      v6 = (unsigned __int16)v5;
    if ( !v6 )
    {
LABEL_6:
      v7 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))a2->lpVtbl->appendChild)(a2, v9, 0);
      v6 = v7;
      if ( v7 < 0 )
      {
        if ( (v7 & 0x1FFF0000) == 0x70000 )
          v6 = (unsigned __int16)v7;
      }
      else
      {
        v6 = 0;
      }
    }
  }
  else
  {
    v4 = 0;
    v6 = 14;
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  SysFreeString(v4);
  return v6;
}

```

## disassembly

```asm
0x1800124bc  mov     [rsp+arg_0], rbx
0x1800124c1  mov     [rsp+arg_8], rsi
0x1800124c6  push    rdi
0x1800124c7  sub     rsp, 20h
0x1800124cb  mov     rdi, rcx
0x1800124ce  mov     [rsp+28h+arg_10], 0
0x1800124d7  xor     ecx, ecx; bstrString
0x1800124d9  mov     rsi, rdx
0x1800124dc  call    cs:__imp_SysFreeString
0x1800124e2  lea     rcx, asc_180016238; "\n"
0x1800124e9  call    cs:__imp_SysAllocString
0x1800124ef  mov     rbx, rax
0x1800124f2  test    rax, rax
0x1800124f5  jz      short loc_180012567
0x1800124f7  xor     ecx, ecx; bstrString
0x1800124f9  call    cs:__imp_SysFreeString
0x1800124ff  mov     rax, [rdi]
0x180012502  lea     r8, [rsp+28h+arg_10]
0x180012507  mov     rdx, rbx
0x18001250a  mov     rcx, rdi
0x18001250d  mov     rax, [rax+188h]
0x180012514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012519  mov     edi, eax
0x18001251b  test    eax, eax
0x18001251d  jns     short loc_180012532
0x18001251f  and     eax, 1FFF0000h
0x180012524  cmp     eax, 70000h
0x180012529  jnz     short loc_18001252E
0x18001252b  movzx   edi, di
0x18001252e  test    edi, edi
0x180012530  jnz     short loc_18001256C
0x180012532  mov     rax, [rsi]
0x180012535  xor     r8d, r8d
0x180012538  mov     rdx, [rsp+28h+arg_10]
0x18001253d  mov     rcx, rsi
0x180012540  mov     rax, [rax+0A8h]
0x180012547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001254c  mov     edi, eax
0x18001254e  test    eax, eax
0x180012550  js      short loc_180012556
0x180012552  xor     edi, edi
0x180012554  jmp     short loc_18001256C
0x180012556  and     eax, 1FFF0000h
0x18001255b  cmp     eax, 70000h
0x180012560  jnz     short loc_18001256C
0x180012562  movzx   edi, di
0x180012565  jmp     short loc_18001256C
0x180012567  xor     ebx, ebx
0x180012569  lea     edi, [rbx+0Eh]
0x18001256c  mov     rcx, [rsp+28h+arg_10]
0x180012571  test    rcx, rcx
0x180012574  jz      short loc_180012582
0x180012576  mov     rdx, [rcx]
0x180012579  mov     rax, [rdx+10h]
0x18001257d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012582  mov     rcx, rbx; bstrString
0x180012585  call    cs:__imp_SysFreeString
0x18001258b  mov     rbx, [rsp+28h+arg_0]
0x180012590  mov     eax, edi
0x180012592  mov     rsi, [rsp+28h+arg_8]
0x180012597  add     rsp, 20h
0x18001259b  pop     rdi
0x18001259c  retn
```

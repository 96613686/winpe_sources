# XcLoadXml(IXMLDOMDocument2 *,ushort const *,int *)

- ea: `0x180013334`
- end: `0x1800133da`
- name: `?XcLoadXml@@YAKPEAUIXMLDOMDocument2@@PEBGPEAH@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e3f0`

## callees

- `0x180013334`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001335e`
- `OLEAUT32!__imp_SysAllocString` at `0x18001335e`
- `OLEAUT32!__imp_SysFreeString` at `0x180013355`
- `OLEAUT32!__imp_SysFreeString` at `0x18001336e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800133c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180013355`
- `OLEAUT32!__imp_SysFreeString` at `0x18001336e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800133c2`

## pseudocode

```c
__int64 __fastcall XcLoadXml(struct IXMLDOMDocument2 *a1, const unsigned __int16 *a2, int *a3)
{
  OLECHAR *v6; // rbx
  int v7; // eax
  unsigned int v8; // edi
  __int16 v10; // [rsp+48h] [rbp+20h] BYREF

  v10 = 0;
  SysFreeString(0);
  v6 = SysAllocString(a2);
  if ( !v6 )
  {
    v6 = 0;
    v8 = 14;
    goto LABEL_9;
  }
  SysFreeString(0);
  v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, __int16 *))a1->lpVtbl->loadXML)(a1, v6, &v10);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v8 = 0;
LABEL_7:
    *a3 = v10 == -1;
    goto LABEL_9;
  }
  if ( (v7 & 0x1FFF0000) == 0x70000 )
    v8 = (unsigned __int16)v7;
  if ( !v8 )
    goto LABEL_7;
LABEL_9:
  SysFreeString(v6);
  return v8;
}

```

## disassembly

```asm
0x180013334  mov     [rsp+arg_0], rbx
0x180013339  mov     [rsp+arg_8], rsi
0x18001333e  push    rdi
0x18001333f  sub     rsp, 20h
0x180013343  mov     rdi, rcx
0x180013346  xor     eax, eax
0x180013348  xor     ecx, ecx; bstrString
0x18001334a  mov     [rsp+28h+arg_18], ax
0x18001334f  mov     rsi, r8
0x180013352  mov     rbx, rdx
0x180013355  call    cs:__imp_SysFreeString
0x18001335b  mov     rcx, rbx; psz
0x18001335e  call    cs:__imp_SysAllocString
0x180013364  mov     rbx, rax
0x180013367  test    rax, rax
0x18001336a  jz      short loc_1800133BA
0x18001336c  xor     ecx, ecx; bstrString
0x18001336e  call    cs:__imp_SysFreeString
0x180013374  mov     rax, [rdi]
0x180013377  lea     r8, [rsp+28h+arg_18]
0x18001337c  mov     rdx, rbx
0x18001337f  mov     rcx, rdi
0x180013382  mov     rax, [rax+208h]
0x180013389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001338e  mov     edi, eax
0x180013390  test    eax, eax
0x180013392  js      short loc_180013398
0x180013394  xor     edi, edi
0x180013396  jmp     short loc_1800133AB
0x180013398  and     eax, 1FFF0000h
0x18001339d  cmp     eax, 70000h
0x1800133a2  jnz     short loc_1800133A7
0x1800133a4  movzx   edi, di
0x1800133a7  test    edi, edi
0x1800133a9  jnz     short loc_1800133BF
0x1800133ab  xor     eax, eax
0x1800133ad  cmp     [rsp+28h+arg_18], 0FFFFh
0x1800133b3  setz    al
0x1800133b6  mov     [rsi], eax
0x1800133b8  jmp     short loc_1800133BF
0x1800133ba  xor     ebx, ebx
0x1800133bc  lea     edi, [rbx+0Eh]
0x1800133bf  mov     rcx, rbx; bstrString
0x1800133c2  call    cs:__imp_SysFreeString
0x1800133c8  mov     rbx, [rsp+28h+arg_0]
0x1800133cd  mov     eax, edi
0x1800133cf  mov     rsi, [rsp+28h+arg_8]
0x1800133d4  add     rsp, 20h
0x1800133d8  pop     rdi
0x1800133d9  retn
```

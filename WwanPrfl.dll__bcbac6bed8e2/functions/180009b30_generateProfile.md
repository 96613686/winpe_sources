# _generateProfile

- ea: `0x180009b30`
- end: `0x180009c7b`
- name: `_generateProfile`
- size: `331`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, OLECHAR *, __int64, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000dd90`
- `0x18000dea0`

## callees

- `0x180009b30`
- `0x18000a298`
- `0x18000ec80`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180009b65`
- `OLEAUT32!__imp_SysAllocString` at `0x180009b8f`
- `OLEAUT32!__imp_SysAllocString` at `0x180009b65`
- `OLEAUT32!__imp_SysAllocString` at `0x180009b8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b56`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b75`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b80`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c44`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b56`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b75`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b80`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c3b`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c44`

## pseudocode

```c
__int64 __fastcall generateProfile(struct IXMLDOMDocument2 *a1, OLECHAR *a2, __int64 a3, int a4)
{
  OLECHAR *v7; // rdi
  BSTR v8; // rbx
  OLECHAR *v9; // rbx
  BSTR v10; // rsi
  int v11; // eax
  unsigned int v12; // esi
  int v13; // eax
  _QWORD v15[9]; // [rsp+30h] [rbp-48h] BYREF

  v15[0] = 0;
  SysFreeString(0);
  v7 = 0;
  v8 = SysAllocString(L"xml");
  if ( v8 )
  {
    SysFreeString(0);
    v7 = v8;
  }
  SysFreeString(0);
  v9 = 0;
  v10 = SysAllocString(L"version=\"1.0\"");
  if ( v10 )
  {
    SysFreeString(0);
    v9 = v10;
  }
  if ( v7 && v9 )
  {
    v11 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, OLECHAR *, OLECHAR *, _QWORD *))a1->lpVtbl->createProcessingInstruction)(
            a1,
            v7,
            v9,
            v15);
    v12 = v11;
    if ( v11 >= 0 )
      goto LABEL_11;
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v11;
    if ( !v12 )
    {
LABEL_11:
      v13 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, _QWORD, _QWORD))a1->lpVtbl->appendChild)(a1, v15[0], 0);
      v12 = v13;
      if ( v13 < 0 )
      {
        if ( (v13 & 0x1FFF0000) == 0x70000 )
          v12 = (unsigned __int16)v13;
      }
      else
      {
        v12 = 0;
      }
    }
  }
  else
  {
    v12 = 14;
  }
  if ( v15[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v15[0] + 16LL))(v15[0]);
  SysFreeString(v9);
  SysFreeString(v7);
  if ( v12 )
    return v12;
  if ( a4 )
    return _generateDMConfigRootNode(a1, a2);
  return generateRootNode(a1, a2);
}

```

## disassembly

```asm
0x180009b30  push    rbx
0x180009b32  push    rbp
0x180009b33  push    rsi
0x180009b34  push    rdi
0x180009b35  push    r12
0x180009b37  push    r14
0x180009b39  push    r15
0x180009b3b  sub     rsp, 40h
0x180009b3f  mov     r14, rcx
0x180009b42  mov     [rsp+78h+var_48], 0
0x180009b4b  xor     ecx, ecx; bstrString
0x180009b4d  mov     r15d, r9d
0x180009b50  mov     r12d, r8d
0x180009b53  mov     rbp, rdx
0x180009b56  call    cs:__imp_SysFreeString
0x180009b5c  lea     rcx, psz; "xml"
0x180009b63  xor     edi, edi
0x180009b65  call    cs:__imp_SysAllocString
0x180009b6b  mov     rbx, rax
0x180009b6e  test    rax, rax
0x180009b71  jz      short loc_180009B7E
0x180009b73  xor     ecx, ecx; bstrString
0x180009b75  call    cs:__imp_SysFreeString
0x180009b7b  mov     rdi, rbx
0x180009b7e  xor     ecx, ecx; bstrString
0x180009b80  call    cs:__imp_SysFreeString
0x180009b86  lea     rcx, aVersion10; "version=\"1.0\""
0x180009b8d  xor     ebx, ebx
0x180009b8f  call    cs:__imp_SysAllocString
0x180009b95  mov     rsi, rax
0x180009b98  test    rax, rax
0x180009b9b  jz      short loc_180009BA8
0x180009b9d  xor     ecx, ecx; bstrString
0x180009b9f  call    cs:__imp_SysFreeString
0x180009ba5  mov     rbx, rsi
0x180009ba8  test    rdi, rdi
0x180009bab  jz      short loc_180009C1D
0x180009bad  test    rbx, rbx
0x180009bb0  jz      short loc_180009C1D
0x180009bb2  mov     rax, [r14]
0x180009bb5  lea     r9, [rsp+78h+var_48]
0x180009bba  mov     r8, rbx
0x180009bbd  mov     rdx, rdi
0x180009bc0  mov     rcx, r14
0x180009bc3  mov     rax, [rax+1A0h]
0x180009bca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bcf  mov     esi, eax
0x180009bd1  test    eax, eax
0x180009bd3  jns     short loc_180009BE8
0x180009bd5  and     eax, 1FFF0000h
0x180009bda  cmp     eax, 70000h
0x180009bdf  jnz     short loc_180009BE4
0x180009be1  movzx   esi, si
0x180009be4  test    esi, esi
0x180009be6  jnz     short loc_180009C22
0x180009be8  mov     rax, [r14]
0x180009beb  xor     r8d, r8d
0x180009bee  mov     rdx, [rsp+78h+var_48]
0x180009bf3  mov     rcx, r14
0x180009bf6  mov     rax, [rax+0A8h]
0x180009bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c02  mov     esi, eax
0x180009c04  test    eax, eax
0x180009c06  js      short loc_180009C0C
0x180009c08  xor     esi, esi
0x180009c0a  jmp     short loc_180009C22
0x180009c0c  and     eax, 1FFF0000h
0x180009c11  cmp     eax, 70000h
0x180009c16  jnz     short loc_180009C22
0x180009c18  movzx   esi, si
0x180009c1b  jmp     short loc_180009C22
0x180009c1d  mov     esi, 0Eh
0x180009c22  mov     rcx, [rsp+78h+var_48]
0x180009c27  test    rcx, rcx
0x180009c2a  jz      short loc_180009C38
0x180009c2c  mov     rdx, [rcx]
0x180009c2f  mov     rax, [rdx+10h]
0x180009c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c38  mov     rcx, rbx; bstrString
0x180009c3b  call    cs:__imp_SysFreeString
0x180009c41  mov     rcx, rdi; bstrString
0x180009c44  call    cs:__imp_SysFreeString
0x180009c4a  test    esi, esi
0x180009c4c  jz      short loc_180009C52
0x180009c4e  mov     eax, esi
0x180009c50  jmp     short loc_180009C6C
0x180009c52  mov     rdx, rbp; OLECHAR *
0x180009c55  mov     rcx, r14; struct IXMLDOMDocument2 *
0x180009c58  test    r15d, r15d
0x180009c5b  jz      short loc_180009C64
0x180009c5d  call    ?_generateDMConfigRootNode@@YAKPEAUIXMLDOMDocument2@@PEAUWWAN_PROFILE@@@Z; _generateDMConfigRootNode(IXMLDOMDocument2 *,WWAN_PROFILE *)
0x180009c62  jmp     short loc_180009C6C
0x180009c64  mov     r8d, r12d
0x180009c67  call    _generateRootNode
0x180009c6c  add     rsp, 40h
0x180009c70  pop     r15
0x180009c72  pop     r14
0x180009c74  pop     r12
0x180009c76  pop     rdi
0x180009c77  pop     rsi
0x180009c78  pop     rbp
0x180009c79  pop     rbx
0x180009c7a  retn
```

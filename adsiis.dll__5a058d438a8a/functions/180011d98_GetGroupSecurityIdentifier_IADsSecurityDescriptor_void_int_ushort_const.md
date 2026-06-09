# GetGroupSecurityIdentifier(IADsSecurityDescriptor *,void * *,int *,ushort const *)

- ea: `0x180011d98`
- end: `0x180011e5d`
- name: `?GetGroupSecurityIdentifier@@YAJPEAUIADsSecurityDescriptor@@PEAPEAXPEAHPEBG@Z`
- size: `197`
- prototype: `int(struct IADsSecurityDescriptor *, void **, int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800118c4`

## callees

- `0x180011b9c`
- `0x180011d98`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011e48`
- `OLEAUT32!__imp_SysFreeString` at `0x180011e48`

## pseudocode

```c
__int64 __fastcall GetGroupSecurityIdentifier(
        struct IADsSecurityDescriptor *a1,
        void **a2,
        int *a3,
        const unsigned __int16 *a4)
{
  struct IADsSecurityDescriptorVtbl *lpVtbl; // rax
  int v9; // ebx
  OLECHAR *v10; // rcx
  unsigned int v12; // [rsp+20h] [rbp-48h] BYREF
  BSTR bstrString[8]; // [rsp+28h] [rbp-40h] BYREF
  __int16 v14; // [rsp+70h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  bstrString[0] = 0;
  v12 = 0;
  v14 = 0;
  v9 = ((__int64 (__fastcall *)(struct IADsSecurityDescriptor *, BSTR *))lpVtbl->get_Group)(a1, bstrString);
  if ( v9 >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(struct IADsSecurityDescriptor *, __int16 *))a1->lpVtbl->get_GroupDefaulted)(a1, &v14);
    if ( v9 >= 0 )
    {
      v10 = bstrString[0];
      if ( v14 )
      {
        *a2 = 0;
        *a3 = 1;
        goto LABEL_12;
      }
      if ( !bstrString[0] || !*bstrString[0] )
      {
        *a2 = 0;
        goto LABEL_9;
      }
      v9 = ConvertTrusteeToSid(bstrString[0], a2, &v12, a4);
      if ( v9 >= 0 )
      {
        v10 = bstrString[0];
LABEL_9:
        *a3 = 0;
        goto LABEL_12;
      }
    }
  }
  v10 = bstrString[0];
LABEL_12:
  if ( v10 )
    SysFreeString(v10);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011d98  mov     r11, rsp
0x180011d9b  push    rbx
0x180011d9c  push    rbp
0x180011d9d  push    rsi
0x180011d9e  push    rdi
0x180011d9f  push    r14
0x180011da1  push    r15
0x180011da3  sub     rsp, 38h
0x180011da7  mov     rax, [rcx]
0x180011daa  xor     r15d, r15d
0x180011dad  mov     rdi, rdx
0x180011db0  mov     [r11-40h], r15
0x180011db4  lea     rdx, [r11-40h]
0x180011db8  mov     [r11-48h], r15d
0x180011dbc  mov     rbp, r9
0x180011dbf  mov     [r11+8], r15w
0x180011dc4  mov     rax, [rax+78h]
0x180011dc8  mov     rsi, r8
0x180011dcb  mov     r14, rcx
0x180011dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dd3  mov     ebx, eax
0x180011dd5  test    eax, eax
0x180011dd7  js      short loc_180011E3E
0x180011dd9  mov     rax, [r14]
0x180011ddc  lea     rdx, [rsp+68h+arg_0]
0x180011de1  mov     rcx, r14
0x180011de4  mov     rax, [rax+88h]
0x180011deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011df0  mov     ebx, eax
0x180011df2  test    eax, eax
0x180011df4  js      short loc_180011E3E
0x180011df6  mov     rcx, [rsp+68h+bstrString]; lpAccountName
0x180011dfb  cmp     [rsp+68h+arg_0], r15w
0x180011e01  jnz     short loc_180011E33
0x180011e03  test    rcx, rcx
0x180011e06  jz      short loc_180011E2B
0x180011e08  cmp     [rcx], r15w
0x180011e0c  jz      short loc_180011E2B
0x180011e0e  mov     r9, rbp; unsigned __int16 *
0x180011e11  lea     r8, [rsp+68h+var_48]; unsigned int *
0x180011e16  mov     rdx, rdi; void **
0x180011e19  call    ?ConvertTrusteeToSid@@YAJPEAGPEAPEAXPEAKPEBG@Z; ConvertTrusteeToSid(ushort *,void * *,ulong *,ushort const *)
0x180011e1e  mov     ebx, eax
0x180011e20  test    eax, eax
0x180011e22  js      short loc_180011E3E
0x180011e24  mov     rcx, [rsp+68h+bstrString]
0x180011e29  jmp     short loc_180011E2E
0x180011e2b  mov     [rdi], r15
0x180011e2e  mov     [rsi], r15d
0x180011e31  jmp     short loc_180011E43
0x180011e33  mov     [rdi], r15
0x180011e36  mov     dword ptr [rsi], 1
0x180011e3c  jmp     short loc_180011E43
0x180011e3e  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180011e43  test    rcx, rcx
0x180011e46  jz      short loc_180011E4E
0x180011e48  call    cs:__imp_SysFreeString
0x180011e4e  mov     eax, ebx
0x180011e50  add     rsp, 38h
0x180011e54  pop     r15
0x180011e56  pop     r14
0x180011e58  pop     rdi
0x180011e59  pop     rsi
0x180011e5a  pop     rbp
0x180011e5b  pop     rbx
0x180011e5c  retn
```

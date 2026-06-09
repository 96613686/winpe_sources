# GetOwnerSecurityIdentifier(IADsSecurityDescriptor *,void * *,int *,ushort const *)

- ea: `0x180011e64`
- end: `0x180011f26`
- name: `?GetOwnerSecurityIdentifier@@YAJPEAUIADsSecurityDescriptor@@PEAPEAXPEAHPEBG@Z`
- size: `194`
- prototype: `int(struct IADsSecurityDescriptor *, void **, int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800118c4`

## callees

- `0x180011b9c`
- `0x180011e64`
- `0x18001e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011f11`
- `OLEAUT32!__imp_SysFreeString` at `0x180011f11`

## pseudocode

```c
__int64 __fastcall GetOwnerSecurityIdentifier(
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
  v9 = ((__int64 (__fastcall *)(struct IADsSecurityDescriptor *, BSTR *))lpVtbl->get_Owner)(a1, bstrString);
  if ( v9 >= 0 )
  {
    v9 = ((__int64 (__fastcall *)(struct IADsSecurityDescriptor *, __int16 *))a1->lpVtbl->get_OwnerDefaulted)(a1, &v14);
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
0x180011e64  mov     r11, rsp
0x180011e67  push    rbx
0x180011e68  push    rbp
0x180011e69  push    rsi
0x180011e6a  push    rdi
0x180011e6b  push    r14
0x180011e6d  push    r15
0x180011e6f  sub     rsp, 38h
0x180011e73  mov     rax, [rcx]
0x180011e76  xor     r15d, r15d
0x180011e79  mov     rdi, rdx
0x180011e7c  mov     [r11-40h], r15
0x180011e80  lea     rdx, [r11-40h]
0x180011e84  mov     [r11-48h], r15d
0x180011e88  mov     rbp, r9
0x180011e8b  mov     [r11+8], r15w
0x180011e90  mov     rax, [rax+58h]
0x180011e94  mov     rsi, r8
0x180011e97  mov     r14, rcx
0x180011e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e9f  mov     ebx, eax
0x180011ea1  test    eax, eax
0x180011ea3  js      short loc_180011F07
0x180011ea5  mov     rax, [r14]
0x180011ea8  lea     rdx, [rsp+68h+arg_0]
0x180011ead  mov     rcx, r14
0x180011eb0  mov     rax, [rax+68h]
0x180011eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eb9  mov     ebx, eax
0x180011ebb  test    eax, eax
0x180011ebd  js      short loc_180011F07
0x180011ebf  mov     rcx, [rsp+68h+bstrString]; lpAccountName
0x180011ec4  cmp     [rsp+68h+arg_0], r15w
0x180011eca  jnz     short loc_180011EFC
0x180011ecc  test    rcx, rcx
0x180011ecf  jz      short loc_180011EF4
0x180011ed1  cmp     [rcx], r15w
0x180011ed5  jz      short loc_180011EF4
0x180011ed7  mov     r9, rbp; unsigned __int16 *
0x180011eda  lea     r8, [rsp+68h+var_48]; unsigned int *
0x180011edf  mov     rdx, rdi; void **
0x180011ee2  call    ?ConvertTrusteeToSid@@YAJPEAGPEAPEAXPEAKPEBG@Z; ConvertTrusteeToSid(ushort *,void * *,ulong *,ushort const *)
0x180011ee7  mov     ebx, eax
0x180011ee9  test    eax, eax
0x180011eeb  js      short loc_180011F07
0x180011eed  mov     rcx, [rsp+68h+bstrString]
0x180011ef2  jmp     short loc_180011EF7
0x180011ef4  mov     [rdi], r15
0x180011ef7  mov     [rsi], r15d
0x180011efa  jmp     short loc_180011F0C
0x180011efc  mov     [rdi], r15
0x180011eff  mov     dword ptr [rsi], 1
0x180011f05  jmp     short loc_180011F0C
0x180011f07  mov     rcx, [rsp+68h+bstrString]; bstrString
0x180011f0c  test    rcx, rcx
0x180011f0f  jz      short loc_180011F17
0x180011f11  call    cs:__imp_SysFreeString
0x180011f17  mov     eax, ebx
0x180011f19  add     rsp, 38h
0x180011f1d  pop     r15
0x180011f1f  pop     r14
0x180011f21  pop     rdi
0x180011f22  pop     rsi
0x180011f23  pop     rbp
0x180011f24  pop     rbx
0x180011f25  retn
```

# GetDacl(IADsSecurityDescriptor *,_ACL * *,int *,ushort const *)

- ea: `0x180011ca8`
- end: `0x180011d91`
- name: `?GetDacl@@YAJPEAUIADsSecurityDescriptor@@PEAPEAU_ACL@@PEAHPEBG@Z`
- size: `233`
- prototype: `int(struct IADsSecurityDescriptor *, struct _ACL **, int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800118c4`

## callees

- `0x180011630`
- `0x180011ca8`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall GetDacl(struct IADsSecurityDescriptor *a1, struct _ACL **a2, int *a3, const unsigned __int16 *a4)
{
  struct IADsSecurityDescriptorVtbl *lpVtbl; // rax
  int v9; // ebx
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  struct IADsAccessControlList *v12; // [rsp+28h] [rbp-40h] BYREF
  __int16 v13; // [rsp+70h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  v12 = 0;
  v11 = 0;
  v13 = 0;
  v9 = ((__int64 (__fastcall *)(struct IADsSecurityDescriptor *, __int16 *))lpVtbl->get_DaclDefaulted)(a1, &v13);
  if ( v9 >= 0 )
  {
    *a3 = v13 != 0;
    v9 = ((__int64 (__fastcall *)(struct IADsSecurityDescriptor *, __int64 *))a1->lpVtbl->get_DiscretionaryAcl)(
           a1,
           &v11);
    if ( v9 >= 0 )
    {
      if ( !v11 )
      {
        *a2 = 0;
        goto LABEL_9;
      }
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IADsAccessControlList **))v11)(
             v11,
             &IID_IADsAccessControlList,
             &v12);
      if ( v9 >= 0 )
        v9 = ConvertAccessControlListToAcl(v12, a2, a4);
    }
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
LABEL_9:
  if ( v12 )
    ((void (__fastcall *)(struct IADsAccessControlList *))v12->lpVtbl->Release)(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180011ca8  mov     r11, rsp
0x180011cab  push    rbx
0x180011cac  push    rbp
0x180011cad  push    rsi
0x180011cae  push    rdi
0x180011caf  push    r14
0x180011cb1  push    r15
0x180011cb3  sub     rsp, 38h
0x180011cb7  mov     rax, [rcx]
0x180011cba  xor     r15d, r15d
0x180011cbd  mov     rdi, rdx
0x180011cc0  mov     [r11-40h], r15
0x180011cc4  lea     rdx, [r11+8]
0x180011cc8  mov     [r11-48h], r15
0x180011ccc  mov     rbp, r9
0x180011ccf  mov     [r11+8], r15w
0x180011cd4  mov     rax, [rax+0A8h]
0x180011cdb  mov     r14, r8
0x180011cde  mov     rsi, rcx
0x180011ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ce6  mov     ebx, eax
0x180011ce8  test    eax, eax
0x180011cea  js      short loc_180011D56
0x180011cec  cmp     [rsp+68h+arg_0], r15w
0x180011cf2  lea     rdx, [rsp+68h+var_48]
0x180011cf7  mov     eax, r15d
0x180011cfa  mov     rcx, rsi
0x180011cfd  setnz   al
0x180011d00  mov     [r14], eax
0x180011d03  mov     rax, [rsi]
0x180011d06  mov     rax, [rax+98h]
0x180011d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d12  mov     ebx, eax
0x180011d14  test    eax, eax
0x180011d16  js      short loc_180011D56
0x180011d18  mov     rcx, [rsp+68h+var_48]
0x180011d1d  test    rcx, rcx
0x180011d20  jnz     short loc_180011D27
0x180011d22  mov     [rdi], r15
0x180011d25  jmp     short loc_180011D6C
0x180011d27  mov     rax, [rcx]
0x180011d2a  lea     r8, [rsp+68h+var_40]
0x180011d2f  lea     rdx, IID_IADsAccessControlList
0x180011d36  mov     rax, [rax]
0x180011d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d3e  mov     ebx, eax
0x180011d40  test    eax, eax
0x180011d42  js      short loc_180011D56
0x180011d44  mov     rcx, [rsp+68h+var_40]; struct IADsAccessControlList *
0x180011d49  mov     r8, rbp; unsigned __int16 *
0x180011d4c  mov     rdx, rdi; struct _ACL **
0x180011d4f  call    ?ConvertAccessControlListToAcl@@YAJPEAUIADsAccessControlList@@PEAPEAU_ACL@@PEBG@Z; ConvertAccessControlListToAcl(IADsAccessControlList *,_ACL * *,ushort const *)
0x180011d54  mov     ebx, eax
0x180011d56  mov     rcx, [rsp+68h+var_48]
0x180011d5b  test    rcx, rcx
0x180011d5e  jz      short loc_180011D6C
0x180011d60  mov     rax, [rcx]
0x180011d63  mov     rax, [rax+10h]
0x180011d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d6c  mov     rcx, [rsp+68h+var_40]
0x180011d71  test    rcx, rcx
0x180011d74  jz      short loc_180011D82
0x180011d76  mov     rax, [rcx]
0x180011d79  mov     rax, [rax+10h]
0x180011d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d82  mov     eax, ebx
0x180011d84  add     rsp, 38h
0x180011d88  pop     r15
0x180011d8a  pop     r14
0x180011d8c  pop     rdi
0x180011d8d  pop     rsi
0x180011d8e  pop     rbp
0x180011d8f  pop     rbx
0x180011d90  retn
```

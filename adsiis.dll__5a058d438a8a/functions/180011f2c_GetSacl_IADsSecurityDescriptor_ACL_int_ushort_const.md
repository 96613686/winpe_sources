# GetSacl(IADsSecurityDescriptor *,_ACL * *,int *,ushort const *)

- ea: `0x180011f2c`
- end: `0x180012015`
- name: `?GetSacl@@YAJPEAUIADsSecurityDescriptor@@PEAPEAU_ACL@@PEAHPEBG@Z`
- size: `233`
- prototype: `int(struct IADsSecurityDescriptor *, struct _ACL **, int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800118c4`

## callees

- `0x180011630`
- `0x180011f2c`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall GetSacl(struct IADsSecurityDescriptor *a1, struct _ACL **a2, int *a3, const unsigned __int16 *a4)
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
  v9 = ((__int64 (__fastcall *)(struct IADsSecurityDescriptor *, __int16 *))lpVtbl->get_SaclDefaulted)(a1, &v13);
  if ( v9 >= 0 )
  {
    *a3 = v13 != 0;
    v9 = ((__int64 (__fastcall *)(struct IADsSecurityDescriptor *, __int64 *))a1->lpVtbl->get_SystemAcl)(a1, &v11);
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
0x180011f2c  mov     r11, rsp
0x180011f2f  push    rbx
0x180011f30  push    rbp
0x180011f31  push    rsi
0x180011f32  push    rdi
0x180011f33  push    r14
0x180011f35  push    r15
0x180011f37  sub     rsp, 38h
0x180011f3b  mov     rax, [rcx]
0x180011f3e  xor     r15d, r15d
0x180011f41  mov     rdi, rdx
0x180011f44  mov     [r11-40h], r15
0x180011f48  lea     rdx, [r11+8]
0x180011f4c  mov     [r11-48h], r15
0x180011f50  mov     rbp, r9
0x180011f53  mov     [r11+8], r15w
0x180011f58  mov     rax, [rax+0C8h]
0x180011f5f  mov     r14, r8
0x180011f62  mov     rsi, rcx
0x180011f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f6a  mov     ebx, eax
0x180011f6c  test    eax, eax
0x180011f6e  js      short loc_180011FDA
0x180011f70  cmp     [rsp+68h+arg_0], r15w
0x180011f76  lea     rdx, [rsp+68h+var_48]
0x180011f7b  mov     eax, r15d
0x180011f7e  mov     rcx, rsi
0x180011f81  setnz   al
0x180011f84  mov     [r14], eax
0x180011f87  mov     rax, [rsi]
0x180011f8a  mov     rax, [rax+0B8h]
0x180011f91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f96  mov     ebx, eax
0x180011f98  test    eax, eax
0x180011f9a  js      short loc_180011FDA
0x180011f9c  mov     rcx, [rsp+68h+var_48]
0x180011fa1  test    rcx, rcx
0x180011fa4  jnz     short loc_180011FAB
0x180011fa6  mov     [rdi], r15
0x180011fa9  jmp     short loc_180011FF0
0x180011fab  mov     rax, [rcx]
0x180011fae  lea     r8, [rsp+68h+var_40]
0x180011fb3  lea     rdx, IID_IADsAccessControlList
0x180011fba  mov     rax, [rax]
0x180011fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011fc2  mov     ebx, eax
0x180011fc4  test    eax, eax
0x180011fc6  js      short loc_180011FDA
0x180011fc8  mov     rcx, [rsp+68h+var_40]; struct IADsAccessControlList *
0x180011fcd  mov     r8, rbp; unsigned __int16 *
0x180011fd0  mov     rdx, rdi; struct _ACL **
0x180011fd3  call    ?ConvertAccessControlListToAcl@@YAJPEAUIADsAccessControlList@@PEAPEAU_ACL@@PEBG@Z; ConvertAccessControlListToAcl(IADsAccessControlList *,_ACL * *,ushort const *)
0x180011fd8  mov     ebx, eax
0x180011fda  mov     rcx, [rsp+68h+var_48]
0x180011fdf  test    rcx, rcx
0x180011fe2  jz      short loc_180011FF0
0x180011fe4  mov     rax, [rcx]
0x180011fe7  mov     rax, [rax+10h]
0x180011feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ff0  mov     rcx, [rsp+68h+var_40]
0x180011ff5  test    rcx, rcx
0x180011ff8  jz      short loc_180012006
0x180011ffa  mov     rax, [rcx]
0x180011ffd  mov     rax, [rax+10h]
0x180012001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012006  mov     eax, ebx
0x180012008  add     rsp, 38h
0x18001200c  pop     r15
0x18001200e  pop     r14
0x180012010  pop     rdi
0x180012011  pop     rsi
0x180012012  pop     rbp
0x180012013  pop     rbx
0x180012014  retn
```

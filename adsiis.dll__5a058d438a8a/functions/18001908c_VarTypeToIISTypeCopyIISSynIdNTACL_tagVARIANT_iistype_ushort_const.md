# VarTypeToIISTypeCopyIISSynIdNTACL(tagVARIANT *,_iistype *,ushort const *)

- ea: `0x18001908c`
- end: `0x180019164`
- name: `?VarTypeToIISTypeCopyIISSynIdNTACL@@YAJPEAUtagVARIANT@@PEAU_iistype@@PEBG@Z`
- size: `216`
- prototype: `int(struct tagVARIANT *, struct _iistype *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018a44`

## callees

- `0x1800118c4`
- `0x18001908c`
- `0x18001d652`
- `0x18001e010`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x180019113`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180019113`

## pseudocode

```c
__int64 __fastcall VarTypeToIISTypeCopyIISSynIdNTACL(
        struct tagVARIANT *a1,
        struct _iistype *a2,
        const unsigned __int16 *a3)
{
  bool v3; // zf
  int v7; // ebx
  size_t v8; // rdi
  void *v9; // rax
  void *v10; // rdx
  void *Src; // [rsp+20h] [rbp-18h] BYREF
  DWORD cb; // [rsp+40h] [rbp+8h] BYREF
  struct IADsSecurityDescriptor *v13; // [rsp+58h] [rbp+20h] BYREF

  v3 = a1->vt == 9;
  v13 = 0;
  Src = 0;
  cb = 0;
  if ( !v3 )
    return 2147504140LL;
  *(_DWORD *)a2 = 5;
  v7 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, struct IADsSecurityDescriptor **))a1->llVal)(
         a1->llVal,
         &IID_IADsSecurityDescriptor,
         &v13);
  if ( v7 >= 0 )
  {
    v7 = ConvertSecurityDescriptorToSecDes(v13, &Src, &cb, a3);
    if ( v7 >= 0 )
    {
      v8 = cb;
      v9 = AllocADsMem(cb);
      *((_QWORD *)a2 + 2) = v9;
      if ( v9 )
      {
        v10 = Src;
        *((_DWORD *)a2 + 2) = v8;
        memcpy_0(v9, v10, v8);
      }
      else
      {
        v7 = -2147024882;
      }
    }
  }
  if ( v13 )
    ((void (__fastcall *)(struct IADsSecurityDescriptor *))v13->lpVtbl->Release)(v13);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001908c  mov     rax, rsp
0x18001908f  mov     [rax+10h], rbx
0x180019093  mov     [rax+18h], rsi
0x180019097  push    rdi
0x180019098  sub     rsp, 30h
0x18001909c  cmp     word ptr [rcx], 9
0x1800190a0  mov     rdi, r8
0x1800190a3  mov     rsi, rdx
0x1800190a6  mov     qword ptr [rax+20h], 0
0x1800190ae  mov     qword ptr [rax-18h], 0
0x1800190b6  mov     dword ptr [rax+8], 0
0x1800190bd  jz      short loc_1800190C9
0x1800190bf  mov     eax, 8000500Ch
0x1800190c4  jmp     loc_180019154
0x1800190c9  mov     dword ptr [rdx], 5
0x1800190cf  lea     r8, [rsp+38h+arg_18]
0x1800190d4  mov     rcx, [rcx+8]
0x1800190d8  lea     rdx, IID_IADsSecurityDescriptor
0x1800190df  mov     rax, [rcx]
0x1800190e2  mov     rax, [rax]
0x1800190e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190ea  mov     ebx, eax
0x1800190ec  test    eax, eax
0x1800190ee  js      short loc_18001913C
0x1800190f0  mov     rcx, [rsp+38h+arg_18]; struct IADsSecurityDescriptor *
0x1800190f5  lea     r8, [rsp+38h+cb]; unsigned int *
0x1800190fa  mov     r9, rdi; unsigned __int16 *
0x1800190fd  lea     rdx, [rsp+38h+Src]; void **
0x180019102  call    ?ConvertSecurityDescriptorToSecDes@@YAJPEAUIADsSecurityDescriptor@@PEAPEAXPEAKPEBG@Z; ConvertSecurityDescriptorToSecDes(IADsSecurityDescriptor *,void * *,ulong *,ushort const *)
0x180019107  mov     ebx, eax
0x180019109  test    eax, eax
0x18001910b  js      short loc_18001913C
0x18001910d  mov     edi, [rsp+38h+cb]
0x180019111  mov     ecx, edi; cb
0x180019113  call    cs:__imp_AllocADsMem
0x180019119  mov     [rsi+10h], rax
0x18001911d  test    rax, rax
0x180019120  jnz     short loc_180019129
0x180019122  mov     ebx, 8007000Eh
0x180019127  jmp     short loc_18001913C
0x180019129  mov     rdx, [rsp+38h+Src]; Src
0x18001912e  mov     r8, rdi; Size
0x180019131  mov     rcx, rax; void *
0x180019134  mov     [rsi+8], edi
0x180019137  call    memcpy_0
0x18001913c  mov     rcx, [rsp+38h+arg_18]
0x180019141  test    rcx, rcx
0x180019144  jz      short loc_180019152
0x180019146  mov     rax, [rcx]
0x180019149  mov     rax, [rax+10h]
0x18001914d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019152  mov     eax, ebx
0x180019154  mov     rbx, [rsp+38h+arg_8]
0x180019159  mov     rsi, [rsp+38h+arg_10]
0x18001915e  add     rsp, 30h
0x180019162  pop     rdi
0x180019163  retn
```

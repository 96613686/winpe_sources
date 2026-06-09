# VarTypeToIISTypeCopyIISSynIdIPSECLIST(tagVARIANT *,_iistype *)

- ea: `0x180018f20`
- end: `0x180018fae`
- name: `?VarTypeToIISTypeCopyIISSynIdIPSECLIST@@YAJPEAUtagVARIANT@@PEAU_iistype@@@Z`
- size: `142`
- prototype: `__int64 __fastcall(struct tagVARIANT *, struct _iistype *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180018a44`

## callees

- `0x18000e3dc`
- `0x180018f20`
- `0x18001d652`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x180018f82`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180018f82`

## pseudocode

```c
__int64 __fastcall VarTypeToIISTypeCopyIISSynIdIPSECLIST(struct tagVARIANT *a1, struct _iistype *a2)
{
  unsigned int v4; // ebp
  DWORD v5; // ebx
  DWORD v6; // ecx
  void *v7; // rax
  void *v8; // rdx
  DWORD cb; // [rsp+30h] [rbp+8h] BYREF
  void *Src; // [rsp+40h] [rbp+18h] BYREF

  Src = 0;
  cb = 0;
  if ( a1->vt != 9 )
    return 2147504140LL;
  *(_DWORD *)a2 = 9;
  v4 = CIPSecurity::CopyIPSecurity((CIPSecurity *)a1->llVal, (unsigned __int8 **)&Src, &cb);
  if ( !Src )
    return 2147942414LL;
  v5 = cb;
  v6 = cb;
  *((_DWORD *)a2 + 2) = cb;
  v7 = AllocADsMem(v6);
  v8 = Src;
  *((_QWORD *)a2 + 2) = v7;
  memcpy_0(v7, v8, v5);
  return v4;
}

```

## disassembly

```asm
0x180018f20  mov     rax, rsp
0x180018f23  mov     [rax+10h], rbx
0x180018f27  mov     [rax+20h], rbp
0x180018f2b  push    rdi
0x180018f2c  sub     rsp, 20h
0x180018f30  mov     qword ptr [rax+18h], 0
0x180018f38  mov     rdi, rdx
0x180018f3b  mov     dword ptr [rax+8], 0
0x180018f42  mov     eax, 9
0x180018f47  cmp     [rcx], ax
0x180018f4a  jz      short loc_180018F53
0x180018f4c  mov     eax, 8000500Ch
0x180018f51  jmp     short loc_180018F9E
0x180018f53  mov     [rdx], eax
0x180018f55  lea     r8, [rsp+28h+cb]; unsigned int *
0x180018f5a  mov     rcx, [rcx+8]; this
0x180018f5e  lea     rdx, [rsp+28h+Src]; unsigned __int8 **
0x180018f63  call    ?CopyIPSecurity@CIPSecurity@@QEAAJPEAPEAEPEAK@Z; CIPSecurity::CopyIPSecurity(uchar * *,ulong *)
0x180018f68  cmp     [rsp+28h+Src], 0
0x180018f6e  mov     ebp, eax
0x180018f70  jnz     short loc_180018F79
0x180018f72  mov     eax, 8007000Eh
0x180018f77  jmp     short loc_180018F9E
0x180018f79  mov     ebx, [rsp+28h+cb]
0x180018f7d  mov     ecx, ebx; cb
0x180018f7f  mov     [rdi+8], ebx
0x180018f82  call    cs:__imp_AllocADsMem
0x180018f88  mov     rdx, [rsp+28h+Src]; Src
0x180018f8d  mov     r8d, ebx; Size
0x180018f90  mov     rcx, rax; void *
0x180018f93  mov     [rdi+10h], rax
0x180018f97  call    memcpy_0
0x180018f9c  mov     eax, ebp
0x180018f9e  mov     rbx, [rsp+28h+arg_8]
0x180018fa3  mov     rbp, [rsp+28h+arg_18]
0x180018fa8  add     rsp, 20h
0x180018fac  pop     rdi
0x180018fad  retn
```

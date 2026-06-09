# ABO_NODE::CopyPropertiesAndChildren(ABO_NODE *)

- ea: `0x180006f54`
- end: `0x18000707a`
- name: `?CopyPropertiesAndChildren@ABO_NODE@@QEAAJPEAV1@@Z`
- size: `294`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, struct ABO_NODE *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006f54`
- `0x18000c560`
- `0x18000f110`

## callees

- `0x18000473c`
- `0x180006f54`
- `0x180007148`
- `0x180007ac8`
- `0x18000a6fc`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180006fd9`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180007000`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180006fd9`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180007000`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180006f9a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180006f9a`

## pseudocode

```c
__int64 __fastcall ABO_NODE::CopyPropertiesAndChildren(ABO_NODE *this, struct ABO_NODE *a2)
{
  int v4; // edi
  __int64 v5; // rbx
  struct _METADATA_RECORD *Ptr; // rax
  const unsigned __int16 *Str; // rax
  ABO_NODE *v9; // [rsp+78h] [rbp+10h] BYREF

  v9 = 0;
  if ( a2 )
  {
    v4 = 0;
    v5 = 0;
    if ( *((_DWORD *)a2 + 50) )
    {
      while ( 1 )
      {
        Ptr = (struct _METADATA_RECORD *)BUFFER::QueryPtr((BUFFER *)(*(_QWORD *)(*((_QWORD *)a2 + 24) + 8 * v5) + 16LL));
        v4 = ABO_NODE::SetData(this, Ptr, 0);
        if ( v4 < 0 )
          break;
        v5 = (unsigned int)(v5 + 1);
        if ( (unsigned int)v5 >= *((_DWORD *)a2 + 50) )
          goto LABEL_6;
      }
    }
    else
    {
LABEL_6:
      if ( *((_DWORD *)a2 + 10) )
      {
        Str = STRU::QueryStr((STRU *)(**((_QWORD **)a2 + 4) + 56LL));
        ABO_NODE::FindNode(this, Str, &v9);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006f54  push    rbx
0x180006f56  push    rbp
0x180006f57  push    rsi
0x180006f58  push    rdi
0x180006f59  push    r14
0x180006f5b  push    r15
0x180006f5d  sub     rsp, 38h
0x180006f61  mov     [rsp+68h+arg_8], 0
0x180006f6a  mov     rsi, rdx
0x180006f6d  mov     r14, rcx
0x180006f70  test    rdx, rdx
0x180006f73  jnz     short loc_180006F7F
0x180006f75  mov     edi, 80070057h
0x180006f7a  jmp     loc_18000706B
0x180006f7f  xor     edi, edi
0x180006f81  xor     ebx, ebx
0x180006f83  cmp     [rdx+0C8h], ebx
0x180006f89  jbe     short loc_180006FC2
0x180006f8b  mov     rax, [rsi+0C0h]
0x180006f92  mov     rcx, [rax+rbx*8]
0x180006f96  add     rcx, 10h
0x180006f9a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180006fa0  xor     r8d, r8d; int
0x180006fa3  mov     rcx, r14; this
0x180006fa6  mov     rdx, rax; struct _METADATA_RECORD *
0x180006fa9  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x180006fae  mov     edi, eax
0x180006fb0  test    eax, eax
0x180006fb2  js      loc_18000706B
0x180006fb8  inc     ebx
0x180006fba  cmp     ebx, [rsi+0C8h]
0x180006fc0  jb      short loc_180006F8B
0x180006fc2  xor     ebp, ebp
0x180006fc4  cmp     [rsi+28h], ebp
0x180006fc7  jbe     loc_18000706B
0x180006fcd  mov     rax, [rsi+20h]
0x180006fd1  mov     rbx, [rax+rbp*8]
0x180006fd5  lea     rcx, [rbx+38h]
0x180006fd9  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180006fdf  lea     r8, [rsp+68h+arg_8]; struct ABO_NODE **
0x180006fe4  mov     rcx, r14; this
0x180006fe7  mov     rdx, rax; unsigned __int16 *
0x180006fea  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x180006fef  mov     edi, eax
0x180006ff1  test    eax, eax
0x180006ff3  jns     short loc_180007027
0x180006ff5  cmp     eax, 80070003h
0x180006ffa  jnz     short loc_180007059
0x180006ffc  lea     rcx, [rbx+38h]
0x180007000  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180007006  lea     r9, [rsp+68h+arg_8]; struct ABO_NODE **
0x18000700b  mov     [rsp+68h+var_48], 1; int
0x180007013  mov     rdx, rax; unsigned __int16 *
0x180007016  xor     r8d, r8d; int
0x180007019  mov     rcx, r14; this
0x18000701c  call    ?CreateNode@ABO_NODE@@QEAAJPEBGHPEAPEAV1@H@Z; ABO_NODE::CreateNode(ushort const *,int,ABO_NODE * *,int)
0x180007021  mov     edi, eax
0x180007023  test    eax, eax
0x180007025  js      short loc_180007059
0x180007027  mov     rdx, rbx; struct ABO_NODE *
0x18000702a  mov     rbx, [rsp+68h+arg_8]
0x18000702f  mov     rcx, rbx; this
0x180007032  call    ?CopyPropertiesAndChildren@ABO_NODE@@QEAAJPEAV1@@Z; ABO_NODE::CopyPropertiesAndChildren(ABO_NODE *)
0x180007037  mov     edi, eax
0x180007039  test    eax, eax
0x18000703b  js      short loc_18000705E
0x18000703d  mov     rcx, rbx; this
0x180007040  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180007045  xor     ebx, ebx
0x180007047  inc     ebp
0x180007049  mov     [rsp+68h+arg_8], rbx
0x18000704e  cmp     ebp, [rsi+28h]
0x180007051  jb      loc_180006FCD
0x180007057  jmp     short loc_18000705E
0x180007059  mov     rbx, [rsp+68h+arg_8]
0x18000705e  test    rbx, rbx
0x180007061  jz      short loc_18000706B
0x180007063  mov     rcx, rbx; this
0x180007066  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x18000706b  mov     eax, edi
0x18000706d  add     rsp, 38h
0x180007071  pop     r15
0x180007073  pop     r14
0x180007075  pop     rdi
0x180007076  pop     rsi
0x180007077  pop     rbp
0x180007078  pop     rbx
0x180007079  retn
```

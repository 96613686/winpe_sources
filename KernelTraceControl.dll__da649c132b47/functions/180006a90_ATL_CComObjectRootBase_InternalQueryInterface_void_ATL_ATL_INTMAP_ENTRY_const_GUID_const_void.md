# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180006a90`
- end: `0x180006baa`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `282`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800054f0`
- `0x180005b80`
- `0x180005d00`

## callees

- `0x180006a90`
- `0x180027910`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  unsigned int v4; // edi
  const struct ATL::_ATL_INTMAP_ENTRY *v7; // rbx
  __int64 v9; // rbx
  char *v10; // rbx
  _DWORD *v11; // rbp
  __int64 (__fastcall *v12)(char *, const struct _GUID *, char **, _QWORD); // rax
  int v13; // eax

  v4 = 0;
  v7 = a2;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  if ( !a4 )
    return (unsigned int)-2147467261;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v9 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  if ( !*((_QWORD *)a2 + 2) )
    return (unsigned int)-2147467262;
  while ( 1 )
  {
    v11 = *(_DWORD **)v7;
    if ( *(_QWORD *)v7
      && (*v11 != a3->Data1
       || v11[1] != *(_DWORD *)&a3->Data2
       || v11[2] != *(_DWORD *)a3->Data4
       || v11[3] != *(_DWORD *)&a3->Data4[4]) )
    {
      goto LABEL_20;
    }
    v12 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v7 + 2);
    if ( v12 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      break;
    v13 = v12(a1, a3, a4, *((_QWORD *)v7 + 1));
    if ( !v13 || v11 && v13 < 0 )
      return (unsigned int)v13;
LABEL_20:
    v7 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v7 + 24);
    if ( !*((_QWORD *)v7 + 2) )
      return (unsigned int)-2147467262;
  }
  v9 = *((_QWORD *)v7 + 1);
LABEL_9:
  v10 = &a1[v9];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
  *a4 = v10;
  return v4;
}

```

## disassembly

```asm
0x180006a90  mov     [rsp+arg_0], rbx
0x180006a95  mov     [rsp+arg_8], rbp
0x180006a9a  mov     [rsp+arg_10], rsi
0x180006a9f  push    rdi
0x180006aa0  push    r14
0x180006aa2  push    r15
0x180006aa4  sub     rsp, 30h
0x180006aa8  xor     edi, edi
0x180006aaa  mov     r14, r9
0x180006aad  mov     rsi, r8
0x180006ab0  mov     rbx, rdx
0x180006ab3  mov     r15, rcx
0x180006ab6  test    rcx, rcx
0x180006ab9  jz      loc_180006B8A
0x180006abf  test    rdx, rdx
0x180006ac2  jz      loc_180006B8A
0x180006ac8  test    r9, r9
0x180006acb  jnz     short loc_180006AD7
0x180006acd  mov     edi, 80004003h
0x180006ad2  jmp     loc_180006B8F
0x180006ad7  mov     [r9], rdi
0x180006ada  cmp     [r8], edi
0x180006add  jnz     short loc_180006B15
0x180006adf  cmp     [r8+4], edi
0x180006ae3  jnz     short loc_180006B15
0x180006ae5  cmp     dword ptr [r8+8], 0C0h
0x180006aed  jnz     short loc_180006B15
0x180006aef  cmp     dword ptr [r8+0Ch], 46000000h
0x180006af7  jnz     short loc_180006B15
0x180006af9  mov     rbx, [rdx+8]
0x180006afd  add     rbx, r15
0x180006b00  mov     rcx, rbx
0x180006b03  mov     rax, [rbx]
0x180006b06  mov     rax, [rax+8]
0x180006b0a  call    cs:__guard_dispatch_icall_fptr
0x180006b10  mov     [r14], rbx
0x180006b13  jmp     short loc_180006B8F
0x180006b15  cmp     [rdx+10h], rdi
0x180006b19  jz      short loc_180006B76
0x180006b1b  mov     rbp, [rbx]
0x180006b1e  test    rbp, rbp
0x180006b21  jz      short loc_180006B42
0x180006b23  mov     eax, [rsi]
0x180006b25  cmp     [rbp+0], eax
0x180006b28  jnz     short loc_180006B6C
0x180006b2a  mov     eax, [rsi+4]
0x180006b2d  cmp     [rbp+4], eax
0x180006b30  jnz     short loc_180006B6C
0x180006b32  mov     eax, [rsi+8]
0x180006b35  cmp     [rbp+8], eax
0x180006b38  jnz     short loc_180006B6C
0x180006b3a  mov     eax, [rsi+0Ch]
0x180006b3d  cmp     [rbp+0Ch], eax
0x180006b40  jnz     short loc_180006B6C
0x180006b42  mov     rax, [rbx+10h]
0x180006b46  cmp     rax, 1
0x180006b4a  jz      short loc_180006B81
0x180006b4c  mov     r9, [rbx+8]
0x180006b50  mov     r8, r14
0x180006b53  mov     rdx, rsi
0x180006b56  mov     rcx, r15
0x180006b59  call    cs:__guard_dispatch_icall_fptr
0x180006b5f  test    eax, eax
0x180006b61  jz      short loc_180006B7D
0x180006b63  test    rbp, rbp
0x180006b66  jz      short loc_180006B6C
0x180006b68  test    eax, eax
0x180006b6a  js      short loc_180006B7D
0x180006b6c  add     rbx, 18h
0x180006b70  cmp     [rbx+10h], rdi
0x180006b74  jnz     short loc_180006B1B
0x180006b76  mov     edi, 80004002h
0x180006b7b  jmp     short loc_180006B8F
0x180006b7d  mov     edi, eax
0x180006b7f  jmp     short loc_180006B8F
0x180006b81  mov     rbx, [rbx+8]
0x180006b85  jmp     loc_180006AFD
0x180006b8a  mov     edi, 80070057h
0x180006b8f  mov     rbx, [rsp+48h+arg_0]
0x180006b94  mov     eax, edi
0x180006b96  mov     rbp, [rsp+48h+arg_8]
0x180006b9b  mov     rsi, [rsp+48h+arg_10]
0x180006ba0  add     rsp, 30h
0x180006ba4  pop     r15
0x180006ba6  pop     r14
0x180006ba8  pop     rdi
0x180006ba9  retn
```

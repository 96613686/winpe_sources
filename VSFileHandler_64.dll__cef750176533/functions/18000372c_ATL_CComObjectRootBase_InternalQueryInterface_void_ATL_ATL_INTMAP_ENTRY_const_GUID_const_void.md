# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000372c`
- end: `0x180003832`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002ed0`
- `0x1800031f0`
- `0x1800032b0`

## callees

- `0x18000372c`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  unsigned int v4; // edi
  __int64 v8; // rbx
  char *v9; // rbx
  _QWORD *i; // rsi
  _DWORD *v11; // rbp
  int v12; // eax

  v4 = 0;
  if ( !a1 || !a2 )
    return (unsigned int)-2147024809;
  if ( !a4 )
    return (unsigned int)-2147467261;
  if ( !a3->Data1 && !*(_DWORD *)&a3->Data2 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v8 = *((_QWORD *)a2 + 1);
    goto LABEL_10;
  }
  for ( i = (_QWORD *)((char *)a2 + 16); ; i += 3 )
  {
    if ( !*i )
    {
      v12 = -2147467262;
LABEL_24:
      *a4 = 0;
      return (unsigned int)v12;
    }
    v11 = (_DWORD *)*(i - 2);
    if ( !v11
      || *v11 == a3->Data1
      && v11[1] == *(_DWORD *)&a3->Data2
      && v11[2] == *(_DWORD *)a3->Data4
      && v11[3] == *(_DWORD *)&a3->Data4[4] )
    {
      break;
    }
LABEL_21:
    ;
  }
  if ( *i != 1 )
  {
    v12 = ((__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*i)(a1, a3, a4, *(i - 1));
    if ( !v12 )
      return v4;
    if ( v11 && v12 < 0 )
      goto LABEL_24;
    goto LABEL_21;
  }
  v8 = *(i - 1);
LABEL_10:
  v9 = &a1[v8];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 8LL))(v9);
  *a4 = v9;
  return v4;
}

```

## disassembly

```asm
0x18000372c  mov     [rsp+arg_0], rbx
0x180003731  mov     [rsp+arg_8], rbp
0x180003736  mov     [rsp+arg_10], rsi
0x18000373b  push    rdi
0x18000373c  push    r14
0x18000373e  push    r15
0x180003740  sub     rsp, 20h
0x180003744  xor     edi, edi
0x180003746  mov     r14, r9
0x180003749  mov     rbx, r8
0x18000374c  mov     r15, rcx
0x18000374f  test    rcx, rcx
0x180003752  jz      loc_180003812
0x180003758  test    rdx, rdx
0x18000375b  jz      loc_180003812
0x180003761  test    r9, r9
0x180003764  jnz     short loc_180003770
0x180003766  mov     edi, 80004003h
0x18000376b  jmp     loc_180003817
0x180003770  cmp     [r8], edi
0x180003773  jnz     short loc_1800037A4
0x180003775  cmp     [r8+4], edi
0x180003779  jnz     short loc_1800037A4
0x18000377b  cmp     dword ptr [r8+8], 0C0h
0x180003783  jnz     short loc_1800037A4
0x180003785  cmp     dword ptr [r8+0Ch], 46000000h
0x18000378d  jnz     short loc_1800037A4
0x18000378f  mov     rbx, [rdx+8]
0x180003793  add     rbx, r15
0x180003796  mov     rcx, rbx
0x180003799  mov     rax, [rbx]
0x18000379c  call    qword ptr [rax+8]
0x18000379f  mov     [r14], rbx
0x1800037a2  jmp     short loc_180003817
0x1800037a4  lea     rsi, [rdx+10h]
0x1800037a8  jmp     short loc_1800037FB
0x1800037aa  mov     rbp, [rsi-10h]
0x1800037ae  test    rbp, rbp
0x1800037b1  jz      short loc_1800037D2
0x1800037b3  mov     eax, [rbx]
0x1800037b5  cmp     [rbp+0], eax
0x1800037b8  jnz     short loc_1800037F7
0x1800037ba  mov     eax, [rbx+4]
0x1800037bd  cmp     [rbp+4], eax
0x1800037c0  jnz     short loc_1800037F7
0x1800037c2  mov     eax, [rbx+8]
0x1800037c5  cmp     [rbp+8], eax
0x1800037c8  jnz     short loc_1800037F7
0x1800037ca  mov     eax, [rbx+0Ch]
0x1800037cd  cmp     [rbp+0Ch], eax
0x1800037d0  jnz     short loc_1800037F7
0x1800037d2  mov     rax, [rsi]
0x1800037d5  cmp     rax, 1
0x1800037d9  jz      short loc_18000380C
0x1800037db  mov     r9, [rsi-8]
0x1800037df  mov     r8, r14
0x1800037e2  mov     rdx, rbx
0x1800037e5  mov     rcx, r15
0x1800037e8  call    rax
0x1800037ea  test    eax, eax
0x1800037ec  jz      short loc_180003817
0x1800037ee  test    rbp, rbp
0x1800037f1  jz      short loc_1800037F7
0x1800037f3  test    eax, eax
0x1800037f5  js      short loc_180003805
0x1800037f7  add     rsi, 18h
0x1800037fb  cmp     [rsi], rdi
0x1800037fe  jnz     short loc_1800037AA
0x180003800  mov     eax, 80004002h
0x180003805  mov     [r14], rdi
0x180003808  mov     edi, eax
0x18000380a  jmp     short loc_180003817
0x18000380c  mov     rbx, [rsi-8]
0x180003810  jmp     short loc_180003793
0x180003812  mov     edi, 80070057h
0x180003817  mov     rbx, [rsp+38h+arg_0]
0x18000381c  mov     eax, edi
0x18000381e  mov     rbp, [rsp+38h+arg_8]
0x180003823  mov     rsi, [rsp+38h+arg_10]
0x180003828  add     rsp, 20h
0x18000382c  pop     r15
0x18000382e  pop     r14
0x180003830  pop     rdi
0x180003831  retn
```

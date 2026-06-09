# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18000323c`
- end: `0x180003350`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ab0`
- `0x180001e40`
- `0x180001fd0`
- `0x180009ea0`
- `0x18000bd50`
- `0x18000c700`
- `0x18000c790`

## callees

- `0x18000323c`
- `0x18000e4a0`

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
0x18000323c  mov     [rsp+arg_0], rbx
0x180003241  mov     [rsp+arg_8], rbp
0x180003246  mov     [rsp+arg_10], rsi
0x18000324b  push    rdi
0x18000324c  push    r14
0x18000324e  push    r15
0x180003250  sub     rsp, 30h
0x180003254  xor     edi, edi
0x180003256  mov     r14, r9
0x180003259  mov     rbx, r8
0x18000325c  mov     r15, rcx
0x18000325f  test    rcx, rcx
0x180003262  jz      loc_180003330
0x180003268  test    rdx, rdx
0x18000326b  jz      loc_180003330
0x180003271  test    r9, r9
0x180003274  jnz     short loc_180003280
0x180003276  mov     edi, 80004003h
0x18000327b  jmp     loc_180003335
0x180003280  cmp     [r8], edi
0x180003283  jnz     short loc_1800032BB
0x180003285  cmp     [r8+4], edi
0x180003289  jnz     short loc_1800032BB
0x18000328b  cmp     dword ptr [r8+8], 0C0h
0x180003293  jnz     short loc_1800032BB
0x180003295  cmp     dword ptr [r8+0Ch], 46000000h
0x18000329d  jnz     short loc_1800032BB
0x18000329f  mov     rbx, [rdx+8]
0x1800032a3  add     rbx, r15
0x1800032a6  mov     rcx, rbx
0x1800032a9  mov     rax, [rbx]
0x1800032ac  mov     rax, [rax+8]
0x1800032b0  call    cs:__guard_dispatch_icall_fptr
0x1800032b6  mov     [r14], rbx
0x1800032b9  jmp     short loc_180003335
0x1800032bb  lea     rsi, [rdx+10h]
0x1800032bf  jmp     short loc_180003316
0x1800032c1  mov     rbp, [rsi-10h]
0x1800032c5  test    rbp, rbp
0x1800032c8  jz      short loc_1800032E9
0x1800032ca  mov     eax, [rbx]
0x1800032cc  cmp     [rbp+0], eax
0x1800032cf  jnz     short loc_180003312
0x1800032d1  mov     eax, [rbx+4]
0x1800032d4  cmp     [rbp+4], eax
0x1800032d7  jnz     short loc_180003312
0x1800032d9  mov     eax, [rbx+8]
0x1800032dc  cmp     [rbp+8], eax
0x1800032df  jnz     short loc_180003312
0x1800032e1  mov     eax, [rbx+0Ch]
0x1800032e4  cmp     [rbp+0Ch], eax
0x1800032e7  jnz     short loc_180003312
0x1800032e9  cmp     qword ptr [rsi], 1
0x1800032ed  jz      short loc_180003327
0x1800032ef  mov     r9, [rsi-8]
0x1800032f3  mov     r8, r14
0x1800032f6  mov     rax, [rsi]
0x1800032f9  mov     rdx, rbx
0x1800032fc  mov     rcx, r15
0x1800032ff  call    cs:__guard_dispatch_icall_fptr
0x180003305  test    eax, eax
0x180003307  jz      short loc_180003335
0x180003309  test    rbp, rbp
0x18000330c  jz      short loc_180003312
0x18000330e  test    eax, eax
0x180003310  js      short loc_180003320
0x180003312  add     rsi, 18h
0x180003316  cmp     [rsi], rdi
0x180003319  jnz     short loc_1800032C1
0x18000331b  mov     eax, 80004002h
0x180003320  mov     [r14], rdi
0x180003323  mov     edi, eax
0x180003325  jmp     short loc_180003335
0x180003327  mov     rbx, [rsi-8]
0x18000332b  jmp     loc_1800032A3
0x180003330  mov     edi, 80070057h
0x180003335  mov     rbx, [rsp+48h+arg_0]
0x18000333a  mov     eax, edi
0x18000333c  mov     rbp, [rsp+48h+arg_8]
0x180003341  mov     rsi, [rsp+48h+arg_10]
0x180003346  add     rsp, 30h
0x18000334a  pop     r15
0x18000334c  pop     r14
0x18000334e  pop     rdi
0x18000334f  retn
```

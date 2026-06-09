# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x1800119e8`
- end: `0x180011aec`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011b40`
- `0x180011bd0`
- `0x180011bf0`

## callees

- `0x1800119e8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectRootBase::InternalQueryInterface(
        char *a1,
        const struct ATL::_ATL_INTMAP_ENTRY *a2,
        const struct _GUID *a3,
        char **a4)
{
  const struct ATL::_ATL_INTMAP_ENTRY *v6; // rbx
  __int64 result; // rax
  __int64 v9; // rbx
  char *v10; // rbx
  _DWORD *v11; // rcx
  int v12; // ebp
  __int64 (__fastcall *v13)(char *, const struct _GUID *, char **, _QWORD); // rax

  v6 = a2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( !*(_QWORD *)&a3->Data1 && *(_DWORD *)a3->Data4 == 192 && *(_DWORD *)&a3->Data4[4] == 1174405120 )
  {
    v9 = *((_QWORD *)a2 + 1);
    goto LABEL_9;
  }
  if ( !*((_QWORD *)a2 + 2) )
    return 2147500034LL;
  while ( 1 )
  {
    v11 = *(_DWORD **)v6;
    if ( *(_QWORD *)v6 )
    {
      if ( *v11 != a3->Data1
        || v11[1] != *(_DWORD *)&a3->Data2
        || v11[2] != *(_DWORD *)a3->Data4
        || v11[3] != *(_DWORD *)&a3->Data4[4] )
      {
        goto LABEL_22;
      }
      v12 = 0;
    }
    else
    {
      v12 = 1;
    }
    v13 = (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))*((_QWORD *)v6 + 2);
    if ( v13 == (__int64 (__fastcall *)(char *, const struct _GUID *, char **, _QWORD))1 )
      break;
    result = v13(a1, a3, a4, *((_QWORD *)v6 + 1));
    if ( !(_DWORD)result || !v12 && (int)result < 0 )
      return result;
LABEL_22:
    v6 = (const struct ATL::_ATL_INTMAP_ENTRY *)((char *)v6 + 24);
    if ( !*((_QWORD *)v6 + 2) )
      return 2147500034LL;
  }
  v9 = *((_QWORD *)v6 + 1);
LABEL_9:
  v10 = &a1[v9];
  (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))(v10);
  result = 0;
  *a4 = v10;
  return result;
}

```

## disassembly

```asm
0x1800119e8  push    rbx
0x1800119ea  push    rbp
0x1800119eb  push    rsi
0x1800119ec  push    rdi
0x1800119ed  push    r14
0x1800119ef  sub     rsp, 30h
0x1800119f3  mov     rsi, r9
0x1800119f6  mov     rdi, r8
0x1800119f9  mov     rbx, rdx
0x1800119fc  mov     r14, rcx
0x1800119ff  test    rcx, rcx
0x180011a02  jz      loc_180011ADC
0x180011a08  test    rdx, rdx
0x180011a0b  jz      loc_180011ADC
0x180011a11  test    r9, r9
0x180011a14  jnz     short loc_180011A20
0x180011a16  mov     eax, 80004003h
0x180011a1b  jmp     loc_180011AE1
0x180011a20  mov     qword ptr [r9], 0
0x180011a27  cmp     dword ptr [r8], 0
0x180011a2b  jnz     short loc_180011A65
0x180011a2d  cmp     dword ptr [r8+4], 0
0x180011a32  jnz     short loc_180011A65
0x180011a34  cmp     dword ptr [r8+8], 0C0h
0x180011a3c  jnz     short loc_180011A65
0x180011a3e  cmp     dword ptr [r8+0Ch], 46000000h
0x180011a46  jnz     short loc_180011A65
0x180011a48  mov     rbx, [rdx+8]
0x180011a4c  add     rbx, r14
0x180011a4f  mov     rcx, rbx
0x180011a52  mov     rax, [rbx]
0x180011a55  mov     rax, [rax+8]
0x180011a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a5e  xor     eax, eax
0x180011a60  mov     [rsi], rbx
0x180011a63  jmp     short loc_180011AE1
0x180011a65  cmp     qword ptr [rdx+10h], 0
0x180011a6a  jz      short loc_180011ACC
0x180011a6c  mov     rcx, [rbx]
0x180011a6f  test    rcx, rcx
0x180011a72  jnz     short loc_180011A79
0x180011a74  lea     ebp, [rcx+1]
0x180011a77  jmp     short loc_180011A99
0x180011a79  mov     eax, [rdi]
0x180011a7b  cmp     [rcx], eax
0x180011a7d  jnz     short loc_180011AC1
0x180011a7f  mov     eax, [rdi+4]
0x180011a82  cmp     [rcx+4], eax
0x180011a85  jnz     short loc_180011AC1
0x180011a87  mov     eax, [rdi+8]
0x180011a8a  cmp     [rcx+8], eax
0x180011a8d  jnz     short loc_180011AC1
0x180011a8f  mov     eax, [rdi+0Ch]
0x180011a92  cmp     [rcx+0Ch], eax
0x180011a95  jnz     short loc_180011AC1
0x180011a97  xor     ebp, ebp
0x180011a99  mov     rax, [rbx+10h]
0x180011a9d  cmp     rax, 1
0x180011aa1  jz      short loc_180011AD3
0x180011aa3  mov     r9, [rbx+8]
0x180011aa7  mov     r8, rsi
0x180011aaa  mov     rdx, rdi
0x180011aad  mov     rcx, r14
0x180011ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ab5  test    eax, eax
0x180011ab7  jz      short loc_180011AE1
0x180011ab9  test    ebp, ebp
0x180011abb  jnz     short loc_180011AC1
0x180011abd  test    eax, eax
0x180011abf  js      short loc_180011AE1
0x180011ac1  add     rbx, 18h
0x180011ac5  cmp     qword ptr [rbx+10h], 0
0x180011aca  jnz     short loc_180011A6C
0x180011acc  mov     eax, 80004002h
0x180011ad1  jmp     short loc_180011AE1
0x180011ad3  mov     rbx, [rbx+8]
0x180011ad7  jmp     loc_180011A4C
0x180011adc  mov     eax, 80070057h
0x180011ae1  add     rsp, 30h
0x180011ae5  pop     r14
0x180011ae7  pop     rdi
0x180011ae8  pop     rsi
0x180011ae9  pop     rbp
0x180011aea  pop     rbx
0x180011aeb  retn
```

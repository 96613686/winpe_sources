# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180017c1c`
- end: `0x180017d20`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018d70`
- `0x180018d90`
- `0x180018db0`
- `0x180018dd0`
- `0x18001cdb0`
- `0x180026170`
- `0x180029010`
- `0x18002a230`
- `0x18002cc00`
- `0x18002ef60`
- `0x18002fd50`
- `0x1800300c0`
- `0x180031c60`

## callees

- `0x180017c1c`
- `0x180037010`

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
0x180017c1c  push    rbx
0x180017c1e  push    rbp
0x180017c1f  push    rsi
0x180017c20  push    rdi
0x180017c21  push    r14
0x180017c23  sub     rsp, 30h
0x180017c27  mov     rsi, r9
0x180017c2a  mov     rdi, r8
0x180017c2d  mov     rbx, rdx
0x180017c30  mov     r14, rcx
0x180017c33  test    rcx, rcx
0x180017c36  jz      loc_180017D10
0x180017c3c  test    rdx, rdx
0x180017c3f  jz      loc_180017D10
0x180017c45  test    r9, r9
0x180017c48  jnz     short loc_180017C54
0x180017c4a  mov     eax, 80004003h
0x180017c4f  jmp     loc_180017D15
0x180017c54  mov     qword ptr [r9], 0
0x180017c5b  cmp     dword ptr [r8], 0
0x180017c5f  jnz     short loc_180017C99
0x180017c61  cmp     dword ptr [r8+4], 0
0x180017c66  jnz     short loc_180017C99
0x180017c68  cmp     dword ptr [r8+8], 0C0h
0x180017c70  jnz     short loc_180017C99
0x180017c72  cmp     dword ptr [r8+0Ch], 46000000h
0x180017c7a  jnz     short loc_180017C99
0x180017c7c  mov     rbx, [rdx+8]
0x180017c80  add     rbx, r14
0x180017c83  mov     rcx, rbx
0x180017c86  mov     rax, [rbx]
0x180017c89  mov     rax, [rax+8]
0x180017c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c92  xor     eax, eax
0x180017c94  mov     [rsi], rbx
0x180017c97  jmp     short loc_180017D15
0x180017c99  cmp     qword ptr [rdx+10h], 0
0x180017c9e  jz      short loc_180017D00
0x180017ca0  mov     rcx, [rbx]
0x180017ca3  test    rcx, rcx
0x180017ca6  jnz     short loc_180017CAD
0x180017ca8  lea     ebp, [rcx+1]
0x180017cab  jmp     short loc_180017CCD
0x180017cad  mov     eax, [rdi]
0x180017caf  cmp     [rcx], eax
0x180017cb1  jnz     short loc_180017CF5
0x180017cb3  mov     eax, [rdi+4]
0x180017cb6  cmp     [rcx+4], eax
0x180017cb9  jnz     short loc_180017CF5
0x180017cbb  mov     eax, [rdi+8]
0x180017cbe  cmp     [rcx+8], eax
0x180017cc1  jnz     short loc_180017CF5
0x180017cc3  mov     eax, [rdi+0Ch]
0x180017cc6  cmp     [rcx+0Ch], eax
0x180017cc9  jnz     short loc_180017CF5
0x180017ccb  xor     ebp, ebp
0x180017ccd  mov     rax, [rbx+10h]
0x180017cd1  cmp     rax, 1
0x180017cd5  jz      short loc_180017D07
0x180017cd7  mov     r9, [rbx+8]
0x180017cdb  mov     r8, rsi
0x180017cde  mov     rdx, rdi
0x180017ce1  mov     rcx, r14
0x180017ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ce9  test    eax, eax
0x180017ceb  jz      short loc_180017D15
0x180017ced  test    ebp, ebp
0x180017cef  jnz     short loc_180017CF5
0x180017cf1  test    eax, eax
0x180017cf3  js      short loc_180017D15
0x180017cf5  add     rbx, 18h
0x180017cf9  cmp     qword ptr [rbx+10h], 0
0x180017cfe  jnz     short loc_180017CA0
0x180017d00  mov     eax, 80004002h
0x180017d05  jmp     short loc_180017D15
0x180017d07  mov     rbx, [rbx+8]
0x180017d0b  jmp     loc_180017C80
0x180017d10  mov     eax, 80070057h
0x180017d15  add     rsp, 30h
0x180017d19  pop     r14
0x180017d1b  pop     rdi
0x180017d1c  pop     rsi
0x180017d1d  pop     rbp
0x180017d1e  pop     rbx
0x180017d1f  retn
```

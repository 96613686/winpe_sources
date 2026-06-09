# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x18001013c`
- end: `0x180010240`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(char *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, char **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011840`
- `0x180011930`
- `0x1800119a0`

## callees

- `0x18001013c`
- `0x180018010`

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
0x18001013c  push    rbx
0x18001013e  push    rbp
0x18001013f  push    rsi
0x180010140  push    rdi
0x180010141  push    r14
0x180010143  sub     rsp, 30h
0x180010147  mov     rsi, r9
0x18001014a  mov     rdi, r8
0x18001014d  mov     rbx, rdx
0x180010150  mov     r14, rcx
0x180010153  test    rcx, rcx
0x180010156  jz      loc_180010230
0x18001015c  test    rdx, rdx
0x18001015f  jz      loc_180010230
0x180010165  test    r9, r9
0x180010168  jnz     short loc_180010174
0x18001016a  mov     eax, 80004003h
0x18001016f  jmp     loc_180010235
0x180010174  mov     qword ptr [r9], 0
0x18001017b  cmp     dword ptr [r8], 0
0x18001017f  jnz     short loc_1800101B9
0x180010181  cmp     dword ptr [r8+4], 0
0x180010186  jnz     short loc_1800101B9
0x180010188  cmp     dword ptr [r8+8], 0C0h
0x180010190  jnz     short loc_1800101B9
0x180010192  cmp     dword ptr [r8+0Ch], 46000000h
0x18001019a  jnz     short loc_1800101B9
0x18001019c  mov     rbx, [rdx+8]
0x1800101a0  add     rbx, r14
0x1800101a3  mov     rcx, rbx
0x1800101a6  mov     rax, [rbx]
0x1800101a9  mov     rax, [rax+8]
0x1800101ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101b2  xor     eax, eax
0x1800101b4  mov     [rsi], rbx
0x1800101b7  jmp     short loc_180010235
0x1800101b9  cmp     qword ptr [rdx+10h], 0
0x1800101be  jz      short loc_180010220
0x1800101c0  mov     rcx, [rbx]
0x1800101c3  test    rcx, rcx
0x1800101c6  jnz     short loc_1800101CD
0x1800101c8  lea     ebp, [rcx+1]
0x1800101cb  jmp     short loc_1800101ED
0x1800101cd  mov     eax, [rdi]
0x1800101cf  cmp     [rcx], eax
0x1800101d1  jnz     short loc_180010215
0x1800101d3  mov     eax, [rdi+4]
0x1800101d6  cmp     [rcx+4], eax
0x1800101d9  jnz     short loc_180010215
0x1800101db  mov     eax, [rdi+8]
0x1800101de  cmp     [rcx+8], eax
0x1800101e1  jnz     short loc_180010215
0x1800101e3  mov     eax, [rdi+0Ch]
0x1800101e6  cmp     [rcx+0Ch], eax
0x1800101e9  jnz     short loc_180010215
0x1800101eb  xor     ebp, ebp
0x1800101ed  mov     rax, [rbx+10h]
0x1800101f1  cmp     rax, 1
0x1800101f5  jz      short loc_180010227
0x1800101f7  mov     r9, [rbx+8]
0x1800101fb  mov     r8, rsi
0x1800101fe  mov     rdx, rdi
0x180010201  mov     rcx, r14
0x180010204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010209  test    eax, eax
0x18001020b  jz      short loc_180010235
0x18001020d  test    ebp, ebp
0x18001020f  jnz     short loc_180010215
0x180010211  test    eax, eax
0x180010213  js      short loc_180010235
0x180010215  add     rbx, 18h
0x180010219  cmp     qword ptr [rbx+10h], 0
0x18001021e  jnz     short loc_1800101C0
0x180010220  mov     eax, 80004002h
0x180010225  jmp     short loc_180010235
0x180010227  mov     rbx, [rbx+8]
0x18001022b  jmp     loc_1800101A0
0x180010230  mov     eax, 80070057h
0x180010235  add     rsp, 30h
0x180010239  pop     r14
0x18001023b  pop     rdi
0x18001023c  pop     rsi
0x18001023d  pop     rbp
0x18001023e  pop     rbx
0x18001023f  retn
```

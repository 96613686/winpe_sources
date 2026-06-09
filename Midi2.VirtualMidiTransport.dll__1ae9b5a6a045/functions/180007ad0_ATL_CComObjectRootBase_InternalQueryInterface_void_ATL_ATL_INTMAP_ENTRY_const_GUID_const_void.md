# ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)

- ea: `0x180007ad0`
- end: `0x180007bd4`
- name: `?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: `__int64 __fastcall(void *, const struct ATL::_ATL_INTMAP_ENTRY *, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800084a0`
- `0x180008530`
- `0x180008550`

## callees

- `0x180007ad0`
- `0x180021010`

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
0x180007ad0  push    rbx
0x180007ad2  push    rbp
0x180007ad3  push    rsi
0x180007ad4  push    rdi
0x180007ad5  push    r14
0x180007ad7  sub     rsp, 30h
0x180007adb  mov     rsi, r9
0x180007ade  mov     rdi, r8
0x180007ae1  mov     rbx, rdx
0x180007ae4  mov     r14, rcx
0x180007ae7  test    rcx, rcx
0x180007aea  jz      loc_180007BC4
0x180007af0  test    rdx, rdx
0x180007af3  jz      loc_180007BC4
0x180007af9  test    r9, r9
0x180007afc  jnz     short loc_180007B08
0x180007afe  mov     eax, 80004003h
0x180007b03  jmp     loc_180007BC9
0x180007b08  mov     qword ptr [r9], 0
0x180007b0f  cmp     dword ptr [r8], 0
0x180007b13  jnz     short loc_180007B4D
0x180007b15  cmp     dword ptr [r8+4], 0
0x180007b1a  jnz     short loc_180007B4D
0x180007b1c  cmp     dword ptr [r8+8], 0C0h
0x180007b24  jnz     short loc_180007B4D
0x180007b26  cmp     dword ptr [r8+0Ch], 46000000h
0x180007b2e  jnz     short loc_180007B4D
0x180007b30  mov     rbx, [rdx+8]
0x180007b34  add     rbx, r14
0x180007b37  mov     rcx, rbx
0x180007b3a  mov     rax, [rbx]
0x180007b3d  mov     rax, [rax+8]
0x180007b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b46  xor     eax, eax
0x180007b48  mov     [rsi], rbx
0x180007b4b  jmp     short loc_180007BC9
0x180007b4d  cmp     qword ptr [rdx+10h], 0
0x180007b52  jz      short loc_180007BB4
0x180007b54  mov     rcx, [rbx]
0x180007b57  test    rcx, rcx
0x180007b5a  jnz     short loc_180007B61
0x180007b5c  lea     ebp, [rcx+1]
0x180007b5f  jmp     short loc_180007B81
0x180007b61  mov     eax, [rdi]
0x180007b63  cmp     [rcx], eax
0x180007b65  jnz     short loc_180007BA9
0x180007b67  mov     eax, [rdi+4]
0x180007b6a  cmp     [rcx+4], eax
0x180007b6d  jnz     short loc_180007BA9
0x180007b6f  mov     eax, [rdi+8]
0x180007b72  cmp     [rcx+8], eax
0x180007b75  jnz     short loc_180007BA9
0x180007b77  mov     eax, [rdi+0Ch]
0x180007b7a  cmp     [rcx+0Ch], eax
0x180007b7d  jnz     short loc_180007BA9
0x180007b7f  xor     ebp, ebp
0x180007b81  mov     rax, [rbx+10h]
0x180007b85  cmp     rax, 1
0x180007b89  jz      short loc_180007BBB
0x180007b8b  mov     r9, [rbx+8]
0x180007b8f  mov     r8, rsi
0x180007b92  mov     rdx, rdi
0x180007b95  mov     rcx, r14
0x180007b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b9d  test    eax, eax
0x180007b9f  jz      short loc_180007BC9
0x180007ba1  test    ebp, ebp
0x180007ba3  jnz     short loc_180007BA9
0x180007ba5  test    eax, eax
0x180007ba7  js      short loc_180007BC9
0x180007ba9  add     rbx, 18h
0x180007bad  cmp     qword ptr [rbx+10h], 0
0x180007bb2  jnz     short loc_180007B54
0x180007bb4  mov     eax, 80004002h
0x180007bb9  jmp     short loc_180007BC9
0x180007bbb  mov     rbx, [rbx+8]
0x180007bbf  jmp     loc_180007B34
0x180007bc4  mov     eax, 80070057h
0x180007bc9  add     rsp, 30h
0x180007bcd  pop     r14
0x180007bcf  pop     rdi
0x180007bd0  pop     rsi
0x180007bd1  pop     rbp
0x180007bd2  pop     rbx
0x180007bd3  retn
```

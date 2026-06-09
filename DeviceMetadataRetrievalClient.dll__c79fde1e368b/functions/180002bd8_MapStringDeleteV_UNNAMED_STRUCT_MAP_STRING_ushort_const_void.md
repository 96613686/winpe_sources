# MapStringDeleteV(UNNAMED_STRUCT_MAP_STRING *,ushort const *,void * *)

- ea: `0x180002bd8`
- end: `0x180002c50`
- name: `?MapStringDeleteV@@YAHPEAUUNNAMED_STRUCT_MAP_STRING@@PEBGPEAPEAX@Z`
- size: `120`
- prototype: `__int64 __fastcall(struct UNNAMED_STRUCT_MAP_STRING *, const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000768c`
- `0x18000b96c`

## callees

- `0x180002934`
- `0x180002998`
- `0x180002bd8`
- `0x180014010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180002c2b`
- `KERNEL32!SetLastError` at `0x180002c3d`
- `KERNEL32!SetLastError` at `0x180002c2b`
- `KERNEL32!SetLastError` at `0x180002c3d`

## pseudocode

```c
__int64 __fastcall MapStringDeleteV(struct UNNAMED_STRUCT_MAP_STRING *a1, const unsigned __int16 *a2, void **a3)
{
  __int64 v4; // rdi
  DWORD v5; // ecx
  void (__fastcall *v6)(_QWORD); // rax

  if ( !a1 || *(_DWORD *)a1 != -1507010302 )
  {
    v5 = 87;
    goto LABEL_9;
  }
  v4 = LocalMapStringFind(a1, a2, a3);
  if ( !v4 )
  {
    v5 = 2;
LABEL_9:
    SetLastError(v5);
    return 0;
  }
  v6 = (void (__fastcall *)(_QWORD))*((_QWORD *)a1 + 2);
  if ( v6 )
  {
    v6(*(_QWORD *)(v4 + 8));
    *(_QWORD *)(v4 + 8) = 0;
  }
  LocalMapStringRemoveNode(a1, v4);
  SetLastError(0);
  return 1;
}

```

## disassembly

```asm
0x180002bd8  mov     [rsp+arg_0], rbx
0x180002bdd  push    rdi
0x180002bde  sub     rsp, 20h
0x180002be2  mov     rbx, rcx
0x180002be5  test    rcx, rcx
0x180002be8  jz      short loc_180002C38
0x180002bea  cmp     dword ptr [rcx], 0A62CD902h
0x180002bf0  jnz     short loc_180002C38
0x180002bf2  call    LocalMapStringFind
0x180002bf7  mov     rdi, rax
0x180002bfa  test    rax, rax
0x180002bfd  jnz     short loc_180002C04
0x180002bff  lea     ecx, [rax+2]
0x180002c02  jmp     short loc_180002C3D
0x180002c04  mov     rax, [rbx+10h]
0x180002c08  test    rax, rax
0x180002c0b  jz      short loc_180002C1E
0x180002c0d  mov     rcx, [rdi+8]
0x180002c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c16  mov     qword ptr [rdi+8], 0
0x180002c1e  mov     rdx, rdi
0x180002c21  mov     rcx, rbx
0x180002c24  call    LocalMapStringRemoveNode
0x180002c29  xor     ecx, ecx; dwErrCode
0x180002c2b  call    cs:__imp_SetLastError
0x180002c31  mov     eax, 1
0x180002c36  jmp     short loc_180002C45
0x180002c38  mov     ecx, 57h ; 'W'; dwErrCode
0x180002c3d  call    cs:__imp_SetLastError
0x180002c43  xor     eax, eax
0x180002c45  mov     rbx, [rsp+28h+arg_0]
0x180002c4a  add     rsp, 20h
0x180002c4e  pop     rdi
0x180002c4f  retn
```

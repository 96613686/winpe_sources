# TsiFreeAppContainerSecurityInfo(_APPCONTAINER_SECURITY_INFO *)

- ea: `0x180002c04`
- end: `0x180002c72`
- name: `?TsiFreeAppContainerSecurityInfo@@YAJPEAU_APPCONTAINER_SECURITY_INFO@@@Z`
- size: `110`
- prototype: `__int64 __fastcall(struct _APPCONTAINER_SECURITY_INFO *)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180002f00`
- `0x180004db0`
- `0x180006410`
- `0x18000dc54`
- `0x180018dac`

## callees

- `0x180002c04`
- `0x180005400`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002c5a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002c5a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002c51`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002c51`

## pseudocode

```c
__int64 __fastcall TsiFreeAppContainerSecurityInfo(struct _APPCONTAINER_SECURITY_INFO *a1)
{
  void ***v3; // rdi
  unsigned int i; // esi

  if ( !a1 )
    return 2147500035LL;
  TsiFreeScheduleSid(*(void ***)a1);
  v3 = (void ***)*((_QWORD *)a1 + 1);
  if ( v3 )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 4); v3 += 2 )
    {
      TsiFreeScheduleSid(*v3);
      ++i;
    }
    operator delete[](*((void **)a1 + 1));
  }
  operator delete(a1);
  return 0;
}

```

## disassembly

```asm
0x180002c04  mov     [rsp+arg_0], rbx
0x180002c09  mov     [rsp+arg_8], rsi
0x180002c0e  push    rdi
0x180002c0f  sub     rsp, 20h
0x180002c13  mov     rbx, rcx
0x180002c16  test    rcx, rcx
0x180002c19  jnz     short loc_180002C22
0x180002c1b  mov     eax, 80004003h
0x180002c20  jmp     short loc_180002C62
0x180002c22  mov     rcx, [rcx]; struct _SCHEDULE_SID *
0x180002c25  call    ?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z; TsiFreeScheduleSid(_SCHEDULE_SID *)
0x180002c2a  mov     rdi, [rbx+8]
0x180002c2e  test    rdi, rdi
0x180002c31  jz      short loc_180002C57
0x180002c33  xor     esi, esi
0x180002c35  cmp     [rbx+10h], esi
0x180002c38  jbe     short loc_180002C4D
0x180002c3a  mov     rcx, [rdi]; struct _SCHEDULE_SID *
0x180002c3d  call    ?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z; TsiFreeScheduleSid(_SCHEDULE_SID *)
0x180002c42  inc     esi
0x180002c44  lea     rdi, [rdi+10h]
0x180002c48  cmp     esi, [rbx+10h]
0x180002c4b  jb      short loc_180002C3A
0x180002c4d  mov     rcx, [rbx+8]
0x180002c51  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002c57  mov     rcx, rbx
0x180002c5a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002c60  xor     eax, eax
0x180002c62  mov     rbx, [rsp+28h+arg_0]
0x180002c67  mov     rsi, [rsp+28h+arg_8]
0x180002c6c  add     rsp, 20h
0x180002c70  pop     rdi
0x180002c71  retn
```

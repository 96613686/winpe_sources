# _dynamic_atexit_destructor_for___AtlModule__

- ea: `0x18000ce90`
- end: `0x18000cf52`
- name: `_dynamic_atexit_destructor_for___AtlModule__`
- size: `194`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000ce90`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cf03`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cf03`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cf37`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000cf37`

## pseudocode

```c
void dynamic_atexit_destructor_for___AtlModule__()
{
  struct ATL::_ATL_OBJMAP_ENTRY30 *v0; // rbx
  __int64 *v1; // rcx
  _QWORD *v2; // rdi
  _QWORD *v3; // rbx

  v0 = off_1800156B0;
  v1 = (__int64 *)off_1800156B8;
  if ( off_1800156B0 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)off_1800156B8 )
  {
    do
    {
      if ( *(_QWORD *)v0 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v0 + 64LL))(0);
        v1 = (__int64 *)off_1800156B8;
      }
      v0 = (struct ATL::_ATL_OBJMAP_ENTRY30 *)((char *)v0 + 8);
    }
    while ( v0 < (struct ATL::_ATL_OBJMAP_ENTRY30 *)v1 );
  }
  if ( dword_1800160C8 )
  {
    v2 = (_QWORD *)qword_1800160D0;
    if ( qword_1800160D0 )
    {
      do
      {
        ((void (__fastcall *)(_QWORD))*v2)(v2[1]);
        v3 = (_QWORD *)v2[2];
        operator delete(v2);
        v2 = v3;
      }
      while ( v3 );
      qword_1800160D0 = 0;
    }
    if ( qword_180016100 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180016100 + 16LL))(qword_180016100);
    DeleteCriticalSection(&stru_1800160D8);
    dword_1800160C8 = 0;
  }
}

```

## disassembly

```asm
0x18000ce90  mov     [rsp+arg_0], rbx
0x18000ce95  push    rdi
0x18000ce96  sub     rsp, 20h
0x18000ce9a  mov     rbx, cs:off_1800156B0
0x18000cea1  mov     rcx, cs:off_1800156B8
0x18000cea8  cmp     rbx, rcx
0x18000ceab  jnb     short loc_18000CED3
0x18000cead  nop     dword ptr [rax]
0x18000ceb0  mov     rax, [rbx]
0x18000ceb3  test    rax, rax
0x18000ceb6  jz      short loc_18000CECA
0x18000ceb8  xor     ecx, ecx
0x18000ceba  mov     rax, [rax+40h]
0x18000cebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cec3  mov     rcx, cs:off_1800156B8
0x18000ceca  add     rbx, 8
0x18000cece  cmp     rbx, rcx
0x18000ced1  jb      short loc_18000CEB0
0x18000ced3  cmp     cs:dword_1800160C8, 0
0x18000ceda  jz      short loc_18000CF47
0x18000cedc  mov     rdi, cs:qword_1800160D0
0x18000cee3  test    rdi, rdi
0x18000cee6  jz      short loc_18000CF18
0x18000cee8  nop     dword ptr [rax+rax+00000000h]
0x18000cef0  mov     rcx, [rdi+8]
0x18000cef4  mov     rax, [rdi]
0x18000cef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cefc  mov     rbx, [rdi+10h]
0x18000cf00  mov     rcx, rdi
0x18000cf03  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cf09  mov     rdi, rbx
0x18000cf0c  test    rbx, rbx
0x18000cf0f  jnz     short loc_18000CEF0
0x18000cf11  mov     cs:qword_1800160D0, rbx
0x18000cf18  mov     rcx, cs:qword_180016100
0x18000cf1f  test    rcx, rcx
0x18000cf22  jz      short loc_18000CF30
0x18000cf24  mov     rax, [rcx]
0x18000cf27  mov     rax, [rax+10h]
0x18000cf2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf30  lea     rcx, stru_1800160D8; lpCriticalSection
0x18000cf37  call    cs:__imp_DeleteCriticalSection
0x18000cf3d  mov     cs:dword_1800160C8, 0
0x18000cf47  mov     rbx, [rsp+28h+arg_0]
0x18000cf4c  add     rsp, 20h
0x18000cf50  pop     rdi
0x18000cf51  retn
```

# ATL::CComObject<CConnectedUser>::`vector deleting destructor'(uint)

- ea: `0x18000db60`
- end: `0x18000dbf1`
- name: `??_E?$CComObject@VCConnectedUser@@@ATL@@UEAAPEAXI@Z`
- size: `145`
- prototype: `char *__fastcall(char *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000db60`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000dbdd`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dbdd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dbcd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000dbcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbb9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dbb9`

## pseudocode

```c
char *__fastcall ATL::CComObject<CConnectedUser>::`vector deleting destructor'(char *a1, char a2)
{
  __int64 v4; // rcx
  void *v5; // rcx

  *(_QWORD *)a1 = &ATL::CComObject<CConnectedUser>::`vftable';
  *((_DWORD *)a1 + 2) = -1073741823;
  v4 = *((_QWORD *)a1 + 11);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)a1 + 11) = 0;
  }
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v5 = (void *)*((_QWORD *)a1 + 12);
  if ( v5 )
    LocalFree(v5);
  if ( a1[56] )
  {
    a1[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000db60  mov     [rsp+arg_0], rbx
0x18000db65  push    rdi
0x18000db66  sub     rsp, 20h
0x18000db6a  mov     edi, edx
0x18000db6c  mov     rbx, rcx
0x18000db6f  lea     rax, ??_7?$CComObject@VCConnectedUser@@@ATL@@6B@; const ATL::CComObject<CConnectedUser>::`vftable'
0x18000db76  mov     [rcx], rax
0x18000db79  mov     dword ptr [rcx+8], 0C0000001h
0x18000db80  mov     rcx, [rcx+58h]
0x18000db84  test    rcx, rcx
0x18000db87  jz      short loc_18000DB9D
0x18000db89  mov     rax, [rcx]
0x18000db8c  mov     rax, [rax+10h]
0x18000db90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db95  mov     qword ptr [rbx+58h], 0
0x18000db9d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000dba4  mov     rax, [rcx]
0x18000dba7  mov     rax, [rax+10h]
0x18000dbab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbb0  mov     rcx, [rbx+60h]; hMem
0x18000dbb4  test    rcx, rcx
0x18000dbb7  jz      short loc_18000DBBF
0x18000dbb9  call    cs:__imp_LocalFree
0x18000dbbf  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000dbc3  cmp     byte ptr [rcx+28h], 0
0x18000dbc7  jz      short loc_18000DBD4
0x18000dbc9  mov     byte ptr [rcx+28h], 0
0x18000dbcd  call    cs:__imp_DeleteCriticalSection
0x18000dbd3  nop
0x18000dbd4  test    dil, 1
0x18000dbd8  jz      short loc_18000DBE3
0x18000dbda  mov     rcx, rbx
0x18000dbdd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dbe3  mov     rax, rbx
0x18000dbe6  mov     rbx, [rsp+28h+arg_0]
0x18000dbeb  add     rsp, 20h
0x18000dbef  pop     rdi
0x18000dbf0  retn
```

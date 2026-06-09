# ATL::CComObject<CPolicyComponent>::`vector deleting destructor'(uint)

- ea: `0x18000d500`
- end: `0x18000d56f`
- name: `??_E?$CComObject@VCPolicyComponent@@@ATL@@UEAAPEAXI@Z`
- size: `111`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000d500`
- `0x18001662c`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d541`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d541`

## pseudocode

```c
char *__fastcall ATL::CComObject<CPolicyComponent>::`vector deleting destructor'(char *hMem, char a2)
{
  *((_DWORD *)hMem + 2) = -1073741823;
  *(_QWORD *)hMem = &ATL::CComObject<CPolicyComponent>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( hMem[56] )
  {
    hMem[56] = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)(hMem + 16));
  }
  if ( (a2 & 1) != 0 )
    operator delete(hMem);
  return hMem;
}

```

## disassembly

```asm
0x18000d500  mov     [rsp+arg_0], rbx
0x18000d505  push    rdi
0x18000d506  sub     rsp, 20h
0x18000d50a  mov     dword ptr [rcx+8], 0C0000001h
0x18000d511  lea     rax, ??_7?$CComObject@VCPolicyComponent@@@ATL@@6B@; const ATL::CComObject<CPolicyComponent>::`vftable'
0x18000d518  mov     [rcx], rax
0x18000d51b  mov     rbx, rcx
0x18000d51e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d525  mov     edi, edx
0x18000d527  mov     rax, [rcx]
0x18000d52a  mov     rax, [rax+10h]
0x18000d52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d533  cmp     byte ptr [rbx+38h], 0
0x18000d537  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000d53b  jz      short loc_18000D54D
0x18000d53d  mov     byte ptr [rcx+28h], 0
0x18000d541  call    cs:__imp_DeleteCriticalSection
0x18000d548  nop     dword ptr [rax+rax+00h]
0x18000d54d  test    dil, 1
0x18000d551  jz      short loc_18000D560
0x18000d553  mov     edx, 48h ; 'H'
0x18000d558  mov     rcx, rbx; hMem
0x18000d55b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d560  mov     rax, rbx
0x18000d563  mov     rbx, [rsp+28h+arg_0]
0x18000d568  add     rsp, 20h
0x18000d56c  pop     rdi
0x18000d56d  retn
```

# ATL::CComContainedObject<CMsMpComFactoryHome>::`vector deleting destructor'(uint)

- ea: `0x180002dc0`
- end: `0x180002e17`
- name: `??_E?$CComContainedObject@VCMsMpComFactoryHome@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180002dc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002e03`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002e03`
- `KERNEL32!DeleteCriticalSection` at `0x180002df4`
- `KERNEL32!DeleteCriticalSection` at `0x180002df4`
- `mpclient!MpConfigUninitialize` at `0x180002dd6`
- `mpclient!MpConfigUninitialize` at `0x180002dd6`

## pseudocode

```c
char *__fastcall ATL::CComContainedObject<CMsMpComFactoryHome>::`vector deleting destructor'(char *a1, char a2)
{
  if ( *((_QWORD *)a1 + 9) )
    MpConfigUninitialize();
  *(_QWORD *)a1 = &MP_CComObjectRootEx::`vftable';
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
0x180002dc0  mov     [rsp+arg_0], rbx
0x180002dc5  push    rdi
0x180002dc6  sub     rsp, 20h
0x180002dca  cmp     qword ptr [rcx+48h], 0
0x180002dcf  mov     edi, edx
0x180002dd1  mov     rbx, rcx
0x180002dd4  jz      short loc_180002DDC
0x180002dd6  call    cs:__imp_MpConfigUninitialize
0x180002ddc  lea     rax, ??_7MP_CComObjectRootEx@@6B@; const MP_CComObjectRootEx::`vftable'
0x180002de3  lea     rcx, [rbx+10h]; lpCriticalSection
0x180002de7  mov     [rbx], rax
0x180002dea  cmp     byte ptr [rcx+28h], 0
0x180002dee  jz      short loc_180002DFA
0x180002df0  mov     byte ptr [rcx+28h], 0
0x180002df4  call    cs:__imp_DeleteCriticalSection
0x180002dfa  test    dil, 1
0x180002dfe  jz      short loc_180002E09
0x180002e00  mov     rcx, rbx
0x180002e03  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002e09  mov     rax, rbx
0x180002e0c  mov     rbx, [rsp+28h+arg_0]
0x180002e11  add     rsp, 20h
0x180002e15  pop     rdi
0x180002e16  retn
```

# SmartPtr<IBackgroundCopyFile2>::`scalar deleting destructor'(uint)

- ea: `0x18001b010`
- end: `0x18001b055`
- name: `??_G?$SmartPtr@UIBackgroundCopyFile2@@@@UEAAPEAXI@Z`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001afb4`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001b03a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001b03a`

## pseudocode

```c
__int64 *__fastcall SmartPtr<IBackgroundCopyFile2>::`scalar deleting destructor'(__int64 *a1, char a2)
{
  *a1 = (__int64)&SmartPtr<IBITSDownloadMonitor>::`vftable';
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(a1 + 1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18001b010  mov     [rsp+arg_0], rbx
0x18001b015  push    rdi
0x18001b016  sub     rsp, 20h
0x18001b01a  lea     rax, ??_7?$SmartPtr@UIBITSDownloadMonitor@@@@6B@; const SmartPtr<IBITSDownloadMonitor>::`vftable'
0x18001b021  mov     rdi, rcx
0x18001b024  mov     [rcx], rax
0x18001b027  mov     ebx, edx
0x18001b029  add     rcx, 8
0x18001b02d  call    ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
0x18001b032  test    bl, 1
0x18001b035  jz      short loc_18001B046
0x18001b037  mov     rcx, rdi
0x18001b03a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001b041  nop     dword ptr [rax+rax+00h]
0x18001b046  mov     rbx, [rsp+28h+arg_0]
0x18001b04b  mov     rax, rdi
0x18001b04e  add     rsp, 20h
0x18001b052  pop     rdi
0x18001b053  retn
```

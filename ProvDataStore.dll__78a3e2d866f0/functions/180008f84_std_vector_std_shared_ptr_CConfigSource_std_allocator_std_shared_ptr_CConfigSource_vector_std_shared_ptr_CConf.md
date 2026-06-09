# std::vector<std::shared_ptr<CConfigSource>,std::allocator<std::shared_ptr<CConfigSource>>>::~vector<std::shared_ptr<CConfigSource>,std::allocator<std::shared_ptr<CConfigSource>>>(void)

- ea: `0x180008f84`
- end: `0x180008fc4`
- name: `??1?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@QEAA@XZ`
- size: `64`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18001187f`
- `0x18001192d`
- `0x18001193f`
- `0x180011a7f`

## callees

- `0x180008f84`
- `0x18000a148`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008fa1`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008fa1`

## pseudocode

```c
void __fastcall std::vector<std::shared_ptr<CConfigSource>>::~vector<std::shared_ptr<CConfigSource>>(_QWORD *a1)
{
  if ( *a1 )
  {
    std::vector<std::shared_ptr<CConfigSet>>::_Destroy(a1, *a1, a1[1]);
    operator delete((void *)*a1);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x180008f84  push    rbx
0x180008f86  sub     rsp, 20h
0x180008f8a  mov     rdx, [rcx]
0x180008f8d  mov     rbx, rcx
0x180008f90  test    rdx, rdx
0x180008f93  jz      short loc_180008FBE
0x180008f95  mov     r8, [rcx+8]
0x180008f99  call    ?_Destroy@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@IEAAXPEAV?$shared_ptr@VCConfigSet@@@2@0@Z; std::vector<std::shared_ptr<CConfigSet>>::_Destroy(std::shared_ptr<CConfigSet> *,std::shared_ptr<CConfigSet> *)
0x180008f9e  mov     rcx, [rbx]
0x180008fa1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008fa7  mov     qword ptr [rbx], 0
0x180008fae  mov     qword ptr [rbx+8], 0
0x180008fb6  mov     qword ptr [rbx+10h], 0
0x180008fbe  add     rsp, 20h
0x180008fc2  pop     rbx
0x180008fc3  retn
```

# ___String::SetStringCopy_::_1_::catch$0

- ea: `0x1400158d4`
- end: `0x14001590e`
- name: `___String::SetStringCopy_::_1_::catch$0`
- size: `58`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400158d4`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400158ef`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400158ef`

## pseudocode

```c
__int64 __fastcall __String::SetStringCopy_::_1_::catch_0(__int64 a1, __int64 a2)
{
  void **v2; // rbx

  v2 = *(void ***)(a2 + 48);
  if ( *v2 )
  {
    CWin32DefaultArena::WbemMemFree(*v2);
    *v2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1400158d4  mov     [rsp+arg_8], rdx
0x1400158d9  push    rbx
0x1400158da  push    rbp
0x1400158db  sub     rsp, 28h
0x1400158df  mov     rbp, rdx
0x1400158e2  mov     rbx, [rbp+30h]
0x1400158e6  cmp     qword ptr [rbx], 0
0x1400158ea  jz      short loc_1400158FC
0x1400158ec  mov     rcx, [rbx]
0x1400158ef  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400158f5  mov     qword ptr [rbx], 0
0x1400158fc  mov     rax, 0
0x140015906  add     rsp, 28h
0x14001590a  pop     rbp
0x14001590b  pop     rbx
0x14001590c  retn
```

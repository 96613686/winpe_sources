# std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>>>(std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>> &,std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *> *)

- ea: `0x18000b7ac`
- end: `0x18000b802`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@1@@Z`
- size: `86`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000b7ac`
- `0x18000babc`
- `0x18000d988`

## callees

- `0x1800036e4`
- `0x180005f9c`
- `0x18000b7ac`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rdi
  _QWORD *v6; // rcx
  void *v7; // rbx

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = v3;
      v7 = v3;
      v3 = (_QWORD *)*v3;
      std::wstring::~wstring(v6 + 13);
      operator delete(v7);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x18000b7ac  push    rbx
0x18000b7ae  push    rbp
0x18000b7af  push    rsi
0x18000b7b0  push    rdi
0x18000b7b1  sub     rsp, 28h
0x18000b7b5  cmp     byte ptr [r8+19h], 0
0x18000b7ba  mov     rdi, r8
0x18000b7bd  mov     rsi, rdx
0x18000b7c0  mov     rbp, rcx
0x18000b7c3  jnz     short loc_18000B7F9
0x18000b7c5  mov     r8, [rdi+10h]
0x18000b7c9  mov     rdx, rsi
0x18000b7cc  mov     rcx, rbp
0x18000b7cf  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>>>(std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>> &,std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *> *)
0x18000b7d4  mov     rcx, rdi
0x18000b7d7  mov     rbx, rdi
0x18000b7da  mov     rdi, [rdi]
0x18000b7dd  add     rcx, 68h ; 'h'
0x18000b7e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000b7e6  mov     edx, 98h
0x18000b7eb  mov     rcx, rbx; Block
0x18000b7ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b7f3  cmp     byte ptr [rdi+19h], 0
0x18000b7f7  jz      short loc_18000B7C5
0x18000b7f9  add     rsp, 28h
0x18000b7fd  pop     rdi
0x18000b7fe  pop     rsi
0x18000b7ff  pop     rbp
0x18000b800  pop     rbx
0x18000b801  retn
```

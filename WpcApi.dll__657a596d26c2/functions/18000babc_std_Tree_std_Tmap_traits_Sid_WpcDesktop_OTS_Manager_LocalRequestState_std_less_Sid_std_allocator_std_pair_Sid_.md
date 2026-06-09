# std::_Tree<std::_Tmap_traits<Sid,WpcDesktop::OTS::Manager::LocalRequestState,std::less<Sid>,std::allocator<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>,0>>::~_Tree<std::_Tmap_traits<Sid,WpcDesktop::OTS::Manager::LocalRequestState,std::less<Sid>,std::allocator<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>,0>>(void)

- ea: `0x18000babc`
- end: `0x18000bb27`
- name: `??1?$_Tree@V?$_Tmap_traits@VSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@U?$less@VSid@@@std@@V?$allocator@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@7@$0A@@std@@@std@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18002aff0`

## callees

- `0x1800036e4`
- `0x180005f9c`
- `0x18000b7ac`
- `0x18000babc`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<Sid,WpcDesktop::OTS::Manager::LocalRequestState,std::less<Sid>,std::allocator<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>,0>>::~_Tree<std::_Tmap_traits<Sid,WpcDesktop::OTS::Manager::LocalRequestState,std::less<Sid>,std::allocator<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>,0>>(
        void **a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rcx
  void *v4; // rbx

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      v2[2]);
    v3 = v2;
    v4 = v2;
    v2 = (_QWORD *)*v2;
    std::wstring::~wstring(v3 + 13);
    operator delete(v4);
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x18000babc  mov     [rsp+arg_0], rbx
0x18000bac1  mov     [rsp+arg_8], rsi
0x18000bac6  push    rdi
0x18000bac7  sub     rsp, 20h
0x18000bacb  mov     rax, [rcx]
0x18000bace  mov     rsi, rcx
0x18000bad1  mov     rdi, [rax+8]
0x18000bad5  jmp     short loc_18000BB05
0x18000bad7  mov     r8, [rdi+10h]
0x18000badb  mov     rdx, rsi
0x18000bade  mov     rcx, rsi
0x18000bae1  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBVSid@@ULocalRequestState@Manager@OTS@WpcDesktop@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>>>(std::allocator<std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *>> &,std::_Tree_node<std::pair<Sid const,WpcDesktop::OTS::Manager::LocalRequestState>,void *> *)
0x18000bae6  mov     rcx, rdi
0x18000bae9  mov     rbx, rdi
0x18000baec  mov     rdi, [rdi]
0x18000baef  add     rcx, 68h ; 'h'
0x18000baf3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000baf8  mov     edx, 98h
0x18000bafd  mov     rcx, rbx; Block
0x18000bb00  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bb05  cmp     byte ptr [rdi+19h], 0
0x18000bb09  jz      short loc_18000BAD7
0x18000bb0b  mov     rcx, [rsi]; Block
0x18000bb0e  mov     edx, 98h
0x18000bb13  mov     rbx, [rsp+28h+arg_0]
0x18000bb18  mov     rsi, [rsp+28h+arg_8]
0x18000bb1d  add     rsp, 20h
0x18000bb21  pop     rdi
0x18000bb22  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

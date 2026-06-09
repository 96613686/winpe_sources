# RootCause::addRepair(Repair *)

- ea: `0x18000f7dc`
- end: `0x18000f848`
- name: `?addRepair@RootCause@@QEAAXPEAVRepair@@@Z`
- size: `108`
- prototype: `void __fastcall(RootCause *__hidden this, struct Repair *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180002974`

## callees

- `0x1800015b8`
- `0x18000a960`
- `0x18000f7dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RootCause::addRepair(RootCause *this, struct Repair *a2)
{
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rax
  int v6; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+28h] [rbp-20h] BYREF
  struct Repair *v8; // [rsp+58h] [rbp+10h] BYREF

  v8 = a2;
  v3 = *((_QWORD *)this + 3);
  try
  {
    v4 = std::_List_buy<Repair *>::_Buynode<Repair * const &>(this, *((_QWORD *)this + 3), *(_QWORD *)(v3 + 8), &v8);
    v5 = *((_QWORD *)this + 4);
    if ( v5 == 0xAAAAAAAAAAAAAA9LL )
      std::_Xlength_error("list<T> too long");
    *((_QWORD *)this + 4) = v5 + 1;
    *(_QWORD *)(v3 + 8) = v4;
    **(_QWORD **)(v4 + 8) = v4;
  }
  catch ( exception v7 )
  {
    v6 = 0;
    throw (TestException *)&v6;
  }
}

```

## disassembly

```asm
0x18000f7dc  mov     [rsp+arg_0], rbx
0x18000f7e1  mov     [rsp+arg_8], rdx
0x18000f7e6  push    rdi
0x18000f7e7  sub     rsp, 40h
0x18000f7eb  mov     rbx, rcx
0x18000f7ee  mov     rdi, [rcx+18h]
0x18000f7f2  lea     r9, [rsp+48h+arg_8]
0x18000f7f7  mov     r8, [rdi+8]
0x18000f7fb  mov     rdx, rdi
0x18000f7fe  call    ??$_Buynode@AEBQEAVRepair@@@?$_List_buy@PEAVRepair@@V?$allocator@PEAVRepair@@@std@@@std@@QEAAPEAU?$_List_node@PEAVRepair@@PEAX@1@PEAU21@0AEBQEAVRepair@@@Z; std::_List_buy<Repair *>::_Buynode<Repair * const &>(std::_List_node<Repair *,void *> *,std::_List_node<Repair *,void *> *,Repair * const &)
0x18000f803  mov     rdx, rax
0x18000f806  mov     rax, [rbx+20h]
0x18000f80a  mov     rcx, 0AAAAAAAAAAAAAA9h
0x18000f814  sub     rcx, rax
0x18000f817  cmp     rcx, 1
0x18000f81b  jb      short loc_18000F83A
0x18000f81d  inc     rax
0x18000f820  mov     [rbx+20h], rax
0x18000f824  mov     [rdi+8], rdx
0x18000f828  mov     rax, [rdx+8]
0x18000f82c  mov     [rax], rdx
0x18000f82f  mov     rbx, [rsp+48h+arg_0]
0x18000f834  add     rsp, 40h
0x18000f838  pop     rdi
0x18000f839  retn
0x18000f83a  lea     rcx, aListTTooLong; "list<T> too long"
0x18000f841  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```

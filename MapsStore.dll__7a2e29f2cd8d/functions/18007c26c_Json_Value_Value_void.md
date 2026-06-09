# Json::Value::~Value(void)

- ea: `0x18007c26c`
- end: `0x18007c2f7`
- name: `??1Value@Json@@QEAA@XZ`
- size: `139`
- prototype: `void __fastcall(Json::Value *__hidden this)`
- caller_count: `35`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003c3e4`
- `0x18003c54c`
- `0x18003ca14`
- `0x18003cb9c`
- `0x18003dd5c`
- `0x18003ee8c`
- `0x18003ef20`
- `0x1800723a4`
- `0x18007c1e4`
- `0x18007c300`
- `0x18007e1bc`
- `0x18007ec2c`
- `0x18007ee0c`
- `0x18007fe64`
- `0x1800802e4`
- `0x1800809e0`
- `0x180081930`
- `0x18008fdce`
- `0x18008fde0`
- `0x18008fdf2`
- `0x18008fe04`
- `0x18008fe16`
- `0x18008fe28`
- `0x18008fe9f`
- `0x18008feb1`
- `0x18008fec3`
- `0x180090087`
- `0x180090099`
- `0x180093768`
- `0x18009377a`
- `0x180095bce`
- `0x1800961b7`
- `0x18009626d`
- `0x180096291`
- `0x1800962b5`

## callees

- `0x18000d460`
- `0x18000d4e0`
- `0x18000d4ec`
- `0x18007b978`
- `0x18007c26c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007c2b5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007c2b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Json::Value::~Value(void **this)
{
  void *v2; // rbx
  char *v3; // rcx
  char *v4; // rbx

  if ( *((_BYTE *)this + 8) == 4 )
  {
    if ( ((_DWORD)this[1] & 0x100) != 0 )
      free(*this);
  }
  else if ( (unsigned int)(*((char *)this + 8) - 6) <= 1 )
  {
    v2 = *this;
    if ( *this )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<Json::Value::CZString const,Json::Value>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<Json::Value::CZString const,Json::Value>,void *>>>(
        (void **)*this,
        (__int64)*this);
      operator delete(v2);
    }
  }
  v3 = (char *)this[2];
  if ( v3 )
  {
    v4 = v3 - 8;
    `eh vector destructor iterator'(
      v3,
      8u,
      *((_QWORD *)v3 - 1),
      (void (*)(void *))Json::Value::CommentInfo::~CommentInfo);
    operator delete(v4);
  }
  *this = 0;
}

```

## disassembly

```asm
0x18007c26c  mov     [rsp+arg_0], rbx
0x18007c271  push    rdi
0x18007c272  sub     rsp, 20h
0x18007c276  mov     rdi, rcx
0x18007c279  movsx   edx, byte ptr [rcx+8]
0x18007c27d  sub     edx, 4
0x18007c280  jz      short loc_18007C2A9
0x18007c282  sub     edx, 2
0x18007c285  jz      short loc_18007C28C
0x18007c287  cmp     edx, 1
0x18007c28a  jnz     short loc_18007C2BB
0x18007c28c  mov     rbx, [rcx]
0x18007c28f  test    rbx, rbx
0x18007c292  jz      short loc_18007C2BB
0x18007c294  mov     rdx, rbx
0x18007c297  mov     rcx, rbx
0x18007c29a  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Json::Value::CZString const,Json::Value>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<Json::Value::CZString const,Json::Value>,void *>>>(std::allocator<std::_Tree_node<std::pair<Json::Value::CZString const,Json::Value>,void *>> &)
0x18007c29f  mov     rcx, rbx; Block
0x18007c2a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007c2a7  jmp     short loc_18007C2BB
0x18007c2a9  test    dword ptr [rcx+8], 100h
0x18007c2b0  jz      short loc_18007C2BB
0x18007c2b2  mov     rcx, [rcx]; Block
0x18007c2b5  call    cs:__imp_free
0x18007c2bb  mov     rcx, [rdi+10h]; void *
0x18007c2bf  test    rcx, rcx
0x18007c2c2  jz      short loc_18007C2E5
0x18007c2c4  lea     rbx, [rcx-8]
0x18007c2c8  lea     r9, ??1CommentInfo@Value@Json@@QEAA@XZ; void (*)(void *)
0x18007c2cf  mov     r8, [rbx]; unsigned __int64
0x18007c2d2  mov     edx, 8; unsigned __int64
0x18007c2d7  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18007c2dc  mov     rcx, rbx; Block
0x18007c2df  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007c2e4  nop
0x18007c2e5  mov     qword ptr [rdi], 0
0x18007c2ec  mov     rbx, [rsp+28h+arg_0]
0x18007c2f1  add     rsp, 20h
0x18007c2f5  pop     rdi
0x18007c2f6  retn
```

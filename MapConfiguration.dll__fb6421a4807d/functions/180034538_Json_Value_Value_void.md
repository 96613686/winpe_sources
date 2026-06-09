# Json::Value::~Value(void)

- ea: `0x180034538`
- end: `0x1800345c3`
- name: `??1Value@Json@@QEAA@XZ`
- size: `139`
- prototype: `void __fastcall(Json::Value *__hidden this)`
- caller_count: `45`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001f4c4`
- `0x18001f774`
- `0x18002149c`
- `0x1800217dc`
- `0x1800219fc`
- `0x180021ccc`
- `0x180021e14`
- `0x1800222e4`
- `0x1800225d8`
- `0x180022764`
- `0x18002470c`
- `0x180025660`
- `0x1800256b8`
- `0x180034470`
- `0x180034630`
- `0x1800367e8`
- `0x1800372cc`
- `0x1800374ac`
- `0x180038504`
- `0x180038984`
- `0x180039080`
- `0x18003d0d9`
- `0x18003d19a`
- `0x18003d1ac`
- `0x18003d48c`
- `0x18003d4d4`
- `0x18003d4e6`
- `0x18003d50a`
- `0x18003d540`
- `0x18003d552`
- `0x18003d588`
- `0x18003d59a`
- `0x18003d5ac`
- `0x18003d5be`
- `0x18003d5d0`
- `0x18003d67d`
- `0x18003d6a1`
- `0x18003d6b3`
- `0x18003d6c5`
- `0x18003f92e`
- `0x18003f940`
- `0x180041005`
- `0x180041aa6`
- `0x180041b80`
- `0x180041ba4`

## callees

- `0x1800094c4`
- `0x1800094d0`
- `0x1800095a0`
- `0x180033b28`
- `0x180034538`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034581`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180034581`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Json::Value::~Value(void **this)
{
  void *v2; // rbx
  char *v3; // rcx
  char *v4; // rbx
  unsigned __int64 v5; // rdx

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
    operator delete(v4, v5);
  }
  *this = 0;
}

```

## disassembly

```asm
0x180034538  mov     [rsp+arg_0], rbx
0x18003453d  push    rdi
0x18003453e  sub     rsp, 20h
0x180034542  mov     rdi, rcx
0x180034545  movsx   edx, byte ptr [rcx+8]
0x180034549  sub     edx, 4
0x18003454c  jz      short loc_180034575
0x18003454e  sub     edx, 2
0x180034551  jz      short loc_180034558
0x180034553  cmp     edx, 1
0x180034556  jnz     short loc_180034587
0x180034558  mov     rbx, [rcx]
0x18003455b  test    rbx, rbx
0x18003455e  jz      short loc_180034587
0x180034560  mov     rdx, rbx
0x180034563  mov     rcx, rbx
0x180034566  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVCZString@Value@Json@@V23@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Json::Value::CZString const,Json::Value>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<Json::Value::CZString const,Json::Value>,void *>>>(std::allocator<std::_Tree_node<std::pair<Json::Value::CZString const,Json::Value>,void *>> &)
0x18003456b  mov     rcx, rbx; Block
0x18003456e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180034573  jmp     short loc_180034587
0x180034575  test    dword ptr [rcx+8], 100h
0x18003457c  jz      short loc_180034587
0x18003457e  mov     rcx, [rcx]; Block
0x180034581  call    cs:__imp_free
0x180034587  mov     rcx, [rdi+10h]; void *
0x18003458b  test    rcx, rcx
0x18003458e  jz      short loc_1800345B1
0x180034590  lea     rbx, [rcx-8]
0x180034594  lea     r9, ??1CommentInfo@Value@Json@@QEAA@XZ; void (*)(void *)
0x18003459b  mov     r8, [rbx]; unsigned __int64
0x18003459e  mov     edx, 8; unsigned __int64
0x1800345a3  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800345a8  mov     rcx, rbx; void *
0x1800345ab  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800345b0  nop
0x1800345b1  mov     qword ptr [rdi], 0
0x1800345b8  mov     rbx, [rsp+28h+arg_0]
0x1800345bd  add     rsp, 20h
0x1800345c1  pop     rdi
0x1800345c2  retn
```

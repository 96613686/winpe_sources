# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>(void)

- ea: `0x18001ee54`
- end: `0x18001eef3`
- name: `??1?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `159`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001f1b4`
- `0x180036282`

## callees

- `0x180001bc8`
- `0x18000a600`
- `0x18001ee54`
- `0x18001ef84`

## pseudocode

```c
void __fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
        void **a1)
{
  void **v1; // rdx
  char *v3; // r14
  char *v4; // rdi
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rdx

  v1 = (void **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = (char *)*v1;
  if ( *v1 )
  {
    do
    {
      v4 = *(char **)v3;
      std::vector<char>::~vector<char>(v3 + 112);
      operator delete(*((void **)v3 + 13), v5);
      *((_QWORD *)v3 + 13) = 0;
      operator delete(*((void **)v3 + 12), v6);
      *((_QWORD *)v3 + 12) = 0;
      operator delete(*((void **)v3 + 11), v7);
      *((_QWORD *)v3 + 11) = 0;
      std::wstring::~wstring((char **)v3 + 6);
      std::wstring::~wstring((char **)v3 + 2);
      operator delete(v3, 0xA0u);
      v3 = v4;
    }
    while ( v4 );
  }
  operator delete(*a1, 0xA0u);
}

```

## disassembly

```asm
0x18001ee54  push    rbx
0x18001ee56  push    rsi
0x18001ee57  push    rdi
0x18001ee58  push    r14
0x18001ee5a  sub     rsp, 28h
0x18001ee5e  mov     rdx, [rcx]
0x18001ee61  mov     rsi, rcx
0x18001ee64  mov     rax, [rdx+8]
0x18001ee68  mov     qword ptr [rax], 0
0x18001ee6f  mov     r14, [rdx]
0x18001ee72  test    r14, r14
0x18001ee75  jz      short loc_18001EEDD
0x18001ee77  mov     rdi, [r14]
0x18001ee7a  lea     rcx, [r14+70h]
0x18001ee7e  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001ee83  mov     rcx, [r14+68h]; void *
0x18001ee87  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ee8c  mov     qword ptr [r14+68h], 0
0x18001ee94  mov     rcx, [r14+60h]; void *
0x18001ee98  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ee9d  mov     qword ptr [r14+60h], 0
0x18001eea5  mov     rcx, [r14+58h]; void *
0x18001eea9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eeae  lea     rcx, [r14+30h]
0x18001eeb2  mov     qword ptr [r14+58h], 0
0x18001eeba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eebf  lea     rcx, [r14+10h]
0x18001eec3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eec8  mov     edx, 0A0h; unsigned __int64
0x18001eecd  mov     rcx, r14; void *
0x18001eed0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eed5  mov     r14, rdi
0x18001eed8  test    rdi, rdi
0x18001eedb  jnz     short loc_18001EE77
0x18001eedd  mov     rcx, [rsi]; void *
0x18001eee0  mov     edx, 0A0h; unsigned __int64
0x18001eee5  add     rsp, 28h
0x18001eee9  pop     r14
0x18001eeeb  pop     rdi
0x18001eeec  pop     rsi
0x18001eeed  pop     rbx
0x18001eeee  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

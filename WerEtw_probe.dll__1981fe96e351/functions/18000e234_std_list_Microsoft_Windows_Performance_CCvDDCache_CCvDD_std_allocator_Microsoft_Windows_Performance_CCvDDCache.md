# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>(void)

- ea: `0x18000e234`
- end: `0x18000e2d3`
- name: `??1?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e594`
- `0x180028283`

## callees

- `0x180001894`
- `0x18000b534`
- `0x18000e234`
- `0x18000e364`

## pseudocode

```c
void __fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
        void **a1)
{
  void **v1; // rdx
  void **v3; // r14
  void **v4; // rdi

  v1 = (void **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = (void **)*v1;
  if ( *v1 )
  {
    do
    {
      v4 = (void **)*v3;
      std::vector<char>::~vector<char>(v3 + 14);
      operator delete(v3[13]);
      v3[13] = 0;
      operator delete(v3[12]);
      v3[12] = 0;
      operator delete(v3[11]);
      v3[11] = 0;
      std::wstring::~wstring(v3 + 6);
      std::wstring::~wstring(v3 + 2);
      operator delete(v3);
      v3 = v4;
    }
    while ( v4 );
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x18000e234  push    rbx
0x18000e236  push    rsi
0x18000e237  push    rdi
0x18000e238  push    r14
0x18000e23a  sub     rsp, 28h
0x18000e23e  mov     rdx, [rcx]
0x18000e241  mov     rsi, rcx
0x18000e244  mov     rax, [rdx+8]
0x18000e248  mov     qword ptr [rax], 0
0x18000e24f  mov     r14, [rdx]
0x18000e252  test    r14, r14
0x18000e255  jz      short loc_18000E2BD
0x18000e257  mov     rdi, [r14]
0x18000e25a  lea     rcx, [r14+70h]
0x18000e25e  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18000e263  mov     rcx, [r14+68h]; Block
0x18000e267  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e26c  mov     qword ptr [r14+68h], 0
0x18000e274  mov     rcx, [r14+60h]; Block
0x18000e278  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e27d  mov     qword ptr [r14+60h], 0
0x18000e285  mov     rcx, [r14+58h]; Block
0x18000e289  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e28e  lea     rcx, [r14+30h]
0x18000e292  mov     qword ptr [r14+58h], 0
0x18000e29a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e29f  lea     rcx, [r14+10h]
0x18000e2a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e2a8  mov     edx, 0A0h
0x18000e2ad  mov     rcx, r14; Block
0x18000e2b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e2b5  mov     r14, rdi
0x18000e2b8  test    rdi, rdi
0x18000e2bb  jnz     short loc_18000E257
0x18000e2bd  mov     rcx, [rsi]; Block
0x18000e2c0  mov     edx, 0A0h
0x18000e2c5  add     rsp, 28h
0x18000e2c9  pop     r14
0x18000e2cb  pop     rdi
0x18000e2cc  pop     rsi
0x18000e2cd  pop     rbx
0x18000e2ce  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

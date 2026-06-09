# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>(void)

- ea: `0x18001fe48`
- end: `0x18001fee7`
- name: `??1?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800201b4`
- `0x180037a34`

## callees

- `0x180001bf8`
- `0x18000a924`
- `0x18001fe48`
- `0x18001ff78`

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
0x18001fe48  push    rbx
0x18001fe4a  push    rsi
0x18001fe4b  push    rdi
0x18001fe4c  push    r14
0x18001fe4e  sub     rsp, 28h
0x18001fe52  mov     rdx, [rcx]
0x18001fe55  mov     rsi, rcx
0x18001fe58  mov     rax, [rdx+8]
0x18001fe5c  mov     qword ptr [rax], 0
0x18001fe63  mov     r14, [rdx]
0x18001fe66  test    r14, r14
0x18001fe69  jz      short loc_18001FED1
0x18001fe6b  mov     rdi, [r14]
0x18001fe6e  lea     rcx, [r14+70h]
0x18001fe72  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001fe77  mov     rcx, [r14+68h]; void *
0x18001fe7b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fe80  mov     qword ptr [r14+68h], 0
0x18001fe88  mov     rcx, [r14+60h]; void *
0x18001fe8c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fe91  mov     qword ptr [r14+60h], 0
0x18001fe99  mov     rcx, [r14+58h]; void *
0x18001fe9d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fea2  lea     rcx, [r14+30h]
0x18001fea6  mov     qword ptr [r14+58h], 0
0x18001feae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001feb3  lea     rcx, [r14+10h]
0x18001feb7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001febc  mov     edx, 0A0h; unsigned __int64
0x18001fec1  mov     rcx, r14; void *
0x18001fec4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fec9  mov     r14, rdi
0x18001fecc  test    rdi, rdi
0x18001fecf  jnz     short loc_18001FE6B
0x18001fed1  mov     rcx, [rsi]; void *
0x18001fed4  mov     edx, 0A0h; unsigned __int64
0x18001fed9  add     rsp, 28h
0x18001fedd  pop     r14
0x18001fedf  pop     rdi
0x18001fee0  pop     rsi
0x18001fee1  pop     rbx
0x18001fee2  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```

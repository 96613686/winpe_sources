# Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)

- ea: `0x18001f150`
- end: `0x18001f1ab`
- name: `??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180036364`
- `0x18003639a`

## callees

- `0x180001bc8`
- `0x18000a600`
- `0x18001ef84`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(
        Microsoft::Windows::Performance::CCvDDCache::CCvDD *this)
{
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rdx

  std::vector<char>::~vector<char>((char **)this + 12);
  operator delete(*((void **)this + 11), v2);
  *((_QWORD *)this + 11) = 0;
  operator delete(*((void **)this + 10), v3);
  *((_QWORD *)this + 10) = 0;
  operator delete(*((void **)this + 9), v4);
  *((_QWORD *)this + 9) = 0;
  std::wstring::~wstring((char **)this + 4);
  std::wstring::~wstring((char **)this);
}

```

## disassembly

```asm
0x18001f150  push    rbx
0x18001f152  sub     rsp, 20h
0x18001f156  mov     rbx, rcx
0x18001f159  add     rcx, 60h ; '`'
0x18001f15d  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001f162  mov     rcx, [rbx+58h]; void *
0x18001f166  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f16b  mov     qword ptr [rbx+58h], 0
0x18001f173  mov     rcx, [rbx+50h]; void *
0x18001f177  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f17c  mov     qword ptr [rbx+50h], 0
0x18001f184  mov     rcx, [rbx+48h]; void *
0x18001f188  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f18d  lea     rcx, [rbx+20h]
0x18001f191  mov     qword ptr [rbx+48h], 0
0x18001f199  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001f19e  mov     rcx, rbx
0x18001f1a1  add     rsp, 20h
0x18001f1a5  pop     rbx
0x18001f1a6  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```

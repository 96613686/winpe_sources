# Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)

- ea: `0x18000e530`
- end: `0x18000e58b`
- name: `??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002834b`
- `0x1800283a5`

## callees

- `0x180001894`
- `0x18000b534`
- `0x18000e364`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(
        Microsoft::Windows::Performance::CCvDDCache::CCvDD *this)
{
  std::vector<char>::~vector<char>((char **)this + 12);
  operator delete(*((void **)this + 11));
  *((_QWORD *)this + 11) = 0;
  operator delete(*((void **)this + 10));
  *((_QWORD *)this + 10) = 0;
  operator delete(*((void **)this + 9));
  *((_QWORD *)this + 9) = 0;
  std::wstring::~wstring((char **)this + 4);
  std::wstring::~wstring((char **)this);
}

```

## disassembly

```asm
0x18000e530  push    rbx
0x18000e532  sub     rsp, 20h
0x18000e536  mov     rbx, rcx
0x18000e539  add     rcx, 60h ; '`'
0x18000e53d  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18000e542  mov     rcx, [rbx+58h]; Block
0x18000e546  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e54b  mov     qword ptr [rbx+58h], 0
0x18000e553  mov     rcx, [rbx+50h]; Block
0x18000e557  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e55c  mov     qword ptr [rbx+50h], 0
0x18000e564  mov     rcx, [rbx+48h]; Block
0x18000e568  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e56d  lea     rcx, [rbx+20h]
0x18000e571  mov     qword ptr [rbx+48h], 0
0x18000e579  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e57e  mov     rcx, rbx
0x18000e581  add     rsp, 20h
0x18000e585  pop     rbx
0x18000e586  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```

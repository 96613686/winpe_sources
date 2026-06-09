# Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)

- ea: `0x180020150`
- end: `0x1800201ab`
- name: `??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `91`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180037b17`
- `0x180037b4d`

## callees

- `0x180001bf8`
- `0x18000a924`
- `0x18001ff78`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void **this)
{
  std::vector<char>::~vector<char>(this + 12);
  operator delete(this[11]);
  this[11] = 0;
  operator delete(this[10]);
  this[10] = 0;
  operator delete(this[9]);
  this[9] = 0;
  std::wstring::~wstring(this + 4);
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x180020150  push    rbx
0x180020152  sub     rsp, 20h
0x180020156  mov     rbx, rcx
0x180020159  add     rcx, 60h ; '`'
0x18002015d  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180020162  mov     rcx, [rbx+58h]; void *
0x180020166  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002016b  mov     qword ptr [rbx+58h], 0
0x180020173  mov     rcx, [rbx+50h]; void *
0x180020177  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002017c  mov     qword ptr [rbx+50h], 0
0x180020184  mov     rcx, [rbx+48h]; void *
0x180020188  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002018d  lea     rcx, [rbx+20h]
0x180020191  mov     qword ptr [rbx+48h], 0
0x180020199  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002019e  mov     rcx, rbx
0x1800201a1  add     rsp, 20h
0x1800201a5  pop     rbx
0x1800201a6  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```

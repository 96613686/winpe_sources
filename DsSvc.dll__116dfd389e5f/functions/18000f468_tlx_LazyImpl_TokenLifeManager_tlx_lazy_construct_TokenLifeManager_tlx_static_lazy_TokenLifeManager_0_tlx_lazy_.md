# tlx::_LazyImpl<TokenLifeManager,tlx::lazy_construct<TokenLifeManager>,tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>>>::get(void)

- ea: `0x18000f468`
- end: `0x18000f4f0`
- name: `?get@?$_LazyImpl@VTokenLifeManager@@V?$lazy_construct@VTokenLifeManager@@@tlx@@V?$static_lazy@VTokenLifeManager@@$0A@V?$lazy_construct@VTokenLifeManager@@@tlx@@@3@@tlx@@QEAAAEAVTokenLifeManager@@XZ`
- size: `136`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d21c`
- `0x180011d20`
- `0x180011fc0`

## callees

- `0x1800044cc`
- `0x18000f468`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f494`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f494`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f4d7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f4d7`

## pseudocode

```c
int *__fastcall tlx::_LazyImpl<TokenLifeManager,tlx::lazy_construct<TokenLifeManager>,tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>>>::get(
        __int64 a1)
{
  int *v1; // rbx
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF
  int *v4; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(v3) = HIDWORD(a1);
  LODWORD(v3) = 0;
  v4 = 0;
  InitOnceBeginInitialize(&TokenLifeManagerSingleton, 0, (PBOOL)&v3, (LPVOID *)&v4);
  v1 = v4;
  if ( !v4 )
  {
    v3 = 0;
    v1 = &dword_18002B568;
    dword_18002B568 = 86400;
    dword_18002B56C = 1296000;
    dword_18002B570 = 86400;
    InitOnceComplete(&TokenLifeManagerSingleton, 0, &dword_18002B568);
    tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::_Initializer::~_Initializer(&v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f468  mov     rax, rsp
0x18000f46b  mov     [rax+8], rcx
0x18000f46f  push    rbx
0x18000f470  sub     rsp, 20h
0x18000f474  lea     r9, [rax+10h]; lpContext
0x18000f478  mov     dword ptr [rax+8], 0
0x18000f47f  lea     r8, [rax+8]; fPending
0x18000f483  mov     qword ptr [rax+10h], 0
0x18000f48b  xor     edx, edx; dwFlags
0x18000f48d  lea     rcx, ?TokenLifeManagerSingleton@@3V?$static_lazy@VTokenLifeManager@@$0A@V?$lazy_construct@VTokenLifeManager@@@tlx@@@tlx@@A; lpInitOnce
0x18000f494  call    cs:__imp_InitOnceBeginInitialize
0x18000f49a  mov     rbx, [rsp+28h+arg_8]
0x18000f49f  test    rbx, rbx
0x18000f4a2  jnz     short loc_18000F4E7
0x18000f4a4  mov     eax, 15180h
0x18000f4a9  mov     [rsp+28h+arg_0], rbx
0x18000f4ae  lea     rbx, dword_18002B568
0x18000f4b5  mov     cs:dword_18002B568, eax
0x18000f4bb  mov     r8, rbx; lpContext
0x18000f4be  mov     cs:dword_18002B56C, 13C680h
0x18000f4c8  xor     edx, edx; dwFlags
0x18000f4ca  mov     cs:dword_18002B570, eax
0x18000f4d0  lea     rcx, ?TokenLifeManagerSingleton@@3V?$static_lazy@VTokenLifeManager@@$0A@V?$lazy_construct@VTokenLifeManager@@@tlx@@@tlx@@A; lpInitOnce
0x18000f4d7  call    cs:__imp_InitOnceComplete
0x18000f4dd  lea     rcx, [rsp+28h+arg_0]
0x18000f4e2  call    ??1_Initializer@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::_Initializer::~_Initializer(void)
0x18000f4e7  mov     rax, rbx
0x18000f4ea  add     rsp, 20h
0x18000f4ee  pop     rbx
0x18000f4ef  retn
```

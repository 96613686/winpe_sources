# tlx::_LazyImpl<PMNotificationHandler,tlx::lazy_construct<PMNotificationHandler>,tlx::static_lazy<PMNotificationHandler,0,tlx::lazy_construct<PMNotificationHandler>>>::get(void)

- ea: `0x18000f300`
- end: `0x18000f37e`
- name: `?get@?$_LazyImpl@VPMNotificationHandler@@V?$lazy_construct@VPMNotificationHandler@@@tlx@@V?$static_lazy@VPMNotificationHandler@@$0A@V?$lazy_construct@VPMNotificationHandler@@@tlx@@@3@@tlx@@QEAAAEAVPMNotificationHandler@@XZ`
- size: `126`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d21c`
- `0x18000d860`

## callees

- `0x1800044cc`
- `0x18000f300`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f32c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000f32c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f365`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f365`

## pseudocode

```c
int *__fastcall tlx::_LazyImpl<PMNotificationHandler,tlx::lazy_construct<PMNotificationHandler>,tlx::static_lazy<PMNotificationHandler,0,tlx::lazy_construct<PMNotificationHandler>>>::get(
        __int64 a1)
{
  int *v1; // rbx
  union _RTL_RUN_ONCE *v3; // [rsp+30h] [rbp+8h] BYREF
  int *v4; // [rsp+38h] [rbp+10h] BYREF

  HIDWORD(v3) = HIDWORD(a1);
  LODWORD(v3) = 0;
  v4 = 0;
  InitOnceBeginInitialize(&PMNotificationHandlerSingleton, 0, (PBOOL)&v3, (LPVOID *)&v4);
  v1 = v4;
  if ( !v4 )
  {
    dword_18002B580 = 0;
    v3 = 0;
    v1 = &dword_18002B580;
    xmmword_18002B588 = 0;
    InitOnceComplete(&PMNotificationHandlerSingleton, 0, &dword_18002B580);
    tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::_Initializer::~_Initializer(&v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18000f300  mov     rax, rsp
0x18000f303  mov     [rax+8], rcx
0x18000f307  push    rbx
0x18000f308  sub     rsp, 20h
0x18000f30c  lea     r9, [rax+10h]; lpContext
0x18000f310  mov     dword ptr [rax+8], 0
0x18000f317  lea     r8, [rax+8]; fPending
0x18000f31b  mov     qword ptr [rax+10h], 0
0x18000f323  xor     edx, edx; dwFlags
0x18000f325  lea     rcx, ?PMNotificationHandlerSingleton@@3V?$static_lazy@VPMNotificationHandler@@$0A@V?$lazy_construct@VPMNotificationHandler@@@tlx@@@tlx@@A; lpInitOnce
0x18000f32c  call    cs:__imp_InitOnceBeginInitialize
0x18000f332  mov     rbx, [rsp+28h+arg_8]
0x18000f337  test    rbx, rbx
0x18000f33a  jnz     short loc_18000F375
0x18000f33c  mov     cs:dword_18002B580, ebx
0x18000f342  lea     rcx, ?PMNotificationHandlerSingleton@@3V?$static_lazy@VPMNotificationHandler@@$0A@V?$lazy_construct@VPMNotificationHandler@@@tlx@@@tlx@@A; lpInitOnce
0x18000f349  xorps   xmm0, xmm0
0x18000f34c  mov     [rsp+28h+arg_0], rbx
0x18000f351  lea     rbx, dword_18002B580
0x18000f358  xor     edx, edx; dwFlags
0x18000f35a  mov     r8, rbx; lpContext
0x18000f35d  movdqu  cs:xmmword_18002B588, xmm0
0x18000f365  call    cs:__imp_InitOnceComplete
0x18000f36b  lea     rcx, [rsp+28h+arg_0]
0x18000f370  call    ??1_Initializer@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAA@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::_Initializer::~_Initializer(void)
0x18000f375  mov     rax, rbx
0x18000f378  add     rsp, 20h
0x18000f37c  pop     rbx
0x18000f37d  retn
```

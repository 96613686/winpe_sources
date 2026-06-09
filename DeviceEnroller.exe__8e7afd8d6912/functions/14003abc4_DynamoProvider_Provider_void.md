# DynamoProvider::Provider(void)

- ea: `0x14003abc4`
- end: `0x14003acad`
- name: `?Provider@DynamoProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `25`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140036540`
- `0x140036e50`
- `0x140036ed0`
- `0x14003a500`
- `0x14003a850`
- `0x14003acd8`
- `0x14003b7e8`
- `0x14003b8d0`
- `0x14003b9d4`
- `0x14003bad8`
- `0x14003bbdc`
- `0x14003bcc4`
- `0x14003bdac`
- `0x14003bed0`
- `0x14003c030`
- `0x14003c2d0`
- `0x14003c560`
- `0x14003c7f0`
- `0x14003ca80`
- `0x14003cd20`
- `0x14003d150`
- `0x14003f448`
- `0x14003f530`
- `0x14003f620`
- `0x14003f8c0`

## callees

- `0x140001f30`
- `0x140004588`
- `0x14003abc4`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14003abec`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14003abec`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14003ac98`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14003ac98`

## pseudocode

```c
const struct _tlgProvider_t *DynamoProvider::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`DynamoProvider::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_14007E598 = 0;
    v2 = &qword_14007E590;
    qword_14007E590 = (__int64)&CDNDownloaderProvider::`vftable';
    byte_14007E5A0 = 0;
    dword_14007E5A4 = 0;
    qword_14007E5A8 = &`DynamoProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_fe5e1d0125b409f0cdc4f03944f45b13_::_lambda_invoker_cdecl_);
    qword_14007E598 = (__int64)qword_14007E5A8;
    byte_14007E5A0 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_14007E5A8);
    dword_14007E5A4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_14007E590 + 8))(&qword_14007E590);
    InitOnceComplete(&`DynamoProvider::Instance'::`2'::wrapper, 0, &qword_14007E590);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x14003abc4  mov     rax, rsp
0x14003abc7  push    rbx
0x14003abc8  sub     rsp, 20h
0x14003abcc  lea     r9, [rax+10h]; lpContext
0x14003abd0  mov     qword ptr [rax+10h], 0
0x14003abd8  lea     r8, [rax+8]; fPending
0x14003abdc  mov     dword ptr [rax+8], 0
0x14003abe3  xor     edx, edx; dwFlags
0x14003abe5  lea     rcx, ?wrapper@?1??Instance@DynamoProvider@@KAPEAV2@XZ@4V?$static_lazy@VDynamoProvider@@@details@wil@@A; lpInitOnce
0x14003abec  call    cs:__imp_InitOnceBeginInitialize
0x14003abf2  test    eax, eax
0x14003abf4  jz      loc_14003AC9E
0x14003abfa  cmp     [rsp+28h+arg_0], 0
0x14003abff  jz      loc_14003AC9E
0x14003ac05  lea     rbx, qword_14007E590
0x14003ac0c  mov     cs:qword_14007E598, 0
0x14003ac17  lea     rax, ??_7CDNDownloaderProvider@@6B@; const CDNDownloaderProvider::`vftable'
0x14003ac1e  mov     [rsp+28h+arg_8], rbx
0x14003ac23  mov     cs:qword_14007E590, rax
0x14003ac2a  mov     cs:byte_14007E5A0, 0
0x14003ac31  mov     cs:dword_14007E5A4, 0
0x14003ac3b  lea     rax, ?__hInner@?1???0StaticHandle@DynamoProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DynamoProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14003ac42  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_fe5e1d0125b409f0cdc4f03944f45b13_@@CA@XZ; void (__cdecl *)()
0x14003ac49  mov     cs:qword_14007E5A8, rax
0x14003ac50  call    atexit
0x14003ac55  mov     rcx, cs:qword_14007E5A8; CallbackContext
0x14003ac5c  mov     cs:qword_14007E598, rcx
0x14003ac63  mov     cs:byte_14007E5A0, 1
0x14003ac6a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14003ac6f  mov     rax, cs:qword_14007E590
0x14003ac76  mov     rcx, rbx
0x14003ac79  mov     cs:dword_14007E5A4, 1
0x14003ac83  mov     rax, [rax+8]
0x14003ac87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ac8c  mov     r8, rbx; lpContext
0x14003ac8f  lea     rcx, ?wrapper@?1??Instance@DynamoProvider@@KAPEAV2@XZ@4V?$static_lazy@VDynamoProvider@@@details@wil@@A; lpInitOnce
0x14003ac96  xor     edx, edx; dwFlags
0x14003ac98  call    cs:__imp_InitOnceComplete
0x14003ac9e  mov     rax, [rsp+28h+arg_8]
0x14003aca3  mov     rax, [rax+8]
0x14003aca7  add     rsp, 20h
0x14003acab  pop     rbx
0x14003acac  retn
```

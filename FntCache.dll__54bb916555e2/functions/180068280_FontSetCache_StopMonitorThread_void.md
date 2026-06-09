# FontSetCache::StopMonitorThread(void)

- ea: `0x180068280`
- end: `0x180068308`
- name: `?StopMonitorThread@FontSetCache@@UEAAXXZ`
- size: `136`
- prototype: `void __fastcall(FontSetCache *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180063950`
- `0x180069ca8`

## callees

- `0x180068280`
- `0x180068310`
- `0x1800a1558`
- `0x1800a2690`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18006829b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18006829b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800682b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800682b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FontSetCache::StopMonitorThread(HANDLE *this)
{
  HANDLE v2; // rdi
  DWORD v3; // eax
  HANDLE v4; // rcx
  HANDLE v5; // rcx
  DWORD v6; // eax

  FontSetCache::SignalMonitorThread((FontSetCache *)this, 1u);
  ResumeThread(this[15]);
  v2 = this[15];
  while ( 1 )
  {
    v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 1);
    if ( !v3 )
      break;
    v6 = v3 - 192;
    if ( v6 )
    {
      if ( v6 != 66 )
        OSException::ThrowLastError();
      break;
    }
  }
  v4 = this[11];
  this[11] = 0;
  if ( v4 )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = this[12];
  this[12] = 0;
  ComPtr<IDWriteFontFileLoader>::Deref(v5);
}

```

## disassembly

```asm
0x180068280  mov     [rsp+arg_0], rbx
0x180068285  push    rdi
0x180068286  sub     rsp, 20h
0x18006828a  mov     rbx, rcx
0x18006828d  mov     edx, 1; unsigned int
0x180068292  call    ?SignalMonitorThread@FontSetCache@@AEAAXI@Z; FontSetCache::SignalMonitorThread(uint)
0x180068297  mov     rcx, [rbx+78h]; hThread
0x18006829b  call    cs:__imp_ResumeThread
0x1800682a1  mov     rdi, [rbx+78h]
0x1800682a5  mov     r8d, 1; bAlertable
0x1800682ab  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800682ae  mov     rcx, rdi; hHandle
0x1800682b1  call    cs:__imp_WaitForSingleObjectEx
0x1800682b7  test    eax, eax
0x1800682b9  jnz     short loc_1800682E7
0x1800682bb  mov     rcx, [rbx+58h]
0x1800682bf  mov     qword ptr [rbx+58h], 0
0x1800682c7  test    rcx, rcx
0x1800682ca  jnz     short loc_1800682F9
0x1800682cc  mov     rcx, [rbx+60h]
0x1800682d0  mov     qword ptr [rbx+60h], 0
0x1800682d8  mov     rbx, [rsp+28h+arg_0]
0x1800682dd  add     rsp, 20h
0x1800682e1  pop     rdi
0x1800682e2  jmp     ?Deref@?$ComPtr@UIDWriteFontFileLoader@@@@CAXPEAUIDWriteFontFileLoader@@@Z; ComPtr<IDWriteFontFileLoader>::Deref(IDWriteFontFileLoader *)
0x1800682e7  sub     eax, 0C0h
0x1800682ec  jz      short loc_1800682A5
0x1800682ee  cmp     eax, 42h ; 'B'
0x1800682f1  jz      short loc_1800682BB
0x1800682f3  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x1800682f9  mov     rax, [rcx]
0x1800682fc  mov     rax, [rax+10h]
0x180068300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068305  jmp     short loc_1800682CC
```

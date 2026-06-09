# UserHelpers::UserCache::CachedData::~CachedData(void)

- ea: `0x18000868c`
- end: `0x180008762`
- name: `??1CachedData@UserCache@UserHelpers@@QEAA@XZ`
- size: `214`
- prototype: `void __fastcall(UserHelpers::UserCache::CachedData *__hidden this)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008b00`
- `0x18000be34`
- `0x1800136c0`
- `0x180014c20`
- `0x1800153f0`
- `0x1800154f0`
- `0x180022db2`
- `0x180023b70`

## callees

- `0x18000868c`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800086f9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800086f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800086a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800086a7`

## pseudocode

```c
void __fastcall UserHelpers::UserCache::CachedData::~CachedData(UserHelpers::UserCache::CachedData *this)
{
  HSTRING v2; // rcx
  volatile signed __int32 *v3; // rdi
  volatile signed __int32 *v4; // rbx

  v2 = (HSTRING)*((_QWORD *)this + 8);
  if ( v2 )
    WindowsDeleteString(v2);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 7);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  if ( *((_QWORD *)this + 5) >= 8u )
    operator delete(*((void **)this + 2));
  *((_QWORD *)this + 5) = 7;
  *((_QWORD *)this + 4) = 0;
  *((_WORD *)this + 8) = 0;
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v4 && !_InterlockedDecrement(v4 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( !_InterlockedDecrement(v4 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
}

```

## disassembly

```asm
0x18000868c  mov     [rsp+arg_0], rbx
0x180008691  mov     [rsp+arg_8], rsi
0x180008696  push    rdi
0x180008697  sub     rsp, 20h
0x18000869b  mov     rbx, rcx
0x18000869e  mov     rcx, [rcx+40h]; string
0x1800086a2  test    rcx, rcx
0x1800086a5  jz      short loc_1800086AE
0x1800086a7  call    cs:__imp_WindowsDeleteString
0x1800086ad  nop
0x1800086ae  mov     rdi, [rbx+38h]
0x1800086b2  or      esi, 0FFFFFFFFh
0x1800086b5  test    rdi, rdi
0x1800086b8  jz      short loc_1800086EE
0x1800086ba  mov     eax, esi
0x1800086bc  lock xadd [rdi+8], eax
0x1800086c1  add     eax, esi
0x1800086c3  jnz     short loc_1800086EE
0x1800086c5  mov     rax, [rdi]
0x1800086c8  mov     rcx, rdi
0x1800086cb  mov     rax, [rax]
0x1800086ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086d3  mov     eax, esi
0x1800086d5  lock xadd [rdi+0Ch], eax
0x1800086da  add     eax, esi
0x1800086dc  jnz     short loc_1800086EE
0x1800086de  mov     rax, [rdi]
0x1800086e1  mov     rcx, rdi
0x1800086e4  mov     rax, [rax+8]
0x1800086e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ed  nop
0x1800086ee  cmp     qword ptr [rbx+28h], 8
0x1800086f3  jb      short loc_1800086FF
0x1800086f5  mov     rcx, [rbx+10h]
0x1800086f9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800086ff  mov     qword ptr [rbx+28h], 7
0x180008707  mov     qword ptr [rbx+20h], 0
0x18000870f  xor     eax, eax
0x180008711  mov     [rbx+10h], ax
0x180008715  mov     rbx, [rbx+8]
0x180008719  test    rbx, rbx
0x18000871c  jz      short loc_180008752
0x18000871e  mov     eax, esi
0x180008720  lock xadd [rbx+8], eax
0x180008725  add     eax, esi
0x180008727  jnz     short loc_180008752
0x180008729  mov     rax, [rbx]
0x18000872c  mov     rcx, rbx
0x18000872f  mov     rax, [rax]
0x180008732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008737  mov     eax, esi
0x180008739  lock xadd [rbx+0Ch], eax
0x18000873e  add     eax, esi
0x180008740  jnz     short loc_180008752
0x180008742  mov     rax, [rbx]
0x180008745  mov     rcx, rbx
0x180008748  mov     rax, [rax+8]
0x18000874c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008751  nop
0x180008752  mov     rbx, [rsp+28h+arg_0]
0x180008757  mov     rsi, [rsp+28h+arg_8]
0x18000875c  add     rsp, 20h
0x180008760  pop     rdi
0x180008761  retn
```

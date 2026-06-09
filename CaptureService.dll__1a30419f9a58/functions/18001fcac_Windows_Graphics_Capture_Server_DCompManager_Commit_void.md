# Windows::Graphics::Capture::Server::DCompManager::Commit(void)

- ea: `0x18001fcac`
- end: `0x18001fcec`
- name: `?Commit@DCompManager@Server@Capture@Graphics@Windows@@QEAAJXZ`
- size: `64`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::DCompManager *this)`
- caller_count: `11`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c1b8`
- `0x18001c540`
- `0x18001c9e0`
- `0x18001ce10`
- `0x18001ceb0`
- `0x18001d050`
- `0x18001d110`
- `0x18001d1d0`
- `0x18001d270`
- `0x18001d350`
- `0x18001d4b0`

## callees

- `0x18000907c`
- `0x18001fcac`
- `0x180022010`

## string_xrefs

- `0x18001fccc`: `onecoreuap\windows\dwm\capture\svc\dll\dcompmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Graphics::Capture::Server::DCompManager::Commit(
        Windows::Graphics::Capture::Server::DCompManager *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 24LL))(*(_QWORD *)this);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7F,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\dcompmanager.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18001fcac  push    rbx; int
0x18001fcae  sub     rsp, 20h
0x18001fcb2  mov     rcx, [rcx]
0x18001fcb5  mov     rax, [rcx]
0x18001fcb8  mov     rax, [rax+18h]
0x18001fcbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcc1  mov     ebx, eax
0x18001fcc3  test    eax, eax
0x18001fcc5  jns     short loc_18001FCE4
0x18001fcc7  mov     rcx, [rsp+28h]; this
0x18001fccc  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001fcd3  mov     r9d, eax; char *
0x18001fcd6  mov     edx, 7Fh; void *
0x18001fcdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fce0  mov     eax, ebx
0x18001fce2  jmp     short loc_18001FCE6
0x18001fce4  xor     eax, eax
0x18001fce6  add     rsp, 20h
0x18001fcea  pop     rbx
0x18001fceb  retn
```

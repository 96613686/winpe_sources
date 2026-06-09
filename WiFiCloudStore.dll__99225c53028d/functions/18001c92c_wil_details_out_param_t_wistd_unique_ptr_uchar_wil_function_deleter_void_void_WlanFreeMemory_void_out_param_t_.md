# wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WlanFreeMemory(void *)>>>(void)

- ea: `0x18001c92c`
- end: `0x18001c956`
- name: `??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WlanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(__int64)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180014d70`
- `0x1800242a0`
- `0x18002547c`
- `0x180030f60`
- `0x18003651c`
- `0x18003ed13`
- `0x18003ee28`
- `0x18003f18d`
- `0x18003f5d0`
- `0x18003fcfb`
- `0x1800405a0`

## callees

- `0x18001c92c`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x18001c94b`
- `wlanapi!WlanFreeMemory` at `0x18001c94b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WlanFreeMemory(void *)>>>(
        __int64 a1)
{
  void *v1; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
      WlanFreeMemory(v1);
  }
}

```

## disassembly

```asm
0x18001c92c  sub     rsp, 28h
0x18001c930  cmp     byte ptr [rcx+10h], 0
0x18001c934  jz      short loc_18001C951
0x18001c936  mov     rdx, [rcx]
0x18001c939  mov     rax, [rcx+8]
0x18001c93d  mov     r8, [rdx]
0x18001c940  mov     [rdx], rax
0x18001c943  test    r8, r8
0x18001c946  jz      short loc_18001C951
0x18001c948  mov     rcx, r8; pMemory
0x18001c94b  call    cs:__imp_WlanFreeMemory
0x18001c951  add     rsp, 28h
0x18001c955  retn
```

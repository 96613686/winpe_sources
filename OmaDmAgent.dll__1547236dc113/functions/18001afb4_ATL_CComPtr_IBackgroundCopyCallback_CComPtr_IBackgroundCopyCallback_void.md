# ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)

- ea: `0x18001afb4`
- end: `0x18001afd3`
- name: `??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001afdc`
- `0x18001aff8`
- `0x18001b010`
- `0x18001b05c`
- `0x18001b6bc`
- `0x18001b9d4`
- `0x18001bcd4`
- `0x18001bfcc`
- `0x18001c8e4`
- `0x18001cb10`
- `0x18001d000`
- `0x18001e07c`
- `0x18001e154`
- `0x18001e24c`
- `0x18001e530`
- `0x18001e9f0`
- `0x18001eac4`
- `0x18001eba8`
- `0x18001ed00`
- `0x180020b2d`
- `0x180020b3f`
- `0x180020b51`
- `0x180020b63`
- `0x180020b75`
- `0x180020bab`
- `0x180020c35`
- `0x180020c47`
- `0x180020c59`

## callees

- `0x18001afb4`
- `0x180021010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18001afb4  sub     rsp, 28h
0x18001afb8  mov     rcx, [rcx]
0x18001afbb  test    rcx, rcx
0x18001afbe  jz      short loc_18001AFCD
0x18001afc0  mov     rax, [rcx]
0x18001afc3  mov     rax, [rax+10h]
0x18001afc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afcc  nop
0x18001afcd  add     rsp, 28h
0x18001afd1  retn
```

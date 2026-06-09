# Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)

- ea: `0x18000517c`
- end: `0x1800051a2`
- name: `?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `74`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005170`
- `0x18000542c`
- `0x1800054cc`
- `0x18000607c`
- `0x180006504`
- `0x180006590`
- `0x180006634`
- `0x1800080f0`
- `0x1800081b0`
- `0x18000847c`
- `0x18000851c`
- `0x180008950`
- `0x1800092c4`
- `0x180009708`
- `0x180009c68`
- `0x18000a038`
- `0x18000a1f0`
- `0x18000a440`
- `0x18000e1a0`
- `0x18000e210`
- `0x18000e2d0`
- `0x180011b80`
- `0x180014150`
- `0x180014268`
- `0x1800143a8`
- `0x1800144e8`
- `0x180014628`
- `0x1800148ac`
- `0x180014a3c`
- `0x180014bcc`
- `0x180014d5c`
- `0x1800154d4`
- `0x1800154e4`
- `0x180015520`
- `0x180015548`
- `0x180015584`
- `0x18001566c`
- `0x1800156b0`
- `0x180015730`
- `0x180015820`
- `0x180015864`
- `0x1800158a8`
- `0x1800158ec`
- `0x180015930`
- `0x180015978`
- `0x180016d70`
- `0x1800177a0`
- `0x180017890`
- `0x180017ab0`
- `0x180017b8c`

## callees

- `0x18000517c`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(
        __int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx

  result = 0;
  v3 = *a1;
  if ( v3 )
  {
    *a1 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000517c  sub     rsp, 28h
0x180005180  mov     rdx, rcx
0x180005183  xor     eax, eax
0x180005185  mov     rcx, [rcx]
0x180005188  test    rcx, rcx
0x18000518b  jz      short loc_18000519D
0x18000518d  mov     [rdx], rax
0x180005190  mov     rax, [rcx]
0x180005193  mov     rax, [rax+10h]
0x180005197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000519c  nop
0x18000519d  add     rsp, 28h
0x1800051a1  retn
```

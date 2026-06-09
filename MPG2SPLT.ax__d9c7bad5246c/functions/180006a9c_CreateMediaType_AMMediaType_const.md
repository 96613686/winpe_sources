# CreateMediaType(_AMMediaType const *)

- ea: `0x180006a9c`
- end: `0x180006ae8`
- name: `?CreateMediaType@@YAPEAU_AMMediaType@@PEBU1@@Z`
- size: `76`
- prototype: `struct _AMMediaType *__fastcall(const struct _AMMediaType *)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004530`
- `0x180005e00`
- `0x180005fe0`
- `0x1800084a0`
- `0x180018a50`
- `0x180019d80`
- `0x180019e40`
- `0x18002ba10`
- `0x18002be40`

## callees

- `0x180006a0c`
- `0x180006a9c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180006ad2`
- `ole32!CoTaskMemFree` at `0x180006ad2`
- `ole32!CoTaskMemAlloc` at `0x180006aae`
- `ole32!CoTaskMemAlloc` at `0x180006aae`

## pseudocode

```c
struct _AMMediaType *__fastcall CreateMediaType(const struct _AMMediaType *a1)
{
  struct _AMMediaType *v2; // rax
  struct _AMMediaType *v3; // rbx

  v2 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
  v3 = v2;
  if ( !v2 )
    return 0;
  if ( (int)CopyMediaType(v2, a1) < 0 )
  {
    CoTaskMemFree(v3);
    return 0;
  }
  return v3;
}

```

## disassembly

```asm
0x180006a9c  mov     [rsp+arg_0], rbx
0x180006aa1  push    rdi
0x180006aa2  sub     rsp, 20h
0x180006aa6  mov     rdi, rcx
0x180006aa9  mov     ecx, 58h ; 'X'; cb
0x180006aae  call    cs:__imp_CoTaskMemAlloc
0x180006ab4  mov     rbx, rax
0x180006ab7  test    rax, rax
0x180006aba  jnz     short loc_180006AC0
0x180006abc  xor     eax, eax
0x180006abe  jmp     short loc_180006ADD
0x180006ac0  mov     rdx, rdi; struct _AMMediaType *
0x180006ac3  mov     rcx, rbx; struct _AMMediaType *
0x180006ac6  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x180006acb  test    eax, eax
0x180006acd  jns     short loc_180006ADA
0x180006acf  mov     rcx, rbx; pv
0x180006ad2  call    cs:__imp_CoTaskMemFree
0x180006ad8  jmp     short loc_180006ABC
0x180006ada  mov     rax, rbx
0x180006add  mov     rbx, [rsp+28h+arg_0]
0x180006ae2  add     rsp, 20h
0x180006ae6  pop     rdi
0x180006ae7  retn
```

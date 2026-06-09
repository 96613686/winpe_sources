# CopyMediaType(_AMMediaType *,_AMMediaType const *)

- ea: `0x180006a0c`
- end: `0x180006a93`
- name: `?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z`
- size: `135`
- prototype: `__int64 __fastcall(struct _AMMediaType *, const struct _AMMediaType *)`
- caller_count: `10`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180003d40`
- `0x180005db0`
- `0x1800068e4`
- `0x180006a9c`
- `0x18000bed0`
- `0x18000c690`
- `0x1800174cc`
- `0x18001cad0`
- `0x18001cc60`
- `0x180021eac`

## callees

- `0x180006a0c`
- `0x180033dfd`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180006a55`
- `ole32!CoTaskMemAlloc` at `0x180006a55`

## pseudocode

```c
__int64 __fastcall CopyMediaType(struct _AMMediaType *a1, const struct _AMMediaType *a2)
{
  BYTE *v4; // rax

  *a1 = *a2;
  if ( a2->cbFormat )
  {
    v4 = (BYTE *)CoTaskMemAlloc(a2->cbFormat);
    a1->pbFormat = v4;
    if ( !v4 )
    {
      a1->cbFormat = 0;
      return 2147942414LL;
    }
    memcpy_0(v4, a2->pbFormat, a1->cbFormat);
  }
  a1->pUnk = 0;
  return 0;
}

```

## disassembly

```asm
0x180006a0c  mov     [rsp+arg_0], rbx
0x180006a11  push    rdi
0x180006a12  sub     rsp, 20h
0x180006a16  movups  xmm0, xmmword ptr [rdx]
0x180006a19  mov     rdi, rdx
0x180006a1c  mov     rbx, rcx
0x180006a1f  movups  xmmword ptr [rcx], xmm0
0x180006a22  movups  xmm1, xmmword ptr [rdx+10h]
0x180006a26  movups  xmmword ptr [rcx+10h], xmm1
0x180006a2a  movups  xmm0, xmmword ptr [rdx+20h]
0x180006a2e  movups  xmmword ptr [rcx+20h], xmm0
0x180006a32  movups  xmm1, xmmword ptr [rdx+30h]
0x180006a36  movups  xmmword ptr [rcx+30h], xmm1
0x180006a3a  movups  xmm0, xmmword ptr [rdx+40h]
0x180006a3e  movups  xmmword ptr [rcx+40h], xmm0
0x180006a42  movsd   xmm1, qword ptr [rdx+50h]
0x180006a47  movsd   qword ptr [rcx+50h], xmm1
0x180006a4c  cmp     dword ptr [rdx+48h], 0
0x180006a50  jz      short loc_180006A7E
0x180006a52  mov     ecx, [rdx+48h]; cb
0x180006a55  call    cs:__imp_CoTaskMemAlloc
0x180006a5b  mov     [rbx+50h], rax
0x180006a5f  test    rax, rax
0x180006a62  jnz     short loc_180006A6E
0x180006a64  mov     [rbx+48h], eax
0x180006a67  mov     eax, 8007000Eh
0x180006a6c  jmp     short loc_180006A88
0x180006a6e  mov     r8d, [rbx+48h]; Size
0x180006a72  mov     rcx, rax; void *
0x180006a75  mov     rdx, [rdi+50h]; Src
0x180006a79  call    memcpy_0
0x180006a7e  mov     qword ptr [rbx+40h], 0
0x180006a86  xor     eax, eax
0x180006a88  mov     rbx, [rsp+28h+arg_0]
0x180006a8d  add     rsp, 20h
0x180006a91  pop     rdi
0x180006a92  retn
```

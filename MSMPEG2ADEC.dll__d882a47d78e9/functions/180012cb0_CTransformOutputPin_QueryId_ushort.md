# CTransformOutputPin::QueryId(ushort * *)

- ea: `0x180012cb0`
- end: `0x180012d66`
- name: `?QueryId@CTransformOutputPin@@UEAAJPEAPEAG@Z`
- size: `182`
- prototype: `__int64 __fastcall(CTransformOutputPin *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180012cb0`
- `0x1800886fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012d17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012d17`

## pseudocode

```c
__int64 __fastcall CTransformOutputPin::QueryId(CTransformOutputPin *this, unsigned __int16 **a2)
{
  __int64 v4; // rcx
  const WCHAR *v5; // rax
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v4 = 50000;
  v5 = L"Out";
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  if ( !v4 )
    return 2147942487LL;
  v6 = 2 * (50000 - v4);
  v7 = (unsigned __int16 *)CoTaskMemAlloc(v6 + 2);
  *a2 = v7;
  if ( !v7 )
    return 2147942414LL;
  memcpy_0(v7, L"Out", v6 + 2);
  return 0;
}

```

## disassembly

```asm
0x180012cb0  push    rbx
0x180012cb2  sub     rsp, 20h
0x180012cb6  mov     rbx, rdx
0x180012cb9  test    rdx, rdx
0x180012cbc  jnz     short loc_180012CCA
0x180012cbe  mov     eax, 80004003h
0x180012cc3  add     rsp, 20h
0x180012cc7  pop     rbx
0x180012cc8  retn
0x180012cca  mov     r8d, 0C350h
0x180012cd0  mov     qword ptr [rdx], 0
0x180012cd7  mov     ecx, r8d
0x180012cda  lea     rax, Src; "Out"
0x180012ce1  cmp     word ptr [rax], 0
0x180012ce5  jz      short loc_180012CF1
0x180012ce7  add     rax, 2
0x180012ceb  sub     rcx, 1
0x180012cef  jnz     short loc_180012CE1
0x180012cf1  xor     eax, eax
0x180012cf3  mov     edx, 80070057h
0x180012cf8  test    rcx, rcx
0x180012cfb  cmovnz  edx, eax
0x180012cfe  jz      short loc_180012D5D
0x180012d00  sub     r8, rcx
0x180012d03  mov     [rsp+28h+arg_0], rdi
0x180012d08  test    rcx, rcx
0x180012d0b  lea     rdi, [r8+r8]
0x180012d0f  cmovz   rdi, rax
0x180012d13  lea     rcx, [rdi+2]; cb
0x180012d17  call    cs:__imp_CoTaskMemAlloc
0x180012d1e  nop     dword ptr [rax+rax+00h]
0x180012d23  mov     [rbx], rax
0x180012d26  test    rax, rax
0x180012d29  jnz     short loc_180012D3C
0x180012d2b  mov     rdi, [rsp+28h+arg_0]
0x180012d30  mov     eax, 8007000Eh
0x180012d35  add     rsp, 20h
0x180012d39  pop     rbx
0x180012d3a  retn
0x180012d3c  lea     r8, [rdi+2]; Size
0x180012d40  mov     rcx, rax; void *
0x180012d43  lea     rdx, Src; "Out"
0x180012d4a  call    memcpy_0
0x180012d4f  mov     rdi, [rsp+28h+arg_0]
0x180012d54  xor     eax, eax
0x180012d56  add     rsp, 20h
0x180012d5a  pop     rbx
0x180012d5b  retn
0x180012d5d  mov     eax, edx
0x180012d5f  add     rsp, 20h
0x180012d63  pop     rbx
0x180012d64  retn
```

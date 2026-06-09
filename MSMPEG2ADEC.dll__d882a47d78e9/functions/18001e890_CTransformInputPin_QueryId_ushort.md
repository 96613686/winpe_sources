# CTransformInputPin::QueryId(ushort * *)

- ea: `0x18001e890`
- end: `0x18001e946`
- name: `?QueryId@CTransformInputPin@@UEAAJPEAPEAG@Z`
- size: `182`
- prototype: `__int64 __fastcall(CTransformInputPin *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001e890`
- `0x1800886fc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e8f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e8f7`

## pseudocode

```c
__int64 __fastcall CTransformInputPin::QueryId(CTransformInputPin *this, unsigned __int16 **a2)
{
  __int64 v4; // rcx
  const WCHAR *v5; // rax
  __int64 v6; // rdi
  unsigned __int16 *v7; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v4 = 50000;
  v5 = L"In";
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
  memcpy_0(v7, L"In", v6 + 2);
  return 0;
}

```

## disassembly

```asm
0x18001e890  push    rbx
0x18001e892  sub     rsp, 20h
0x18001e896  mov     rbx, rdx
0x18001e899  test    rdx, rdx
0x18001e89c  jnz     short loc_18001E8AA
0x18001e89e  mov     eax, 80004003h
0x18001e8a3  add     rsp, 20h
0x18001e8a7  pop     rbx
0x18001e8a8  retn
0x18001e8aa  mov     r8d, 0C350h
0x18001e8b0  mov     qword ptr [rdx], 0
0x18001e8b7  mov     ecx, r8d
0x18001e8ba  lea     rax, String2; "In"
0x18001e8c1  cmp     word ptr [rax], 0
0x18001e8c5  jz      short loc_18001E8D1
0x18001e8c7  add     rax, 2
0x18001e8cb  sub     rcx, 1
0x18001e8cf  jnz     short loc_18001E8C1
0x18001e8d1  xor     eax, eax
0x18001e8d3  mov     edx, 80070057h
0x18001e8d8  test    rcx, rcx
0x18001e8db  cmovnz  edx, eax
0x18001e8de  jz      short loc_18001E93D
0x18001e8e0  sub     r8, rcx
0x18001e8e3  mov     [rsp+28h+arg_0], rdi
0x18001e8e8  test    rcx, rcx
0x18001e8eb  lea     rdi, [r8+r8]
0x18001e8ef  cmovz   rdi, rax
0x18001e8f3  lea     rcx, [rdi+2]; cb
0x18001e8f7  call    cs:__imp_CoTaskMemAlloc
0x18001e8fe  nop     dword ptr [rax+rax+00h]
0x18001e903  mov     [rbx], rax
0x18001e906  test    rax, rax
0x18001e909  jnz     short loc_18001E91C
0x18001e90b  mov     rdi, [rsp+28h+arg_0]
0x18001e910  mov     eax, 8007000Eh
0x18001e915  add     rsp, 20h
0x18001e919  pop     rbx
0x18001e91a  retn
0x18001e91c  lea     r8, [rdi+2]; Size
0x18001e920  mov     rcx, rax; void *
0x18001e923  lea     rdx, String2; "In"
0x18001e92a  call    memcpy_0
0x18001e92f  mov     rdi, [rsp+28h+arg_0]
0x18001e934  xor     eax, eax
0x18001e936  add     rsp, 20h
0x18001e93a  pop     rbx
0x18001e93b  retn
0x18001e93d  mov     eax, edx
0x18001e93f  add     rsp, 20h
0x18001e943  pop     rbx
0x18001e944  retn
```

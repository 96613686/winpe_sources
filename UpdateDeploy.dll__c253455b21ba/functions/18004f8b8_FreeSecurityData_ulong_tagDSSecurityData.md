# FreeSecurityData(ulong,tagDSSecurityData *)

- ea: `0x18004f8b8`
- end: `0x18004f920`
- name: `?FreeSecurityData@@YAXKPEAUtagDSSecurityData@@@Z`
- size: `104`
- prototype: `void(unsigned int, struct tagDSSecurityData *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004f68c`
- `0x180051b80`

## callees

- `0x18004f8b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f8eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f8eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004f905`

## pseudocode

```c
void __fastcall FreeSecurityData(unsigned int a1, struct tagDSSecurityData *a2)
{
  void **v3; // rbx
  __int64 v4; // rbp

  if ( a2 )
  {
    if ( a1 )
    {
      v3 = (void **)((char *)a2 + 8);
      v4 = a1;
      do
      {
        memset(*v3, 0, *((unsigned int *)v3 - 2));
        CoTaskMemFree(*v3);
        *v3 = 0;
        v3 += 2;
        --v4;
      }
      while ( v4 );
    }
    CoTaskMemFree(a2);
  }
}

```

## disassembly

```asm
0x18004f8b8  test    rdx, rdx
0x18004f8bb  jz      short locret_18004F91F
0x18004f8bd  mov     [rsp+arg_0], rbx
0x18004f8c2  mov     [rsp+arg_8], rbp
0x18004f8c7  mov     [rsp+arg_10], rsi
0x18004f8cc  push    rdi
0x18004f8cd  sub     rsp, 20h
0x18004f8d1  mov     rsi, rdx
0x18004f8d4  test    ecx, ecx
0x18004f8d6  jz      short loc_18004F902
0x18004f8d8  lea     rbx, [rdx+8]
0x18004f8dc  mov     ebp, ecx
0x18004f8de  mov     ecx, [rbx-8]
0x18004f8e1  xor     eax, eax
0x18004f8e3  mov     rdi, [rbx]
0x18004f8e6  rep stosb
0x18004f8e8  mov     rcx, [rbx]; pv
0x18004f8eb  call    cs:__imp_CoTaskMemFree
0x18004f8f1  mov     qword ptr [rbx], 0
0x18004f8f8  lea     rbx, [rbx+10h]
0x18004f8fc  sub     rbp, 1
0x18004f900  jnz     short loc_18004F8DE
0x18004f902  mov     rcx, rsi; pv
0x18004f905  call    cs:__imp_CoTaskMemFree
0x18004f90b  mov     rbx, [rsp+28h+arg_0]
0x18004f910  mov     rbp, [rsp+28h+arg_8]
0x18004f915  mov     rsi, [rsp+28h+arg_10]
0x18004f91a  add     rsp, 20h
0x18004f91e  pop     rdi
0x18004f91f  retn
```

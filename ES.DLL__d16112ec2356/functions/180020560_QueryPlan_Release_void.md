# QueryPlan::Release(void)

- ea: `0x180020560`
- end: `0x1800205e2`
- name: `?Release@QueryPlan@@UEAAKXZ`
- size: `130`
- prototype: `unsigned int __fastcall(QueryPlan *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180020560`

## import_xrefs

- `msvcrt!free` at `0x1800205a7`
- `msvcrt!free` at `0x1800205a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800205ca`

## pseudocode

```c
__int64 __fastcall QueryPlan::Release(QueryPlan *this)
{
  unsigned __int32 v2; // ebp
  __int64 v3; // rbx
  __int64 v4; // rdi

  v2 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v2 && this )
  {
    *(_QWORD *)this = &QueryPlan::`vftable';
    v3 = *((_QWORD *)this + 4);
    if ( v3 )
    {
      do
      {
        v4 = *(_QWORD *)(v3 + 24);
        free(*(void **)v3);
        CoTaskMemFree((LPVOID)v3);
        *((_QWORD *)this + 4) = v4;
        v3 = v4;
      }
      while ( v4 );
    }
    CoTaskMemFree(this);
  }
  return v2;
}

```

## disassembly

```asm
0x180020560  mov     [rsp+arg_10], rbp
0x180020565  push    rsi
0x180020566  sub     rsp, 20h
0x18002056a  mov     rsi, rcx
0x18002056d  mov     ebp, 0FFFFFFFFh
0x180020572  lock xadd [rcx+8], ebp
0x180020577  sub     ebp, 1
0x18002057a  jnz     short loc_1800205D5
0x18002057c  test    rcx, rcx
0x18002057f  jz      short loc_1800205D5
0x180020581  lea     rax, ??_7QueryPlan@@6B@; const QueryPlan::`vftable'
0x180020588  mov     [rsp+28h+arg_0], rbx
0x18002058d  mov     [rcx], rax
0x180020590  mov     rbx, [rcx+20h]
0x180020594  test    rbx, rbx
0x180020597  jz      short loc_1800205C7
0x180020599  mov     [rsp+28h+arg_8], rdi
0x18002059e  xchg    ax, ax
0x1800205a0  mov     rcx, [rbx]; Block
0x1800205a3  mov     rdi, [rbx+18h]
0x1800205a7  call    cs:__imp_free
0x1800205ad  mov     rcx, rbx; pv
0x1800205b0  call    cs:__imp_CoTaskMemFree
0x1800205b6  mov     [rsi+20h], rdi
0x1800205ba  mov     rbx, rdi
0x1800205bd  test    rdi, rdi
0x1800205c0  jnz     short loc_1800205A0
0x1800205c2  mov     rdi, [rsp+28h+arg_8]
0x1800205c7  mov     rcx, rsi; pv
0x1800205ca  call    cs:__imp_CoTaskMemFree
0x1800205d0  mov     rbx, [rsp+28h+arg_0]
0x1800205d5  mov     eax, ebp
0x1800205d7  mov     rbp, [rsp+28h+arg_10]
0x1800205dc  add     rsp, 20h
0x1800205e0  pop     rsi
0x1800205e1  retn
```

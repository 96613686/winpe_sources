# co_array_t<IMVKey *>::allocate(unsigned __int64)

- ea: `0x18000f65c`
- end: `0x18000f6fb`
- name: `?allocate@?$co_array_t@PEAUIMVKey@@@@QEAAX_K@Z`
- size: `159`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d610`

## callees

- `0x18000a2e4`
- `0x18000a304`
- `0x18000f65c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f688`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f688`

## string_xrefs

- `0x18000f6b8`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`
- `0x18000f6e0`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`

## pseudocode

```c
__int64 __fastcall co_array_t<IMVKey *>::allocate(__int64 a1, unsigned __int64 a2)
{
  LPVOID v4; // rax
  void *v5; // rdx
  __int64 v6; // r8
  const char *v7; // r9
  __int64 result; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !is_mul_ok(a2, 8u) )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x3B,
      (int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvtypes.h",
      (const char *)0x80070216LL,
      v9);
  v4 = CoTaskMemRealloc(*(LPVOID *)a1, 8 * a2);
  *(_QWORD *)a1 = v4;
  if ( a2 && !v4 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v5, v6, v7);
  result = 0xFFFFFFFFLL;
  if ( a2 > 0xFFFFFFFF )
  {
    *(_DWORD *)(a1 + 8) = -1;
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x41,
      (int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvtypes.h",
      (const char *)0x80070216LL,
      v9);
  }
  *(_DWORD *)(a1 + 8) = a2;
  return result;
}

```

## disassembly

```asm
0x18000f65c  mov     [rsp+arg_0], rbx
0x18000f661  push    rdi; int
0x18000f662  sub     rsp, 20h
0x18000f666  mov     eax, 8
0x18000f66b  mov     [rsp+28h+arg_10], 0
0x18000f674  mov     rbx, rdx
0x18000f677  mov     rdi, rcx
0x18000f67a  mul     rdx
0x18000f67d  test    rdx, rdx
0x18000f680  jnz     short loc_18000F6B3
0x18000f682  mov     rcx, [rcx]; pv
0x18000f685  mov     rdx, rax; cb
0x18000f688  call    cs:__imp_CoTaskMemRealloc
0x18000f68e  mov     [rdi], rax
0x18000f691  test    rbx, rbx
0x18000f694  jz      short loc_18000F69B
0x18000f696  test    rax, rax
0x18000f699  jz      short loc_18000F6D0
0x18000f69b  mov     eax, 0FFFFFFFFh
0x18000f6a0  cmp     rbx, rax
0x18000f6a3  ja      short loc_18000F6DB
0x18000f6a5  mov     [rdi+8], ebx
0x18000f6a8  mov     rbx, [rsp+28h+arg_0]
0x18000f6ad  add     rsp, 20h
0x18000f6b1  pop     rdi
0x18000f6b2  retn
0x18000f6b3  mov     rcx, [rsp+28h]; this
0x18000f6b8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000f6bf  mov     r9d, 80070216h; char *
0x18000f6c5  mov     edx, 3Bh ; ';'; void *
0x18000f6ca  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000f6d0  mov     rcx, [rsp+28h]; this
0x18000f6d5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18000f6db  mov     rcx, [rsp+28h]; this
0x18000f6e0  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000f6e7  mov     r9d, 80070216h; char *
0x18000f6ed  mov     [rdi+8], eax
0x18000f6f0  mov     edx, 41h ; 'A'; void *
0x18000f6f5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```

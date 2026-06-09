# Windows::Foundation::AsyncOperationCompletedHandler<bool>::__abi_GetIids(ulong *,Platform::Guid * *)

- ea: `0x14001ed7c`
- end: `0x14001edd2`
- name: `?__abi_GetIids@?$AsyncOperationCompletedHandler@_N@Foundation@Windows@@UE$AAAJPEAKPEAPEAVGuid@Platform@@@Z`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001ede0`
- `0x14001edf0`

## callees

- `0x140002844`
- `0x140031960`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::AsyncOperationCompletedHandler<bool>::__abi_GetIids(
        __int64 a1,
        int a2,
        const struct __s_GUID *a3)
{
  __int64 v4; // [rsp+20h] [rbp-20h] BYREF
  int v5; // [rsp+28h] [rbp-18h]
  int v6; // [rsp+2Ch] [rbp-14h]

  v5 = -1873978735;
  v6 = -1518122057;
  return __winRT::__getIids((__winRT *)1, a2, (unsigned int *)&v4, a3, (struct Platform::Guid **)0x4478E5D8FCDCF02CLL);
}

```

## disassembly

```asm
0x14001ed7c  push    rbp
0x14001ed7e  mov     rbp, rsp
0x14001ed81  sub     rsp, 40h
0x14001ed85  mov     rax, cs:__security_cookie
0x14001ed8c  xor     rax, rsp
0x14001ed8f  mov     [rbp+var_10], rax
0x14001ed93  mov     r9, r8; struct __s_GUID *
0x14001ed96  mov     dword ptr [rbp+var_20], 0FCDCF02Ch
0x14001ed9d  lea     r8, [rbp+var_20]; unsigned int *
0x14001eda1  mov     dword ptr [rbp+var_20+4], 4478E5D8h
0x14001eda8  mov     ecx, 1; this
0x14001edad  mov     [rbp+var_18], 904D5A91h
0x14001edb4  mov     [rbp+var_14], 0A5834BB7h
0x14001edbb  call    ?__getIids@__winRT@@YAJHPEAKPEBU__s_GUID@@PEAPEAVGuid@Platform@@@Z; __winRT::__getIids(int,ulong *,__s_GUID const *,Platform::Guid * *)
0x14001edc0  mov     rcx, [rbp+var_10]
0x14001edc4  xor     rcx, rsp; StackCookie
0x14001edc7  call    __security_check_cookie
0x14001edcc  add     rsp, 40h
0x14001edd0  pop     rbp
0x14001edd1  retn
```

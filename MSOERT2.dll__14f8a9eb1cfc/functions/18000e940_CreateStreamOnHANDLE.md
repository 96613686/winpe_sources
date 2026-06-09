# CreateStreamOnHANDLE

- ea: `0x18000e940`
- end: `0x18000e9a9`
- name: `CreateStreamOnHANDLE`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000eaa0`

## callees

- `0x180001b60`
- `0x180001c50`
- `0x18000e940`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CreateStreamOnHANDLE(void *a1, __int64 a2)
{
  int v3; // ebx
  struct CFileStream *v5; // [rsp+38h] [rbp+10h] BYREF

  v3 = -2147024809;
  if ( a2 )
  {
    if ( a1 != (void *)-1LL )
    {
      v5 = 0;
      v3 = CFileStream::CreateInstance(a1, &v5);
      if ( v3 >= 0 )
      {
        v3 = (**(__int64 (__fastcall ***)(struct CFileStream *, GUID *, __int64))v5)(
               v5,
               &GUID_0000000c_0000_0000_c000_000000000046,
               a2);
        OE_SafeReleaseAndNullPtr<CFileStream>(&v5);
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000e940  mov     [rsp+arg_0], rbx
0x18000e945  push    rdi
0x18000e946  sub     rsp, 20h
0x18000e94a  mov     rdi, rdx
0x18000e94d  mov     ebx, 80070057h
0x18000e952  test    rdx, rdx
0x18000e955  jz      short loc_18000E99C
0x18000e957  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e95b  jz      short loc_18000E99C
0x18000e95d  lea     rdx, [rsp+28h+arg_8]; struct CFileStream **
0x18000e962  mov     [rsp+28h+arg_8], 0
0x18000e96b  call    ?CreateInstance@CFileStream@@SAJPEAXPEAPEAV1@@Z; CFileStream::CreateInstance(void *,CFileStream * *)
0x18000e970  mov     ebx, eax
0x18000e972  test    eax, eax
0x18000e974  js      short loc_18000E99C
0x18000e976  mov     rcx, [rsp+28h+arg_8]
0x18000e97b  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x18000e982  mov     r8, rdi
0x18000e985  mov     rax, [rcx]
0x18000e988  mov     rax, [rax]
0x18000e98b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e990  lea     rcx, [rsp+28h+arg_8]
0x18000e995  mov     ebx, eax
0x18000e997  call    ??$OE_SafeReleaseAndNullPtr@VCFileStream@@@@YAXAEAPEAVCFileStream@@@Z; OE_SafeReleaseAndNullPtr<CFileStream>(CFileStream * &)
0x18000e99c  mov     eax, ebx
0x18000e99e  mov     rbx, [rsp+28h+arg_0]
0x18000e9a3  add     rsp, 20h
0x18000e9a7  pop     rdi
0x18000e9a8  retn
```

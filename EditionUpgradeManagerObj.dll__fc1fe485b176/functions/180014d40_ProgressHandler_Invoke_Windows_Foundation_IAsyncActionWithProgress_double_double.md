# ProgressHandler::Invoke(Windows::Foundation::IAsyncActionWithProgress<double> *,double)

- ea: `0x180014d40`
- end: `0x180014d97`
- name: `?Invoke@ProgressHandler@@UEAAJPEAU?$IAsyncActionWithProgress@N@Foundation@Windows@@N@Z`
- size: `87`
- prototype: `__int64 __fastcall(__int64, __int64, double)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180014d40`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x180014d8a`
- `USER32!PostThreadMessageW` at `0x180014d8a`

## pseudocode

```c
__int64 __fastcall ProgressHandler::Invoke(__int64 a1, __int64 a2, double a3)
{
  DWORD v3; // ecx
  double v4; // xmm2_8
  unsigned __int64 v5; // rax

  v3 = *(_DWORD *)(a1 + 72);
  if ( v3 )
  {
    v4 = a3 * 100.0;
    v5 = 0;
    if ( v4 >= 9.223372036854776e18 )
    {
      v4 = v4 - 9.223372036854776e18;
      if ( v4 < 9.223372036854776e18 )
        v5 = 0x8000000000000000uLL;
    }
    PostThreadMessageW(v3, 0x1117u, v5 + (unsigned int)(int)v4, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180014d40  sub     rsp, 28h
0x180014d44  mov     ecx, [rcx+48h]; idThread
0x180014d47  test    ecx, ecx
0x180014d49  jz      short loc_180014D90
0x180014d4b  mulsd   xmm2, cs:__real@4059000000000000
0x180014d53  xor     eax, eax
0x180014d55  movsd   xmm0, cs:__real@43e0000000000000
0x180014d5d  comisd  xmm2, xmm0
0x180014d61  jb      short loc_180014D7A
0x180014d63  subsd   xmm2, xmm0
0x180014d67  comisd  xmm2, xmm0
0x180014d6b  jnb     short loc_180014D7A
0x180014d6d  mov     rdx, 8000000000000000h
0x180014d77  mov     rax, rdx
0x180014d7a  cvttsd2si r8, xmm2
0x180014d7f  xor     r9d, r9d; lParam
0x180014d82  mov     edx, 1117h; Msg
0x180014d87  add     r8, rax; wParam
0x180014d8a  call    cs:__imp_PostThreadMessageW
0x180014d90  xor     eax, eax
0x180014d92  add     rsp, 28h
0x180014d96  retn
```

# Dns_CreateStringCopy_W

- ea: `0x18000e3c8`
- end: `0x18000e468`
- name: `Dns_CreateStringCopy_W`
- size: `160`
- prototype: `__int64 __fastcall(_WORD *Src)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x180007f4c`
- `0x180010898`
- `0x180011858`
- `0x180011f68`
- `0x1800126d8`
- `0x180012838`

## callees

- `0x18000e3c8`
- `0x180012564`
- `0x180013bd4`
- `0x180013f19`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e41a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e41a`

## pseudocode

```c
__int64 __fastcall Dns_CreateStringCopy_W(_WORD *Src)
{
  __int64 v2; // rdi
  __int64 v3; // rax
  SIZE_T v4; // rsi
  __int64 v5; // rax
  void *v6; // rcx
  DWORD v7; // ecx
  __int64 v9; // rax
  LPVOID v10; // rax

  if ( !g_fVelocityDnsKernelApi )
  {
    if ( Src )
    {
      v9 = -1;
      do
        ++v9;
      while ( Src[v9] );
      v4 = (unsigned int)(2 * v9 + 2);
      v10 = Dns_Allocate(v4);
      v2 = (__int64)v10;
      if ( v10 )
      {
        v6 = v10;
        goto LABEL_16;
      }
      v7 = 14;
    }
    else
    {
      v7 = 87;
    }
    SetLastError(v7);
    return 0;
  }
  if ( Src )
  {
    v3 = -1;
    do
      ++v3;
    while ( Src[v3] );
    v4 = (unsigned int)(2 * v3 + 2);
    v5 = Rpc_AllocZero(v4);
    v2 = v5;
    if ( v5 )
    {
      v6 = (void *)v5;
LABEL_16:
      memcpy_0(v6, Src, v4);
      return v2;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e3c8  push    rbx
0x18000e3ca  push    rbp
0x18000e3cb  push    rsi
0x18000e3cc  push    rdi
0x18000e3cd  sub     rsp, 28h
0x18000e3d1  xor     ebp, ebp
0x18000e3d3  mov     rbx, rcx
0x18000e3d6  cmp     cs:g_fVelocityDnsKernelApi, ebp
0x18000e3dc  jz      short loc_18000E412
0x18000e3de  test    rcx, rcx
0x18000e3e1  jnz     short loc_18000E3E8
0x18000e3e3  mov     rdi, rbp
0x18000e3e6  jmp     short loc_18000E45C
0x18000e3e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e3ec  inc     rax
0x18000e3ef  cmp     [rcx+rax*2], bp
0x18000e3f3  jnz     short loc_18000E3EC
0x18000e3f5  lea     eax, ds:2[rax*2]
0x18000e3fc  mov     ecx, eax
0x18000e3fe  mov     esi, eax
0x18000e400  call    Rpc_AllocZero
0x18000e405  mov     rdi, rax
0x18000e408  test    rax, rax
0x18000e40b  jz      short loc_18000E3E3
0x18000e40d  mov     rcx, rax
0x18000e410  jmp     short loc_18000E451
0x18000e412  test    rbx, rbx
0x18000e415  jnz     short loc_18000E424
0x18000e417  lea     ecx, [rbx+57h]; dwErrCode
0x18000e41a  call    cs:__imp_SetLastError
0x18000e420  xor     eax, eax
0x18000e422  jmp     short loc_18000E45F
0x18000e424  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e428  inc     rax
0x18000e42b  cmp     [rcx+rax*2], bp
0x18000e42f  jnz     short loc_18000E428
0x18000e431  lea     eax, ds:2[rax*2]
0x18000e438  mov     ecx, eax
0x18000e43a  mov     esi, eax
0x18000e43c  call    Dns_Allocate
0x18000e441  mov     rdi, rax
0x18000e444  test    rax, rax
0x18000e447  jnz     short loc_18000E44E
0x18000e449  lea     ecx, [rax+0Eh]
0x18000e44c  jmp     short loc_18000E41A
0x18000e44e  mov     rcx, rdi; void *
0x18000e451  mov     r8, rsi; Size
0x18000e454  mov     rdx, rbx; Src
0x18000e457  call    memcpy_0
0x18000e45c  mov     rax, rdi
0x18000e45f  add     rsp, 28h
0x18000e463  pop     rdi
0x18000e464  pop     rsi
0x18000e465  pop     rbp
0x18000e466  pop     rbx
0x18000e467  retn
```

# SspirCallRpc

- ea: `0x1800012b0`
- end: `0x1800013bc`
- name: `SspirCallRpc`
- size: `268`
- prototype: `__int64 __fastcall(__int64, unsigned int, const void *, _DWORD *, __int16 **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800029d0`

## callees

- `0x1800012b0`
- `0x1800013d0`
- `0x180003207`
- `0x180003213`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall SspirCallRpc(__int64 a1, unsigned int a2, const void *a3, _DWORD *a4, __int16 **a5, __int64 a6)
{
  __int16 *v10; // rax
  __int16 *v11; // rbx
  int v12; // edi

  if ( !gLsapSspiExtension || !*(_QWORD *)(gLsapSspiExtension + 32) )
    return 3221225659LL;
  if ( a2 > 0x1F8 )
    return 3221225485LL;
  if ( *(_QWORD *)gLsapSspiExtension )
  {
    v10 = (__int16 *)(*(__int64 (__fastcall **)(__int64))gLsapSspiExtension)(504);
    v11 = v10;
    if ( v10 )
    {
      memset_0(v10, 0, 0x1F8u);
      memcpy_0(v11, a3, a2);
      if ( v11[1] == a2 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, __int16 *, __int64))(gLsapSspiExtension + 32))(a1, v11, a6);
        if ( v12 >= 0 )
        {
          *a5 = v11;
          *a4 = v11[1];
          return (unsigned int)v12;
        }
      }
      else
      {
        v12 = -1073741584;
      }
      MIDL_user_free(v11);
      return (unsigned int)v12;
    }
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x1800012b0  push    rbp
0x1800012b2  push    rsi
0x1800012b3  push    rdi
0x1800012b4  push    r14
0x1800012b6  sub     rsp, 28h
0x1800012ba  mov     rax, cs:gLsapSspiExtension
0x1800012c1  mov     rsi, r9
0x1800012c4  mov     edi, edx
0x1800012c6  mov     rbp, r8
0x1800012c9  mov     r14, rcx
0x1800012cc  test    rax, rax
0x1800012cf  jz      loc_180001379
0x1800012d5  cmp     qword ptr [rax+20h], 0
0x1800012da  jz      loc_180001379
0x1800012e0  cmp     edi, 1F8h
0x1800012e6  ja      loc_180001388
0x1800012ec  mov     rax, [rax]
0x1800012ef  mov     [rsp+48h+arg_0], rbx
0x1800012f4  test    rax, rax
0x1800012f7  jz      loc_180001397
0x1800012fd  mov     ecx, 1F8h
0x180001302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001307  mov     rbx, rax
0x18000130a  test    rax, rax
0x18000130d  jz      loc_180001397
0x180001313  xor     edx, edx; Val
0x180001315  mov     r8d, 1F8h; Size
0x18000131b  mov     rcx, rax; void *
0x18000131e  call    memset_0
0x180001323  mov     r8d, edi; Size
0x180001326  mov     rdx, rbp; Src
0x180001329  mov     rcx, rbx; void *
0x18000132c  call    memcpy_0
0x180001331  movsx   ecx, word ptr [rbx+2]
0x180001335  cmp     ecx, edi
0x180001337  jnz     short loc_1800013B5
0x180001339  mov     rax, cs:gLsapSspiExtension
0x180001340  mov     rdx, rbx
0x180001343  mov     r8, [rsp+48h+arg_28]
0x180001348  mov     rcx, r14
0x18000134b  mov     rax, [rax+20h]
0x18000134f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001354  mov     edi, eax
0x180001356  test    eax, eax
0x180001358  js      short loc_1800013AB
0x18000135a  mov     rcx, [rsp+48h+arg_20]
0x18000135f  mov     [rcx], rbx
0x180001362  movsx   ecx, word ptr [rbx+2]
0x180001366  mov     [rsi], ecx
0x180001368  mov     rbx, [rsp+48h+arg_0]
0x18000136d  mov     eax, edi
0x18000136f  add     rsp, 28h
0x180001373  pop     r14
0x180001375  pop     rdi
0x180001376  pop     rsi
0x180001377  pop     rbp
0x180001378  retn
0x180001379  mov     eax, 0C00000BBh
0x18000137e  add     rsp, 28h
0x180001382  pop     r14
0x180001384  pop     rdi
0x180001385  pop     rsi
0x180001386  pop     rbp
0x180001387  retn
0x180001388  mov     eax, 0C000000Dh
0x18000138d  add     rsp, 28h
0x180001391  pop     r14
0x180001393  pop     rdi
0x180001394  pop     rsi
0x180001395  pop     rbp
0x180001396  retn
0x180001397  mov     rbx, [rsp+48h+arg_0]
0x18000139c  mov     eax, 0C000009Ah
0x1800013a1  add     rsp, 28h
0x1800013a5  pop     r14
0x1800013a7  pop     rdi
0x1800013a8  pop     rsi
0x1800013a9  pop     rbp
0x1800013aa  retn
0x1800013ab  mov     rcx, rbx; void *
0x1800013ae  call    MIDL_user_free
0x1800013b3  jmp     short loc_180001368
0x1800013b5  mov     edi, 0C00000F0h
0x1800013ba  jmp     short loc_1800013AB
```

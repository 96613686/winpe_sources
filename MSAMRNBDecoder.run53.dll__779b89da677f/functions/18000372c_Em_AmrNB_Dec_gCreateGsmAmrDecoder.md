# Em_AmrNB_Dec_gCreateGsmAmrDecoder

- ea: `0x18000372c`
- end: `0x1800037f8`
- name: `Em_AmrNB_Dec_gCreateGsmAmrDecoder`
- size: `204`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003080`

## callees

- `0x180001f42`
- `0x180001f66`
- `0x18000372c`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gCreateGsmAmrDecoder(_QWORD *a1)
{
  _OWORD *v2; // rbx
  void *v3; // rax
  __int64 result; // rax

  v2 = o_malloc_0(0x48u);
  if ( !v2 )
    return 4294967294LL;
  *v2 = 0;
  v2[1] = 0;
  v2[2] = 0;
  v2[3] = 0;
  *((_QWORD *)v2 + 8) = 0;
  v3 = o_malloc_0(0x4E4u);
  *((_QWORD *)v2 + 5) = v3;
  if ( !v3 )
    return 4294967294LL;
  memset_0(v3, 0, 0x4E4u);
  *((_DWORD *)v2 + 12) = 0;
  *((_QWORD *)v2 + 3) = Em_AmrNB_Dec_sGsmAmrDelete;
  *((_DWORD *)v2 + 15) = 1;
  *(_QWORD *)v2 = Em_AmrNB_Dec_sGsmAmrDecodeFrame;
  *((_QWORD *)v2 + 2) = Em_AmrNB_Dec_sGsmAmrGetParam;
  *((_QWORD *)v2 + 1) = Em_AmrNB_Dec_sGsmAmrSetParam;
  *((_QWORD *)v2 + 4) = Em_AmrNB_Dec_sGsmAmrReset;
  *a1 = v2;
  (*((void (__fastcall **)(_OWORD *))v2 + 4))(v2);
  result = 0;
  *((_DWORD *)v2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x18000372c  mov     [rsp+arg_0], rbx
0x180003731  push    rdi
0x180003732  sub     rsp, 20h
0x180003736  mov     rdi, rcx
0x180003739  mov     ecx, 48h ; 'H'; Size
0x18000373e  call    _o_malloc_0
0x180003743  mov     rbx, rax
0x180003746  test    rax, rax
0x180003749  jz      loc_1800037E8
0x18000374f  xorps   xmm0, xmm0
0x180003752  xor     eax, eax
0x180003754  movups  xmmword ptr [rbx], xmm0
0x180003757  mov     ecx, 4E4h; Size
0x18000375c  movups  xmmword ptr [rbx+10h], xmm0
0x180003760  movups  xmmword ptr [rbx+20h], xmm0
0x180003764  movups  xmmword ptr [rbx+30h], xmm0
0x180003768  mov     [rbx+40h], rax
0x18000376c  call    _o_malloc_0
0x180003771  mov     [rbx+28h], rax
0x180003775  test    rax, rax
0x180003778  jz      short loc_1800037E8
0x18000377a  xor     edx, edx; Val
0x18000377c  mov     r8d, 4E4h; Size
0x180003782  mov     rcx, rax; void *
0x180003785  call    memset_0
0x18000378a  lea     rax, Em_AmrNB_Dec_sGsmAmrDelete
0x180003791  mov     dword ptr [rbx+30h], 0
0x180003798  mov     [rbx+18h], rax
0x18000379c  mov     rcx, rbx
0x18000379f  lea     rax, Em_AmrNB_Dec_sGsmAmrDecodeFrame
0x1800037a6  mov     dword ptr [rbx+3Ch], 1
0x1800037ad  mov     [rbx], rax
0x1800037b0  lea     rax, Em_AmrNB_Dec_sGsmAmrGetParam
0x1800037b7  mov     [rbx+10h], rax
0x1800037bb  lea     rax, Em_AmrNB_Dec_sGsmAmrSetParam
0x1800037c2  mov     [rbx+8], rax
0x1800037c6  lea     rax, Em_AmrNB_Dec_sGsmAmrReset
0x1800037cd  mov     [rbx+20h], rax
0x1800037d1  mov     [rdi], rbx
0x1800037d4  mov     rax, [rbx+20h]
0x1800037d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037dd  xor     eax, eax
0x1800037df  mov     dword ptr [rbx+40h], 0
0x1800037e6  jmp     short loc_1800037ED
0x1800037e8  mov     eax, 0FFFFFFFEh
0x1800037ed  mov     rbx, [rsp+28h+arg_0]
0x1800037f2  add     rsp, 20h
0x1800037f6  pop     rdi
0x1800037f7  retn
```

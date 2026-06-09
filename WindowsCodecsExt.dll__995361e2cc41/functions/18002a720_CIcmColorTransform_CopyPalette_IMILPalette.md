# CIcmColorTransform::CopyPalette(IMILPalette *)

- ea: `0x18002a720`
- end: `0x18002a792`
- name: `?CopyPalette@CIcmColorTransform@@UEAAJPEAUIMILPalette@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(CIcmColorTransform *__hidden this, struct IMILPalette *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x18002a720`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform::CopyPalette(CIcmColorTransform *this, struct IMILPalette *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  char *v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = (char *)this - 72;
  CMTALock::Enter((CIcmColorTransform *)((char *)this - 72));
  if ( a2 )
  {
    v5 = *((_QWORD *)this + 5);
    if ( v5 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, struct IMILPalette *))(*(_QWORD *)v5 + 48LL))(v5, a2);
    }
    else
    {
      v4 = -2003292347;
      if ( g_doStackCaptures )
        DoStackCapture(-2003292347);
    }
  }
  else
  {
    v4 = -2147024809;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v7);
  return v4;
}

```

## disassembly

```asm
0x18002a720  mov     [rsp+arg_8], rbx
0x18002a725  push    rdi
0x18002a726  sub     rsp, 20h
0x18002a72a  mov     rbx, rcx
0x18002a72d  mov     rdi, rdx
0x18002a730  add     rcx, 0FFFFFFFFFFFFFFB8h; this
0x18002a734  mov     [rsp+28h+arg_0], rcx
0x18002a739  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002a73e  test    rdi, rdi
0x18002a741  jnz     short loc_18002A74A
0x18002a743  mov     ebx, 80070057h
0x18002a748  jmp     short loc_18002A77B
0x18002a74a  mov     rcx, [rbx+28h]
0x18002a74e  test    rcx, rcx
0x18002a751  jz      short loc_18002A766
0x18002a753  mov     rax, [rcx]
0x18002a756  mov     rdx, rdi
0x18002a759  mov     rax, [rax+30h]
0x18002a75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a762  mov     ebx, eax
0x18002a764  jmp     short loc_18002A77B
0x18002a766  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002a76d  mov     ebx, 88982F45h
0x18002a772  jz      short loc_18002A77B
0x18002a774  mov     ecx, ebx; int
0x18002a776  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002a77b  lea     rcx, [rsp+28h+arg_0]
0x18002a780  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18002a785  mov     eax, ebx
0x18002a787  mov     rbx, [rsp+28h+arg_8]
0x18002a78c  add     rsp, 20h
0x18002a790  pop     rdi
0x18002a791  retn
```

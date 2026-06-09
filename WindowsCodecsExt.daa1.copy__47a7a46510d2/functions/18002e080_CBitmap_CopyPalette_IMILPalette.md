# CBitmap::CopyPalette(IMILPalette *)

- ea: `0x18002e080`
- end: `0x18002e0fd`
- name: `?CopyPalette@CBitmap@@UEAAJPEAUIMILPalette@@@Z`
- size: `125`
- prototype: `__int64 __fastcall(CBitmap *__hidden this, struct IMILPalette *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x18002e080`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CBitmap::CopyPalette(CBitmap *this, struct IMILPalette *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  char *v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = (char *)this + 160;
  CMTALock::Enter((CBitmap *)((char *)this + 160));
  if ( a2 )
  {
    v5 = *((_QWORD *)this + 15);
    if ( v5 )
    {
      v6 = (*(__int64 (__fastcall **)(struct IMILPalette *, __int64))(*(_QWORD *)a2 + 48LL))(a2, v5 + 72);
      v4 = v6;
      if ( v6 < 0 && g_doStackCaptures )
        DoStackCapture(v6);
    }
    else
    {
      v4 = -2003292347;
    }
  }
  else
  {
    v4 = -2147024809;
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v8);
  return v4;
}

```

## disassembly

```asm
0x18002e080  mov     [rsp+arg_8], rbx
0x18002e085  push    rdi
0x18002e086  sub     rsp, 20h
0x18002e08a  mov     rbx, rcx
0x18002e08d  mov     rdi, rdx
0x18002e090  add     rcx, 0A0h; this
0x18002e097  mov     [rsp+28h+arg_0], rcx
0x18002e09c  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002e0a1  test    rdi, rdi
0x18002e0a4  jnz     short loc_18002E0AD
0x18002e0a6  mov     ebx, 80070057h
0x18002e0ab  jmp     short loc_18002E0E6
0x18002e0ad  mov     rdx, [rbx+78h]
0x18002e0b1  test    rdx, rdx
0x18002e0b4  jnz     short loc_18002E0BD
0x18002e0b6  mov     ebx, 88982F45h
0x18002e0bb  jmp     short loc_18002E0E6
0x18002e0bd  mov     rax, [rdi]
0x18002e0c0  add     rdx, 48h ; 'H'
0x18002e0c4  mov     rcx, rdi
0x18002e0c7  mov     rax, [rax+30h]
0x18002e0cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0d0  mov     ebx, eax
0x18002e0d2  test    eax, eax
0x18002e0d4  jns     short loc_18002E0E6
0x18002e0d6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002e0dd  jz      short loc_18002E0E6
0x18002e0df  mov     ecx, eax; int
0x18002e0e1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002e0e6  lea     rcx, [rsp+28h+arg_0]
0x18002e0eb  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18002e0f0  mov     eax, ebx
0x18002e0f2  mov     rbx, [rsp+28h+arg_8]
0x18002e0f7  add     rsp, 20h
0x18002e0fb  pop     rdi
0x18002e0fc  retn
```

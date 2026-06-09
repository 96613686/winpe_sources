# CFormatConverterNChannel::CopyPalette(IWICPalette *)

- ea: `0x18002a3f0`
- end: `0x18002a465`
- name: `?CopyPalette@CFormatConverterNChannel@@UEAAJPEAUIWICPalette@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(CFormatConverterNChannel *__hidden this, struct IWICPalette *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x18002a3f0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CFormatConverterNChannel::CopyPalette(CFormatConverterNChannel *this, struct IWICPalette *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rcx
  int v6; // eax
  char *v8; // [rsp+30h] [rbp+8h] BYREF

  v4 = -2003292412;
  v8 = (char *)this - 56;
  CMTALock::Enter((CFormatConverterNChannel *)((char *)this - 56));
  v5 = *((_QWORD *)this + 17);
  if ( v5 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, struct IWICPalette *))(*(_QWORD *)v5 + 48LL))(v5, a2);
    v4 = v6;
    if ( v6 < 0 )
    {
      if ( g_doStackCaptures )
        DoStackCapture(v6);
    }
  }
  CGuard<CMTALock>::~CGuard<CMTALock>(&v8);
  return v4;
}

```

## disassembly

```asm
0x18002a3f0  mov     [rsp+arg_8], rbx
0x18002a3f5  mov     [rsp+arg_10], rsi
0x18002a3fa  push    rdi
0x18002a3fb  sub     rsp, 20h
0x18002a3ff  mov     rbx, rcx
0x18002a402  mov     rsi, rdx
0x18002a405  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x18002a409  mov     edi, 88982F04h
0x18002a40e  mov     [rsp+28h+arg_0], rcx
0x18002a413  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002a418  mov     rcx, [rbx+88h]
0x18002a41f  test    rcx, rcx
0x18002a422  jz      short loc_18002A449
0x18002a424  mov     rax, [rcx]
0x18002a427  mov     rdx, rsi
0x18002a42a  mov     rax, [rax+30h]
0x18002a42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a433  mov     edi, eax
0x18002a435  test    eax, eax
0x18002a437  jns     short loc_18002A449
0x18002a439  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002a440  jz      short loc_18002A449
0x18002a442  mov     ecx, eax; int
0x18002a444  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002a449  lea     rcx, [rsp+28h+arg_0]
0x18002a44e  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18002a453  mov     rbx, [rsp+28h+arg_8]
0x18002a458  mov     eax, edi
0x18002a45a  mov     rsi, [rsp+28h+arg_10]
0x18002a45f  add     rsp, 20h
0x18002a463  pop     rdi
0x18002a464  retn
```

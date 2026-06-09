# CFormatConverterWMPhoto::CopyPalette(IWICPalette *)

- ea: `0x18002b1e0`
- end: `0x18002b252`
- name: `?CopyPalette@CFormatConverterWMPhoto@@UEAAJPEAUIWICPalette@@@Z`
- size: `114`
- prototype: `__int64 __fastcall(CFormatConverterWMPhoto *__hidden this, struct IWICPalette *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x1800171c4`
- `0x18002b1e0`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CFormatConverterWMPhoto::CopyPalette(CFormatConverterWMPhoto *this, struct IWICPalette *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rcx
  int v6; // eax
  char *v8; // [rsp+30h] [rbp+8h] BYREF

  v4 = -2003292412;
  v8 = (char *)this - 56;
  CMTALock::Enter((CFormatConverterWMPhoto *)((char *)this - 56));
  v5 = *((_QWORD *)this + 9);
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
0x18002b1e0  mov     [rsp+arg_8], rbx
0x18002b1e5  mov     [rsp+arg_10], rsi
0x18002b1ea  push    rdi
0x18002b1eb  sub     rsp, 20h
0x18002b1ef  mov     rbx, rcx
0x18002b1f2  mov     rsi, rdx
0x18002b1f5  add     rcx, 0FFFFFFFFFFFFFFC8h; this
0x18002b1f9  mov     edi, 88982F04h
0x18002b1fe  mov     [rsp+28h+arg_0], rcx
0x18002b203  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18002b208  mov     rcx, [rbx+48h]
0x18002b20c  test    rcx, rcx
0x18002b20f  jz      short loc_18002B236
0x18002b211  mov     rax, [rcx]
0x18002b214  mov     rdx, rsi
0x18002b217  mov     rax, [rax+30h]
0x18002b21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b220  mov     edi, eax
0x18002b222  test    eax, eax
0x18002b224  jns     short loc_18002B236
0x18002b226  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002b22d  jz      short loc_18002B236
0x18002b22f  mov     ecx, eax; int
0x18002b231  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002b236  lea     rcx, [rsp+28h+arg_0]
0x18002b23b  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x18002b240  mov     rbx, [rsp+28h+arg_8]
0x18002b245  mov     eax, edi
0x18002b247  mov     rsi, [rsp+28h+arg_10]
0x18002b24c  add     rsp, 20h
0x18002b250  pop     rdi
0x18002b251  retn
```

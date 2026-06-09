# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003b00`
- end: `0x180003b59`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `89`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003b00`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        __int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2
    && (a3->Data1 || *(_DWORD *)&a3->Data2 || *(_DWORD *)a3->Data4 != 192 || *(_DWORD *)&a3->Data4[4] != 1174405120) )
  {
    return 2147746064LL;
  }
  else
  {
    return this[8](a2, a3, a4);
  }
}

```

## disassembly

```asm
0x180003b00  mov     rax, r8
0x180003b03  mov     r10, rdx
0x180003b06  mov     r11, rcx
0x180003b09  test    r9, r9
0x180003b0c  jz      short loc_180003B53
0x180003b0e  mov     qword ptr [r9], 0
0x180003b15  test    rdx, rdx
0x180003b18  jz      short loc_180003B41
0x180003b1a  cmp     dword ptr [r8], 0
0x180003b1e  jnz     short loc_180003B3B
0x180003b20  cmp     dword ptr [r8+4], 0
0x180003b25  jnz     short loc_180003B3B
0x180003b27  cmp     dword ptr [r8+8], 0C0h
0x180003b2f  jnz     short loc_180003B3B
0x180003b31  cmp     dword ptr [r8+0Ch], 46000000h
0x180003b39  jz      short loc_180003B41
0x180003b3b  mov     eax, 80040110h
0x180003b40  retn
0x180003b41  mov     rdx, rax
0x180003b44  mov     r8, r9
0x180003b47  mov     rax, [r11+40h]
0x180003b4b  mov     rcx, r10
0x180003b4e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180003b53  mov     eax, 80004003h
0x180003b58  retn
```

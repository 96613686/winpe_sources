# CreateInstance

- ea: `0x180008db0`
- end: `0x180008e59`
- name: `CreateInstance`
- size: `169`
- prototype: `__int64 __fastcall(void *Buf2, struct IUnknown *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008ab0`
- `0x180008db0`
- `0x180020f39`

## pseudocode

```c
__int64 __fastcall CreateInstance(void *Buf2, struct IUnknown *a2, struct _GUID *a3, void **a4)
{
  __int64 result; // rax
  int v9; // ebx
  _QWORD v10[2]; // [rsp+20h] [rbp-58h] BYREF
  int v11; // [rsp+30h] [rbp-48h]

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v9 = 0;
  while ( memcmp_0(*(&g_ComClassTemplates + 2 * v9), Buf2, 0x10u) )
  {
    if ( ++v9 >= 1 )
      return 2147746065LL;
  }
  _InterlockedIncrement(&g_cActiveObjects);
  v10[1] = &g_ComClassTemplates + 2 * v9;
  v10[0] = &CClassFactory::`vftable';
  v11 = 0;
  result = CClassFactory::CreateInstance((CClassFactory *)v10, a2, a3, a4);
  _InterlockedDecrement(&g_cActiveObjects);
  return result;
}

```

## disassembly

```asm
0x180008db0  push    rbx
0x180008db2  push    rbp
0x180008db3  push    rsi
0x180008db4  push    rdi
0x180008db5  push    r14
0x180008db7  push    r15
0x180008db9  sub     rsp, 48h
0x180008dbd  mov     rdi, r9
0x180008dc0  mov     rbp, r8
0x180008dc3  mov     r14, rdx
0x180008dc6  mov     r15, rcx
0x180008dc9  test    r9, r9
0x180008dcc  jnz     short loc_180008DD5
0x180008dce  mov     eax, 80004003h
0x180008dd3  jmp     short loc_180008E4C
0x180008dd5  mov     qword ptr [r9], 0
0x180008ddc  xor     ebx, ebx
0x180008dde  lea     rcx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x180008de5  movsxd  rsi, ebx
0x180008de8  shl     rsi, 4
0x180008dec  mov     r8d, 10h; Size
0x180008df2  add     rsi, rcx
0x180008df5  mov     rdx, r15; Buf2
0x180008df8  mov     rcx, [rsi]; Buf1
0x180008dfb  call    memcmp_0
0x180008e00  test    eax, eax
0x180008e02  jz      short loc_180008E12
0x180008e04  inc     ebx
0x180008e06  cmp     ebx, 1
0x180008e09  jl      short loc_180008DDE
0x180008e0b  mov     eax, 80040111h
0x180008e10  jmp     short loc_180008E4C
0x180008e12  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180008e19  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180008e20  mov     [rsp+78h+var_50], rsi
0x180008e25  mov     r9, rdi; void **
0x180008e28  mov     [rsp+78h+var_58], rax
0x180008e2d  mov     r8, rbp; struct _GUID *
0x180008e30  mov     [rsp+78h+var_48], 0
0x180008e38  mov     rdx, r14; struct IUnknown *
0x180008e3b  lea     rcx, [rsp+78h+var_58]; this
0x180008e40  call    ?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)
0x180008e45  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180008e4c  add     rsp, 48h
0x180008e50  pop     r15
0x180008e52  pop     r14
0x180008e54  pop     rdi
0x180008e55  pop     rsi
0x180008e56  pop     rbp
0x180008e57  pop     rbx
0x180008e58  retn
```

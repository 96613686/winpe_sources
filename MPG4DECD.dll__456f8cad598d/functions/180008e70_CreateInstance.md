# CreateInstance

- ea: `0x180008e70`
- end: `0x180008f19`
- name: `CreateInstance`
- size: `169`
- prototype: `__int64 __fastcall(void *Buf2, struct IUnknown *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180008b70`
- `0x180008e70`
- `0x180020ff9`

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
0x180008e70  push    rbx
0x180008e72  push    rbp
0x180008e73  push    rsi
0x180008e74  push    rdi
0x180008e75  push    r14
0x180008e77  push    r15
0x180008e79  sub     rsp, 48h
0x180008e7d  mov     rdi, r9
0x180008e80  mov     rbp, r8
0x180008e83  mov     r14, rdx
0x180008e86  mov     r15, rcx
0x180008e89  test    r9, r9
0x180008e8c  jnz     short loc_180008E95
0x180008e8e  mov     eax, 80004003h
0x180008e93  jmp     short loc_180008F0C
0x180008e95  mov     qword ptr [r9], 0
0x180008e9c  xor     ebx, ebx
0x180008e9e  lea     rcx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x180008ea5  movsxd  rsi, ebx
0x180008ea8  shl     rsi, 4
0x180008eac  mov     r8d, 10h; Size
0x180008eb2  add     rsi, rcx
0x180008eb5  mov     rdx, r15; Buf2
0x180008eb8  mov     rcx, [rsi]; Buf1
0x180008ebb  call    memcmp_0
0x180008ec0  test    eax, eax
0x180008ec2  jz      short loc_180008ED2
0x180008ec4  inc     ebx
0x180008ec6  cmp     ebx, 1
0x180008ec9  jl      short loc_180008E9E
0x180008ecb  mov     eax, 80040111h
0x180008ed0  jmp     short loc_180008F0C
0x180008ed2  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180008ed9  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180008ee0  mov     [rsp+78h+var_50], rsi
0x180008ee5  mov     r9, rdi; void **
0x180008ee8  mov     [rsp+78h+var_58], rax
0x180008eed  mov     r8, rbp; struct _GUID *
0x180008ef0  mov     [rsp+78h+var_48], 0
0x180008ef8  mov     rdx, r14; struct IUnknown *
0x180008efb  lea     rcx, [rsp+78h+var_58]; this
0x180008f00  call    ?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)
0x180008f05  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180008f0c  add     rsp, 48h
0x180008f10  pop     r15
0x180008f12  pop     r14
0x180008f14  pop     rdi
0x180008f15  pop     rsi
0x180008f16  pop     rbp
0x180008f17  pop     rbx
0x180008f18  retn
```

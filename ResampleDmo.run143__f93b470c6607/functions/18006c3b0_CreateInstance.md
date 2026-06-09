# CreateInstance

- ea: `0x18006c3b0`
- end: `0x18006c448`
- name: `CreateInstance`
- size: `152`
- prototype: `__int64 __fastcall(void *Buf2, struct IUnknown *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800086cc`
- `0x180008f60`
- `0x18006c3b0`
- `0x180084684`

## pseudocode

```c
__int64 __fastcall CreateInstance(void *Buf2, struct IUnknown *a2, struct _GUID *a3, void **a4)
{
  __int64 result; // rax
  int i; // ebx
  const struct CComClassTemplate *v10; // rsi
  _BYTE v11[88]; // [rsp+20h] [rbp-58h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  for ( i = 0; i < 1; ++i )
  {
    v10 = (const struct CComClassTemplate *)(&g_ComClassTemplates + 2 * i);
    if ( !memcmp_0(*(const void **)v10, Buf2, 0x10u) )
    {
      CClassFactory::CClassFactory((CClassFactory *)v11, v10);
      result = CClassFactory::CreateInstance((CClassFactory *)v11, a2, a3, a4);
      _InterlockedDecrement(&g_cActiveObjects);
      return result;
    }
  }
  return 2147746065LL;
}

```

## disassembly

```asm
0x18006c3b0  push    rbx
0x18006c3b2  push    rbp
0x18006c3b3  push    rsi
0x18006c3b4  push    rdi
0x18006c3b5  push    r14
0x18006c3b7  push    r15
0x18006c3b9  sub     rsp, 48h
0x18006c3bd  mov     rdi, r9
0x18006c3c0  mov     rbp, r8
0x18006c3c3  mov     r14, rdx
0x18006c3c6  mov     r15, rcx
0x18006c3c9  test    r9, r9
0x18006c3cc  jnz     short loc_18006C3D5
0x18006c3ce  mov     eax, 80004003h
0x18006c3d3  jmp     short loc_18006C43B
0x18006c3d5  mov     qword ptr [r9], 0
0x18006c3dc  xor     ebx, ebx
0x18006c3de  cmp     ebx, 1
0x18006c3e1  jge     short loc_18006C436
0x18006c3e3  lea     rcx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x18006c3ea  movsxd  rsi, ebx
0x18006c3ed  shl     rsi, 4
0x18006c3f1  mov     r8d, 10h; Size
0x18006c3f7  add     rsi, rcx
0x18006c3fa  mov     rdx, r15; Buf2
0x18006c3fd  mov     rcx, [rsi]; Buf1
0x18006c400  call    memcmp_0
0x18006c405  test    eax, eax
0x18006c407  jz      short loc_18006C40D
0x18006c409  inc     ebx
0x18006c40b  jmp     short loc_18006C3DE
0x18006c40d  mov     rdx, rsi; struct CComClassTemplate *
0x18006c410  lea     rcx, [rsp+78h+var_58]; this
0x18006c415  call    ??0CClassFactory@@QEAA@PEBUCComClassTemplate@@@Z; CClassFactory::CClassFactory(CComClassTemplate const *)
0x18006c41a  mov     r9, rdi; void **
0x18006c41d  lea     rcx, [rsp+78h+var_58]; this
0x18006c422  mov     r8, rbp; struct _GUID *
0x18006c425  mov     rdx, r14; struct IUnknown *
0x18006c428  call    ?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)
0x18006c42d  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18006c434  jmp     short loc_18006C43B
0x18006c436  mov     eax, 80040111h
0x18006c43b  add     rsp, 48h
0x18006c43f  pop     r15
0x18006c441  pop     r14
0x18006c443  pop     rdi
0x18006c444  pop     rsi
0x18006c445  pop     rbp
0x18006c446  pop     rbx
0x18006c447  retn
```

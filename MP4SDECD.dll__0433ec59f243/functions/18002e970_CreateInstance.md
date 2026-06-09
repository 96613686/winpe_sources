# CreateInstance

- ea: `0x18002e970`
- end: `0x18002ea08`
- name: `CreateInstance`
- size: `152`
- prototype: `__int64 __fastcall(void *Buf2, struct IUnknown *, struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180025f38`
- `0x1800278b0`
- `0x18002e970`
- `0x1800457f9`

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
  for ( i = 0; i < 2; ++i )
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
0x18002e970  push    rbx
0x18002e972  push    rbp
0x18002e973  push    rsi
0x18002e974  push    rdi
0x18002e975  push    r14
0x18002e977  push    r15
0x18002e979  sub     rsp, 48h
0x18002e97d  mov     rdi, r9
0x18002e980  mov     rbp, r8
0x18002e983  mov     r14, rdx
0x18002e986  mov     r15, rcx
0x18002e989  test    r9, r9
0x18002e98c  jnz     short loc_18002E995
0x18002e98e  mov     eax, 80004003h
0x18002e993  jmp     short loc_18002E9FB
0x18002e995  mov     qword ptr [r9], 0
0x18002e99c  xor     ebx, ebx
0x18002e99e  cmp     ebx, 2
0x18002e9a1  jge     short loc_18002E9F6
0x18002e9a3  lea     rcx, ?g_ComClassTemplates@@3PAUCComClassTemplate@@A; CComClassTemplate near * g_ComClassTemplates
0x18002e9aa  movsxd  rsi, ebx
0x18002e9ad  shl     rsi, 4
0x18002e9b1  mov     r8d, 10h; Size
0x18002e9b7  add     rsi, rcx
0x18002e9ba  mov     rdx, r15; Buf2
0x18002e9bd  mov     rcx, [rsi]; Buf1
0x18002e9c0  call    memcmp_0
0x18002e9c5  test    eax, eax
0x18002e9c7  jz      short loc_18002E9CD
0x18002e9c9  inc     ebx
0x18002e9cb  jmp     short loc_18002E99E
0x18002e9cd  mov     rdx, rsi; struct CComClassTemplate *
0x18002e9d0  lea     rcx, [rsp+78h+var_58]; this
0x18002e9d5  call    ??0CClassFactory@@QEAA@PEBUCComClassTemplate@@@Z; CClassFactory::CClassFactory(CComClassTemplate const *)
0x18002e9da  mov     r9, rdi; void **
0x18002e9dd  lea     rcx, [rsp+78h+var_58]; this
0x18002e9e2  mov     r8, rbp; struct _GUID *
0x18002e9e5  mov     rdx, r14; struct IUnknown *
0x18002e9e8  call    ?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)
0x18002e9ed  lock dec cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18002e9f4  jmp     short loc_18002E9FB
0x18002e9f6  mov     eax, 80040111h
0x18002e9fb  add     rsp, 48h
0x18002e9ff  pop     r15
0x18002ea01  pop     r14
0x18002ea03  pop     rdi
0x18002ea04  pop     rsi
0x18002ea05  pop     rbp
0x18002ea06  pop     rbx
0x18002ea07  retn
```

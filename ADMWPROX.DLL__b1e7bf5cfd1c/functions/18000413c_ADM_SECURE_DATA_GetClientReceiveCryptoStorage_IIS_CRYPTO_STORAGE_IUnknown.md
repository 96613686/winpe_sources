# ADM_SECURE_DATA::GetClientReceiveCryptoStorage(IIS_CRYPTO_STORAGE * *,IUnknown *)

- ea: `0x18000413c`
- end: `0x1800041a4`
- name: `?GetClientReceiveCryptoStorage@ADM_SECURE_DATA@@QEAAJPEAPEAVIIS_CRYPTO_STORAGE@@PEAUIUnknown@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(ADM_SECURE_DATA *__hidden this, struct IIS_CRYPTO_STORAGE **, struct IUnknown *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800025f0`
- `0x180002850`
- `0x180002c40`

## callees

- `0x180003538`
- `0x18000413c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000415d`
- `KERNEL32!EnterCriticalSection` at `0x18000415d`
- `KERNEL32!LeaveCriticalSection` at `0x18000417e`
- `KERNEL32!LeaveCriticalSection` at `0x18000418b`
- `KERNEL32!LeaveCriticalSection` at `0x18000417e`
- `KERNEL32!LeaveCriticalSection` at `0x18000418b`

## pseudocode

```c
__int64 __fastcall ADM_SECURE_DATA::GetClientReceiveCryptoStorage(
        ADM_SECURE_DATA *this,
        struct IIS_CRYPTO_STORAGE **a2,
        struct IUnknown *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  int v7; // esi

  if ( !*((_QWORD *)this + 4) )
  {
    v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
    if ( !*((_QWORD *)this + 4) )
    {
      v7 = ADM_SECURE_DATA::DoClientSideKeyExchange(this, a3);
      if ( v7 < 0 )
      {
        LeaveCriticalSection(v6);
        return (unsigned int)v7;
      }
    }
    LeaveCriticalSection(v6);
  }
  *a2 = (struct IIS_CRYPTO_STORAGE *)*((_QWORD *)this + 7);
  return 0;
}

```

## disassembly

```asm
0x18000413c  push    rbx
0x18000413e  push    rsi
0x18000413f  push    rdi
0x180004140  push    r14
0x180004142  sub     rsp, 28h
0x180004146  cmp     qword ptr [rcx+20h], 0
0x18000414b  mov     rsi, r8
0x18000414e  mov     r14, rdx
0x180004151  mov     rbx, rcx
0x180004154  jnz     short loc_180004191
0x180004156  lea     rdi, [rcx+40h]
0x18000415a  mov     rcx, rdi; lpCriticalSection
0x18000415d  call    cs:__imp_EnterCriticalSection
0x180004163  cmp     qword ptr [rbx+20h], 0
0x180004168  jnz     short loc_180004188
0x18000416a  mov     rdx, rsi; struct IUnknown *
0x18000416d  mov     rcx, rbx; this
0x180004170  call    ?DoClientSideKeyExchange@ADM_SECURE_DATA@@AEAAJPEAUIUnknown@@@Z; ADM_SECURE_DATA::DoClientSideKeyExchange(IUnknown *)
0x180004175  mov     esi, eax
0x180004177  test    eax, eax
0x180004179  jns     short loc_180004188
0x18000417b  mov     rcx, rdi; lpCriticalSection
0x18000417e  call    cs:__imp_LeaveCriticalSection
0x180004184  mov     eax, esi
0x180004186  jmp     short loc_18000419A
0x180004188  mov     rcx, rdi; lpCriticalSection
0x18000418b  call    cs:__imp_LeaveCriticalSection
0x180004191  mov     rax, [rbx+38h]
0x180004195  mov     [r14], rax
0x180004198  xor     eax, eax
0x18000419a  add     rsp, 28h
0x18000419e  pop     r14
0x1800041a0  pop     rdi
0x1800041a1  pop     rsi
0x1800041a2  pop     rbx
0x1800041a3  retn
```

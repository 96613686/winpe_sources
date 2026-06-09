# ADM_SECURE_DATA::GetCryptoProviderHelper(unsigned __int64 *,unsigned __int64 *,char *,ulong)

- ea: `0x1800041ac`
- end: `0x180004224`
- name: `?GetCryptoProviderHelper@ADM_SECURE_DATA@@AEAAJPEA_K0PEADK@Z`
- size: `120`
- prototype: `int(ADM_SECURE_DATA *__hidden this, unsigned __int64 *, unsigned __int64 *, char *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003538`
- `0x1800039d4`

## callees

- `0x1800041ac`
- `0x18000522c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800041d0`
- `KERNEL32!EnterCriticalSection` at `0x1800041d0`
- `KERNEL32!LeaveCriticalSection` at `0x180004209`
- `KERNEL32!LeaveCriticalSection` at `0x180004209`

## pseudocode

```c
__int64 __fastcall ADM_SECURE_DATA::GetCryptoProviderHelper(
        ADM_SECURE_DATA *this,
        unsigned __int64 *a2,
        unsigned __int64 *a3,
        char *a4,
        unsigned int a5)
{
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  int CryptoContainerByName; // ebx
  int v10; // r9d
  unsigned __int64 v11; // rax
  unsigned __int64 v13; // [rsp+40h] [rbp+8h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 64);
  CryptoContainerByName = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v11 = *a3;
  v13 = v11;
  if ( v11 )
    goto LABEL_4;
  CryptoContainerByName = IIS_CRYPTO_BASE::GetCryptoContainerByName(&v13, a4, a5, v10);
  if ( CryptoContainerByName >= 0 )
  {
    v11 = v13;
LABEL_4:
    *a3 = v11;
    *a2 = v11;
  }
  LeaveCriticalSection(v5);
  return (unsigned int)CryptoContainerByName;
}

```

## disassembly

```asm
0x1800041ac  mov     [rsp+arg_8], rbx
0x1800041b1  mov     [rsp+arg_10], rbp
0x1800041b6  push    rsi
0x1800041b7  push    rdi
0x1800041b8  push    r14
0x1800041ba  sub     rsp, 20h
0x1800041be  lea     rdi, [rcx+40h]
0x1800041c2  mov     rbp, r9
0x1800041c5  mov     rcx, rdi; lpCriticalSection
0x1800041c8  mov     rsi, r8
0x1800041cb  mov     r14, rdx
0x1800041ce  xor     ebx, ebx
0x1800041d0  call    cs:__imp_EnterCriticalSection
0x1800041d6  mov     rax, [rsi]
0x1800041d9  mov     [rsp+38h+arg_0], rax
0x1800041de  test    rax, rax
0x1800041e1  jnz     short loc_180004200
0x1800041e3  mov     r8d, [rsp+38h+arg_20]; unsigned int
0x1800041e8  lea     rcx, [rsp+38h+arg_0]; unsigned __int64 *
0x1800041ed  mov     rdx, rbp; char *
0x1800041f0  call    ?GetCryptoContainerByName@IIS_CRYPTO_BASE@@SAJPEA_KPEADKH@Z; IIS_CRYPTO_BASE::GetCryptoContainerByName(unsigned __int64 *,char *,ulong,int)
0x1800041f5  mov     ebx, eax
0x1800041f7  test    eax, eax
0x1800041f9  js      short loc_180004206
0x1800041fb  mov     rax, [rsp+38h+arg_0]
0x180004200  mov     [rsi], rax
0x180004203  mov     [r14], rax
0x180004206  mov     rcx, rdi; lpCriticalSection
0x180004209  call    cs:__imp_LeaveCriticalSection
0x18000420f  mov     rbp, [rsp+38h+arg_10]
0x180004214  mov     eax, ebx
0x180004216  mov     rbx, [rsp+38h+arg_8]
0x18000421b  add     rsp, 20h
0x18000421f  pop     r14
0x180004221  pop     rdi
0x180004222  pop     rsi
0x180004223  retn
```

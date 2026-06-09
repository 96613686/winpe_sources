# CachedOpenAlgorithmProvider

- ea: `0x180016298`
- end: `0x18001630f`
- name: `CachedOpenAlgorithmProvider`
- size: `119`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180014084`
- `0x180014d6c`
- `0x180016b60`
- `0x180017420`

## callees

- `0x1800070d0`
- `0x180016298`
- `0x180016318`
- `0x18001641c`

## pseudocode

```c
__int64 __fastcall CachedOpenAlgorithmProvider(_QWORD *a1, wchar_t *a2)
{
  NTSTATUS v3; // ebx
  BCRYPT_ALG_HANDLE EntryInCache; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  phAlgorithm = 0;
  EntryInCache = (BCRYPT_ALG_HANDLE)findEntryInCache(a2);
  phAlgorithm = EntryInCache;
  if ( !EntryInCache )
  {
    v3 = BCryptOpenAlgorithmProvider(&phAlgorithm, a2, 0, 0);
    if ( v3 >= 0 )
    {
      addEntryToCache(phAlgorithm, a2);
      EntryInCache = phAlgorithm;
    }
    else
    {
      EntryInCache = 0;
    }
  }
  *a1 = EntryInCache;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016298  mov     rax, rsp
0x18001629b  mov     [rax+8], rbx
0x18001629f  mov     [rax+10h], rsi
0x1800162a3  mov     [rax+18h], r8
0x1800162a7  push    rdi
0x1800162a8  sub     rsp, 20h
0x1800162ac  mov     rsi, rcx
0x1800162af  xor     ebx, ebx
0x1800162b1  mov     rcx, rdx; String1
0x1800162b4  mov     [rax+18h], rbx
0x1800162b8  mov     rdi, rdx
0x1800162bb  call    findEntryInCache
0x1800162c0  mov     [rsp+28h+phAlgorithm], rax
0x1800162c5  test    rax, rax
0x1800162c8  jnz     short loc_1800162F9
0x1800162ca  xor     r9d, r9d; dwFlags
0x1800162cd  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x1800162d2  xor     r8d, r8d; pszImplementation
0x1800162d5  mov     rdx, rdi; pszAlgId
0x1800162d8  call    BCryptOpenAlgorithmProvider
0x1800162dd  mov     ebx, eax
0x1800162df  test    eax, eax
0x1800162e1  jns     short loc_1800162E7
0x1800162e3  xor     eax, eax
0x1800162e5  jmp     short loc_1800162F9
0x1800162e7  mov     rcx, [rsp+28h+phAlgorithm]
0x1800162ec  mov     rdx, rdi
0x1800162ef  call    addEntryToCache
0x1800162f4  mov     rax, [rsp+28h+phAlgorithm]
0x1800162f9  mov     [rsi], rax
0x1800162fc  mov     eax, ebx
0x1800162fe  mov     rbx, [rsp+28h+arg_0]
0x180016303  mov     rsi, [rsp+28h+arg_8]
0x180016308  add     rsp, 20h
0x18001630c  pop     rdi
0x18001630d  retn
```

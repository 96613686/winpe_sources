# COleDataSource::GetCacheEntry(tagFORMATETC *,tagDATADIR)

- ea: `0x1800874d0`
- end: `0x1800875ab`
- name: `?GetCacheEntry@COleDataSource@@IEAAPEAUAFX_DATACACHE_ENTRY@@PEAUtagFORMATETC@@W4tagDATADIR@@@Z`
- size: `219`
- prototype: `struct AFX_DATACACHE_ENTRY *__fastcall(COleDataSource *__hidden this, struct tagFORMATETC *, enum tagDATADIR)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800871f0`
- `0x180087260`
- `0x180087300`
- `0x180087380`
- `0x1800873e0`

## callees

- `0x18000ce50`
- `0x1800874d0`
- `0x1800877b0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180087564`
- `msvcrt!memcpy_s` at `0x180087564`
- `msvcrt!free` at `0x18008756e`
- `msvcrt!free` at `0x18008756e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800874f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800874f7`
- `OLE32!ReleaseStgMedium` at `0x180087501`
- `OLE32!ReleaseStgMedium` at `0x180087501`

## pseudocode

```c
struct AFX_DATACACHE_ENTRY *__fastcall COleDataSource::GetCacheEntry(
        void **this,
        struct tagFORMATETC *a2,
        enum tagDATADIR a3)
{
  struct AFX_DATACACHE_ENTRY *v6; // rax
  struct AFX_DATACACHE_ENTRY *v7; // rbx
  char *v8; // rbp
  _DWORD *v9; // rbx
  _DWORD *v10; // rdi
  char *v11; // rax
  const void *v12; // r8
  int v13; // eax
  struct AFX_DATACACHE_ENTRY *result; // rax

  v6 = COleDataSource::Lookup((COleDataSource *)this, a2, a3);
  v7 = v6;
  if ( v6 )
  {
    CoTaskMemFree(*((LPVOID *)v6 + 1));
    ReleaseStgMedium((LPSTGMEDIUM)((char *)v7 + 32));
  }
  else
  {
    v8 = (char *)this[8];
    v9 = this + 9;
    v10 = (_DWORD *)this + 19;
    if ( !v8 || *v10 == *v9 )
    {
      v11 = (char *)operator new(saturated_mul((unsigned int)(*((_DWORD *)this + 20) + *v9), 0x40u));
      v12 = this[8];
      v8 = v11;
      v13 = *((_DWORD *)this + 20);
      *v9 += v13;
      if ( v12 )
      {
        memcpy_s(v8, (unsigned __int64)(unsigned int)(*v9 + v13) << 6, v12, (unsigned __int64)(unsigned int)*v10 << 6);
        free(this[8]);
      }
      this[8] = v8;
    }
    v7 = (struct AFX_DATACACHE_ENTRY *)&v8[64 * (unsigned __int64)(unsigned int)(*v10)++];
  }
  *((_DWORD *)v7 + 14) = a3;
  result = v7;
  *(_OWORD *)v7 = *(_OWORD *)&a2->cfFormat;
  *((_OWORD *)v7 + 1) = *(_OWORD *)&a2->dwAspect;
  return result;
}

```

## disassembly

```asm
0x1800874d0  push    rbx
0x1800874d2  push    rbp
0x1800874d3  push    rsi
0x1800874d4  push    rdi
0x1800874d5  push    r14
0x1800874d7  push    r15
0x1800874d9  sub     rsp, 28h
0x1800874dd  mov     r15d, r8d
0x1800874e0  mov     r14, rdx
0x1800874e3  mov     rsi, rcx
0x1800874e6  call    ?Lookup@COleDataSource@@IEBAPEAUAFX_DATACACHE_ENTRY@@PEAUtagFORMATETC@@W4tagDATADIR@@@Z; COleDataSource::Lookup(tagFORMATETC *,tagDATADIR)
0x1800874eb  mov     rbx, rax
0x1800874ee  test    rax, rax
0x1800874f1  jz      short loc_180087509
0x1800874f3  mov     rcx, [rax+8]; pv
0x1800874f7  call    cs:__imp_CoTaskMemFree
0x1800874fd  lea     rcx, [rbx+20h]; LPSTGMEDIUM
0x180087501  call    cs:__imp_ReleaseStgMedium
0x180087507  jmp     short loc_180087587
0x180087509  mov     rbp, [rsi+40h]
0x18008750d  lea     rbx, [rsi+48h]
0x180087511  lea     rdi, [rsi+4Ch]
0x180087515  test    rbp, rbp
0x180087518  jz      short loc_180087520
0x18008751a  mov     eax, [rbx]
0x18008751c  cmp     [rdi], eax
0x18008751e  jnz     short loc_180087578
0x180087520  mov     ecx, [rbx]
0x180087522  mov     eax, 40h ; '@'
0x180087527  add     ecx, [rsi+50h]
0x18008752a  mul     rcx
0x18008752d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180087534  cmovb   rax, rcx
0x180087538  mov     rcx, rax; Size
0x18008753b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180087540  mov     r8, [rsi+40h]; Source
0x180087544  mov     rbp, rax
0x180087547  mov     eax, [rsi+50h]
0x18008754a  add     [rbx], eax
0x18008754c  mov     ecx, [rbx]
0x18008754e  test    r8, r8
0x180087551  jz      short loc_180087574
0x180087553  mov     r9d, [rdi]
0x180087556  lea     edx, [rcx+rax]
0x180087559  shl     r9, 6; SourceSize
0x18008755d  mov     rcx, rbp; Destination
0x180087560  shl     rdx, 6; DestinationSize
0x180087564  call    cs:__imp_memcpy_s
0x18008756a  mov     rcx, [rsi+40h]; Block
0x18008756e  call    cs:__imp_free
0x180087574  mov     [rsi+40h], rbp
0x180087578  mov     ecx, [rdi]
0x18008757a  mov     ebx, ecx
0x18008757c  shl     rbx, 6
0x180087580  add     rbx, rbp
0x180087583  inc     ecx
0x180087585  mov     [rdi], ecx
0x180087587  mov     [rbx+38h], r15d
0x18008758b  mov     rax, rbx
0x18008758e  movups  xmm0, xmmword ptr [r14]
0x180087592  movups  xmmword ptr [rbx], xmm0
0x180087595  movups  xmm1, xmmword ptr [r14+10h]
0x18008759a  movups  xmmword ptr [rbx+10h], xmm1
0x18008759e  add     rsp, 28h
0x1800875a2  pop     r15
0x1800875a4  pop     r14
0x1800875a6  pop     rdi
0x1800875a7  pop     rsi
0x1800875a8  pop     rbp
0x1800875a9  pop     rbx
0x1800875aa  retn
```

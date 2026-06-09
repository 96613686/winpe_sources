# ABO_NODE::Initialize(void)

- ea: `0x180001604`
- end: `0x18000168f`
- name: `?Initialize@ABO_NODE@@SAJXZ`
- size: `139`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180001010`

## callees

- `0x180001604`
- `0x180002990`
- `0x180003460`

## import_xrefs

- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180001657`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180001657`

## pseudocode

```c
__int64 ABO_NODE::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  _DWORD v2[4]; // [rsp+20h] [rbp-28h] BYREF

  v2[0] = 1;
  v2[1] = 100;
  v2[2] = 312;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( v0 )
  {
    ABO_NODE::sm_pachAboNodes = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
                                  v0,
                                  "ABO_NODE",
                                  (const struct ALLOC_CACHE_CONFIGURATION *)v2,
                                  1);
    if ( ABO_NODE::sm_pachAboNodes )
    {
      ABO_NODE::sm_pBigRefTrace = 0;
      return 0;
    }
  }
  else
  {
    ABO_NODE::sm_pachAboNodes = 0;
  }
  return 2147942408LL;
}

```

## disassembly

```asm
0x180001604  sub     rsp, 48h
0x180001608  mov     rax, cs:__security_cookie
0x18000160f  xor     rax, rsp
0x180001612  mov     [rsp+48h+var_18], rax
0x180001617  mov     ecx, 100h; Size
0x18000161c  mov     [rsp+48h+var_28], 1
0x180001624  mov     [rsp+48h+var_24], 64h ; 'd'
0x18000162c  mov     [rsp+48h+var_20], 138h
0x180001634  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001639  test    rax, rax
0x18000163c  jz      loc_1800039FA
0x180001642  mov     r9d, 1
0x180001648  lea     r8, [rsp+48h+var_28]
0x18000164d  lea     rdx, aAboNode; "ABO_NODE"
0x180001654  mov     rcx, rax
0x180001657  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x18000165d  mov     cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180001664  test    rax, rax
0x180001667  jz      short loc_180001688
0x180001669  mov     cs:?sm_pBigRefTrace@ABO_NODE@@0PEAVBIG_REF_TRACE@@EA, 0; BIG_REF_TRACE * ABO_NODE::sm_pBigRefTrace
0x180001674  xor     eax, eax
0x180001676  mov     rcx, [rsp+48h+var_18]
0x18000167b  xor     rcx, rsp; StackCookie
0x18000167e  call    __security_check_cookie
0x180001683  add     rsp, 48h
0x180001687  retn
0x180001688  mov     eax, 80070008h
0x18000168d  jmp     short loc_180001676
0x1800039fa  mov     cs:?sm_pachAboNodes@ABO_NODE@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * ABO_NODE::sm_pachAboNodes
0x180003a05  jmp     loc_180001688
```

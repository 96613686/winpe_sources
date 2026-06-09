# DIGEST_CONTEXT_CACHE_ENTRY::Initialize(void)

- ea: `0x180004b1c`
- end: `0x180004bf9`
- name: `?Initialize@DIGEST_CONTEXT_CACHE_ENTRY@@SAJXZ`
- size: `221`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800042d0`

## callees

- `0x180001024`
- `0x180001064`
- `0x180004b1c`
- `0x180006600`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180004bde`
- `iisutil!PuDbgPrint` at `0x180004bde`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180004b6b`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180004b6b`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180004b8c`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180004b8c`

## string_xrefs

- `0x180004b61`: `DIGEST_CONTEXT_CACHE_ENTRY`
- `0x180004bb3`: `Error initializing sm_pachDigestContextCacheEntry. hr = 0x%x\n`
- `0x180004bc3`: `DIGEST_CONTEXT_CACHE_ENTRY::Initialize`
- `0x180004bd1`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\digest_auth\digestcontextcache.cxx`

## pseudocode

```c
__int64 DIGEST_CONTEXT_CACHE_ENTRY::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  ALLOC_CACHE_HANDLER *v1; // rax
  ALLOC_CACHE_HANDLER *v2; // rbx
  _DWORD v4[4]; // [rsp+30h] [rbp-28h] BYREF

  v4[1] = 100;
  v4[0] = 1;
  v4[2] = 48;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( !v0 )
  {
LABEL_6:
    DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry = 0;
    goto LABEL_7;
  }
  v1 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
         v0,
         "DIGEST_CONTEXT_CACHE_ENTRY",
         (const struct ALLOC_CACHE_CONFIGURATION *)v4,
         1);
  DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry = v1;
  v2 = v1;
  if ( v1 )
  {
    if ( *(_DWORD *)v1 )
      return 0;
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(v1);
    operator delete(v2);
    goto LABEL_6;
  }
LABEL_7:
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\digest_auth\\digestcontextcache.cxx",
      77,
      "DIGEST_CONTEXT_CACHE_ENTRY::Initialize",
      "Error initializing sm_pachDigestContextCacheEntry. hr = 0x%x\n",
      -2147024888);
  return 2147942408LL;
}

```

## disassembly

```asm
0x180004b1c  push    rbx
0x180004b1e  sub     rsp, 50h
0x180004b22  mov     rax, cs:__security_cookie
0x180004b29  xor     rax, rsp
0x180004b2c  mov     [rsp+58h+var_18], rax
0x180004b31  mov     ebx, 1
0x180004b36  mov     [rsp+58h+var_24], 64h ; 'd'
0x180004b3e  mov     ecx, 100h; Size
0x180004b43  mov     [rsp+58h+var_28], ebx
0x180004b47  mov     [rsp+58h+var_20], 30h ; '0'
0x180004b4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004b54  test    rax, rax
0x180004b57  jz      short loc_180004B9A
0x180004b59  mov     r9d, ebx
0x180004b5c  lea     r8, [rsp+58h+var_28]
0x180004b61  lea     rdx, aDigestContextC_1; "DIGEST_CONTEXT_CACHE_ENTRY"
0x180004b68  mov     rcx, rax
0x180004b6b  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180004b71  mov     cs:?sm_pachDigestContextCacheEntry@DIGEST_CONTEXT_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry
0x180004b78  mov     rbx, rax
0x180004b7b  test    rax, rax
0x180004b7e  jz      short loc_180004BA5
0x180004b80  cmp     dword ptr [rax], 0
0x180004b83  jz      short loc_180004B89
0x180004b85  xor     eax, eax
0x180004b87  jmp     short loc_180004BE6
0x180004b89  mov     rcx, rbx
0x180004b8c  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180004b92  mov     rcx, rbx; Block
0x180004b95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004b9a  mov     cs:?sm_pachDigestContextCacheEntry@DIGEST_CONTEXT_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * DIGEST_CONTEXT_CACHE_ENTRY::sm_pachDigestContextCacheEntry
0x180004ba5  test    byte ptr cs:g_dwDebugFlags, 3
0x180004bac  mov     ebx, 80070008h
0x180004bb1  jz      short loc_180004BE4
0x180004bb3  lea     rcx, aErrorInitializ_0; "Error initializing sm_pachDigestContext"...
0x180004bba  mov     [rsp+58h+var_30], ebx
0x180004bbe  mov     [rsp+58h+var_38], rcx
0x180004bc3  lea     r9, aDigestContextC_0; "DIGEST_CONTEXT_CACHE_ENTRY::Initialize"
0x180004bca  mov     rcx, cs:g_pDebug
0x180004bd1  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004bd8  mov     r8d, 4Dh ; 'M'
0x180004bde  call    cs:__imp_PuDbgPrint
0x180004be4  mov     eax, ebx
0x180004be6  mov     rcx, [rsp+58h+var_18]
0x180004beb  xor     rcx, rsp; StackCookie
0x180004bee  call    __security_check_cookie
0x180004bf3  add     rsp, 50h
0x180004bf7  pop     rbx
0x180004bf8  retn
```

# SSPI_SECURITY_CONTEXT::Initialize(void)

- ea: `0x18000839c`
- end: `0x180008479`
- name: `?Initialize@SSPI_SECURITY_CONTEXT@@SAJXZ`
- size: `221`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005be0`

## callees

- `0x180001024`
- `0x180001064`
- `0x18000839c`
- `0x180008ba0`

## import_xrefs

- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000840c`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x18000840c`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x1800083eb`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x1800083eb`
- `iisutil!PuDbgPrint` at `0x18000845e`
- `iisutil!PuDbgPrint` at `0x18000845e`

## string_xrefs

- `0x180008451`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\sspi_lib\sspi_lib.cxx`
- `0x1800083e1`: `SSPI_SECURITY_CONTEXT`
- `0x180008443`: `SSPI_SECURITY_CONTEXT::Initialize`

## pseudocode

```c
__int64 SSPI_SECURITY_CONTEXT::Initialize(void)
{
  ALLOC_CACHE_HANDLER *v0; // rax
  ALLOC_CACHE_HANDLER *v1; // rax
  ALLOC_CACHE_HANDLER *v2; // rbx
  _DWORD v4[4]; // [rsp+30h] [rbp-28h] BYREF

  v4[1] = 100;
  v4[0] = 1;
  v4[2] = 64;
  v0 = (ALLOC_CACHE_HANDLER *)operator new(0x100u);
  if ( !v0 )
  {
LABEL_6:
    SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext = 0;
    goto LABEL_7;
  }
  v1 = ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(
         v0,
         "SSPI_SECURITY_CONTEXT",
         (const struct ALLOC_CACHE_CONFIGURATION *)v4,
         1);
  SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext = v1;
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
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\sspi_lib\\sspi_lib.cxx",
      546,
      "SSPI_SECURITY_CONTEXT::Initialize",
      "Error initializing sm_pachSSPISecContext. hr = 0x%x\n",
      -2147024888);
  return 2147942408LL;
}

```

## disassembly

```asm
0x18000839c  push    rbx
0x18000839e  sub     rsp, 50h
0x1800083a2  mov     rax, cs:__security_cookie
0x1800083a9  xor     rax, rsp
0x1800083ac  mov     [rsp+58h+var_18], rax
0x1800083b1  mov     ebx, 1
0x1800083b6  mov     [rsp+58h+var_24], 64h ; 'd'
0x1800083be  mov     ecx, 100h; Size
0x1800083c3  mov     [rsp+58h+var_28], ebx
0x1800083c7  mov     [rsp+58h+var_20], 40h ; '@'
0x1800083cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800083d4  test    rax, rax
0x1800083d7  jz      short loc_18000841A
0x1800083d9  mov     r9d, ebx
0x1800083dc  lea     r8, [rsp+58h+var_28]
0x1800083e1  lea     rdx, aSspiSecurityCo_0; "SSPI_SECURITY_CONTEXT"
0x1800083e8  mov     rcx, rax
0x1800083eb  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x1800083f1  mov     cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x1800083f8  mov     rbx, rax
0x1800083fb  test    rax, rax
0x1800083fe  jz      short loc_180008425
0x180008400  cmp     dword ptr [rax], 0
0x180008403  jz      short loc_180008409
0x180008405  xor     eax, eax
0x180008407  jmp     short loc_180008466
0x180008409  mov     rcx, rbx
0x18000840c  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180008412  mov     rcx, rbx; Block
0x180008415  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000841a  mov     cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180008425  test    byte ptr cs:g_dwDebugFlags, 3
0x18000842c  mov     ebx, 80070008h
0x180008431  jz      short loc_180008464
0x180008433  lea     rcx, aErrorInitializ; "Error initializing sm_pachSSPISecContex"...
0x18000843a  mov     [rsp+58h+var_30], ebx
0x18000843e  mov     [rsp+58h+var_38], rcx
0x180008443  lea     r9, aSspiSecurityCo; "SSPI_SECURITY_CONTEXT::Initialize"
0x18000844a  mov     rcx, cs:g_pDebug
0x180008451  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008458  mov     r8d, 222h
0x18000845e  call    cs:__imp_PuDbgPrint
0x180008464  mov     eax, ebx
0x180008466  mov     rcx, [rsp+58h+var_18]
0x18000846b  xor     rcx, rsp; StackCookie
0x18000846e  call    __security_check_cookie
0x180008473  add     rsp, 50h
0x180008477  pop     rbx
0x180008478  retn
```

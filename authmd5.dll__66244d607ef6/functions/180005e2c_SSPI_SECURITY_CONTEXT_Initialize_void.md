# SSPI_SECURITY_CONTEXT::Initialize(void)

- ea: `0x180005e2c`
- end: `0x180005f09`
- name: `?Initialize@SSPI_SECURITY_CONTEXT@@SAJXZ`
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
- `0x180005e2c`
- `0x180006600`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180005eee`
- `iisutil!PuDbgPrint` at `0x180005eee`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180005e7b`
- `iisutil!??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z` at `0x180005e7b`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180005e9c`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180005e9c`

## string_xrefs

- `0x180005ee1`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\sspi_lib\sspi_lib.cxx`
- `0x180005e71`: `SSPI_SECURITY_CONTEXT`
- `0x180005ed3`: `SSPI_SECURITY_CONTEXT::Initialize`

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
0x180005e2c  push    rbx
0x180005e2e  sub     rsp, 50h
0x180005e32  mov     rax, cs:__security_cookie
0x180005e39  xor     rax, rsp
0x180005e3c  mov     [rsp+58h+var_18], rax
0x180005e41  mov     ebx, 1
0x180005e46  mov     [rsp+58h+var_24], 64h ; 'd'
0x180005e4e  mov     ecx, 100h; Size
0x180005e53  mov     [rsp+58h+var_28], ebx
0x180005e57  mov     [rsp+58h+var_20], 40h ; '@'
0x180005e5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005e64  test    rax, rax
0x180005e67  jz      short loc_180005EAA
0x180005e69  mov     r9d, ebx
0x180005e6c  lea     r8, [rsp+58h+var_28]
0x180005e71  lea     rdx, aSspiSecurityCo_0; "SSPI_SECURITY_CONTEXT"
0x180005e78  mov     rcx, rax
0x180005e7b  call    cs:__imp_??0ALLOC_CACHE_HANDLER@@QEAA@PEBDPEBUALLOC_CACHE_CONFIGURATION@@H@Z; ALLOC_CACHE_HANDLER::ALLOC_CACHE_HANDLER(char const *,ALLOC_CACHE_CONFIGURATION const *,int)
0x180005e81  mov     cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, rax; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180005e88  mov     rbx, rax
0x180005e8b  test    rax, rax
0x180005e8e  jz      short loc_180005EB5
0x180005e90  cmp     dword ptr [rax], 0
0x180005e93  jz      short loc_180005E99
0x180005e95  xor     eax, eax
0x180005e97  jmp     short loc_180005EF6
0x180005e99  mov     rcx, rbx
0x180005e9c  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x180005ea2  mov     rcx, rbx; Block
0x180005ea5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005eaa  mov     cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180005eb5  test    byte ptr cs:g_dwDebugFlags, 3
0x180005ebc  mov     ebx, 80070008h
0x180005ec1  jz      short loc_180005EF4
0x180005ec3  lea     rcx, aErrorInitializ; "Error initializing sm_pachSSPISecContex"...
0x180005eca  mov     [rsp+58h+var_30], ebx
0x180005ece  mov     [rsp+58h+var_38], rcx
0x180005ed3  lea     r9, aSspiSecurityCo; "SSPI_SECURITY_CONTEXT::Initialize"
0x180005eda  mov     rcx, cs:g_pDebug
0x180005ee1  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005ee8  mov     r8d, 222h
0x180005eee  call    cs:__imp_PuDbgPrint
0x180005ef4  mov     eax, ebx
0x180005ef6  mov     rcx, [rsp+58h+var_18]
0x180005efb  xor     rcx, rsp; StackCookie
0x180005efe  call    __security_check_cookie
0x180005f03  add     rsp, 50h
0x180005f07  pop     rbx
0x180005f08  retn
```

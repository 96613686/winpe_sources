# CIISModuleFactory::Terminate(void)

- ea: `0x180006120`
- end: `0x1800061fd`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `221`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001064`
- `0x180001c34`
- `0x180006120`
- `0x180008538`

## import_xrefs

- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180006158`
- `iisutil!??1ALLOC_CACHE_HANDLER@@QEAA@XZ` at `0x180006158`
- `iisutil!PuDeleteDebugPrintsObject` at `0x1800061cd`
- `iisutil!PuDeleteDebugPrintsObject` at `0x1800061cd`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  void *v2; // rbx
  KERBEROS_INFO *v3; // rbx

  if ( s_pSSPIAuthProvider )
  {
    operator delete(s_pSSPIAuthProvider);
    s_pSSPIAuthProvider = 0;
  }
  v2 = SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext;
  if ( SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext )
  {
    ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER((ALLOC_CACHE_HANDLER *)SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext);
    operator delete(v2);
  }
  SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext = 0;
  SSPI_CREDENTIAL::Terminate();
  v3 = KERBEROS_INFO::sm_pKerberosInfo;
  if ( KERBEROS_INFO::sm_pKerberosInfo )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)KERBEROS_INFO::sm_pKerberosInfo, 0xFFFFFFFF) == 1 && v3 )
    {
      KERBEROS_INFO::~KERBEROS_INFO(v3);
      operator delete(v3);
    }
    KERBEROS_INFO::sm_pKerberosInfo = 0;
    KERBEROS_INFO::sm_State = 0;
  }
  if ( g_pDebug && *(_DWORD *)(g_pDebug + 640) )
    g_pDebug = PuDeleteDebugPrintsObject();
  if ( this )
  {
    *((_QWORD *)this + 1) = &CHttpModule::`vftable';
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180006120  mov     [rsp+arg_0], rbx
0x180006125  push    rdi
0x180006126  sub     rsp, 20h
0x18000612a  mov     rdi, rcx
0x18000612d  mov     rcx, cs:?s_pSSPIAuthProvider@@3PEAVSSPI_AUTH_PROVIDER@@EA; Block
0x180006134  test    rcx, rcx
0x180006137  jz      short loc_180006149
0x180006139  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000613e  mov     cs:?s_pSSPIAuthProvider@@3PEAVSSPI_AUTH_PROVIDER@@EA, 0; SSPI_AUTH_PROVIDER * s_pSSPIAuthProvider
0x180006149  mov     rbx, cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180006150  test    rbx, rbx
0x180006153  jz      short loc_180006166
0x180006155  mov     rcx, rbx
0x180006158  call    cs:__imp_??1ALLOC_CACHE_HANDLER@@QEAA@XZ; ALLOC_CACHE_HANDLER::~ALLOC_CACHE_HANDLER(void)
0x18000615e  mov     rcx, rbx; Block
0x180006161  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006166  mov     cs:?sm_pachSSPISecContext@SSPI_SECURITY_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA, 0; ALLOC_CACHE_HANDLER * SSPI_SECURITY_CONTEXT::sm_pachSSPISecContext
0x180006171  call    ?Terminate@SSPI_CREDENTIAL@@SAXXZ; SSPI_CREDENTIAL::Terminate(void)
0x180006176  mov     rbx, cs:?sm_pKerberosInfo@KERBEROS_INFO@@0PEAV1@EA; KERBEROS_INFO * KERBEROS_INFO::sm_pKerberosInfo
0x18000617d  test    rbx, rbx
0x180006180  jz      short loc_1800061B8
0x180006182  or      eax, 0FFFFFFFFh
0x180006185  lock xadd [rbx], eax
0x180006189  cmp     eax, 1
0x18000618c  jnz     short loc_1800061A3
0x18000618e  test    rbx, rbx
0x180006191  jz      short loc_1800061A3
0x180006193  mov     rcx, rbx; this
0x180006196  call    ??1KERBEROS_INFO@@QEAA@XZ; KERBEROS_INFO::~KERBEROS_INFO(void)
0x18000619b  mov     rcx, rbx; Block
0x18000619e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800061a3  mov     cs:?sm_pKerberosInfo@KERBEROS_INFO@@0PEAV1@EA, 0; KERBEROS_INFO * KERBEROS_INFO::sm_pKerberosInfo
0x1800061ae  mov     cs:?sm_State@KERBEROS_INFO@@0JA, 0; long KERBEROS_INFO::sm_State
0x1800061b8  mov     rcx, cs:g_pDebug
0x1800061bf  test    rcx, rcx
0x1800061c2  jz      short loc_1800061DA
0x1800061c4  cmp     dword ptr [rcx+280h], 0
0x1800061cb  jz      short loc_1800061DA
0x1800061cd  call    cs:__imp_PuDeleteDebugPrintsObject
0x1800061d3  mov     cs:g_pDebug, rax
0x1800061da  test    rdi, rdi
0x1800061dd  jz      short loc_1800061F2
0x1800061df  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x1800061e6  mov     rcx, rdi; Block
0x1800061e9  mov     [rdi+8], rax
0x1800061ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800061f2  mov     rbx, [rsp+28h+arg_0]
0x1800061f7  add     rsp, 20h
0x1800061fb  pop     rdi
0x1800061fc  retn
```

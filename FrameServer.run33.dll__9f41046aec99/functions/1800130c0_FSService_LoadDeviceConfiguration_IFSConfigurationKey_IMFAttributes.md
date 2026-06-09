# FSService::LoadDeviceConfiguration(IFSConfigurationKey *,IMFAttributes * *)

- ea: `0x1800130c0`
- end: `0x1800132ac`
- name: `?LoadDeviceConfiguration@FSService@@UEAAJPEAUIFSConfigurationKey@@PEAPEAUIMFAttributes@@@Z`
- size: `492`
- prototype: `int(FSService *__hidden this, struct IFSConfigurationKey *, struct IMFAttributes **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x1800130c0`
- `0x180032fb4`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800131b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800131c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800131b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800131c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013163`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013163`
- `MFPlat!MFCreateAttributes` at `0x18001322d`
- `MFPlat!MFCreateAttributes` at `0x18001322d`

## pseudocode

```c
__int64 __fastcall FSService::LoadDeviceConfiguration(
        FSService *this,
        struct IFSConfigurationKey *a2,
        struct IMFAttributes **a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  struct _RTL_CRITICAL_SECTION *v8; // r14
  HRESULT v9; // eax
  __int64 v10; // rdx
  UINT32 v11; // ebx
  struct IFSConfiguration *v13[2]; // [rsp+30h] [rbp-10h] BYREF
  UINT32 cInitialSize; // [rsp+68h] [rbp+28h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+78h] [rbp+38h] BYREF

  cInitialSize = 0;
  v13[0] = 0;
  ppMFAttributes = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( g_wppLevels )
    {
      v7 = 309;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, v6);
      goto LABEL_27;
    }
    goto LABEL_27;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    if ( g_wppLevels )
    {
      v7 = 310;
      goto LABEL_4;
    }
    goto LABEL_27;
  }
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1144);
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1144));
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(v13);
  v6 = FSLoadDeviceConfiguration(a2, v13);
  if ( v6 == -1072875819 )
  {
    if ( g_wppLevels >= 8u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        311,
        &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids,
        this,
        -1072875819);
    LeaveCriticalSection(v8);
    goto LABEL_27;
  }
  LeaveCriticalSection(v8);
  if ( v6 < 0 )
  {
    if ( g_wppLevels )
    {
      v7 = 312;
      goto LABEL_4;
    }
    goto LABEL_27;
  }
  v9 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, UINT32 *))(*(_QWORD *)v13[0] + 240LL))(
         v13[0],
         &cInitialSize);
  v6 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_27;
    v10 = 313;
LABEL_19:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids, this, v9);
    goto LABEL_27;
  }
  v11 = cInitialSize;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v9 = MFCreateAttributes(&ppMFAttributes, v11);
  v6 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_27;
    v10 = 314;
    goto LABEL_19;
  }
  v9 = (*(__int64 (__fastcall **)(struct IFSConfiguration *, IMFAttributes *))(*(_QWORD *)v13[0] + 256LL))(
         v13[0],
         ppMFAttributes);
  v6 = v9;
  if ( v9 >= 0 )
  {
    *a3 = ppMFAttributes;
    ppMFAttributes = 0;
    goto LABEL_27;
  }
  if ( g_wppLevels )
  {
    v10 = 315;
    goto LABEL_19;
  }
LABEL_27:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v13);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800130c0  mov     [rsp-18h+arg_0], rbx
0x1800130c5  mov     [rsp-18h+arg_10], rsi
0x1800130ca  push    rbp
0x1800130cb  push    rdi
0x1800130cc  push    r14
0x1800130ce  mov     rbp, rsp
0x1800130d1  sub     rsp, 40h
0x1800130d5  mov     [rbp+cInitialSize], 0
0x1800130dc  mov     rsi, r8
0x1800130df  mov     [rbp+var_10], 0
0x1800130e7  mov     rbx, rdx
0x1800130ea  mov     [rbp+ppMFAttributes], 0
0x1800130f2  mov     rdi, rcx
0x1800130f5  test    rdx, rdx
0x1800130f8  jnz     short loc_180013134
0x1800130fa  mov     ebx, 80070057h
0x1800130ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013106  jb      loc_180013285
0x18001310c  mov     edx, 135h
0x180013111  mov     [rsp+40h+var_20], ebx
0x180013115  mov     rcx, cs:WPP_GLOBAL_Control
0x18001311c  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x180013123  mov     r9, rdi
0x180013126  mov     rcx, [rcx+10h]
0x18001312a  call    WPP_SF_qD
0x18001312f  jmp     loc_180013285
0x180013134  test    rsi, rsi
0x180013137  jnz     short loc_180013152
0x180013139  mov     ebx, 80004003h
0x18001313e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013145  jb      loc_180013285
0x18001314b  mov     edx, 136h
0x180013150  jmp     short loc_180013111
0x180013152  lea     r14, [rcx+478h]
0x180013159  mov     qword ptr [r8], 0
0x180013160  mov     rcx, r14; lpCriticalSection
0x180013163  call    cs:__imp_EnterCriticalSection
0x180013169  lea     rcx, [rbp+var_10]
0x18001316d  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180013172  lea     rdx, [rbp+var_10]; struct IFSConfiguration **
0x180013176  mov     rcx, rbx; struct IFSConfigurationKey *
0x180013179  call    FSLoadDeviceConfiguration
0x18001317e  mov     ebx, eax
0x180013180  mov     eax, 0C00D36D5h
0x180013185  cmp     ebx, eax
0x180013187  jnz     short loc_1800131C3
0x180013189  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 8; MFWppLevels g_wppLevels
0x180013190  jb      short loc_1800131B5
0x180013192  mov     rcx, cs:WPP_GLOBAL_Control
0x180013199  lea     r8, WPP_bf8eb6dcf9f335b58edb5d8e4205d4fb_Traceguids
0x1800131a0  mov     edx, 137h
0x1800131a5  mov     [rsp+40h+var_20], eax
0x1800131a9  mov     r9, rdi
0x1800131ac  mov     rcx, [rcx+10h]
0x1800131b0  call    WPP_SF_qD
0x1800131b5  mov     rcx, r14; lpCriticalSection
0x1800131b8  call    cs:__imp_LeaveCriticalSection
0x1800131be  jmp     loc_180013285
0x1800131c3  mov     rcx, r14; lpCriticalSection
0x1800131c6  call    cs:__imp_LeaveCriticalSection
0x1800131cc  test    ebx, ebx
0x1800131ce  jns     short loc_1800131E7
0x1800131d0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800131d7  jb      loc_180013285
0x1800131dd  mov     edx, 138h
0x1800131e2  jmp     loc_180013111
0x1800131e7  mov     rcx, [rbp+var_10]
0x1800131eb  lea     rdx, [rbp+cInitialSize]
0x1800131ef  mov     rax, [rcx]
0x1800131f2  mov     rax, [rax+0F0h]
0x1800131f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131fe  mov     ebx, eax
0x180013200  test    eax, eax
0x180013202  jns     short loc_18001321B
0x180013204  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001320b  jb      short loc_180013285
0x18001320d  mov     edx, 139h
0x180013212  mov     [rsp+40h+var_20], eax
0x180013216  jmp     loc_180013115
0x18001321b  mov     ebx, [rbp+cInitialSize]
0x18001321e  lea     rcx, [rbp+ppMFAttributes]
0x180013222  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180013227  mov     edx, ebx; cInitialSize
0x180013229  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18001322d  call    cs:__imp_MFCreateAttributes
0x180013233  mov     ebx, eax
0x180013235  test    eax, eax
0x180013237  jns     short loc_180013249
0x180013239  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013240  jb      short loc_180013285
0x180013242  mov     edx, 13Ah
0x180013247  jmp     short loc_180013212
0x180013249  mov     rcx, [rbp+var_10]
0x18001324d  mov     rdx, [rbp+ppMFAttributes]
0x180013251  mov     rax, [rcx]
0x180013254  mov     rax, [rax+100h]
0x18001325b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013260  mov     ebx, eax
0x180013262  test    eax, eax
0x180013264  jns     short loc_180013276
0x180013266  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001326d  jb      short loc_180013285
0x18001326f  mov     edx, 13Bh
0x180013274  jmp     short loc_180013212
0x180013276  mov     rax, [rbp+ppMFAttributes]
0x18001327a  mov     [rsi], rax
0x18001327d  mov     [rbp+ppMFAttributes], 0
0x180013285  lea     rcx, [rbp+ppMFAttributes]; void *
0x180013289  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18001328e  lea     rcx, [rbp+var_10]; void *
0x180013292  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180013297  mov     rsi, [rsp+40h+arg_10]
0x18001329c  mov     eax, ebx
0x18001329e  mov     rbx, [rsp+40h+arg_0]
0x1800132a3  add     rsp, 40h
0x1800132a7  pop     r14
0x1800132a9  pop     rdi
0x1800132aa  pop     rbp
0x1800132ab  retn
```

# FSToastManager::PostToastNotification(__MIDL___MIDL_itf_fsserviceapi_0000_0000_0006,IDeviceAccessHandler *,ulong,long)

- ea: `0x18004b830`
- end: `0x18004ba0d`
- name: `?PostToastNotification@FSToastManager@@UEAAJW4__MIDL___MIDL_itf_fsserviceapi_0000_0000_0006@@PEAUIDeviceAccessHandler@@KJ@Z`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003e20`
- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x18004b830`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b9e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b9e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b890`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b890`
- `MFPlat!MFPutWorkItem` at `0x18004b96c`
- `MFPlat!MFPutWorkItem` at `0x18004b96c`
- `MFPlat!MFCreateAttributes` at `0x18004b8cd`
- `MFPlat!MFCreateAttributes` at `0x18004b8cd`

## pseudocode

```c
__int64 __fastcall FSToastManager::PostToastNotification(__int64 a1, int a2, __int64 a3, unsigned int a4, int a5)
{
  __int64 v5; // r15
  unsigned int v9; // ebx
  HRESULT v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  IMFAttributes *ppMFAttributes; // [rsp+30h] [rbp-38h] BYREF
  _DWORD v15[2]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-28h]
  int v17; // [rsp+48h] [rbp-20h]
  int v18; // [rsp+4Ch] [rbp-1Ch]

  v5 = a4;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 22, &WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids, a1);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v15[0] = a2;
  v15[1] = 0;
  v9 = 0;
  v17 = a5;
  ppMFAttributes = 0;
  v16 = v5;
  v18 = 0;
  if ( !*(_BYTE *)(a1 + 64) )
  {
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
    v10 = MFCreateAttributes(&ppMFAttributes, 2u);
    v9 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_17;
      v11 = 23;
      goto LABEL_16;
    }
    v10 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUnknown)(
            ppMFAttributes,
            MF_FSTOAST_DEVICEACCESS_HANDLER,
            a3);
    v9 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_17;
      v11 = 24;
      goto LABEL_16;
    }
    v10 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _DWORD *, __int64))ppMFAttributes->lpVtbl->SetBlob)(
            ppMFAttributes,
            MF_FSTOAST_DATA,
            v15,
            24);
    v9 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_17;
      v11 = 25;
      goto LABEL_16;
    }
    v10 = MFPutWorkItem(*(_DWORD *)(a1 + 84), (IMFAsyncCallback *)(a1 + 8), (IUnknown *)ppMFAttributes);
    v9 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_17;
      v11 = 26;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids, a1, v10);
LABEL_17:
      if ( byte_18010EC4D )
      {
        v12 = 27;
LABEL_21:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v12, &WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids, a1, v9);
        goto LABEL_22;
      }
      goto LABEL_22;
    }
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v12 = 28;
    goto LABEL_21;
  }
LABEL_22:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  return v9;
}

```

## disassembly

```asm
0x18004b830  push    rbp
0x18004b832  push    rbx
0x18004b833  push    rsi
0x18004b834  push    rdi
0x18004b835  push    r12
0x18004b837  push    r13
0x18004b839  push    r14
0x18004b83b  push    r15
0x18004b83d  mov     rbp, rsp
0x18004b840  sub     rsp, 68h
0x18004b844  mov     rax, cs:__security_cookie
0x18004b84b  xor     rax, rsp
0x18004b84e  mov     [rbp+var_18], rax
0x18004b852  mov     r15d, r9d
0x18004b855  mov     r12, r8
0x18004b858  mov     r14d, edx
0x18004b85b  mov     rdi, rcx
0x18004b85e  cmp     cs:byte_18010EC4D, 8
0x18004b865  lea     r13, WPP_307ce710a78a3badfb5c6e7ffbaf2fc8_Traceguids
0x18004b86c  jb      short loc_18004B88C
0x18004b86e  mov     r9, rcx
0x18004b871  mov     edx, 16h
0x18004b876  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b87d  mov     r8, r13
0x18004b880  mov     rcx, [rcx+0D8h]
0x18004b887  call    WPP_SF_q
0x18004b88c  lea     rcx, [rdi+18h]; lpCriticalSection
0x18004b890  call    cs:__imp_EnterCriticalSection
0x18004b896  xor     eax, eax
0x18004b898  mov     [rbp+var_30], r14d
0x18004b89c  mov     [rbp+var_2C], eax
0x18004b89f  xor     ebx, ebx
0x18004b8a1  mov     eax, [rbp+arg_20]
0x18004b8a4  mov     [rbp+var_20], eax
0x18004b8a7  xor     eax, eax
0x18004b8a9  mov     [rbp+ppMFAttributes], rbx
0x18004b8ad  mov     [rbp+var_28], r15
0x18004b8b1  mov     [rbp+var_1C], eax
0x18004b8b4  cmp     [rdi+40h], al
0x18004b8b7  jnz     loc_18004B9B0
0x18004b8bd  lea     rcx, [rbp+ppMFAttributes]
0x18004b8c1  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18004b8c6  lea     edx, [rbx+2]; cInitialSize
0x18004b8c9  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18004b8cd  call    cs:__imp_MFCreateAttributes
0x18004b8d3  mov     ebx, eax
0x18004b8d5  test    eax, eax
0x18004b8d7  jns     short loc_18004B8F0
0x18004b8d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b8e0  jb      loc_18004B9A0
0x18004b8e6  mov     edx, 17h
0x18004b8eb  jmp     loc_18004B986
0x18004b8f0  mov     rcx, [rbp+ppMFAttributes]
0x18004b8f4  lea     rdx, MF_FSTOAST_DEVICEACCESS_HANDLER
0x18004b8fb  mov     r8, r12
0x18004b8fe  mov     rax, [rcx]
0x18004b901  mov     rax, [rax+0D8h]
0x18004b908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b90d  mov     ebx, eax
0x18004b90f  test    eax, eax
0x18004b911  jns     short loc_18004B927
0x18004b913  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b91a  jb      loc_18004B9A0
0x18004b920  mov     edx, 18h
0x18004b925  jmp     short loc_18004B986
0x18004b927  mov     rcx, [rbp+ppMFAttributes]
0x18004b92b  lea     r8, [rbp+var_30]
0x18004b92f  mov     r9d, 18h
0x18004b935  lea     rdx, MF_FSTOAST_DATA
0x18004b93c  mov     rax, [rcx]
0x18004b93f  mov     rax, [rax+0D0h]
0x18004b946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b94b  mov     ebx, eax
0x18004b94d  test    eax, eax
0x18004b94f  jns     short loc_18004B961
0x18004b951  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b958  jb      short loc_18004B9A0
0x18004b95a  mov     edx, 19h
0x18004b95f  jmp     short loc_18004B986
0x18004b961  mov     r8, [rbp+ppMFAttributes]; pState
0x18004b965  lea     rdx, [rdi+8]; pCallback
0x18004b969  mov     ecx, [rdi+54h]; dwQueue
0x18004b96c  call    cs:__imp_MFPutWorkItem
0x18004b972  mov     ebx, eax
0x18004b974  test    eax, eax
0x18004b976  jns     short loc_18004B9B0
0x18004b978  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004b97f  jb      short loc_18004B9A0
0x18004b981  mov     edx, 1Ah
0x18004b986  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b98d  mov     r9, rdi
0x18004b990  mov     r8, r13
0x18004b993  mov     [rsp+68h+var_48], eax
0x18004b997  mov     rcx, [rcx+10h]
0x18004b99b  call    WPP_SF_qD
0x18004b9a0  cmp     cs:byte_18010EC4D, 1
0x18004b9a7  jb      short loc_18004B9DB
0x18004b9a9  mov     edx, 1Bh
0x18004b9ae  jmp     short loc_18004B9BE
0x18004b9b0  cmp     cs:byte_18010EC4D, 8
0x18004b9b7  jb      short loc_18004B9DB
0x18004b9b9  mov     edx, 1Ch
0x18004b9be  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b9c5  mov     r9, rdi
0x18004b9c8  mov     r8, r13
0x18004b9cb  mov     [rsp+68h+var_48], ebx
0x18004b9cf  mov     rcx, [rcx+0D8h]
0x18004b9d6  call    WPP_SF_qD
0x18004b9db  lea     rcx, [rbp+ppMFAttributes]; void *
0x18004b9df  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18004b9e4  lea     rcx, [rdi+18h]; lpCriticalSection
0x18004b9e8  call    cs:__imp_LeaveCriticalSection
0x18004b9ee  mov     eax, ebx
0x18004b9f0  mov     rcx, [rbp+var_18]
0x18004b9f4  xor     rcx, rsp; StackCookie
0x18004b9f7  call    __security_check_cookie
0x18004b9fc  add     rsp, 68h
0x18004ba00  pop     r15
0x18004ba02  pop     r14
0x18004ba04  pop     r13
0x18004ba06  pop     r12
0x18004ba08  pop     rdi
0x18004ba09  pop     rsi
0x18004ba0a  pop     rbx
0x18004ba0b  pop     rbp
0x18004ba0c  retn
```

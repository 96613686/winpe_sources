# FSVMDuplicateGfxHandle(_GUID const &,ulong,void *,void * *)

- ea: `0x18002575c`
- end: `0x1800259bd`
- name: `?FSVMDuplicateGfxHandle@@YAJAEBU_GUID@@KPEAXPEAPEAX@Z`
- size: `609`
- prototype: `__int64 __fastcall(const struct _GUID *, DWORD dwProcessId, HANDLE hSourceHandle, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800d4ba0`

## callees

- `0x180003e20`
- `0x180009608`
- `0x180009b5c`
- `0x1800198f4`
- `0x18001c444`
- `0x18002575c`
- `0x18002681c`
- `0x1800268fc`
- `0x18004d714`
- `0x18004da70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800258cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025950`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025923`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180025946`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180025946`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800258a6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800258a6`
- `api-ms-win-dx-d3dkmt-l1-1-6!D3DKMTDuplicateHandle` at `0x18002581c`
- `api-ms-win-dx-d3dkmt-l1-1-6!D3DKMTDuplicateHandle` at `0x18002581c`

## pseudocode

```c
__int64 __fastcall FSVMDuplicateGfxHandle(const struct _GUID *a1, DWORD dwProcessId, HANDLE hSourceHandle, void **a4)
{
  char v4; // bl
  char v5; // r15
  unsigned int v9; // edi
  __int64 v10; // rdx
  bool v11; // zf
  struct _GUID v12; // xmm0
  int v13; // eax
  GuidTrace *v14; // rax
  const char *String; // rax
  int v16; // edx
  int v17; // r8d
  HANDLE v18; // rbx
  signed int v19; // eax
  __int64 v20; // rdx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  HANDLE TargetHandle; // [rsp+40h] [rbp-49h] BYREF
  HANDLE hTargetProcessHandle; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v26; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v27[32]; // [rsp+58h] [rbp-31h] BYREF
  HANDLE v28; // [rsp+78h] [rbp-11h] BYREF
  struct _GUID v29; // [rsp+80h] [rbp-9h]
  __int64 v30; // [rsp+90h] [rbp+7h]
  void *v31; // [rsp+98h] [rbp+Fh]
  int v32; // [rsp+A0h] [rbp+17h]
  int v33; // [rsp+A4h] [rbp+1Bh]

  v4 = 0;
  v5 = dwProcessId;
  LODWORD(TargetHandle) = 0;
  if ( hSourceHandle )
  {
    if ( !a4 )
    {
      v9 = -2147467261;
      if ( !g_wppLevels )
        return v9;
      v10 = 55;
      goto LABEL_4;
    }
    v11 = byte_18010ED54 == 0;
    *a4 = 0;
    if ( !v11 )
    {
      v12 = *a1;
      v31 = 0;
      v28 = hSourceHandle;
      v29 = v12;
      v30 = dwProcessId;
      v32 = 0;
      v33 = 1;
      v13 = D3DKMTDuplicateHandle(&v28);
      v9 = v13 | 0x10000000;
      if ( v13 >= 0 )
      {
        *a4 = v31;
      }
      else
      {
        if ( byte_18010EC4D )
        {
          v14 = GuidTrace::GuidTrace((GuidTrace *)v27, a1);
          String = GuidTrace::GetString(v14);
          WPP_SF_DqsD(*((_QWORD *)WPP_GLOBAL_Control + 27), v16, v17, v9, (char)hSourceHandle, (__int64)String, v5);
          v4 = 1;
        }
        if ( (v4 & 1) != 0 )
          FSString::~FSString((FSString *)v27);
      }
      return v9;
    }
    TargetHandle = 0;
    hTargetProcessHandle = 0;
    v26 = OpenProcess(0x40u, 0, dwProcessId);
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::swap(
      &hTargetProcessHandle,
      &v26);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
    v18 = hTargetProcessHandle;
    if ( hTargetProcessHandle )
    {
      v9 = 0;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TargetHandle,
        0);
      CurrentProcess = GetCurrentProcess();
      if ( DuplicateHandle(CurrentProcess, hSourceHandle, v18, &TargetHandle, 0, 0, 2u) )
        goto LABEL_27;
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( (v9 & 0x80000000) == 0 )
      {
LABEL_27:
        *a4 = TargetHandle;
        TargetHandle = 0;
        goto LABEL_28;
      }
      if ( !g_wppLevels )
      {
LABEL_28:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hTargetProcessHandle);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
        return v9;
      }
      v20 = 58;
    }
    else
    {
      v19 = GetLastError();
      v9 = v19;
      if ( v19 > 0 )
        v9 = (unsigned __int16)v19 | 0x80070000;
      if ( !g_wppLevels )
        goto LABEL_28;
      v20 = 57;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v9);
    goto LABEL_28;
  }
  v9 = -2147024809;
  if ( g_wppLevels )
  {
    v10 = 54;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x18002575c  push    rbp
0x18002575e  push    rbx
0x18002575f  push    rsi
0x180025760  push    rdi
0x180025761  push    r12
0x180025763  push    r14
0x180025765  push    r15
0x180025767  lea     rbp, [rsp-27h]
0x18002576c  sub     rsp, 0B0h
0x180025773  mov     rax, cs:__security_cookie
0x18002577a  xor     rax, rsp
0x18002577d  mov     [rbp+57h+var_38], rax
0x180025781  xor     ebx, ebx
0x180025783  mov     r15d, edx
0x180025786  mov     dword ptr [rbp+57h+TargetHandle], ebx
0x180025789  mov     rsi, r9
0x18002578c  mov     r14, r8
0x18002578f  mov     r12, rcx
0x180025792  test    r8, r8
0x180025795  jnz     short loc_1800257CF
0x180025797  mov     edi, 80070057h
0x18002579c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800257a3  jb      loc_18002599D
0x1800257a9  lea     edx, [rbx+36h]
0x1800257ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800257b3  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x1800257ba  xor     r9d, r9d
0x1800257bd  mov     [rsp+0E0h+dwDesiredAccess], edi
0x1800257c1  mov     rcx, [rcx+10h]
0x1800257c5  call    WPP_SF_qD
0x1800257ca  jmp     loc_18002599D
0x1800257cf  test    rsi, rsi
0x1800257d2  jnz     short loc_1800257EB
0x1800257d4  mov     edi, 80004003h
0x1800257d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800257e0  jb      loc_18002599D
0x1800257e6  lea     edx, [rsi+37h]
0x1800257e9  jmp     short loc_1800257AC
0x1800257eb  cmp     cs:byte_18010ED54, bl
0x1800257f1  mov     [r9], rbx
0x1800257f4  jz      loc_180025896
0x1800257fa  movups  xmm0, xmmword ptr [rcx]
0x1800257fd  lea     rcx, [rbp+57h+var_68]
0x180025801  mov     [rbp+57h+var_48], rbx
0x180025805  mov     [rbp+57h+var_68], r14
0x180025809  movdqu  [rbp+57h+var_60], xmm0
0x18002580e  mov     [rbp+57h+var_50], r15
0x180025812  mov     [rbp+57h+var_40], ebx
0x180025815  mov     [rbp+57h+var_3C], 1
0x18002581c  call    cs:__imp_D3DKMTDuplicateHandle
0x180025822  mov     edi, eax
0x180025824  or      edi, 10000000h
0x18002582a  jge     short loc_18002588A
0x18002582c  cmp     cs:byte_18010EC4D, 1
0x180025833  jb      short loc_180025873
0x180025835  mov     rdx, r12; struct _GUID *
0x180025838  lea     rcx, [rbp+57h+var_88]; this
0x18002583c  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180025841  mov     rcx, rax; this
0x180025844  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180025849  mov     rcx, cs:WPP_GLOBAL_Control
0x180025850  mov     r9d, edi
0x180025853  mov     [rsp+0E0h+dwOptions], r15d
0x180025858  mov     qword ptr [rsp+0E0h+bInheritHandle], rax
0x18002585d  mov     qword ptr [rsp+0E0h+dwDesiredAccess], r14
0x180025862  mov     rcx, [rcx+0D8h]
0x180025869  call    WPP_SF_DqsD
0x18002586e  mov     ebx, 1
0x180025873  test    bl, 1
0x180025876  jz      loc_18002599D
0x18002587c  lea     rcx, [rbp+57h+var_88]; this
0x180025880  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180025885  jmp     loc_18002599D
0x18002588a  mov     rax, [rbp+57h+var_48]
0x18002588e  mov     [rsi], rax
0x180025891  jmp     loc_18002599D
0x180025896  xor     edx, edx; bInheritHandle
0x180025898  mov     [rbp+57h+TargetHandle], rbx
0x18002589c  mov     r8d, r15d; dwProcessId
0x18002589f  mov     [rbp+57h+hTargetProcessHandle], rbx
0x1800258a3  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800258a6  call    cs:__imp_OpenProcess
0x1800258ac  lea     rdx, [rbp+57h+var_90]
0x1800258b0  mov     [rbp+57h+var_90], rax
0x1800258b4  lea     rcx, [rbp+57h+hTargetProcessHandle]
0x1800258b8  call    ?swap@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::swap(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1800258bd  lea     rcx, [rbp+57h+var_90]
0x1800258c1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800258c6  mov     rbx, [rbp+57h+hTargetProcessHandle]
0x1800258ca  test    rbx, rbx
0x1800258cd  jnz     short loc_180025916
0x1800258cf  call    cs:__imp_GetLastError
0x1800258d5  mov     edi, eax
0x1800258d7  test    eax, eax
0x1800258d9  jle     short loc_1800258E4
0x1800258db  movzx   edi, ax
0x1800258de  or      edi, 80070000h
0x1800258e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800258eb  jb      loc_18002598B
0x1800258f1  mov     edx, 39h ; '9'
0x1800258f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258fd  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180025904  xor     r9d, r9d
0x180025907  mov     [rsp+0E0h+dwDesiredAccess], edi
0x18002590b  mov     rcx, [rcx+10h]
0x18002590f  call    WPP_SF_qD
0x180025914  jmp     short loc_18002598B
0x180025916  xor     edx, edx
0x180025918  lea     rcx, [rbp+57h+TargetHandle]
0x18002591c  xor     edi, edi
0x18002591e  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180025923  call    cs:__imp_GetCurrentProcess
0x180025929  mov     [rsp+0E0h+dwOptions], 2; dwOptions
0x180025931  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x180025935  mov     rcx, rax; hSourceProcessHandle
0x180025938  mov     [rsp+0E0h+bInheritHandle], edi; bInheritHandle
0x18002593c  mov     r8, rbx; hTargetProcessHandle
0x18002593f  mov     [rsp+0E0h+dwDesiredAccess], edi; dwDesiredAccess
0x180025943  mov     rdx, r14; hSourceHandle
0x180025946  call    cs:__imp_DuplicateHandle
0x18002594c  test    eax, eax
0x18002594e  jnz     short loc_18002597C
0x180025950  call    cs:__imp_GetLastError
0x180025956  mov     edi, eax
0x180025958  test    eax, eax
0x18002595a  jle     short loc_180025965
0x18002595c  movzx   edi, ax
0x18002595f  or      edi, 80070000h
0x180025965  test    edi, edi
0x180025967  jns     short loc_18002597C
0x180025969  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025970  jb      short loc_18002598B
0x180025972  mov     edx, 3Ah ; ':'
0x180025977  jmp     loc_1800258F6
0x18002597c  mov     rcx, [rbp+57h+TargetHandle]
0x180025980  mov     [rsi], rcx
0x180025983  mov     [rbp+57h+TargetHandle], 0
0x18002598b  lea     rcx, [rbp+57h+hTargetProcessHandle]
0x18002598f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180025994  lea     rcx, [rbp+57h+TargetHandle]
0x180025998  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002599d  mov     eax, edi
0x18002599f  mov     rcx, [rbp+57h+var_38]
0x1800259a3  xor     rcx, rsp; StackCookie
0x1800259a6  call    __security_check_cookie
0x1800259ab  add     rsp, 0B0h
0x1800259b2  pop     r15
0x1800259b4  pop     r14
0x1800259b6  pop     r12
0x1800259b8  pop     rdi
0x1800259b9  pop     rsi
0x1800259ba  pop     rbx
0x1800259bb  pop     rbp
0x1800259bc  retn
```

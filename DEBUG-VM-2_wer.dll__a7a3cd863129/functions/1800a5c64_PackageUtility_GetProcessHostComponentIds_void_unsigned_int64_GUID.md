# PackageUtility::GetProcessHostComponentIds(void *,unsigned __int64 *,_GUID *)

- ea: `0x1800a5c64`
- end: `0x1800a5dac`
- name: `?GetProcessHostComponentIds@PackageUtility@@SAJPEAXPEA_KPEAU_GUID@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, unsigned __int64 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002054c`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x18001fe24`
- `0x18002bed4`
- `0x1800a5c64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a5ca8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a5ca8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5cb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5cb2`
- `ntdll!RtlQueryPackageIdentityEx` at `0x1800a5d0d`
- `ntdll!RtlQueryPackageIdentityEx` at `0x1800a5d0d`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x1800a5d56`
- `ntdll!RtlQueryTokenHostIdAsUlong64` at `0x1800a5d56`

## pseudocode

```c
__int64 __fastcall PackageUtility::GetProcessHostComponentIds(
        HANDLE ProcessHandle,
        unsigned __int64 *a2,
        struct _GUID *a3)
{
  void **v6; // rax
  DWORD LastError; // eax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  wchar_t *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int PackageIdentity; // eax
  int TokenHostIdAsUlong64; // eax
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  v16 = 0;
  *a3 = 0;
  v6 = (void **)tlx::replace<tlx::file_handle_traits>(&v16);
  if ( OpenProcessToken(ProcessHandle, 8u, v6) )
  {
    v9 = 0;
    PackageIdentity = RtlQueryPackageIdentityEx(v16, 0, 0, 0, 0, a3, 0);
    if ( PackageIdentity < 0 )
    {
      v9 = PackageIdentity | 0x10000000;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids, v9);
    }
    TokenHostIdAsUlong64 = RtlQueryTokenHostIdAsUlong64(v16, a2);
    if ( TokenHostIdAsUlong64 < 0 )
    {
      v9 = TokenHostIdAsUlong64 | 0x10000000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        v11 = 25;
        v12 = v9;
        goto LABEL_13;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v8 = ERROR_HR_FROM_WIN32(LastError);
    v9 = v8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v11 = 23;
      v12 = v8;
LABEL_13:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids, v12);
    }
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v16);
  return v9;
}

```

## disassembly

```asm
0x1800a5c64  mov     rax, rsp
0x1800a5c67  mov     [rax+8], rbx
0x1800a5c6b  mov     [rax+18h], rsi
0x1800a5c6f  push    rdi
0x1800a5c70  sub     rsp, 40h
0x1800a5c74  mov     rbx, rcx
0x1800a5c77  mov     qword ptr [rdx], 0
0x1800a5c7e  xorps   xmm0, xmm0
0x1800a5c81  mov     qword ptr [rax+10h], 0
0x1800a5c89  lea     rcx, [rax+10h]
0x1800a5c8d  mov     rdi, r8
0x1800a5c90  movdqu  xmmword ptr [r8], xmm0
0x1800a5c95  mov     rsi, rdx
0x1800a5c98  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1800a5c9d  mov     r8, rax; TokenHandle
0x1800a5ca0  mov     edx, 8; DesiredAccess
0x1800a5ca5  mov     rcx, rbx; ProcessHandle
0x1800a5ca8  call    cs:__imp_OpenProcessToken
0x1800a5cae  test    eax, eax
0x1800a5cb0  jnz     short loc_1800A5CEF
0x1800a5cb2  call    cs:__imp_GetLastError
0x1800a5cb8  mov     ecx, eax; unsigned int
0x1800a5cba  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800a5cbf  mov     ebx, eax
0x1800a5cc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5cc8  lea     rdi, WPP_GLOBAL_Control
0x1800a5ccf  cmp     rcx, rdi
0x1800a5cd2  jz      loc_1800A5D90
0x1800a5cd8  test    byte ptr [rcx+1Ch], 1
0x1800a5cdc  jz      loc_1800A5D90
0x1800a5ce2  mov     edx, 17h
0x1800a5ce7  mov     r9d, eax
0x1800a5cea  jmp     loc_1800A5D80
0x1800a5cef  mov     rcx, [rsp+48h+arg_8]
0x1800a5cf4  xor     ebx, ebx
0x1800a5cf6  mov     [rsp+48h+var_18], rbx
0x1800a5cfb  xor     r9d, r9d
0x1800a5cfe  mov     [rsp+48h+var_20], rdi
0x1800a5d03  xor     r8d, r8d
0x1800a5d06  xor     edx, edx
0x1800a5d08  mov     [rsp+48h+var_28], rbx
0x1800a5d0d  call    cs:__imp_RtlQueryPackageIdentityEx
0x1800a5d13  lea     rdi, WPP_GLOBAL_Control
0x1800a5d1a  test    eax, eax
0x1800a5d1c  jns     short loc_1800A5D4E
0x1800a5d1e  mov     ebx, eax
0x1800a5d20  bts     ebx, 1Ch
0x1800a5d24  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5d2b  cmp     rcx, rdi
0x1800a5d2e  jz      short loc_1800A5D4E
0x1800a5d30  test    byte ptr [rcx+1Ch], 2
0x1800a5d34  jz      short loc_1800A5D4E
0x1800a5d36  mov     rcx, [rcx+10h]
0x1800a5d3a  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x1800a5d41  mov     edx, 18h
0x1800a5d46  mov     r9d, ebx
0x1800a5d49  call    WPP_SF_d
0x1800a5d4e  mov     rcx, [rsp+48h+arg_8]
0x1800a5d53  mov     rdx, rsi
0x1800a5d56  call    cs:__imp_RtlQueryTokenHostIdAsUlong64
0x1800a5d5c  test    eax, eax
0x1800a5d5e  jns     short loc_1800A5D90
0x1800a5d60  mov     ebx, eax
0x1800a5d62  bts     ebx, 1Ch
0x1800a5d66  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a5d6d  cmp     rcx, rdi
0x1800a5d70  jz      short loc_1800A5D90
0x1800a5d72  test    byte ptr [rcx+1Ch], 2
0x1800a5d76  jz      short loc_1800A5D90
0x1800a5d78  mov     edx, 19h
0x1800a5d7d  mov     r9d, ebx
0x1800a5d80  mov     rcx, [rcx+10h]
0x1800a5d84  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x1800a5d8b  call    WPP_SF_d
0x1800a5d90  lea     rcx, [rsp+48h+arg_8]
0x1800a5d95  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800a5d9a  mov     rsi, [rsp+48h+arg_10]
0x1800a5d9f  mov     eax, ebx
0x1800a5da1  mov     rbx, [rsp+48h+arg_0]
0x1800a5da6  add     rsp, 40h
0x1800a5daa  pop     rdi
0x1800a5dab  retn
```

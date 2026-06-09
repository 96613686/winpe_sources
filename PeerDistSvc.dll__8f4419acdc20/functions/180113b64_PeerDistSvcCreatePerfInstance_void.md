# PeerDistSvcCreatePerfInstance(void)

- ea: `0x180113b64`
- end: `0x180113cb9`
- name: `?PeerDistSvcCreatePerfInstance@@YAJXZ`
- size: `341`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000594c`

## callees

- `0x180004374`
- `0x180008290`
- `0x1800180e4`
- `0x180113b64`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113c5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180113bd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180113bd1`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180113c54`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180113c54`

## pseudocode

```c
__int64 PeerDistSvcCreatePerfInstance(void)
{
  DWORD CurrentProcessId; // eax
  unsigned int v2; // ebx
  CHostedCacheMsgEncoding *v3; // rcx
  __int64 v4; // rdx
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax
  signed int LastError; // eax
  WCHAR Name[8]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]

  *(_OWORD *)Name = 0;
  v8 = 0;
  if ( byte_1801A77A8 )
  {
    CurrentProcessId = GetCurrentProcessId();
    v2 = StringCchPrintfW(Name, 0xCu, L"%d", CurrentProcessId);
    if ( (v2 & 0x80000000) == 0 )
    {
      Instance = PerfCreateInstance(PeerDistSvc, &BranchCacheGuid, Name, 0);
      if ( Instance )
      {
        ::Instance = Instance;
        return v2;
      }
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return v2;
      }
      v4 = 12;
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return v2;
      }
      v4 = 11;
    }
    WPP_SF_d(*((_QWORD *)v3 + 12), v4, WPP_c106f1c2962a3571e634919788e67001_Traceguids, v2);
    return v2;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_c106f1c2962a3571e634919788e67001_Traceguids);
  }
  return 2147943174LL;
}

```

## disassembly

```asm
0x180113b64  push    rbx
0x180113b66  sub     rsp, 40h
0x180113b6a  mov     rax, cs:__security_cookie
0x180113b71  xor     rax, rsp
0x180113b74  mov     [rsp+48h+var_10], rax
0x180113b79  xor     eax, eax
0x180113b7b  xorps   xmm0, xmm0
0x180113b7e  cmp     cs:byte_1801A77A8, al
0x180113b84  movups  xmmword ptr [rsp+48h+Name], xmm0
0x180113b89  mov     [rsp+48h+var_18], rax
0x180113b8e  jnz     short loc_180113BD1
0x180113b90  mov     rcx, cs:WPP_GLOBAL_Control
0x180113b97  lea     rax, WPP_GLOBAL_Control
0x180113b9e  cmp     rcx, rax
0x180113ba1  jz      short loc_180113BC7
0x180113ba3  test    dword ptr [rcx+6Ch], 800h
0x180113baa  jz      short loc_180113BC7
0x180113bac  cmp     byte ptr [rcx+69h], 1
0x180113bb0  jb      short loc_180113BC7
0x180113bb2  mov     rcx, [rcx+60h]
0x180113bb6  lea     r8, WPP_c106f1c2962a3571e634919788e67001_Traceguids
0x180113bbd  mov     edx, 0Ah
0x180113bc2  call    WPP_SF_
0x180113bc7  mov     eax, 80070306h
0x180113bcc  jmp     loc_180113CA6
0x180113bd1  call    cs:__imp_GetCurrentProcessId
0x180113bd7  lea     r8, aD; "%d"
0x180113bde  mov     edx, 0Ch; unsigned __int64
0x180113be3  mov     r9d, eax
0x180113be6  lea     rcx, [rsp+48h+Name]; unsigned __int16 *
0x180113beb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180113bf0  mov     ebx, eax
0x180113bf2  test    eax, eax
0x180113bf4  jns     short loc_180113C3E
0x180113bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180113bfd  lea     rax, WPP_GLOBAL_Control
0x180113c04  cmp     rcx, rax
0x180113c07  jz      loc_180113CA4
0x180113c0d  test    dword ptr [rcx+6Ch], 800h
0x180113c14  jz      loc_180113CA4
0x180113c1a  cmp     byte ptr [rcx+69h], 1
0x180113c1e  jb      loc_180113CA4
0x180113c24  mov     edx, 0Bh
0x180113c29  mov     rcx, [rcx+60h]
0x180113c2d  lea     r8, WPP_c106f1c2962a3571e634919788e67001_Traceguids
0x180113c34  mov     r9d, ebx
0x180113c37  call    WPP_SF_d
0x180113c3c  jmp     short loc_180113CA4
0x180113c3e  mov     rcx, cs:PeerDistSvc; ProviderHandle
0x180113c45  lea     r8, [rsp+48h+Name]; Name
0x180113c4a  xor     r9d, r9d; Id
0x180113c4d  lea     rdx, BranchCacheGuid; CounterSetGuid
0x180113c54  call    cs:__imp_PerfCreateInstance
0x180113c5a  test    rax, rax
0x180113c5d  jnz     short loc_180113C9D
0x180113c5f  call    cs:__imp_GetLastError
0x180113c65  mov     ebx, eax
0x180113c67  test    eax, eax
0x180113c69  jle     short loc_180113C74
0x180113c6b  movzx   ebx, ax
0x180113c6e  or      ebx, 80070000h
0x180113c74  mov     rcx, cs:WPP_GLOBAL_Control
0x180113c7b  lea     rax, WPP_GLOBAL_Control
0x180113c82  cmp     rcx, rax
0x180113c85  jz      short loc_180113CA4
0x180113c87  test    dword ptr [rcx+6Ch], 800h
0x180113c8e  jz      short loc_180113CA4
0x180113c90  cmp     byte ptr [rcx+69h], 1
0x180113c94  jb      short loc_180113CA4
0x180113c96  mov     edx, 0Ch
0x180113c9b  jmp     short loc_180113C29
0x180113c9d  mov     cs:Instance, rax
0x180113ca4  mov     eax, ebx
0x180113ca6  mov     rcx, [rsp+48h+var_10]
0x180113cab  xor     rcx, rsp; StackCookie
0x180113cae  call    __security_check_cookie
0x180113cb3  add     rsp, 40h
0x180113cb7  pop     rbx
0x180113cb8  retn
```

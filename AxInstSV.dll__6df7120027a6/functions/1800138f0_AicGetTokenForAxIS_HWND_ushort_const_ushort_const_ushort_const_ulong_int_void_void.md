# AicGetTokenForAxIS(HWND__ *,ushort const *,ushort const *,ushort const *,ulong,int,void *,void * *)

- ea: `0x1800138f0`
- end: `0x180013baa`
- name: `?AicGetTokenForAxIS@@YAJPEAUHWND__@@PEBG11KHPEAXPEAPEAX@Z`
- size: `698`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, HANDLE hToken, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006e30`

## callees

- `0x180001720`
- `0x1800021b8`
- `0x18000228f`
- `0x180002332`
- `0x1800138f0`
- `0x180013bb0`
- `0x180013bdc`
- `0x180013c68`
- `0x180013cc0`
- `0x180013e1c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013a5d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013aa2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013a5d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180013aa2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013a7a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013b64`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013a7a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013b64`
- `RPCRT4!I_RpcExceptionFilter` at `0x180014bec`
- `RPCRT4!I_RpcExceptionFilter` at `0x180014bec`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180013b10`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180013b10`
- `RPCRT4!RpcBindingFree` at `0x1800139cf`
- `RPCRT4!RpcBindingFree` at `0x1800139cf`

## pseudocode

```c
__int64 __fastcall AicGetTokenForAxIS(
        HWND a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        int a6,
        HANDLE hToken,
        void **a8)
{
  unsigned int v10; // edi
  unsigned int v11; // r14d
  unsigned int v12; // edx
  unsigned __int16 *v13; // rcx
  unsigned int v14; // r8d
  int v15; // esi
  signed int started; // ebx
  unsigned __int64 v17; // rax
  __int64 v18; // rcx
  unsigned int v19; // ecx
  __int64 v21; // [rsp+30h] [rbp-158h]
  __int64 v22; // [rsp+38h] [rbp-150h]
  __int64 v23; // [rsp+58h] [rbp-130h]
  RPC_BINDING_HANDLE Binding; // [rsp+78h] [rbp-110h] BYREF
  HWND v25; // [rsp+80h] [rbp-108h]
  const unsigned __int16 *v26; // [rsp+88h] [rbp-100h]
  HWND v27; // [rsp+90h] [rbp-F8h]
  const unsigned __int16 *v28; // [rsp+A0h] [rbp-E8h]
  const unsigned __int16 *v29; // [rsp+B0h] [rbp-D8h]
  HANDLE v30; // [rsp+B8h] [rbp-D0h]
  void **v31; // [rsp+C0h] [rbp-C8h]
  _RPC_ASYNC_STATE pAsync; // [rsp+D0h] [rbp-B8h] BYREF

  v26 = a3;
  v25 = a1;
  v27 = a1;
  v28 = a3;
  v29 = a4;
  v30 = hToken;
  v31 = a8;
  v10 = 0;
  Binding = 0;
  v11 = 0;
  memset_0(&pAsync, 0, sizeof(pAsync));
  v15 = 0;
  *a8 = 0;
  if ( a3 && a4 )
  {
    if ( qword_1800215B8 )
      goto LABEL_19;
    started = AicpCreateBindingHandle(v13, v12, &Binding);
    if ( !started )
    {
      if ( _InterlockedCompareExchange64(&qword_1800215B8, (signed __int64)Binding, 0) )
      {
        RpcBindingFree(&Binding);
        Binding = 0;
      }
      goto LABEL_19;
    }
  }
  else
  {
    started = 87;
  }
  while ( 1 )
  {
    if ( v15 )
    {
      started = AicpAsyncFinishCall(&pAsync, v12, v14, started);
      v15 = 0;
    }
    AicpAsyncCloseHandle(&pAsync);
    if ( !started )
      return v10;
    if ( *a8 )
    {
      CloseHandle_0(*a8);
      *a8 = 0;
    }
    v17 = (unsigned int)(started - 1708);
    if ( (unsigned int)v17 > 0x2D )
      goto LABEL_23;
    v18 = 0x200000004201LL;
    if ( !_bittest64(&v18, v17) )
      goto LABEL_23;
    if ( v11 > 1 )
    {
      started = 1061;
LABEL_23:
      if ( started > 0 )
        return (unsigned __int16)started | 0x80070000;
      return (unsigned int)started;
    }
    ++v11;
    if ( ImpersonateLoggedOnUser(hToken) )
    {
      started = AicpStartAIS(v19);
      RevertToSelf();
      if ( !started )
      {
LABEL_19:
        started = AicpAsyncInitializeHandle(&pAsync, v12);
        if ( !started )
        {
          if ( !ImpersonateLoggedOnUser(hToken) )
            goto LABEL_17;
          LODWORD(v23) = -1;
          LODWORD(v22) = 0;
          LODWORD(v21) = 2;
          Ndr64AsyncClientCall(
            (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
            0,
            0,
            &pAsync,
            qword_1800215B8,
            v25,
            v21,
            v22,
            L"Winsta0\\Default",
            v26,
            a4,
            v23,
            a8);
          v15 = started + 1;
          RevertToSelf();
        }
      }
    }
    else
    {
LABEL_17:
      started = GetLastError_0();
    }
  }
}

```

## disassembly

```asm
0x1800138f0  push    rbx
0x1800138f2  push    rsi
0x1800138f3  push    rdi
0x1800138f4  push    r12
0x1800138f6  push    r13
0x1800138f8  push    r14
0x1800138fa  push    r15
0x1800138fc  sub     rsp, 150h
0x180013903  mov     rax, cs:__security_cookie
0x18001390a  xor     rax, rsp
0x18001390d  mov     [rsp+188h+var_48], rax
0x180013915  mov     r12, r9
0x180013918  mov     rbx, r8
0x18001391b  mov     [rsp+188h+var_100], rbx
0x180013923  mov     [rsp+188h+var_108], rcx
0x18001392b  mov     [rsp+188h+var_F8], rcx
0x180013933  mov     [rsp+188h+var_E8], rbx
0x18001393b  mov     [rsp+188h+var_D8], r9
0x180013943  mov     r13, [rsp+188h+hToken]
0x18001394b  mov     [rsp+188h+var_D0], r13
0x180013953  mov     r15, [rsp+188h+arg_38]
0x18001395b  mov     [rsp+188h+var_C8], r15
0x180013963  xor     edi, edi
0x180013965  mov     [rsp+188h+Binding], rdi
0x18001396a  mov     r14d, edi
0x18001396d  mov     [rsp+188h+var_114], edi
0x180013971  xor     edx, edx; Val
0x180013973  lea     r8d, [rdi+70h]; Size
0x180013977  lea     rcx, [rsp+188h+pAsync]; void *
0x18001397f  call    memset_0
0x180013984  mov     esi, edi
0x180013986  mov     [rsp+188h+var_118], edi
0x18001398a  mov     [r15], rdi
0x18001398d  test    rbx, rbx
0x180013990  jz      short loc_1800139DF
0x180013992  test    r12, r12
0x180013995  jz      short loc_1800139DF
0x180013997  cmp     cs:qword_1800215B8, rdi
0x18001399e  jnz     loc_180013A88
0x1800139a4  lea     r8, [rsp+188h+Binding]; void **
0x1800139a9  call    ?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z; AicpCreateBindingHandle(ushort *,int,void * *)
0x1800139ae  mov     ebx, eax
0x1800139b0  test    eax, eax
0x1800139b2  jnz     short loc_1800139E4
0x1800139b4  mov     rcx, [rsp+188h+Binding]
0x1800139b9  xor     eax, eax
0x1800139bb  lock cmpxchg cs:qword_1800215B8, rcx
0x1800139c4  jz      loc_180013A88
0x1800139ca  lea     rcx, [rsp+188h+Binding]; Binding
0x1800139cf  call    cs:__imp_RpcBindingFree
0x1800139d5  mov     [rsp+188h+Binding], rdi
0x1800139da  jmp     loc_180013A88
0x1800139df  mov     ebx, 57h ; 'W'
0x1800139e4  test    esi, esi
0x1800139e6  jz      short loc_180013A00
0x1800139e8  mov     r9d, ebx; unsigned int
0x1800139eb  lea     rcx, [rsp+188h+pAsync]; pAsync
0x1800139f3  call    ?AicpAsyncFinishCall@@YAKPEAU_RPC_ASYNC_STATE@@HKK@Z; AicpAsyncFinishCall(_RPC_ASYNC_STATE *,int,ulong,ulong)
0x1800139f8  mov     ebx, eax
0x1800139fa  mov     esi, edi
0x1800139fc  mov     [rsp+188h+var_118], edi
0x180013a00  lea     rcx, [rsp+188h+pAsync]; struct _RPC_ASYNC_STATE *
0x180013a08  call    ?AicpAsyncCloseHandle@@YAXPEAU_RPC_ASYNC_STATE@@@Z; AicpAsyncCloseHandle(_RPC_ASYNC_STATE *)
0x180013a0d  test    ebx, ebx
0x180013a0f  jz      loc_180013B85
0x180013a15  cmp     [r15], rdi
0x180013a18  jz      short loc_180013A25
0x180013a1a  mov     rcx, [r15]; hObject
0x180013a1d  call    CloseHandle_0
0x180013a22  mov     [r15], rdi
0x180013a25  lea     eax, [rbx-6ACh]
0x180013a2b  cmp     eax, 2Dh ; '-'
0x180013a2e  ja      loc_180013B74
0x180013a34  mov     rcx, 200000004201h
0x180013a3e  bt      rcx, rax
0x180013a42  jnb     loc_180013B74
0x180013a48  cmp     r14d, 1
0x180013a4c  ja      loc_180013B6F
0x180013a52  inc     r14d
0x180013a55  mov     [rsp+188h+var_114], r14d
0x180013a5a  mov     rcx, r13; hToken
0x180013a5d  call    cs:__imp_ImpersonateLoggedOnUser
0x180013a63  test    eax, eax
0x180013a65  jnz     short loc_180013A73
0x180013a67  call    GetLastError_0
0x180013a6c  mov     ebx, eax
0x180013a6e  jmp     loc_1800139E4
0x180013a73  call    ?AicpStartAIS@@YAKK@Z; AicpStartAIS(ulong)
0x180013a78  mov     ebx, eax
0x180013a7a  call    cs:__imp_RevertToSelf
0x180013a80  test    ebx, ebx
0x180013a82  jnz     loc_1800139E4
0x180013a88  lea     rcx, [rsp+188h+pAsync]; struct _RPC_ASYNC_STATE *
0x180013a90  call    ?AicpAsyncInitializeHandle@@YAKPEAU_RPC_ASYNC_STATE@@K@Z; AicpAsyncInitializeHandle(_RPC_ASYNC_STATE *,ulong)
0x180013a95  mov     ebx, eax
0x180013a97  test    eax, eax
0x180013a99  jnz     loc_1800139E4
0x180013a9f  mov     rcx, r13; hToken
0x180013aa2  call    cs:__imp_ImpersonateLoggedOnUser
0x180013aa8  test    eax, eax
0x180013aaa  jz      short loc_180013A67
0x180013aac  mov     [rsp+188h+var_128], r15
0x180013ab1  mov     dword ptr [rsp+188h+var_130], 0FFFFFFFFh
0x180013ab9  mov     [rsp+188h+var_138], r12
0x180013abe  mov     rax, [rsp+188h+var_100]
0x180013ac6  mov     [rsp+188h+var_140], rax
0x180013acb  lea     rax, aWinsta0Default; "Winsta0\\Default"
0x180013ad2  mov     [rsp+188h+var_148], rax
0x180013ad7  mov     dword ptr [rsp+188h+var_150], edi
0x180013adb  mov     dword ptr [rsp+188h+var_158], 2
0x180013ae3  mov     rax, [rsp+188h+var_108]
0x180013aeb  mov     [rsp+188h+var_160], rax
0x180013af0  mov     rax, cs:qword_1800215B8
0x180013af7  mov     [rsp+188h+var_168], rax
0x180013afc  lea     r9, [rsp+188h+pAsync]
0x180013b04  xor     r8d, r8d; pReturnValue
0x180013b07  xor     edx, edx; nProcNum
0x180013b09  lea     rcx, pProxyInfo; pProxyInfo
0x180013b10  call    cs:__imp_Ndr64AsyncClientCall
0x180013b16  lea     esi, [rbx+1]
0x180013b19  mov     [rsp+188h+var_118], esi
0x180013b1d  jmp     short loc_180013B64
0x180013b1f  mov     ebx, eax
0x180013b21  xor     edi, edi
0x180013b23  mov     r14d, [rsp+188h+var_114]
0x180013b28  mov     esi, [rsp+188h+var_118]
0x180013b2c  mov     rax, [rsp+188h+var_F8]
0x180013b34  mov     [rsp+188h+var_108], rax
0x180013b3c  mov     rax, [rsp+188h+var_E8]
0x180013b44  mov     [rsp+188h+var_100], rax
0x180013b4c  mov     r12, [rsp+188h+var_D8]
0x180013b54  mov     r13, [rsp+188h+var_D0]
0x180013b5c  mov     r15, [rsp+188h+var_C8]
0x180013b64  call    cs:__imp_RevertToSelf
0x180013b6a  jmp     loc_1800139E4
0x180013b6f  mov     ebx, 425h
0x180013b74  test    ebx, ebx
0x180013b76  jz      short loc_180013B85
0x180013b78  jle     short loc_180013B83
0x180013b7a  movzx   ebx, bx
0x180013b7d  or      ebx, 80070000h
0x180013b83  mov     edi, ebx
0x180013b85  mov     eax, edi
0x180013b87  mov     rcx, [rsp+188h+var_48]
0x180013b8f  xor     rcx, rsp; StackCookie
0x180013b92  call    __security_check_cookie
0x180013b97  add     rsp, 150h
0x180013b9e  pop     r15
0x180013ba0  pop     r14
0x180013ba2  pop     r13
0x180013ba4  pop     r12
0x180013ba6  pop     rdi
0x180013ba7  pop     rsi
0x180013ba8  pop     rbx
0x180013ba9  retn
0x180014bde  push    rbp
0x180014be0  sub     rsp, 70h
0x180014be4  mov     rbp, rdx
0x180014be7  mov     rcx, [rcx]
0x180014bea  mov     ecx, [rcx]; ExceptionCode
0x180014bec  call    cs:__imp_I_RpcExceptionFilter
0x180014bf2  nop
0x180014bf3  add     rsp, 70h
0x180014bf7  pop     rbp
0x180014bf8  retn
```

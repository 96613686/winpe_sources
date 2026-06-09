# EffectiveUserContext::Impersonate(void)

- ea: `0x180024020`
- end: `0x1800242ec`
- name: `?Impersonate@EffectiveUserContext@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ`
- size: `716`
- prototype: `_QWORD *__fastcall(void ***, _QWORD *)`
- caller_count: `54`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010020`
- `0x1800111a0`
- `0x1800139b4`
- `0x180013fd0`
- `0x180014384`
- `0x180023920`
- `0x180024450`
- `0x180039144`
- `0x1800393b4`
- `0x18003a068`
- `0x18003c020`
- `0x180041888`
- `0x18005c204`
- `0x180060290`
- `0x1800608ac`
- `0x18006635c`
- `0x180086bd0`
- `0x180087e10`
- `0x180093784`
- `0x18009b3ac`
- `0x1800a5a20`
- `0x1800aa728`
- `0x1800b16f0`
- `0x1800e6384`
- `0x1800f0f20`
- `0x1800feca0`
- `0x180102c4c`
- `0x180108080`
- `0x18010cf8c`
- `0x180116a38`
- `0x18016c720`
- `0x18016cb7c`
- `0x18017a2f0`
- `0x180181808`
- `0x180181890`
- `0x18018199c`
- `0x180181a2c`
- `0x180181ad0`
- `0x180181b64`
- `0x180181c08`
- `0x180181cec`
- `0x180181dc4`
- `0x180181e54`
- `0x180181ee4`
- `0x180182014`
- `0x1801820f8`
- `0x180182194`
- `0x180182230`
- `0x18018230c`
- `0x1801823ac`

## callees

- `0x180024020`
- `0x180024300`
- `0x180032b98`
- `0x180032bd0`
- `0x18009c1b8`
- `0x1800a15ac`
- `0x180120850`
- `0x180178038`
- `0x1801a6bf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002427f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002427f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024218`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024218`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800240a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800240a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180024064`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800241af`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180024064`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800241af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002404f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002404f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002408f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002408f`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x18002429d`
- `api-ms-win-core-registry-l1-1-0!RegDisablePredefinedCacheEx` at `0x18002429d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024121`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024121`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800241c8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800241c8`

## string_xrefs

- `0x18002426d`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800242c4`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`
- `0x1800242da`: `onecoreuap\shell\cloudstore\common\src\effectivecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall EffectiveUserContext::Impersonate(void ***a1, _QWORD *a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v6; // ebx
  HANDLE CurrentProcess; // rax
  bool v8; // bl
  void *v9; // r14
  char v10; // di
  char *v11; // rbx
  void *v12; // rdx
  void *v13; // rcx
  void *v14; // rcx
  HANDLE v16; // rax
  void *v17; // rcx
  const char *v18; // r9
  void *v19; // rax
  void *v20; // rcx
  void *v21; // rcx
  const char *v22; // r9
  signed int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // [rsp+20h] [rbp-30h]
  void *v26; // [rsp+28h] [rbp-28h] BYREF
  HANDLE *p_hObject; // [rsp+30h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-18h] BYREF
  char v29; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  void *Block; // [rsp+90h] [rbp+40h] BYREF
  void *v32; // [rsp+A0h] [rbp+50h] BYREF
  HANDLE hObject; // [rsp+A8h] [rbp+58h] BYREF

  hObject = 0;
  p_hObject = &hObject;
  TokenHandle = 0;
  v29 = 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0x2000000u, 0, &TokenHandle) )
  {
    v6 = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 == -2147023888 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle) )
      {
        v6 = 0;
      }
      else
      {
        v23 = GetLastError();
        v6 = v23;
        if ( v23 > 0 )
          v6 = (unsigned __int16)v23 | 0x80070000;
      }
    }
  }
  v8 = v6 >= 0;
  if ( v29 )
  {
    v9 = TokenHandle;
    if ( (char *)*p_hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      wil::details::close_invoke_helper<1,int (*)(void *),&int CloseHandle(void *),void *>::close_reset(*p_hObject);
    *p_hObject = v9;
  }
  if ( v8 )
  {
    v10 = 0;
  }
  else
  {
    wil::open_current_access_token(&p_hObject);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hObject,
      p_hObject);
    v10 = 1;
  }
  v11 = (char *)hObject;
  LOBYTE(TokenHandle) = v10;
  p_hObject = (HANDLE *)hObject;
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&v32, hObject);
  if ( *a1 )
    v12 = **a1;
  else
    v12 = 0;
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, v12);
  if ( EqualSid(*(PSID *)v32, *(PSID *)Block) )
  {
    if ( v10 )
      EnsurePredefinedCacheDisabled();
    *a2 = -1;
    v13 = Block;
    Block = 0;
    if ( v13 )
      operator delete(v13);
    v14 = v32;
    v32 = 0;
    if ( v14 )
      operator delete(v14);
    if ( (unsigned __int64)(v11 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      return a2;
LABEL_35:
    CloseHandle(v11);
    return a2;
  }
  if ( !byte_180284CE0 )
  {
    v24 = RegDisablePredefinedCacheEx();
    if ( v24 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x24E,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
        (const char *)v24,
        v25);
    byte_180284CE0 = 1;
  }
  v26 = 0;
  v16 = GetCurrentThread();
  if ( !OpenThreadToken(v16, 0xF01FFu, 1, &v26) && GetLastError() != 1008 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      v22);
  if ( *a1 )
    v17 = **a1;
  else
    v17 = 0;
  if ( !ImpersonateLoggedOnUser(v17) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x275,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\common\\src\\effectivecontext.cpp",
      v18);
  v19 = v26;
  v26 = 0;
  *a2 = v19;
  v20 = Block;
  Block = 0;
  if ( v20 )
    operator delete(v20);
  v21 = v32;
  v32 = 0;
  if ( v21 )
    operator delete(v21);
  if ( (unsigned __int64)(v11 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_35;
  return a2;
}

```

## disassembly

```asm
0x180024020  push    rbp
0x180024022  push    rbx
0x180024023  push    rsi
0x180024024  push    rdi
0x180024025  push    r12
0x180024027  push    r14
0x180024029  push    r15
0x18002402b  mov     rbp, rsp
0x18002402e  sub     rsp, 50h
0x180024032  mov     rsi, rdx
0x180024035  mov     r15, rcx
0x180024038  xor     r12d, r12d
0x18002403b  mov     [rbp+hObject], r12
0x18002403f  lea     rax, [rbp+hObject]
0x180024043  mov     [rbp+var_20], rax
0x180024047  mov     [rbp+TokenHandle], r12
0x18002404b  mov     [rbp+var_10], 1
0x18002404f  call    cs:__imp_GetCurrentThread
0x180024055  mov     rcx, rax; ThreadHandle
0x180024058  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002405c  xor     r8d, r8d; OpenAsSelf
0x18002405f  mov     edx, 2000000h; DesiredAccess
0x180024064  call    cs:__imp_OpenThreadToken
0x18002406a  test    eax, eax
0x18002406c  jnz     loc_180024232
0x180024072  call    cs:__imp_GetLastError
0x180024078  mov     ebx, eax
0x18002407a  test    eax, eax
0x18002407c  jle     short loc_180024087
0x18002407e  movzx   ebx, ax
0x180024081  or      ebx, 80070000h
0x180024087  cmp     ebx, 800703F0h
0x18002408d  jnz     short loc_1800240B2
0x18002408f  call    cs:__imp_GetCurrentProcess
0x180024095  mov     rcx, rax; ProcessHandle
0x180024098  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002409c  mov     edx, 2000000h; DesiredAccess
0x1800240a1  call    cs:__imp_OpenProcessToken
0x1800240a7  test    eax, eax
0x1800240a9  jz      loc_18002427F
0x1800240af  mov     ebx, r12d
0x1800240b2  shr     ebx, 1Fh
0x1800240b5  xor     bl, 1
0x1800240b8  cmp     [rbp+var_10], 0
0x1800240bc  jz      short loc_1800240DA
0x1800240be  mov     r14, [rbp+TokenHandle]
0x1800240c2  mov     rdi, [rbp+var_20]
0x1800240c6  mov     rcx, [rdi]; hObject
0x1800240c9  lea     rax, [rcx-1]
0x1800240cd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800240d1  jbe     loc_1800242B7
0x1800240d7  mov     [rdi], r14
0x1800240da  test    bl, bl
0x1800240dc  jz      loc_18002423A
0x1800240e2  xor     dil, dil
0x1800240e5  mov     rbx, [rbp+hObject]
0x1800240e9  mov     byte ptr [rbp+TokenHandle], dil
0x1800240ed  mov     [rbp+var_20], rbx
0x1800240f1  mov     rdx, rbx
0x1800240f4  lea     rcx, [rbp+arg_10]
0x1800240f8  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x1800240fd  nop
0x1800240fe  mov     rax, [r15]
0x180024101  test    rax, rax
0x180024104  jz      short loc_180024181
0x180024106  mov     rdx, [rax]
0x180024109  lea     rcx, [rbp+Block]
0x18002410d  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x180024112  nop
0x180024113  mov     rdx, [rbp+Block]
0x180024117  mov     rdx, [rdx]; pSid2
0x18002411a  mov     rcx, [rbp+arg_10]
0x18002411e  mov     rcx, [rcx]; pSid1
0x180024121  call    cs:__imp_EqualSid
0x180024127  test    eax, eax
0x180024129  jz      short loc_180024186
0x18002412b  test    dil, dil
0x18002412e  jnz     loc_180024228
0x180024134  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x18002413b  mov     rcx, [rbp+Block]; Block
0x18002413f  mov     [rbp+Block], r12
0x180024143  test    rcx, rcx
0x180024146  jz      short loc_18002414E
0x180024148  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002414d  nop
0x18002414e  mov     rcx, [rbp+arg_10]; Block
0x180024152  mov     [rbp+arg_10], r12
0x180024156  test    rcx, rcx
0x180024159  jz      short loc_180024161
0x18002415b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024160  nop
0x180024161  lea     rax, [rbx-1]
0x180024165  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024169  jbe     loc_180024215
0x18002416f  mov     rax, rsi
0x180024172  add     rsp, 50h
0x180024176  pop     r15
0x180024178  pop     r14
0x18002417a  pop     r12
0x18002417c  pop     rdi
0x18002417d  pop     rsi
0x18002417e  pop     rbx
0x18002417f  pop     rbp
0x180024180  retn
0x180024181  mov     rdx, r12
0x180024184  jmp     short loc_180024109
0x180024186  cmp     cs:byte_180284CE0, 0
0x18002418d  jz      loc_18002429D
0x180024193  mov     [rbp+var_28], r12
0x180024197  call    cs:__imp_GetCurrentThread
0x18002419d  lea     r9, [rbp+var_28]; TokenHandle
0x1800241a1  mov     edx, 0F01FFh; DesiredAccess
0x1800241a6  mov     r8d, 1; OpenAsSelf
0x1800241ac  mov     rcx, rax; ThreadHandle
0x1800241af  call    cs:__imp_OpenThreadToken
0x1800241b5  test    eax, eax
0x1800241b7  jz      loc_180024258
0x1800241bd  mov     rax, [r15]
0x1800241c0  test    rax, rax
0x1800241c3  jz      short loc_180024223
0x1800241c5  mov     rcx, [rax]; hToken
0x1800241c8  call    cs:__imp_ImpersonateLoggedOnUser
0x1800241ce  test    eax, eax
0x1800241d0  jz      loc_1800242D6
0x1800241d6  mov     rax, [rbp+var_28]
0x1800241da  mov     [rbp+var_28], r12
0x1800241de  mov     [rsi], rax
0x1800241e1  mov     rcx, [rbp+Block]; Block
0x1800241e5  mov     [rbp+Block], r12
0x1800241e9  test    rcx, rcx
0x1800241ec  jz      short loc_1800241F4
0x1800241ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800241f3  nop
0x1800241f4  mov     rcx, [rbp+arg_10]; Block
0x1800241f8  mov     [rbp+arg_10], r12
0x1800241fc  test    rcx, rcx
0x1800241ff  jz      short loc_180024207
0x180024201  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024206  nop
0x180024207  lea     rax, [rbx-1]
0x18002420b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002420f  ja      loc_18002416F
0x180024215  mov     rcx, rbx; hObject
0x180024218  call    cs:__imp_CloseHandle
0x18002421e  jmp     loc_18002416F
0x180024223  mov     rcx, r12
0x180024226  jmp     short loc_1800241C8
0x180024228  call    ?EnsurePredefinedCacheDisabled@@YAXXZ; EnsurePredefinedCacheDisabled(void)
0x18002422d  jmp     loc_180024134
0x180024232  mov     ebx, r12d
0x180024235  jmp     loc_1800240B2
0x18002423a  lea     rcx, [rbp+var_20]
0x18002423e  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x180024243  mov     rdx, [rbp+var_20]
0x180024247  lea     rcx, [rbp+hObject]
0x18002424b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180024250  mov     dil, 1
0x180024253  jmp     loc_1800240E5
0x180024258  call    cs:__imp_GetLastError
0x18002425e  cmp     eax, 3F0h
0x180024263  jz      loc_1800241BD
0x180024269  mov     rcx, [rbp+38h]; this
0x18002426d  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x180024274  mov     edx, 270h; void *
0x180024279  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002427f  call    cs:__imp_GetLastError
0x180024285  mov     ebx, eax
0x180024287  test    eax, eax
0x180024289  jle     loc_1800240B2
0x18002428f  movzx   ebx, ax
0x180024292  or      ebx, 80070000h
0x180024298  jmp     loc_1800240B2
0x18002429d  call    cs:__imp_RegDisablePredefinedCacheEx
0x1800242a3  mov     rcx, [rbp+38h]; this
0x1800242a7  test    eax, eax
0x1800242a9  jnz     short loc_1800242C1
0x1800242ab  mov     cs:byte_180284CE0, 1
0x1800242b2  jmp     loc_180024193
0x1800242b7  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x1800242bc  jmp     loc_1800240D7
0x1800242c1  mov     r9d, eax; char *
0x1800242c4  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800242cb  mov     edx, 24Eh; void *
0x1800242d0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800242d6  mov     rcx, [rbp+38h]; this
0x1800242da  lea     r8, aOnecoreuapShel_10; "onecoreuap\\shell\\cloudstore\\common\\"...
0x1800242e1  mov     edx, 275h; void *
0x1800242e6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

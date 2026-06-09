# CIISModuleFactory::Terminate(void)

- ea: `0x1800040c0`
- end: `0x18000419e`
- name: `?Terminate@CIISModuleFactory@@UEAAXXZ`
- size: `222`
- prototype: `void __fastcall(CIISModuleFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800029b8`
- `0x1800040c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004112`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800040eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004112`
- `iisutil!PuDeleteDebugPrintsObject` at `0x18000416e`
- `iisutil!PuDeleteDebugPrintsObject` at `0x18000416e`
- `CRYPTSP!CryptReleaseContext` at `0x180004148`
- `CRYPTSP!CryptReleaseContext` at `0x180004148`

## pseudocode

```c
void __fastcall CIISModuleFactory::Terminate(CIISModuleFactory *this)
{
  void *v2; // rcx
  void *v3; // rdi

  v2 = s_pAnonAuthProvider;
  if ( s_pAnonAuthProvider )
  {
    v3 = s_pAnonAuthProvider;
    if ( *((_QWORD *)s_pAnonAuthProvider + 324) )
    {
      CloseHandle(*((HANDLE *)s_pAnonAuthProvider + 324));
      v2 = s_pAnonAuthProvider;
      *((_QWORD *)v3 + 324) = 0;
    }
    if ( *((_QWORD *)v3 + 325) )
    {
      CloseHandle(*((HANDLE *)v3 + 325));
      v2 = s_pAnonAuthProvider;
      *((_QWORD *)v3 + 325) = 0;
    }
    operator delete(v2);
    s_pAnonAuthProvider = 0;
  }
  if ( TOKEN_KEY::sm_hCryptProv )
  {
    CryptReleaseContext(TOKEN_KEY::sm_hCryptProv, 0);
    TOKEN_KEY::sm_hCryptProv = 0;
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
0x1800040c0  mov     [rsp+arg_0], rbx
0x1800040c5  push    rdi
0x1800040c6  sub     rsp, 20h
0x1800040ca  mov     rbx, rcx
0x1800040cd  mov     rcx, cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA; ANON_AUTH_PROVIDER * s_pAnonAuthProvider
0x1800040d4  test    rcx, rcx
0x1800040d7  jz      short loc_18000413A
0x1800040d9  mov     rax, [rcx+0A20h]
0x1800040e0  mov     rdi, rcx
0x1800040e3  test    rax, rax
0x1800040e6  jz      short loc_180004103
0x1800040e8  mov     rcx, rax; hObject
0x1800040eb  call    cs:__imp_CloseHandle
0x1800040f1  mov     rcx, cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA; ANON_AUTH_PROVIDER * s_pAnonAuthProvider
0x1800040f8  mov     qword ptr [rdi+0A20h], 0
0x180004103  mov     rax, [rdi+0A28h]
0x18000410a  test    rax, rax
0x18000410d  jz      short loc_18000412A
0x18000410f  mov     rcx, rax; hObject
0x180004112  call    cs:__imp_CloseHandle
0x180004118  mov     rcx, cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA; Block
0x18000411f  mov     qword ptr [rdi+0A28h], 0
0x18000412a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000412f  mov     cs:?s_pAnonAuthProvider@@3PEAVANON_AUTH_PROVIDER@@EA, 0; ANON_AUTH_PROVIDER * s_pAnonAuthProvider
0x18000413a  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x180004141  test    rcx, rcx
0x180004144  jz      short loc_180004159
0x180004146  xor     edx, edx; dwFlags
0x180004148  call    cs:__imp_CryptReleaseContext
0x18000414e  mov     cs:?sm_hCryptProv@TOKEN_KEY@@0_KA, 0; unsigned __int64 TOKEN_KEY::sm_hCryptProv
0x180004159  mov     rcx, cs:g_pDebug
0x180004160  test    rcx, rcx
0x180004163  jz      short loc_18000417B
0x180004165  cmp     dword ptr [rcx+280h], 0
0x18000416c  jz      short loc_18000417B
0x18000416e  call    cs:__imp_PuDeleteDebugPrintsObject
0x180004174  mov     cs:g_pDebug, rax
0x18000417b  test    rbx, rbx
0x18000417e  jz      short loc_180004193
0x180004180  lea     rax, ??_7CHttpModule@@6B@; const CHttpModule::`vftable'
0x180004187  mov     rcx, rbx; Block
0x18000418a  mov     [rbx+8], rax
0x18000418e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004193  mov     rbx, [rsp+28h+arg_0]
0x180004198  add     rsp, 20h
0x18000419c  pop     rdi
0x18000419d  retn
```

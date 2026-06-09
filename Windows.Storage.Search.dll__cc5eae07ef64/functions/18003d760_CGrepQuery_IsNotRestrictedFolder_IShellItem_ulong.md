# CGrepQuery::_IsNotRestrictedFolder(IShellItem *,ulong)

- ea: `0x18003d760`
- end: `0x18003d867`
- name: `?_IsNotRestrictedFolder@CGrepQuery@@AEAAHPEAUIShellItem@@K@Z`
- size: `263`
- prototype: `int(CGrepQuery *__hidden this, struct IShellItem *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18003d760`
- `0x18003d95c`
- `0x18006d260`
- `0x1800c35a4`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!__imp_SHRestricted` at `0x18003d817`
- `Windows.Storage!__imp_SHRestricted` at `0x18003d817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d7f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d7f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d83b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003d83b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18003d826`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18003d826`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall CGrepQuery::_IsNotRestrictedFolder(CGrepQuery *this, struct IShellItem *a2)
{
  struct IShellItemVtbl *lpVtbl; // rax
  bool v5; // bl
  bool v6; // si
  DWORD v8; // edi
  unsigned int DriveNumberW; // eax
  CallerIdentity *v10; // rcx
  WCHAR *v11; // [rsp+28h] [rbp-50h] BYREF
  char v12; // [rsp+30h] [rbp-48h]
  WCHAR *pv; // [rsp+88h] [rbp+10h]

  pv = 0;
  lpVtbl = a2->lpVtbl;
  v11 = 0;
  v5 = 1;
  v12 = 1;
  v6 = ((int (__fastcall *)(struct IShellItem *, __int64, WCHAR **))lpVtbl->GetDisplayName)(a2, 2147647488LL, &v11) >= 0;
  if ( v12 )
    pv = v11;
  if ( v6
    && (v8 = SHRestricted(REST_NOVIEWONDRIVE)) != 0
    && (DriveNumberW = PathGetDriveNumberW(pv), DriveNumberW != -1)
    && _bittest((const int *)&v8, DriveNumberW)
    && (CallerIdentity::_EnsureRuntimeBrokerPID(v10), GetCurrentProcessId() != CallerIdentity::g_dwRuntimeBrokerProcessId) )
  {
    v5 = 0;
  }
  else if ( (*((_DWORD *)this + 38) & 0x2000) != 0 )
  {
    v5 = (unsigned int)IsItemHiddenForPurposesOfWinRTStorageAPI(a2) == 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return v5;
}

```

## disassembly

```asm
0x18003d760  mov     r11, rsp
0x18003d763  push    rbx
0x18003d764  push    rbp
0x18003d765  push    rsi
0x18003d766  push    rdi
0x18003d767  push    r14
0x18003d769  push    r15
0x18003d76b  sub     rsp, 48h
0x18003d76f  mov     r14, rdx
0x18003d772  mov     r15, rcx
0x18003d775  mov     qword ptr [r11+10h], 0
0x18003d77d  mov     rax, [rdx]
0x18003d780  lea     rcx, [r11+10h]
0x18003d784  mov     [r11-58h], rcx
0x18003d788  mov     qword ptr [r11-50h], 0
0x18003d790  mov     bl, 1
0x18003d792  mov     [rsp+78h+var_48], bl
0x18003d796  lea     r8, [r11-50h]
0x18003d79a  mov     edx, 80028000h
0x18003d79f  mov     rcx, r14
0x18003d7a2  mov     rax, [rax+28h]
0x18003d7a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7ab  mov     esi, eax
0x18003d7ad  shr     esi, 1Fh
0x18003d7b0  xor     sil, bl
0x18003d7b3  cmp     [rsp+78h+var_48], 0
0x18003d7b8  jz      short loc_18003D7D3
0x18003d7ba  mov     rbp, [rsp+78h+var_50]
0x18003d7bf  mov     rdi, [rsp+78h+var_58]
0x18003d7c4  mov     rcx, [rdi]; pv
0x18003d7c7  test    rcx, rcx
0x18003d7ca  jnz     loc_18003D85C
0x18003d7d0  mov     [rdi], rbp
0x18003d7d3  test    sil, sil
0x18003d7d6  jnz     short loc_18003D80A
0x18003d7d8  test    dword ptr [r15+98h], 2000h
0x18003d7e3  jnz     short loc_18003D84D
0x18003d7e5  movzx   ebx, bl
0x18003d7e8  mov     rcx, [rsp+78h+pv]; pv
0x18003d7f0  test    rcx, rcx
0x18003d7f3  jz      short loc_18003D7FB
0x18003d7f5  call    cs:__imp_CoTaskMemFree
0x18003d7fb  mov     eax, ebx
0x18003d7fd  add     rsp, 48h
0x18003d801  pop     r15
0x18003d803  pop     r14
0x18003d805  pop     rdi
0x18003d806  pop     rsi
0x18003d807  pop     rbp
0x18003d808  pop     rbx
0x18003d809  retn
0x18003d80a  mov     rsi, [rsp+78h+pv]
0x18003d812  mov     ecx, 4000004Ch; rest
0x18003d817  call    cs:__imp_SHRestricted
0x18003d81d  mov     edi, eax
0x18003d81f  test    eax, eax
0x18003d821  jz      short loc_18003D7D8
0x18003d823  mov     rcx, rsi; pszPath
0x18003d826  call    cs:__imp_PathGetDriveNumberW
0x18003d82c  cmp     eax, 0FFFFFFFFh
0x18003d82f  jz      short loc_18003D7D8
0x18003d831  bt      edi, eax
0x18003d834  jnb     short loc_18003D7D8
0x18003d836  call    ?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ; CallerIdentity::_EnsureRuntimeBrokerPID(void)
0x18003d83b  call    cs:__imp_GetCurrentProcessId
0x18003d841  cmp     eax, cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x18003d847  jz      short loc_18003D7D8
0x18003d849  xor     bl, bl
0x18003d84b  jmp     short loc_18003D7E5
0x18003d84d  mov     rcx, r14; struct IShellItem *
0x18003d850  call    ?IsItemHiddenForPurposesOfWinRTStorageAPI@@YAHPEAUIShellItem@@@Z; IsItemHiddenForPurposesOfWinRTStorageAPI(IShellItem *)
0x18003d855  test    eax, eax
0x18003d857  setz    bl
0x18003d85a  jmp     short loc_18003D7E5
0x18003d85c  call    ?close_reset@?$close_invoke_helper@$00P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZPEAG@details@wil@@SAXPEAG@Z; wil::details::close_invoke_helper<1,void (*)(void *),&CoTaskMemFree(void *),ushort *>::close_reset(ushort *)
0x18003d861  jmp     loc_18003D7D0
```

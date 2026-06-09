# DllGetClassObject

- ea: `0x180003370`
- end: `0x180003446`
- name: `DllGetClassObject`
- size: `214`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001474`
- `0x180003370`
- `0x180014010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // r14
  _QWORD *v9; // rdx
  _QWORD *v10; // rdi
  __int64 v11; // rax

  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = -2147221231;
  v7 = 0;
  while ( 1 )
  {
    v8 = 2 * v7;
    v9 = (_QWORD *)*((_QWORD *)&off_180015130 + 2 * v7);
    if ( *(_QWORD *)&rclsid->Data1 == *v9 && *(_QWORD *)rclsid->Data4 == v9[1] )
      break;
    if ( ++v7 )
      return v6;
  }
  v10 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v10 )
    return -2147024882;
  v11 = *((_QWORD *)&off_180015130 + v8 + 1);
  *v10 = &CClassFactory::`vftable';
  v10[2] = v11;
  *((_DWORD *)v10 + 2) = 1;
  _InterlockedIncrement(&g_cRefModule);
  v6 = (*(__int64 (__fastcall **)(_QWORD *, const IID *const, LPVOID *))*v10)(v10, riid, ppv);
  (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
  return v6;
}

```

## disassembly

```asm
0x180003370  push    rbx
0x180003372  push    rbp
0x180003373  push    rsi
0x180003374  push    rdi
0x180003375  push    r14
0x180003377  push    r15
0x180003379  sub     rsp, 28h
0x18000337d  mov     rsi, r8
0x180003380  mov     rbp, rdx
0x180003383  mov     r8, rcx
0x180003386  test    rsi, rsi
0x180003389  jnz     short loc_180003395
0x18000338b  mov     ebx, 80004003h
0x180003390  jmp     loc_180003437
0x180003395  mov     qword ptr [rsi], 0
0x18000339c  lea     r15, off_180015130
0x1800033a3  mov     ebx, 80040111h
0x1800033a8  xor     ecx, ecx
0x1800033aa  mov     rax, [r8]
0x1800033ad  mov     r14, rcx
0x1800033b0  add     r14, r14
0x1800033b3  mov     rdx, [r15+r14*8]
0x1800033b7  cmp     rax, [rdx]
0x1800033ba  jnz     short loc_1800033C6
0x1800033bc  mov     rax, [r8+8]
0x1800033c0  cmp     rax, [rdx+8]
0x1800033c4  jz      short loc_1800033D1
0x1800033c6  inc     rcx
0x1800033c9  cmp     rcx, 1
0x1800033cd  jb      short loc_1800033AA
0x1800033cf  jmp     short loc_180003437
0x1800033d1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800033d8  mov     ecx, 18h; unsigned __int64
0x1800033dd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800033e2  mov     rdi, rax
0x1800033e5  test    rax, rax
0x1800033e8  jz      short loc_180003432
0x1800033ea  mov     rax, [r15+r14*8+8]
0x1800033ef  lea     rcx, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x1800033f6  mov     [rdi], rcx
0x1800033f9  mov     [rdi+10h], rax
0x1800033fd  mov     dword ptr [rdi+8], 1
0x180003404  lock inc cs:?g_cRefModule@@3JA; long g_cRefModule
0x18000340b  mov     rax, [rdi]
0x18000340e  mov     r8, rsi
0x180003411  mov     rdx, rbp
0x180003414  mov     rcx, rdi
0x180003417  mov     rax, [rax]
0x18000341a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000341f  mov     ebx, eax
0x180003421  mov     rcx, rdi
0x180003424  mov     rax, [rdi]
0x180003427  mov     rax, [rax+10h]
0x18000342b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003430  jmp     short loc_180003437
0x180003432  mov     ebx, 8007000Eh
0x180003437  mov     eax, ebx
0x180003439  add     rsp, 28h
0x18000343d  pop     r15
0x18000343f  pop     r14
0x180003441  pop     rdi
0x180003442  pop     rsi
0x180003443  pop     rbp
0x180003444  pop     rbx
0x180003445  retn
```

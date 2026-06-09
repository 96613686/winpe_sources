# DllGetClassObject

- ea: `0x180002e50`
- end: `0x180002f00`
- name: `DllGetClassObject`
- size: `176`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001ce0`
- `0x180002e50`
- `0x180009010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  _DWORD *v7; // rax
  _DWORD *v8; // rdi

  if ( !ppv )
    return -2147024809;
  *ppv = 0;
  v6 = -2147221231;
  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_ProfileNotifyHandler )
  {
    v6 = -2147024882;
    v7 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    if ( v7 )
    {
      ++g_cRefDll;
      *(_QWORD *)v7 = &CClassFactory::`vftable';
      v7[2] = 1;
      *((_QWORD *)v7 + 2) = CProfileNotifyHandler_CreateInstance;
      v6 = ((__int64 (__fastcall *)(_DWORD *, const IID *const, LPVOID *))CClassFactory::`vftable')(v7, riid, ppv);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180002e50  push    rbx
0x180002e52  push    rbp
0x180002e53  push    rsi
0x180002e54  push    rdi
0x180002e55  sub     rsp, 28h
0x180002e59  mov     rsi, r8
0x180002e5c  mov     rbp, rdx
0x180002e5f  test    r8, r8
0x180002e62  jnz     short loc_180002E6E
0x180002e64  mov     eax, 80070057h
0x180002e69  jmp     loc_180002EF7
0x180002e6e  mov     qword ptr [r8], 0
0x180002e75  mov     ebx, 80040111h
0x180002e7a  mov     rax, [rcx]
0x180002e7d  cmp     rax, qword ptr cs:CLSID_ProfileNotifyHandler.Data1
0x180002e84  jnz     short loc_180002EF5
0x180002e86  mov     rax, [rcx+8]
0x180002e8a  cmp     rax, qword ptr cs:CLSID_ProfileNotifyHandler.Data4
0x180002e91  jnz     short loc_180002EF5
0x180002e93  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002e9a  mov     ecx, 18h; unsigned __int64
0x180002e9f  mov     ebx, 8007000Eh
0x180002ea4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002ea9  mov     rdi, rax
0x180002eac  test    rax, rax
0x180002eaf  jz      short loc_180002EF5
0x180002eb1  inc     cs:?g_cRefDll@@3JA; long g_cRefDll
0x180002eb7  lea     r9, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180002ebe  mov     [rax], r9
0x180002ec1  mov     r8, rsi
0x180002ec4  mov     dword ptr [rax+8], 1
0x180002ecb  mov     rdx, rbp
0x180002ece  lea     rax, ?CProfileNotifyHandler_CreateInstance@@YAJAEBU_GUID@@PEAPEAX@Z; CProfileNotifyHandler_CreateInstance(_GUID const &,void * *)
0x180002ed5  mov     rcx, rdi
0x180002ed8  mov     [rdi+10h], rax
0x180002edc  mov     rax, [r9]
0x180002edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee4  mov     rcx, [rdi]
0x180002ee7  mov     ebx, eax
0x180002ee9  mov     rax, [rcx+10h]
0x180002eed  mov     rcx, rdi
0x180002ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef5  mov     eax, ebx
0x180002ef7  add     rsp, 28h
0x180002efb  pop     rdi
0x180002efc  pop     rsi
0x180002efd  pop     rbp
0x180002efe  pop     rbx
0x180002eff  retn
```

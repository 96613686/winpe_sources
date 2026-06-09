# DllGetClassObject

- ea: `0x180002780`
- end: `0x18000281e`
- name: `DllGetClassObject`
- size: `158`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001064`
- `0x180002780`
- `0x180009010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v5; // edi
  _DWORD *v6; // rax
  _DWORD *v7; // rbx

  *ppv = 0;
  v5 = -2147221231;
  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_HotPlug )
  {
    v5 = -2147024882;
    v6 = operator new(0x18u);
    v7 = v6;
    if ( v6 )
    {
      v6[2] = 1;
      *(_QWORD *)v6 = &CClassFactory::`vftable';
      *((_QWORD *)v6 + 2) = CHotPlug_CreateInstance;
      _InterlockedIncrement(&g_cLocks);
      v5 = (**(__int64 (__fastcall ***)(void *, const IID *const, LPVOID *))v6)(v6, riid, ppv);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180002780  push    rbx
0x180002782  push    rbp
0x180002783  push    rsi
0x180002784  push    rdi
0x180002785  sub     rsp, 28h
0x180002789  mov     qword ptr [r8], 0
0x180002790  mov     rsi, r8
0x180002793  mov     rax, [rcx]
0x180002796  mov     rbp, rdx
0x180002799  cmp     rax, qword ptr cs:CLSID_HotPlug.Data1
0x1800027a0  mov     edi, 80040111h
0x1800027a5  jnz     short loc_180002813
0x1800027a7  mov     rax, [rcx+8]
0x1800027ab  cmp     rax, qword ptr cs:CLSID_HotPlug.Data4
0x1800027b2  jnz     short loc_180002813
0x1800027b4  mov     ecx, 18h; Size
0x1800027b9  mov     edi, 8007000Eh
0x1800027be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800027c3  mov     rbx, rax
0x1800027c6  test    rax, rax
0x1800027c9  jz      short loc_180002813
0x1800027cb  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x1800027d2  mov     dword ptr [rbx+8], 1
0x1800027d9  mov     [rbx], rax
0x1800027dc  lea     rax, CHotPlug_CreateInstance
0x1800027e3  mov     [rbx+10h], rax
0x1800027e7  lock inc cs:?g_cLocks@@3JA; long g_cLocks
0x1800027ee  mov     rax, [rbx]
0x1800027f1  mov     r8, rsi
0x1800027f4  mov     rdx, rbp
0x1800027f7  mov     rcx, rbx
0x1800027fa  mov     rax, [rax]
0x1800027fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002802  mov     rcx, [rbx]
0x180002805  mov     edi, eax
0x180002807  mov     rax, [rcx+10h]
0x18000280b  mov     rcx, rbx
0x18000280e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002813  mov     eax, edi
0x180002815  add     rsp, 28h
0x180002819  pop     rdi
0x18000281a  pop     rsi
0x18000281b  pop     rbp
0x18000281c  pop     rbx
0x18000281d  retn
```

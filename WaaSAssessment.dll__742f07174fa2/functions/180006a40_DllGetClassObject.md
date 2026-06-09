# DllGetClassObject

- ea: `0x180006a40`
- end: `0x180006b38`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003da8`
- `0x180006a40`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006aee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006aee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ac3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ac3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const IID *v5; // rbp
  HRESULT v6; // edi
  __int64 v7; // rbx
  const IID *const *v8; // r14

  v5 = rclsid;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v6 = 0;
  v7 = qword_180027D28;
  if ( qword_180027D28 )
  {
    while ( *(_QWORD *)v7 )
    {
      if ( *(_QWORD *)(v7 + 16) )
      {
        rclsid = *(const IID *const *)v7;
        if ( v5->Data1 == **(_DWORD **)v7
          && *(_DWORD *)&v5->Data2 == *(_DWORD *)&rclsid->Data2
          && *(_DWORD *)v5->Data4 == *(_DWORD *)rclsid->Data4
          && *(_DWORD *)&v5->Data4[4] == *(_DWORD *)&rclsid->Data4[4] )
        {
          v8 = (const IID *const *)(v7 + 32);
          if ( !*(_QWORD *)(v7 + 32) )
          {
            EnterCriticalSection(&stru_1800270E0);
            if ( !*v8 )
              v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                     *(_QWORD *)(v7 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v7 + 32);
            LeaveCriticalSection(&stru_1800270E0);
          }
          rclsid = *v8;
          if ( *v8 )
            v6 = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(
                   rclsid,
                   riid,
                   ppv);
          break;
        }
      }
      v7 += 72;
    }
  }
  if ( !*ppv && !v6 )
    return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
  return v6;
}

```

## disassembly

```asm
0x180006a40  push    rbx
0x180006a42  push    rbp
0x180006a43  push    rsi
0x180006a44  push    rdi
0x180006a45  push    r14
0x180006a47  push    r15
0x180006a49  sub     rsp, 28h
0x180006a4d  mov     rsi, r8
0x180006a50  mov     r15, rdx
0x180006a53  mov     rbp, rcx
0x180006a56  test    r8, r8
0x180006a59  jnz     short loc_180006A65
0x180006a5b  mov     edi, 80004003h
0x180006a60  jmp     loc_180006B29
0x180006a65  mov     qword ptr [r8], 0
0x180006a6c  xor     edi, edi
0x180006a6e  mov     rbx, cs:qword_180027D28
0x180006a75  test    rbx, rbx
0x180006a78  jz      loc_180006B0F
0x180006a7e  jmp     short loc_180006AAC
0x180006a80  cmp     [rbx+10h], rdi
0x180006a84  jz      short loc_180006AA8
0x180006a86  mov     rcx, [rbx]
0x180006a89  mov     eax, [rcx]
0x180006a8b  cmp     [rbp+0], eax
0x180006a8e  jnz     short loc_180006AA8
0x180006a90  mov     eax, [rcx+4]
0x180006a93  cmp     [rbp+4], eax
0x180006a96  jnz     short loc_180006AA8
0x180006a98  mov     eax, [rcx+8]
0x180006a9b  cmp     [rbp+8], eax
0x180006a9e  jnz     short loc_180006AA8
0x180006aa0  mov     eax, [rcx+0Ch]
0x180006aa3  cmp     [rbp+0Ch], eax
0x180006aa6  jz      short loc_180006AB3
0x180006aa8  add     rbx, 48h ; 'H'
0x180006aac  cmp     [rbx], rdi
0x180006aaf  jnz     short loc_180006A80
0x180006ab1  jmp     short loc_180006B0F
0x180006ab3  lea     r14, [rbx+20h]
0x180006ab7  cmp     [r14], rdi
0x180006aba  jnz     short loc_180006AF4
0x180006abc  lea     rcx, stru_1800270E0; lpCriticalSection
0x180006ac3  call    cs:__imp_EnterCriticalSection
0x180006ac9  cmp     [r14], rdi
0x180006acc  jnz     short loc_180006AE7
0x180006ace  mov     r8, r14
0x180006ad1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180006ad8  mov     rcx, [rbx+18h]
0x180006adc  mov     rax, [rbx+10h]
0x180006ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae5  mov     edi, eax
0x180006ae7  lea     rcx, stru_1800270E0; lpCriticalSection
0x180006aee  call    cs:__imp_LeaveCriticalSection
0x180006af4  mov     rcx, [r14]
0x180006af7  test    rcx, rcx
0x180006afa  jz      short loc_180006B0F
0x180006afc  mov     rax, [rcx]
0x180006aff  mov     r8, rsi
0x180006b02  mov     rdx, r15
0x180006b05  mov     rax, [rax]
0x180006b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0d  mov     edi, eax
0x180006b0f  cmp     qword ptr [rsi], 0
0x180006b13  jnz     short loc_180006B29
0x180006b15  test    edi, edi
0x180006b17  jnz     short loc_180006B29
0x180006b19  mov     r9, rsi; void **
0x180006b1c  mov     r8, r15; struct _GUID *
0x180006b1f  mov     rdx, rbp; struct _GUID *
0x180006b22  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180006b27  mov     edi, eax
0x180006b29  mov     eax, edi
0x180006b2b  add     rsp, 28h
0x180006b2f  pop     r15
0x180006b31  pop     r14
0x180006b33  pop     rdi
0x180006b34  pop     rsi
0x180006b35  pop     rbp
0x180006b36  pop     rbx
0x180006b37  retn
```

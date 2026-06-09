# DllGetClassObject

- ea: `0x180007320`
- end: `0x180007418`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004cf8`
- `0x180007320`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800073ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073a3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800073a3`

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
  v7 = qword_18000F378;
  if ( qword_18000F378 )
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
            EnterCriticalSection(&CriticalSection);
            if ( !*v8 )
              v6 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                     *(_QWORD *)(v7 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v7 + 32);
            LeaveCriticalSection(&CriticalSection);
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
0x180007320  push    rbx
0x180007322  push    rbp
0x180007323  push    rsi
0x180007324  push    rdi
0x180007325  push    r14
0x180007327  push    r15
0x180007329  sub     rsp, 28h
0x18000732d  mov     rsi, r8
0x180007330  mov     r15, rdx
0x180007333  mov     rbp, rcx
0x180007336  test    r8, r8
0x180007339  jnz     short loc_180007345
0x18000733b  mov     edi, 80004003h
0x180007340  jmp     loc_180007409
0x180007345  mov     qword ptr [r8], 0
0x18000734c  xor     edi, edi
0x18000734e  mov     rbx, cs:qword_18000F378
0x180007355  test    rbx, rbx
0x180007358  jz      loc_1800073EF
0x18000735e  jmp     short loc_18000738C
0x180007360  cmp     [rbx+10h], rdi
0x180007364  jz      short loc_180007388
0x180007366  mov     rcx, [rbx]
0x180007369  mov     eax, [rcx]
0x18000736b  cmp     [rbp+0], eax
0x18000736e  jnz     short loc_180007388
0x180007370  mov     eax, [rcx+4]
0x180007373  cmp     [rbp+4], eax
0x180007376  jnz     short loc_180007388
0x180007378  mov     eax, [rcx+8]
0x18000737b  cmp     [rbp+8], eax
0x18000737e  jnz     short loc_180007388
0x180007380  mov     eax, [rcx+0Ch]
0x180007383  cmp     [rbp+0Ch], eax
0x180007386  jz      short loc_180007393
0x180007388  add     rbx, 48h ; 'H'
0x18000738c  cmp     [rbx], rdi
0x18000738f  jnz     short loc_180007360
0x180007391  jmp     short loc_1800073EF
0x180007393  lea     r14, [rbx+20h]
0x180007397  cmp     [r14], rdi
0x18000739a  jnz     short loc_1800073D4
0x18000739c  lea     rcx, CriticalSection; lpCriticalSection
0x1800073a3  call    cs:__imp_EnterCriticalSection
0x1800073a9  cmp     [r14], rdi
0x1800073ac  jnz     short loc_1800073C7
0x1800073ae  mov     r8, r14
0x1800073b1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800073b8  mov     rcx, [rbx+18h]
0x1800073bc  mov     rax, [rbx+10h]
0x1800073c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c5  mov     edi, eax
0x1800073c7  lea     rcx, CriticalSection; lpCriticalSection
0x1800073ce  call    cs:__imp_LeaveCriticalSection
0x1800073d4  mov     rcx, [r14]
0x1800073d7  test    rcx, rcx
0x1800073da  jz      short loc_1800073EF
0x1800073dc  mov     rax, [rcx]
0x1800073df  mov     r8, rsi
0x1800073e2  mov     rdx, r15
0x1800073e5  mov     rax, [rax]
0x1800073e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ed  mov     edi, eax
0x1800073ef  cmp     qword ptr [rsi], 0
0x1800073f3  jnz     short loc_180007409
0x1800073f5  test    edi, edi
0x1800073f7  jnz     short loc_180007409
0x1800073f9  mov     r9, rsi; void **
0x1800073fc  mov     r8, r15; struct _GUID *
0x1800073ff  mov     rdx, rbp; struct _GUID *
0x180007402  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180007407  mov     edi, eax
0x180007409  mov     eax, edi
0x18000740b  add     rsp, 28h
0x18000740f  pop     r15
0x180007411  pop     r14
0x180007413  pop     rdi
0x180007414  pop     rsi
0x180007415  pop     rbp
0x180007416  pop     rbx
0x180007417  retn
```

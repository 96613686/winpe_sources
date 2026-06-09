# DllGetClassObject

- ea: `0x1800226f0`
- end: `0x1800227e8`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001fb68`
- `0x1800226f0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022773`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022773`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002279e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002279e`

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
  v7 = qword_1800353C8;
  if ( qword_1800353C8 )
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
0x1800226f0  push    rbx
0x1800226f2  push    rbp
0x1800226f3  push    rsi
0x1800226f4  push    rdi
0x1800226f5  push    r14
0x1800226f7  push    r15
0x1800226f9  sub     rsp, 28h
0x1800226fd  mov     rsi, r8
0x180022700  mov     r15, rdx
0x180022703  mov     rbp, rcx
0x180022706  test    r8, r8
0x180022709  jnz     short loc_180022715
0x18002270b  mov     edi, 80004003h
0x180022710  jmp     loc_1800227D9
0x180022715  mov     qword ptr [r8], 0
0x18002271c  xor     edi, edi
0x18002271e  mov     rbx, cs:qword_1800353C8
0x180022725  test    rbx, rbx
0x180022728  jz      loc_1800227BF
0x18002272e  jmp     short loc_18002275C
0x180022730  cmp     [rbx+10h], rdi
0x180022734  jz      short loc_180022758
0x180022736  mov     rcx, [rbx]
0x180022739  mov     eax, [rcx]
0x18002273b  cmp     [rbp+0], eax
0x18002273e  jnz     short loc_180022758
0x180022740  mov     eax, [rcx+4]
0x180022743  cmp     [rbp+4], eax
0x180022746  jnz     short loc_180022758
0x180022748  mov     eax, [rcx+8]
0x18002274b  cmp     [rbp+8], eax
0x18002274e  jnz     short loc_180022758
0x180022750  mov     eax, [rcx+0Ch]
0x180022753  cmp     [rbp+0Ch], eax
0x180022756  jz      short loc_180022763
0x180022758  add     rbx, 48h ; 'H'
0x18002275c  cmp     [rbx], rdi
0x18002275f  jnz     short loc_180022730
0x180022761  jmp     short loc_1800227BF
0x180022763  lea     r14, [rbx+20h]
0x180022767  cmp     [r14], rdi
0x18002276a  jnz     short loc_1800227A4
0x18002276c  lea     rcx, CriticalSection; lpCriticalSection
0x180022773  call    cs:__imp_EnterCriticalSection
0x180022779  cmp     [r14], rdi
0x18002277c  jnz     short loc_180022797
0x18002277e  mov     r8, r14
0x180022781  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180022788  mov     rcx, [rbx+18h]
0x18002278c  mov     rax, [rbx+10h]
0x180022790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022795  mov     edi, eax
0x180022797  lea     rcx, CriticalSection; lpCriticalSection
0x18002279e  call    cs:__imp_LeaveCriticalSection
0x1800227a4  mov     rcx, [r14]
0x1800227a7  test    rcx, rcx
0x1800227aa  jz      short loc_1800227BF
0x1800227ac  mov     rax, [rcx]
0x1800227af  mov     r8, rsi
0x1800227b2  mov     rdx, r15
0x1800227b5  mov     rax, [rax]
0x1800227b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227bd  mov     edi, eax
0x1800227bf  cmp     qword ptr [rsi], 0
0x1800227c3  jnz     short loc_1800227D9
0x1800227c5  test    edi, edi
0x1800227c7  jnz     short loc_1800227D9
0x1800227c9  mov     r9, rsi; void **
0x1800227cc  mov     r8, r15; struct _GUID *
0x1800227cf  mov     rdx, rbp; struct _GUID *
0x1800227d2  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800227d7  mov     edi, eax
0x1800227d9  mov     eax, edi
0x1800227db  add     rsp, 28h
0x1800227df  pop     r15
0x1800227e1  pop     r14
0x1800227e3  pop     rdi
0x1800227e4  pop     rsi
0x1800227e5  pop     rbp
0x1800227e6  pop     rbx
0x1800227e7  retn
```

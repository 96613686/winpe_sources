# DllGetClassObject

- ea: `0x180007110`
- end: `0x180007208`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003608`
- `0x180007110`
- `0x18000d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800071be`
- `KERNEL32!LeaveCriticalSection` at `0x1800071be`
- `KERNEL32!EnterCriticalSection` at `0x180007193`
- `KERNEL32!EnterCriticalSection` at `0x180007193`

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
  v7 = qword_1800128E8;
  if ( qword_1800128E8 )
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
0x180007110  push    rbx
0x180007112  push    rbp
0x180007113  push    rsi
0x180007114  push    rdi
0x180007115  push    r14
0x180007117  push    r15
0x180007119  sub     rsp, 28h
0x18000711d  mov     rsi, r8
0x180007120  mov     r15, rdx
0x180007123  mov     rbp, rcx
0x180007126  test    r8, r8
0x180007129  jnz     short loc_180007135
0x18000712b  mov     edi, 80004003h
0x180007130  jmp     loc_1800071F9
0x180007135  mov     qword ptr [r8], 0
0x18000713c  xor     edi, edi
0x18000713e  mov     rbx, cs:qword_1800128E8
0x180007145  test    rbx, rbx
0x180007148  jz      loc_1800071DF
0x18000714e  jmp     short loc_18000717C
0x180007150  cmp     [rbx+10h], rdi
0x180007154  jz      short loc_180007178
0x180007156  mov     rcx, [rbx]
0x180007159  mov     eax, [rcx]
0x18000715b  cmp     [rbp+0], eax
0x18000715e  jnz     short loc_180007178
0x180007160  mov     eax, [rcx+4]
0x180007163  cmp     [rbp+4], eax
0x180007166  jnz     short loc_180007178
0x180007168  mov     eax, [rcx+8]
0x18000716b  cmp     [rbp+8], eax
0x18000716e  jnz     short loc_180007178
0x180007170  mov     eax, [rcx+0Ch]
0x180007173  cmp     [rbp+0Ch], eax
0x180007176  jz      short loc_180007183
0x180007178  add     rbx, 48h ; 'H'
0x18000717c  cmp     [rbx], rdi
0x18000717f  jnz     short loc_180007150
0x180007181  jmp     short loc_1800071DF
0x180007183  lea     r14, [rbx+20h]
0x180007187  cmp     [r14], rdi
0x18000718a  jnz     short loc_1800071C4
0x18000718c  lea     rcx, CriticalSection; lpCriticalSection
0x180007193  call    cs:__imp_EnterCriticalSection
0x180007199  cmp     [r14], rdi
0x18000719c  jnz     short loc_1800071B7
0x18000719e  mov     r8, r14
0x1800071a1  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800071a8  mov     rcx, [rbx+18h]
0x1800071ac  mov     rax, [rbx+10h]
0x1800071b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071b5  mov     edi, eax
0x1800071b7  lea     rcx, CriticalSection; lpCriticalSection
0x1800071be  call    cs:__imp_LeaveCriticalSection
0x1800071c4  mov     rcx, [r14]
0x1800071c7  test    rcx, rcx
0x1800071ca  jz      short loc_1800071DF
0x1800071cc  mov     rax, [rcx]
0x1800071cf  mov     r8, rsi
0x1800071d2  mov     rdx, r15
0x1800071d5  mov     rax, [rax]
0x1800071d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071dd  mov     edi, eax
0x1800071df  cmp     qword ptr [rsi], 0
0x1800071e3  jnz     short loc_1800071F9
0x1800071e5  test    edi, edi
0x1800071e7  jnz     short loc_1800071F9
0x1800071e9  mov     r9, rsi; void **
0x1800071ec  mov     r8, r15; struct _GUID *
0x1800071ef  mov     rdx, rbp; struct _GUID *
0x1800071f2  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800071f7  mov     edi, eax
0x1800071f9  mov     eax, edi
0x1800071fb  add     rsp, 28h
0x1800071ff  pop     r15
0x180007201  pop     r14
0x180007203  pop     rdi
0x180007204  pop     rsi
0x180007205  pop     rbp
0x180007206  pop     rbx
0x180007207  retn
```

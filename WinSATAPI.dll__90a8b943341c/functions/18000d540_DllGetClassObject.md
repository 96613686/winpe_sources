# DllGetClassObject

- ea: `0x18000d540`
- end: `0x18000d652`
- name: `DllGetClassObject`
- size: `274`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000d540`
- `0x18000e380`
- `0x180014204`
- `0x1800155f8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d5c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d5c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID *v5; // rdi
  HRESULT v7; // ebp
  __int64 v8; // r14
  _RTL_CRITICAL_SECTION *v9; // [rsp+28h] [rbp-30h] BYREF
  char v10; // [rsp+30h] [rbp-28h]

  v5 = rclsid;
  if ( !ppv )
    return -2147467261;
  v7 = 0;
  *ppv = 0;
  v8 = qword_18004BDB8;
  if ( qword_18004BDB8 )
  {
    while ( *(_QWORD *)v8 )
    {
      if ( *(_QWORD *)(v8 + 16) && (unsigned int)InlineIsEqualGUID(v5, *(_QWORD *)v8) )
      {
        if ( !*(_QWORD *)(v8 + 32) )
        {
          v9 = &stru_18004A3F0;
          EnterCriticalSection(&stru_18004A3F0);
          v10 = 1;
          if ( !*(_QWORD *)(v8 + 32) )
            v7 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v8 + 16))(
                   *(_QWORD *)(v8 + 24),
                   &GUID_00000000_0000_0000_c000_000000000046,
                   v8 + 32);
          ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v9);
        }
        rclsid = *(const IID *const *)(v8 + 32);
        if ( rclsid )
          v7 = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(
                 rclsid,
                 riid,
                 ppv);
        break;
      }
      v8 += 72;
    }
  }
  if ( !*ppv && !v7 )
    return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
  return v7;
}

```

## disassembly

```asm
0x18000d540  push    rdi
0x18000d542  push    r14
0x18000d544  push    r15
0x18000d546  sub     rsp, 40h
0x18000d54a  mov     [rsp+58h+var_38], 0FFFFFFFFFFFFFFFEh
0x18000d553  mov     [rsp+58h+arg_0], rbx
0x18000d558  mov     [rsp+58h+arg_8], rbp
0x18000d55d  mov     [rsp+58h+arg_10], rsi
0x18000d562  mov     rbx, r8
0x18000d565  mov     rsi, rdx
0x18000d568  mov     rdi, rcx
0x18000d56b  test    r8, r8
0x18000d56e  jnz     short loc_18000D57A
0x18000d570  mov     eax, 80004003h
0x18000d575  jmp     loc_18000D638
0x18000d57a  xor     ebp, ebp
0x18000d57c  mov     [r8], rbp
0x18000d57f  mov     r14, cs:qword_18004BDB8
0x18000d586  test    r14, r14
0x18000d589  jz      loc_18000D61C
0x18000d58f  mov     rdx, [r14]
0x18000d592  test    rdx, rdx
0x18000d595  jz      loc_18000D61C
0x18000d59b  cmp     [r14+10h], rbp
0x18000d59f  jz      short loc_18000D5AD
0x18000d5a1  mov     rcx, rdi
0x18000d5a4  call    InlineIsEqualGUID
0x18000d5a9  test    eax, eax
0x18000d5ab  jnz     short loc_18000D5B3
0x18000d5ad  add     r14, 48h ; 'H'
0x18000d5b1  jmp     short loc_18000D58F
0x18000d5b3  cmp     [r14+20h], rbp
0x18000d5b7  jnz     short loc_18000D600
0x18000d5b9  lea     rcx, stru_18004A3F0; lpCriticalSection
0x18000d5c0  mov     [rsp+58h+var_30], rcx
0x18000d5c5  call    cs:__imp_EnterCriticalSection
0x18000d5cc  nop     dword ptr [rax+rax+00h]
0x18000d5d1  mov     [rsp+58h+var_28], 1
0x18000d5d6  cmp     [r14+20h], rbp
0x18000d5da  jnz     short loc_18000D5F6
0x18000d5dc  lea     r8, [r14+20h]
0x18000d5e0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000d5e7  mov     rcx, [r14+18h]
0x18000d5eb  mov     rax, [r14+10h]
0x18000d5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5f4  mov     ebp, eax
0x18000d5f6  lea     rcx, [rsp+58h+var_30]
0x18000d5fb  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000d600  mov     rcx, [r14+20h]
0x18000d604  test    rcx, rcx
0x18000d607  jz      short loc_18000D61C
0x18000d609  mov     rax, [rcx]
0x18000d60c  mov     r8, rbx
0x18000d60f  mov     rdx, rsi
0x18000d612  mov     rax, [rax]
0x18000d615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d61a  mov     ebp, eax
0x18000d61c  cmp     qword ptr [rbx], 0
0x18000d620  jnz     short loc_18000D636
0x18000d622  test    ebp, ebp
0x18000d624  jnz     short loc_18000D636
0x18000d626  mov     r9, rbx; void **
0x18000d629  mov     r8, rsi; struct _GUID *
0x18000d62c  mov     rdx, rdi; struct _GUID *
0x18000d62f  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000d634  mov     ebp, eax
0x18000d636  mov     eax, ebp
0x18000d638  mov     rbx, [rsp+58h+arg_0]
0x18000d63d  mov     rbp, [rsp+58h+arg_8]
0x18000d642  mov     rsi, [rsp+58h+arg_10]
0x18000d647  add     rsp, 40h
0x18000d64b  pop     r15
0x18000d64d  pop     r14
0x18000d64f  pop     rdi
0x18000d650  retn
```

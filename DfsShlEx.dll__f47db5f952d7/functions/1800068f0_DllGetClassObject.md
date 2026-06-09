# DllGetClassObject

- ea: `0x1800068f0`
- end: `0x1800069e8`
- name: `DllGetClassObject`
- size: `248`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000398c`
- `0x1800068f0`
- `0x18000c010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006973`
- `KERNEL32!EnterCriticalSection` at `0x180006973`
- `KERNEL32!LeaveCriticalSection` at `0x18000699e`
- `KERNEL32!LeaveCriticalSection` at `0x18000699e`

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
  v7 = qword_180013A08;
  if ( qword_180013A08 )
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
0x1800068f0  push    rbx
0x1800068f2  push    rbp
0x1800068f3  push    rsi
0x1800068f4  push    rdi
0x1800068f5  push    r14
0x1800068f7  push    r15
0x1800068f9  sub     rsp, 28h
0x1800068fd  mov     rsi, r8
0x180006900  mov     r15, rdx
0x180006903  mov     rbp, rcx
0x180006906  test    r8, r8
0x180006909  jnz     short loc_180006915
0x18000690b  mov     edi, 80004003h
0x180006910  jmp     loc_1800069D9
0x180006915  mov     qword ptr [r8], 0
0x18000691c  xor     edi, edi
0x18000691e  mov     rbx, cs:qword_180013A08
0x180006925  test    rbx, rbx
0x180006928  jz      loc_1800069BF
0x18000692e  jmp     short loc_18000695C
0x180006930  cmp     [rbx+10h], rdi
0x180006934  jz      short loc_180006958
0x180006936  mov     rcx, [rbx]
0x180006939  mov     eax, [rcx]
0x18000693b  cmp     [rbp+0], eax
0x18000693e  jnz     short loc_180006958
0x180006940  mov     eax, [rcx+4]
0x180006943  cmp     [rbp+4], eax
0x180006946  jnz     short loc_180006958
0x180006948  mov     eax, [rcx+8]
0x18000694b  cmp     [rbp+8], eax
0x18000694e  jnz     short loc_180006958
0x180006950  mov     eax, [rcx+0Ch]
0x180006953  cmp     [rbp+0Ch], eax
0x180006956  jz      short loc_180006963
0x180006958  add     rbx, 48h ; 'H'
0x18000695c  cmp     [rbx], rdi
0x18000695f  jnz     short loc_180006930
0x180006961  jmp     short loc_1800069BF
0x180006963  lea     r14, [rbx+20h]
0x180006967  cmp     [r14], rdi
0x18000696a  jnz     short loc_1800069A4
0x18000696c  lea     rcx, CriticalSection; lpCriticalSection
0x180006973  call    cs:__imp_EnterCriticalSection
0x180006979  cmp     [r14], rdi
0x18000697c  jnz     short loc_180006997
0x18000697e  mov     r8, r14
0x180006981  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180006988  mov     rcx, [rbx+18h]
0x18000698c  mov     rax, [rbx+10h]
0x180006990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006995  mov     edi, eax
0x180006997  lea     rcx, CriticalSection; lpCriticalSection
0x18000699e  call    cs:__imp_LeaveCriticalSection
0x1800069a4  mov     rcx, [r14]
0x1800069a7  test    rcx, rcx
0x1800069aa  jz      short loc_1800069BF
0x1800069ac  mov     rax, [rcx]
0x1800069af  mov     r8, rsi
0x1800069b2  mov     rdx, r15
0x1800069b5  mov     rax, [rax]
0x1800069b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069bd  mov     edi, eax
0x1800069bf  cmp     qword ptr [rsi], 0
0x1800069c3  jnz     short loc_1800069D9
0x1800069c5  test    edi, edi
0x1800069c7  jnz     short loc_1800069D9
0x1800069c9  mov     r9, rsi; void **
0x1800069cc  mov     r8, r15; struct _GUID *
0x1800069cf  mov     rdx, rbp; struct _GUID *
0x1800069d2  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800069d7  mov     edi, eax
0x1800069d9  mov     eax, edi
0x1800069db  add     rsp, 28h
0x1800069df  pop     r15
0x1800069e1  pop     r14
0x1800069e3  pop     rdi
0x1800069e4  pop     rsi
0x1800069e5  pop     rbp
0x1800069e6  pop     rbx
0x1800069e7  retn
```

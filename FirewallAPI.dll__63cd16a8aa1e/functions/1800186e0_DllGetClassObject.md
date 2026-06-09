# DllGetClassObject

- ea: `0x1800186e0`
- end: `0x180018825`
- name: `DllGetClassObject`
- size: `325`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800186e0`
- `0x18002afa0`
- `0x18005e010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180018818`
- `RPCRT4!NdrDllGetClassObject` at `0x180018818`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001878b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001878b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001879d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001879d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const IID *v5; // rbp
  HRESULT ClassObject; // ebx
  __int64 v7; // rdi
  const IID *const *v8; // r14
  const PCInterfaceStubVtblList *pStubVtblList; // rcx
  const CLSID *pclsid; // rcx

  v5 = rclsid;
  if ( ppv )
  {
    *ppv = 0;
    ClassObject = 0;
    v7 = qword_180098068;
    if ( qword_180098068 )
    {
      while ( 1 )
      {
        rclsid = *(const IID *const *)v7;
        if ( !*(_QWORD *)v7 )
          break;
        if ( *(_QWORD *)(v7 + 16)
          && v5->Data1 == rclsid->Data1
          && *(_DWORD *)&v5->Data2 == *(_DWORD *)&rclsid->Data2
          && *(_DWORD *)v5->Data4 == *(_DWORD *)rclsid->Data4
          && *(_DWORD *)&v5->Data4[4] == *(_DWORD *)&rclsid->Data4[4] )
        {
          v8 = (const IID *const *)(v7 + 32);
          if ( !*(_QWORD *)(v7 + 32) )
          {
            EnterCriticalSection(&stru_1800980F0);
            if ( !*v8 )
              ClassObject = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v7 + 16))(
                              *(_QWORD *)(v7 + 24),
                              &GUID_00000000_0000_0000_c000_000000000046,
                              v7 + 32);
            LeaveCriticalSection(&stru_1800980F0);
          }
          rclsid = *v8;
          if ( *v8 )
            ClassObject = (**(__int64 (__fastcall ***)(const IID *const, const IID *const, LPVOID *))&rclsid->Data1)(
                            rclsid,
                            riid,
                            ppv);
          break;
        }
        v7 += 72;
      }
    }
    if ( !*ppv && !ClassObject )
      ClassObject = ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)rclsid, v5, riid, ppv);
  }
  else
  {
    ClassObject = -2147467261;
  }
  if ( ClassObject < 0 )
  {
    pStubVtblList = aProxyFileList->pStubVtblList;
    if ( *pStubVtblList )
      pclsid = **(const CLSID ***)pStubVtblList;
    else
      pclsid = 0;
    return NdrDllGetClassObject(v5, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory);
  }
  return ClassObject;
}

```

## disassembly

```asm
0x1800186e0  push    rbx
0x1800186e2  push    rbp
0x1800186e3  push    rsi
0x1800186e4  push    rdi
0x1800186e5  push    r14
0x1800186e7  push    r15
0x1800186e9  sub     rsp, 38h
0x1800186ed  mov     rsi, r8
0x1800186f0  mov     r15, rdx
0x1800186f3  mov     rbp, rcx
0x1800186f6  test    r8, r8
0x1800186f9  jz      loc_1800187A5
0x1800186ff  mov     qword ptr [r8], 0
0x180018706  xor     ebx, ebx
0x180018708  mov     rdi, cs:qword_180098068
0x18001870f  test    rdi, rdi
0x180018712  jz      short loc_18001876B
0x180018714  mov     rcx, [rdi]
0x180018717  test    rcx, rcx
0x18001871a  jz      short loc_18001876B
0x18001871c  cmp     [rdi+10h], rbx
0x180018720  jz      short loc_180018729
0x180018722  mov     eax, [rcx]
0x180018724  cmp     [rbp+0], eax
0x180018727  jz      short loc_18001872F
0x180018729  add     rdi, 48h ; 'H'
0x18001872d  jmp     short loc_180018714
0x18001872f  mov     eax, [rcx+4]
0x180018732  cmp     [rbp+4], eax
0x180018735  jnz     short loc_180018729
0x180018737  mov     eax, [rcx+8]
0x18001873a  cmp     [rbp+8], eax
0x18001873d  jnz     short loc_180018729
0x18001873f  mov     eax, [rcx+0Ch]
0x180018742  cmp     [rbp+0Ch], eax
0x180018745  jnz     short loc_180018729
0x180018747  lea     r14, [rdi+20h]
0x18001874b  cmp     [r14], rbx
0x18001874e  jz      short loc_180018784
0x180018750  mov     rcx, [r14]
0x180018753  test    rcx, rcx
0x180018756  jz      short loc_18001876B
0x180018758  mov     rax, [rcx]
0x18001875b  mov     r8, rsi
0x18001875e  mov     rdx, r15
0x180018761  mov     rax, [rax]
0x180018764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018769  mov     ebx, eax
0x18001876b  cmp     qword ptr [rsi], 0
0x18001876f  jz      short loc_1800187C7
0x180018771  test    ebx, ebx
0x180018773  js      short loc_1800187DD
0x180018775  mov     eax, ebx
0x180018777  add     rsp, 38h
0x18001877b  pop     r15
0x18001877d  pop     r14
0x18001877f  pop     rdi
0x180018780  pop     rsi
0x180018781  pop     rbp
0x180018782  pop     rbx
0x180018783  retn
0x180018784  lea     rcx, stru_1800980F0; lpCriticalSection
0x18001878b  call    cs:__imp_EnterCriticalSection
0x180018791  cmp     [r14], rbx
0x180018794  jz      short loc_1800187AC
0x180018796  lea     rcx, stru_1800980F0; lpCriticalSection
0x18001879d  call    cs:__imp_LeaveCriticalSection
0x1800187a3  jmp     short loc_180018750
0x1800187a5  mov     ebx, 80004003h
0x1800187aa  jmp     short loc_180018771
0x1800187ac  mov     r8, r14
0x1800187af  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800187b6  mov     rcx, [rdi+18h]
0x1800187ba  mov     rax, [rdi+10h]
0x1800187be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187c3  mov     ebx, eax
0x1800187c5  jmp     short loc_180018796
0x1800187c7  test    ebx, ebx
0x1800187c9  jnz     short loc_180018771
0x1800187cb  mov     r9, rsi; void **
0x1800187ce  mov     r8, r15; struct _GUID *
0x1800187d1  mov     rdx, rbp; struct _GUID *
0x1800187d4  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800187d9  mov     ebx, eax
0x1800187db  jmp     short loc_180018771
0x1800187dd  mov     rax, cs:aProxyFileList
0x1800187e4  mov     rcx, [rax+8]
0x1800187e8  mov     rax, [rcx]
0x1800187eb  test    rax, rax
0x1800187ee  jz      short loc_1800187F5
0x1800187f0  mov     rcx, [rax]
0x1800187f3  jmp     short loc_1800187F7
0x1800187f5  xor     ecx, ecx
0x1800187f7  lea     rax, gPFactory
0x1800187fe  mov     [rsp+68h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180018803  mov     [rsp+68h+pclsid], rcx; pclsid
0x180018808  lea     r9, aProxyFileList; pProxyFileList
0x18001880f  mov     r8, rsi; ppv
0x180018812  mov     rdx, r15; riid
0x180018815  mov     rcx, rbp; rclsid
0x180018818  call    cs:__imp_NdrDllGetClassObject
0x18001881e  mov     ebx, eax
0x180018820  jmp     loc_180018775
```

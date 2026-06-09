# DllGetClassObject

- ea: `0x18000a4d0`
- end: `0x18000a613`
- name: `DllGetClassObject`
- size: `323`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a4d0`
- `0x1800181ec`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a5f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a5f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a5cc`
- `RPCRT4!NdrDllGetClassObject` at `0x18000a514`
- `RPCRT4!NdrDllGetClassObject` at `0x18000a514`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const CLSID *pclsid; // rax
  __int64 v7; // rcx
  __int64 v8; // rbx
  HRESULT v9; // ebp

  pclsid = (const CLSID *)*aProxyFileList->pStubVtblList;
  if ( pclsid )
    pclsid = *(const CLSID **)&pclsid->Data1;
  if ( !NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&aProxyFileList, pclsid, &gPFactory) )
    return 0;
  if ( !ppv )
    return -2147467261;
  *ppv = 0;
  v8 = qword_180098F98;
  if ( qword_180098F98 )
  {
    while ( 1 )
    {
      v7 = *(_QWORD *)v8;
      if ( !*(_QWORD *)v8 )
        break;
      if ( *(_QWORD *)(v8 + 16)
        && rclsid->Data1 == *(_DWORD *)v7
        && *(_DWORD *)&rclsid->Data2 == *(_DWORD *)(v7 + 4)
        && *(_DWORD *)rclsid->Data4 == *(_DWORD *)(v7 + 8)
        && *(_DWORD *)&rclsid->Data4[4] == *(_DWORD *)(v7 + 12) )
      {
        v9 = 0;
        if ( !*(_QWORD *)(v8 + 32) )
        {
          EnterCriticalSection(&stru_180099070);
          if ( !*(_QWORD *)(v8 + 32) )
            v9 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v8 + 16))(
                   *(_QWORD *)(v8 + 24),
                   &GUID_00000000_0000_0000_c000_000000000046,
                   v8 + 32);
          LeaveCriticalSection(&stru_180099070);
        }
        v7 = *(_QWORD *)(v8 + 32);
        if ( v7 )
          v9 = (**(__int64 (__fastcall ***)(__int64, const IID *const, LPVOID *))v7)(v7, riid, ppv);
        if ( *ppv || v9 )
          return v9;
        return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)v7, rclsid, riid, ppv);
      }
      v8 += 72;
    }
  }
  return ATL::AtlComModuleGetClassObject((struct ATL::_ATL_COM_MODULE70 *)v7, rclsid, riid, ppv);
}

```

## disassembly

```asm
0x18000a4d0  push    rbx
0x18000a4d2  push    rbp
0x18000a4d3  push    rsi
0x18000a4d4  push    rdi
0x18000a4d5  push    r14
0x18000a4d7  push    r15
0x18000a4d9  sub     rsp, 38h
0x18000a4dd  mov     rdi, r8
0x18000a4e0  mov     r15, rdx
0x18000a4e3  mov     r14, rcx
0x18000a4e6  mov     rax, cs:aProxyFileList
0x18000a4ed  mov     r9, [rax+8]
0x18000a4f1  mov     rax, [r9]
0x18000a4f4  test    rax, rax
0x18000a4f7  jnz     short loc_18000A55A
0x18000a4f9  lea     rcx, gPFactory
0x18000a500  mov     [rsp+68h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x18000a505  mov     [rsp+68h+pclsid], rax; pclsid
0x18000a50a  lea     r9, aProxyFileList; pProxyFileList
0x18000a511  mov     rcx, r14; rclsid
0x18000a514  call    cs:__imp_NdrDllGetClassObject
0x18000a51a  test    eax, eax
0x18000a51c  jz      loc_18000A601
0x18000a522  test    rdi, rdi
0x18000a525  jz      loc_18000A605
0x18000a52b  mov     qword ptr [rdi], 0
0x18000a532  mov     rbx, cs:qword_180098F98
0x18000a539  test    rbx, rbx
0x18000a53c  jz      short loc_18000A5B3
0x18000a53e  mov     rcx, [rbx]
0x18000a541  test    rcx, rcx
0x18000a544  jz      short loc_18000A5B3
0x18000a546  cmp     qword ptr [rbx+10h], 0
0x18000a54b  jz      short loc_18000A554
0x18000a54d  mov     eax, [rcx]
0x18000a54f  cmp     [r14], eax
0x18000a552  jz      short loc_18000A55F
0x18000a554  add     rbx, 48h ; 'H'
0x18000a558  jmp     short loc_18000A53E
0x18000a55a  mov     rax, [rax]
0x18000a55d  jmp     short loc_18000A4F9
0x18000a55f  mov     eax, [rcx+4]
0x18000a562  cmp     [r14+4], eax
0x18000a566  jnz     short loc_18000A554
0x18000a568  mov     eax, [rcx+8]
0x18000a56b  cmp     [r14+8], eax
0x18000a56f  jnz     short loc_18000A554
0x18000a571  mov     eax, [rcx+0Ch]
0x18000a574  cmp     [r14+0Ch], eax
0x18000a578  jnz     short loc_18000A554
0x18000a57a  xor     ebp, ebp
0x18000a57c  cmp     [rbx+20h], rbp
0x18000a580  jz      short loc_18000A5C5
0x18000a582  mov     rcx, [rbx+20h]
0x18000a586  test    rcx, rcx
0x18000a589  jz      short loc_18000A59E
0x18000a58b  mov     rax, [rcx]
0x18000a58e  mov     r8, rdi
0x18000a591  mov     rdx, r15
0x18000a594  mov     rax, [rax]
0x18000a597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a59c  mov     ebp, eax
0x18000a59e  cmp     qword ptr [rdi], 0
0x18000a5a2  jz      short loc_18000A60C
0x18000a5a4  mov     eax, ebp
0x18000a5a6  add     rsp, 38h
0x18000a5aa  pop     r15
0x18000a5ac  pop     r14
0x18000a5ae  pop     rdi
0x18000a5af  pop     rsi
0x18000a5b0  pop     rbp
0x18000a5b1  pop     rbx
0x18000a5b2  retn
0x18000a5b3  mov     r9, rdi; void **
0x18000a5b6  mov     r8, r15; struct _GUID *
0x18000a5b9  mov     rdx, r14; struct _GUID *
0x18000a5bc  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000a5c1  mov     ebp, eax
0x18000a5c3  jmp     short loc_18000A5A4
0x18000a5c5  lea     rcx, stru_180099070; lpCriticalSection
0x18000a5cc  call    cs:__imp_EnterCriticalSection
0x18000a5d2  cmp     [rbx+20h], rbp
0x18000a5d6  jnz     short loc_18000A5F2
0x18000a5d8  lea     r8, [rbx+20h]
0x18000a5dc  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000a5e3  mov     rcx, [rbx+18h]
0x18000a5e7  mov     rax, [rbx+10h]
0x18000a5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5f0  mov     ebp, eax
0x18000a5f2  lea     rcx, stru_180099070; lpCriticalSection
0x18000a5f9  call    cs:__imp_LeaveCriticalSection
0x18000a5ff  jmp     short loc_18000A582
0x18000a601  xor     eax, eax
0x18000a603  jmp     short loc_18000A5A6
0x18000a605  mov     ebp, 80004003h
0x18000a60a  jmp     short loc_18000A5A4
0x18000a60c  test    ebp, ebp
0x18000a60e  jnz     short loc_18000A5A4
0x18000a610  jmp     short loc_18000A5B3
```

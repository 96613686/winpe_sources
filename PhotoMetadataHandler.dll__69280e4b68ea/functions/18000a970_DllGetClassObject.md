# DllGetClassObject

- ea: `0x18000a970`
- end: `0x18000aac9`
- name: `DllGetClassObject`
- size: `345`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a970`
- `0x180018c24`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aaa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aaa6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa73`
- `RPCRT4!NdrDllGetClassObject` at `0x18000a9b4`
- `RPCRT4!NdrDllGetClassObject` at `0x18000a9b4`

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
  v8 = qword_18009A088;
  if ( qword_18009A088 )
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
          EnterCriticalSection(&stru_18009A160);
          if ( !*(_QWORD *)(v8 + 32) )
            v9 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v8 + 16))(
                   *(_QWORD *)(v8 + 24),
                   &GUID_00000000_0000_0000_c000_000000000046,
                   v8 + 32);
          LeaveCriticalSection(&stru_18009A160);
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
0x18000a970  push    rbx
0x18000a972  push    rbp
0x18000a973  push    rsi
0x18000a974  push    rdi
0x18000a975  push    r14
0x18000a977  push    r15
0x18000a979  sub     rsp, 38h
0x18000a97d  mov     rdi, r8
0x18000a980  mov     r15, rdx
0x18000a983  mov     r14, rcx
0x18000a986  mov     rax, cs:aProxyFileList
0x18000a98d  mov     r9, [rax+8]
0x18000a991  mov     rax, [r9]
0x18000a994  test    rax, rax
0x18000a997  jnz     short loc_18000AA00
0x18000a999  lea     rcx, gPFactory
0x18000a9a0  mov     [rsp+68h+pPSFactoryBuffer], rcx; pPSFactoryBuffer
0x18000a9a5  mov     [rsp+68h+pclsid], rax; pclsid
0x18000a9aa  lea     r9, aProxyFileList; pProxyFileList
0x18000a9b1  mov     rcx, r14; rclsid
0x18000a9b4  call    cs:__imp_NdrDllGetClassObject
0x18000a9bb  nop     dword ptr [rax+rax+00h]
0x18000a9c0  test    eax, eax
0x18000a9c2  jz      loc_18000AAB7
0x18000a9c8  test    rdi, rdi
0x18000a9cb  jz      loc_18000AABB
0x18000a9d1  mov     qword ptr [rdi], 0
0x18000a9d8  mov     rbx, cs:qword_18009A088
0x18000a9df  test    rbx, rbx
0x18000a9e2  jz      short loc_18000AA5A
0x18000a9e4  mov     rcx, [rbx]
0x18000a9e7  test    rcx, rcx
0x18000a9ea  jz      short loc_18000AA5A
0x18000a9ec  cmp     qword ptr [rbx+10h], 0
0x18000a9f1  jz      short loc_18000A9FA
0x18000a9f3  mov     eax, [rcx]
0x18000a9f5  cmp     [r14], eax
0x18000a9f8  jz      short loc_18000AA05
0x18000a9fa  add     rbx, 48h ; 'H'
0x18000a9fe  jmp     short loc_18000A9E4
0x18000aa00  mov     rax, [rax]
0x18000aa03  jmp     short loc_18000A999
0x18000aa05  mov     eax, [rcx+4]
0x18000aa08  cmp     [r14+4], eax
0x18000aa0c  jnz     short loc_18000A9FA
0x18000aa0e  mov     eax, [rcx+8]
0x18000aa11  cmp     [r14+8], eax
0x18000aa15  jnz     short loc_18000A9FA
0x18000aa17  mov     eax, [rcx+0Ch]
0x18000aa1a  cmp     [r14+0Ch], eax
0x18000aa1e  jnz     short loc_18000A9FA
0x18000aa20  xor     ebp, ebp
0x18000aa22  cmp     [rbx+20h], rbp
0x18000aa26  jz      short loc_18000AA6C
0x18000aa28  mov     rcx, [rbx+20h]
0x18000aa2c  test    rcx, rcx
0x18000aa2f  jz      short loc_18000AA44
0x18000aa31  mov     rax, [rcx]
0x18000aa34  mov     r8, rdi
0x18000aa37  mov     rdx, r15
0x18000aa3a  mov     rax, [rax]
0x18000aa3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa42  mov     ebp, eax
0x18000aa44  cmp     qword ptr [rdi], 0
0x18000aa48  jz      short loc_18000AAC2
0x18000aa4a  mov     eax, ebp
0x18000aa4c  add     rsp, 38h
0x18000aa50  pop     r15
0x18000aa52  pop     r14
0x18000aa54  pop     rdi
0x18000aa55  pop     rsi
0x18000aa56  pop     rbp
0x18000aa57  pop     rbx
0x18000aa58  retn
0x18000aa5a  mov     r9, rdi; void **
0x18000aa5d  mov     r8, r15; struct _GUID *
0x18000aa60  mov     rdx, r14; struct _GUID *
0x18000aa63  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x18000aa68  mov     ebp, eax
0x18000aa6a  jmp     short loc_18000AA4A
0x18000aa6c  lea     rcx, stru_18009A160; lpCriticalSection
0x18000aa73  call    cs:__imp_EnterCriticalSection
0x18000aa7a  nop     dword ptr [rax+rax+00h]
0x18000aa7f  cmp     [rbx+20h], rbp
0x18000aa83  jnz     short loc_18000AA9F
0x18000aa85  lea     r8, [rbx+20h]
0x18000aa89  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000aa90  mov     rcx, [rbx+18h]
0x18000aa94  mov     rax, [rbx+10h]
0x18000aa98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa9d  mov     ebp, eax
0x18000aa9f  lea     rcx, stru_18009A160; lpCriticalSection
0x18000aaa6  call    cs:__imp_LeaveCriticalSection
0x18000aaad  nop     dword ptr [rax+rax+00h]
0x18000aab2  jmp     loc_18000AA28
0x18000aab7  xor     eax, eax
0x18000aab9  jmp     short loc_18000AA4C
0x18000aabb  mov     ebp, 80004003h
0x18000aac0  jmp     short loc_18000AA4A
0x18000aac2  test    ebp, ebp
0x18000aac4  jnz     short loc_18000AA4A
0x18000aac6  jmp     short loc_18000AA5A
```

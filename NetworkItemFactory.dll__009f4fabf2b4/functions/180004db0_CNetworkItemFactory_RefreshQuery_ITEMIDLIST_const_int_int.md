# CNetworkItemFactory::_RefreshQuery(_ITEMIDLIST const *,int,int)

- ea: `0x180004db0`
- end: `0x180004fa9`
- name: `?_RefreshQuery@CNetworkItemFactory@@AEAAJPEFBU_ITEMIDLIST@@HH@Z`
- size: `505`
- prototype: `__int64 __fastcall(CNetworkItemFactory *__hidden this, LPCITEMIDLIST pidl, int, int)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003a10`
- `0x180003ba0`
- `0x1800067b0`

## callees

- `0x180004ba0`
- `0x180004db0`
- `0x180005058`
- `0x1800052c4`
- `0x18000589c`
- `0x180008250`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180004ef5`
- `KERNEL32!GetTickCount` at `0x180004f0b`
- `KERNEL32!GetTickCount` at `0x180004ef5`
- `KERNEL32!GetTickCount` at `0x180004f0b`
- `KERNEL32!LeaveCriticalSection` at `0x180004f94`
- `KERNEL32!LeaveCriticalSection` at `0x180004f94`
- `KERNEL32!EnterCriticalSection` at `0x180004eb3`
- `KERNEL32!EnterCriticalSection` at `0x180004eb3`
- `ole32!CoCreateInstance` at `0x180004df5`
- `ole32!CoCreateInstance` at `0x180004df5`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::_RefreshQuery(CNetworkItemFactory *this, LPCITEMIDLIST pidl, int a3, int a4)
{
  BOOL v8; // esi
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  signed int started; // edi
  LKRhash::CLKRHashTable *v12; // rcx
  int v14; // [rsp+30h] [rbp-48h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-40h] BYREF
  int v16; // [rsp+80h] [rbp+8h] BYREF

  ppv = 0;
  v8 = 1;
  if ( CoCreateInstance(&CLSID_DetectionAndSharing, 0, 3u, &GUID_1fda955c_61ff_11da_978c_0008744faab7, &ppv) < 0 )
    goto LABEL_9;
  v16 = 0;
  v14 = 0;
  if ( (*(int (__fastcall **)(LPVOID, _QWORD, int *, int *))(*(_QWORD *)ppv + 24LL))(ppv, 0, &v16, &v14) >= 0 )
    v8 = v16 != 0;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v8 )
  {
LABEL_9:
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 23;
      goto LABEL_13;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v10 = 24;
LABEL_13:
      WPP_SF_(v9[2], v10, &WPP_182dd27e7f09338048566614cf2976f3_Traceguids);
    }
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_DWORD *)this + 14) )
  {
    if ( v8 )
    {
      if ( !a3 || GetTickCount() - *((_DWORD *)this + 24) < 0x2710 && !a4 )
      {
        started = 1;
        goto LABEL_30;
      }
      started = CNetworkItemFactory::_StopAllFDQueries(this);
      if ( started >= 0 )
      {
        LKRhash::CLKRHashTable::Clear(*((LKRhash::CLKRHashTable **)this + 10));
        LKRhash::CLKRHashTable::Clear(*((LKRhash::CLKRHashTable **)this + 11));
        *(_QWORD *)((char *)this + 60) = 0;
        started = CNetworkItemFactory::_StartAllFDQueries(this);
        if ( started >= 0 )
          goto LABEL_19;
      }
    }
    else
    {
      started = CNetworkItemFactory::_StopAllFDQueries(this);
      if ( started >= 0 )
      {
        v12 = (LKRhash::CLKRHashTable *)*((_QWORD *)this + 10);
        *((_QWORD *)this + 7) = 0;
        *((_DWORD *)this + 16) = 0;
        LKRhash::CLKRHashTable::Clear(v12);
        LKRhash::CLKRHashTable::Clear(*((LKRhash::CLKRHashTable **)this + 11));
        started = 0;
      }
    }
  }
  else
  {
    started = CNetworkItemFactory::_InitializeDataSource(this, pidl);
    if ( started >= 0 )
    {
      if ( v8 )
      {
        started = CNetworkItemFactory::_StartAllFDQueries(this);
        if ( started >= 0 )
        {
          *((_DWORD *)this + 14) = 1;
LABEL_19:
          *((_DWORD *)this + 24) = GetTickCount();
        }
      }
    }
  }
LABEL_30:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return (unsigned int)started;
}

```

## disassembly

```asm
0x180004db0  push    rbx
0x180004db2  push    rbp
0x180004db3  push    rsi
0x180004db4  push    rdi
0x180004db5  push    r14
0x180004db7  push    r15
0x180004db9  sub     rsp, 48h
0x180004dbd  mov     r14d, r9d
0x180004dc0  mov     [rsp+78h+var_40], 0
0x180004dc9  mov     edi, r8d
0x180004dcc  lea     rax, [rsp+78h+var_40]
0x180004dd1  mov     r15, rdx
0x180004dd4  mov     [rsp+78h+ppv], rax; ppv
0x180004dd9  mov     rbx, rcx
0x180004ddc  lea     r9, _GUID_1fda955c_61ff_11da_978c_0008744faab7; riid
0x180004de3  mov     esi, 1
0x180004de8  lea     rcx, CLSID_DetectionAndSharing; rclsid
0x180004def  xor     edx, edx; pUnkOuter
0x180004df1  lea     r8d, [rsi+2]; dwClsContext
0x180004df5  call    cs:__imp_CoCreateInstance
0x180004dfb  test    eax, eax
0x180004dfd  js      short loc_180004E7B
0x180004dff  mov     rcx, [rsp+78h+var_40]
0x180004e04  lea     r9, [rsp+78h+var_48]
0x180004e09  mov     [rsp+78h+arg_0], 0
0x180004e14  lea     r8, [rsp+78h+arg_0]
0x180004e1c  mov     [rsp+78h+var_48], 0
0x180004e24  xor     edx, edx
0x180004e26  mov     rax, [rcx]
0x180004e29  mov     rax, [rax+18h]
0x180004e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e32  test    eax, eax
0x180004e34  js      short loc_180004E42
0x180004e36  xor     eax, eax
0x180004e38  cmp     [rsp+78h+arg_0], eax
0x180004e3f  cmovz   esi, eax
0x180004e42  mov     rcx, [rsp+78h+var_40]
0x180004e47  mov     rax, [rcx]
0x180004e4a  mov     rax, [rax+10h]
0x180004e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e53  test    esi, esi
0x180004e55  jnz     short loc_180004E7B
0x180004e57  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e5e  lea     rax, WPP_GLOBAL_Control
0x180004e65  cmp     rcx, rax
0x180004e68  jz      short loc_180004EAF
0x180004e6a  cmp     byte ptr [rcx+19h], 4
0x180004e6e  jb      short loc_180004EAF
0x180004e70  test    byte ptr [rcx+1Ch], 2
0x180004e74  jz      short loc_180004EAF
0x180004e76  lea     edx, [rsi+18h]
0x180004e79  jmp     short loc_180004E9F
0x180004e7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e82  lea     rax, WPP_GLOBAL_Control
0x180004e89  cmp     rcx, rax
0x180004e8c  jz      short loc_180004EAF
0x180004e8e  cmp     byte ptr [rcx+19h], 4
0x180004e92  jb      short loc_180004EAF
0x180004e94  test    byte ptr [rcx+1Ch], 2
0x180004e98  jz      short loc_180004EAF
0x180004e9a  mov     edx, 17h
0x180004e9f  mov     rcx, [rcx+10h]
0x180004ea3  lea     r8, WPP_182dd27e7f09338048566614cf2976f3_Traceguids
0x180004eaa  call    WPP_SF_
0x180004eaf  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004eb3  call    cs:__imp_EnterCriticalSection
0x180004eb9  cmp     dword ptr [rbx+38h], 0
0x180004ebd  jnz     short loc_180004F03
0x180004ebf  mov     rdx, r15; pidl
0x180004ec2  mov     rcx, rbx; this
0x180004ec5  call    ?_InitializeDataSource@CNetworkItemFactory@@AEAAJPEFBU_ITEMIDLIST@@@Z; CNetworkItemFactory::_InitializeDataSource(_ITEMIDLIST const *)
0x180004eca  mov     edi, eax
0x180004ecc  test    eax, eax
0x180004ece  js      loc_180004F90
0x180004ed4  test    esi, esi
0x180004ed6  jz      loc_180004F90
0x180004edc  mov     rcx, rbx; this
0x180004edf  call    ?_StartAllFDQueries@CNetworkItemFactory@@AEAAJXZ; CNetworkItemFactory::_StartAllFDQueries(void)
0x180004ee4  mov     edi, eax
0x180004ee6  test    eax, eax
0x180004ee8  js      loc_180004F90
0x180004eee  mov     dword ptr [rbx+38h], 1
0x180004ef5  call    cs:__imp_GetTickCount
0x180004efb  mov     [rbx+60h], eax
0x180004efe  jmp     loc_180004F90
0x180004f03  test    esi, esi
0x180004f05  jz      short loc_180004F5F
0x180004f07  test    edi, edi
0x180004f09  jz      short loc_180004F58
0x180004f0b  call    cs:__imp_GetTickCount
0x180004f11  sub     eax, [rbx+60h]
0x180004f14  cmp     eax, 2710h
0x180004f19  jnb     short loc_180004F20
0x180004f1b  test    r14d, r14d
0x180004f1e  jz      short loc_180004F58
0x180004f20  mov     rcx, rbx; this
0x180004f23  call    ?_StopAllFDQueries@CNetworkItemFactory@@AEAAJXZ; CNetworkItemFactory::_StopAllFDQueries(void)
0x180004f28  mov     edi, eax
0x180004f2a  test    eax, eax
0x180004f2c  js      short loc_180004F90
0x180004f2e  mov     rcx, [rbx+50h]; this
0x180004f32  call    ?Clear@CLKRHashTable@LKRhash@@QEAAXXZ; LKRhash::CLKRHashTable::Clear(void)
0x180004f37  mov     rcx, [rbx+58h]; this
0x180004f3b  call    ?Clear@CLKRHashTable@LKRhash@@QEAAXXZ; LKRhash::CLKRHashTable::Clear(void)
0x180004f40  mov     rcx, rbx; this
0x180004f43  mov     qword ptr [rbx+3Ch], 0
0x180004f4b  call    ?_StartAllFDQueries@CNetworkItemFactory@@AEAAJXZ; CNetworkItemFactory::_StartAllFDQueries(void)
0x180004f50  mov     edi, eax
0x180004f52  test    eax, eax
0x180004f54  js      short loc_180004F90
0x180004f56  jmp     short loc_180004EF5
0x180004f58  mov     edi, 1
0x180004f5d  jmp     short loc_180004F90
0x180004f5f  mov     rcx, rbx; this
0x180004f62  call    ?_StopAllFDQueries@CNetworkItemFactory@@AEAAJXZ; CNetworkItemFactory::_StopAllFDQueries(void)
0x180004f67  mov     edi, eax
0x180004f69  test    eax, eax
0x180004f6b  js      short loc_180004F90
0x180004f6d  mov     rcx, [rbx+50h]; this
0x180004f71  mov     qword ptr [rbx+38h], 0
0x180004f79  mov     dword ptr [rbx+40h], 0
0x180004f80  call    ?Clear@CLKRHashTable@LKRhash@@QEAAXXZ; LKRhash::CLKRHashTable::Clear(void)
0x180004f85  mov     rcx, [rbx+58h]; this
0x180004f89  call    ?Clear@CLKRHashTable@LKRhash@@QEAAXXZ; LKRhash::CLKRHashTable::Clear(void)
0x180004f8e  xor     edi, edi
0x180004f90  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004f94  call    cs:__imp_LeaveCriticalSection
0x180004f9a  mov     eax, edi
0x180004f9c  add     rsp, 48h
0x180004fa0  pop     r15
0x180004fa2  pop     r14
0x180004fa4  pop     rdi
0x180004fa5  pop     rsi
0x180004fa6  pop     rbp
0x180004fa7  pop     rbx
0x180004fa8  retn
```

# _anonymous_namespace_::ServiceLifetimeManager::RemoveSession

- ea: `0x140005400`
- end: `0x140005617`
- name: `_anonymous_namespace_::ServiceLifetimeManager::RemoveSession`
- size: `535`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140003220`
- `0x140005400`
- `0x140006c80`
- `0x14000a278`
- `0x1400137e0`
- `0x14001382c`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400055e9`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400055e9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140005445`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140005445`
- `KERNEL32!SetThreadpoolTimer` at `0x1400055d0`
- `KERNEL32!SetThreadpoolTimer` at `0x1400055d0`
- `ADVAPI32!RegQueryValueExW` at `0x140005577`
- `ADVAPI32!RegQueryValueExW` at `0x140005577`
- `ADVAPI32!RegCloseKey` at `0x1400055df`
- `ADVAPI32!RegCloseKey` at `0x1400055df`

## string_xrefs

- `0x140005595`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Service\StandardCollectorHost.cpp`
- `0x14000556d`: `CollectorService.IdleShutdownInSeconds`
- `0x14000558e`: `Service idle shutdown has been disabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall anonymous_namespace_::ServiceLifetimeManager::RemoveSession(RTL_SRWLOCK *a1, __int64 a2)
{
  RTL_SRWLOCK *v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // rdx
  unsigned __int64 i; // rcx
  unsigned __int64 j; // rcx
  __int64 v9; // rbx
  HKEY v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  _QWORD *Ptr; // r8
  PVOID v14; // rax
  __int64 v15; // rdx
  unsigned int v16; // edi
  int v17; // eax
  HKEY v18; // rbx
  struct _TP_TIMER *v19; // rcx
  HKEY hKey[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+40h] [rbp-40h]
  RTL_SRWLOCK *v22; // [rsp+48h] [rbp-38h]
  int v23; // [rsp+50h] [rbp-30h]
  BYTE Data[4]; // [rsp+58h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-24h] BYREF
  struct _FILETIME Type[2]; // [rsp+60h] [rbp-20h] BYREF

  v4 = a1 + 5;
  v22 = a1 + 5;
  v23 = 1;
  AcquireSRWLockExclusive(a1 + 5);
  v5 = 0xCBF29CE484222325uLL;
  v6 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 8; ++i )
    v6 = 0x100000001B3LL * (*(unsigned __int8 *)(a2 + i) ^ (unsigned __int64)v6);
  for ( j = 0; j < 8; ++j )
    v5 = 0x100000001B3LL * (*(unsigned __int8 *)(a2 + j + 8) ^ (unsigned __int64)v5);
  v9 = v6 ^ v5;
  v11 = *(_QWORD **)(std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(
                       &a1[6],
                       Type,
                       a2,
                       v9)
                   + 8);
  if ( v11 )
  {
    v12 = 2 * (v9 & (__int64)a1[12].Ptr);
    Ptr = a1[9].Ptr;
    if ( (_QWORD *)Ptr[2 * (v9 & (__int64)a1[12].Ptr) + 1] == v11 )
    {
      if ( (_QWORD *)Ptr[2 * (v9 & (__int64)a1[12].Ptr)] == v11 )
      {
        v14 = a1[7].Ptr;
        Ptr[2 * (v9 & (__int64)a1[12].Ptr)] = v14;
      }
      else
      {
        v14 = (PVOID)v11[1];
      }
      Ptr[v12 + 1] = v14;
    }
    else if ( (_QWORD *)Ptr[2 * (v9 & (__int64)a1[12].Ptr)] == v11 )
    {
      Ptr[2 * (v9 & (__int64)a1[12].Ptr)] = *v11;
    }
    v15 = *v11;
    --a1[8].Ptr;
    *(_QWORD *)v11[1] = v15;
    *(_QWORD *)(v15 + 8) = v11[1];
    operator delete(v11);
  }
  if ( !a1[8].Ptr )
  {
    v16 = 300;
    hKey[0] = 0;
    hKey[1] = 0;
    v21 = 0;
    v17 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, v10, L"Software\\Microsoft\\VisualStudio\\DiagnosticsHub");
    v18 = hKey[0];
    if ( v17
      || (*(_DWORD *)Data = 0,
          cbData = 4,
          RegQueryValueExW(hKey[0], L"CollectorService.IdleShutdownInSeconds", 0, (LPDWORD)Type, Data, &cbData))
      || Type[0].dwLowDateTime != 4
      || (v16 = *(_DWORD *)Data) != 0 )
    {
      v19 = (struct _TP_TIMER *)a1[3].Ptr;
      if ( v19 )
      {
        Type[0] = (struct _FILETIME)(-10000000LL * v16);
        SetThreadpoolTimer(v19, Type, 0, 0);
      }
    }
    else
    {
      DiagHubCommon::LogStream::Write(
        _logger,
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Service\\StandardCollectorHost.cpp",
        L"Service idle shutdown has been disabled");
    }
    if ( v18 )
      RegCloseKey(v18);
  }
  ReleaseSRWLockExclusive(v4);
}

```

## disassembly

```asm
0x140005400  mov     [rsp-28h+arg_10], rbx
0x140005405  mov     [rsp-28h+arg_18], rsi
0x14000540a  push    rbp
0x14000540b  push    rdi
0x14000540c  push    r13
0x14000540e  push    r14
0x140005410  push    r15
0x140005412  mov     rbp, rsp
0x140005415  sub     rsp, 80h
0x14000541c  mov     rax, cs:__security_cookie
0x140005423  xor     rax, rsp
0x140005426  mov     [rbp+var_10], rax
0x14000542a  mov     r15, rdx
0x14000542d  mov     r14, rcx
0x140005430  lea     rsi, [rcx+28h]
0x140005434  mov     [rbp+var_38], rsi
0x140005438  mov     r13d, 1
0x14000543e  mov     [rbp+var_30], r13d
0x140005442  mov     rcx, rsi; SRWLock
0x140005445  call    cs:__imp_AcquireSRWLockExclusive
0x14000544b  nop
0x14000544c  mov     rbx, 0CBF29CE484222325h
0x140005456  mov     rdx, rbx
0x140005459  xor     ecx, ecx
0x14000545b  mov     r8, 100000001B3h
0x140005465  movzx   eax, byte ptr [r15+rcx]
0x14000546a  xor     rdx, rax
0x14000546d  imul    rdx, r8
0x140005471  add     rcx, r13
0x140005474  cmp     rcx, 8
0x140005478  jb      short loc_140005465
0x14000547a  xor     ecx, ecx
0x14000547c  movzx   eax, byte ptr [r15+rcx+8]
0x140005482  xor     rbx, rax
0x140005485  imul    rbx, r8
0x140005489  add     rcx, r13
0x14000548c  cmp     rcx, 8
0x140005490  jb      short loc_14000547C
0x140005492  xor     rbx, rdx
0x140005495  mov     r9, rbx
0x140005498  mov     r8, r15
0x14000549b  lea     rdx, [rbp+Type]
0x14000549f  lea     rcx, [r14+30h]
0x1400054a3  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Uset_traits@U_GUID@@V?$_Uhash_compare@U_GUID@@UGuidHash@DiagHubCommon@@UGuidEqualTo@3@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U_GUID@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,DiagHubCommon::GuidHash,DiagHubCommon::GuidEqualTo>,std::allocator<_GUID>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x1400054a8  mov     rcx, [rax+8]; Block
0x1400054ac  test    rcx, rcx
0x1400054af  jz      short loc_14000550E
0x1400054b1  mov     rdx, [r14+60h]
0x1400054b5  and     rdx, rbx
0x1400054b8  add     rdx, rdx
0x1400054bb  mov     r8, [r14+48h]
0x1400054bf  cmp     [r8+rdx*8+8], rcx
0x1400054c4  jnz     short loc_1400054E1
0x1400054c6  cmp     [r8+rdx*8], rcx
0x1400054ca  jnz     short loc_1400054D6
0x1400054cc  mov     rax, [r14+38h]
0x1400054d0  mov     [r8+rdx*8], rax
0x1400054d4  jmp     short loc_1400054DA
0x1400054d6  mov     rax, [rcx+8]
0x1400054da  mov     [r8+rdx*8+8], rax
0x1400054df  jmp     short loc_1400054EE
0x1400054e1  cmp     [r8+rdx*8], rcx
0x1400054e5  jnz     short loc_1400054EE
0x1400054e7  mov     rax, [rcx]
0x1400054ea  mov     [r8+rdx*8], rax
0x1400054ee  mov     rdx, [rcx]
0x1400054f1  dec     qword ptr [r14+40h]
0x1400054f5  mov     rax, [rcx+8]
0x1400054f9  mov     [rax], rdx
0x1400054fc  mov     rax, [rcx+8]
0x140005500  mov     [rdx+8], rax
0x140005504  mov     edx, 20h ; ' '
0x140005509  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000550e  cmp     qword ptr [r14+40h], 0
0x140005513  jnz     loc_1400055E6
0x140005519  mov     edi, 12Ch
0x14000551e  xorps   xmm0, xmm0
0x140005521  xor     eax, eax
0x140005523  movups  xmmword ptr [rbp+hKey], xmm0
0x140005527  mov     [rbp+hKey], rax
0x14000552b  mov     dword ptr [rbp+hKey+8], eax
0x14000552e  mov     [rbp+var_40], rax
0x140005532  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\VisualStudio\\Diag"...
0x140005539  lea     rcx, [rbp+hKey]; this
0x14000553d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140005542  mov     rbx, [rbp+hKey]
0x140005546  test    eax, eax
0x140005548  jnz     short loc_1400055AA
0x14000554a  mov     dword ptr [rbp+Data], eax
0x14000554d  mov     [rbp+cbData], 4
0x140005554  lea     rax, [rbp+cbData]
0x140005558  mov     [rsp+80h+lpcbData], rax; lpcbData
0x14000555d  lea     rax, [rbp+Data]
0x140005561  mov     [rsp+80h+lpData], rax; lpData
0x140005566  lea     r9, [rbp+Type]; lpType
0x14000556a  xor     r8d, r8d; lpReserved
0x14000556d  lea     rdx, aCollectorservi; "CollectorService.IdleShutdownInSeconds"
0x140005574  mov     rcx, rbx; hKey
0x140005577  call    cs:__imp_RegQueryValueExW
0x14000557d  test    eax, eax
0x14000557f  jnz     short loc_1400055AA
0x140005581  cmp     dword ptr [rbp+Type], 4
0x140005585  jnz     short loc_1400055AA
0x140005587  mov     edi, dword ptr [rbp+Data]
0x14000558a  test    edi, edi
0x14000558c  jnz     short loc_1400055AA
0x14000558e  lea     r8, aServiceIdleShu; "Service idle shutdown has been disabled"
0x140005595  lea     rdx, aDAWork1SSource_0; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x14000559c  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x1400055a3  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1400055a8  jmp     short loc_1400055D7
0x1400055aa  mov     rcx, [r14+18h]; pti
0x1400055ae  test    rcx, rcx
0x1400055b1  jz      short loc_1400055D7
0x1400055b3  mov     eax, edi
0x1400055b5  imul    rdx, rax, 0FFFFFFFFFF676980h
0x1400055bc  mov     dword ptr [rbp+Type], edx
0x1400055bf  sar     rdx, 20h
0x1400055c3  mov     dword ptr [rbp+Type+4], edx
0x1400055c6  xor     r9d, r9d; msWindowLength
0x1400055c9  xor     r8d, r8d; msPeriod
0x1400055cc  lea     rdx, [rbp+Type]; pftDueTime
0x1400055d0  call    cs:__imp_SetThreadpoolTimer
0x1400055d6  nop
0x1400055d7  test    rbx, rbx
0x1400055da  jz      short loc_1400055E6
0x1400055dc  mov     rcx, rbx; hKey
0x1400055df  call    cs:__imp_RegCloseKey
0x1400055e5  nop
0x1400055e6  mov     rcx, rsi; SRWLock
0x1400055e9  call    cs:__imp_ReleaseSRWLockExclusive
0x1400055ef  mov     rcx, [rbp+var_10]
0x1400055f3  xor     rcx, rsp; StackCookie
0x1400055f6  call    __security_check_cookie
0x1400055fb  lea     r11, [rsp+80h+var_s0]
0x140005603  mov     rbx, [r11+40h]
0x140005607  mov     rsi, [r11+48h]
0x14000560b  mov     rsp, r11
0x14000560e  pop     r15
0x140005610  pop     r14
0x140005612  pop     r13
0x140005614  pop     rdi
0x140005615  pop     rbp
0x140005616  retn
```

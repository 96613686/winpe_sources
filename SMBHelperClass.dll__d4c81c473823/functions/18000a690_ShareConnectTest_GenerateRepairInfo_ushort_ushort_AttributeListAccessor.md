# ShareConnectTest::GenerateRepairInfo(ushort *,ushort *,AttributeListAccessor *)

- ea: `0x18000a690`
- end: `0x18000a8f2`
- name: `?GenerateRepairInfo@ShareConnectTest@@SAXPEAG0PEAVAttributeListAccessor@@@Z`
- size: `610`
- prototype: `void __fastcall(unsigned __int16 *, unsigned __int16 *, struct AttributeListAccessor *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800051b4`

## callees

- `0x18000257c`
- `0x18000a58c`
- `0x18000a690`
- `0x18000a98c`
- `0x18000aa18`
- `0x18000aa6c`
- `0x18000ab58`
- `0x18000ae80`
- `0x18000af74`
- `0x18000d3d8`
- `0x18000e10c`
- `0x18000e594`
- `0x18000fc30`

## import_xrefs

- `msvcrt!towlower` at `0x18000a744`
- `msvcrt!towlower` at `0x18000a744`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a88d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000a88d`
- `KERNEL32!ReleaseMutex` at `0x18000a84d`
- `KERNEL32!ReleaseMutex` at `0x18000a84d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a7eb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a7eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a8ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a8ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ShareConnectTest::GenerateRepairInfo(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        struct AttributeListAccessor *a3)
{
  unsigned __int64 v6; // rsi
  unsigned __int64 v7; // r8
  int v8; // edx
  unsigned int v9; // r9d
  int v10; // ecx
  unsigned __int16 *v11; // rdx
  unsigned int i; // r14d
  __int64 v13; // rcx
  HRESULT v14; // eax
  void *v15; // rdx
  unsigned __int64 v16; // r8
  unsigned int v17; // r8d
  unsigned __int16 *v18; // rdi
  int pExceptionObject; // [rsp+30h] [rbp-918h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-910h] BYREF
  HANDLE hMutex[2]; // [rsp+40h] [rbp-908h] BYREF
  __int64 v22; // [rsp+50h] [rbp-8F8h] BYREF
  __int64 v23; // [rsp+58h] [rbp-8F0h]
  __int64 v24; // [rsp+60h] [rbp-8E8h]
  __int64 v25; // [rsp+68h] [rbp-8E0h]
  __int64 v26; // [rsp+70h] [rbp-8D8h]
  __int64 v27; // [rsp+78h] [rbp-8D0h]
  __int64 v28; // [rsp+80h] [rbp-8C8h]
  __int64 v29; // [rsp+90h] [rbp-8B8h]
  LPVOID ppv; // [rsp+98h] [rbp-8B0h] BYREF
  void *v31[4]; // [rsp+A0h] [rbp-8A8h] BYREF
  _BYTE v32[64]; // [rsp+C0h] [rbp-888h] BYREF
  unsigned __int16 v33[1024]; // [rsp+100h] [rbp-848h] BYREF

  pv = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = -1;
  v9 = 0;
  if ( v7 )
  {
    do
    {
      v10 = v9;
      if ( a2[v9] != 92 )
        v10 = v8;
      v8 = v10;
      ++v9;
    }
    while ( v9 < v7 );
    if ( v10 != -1 )
    {
      v11 = &a2[v10 + 1];
      if ( *v11 )
      {
        if ( __eh34_try(-1, 0) )
        {
          __eh34_scope_strut(0);
          AllocateAndLoadString((unsigned __int16 **)&pv, v11);
          v18 = (unsigned __int16 *)pv;
          do
            ++v6;
          while ( *((_WORD *)pv + v6) );
          for ( i = 0; i < v6; ++i )
            v18[i] = towlower(v18[i]);
        }
        if ( __eh34_catch(0) )
        {
          if ( __eh34_catch_type(0, &enum TestException `RTTI Type Descriptor', 0) )
          {
            __eh34_try_continuation(0, &enum TestException `RTTI Type Descriptor', &loc_18000A8B4);
            return;
          }
        }
        if ( __eh34_try(-1, 2) )
        {
          __eh34_scope_strut(2);
          ((void (__stdcall *)(NetShareEnumerator *, unsigned __int16 *))NetShareEnumerator::NetShareEnumerator)(
            (NetShareEnumerator *)v32,
            a1 + 2);
          EditDistance::EditDistance((EditDistance *)v31, v18);
          v22 = 0;
          v23 = 0;
          v22 = std::_List_alloc<0,std::_List_base_types<Repair *>>::_Buynode0(v13, 0, 0);
          v24 = 2;
          v25 = 5;
          v26 = 1023;
          v27 = 100;
          v28 = 0;
          v29 = 2;
          v14 = CoCreateInstance(&CLSID_NDFEtw, 0, 1u, &IID_INDFEtw, &ppv);
          v15 = ppv;
          if ( v14 )
            v15 = 0;
          ppv = v15;
          StringEnumerationMatcher::findMatches(
            (_QWORD ***)&v22,
            (unsigned int (__fastcall ***)(_QWORD, unsigned __int16 **))v32,
            v31);
          if ( v23 )
          {
            ((void (__stdcall *)(StringEnumerationMatcher *, unsigned __int16 *, unsigned __int64))StringEnumerationMatcher::concatenateMatches)(
              (StringEnumerationMatcher *)&v22,
              v33,
              v16);
            AutoMutex::AutoMutex((AutoMutex *)hMutex, *((void **)a3 + 4), v17);
            ReleaseMutex(hMutex[0]);
            if ( **((_DWORD **)a3 + 1) )
            {
              pExceptionObject = 10;
              throw (TestException *)&pExceptionObject;
            }
            AttributeList::setStringAttribute(*((AttributeList **)a3 + 5), L"ShareCandidates", v33);
          }
          StringEnumerationMatcher::~StringEnumerationMatcher((StringEnumerationMatcher *)&v22);
          if ( v31[0] )
            operator delete[](v31[0]);
          NetShareEnumerator::~NetShareEnumerator((NetShareEnumerator *)v32);
        }
        if ( __eh34_catch(2) )
        {
          if ( __eh34_catch_type(2, &unsigned long `RTTI Type Descriptor', 0) )
          {
            v18 = (unsigned __int16 *)pv;
            __eh34_try_continuation(2, &unsigned long `RTTI Type Descriptor', &loc_18000A8A4);
          }
        }
        CoTaskMemFree(v18);
      }
    }
  }
}

```

## disassembly

```asm
0x18000a690  push    rbx
0x18000a692  push    rsi
0x18000a693  push    rdi
0x18000a694  push    r12
0x18000a696  push    r13
0x18000a698  push    r14
0x18000a69a  push    r15
0x18000a69c  sub     rsp, 910h
0x18000a6a3  mov     rax, cs:__security_cookie
0x18000a6aa  xor     rax, rsp
0x18000a6ad  mov     [rsp+948h+var_48], rax
0x18000a6b5  mov     r15, r8
0x18000a6b8  mov     r10, rdx
0x18000a6bb  mov     r13, rcx
0x18000a6be  xor     r12d, r12d
0x18000a6c1  mov     [rsp+948h+pv], r12
0x18000a6c6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a6ca  mov     r8, rsi
0x18000a6cd  inc     r8
0x18000a6d0  cmp     [rdx+r8*2], r12w
0x18000a6d5  jnz     short loc_18000A6CD
0x18000a6d7  mov     edx, esi
0x18000a6d9  mov     r9d, r12d
0x18000a6dc  test    r8, r8
0x18000a6df  jz      loc_18000A8B4
0x18000a6e5  mov     eax, r9d
0x18000a6e8  mov     ecx, r9d
0x18000a6eb  cmp     word ptr [r10+rax*2], 5Ch ; '\'
0x18000a6f1  cmovnz  ecx, edx
0x18000a6f4  movsxd  rdx, ecx
0x18000a6f7  inc     r9d
0x18000a6fa  mov     eax, r9d
0x18000a6fd  cmp     rax, r8
0x18000a700  jb      short loc_18000A6E5
0x18000a702  cmp     edx, esi
0x18000a704  jz      loc_18000A8B4
0x18000a70a  inc     rdx
0x18000a70d  lea     rdx, [r10+rdx*2]; unsigned __int16 *
0x18000a711  cmp     [rdx], r12w
0x18000a715  jz      loc_18000A8B4
0x18000a71b  lea     rcx, [rsp+948h+pv]; unsigned __int16 **
0x18000a720  call    ?AllocateAndLoadString@@YAXPEAPEAGPEAG@Z; AllocateAndLoadString(ushort * *,ushort *)
0x18000a725  nop
0x18000a726  mov     rdi, [rsp+948h+pv]
0x18000a72b  inc     rsi
0x18000a72e  cmp     [rdi+rsi*2], r12w
0x18000a733  jnz     short loc_18000A72B
0x18000a735  mov     r14d, r12d
0x18000a738  test    rsi, rsi
0x18000a73b  jz      short loc_18000A759
0x18000a73d  mov     ebx, r14d
0x18000a740  movzx   ecx, word ptr [rdi+rbx*2]; C
0x18000a744  call    cs:__imp_towlower
0x18000a74a  mov     [rdi+rbx*2], ax
0x18000a74e  inc     r14d
0x18000a751  mov     eax, r14d
0x18000a754  cmp     rax, rsi
0x18000a757  jb      short loc_18000A73D
0x18000a759  lea     rdx, [r13+4]; unsigned __int16 *
0x18000a75d  lea     rcx, [rsp+948h+var_888]; this
0x18000a765  call    ??0NetShareEnumerator@@QEAA@PEAG@Z; NetShareEnumerator::NetShareEnumerator(ushort *)
0x18000a76a  nop
0x18000a76b  mov     rdx, rdi; unsigned __int16 *
0x18000a76e  lea     rcx, [rsp+948h+var_8A8]; this
0x18000a776  call    ??0EditDistance@@QEAA@PEAG@Z; EditDistance::EditDistance(ushort *)
0x18000a77b  nop
0x18000a77c  mov     [rsp+948h+var_8F8], r12
0x18000a781  mov     [rsp+948h+var_8F0], r12
0x18000a786  xor     r8d, r8d
0x18000a789  xor     edx, edx
0x18000a78b  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAVRepair@@V?$allocator@PEAVRepair@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAVRepair@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Repair *>>::_Buynode0(std::_List_node<Repair *,void *> *,std::_List_node<Repair *,void *> *)
0x18000a790  mov     [rsp+948h+var_8F8], rax
0x18000a795  mov     eax, 2
0x18000a79a  mov     [rsp+948h+var_8E8], rax
0x18000a79f  mov     [rsp+948h+var_8E0], 5
0x18000a7a8  mov     [rsp+948h+var_8D8], 3FFh
0x18000a7b1  mov     [rsp+948h+var_8D0], 64h ; 'd'
0x18000a7ba  mov     [rsp+948h+var_8C8], r12
0x18000a7c2  mov     [rsp+948h+var_8B8], rax
0x18000a7ca  lea     rax, [rsp+948h+var_8B0]
0x18000a7d2  mov     [rsp+948h+ppv], rax; ppv
0x18000a7d7  lea     r9, IID_INDFEtw; riid
0x18000a7de  xor     edx, edx; pUnkOuter
0x18000a7e0  lea     r8d, [rdx+1]; dwClsContext
0x18000a7e4  lea     rcx, CLSID_NDFEtw; rclsid
0x18000a7eb  call    cs:__imp_CoCreateInstance
0x18000a7f1  mov     rdx, [rsp+948h+var_8B0]
0x18000a7f9  test    eax, eax
0x18000a7fb  cmovnz  rdx, r12
0x18000a7ff  mov     [rsp+948h+var_8B0], rdx
0x18000a807  lea     r8, [rsp+948h+var_8A8]
0x18000a80f  lea     rdx, [rsp+948h+var_888]
0x18000a817  lea     rcx, [rsp+948h+var_8F8]
0x18000a81c  call    ?findMatches@StringEnumerationMatcher@@QEAAXAEAV?$Enumerator@PEAG@@AEAVEditDistance@@@Z; StringEnumerationMatcher::findMatches(Enumerator<ushort *> &,EditDistance &)
0x18000a821  cmp     [rsp+948h+var_8F0], r12
0x18000a826  jbe     short loc_18000A875
0x18000a828  lea     rdx, [rsp+948h+var_848]; unsigned __int16 *
0x18000a830  lea     rcx, [rsp+948h+var_8F8]; this
0x18000a835  call    ?concatenateMatches@StringEnumerationMatcher@@QEAAXPEAG_K@Z; StringEnumerationMatcher::concatenateMatches(ushort *,unsigned __int64)
0x18000a83a  mov     rdx, [r15+20h]; void *
0x18000a83e  lea     rcx, [rsp+948h+hMutex]; this
0x18000a843  call    ??0AutoMutex@@QEAA@PEAXK@Z; AutoMutex::AutoMutex(void *,ulong)
0x18000a848  mov     rcx, [rsp+948h+hMutex]; hMutex
0x18000a84d  call    cs:__imp_ReleaseMutex
0x18000a853  mov     rax, [r15+8]
0x18000a857  cmp     [rax], r12d
0x18000a85a  jnz     short loc_18000A8D7
0x18000a85c  lea     r8, [rsp+948h+var_848]; unsigned __int16 *
0x18000a864  lea     rdx, aSharecandidate; "ShareCandidates"
0x18000a86b  mov     rcx, [r15+28h]; this
0x18000a86f  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x18000a874  nop
0x18000a875  lea     rcx, [rsp+948h+var_8F8]; this
0x18000a87a  call    ??1StringEnumerationMatcher@@QEAA@XZ; StringEnumerationMatcher::~StringEnumerationMatcher(void)
0x18000a87f  nop
0x18000a880  mov     rcx, [rsp+948h+var_8A8]
0x18000a888  test    rcx, rcx
0x18000a88b  jz      short loc_18000A894
0x18000a88d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a893  nop
0x18000a894  lea     rcx, [rsp+948h+var_888]; this
0x18000a89c  call    ??1NetShareEnumerator@@QEAA@XZ; NetShareEnumerator::~NetShareEnumerator(void)
0x18000a8a1  nop
0x18000a8a2  jmp     short loc_18000A8A9
0x18000a8a4  mov     rdi, [rsp+948h+pv]
0x18000a8a9  mov     rcx, rdi; pv
0x18000a8ac  call    cs:__imp_CoTaskMemFree
0x18000a8b2  jmp     short $+2
0x18000a8b4  mov     rcx, [rsp+948h+var_48]
0x18000a8bc  xor     rcx, rsp; StackCookie
0x18000a8bf  call    __security_check_cookie
0x18000a8c4  add     rsp, 910h
0x18000a8cb  pop     r15
0x18000a8cd  pop     r14
0x18000a8cf  pop     r13
0x18000a8d1  pop     r12
0x18000a8d3  pop     rdi
0x18000a8d4  pop     rsi
0x18000a8d5  pop     rbx
0x18000a8d6  retn
0x18000a8d7  mov     [rsp+948h+pExceptionObject], 0Ah
0x18000a8df  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18000a8e6  lea     rcx, [rsp+948h+pExceptionObject]; pExceptionObject
0x18000a8eb  call    _CxxThrowException_0
```

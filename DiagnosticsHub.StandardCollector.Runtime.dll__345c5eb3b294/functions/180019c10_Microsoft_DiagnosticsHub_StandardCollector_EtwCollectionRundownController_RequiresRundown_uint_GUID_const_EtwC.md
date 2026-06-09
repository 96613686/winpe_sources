# Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::RequiresRundown(uint,_GUID const &,EtwConfigurationType,Microsoft::DiagnosticsHub::StandardCollector::EtwEventRoutingFlagsInternal,unsigned __int64,uchar,EtwProviderConfig &)

- ea: `0x180019c10`
- end: `0x180019e98`
- name: `?RequiresRundown@EtwCollectionRundownController@StandardCollector@DiagnosticsHub@Microsoft@@IEAA_NIAEBU_GUID@@W4EtwConfigurationType@@W4EtwEventRoutingFlagsInternal@234@_KEAEAUEtwProviderConfig@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c978`

## callees

- `0x18000b518`
- `0x18000b760`
- `0x180019c10`
- `0x18003d864`
- `0x180048d90`
- `0x18004a03c`

## import_xrefs

- `VCRUNTIME140!memcmp` at `0x180019c7e`
- `VCRUNTIME140!memcmp` at `0x180019c9f`
- `VCRUNTIME140!memcmp` at `0x180019d14`
- `VCRUNTIME140!memcmp` at `0x180019c7e`
- `VCRUNTIME140!memcmp` at `0x180019c9f`
- `VCRUNTIME140!memcmp` at `0x180019d14`
- `KERNEL32!ResetEvent` at `0x180019e47`
- `KERNEL32!ResetEvent` at `0x180019e47`
- `KERNEL32!LeaveCriticalSection` at `0x180019e77`
- `KERNEL32!LeaveCriticalSection` at `0x180019e77`
- `KERNEL32!EnterCriticalSection` at `0x180019d47`
- `KERNEL32!EnterCriticalSection` at `0x180019d47`

## string_xrefs

- `0x180019e20`: `Already performing rundown '%d' for process %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Microsoft::DiagnosticsHub::StandardCollector::EtwCollectionRundownController::RequiresRundown(
        __int64 a1,
        unsigned int a2,
        const struct _GUID *a3,
        int a4,
        int a5,
        __int64 a6,
        char a7,
        __int64 a8)
{
  unsigned int v11; // esi
  __int64 v12; // r13
  unsigned __int64 v13; // rdi
  struct _RTL_CRITICAL_SECTION *v14; // rbx
  _QWORD *v15; // r15
  __int64 *v16; // rdi
  __int64 *v17; // rcx
  int v18; // edx
  __int64 *v19; // r8
  __int64 *v20; // rax
  char v21; // al
  _DWORD *v22; // rax
  __int64 v23; // rcx
  __int64 v25; // [rsp+20h] [rbp-50h]
  bool v26[16]; // [rsp+30h] [rbp-40h] BYREF
  __int128 v27; // [rsp+40h] [rbp-30h] BYREF
  __int128 v28; // [rsp+50h] [rbp-20h]
  struct _RTL_CRITICAL_SECTION *v29; // [rsp+68h] [rbp-8h]

  *(struct _GUID *)a8 = *a3;
  *(_DWORD *)(a8 + 20) = a4;
  *(_DWORD *)(a8 + 16) |= a5 | 0x80000000;
  *(_QWORD *)(a8 + 24) = a6;
  *(_BYTE *)(a8 + 32) = a7;
  if ( (int)Microsoft::EventTrace::Utilities::IsProviderRegisteredInProcess(a3, a2, v26) < 0 )
    return 0;
  _mm_lfence();
  if ( memcmp(a3, &SystemTraceControlGuid, 0x10u) )
  {
    _mm_lfence();
    if ( !memcmp(a3, qword_1800569E8, 0x10u) )
    {
      if ( v26[0]
        || (_mm_lfence(),
            (int)Microsoft::EventTrace::Utilities::IsProviderRegisteredInProcess(&stru_1800569D8, a2, v26) >= 0)
        && v26[0] )
      {
        if ( (a6 & 0x2050878) != 0 )
        {
          *(struct _GUID *)a8 = stru_1800569D8;
          *(_QWORD *)(a8 + 24) |= 0x40uLL;
          v11 = 1;
          goto LABEL_13;
        }
      }
    }
    else if ( v26[0] )
    {
      _mm_lfence();
      if ( !memcmp(a3, qword_1800569C8, 0x10u) )
      {
        v11 = 2;
        *(_QWORD *)(a8 + 24) |= 2uLL;
        goto LABEL_13;
      }
    }
    return 0;
  }
  v11 = 0;
LABEL_13:
  v12 = *(_QWORD *)(a1 + 8);
  v13 = (unsigned __int64)v11 << 6;
  *(_BYTE *)(v13 + v12 + 24) = 1;
  v14 = (struct _RTL_CRITICAL_SECTION *)(v13 + v12 + 32);
  v29 = v14;
  EnterCriticalSection(v14);
  v15 = (_QWORD *)(v13 + v12 + 72);
  v16 = (__int64 *)*v15;
  v17 = *(__int64 **)(*v15 + 8LL);
  v18 = 0;
  v19 = (__int64 *)*v15;
  if ( !*((_BYTE *)v17 + 25) )
  {
    v20 = *(__int64 **)(*v15 + 8LL);
    do
    {
      v17 = v20;
      if ( *((_DWORD *)v20 + 7) >= a2 )
      {
        v18 = 1;
        v19 = v20;
      }
      else
      {
        v18 = 0;
        v20 += 2;
      }
      v20 = (__int64 *)*v20;
    }
    while ( !*((_BYTE *)v20 + 25) );
  }
  *(_QWORD *)&v28 = v17;
  DWORD2(v28) = v18;
  if ( *((_BYTE *)v19 + 25) || a2 < *((_DWORD *)v19 + 7) )
  {
    if ( v15[1] == 0x7FFFFFFFFFFFFFFLL )
      std::_Throw_tree_length_error();
    v27 = (unsigned __int64)v15;
    v22 = operator new(0x20u);
    v22[7] = a2;
    *(_QWORD *)v22 = v16;
    *((_QWORD *)v22 + 1) = v16;
    *((_QWORD *)v22 + 2) = v16;
    *((_WORD *)v22 + 12) = 0;
    v27 = v28;
    std::_Tree_val<std::_Tree_simple_types<ATL::CComBSTR>>::_Insert_node(v15, &v27, v22);
    v21 = 1;
  }
  else
  {
    v21 = 0;
  }
  _mm_lfence();
  if ( !v21 )
  {
    _mm_lfence();
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 112),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRundownController.cpp",
      L"Already performing rundown '%d' for process %d",
      v11,
      a2);
  }
  v23 = *(_QWORD *)(v12 + 216);
  if ( *(int *)(v23 + 8) >= 0 )
    ResetEvent(*(HANDLE *)v23);
  LODWORD(v25) = a2;
  DiagHubCommon::LogStream::Write(
    (DiagHubCommon::LogStream *)((char *)_logger + 56),
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\EtwCollectionRundownController.cpp",
    L"Enabled rundown '%d' for process %d",
    v11,
    v25);
  LeaveCriticalSection(v14);
  return 1;
}

```

## disassembly

```asm
0x180019c10  push    rbp
0x180019c12  push    rbx
0x180019c13  push    rsi
0x180019c14  push    rdi
0x180019c15  push    r13
0x180019c17  push    r14
0x180019c19  push    r15
0x180019c1b  mov     rbp, rsp
0x180019c1e  sub     rsp, 70h
0x180019c22  mov     rdi, r8
0x180019c25  mov     r14d, edx
0x180019c28  mov     r13, rcx
0x180019c2b  mov     rbx, [rbp+arg_38]
0x180019c2f  movups  xmm0, xmmword ptr [r8]
0x180019c33  movdqu  xmmword ptr [rbx], xmm0
0x180019c37  mov     [rbx+14h], r9d
0x180019c3b  mov     eax, [rbp+arg_20]
0x180019c3e  or      eax, 80000000h
0x180019c43  or      [rbx+10h], eax
0x180019c46  mov     rsi, [rbp+arg_28]
0x180019c4a  mov     [rbx+18h], rsi
0x180019c4e  mov     al, [rbp+arg_30]
0x180019c51  mov     [rbx+20h], al
0x180019c54  lea     r8, [rbp+var_40]; bool *
0x180019c58  mov     rcx, rdi; struct _GUID *
0x180019c5b  call    ?IsProviderRegisteredInProcess@Utilities@EventTrace@Microsoft@@SAJAEBU_GUID@@IAEA_N@Z; Microsoft::EventTrace::Utilities::IsProviderRegisteredInProcess(_GUID const &,uint,bool &)
0x180019c60  test    eax, eax
0x180019c62  js      loc_180019E81
0x180019c68  lfence
0x180019c6b  mov     r15d, 10h
0x180019c71  mov     r8d, r15d; Size
0x180019c74  lea     rdx, SystemTraceControlGuid; Buf2
0x180019c7b  mov     rcx, rdi; Buf1
0x180019c7e  call    cs:__imp_memcmp
0x180019c84  test    eax, eax
0x180019c86  jnz     short loc_180019C8F
0x180019c88  xor     esi, esi
0x180019c8a  jmp     loc_180019D29
0x180019c8f  lfence
0x180019c92  mov     r8, r15; Size
0x180019c95  lea     rdx, qword_1800569E8; Buf2
0x180019c9c  mov     rcx, rdi; Buf1
0x180019c9f  call    cs:__imp_memcmp
0x180019ca5  test    eax, eax
0x180019ca7  jnz     short loc_180019CFA
0x180019ca9  cmp     [rbp+var_40], al
0x180019cac  jnz     short loc_180019CD6
0x180019cae  lfence
0x180019cb1  lea     r8, [rbp+var_40]; bool *
0x180019cb5  mov     edx, r14d; unsigned int
0x180019cb8  lea     rcx, stru_1800569D8; struct _GUID *
0x180019cbf  call    ?IsProviderRegisteredInProcess@Utilities@EventTrace@Microsoft@@SAJAEBU_GUID@@IAEA_N@Z; Microsoft::EventTrace::Utilities::IsProviderRegisteredInProcess(_GUID const &,uint,bool &)
0x180019cc4  test    eax, eax
0x180019cc6  js      loc_180019E81
0x180019ccc  cmp     [rbp+var_40], 0
0x180019cd0  jz      loc_180019E81
0x180019cd6  test    rsi, 2050878h
0x180019cdd  jz      loc_180019E81
0x180019ce3  movups  xmm0, xmmword ptr cs:stru_1800569D8.Data1
0x180019cea  movdqu  xmmword ptr [rbx], xmm0
0x180019cee  or      qword ptr [rbx+18h], 40h
0x180019cf3  mov     esi, 1
0x180019cf8  jmp     short loc_180019D29
0x180019cfa  cmp     [rbp+var_40], 0
0x180019cfe  jz      loc_180019E81
0x180019d04  lfence
0x180019d07  mov     r8, r15; Size
0x180019d0a  lea     rdx, qword_1800569C8; Buf2
0x180019d11  mov     rcx, rdi; Buf1
0x180019d14  call    cs:__imp_memcmp
0x180019d1a  test    eax, eax
0x180019d1c  jnz     loc_180019E81
0x180019d22  lea     esi, [rax+2]
0x180019d25  or      [rbx+18h], rsi
0x180019d29  mov     r13, [r13+8]
0x180019d2d  mov     edi, esi
0x180019d2f  shl     rdi, 6
0x180019d33  mov     byte ptr [rdi+r13+18h], 1
0x180019d39  lea     rbx, [r13+20h]
0x180019d3d  add     rbx, rdi
0x180019d40  mov     [rbp+var_8], rbx
0x180019d44  mov     rcx, rbx; lpCriticalSection
0x180019d47  call    cs:__imp_EnterCriticalSection
0x180019d4d  nop
0x180019d4e  lea     r15, [r13+48h]
0x180019d52  add     r15, rdi
0x180019d55  mov     rdi, [r15]
0x180019d58  mov     rcx, [rdi+8]
0x180019d5c  xor     edx, edx
0x180019d5e  mov     r8, rdi
0x180019d61  cmp     [rcx+19h], dl
0x180019d64  jnz     short loc_180019D8B
0x180019d66  mov     rax, rcx
0x180019d69  mov     rcx, rax
0x180019d6c  cmp     [rax+1Ch], r14d
0x180019d70  jnb     short loc_180019D7A
0x180019d72  xor     edx, edx
0x180019d74  add     rax, 10h
0x180019d78  jmp     short loc_180019D82
0x180019d7a  mov     edx, 1
0x180019d7f  mov     r8, rax
0x180019d82  mov     rax, [rax]
0x180019d85  cmp     byte ptr [rax+19h], 0
0x180019d89  jz      short loc_180019D69
0x180019d8b  mov     qword ptr [rbp+var_20], rcx
0x180019d8f  mov     dword ptr [rbp+var_20+8], edx
0x180019d92  mov     eax, dword ptr [rbp+var_20+0Ch]
0x180019d95  mov     dword ptr [rbp+var_20+0Ch], eax
0x180019d98  cmp     byte ptr [r8+19h], 0
0x180019d9d  jnz     short loc_180019DA9
0x180019d9f  cmp     r14d, [r8+1Ch]
0x180019da3  jb      short loc_180019DA9
0x180019da5  xor     al, al
0x180019da7  jmp     short loc_180019E03
0x180019da9  mov     rax, 7FFFFFFFFFFFFFFh
0x180019db3  cmp     [r15+8], rax
0x180019db7  jz      loc_180019E92
0x180019dbd  mov     qword ptr [rbp+var_30], r15
0x180019dc1  mov     qword ptr [rbp+var_30+8], 0
0x180019dc9  mov     ecx, 20h ; ' '; Size
0x180019dce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019dd3  nop
0x180019dd4  mov     [rax+1Ch], r14d
0x180019dd8  mov     [rax], rdi
0x180019ddb  mov     [rax+8], rdi
0x180019ddf  mov     [rax+10h], rdi
0x180019de3  mov     word ptr [rax+18h], 0
0x180019de9  movups  xmm0, [rbp+var_20]
0x180019ded  movdqu  [rbp+var_30], xmm0
0x180019df2  mov     r8, rax
0x180019df5  lea     rdx, [rbp+var_30]
0x180019df9  mov     rcx, r15
0x180019dfc  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@VCComBSTR@ATL@@@std@@@std@@QEAAPEAU?$_Tree_node@VCComBSTR@ATL@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@VCComBSTR@ATL@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ATL::CComBSTR>>::_Insert_node(std::_Tree_id<std::_Tree_node<ATL::CComBSTR,void *> *>,std::_Tree_node<ATL::CComBSTR,void *> * const)
0x180019e01  mov     al, 1
0x180019e03  lfence
0x180019e06  test    al, al
0x180019e08  jnz     short loc_180019E33
0x180019e0a  lfence
0x180019e0d  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180019e14  add     rcx, 70h ; 'p'; this
0x180019e18  mov     [rsp+70h+var_50], r14d
0x180019e1d  mov     r9d, esi
0x180019e20  lea     r8, aAlreadyPerform; "Already performing rundown '%d' for pro"...
0x180019e27  lea     rdx, aDAWork1SSource_16; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180019e2e  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180019e33  mov     rcx, [r13+0D8h]
0x180019e3a  mov     eax, [rcx+8]
0x180019e3d  shr     eax, 1Fh
0x180019e40  test    al, al
0x180019e42  jnz     short loc_180019E4D
0x180019e44  mov     rcx, [rcx]; hEvent
0x180019e47  call    cs:__imp_ResetEvent
0x180019e4d  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180019e54  add     rcx, 38h ; '8'; this
0x180019e58  mov     [rsp+70h+var_50], r14d
0x180019e5d  mov     r9d, esi
0x180019e60  lea     r8, aEnabledRundown; "Enabled rundown '%d' for process %d"
0x180019e67  lea     rdx, aDAWork1SSource_16; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180019e6e  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180019e73  nop
0x180019e74  mov     rcx, rbx; lpCriticalSection
0x180019e77  call    cs:__imp_LeaveCriticalSection
0x180019e7d  mov     al, 1
0x180019e7f  jmp     short loc_180019E83
0x180019e81  xor     al, al
0x180019e83  add     rsp, 70h
0x180019e87  pop     r15
0x180019e89  pop     r14
0x180019e8b  pop     r13
0x180019e8d  pop     rdi
0x180019e8e  pop     rsi
0x180019e8f  pop     rbx
0x180019e90  pop     rbp
0x180019e91  retn
0x180019e92  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```

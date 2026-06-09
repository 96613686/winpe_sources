# Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::UpdateHeadlessGraphUpdates(HeadlessGraphUpdates const &)

- ea: `0x18000aa24`
- end: `0x18000af6d`
- name: `?UpdateHeadlessGraphUpdates@CollectionSessionController@StandardCollector@DiagnosticsHub@Microsoft@@IEAAJAEBUHeadlessGraphUpdates@@@Z`
- size: `1353`
- prototype: `__int64 __fastcall(Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *__hidden this, const struct HeadlessGraphUpdates *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a8c0`

## callees

- `0x180002604`
- `0x180008898`
- `0x18000aa24`
- `0x18000b518`
- `0x18000b760`
- `0x18003d864`
- `0x180049b50`
- `0x18004a03c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000aded`
- `KERNEL32!LeaveCriticalSection` at `0x18000aeed`
- `KERNEL32!LeaveCriticalSection` at `0x18000aded`
- `KERNEL32!LeaveCriticalSection` at `0x18000aeed`
- `KERNEL32!EnterCriticalSection` at `0x18000ab27`
- `KERNEL32!EnterCriticalSection` at `0x18000ae22`
- `KERNEL32!EnterCriticalSection` at `0x18000ab27`
- `KERNEL32!EnterCriticalSection` at `0x18000ae22`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000ab0b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000ab0b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000aba5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18000aba5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000ab6e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18000ab6e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18000aaec`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18000aaec`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000aafe`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000adf7`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000aafe`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18000adf7`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18000aaa0`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x18000aaa0`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000ad6e`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18000ad6e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000ad82`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000ad82`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18000ac00`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18000ac48`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18000aca4`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18000ad05`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18000ac00`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18000ac48`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18000aca4`
- `OLEAUT32!__imp_VarBstrCmp` at `0x18000ad05`

## string_xrefs

- `0x18000ae3b`: `Headless graph update frequency set: %d ms`
- `0x18000ae59`: `Headless graph update counters:`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController::UpdateHeadlessGraphUpdates(
        Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *this,
        const struct HeadlessGraphUpdates *a2)
{
  Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *v2; // rsi
  int v4; // eax
  SAFEARRAY *v5; // rbx
  HRESULT Vartype; // eax
  VARTYPE v7; // cx
  HRESULT v8; // edi
  struct _RTL_CRITICAL_SECTION *v9; // rdi
  SAFEARRAY *v10; // rbx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  __int64 v13; // rax
  BSTR *pvData; // rcx
  _QWORD *v15; // r13
  __int64 v16; // rsi
  __int64 v17; // r14
  HRESULT v18; // eax
  __int64 v19; // rcx
  __int64 *v20; // rcx
  __int64 *v21; // r14
  int v22; // r12d
  unsigned int Count; // eax
  __int64 v24; // rax
  int v25; // ecx
  __int64 *v26; // rsi
  OLECHAR *v27; // rdx
  __int64 v28; // r14
  _QWORD *v29; // rsi
  BSTR *v30; // rax
  OLECHAR *v31; // rcx
  UINT v32; // eax
  __int64 v33; // rax
  __int64 *v34; // rbx
  __int64 **v35; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v38; // [rsp+20h] [rbp-A8h]
  SAFEARRAY *psa; // [rsp+28h] [rbp-A0h] BYREF
  unsigned int v40; // [rsp+30h] [rbp-98h]
  __int128 v41; // [rsp+40h] [rbp-88h] BYREF
  Microsoft::DiagnosticsHub::StandardCollector::CollectionSessionController *v42; // [rsp+50h] [rbp-78h]
  char *v43; // [rsp+58h] [rbp-70h]
  _QWORD *v44; // [rsp+60h] [rbp-68h]
  _QWORD *v45; // [rsp+68h] [rbp-60h]
  __int128 v46; // [rsp+70h] [rbp-58h]
  VARTYPE pvt[2]; // [rsp+88h] [rbp-40h] BYREF
  LONG plUbound[2]; // [rsp+90h] [rbp-38h] BYREF

  v2 = this;
  v42 = this;
  if ( *((_DWORD *)this + 232) != 2 )
    return 1;
  v4 = *(_DWORD *)a2;
  if ( *(int *)a2 > 0 )
  {
    if ( v4 < 100 )
      return 2147942487LL;
    *((_DWORD *)this + 240) = v4;
  }
  v5 = (SAFEARRAY *)*((_QWORD *)a2 + 1);
  if ( v5 )
  {
    psa = 0;
    Vartype = SafeArrayGetVartype(v5, pvt);
    if ( Vartype < 0 )
    {
      _mm_lfence();
      ATL::AtlThrowImpl(Vartype);
    }
    v7 = pvt[0];
    if ( pvt[0] == 13 && (v5->fFeatures & 0x440) == 0x440 )
    {
      v7 = 9;
      pvt[0] = 9;
    }
    if ( v7 != 8 )
      ATL::AtlThrowImpl(-2147024809);
    psa = v5;
    v8 = SafeArrayLock(v5);
    if ( v8 < 0 )
    {
      _mm_lfence();
      if ( SafeArrayUnlock(v5) >= 0 )
        SafeArrayDestroy(v5);
      return (unsigned int)v8;
    }
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)v2 + 984);
    v43 = (char *)v2 + 984;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 984));
    try
    {
      Count = ATL::CComSafeArray<unsigned short *,8>::GetCount(&psa);
      v40 = Count;
      v22 = 0;
      v10 = psa;
      while ( 1 )
      {
        if ( v22 >= Count )
        {
          LeaveCriticalSection(v9);
          SafeArrayUnlock(v10);
          goto LABEL_77;
        }
        if ( !v10 )
          ATL::AtlThrowImpl(-2147467259);
        *(_DWORD *)pvt = 0;
        LBound = SafeArrayGetLBound(v10, 1u, (LONG *)pvt);
        if ( LBound < 0 )
        {
          _mm_lfence();
          ATL::AtlThrowImpl(LBound);
        }
        if ( v22 < *(int *)pvt )
          goto LABEL_73;
        _mm_lfence();
        plUbound[0] = 0;
        UBound = SafeArrayGetUBound(v10, 1u, plUbound);
        if ( UBound < 0 )
        {
          _mm_lfence();
          ATL::AtlThrowImpl(UBound);
        }
        if ( v22 > plUbound[0] )
LABEL_73:
          ATL::AtlThrowImpl(-2147024809);
        v13 = v22 - *(_DWORD *)pvt;
        v38 = v13;
        pvData = (BSTR *)v10->pvData;
        *(_QWORD *)plUbound = pvData;
        v15 = (_QWORD *)((char *)v2 + 968);
        v16 = *((_QWORD *)v2 + 121);
        v17 = *(_QWORD *)(v16 + 8);
        while ( !*(_BYTE *)(v17 + 25) )
        {
          v18 = VarBstrCmp(*(BSTR *)(v17 + 32), pvData[v13], 0x400u, 0);
          v19 = v17;
          if ( !v18 )
            v19 = v16;
          v16 = v19;
          v20 = (__int64 *)(v17 + 16);
          if ( v18 )
            v20 = (__int64 *)v17;
          v17 = *v20;
          v13 = v38;
          pvData = *(BSTR **)plUbound;
        }
        if ( *(_BYTE *)(v16 + 25) || !VarBstrCmp(pvData[v13], *(BSTR *)(v16 + 32), 0x400u, 0) )
        {
          v21 = (__int64 *)*v15;
        }
        else
        {
          v21 = (__int64 *)*v15;
          if ( v16 != *v15 )
            goto LABEL_34;
        }
        v24 = v21[1];
        v25 = 0;
        if ( !*(_BYTE *)(v24 + 25) )
        {
          v26 = (__int64 *)v21[1];
          do
          {
            *(_QWORD *)&v41 = v26;
            if ( VarBstrCmp((BSTR)v26[4], *(BSTR *)(*(_QWORD *)plUbound + 8 * v38), 0x400u, 0) )
            {
              v25 = 1;
              v21 = v26;
            }
            else
            {
              v25 = 0;
              v26 += 2;
            }
            v26 = (__int64 *)*v26;
          }
          while ( !*((_BYTE *)v26 + 25) );
          v24 = v41;
        }
        *(_QWORD *)&v46 = v24;
        DWORD2(v46) = v25;
        if ( *((_BYTE *)v21 + 25) )
        {
          v28 = v38;
        }
        else
        {
          _mm_lfence();
          v27 = (OLECHAR *)v21[4];
          v28 = v38;
          if ( VarBstrCmp(*(BSTR *)(*(_QWORD *)plUbound + 8 * v38), v27, 0x400u, 0) )
            goto LABEL_34;
        }
        if ( v15[1] == 0x666666666666666LL )
          std::_Throw_tree_length_error();
        *(_QWORD *)&v41 = *v15;
        v44 = v15;
        v45 = 0;
        v29 = operator new(0x28u);
        _mm_lfence();
        v45 = v29;
        v30 = *(BSTR **)plUbound;
        v31 = *(OLECHAR **)(*(_QWORD *)plUbound + 8 * v28);
        if ( v31 )
        {
          _mm_lfence();
          v32 = SysStringByteLen(v31);
          v31 = SysAllocStringByteLen(*(LPCSTR *)(*(_QWORD *)plUbound + 8 * v28), v32);
          v30 = *(BSTR **)plUbound;
        }
        v29[4] = v31;
        if ( v30[v28] && !v31 )
          ATL::AtlThrowImpl(-2147024882);
        v33 = v41;
        *v29 = v41;
        v29[1] = v33;
        v29[2] = v33;
        *((_WORD *)v29 + 12) = 0;
        v45 = 0;
        v41 = v46;
        std::_Tree_val<std::_Tree_simple_types<ATL::CComBSTR>>::_Insert_node(v15, &v41, v29);
LABEL_34:
        ++v22;
        v2 = v42;
        Count = v40;
      }
    }
    catch ( std::bad_alloc )
    {
      SafeArrayUnlock(psa);
      return 2147942414LL;
    }
LABEL_77:
    ;
  }
  if ( *((_QWORD *)_logger + 7) != *((_QWORD *)_logger + 8) )
  {
    v43 = (char *)v2 + 984;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 984));
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessionController.cpp",
      L"Headless graph update frequency set: %d ms",
      *((unsigned int *)v2 + 240));
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 56),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessionController.cpp",
      L"Headless graph update counters:");
    v34 = (__int64 *)**((_QWORD **)v2 + 121);
    while ( !*((_BYTE *)v34 + 25) )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 56),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessionController.cpp",
        L"    %s",
        v34[4]);
      v35 = (__int64 **)v34[2];
      if ( *((_BYTE *)v35 + 25) )
      {
        for ( i = (__int64 *)v34[1]; !*((_BYTE *)i + 25) && v34 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v34 = i;
        v34 = i;
      }
      else
      {
        v34 = (__int64 *)v34[2];
        for ( j = *v35; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v34 = j;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v2 + 984));
  }
  return 0;
}

```

## disassembly

```asm
0x18000aa24  mov     [rsp+arg_10], rbx
0x18000aa29  push    rsi
0x18000aa2a  push    rdi
0x18000aa2b  push    r12
0x18000aa2d  push    r13
0x18000aa2f  push    r14
0x18000aa31  sub     rsp, 0A0h
0x18000aa38  mov     rax, cs:__security_cookie
0x18000aa3f  xor     rax, rsp
0x18000aa42  mov     [rsp+0C8h+var_30], rax
0x18000aa4a  mov     rsi, rcx
0x18000aa4d  mov     [rsp+0C8h+var_78], rcx
0x18000aa52  cmp     dword ptr [rcx+3A0h], 2
0x18000aa59  jz      short loc_18000AA65
0x18000aa5b  mov     eax, 1
0x18000aa60  jmp     loc_18000AEF5
0x18000aa65  mov     eax, [rdx]
0x18000aa67  xor     r14d, r14d
0x18000aa6a  test    eax, eax
0x18000aa6c  jle     short loc_18000AA83
0x18000aa6e  cmp     eax, 64h ; 'd'
0x18000aa71  jge     short loc_18000AA7D
0x18000aa73  mov     eax, 80070057h
0x18000aa78  jmp     loc_18000AEF5
0x18000aa7d  mov     [rcx+3C0h], eax
0x18000aa83  mov     rbx, [rdx+8]
0x18000aa87  test    rbx, rbx
0x18000aa8a  jz      loc_18000ADFE
0x18000aa90  mov     [rsp+0C8h+psa], r14
0x18000aa95  lea     rdx, [rsp+0C8h+pvt]; pvt
0x18000aa9d  mov     rcx, rbx; psa
0x18000aaa0  call    cs:__imp_SafeArrayGetVartype
0x18000aaa6  test    eax, eax
0x18000aaa8  js      loc_18000AF62
0x18000aaae  movzx   ecx, [rsp+0C8h+pvt]
0x18000aab6  cmp     cx, 0Dh
0x18000aaba  jnz     short loc_18000AADA
0x18000aabc  movzx   eax, word ptr [rbx+2]
0x18000aac0  mov     edx, 440h
0x18000aac5  and     ax, dx
0x18000aac8  cmp     ax, dx
0x18000aacb  jnz     short loc_18000AADA
0x18000aacd  mov     ecx, 9
0x18000aad2  mov     [rsp+0C8h+pvt], cx
0x18000aada  cmp     cx, 8
0x18000aade  jnz     loc_18000AF1D
0x18000aae4  mov     [rsp+0C8h+psa], rbx
0x18000aae9  mov     rcx, rbx; psa
0x18000aaec  call    cs:__imp_SafeArrayLock
0x18000aaf2  mov     edi, eax
0x18000aaf4  test    eax, eax
0x18000aaf6  jns     short loc_18000AB18
0x18000aaf8  lfence
0x18000aafb  mov     rcx, rbx; psa
0x18000aafe  call    cs:__imp_SafeArrayUnlock
0x18000ab04  test    eax, eax
0x18000ab06  js      short loc_18000AB11
0x18000ab08  mov     rcx, rbx; psa
0x18000ab0b  call    cs:__imp_SafeArrayDestroy
0x18000ab11  mov     eax, edi
0x18000ab13  jmp     loc_18000AEF5
0x18000ab18  lea     rdi, [rsi+3D8h]
0x18000ab1f  mov     [rsp+0C8h+var_70], rdi
0x18000ab24  mov     rcx, rdi; lpCriticalSection
0x18000ab27  call    cs:__imp_EnterCriticalSection
0x18000ab2d  nop
0x18000ab2e  lea     rcx, [rsp+0C8h+psa]
0x18000ab33  call    ?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z; ATL::CComSafeArray<ushort *,8>::GetCount(uint)
0x18000ab38  mov     [rsp+0C8h+var_98], eax
0x18000ab3c  mov     r12d, r14d
0x18000ab3f  mov     rbx, [rsp+0C8h+psa]
0x18000ab44  cmp     r12d, eax
0x18000ab47  jnb     loc_18000ADEA
0x18000ab4d  test    rbx, rbx
0x18000ab50  jz      loc_18000AF28
0x18000ab56  mov     dword ptr [rsp+0C8h+pvt], r14d
0x18000ab5e  lea     r8, [rsp+0C8h+pvt]; plLbound
0x18000ab66  mov     edx, 1; nDim
0x18000ab6b  mov     rcx, rbx; psa
0x18000ab6e  call    cs:__imp_SafeArrayGetLBound
0x18000ab74  test    eax, eax
0x18000ab76  js      loc_18000AF32
0x18000ab7c  cmp     r12d, dword ptr [rsp+0C8h+pvt]
0x18000ab84  jl      loc_18000AF57
0x18000ab8a  lfence
0x18000ab8d  mov     [rsp+0C8h+plUbound], r14d
0x18000ab95  lea     r8, [rsp+0C8h+plUbound]; plUbound
0x18000ab9d  mov     edx, 1; nDim
0x18000aba2  mov     rcx, rbx; psa
0x18000aba5  call    cs:__imp_SafeArrayGetUBound
0x18000abab  test    eax, eax
0x18000abad  js      loc_18000AF3C
0x18000abb3  cmp     r12d, [rsp+0C8h+plUbound]
0x18000abbb  jg      loc_18000AF57
0x18000abc1  mov     eax, r12d
0x18000abc4  sub     eax, dword ptr [rsp+0C8h+pvt]
0x18000abcb  cdqe
0x18000abcd  mov     [rsp+0C8h+var_A8], rax
0x18000abd2  mov     rcx, [rbx+10h]
0x18000abd6  mov     qword ptr [rsp+0C8h+plUbound], rcx
0x18000abde  lea     r13, [rsi+3C8h]
0x18000abe5  mov     rsi, [r13+0]
0x18000abe9  mov     r14, [rsi+8]
0x18000abed  jmp     short loc_18000AC2A
0x18000abef  xor     r9d, r9d; dwFlags
0x18000abf2  mov     r8d, 400h; lcid
0x18000abf8  mov     rdx, [rcx+rax*8]; bstrRight
0x18000abfc  mov     rcx, [r14+20h]; bstrLeft
0x18000ac00  call    cs:__imp_VarBstrCmp
0x18000ac06  mov     rcx, r14
0x18000ac09  test    eax, eax
0x18000ac0b  cmovz   rcx, rsi
0x18000ac0f  mov     rsi, rcx
0x18000ac12  lea     rcx, [r14+10h]
0x18000ac16  cmovnz  rcx, r14
0x18000ac1a  mov     r14, [rcx]
0x18000ac1d  mov     rax, [rsp+0C8h+var_A8]
0x18000ac22  mov     rcx, qword ptr [rsp+0C8h+plUbound]
0x18000ac2a  cmp     byte ptr [r14+19h], 0
0x18000ac2f  jz      short loc_18000ABEF
0x18000ac31  cmp     byte ptr [rsi+19h], 0
0x18000ac35  jnz     short loc_18000AC6F
0x18000ac37  xor     r9d, r9d; dwFlags
0x18000ac3a  mov     r8d, 400h; lcid
0x18000ac40  mov     rdx, [rsi+20h]; bstrRight
0x18000ac44  mov     rcx, [rcx+rax*8]; bstrLeft
0x18000ac48  call    cs:__imp_VarBstrCmp
0x18000ac4e  test    eax, eax
0x18000ac50  jz      short loc_18000AC6F
0x18000ac52  mov     r14, [r13+0]
0x18000ac56  cmp     rsi, r14
0x18000ac59  jz      short loc_18000AC73
0x18000ac5b  xor     r14d, r14d
0x18000ac5e  inc     r12d
0x18000ac61  mov     rsi, [rsp+0C8h+var_78]
0x18000ac66  mov     eax, [rsp+0C8h+var_98]
0x18000ac6a  jmp     loc_18000AB44
0x18000ac6f  mov     r14, [r13+0]
0x18000ac73  mov     rax, [r14+8]
0x18000ac77  xor     ecx, ecx
0x18000ac79  cmp     [rax+19h], cl
0x18000ac7c  jnz     short loc_18000ACCC
0x18000ac7e  mov     rsi, rax
0x18000ac81  mov     qword ptr [rsp+0C8h+var_88], rsi
0x18000ac86  xor     r9d, r9d; dwFlags
0x18000ac89  mov     r8d, 400h; lcid
0x18000ac8f  mov     rax, [rsp+0C8h+var_A8]
0x18000ac94  mov     rcx, qword ptr [rsp+0C8h+plUbound]
0x18000ac9c  mov     rdx, [rcx+rax*8]; bstrRight
0x18000aca0  mov     rcx, [rsi+20h]; bstrLeft
0x18000aca4  call    cs:__imp_VarBstrCmp
0x18000acaa  test    eax, eax
0x18000acac  jnz     short loc_18000ACB6
0x18000acae  xor     ecx, ecx
0x18000acb0  add     rsi, 10h
0x18000acb4  jmp     short loc_18000ACBE
0x18000acb6  mov     ecx, 1
0x18000acbb  mov     r14, rsi
0x18000acbe  mov     rsi, [rsi]
0x18000acc1  cmp     byte ptr [rsi+19h], 0
0x18000acc5  jz      short loc_18000AC81
0x18000acc7  mov     rax, qword ptr [rsp+0C8h+var_88]
0x18000accc  mov     qword ptr [rsp+0C8h+var_58], rax
0x18000acd1  mov     dword ptr [rsp+0C8h+var_58+8], ecx
0x18000acd5  mov     eax, dword ptr [rsp+0C8h+var_58+0Ch]
0x18000acd9  mov     dword ptr [rsp+0C8h+var_58+0Ch], eax
0x18000acdd  cmp     byte ptr [r14+19h], 0
0x18000ace2  jnz     short loc_18000AD15
0x18000ace4  lfence
0x18000ace7  xor     r9d, r9d; dwFlags
0x18000acea  mov     r8d, 400h; lcid
0x18000acf0  mov     rdx, [r14+20h]; bstrRight
0x18000acf4  mov     r14, [rsp+0C8h+var_A8]
0x18000acf9  mov     rax, qword ptr [rsp+0C8h+plUbound]
0x18000ad01  mov     rcx, [rax+r14*8]; bstrLeft
0x18000ad05  call    cs:__imp_VarBstrCmp
0x18000ad0b  test    eax, eax
0x18000ad0d  jnz     loc_18000AC5B
0x18000ad13  jmp     short loc_18000AD1A
0x18000ad15  mov     r14, [rsp+0C8h+var_A8]
0x18000ad1a  mov     rax, 666666666666666h
0x18000ad24  cmp     [r13+8], rax
0x18000ad28  jz      loc_18000AF46
0x18000ad2e  mov     rax, [r13+0]
0x18000ad32  mov     qword ptr [rsp+0C8h+var_88], rax
0x18000ad37  mov     [rsp+0C8h+var_68], r13
0x18000ad3c  mov     [rsp+0C8h+var_60], 0
0x18000ad45  mov     ecx, 28h ; '('; Size
0x18000ad4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ad4f  mov     rsi, rax
0x18000ad52  lfence
0x18000ad55  mov     [rsp+0C8h+var_60], rax
0x18000ad5a  mov     rax, qword ptr [rsp+0C8h+plUbound]
0x18000ad62  mov     rcx, [rax+r14*8]; bstr
0x18000ad66  test    rcx, rcx
0x18000ad69  jz      short loc_18000AD93
0x18000ad6b  lfence
0x18000ad6e  call    cs:__imp_SysStringByteLen
0x18000ad74  mov     edx, eax; len
0x18000ad76  mov     rax, qword ptr [rsp+0C8h+plUbound]
0x18000ad7e  mov     rcx, [rax+r14*8]; psz
0x18000ad82  call    cs:__imp_SysAllocStringByteLen
0x18000ad88  mov     rcx, rax
0x18000ad8b  mov     rax, qword ptr [rsp+0C8h+plUbound]
0x18000ad93  mov     [rsi+20h], rcx
0x18000ad97  cmp     qword ptr [rax+r14*8], 0
0x18000ad9c  jz      short loc_18000ADAC
0x18000ad9e  xor     r14d, r14d
0x18000ada1  test    rcx, rcx
0x18000ada4  jz      loc_18000AF4C
0x18000adaa  jmp     short loc_18000ADAF
0x18000adac  xor     r14d, r14d
0x18000adaf  mov     rax, qword ptr [rsp+0C8h+var_88]
0x18000adb4  mov     [rsi], rax
0x18000adb7  mov     [rsi+8], rax
0x18000adbb  mov     [rsi+10h], rax
0x18000adbf  mov     word ptr [rsi+18h], 0
0x18000adc5  mov     [rsp+0C8h+var_60], r14
0x18000adca  movups  xmm0, [rsp+0C8h+var_58]
0x18000adcf  movdqu  [rsp+0C8h+var_88], xmm0
0x18000add5  mov     r8, rsi
0x18000add8  lea     rdx, [rsp+0C8h+var_88]
0x18000addd  mov     rcx, r13
0x18000ade0  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@VCComBSTR@ATL@@@std@@@std@@QEAAPEAU?$_Tree_node@VCComBSTR@ATL@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@VCComBSTR@ATL@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<ATL::CComBSTR>>::_Insert_node(std::_Tree_id<std::_Tree_node<ATL::CComBSTR,void *> *>,std::_Tree_node<ATL::CComBSTR,void *> * const)
0x18000ade5  jmp     loc_18000AC5E
0x18000adea  mov     rcx, rdi; lpCriticalSection
0x18000aded  call    cs:__imp_LeaveCriticalSection
0x18000adf3  nop
0x18000adf4  mov     rcx, rbx; psa
0x18000adf7  call    cs:__imp_SafeArrayUnlock
0x18000adfd  nop
0x18000adfe  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000ae05  mov     rax, [rcx+40h]
0x18000ae09  cmp     [rcx+38h], rax
0x18000ae0d  jz      loc_18000AEF3
0x18000ae13  lea     rdi, [rsi+3D8h]
0x18000ae1a  mov     [rsp+0C8h+var_70], rdi
0x18000ae1f  mov     rcx, rdi; lpCriticalSection
0x18000ae22  call    cs:__imp_EnterCriticalSection
0x18000ae28  nop
0x18000ae29  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000ae30  add     rcx, 38h ; '8'; this
0x18000ae34  mov     r9d, [rsi+3C0h]
0x18000ae3b  lea     r8, aHeadlessGraphU; "Headless graph update frequency set: %d"...
0x18000ae42  lea     rdx, aDAWork1SSource_3; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000ae49  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000ae4e  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000ae55  add     rcx, 38h ; '8'; this
0x18000ae59  lea     r8, aHeadlessGraphU_0; "Headless graph update counters:"
0x18000ae60  lea     rdx, aDAWork1SSource_3; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000ae67  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000ae6c  mov     rbx, [rsi+3C8h]
0x18000ae73  mov     rbx, [rbx]
0x18000ae76  jmp     short loc_18000AEE4
0x18000ae78  mov     eax, 8007000Eh
0x18000ae7d  jmp     short loc_18000AEF5
0x18000ae7f  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18000ae86  add     rcx, 38h ; '8'; this
0x18000ae8a  mov     r9, [rbx+20h]
0x18000ae8e  lea     r8, aS_1; "    %s"
0x18000ae95  lea     rdx, aDAWork1SSource_3; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18000ae9c  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18000aea1  mov     rcx, [rbx+10h]
0x18000aea5  cmp     [rcx+19h], r14b
0x18000aea9  jz      short loc_18000AEC9
0x18000aeab  mov     rax, [rbx+8]
0x18000aeaf  jmp     short loc_18000AEBE
0x18000aeb1  cmp     rbx, [rax+10h]
0x18000aeb5  jnz     short loc_18000AEC4
0x18000aeb7  mov     rbx, rax
0x18000aeba  mov     rax, [rax+8]
0x18000aebe  cmp     [rax+19h], r14b
0x18000aec2  jz      short loc_18000AEB1
0x18000aec4  mov     rbx, rax
0x18000aec7  jmp     short loc_18000AEE4
0x18000aec9  mov     rbx, rcx
0x18000aecc  mov     rcx, [rcx]
0x18000aecf  cmp     [rcx+19h], r14b
0x18000aed3  jnz     short loc_18000AEE4
0x18000aed5  mov     rbx, rcx
0x18000aed8  mov     rax, [rcx]
0x18000aedb  mov     rcx, rax
0x18000aede  cmp     [rax+19h], r14b
0x18000aee2  jz      short loc_18000AED5
0x18000aee4  cmp     [rbx+19h], r14b
0x18000aee8  jz      short loc_18000AE7F
0x18000aeea  mov     rcx, rdi; lpCriticalSection
0x18000aeed  call    cs:__imp_LeaveCriticalSection
0x18000aef3  xor     eax, eax
0x18000aef5  mov     rcx, [rsp+0C8h+var_30]
0x18000aefd  xor     rcx, rsp; StackCookie
0x18000af00  call    __security_check_cookie
0x18000af05  mov     rbx, [rsp+0C8h+arg_10]
0x18000af0d  add     rsp, 0A0h
0x18000af14  pop     r14
0x18000af16  pop     r13
0x18000af18  pop     r12
0x18000af1a  pop     rdi
0x18000af1b  pop     rsi
0x18000af1c  retn
  ... truncated ...
```

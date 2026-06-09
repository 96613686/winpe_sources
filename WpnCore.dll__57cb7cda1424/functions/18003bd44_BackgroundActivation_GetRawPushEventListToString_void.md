# BackgroundActivation::GetRawPushEventListToString(void)

- ea: `0x18003bd44`
- end: `0x18003bfa9`
- name: `?GetRawPushEventListToString@BackgroundActivation@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `613`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180035508`
- `0x18003c04c`

## callees

- `0x18000e5f4`
- `0x180011e6c`
- `0x180013360`
- `0x180014160`
- `0x180014220`
- `0x1800193e8`
- `0x18003bd44`
- `0x18003bfb0`
- `0x1800b99f0`
- `0x1800ca9d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003bf64`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003bf64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003bd81`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003bd81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003beac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003beac`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003be45`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18003be45`
- `OLEAUT32!__imp_SysStringLen` at `0x18003bdec`
- `OLEAUT32!__imp_SysStringLen` at `0x18003bdec`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall BackgroundActivation::GetRawPushEventListToString(RTL_SRWLOCK *a1, __int64 a2)
{
  __int64 v4; // rdx
  BSTR Ptr; // rsi
  __int64 v6; // r8
  char v7; // r15
  const IID *i; // rdi
  HRESULT v9; // eax
  __int64 v10; // r8
  const char *v11; // r9
  __int64 result; // rax
  __int64 v13; // rcx
  LPOLESTR lpsz; // [rsp+20h] [rbp-98h] BYREF
  __int64 v15; // [rsp+30h] [rbp-88h]
  RTL_SRWLOCK *v16; // [rsp+38h] [rbp-80h]
  char v17; // [rsp+40h] [rbp-78h]
  __int128 Src; // [rsp+48h] [rbp-70h] BYREF
  __int64 v19; // [rsp+58h] [rbp-60h]
  unsigned __int64 v20; // [rsp+60h] [rbp-58h]
  __int128 v21; // [rsp+68h] [rbp-50h] BYREF
  __m128i si128; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v15 = a2;
  AcquireSRWLockShared(a1 + 4);
  v16 = a1;
  v17 = 1;
  v21 = 0;
  si128 = 0;
  std::wstring::_Construct_empty(&v21, v4);
  Ptr = (BSTR)a1[2].Ptr;
  try
  {
    while ( Ptr != (BSTR)&a1[2] )
    {
      Src = 0;
      v19 = 0;
      v20 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&Src, L"{");
      v6 = SysStringLen(*((BSTR *)Ptr + 2));
      std::wstring::append(&Src, *((_QWORD *)Ptr + 2), v6);
      v7 = 0;
      std::wstring::_Append<unsigned short>(&Src);
      for ( i = (const IID *)*((_QWORD *)Ptr + 3); i != (const IID *)(Ptr + 12); i = *(const IID **)&i->Data1 )
      {
        if ( !i[2].Data1 )
        {
          lpsz = 0;
          v9 = StringFromCLSID(i + 1, &lpsz);
          if ( v9 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x621,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
              (const char *)(unsigned int)v9,
              (int)lpsz);
          v10 = -1;
          do
            ++v10;
          while ( lpsz[v10] );
          std::wstring::_Append<unsigned short>(&Src);
          std::wstring::_Append<unsigned short>(&Src);
          v7 = 1;
          if ( lpsz )
            CoTaskMemFree(lpsz);
        }
      }
      if ( v7 )
      {
        std::wstring::_Append<unsigned short>(&Src);
        std::wstring::_Append<unsigned short>(&v21);
      }
      Ptr = *(BSTR *)Ptr;
      if ( v20 > 7 )
        std::_Deallocate<16>((void *)Src, 2 * v20 + 2);
    }
    std::wstring::wstring(a2, &v21);
    if ( si128.m128i_i64[1] > 7uLL )
      std::_Deallocate<16>((void *)v21, 2 * si128.m128i_i64[1] + 2);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v21) = 0;
    ReleaseSRWLockShared(a1 + 4);
    result = a2;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x635,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\backgroundactivation.cpp",
      v11);
    std::wstring::wstring(v15);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x18003bd44  mov     [rsp+arg_10], rbx
0x18003bd49  mov     [rsp+arg_18], rsi
0x18003bd4e  push    rdi
0x18003bd4f  push    r12
0x18003bd51  push    r13
0x18003bd53  push    r14
0x18003bd55  push    r15
0x18003bd57  sub     rsp, 90h
0x18003bd5e  mov     rax, cs:__security_cookie
0x18003bd65  xor     rax, rsp
0x18003bd68  mov     [rsp+0B8h+var_30], rax
0x18003bd70  mov     r14, rdx
0x18003bd73  mov     rbx, rcx
0x18003bd76  mov     [rsp+0B8h+var_88], rdx
0x18003bd7b  xor     edi, edi
0x18003bd7d  add     rcx, 20h ; ' '; SRWLock
0x18003bd81  call    cs:__imp_AcquireSRWLockShared
0x18003bd87  mov     [rsp+0B8h+var_80], rbx
0x18003bd8c  mov     [rsp+0B8h+var_78], 1
0x18003bd91  xorps   xmm0, xmm0
0x18003bd94  movups  [rsp+0B8h+var_50], xmm0
0x18003bd99  xorps   xmm1, xmm1
0x18003bd9c  movdqu  [rsp+0B8h+var_40], xmm1
0x18003bda2  lea     rcx, [rsp+0B8h+var_50]
0x18003bda7  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18003bdac  nop
0x18003bdad  lea     r13, [rbx+10h]
0x18003bdb1  mov     rsi, [r13+0]
0x18003bdb5  cmp     rsi, r13
0x18003bdb8  jz      loc_18003BF1F
0x18003bdbe  xorps   xmm0, xmm0
0x18003bdc1  movups  [rsp+0B8h+Src], xmm0
0x18003bdc6  mov     [rsp+0B8h+var_60], rdi
0x18003bdcb  mov     [rsp+0B8h+var_58], rdi
0x18003bdd0  mov     r8d, 1
0x18003bdd6  lea     rdx, asc_180125564; "{"
0x18003bddd  lea     rcx, [rsp+0B8h+Src]
0x18003bde2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003bde7  nop
0x18003bde8  mov     rcx, [rsi+10h]; pbstr
0x18003bdec  call    cs:__imp_SysStringLen
0x18003bdf2  mov     r8d, eax
0x18003bdf5  mov     rdx, [rsi+10h]
0x18003bdf9  lea     rcx, [rsp+0B8h+Src]
0x18003bdfe  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::append(ushort const * const,unsigned __int64)
0x18003be03  mov     r15b, dil
0x18003be06  mov     r8d, 2
0x18003be0c  lea     rdx, asc_180125568; ": "
0x18003be13  lea     rcx, [rsp+0B8h+Src]; Src
0x18003be18  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003be1d  lea     r12, [rsi+18h]
0x18003be21  mov     rdi, [r12]
0x18003be25  cmp     rdi, r12
0x18003be28  jz      loc_18003BEBA
0x18003be2e  cmp     dword ptr [rdi+20h], 0
0x18003be32  jnz     short loc_18003BEB2
0x18003be34  xor     r15d, r15d
0x18003be37  mov     [rsp+0B8h+lpsz], r15; int
0x18003be3c  lea     rcx, [rdi+10h]; rclsid
0x18003be40  lea     rdx, [rsp+0B8h+lpsz]; lplpsz
0x18003be45  call    cs:__imp_StringFromCLSID
0x18003be4b  mov     rcx, [rsp+0B8h]; this
0x18003be53  test    eax, eax
0x18003be55  jns     short loc_18003BE6B
0x18003be57  mov     r9d, eax; char *
0x18003be5a  lea     r8, aOnecoreuapBase_147; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003be61  mov     edx, 621h; void *
0x18003be66  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003be6b  mov     rdx, [rsp+0B8h+lpsz]
0x18003be70  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003be74  inc     r8
0x18003be77  cmp     [rdx+r8*2], r15w
0x18003be7c  jnz     short loc_18003BE74
0x18003be7e  lea     rcx, [rsp+0B8h+Src]; Src
0x18003be83  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003be88  mov     r8d, 1
0x18003be8e  lea     rdx, asc_1801242B4; " "
0x18003be95  lea     rcx, [rsp+0B8h+Src]; Src
0x18003be9a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003be9f  mov     r15b, 1
0x18003bea2  mov     rcx, [rsp+0B8h+lpsz]; pv
0x18003bea7  test    rcx, rcx
0x18003beaa  jz      short loc_18003BEB2
0x18003beac  call    cs:__imp_CoTaskMemFree
0x18003beb2  mov     rdi, [rdi]
0x18003beb5  jmp     loc_18003BE25
0x18003beba  xor     edi, edi
0x18003bebc  test    r15b, r15b
0x18003bebf  jz      short loc_18003BEF6
0x18003bec1  lea     r8d, [rdi+2]
0x18003bec5  lea     rdx, asc_18012EE60; "} "
0x18003becc  lea     rcx, [rsp+0B8h+Src]; Src
0x18003bed1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003bed6  lea     rdx, [rsp+0B8h+Src]
0x18003bedb  cmp     [rsp+0B8h+var_58], 7
0x18003bee1  cmova   rdx, qword ptr [rsp+0B8h+Src]
0x18003bee7  mov     r8, [rsp+0B8h+var_60]
0x18003beec  lea     rcx, [rsp+0B8h+var_50]; Src
0x18003bef1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003bef6  mov     rsi, [rsi]
0x18003bef9  mov     rdx, [rsp+0B8h+var_58]
0x18003befe  cmp     rdx, 7
0x18003bf02  jbe     loc_18003BDB5
0x18003bf08  lea     rdx, ds:2[rdx*2]
0x18003bf10  mov     rcx, qword ptr [rsp+0B8h+Src]
0x18003bf15  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003bf1a  jmp     loc_18003BDB5
0x18003bf1f  lea     rdx, [rsp+0B8h+var_50]
0x18003bf24  mov     rcx, r14
0x18003bf27  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18003bf2c  nop
0x18003bf2d  mov     rdx, qword ptr [rsp+0B8h+var_40+8]
0x18003bf35  cmp     rdx, 7
0x18003bf39  jbe     short loc_18003BF4D
0x18003bf3b  lea     rdx, ds:2[rdx*2]
0x18003bf43  mov     rcx, qword ptr [rsp+0B8h+var_50]
0x18003bf48  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003bf4d  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18003bf55  movdqu  [rsp+0B8h+var_40], xmm0
0x18003bf5b  mov     word ptr [rsp+0B8h+var_50], di
0x18003bf60  lea     rcx, [rbx+20h]; SRWLock
0x18003bf64  call    cs:__imp_ReleaseSRWLockShared
0x18003bf6a  mov     rax, r14
0x18003bf6d  jmp     short loc_18003BF7C
0x18003bf6f  mov     rcx, [rsp+0B8h+var_88]
0x18003bf74  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003bf79  mov     rax, rcx
0x18003bf7c  mov     rcx, [rsp+0B8h+var_30]
0x18003bf84  xor     rcx, rsp; StackCookie
0x18003bf87  call    __security_check_cookie
0x18003bf8c  lea     r11, [rsp+0B8h+var_28]
0x18003bf94  mov     rbx, [r11+40h]
0x18003bf98  mov     rsi, [r11+48h]
0x18003bf9c  mov     rsp, r11
0x18003bf9f  pop     r15
0x18003bfa1  pop     r14
0x18003bfa3  pop     r13
0x18003bfa5  pop     r12
0x18003bfa7  pop     rdi
0x18003bfa8  retn
```

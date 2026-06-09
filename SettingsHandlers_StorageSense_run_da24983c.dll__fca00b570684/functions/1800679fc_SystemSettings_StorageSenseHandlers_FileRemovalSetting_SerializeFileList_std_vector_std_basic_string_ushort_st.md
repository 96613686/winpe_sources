# SystemSettings::StorageSenseHandlers::FileRemovalSetting::SerializeFileList(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,tagSAFEARRAY *)

- ea: `0x1800679fc`
- end: `0x180067b21`
- name: `?SerializeFileList@FileRemovalSetting@StorageSenseHandlers@SystemSettings@@IEAAJAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUtagSAFEARRAY@@@Z`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006697c`

## callees

- `0x180012374`
- `0x180023578`
- `0x1800679fc`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180067ad1`
- `OLEAUT32!__imp_SysAllocString` at `0x180067ad1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180067a69`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180067a69`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180067af9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180067af9`

## string_xrefs

- `0x180067a36`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180067a86`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\recommendationlist.cpp`
- `0x180067a2a`: `CleanupRecommendations`
- `0x180067a7a`: `CleanupRecommendations`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::FileRemovalSetting::SerializeFileList(
        void *a1,
        __int64 *a2,
        SAFEARRAY *a3)
{
  HRESULT v5; // ebx
  __int64 v6; // rdx
  HRESULT v8; // edi
  __int64 v9; // rdx
  unsigned __int64 v10; // rdi
  const OLECHAR *v11; // rax
  BSTR v12; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *ppvData; // [rsp+40h] [rbp+8h] BYREF

  ppvData = a1;
  if ( !a3 )
  {
    v5 = -2147467261;
    v6 = 781;
LABEL_3:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)v5,
      (int)"%hs",
      "CleanupRecommendations");
    return (unsigned int)v5;
  }
  ppvData = 0;
  v8 = SafeArrayAccessData(a3, &ppvData);
  if ( v8 >= 0 )
  {
    v9 = *a2;
    if ( (a2[1] - *a2) >> 5 )
    {
      v10 = 0;
      do
      {
        v11 = (const OLECHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9 + 32 * v10);
        v12 = SysAllocString(v11);
        *((_QWORD *)ppvData + v10++) = v12;
        v9 = *a2;
      }
      while ( v10 < (a2[1] - *a2) >> 5 );
    }
    v5 = SafeArrayUnaccessData(a3);
    if ( v5 < 0 )
    {
      v6 = 792;
      goto LABEL_3;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x311,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\recommendationlist.cpp",
      (const char *)(unsigned int)v8,
      (int)"%hs",
      "CleanupRecommendations");
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x1800679fc  mov     [rsp+arg_8], rbx
0x180067a01  mov     [rsp+arg_10], rsi
0x180067a06  mov     [rsp+ppvData], rcx
0x180067a0b  push    rdi
0x180067a0c  sub     rsp, 30h
0x180067a10  mov     rbx, r8
0x180067a13  mov     rsi, rdx
0x180067a16  test    r8, r8
0x180067a19  jnz     short loc_180067A58
0x180067a1b  mov     ebx, 80004003h
0x180067a20  mov     edx, 30Dh; void *
0x180067a25  mov     rcx, [rsp+38h]; this
0x180067a2a  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180067a31  mov     [rsp+38h+var_10], rax; char *
0x180067a36  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180067a3d  lea     rax, aHs; "%hs"
0x180067a44  mov     r9d, ebx; char *
0x180067a47  mov     qword ptr [rsp+38h+var_18], rax; int
0x180067a4c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180067a51  mov     eax, ebx
0x180067a53  jmp     loc_180067B11
0x180067a58  lea     rdx, [rsp+38h+ppvData]; ppvData
0x180067a5d  mov     [rsp+38h+ppvData], 0
0x180067a66  mov     rcx, rbx; psa
0x180067a69  call    cs:__imp_SafeArrayAccessData
0x180067a6f  mov     edi, eax
0x180067a71  test    eax, eax
0x180067a73  jns     short loc_180067AAA
0x180067a75  mov     rcx, [rsp+38h]; this
0x180067a7a  lea     rax, aCleanuprecomme; "CleanupRecommendations"
0x180067a81  mov     [rsp+38h+var_10], rax; char *
0x180067a86  lea     r8, aOnecoreuapShel_16; "onecoreuap\\shell\\coresettinghandlers"...
0x180067a8d  lea     rax, aHs; "%hs"
0x180067a94  mov     r9d, edi; char *
0x180067a97  mov     edx, 311h; void *
0x180067a9c  mov     qword ptr [rsp+38h+var_18], rax; int
0x180067aa1  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180067aa6  mov     eax, edi
0x180067aa8  jmp     short loc_180067B11
0x180067aaa  mov     rdx, [rsi]
0x180067aad  mov     rax, [rsi+8]
0x180067ab1  sub     rax, rdx
0x180067ab4  sar     rax, 5
0x180067ab8  test    rax, rax
0x180067abb  jz      short loc_180067AF6
0x180067abd  xor     edi, edi
0x180067abf  mov     rcx, rdi
0x180067ac2  shl     rcx, 5
0x180067ac6  add     rcx, rdx
0x180067ac9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180067ace  mov     rcx, rax; psz
0x180067ad1  call    cs:__imp_SysAllocString
0x180067ad7  mov     rcx, [rsp+38h+ppvData]
0x180067adc  mov     [rcx+rdi*8], rax
0x180067ae0  inc     rdi
0x180067ae3  mov     rdx, [rsi]
0x180067ae6  mov     rax, [rsi+8]
0x180067aea  sub     rax, rdx
0x180067aed  sar     rax, 5
0x180067af1  cmp     rdi, rax
0x180067af4  jb      short loc_180067ABF
0x180067af6  mov     rcx, rbx; psa
0x180067af9  call    cs:__imp_SafeArrayUnaccessData
0x180067aff  mov     ebx, eax
0x180067b01  test    eax, eax
0x180067b03  jns     short loc_180067B0F
0x180067b05  mov     edx, 318h
0x180067b0a  jmp     loc_180067A25
0x180067b0f  xor     eax, eax
0x180067b11  mov     rbx, [rsp+38h+arg_8]
0x180067b16  mov     rsi, [rsp+38h+arg_10]
0x180067b1b  add     rsp, 30h
0x180067b1f  pop     rdi
0x180067b20  retn
```

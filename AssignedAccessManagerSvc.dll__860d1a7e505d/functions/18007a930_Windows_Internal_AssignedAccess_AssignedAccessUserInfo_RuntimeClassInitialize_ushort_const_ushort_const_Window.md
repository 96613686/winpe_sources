# Windows::Internal::AssignedAccess::AssignedAccessUserInfo::RuntimeClassInitialize(ushort const *,ushort const *,Windows::Internal::AssignedAccess::IAssignedAccessProfile *,Windows::Internal::AssignedAccess::ConfigSource const &,Windows::Internal::AssignedAccess::AccountType)

- ea: `0x18007a930`
- end: `0x18007ac75`
- name: `?RuntimeClassInitialize@AssignedAccessUserInfo@AssignedAccess@Internal@Windows@@QEAAJPEBG0PEAUIAssignedAccessProfile@234@AEBW4ConfigSource@234@W4AccountType@234@@Z`
- size: `837`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007a340`
- `0x18007ac7c`

## callees

- `0x180006640`
- `0x180008d89`
- `0x18000b6b4`
- `0x18000cfe4`
- `0x180010590`
- `0x18002074c`
- `0x1800221e0`
- `0x18002be50`
- `0x180066fc4`
- `0x180074914`
- `0x18007a75c`
- `0x18007a930`
- `0x180096010`

## string_xrefs

- `0x18007a971`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessuserinfo.cpp`
- `0x18007a99e`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessuserinfo.cpp`
- `0x18007a9d2`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessuserinfo.cpp`
- `0x18007aa17`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessuserinfo.cpp`
- `0x18007aa5a`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessuserinfo.cpp`
- `0x18007ab18`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessuserinfo.cpp`
- `0x18007abb0`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessuserinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessUserInfo::RuntimeClassInitialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        int a6)
{
  int v11; // eax
  unsigned int v12; // edi
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  unsigned int v18; // edi
  int i; // eax
  _QWORD *v20; // rsi
  int v21; // eax
  unsigned int v22; // edi
  __int64 v23; // rcx
  __int64 v24; // rdi
  int v25; // [rsp+20h] [rbp-98h] BYREF
  __int64 v26; // [rsp+28h] [rbp-90h] BYREF
  __int64 v27; // [rsp+30h] [rbp-88h] BYREF
  int v28; // [rsp+38h] [rbp-80h]
  __int64 v29; // [rsp+40h] [rbp-78h] BYREF
  __int64 v30; // [rsp+48h] [rbp-70h] BYREF
  _BYTE v31[8]; // [rsp+50h] [rbp-68h] BYREF
  int v32; // [rsp+58h] [rbp-60h]
  _BYTE v33[8]; // [rsp+60h] [rbp-58h] BYREF
  __int128 Buf1; // [rsp+68h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  if ( a2 )
  {
    if ( a4 )
    {
      if ( *a5 )
      {
        Buf1 = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a4 + 56LL))(a4, &Buf1);
        v12 = v11;
        if ( v11 >= 0 )
        {
          if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1E,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessuserinfo.cpp",
              (const char *)0x80070057LL,
              v25);
            return 2147942487LL;
          }
          else
          {
            *(_OWORD *)(a1 + 72) = Buf1;
            wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>::operator=(
              a1 + 88,
              a4);
            v13 = std::_WChar_traits<unsigned short>::length(a2);
            std::wstring::_Assign<unsigned short>(a1 + 104, a2, v13);
            if ( a3 )
            {
              v14 = std::_WChar_traits<unsigned short>::length(a3);
              std::wstring::_Assign<unsigned short>(a1 + 136, a3, v14);
            }
            *(_DWORD *)(a1 + 168) = *a5;
            *(_DWORD *)(a1 + 176) = a6;
            *(_DWORD *)(a1 + 172) = Windows::Internal::AssignedAccess::AssignedAccessUserInfo::ExtractAssignedAccessTypeFromProfile(a4);
            v26 = 0;
            v15 = *(__int64 **)(a1 + 88);
            v16 = *v15;
            v26 = 0;
            v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v16 + 120))(v15, &v26);
            v18 = v17;
            if ( v17 >= 0 )
            {
              v30 = v26;
              v27 = v26;
              v28 = 0;
              v29 = 0;
              wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Management::MdmAlert *>,wil::err_exception_policy>::end(
                &v30,
                v31);
              for ( i = v28; i != v32; i = ++v28 )
              {
                v20 = (_QWORD *)wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,wil::err_exception_policy>::vector_iterator::operator*(&v27);
                LOBYTE(v25) = 0;
                v21 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v20 + 96LL))(*v20, &v25);
                v22 = v21;
                if ( v21 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2F,
                    (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessuserinfo.cpp",
                    (const char *)(unsigned int)v21,
                    v25);
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v33);
                  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
                  wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v26);
                  return v22;
                }
                if ( (_BYTE)v25 )
                {
                  v23 = *v20;
                  v24 = *(_QWORD *)(a1 + 96);
                  *(_QWORD *)(a1 + 96) = *v20;
                  if ( v23 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
                  if ( v24 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                  break;
                }
              }
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v33);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v26);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2B,
                (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessuserinfo.cpp",
                (const char *)(unsigned int)v17,
                v25);
              wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(&v26);
              return v18;
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D,
            (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessuserinfo.cpp",
            (const char *)(unsigned int)v11,
            v25);
          return v12;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessuserinfo.cpp",
          (const char *)0x80070057LL,
          v25);
        return 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A,
        (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessuserinfo.cpp",
        (const char *)0x80070057LL,
        v25);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessuserinfo.cpp",
      (const char *)0x80070057LL,
      v25);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18007a930  push    rbx
0x18007a932  push    rsi
0x18007a933  push    rdi
0x18007a934  push    r12
0x18007a936  push    r14
0x18007a938  push    r15
0x18007a93a  sub     rsp, 88h
0x18007a941  mov     rax, cs:__security_cookie
0x18007a948  xor     rax, rsp
0x18007a94b  mov     [rsp+0B8h+var_40], rax
0x18007a950  mov     rsi, r9
0x18007a953  mov     r14, r8
0x18007a956  mov     r12, rdx
0x18007a959  mov     rbx, rcx
0x18007a95c  test    rdx, rdx
0x18007a95f  jnz     short loc_18007A989
0x18007a961  mov     rcx, [rsp+0B8h]; this
0x18007a969  mov     ebx, 80070057h
0x18007a96e  mov     r9d, ebx; char *
0x18007a971  lea     r8, aOnecoreuapBase_97; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007a978  lea     edx, [r12+19h]; void *
0x18007a97d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a982  mov     eax, ebx
0x18007a984  jmp     loc_18007AC46
0x18007a989  test    rsi, rsi
0x18007a98c  jnz     short loc_18007A9B4
0x18007a98e  mov     rcx, [rsp+0B8h]; this
0x18007a996  mov     ebx, 80070057h
0x18007a99b  mov     r9d, ebx; char *
0x18007a99e  lea     r8, aOnecoreuapBase_97; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007a9a5  lea     edx, [rsi+1Ah]; void *
0x18007a9a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a9ad  mov     eax, ebx
0x18007a9af  jmp     loc_18007AC46
0x18007a9b4  mov     r15, [rsp+0B8h+arg_20]
0x18007a9bc  cmp     dword ptr [r15], 0
0x18007a9c0  jnz     short loc_18007A9EA
0x18007a9c2  mov     rcx, [rsp+0B8h]; this
0x18007a9ca  mov     ebx, 80070057h
0x18007a9cf  mov     r9d, ebx; char *
0x18007a9d2  lea     r8, aOnecoreuapBase_97; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007a9d9  mov     edx, 1Bh; void *
0x18007a9de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a9e3  mov     eax, ebx
0x18007a9e5  jmp     loc_18007AC46
0x18007a9ea  xorps   xmm0, xmm0
0x18007a9ed  movups  [rsp+0B8h+Buf1], xmm0
0x18007a9f2  mov     rax, [r9]
0x18007a9f5  lea     rdx, [rsp+0B8h+Buf1]
0x18007a9fa  mov     rcx, rsi
0x18007a9fd  mov     rax, [rax+38h]
0x18007aa01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aa06  mov     edi, eax
0x18007aa08  test    eax, eax
0x18007aa0a  jns     short loc_18007AA2F
0x18007aa0c  mov     rcx, [rsp+0B8h]; this
0x18007aa14  mov     r9d, eax; char *
0x18007aa17  lea     r8, aOnecoreuapBase_97; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007aa1e  mov     edx, 1Dh; void *
0x18007aa23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007aa28  mov     eax, edi
0x18007aa2a  jmp     loc_18007AC46
0x18007aa2f  mov     r8d, 10h; Size
0x18007aa35  lea     rdx, GUID_NULL; Buf2
0x18007aa3c  lea     rcx, [rsp+0B8h+Buf1]; Buf1
0x18007aa41  call    memcmp_0
0x18007aa46  test    eax, eax
0x18007aa48  jnz     short loc_18007AA70
0x18007aa4a  mov     rcx, [rsp+0B8h]; this
0x18007aa52  mov     ebx, 80070057h
0x18007aa57  mov     r9d, ebx; char *
0x18007aa5a  lea     r8, aOnecoreuapBase_97; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007aa61  lea     edx, [rax+1Eh]; void *
0x18007aa64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007aa69  mov     eax, ebx
0x18007aa6b  jmp     loc_18007AC46
0x18007aa70  movups  xmm0, [rsp+0B8h+Buf1]
0x18007aa75  movdqu  xmmword ptr [rbx+48h], xmm0
0x18007aa7a  mov     rdx, rsi
0x18007aa7d  lea     rcx, [rbx+58h]
0x18007aa81  call    ??4?$com_ptr_t@UIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIAssignedAccessUserInfo@AssignedAccess@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::AssignedAccess::IAssignedAccessUserInfo,wil::err_exception_policy>::operator=(Windows::Internal::AssignedAccess::IAssignedAccessUserInfo *)
0x18007aa86  mov     rcx, r12
0x18007aa89  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18007aa8e  lea     rcx, [rbx+68h]
0x18007aa92  mov     r8, rax
0x18007aa95  mov     rdx, r12
0x18007aa98  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007aa9d  test    r14, r14
0x18007aaa0  jz      short loc_18007AABC
0x18007aaa2  mov     rcx, r14
0x18007aaa5  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18007aaaa  lea     rcx, [rbx+88h]
0x18007aab1  mov     r8, rax
0x18007aab4  mov     rdx, r14
0x18007aab7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18007aabc  mov     eax, [r15]
0x18007aabf  mov     [rbx+0A8h], eax
0x18007aac5  mov     eax, [rsp+0B8h+arg_28]
0x18007aacc  mov     [rbx+0B0h], eax
0x18007aad2  mov     rcx, rsi
0x18007aad5  call    ?ExtractAssignedAccessTypeFromProfile@AssignedAccessUserInfo@AssignedAccess@Internal@Windows@@CA?AW4AssignedAccessType@234@PEAUIAssignedAccessProfile@234@@Z; Windows::Internal::AssignedAccess::AssignedAccessUserInfo::ExtractAssignedAccessTypeFromProfile(Windows::Internal::AssignedAccess::IAssignedAccessProfile *)
0x18007aada  mov     [rbx+0ACh], eax
0x18007aae0  mov     [rsp+0B8h+var_90], 0
0x18007aae9  mov     rcx, [rbx+58h]
0x18007aaed  mov     rax, [rcx]
0x18007aaf0  mov     [rsp+0B8h+var_90], 0
0x18007aaf9  lea     rdx, [rsp+0B8h+var_90]
0x18007aafe  mov     rax, [rax+78h]
0x18007ab02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ab07  mov     edi, eax
0x18007ab09  test    eax, eax
0x18007ab0b  jns     short loc_18007AB3B
0x18007ab0d  mov     rcx, [rsp+0B8h]; this
0x18007ab15  mov     r9d, eax; char *
0x18007ab18  lea     r8, aOnecoreuapBase_97; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007ab1f  mov     edx, 2Bh ; '+'; void *
0x18007ab24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ab29  nop
0x18007ab2a  lea     rcx, [rsp+0B8h+var_90]
0x18007ab2f  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18007ab34  mov     eax, edi
0x18007ab36  jmp     loc_18007AC46
0x18007ab3b  mov     rax, [rsp+0B8h+var_90]
0x18007ab40  mov     [rsp+0B8h+var_70], rax
0x18007ab45  mov     [rsp+0B8h+var_88], rax
0x18007ab4a  mov     [rsp+0B8h+var_80], 0
0x18007ab52  mov     [rsp+0B8h+var_78], 0
0x18007ab5b  lea     rdx, [rsp+0B8h+var_68]
0x18007ab60  lea     rcx, [rsp+0B8h+var_70]
0x18007ab65  call    ?end@?$vector_range@U?$IVectorView@PEAVMdmAlert@Management@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Management::MdmAlert *>,wil::err_exception_policy>::end(void)
0x18007ab6a  nop
0x18007ab6b  mov     eax, [rsp+0B8h+var_80]
0x18007ab6f  cmp     eax, [rsp+0B8h+var_60]
0x18007ab73  jz      loc_18007AC1E
0x18007ab79  lea     rcx, [rsp+0B8h+var_88]
0x18007ab7e  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@PEAVAssignedAccessApplication@AssignedAccess@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIAssignedAccessApplication@AssignedAccess@Internal@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::AssignedAccess::AssignedAccessApplication *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x18007ab83  mov     rsi, rax
0x18007ab86  mov     byte ptr [rsp+0B8h+var_98], 0; int
0x18007ab8b  mov     rcx, [rax]
0x18007ab8e  mov     rdx, [rcx]
0x18007ab91  mov     rax, [rdx+60h]
0x18007ab95  lea     rdx, [rsp+0B8h+var_98]
0x18007ab9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ab9f  mov     edi, eax
0x18007aba1  test    eax, eax
0x18007aba3  jns     short loc_18007ABE6
0x18007aba5  mov     rcx, [rsp+0B8h]; this
0x18007abad  mov     r9d, eax; char *
0x18007abb0  lea     r8, aOnecoreuapBase_97; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x18007abb7  mov     edx, 2Fh ; '/'; void *
0x18007abbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007abc1  nop
0x18007abc2  lea     rcx, [rsp+0B8h+var_58]
0x18007abc7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007abcc  nop
0x18007abcd  lea     rcx, [rsp+0B8h+var_78]
0x18007abd2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007abd7  nop
0x18007abd8  lea     rcx, [rsp+0B8h+var_90]
0x18007abdd  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18007abe2  mov     eax, edi
0x18007abe4  jmp     short loc_18007AC46
0x18007abe6  cmp     byte ptr [rsp+0B8h+var_98], 0
0x18007abeb  jz      short loc_18007AC64
0x18007abed  mov     rcx, [rsi]
0x18007abf0  mov     rdi, [rbx+60h]
0x18007abf4  mov     [rbx+60h], rcx
0x18007abf8  test    rcx, rcx
0x18007abfb  jz      short loc_18007AC09
0x18007abfd  mov     rax, [rcx]
0x18007ac00  mov     rax, [rax+8]
0x18007ac04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac09  test    rdi, rdi
0x18007ac0c  jz      short loc_18007AC1E
0x18007ac0e  mov     rax, [rdi]
0x18007ac11  mov     rcx, rdi
0x18007ac14  mov     rax, [rax+10h]
0x18007ac18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac1d  nop
0x18007ac1e  lea     rcx, [rsp+0B8h+var_58]
0x18007ac23  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007ac28  nop
0x18007ac29  lea     rcx, [rsp+0B8h+var_78]
0x18007ac2e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007ac33  nop
0x18007ac34  lea     rcx, [rsp+0B8h+var_90]
0x18007ac39  call    ??1?$com_ptr_t@UIStorageFolder@Storage@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>::~com_ptr_t<Windows::Storage::IStorageFolder,wil::err_exception_policy>(void)
0x18007ac3e  xor     eax, eax
0x18007ac40  jmp     short loc_18007AC46
0x18007ac42  mov     eax, dword ptr [rsp+0B8h+var_90]
0x18007ac46  mov     rcx, [rsp+0B8h+var_40]
0x18007ac4b  xor     rcx, rsp; StackCookie
0x18007ac4e  call    __security_check_cookie
0x18007ac53  add     rsp, 88h
0x18007ac5a  pop     r15
0x18007ac5c  pop     r14
0x18007ac5e  pop     r12
0x18007ac60  pop     rdi
0x18007ac61  pop     rsi
0x18007ac62  pop     rbx
0x18007ac63  retn
0x18007ac64  mov     eax, [rsp+0B8h+var_80]
0x18007ac68  inc     eax
0x18007ac6a  mov     [rsp+0B8h+var_80], eax
0x18007ac6e  jmp     loc_18007AB6F
```

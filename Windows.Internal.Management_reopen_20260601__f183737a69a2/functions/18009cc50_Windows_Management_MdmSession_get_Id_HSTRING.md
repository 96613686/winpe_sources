# Windows::Management::MdmSession::get_Id(HSTRING__ * *)

- ea: `0x18009cc50`
- end: `0x18009ce41`
- name: `?get_Id@MdmSession@Management@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(PVOID Parameter, HSTRING *newString)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004eb0`
- `0x18000a5c4`
- `0x18000dc18`
- `0x180017024`
- `0x1800340e4`
- `0x18009b028`
- `0x18009c8d4`
- `0x18009c930`
- `0x18009cc50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18009ccb2`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18009ccb2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009cd1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009cdbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009ce11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009cd1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009cdbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009ce11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18009cced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18009cced`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ccff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cda2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cdf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009ccff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cda2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009cdf2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Management::MdmSession::get_Id(RTL_SRWLOCK *Parameter, HSTRING *newString)
{
  __int64 result; // rax
  struct _RTL_SRWLOCK *v5; // r15
  char v6; // al
  RTL_SRWLOCK *v7; // rbx
  HSTRING v8; // rcx
  const char *v9; // r9
  __int64 first_of; // rax
  const unsigned __int16 *v11; // rax
  int v12; // eax
  unsigned int v13; // esi
  int v14; // [rsp+20h] [rbp-68h]
  HSTRING string; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-50h]
  int v17; // [rsp+3Ch] [rbp-4Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-48h]
  _BYTE v19[32]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !newString )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
      (const char *)0x80004003LL,
      v14);
    return 2147500035LL;
  }
  v17 = 123;
  v5 = Parameter + 17;
  v6 = -TryAcquireSRWLockShared(Parameter + 17);
  v7 = (RTL_SRWLOCK *)((unsigned __int64)v5 & -(__int64)(v6 != 0));
  SRWLock = v7;
  if ( !v7 )
    Windows::Management::MdmSession::WaitSessionLock(Parameter, v5);
  try
  {
    string = 0;
    if ( Parameter[10].Ptr )
    {
      first_of = std::wstring::find_first_of(&Parameter[8], &v17);
      std::wstring::wstring(v19, &Parameter[8], first_of, -1);
      v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v19);
      v12 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v11, 0x27u);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x223,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
          (const char *)(unsigned int)v12,
          v14);
        std::wstring::~wstring(v19);
        WindowsDeleteString(string);
        string = 0;
        if ( v7 )
        {
          ReleaseSRWLockShared(v7);
          SRWLock = 0;
        }
        return v13;
      }
      std::wstring::~wstring(v19);
      v8 = string;
    }
    else
    {
      v8 = 0;
    }
    WindowsDuplicateString(v8, newString);
    WindowsDeleteString(string);
    string = 0;
    if ( v7 )
      ReleaseSRWLockShared(v7);
    result = 0;
  }
  catch ( ... )
  {
    v16 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x225,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsession.cpp",
            v9);
    WindowsDeleteString(string);
    string = 0;
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    return v16;
  }
  return result;
}

```

## disassembly

```asm
0x18009cc50  mov     [rsp+arg_10], rbx
0x18009cc55  push    rsi
0x18009cc56  push    r14
0x18009cc58  push    r15
0x18009cc5a  sub     rsp, 70h
0x18009cc5e  mov     rax, cs:__security_cookie
0x18009cc65  xor     rax, rsp
0x18009cc68  mov     [rsp+88h+var_20], rax
0x18009cc6d  mov     r14, rdx
0x18009cc70  mov     rsi, rcx
0x18009cc73  test    rdx, rdx
0x18009cc76  jnz     short loc_18009CCA0
0x18009cc78  mov     rcx, [rsp+88h]; this
0x18009cc80  mov     ebx, 80004003h
0x18009cc85  mov     r9d, ebx; char *
0x18009cc88  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009cc8f  mov     edx, 20Ah; void *
0x18009cc94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009cc99  mov     eax, ebx
0x18009cc9b  jmp     loc_18009CE21
0x18009cca0  mov     [rsp+88h+var_4C], 7Bh ; '{'
0x18009cca8  lea     r15, [rcx+88h]
0x18009ccaf  mov     rcx, r15; SRWLock
0x18009ccb2  call    cs:__imp_TryAcquireSRWLockShared
0x18009ccb9  nop     dword ptr [rax+rax+00h]
0x18009ccbe  neg     al
0x18009ccc0  sbb     rbx, rbx
0x18009ccc3  and     rbx, r15
0x18009ccc6  mov     [rsp+88h+SRWLock], rbx
0x18009cccb  jnz     short loc_18009CCD8
0x18009cccd  mov     rdx, r15; struct _RTL_SRWLOCK *
0x18009ccd0  mov     rcx, rsi; Parameter
0x18009ccd3  call    ?WaitSessionLock@MdmSession@Management@Windows@@AEAAXPEAU_RTL_SRWLOCK@@@Z; Windows::Management::MdmSession::WaitSessionLock(_RTL_SRWLOCK *)
0x18009ccd8  mov     [rsp+88h+string], 0
0x18009cce1  cmp     qword ptr [rsi+50h], 0
0x18009cce6  jnz     short loc_18009CD2F
0x18009cce8  xor     ecx, ecx; string
0x18009ccea  mov     rdx, r14; newString
0x18009cced  call    cs:__imp_WindowsDuplicateString
0x18009ccf4  nop     dword ptr [rax+rax+00h]
0x18009ccf9  nop
0x18009ccfa  mov     rcx, [rsp+88h+string]; string
0x18009ccff  call    cs:__imp_WindowsDeleteString
0x18009cd06  nop     dword ptr [rax+rax+00h]
0x18009cd0b  mov     [rsp+88h+string], 0
0x18009cd14  test    rbx, rbx
0x18009cd17  jz      short loc_18009CD28
0x18009cd19  mov     rcx, rbx; SRWLock
0x18009cd1c  call    cs:__imp_ReleaseSRWLockShared
0x18009cd23  nop     dword ptr [rax+rax+00h]
0x18009cd28  xor     eax, eax
0x18009cd2a  jmp     loc_18009CE21
0x18009cd2f  lea     rdx, [rsp+88h+var_4C]
0x18009cd34  lea     rcx, [rsi+40h]
0x18009cd38  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_of(ushort const * const,unsigned __int64)
0x18009cd3d  nop
0x18009cd3e  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009cd42  mov     r8, rax
0x18009cd45  lea     rdx, [rsi+40h]
0x18009cd49  lea     rcx, [rsp+88h+var_40]
0x18009cd4e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x18009cd53  lea     rcx, [rsp+88h+var_40]
0x18009cd58  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009cd5d  mov     rdx, rax; unsigned __int16 *
0x18009cd60  mov     r8d, 27h ; '''; unsigned int
0x18009cd66  lea     rcx, [rsp+88h+string]; this
0x18009cd6b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18009cd70  mov     esi, eax
0x18009cd72  test    eax, eax
0x18009cd74  jns     short loc_18009CDD8
0x18009cd76  mov     rcx, [rsp+88h]; this
0x18009cd7e  mov     r9d, eax; char *
0x18009cd81  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009cd88  mov     edx, 223h; void *
0x18009cd8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009cd92  lea     rcx, [rsp+88h+var_40]
0x18009cd97  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009cd9c  nop
0x18009cd9d  mov     rcx, [rsp+88h+string]; string
0x18009cda2  call    cs:__imp_WindowsDeleteString
0x18009cda9  nop     dword ptr [rax+rax+00h]
0x18009cdae  mov     [rsp+88h+string], 0
0x18009cdb7  test    rbx, rbx
0x18009cdba  jz      short loc_18009CDD4
0x18009cdbc  mov     rcx, rbx; SRWLock
0x18009cdbf  call    cs:__imp_ReleaseSRWLockShared
0x18009cdc6  nop     dword ptr [rax+rax+00h]
0x18009cdcb  mov     [rsp+88h+SRWLock], 0
0x18009cdd4  mov     eax, esi
0x18009cdd6  jmp     short loc_18009CE21
0x18009cdd8  lea     rcx, [rsp+88h+var_40]
0x18009cddd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009cde2  nop
0x18009cde3  mov     rcx, [rsp+88h+string]
0x18009cde8  jmp     loc_18009CCEA
0x18009cded  mov     rcx, [rsp+88h+string]; string
0x18009cdf2  call    cs:__imp_WindowsDeleteString
0x18009cdf9  nop     dword ptr [rax+rax+00h]
0x18009cdfe  mov     [rsp+88h+string], 0
0x18009ce07  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x18009ce0c  test    rcx, rcx
0x18009ce0f  jz      short loc_18009CE1D
0x18009ce11  call    cs:__imp_ReleaseSRWLockShared
0x18009ce18  nop     dword ptr [rax+rax+00h]
0x18009ce1d  mov     eax, [rsp+88h+var_50]
0x18009ce21  mov     rcx, [rsp+88h+var_20]
0x18009ce26  xor     rcx, rsp; StackCookie
0x18009ce29  call    __security_check_cookie
0x18009ce2e  mov     rbx, [rsp+88h+arg_10]
0x18009ce36  add     rsp, 70h
0x18009ce3a  pop     r15
0x18009ce3c  pop     r14
0x18009ce3e  pop     rsi
0x18009ce3f  retn
```

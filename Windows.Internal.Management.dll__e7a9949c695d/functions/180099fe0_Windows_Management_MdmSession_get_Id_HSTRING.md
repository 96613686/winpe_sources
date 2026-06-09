# Windows::Management::MdmSession::get_Id(HSTRING__ * *)

- ea: `0x180099fe0`
- end: `0x18009a1a0`
- name: `?get_Id@MdmSession@Management@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(PVOID Parameter, HSTRING *newString)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004d50`
- `0x18000a2a4`
- `0x18000d724`
- `0x1800168d0`
- `0x180034fcc`
- `0x180098524`
- `0x180099ca0`
- `0x180099cf0`
- `0x180099fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18009a042`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockShared` at `0x18009a042`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009a09a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009a131`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009a177`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009a09a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009a131`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18009a177`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18009a077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18009a077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a11a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a15e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a083`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a11a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a15e`

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
0x180099fe0  mov     [rsp+arg_10], rbx
0x180099fe5  push    rsi
0x180099fe6  push    r14
0x180099fe8  push    r15
0x180099fea  sub     rsp, 70h
0x180099fee  mov     rax, cs:__security_cookie
0x180099ff5  xor     rax, rsp
0x180099ff8  mov     [rsp+88h+var_20], rax
0x180099ffd  mov     r14, rdx
0x18009a000  mov     rsi, rcx
0x18009a003  test    rdx, rdx
0x18009a006  jnz     short loc_18009A030
0x18009a008  mov     rcx, [rsp+88h]; this
0x18009a010  mov     ebx, 80004003h
0x18009a015  mov     r9d, ebx; char *
0x18009a018  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009a01f  mov     edx, 20Ah; void *
0x18009a024  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a029  mov     eax, ebx
0x18009a02b  jmp     loc_18009A181
0x18009a030  mov     [rsp+88h+var_4C], 7Bh ; '{'
0x18009a038  lea     r15, [rcx+88h]
0x18009a03f  mov     rcx, r15; SRWLock
0x18009a042  call    cs:__imp_TryAcquireSRWLockShared
0x18009a048  neg     al
0x18009a04a  sbb     rbx, rbx
0x18009a04d  and     rbx, r15
0x18009a050  mov     [rsp+88h+SRWLock], rbx
0x18009a055  jnz     short loc_18009A062
0x18009a057  mov     rdx, r15; struct _RTL_SRWLOCK *
0x18009a05a  mov     rcx, rsi; Parameter
0x18009a05d  call    ?WaitSessionLock@MdmSession@Management@Windows@@AEAAXPEAU_RTL_SRWLOCK@@@Z; Windows::Management::MdmSession::WaitSessionLock(_RTL_SRWLOCK *)
0x18009a062  mov     [rsp+88h+string], 0
0x18009a06b  cmp     qword ptr [rsi+50h], 0
0x18009a070  jnz     short loc_18009A0A7
0x18009a072  xor     ecx, ecx; string
0x18009a074  mov     rdx, r14; newString
0x18009a077  call    cs:__imp_WindowsDuplicateString
0x18009a07d  nop
0x18009a07e  mov     rcx, [rsp+88h+string]; string
0x18009a083  call    cs:__imp_WindowsDeleteString
0x18009a089  mov     [rsp+88h+string], 0
0x18009a092  test    rbx, rbx
0x18009a095  jz      short loc_18009A0A0
0x18009a097  mov     rcx, rbx; SRWLock
0x18009a09a  call    cs:__imp_ReleaseSRWLockShared
0x18009a0a0  xor     eax, eax
0x18009a0a2  jmp     loc_18009A181
0x18009a0a7  lea     rdx, [rsp+88h+var_4C]
0x18009a0ac  lea     rcx, [rsi+40h]
0x18009a0b0  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_first_of(ushort const * const,unsigned __int64)
0x18009a0b5  nop
0x18009a0b6  or      r9, 0FFFFFFFFFFFFFFFFh
0x18009a0ba  mov     r8, rax
0x18009a0bd  lea     rdx, [rsi+40h]
0x18009a0c1  lea     rcx, [rsp+88h+var_40]
0x18009a0c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x18009a0cb  lea     rcx, [rsp+88h+var_40]
0x18009a0d0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009a0d5  mov     rdx, rax; unsigned __int16 *
0x18009a0d8  mov     r8d, 27h ; '''; unsigned int
0x18009a0de  lea     rcx, [rsp+88h+string]; this
0x18009a0e3  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18009a0e8  mov     esi, eax
0x18009a0ea  test    eax, eax
0x18009a0ec  jns     short loc_18009A144
0x18009a0ee  mov     rcx, [rsp+88h]; this
0x18009a0f6  mov     r9d, eax; char *
0x18009a0f9  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009a100  mov     edx, 223h; void *
0x18009a105  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a10a  lea     rcx, [rsp+88h+var_40]
0x18009a10f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009a114  nop
0x18009a115  mov     rcx, [rsp+88h+string]; string
0x18009a11a  call    cs:__imp_WindowsDeleteString
0x18009a120  mov     [rsp+88h+string], 0
0x18009a129  test    rbx, rbx
0x18009a12c  jz      short loc_18009A140
0x18009a12e  mov     rcx, rbx; SRWLock
0x18009a131  call    cs:__imp_ReleaseSRWLockShared
0x18009a137  mov     [rsp+88h+SRWLock], 0
0x18009a140  mov     eax, esi
0x18009a142  jmp     short loc_18009A181
0x18009a144  lea     rcx, [rsp+88h+var_40]
0x18009a149  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009a14e  nop
0x18009a14f  mov     rcx, [rsp+88h+string]
0x18009a154  jmp     loc_18009A074
0x18009a159  mov     rcx, [rsp+88h+string]; string
0x18009a15e  call    cs:__imp_WindowsDeleteString
0x18009a164  mov     [rsp+88h+string], 0
0x18009a16d  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x18009a172  test    rcx, rcx
0x18009a175  jz      short loc_18009A17D
0x18009a177  call    cs:__imp_ReleaseSRWLockShared
0x18009a17d  mov     eax, [rsp+88h+var_50]
0x18009a181  mov     rcx, [rsp+88h+var_20]
0x18009a186  xor     rcx, rsp; StackCookie
0x18009a189  call    __security_check_cookie
0x18009a18e  mov     rbx, [rsp+88h+arg_10]
0x18009a196  add     rsp, 70h
0x18009a19a  pop     r15
0x18009a19c  pop     r14
0x18009a19e  pop     rsi
0x18009a19f  retn
```

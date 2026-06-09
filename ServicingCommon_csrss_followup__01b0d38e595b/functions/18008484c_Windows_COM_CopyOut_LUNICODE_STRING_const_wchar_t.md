# Windows::COM::CopyOut(_LUNICODE_STRING const *,wchar_t * *)

- ea: `0x18008484c`
- end: `0x180084a09`
- name: `?CopyOut@COM@Windows@@YAJPEBU_LUNICODE_STRING@@PEAPEA_W@Z`
- size: `445`
- prototype: `__int64 __fastcall(Windows::COM *__hidden this, const struct _LUNICODE_STRING *, wchar_t **)`
- caller_count: `7`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800779dc`
- `0x180077b70`
- `0x18007834c`
- `0x180078520`
- `0x180079f90`
- `0x18007a6d0`
- `0x18007b2e0`

## callees

- `0x1800211f0`
- `0x180021794`
- `0x18002d2b0`
- `0x180047b24`
- `0x18008484c`
- `0x180096f68`
- `0x1800981e0`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x1800848a5`
- `ntdll!RtlRaiseStatus` at `0x1800848a5`

## string_xrefs

- `0x1800848d5`: `Windows::COM::CopyOut`
- `0x18008492e`: `Windows::COM::CopyOut`
- `0x180084970`: `Windows::COM::CopyOut`
- `0x1800849c9`: `Windows::COM::CopyOut`
- `0x1800848bc`: `onecore\base\wcp\com\copyout_string.cpp`
- `0x180084915`: `onecore\base\wcp\com\copyout_string.cpp`
- `0x180084959`: `onecore\base\wcp\com\copyout_string.cpp`
- `0x1800849b2`: `onecore\base\wcp\com\copyout_string.cpp`
- `0x180084985`: `pszTemp = reinterpret_cast<PWSTR>(Windows::COM::CoTaskMemAlloc(static_cast<ULONG>(cb) + sizeof(WCHAR)))`

## pseudocode

```c
__int64 __fastcall Windows::COM::CopyOut(Windows::COM *this, const struct _LUNICODE_STRING *a2, wchar_t **a3)
{
  size_t v5; // rbx
  __int64 v6; // r8
  unsigned __int64 i; // rdx
  char *v9; // rax
  char *v10; // rsi
  const char *v11; // [rsp+20h] [rbp-30h] BYREF
  const char *v12; // [rsp+28h] [rbp-28h]
  __int64 v13; // [rsp+30h] [rbp-20h]
  const char *v14; // [rsp+38h] [rbp-18h]
  int v15; // [rsp+40h] [rbp-10h] BYREF

  v15 = 0;
  if ( !a2 )
  {
    v13 = 24;
    v11 = "onecore\\base\\wcp\\com\\copyout_string.cpp";
    v12 = "Windows::COM::CopyOut";
    v14 = "Not-null check failed: StringOut";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v15,
             &v11);
  }
  *(_QWORD *)a2 = 0;
  if ( !this )
    return 0;
  v5 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    return 0;
  if ( (v5 & 1) != 0 )
    RtlRaiseStatus(-1073741595);
  if ( v5 <= 0xFFFFFFFD )
  {
    for ( i = 0; (unsigned int)i < (unsigned int)(v5 >> 1); i = (unsigned int)(i + 1) )
    {
      if ( !*(_WORD *)(*((_QWORD *)this + 2) + 2LL * (unsigned int)i) )
      {
        v13 = 39;
        v11 = "onecore\\base\\wcp\\com\\copyout_string.cpp";
        v6 = 3221225825LL;
        v12 = "Windows::COM::CopyOut";
        v14 = "StringIn->Buffer[i] != L'\\0'";
        return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
                 &v15,
                 &v11,
                 v6);
      }
    }
    v9 = (char *)Windows::COM::CoTaskMemAlloc((Windows::COM *)((unsigned int)v5 + 2LL), i);
    v10 = v9;
    if ( !v9 )
    {
      v13 = 43;
      v11 = "onecore\\base\\wcp\\com\\copyout_string.cpp";
      v12 = "Windows::COM::CopyOut";
      v14 = "pszTemp = reinterpret_cast<PWSTR>(Windows::COM::CoTaskMemAlloc(static_cast<ULONG>(cb) + sizeof(WCHAR)))";
      return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
               &v15,
               &v11,
               2147942414LL);
    }
    memmove(v9, *((const void **)this + 2), v5);
    *(_WORD *)&v10[v5] = 0;
    *(_QWORD *)a2 = v10;
    return 0;
  }
  v13 = 34;
  v11 = "onecore\\base\\wcp\\com\\copyout_string.cpp";
  v6 = 3221226539LL;
  v14 = 0;
  v12 = "Windows::COM::CopyOut";
  return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
           &v15,
           &v11,
           v6);
}

```

## disassembly

```asm
0x18008484c  mov     [rsp-28h+arg_10], rbx
0x180084851  push    rbp
0x180084852  push    rsi
0x180084853  push    rdi
0x180084854  push    r14
0x180084856  push    r15
0x180084858  mov     rbp, rsp
0x18008485b  sub     rsp, 50h
0x18008485f  mov     rax, cs:__security_cookie
0x180084866  xor     rax, rsp
0x180084869  mov     [rbp+var_8], rax
0x18008486d  xor     r15d, r15d
0x180084870  mov     r14, rdx
0x180084873  mov     [rbp+var_10], r15d
0x180084877  mov     rdi, rcx
0x18008487a  test    rdx, rdx
0x18008487d  jz      loc_1800849B2
0x180084883  mov     [rdx], r15
0x180084886  test    rcx, rcx
0x180084889  jz      loc_1800849AE
0x18008488f  mov     rbx, [rcx]
0x180084892  test    rbx, rbx
0x180084895  jz      loc_1800849AE
0x18008489b  test    bl, 1
0x18008489e  jz      short loc_1800848B2
0x1800848a0  mov     ecx, 0C00000E5h; Status
0x1800848a5  call    cs:__imp_RtlRaiseStatus
0x1800848ac  nop     dword ptr [rax+rax+00h]
0x1800848b1  int     3; Trap to Debugger
0x1800848b2  mov     eax, 0FFFFFFFDh
0x1800848b7  cmp     rbx, rax
0x1800848ba  jbe     short loc_1800848F6
0x1800848bc  lea     rax, aOnecoreBaseWcp_19; "onecore\\base\\wcp\\com\\copyout_string"...
0x1800848c3  mov     [rbp+var_20], 22h ; '"'
0x1800848cb  mov     [rbp+var_30], rax
0x1800848cf  mov     r8d, 0C000042Bh
0x1800848d5  lea     rax, aWindowsComCopy; "Windows::COM::CopyOut"
0x1800848dc  mov     [rbp+var_18], r15
0x1800848e0  mov     [rbp+var_28], rax
0x1800848e4  lea     rdx, [rbp+var_30]
0x1800848e8  lea     rcx, [rbp+var_10]
0x1800848ec  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800848f1  jmp     loc_1800849E8
0x1800848f6  mov     r8, rbx
0x1800848f9  mov     edx, r15d; unsigned __int64
0x1800848fc  shr     r8, 1
0x1800848ff  cmp     edx, r8d
0x180084902  jnb     short loc_180084946
0x180084904  mov     rax, [rdi+10h]
0x180084908  mov     ecx, edx
0x18008490a  cmp     [rax+rcx*2], r15w
0x18008490f  jz      short loc_180084915
0x180084911  inc     edx
0x180084913  jmp     short loc_1800848FF
0x180084915  lea     rax, aOnecoreBaseWcp_19; "onecore\\base\\wcp\\com\\copyout_string"...
0x18008491c  mov     [rbp+var_20], 27h ; '''
0x180084924  mov     [rbp+var_30], rax
0x180084928  mov     r8d, 0C0000161h
0x18008492e  lea     rax, aWindowsComCopy; "Windows::COM::CopyOut"
0x180084935  mov     [rbp+var_28], rax
0x180084939  lea     rax, aStringinBuffer; "StringIn->Buffer[i] != L'\\0'"
0x180084940  mov     [rbp+var_18], rax
0x180084944  jmp     short loc_1800848E4
0x180084946  mov     ecx, ebx
0x180084948  add     rcx, 2; this
0x18008494c  call    ?CoTaskMemAlloc@COM@Windows@@YAPEAX_K@Z; Windows::COM::CoTaskMemAlloc(unsigned __int64)
0x180084951  mov     rsi, rax
0x180084954  test    rax, rax
0x180084957  jnz     short loc_180084997
0x180084959  lea     rax, aOnecoreBaseWcp_19; "onecore\\base\\wcp\\com\\copyout_string"...
0x180084960  mov     [rbp+var_20], 2Bh ; '+'
0x180084968  mov     [rbp+var_30], rax
0x18008496c  lea     rdx, [rbp+var_30]
0x180084970  lea     rax, aWindowsComCopy; "Windows::COM::CopyOut"
0x180084977  mov     r8d, 8007000Eh
0x18008497d  mov     [rbp+var_28], rax
0x180084981  lea     rcx, [rbp+var_10]
0x180084985  lea     rax, aPsztempReinter; "pszTemp = reinterpret_cast<PWSTR>(Windo"...
0x18008498c  mov     [rbp+var_18], rax
0x180084990  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180084995  jmp     short loc_1800849E8
0x180084997  mov     rdx, [rdi+10h]; Src
0x18008499b  mov     r8, rbx; Size
0x18008499e  mov     rcx, rsi; void *
0x1800849a1  call    memmove
0x1800849a6  mov     [rsi+rbx], r15w
0x1800849ab  mov     [r14], rsi
0x1800849ae  xor     eax, eax
0x1800849b0  jmp     short loc_1800849E8
0x1800849b2  lea     rax, aOnecoreBaseWcp_19; "onecore\\base\\wcp\\com\\copyout_string"...
0x1800849b9  mov     [rbp+var_20], 18h
0x1800849c1  mov     [rbp+var_30], rax
0x1800849c5  lea     rdx, [rbp+var_30]
0x1800849c9  lea     rax, aWindowsComCopy; "Windows::COM::CopyOut"
0x1800849d0  mov     [rbp+var_28], rax
0x1800849d4  lea     rcx, [rbp+var_10]
0x1800849d8  lea     rax, aNotNullCheckFa_11; "Not-null check failed: StringOut"
0x1800849df  mov     [rbp+var_18], rax
0x1800849e3  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800849e8  mov     rcx, [rbp+var_8]
0x1800849ec  xor     rcx, rsp; StackCookie
0x1800849ef  call    __security_check_cookie
0x1800849f4  mov     rbx, [rsp+50h+arg_10]
0x1800849fc  add     rsp, 50h
0x180084a00  pop     r15
0x180084a02  pop     r14
0x180084a04  pop     rdi
0x180084a05  pop     rsi
0x180084a06  pop     rbp
0x180084a07  retn
```

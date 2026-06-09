# Windows::COM::CopyOut(_LUNICODE_STRING const *,wchar_t * *)

- ea: `0x1800857b4`
- end: `0x180085975`
- name: `?CopyOut@COM@Windows@@YAJPEBU_LUNICODE_STRING@@PEAPEA_W@Z`
- size: `449`
- prototype: `__int64 __fastcall(Windows::COM *__hidden this, const struct _LUNICODE_STRING *, wchar_t **)`
- caller_count: `7`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180077d4c`
- `0x180077ee0`
- `0x1800786bc`
- `0x180078890`
- `0x18007a2c0`
- `0x18007a9f0`
- `0x18007b610`

## callees

- `0x18001f51c`
- `0x18001f604`
- `0x18001fd10`
- `0x1800293a0`
- `0x1800432a0`
- `0x1800857b4`
- `0x180098e14`
- `0x18009a070`

## string_xrefs

- `0x18008582f`: `Windows::COM::CopyOut`
- `0x18008589a`: `Windows::COM::CopyOut`
- `0x1800858dd`: `Windows::COM::CopyOut`
- `0x18008592a`: `Windows::COM::CopyOut`
- `0x180085816`: `onecore\base\wcp\com\copyout_string.cpp`
- `0x180085883`: `onecore\base\wcp\com\copyout_string.cpp`
- `0x1800858c4`: `onecore\base\wcp\com\copyout_string.cpp`
- `0x180085913`: `onecore\base\wcp\com\copyout_string.cpp`
- `0x1800858af`: `pszTemp = reinterpret_cast<PWSTR>(Windows::COM::CoTaskMemAlloc(static_cast<ULONG>(cb) + sizeof(WCHAR)))`

## pseudocode

```c
__int64 __fastcall Windows::COM::CopyOut(Windows::COM *this, unsigned __int64 a2, wchar_t **a3)
{
  const struct _LUNICODE_STRING *v3; // r14
  size_t v5; // rbx
  __int64 v6; // r8
  char *v8; // rax
  char *v9; // rsi
  const char *v10; // [rsp+20h] [rbp-30h] BYREF
  const char *v11; // [rsp+28h] [rbp-28h]
  __int64 v12; // [rsp+30h] [rbp-20h]
  const char *v13; // [rsp+38h] [rbp-18h]
  int v14; // [rsp+40h] [rbp-10h] BYREF

  v3 = (const struct _LUNICODE_STRING *)a2;
  v14 = 0;
  if ( a2 )
  {
    *(_QWORD *)a2 = 0;
    if ( this )
    {
      v5 = *(_QWORD *)this;
      if ( *(_QWORD *)this )
      {
        if ( (v5 & 1) != 0 )
        {
          INTERNAL_ERROR_ACTION(-1073741595);
          JUMPOUT(0x180085974LL);
        }
        if ( v5 > 0xFFFFFFFD )
        {
          v12 = 34;
          v10 = "onecore\\base\\wcp\\com\\copyout_string.cpp";
          v6 = 3221226539LL;
          v13 = 0;
          v11 = "Windows::COM::CopyOut";
          return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
                   &v14,
                   &v10,
                   v6);
        }
        if ( (unsigned int)(v5 >> 1) )
        {
          LODWORD(a2) = 0;
          while ( *(_WORD *)(*((_QWORD *)this + 2) + 2LL * (unsigned int)a2) )
          {
            a2 = (unsigned int)(a2 + 1);
            if ( (unsigned int)a2 >= (unsigned int)(v5 >> 1) )
              goto LABEL_12;
          }
          v12 = 39;
          v10 = "onecore\\base\\wcp\\com\\copyout_string.cpp";
          v6 = 3221225825LL;
          v11 = "Windows::COM::CopyOut";
          v13 = "StringIn->Buffer[i] != L'\\0'";
          return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
                   &v14,
                   &v10,
                   v6);
        }
LABEL_12:
        v8 = (char *)Windows::COM::CoTaskMemAlloc((Windows::COM *)((unsigned int)v5 + 2LL), a2);
        v9 = v8;
        if ( !v8 )
        {
          v12 = 43;
          v10 = "onecore\\base\\wcp\\com\\copyout_string.cpp";
          v11 = "Windows::COM::CopyOut";
          v13 = "pszTemp = reinterpret_cast<PWSTR>(Windows::COM::CoTaskMemAlloc(static_cast<ULONG>(cb) + sizeof(WCHAR)))";
          return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
                   &v14,
                   &v10,
                   2147942414LL);
        }
        memmove(v8, *((const void **)this + 2), v5);
        *(_WORD *)&v9[v5] = 0;
        *(_QWORD *)v3 = v9;
      }
    }
    return 0;
  }
  else
  {
    v12 = 24;
    v10 = "onecore\\base\\wcp\\com\\copyout_string.cpp";
    v11 = "Windows::COM::CopyOut";
    v13 = "Not-null check failed: StringOut";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
             &v14,
             &v10);
  }
}

```

## disassembly

```asm
0x1800857b4  mov     [rsp-28h+arg_10], rbx
0x1800857b9  push    rbp
0x1800857ba  push    rsi
0x1800857bb  push    rdi
0x1800857bc  push    r14
0x1800857be  push    r15
0x1800857c0  mov     rbp, rsp
0x1800857c3  sub     rsp, 50h
0x1800857c7  mov     rax, cs:__security_cookie
0x1800857ce  xor     rax, rsp
0x1800857d1  mov     [rbp+var_8], rax
0x1800857d5  xor     r15d, r15d
0x1800857d8  mov     r14, rdx
0x1800857db  mov     [rbp+var_10], r15d
0x1800857df  mov     rdi, rcx
0x1800857e2  test    rdx, rdx
0x1800857e5  jz      loc_180085913
0x1800857eb  mov     [rdx], r15
0x1800857ee  test    rcx, rcx
0x1800857f1  jz      loc_18008590F
0x1800857f7  mov     rbx, [rcx]
0x1800857fa  test    rbx, rbx
0x1800857fd  jz      loc_18008590F
0x180085803  test    bl, 1
0x180085806  jnz     loc_18008596A
0x18008580c  mov     eax, 0FFFFFFFDh
0x180085811  cmp     rbx, rax
0x180085814  jbe     short loc_180085850
0x180085816  lea     rax, aOnecoreBaseWcp_19; "onecore\\base\\wcp\\com\\copyout_string"...
0x18008581d  mov     [rbp+var_20], 22h ; '"'
0x180085825  mov     [rbp+var_30], rax
0x180085829  mov     r8d, 0C000042Bh
0x18008582f  lea     rax, aWindowsComCopy; "Windows::COM::CopyOut"
0x180085836  mov     [rbp+var_18], r15
0x18008583a  mov     [rbp+var_28], rax
0x18008583e  lea     rdx, [rbp+var_30]
0x180085842  lea     rcx, [rbp+var_10]
0x180085846  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18008584b  jmp     loc_180085949
0x180085850  mov     rcx, rbx
0x180085853  shr     rcx, 1
0x180085856  test    ecx, ecx
0x180085858  jz      short loc_180085870
0x18008585a  mov     r8, [rdi+10h]
0x18008585e  mov     edx, r15d
0x180085861  mov     eax, edx
0x180085863  cmp     [r8+rax*2], r15w
0x180085868  jz      short loc_1800858C4
0x18008586a  inc     edx; unsigned __int64
0x18008586c  cmp     edx, ecx
0x18008586e  jb      short loc_180085861
0x180085870  mov     ecx, ebx
0x180085872  add     rcx, 2; this
0x180085876  call    ?CoTaskMemAlloc@COM@Windows@@YAPEAX_K@Z; Windows::COM::CoTaskMemAlloc(unsigned __int64)
0x18008587b  mov     rsi, rax
0x18008587e  test    rax, rax
0x180085881  jnz     short loc_1800858F8
0x180085883  lea     rax, aOnecoreBaseWcp_19; "onecore\\base\\wcp\\com\\copyout_string"...
0x18008588a  mov     [rbp+var_20], 2Bh ; '+'
0x180085892  mov     [rbp+var_30], rax
0x180085896  lea     rdx, [rbp+var_30]
0x18008589a  lea     rax, aWindowsComCopy; "Windows::COM::CopyOut"
0x1800858a1  mov     r8d, 8007000Eh
0x1800858a7  mov     [rbp+var_28], rax
0x1800858ab  lea     rcx, [rbp+var_10]
0x1800858af  lea     rax, aPsztempReinter; "pszTemp = reinterpret_cast<PWSTR>(Windo"...
0x1800858b6  mov     [rbp+var_18], rax
0x1800858ba  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800858bf  jmp     loc_180085949
0x1800858c4  lea     rax, aOnecoreBaseWcp_19; "onecore\\base\\wcp\\com\\copyout_string"...
0x1800858cb  mov     [rbp+var_20], 27h ; '''
0x1800858d3  mov     [rbp+var_30], rax
0x1800858d7  mov     r8d, 0C0000161h
0x1800858dd  lea     rax, aWindowsComCopy; "Windows::COM::CopyOut"
0x1800858e4  mov     [rbp+var_28], rax
0x1800858e8  lea     rax, aStringinBuffer; "StringIn->Buffer[i] != L'\\0'"
0x1800858ef  mov     [rbp+var_18], rax
0x1800858f3  jmp     loc_18008583E
0x1800858f8  mov     rdx, [rdi+10h]; Src
0x1800858fc  mov     r8, rbx; Size
0x1800858ff  mov     rcx, rsi; void *
0x180085902  call    memmove
0x180085907  mov     [rsi+rbx], r15w
0x18008590c  mov     [r14], rsi
0x18008590f  xor     eax, eax
0x180085911  jmp     short loc_180085949
0x180085913  lea     rax, aOnecoreBaseWcp_19; "onecore\\base\\wcp\\com\\copyout_string"...
0x18008591a  mov     [rbp+var_20], 18h
0x180085922  mov     [rbp+var_30], rax
0x180085926  lea     rdx, [rbp+var_30]
0x18008592a  lea     rax, aWindowsComCopy; "Windows::COM::CopyOut"
0x180085931  mov     [rbp+var_28], rax
0x180085935  lea     rcx, [rbp+var_10]
0x180085939  lea     rax, aNotNullCheckFa_11; "Not-null check failed: StringOut"
0x180085940  mov     [rbp+var_18], rax
0x180085944  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x180085949  mov     rcx, [rbp+var_8]
0x18008594d  xor     rcx, rsp; StackCookie
0x180085950  call    __security_check_cookie
0x180085955  mov     rbx, [rsp+50h+arg_10]
0x18008595d  add     rsp, 50h
0x180085961  pop     r15
0x180085963  pop     r14
0x180085965  pop     rdi
0x180085966  pop     rsi
0x180085967  pop     rbp
0x180085968  retn
0x18008596a  mov     ecx, 0C00000E5h; int
0x18008596f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```

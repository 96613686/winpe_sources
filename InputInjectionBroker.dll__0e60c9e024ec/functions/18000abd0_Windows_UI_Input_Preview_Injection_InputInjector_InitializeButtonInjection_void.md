# Windows::UI::Input::Preview::Injection::InputInjector::InitializeButtonInjection(void)

- ea: `0x18000abd0`
- end: `0x18000acd9`
- name: `?InitializeButtonInjection@InputInjector@Injection@Preview@Input@UI@Windows@@AEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InputInjector *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000afa0`

## callees

- `0x180004a34`
- `0x18000abd0`
- `0x18000e2bc`
- `0x18001143a`
- `0x180011460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000acb3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000acb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000abf9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000abf9`
- `ext-ms-win-ntuser-rim-l1-1-1!InitializeGenericHidInjection` at `0x18000ac45`
- `ext-ms-win-ntuser-rim-l1-1-1!InitializeGenericHidInjection` at `0x18000ac45`
- `ext-ms-win-ntuser-rim-l1-1-1!InjectGenericHidInput` at `0x18000ac6d`
- `ext-ms-win-ntuser-rim-l1-1-1!InjectGenericHidInput` at `0x18000ac6d`

## string_xrefs

- `0x18000ac84`: `onecore\windows\advcore\winrt\inputinjectionbroker\common\lib\inputinjector.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::InitializeButtonInjection(
        Windows::UI::Input::Preview::Injection::InputInjector *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v3; // rdx
  __int64 v4; // rcx
  int v6[4]; // [rsp+20h] [rbp-68h] BYREF
  int v7; // [rsp+30h] [rbp-58h] BYREF
  __int16 v8; // [rsp+34h] [rbp-54h]
  unsigned __int8 near **v9; // [rsp+50h] [rbp-38h]
  __int16 v10; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  Windows::UI::Input::Preview::Injection::InputInjector::UninitializeButtonInjection(this);
  memset_0(&v7, 0, 0x40u);
  v7 = 65537;
  v8 = 0;
  v9 = &Windows::UI::Input::Preview::Injection::ButtonReportDescriptor;
  v10 = 73;
  if ( !(unsigned int)InitializeGenericHidInjection(&v7, (char *)this + 112) )
  {
    v3 = 499;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\windows\\advcore\\winrt\\inputinjectionbroker\\common\\lib\\inputinjector.cpp",
      (const char *)0x80004005LL,
      v6[0]);
    if ( v1 )
      LeaveCriticalSection(v1);
    return 2147500037LL;
  }
  v4 = *((_QWORD *)this + 14);
  v6[0] = 0;
  if ( !(unsigned int)InjectGenericHidInput(v4, v6, 4) )
  {
    v3 = 504;
    goto LABEL_5;
  }
  if ( v1 )
    LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x18000abd0  mov     [rsp+arg_8], rbx
0x18000abd5  push    rdi
0x18000abd6  sub     rsp, 80h
0x18000abdd  mov     rax, cs:__security_cookie
0x18000abe4  xor     rax, rsp
0x18000abe7  mov     [rsp+88h+var_18], rax
0x18000abec  lea     rdi, [rcx+80h]
0x18000abf3  mov     rbx, rcx
0x18000abf6  mov     rcx, rdi; lpCriticalSection
0x18000abf9  call    cs:__imp_EnterCriticalSection
0x18000abff  mov     rcx, rbx; this
0x18000ac02  call    ?UninitializeButtonInjection@InputInjector@Injection@Preview@Input@UI@Windows@@AEAAJXZ; Windows::UI::Input::Preview::Injection::InputInjector::UninitializeButtonInjection(void)
0x18000ac07  xor     edx, edx; Val
0x18000ac09  lea     rcx, [rsp+88h+var_58]; void *
0x18000ac0e  lea     r8d, [rdx+40h]; Size
0x18000ac12  call    memset_0
0x18000ac17  xor     eax, eax
0x18000ac19  mov     [rsp+88h+var_58], 10001h
0x18000ac21  mov     [rsp+88h+var_54], ax
0x18000ac26  lea     rdx, [rbx+70h]
0x18000ac2a  lea     rax, ?ButtonReportDescriptor@Injection@Preview@Input@UI@Windows@@3PAEA; uchar near * Windows::UI::Input::Preview::Injection::ButtonReportDescriptor
0x18000ac31  mov     [rsp+88h+var_38], rax
0x18000ac36  lea     rcx, [rsp+88h+var_58]
0x18000ac3b  mov     eax, 49h ; 'I'
0x18000ac40  mov     [rsp+88h+var_30], ax
0x18000ac45  call    cs:__imp_InitializeGenericHidInjection
0x18000ac4b  test    eax, eax
0x18000ac4d  jnz     short loc_18000AC56
0x18000ac4f  mov     edx, 1F3h
0x18000ac54  jmp     short loc_18000AC7C
0x18000ac56  mov     rcx, [rbx+70h]
0x18000ac5a  lea     rdx, [rsp+88h+var_68]
0x18000ac5f  mov     r8d, 4
0x18000ac65  mov     [rsp+88h+var_68], 0; int
0x18000ac6d  call    cs:__imp_InjectGenericHidInput
0x18000ac73  test    eax, eax
0x18000ac75  jnz     short loc_18000ACAB
0x18000ac77  mov     edx, 1F8h; void *
0x18000ac7c  mov     rcx, [rsp+88h]; this
0x18000ac84  lea     r8, aOnecoreWindows; "onecore\\windows\\advcore\\winrt\\input"...
0x18000ac8b  mov     r9d, 80004005h; char *
0x18000ac91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac96  test    rdi, rdi
0x18000ac99  jz      short loc_18000ACA4
0x18000ac9b  mov     rcx, rdi; lpCriticalSection
0x18000ac9e  call    cs:__imp_LeaveCriticalSection
0x18000aca4  mov     eax, 80004005h
0x18000aca9  jmp     short loc_18000ACBB
0x18000acab  test    rdi, rdi
0x18000acae  jz      short loc_18000ACB9
0x18000acb0  mov     rcx, rdi; lpCriticalSection
0x18000acb3  call    cs:__imp_LeaveCriticalSection
0x18000acb9  xor     eax, eax
0x18000acbb  mov     rcx, [rsp+88h+var_18]
0x18000acc0  xor     rcx, rsp; StackCookie
0x18000acc3  call    __security_check_cookie
0x18000acc8  mov     rbx, [rsp+88h+arg_8]
0x18000acd0  add     rsp, 80h
0x18000acd7  pop     rdi
0x18000acd8  retn
```

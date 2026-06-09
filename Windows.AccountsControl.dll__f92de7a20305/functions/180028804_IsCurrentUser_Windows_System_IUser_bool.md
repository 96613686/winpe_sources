# IsCurrentUser(Windows::System::IUser *,bool *)

- ea: `0x180028804`
- end: `0x180028977`
- name: `?IsCurrentUser@@YAJPEAUIUser@System@Windows@@PEA_N@Z`
- size: `371`
- prototype: `int(struct Windows::System::IUser *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026130`

## callees

- `0x180006eac`
- `0x18000e5f0`
- `0x180011ffc`
- `0x180028804`
- `0x180043cb0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800288b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800288dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002891d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800288b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800288dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002891d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028945`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028957`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IsCurrentUser(struct Windows::System::IUser *a1, bool *a2)
{
  int CurrentUser; // eax
  unsigned int v5; // ebx
  __int64 (__fastcall *v6)(struct Windows::System::IUser *, HSTRING *); // rbx
  int v7; // eax
  struct Windows::System::IUser *v8; // rdi
  __int64 (__fastcall *v9)(struct Windows::System::IUser *, HSTRING *); // rbx
  int v10; // eax
  HSTRING v11; // r8
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+48h] [rbp+28h] BYREF
  HSTRING v16; // [rsp+50h] [rbp+30h] BYREF
  struct Windows::System::IUser *v17; // [rsp+58h] [rbp+38h] BYREF

  *a2 = 0;
  v17 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  CurrentUser = GetCurrentUser(&v17);
  v5 = CurrentUser;
  if ( CurrentUser >= 0 )
  {
    if ( v17 )
    {
      string = 0;
      v6 = *(__int64 (__fastcall **)(struct Windows::System::IUser *, HSTRING *))(*(_QWORD *)a1 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v7 = v6(a1, &string);
      v5 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
          (const char *)(unsigned int)v7,
          savedregs);
LABEL_6:
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_13;
      }
      v16 = 0;
      v8 = v17;
      v9 = *(__int64 (__fastcall **)(struct Windows::System::IUser *, HSTRING *))(*(_QWORD *)v17 + 48LL);
      WindowsDeleteString(0);
      v16 = 0;
      v10 = v9(v8, &v16);
      v5 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5F,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
          (const char *)(unsigned int)v10,
          savedregs);
        WindowsDeleteString(v16);
        v16 = 0;
        goto LABEL_6;
      }
      if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                            (Microsoft::WRL::Wrappers::Details *)string,
                            v16,
                            v11) )
        *a2 = 1;
      WindowsDeleteString(v16);
      v16 = 0;
      WindowsDeleteString(string);
    }
    v5 = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x58,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
    (const char *)(unsigned int)CurrentUser,
    savedregs);
LABEL_13:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  return v5;
}

```

## disassembly

```asm
0x180028804  mov     [rsp-18h+arg_0], rbx
0x180028809  push    rbp
0x18002880a  push    rsi
0x18002880b  push    rdi; int
0x18002880c  mov     rbp, rsp
0x18002880f  sub     rsp, 20h
0x180028813  mov     rsi, rdx
0x180028816  mov     rdi, rcx
0x180028819  mov     byte ptr [rdx], 0
0x18002881c  mov     [rbp+arg_18], 0
0x180028824  lea     rcx, [rbp+arg_18]
0x180028828  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002882d  lea     rcx, [rbp+arg_18]; struct Windows::System::IUser **
0x180028831  call    ?GetCurrentUser@@YAJPEAPEAUIUser@System@Windows@@@Z; GetCurrentUser(Windows::System::IUser * *)
0x180028836  mov     ebx, eax
0x180028838  test    eax, eax
0x18002883a  jns     short loc_180028859
0x18002883c  mov     rcx, [rbp+18h]; this
0x180028840  mov     r9d, eax; char *
0x180028843  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x18002884a  mov     edx, 58h ; 'X'; void *
0x18002884f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028854  jmp     loc_18002895F
0x180028859  cmp     [rbp+arg_18], 0
0x18002885e  jz      loc_18002895D
0x180028864  mov     [rbp+string], 0
0x18002886c  mov     rax, [rdi]
0x18002886f  mov     rbx, [rax+30h]
0x180028873  xor     ecx, ecx; string
0x180028875  call    cs:__imp_WindowsDeleteString
0x18002887b  mov     [rbp+string], 0
0x180028883  lea     rdx, [rbp+string]
0x180028887  mov     rcx, rdi
0x18002888a  mov     rax, rbx
0x18002888d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028892  mov     ebx, eax
0x180028894  test    eax, eax
0x180028896  jns     short loc_1800288C8
0x180028898  mov     rcx, [rbp+18h]; this
0x18002889c  mov     r9d, eax; char *
0x18002889f  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800288a6  mov     edx, 5Ch ; '\'; void *
0x1800288ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800288b0  nop
0x1800288b1  mov     rcx, [rbp+string]; string
0x1800288b5  call    cs:__imp_WindowsDeleteString
0x1800288bb  mov     [rbp+string], 0
0x1800288c3  jmp     loc_18002895F
0x1800288c8  mov     [rbp+arg_10], 0
0x1800288d0  mov     rdi, [rbp+arg_18]
0x1800288d4  mov     rax, [rdi]
0x1800288d7  mov     rbx, [rax+30h]
0x1800288db  xor     ecx, ecx; string
0x1800288dd  call    cs:__imp_WindowsDeleteString
0x1800288e3  mov     [rbp+arg_10], 0
0x1800288eb  lea     rdx, [rbp+arg_10]
0x1800288ef  mov     rcx, rdi
0x1800288f2  mov     rax, rbx
0x1800288f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288fa  mov     ebx, eax
0x1800288fc  test    eax, eax
0x1800288fe  jns     short loc_18002892D
0x180028900  mov     rcx, [rbp+18h]; this
0x180028904  mov     r9d, eax; char *
0x180028907  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x18002890e  mov     edx, 5Fh ; '_'; void *
0x180028913  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028918  nop
0x180028919  mov     rcx, [rbp+arg_10]; string
0x18002891d  call    cs:__imp_WindowsDeleteString
0x180028923  mov     [rbp+arg_10], 0
0x18002892b  jmp     short loc_1800288B1
0x18002892d  mov     rdx, [rbp+arg_10]; HSTRING
0x180028931  mov     rcx, [rbp+string]; this
0x180028935  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18002893a  test    eax, eax
0x18002893c  jnz     short loc_180028941
0x18002893e  mov     byte ptr [rsi], 1
0x180028941  mov     rcx, [rbp+arg_10]; string
0x180028945  call    cs:__imp_WindowsDeleteString
0x18002894b  mov     [rbp+arg_10], 0
0x180028953  mov     rcx, [rbp+string]; string
0x180028957  call    cs:__imp_WindowsDeleteString
0x18002895d  xor     ebx, ebx
0x18002895f  lea     rcx, [rbp+arg_18]
0x180028963  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028968  mov     eax, ebx
0x18002896a  mov     rbx, [rsp+20h+arg_0]
0x18002896f  add     rsp, 20h
0x180028973  pop     rdi
0x180028974  pop     rsi
0x180028975  pop     rbp
0x180028976  retn
```

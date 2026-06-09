# ExtensionRegistrationMatchesAumid(Windows::Foundation::IExtensionRegistration *,ushort const *,HSTRING__ * *)

- ea: `0x180011354`
- end: `0x180011581`
- name: `?ExtensionRegistrationMatchesAumid@@YA_NPEAUIExtensionRegistration@Foundation@Windows@@PEBGPEAPEAUHSTRING__@@@Z`
- size: `557`
- prototype: `bool(struct Windows::Foundation::IExtensionRegistration *, const unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180048edc`

## callees

- `0x18000b5c0`
- `0x180010a34`
- `0x180011328`
- `0x180011354`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800114b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011379`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800114b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800114d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800114d0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800114dc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800114dc`

## string_xrefs

- `0x1800114f3`: `onecoreuap\base\appmodel\execmodel\shared\utility\extensionregistrationhelper.cpp`
- `0x18001154d`: `onecoreuap\base\appmodel\execmodel\shared\utility\extensionregistrationhelper.cpp`

## pseudocode

```c
char __fastcall ExtensionRegistrationMatchesAumid(
        struct Windows::Foundation::IExtensionRegistration *a1,
        const unsigned __int16 *a2,
        HSTRING *a3)
{
  __int64 v6; // rax
  __int64 (__fastcall *v7)(struct Windows::Foundation::IExtensionRegistration *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v8; // eax
  int v9; // ebx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 (__fastcall *v14)(__int64, __int64 *); // rdi
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  char v18; // bl
  const WCHAR *StringRawBuffer; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-10h] BYREF
  HSTRING string; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int64 v28; // [rsp+60h] [rbp+30h] BYREF
  __int64 v29; // [rsp+78h] [rbp+48h] BYREF

  string = 0;
  WindowsDeleteString(0);
  v6 = *(_QWORD *)a1;
  string = 0;
  v25 = 0;
  v29 = 0;
  v7 = *(__int64 (__fastcall **)(struct Windows::Foundation::IExtensionRegistration *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v6 + 80);
  v28 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  v8 = v7(a1, &v25);
  v9 = v8;
  if ( v8 < 0 )
  {
    v21 = 29;
  }
  else
  {
    v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v25;
    v11 = **v25;
    Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v29);
    v8 = v11(v10, &GUID_9308c3c5_c2ac_49d1_a024_660a2bb5d5ac, &v29);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v12 = v29;
      v13 = v28;
      v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 48LL);
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      v15 = v14(v12, &v28);
      v9 = v15;
      if ( v15 < 0 )
      {
        v24 = 31;
      }
      else
      {
        v15 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 72LL))(v28, &string);
        v9 = v15;
        if ( v15 < 0 )
        {
          v24 = 35;
        }
        else
        {
          if ( !a3
            || (v15 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 56LL))(v28, a3),
                v9 = v15,
                v15 >= 0) )
          {
            v16 = v28;
            if ( v28 )
            {
              v28 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            }
            v17 = v29;
            if ( v29 )
            {
              v29 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            }
            v9 = 0;
            goto LABEL_14;
          }
          v24 = 40;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\extensionregistrationhelper.cpp",
        (const char *)(unsigned int)v15,
        (int)v25);
      Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v28);
      Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v29);
      goto LABEL_14;
    }
    v21 = 30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v21,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\shared\\utility\\extensionregistrationhelper.cpp",
    (const char *)(unsigned int)v8,
    (int)v25);
  v22 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
LABEL_14:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  if ( v9 < 0 || (StringRawBuffer = WindowsGetStringRawBuffer(string, 0), v18 = 1, StrCmpIW(a2, StringRawBuffer)) )
    v18 = 0;
  WindowsDeleteString(string);
  return v18;
}

```

## disassembly

```asm
0x180011354  mov     [rsp-28h+arg_8], rbx
0x180011359  push    rbp
0x18001135a  push    rsi
0x18001135b  push    rdi
0x18001135c  push    r14
0x18001135e  push    r15
0x180011360  mov     rbp, rsp
0x180011363  sub     rsp, 30h
0x180011367  mov     rdi, rcx
0x18001136a  xor     r15d, r15d
0x18001136d  xor     ecx, ecx; string
0x18001136f  mov     [rbp+string], r15
0x180011373  mov     rsi, r8
0x180011376  mov     r14, rdx
0x180011379  call    cs:__imp_WindowsDeleteString
0x18001137f  mov     rax, [rdi]
0x180011382  lea     rcx, [rbp+var_10]
0x180011386  mov     [rbp+string], r15
0x18001138a  mov     [rbp+var_10], r15
0x18001138e  mov     [rbp+arg_18], r15
0x180011392  mov     rbx, [rax+50h]
0x180011396  mov     [rbp+arg_0], r15
0x18001139a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001139f  lea     rdx, [rbp+var_10]
0x1800113a3  mov     rcx, rdi
0x1800113a6  mov     rax, rbx
0x1800113a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ae  mov     ebx, eax
0x1800113b0  test    eax, eax
0x1800113b2  js      loc_1800114EA
0x1800113b8  mov     rbx, [rbp+var_10]
0x1800113bc  lea     rcx, [rbp+arg_18]
0x1800113c0  mov     rax, [rbx]
0x1800113c3  mov     rdi, [rax]
0x1800113c6  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x1800113cb  lea     r8, [rbp+arg_18]
0x1800113cf  mov     rcx, rbx
0x1800113d2  lea     rdx, _GUID_9308c3c5_c2ac_49d1_a024_660a2bb5d5ac
0x1800113d9  mov     rax, rdi
0x1800113dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113e1  mov     ebx, eax
0x1800113e3  test    eax, eax
0x1800113e5  js      loc_18001153D
0x1800113eb  mov     rbx, [rbp+arg_18]
0x1800113ef  mov     rcx, [rbp+arg_0]
0x1800113f3  mov     rax, [rbx]
0x1800113f6  mov     rdi, [rax+30h]
0x1800113fa  test    rcx, rcx
0x1800113fd  jz      short loc_18001140F
0x1800113ff  mov     [rbp+arg_0], r15
0x180011403  mov     rdx, [rcx]
0x180011406  mov     rax, [rdx+10h]
0x18001140a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001140f  lea     rdx, [rbp+arg_0]
0x180011413  mov     rcx, rbx
0x180011416  mov     rax, rdi
0x180011419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001141e  mov     ebx, eax
0x180011420  test    eax, eax
0x180011422  js      loc_180011573
0x180011428  mov     rcx, [rbp+arg_0]
0x18001142c  lea     rdx, [rbp+string]
0x180011430  mov     rax, [rcx]
0x180011433  mov     rax, [rax+48h]
0x180011437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001143c  mov     ebx, eax
0x18001143e  test    eax, eax
0x180011440  js      loc_180011544
0x180011446  test    rsi, rsi
0x180011449  jz      short loc_180011468
0x18001144b  mov     rcx, [rbp+arg_0]
0x18001144f  mov     rdx, rsi
0x180011452  mov     rax, [rcx]
0x180011455  mov     rax, [rax+38h]
0x180011459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001145e  mov     ebx, eax
0x180011460  test    eax, eax
0x180011462  js      loc_18001157A
0x180011468  mov     rcx, [rbp+arg_0]
0x18001146c  test    rcx, rcx
0x18001146f  jz      short loc_180011481
0x180011471  mov     [rbp+arg_0], r15
0x180011475  mov     rax, [rcx]
0x180011478  mov     rax, [rax+10h]
0x18001147c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011481  mov     rcx, [rbp+arg_18]
0x180011485  test    rcx, rcx
0x180011488  jz      short loc_18001149A
0x18001148a  mov     [rbp+arg_18], r15
0x18001148e  mov     rax, [rcx]
0x180011491  mov     rax, [rax+10h]
0x180011495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001149a  mov     ebx, r15d
0x18001149d  lea     rcx, [rbp+var_10]
0x1800114a1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800114a6  test    ebx, ebx
0x1800114a8  jns     short loc_1800114CA
0x1800114aa  mov     bl, r15b
0x1800114ad  mov     rcx, [rbp+string]; string
0x1800114b1  call    cs:__imp_WindowsDeleteString
0x1800114b7  mov     al, bl
0x1800114b9  mov     rbx, [rsp+30h+arg_8]
0x1800114be  add     rsp, 30h
0x1800114c2  pop     r15
0x1800114c4  pop     r14
0x1800114c6  pop     rdi
0x1800114c7  pop     rsi
0x1800114c8  pop     rbp
0x1800114c9  retn
0x1800114ca  mov     rcx, [rbp+string]; string
0x1800114ce  xor     edx, edx; length
0x1800114d0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800114d6  mov     rdx, rax; psz2
0x1800114d9  mov     rcx, r14; psz1
0x1800114dc  call    cs:__imp_StrCmpIW
0x1800114e2  mov     bl, 1
0x1800114e4  test    eax, eax
0x1800114e6  jnz     short loc_1800114AA
0x1800114e8  jmp     short loc_1800114AD
0x1800114ea  mov     edx, 1Dh; void *
0x1800114ef  mov     rcx, [rbp+28h]; this
0x1800114f3  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800114fa  mov     r9d, eax; char *
0x1800114fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011502  mov     rcx, [rbp+arg_0]
0x180011506  test    rcx, rcx
0x180011509  jz      short loc_18001151B
0x18001150b  mov     [rbp+arg_0], r15
0x18001150f  mov     rax, [rcx]
0x180011512  mov     rax, [rax+10h]
0x180011516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001151b  mov     rcx, [rbp+arg_18]
0x18001151f  test    rcx, rcx
0x180011522  jz      loc_18001149D
0x180011528  mov     [rbp+arg_18], r15
0x18001152c  mov     rax, [rcx]
0x18001152f  mov     rax, [rax+10h]
0x180011533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011538  jmp     loc_18001149D
0x18001153d  mov     edx, 1Eh
0x180011542  jmp     short loc_1800114EF
0x180011544  mov     edx, 23h ; '#'; void *
0x180011549  mov     rcx, [rbp+28h]; this
0x18001154d  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180011554  mov     r9d, eax; char *
0x180011557  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001155c  lea     rcx, [rbp+arg_0]
0x180011560  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x180011565  lea     rcx, [rbp+arg_18]
0x180011569  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x18001156e  jmp     loc_18001149D
0x180011573  mov     edx, 1Fh
0x180011578  jmp     short loc_180011549
0x18001157a  mov     edx, 28h ; '('
0x18001157f  jmp     short loc_180011549
```

# ClassicAppManagerFactory::FindInstalledApp(HSTRING__ *,Windows::Management::Deployment::Preview::IInstalledClassicAppInfo * *)

- ea: `0x180040b80`
- end: `0x180040ca0`
- name: `?FindInstalledApp@ClassicAppManagerFactory@@UEAAJPEAUHSTRING__@@PEAPEAUIInstalledClassicAppInfo@Preview@Deployment@Management@Windows@@@Z`
- size: `288`
- prototype: `int(ClassicAppManagerFactory *__hidden this, HSTRING, struct Windows::Management::Deployment::Preview::IInstalledClassicAppInfo **)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007560`
- `0x180040230`
- `0x180040b80`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040bf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040c02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040c53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040c65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040bf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040c02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040c53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040c65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180040bbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180040bbf`

## string_xrefs

- `0x180040c3b`: `shell\cpls\appwzdui\installedclassicappinfo.cpp`

## pseudocode

```c
__int64 __fastcall ClassicAppManagerFactory::FindInstalledApp(
        ClassicAppManagerFactory *this,
        HSTRING a2,
        struct Windows::Management::Deployment::Preview::IInstalledClassicAppInfo **a3)
{
  __int64 i; // rbx
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING, HSTRING *, HSTRING *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  int v13; // [rsp+20h] [rbp-20h]
  HSTRING v14[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  HSTRING result; // [rsp+70h] [rbp+30h] BYREF
  HSTRING v17; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *((_DWORD *)this + 22) )
      return 0;
    v7 = *((_QWORD *)this + 10);
    LODWORD(result) = 0;
    if ( WindowsCompareStringOrdinal(a2, *(HSTRING *)(v7 + 8 * i), (INT32 *)&result) >= 0 && !(_DWORD)result )
      break;
  }
  v8 = *((_QWORD *)this + 9);
  string = 0;
  v17 = 0;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *, HSTRING *))(*(_QWORD *)v8 + 56LL);
  WindowsDeleteString(0);
  v17 = 0;
  WindowsDeleteString(string);
  string = 0;
  v10 = v9(v8, a2, &string, &v17);
  v11 = v10;
  if ( v10 == -2147024894 )
  {
    v11 = 0;
  }
  else if ( v10 >= 0 )
  {
    result = v17;
    v14[0] = string;
    v11 = Microsoft::WRL::Details::MakeAndInitialize<InstalledClassicAppInfoServer,Windows::Management::Deployment::Preview::IInstalledClassicAppInfo,HSTRING__ *,HSTRING__ *>(
            a3,
            v14,
            &result);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"shell\\cpls\\appwzdui\\installedclassicappinfo.cpp",
      (const char *)(unsigned int)v10,
      v13);
  }
  WindowsDeleteString(v17);
  v17 = 0;
  WindowsDeleteString(string);
  return v11;
}

```

## disassembly

```asm
0x180040b80  push    rbp
0x180040b82  push    rbx
0x180040b83  push    rsi
0x180040b84  push    rdi
0x180040b85  push    r14
0x180040b87  mov     rbp, rsp
0x180040b8a  sub     rsp, 40h
0x180040b8e  mov     rsi, r8
0x180040b91  mov     qword ptr [r8], 0
0x180040b98  mov     r14, rdx
0x180040b9b  mov     rdi, rcx
0x180040b9e  xor     ebx, ebx
0x180040ba0  cmp     ebx, [rdi+58h]
0x180040ba3  jnb     loc_180040C93
0x180040ba9  mov     rdx, [rdi+50h]
0x180040bad  lea     r8, [rbp+result]; result
0x180040bb1  mov     dword ptr [rbp+result], 0
0x180040bb8  mov     rcx, r14; string1
0x180040bbb  mov     rdx, [rdx+rbx*8]; string2
0x180040bbf  call    cs:__imp_WindowsCompareStringOrdinal
0x180040bc5  test    eax, eax
0x180040bc7  js      short loc_180040BCF
0x180040bc9  cmp     dword ptr [rbp+result], 0
0x180040bcd  jz      short loc_180040BD3
0x180040bcf  inc     ebx
0x180040bd1  jmp     short loc_180040BA0
0x180040bd3  mov     rdi, [rdi+48h]
0x180040bd7  xor     ecx, ecx; string
0x180040bd9  mov     [rbp+string], 0
0x180040be1  mov     [rbp+arg_10], 0
0x180040be9  mov     rax, [rdi]
0x180040bec  mov     rbx, [rax+38h]
0x180040bf0  call    cs:__imp_WindowsDeleteString
0x180040bf6  mov     rcx, [rbp+string]; string
0x180040bfa  mov     [rbp+arg_10], 0
0x180040c02  call    cs:__imp_WindowsDeleteString
0x180040c08  lea     r9, [rbp+arg_10]
0x180040c0c  mov     [rbp+string], 0
0x180040c14  lea     r8, [rbp+string]
0x180040c18  mov     rdx, r14
0x180040c1b  mov     rcx, rdi
0x180040c1e  mov     rax, rbx
0x180040c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c26  mov     ebx, eax
0x180040c28  cmp     eax, 80070002h
0x180040c2d  jnz     short loc_180040C33
0x180040c2f  xor     ebx, ebx
0x180040c31  jmp     short loc_180040C4F
0x180040c33  test    eax, eax
0x180040c35  jns     short loc_180040C6F
0x180040c37  mov     rcx, [rbp+28h]; this
0x180040c3b  lea     r8, aShellCplsAppwz; "shell\\cpls\\appwzdui\\installedclassic"...
0x180040c42  mov     r9d, eax; char *
0x180040c45  mov     edx, 8Eh; void *
0x180040c4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040c4f  mov     rcx, [rbp+arg_10]; string
0x180040c53  call    cs:__imp_WindowsDeleteString
0x180040c59  mov     rcx, [rbp+string]; string
0x180040c5d  mov     [rbp+arg_10], 0
0x180040c65  call    cs:__imp_WindowsDeleteString
0x180040c6b  mov     eax, ebx
0x180040c6d  jmp     short loc_180040C95
0x180040c6f  mov     rax, [rbp+arg_10]
0x180040c73  lea     r8, [rbp+result]
0x180040c77  mov     [rbp+result], rax
0x180040c7b  lea     rdx, [rbp+var_10]
0x180040c7f  mov     rax, [rbp+string]
0x180040c83  mov     rcx, rsi
0x180040c86  mov     [rbp+var_10], rax
0x180040c8a  call    ??$MakeAndInitialize@VInstalledClassicAppInfoServer@@UIInstalledClassicAppInfo@Preview@Deployment@Management@Windows@@PEAUHSTRING__@@PEAU7@@Details@WRL@Microsoft@@YAJPEAPEAUIInstalledClassicAppInfo@Preview@Deployment@Management@Windows@@$$QEAPEAUHSTRING__@@1@Z; Microsoft::WRL::Details::MakeAndInitialize<InstalledClassicAppInfoServer,Windows::Management::Deployment::Preview::IInstalledClassicAppInfo,HSTRING__ *,HSTRING__ *>(Windows::Management::Deployment::Preview::IInstalledClassicAppInfo * *,HSTRING__ * &&,HSTRING__ * &&)
0x180040c8f  mov     ebx, eax
0x180040c91  jmp     short loc_180040C4F
0x180040c93  xor     eax, eax
0x180040c95  add     rsp, 40h
0x180040c99  pop     r14
0x180040c9b  pop     rdi
0x180040c9c  pop     rsi
0x180040c9d  pop     rbx
0x180040c9e  pop     rbp
0x180040c9f  retn
```

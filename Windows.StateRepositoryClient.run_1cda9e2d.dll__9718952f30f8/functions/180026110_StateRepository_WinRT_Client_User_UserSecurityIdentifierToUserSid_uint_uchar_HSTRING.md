# StateRepository::WinRT::Client::User::UserSecurityIdentifierToUserSid(uint,uchar *,HSTRING__ * *)

- ea: `0x180026110`
- end: `0x18002625f`
- name: `?UserSecurityIdentifierToUserSid@User@Client@WinRT@StateRepository@@YAJIPEAEPEAPEAUHSTRING__@@@Z`
- size: `335`
- prototype: `int(StateRepository::WinRT::Client::User *__hidden this, unsigned int, unsigned __int8 *, HSTRING *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019930`
- `0x18001aff0`

## callees

- `0x1800075c4`
- `0x1800075e4`
- `0x18000c298`
- `0x18000c408`
- `0x180026110`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026222`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026231`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026222`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026231`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180026199`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180026199`
- `ntdll!RtlLengthSid` at `0x18002617d`
- `ntdll!RtlLengthSid` at `0x18002617d`
- `ntdll!RtlValidSid` at `0x180026143`
- `ntdll!RtlValidSid` at `0x180026143`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002616d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026244`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002616d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026244`

## string_xrefs

- `0x180026155`: `onecore\base\appmodel\staterepository\winrt\common\src\winrt-client-user.cpp`
- `0x1800261a7`: `onecore\base\appmodel\staterepository\winrt\common\src\winrt-client-user.cpp`
- `0x18002620a`: `onecore\base\appmodel\staterepository\winrt\common\src\winrt-client-user.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::WinRT::Client::User::UserSecurityIdentifierToUserSid(
        StateRepository::WinRT::Client::User *this,
        void *a2,
        unsigned __int8 *a3,
        HSTRING *a4)
{
  HSTRING v5; // rax
  int v7; // edi
  __int64 v8; // rdx
  int LastError; // ebx
  const char *v11; // r9
  unsigned __int64 v12; // rcx
  const unsigned __int16 *v13; // r9
  unsigned int v14; // r8d
  const unsigned __int16 *v15; // rdx
  LPWSTR StringSid; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  unsigned int v18; // [rsp+58h] [rbp+28h] BYREF
  HSTRING string; // [rsp+68h] [rbp+38h] BYREF

  v5 = 0;
  string = 0;
  v7 = (int)this;
  if ( a2 )
  {
    if ( !RtlValidSid(a2) )
    {
      v8 = 46;
LABEL_4:
      LastError = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\common\\src\\winrt-client-user.cpp",
        (const char *)0x80070057LL,
        (int)StringSid);
LABEL_5:
      WindowsDeleteString(string);
      return (unsigned int)LastError;
    }
    if ( RtlLengthSid(a2) != v7 )
    {
      v8 = 47;
      goto LABEL_4;
    }
    StringSid = 0;
    if ( !ConvertSidToStringSidW(a2, &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x32,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\common\\src\\winrt-client-user.cpp",
                    v11);
LABEL_18:
      LocalFree(StringSid);
      goto LABEL_5;
    }
    if ( StringSid )
    {
      v18 = 0;
      v12 = -1;
      do
        ++v12;
      while ( StringSid[v12] );
      LastError = ULongLongToUInt(v12, &v18);
      if ( LastError < 0 )
        goto LABEL_17;
      v14 = v18;
      v15 = v13;
    }
    else
    {
      v14 = 0;
      v15 = &word_18002C434;
    }
    LastError = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v15, v14);
    if ( LastError < 0 )
    {
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\common\\src\\winrt-client-user.cpp",
        (const char *)(unsigned int)LastError,
        (int)StringSid);
      goto LABEL_18;
    }
    LocalFree(StringSid);
    v5 = string;
  }
  string = 0;
  *(_QWORD *)a3 = v5;
  WindowsDeleteString(0);
  return 0;
}

```

## disassembly

```asm
0x180026110  mov     [rsp-18h+arg_0], rbx
0x180026115  mov     [rsp-18h+arg_10], rsi
0x18002611a  push    rbp
0x18002611b  push    rdi
0x18002611c  push    r14
0x18002611e  mov     rbp, rsp
0x180026121  sub     rsp, 30h
0x180026125  xor     r14d, r14d
0x180026128  mov     rsi, r8
0x18002612b  mov     eax, r14d
0x18002612e  mov     rbx, rdx
0x180026131  mov     [rbp+string], rax
0x180026135  mov     edi, ecx
0x180026137  test    rdx, rdx
0x18002613a  jz      loc_18002623B
0x180026140  mov     rcx, rdx; Sid
0x180026143  call    cs:__imp_RtlValidSid
0x180026149  test    al, al
0x18002614b  jnz     short loc_18002617A
0x18002614d  lea     edx, [r14+2Eh]; void *
0x180026151  mov     rcx, [rbp+18h]; this
0x180026155  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\staterepositor"...
0x18002615c  mov     ebx, 80070057h
0x180026161  mov     r9d, ebx; char *
0x180026164  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026169  mov     rcx, [rbp+string]; string
0x18002616d  call    cs:__imp_WindowsDeleteString
0x180026173  mov     eax, ebx
0x180026175  jmp     loc_18002624C
0x18002617a  mov     rcx, rbx; Sid
0x18002617d  call    cs:__imp_RtlLengthSid
0x180026183  cmp     eax, edi
0x180026185  jz      short loc_18002618E
0x180026187  mov     edx, 2Fh ; '/'
0x18002618c  jmp     short loc_180026151
0x18002618e  lea     rdx, [rbp+StringSid]; StringSid
0x180026192  mov     [rbp+StringSid], r14
0x180026196  mov     rcx, rbx; Sid
0x180026199  call    cs:__imp_ConvertSidToStringSidW
0x18002619f  test    eax, eax
0x1800261a1  jnz     short loc_1800261BA
0x1800261a3  mov     rcx, [rbp+18h]; this
0x1800261a7  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\staterepositor"...
0x1800261ae  lea     edx, [rax+32h]; void *
0x1800261b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800261b6  mov     ebx, eax
0x1800261b8  jmp     short loc_18002621E
0x1800261ba  mov     r9, [rbp+StringSid]
0x1800261be  test    r9, r9
0x1800261c1  jz      short loc_1800261ED
0x1800261c3  mov     [rbp+arg_8], r14d
0x1800261c7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800261cb  inc     rcx; unsigned __int64
0x1800261ce  cmp     [r9+rcx*2], r14w
0x1800261d3  jnz     short loc_1800261CB
0x1800261d5  lea     rdx, [rbp+arg_8]; unsigned int *
0x1800261d9  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800261de  mov     ebx, eax
0x1800261e0  test    eax, eax
0x1800261e2  js      short loc_180026206
0x1800261e4  mov     r8d, [rbp+arg_8]
0x1800261e8  mov     rdx, r9
0x1800261eb  jmp     short loc_1800261F7
0x1800261ed  xor     r8d, r8d; unsigned int
0x1800261f0  lea     rdx, word_18002C434; unsigned __int16 *
0x1800261f7  lea     rcx, [rbp+string]; this
0x1800261fb  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180026200  mov     ebx, eax
0x180026202  test    eax, eax
0x180026204  jns     short loc_18002622D
0x180026206  mov     rcx, [rbp+18h]; this
0x18002620a  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\staterepositor"...
0x180026211  mov     r9d, ebx; char *
0x180026214  mov     edx, 33h ; '3'; void *
0x180026219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002621e  mov     rcx, [rbp+StringSid]; hMem
0x180026222  call    cs:__imp_LocalFree
0x180026228  jmp     loc_180026169
0x18002622d  mov     rcx, [rbp+StringSid]; hMem
0x180026231  call    cs:__imp_LocalFree
0x180026237  mov     rax, [rbp+string]
0x18002623b  xor     ecx, ecx; string
0x18002623d  mov     [rbp+string], r14
0x180026241  mov     [rsi], rax
0x180026244  call    cs:__imp_WindowsDeleteString
0x18002624a  xor     eax, eax
0x18002624c  mov     rbx, [rsp+30h+arg_0]
0x180026251  mov     rsi, [rsp+30h+arg_10]
0x180026256  add     rsp, 30h
0x18002625a  pop     r14
0x18002625c  pop     rdi
0x18002625d  pop     rbp
0x18002625e  retn
```

# AppxAllUserStore::ImmersiveUILayoutPolicyChecker::LoadIUIPolicyDLL(void)

- ea: `0x18001f780`
- end: `0x18001f880`
- name: `?LoadIUIPolicyDLL@ImmersiveUILayoutPolicyChecker@AppxAllUserStore@@AEAAJXZ`
- size: `256`
- prototype: `__int64 __fastcall(AppxAllUserStore::ImmersiveUILayoutPolicyChecker *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036a5c`

## callees

- `0x180004920`
- `0x180017f50`
- `0x18001f780`
- `0x18001f888`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001f7fa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001f814`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001f82e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001f7fa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001f814`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001f82e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18001f7cb`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18001f7cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f7da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f7da`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::ImmersiveUILayoutPolicyChecker::LoadIUIPolicyDLL(
        AppxAllUserStore::ImmersiveUILayoutPolicyChecker *this,
        struct Common::StringBuffer *a2)
{
  int IUILayoutPolicyModulePath; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  HMODULE Library; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  FARPROC v9; // rax
  FARPROC v10; // rax
  LPCWSTR lpLibFileName[2]; // [rsp+20h] [rbp-28h] BYREF
  int v13; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v13 = 0;
  *(_OWORD *)lpLibFileName = 0;
  IUILayoutPolicyModulePath = Common::Deployment::Configuration::GetIUILayoutPolicyModulePath(
                                (Common::Deployment::Configuration *)lpLibFileName,
                                a2);
  v4 = IUILayoutPolicyModulePath;
  if ( IUILayoutPolicyModulePath < 0 )
  {
    v5 = 34;
LABEL_13:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v5,
      (int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\immersiveuilayoutpolicychecker.cpp",
      (const char *)(unsigned int)IUILayoutPolicyModulePath);
    goto LABEL_14;
  }
  Library = (HMODULE)*((_QWORD *)this + 5);
  if ( !Library )
  {
    Library = LoadLibraryExW(lpLibFileName[1], 0, 0x800u);
    *((_QWORD *)this + 5) = Library;
    if ( !Library )
      goto LABEL_5;
  }
  ProcAddress = GetProcAddress(Library, "CloseLayoutPolicyCheckerInstance");
  *((_QWORD *)this + 10) = ProcAddress;
  if ( ProcAddress
    && (v9 = GetProcAddress(*((HMODULE *)this + 5), "GetLayoutPolicyCheckerInstance"), (*((_QWORD *)this + 8) = v9) != 0)
    && (v10 = GetProcAddress(*((HMODULE *)this + 5), "GetLayoutPolicy"), (*((_QWORD *)this + 9) = v10) != 0) )
  {
    IUILayoutPolicyModulePath = (*((__int64 (__fastcall **)(char *))this + 8))((char *)this + 48);
    v4 = IUILayoutPolicyModulePath;
    if ( IUILayoutPolicyModulePath < 0 )
    {
      v5 = 61;
      goto LABEL_13;
    }
  }
  else
  {
LABEL_5:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v4 = LastError;
  }
LABEL_14:
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpLibFileName);
  return v4;
}

```

## disassembly

```asm
0x18001f780  mov     [rsp+arg_0], rbx
0x18001f785  push    rdi
0x18001f786  sub     rsp, 40h
0x18001f78a  mov     rdi, rcx
0x18001f78d  xor     eax, eax
0x18001f78f  xorps   xmm0, xmm0
0x18001f792  mov     [rsp+48h+var_18], eax
0x18001f796  lea     rcx, [rsp+48h+lpLibFileName]; this
0x18001f79b  movups  xmmword ptr [rsp+48h+lpLibFileName], xmm0; int
0x18001f7a0  call    ?GetIUILayoutPolicyModulePath@Configuration@Deployment@Common@@YAJPEAVStringBuffer@3@@Z; Common::Deployment::Configuration::GetIUILayoutPolicyModulePath(Common::StringBuffer *)
0x18001f7a5  mov     ebx, eax
0x18001f7a7  test    eax, eax
0x18001f7a9  jns     short loc_18001F7B5
0x18001f7ab  mov     edx, 22h ; '"'
0x18001f7b0  jmp     loc_18001F855
0x18001f7b5  mov     rax, [rdi+28h]
0x18001f7b9  test    rax, rax
0x18001f7bc  jnz     short loc_18001F7F0
0x18001f7be  mov     rcx, [rsp+48h+lpLibFileName+8]; lpLibFileName
0x18001f7c3  xor     edx, edx; hFile
0x18001f7c5  mov     r8d, 800h; dwFlags
0x18001f7cb  call    cs:__imp_LoadLibraryExW
0x18001f7d1  mov     [rdi+28h], rax
0x18001f7d5  test    rax, rax
0x18001f7d8  jnz     short loc_18001F7F0
0x18001f7da  call    cs:__imp_GetLastError
0x18001f7e0  test    eax, eax
0x18001f7e2  jle     short loc_18001F7EC
0x18001f7e4  movzx   eax, ax
0x18001f7e7  or      eax, 80070000h
0x18001f7ec  mov     ebx, eax
0x18001f7ee  jmp     short loc_18001F869
0x18001f7f0  lea     rdx, aCloselayoutpol; "CloseLayoutPolicyCheckerInstance"
0x18001f7f7  mov     rcx, rax; hModule
0x18001f7fa  call    cs:__imp_GetProcAddress
0x18001f800  mov     [rdi+50h], rax
0x18001f804  test    rax, rax
0x18001f807  jz      short loc_18001F7DA
0x18001f809  mov     rcx, [rdi+28h]; hModule
0x18001f80d  lea     rdx, aGetlayoutpolic_0; "GetLayoutPolicyCheckerInstance"
0x18001f814  call    cs:__imp_GetProcAddress
0x18001f81a  mov     [rdi+40h], rax
0x18001f81e  test    rax, rax
0x18001f821  jz      short loc_18001F7DA
0x18001f823  mov     rcx, [rdi+28h]; hModule
0x18001f827  lea     rdx, aGetlayoutpolic; "GetLayoutPolicy"
0x18001f82e  call    cs:__imp_GetProcAddress
0x18001f834  mov     [rdi+48h], rax
0x18001f838  test    rax, rax
0x18001f83b  jz      short loc_18001F7DA
0x18001f83d  mov     rax, [rdi+40h]
0x18001f841  lea     rcx, [rdi+30h]
0x18001f845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f84a  mov     ebx, eax
0x18001f84c  test    eax, eax
0x18001f84e  jns     short loc_18001F869
0x18001f850  mov     edx, 3Dh ; '='; void *
0x18001f855  mov     rcx, [rsp+48h]; this
0x18001f85a  lea     r8, aOnecoreAdminAp_25; "onecore\\admin\\appmodel\\appxalluserst"...
0x18001f861  mov     r9d, eax; char *
0x18001f864  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f869  lea     rcx, [rsp+48h+lpLibFileName]; this
0x18001f86e  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x18001f873  mov     eax, ebx
0x18001f875  mov     rbx, [rsp+48h+arg_0]
0x18001f87a  add     rsp, 40h
0x18001f87e  pop     rdi
0x18001f87f  retn
```

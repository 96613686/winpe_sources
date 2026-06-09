# PromptForCreds(_CREDUI_INFOW *,ulong,ulong *,void const *,ulong,void * *,ulong *,int *,ulong,ulong *)

- ea: `0x140010a88`
- end: `0x140010bc5`
- name: `?PromptForCreds@@YAJPEAU_CREDUI_INFOW@@KPEAKPEBXKPEAPEAX1PEAHK1@Z`
- size: `317`
- prototype: `__int64 __fastcall(struct _CREDUI_INFOW *, int, unsigned int *, const void *, unsigned int, void **, unsigned int *, int *, unsigned int, LPDWORD lpExitCode)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017fc0`

## callees

- `0x140009064`
- `0x140010a88`
- `0x1400136dc`
- `0x1400136fc`
- `0x140016940`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140010b92`
- `KERNEL32!WaitForSingleObject` at `0x140010b92`
- `KERNEL32!GetExitCodeThread` at `0x140010ba2`
- `KERNEL32!GetExitCodeThread` at `0x140010ba2`
- `KERNEL32!CreateThread` at `0x140010b61`
- `KERNEL32!CreateThread` at `0x140010b61`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x140010ab7`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x140010ab7`

## string_xrefs

- `0x140010acc`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`
- `0x140010b77`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`

## pseudocode

```c
__int64 __fastcall PromptForCreds(
        struct _CREDUI_INFOW *a1,
        int a2,
        unsigned int *a3,
        const void *a4,
        unsigned int a5,
        void **a6,
        unsigned int *a7,
        int *a8,
        unsigned int a9,
        LPDWORD lpExitCode)
{
  int LastError; // ebx
  __int64 v15; // rdx
  HANDLE v16; // rax
  const char *v17; // r9
  void *v18; // rbx
  DWORD dwCreationFlags; // [rsp+20h] [rbp-71h]
  __int64 v21; // [rsp+30h] [rbp-61h] BYREF
  HANDLE v22; // [rsp+38h] [rbp-59h] BYREF
  struct _CREDUI_INFOW *Parameter; // [rsp+40h] [rbp-51h] BYREF
  int v24; // [rsp+48h] [rbp-49h]
  int v25; // [rsp+4Ch] [rbp-45h]
  unsigned int *v26; // [rsp+50h] [rbp-41h]
  const void *v27; // [rsp+58h] [rbp-39h]
  unsigned int v28; // [rsp+60h] [rbp-31h]
  int v29; // [rsp+64h] [rbp-2Dh]
  void **v30; // [rsp+68h] [rbp-29h]
  unsigned int *v31; // [rsp+70h] [rbp-21h]
  int *v32; // [rsp+78h] [rbp-19h]
  unsigned int v33; // [rsp+80h] [rbp-11h]
  int v34; // [rsp+84h] [rbp-Dh]
  __int64 v35; // [rsp+88h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+37h]

  v21 = 0;
  LastError = UMgrQueryUserContext(0, &v21);
  if ( LastError < 0 )
  {
    v15 = 187;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
      (const char *)(unsigned int)LastError,
      dwCreationFlags);
    return (unsigned int)LastError;
  }
  LastError = TranslateOwnerHwnd(&a1->hwndParent);
  if ( LastError < 0 )
  {
    v15 = 189;
    goto LABEL_3;
  }
  v25 = 0;
  v28 = a5;
  Parameter = a1;
  v29 = 0;
  v30 = a6;
  v31 = a7;
  v32 = a8;
  v33 = a9;
  v34 = 0;
  v35 = v21;
  v24 = a2;
  v26 = a3;
  v27 = a4;
  v16 = CreateThread(0, 0, LaunchCredUIThreadProc, &Parameter, 0, 0);
  v22 = v16;
  v18 = v16;
  if ( v16 )
  {
    WaitForSingleObject(v16, 0xFFFFFFFF);
    GetExitCodeThread(v18, lpExitCode);
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD5,
                  (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
                  v17);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140010a88  push    rbp
0x140010a8a  push    rbx
0x140010a8b  push    rsi
0x140010a8c  push    rdi
0x140010a8d  push    r14
0x140010a8f  push    r15
0x140010a91  lea     rbp, [rsp-7]
0x140010a96  sub     rsp, 98h
0x140010a9d  mov     r15d, edx
0x140010aa0  mov     [rbp+2Fh+var_90], 0
0x140010aa8  mov     rdi, rcx
0x140010aab  lea     rdx, [rbp+2Fh+var_90]
0x140010aaf  xor     ecx, ecx
0x140010ab1  mov     rsi, r9
0x140010ab4  mov     r14, r8
0x140010ab7  call    cs:__imp_UMgrQueryUserContext
0x140010abd  mov     ebx, eax
0x140010abf  test    eax, eax
0x140010ac1  jns     short loc_140010AE0
0x140010ac3  mov     edx, 0BBh; void *
0x140010ac8  mov     rcx, [rbp+37h]; this
0x140010acc  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x140010ad3  mov     r9d, ebx; char *
0x140010ad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010adb  jmp     loc_140010BB3
0x140010ae0  lea     rcx, [rdi+8]; HWND *
0x140010ae4  call    ?TranslateOwnerHwnd@@YAJAEAPEAUHWND__@@@Z; TranslateOwnerHwnd(HWND__ * &)
0x140010ae9  mov     ebx, eax
0x140010aeb  test    eax, eax
0x140010aed  jns     short loc_140010AF6
0x140010aef  mov     edx, 0BDh
0x140010af4  jmp     short loc_140010AC8
0x140010af6  xor     eax, eax
0x140010af8  mov     [rsp+0C0h+lpThreadId], 0; lpThreadId
0x140010b01  mov     [rbp+2Fh+var_74], eax
0x140010b04  lea     r9, [rbp+2Fh+Parameter]; lpParameter
0x140010b08  mov     eax, [rbp+2Fh+arg_20]
0x140010b0b  lea     r8, ?LaunchCredUIThreadProc@@YAKPEAX@Z; lpStartAddress
0x140010b12  mov     [rbp+2Fh+var_60], eax
0x140010b15  xor     edx, edx; dwStackSize
0x140010b17  xor     eax, eax
0x140010b19  mov     [rbp+2Fh+Parameter], rdi
0x140010b1d  mov     [rbp+2Fh+var_5C], eax
0x140010b20  xor     ecx, ecx; lpThreadAttributes
0x140010b22  mov     rax, [rbp+2Fh+arg_28]
0x140010b26  mov     [rbp+2Fh+var_58], rax
0x140010b2a  mov     rax, [rbp+2Fh+arg_30]
0x140010b2e  mov     [rbp+2Fh+var_50], rax
0x140010b32  mov     rax, [rbp+2Fh+arg_38]
0x140010b36  mov     [rbp+2Fh+var_48], rax
0x140010b3a  mov     eax, [rbp+2Fh+arg_40]
0x140010b3d  mov     [rbp+2Fh+var_40], eax
0x140010b40  xor     eax, eax
0x140010b42  mov     [rbp+2Fh+var_3C], eax
0x140010b45  mov     rax, [rbp+2Fh+var_90]
0x140010b49  mov     [rbp+2Fh+var_38], rax
0x140010b4d  mov     [rbp+2Fh+var_78], r15d
0x140010b51  mov     [rbp+2Fh+var_70], r14
0x140010b55  mov     [rbp+2Fh+var_68], rsi
0x140010b59  mov     [rsp+0C0h+dwCreationFlags], 0; dwCreationFlags
0x140010b61  call    cs:__imp_CreateThread
0x140010b67  mov     [rbp+2Fh+var_88], rax
0x140010b6b  mov     rbx, rax
0x140010b6e  test    rax, rax
0x140010b71  jnz     short loc_140010B8C
0x140010b73  mov     rcx, [rbp+37h]; this
0x140010b77  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x140010b7e  mov     edx, 0D5h; void *
0x140010b83  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140010b88  mov     ebx, eax
0x140010b8a  jmp     short loc_140010BAA
0x140010b8c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140010b8f  mov     rcx, rbx; hHandle
0x140010b92  call    cs:__imp_WaitForSingleObject
0x140010b98  mov     rdx, [rbp+2Fh+lpExitCode]; lpExitCode
0x140010b9f  mov     rcx, rbx; hThread
0x140010ba2  call    cs:__imp_GetExitCodeThread
0x140010ba8  xor     ebx, ebx
0x140010baa  lea     rcx, [rbp+2Fh+var_88]
0x140010bae  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140010bb3  mov     eax, ebx
0x140010bb5  add     rsp, 98h
0x140010bbc  pop     r15
0x140010bbe  pop     r14
0x140010bc0  pop     rdi
0x140010bc1  pop     rsi
0x140010bc2  pop     rbx
0x140010bc3  pop     rbp
0x140010bc4  retn
```

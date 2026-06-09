# CSkyDriveNetworkStatesSSO::EnsureNetworkHandlerIsEnabled(void)

- ea: `0x18001c1d8`
- end: `0x18001c2d5`
- name: `?EnsureNetworkHandlerIsEnabled@CSkyDriveNetworkStatesSSO@@AEAAJXZ`
- size: `253`
- prototype: `__int64 __fastcall(CSkyDriveNetworkStatesSSO *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c130`
- `0x18001c380`

## callees

- `0x180004a54`
- `0x1800077c8`
- `0x18001c1d8`
- `0x180037780`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c2ca`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c2ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c21c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c21c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c244`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001c244`

## string_xrefs

- `0x18001c289`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\skydrivenetworkstates.cpp`

## pseudocode

```c
__int64 __fastcall CSkyDriveNetworkStatesSSO::EnsureNetworkHandlerIsEnabled(CSkyDriveNetworkStatesSSO *this)
{
  _QWORD *v1; // r14
  _QWORD *v3; // rdi
  HSTRING v4; // rbx
  int ActivationFactory; // ebx
  __int64 v6; // rdx
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v1 = (_QWORD *)((char *)this + 64);
  v3 = (_QWORD *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) )
    goto LABEL_2;
  if ( *v3 )
    return 0;
  if ( !*v1 )
  {
LABEL_2:
    if ( WindowsCreateStringReference(
           L"Windows.Networking.Connectivity.NetworkInformation",
           0x32u,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v4 = string;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(v1);
    ActivationFactory = RoGetActivationFactory(v4, &GUID_5074f851_950d_4165_9c15_365619481eea, v1);
    if ( ActivationFactory < 0 )
    {
      v6 = 175;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\skydrivenetworkstates.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)string);
      return (unsigned int)ActivationFactory;
    }
  }
  if ( !*v3 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD *))(*(_QWORD *)*v1 + 96LL))(
                          *v1,
                          (char *)this + 8,
                          v3);
    if ( ActivationFactory < 0 )
    {
      v6 = 180;
      goto LABEL_10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001c1d8  push    rbx
0x18001c1da  push    rsi
0x18001c1db  push    rdi
0x18001c1dc  push    r14
0x18001c1de  sub     rsp, 58h
0x18001c1e2  mov     rax, cs:__security_cookie
0x18001c1e9  xor     rax, rsp
0x18001c1ec  mov     [rsp+78h+var_38], rax
0x18001c1f1  lea     r14, [rcx+40h]
0x18001c1f5  mov     rsi, rcx
0x18001c1f8  cmp     qword ptr [r14], 0
0x18001c1fc  lea     rdi, [rcx+48h]
0x18001c200  jnz     loc_18001C2B1
0x18001c206  lea     r9, [rsp+78h+string]; string
0x18001c20b  mov     edx, 32h ; '2'; length
0x18001c210  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x18001c215  lea     rcx, ?RuntimeClass_Windows_Networking_Connectivity_NetworkInformation@@3QBGB; "Windows.Networking.Connectivity.Network"...
0x18001c21c  call    cs:__imp_WindowsCreateStringReference
0x18001c222  test    eax, eax
0x18001c224  js      loc_18001C2BB
0x18001c22a  mov     rbx, [rsp+78h+string]
0x18001c22f  mov     rcx, r14
0x18001c232  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18001c237  mov     r8, r14
0x18001c23a  lea     rdx, _GUID_5074f851_950d_4165_9c15_365619481eea
0x18001c241  mov     rcx, rbx
0x18001c244  call    cs:__imp_RoGetActivationFactory
0x18001c24a  mov     ebx, eax
0x18001c24c  test    eax, eax
0x18001c24e  jns     short loc_18001C25D
0x18001c250  mov     edx, 0AFh
0x18001c255  jmp     short loc_18001C284
0x18001c257  cmp     qword ptr [r14], 0
0x18001c25b  jz      short loc_18001C206
0x18001c25d  cmp     qword ptr [rdi], 0
0x18001c261  jnz     short loc_18001C2B7
0x18001c263  mov     rcx, [r14]
0x18001c266  lea     rdx, [rsi+8]
0x18001c26a  mov     r8, rdi
0x18001c26d  mov     rax, [rcx]
0x18001c270  mov     rax, [rax+60h]
0x18001c274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c279  mov     ebx, eax
0x18001c27b  test    eax, eax
0x18001c27d  jns     short loc_18001C2B7
0x18001c27f  mov     edx, 0B4h; void *
0x18001c284  mov     rcx, [rsp+78h]; this
0x18001c289  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\fileexplorer\\windo"...
0x18001c290  mov     r9d, ebx; char *
0x18001c293  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c298  mov     eax, ebx
0x18001c29a  mov     rcx, [rsp+78h+var_38]
0x18001c29f  xor     rcx, rsp; StackCookie
0x18001c2a2  call    __security_check_cookie
0x18001c2a7  add     rsp, 58h
0x18001c2ab  pop     r14
0x18001c2ad  pop     rdi
0x18001c2ae  pop     rsi
0x18001c2af  pop     rbx
0x18001c2b0  retn
0x18001c2b1  cmp     qword ptr [rdi], 0
0x18001c2b5  jz      short loc_18001C257
0x18001c2b7  xor     eax, eax
0x18001c2b9  jmp     short loc_18001C29A
0x18001c2bb  xor     r9d, r9d; lpArguments
0x18001c2be  xor     r8d, r8d; nNumberOfArguments
0x18001c2c1  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001c2c6  lea     edx, [r9+1]; dwExceptionFlags
0x18001c2ca  call    cs:__imp_RaiseException
0x18001c2d0  jmp     loc_18001C22A
```

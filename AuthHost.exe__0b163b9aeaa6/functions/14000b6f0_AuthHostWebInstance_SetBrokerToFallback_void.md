# AuthHostWebInstance::SetBrokerToFallback(void)

- ea: `0x14000b6f0`
- end: `0x14000b7cd`
- name: `?SetBrokerToFallback@AuthHostWebInstance@@AEAAXXZ`
- size: `221`
- prototype: `void __fastcall(AuthHostWebInstance *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140005940`
- `0x14000a4b0`

## callees

- `0x140002c70`
- `0x1400096a8`
- `0x14000b6f0`
- `0x14000bb4c`
- `0x140012f60`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000b755`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000b755`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000b73c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000b73c`

## pseudocode

```c
void __fastcall AuthHostWebInstance::SetBrokerToFallback(AuthHostWebInstance *this)
{
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF

  if ( !*((_DWORD *)this + 122) && !(unsigned int)HasWebDialogHeaderMetaTag((AuthHostWebInstance *)((char *)this + 176)) )
  {
    if ( WindowsCreateStringReference(&szColor, 0, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 30, &WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids);
    }
    (*(void (__fastcall **)(_QWORD, HSTRING, __int64))(**((_QWORD **)this + 13) + 112LL))(
      *((_QWORD *)this + 13),
      string,
      0xFFFFFFFFLL);
    AuthHostWebInstance::UpdateBrokerLogo((HSTRING *)this);
    *((_DWORD *)this + 122) = 1;
  }
}

```

## disassembly

```asm
0x14000b6f0  push    rbx
0x14000b6f2  sub     rsp, 50h
0x14000b6f6  mov     rax, cs:__security_cookie
0x14000b6fd  xor     rax, rsp
0x14000b700  mov     [rsp+58h+var_18], rax
0x14000b705  cmp     dword ptr [rcx+1E8h], 0
0x14000b70c  mov     rbx, rcx
0x14000b70f  jnz     loc_14000B7BA
0x14000b715  add     rcx, 0B0h; struct _WEB_DIALOG_META_TAG_CONTENT *
0x14000b71c  call    ?HasWebDialogHeaderMetaTag@@YAHPEAU_WEB_DIALOG_META_TAG_CONTENT@@@Z; HasWebDialogHeaderMetaTag(_WEB_DIALOG_META_TAG_CONTENT *)
0x14000b721  test    eax, eax
0x14000b723  jnz     loc_14000B7BA
0x14000b729  lea     r9, [rsp+58h+string]; string
0x14000b72e  xor     edx, edx; length
0x14000b730  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x14000b735  lea     rcx, szColor; sourceString
0x14000b73c  call    cs:__imp_WindowsCreateStringReference
0x14000b742  test    eax, eax
0x14000b744  jns     short loc_14000B75B
0x14000b746  xor     r9d, r9d; lpArguments
0x14000b749  xor     r8d, r8d; nNumberOfArguments
0x14000b74c  mov     ecx, 0C000000Dh; dwExceptionCode
0x14000b751  lea     edx, [r9+1]; dwExceptionFlags
0x14000b755  call    cs:__imp_RaiseException
0x14000b75b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b762  lea     rax, WPP_GLOBAL_Control
0x14000b769  cmp     rcx, rax
0x14000b76c  jz      short loc_14000B78F
0x14000b76e  test    byte ptr [rcx+44h], 4
0x14000b772  jz      short loc_14000B78F
0x14000b774  cmp     byte ptr [rcx+41h], 5
0x14000b778  jb      short loc_14000B78F
0x14000b77a  mov     rcx, [rcx+38h]
0x14000b77e  lea     r8, WPP_eb10dd10cfca36d0d06c224971275cc2_Traceguids
0x14000b785  mov     edx, 1Eh
0x14000b78a  call    WPP_SF_
0x14000b78f  mov     rcx, [rbx+68h]
0x14000b793  or      r8d, 0FFFFFFFFh
0x14000b797  mov     rdx, [rsp+58h+string]
0x14000b79c  mov     rax, [rcx]
0x14000b79f  mov     rax, [rax+70h]
0x14000b7a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7a8  mov     rcx, rbx; this
0x14000b7ab  call    ?UpdateBrokerLogo@AuthHostWebInstance@@AEAAXXZ; AuthHostWebInstance::UpdateBrokerLogo(void)
0x14000b7b0  mov     dword ptr [rbx+1E8h], 1
0x14000b7ba  mov     rcx, [rsp+58h+var_18]
0x14000b7bf  xor     rcx, rsp; StackCookie
0x14000b7c2  call    __security_check_cookie
0x14000b7c7  add     rsp, 50h
0x14000b7cb  pop     rbx
0x14000b7cc  retn
```

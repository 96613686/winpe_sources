# Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)

- ea: `0x140006d90`
- end: `0x140006f00`
- name: `??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140006d90`
- `0x14000a0b8`
- `0x14000e1c0`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x140006ed6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x140006ed6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140006e76`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140006e76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x140006dcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x140006dcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x140006de1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x140006de1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140006dff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140006dff`

## string_xrefs

- `0x140006e9f`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::ActivationFactoryCallback<2>(
        HSTRING string,
        struct Microsoft::WRL::Details::CreatorMap *a2)
{
  Microsoft::WRL::Details *v4; // rsi
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rbp
  __int64 v8; // rax
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  unsigned int *v11; // r8
  int v12; // edx
  unsigned int v13; // ebx
  struct IUnknown **v15; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v17; // [rsp+34h] [rbp-64h] BYREF
  __int128 v18; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v19[22]; // [rsp+48h] [rbp-50h]

  v4 = Microsoft::WRL::Details::ModuleBase::module_;
  *(_QWORD *)a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v18 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v19 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v19[14] = *(_QWORD *)L"sId";
    v13 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v18);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v4 + 40LL))(v4) + 8);
    v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v4 + 48LL))(v4);
    if ( (unsigned __int64)v6 >= v7 )
    {
LABEL_11:
      v13 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *v6 )
        {
          v8 = (*(__int64 (**)(void))(*v6)->Data4)();
          v9 = (unsigned __int16 *)StringRawBuffer;
          v10 = v8 - (_QWORD)StringRawBuffer;
          do
          {
            v11 = (unsigned int *)*(unsigned __int16 *)((char *)v9 + v10);
            v12 = *v9 - (_DWORD)v11;
            if ( v12 )
              break;
            ++v9;
          }
          while ( (_DWORD)v11 );
          if ( !v12 )
            break;
        }
        if ( (unsigned __int64)++v6 >= v7 )
          goto LABEL_11;
      }
      v17 = 2;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             v4,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v17,
                             v11,
                             *v6,
                             a2,
                             v15);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x140006d90  mov     [rsp+arg_10], rbx
0x140006d95  push    rbp
0x140006d96  push    rsi
0x140006d97  push    rdi
0x140006d98  push    r14
0x140006d9a  push    r15
0x140006d9c  sub     rsp, 70h
0x140006da0  mov     rax, cs:__security_cookie
0x140006da7  xor     rax, rsp
0x140006daa  mov     [rsp+98h+var_38], rax
0x140006daf  mov     r14, rdx
0x140006db2  mov     rdi, rcx
0x140006db5  mov     rsi, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140006dbc  mov     qword ptr [rdx], 0
0x140006dc3  mov     [rsp+98h+hasEmbedNull], 0
0x140006dcb  call    cs:__imp_WindowsIsStringEmpty
0x140006dd1  test    eax, eax
0x140006dd3  jnz     loc_140006E9F
0x140006dd9  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x140006dde  mov     rcx, rdi; string
0x140006de1  call    cs:__imp_WindowsStringHasEmbeddedNull
0x140006de7  test    eax, eax
0x140006de9  js      loc_140006E9F
0x140006def  cmp     [rsp+98h+hasEmbedNull], 1
0x140006df4  jz      loc_140006E9F
0x140006dfa  xor     edx, edx; length
0x140006dfc  mov     rcx, rdi; string
0x140006dff  call    cs:__imp_WindowsGetStringRawBuffer
0x140006e05  mov     r15, rax
0x140006e08  mov     rcx, [rsi]
0x140006e0b  mov     rax, [rcx+28h]
0x140006e0f  mov     rcx, rsi
0x140006e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e17  lea     rbx, [rax+8]
0x140006e1b  mov     rcx, [rsi]
0x140006e1e  mov     rax, [rcx+30h]
0x140006e22  mov     rcx, rsi
0x140006e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e2a  mov     rbp, rax
0x140006e2d  cmp     rbx, rax
0x140006e30  jnb     short loc_140006E6C
0x140006e32  mov     rax, [rbx]
0x140006e35  test    rax, rax
0x140006e38  jz      short loc_140006E63
0x140006e3a  mov     rax, [rax+8]
0x140006e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e43  mov     rcx, r15
0x140006e46  sub     rax, r15
0x140006e49  movzx   edx, word ptr [rcx]
0x140006e4c  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x140006e51  sub     edx, r8d
0x140006e54  jnz     short loc_140006E5F
0x140006e56  add     rcx, 2
0x140006e5a  test    r8d, r8d
0x140006e5d  jnz     short loc_140006E49
0x140006e5f  test    edx, edx
0x140006e61  jz      short loc_140006E7E
0x140006e63  add     rbx, 8
0x140006e67  cmp     rbx, rbp
0x140006e6a  jb      short loc_140006E32
0x140006e6c  mov     rdx, rdi
0x140006e6f  mov     ebx, 80040111h
0x140006e74  mov     ecx, ebx
0x140006e76  call    cs:__imp_RoOriginateError
0x140006e7c  jmp     short loc_140006EDD
0x140006e7e  mov     [rsp+98h+var_64], 2
0x140006e86  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x140006e8b  mov     r9, [rbx]; struct _GUID *
0x140006e8e  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x140006e93  mov     rcx, rsi; this
0x140006e96  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x140006e9b  mov     ebx, eax
0x140006e9d  jmp     short loc_140006EDD
0x140006e9f  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x140006ea6  movups  [rsp+98h+var_60], xmm0
0x140006eab  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x140006eb2  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x140006eb7  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x140006ebf  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x140006ec5  lea     r8, [rsp+98h+var_60]
0x140006eca  mov     edx, 12h
0x140006ecf  mov     ebx, 80070057h
0x140006ed4  mov     ecx, ebx
0x140006ed6  call    cs:__imp_RoOriginateErrorW
0x140006edc  nop
0x140006edd  mov     eax, ebx
0x140006edf  mov     rcx, [rsp+98h+var_38]
0x140006ee4  xor     rcx, rsp; StackCookie
0x140006ee7  call    __security_check_cookie
0x140006eec  mov     rbx, [rsp+98h+arg_10]
0x140006ef4  add     rsp, 70h
0x140006ef8  pop     r15
0x140006efa  pop     r14
0x140006efc  pop     rdi
0x140006efd  pop     rsi
0x140006efe  pop     rbp
0x140006eff  retn
```

# Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)

- ea: `0x180002d20`
- end: `0x180002e97`
- name: `??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800016c0`
- `0x180002494`
- `0x180002d20`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002e06`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002e06`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180002e6d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180002e6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180002d71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180002d71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180002d8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180002d8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180002d5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180002d5b`

## string_xrefs

- `0x180002e36`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING string, _QWORD *Ptr)
{
  Microsoft::WRL::Details *v4; // rsi
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rbp
  __int64 v8; // rax
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  int v11; // r8d
  int v12; // edx
  unsigned int v13; // ebx
  struct IUnknown **v15; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v17; // [rsp+34h] [rbp-64h] BYREF
  __int128 v18; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v19[22]; // [rsp+48h] [rbp-50h]

  v4 = Microsoft::WRL::Details::ModuleBase::module_;
  *Ptr = 0;
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
            v11 = *(unsigned __int16 *)((char *)v9 + v10);
            v12 = *v9 - v11;
            if ( v12 )
              break;
            ++v9;
          }
          while ( v11 );
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
                             &GUID_00000035_0000_0000_c000_000000000046.Data1,
                             *v6,
                             Ptr,
                             v15);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180002d20  mov     [rsp+arg_10], rbx
0x180002d25  push    rbp
0x180002d26  push    rsi
0x180002d27  push    rdi
0x180002d28  push    r14
0x180002d2a  push    r15
0x180002d2c  sub     rsp, 70h
0x180002d30  mov     rax, cs:__security_cookie
0x180002d37  xor     rax, rsp
0x180002d3a  mov     [rsp+98h+var_38], rax
0x180002d3f  mov     r14, rdx
0x180002d42  mov     rdi, rcx
0x180002d45  mov     rsi, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002d4c  mov     qword ptr [rdx], 0
0x180002d53  mov     [rsp+98h+hasEmbedNull], 0
0x180002d5b  call    cs:__imp_WindowsIsStringEmpty
0x180002d61  test    eax, eax
0x180002d63  jnz     loc_180002E36
0x180002d69  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180002d6e  mov     rcx, rdi; string
0x180002d71  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180002d77  test    eax, eax
0x180002d79  js      loc_180002E36
0x180002d7f  cmp     [rsp+98h+hasEmbedNull], 1
0x180002d84  jz      loc_180002E36
0x180002d8a  xor     edx, edx; length
0x180002d8c  mov     rcx, rdi; string
0x180002d8f  call    cs:__imp_WindowsGetStringRawBuffer
0x180002d95  mov     r15, rax
0x180002d98  mov     rcx, [rsi]
0x180002d9b  mov     rax, [rcx+28h]
0x180002d9f  mov     rcx, rsi
0x180002da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da7  lea     rbx, [rax+8]
0x180002dab  mov     rcx, [rsi]
0x180002dae  mov     rax, [rcx+30h]
0x180002db2  mov     rcx, rsi
0x180002db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dba  mov     rbp, rax
0x180002dbd  cmp     rbx, rax
0x180002dc0  jnb     short loc_180002DFC
0x180002dc2  mov     rax, [rbx]
0x180002dc5  test    rax, rax
0x180002dc8  jz      short loc_180002DF3
0x180002dca  mov     rax, [rax+8]
0x180002dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd3  mov     rcx, r15
0x180002dd6  sub     rax, r15
0x180002dd9  movzx   edx, word ptr [rcx]
0x180002ddc  movzx   r8d, word ptr [rcx+rax]
0x180002de1  sub     edx, r8d
0x180002de4  jnz     short loc_180002DEF
0x180002de6  add     rcx, 2
0x180002dea  test    r8d, r8d
0x180002ded  jnz     short loc_180002DD9
0x180002def  test    edx, edx
0x180002df1  jz      short loc_180002E0E
0x180002df3  add     rbx, 8
0x180002df7  cmp     rbx, rbp
0x180002dfa  jb      short loc_180002DC2
0x180002dfc  mov     rdx, rdi
0x180002dff  mov     ebx, 80040111h
0x180002e04  mov     ecx, ebx
0x180002e06  call    cs:__imp_RoOriginateError
0x180002e0c  jmp     short loc_180002E74
0x180002e0e  mov     [rsp+98h+var_64], 2
0x180002e16  mov     [rsp+98h+Ptr], r14; Ptr
0x180002e1b  mov     r9, [rbx]; struct _GUID *
0x180002e1e  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180002e25  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180002e2a  mov     rcx, rsi; this
0x180002e2d  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180002e32  mov     ebx, eax
0x180002e34  jmp     short loc_180002E74
0x180002e36  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180002e3d  movups  [rsp+98h+var_60], xmm0
0x180002e42  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180002e49  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180002e4e  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180002e56  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180002e5c  lea     r8, [rsp+98h+var_60]
0x180002e61  mov     edx, 12h
0x180002e66  mov     ebx, 80070057h
0x180002e6b  mov     ecx, ebx
0x180002e6d  call    cs:__imp_RoOriginateErrorW
0x180002e73  nop
0x180002e74  mov     eax, ebx
0x180002e76  mov     rcx, [rsp+98h+var_38]
0x180002e7b  xor     rcx, rsp; StackCookie
0x180002e7e  call    __security_check_cookie
0x180002e83  mov     rbx, [rsp+98h+arg_10]
0x180002e8b  add     rsp, 70h
0x180002e8f  pop     r15
0x180002e91  pop     r14
0x180002e93  pop     rdi
0x180002e94  pop     rsi
0x180002e95  pop     rbp
0x180002e96  retn
```

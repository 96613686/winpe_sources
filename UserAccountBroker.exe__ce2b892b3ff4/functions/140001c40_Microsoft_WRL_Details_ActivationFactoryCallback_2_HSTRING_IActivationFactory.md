# Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)

- ea: `0x140001c40`
- end: `0x140001daf`
- name: `??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140001c40`
- `0x140002b94`
- `0x140006b90`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140001caf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140001caf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x140001c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x140001c91`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x140001c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x140001c7b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140001d26`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140001d26`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x140001d86`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x140001d86`

## string_xrefs

- `0x140001d4f`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ActivationFactoryCallback<2>(
        HSTRING string,
        struct Microsoft::WRL::Details::CreatorMap *a2)
{
  Microsoft::WRL::Details *v2; // rsi
  PCWSTR StringRawBuffer; // r15
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rbp
  __int64 v8; // rax
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  unsigned int *v11; // r8
  int v12; // edx
  unsigned int v13; // ebx
  const struct _GUID *v14; // r9
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v17; // [rsp+34h] [rbp-64h] BYREF
  __int128 v18; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v19[22]; // [rsp+48h] [rbp-50h]

  v2 = Microsoft::WRL::Details::ModuleBase::module_;
  *(_QWORD *)a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v13 = -2147024809;
    v18 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v19 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v19[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v18);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v6 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v2 + 40LL))(v2) + 8;
    v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v2 + 48LL))(v2);
    if ( v6 >= v7 )
    {
LABEL_11:
      v13 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *(_QWORD *)v6 )
        {
          v8 = (*(__int64 (**)(void))(*(_QWORD *)v6 + 8LL))();
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
        v6 += 8LL;
        if ( v6 >= v7 )
          goto LABEL_11;
      }
      v14 = *(const struct _GUID **)v6;
      v17 = 2;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             v2,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v17,
                             v11,
                             v14,
                             a2);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x140001c40  mov     [rsp+arg_10], rbx
0x140001c45  push    rbp
0x140001c46  push    rsi
0x140001c47  push    rdi
0x140001c48  push    r14
0x140001c4a  push    r15
0x140001c4c  sub     rsp, 70h
0x140001c50  mov     rax, cs:__security_cookie
0x140001c57  xor     rax, rsp
0x140001c5a  mov     [rsp+98h+var_38], rax
0x140001c5f  mov     rsi, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140001c66  mov     r14, rdx
0x140001c69  mov     rdi, rcx
0x140001c6c  mov     qword ptr [rdx], 0
0x140001c73  mov     [rsp+98h+hasEmbedNull], 0
0x140001c7b  call    cs:__imp_WindowsIsStringEmpty
0x140001c81  test    eax, eax
0x140001c83  jnz     loc_140001D4F
0x140001c89  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x140001c8e  mov     rcx, rdi; string
0x140001c91  call    cs:__imp_WindowsStringHasEmbeddedNull
0x140001c97  test    eax, eax
0x140001c99  js      loc_140001D4F
0x140001c9f  cmp     [rsp+98h+hasEmbedNull], 1
0x140001ca4  jz      loc_140001D4F
0x140001caa  xor     edx, edx; length
0x140001cac  mov     rcx, rdi; string
0x140001caf  call    cs:__imp_WindowsGetStringRawBuffer
0x140001cb5  mov     rcx, [rsi]
0x140001cb8  mov     r15, rax
0x140001cbb  mov     rax, [rcx+28h]
0x140001cbf  mov     rcx, rsi
0x140001cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001cc7  mov     rcx, [rsi]
0x140001cca  lea     rbx, [rax+8]
0x140001cce  mov     rax, [rcx+30h]
0x140001cd2  mov     rcx, rsi
0x140001cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001cda  mov     rbp, rax
0x140001cdd  cmp     rbx, rax
0x140001ce0  jnb     short loc_140001D1C
0x140001ce2  mov     rax, [rbx]
0x140001ce5  test    rax, rax
0x140001ce8  jz      short loc_140001D13
0x140001cea  mov     rax, [rax+8]
0x140001cee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001cf3  mov     rcx, r15
0x140001cf6  sub     rax, r15
0x140001cf9  movzx   edx, word ptr [rcx]
0x140001cfc  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x140001d01  sub     edx, r8d
0x140001d04  jnz     short loc_140001D0F
0x140001d06  add     rcx, 2
0x140001d0a  test    r8d, r8d
0x140001d0d  jnz     short loc_140001CF9
0x140001d0f  test    edx, edx
0x140001d11  jz      short loc_140001D2E
0x140001d13  add     rbx, 8
0x140001d17  cmp     rbx, rbp
0x140001d1a  jb      short loc_140001CE2
0x140001d1c  mov     ebx, 80040111h
0x140001d21  mov     rdx, rdi
0x140001d24  mov     ecx, ebx
0x140001d26  call    cs:__imp_RoOriginateError
0x140001d2c  jmp     short loc_140001D8C
0x140001d2e  mov     r9, [rbx]; struct _GUID *
0x140001d31  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x140001d36  mov     rcx, rsi; this
0x140001d39  mov     [rsp+98h+var_64], 2
0x140001d41  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x140001d46  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x140001d4b  mov     ebx, eax
0x140001d4d  jmp     short loc_140001D8C
0x140001d4f  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x140001d56  mov     ebx, 80070057h
0x140001d5b  lea     r8, [rsp+98h+var_60]
0x140001d60  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x140001d67  mov     edx, 12h
0x140001d6c  mov     ecx, ebx
0x140001d6e  movups  [rsp+98h+var_60], xmm0
0x140001d73  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x140001d7b  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x140001d80  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x140001d86  call    cs:__imp_RoOriginateErrorW
0x140001d8c  mov     eax, ebx
0x140001d8e  mov     rcx, [rsp+98h+var_38]
0x140001d93  xor     rcx, rsp; StackCookie
0x140001d96  call    __security_check_cookie
0x140001d9b  mov     rbx, [rsp+98h+arg_10]
0x140001da3  add     rsp, 70h
0x140001da7  pop     r15
0x140001da9  pop     r14
0x140001dab  pop     rdi
0x140001dac  pop     rsi
0x140001dad  pop     rbp
0x140001dae  retn
```

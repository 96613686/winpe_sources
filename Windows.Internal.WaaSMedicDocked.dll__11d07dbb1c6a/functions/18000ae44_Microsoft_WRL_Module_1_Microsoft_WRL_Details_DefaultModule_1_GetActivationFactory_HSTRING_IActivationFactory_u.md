# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::GetActivationFactory(HSTRING__ *,IActivationFactory * *,ushort const *)

- ea: `0x18000ae44`
- end: `0x18000afb3`
- name: `?GetActivationFactory@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@PEBG@Z`
- size: `367`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b2fc`

## callees

- `0x180001570`
- `0x18000ae44`
- `0x18000afbc`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000af29`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000af29`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000af89`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000af89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000ae94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000ae94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000aeb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000aeb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000ae7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000ae7e`

## string_xrefs

- `0x18000af52`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::GetActivationFactory(
        Microsoft::WRL::Details *this,
        HSTRING string,
        struct Microsoft::WRL::Details::CreatorMap *a3)
{
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v7; // rbx
  unsigned __int64 v8; // rbp
  __int64 v9; // rax
  unsigned __int16 *v10; // rcx
  __int64 v11; // rax
  unsigned int *v12; // r8
  int v13; // edx
  unsigned int v14; // ebx
  struct IUnknown **v16; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v18; // [rsp+34h] [rbp-64h] BYREF
  __int128 v19; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v20[22]; // [rsp+48h] [rbp-50h]

  *(_QWORD *)a3 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v19 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v20 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v20[14] = *(_QWORD *)L"sId";
    v14 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v19);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v7 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 40LL))(this)
                               + 8);
    v8 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
    if ( (unsigned __int64)v7 >= v8 )
    {
LABEL_11:
      v14 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *v7 )
        {
          v9 = (*(__int64 (**)(void))(*v7)->Data4)();
          v10 = (unsigned __int16 *)StringRawBuffer;
          v11 = v9 - (_QWORD)StringRawBuffer;
          do
          {
            v12 = (unsigned int *)*(unsigned __int16 *)((char *)v10 + v11);
            v13 = *v10 - (_DWORD)v12;
            if ( v13 )
              break;
            ++v10;
          }
          while ( (_DWORD)v12 );
          if ( !v13 )
            break;
        }
        if ( (unsigned __int64)++v7 >= v8 )
          goto LABEL_11;
      }
      v18 = 1;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             this,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v18,
                             v12,
                             *v7,
                             a3,
                             v16);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18000ae44  mov     [rsp+arg_18], rbx
0x18000ae49  push    rbp
0x18000ae4a  push    rsi
0x18000ae4b  push    rdi
0x18000ae4c  push    r14
0x18000ae4e  push    r15
0x18000ae50  sub     rsp, 70h
0x18000ae54  mov     rax, cs:__security_cookie
0x18000ae5b  xor     rax, rsp
0x18000ae5e  mov     [rsp+98h+var_38], rax
0x18000ae63  mov     r14, r8
0x18000ae66  mov     rdi, rdx
0x18000ae69  mov     rsi, rcx
0x18000ae6c  mov     qword ptr [r8], 0
0x18000ae73  mov     [rsp+98h+hasEmbedNull], 0
0x18000ae7b  mov     rcx, rdx; string
0x18000ae7e  call    cs:__imp_WindowsIsStringEmpty
0x18000ae84  test    eax, eax
0x18000ae86  jnz     loc_18000AF52
0x18000ae8c  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x18000ae91  mov     rcx, rdi; string
0x18000ae94  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18000ae9a  test    eax, eax
0x18000ae9c  js      loc_18000AF52
0x18000aea2  cmp     [rsp+98h+hasEmbedNull], 1
0x18000aea7  jz      loc_18000AF52
0x18000aead  xor     edx, edx; length
0x18000aeaf  mov     rcx, rdi; string
0x18000aeb2  call    cs:__imp_WindowsGetStringRawBuffer
0x18000aeb8  mov     r15, rax
0x18000aebb  mov     rcx, [rsi]
0x18000aebe  mov     rax, [rcx+28h]
0x18000aec2  mov     rcx, rsi
0x18000aec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aeca  lea     rbx, [rax+8]
0x18000aece  mov     rcx, [rsi]
0x18000aed1  mov     rax, [rcx+30h]
0x18000aed5  mov     rcx, rsi
0x18000aed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aedd  mov     rbp, rax
0x18000aee0  cmp     rbx, rax
0x18000aee3  jnb     short loc_18000AF1F
0x18000aee5  mov     rax, [rbx]
0x18000aee8  test    rax, rax
0x18000aeeb  jz      short loc_18000AF16
0x18000aeed  mov     rax, [rax+8]
0x18000aef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aef6  mov     rcx, r15
0x18000aef9  sub     rax, r15
0x18000aefc  movzx   edx, word ptr [rcx]
0x18000aeff  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x18000af04  sub     edx, r8d
0x18000af07  jnz     short loc_18000AF12
0x18000af09  add     rcx, 2
0x18000af0d  test    r8d, r8d
0x18000af10  jnz     short loc_18000AEFC
0x18000af12  test    edx, edx
0x18000af14  jz      short loc_18000AF31
0x18000af16  add     rbx, 8
0x18000af1a  cmp     rbx, rbp
0x18000af1d  jb      short loc_18000AEE5
0x18000af1f  mov     rdx, rdi
0x18000af22  mov     ebx, 80040111h
0x18000af27  mov     ecx, ebx
0x18000af29  call    cs:__imp_RoOriginateError
0x18000af2f  jmp     short loc_18000AF90
0x18000af31  mov     [rsp+98h+var_64], 1
0x18000af39  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x18000af3e  mov     r9, [rbx]; struct _GUID *
0x18000af41  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x18000af46  mov     rcx, rsi; this
0x18000af49  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000af4e  mov     ebx, eax
0x18000af50  jmp     short loc_18000AF90
0x18000af52  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18000af59  movups  [rsp+98h+var_60], xmm0
0x18000af5e  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18000af65  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x18000af6a  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x18000af72  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x18000af78  lea     r8, [rsp+98h+var_60]
0x18000af7d  mov     edx, 12h
0x18000af82  mov     ebx, 80070057h
0x18000af87  mov     ecx, ebx
0x18000af89  call    cs:__imp_RoOriginateErrorW
0x18000af8f  nop
0x18000af90  mov     eax, ebx
0x18000af92  mov     rcx, [rsp+98h+var_38]
0x18000af97  xor     rcx, rsp; StackCookie
0x18000af9a  call    __security_check_cookie
0x18000af9f  mov     rbx, [rsp+98h+arg_18]
0x18000afa7  add     rsp, 70h
0x18000afab  pop     r15
0x18000afad  pop     r14
0x18000afaf  pop     rdi
0x18000afb0  pop     rsi
0x18000afb1  pop     rbp
0x18000afb2  retn
```

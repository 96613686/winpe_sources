# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::GetActivationFactory(HSTRING__ *,IActivationFactory * *,ushort const *)

- ea: `0x180014464`
- end: `0x1800145f4`
- name: `?GetActivationFactory@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@PEBG@Z`
- size: `400`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018278`

## callees

- `0x180002880`
- `0x180014464`
- `0x1800145fc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800145c3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800145c3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180014555`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180014555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800144b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800144b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180014498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180014498`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800144d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800144d8`

## string_xrefs

- `0x180014584`: `activatibleClassId`

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
  _OWORD v19[2]; // [rsp+38h] [rbp-60h] BYREF
  int v20; // [rsp+58h] [rbp-40h]
  wchar_t v21; // [rsp+5Ch] [rbp-3Ch]

  *(_QWORD *)a3 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v19[0] = *(_OWORD *)L"activatibleClassId";
    v19[1] = *(_OWORD *)L"bleClassId";
    v20 = *(_DWORD *)L"Id";
    v21 = aActivatiblecla[18];
    v14 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, v19);
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
0x180014464  mov     [rsp+arg_18], rbx
0x180014469  push    rbp
0x18001446a  push    rsi
0x18001446b  push    rdi
0x18001446c  push    r14
0x18001446e  push    r15
0x180014470  sub     rsp, 70h
0x180014474  mov     rax, cs:__security_cookie
0x18001447b  xor     rax, rsp
0x18001447e  mov     [rsp+98h+var_38], rax
0x180014483  mov     r14, r8
0x180014486  mov     rdi, rdx
0x180014489  mov     rsi, rcx
0x18001448c  and     qword ptr [r8], 0
0x180014490  and     [rsp+98h+hasEmbedNull], 0
0x180014495  mov     rcx, rdx; string
0x180014498  call    cs:__imp_WindowsIsStringEmpty
0x18001449f  nop     dword ptr [rax+rax+00h]
0x1800144a4  test    eax, eax
0x1800144a6  jnz     loc_180014584
0x1800144ac  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x1800144b1  mov     rcx, rdi; string
0x1800144b4  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800144bb  nop     dword ptr [rax+rax+00h]
0x1800144c0  test    eax, eax
0x1800144c2  js      loc_180014584
0x1800144c8  cmp     [rsp+98h+hasEmbedNull], 1
0x1800144cd  jz      loc_180014584
0x1800144d3  xor     edx, edx; length
0x1800144d5  mov     rcx, rdi; string
0x1800144d8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800144df  nop     dword ptr [rax+rax+00h]
0x1800144e4  mov     r15, rax
0x1800144e7  mov     rcx, [rsi]
0x1800144ea  mov     rax, [rcx+28h]
0x1800144ee  mov     rcx, rsi
0x1800144f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144f6  lea     rbx, [rax+8]
0x1800144fa  mov     rcx, [rsi]
0x1800144fd  mov     rax, [rcx+30h]
0x180014501  mov     rcx, rsi
0x180014504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014509  mov     rbp, rax
0x18001450c  cmp     rbx, rax
0x18001450f  jnb     short loc_18001454B
0x180014511  mov     rax, [rbx]
0x180014514  test    rax, rax
0x180014517  jz      short loc_180014542
0x180014519  mov     rax, [rax+8]
0x18001451d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014522  mov     rcx, r15
0x180014525  sub     rax, r15
0x180014528  movzx   edx, word ptr [rcx]
0x18001452b  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180014530  sub     edx, r8d
0x180014533  jnz     short loc_18001453E
0x180014535  add     rcx, 2
0x180014539  test    r8d, r8d
0x18001453c  jnz     short loc_180014528
0x18001453e  test    edx, edx
0x180014540  jz      short loc_180014563
0x180014542  add     rbx, 8
0x180014546  cmp     rbx, rbp
0x180014549  jb      short loc_180014511
0x18001454b  mov     rdx, rdi
0x18001454e  mov     ebx, 80040111h
0x180014553  mov     ecx, ebx
0x180014555  call    cs:__imp_RoOriginateError
0x18001455c  nop     dword ptr [rax+rax+00h]
0x180014561  jmp     short loc_1800145D0
0x180014563  mov     [rsp+98h+var_64], 1
0x18001456b  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x180014570  mov     r9, [rbx]; struct _GUID *
0x180014573  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180014578  mov     rcx, rsi; this
0x18001457b  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180014580  mov     ebx, eax
0x180014582  jmp     short loc_1800145D0
0x180014584  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18001458b  movups  [rsp+98h+var_60], xmm0
0x180014590  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180014597  movups  [rsp+98h+var_50], xmm1
0x18001459c  mov     eax, dword ptr cs:aActivatiblecla+20h; "Id"
0x1800145a2  mov     [rsp+98h+var_40], eax
0x1800145a6  movzx   eax, word ptr cs:aActivatiblecla+24h; ""
0x1800145ad  mov     [rsp+98h+var_3C], ax
0x1800145b2  lea     r8, [rsp+98h+var_60]
0x1800145b7  mov     edx, 12h
0x1800145bc  mov     ebx, 80070057h
0x1800145c1  mov     ecx, ebx
0x1800145c3  call    cs:__imp_RoOriginateErrorW
0x1800145ca  nop     dword ptr [rax+rax+00h]
0x1800145cf  nop
0x1800145d0  mov     eax, ebx
0x1800145d2  mov     rcx, [rsp+98h+var_38]
0x1800145d7  xor     rcx, rsp; StackCookie
0x1800145da  call    __security_check_cookie
0x1800145df  mov     rbx, [rsp+98h+arg_18]
0x1800145e7  add     rsp, 70h
0x1800145eb  pop     r15
0x1800145ed  pop     r14
0x1800145ef  pop     rdi
0x1800145f0  pop     rsi
0x1800145f1  pop     rbp
0x1800145f2  retn
```

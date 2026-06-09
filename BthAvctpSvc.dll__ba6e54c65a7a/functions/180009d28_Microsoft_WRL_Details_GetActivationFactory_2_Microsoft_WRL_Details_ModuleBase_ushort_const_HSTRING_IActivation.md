# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180009d28`
- end: `0x180009e9f`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800099d0`

## callees

- `0x180001dd0`
- `0x180009d28`
- `0x18000c308`
- `0x18000d0ec`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009d96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009d96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180009d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180009d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180009d62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180009d62`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180009e76`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180009e76`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009e37`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180009e37`

## string_xrefs

- `0x180009e3f`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<2>(
        Microsoft::WRL::Details *this,
        __int64 a2,
        HSTRING a3,
        RTL_SRWLOCK *a4)
{
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v8; // rbx
  unsigned __int64 v9; // rbp
  unsigned int *v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  int v15; // edx
  unsigned int v17; // ebx
  struct IUnknown **v18; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v20; // [rsp+34h] [rbp-64h] BYREF
  __int128 v21; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v22[22]; // [rsp+48h] [rbp-50h]

  a4->Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(a3) || WindowsStringHasEmbeddedNull(a3, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v21 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v22 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v22[14] = *(_QWORD *)L"sId";
    v17 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v21);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v8 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 40LL))(this)
                               + 8);
    v9 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
    while ( (unsigned __int64)v8 < v9 )
    {
      if ( *v8
        && Microsoft::WRL::Details::IsServerNameEqual((Microsoft::WRL::Details *)*v8, 0, (const unsigned __int16 *)v10) )
      {
        v12 = (*(__int64 (**)(void))(v11 + 8))();
        v13 = (unsigned __int16 *)StringRawBuffer;
        v14 = v12 - (_QWORD)StringRawBuffer;
        do
        {
          v10 = (unsigned int *)*(unsigned __int16 *)((char *)v13 + v14);
          v15 = *v13 - (_DWORD)v10;
          if ( v15 )
            break;
          ++v13;
        }
        while ( (_DWORD)v10 );
        if ( !v15 )
        {
          v20 = 2;
          return Microsoft::WRL::Details::GetCacheEntry(
                   this,
                   (struct Microsoft::WRL::Details::ModuleBase *)&v20,
                   v10,
                   *v8,
                   a4,
                   v18);
        }
      }
      ++v8;
    }
    v17 = -2147221231;
    RoOriginateError(2147746065LL, a3);
  }
  return v17;
}

```

## disassembly

```asm
0x180009d28  mov     [rsp+arg_8], rbx
0x180009d2d  push    rbp
0x180009d2e  push    rsi
0x180009d2f  push    rdi
0x180009d30  push    r14
0x180009d32  push    r15
0x180009d34  sub     rsp, 70h
0x180009d38  mov     rax, cs:__security_cookie
0x180009d3f  xor     rax, rsp
0x180009d42  mov     [rsp+98h+var_38], rax
0x180009d47  mov     r14, r9
0x180009d4a  mov     rdi, r8
0x180009d4d  mov     rsi, rcx
0x180009d50  mov     qword ptr [r9], 0
0x180009d57  mov     [rsp+98h+hasEmbedNull], 0
0x180009d5f  mov     rcx, r8; string
0x180009d62  call    cs:__imp_WindowsIsStringEmpty
0x180009d68  test    eax, eax
0x180009d6a  jnz     loc_180009E3F
0x180009d70  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180009d75  mov     rcx, rdi; string
0x180009d78  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180009d7e  test    eax, eax
0x180009d80  js      loc_180009E3F
0x180009d86  cmp     [rsp+98h+hasEmbedNull], 1
0x180009d8b  jz      loc_180009E3F
0x180009d91  xor     edx, edx; length
0x180009d93  mov     rcx, rdi; string
0x180009d96  call    cs:__imp_WindowsGetStringRawBuffer
0x180009d9c  mov     r15, rax
0x180009d9f  mov     rcx, [rsi]
0x180009da2  mov     rax, [rcx+28h]
0x180009da6  mov     rcx, rsi
0x180009da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dae  lea     rbx, [rax+8]
0x180009db2  mov     rcx, [rsi]
0x180009db5  mov     rax, [rcx+30h]
0x180009db9  mov     rcx, rsi
0x180009dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc1  mov     rbp, rax
0x180009dc4  cmp     rbx, rbp
0x180009dc7  jnb     short loc_180009E2D
0x180009dc9  mov     r9, [rbx]
0x180009dcc  test    r9, r9
0x180009dcf  jz      short loc_180009E08
0x180009dd1  xor     edx, edx; struct Microsoft::WRL::Details::CreatorMap *
0x180009dd3  mov     rcx, r9; this
0x180009dd6  call    ?IsServerNameEqual@Details@WRL@Microsoft@@YA_NPEBUCreatorMap@123@PEBG@Z; Microsoft::WRL::Details::IsServerNameEqual(Microsoft::WRL::Details::CreatorMap const *,ushort const *)
0x180009ddb  test    al, al
0x180009ddd  jz      short loc_180009E08
0x180009ddf  mov     rax, [r9+8]
0x180009de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009de8  mov     rcx, r15
0x180009deb  sub     rax, r15
0x180009dee  movzx   edx, word ptr [rcx]
0x180009df1  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180009df6  sub     edx, r8d
0x180009df9  jnz     short loc_180009E04
0x180009dfb  add     rcx, 2
0x180009dff  test    r8d, r8d
0x180009e02  jnz     short loc_180009DEE
0x180009e04  test    edx, edx
0x180009e06  jz      short loc_180009E0E
0x180009e08  add     rbx, 8
0x180009e0c  jmp     short loc_180009DC4
0x180009e0e  mov     [rsp+98h+var_64], 2
0x180009e16  mov     [rsp+98h+SRWLock], r14; SRWLock
0x180009e1b  mov     r9, [rbx]; struct _GUID *
0x180009e1e  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180009e23  mov     rcx, rsi; this
0x180009e26  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180009e2b  jmp     short loc_180009E7E
0x180009e2d  mov     rdx, rdi
0x180009e30  mov     ebx, 80040111h
0x180009e35  mov     ecx, ebx
0x180009e37  call    cs:__imp_RoOriginateError
0x180009e3d  jmp     short loc_180009E7C
0x180009e3f  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180009e46  movups  [rsp+98h+var_60], xmm0
0x180009e4b  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180009e52  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180009e57  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180009e5f  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180009e65  lea     r8, [rsp+98h+var_60]
0x180009e6a  mov     edx, 12h
0x180009e6f  mov     ebx, 80070057h
0x180009e74  mov     ecx, ebx
0x180009e76  call    cs:__imp_RoOriginateErrorW
0x180009e7c  mov     eax, ebx
0x180009e7e  mov     rcx, [rsp+98h+var_38]
0x180009e83  xor     rcx, rsp; StackCookie
0x180009e86  call    __security_check_cookie
0x180009e8b  mov     rbx, [rsp+98h+arg_8]
0x180009e93  add     rsp, 70h
0x180009e97  pop     r15
0x180009e99  pop     r14
0x180009e9b  pop     rdi
0x180009e9c  pop     rsi
0x180009e9d  pop     rbp
0x180009e9e  retn
```

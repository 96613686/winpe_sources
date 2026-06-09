# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180004c28`
- end: `0x180004d9f`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004a90`

## callees

- `0x180002d40`
- `0x180004c28`
- `0x180009f84`
- `0x18000b5e4`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180004c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180004c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180004c78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180004c78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004c96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004c96`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180004d76`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180004d76`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004d37`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004d37`

## string_xrefs

- `0x180004d3f`: `activatibleClassId`

## pseudocode

```c
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
0x180004c28  mov     [rsp+arg_8], rbx
0x180004c2d  push    rbp
0x180004c2e  push    rsi
0x180004c2f  push    rdi
0x180004c30  push    r14
0x180004c32  push    r15
0x180004c34  sub     rsp, 70h
0x180004c38  mov     rax, cs:__security_cookie
0x180004c3f  xor     rax, rsp
0x180004c42  mov     [rsp+98h+var_38], rax
0x180004c47  mov     r14, r9
0x180004c4a  mov     rdi, r8
0x180004c4d  mov     rsi, rcx
0x180004c50  mov     qword ptr [r9], 0
0x180004c57  mov     [rsp+98h+hasEmbedNull], 0
0x180004c5f  mov     rcx, r8; string
0x180004c62  call    cs:__imp_WindowsIsStringEmpty
0x180004c68  test    eax, eax
0x180004c6a  jnz     loc_180004D3F
0x180004c70  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180004c75  mov     rcx, rdi; string
0x180004c78  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180004c7e  test    eax, eax
0x180004c80  js      loc_180004D3F
0x180004c86  cmp     [rsp+98h+hasEmbedNull], 1
0x180004c8b  jz      loc_180004D3F
0x180004c91  xor     edx, edx; length
0x180004c93  mov     rcx, rdi; string
0x180004c96  call    cs:__imp_WindowsGetStringRawBuffer
0x180004c9c  mov     r15, rax
0x180004c9f  mov     rcx, [rsi]
0x180004ca2  mov     rax, [rcx+28h]
0x180004ca6  mov     rcx, rsi
0x180004ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cae  lea     rbx, [rax+8]
0x180004cb2  mov     rcx, [rsi]
0x180004cb5  mov     rax, [rcx+30h]
0x180004cb9  mov     rcx, rsi
0x180004cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc1  mov     rbp, rax
0x180004cc4  cmp     rbx, rbp
0x180004cc7  jnb     short loc_180004D2D
0x180004cc9  mov     r9, [rbx]
0x180004ccc  test    r9, r9
0x180004ccf  jz      short loc_180004D08
0x180004cd1  xor     edx, edx; struct Microsoft::WRL::Details::CreatorMap *
0x180004cd3  mov     rcx, r9; this
0x180004cd6  call    ?IsServerNameEqual@Details@WRL@Microsoft@@YA_NPEBUCreatorMap@123@PEBG@Z; Microsoft::WRL::Details::IsServerNameEqual(Microsoft::WRL::Details::CreatorMap const *,ushort const *)
0x180004cdb  test    al, al
0x180004cdd  jz      short loc_180004D08
0x180004cdf  mov     rax, [r9+8]
0x180004ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce8  mov     rcx, r15
0x180004ceb  sub     rax, r15
0x180004cee  movzx   edx, word ptr [rcx]
0x180004cf1  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180004cf6  sub     edx, r8d
0x180004cf9  jnz     short loc_180004D04
0x180004cfb  add     rcx, 2
0x180004cff  test    r8d, r8d
0x180004d02  jnz     short loc_180004CEE
0x180004d04  test    edx, edx
0x180004d06  jz      short loc_180004D0E
0x180004d08  add     rbx, 8
0x180004d0c  jmp     short loc_180004CC4
0x180004d0e  mov     [rsp+98h+var_64], 2
0x180004d16  mov     [rsp+98h+SRWLock], r14; SRWLock
0x180004d1b  mov     r9, [rbx]; struct _GUID *
0x180004d1e  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180004d23  mov     rcx, rsi; this
0x180004d26  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180004d2b  jmp     short loc_180004D7E
0x180004d2d  mov     rdx, rdi
0x180004d30  mov     ebx, 80040111h
0x180004d35  mov     ecx, ebx
0x180004d37  call    cs:__imp_RoOriginateError
0x180004d3d  jmp     short loc_180004D7C
0x180004d3f  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180004d46  movups  [rsp+98h+var_60], xmm0
0x180004d4b  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180004d52  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180004d57  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180004d5f  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180004d65  lea     r8, [rsp+98h+var_60]
0x180004d6a  mov     edx, 12h
0x180004d6f  mov     ebx, 80070057h
0x180004d74  mov     ecx, ebx
0x180004d76  call    cs:__imp_RoOriginateErrorW
0x180004d7c  mov     eax, ebx
0x180004d7e  mov     rcx, [rsp+98h+var_38]
0x180004d83  xor     rcx, rsp; StackCookie
0x180004d86  call    __security_check_cookie
0x180004d8b  mov     rbx, [rsp+98h+arg_8]
0x180004d93  add     rsp, 70h
0x180004d97  pop     r15
0x180004d99  pop     r14
0x180004d9b  pop     rdi
0x180004d9c  pop     rsi
0x180004d9d  pop     rbp
0x180004d9e  retn
```

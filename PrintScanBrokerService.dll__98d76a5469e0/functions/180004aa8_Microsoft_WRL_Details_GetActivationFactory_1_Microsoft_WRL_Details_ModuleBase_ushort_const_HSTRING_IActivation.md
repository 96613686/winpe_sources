# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180004aa8`
- end: `0x180004c1f`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011be8`

## callees

- `0x180002d40`
- `0x180004aa8`
- `0x180009f84`
- `0x18000b5e4`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180004ae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180004ae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180004af8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180004af8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004b16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004b16`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180004bf6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180004bf6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004bb7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004bb7`

## string_xrefs

- `0x180004bbf`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<1>(
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
          v20 = 1;
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
0x180004aa8  mov     [rsp+arg_8], rbx
0x180004aad  push    rbp
0x180004aae  push    rsi
0x180004aaf  push    rdi
0x180004ab0  push    r14
0x180004ab2  push    r15
0x180004ab4  sub     rsp, 70h
0x180004ab8  mov     rax, cs:__security_cookie
0x180004abf  xor     rax, rsp
0x180004ac2  mov     [rsp+98h+var_38], rax
0x180004ac7  mov     r14, r9
0x180004aca  mov     rdi, r8
0x180004acd  mov     rsi, rcx
0x180004ad0  mov     qword ptr [r9], 0
0x180004ad7  mov     [rsp+98h+hasEmbedNull], 0
0x180004adf  mov     rcx, r8; string
0x180004ae2  call    cs:__imp_WindowsIsStringEmpty
0x180004ae8  test    eax, eax
0x180004aea  jnz     loc_180004BBF
0x180004af0  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180004af5  mov     rcx, rdi; string
0x180004af8  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180004afe  test    eax, eax
0x180004b00  js      loc_180004BBF
0x180004b06  cmp     [rsp+98h+hasEmbedNull], 1
0x180004b0b  jz      loc_180004BBF
0x180004b11  xor     edx, edx; length
0x180004b13  mov     rcx, rdi; string
0x180004b16  call    cs:__imp_WindowsGetStringRawBuffer
0x180004b1c  mov     r15, rax
0x180004b1f  mov     rcx, [rsi]
0x180004b22  mov     rax, [rcx+28h]
0x180004b26  mov     rcx, rsi
0x180004b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b2e  lea     rbx, [rax+8]
0x180004b32  mov     rcx, [rsi]
0x180004b35  mov     rax, [rcx+30h]
0x180004b39  mov     rcx, rsi
0x180004b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b41  mov     rbp, rax
0x180004b44  cmp     rbx, rbp
0x180004b47  jnb     short loc_180004BAD
0x180004b49  mov     r9, [rbx]
0x180004b4c  test    r9, r9
0x180004b4f  jz      short loc_180004B88
0x180004b51  xor     edx, edx; struct Microsoft::WRL::Details::CreatorMap *
0x180004b53  mov     rcx, r9; this
0x180004b56  call    ?IsServerNameEqual@Details@WRL@Microsoft@@YA_NPEBUCreatorMap@123@PEBG@Z; Microsoft::WRL::Details::IsServerNameEqual(Microsoft::WRL::Details::CreatorMap const *,ushort const *)
0x180004b5b  test    al, al
0x180004b5d  jz      short loc_180004B88
0x180004b5f  mov     rax, [r9+8]
0x180004b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b68  mov     rcx, r15
0x180004b6b  sub     rax, r15
0x180004b6e  movzx   edx, word ptr [rcx]
0x180004b71  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180004b76  sub     edx, r8d
0x180004b79  jnz     short loc_180004B84
0x180004b7b  add     rcx, 2
0x180004b7f  test    r8d, r8d
0x180004b82  jnz     short loc_180004B6E
0x180004b84  test    edx, edx
0x180004b86  jz      short loc_180004B8E
0x180004b88  add     rbx, 8
0x180004b8c  jmp     short loc_180004B44
0x180004b8e  mov     [rsp+98h+var_64], 1
0x180004b96  mov     [rsp+98h+SRWLock], r14; SRWLock
0x180004b9b  mov     r9, [rbx]; struct _GUID *
0x180004b9e  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180004ba3  mov     rcx, rsi; this
0x180004ba6  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180004bab  jmp     short loc_180004BFE
0x180004bad  mov     rdx, rdi
0x180004bb0  mov     ebx, 80040111h
0x180004bb5  mov     ecx, ebx
0x180004bb7  call    cs:__imp_RoOriginateError
0x180004bbd  jmp     short loc_180004BFC
0x180004bbf  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180004bc6  movups  [rsp+98h+var_60], xmm0
0x180004bcb  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180004bd2  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180004bd7  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180004bdf  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180004be5  lea     r8, [rsp+98h+var_60]
0x180004bea  mov     edx, 12h
0x180004bef  mov     ebx, 80070057h
0x180004bf4  mov     ecx, ebx
0x180004bf6  call    cs:__imp_RoOriginateErrorW
0x180004bfc  mov     eax, ebx
0x180004bfe  mov     rcx, [rsp+98h+var_38]
0x180004c03  xor     rcx, rsp; StackCookie
0x180004c06  call    __security_check_cookie
0x180004c0b  mov     rbx, [rsp+98h+arg_8]
0x180004c13  add     rsp, 70h
0x180004c17  pop     r15
0x180004c19  pop     r14
0x180004c1b  pop     rdi
0x180004c1c  pop     rsi
0x180004c1d  pop     rbp
0x180004c1e  retn
```

# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x140005c28`
- end: `0x140005d91`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004f90`

## callees

- `0x140002d30`
- `0x140005c28`
- `0x14000b3c4`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x140005c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x140005c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x140005c78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x140005c78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140005c96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140005c96`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140005d29`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140005d29`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x140005d68`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x140005d68`

## string_xrefs

- `0x140005d31`: `activatibleClassId`

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
  __int64 v10; // rax
  unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  unsigned int *v13; // r8
  int v14; // edx
  unsigned int v16; // ebx
  struct IUnknown **v17; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v19; // [rsp+34h] [rbp-64h] BYREF
  __int128 v20; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v21[22]; // [rsp+48h] [rbp-50h]

  a4->Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(a3) || WindowsStringHasEmbeddedNull(a3, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v20 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v21 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v21[14] = *(_QWORD *)L"sId";
    v16 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v20);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v8 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 40LL))(this)
                               + 8);
    v9 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
    while ( (unsigned __int64)v8 < v9 )
    {
      if ( *v8 )
      {
        v10 = (*(__int64 (**)(void))(*v8)->Data4)();
        v11 = (unsigned __int16 *)StringRawBuffer;
        v12 = v10 - (_QWORD)StringRawBuffer;
        do
        {
          v13 = (unsigned int *)*(unsigned __int16 *)((char *)v11 + v12);
          v14 = *v11 - (_DWORD)v13;
          if ( v14 )
            break;
          ++v11;
        }
        while ( (_DWORD)v13 );
        if ( !v14 )
        {
          v19 = 2;
          return Microsoft::WRL::Details::GetCacheEntry(
                   this,
                   (struct Microsoft::WRL::Details::ModuleBase *)&v19,
                   v13,
                   *v8,
                   a4,
                   v17);
        }
      }
      ++v8;
    }
    v16 = -2147221231;
    RoOriginateError(2147746065LL, a3);
  }
  return v16;
}

```

## disassembly

```asm
0x140005c28  mov     [rsp+arg_8], rbx
0x140005c2d  push    rbp
0x140005c2e  push    rsi
0x140005c2f  push    rdi
0x140005c30  push    r14
0x140005c32  push    r15
0x140005c34  sub     rsp, 70h
0x140005c38  mov     rax, cs:__security_cookie
0x140005c3f  xor     rax, rsp
0x140005c42  mov     [rsp+98h+var_38], rax
0x140005c47  mov     r14, r9
0x140005c4a  mov     rdi, r8
0x140005c4d  mov     rsi, rcx
0x140005c50  mov     qword ptr [r9], 0
0x140005c57  mov     [rsp+98h+hasEmbedNull], 0
0x140005c5f  mov     rcx, r8; string
0x140005c62  call    cs:__imp_WindowsIsStringEmpty
0x140005c68  test    eax, eax
0x140005c6a  jnz     loc_140005D31
0x140005c70  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x140005c75  mov     rcx, rdi; string
0x140005c78  call    cs:__imp_WindowsStringHasEmbeddedNull
0x140005c7e  test    eax, eax
0x140005c80  js      loc_140005D31
0x140005c86  cmp     [rsp+98h+hasEmbedNull], 1
0x140005c8b  jz      loc_140005D31
0x140005c91  xor     edx, edx; length
0x140005c93  mov     rcx, rdi; string
0x140005c96  call    cs:__imp_WindowsGetStringRawBuffer
0x140005c9c  mov     r15, rax
0x140005c9f  mov     rcx, [rsi]
0x140005ca2  mov     rax, [rcx+28h]
0x140005ca6  mov     rcx, rsi
0x140005ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cae  lea     rbx, [rax+8]
0x140005cb2  mov     rcx, [rsi]
0x140005cb5  mov     rax, [rcx+30h]
0x140005cb9  mov     rcx, rsi
0x140005cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cc1  mov     rbp, rax
0x140005cc4  cmp     rbx, rbp
0x140005cc7  jnb     short loc_140005D1F
0x140005cc9  mov     rax, [rbx]
0x140005ccc  test    rax, rax
0x140005ccf  jz      short loc_140005CFA
0x140005cd1  mov     rax, [rax+8]
0x140005cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cda  mov     rcx, r15
0x140005cdd  sub     rax, r15
0x140005ce0  movzx   edx, word ptr [rcx]
0x140005ce3  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x140005ce8  sub     edx, r8d
0x140005ceb  jnz     short loc_140005CF6
0x140005ced  add     rcx, 2
0x140005cf1  test    r8d, r8d
0x140005cf4  jnz     short loc_140005CE0
0x140005cf6  test    edx, edx
0x140005cf8  jz      short loc_140005D00
0x140005cfa  add     rbx, 8
0x140005cfe  jmp     short loc_140005CC4
0x140005d00  mov     [rsp+98h+var_64], 2
0x140005d08  mov     [rsp+98h+SRWLock], r14; SRWLock
0x140005d0d  mov     r9, [rbx]; struct _GUID *
0x140005d10  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x140005d15  mov     rcx, rsi; this
0x140005d18  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x140005d1d  jmp     short loc_140005D70
0x140005d1f  mov     rdx, rdi
0x140005d22  mov     ebx, 80040111h
0x140005d27  mov     ecx, ebx
0x140005d29  call    cs:__imp_RoOriginateError
0x140005d2f  jmp     short loc_140005D6E
0x140005d31  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x140005d38  movups  [rsp+98h+var_60], xmm0
0x140005d3d  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x140005d44  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x140005d49  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x140005d51  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x140005d57  lea     r8, [rsp+98h+var_60]
0x140005d5c  mov     edx, 12h
0x140005d61  mov     ebx, 80070057h
0x140005d66  mov     ecx, ebx
0x140005d68  call    cs:__imp_RoOriginateErrorW
0x140005d6e  mov     eax, ebx
0x140005d70  mov     rcx, [rsp+98h+var_38]
0x140005d75  xor     rcx, rsp; StackCookie
0x140005d78  call    __security_check_cookie
0x140005d7d  mov     rbx, [rsp+98h+arg_8]
0x140005d85  add     rsp, 70h
0x140005d89  pop     r15
0x140005d8b  pop     r14
0x140005d8d  pop     rdi
0x140005d8e  pop     rsi
0x140005d8f  pop     rbp
0x140005d90  retn
```

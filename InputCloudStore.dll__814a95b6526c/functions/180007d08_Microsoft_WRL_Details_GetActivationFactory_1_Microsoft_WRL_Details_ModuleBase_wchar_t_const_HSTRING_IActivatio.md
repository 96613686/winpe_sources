# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,wchar_t const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180007d08`
- end: `0x180007e78`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEB_WPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009090`

## callees

- `0x180003560`
- `0x180007d08`
- `0x180008814`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180007e4f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180007e4f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180007e10`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180007e10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180007d58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180007d58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180007d42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180007d42`

## string_xrefs

- `0x180007e18`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<1>(
        Microsoft::WRL::Details *this,
        __int64 a2,
        HSTRING a3,
        _QWORD *a4)
{
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v8; // rbx
  unsigned __int64 v9; // rbp
  __int64 v10; // rax
  unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  int v13; // r8d
  int v14; // edx
  unsigned int v16; // ebx
  struct IUnknown **v17; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v19; // [rsp+34h] [rbp-64h] BYREF
  __int128 v20; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v21[22]; // [rsp+48h] [rbp-50h]

  *a4 = 0;
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
          v13 = *(unsigned __int16 *)((char *)v11 + v12);
          v14 = *v11 - v13;
          if ( v14 )
            break;
          ++v11;
        }
        while ( v13 );
        if ( !v14 )
        {
          v19 = 1;
          return Microsoft::WRL::Details::GetCacheEntry(
                   this,
                   (struct Microsoft::WRL::Details::ModuleBase *)&v19,
                   &GUID_00000035_0000_0000_c000_000000000046.Data1,
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
0x180007d08  mov     [rsp+arg_8], rbx
0x180007d0d  push    rbp
0x180007d0e  push    rsi
0x180007d0f  push    rdi
0x180007d10  push    r14
0x180007d12  push    r15
0x180007d14  sub     rsp, 70h
0x180007d18  mov     rax, cs:__security_cookie
0x180007d1f  xor     rax, rsp
0x180007d22  mov     [rsp+98h+var_38], rax
0x180007d27  mov     r14, r9
0x180007d2a  mov     rdi, r8
0x180007d2d  mov     rsi, rcx
0x180007d30  mov     qword ptr [r9], 0
0x180007d37  mov     [rsp+98h+hasEmbedNull], 0
0x180007d3f  mov     rcx, r8; string
0x180007d42  call    cs:__imp_WindowsIsStringEmpty
0x180007d48  test    eax, eax
0x180007d4a  jnz     loc_180007E18
0x180007d50  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180007d55  mov     rcx, rdi; string
0x180007d58  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180007d5e  test    eax, eax
0x180007d60  js      loc_180007E18
0x180007d66  cmp     [rsp+98h+hasEmbedNull], 1
0x180007d6b  jz      loc_180007E18
0x180007d71  xor     edx, edx; length
0x180007d73  mov     rcx, rdi; string
0x180007d76  call    cs:__imp_WindowsGetStringRawBuffer
0x180007d7c  mov     r15, rax
0x180007d7f  mov     rcx, [rsi]
0x180007d82  mov     rax, [rcx+28h]
0x180007d86  mov     rcx, rsi
0x180007d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d8e  lea     rbx, [rax+8]
0x180007d92  mov     rcx, [rsi]
0x180007d95  mov     rax, [rcx+30h]
0x180007d99  mov     rcx, rsi
0x180007d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da1  mov     rbp, rax
0x180007da4  cmp     rbx, rbp
0x180007da7  jnb     short loc_180007E06
0x180007da9  mov     rax, [rbx]
0x180007dac  test    rax, rax
0x180007daf  jz      short loc_180007DDA
0x180007db1  mov     rax, [rax+8]
0x180007db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dba  mov     rcx, r15
0x180007dbd  sub     rax, r15
0x180007dc0  movzx   edx, word ptr [rcx]
0x180007dc3  movzx   r8d, word ptr [rcx+rax]
0x180007dc8  sub     edx, r8d
0x180007dcb  jnz     short loc_180007DD6
0x180007dcd  add     rcx, 2
0x180007dd1  test    r8d, r8d
0x180007dd4  jnz     short loc_180007DC0
0x180007dd6  test    edx, edx
0x180007dd8  jz      short loc_180007DE0
0x180007dda  add     rbx, 8
0x180007dde  jmp     short loc_180007DA4
0x180007de0  mov     [rsp+98h+var_64], 1
0x180007de8  mov     [rsp+98h+Ptr], r14; Ptr
0x180007ded  mov     r9, [rbx]; struct _GUID *
0x180007df0  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180007df7  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180007dfc  mov     rcx, rsi; this
0x180007dff  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180007e04  jmp     short loc_180007E57
0x180007e06  mov     rdx, rdi
0x180007e09  mov     ebx, 80040111h
0x180007e0e  mov     ecx, ebx
0x180007e10  call    cs:__imp_RoOriginateError
0x180007e16  jmp     short loc_180007E55
0x180007e18  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180007e1f  movups  [rsp+98h+var_60], xmm0
0x180007e24  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180007e2b  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180007e30  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180007e38  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180007e3e  lea     r8, [rsp+98h+var_60]
0x180007e43  mov     edx, 12h
0x180007e48  mov     ebx, 80070057h
0x180007e4d  mov     ecx, ebx
0x180007e4f  call    cs:__imp_RoOriginateErrorW
0x180007e55  mov     eax, ebx
0x180007e57  mov     rcx, [rsp+98h+var_38]
0x180007e5c  xor     rcx, rsp; StackCookie
0x180007e5f  call    __security_check_cookie
0x180007e64  mov     rbx, [rsp+98h+arg_8]
0x180007e6c  add     rsp, 70h
0x180007e70  pop     r15
0x180007e72  pop     r14
0x180007e74  pop     rdi
0x180007e75  pop     rsi
0x180007e76  pop     rbp
0x180007e77  retn
```

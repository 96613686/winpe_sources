# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180003eb0`
- end: `0x180004020`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009bb4`

## callees

- `0x180002dc0`
- `0x180003eb0`
- `0x1800064a4`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003f1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003f1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003eea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180003f00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180003f00`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003fb8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003fb8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180003ff7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180003ff7`

## string_xrefs

- `0x180003fc0`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180003eb0  mov     [rsp+arg_8], rbx
0x180003eb5  push    rbp
0x180003eb6  push    rsi
0x180003eb7  push    rdi
0x180003eb8  push    r14
0x180003eba  push    r15
0x180003ebc  sub     rsp, 70h
0x180003ec0  mov     rax, cs:__security_cookie
0x180003ec7  xor     rax, rsp
0x180003eca  mov     [rsp+98h+var_38], rax
0x180003ecf  mov     r14, r9
0x180003ed2  mov     rdi, r8
0x180003ed5  mov     rsi, rcx
0x180003ed8  mov     qword ptr [r9], 0
0x180003edf  mov     [rsp+98h+hasEmbedNull], 0
0x180003ee7  mov     rcx, r8; string
0x180003eea  call    cs:__imp_WindowsIsStringEmpty
0x180003ef0  test    eax, eax
0x180003ef2  jnz     loc_180003FC0
0x180003ef8  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180003efd  mov     rcx, rdi; string
0x180003f00  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180003f06  test    eax, eax
0x180003f08  js      loc_180003FC0
0x180003f0e  cmp     [rsp+98h+hasEmbedNull], 1
0x180003f13  jz      loc_180003FC0
0x180003f19  xor     edx, edx; length
0x180003f1b  mov     rcx, rdi; string
0x180003f1e  call    cs:__imp_WindowsGetStringRawBuffer
0x180003f24  mov     r15, rax
0x180003f27  mov     rcx, [rsi]
0x180003f2a  mov     rax, [rcx+28h]
0x180003f2e  mov     rcx, rsi
0x180003f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f36  lea     rbx, [rax+8]
0x180003f3a  mov     rcx, [rsi]
0x180003f3d  mov     rax, [rcx+30h]
0x180003f41  mov     rcx, rsi
0x180003f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f49  mov     rbp, rax
0x180003f4c  cmp     rbx, rbp
0x180003f4f  jnb     short loc_180003FAE
0x180003f51  mov     rax, [rbx]
0x180003f54  test    rax, rax
0x180003f57  jz      short loc_180003F82
0x180003f59  mov     rax, [rax+8]
0x180003f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f62  mov     rcx, r15
0x180003f65  sub     rax, r15
0x180003f68  movzx   edx, word ptr [rcx]
0x180003f6b  movzx   r8d, word ptr [rcx+rax]
0x180003f70  sub     edx, r8d
0x180003f73  jnz     short loc_180003F7E
0x180003f75  add     rcx, 2
0x180003f79  test    r8d, r8d
0x180003f7c  jnz     short loc_180003F68
0x180003f7e  test    edx, edx
0x180003f80  jz      short loc_180003F88
0x180003f82  add     rbx, 8
0x180003f86  jmp     short loc_180003F4C
0x180003f88  mov     [rsp+98h+var_64], 1
0x180003f90  mov     [rsp+98h+Ptr], r14; Ptr
0x180003f95  mov     r9, [rbx]; struct _GUID *
0x180003f98  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180003f9f  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180003fa4  mov     rcx, rsi; this
0x180003fa7  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180003fac  jmp     short loc_180003FFF
0x180003fae  mov     rdx, rdi
0x180003fb1  mov     ebx, 80040111h
0x180003fb6  mov     ecx, ebx
0x180003fb8  call    cs:__imp_RoOriginateError
0x180003fbe  jmp     short loc_180003FFD
0x180003fc0  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180003fc7  movups  [rsp+98h+var_60], xmm0
0x180003fcc  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180003fd3  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180003fd8  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180003fe0  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180003fe6  lea     r8, [rsp+98h+var_60]
0x180003feb  mov     edx, 12h
0x180003ff0  mov     ebx, 80070057h
0x180003ff5  mov     ecx, ebx
0x180003ff7  call    cs:__imp_RoOriginateErrorW
0x180003ffd  mov     eax, ebx
0x180003fff  mov     rcx, [rsp+98h+var_38]
0x180004004  xor     rcx, rsp; StackCookie
0x180004007  call    __security_check_cookie
0x18000400c  mov     rbx, [rsp+98h+arg_8]
0x180004014  add     rsp, 70h
0x180004018  pop     r15
0x18000401a  pop     r14
0x18000401c  pop     rdi
0x18000401d  pop     rsi
0x18000401e  pop     rbp
0x18000401f  retn
```

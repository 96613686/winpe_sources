# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,wchar_t const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180019888`
- end: `0x1800199f1`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEB_WPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019870`

## callees

- `0x18000d2a0`
- `0x180019888`
- `0x18001e7ec`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800199c8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800199c8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180019989`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180019989`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800198f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800198f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800198d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800198d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800198c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800198c2`

## string_xrefs

- `0x180019991`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<2>(
        Microsoft::WRL::Details *this,
        __int64 a2,
        HSTRING a3,
        const struct Microsoft::WRL::Details::CreatorMap *a4)
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

  *(_QWORD *)a4 = 0;
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
0x180019888  mov     [rsp+arg_8], rbx
0x18001988d  push    rbp
0x18001988e  push    rsi
0x18001988f  push    rdi
0x180019890  push    r14
0x180019892  push    r15
0x180019894  sub     rsp, 70h
0x180019898  mov     rax, cs:__security_cookie
0x18001989f  xor     rax, rsp
0x1800198a2  mov     [rsp+98h+var_38], rax
0x1800198a7  mov     r14, r9
0x1800198aa  mov     rdi, r8
0x1800198ad  mov     rsi, rcx
0x1800198b0  mov     qword ptr [r9], 0
0x1800198b7  mov     [rsp+98h+hasEmbedNull], 0
0x1800198bf  mov     rcx, r8; string
0x1800198c2  call    cs:__imp_WindowsIsStringEmpty
0x1800198c8  test    eax, eax
0x1800198ca  jnz     loc_180019991
0x1800198d0  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x1800198d5  mov     rcx, rdi; string
0x1800198d8  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800198de  test    eax, eax
0x1800198e0  js      loc_180019991
0x1800198e6  cmp     [rsp+98h+hasEmbedNull], 1
0x1800198eb  jz      loc_180019991
0x1800198f1  xor     edx, edx; length
0x1800198f3  mov     rcx, rdi; string
0x1800198f6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800198fc  mov     r15, rax
0x1800198ff  mov     rcx, [rsi]
0x180019902  mov     rax, [rcx+28h]
0x180019906  mov     rcx, rsi
0x180019909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001990e  lea     rbx, [rax+8]
0x180019912  mov     rcx, [rsi]
0x180019915  mov     rax, [rcx+30h]
0x180019919  mov     rcx, rsi
0x18001991c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019921  mov     rbp, rax
0x180019924  cmp     rbx, rbp
0x180019927  jnb     short loc_18001997F
0x180019929  mov     rax, [rbx]
0x18001992c  test    rax, rax
0x18001992f  jz      short loc_18001995A
0x180019931  mov     rax, [rax+8]
0x180019935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001993a  mov     rcx, r15
0x18001993d  sub     rax, r15
0x180019940  movzx   edx, word ptr [rcx]
0x180019943  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180019948  sub     edx, r8d
0x18001994b  jnz     short loc_180019956
0x18001994d  add     rcx, 2
0x180019951  test    r8d, r8d
0x180019954  jnz     short loc_180019940
0x180019956  test    edx, edx
0x180019958  jz      short loc_180019960
0x18001995a  add     rbx, 8
0x18001995e  jmp     short loc_180019924
0x180019960  mov     [rsp+98h+var_64], 2
0x180019968  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x18001996d  mov     r9, [rbx]; struct _GUID *
0x180019970  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180019975  mov     rcx, rsi; this
0x180019978  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18001997d  jmp     short loc_1800199D0
0x18001997f  mov     rdx, rdi
0x180019982  mov     ebx, 80040111h
0x180019987  mov     ecx, ebx
0x180019989  call    cs:__imp_RoOriginateError
0x18001998f  jmp     short loc_1800199CE
0x180019991  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180019998  movups  [rsp+98h+var_60], xmm0
0x18001999d  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x1800199a4  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x1800199a9  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x1800199b1  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x1800199b7  lea     r8, [rsp+98h+var_60]
0x1800199bc  mov     edx, 12h
0x1800199c1  mov     ebx, 80070057h
0x1800199c6  mov     ecx, ebx
0x1800199c8  call    cs:__imp_RoOriginateErrorW
0x1800199ce  mov     eax, ebx
0x1800199d0  mov     rcx, [rsp+98h+var_38]
0x1800199d5  xor     rcx, rsp; StackCookie
0x1800199d8  call    __security_check_cookie
0x1800199dd  mov     rbx, [rsp+98h+arg_8]
0x1800199e5  add     rsp, 70h
0x1800199e9  pop     r15
0x1800199eb  pop     r14
0x1800199ed  pop     rdi
0x1800199ee  pop     rsi
0x1800199ef  pop     rbp
0x1800199f0  retn
```

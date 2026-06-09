# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x140006478`
- end: `0x1400065e1`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400062d0`

## callees

- `0x140006478`
- `0x140007cf4`
- `0x1400094d0`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1400064b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1400064b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400064e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400064e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1400064c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1400064c8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140006579`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x140006579`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1400065b8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1400065b8`

## string_xrefs

- `0x140006581`: `activatibleClassId`

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
0x140006478  mov     [rsp+arg_8], rbx
0x14000647d  push    rbp
0x14000647e  push    rsi
0x14000647f  push    rdi
0x140006480  push    r14
0x140006482  push    r15
0x140006484  sub     rsp, 70h
0x140006488  mov     rax, cs:__security_cookie
0x14000648f  xor     rax, rsp
0x140006492  mov     [rsp+98h+var_38], rax
0x140006497  mov     r14, r9
0x14000649a  mov     rdi, r8
0x14000649d  mov     rsi, rcx
0x1400064a0  mov     qword ptr [r9], 0
0x1400064a7  mov     [rsp+98h+hasEmbedNull], 0
0x1400064af  mov     rcx, r8; string
0x1400064b2  call    cs:__imp_WindowsIsStringEmpty
0x1400064b8  test    eax, eax
0x1400064ba  jnz     loc_140006581
0x1400064c0  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x1400064c5  mov     rcx, rdi; string
0x1400064c8  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1400064ce  test    eax, eax
0x1400064d0  js      loc_140006581
0x1400064d6  cmp     [rsp+98h+hasEmbedNull], 1
0x1400064db  jz      loc_140006581
0x1400064e1  xor     edx, edx; length
0x1400064e3  mov     rcx, rdi; string
0x1400064e6  call    cs:__imp_WindowsGetStringRawBuffer
0x1400064ec  mov     r15, rax
0x1400064ef  mov     rcx, [rsi]
0x1400064f2  mov     rax, [rcx+28h]
0x1400064f6  mov     rcx, rsi
0x1400064f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064fe  lea     rbx, [rax+8]
0x140006502  mov     rcx, [rsi]
0x140006505  mov     rax, [rcx+30h]
0x140006509  mov     rcx, rsi
0x14000650c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006511  mov     rbp, rax
0x140006514  cmp     rbx, rbp
0x140006517  jnb     short loc_14000656F
0x140006519  mov     rax, [rbx]
0x14000651c  test    rax, rax
0x14000651f  jz      short loc_14000654A
0x140006521  mov     rax, [rax+8]
0x140006525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000652a  mov     rcx, r15
0x14000652d  sub     rax, r15
0x140006530  movzx   edx, word ptr [rcx]
0x140006533  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x140006538  sub     edx, r8d
0x14000653b  jnz     short loc_140006546
0x14000653d  add     rcx, 2
0x140006541  test    r8d, r8d
0x140006544  jnz     short loc_140006530
0x140006546  test    edx, edx
0x140006548  jz      short loc_140006550
0x14000654a  add     rbx, 8
0x14000654e  jmp     short loc_140006514
0x140006550  mov     [rsp+98h+var_64], 2
0x140006558  mov     [rsp+98h+SRWLock], r14; SRWLock
0x14000655d  mov     r9, [rbx]; struct _GUID *
0x140006560  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x140006565  mov     rcx, rsi; this
0x140006568  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x14000656d  jmp     short loc_1400065C0
0x14000656f  mov     rdx, rdi
0x140006572  mov     ebx, 80040111h
0x140006577  mov     ecx, ebx
0x140006579  call    cs:__imp_RoOriginateError
0x14000657f  jmp     short loc_1400065BE
0x140006581  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x140006588  movups  [rsp+98h+var_60], xmm0
0x14000658d  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x140006594  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x140006599  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x1400065a1  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x1400065a7  lea     r8, [rsp+98h+var_60]
0x1400065ac  mov     edx, 12h
0x1400065b1  mov     ebx, 80070057h
0x1400065b6  mov     ecx, ebx
0x1400065b8  call    cs:__imp_RoOriginateErrorW
0x1400065be  mov     eax, ebx
0x1400065c0  mov     rcx, [rsp+98h+var_38]
0x1400065c5  xor     rcx, rsp; StackCookie
0x1400065c8  call    __security_check_cookie
0x1400065cd  mov     rbx, [rsp+98h+arg_8]
0x1400065d5  add     rsp, 70h
0x1400065d9  pop     r15
0x1400065db  pop     r14
0x1400065dd  pop     rdi
0x1400065de  pop     rsi
0x1400065df  pop     rbp
0x1400065e0  retn
```

# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180014830`
- end: `0x180014999`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014fe0`

## callees

- `0x180002be0`
- `0x180014830`
- `0x180014b84`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180014880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180014880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001489e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001489e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001486a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001486a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180014931`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180014931`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180014970`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180014970`

## string_xrefs

- `0x180014939`: `activatibleClassId`

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
          v19 = 1;
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
0x180014830  mov     [rsp+arg_8], rbx
0x180014835  push    rbp
0x180014836  push    rsi
0x180014837  push    rdi
0x180014838  push    r14
0x18001483a  push    r15
0x18001483c  sub     rsp, 70h
0x180014840  mov     rax, cs:__security_cookie
0x180014847  xor     rax, rsp
0x18001484a  mov     [rsp+98h+var_38], rax
0x18001484f  mov     r14, r9
0x180014852  mov     rdi, r8
0x180014855  mov     rsi, rcx
0x180014858  mov     qword ptr [r9], 0
0x18001485f  mov     [rsp+98h+hasEmbedNull], 0
0x180014867  mov     rcx, r8; string
0x18001486a  call    cs:__imp_WindowsIsStringEmpty
0x180014870  test    eax, eax
0x180014872  jnz     loc_180014939
0x180014878  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x18001487d  mov     rcx, rdi; string
0x180014880  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180014886  test    eax, eax
0x180014888  js      loc_180014939
0x18001488e  cmp     [rsp+98h+hasEmbedNull], 1
0x180014893  jz      loc_180014939
0x180014899  xor     edx, edx; length
0x18001489b  mov     rcx, rdi; string
0x18001489e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800148a4  mov     r15, rax
0x1800148a7  mov     rcx, [rsi]
0x1800148aa  mov     rax, [rcx+28h]
0x1800148ae  mov     rcx, rsi
0x1800148b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148b6  lea     rbx, [rax+8]
0x1800148ba  mov     rcx, [rsi]
0x1800148bd  mov     rax, [rcx+30h]
0x1800148c1  mov     rcx, rsi
0x1800148c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148c9  mov     rbp, rax
0x1800148cc  cmp     rbx, rbp
0x1800148cf  jnb     short loc_180014927
0x1800148d1  mov     rax, [rbx]
0x1800148d4  test    rax, rax
0x1800148d7  jz      short loc_180014902
0x1800148d9  mov     rax, [rax+8]
0x1800148dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148e2  mov     rcx, r15
0x1800148e5  sub     rax, r15
0x1800148e8  movzx   edx, word ptr [rcx]
0x1800148eb  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x1800148f0  sub     edx, r8d
0x1800148f3  jnz     short loc_1800148FE
0x1800148f5  add     rcx, 2
0x1800148f9  test    r8d, r8d
0x1800148fc  jnz     short loc_1800148E8
0x1800148fe  test    edx, edx
0x180014900  jz      short loc_180014908
0x180014902  add     rbx, 8
0x180014906  jmp     short loc_1800148CC
0x180014908  mov     [rsp+98h+var_64], 1
0x180014910  mov     [rsp+98h+SRWLock], r14; SRWLock
0x180014915  mov     r9, [rbx]; struct _GUID *
0x180014918  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x18001491d  mov     rcx, rsi; this
0x180014920  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180014925  jmp     short loc_180014978
0x180014927  mov     rdx, rdi
0x18001492a  mov     ebx, 80040111h
0x18001492f  mov     ecx, ebx
0x180014931  call    cs:__imp_RoOriginateError
0x180014937  jmp     short loc_180014976
0x180014939  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180014940  movups  [rsp+98h+var_60], xmm0
0x180014945  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18001494c  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180014951  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180014959  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x18001495f  lea     r8, [rsp+98h+var_60]
0x180014964  mov     edx, 12h
0x180014969  mov     ebx, 80070057h
0x18001496e  mov     ecx, ebx
0x180014970  call    cs:__imp_RoOriginateErrorW
0x180014976  mov     eax, ebx
0x180014978  mov     rcx, [rsp+98h+var_38]
0x18001497d  xor     rcx, rsp; StackCookie
0x180014980  call    __security_check_cookie
0x180014985  mov     rbx, [rsp+98h+arg_8]
0x18001498d  add     rsp, 70h
0x180014991  pop     r15
0x180014993  pop     r14
0x180014995  pop     rdi
0x180014996  pop     rsi
0x180014997  pop     rbp
0x180014998  retn
```

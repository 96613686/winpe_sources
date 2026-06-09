# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,wchar_t const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180050260`
- end: `0x1800503c9`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEB_WPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050a20`

## callees

- `0x180002b20`
- `0x180050260`
- `0x180050504`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180050361`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180050361`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800503a0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800503a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800502b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800502b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18005029a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18005029a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800502ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800502ce`

## string_xrefs

- `0x180050369`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<1>(
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
0x180050260  mov     [rsp+arg_8], rbx
0x180050265  push    rbp
0x180050266  push    rsi
0x180050267  push    rdi
0x180050268  push    r14
0x18005026a  push    r15
0x18005026c  sub     rsp, 70h
0x180050270  mov     rax, cs:__security_cookie
0x180050277  xor     rax, rsp
0x18005027a  mov     [rsp+98h+var_38], rax
0x18005027f  mov     r14, r9
0x180050282  mov     rdi, r8
0x180050285  mov     rsi, rcx
0x180050288  mov     qword ptr [r9], 0
0x18005028f  mov     [rsp+98h+hasEmbedNull], 0
0x180050297  mov     rcx, r8; string
0x18005029a  call    cs:__imp_WindowsIsStringEmpty
0x1800502a0  test    eax, eax
0x1800502a2  jnz     loc_180050369
0x1800502a8  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x1800502ad  mov     rcx, rdi; string
0x1800502b0  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800502b6  test    eax, eax
0x1800502b8  js      loc_180050369
0x1800502be  cmp     [rsp+98h+hasEmbedNull], 1
0x1800502c3  jz      loc_180050369
0x1800502c9  xor     edx, edx; length
0x1800502cb  mov     rcx, rdi; string
0x1800502ce  call    cs:__imp_WindowsGetStringRawBuffer
0x1800502d4  mov     r15, rax
0x1800502d7  mov     rcx, [rsi]
0x1800502da  mov     rax, [rcx+28h]
0x1800502de  mov     rcx, rsi
0x1800502e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502e6  lea     rbx, [rax+8]
0x1800502ea  mov     rcx, [rsi]
0x1800502ed  mov     rax, [rcx+30h]
0x1800502f1  mov     rcx, rsi
0x1800502f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502f9  mov     rbp, rax
0x1800502fc  cmp     rbx, rbp
0x1800502ff  jnb     short loc_180050357
0x180050301  mov     rax, [rbx]
0x180050304  test    rax, rax
0x180050307  jz      short loc_180050332
0x180050309  mov     rax, [rax+8]
0x18005030d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050312  mov     rcx, r15
0x180050315  sub     rax, r15
0x180050318  movzx   edx, word ptr [rcx]
0x18005031b  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180050320  sub     edx, r8d
0x180050323  jnz     short loc_18005032E
0x180050325  add     rcx, 2
0x180050329  test    r8d, r8d
0x18005032c  jnz     short loc_180050318
0x18005032e  test    edx, edx
0x180050330  jz      short loc_180050338
0x180050332  add     rbx, 8
0x180050336  jmp     short loc_1800502FC
0x180050338  mov     [rsp+98h+var_64], 1
0x180050340  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x180050345  mov     r9, [rbx]; struct _GUID *
0x180050348  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x18005034d  mov     rcx, rsi; this
0x180050350  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180050355  jmp     short loc_1800503A8
0x180050357  mov     rdx, rdi
0x18005035a  mov     ebx, 80040111h
0x18005035f  mov     ecx, ebx
0x180050361  call    cs:__imp_RoOriginateError
0x180050367  jmp     short loc_1800503A6
0x180050369  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180050370  movups  [rsp+98h+var_60], xmm0
0x180050375  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18005037c  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180050381  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180050389  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x18005038f  lea     r8, [rsp+98h+var_60]
0x180050394  mov     edx, 12h
0x180050399  mov     ebx, 80070057h
0x18005039e  mov     ecx, ebx
0x1800503a0  call    cs:__imp_RoOriginateErrorW
0x1800503a6  mov     eax, ebx
0x1800503a8  mov     rcx, [rsp+98h+var_38]
0x1800503ad  xor     rcx, rsp; StackCookie
0x1800503b0  call    __security_check_cookie
0x1800503b5  mov     rbx, [rsp+98h+arg_8]
0x1800503bd  add     rsp, 70h
0x1800503c1  pop     r15
0x1800503c3  pop     r14
0x1800503c5  pop     rdi
0x1800503c6  pop     rsi
0x1800503c7  pop     rbp
0x1800503c8  retn
```

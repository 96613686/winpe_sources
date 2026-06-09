# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180095530`
- end: `0x1800956c0`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800960d0`

## callees

- `0x180002a00`
- `0x180095530`
- `0x180096154`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18009556a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18009556a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800955aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800955aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180095586`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180095586`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180095643`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180095643`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180095690`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180095690`

## string_xrefs

- `0x18009565c`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<1>(
        Microsoft::WRL::Details *this,
        __int64 a2,
        HSTRING a3,
        RTL_SRWLOCK *a4)
{
  PCWSTR StringRawBuffer; // r15
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // rbp
  __int64 v10; // rax
  unsigned __int16 *v11; // rcx
  __int64 v12; // rax
  unsigned int *v13; // r8
  int v14; // edx
  const struct _GUID *v15; // r9
  unsigned int v17; // ebx
  struct IUnknown **v18; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v20; // [rsp+34h] [rbp-64h] BYREF
  _OWORD v21[2]; // [rsp+38h] [rbp-60h] BYREF
  int v22; // [rsp+58h] [rbp-40h]
  wchar_t v23; // [rsp+5Ch] [rbp-3Ch]

  a4->Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(a3) || WindowsStringHasEmbeddedNull(a3, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v22 = *(_DWORD *)L"Id";
    v17 = -2147024809;
    v23 = aActivatiblecla[18];
    v21[0] = *(_OWORD *)L"activatibleClassId";
    v21[1] = *(_OWORD *)L"bleClassId";
    RoOriginateErrorW(2147942487LL, 18, v21);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v8 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 40LL))(this) + 8;
    v9 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
    while ( v8 < v9 )
    {
      if ( *(_QWORD *)v8 )
      {
        v10 = (*(__int64 (**)(void))(*(_QWORD *)v8 + 8LL))();
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
          v15 = *(const struct _GUID **)v8;
          v20 = 1;
          return Microsoft::WRL::Details::GetCacheEntry(
                   this,
                   (struct Microsoft::WRL::Details::ModuleBase *)&v20,
                   v13,
                   v15,
                   a4,
                   v18);
        }
      }
      v8 += 8LL;
    }
    v17 = -2147221231;
    RoOriginateError(2147746065LL, a3);
  }
  return v17;
}

```

## disassembly

```asm
0x180095530  mov     [rsp+arg_8], rbx
0x180095535  push    rbp
0x180095536  push    rsi
0x180095537  push    rdi
0x180095538  push    r14
0x18009553a  push    r15
0x18009553c  sub     rsp, 70h
0x180095540  mov     rax, cs:__security_cookie
0x180095547  xor     rax, rsp
0x18009554a  mov     [rsp+98h+var_38], rax
0x18009554f  mov     rsi, rcx
0x180095552  mov     qword ptr [r9], 0
0x180095559  mov     rcx, r8; string
0x18009555c  mov     [rsp+98h+hasEmbedNull], 0
0x180095564  mov     r14, r9
0x180095567  mov     rdi, r8
0x18009556a  call    cs:__imp_WindowsIsStringEmpty
0x180095571  nop     dword ptr [rax+rax+00h]
0x180095576  test    eax, eax
0x180095578  jnz     loc_180095651
0x18009557e  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180095583  mov     rcx, rdi; string
0x180095586  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18009558d  nop     dword ptr [rax+rax+00h]
0x180095592  test    eax, eax
0x180095594  js      loc_180095651
0x18009559a  cmp     [rsp+98h+hasEmbedNull], 1
0x18009559f  jz      loc_180095651
0x1800955a5  xor     edx, edx; length
0x1800955a7  mov     rcx, rdi; string
0x1800955aa  call    cs:__imp_WindowsGetStringRawBuffer
0x1800955b1  nop     dword ptr [rax+rax+00h]
0x1800955b6  mov     rcx, [rsi]
0x1800955b9  mov     r15, rax
0x1800955bc  mov     rax, [rcx+28h]
0x1800955c0  mov     rcx, rsi
0x1800955c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800955c8  mov     rcx, [rsi]
0x1800955cb  lea     rbx, [rax+8]
0x1800955cf  mov     rax, [rcx+30h]
0x1800955d3  mov     rcx, rsi
0x1800955d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800955db  mov     rbp, rax
0x1800955de  cmp     rbx, rbp
0x1800955e1  jnb     short loc_180095639
0x1800955e3  mov     rax, [rbx]
0x1800955e6  test    rax, rax
0x1800955e9  jz      short loc_180095614
0x1800955eb  mov     rax, [rax+8]
0x1800955ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800955f4  mov     rcx, r15
0x1800955f7  sub     rax, r15
0x1800955fa  movzx   edx, word ptr [rcx]
0x1800955fd  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180095602  sub     edx, r8d
0x180095605  jnz     short loc_180095610
0x180095607  add     rcx, 2
0x18009560b  test    r8d, r8d
0x18009560e  jnz     short loc_1800955FA
0x180095610  test    edx, edx
0x180095612  jz      short loc_18009561A
0x180095614  add     rbx, 8
0x180095618  jmp     short loc_1800955DE
0x18009561a  mov     r9, [rbx]; struct _GUID *
0x18009561d  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180095622  mov     rcx, rsi; this
0x180095625  mov     [rsp+98h+var_64], 1
0x18009562d  mov     [rsp+98h+SRWLock], r14; SRWLock
0x180095632  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180095637  jmp     short loc_18009569E
0x180095639  mov     ebx, 80040111h
0x18009563e  mov     rdx, rdi
0x180095641  mov     ecx, ebx
0x180095643  call    cs:__imp_RoOriginateError
0x18009564a  nop     dword ptr [rax+rax+00h]
0x18009564f  jmp     short loc_18009569C
0x180095651  mov     eax, dword ptr cs:aActivatiblecla+20h; "Id"
0x180095657  lea     r8, [rsp+98h+var_60]
0x18009565c  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180095663  mov     [rsp+98h+var_40], eax
0x180095667  mov     ebx, 80070057h
0x18009566c  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180095673  movzx   eax, word ptr cs:aActivatiblecla+24h; ""
0x18009567a  mov     edx, 12h
0x18009567f  mov     ecx, ebx
0x180095681  mov     [rsp+98h+var_3C], ax
0x180095686  movups  [rsp+98h+var_60], xmm0
0x18009568b  movups  [rsp+98h+var_50], xmm1
0x180095690  call    cs:__imp_RoOriginateErrorW
0x180095697  nop     dword ptr [rax+rax+00h]
0x18009569c  mov     eax, ebx
0x18009569e  mov     rcx, [rsp+98h+var_38]
0x1800956a3  xor     rcx, rsp; StackCookie
0x1800956a6  call    __security_check_cookie
0x1800956ab  mov     rbx, [rsp+98h+arg_8]
0x1800956b3  add     rsp, 70h
0x1800956b7  pop     r15
0x1800956b9  pop     r14
0x1800956bb  pop     rdi
0x1800956bc  pop     rsi
0x1800956bd  pop     rbp
0x1800956be  retn
```

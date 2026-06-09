# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x18000367c`
- end: `0x1800037ec`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005540`

## callees

- `0x1800021d0`
- `0x18000367c`
- `0x180005ed8`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800036b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800036b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800036ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800036ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800036cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800036cc`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800037c3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800037c3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003784`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180003784`

## string_xrefs

- `0x18000378c`: `activatibleClassId`

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
0x18000367c  mov     [rsp+arg_8], rbx
0x180003681  push    rbp
0x180003682  push    rsi
0x180003683  push    rdi
0x180003684  push    r14
0x180003686  push    r15
0x180003688  sub     rsp, 70h
0x18000368c  mov     rax, cs:__security_cookie
0x180003693  xor     rax, rsp
0x180003696  mov     [rsp+98h+var_38], rax
0x18000369b  mov     r14, r9
0x18000369e  mov     rdi, r8
0x1800036a1  mov     rsi, rcx
0x1800036a4  mov     qword ptr [r9], 0
0x1800036ab  mov     [rsp+98h+hasEmbedNull], 0
0x1800036b3  mov     rcx, r8; string
0x1800036b6  call    cs:__imp_WindowsIsStringEmpty
0x1800036bc  test    eax, eax
0x1800036be  jnz     loc_18000378C
0x1800036c4  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x1800036c9  mov     rcx, rdi; string
0x1800036cc  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800036d2  test    eax, eax
0x1800036d4  js      loc_18000378C
0x1800036da  cmp     [rsp+98h+hasEmbedNull], 1
0x1800036df  jz      loc_18000378C
0x1800036e5  xor     edx, edx; length
0x1800036e7  mov     rcx, rdi; string
0x1800036ea  call    cs:__imp_WindowsGetStringRawBuffer
0x1800036f0  mov     r15, rax
0x1800036f3  mov     rcx, [rsi]
0x1800036f6  mov     rax, [rcx+28h]
0x1800036fa  mov     rcx, rsi
0x1800036fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003702  lea     rbx, [rax+8]
0x180003706  mov     rcx, [rsi]
0x180003709  mov     rax, [rcx+30h]
0x18000370d  mov     rcx, rsi
0x180003710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003715  mov     rbp, rax
0x180003718  cmp     rbx, rbp
0x18000371b  jnb     short loc_18000377A
0x18000371d  mov     rax, [rbx]
0x180003720  test    rax, rax
0x180003723  jz      short loc_18000374E
0x180003725  mov     rax, [rax+8]
0x180003729  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000372e  mov     rcx, r15
0x180003731  sub     rax, r15
0x180003734  movzx   edx, word ptr [rcx]
0x180003737  movzx   r8d, word ptr [rcx+rax]
0x18000373c  sub     edx, r8d
0x18000373f  jnz     short loc_18000374A
0x180003741  add     rcx, 2
0x180003745  test    r8d, r8d
0x180003748  jnz     short loc_180003734
0x18000374a  test    edx, edx
0x18000374c  jz      short loc_180003754
0x18000374e  add     rbx, 8
0x180003752  jmp     short loc_180003718
0x180003754  mov     [rsp+98h+var_64], 1
0x18000375c  mov     [rsp+98h+Ptr], r14; Ptr
0x180003761  mov     r9, [rbx]; struct _GUID *
0x180003764  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x18000376b  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180003770  mov     rcx, rsi; this
0x180003773  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180003778  jmp     short loc_1800037CB
0x18000377a  mov     rdx, rdi
0x18000377d  mov     ebx, 80040111h
0x180003782  mov     ecx, ebx
0x180003784  call    cs:__imp_RoOriginateError
0x18000378a  jmp     short loc_1800037C9
0x18000378c  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180003793  movups  [rsp+98h+var_60], xmm0
0x180003798  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18000379f  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x1800037a4  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x1800037ac  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x1800037b2  lea     r8, [rsp+98h+var_60]
0x1800037b7  mov     edx, 12h
0x1800037bc  mov     ebx, 80070057h
0x1800037c1  mov     ecx, ebx
0x1800037c3  call    cs:__imp_RoOriginateErrorW
0x1800037c9  mov     eax, ebx
0x1800037cb  mov     rcx, [rsp+98h+var_38]
0x1800037d0  xor     rcx, rsp; StackCookie
0x1800037d3  call    __security_check_cookie
0x1800037d8  mov     rbx, [rsp+98h+arg_8]
0x1800037e0  add     rsp, 70h
0x1800037e4  pop     r15
0x1800037e6  pop     r14
0x1800037e8  pop     rdi
0x1800037e9  pop     rsi
0x1800037ea  pop     rbp
0x1800037eb  retn
```

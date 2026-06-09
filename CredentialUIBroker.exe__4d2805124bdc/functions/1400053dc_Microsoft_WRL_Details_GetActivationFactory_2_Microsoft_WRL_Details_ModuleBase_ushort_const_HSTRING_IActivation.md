# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x1400053dc`
- end: `0x140005545`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004a60`

## callees

- `0x140003620`
- `0x1400053dc`
- `0x14000c950`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000544a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000544a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x140005416`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x140005416`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x14000542c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x14000542c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x14000551c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x14000551c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1400054dd`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1400054dd`

## string_xrefs

- `0x1400054e5`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<2>(
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
  __int128 v21; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v22[22]; // [rsp+48h] [rbp-50h]

  a4->Ptr = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(a3) || WindowsStringHasEmbeddedNull(a3, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v17 = -2147024809;
    v21 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v22 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v22[14] = *(_QWORD *)L"sId";
    RoOriginateErrorW(2147942487LL, 18, &v21);
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
          v20 = 2;
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
0x1400053dc  mov     [rsp+arg_8], rbx
0x1400053e1  push    rbp
0x1400053e2  push    rsi
0x1400053e3  push    rdi
0x1400053e4  push    r14
0x1400053e6  push    r15
0x1400053e8  sub     rsp, 70h
0x1400053ec  mov     rax, cs:__security_cookie
0x1400053f3  xor     rax, rsp
0x1400053f6  mov     [rsp+98h+var_38], rax
0x1400053fb  mov     rsi, rcx
0x1400053fe  mov     qword ptr [r9], 0
0x140005405  mov     rcx, r8; string
0x140005408  mov     [rsp+98h+hasEmbedNull], 0
0x140005410  mov     r14, r9
0x140005413  mov     rdi, r8
0x140005416  call    cs:__imp_WindowsIsStringEmpty
0x14000541c  test    eax, eax
0x14000541e  jnz     loc_1400054E5
0x140005424  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x140005429  mov     rcx, rdi; string
0x14000542c  call    cs:__imp_WindowsStringHasEmbeddedNull
0x140005432  test    eax, eax
0x140005434  js      loc_1400054E5
0x14000543a  cmp     [rsp+98h+hasEmbedNull], 1
0x14000543f  jz      loc_1400054E5
0x140005445  xor     edx, edx; length
0x140005447  mov     rcx, rdi; string
0x14000544a  call    cs:__imp_WindowsGetStringRawBuffer
0x140005450  mov     rcx, [rsi]
0x140005453  mov     r15, rax
0x140005456  mov     rax, [rcx+28h]
0x14000545a  mov     rcx, rsi
0x14000545d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005462  mov     rcx, [rsi]
0x140005465  lea     rbx, [rax+8]
0x140005469  mov     rax, [rcx+30h]
0x14000546d  mov     rcx, rsi
0x140005470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005475  mov     rbp, rax
0x140005478  cmp     rbx, rbp
0x14000547b  jnb     short loc_1400054D3
0x14000547d  mov     rax, [rbx]
0x140005480  test    rax, rax
0x140005483  jz      short loc_1400054AE
0x140005485  mov     rax, [rax+8]
0x140005489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000548e  mov     rcx, r15
0x140005491  sub     rax, r15
0x140005494  movzx   edx, word ptr [rcx]
0x140005497  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x14000549c  sub     edx, r8d
0x14000549f  jnz     short loc_1400054AA
0x1400054a1  add     rcx, 2
0x1400054a5  test    r8d, r8d
0x1400054a8  jnz     short loc_140005494
0x1400054aa  test    edx, edx
0x1400054ac  jz      short loc_1400054B4
0x1400054ae  add     rbx, 8
0x1400054b2  jmp     short loc_140005478
0x1400054b4  mov     r9, [rbx]; struct _GUID *
0x1400054b7  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x1400054bc  mov     rcx, rsi; this
0x1400054bf  mov     [rsp+98h+var_64], 2
0x1400054c7  mov     [rsp+98h+SRWLock], r14; SRWLock
0x1400054cc  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x1400054d1  jmp     short loc_140005524
0x1400054d3  mov     ebx, 80040111h
0x1400054d8  mov     rdx, rdi
0x1400054db  mov     ecx, ebx
0x1400054dd  call    cs:__imp_RoOriginateError
0x1400054e3  jmp     short loc_140005522
0x1400054e5  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x1400054ec  mov     ebx, 80070057h
0x1400054f1  lea     r8, [rsp+98h+var_60]
0x1400054f6  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x1400054fd  mov     edx, 12h
0x140005502  mov     ecx, ebx
0x140005504  movups  [rsp+98h+var_60], xmm0
0x140005509  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x140005511  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x140005516  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x14000551c  call    cs:__imp_RoOriginateErrorW
0x140005522  mov     eax, ebx
0x140005524  mov     rcx, [rsp+98h+var_38]
0x140005529  xor     rcx, rsp; StackCookie
0x14000552c  call    __security_check_cookie
0x140005531  mov     rbx, [rsp+98h+arg_8]
0x140005539  add     rsp, 70h
0x14000553d  pop     r15
0x14000553f  pop     r14
0x140005541  pop     rdi
0x140005542  pop     rsi
0x140005543  pop     rbp
0x140005544  retn
```

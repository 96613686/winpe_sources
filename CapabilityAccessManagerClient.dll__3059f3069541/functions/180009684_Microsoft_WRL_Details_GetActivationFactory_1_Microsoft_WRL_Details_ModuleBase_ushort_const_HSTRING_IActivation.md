# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180009684`
- end: `0x1800097f4`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800102c0`

## callees

- `0x180003c80`
- `0x180009684`
- `0x18000b914`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800096d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800096d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800096be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800096be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800096f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800096f2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800097cb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800097cb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000978c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000978c`

## string_xrefs

- `0x180009794`: `activatibleClassId`

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
0x180009684  mov     [rsp+arg_8], rbx
0x180009689  push    rbp
0x18000968a  push    rsi
0x18000968b  push    rdi
0x18000968c  push    r14
0x18000968e  push    r15
0x180009690  sub     rsp, 70h
0x180009694  mov     rax, cs:__security_cookie
0x18000969b  xor     rax, rsp
0x18000969e  mov     [rsp+98h+var_38], rax
0x1800096a3  mov     r14, r9
0x1800096a6  mov     rdi, r8
0x1800096a9  mov     rsi, rcx
0x1800096ac  mov     qword ptr [r9], 0
0x1800096b3  mov     [rsp+98h+hasEmbedNull], 0
0x1800096bb  mov     rcx, r8; string
0x1800096be  call    cs:__imp_WindowsIsStringEmpty
0x1800096c4  test    eax, eax
0x1800096c6  jnz     loc_180009794
0x1800096cc  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x1800096d1  mov     rcx, rdi; string
0x1800096d4  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800096da  test    eax, eax
0x1800096dc  js      loc_180009794
0x1800096e2  cmp     [rsp+98h+hasEmbedNull], 1
0x1800096e7  jz      loc_180009794
0x1800096ed  xor     edx, edx; length
0x1800096ef  mov     rcx, rdi; string
0x1800096f2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800096f8  mov     r15, rax
0x1800096fb  mov     rcx, [rsi]
0x1800096fe  mov     rax, [rcx+28h]
0x180009702  mov     rcx, rsi
0x180009705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000970a  lea     rbx, [rax+8]
0x18000970e  mov     rcx, [rsi]
0x180009711  mov     rax, [rcx+30h]
0x180009715  mov     rcx, rsi
0x180009718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000971d  mov     rbp, rax
0x180009720  cmp     rbx, rbp
0x180009723  jnb     short loc_180009782
0x180009725  mov     rax, [rbx]
0x180009728  test    rax, rax
0x18000972b  jz      short loc_180009756
0x18000972d  mov     rax, [rax+8]
0x180009731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009736  mov     rcx, r15
0x180009739  sub     rax, r15
0x18000973c  movzx   edx, word ptr [rcx]
0x18000973f  movzx   r8d, word ptr [rcx+rax]
0x180009744  sub     edx, r8d
0x180009747  jnz     short loc_180009752
0x180009749  add     rcx, 2
0x18000974d  test    r8d, r8d
0x180009750  jnz     short loc_18000973C
0x180009752  test    edx, edx
0x180009754  jz      short loc_18000975C
0x180009756  add     rbx, 8
0x18000975a  jmp     short loc_180009720
0x18000975c  mov     [rsp+98h+var_64], 1
0x180009764  mov     [rsp+98h+Ptr], r14; Ptr
0x180009769  mov     r9, [rbx]; struct _GUID *
0x18000976c  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x180009773  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180009778  mov     rcx, rsi; this
0x18000977b  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180009780  jmp     short loc_1800097D3
0x180009782  mov     rdx, rdi
0x180009785  mov     ebx, 80040111h
0x18000978a  mov     ecx, ebx
0x18000978c  call    cs:__imp_RoOriginateError
0x180009792  jmp     short loc_1800097D1
0x180009794  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18000979b  movups  [rsp+98h+var_60], xmm0
0x1800097a0  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x1800097a7  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x1800097ac  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x1800097b4  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x1800097ba  lea     r8, [rsp+98h+var_60]
0x1800097bf  mov     edx, 12h
0x1800097c4  mov     ebx, 80070057h
0x1800097c9  mov     ecx, ebx
0x1800097cb  call    cs:__imp_RoOriginateErrorW
0x1800097d1  mov     eax, ebx
0x1800097d3  mov     rcx, [rsp+98h+var_38]
0x1800097d8  xor     rcx, rsp; StackCookie
0x1800097db  call    __security_check_cookie
0x1800097e0  mov     rbx, [rsp+98h+arg_8]
0x1800097e8  add     rsp, 70h
0x1800097ec  pop     r15
0x1800097ee  pop     r14
0x1800097f0  pop     rdi
0x1800097f1  pop     rsi
0x1800097f2  pop     rbp
0x1800097f3  retn
```

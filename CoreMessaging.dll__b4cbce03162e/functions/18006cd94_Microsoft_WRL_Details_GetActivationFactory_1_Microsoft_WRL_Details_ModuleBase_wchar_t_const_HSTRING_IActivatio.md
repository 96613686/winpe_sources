# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,wchar_t const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x18006cd94`
- end: `0x18006cf09`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEB_WPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `373`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006cd60`

## callees

- `0x18006cd94`
- `0x18006cf10`
- `0x18009d670`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18006cdce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18006cdce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18006cde4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18006cde4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ce02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006ce02`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18006ceed`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18006ceed`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006cf01`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18006cf01`

## string_xrefs

- `0x18006ceb6`: `activatibleClassId`

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
0x18006cd94  mov     [rsp+arg_8], rbx
0x18006cd99  push    rbp
0x18006cd9a  push    rsi
0x18006cd9b  push    rdi
0x18006cd9c  push    r14
0x18006cd9e  push    r15
0x18006cda0  sub     rsp, 70h
0x18006cda4  mov     rax, cs:__security_cookie
0x18006cdab  xor     rax, rsp
0x18006cdae  mov     [rsp+98h+var_38], rax
0x18006cdb3  mov     r14, r9
0x18006cdb6  mov     rdi, r8
0x18006cdb9  mov     rsi, rcx
0x18006cdbc  mov     qword ptr [r9], 0
0x18006cdc3  mov     [rsp+98h+hasEmbedNull], 0
0x18006cdcb  mov     rcx, r8; string
0x18006cdce  call    cs:__imp_WindowsIsStringEmpty
0x18006cdd4  test    eax, eax
0x18006cdd6  jnz     loc_18006CEB6
0x18006cddc  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x18006cde1  mov     rcx, rdi; string
0x18006cde4  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18006cdea  test    eax, eax
0x18006cdec  js      loc_18006CEB6
0x18006cdf2  cmp     [rsp+98h+hasEmbedNull], 1
0x18006cdf7  jz      loc_18006CEB6
0x18006cdfd  xor     edx, edx; length
0x18006cdff  mov     rcx, rdi; string
0x18006ce02  call    cs:__imp_WindowsGetStringRawBuffer
0x18006ce08  mov     r15, rax
0x18006ce0b  mov     rcx, [rsi]
0x18006ce0e  mov     rax, [rcx+28h]
0x18006ce12  mov     rcx, rsi
0x18006ce15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce1a  lea     rbx, [rax+8]
0x18006ce1e  mov     rcx, [rsi]
0x18006ce21  mov     rax, [rcx+30h]
0x18006ce25  mov     rcx, rsi
0x18006ce28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce2d  mov     rbp, rax
0x18006ce30  cmp     rbx, rbp
0x18006ce33  jnb     loc_18006CEF7
0x18006ce39  mov     rax, [rbx]
0x18006ce3c  test    rax, rax
0x18006ce3f  jz      short loc_18006CE6A
0x18006ce41  mov     rax, [rax+8]
0x18006ce45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce4a  mov     rcx, r15
0x18006ce4d  sub     rax, r15
0x18006ce50  movzx   edx, word ptr [rcx]
0x18006ce53  movzx   r8d, word ptr [rcx+rax]
0x18006ce58  sub     edx, r8d
0x18006ce5b  jnz     short loc_18006CE66
0x18006ce5d  add     rcx, 2
0x18006ce61  test    r8d, r8d
0x18006ce64  jnz     short loc_18006CE50
0x18006ce66  test    edx, edx
0x18006ce68  jz      short loc_18006CE70
0x18006ce6a  add     rbx, 8
0x18006ce6e  jmp     short loc_18006CE30
0x18006ce70  mov     [rsp+98h+var_64], 1
0x18006ce78  mov     [rsp+98h+Ptr], r14; Ptr
0x18006ce7d  mov     r9, [rbx]; struct _GUID *
0x18006ce80  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x18006ce87  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x18006ce8c  mov     rcx, rsi; this
0x18006ce8f  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18006ce94  nop
0x18006ce95  mov     rcx, [rsp+98h+var_38]
0x18006ce9a  xor     rcx, rsp; StackCookie
0x18006ce9d  call    __security_check_cookie
0x18006cea2  mov     rbx, [rsp+98h+arg_8]
0x18006ceaa  add     rsp, 70h
0x18006ceae  pop     r15
0x18006ceb0  pop     r14
0x18006ceb2  pop     rdi
0x18006ceb3  pop     rsi
0x18006ceb4  pop     rbp
0x18006ceb5  retn
0x18006ceb6  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18006cebd  movups  [rsp+98h+var_60], xmm0
0x18006cec2  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18006cec9  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x18006cece  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x18006ced6  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x18006cedc  lea     r8, [rsp+98h+var_60]
0x18006cee1  mov     edx, 12h
0x18006cee6  mov     ebx, 80070057h
0x18006ceeb  mov     ecx, ebx
0x18006ceed  call    cs:__imp_RoOriginateErrorW
0x18006cef3  mov     eax, ebx
0x18006cef5  jmp     short loc_18006CE95
0x18006cef7  mov     rdx, rdi
0x18006cefa  mov     ebx, 80040111h
0x18006ceff  mov     ecx, ebx
0x18006cf01  call    cs:__imp_RoOriginateError
0x18006cf07  jmp     short loc_18006CEF3
```

# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180004f50`
- end: `0x1800050c7`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004d80`

## callees

- `0x180003a60`
- `0x180004f50`
- `0x180008df4`
- `0x18000a154`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180004fa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180004fa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180004f8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180004f8a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004fbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180004fbe`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000505f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000505f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000509e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000509e`

## string_xrefs

- `0x180005067`: `activatibleClassId`

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
  unsigned int *v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  unsigned __int16 *v13; // rcx
  __int64 v14; // rax
  int v15; // edx
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
    v21 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v22 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v22[14] = *(_QWORD *)L"sId";
    v17 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v21);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
    v8 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 40LL))(this)
                               + 8);
    v9 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
    while ( (unsigned __int64)v8 < v9 )
    {
      if ( *v8
        && Microsoft::WRL::Details::IsServerNameEqual((Microsoft::WRL::Details *)*v8, 0, (const unsigned __int16 *)v10) )
      {
        v12 = (*(__int64 (**)(void))(v11 + 8))();
        v13 = (unsigned __int16 *)StringRawBuffer;
        v14 = v12 - (_QWORD)StringRawBuffer;
        do
        {
          v10 = (unsigned int *)*(unsigned __int16 *)((char *)v13 + v14);
          v15 = *v13 - (_DWORD)v10;
          if ( v15 )
            break;
          ++v13;
        }
        while ( (_DWORD)v10 );
        if ( !v15 )
        {
          v20 = 2;
          return Microsoft::WRL::Details::GetCacheEntry(
                   this,
                   (struct Microsoft::WRL::Details::ModuleBase *)&v20,
                   v10,
                   *v8,
                   a4,
                   v18);
        }
      }
      ++v8;
    }
    v17 = -2147221231;
    RoOriginateError(2147746065LL, a3);
  }
  return v17;
}

```

## disassembly

```asm
0x180004f50  mov     [rsp+arg_8], rbx
0x180004f55  push    rbp
0x180004f56  push    rsi
0x180004f57  push    rdi
0x180004f58  push    r14
0x180004f5a  push    r15
0x180004f5c  sub     rsp, 70h
0x180004f60  mov     rax, cs:__security_cookie
0x180004f67  xor     rax, rsp
0x180004f6a  mov     [rsp+98h+var_38], rax
0x180004f6f  mov     r14, r9
0x180004f72  mov     rdi, r8
0x180004f75  mov     rsi, rcx
0x180004f78  mov     qword ptr [r9], 0
0x180004f7f  mov     [rsp+98h+hasEmbedNull], 0
0x180004f87  mov     rcx, r8; string
0x180004f8a  call    cs:__imp_WindowsIsStringEmpty
0x180004f90  test    eax, eax
0x180004f92  jnz     loc_180005067
0x180004f98  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180004f9d  mov     rcx, rdi; string
0x180004fa0  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180004fa6  test    eax, eax
0x180004fa8  js      loc_180005067
0x180004fae  cmp     [rsp+98h+hasEmbedNull], 1
0x180004fb3  jz      loc_180005067
0x180004fb9  xor     edx, edx; length
0x180004fbb  mov     rcx, rdi; string
0x180004fbe  call    cs:__imp_WindowsGetStringRawBuffer
0x180004fc4  mov     r15, rax
0x180004fc7  mov     rcx, [rsi]
0x180004fca  mov     rax, [rcx+28h]
0x180004fce  mov     rcx, rsi
0x180004fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd6  lea     rbx, [rax+8]
0x180004fda  mov     rcx, [rsi]
0x180004fdd  mov     rax, [rcx+30h]
0x180004fe1  mov     rcx, rsi
0x180004fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe9  mov     rbp, rax
0x180004fec  cmp     rbx, rbp
0x180004fef  jnb     short loc_180005055
0x180004ff1  mov     r9, [rbx]
0x180004ff4  test    r9, r9
0x180004ff7  jz      short loc_180005030
0x180004ff9  xor     edx, edx; struct Microsoft::WRL::Details::CreatorMap *
0x180004ffb  mov     rcx, r9; this
0x180004ffe  call    ?IsServerNameEqual@Details@WRL@Microsoft@@YA_NPEBUCreatorMap@123@PEBG@Z; Microsoft::WRL::Details::IsServerNameEqual(Microsoft::WRL::Details::CreatorMap const *,ushort const *)
0x180005003  test    al, al
0x180005005  jz      short loc_180005030
0x180005007  mov     rax, [r9+8]
0x18000500b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005010  mov     rcx, r15
0x180005013  sub     rax, r15
0x180005016  movzx   edx, word ptr [rcx]
0x180005019  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x18000501e  sub     edx, r8d
0x180005021  jnz     short loc_18000502C
0x180005023  add     rcx, 2
0x180005027  test    r8d, r8d
0x18000502a  jnz     short loc_180005016
0x18000502c  test    edx, edx
0x18000502e  jz      short loc_180005036
0x180005030  add     rbx, 8
0x180005034  jmp     short loc_180004FEC
0x180005036  mov     [rsp+98h+var_64], 2
0x18000503e  mov     [rsp+98h+SRWLock], r14; SRWLock
0x180005043  mov     r9, [rbx]; struct _GUID *
0x180005046  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x18000504b  mov     rcx, rsi; this
0x18000504e  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180005053  jmp     short loc_1800050A6
0x180005055  mov     rdx, rdi
0x180005058  mov     ebx, 80040111h
0x18000505d  mov     ecx, ebx
0x18000505f  call    cs:__imp_RoOriginateError
0x180005065  jmp     short loc_1800050A4
0x180005067  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18000506e  movups  [rsp+98h+var_60], xmm0
0x180005073  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18000507a  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x18000507f  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180005087  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x18000508d  lea     r8, [rsp+98h+var_60]
0x180005092  mov     edx, 12h
0x180005097  mov     ebx, 80070057h
0x18000509c  mov     ecx, ebx
0x18000509e  call    cs:__imp_RoOriginateErrorW
0x1800050a4  mov     eax, ebx
0x1800050a6  mov     rcx, [rsp+98h+var_38]
0x1800050ab  xor     rcx, rsp; StackCookie
0x1800050ae  call    __security_check_cookie
0x1800050b3  mov     rbx, [rsp+98h+arg_8]
0x1800050bb  add     rsp, 70h
0x1800050bf  pop     r15
0x1800050c1  pop     r14
0x1800050c3  pop     rdi
0x1800050c4  pop     rsi
0x1800050c5  pop     rbp
0x1800050c6  retn
```

# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180003f18`
- end: `0x18000408f`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003f00`

## callees

- `0x180002e60`
- `0x180003f18`
- `0x1800067e4`
- `0x18000773c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180003f68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180003f68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003f52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180003f52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003f86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180003f86`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180004066`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180004066`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004027`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180004027`

## string_xrefs

- `0x18000402f`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180003f18  mov     [rsp+arg_8], rbx
0x180003f1d  push    rbp
0x180003f1e  push    rsi
0x180003f1f  push    rdi
0x180003f20  push    r14
0x180003f22  push    r15
0x180003f24  sub     rsp, 70h
0x180003f28  mov     rax, cs:__security_cookie
0x180003f2f  xor     rax, rsp
0x180003f32  mov     [rsp+98h+var_38], rax
0x180003f37  mov     r14, r9
0x180003f3a  mov     rdi, r8
0x180003f3d  mov     rsi, rcx
0x180003f40  mov     qword ptr [r9], 0
0x180003f47  mov     [rsp+98h+hasEmbedNull], 0
0x180003f4f  mov     rcx, r8; string
0x180003f52  call    cs:__imp_WindowsIsStringEmpty
0x180003f58  test    eax, eax
0x180003f5a  jnz     loc_18000402F
0x180003f60  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180003f65  mov     rcx, rdi; string
0x180003f68  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180003f6e  test    eax, eax
0x180003f70  js      loc_18000402F
0x180003f76  cmp     [rsp+98h+hasEmbedNull], 1
0x180003f7b  jz      loc_18000402F
0x180003f81  xor     edx, edx; length
0x180003f83  mov     rcx, rdi; string
0x180003f86  call    cs:__imp_WindowsGetStringRawBuffer
0x180003f8c  mov     r15, rax
0x180003f8f  mov     rcx, [rsi]
0x180003f92  mov     rax, [rcx+28h]
0x180003f96  mov     rcx, rsi
0x180003f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f9e  lea     rbx, [rax+8]
0x180003fa2  mov     rcx, [rsi]
0x180003fa5  mov     rax, [rcx+30h]
0x180003fa9  mov     rcx, rsi
0x180003fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fb1  mov     rbp, rax
0x180003fb4  cmp     rbx, rbp
0x180003fb7  jnb     short loc_18000401D
0x180003fb9  mov     r9, [rbx]
0x180003fbc  test    r9, r9
0x180003fbf  jz      short loc_180003FF8
0x180003fc1  xor     edx, edx; struct Microsoft::WRL::Details::CreatorMap *
0x180003fc3  mov     rcx, r9; this
0x180003fc6  call    ?IsServerNameEqual@Details@WRL@Microsoft@@YA_NPEBUCreatorMap@123@PEBG@Z; Microsoft::WRL::Details::IsServerNameEqual(Microsoft::WRL::Details::CreatorMap const *,ushort const *)
0x180003fcb  test    al, al
0x180003fcd  jz      short loc_180003FF8
0x180003fcf  mov     rax, [r9+8]
0x180003fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd8  mov     rcx, r15
0x180003fdb  sub     rax, r15
0x180003fde  movzx   edx, word ptr [rcx]
0x180003fe1  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180003fe6  sub     edx, r8d
0x180003fe9  jnz     short loc_180003FF4
0x180003feb  add     rcx, 2
0x180003fef  test    r8d, r8d
0x180003ff2  jnz     short loc_180003FDE
0x180003ff4  test    edx, edx
0x180003ff6  jz      short loc_180003FFE
0x180003ff8  add     rbx, 8
0x180003ffc  jmp     short loc_180003FB4
0x180003ffe  mov     [rsp+98h+var_64], 2
0x180004006  mov     [rsp+98h+SRWLock], r14; SRWLock
0x18000400b  mov     r9, [rbx]; struct _GUID *
0x18000400e  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180004013  mov     rcx, rsi; this
0x180004016  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000401b  jmp     short loc_18000406E
0x18000401d  mov     rdx, rdi
0x180004020  mov     ebx, 80040111h
0x180004025  mov     ecx, ebx
0x180004027  call    cs:__imp_RoOriginateError
0x18000402d  jmp     short loc_18000406C
0x18000402f  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180004036  movups  [rsp+98h+var_60], xmm0
0x18000403b  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180004042  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180004047  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x18000404f  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180004055  lea     r8, [rsp+98h+var_60]
0x18000405a  mov     edx, 12h
0x18000405f  mov     ebx, 80070057h
0x180004064  mov     ecx, ebx
0x180004066  call    cs:__imp_RoOriginateErrorW
0x18000406c  mov     eax, ebx
0x18000406e  mov     rcx, [rsp+98h+var_38]
0x180004073  xor     rcx, rsp; StackCookie
0x180004076  call    __security_check_cookie
0x18000407b  mov     rbx, [rsp+98h+arg_8]
0x180004083  add     rsp, 70h
0x180004087  pop     r15
0x180004089  pop     r14
0x18000408b  pop     rdi
0x18000408c  pop     rsi
0x18000408d  pop     rbp
0x18000408e  retn
```

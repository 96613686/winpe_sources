# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180005ec8`
- end: `0x18000603f`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005eb0`

## callees

- `0x180003530`
- `0x180005ec8`
- `0x180007a80`
- `0x1800082bc`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005f36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005f36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180005f02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180005f02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180005f18`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180005f18`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006016`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180006016`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005fd7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005fd7`

## string_xrefs

- `0x180005fdf`: `activatibleClassId`

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
0x180005ec8  mov     [rsp+arg_8], rbx
0x180005ecd  push    rbp
0x180005ece  push    rsi
0x180005ecf  push    rdi
0x180005ed0  push    r14
0x180005ed2  push    r15
0x180005ed4  sub     rsp, 70h
0x180005ed8  mov     rax, cs:__security_cookie
0x180005edf  xor     rax, rsp
0x180005ee2  mov     [rsp+98h+var_38], rax
0x180005ee7  mov     r14, r9
0x180005eea  mov     rdi, r8
0x180005eed  mov     rsi, rcx
0x180005ef0  mov     qword ptr [r9], 0
0x180005ef7  mov     [rsp+98h+hasEmbedNull], 0
0x180005eff  mov     rcx, r8; string
0x180005f02  call    cs:__imp_WindowsIsStringEmpty
0x180005f08  test    eax, eax
0x180005f0a  jnz     loc_180005FDF
0x180005f10  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180005f15  mov     rcx, rdi; string
0x180005f18  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180005f1e  test    eax, eax
0x180005f20  js      loc_180005FDF
0x180005f26  cmp     [rsp+98h+hasEmbedNull], 1
0x180005f2b  jz      loc_180005FDF
0x180005f31  xor     edx, edx; length
0x180005f33  mov     rcx, rdi; string
0x180005f36  call    cs:__imp_WindowsGetStringRawBuffer
0x180005f3c  mov     r15, rax
0x180005f3f  mov     rcx, [rsi]
0x180005f42  mov     rax, [rcx+28h]
0x180005f46  mov     rcx, rsi
0x180005f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f4e  lea     rbx, [rax+8]
0x180005f52  mov     rcx, [rsi]
0x180005f55  mov     rax, [rcx+30h]
0x180005f59  mov     rcx, rsi
0x180005f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f61  mov     rbp, rax
0x180005f64  cmp     rbx, rbp
0x180005f67  jnb     short loc_180005FCD
0x180005f69  mov     r9, [rbx]
0x180005f6c  test    r9, r9
0x180005f6f  jz      short loc_180005FA8
0x180005f71  xor     edx, edx; struct Microsoft::WRL::Details::CreatorMap *
0x180005f73  mov     rcx, r9; this
0x180005f76  call    ?IsServerNameEqual@Details@WRL@Microsoft@@YA_NPEBUCreatorMap@123@PEBG@Z; Microsoft::WRL::Details::IsServerNameEqual(Microsoft::WRL::Details::CreatorMap const *,ushort const *)
0x180005f7b  test    al, al
0x180005f7d  jz      short loc_180005FA8
0x180005f7f  mov     rax, [r9+8]
0x180005f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f88  mov     rcx, r15
0x180005f8b  sub     rax, r15
0x180005f8e  movzx   edx, word ptr [rcx]
0x180005f91  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180005f96  sub     edx, r8d
0x180005f99  jnz     short loc_180005FA4
0x180005f9b  add     rcx, 2
0x180005f9f  test    r8d, r8d
0x180005fa2  jnz     short loc_180005F8E
0x180005fa4  test    edx, edx
0x180005fa6  jz      short loc_180005FAE
0x180005fa8  add     rbx, 8
0x180005fac  jmp     short loc_180005F64
0x180005fae  mov     [rsp+98h+var_64], 2
0x180005fb6  mov     [rsp+98h+SRWLock], r14; SRWLock
0x180005fbb  mov     r9, [rbx]; struct _GUID *
0x180005fbe  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180005fc3  mov     rcx, rsi; this
0x180005fc6  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180005fcb  jmp     short loc_18000601E
0x180005fcd  mov     rdx, rdi
0x180005fd0  mov     ebx, 80040111h
0x180005fd5  mov     ecx, ebx
0x180005fd7  call    cs:__imp_RoOriginateError
0x180005fdd  jmp     short loc_18000601C
0x180005fdf  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180005fe6  movups  [rsp+98h+var_60], xmm0
0x180005feb  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180005ff2  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180005ff7  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180005fff  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180006005  lea     r8, [rsp+98h+var_60]
0x18000600a  mov     edx, 12h
0x18000600f  mov     ebx, 80070057h
0x180006014  mov     ecx, ebx
0x180006016  call    cs:__imp_RoOriginateErrorW
0x18000601c  mov     eax, ebx
0x18000601e  mov     rcx, [rsp+98h+var_38]
0x180006023  xor     rcx, rsp; StackCookie
0x180006026  call    __security_check_cookie
0x18000602b  mov     rbx, [rsp+98h+arg_8]
0x180006033  add     rsp, 70h
0x180006037  pop     r15
0x180006039  pop     r14
0x18000603b  pop     rdi
0x18000603c  pop     rsi
0x18000603d  pop     rbp
0x18000603e  retn
```

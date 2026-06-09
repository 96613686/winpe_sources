# Microsoft::WRL::Details::GetActivationFactory<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180005e18`
- end: `0x180005f81`
- name: `??$GetActivationFactory@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005e00`

## callees

- `0x180004170`
- `0x180005e18`
- `0x1800076e4`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180005e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180005e52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180005e68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180005e68`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180005f58`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180005f58`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005f19`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005f19`

## string_xrefs

- `0x180005f21`: `activatibleClassId`

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
          v19 = 2;
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
0x180005e18  mov     [rsp+arg_8], rbx
0x180005e1d  push    rbp
0x180005e1e  push    rsi
0x180005e1f  push    rdi
0x180005e20  push    r14
0x180005e22  push    r15
0x180005e24  sub     rsp, 70h
0x180005e28  mov     rax, cs:__security_cookie
0x180005e2f  xor     rax, rsp
0x180005e32  mov     [rsp+98h+var_38], rax
0x180005e37  mov     r14, r9
0x180005e3a  mov     rdi, r8
0x180005e3d  mov     rsi, rcx
0x180005e40  mov     qword ptr [r9], 0
0x180005e47  mov     [rsp+98h+hasEmbedNull], 0
0x180005e4f  mov     rcx, r8; string
0x180005e52  call    cs:__imp_WindowsIsStringEmpty
0x180005e58  test    eax, eax
0x180005e5a  jnz     loc_180005F21
0x180005e60  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180005e65  mov     rcx, rdi; string
0x180005e68  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180005e6e  test    eax, eax
0x180005e70  js      loc_180005F21
0x180005e76  cmp     [rsp+98h+hasEmbedNull], 1
0x180005e7b  jz      loc_180005F21
0x180005e81  xor     edx, edx; length
0x180005e83  mov     rcx, rdi; string
0x180005e86  call    cs:__imp_WindowsGetStringRawBuffer
0x180005e8c  mov     r15, rax
0x180005e8f  mov     rcx, [rsi]
0x180005e92  mov     rax, [rcx+28h]
0x180005e96  mov     rcx, rsi
0x180005e99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e9e  lea     rbx, [rax+8]
0x180005ea2  mov     rcx, [rsi]
0x180005ea5  mov     rax, [rcx+30h]
0x180005ea9  mov     rcx, rsi
0x180005eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb1  mov     rbp, rax
0x180005eb4  cmp     rbx, rbp
0x180005eb7  jnb     short loc_180005F0F
0x180005eb9  mov     rax, [rbx]
0x180005ebc  test    rax, rax
0x180005ebf  jz      short loc_180005EEA
0x180005ec1  mov     rax, [rax+8]
0x180005ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eca  mov     rcx, r15
0x180005ecd  sub     rax, r15
0x180005ed0  movzx   edx, word ptr [rcx]
0x180005ed3  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180005ed8  sub     edx, r8d
0x180005edb  jnz     short loc_180005EE6
0x180005edd  add     rcx, 2
0x180005ee1  test    r8d, r8d
0x180005ee4  jnz     short loc_180005ED0
0x180005ee6  test    edx, edx
0x180005ee8  jz      short loc_180005EF0
0x180005eea  add     rbx, 8
0x180005eee  jmp     short loc_180005EB4
0x180005ef0  mov     [rsp+98h+var_64], 2
0x180005ef8  mov     [rsp+98h+SRWLock], r14; SRWLock
0x180005efd  mov     r9, [rbx]; struct _GUID *
0x180005f00  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180005f05  mov     rcx, rsi; this
0x180005f08  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180005f0d  jmp     short loc_180005F60
0x180005f0f  mov     rdx, rdi
0x180005f12  mov     ebx, 80040111h
0x180005f17  mov     ecx, ebx
0x180005f19  call    cs:__imp_RoOriginateError
0x180005f1f  jmp     short loc_180005F5E
0x180005f21  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180005f28  movups  [rsp+98h+var_60], xmm0
0x180005f2d  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180005f34  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180005f39  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180005f41  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180005f47  lea     r8, [rsp+98h+var_60]
0x180005f4c  mov     edx, 12h
0x180005f51  mov     ebx, 80070057h
0x180005f56  mov     ecx, ebx
0x180005f58  call    cs:__imp_RoOriginateErrorW
0x180005f5e  mov     eax, ebx
0x180005f60  mov     rcx, [rsp+98h+var_38]
0x180005f65  xor     rcx, rsp; StackCookie
0x180005f68  call    __security_check_cookie
0x180005f6d  mov     rbx, [rsp+98h+arg_8]
0x180005f75  add     rsp, 70h
0x180005f79  pop     r15
0x180005f7b  pop     r14
0x180005f7d  pop     rdi
0x180005f7e  pop     rsi
0x180005f7f  pop     rbp
0x180005f80  retn
```

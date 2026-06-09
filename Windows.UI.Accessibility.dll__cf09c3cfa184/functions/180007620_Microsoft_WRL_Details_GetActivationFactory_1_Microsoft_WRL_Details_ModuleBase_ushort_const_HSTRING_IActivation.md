# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x180007620`
- end: `0x180007789`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800082b8`

## callees

- `0x180003980`
- `0x180007620`
- `0x180007a84`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180007760`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180007760`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180007721`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180007721`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000768e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000768e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180007670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180007670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000765a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000765a`

## string_xrefs

- `0x180007729`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::GetActivationFactory<1>(
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
0x180007620  mov     [rsp+arg_8], rbx
0x180007625  push    rbp
0x180007626  push    rsi
0x180007627  push    rdi
0x180007628  push    r14
0x18000762a  push    r15
0x18000762c  sub     rsp, 70h
0x180007630  mov     rax, cs:__security_cookie
0x180007637  xor     rax, rsp
0x18000763a  mov     [rsp+98h+var_38], rax
0x18000763f  mov     r14, r9
0x180007642  mov     rdi, r8
0x180007645  mov     rsi, rcx
0x180007648  mov     qword ptr [r9], 0
0x18000764f  mov     [rsp+98h+hasEmbedNull], 0
0x180007657  mov     rcx, r8; string
0x18000765a  call    cs:__imp_WindowsIsStringEmpty
0x180007660  test    eax, eax
0x180007662  jnz     loc_180007729
0x180007668  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x18000766d  mov     rcx, rdi; string
0x180007670  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180007676  test    eax, eax
0x180007678  js      loc_180007729
0x18000767e  cmp     [rsp+98h+hasEmbedNull], 1
0x180007683  jz      loc_180007729
0x180007689  xor     edx, edx; length
0x18000768b  mov     rcx, rdi; string
0x18000768e  call    cs:__imp_WindowsGetStringRawBuffer
0x180007694  mov     r15, rax
0x180007697  mov     rcx, [rsi]
0x18000769a  mov     rax, [rcx+28h]
0x18000769e  mov     rcx, rsi
0x1800076a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076a6  lea     rbx, [rax+8]
0x1800076aa  mov     rcx, [rsi]
0x1800076ad  mov     rax, [rcx+30h]
0x1800076b1  mov     rcx, rsi
0x1800076b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076b9  mov     rbp, rax
0x1800076bc  cmp     rbx, rbp
0x1800076bf  jnb     short loc_180007717
0x1800076c1  mov     rax, [rbx]
0x1800076c4  test    rax, rax
0x1800076c7  jz      short loc_1800076F2
0x1800076c9  mov     rax, [rax+8]
0x1800076cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076d2  mov     rcx, r15
0x1800076d5  sub     rax, r15
0x1800076d8  movzx   edx, word ptr [rcx]
0x1800076db  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x1800076e0  sub     edx, r8d
0x1800076e3  jnz     short loc_1800076EE
0x1800076e5  add     rcx, 2
0x1800076e9  test    r8d, r8d
0x1800076ec  jnz     short loc_1800076D8
0x1800076ee  test    edx, edx
0x1800076f0  jz      short loc_1800076F8
0x1800076f2  add     rbx, 8
0x1800076f6  jmp     short loc_1800076BC
0x1800076f8  mov     [rsp+98h+var_64], 1
0x180007700  mov     [rsp+98h+SRWLock], r14; SRWLock
0x180007705  mov     r9, [rbx]; struct _GUID *
0x180007708  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x18000770d  mov     rcx, rsi; this
0x180007710  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x180007715  jmp     short loc_180007768
0x180007717  mov     rdx, rdi
0x18000771a  mov     ebx, 80040111h
0x18000771f  mov     ecx, ebx
0x180007721  call    cs:__imp_RoOriginateError
0x180007727  jmp     short loc_180007766
0x180007729  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180007730  movups  [rsp+98h+var_60], xmm0
0x180007735  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18000773c  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180007741  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180007749  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x18000774f  lea     r8, [rsp+98h+var_60]
0x180007754  mov     edx, 12h
0x180007759  mov     ebx, 80070057h
0x18000775e  mov     ecx, ebx
0x180007760  call    cs:__imp_RoOriginateErrorW
0x180007766  mov     eax, ebx
0x180007768  mov     rcx, [rsp+98h+var_38]
0x18000776d  xor     rcx, rsp; StackCookie
0x180007770  call    __security_check_cookie
0x180007775  mov     rbx, [rsp+98h+arg_8]
0x18000777d  add     rsp, 70h
0x180007781  pop     r15
0x180007783  pop     r14
0x180007785  pop     rdi
0x180007786  pop     rsi
0x180007787  pop     rbp
0x180007788  retn
```

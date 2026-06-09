# Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::GetActivationFactory(HSTRING__ *,IActivationFactory * *,ushort const *)

- ea: `0x180013854`
- end: `0x1800139c3`
- name: `?GetActivationFactory@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@PEBG@Z`
- size: `367`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800175cc`

## callees

- `0x1800028f0`
- `0x180013854`
- `0x1800139cc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180013939`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180013939`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180013999`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180013999`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800138a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800138a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001388e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001388e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800138c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800138c2`

## string_xrefs

- `0x180013962`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::GetActivationFactory(
        Microsoft::WRL::Details *this,
        HSTRING string,
        struct Microsoft::WRL::Details::CreatorMap *a3)
{
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v7; // rbx
  unsigned __int64 v8; // rbp
  __int64 v9; // rax
  unsigned __int16 *v10; // rcx
  __int64 v11; // rax
  unsigned int *v12; // r8
  int v13; // edx
  unsigned int v14; // ebx
  struct IUnknown **v16; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v18; // [rsp+34h] [rbp-64h] BYREF
  __int128 v19; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v20[22]; // [rsp+48h] [rbp-50h]

  *(_QWORD *)a3 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v19 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v20 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v20[14] = *(_QWORD *)L"sId";
    v14 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v19);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v7 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 40LL))(this)
                               + 8);
    v8 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)this + 48LL))(this);
    if ( (unsigned __int64)v7 >= v8 )
    {
LABEL_11:
      v14 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *v7 )
        {
          v9 = (*(__int64 (**)(void))(*v7)->Data4)();
          v10 = (unsigned __int16 *)StringRawBuffer;
          v11 = v9 - (_QWORD)StringRawBuffer;
          do
          {
            v12 = (unsigned int *)*(unsigned __int16 *)((char *)v10 + v11);
            v13 = *v10 - (_DWORD)v12;
            if ( v13 )
              break;
            ++v10;
          }
          while ( (_DWORD)v12 );
          if ( !v13 )
            break;
        }
        if ( (unsigned __int64)++v7 >= v8 )
          goto LABEL_11;
      }
      v18 = 1;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             this,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v18,
                             v12,
                             *v7,
                             a3,
                             v16);
    }
  }
  return v14;
}

```

## disassembly

```asm
0x180013854  mov     [rsp+arg_18], rbx
0x180013859  push    rbp
0x18001385a  push    rsi
0x18001385b  push    rdi
0x18001385c  push    r14
0x18001385e  push    r15
0x180013860  sub     rsp, 70h
0x180013864  mov     rax, cs:__security_cookie
0x18001386b  xor     rax, rsp
0x18001386e  mov     [rsp+98h+var_38], rax
0x180013873  mov     r14, r8
0x180013876  mov     rdi, rdx
0x180013879  mov     rsi, rcx
0x18001387c  mov     qword ptr [r8], 0
0x180013883  mov     [rsp+98h+hasEmbedNull], 0
0x18001388b  mov     rcx, rdx; string
0x18001388e  call    cs:__imp_WindowsIsStringEmpty
0x180013894  test    eax, eax
0x180013896  jnz     loc_180013962
0x18001389c  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x1800138a1  mov     rcx, rdi; string
0x1800138a4  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800138aa  test    eax, eax
0x1800138ac  js      loc_180013962
0x1800138b2  cmp     [rsp+98h+hasEmbedNull], 1
0x1800138b7  jz      loc_180013962
0x1800138bd  xor     edx, edx; length
0x1800138bf  mov     rcx, rdi; string
0x1800138c2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800138c8  mov     r15, rax
0x1800138cb  mov     rcx, [rsi]
0x1800138ce  mov     rax, [rcx+28h]
0x1800138d2  mov     rcx, rsi
0x1800138d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138da  lea     rbx, [rax+8]
0x1800138de  mov     rcx, [rsi]
0x1800138e1  mov     rax, [rcx+30h]
0x1800138e5  mov     rcx, rsi
0x1800138e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138ed  mov     rbp, rax
0x1800138f0  cmp     rbx, rax
0x1800138f3  jnb     short loc_18001392F
0x1800138f5  mov     rax, [rbx]
0x1800138f8  test    rax, rax
0x1800138fb  jz      short loc_180013926
0x1800138fd  mov     rax, [rax+8]
0x180013901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013906  mov     rcx, r15
0x180013909  sub     rax, r15
0x18001390c  movzx   edx, word ptr [rcx]
0x18001390f  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180013914  sub     edx, r8d
0x180013917  jnz     short loc_180013922
0x180013919  add     rcx, 2
0x18001391d  test    r8d, r8d
0x180013920  jnz     short loc_18001390C
0x180013922  test    edx, edx
0x180013924  jz      short loc_180013941
0x180013926  add     rbx, 8
0x18001392a  cmp     rbx, rbp
0x18001392d  jb      short loc_1800138F5
0x18001392f  mov     rdx, rdi
0x180013932  mov     ebx, 80040111h
0x180013937  mov     ecx, ebx
0x180013939  call    cs:__imp_RoOriginateError
0x18001393f  jmp     short loc_1800139A0
0x180013941  mov     [rsp+98h+var_64], 1
0x180013949  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x18001394e  mov     r9, [rbx]; struct _GUID *
0x180013951  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180013956  mov     rcx, rsi; this
0x180013959  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18001395e  mov     ebx, eax
0x180013960  jmp     short loc_1800139A0
0x180013962  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180013969  movups  [rsp+98h+var_60], xmm0
0x18001396e  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180013975  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x18001397a  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180013982  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180013988  lea     r8, [rsp+98h+var_60]
0x18001398d  mov     edx, 12h
0x180013992  mov     ebx, 80070057h
0x180013997  mov     ecx, ebx
0x180013999  call    cs:__imp_RoOriginateErrorW
0x18001399f  nop
0x1800139a0  mov     eax, ebx
0x1800139a2  mov     rcx, [rsp+98h+var_38]
0x1800139a7  xor     rcx, rsp; StackCookie
0x1800139aa  call    __security_check_cookie
0x1800139af  mov     rbx, [rsp+98h+arg_18]
0x1800139b7  add     rsp, 70h
0x1800139bb  pop     r15
0x1800139bd  pop     r14
0x1800139bf  pop     rdi
0x1800139c0  pop     rsi
0x1800139c1  pop     rbp
0x1800139c2  retn
```

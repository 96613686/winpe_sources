# Microsoft::WRL::Details::ActivationFactoryCallback<2>(HSTRING__ *,IActivationFactory * *)

- ea: `0x180002250`
- end: `0x1800023c0`
- name: `??$ActivationFactoryCallback@$01@Details@WRL@Microsoft@@YAJPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(HSTRING string, struct Microsoft::WRL::Details::CreatorMap *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001620`
- `0x180002250`
- `0x180004f14`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000228b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000228b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800022a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800022a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800022bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800022bf`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002336`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180002336`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180002396`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180002396`

## string_xrefs

- `0x18000235f`: `activatibleClassId`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ActivationFactoryCallback<2>(
        HSTRING string,
        struct Microsoft::WRL::Details::CreatorMap *a2)
{
  Microsoft::WRL::Details *v4; // rsi
  PCWSTR StringRawBuffer; // r15
  const struct _GUID **v6; // rbx
  unsigned __int64 v7; // rbp
  __int64 v8; // rax
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  unsigned int *v11; // r8
  int v12; // edx
  unsigned int v13; // ebx
  struct IUnknown **v15; // [rsp+28h] [rbp-70h]
  BOOL hasEmbedNull; // [rsp+30h] [rbp-68h] BYREF
  int v17; // [rsp+34h] [rbp-64h] BYREF
  __int128 v18; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v19[22]; // [rsp+48h] [rbp-50h]

  v4 = Microsoft::WRL::Details::ModuleBase::module_;
  *(_QWORD *)a2 = 0;
  hasEmbedNull = 0;
  if ( WindowsIsStringEmpty(string) || WindowsStringHasEmbeddedNull(string, &hasEmbedNull) < 0 || hasEmbedNull )
  {
    v18 = *(_OWORD *)L"activatibleClassId";
    *(_OWORD *)v19 = *(_OWORD *)L"bleClassId";
    *(_QWORD *)&v19[14] = *(_QWORD *)L"sId";
    v13 = -2147024809;
    RoOriginateErrorW(2147942487LL, 18, &v18);
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v6 = (const struct _GUID **)((*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v4 + 40LL))(v4) + 8);
    v7 = (*(__int64 (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v4 + 48LL))(v4);
    if ( (unsigned __int64)v6 >= v7 )
    {
LABEL_11:
      v13 = -2147221231;
      RoOriginateError(2147746065LL, string);
    }
    else
    {
      while ( 1 )
      {
        if ( *v6 )
        {
          v8 = (*(__int64 (**)(void))(*v6)->Data4)();
          v9 = (unsigned __int16 *)StringRawBuffer;
          v10 = v8 - (_QWORD)StringRawBuffer;
          do
          {
            v11 = (unsigned int *)*(unsigned __int16 *)((char *)v9 + v10);
            v12 = *v9 - (_DWORD)v11;
            if ( v12 )
              break;
            ++v9;
          }
          while ( (_DWORD)v11 );
          if ( !v12 )
            break;
        }
        if ( (unsigned __int64)++v6 >= v7 )
          goto LABEL_11;
      }
      v17 = 2;
      return (unsigned int)Microsoft::WRL::Details::GetCacheEntry(
                             v4,
                             (struct Microsoft::WRL::Details::ModuleBase *)&v17,
                             v11,
                             *v6,
                             a2,
                             v15);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180002250  mov     [rsp+arg_10], rbx
0x180002255  push    rbp
0x180002256  push    rsi
0x180002257  push    rdi
0x180002258  push    r14
0x18000225a  push    r15
0x18000225c  sub     rsp, 70h
0x180002260  mov     rax, cs:__security_cookie
0x180002267  xor     rax, rsp
0x18000226a  mov     [rsp+98h+var_38], rax
0x18000226f  mov     r14, rdx
0x180002272  mov     rdi, rcx
0x180002275  mov     rsi, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000227c  mov     qword ptr [rdx], 0
0x180002283  mov     [rsp+98h+hasEmbedNull], 0
0x18000228b  call    cs:__imp_WindowsIsStringEmpty
0x180002291  test    eax, eax
0x180002293  jnz     loc_18000235F
0x180002299  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x18000229e  mov     rcx, rdi; string
0x1800022a1  call    cs:__imp_WindowsStringHasEmbeddedNull
0x1800022a7  test    eax, eax
0x1800022a9  js      loc_18000235F
0x1800022af  cmp     [rsp+98h+hasEmbedNull], 1
0x1800022b4  jz      loc_18000235F
0x1800022ba  xor     edx, edx; length
0x1800022bc  mov     rcx, rdi; string
0x1800022bf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800022c5  mov     r15, rax
0x1800022c8  mov     rcx, [rsi]
0x1800022cb  mov     rax, [rcx+28h]
0x1800022cf  mov     rcx, rsi
0x1800022d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022d7  lea     rbx, [rax+8]
0x1800022db  mov     rcx, [rsi]
0x1800022de  mov     rax, [rcx+30h]
0x1800022e2  mov     rcx, rsi
0x1800022e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ea  mov     rbp, rax
0x1800022ed  cmp     rbx, rax
0x1800022f0  jnb     short loc_18000232C
0x1800022f2  mov     rax, [rbx]
0x1800022f5  test    rax, rax
0x1800022f8  jz      short loc_180002323
0x1800022fa  mov     rax, [rax+8]
0x1800022fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002303  mov     rcx, r15
0x180002306  sub     rax, r15
0x180002309  movzx   edx, word ptr [rcx]
0x18000230c  movzx   r8d, word ptr [rcx+rax]; unsigned int *
0x180002311  sub     edx, r8d
0x180002314  jnz     short loc_18000231F
0x180002316  add     rcx, 2
0x18000231a  test    r8d, r8d
0x18000231d  jnz     short loc_180002309
0x18000231f  test    edx, edx
0x180002321  jz      short loc_18000233E
0x180002323  add     rbx, 8
0x180002327  cmp     rbx, rbp
0x18000232a  jb      short loc_1800022F2
0x18000232c  mov     rdx, rdi
0x18000232f  mov     ebx, 80040111h
0x180002334  mov     ecx, ebx
0x180002336  call    cs:__imp_RoOriginateError
0x18000233c  jmp     short loc_18000239D
0x18000233e  mov     [rsp+98h+var_64], 2
0x180002346  mov     [rsp+98h+var_78], r14; struct Microsoft::WRL::Details::CreatorMap *
0x18000234b  mov     r9, [rbx]; struct _GUID *
0x18000234e  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x180002353  mov     rcx, rsi; this
0x180002356  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18000235b  mov     ebx, eax
0x18000235d  jmp     short loc_18000239D
0x18000235f  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x180002366  movups  [rsp+98h+var_60], xmm0
0x18000236b  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x180002372  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180002377  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x18000237f  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x180002385  lea     r8, [rsp+98h+var_60]
0x18000238a  mov     edx, 12h
0x18000238f  mov     ebx, 80070057h
0x180002394  mov     ecx, ebx
0x180002396  call    cs:__imp_RoOriginateErrorW
0x18000239c  nop
0x18000239d  mov     eax, ebx
0x18000239f  mov     rcx, [rsp+98h+var_38]
0x1800023a4  xor     rcx, rsp; StackCookie
0x1800023a7  call    __security_check_cookie
0x1800023ac  mov     rbx, [rsp+98h+arg_10]
0x1800023b4  add     rsp, 70h
0x1800023b8  pop     r15
0x1800023ba  pop     r14
0x1800023bc  pop     rdi
0x1800023bd  pop     rsi
0x1800023be  pop     rbp
0x1800023bf  retn
```

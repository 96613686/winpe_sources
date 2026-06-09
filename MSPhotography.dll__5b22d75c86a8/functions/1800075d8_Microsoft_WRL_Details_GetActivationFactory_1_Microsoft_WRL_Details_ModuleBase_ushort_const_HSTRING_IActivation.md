# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x1800075d8`
- end: `0x180007748`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009080`

## callees

- `0x180002420`
- `0x1800075d8`
- `0x18000916c`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000771f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000771f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800076e0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800076e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007646`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007646`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180007628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180007628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180007612`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180007612`

## string_xrefs

- `0x1800076e8`: `activatibleClassId`

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
0x1800075d8  mov     [rsp+arg_8], rbx
0x1800075dd  push    rbp
0x1800075de  push    rsi
0x1800075df  push    rdi
0x1800075e0  push    r14
0x1800075e2  push    r15
0x1800075e4  sub     rsp, 70h
0x1800075e8  mov     rax, cs:__security_cookie
0x1800075ef  xor     rax, rsp
0x1800075f2  mov     [rsp+98h+var_38], rax
0x1800075f7  mov     r14, r9
0x1800075fa  mov     rdi, r8
0x1800075fd  mov     rsi, rcx
0x180007600  mov     qword ptr [r9], 0
0x180007607  mov     [rsp+98h+hasEmbedNull], 0
0x18000760f  mov     rcx, r8; string
0x180007612  call    cs:__imp_WindowsIsStringEmpty
0x180007618  test    eax, eax
0x18000761a  jnz     loc_1800076E8
0x180007620  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x180007625  mov     rcx, rdi; string
0x180007628  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18000762e  test    eax, eax
0x180007630  js      loc_1800076E8
0x180007636  cmp     [rsp+98h+hasEmbedNull], 1
0x18000763b  jz      loc_1800076E8
0x180007641  xor     edx, edx; length
0x180007643  mov     rcx, rdi; string
0x180007646  call    cs:__imp_WindowsGetStringRawBuffer
0x18000764c  mov     r15, rax
0x18000764f  mov     rcx, [rsi]
0x180007652  mov     rax, [rcx+28h]
0x180007656  mov     rcx, rsi
0x180007659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000765e  lea     rbx, [rax+8]
0x180007662  mov     rcx, [rsi]
0x180007665  mov     rax, [rcx+30h]
0x180007669  mov     rcx, rsi
0x18000766c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007671  mov     rbp, rax
0x180007674  cmp     rbx, rbp
0x180007677  jnb     short loc_1800076D6
0x180007679  mov     rax, [rbx]
0x18000767c  test    rax, rax
0x18000767f  jz      short loc_1800076AA
0x180007681  mov     rax, [rax+8]
0x180007685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000768a  mov     rcx, r15
0x18000768d  sub     rax, r15
0x180007690  movzx   edx, word ptr [rcx]
0x180007693  movzx   r8d, word ptr [rcx+rax]
0x180007698  sub     edx, r8d
0x18000769b  jnz     short loc_1800076A6
0x18000769d  add     rcx, 2
0x1800076a1  test    r8d, r8d
0x1800076a4  jnz     short loc_180007690
0x1800076a6  test    edx, edx
0x1800076a8  jz      short loc_1800076B0
0x1800076aa  add     rbx, 8
0x1800076ae  jmp     short loc_180007674
0x1800076b0  mov     [rsp+98h+var_64], 1
0x1800076b8  mov     [rsp+98h+Ptr], r14; Ptr
0x1800076bd  mov     r9, [rbx]; struct _GUID *
0x1800076c0  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x1800076c7  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x1800076cc  mov     rcx, rsi; this
0x1800076cf  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x1800076d4  jmp     short loc_180007727
0x1800076d6  mov     rdx, rdi
0x1800076d9  mov     ebx, 80040111h
0x1800076de  mov     ecx, ebx
0x1800076e0  call    cs:__imp_RoOriginateError
0x1800076e6  jmp     short loc_180007725
0x1800076e8  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x1800076ef  movups  [rsp+98h+var_60], xmm0
0x1800076f4  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x1800076fb  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x180007700  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x180007708  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x18000770e  lea     r8, [rsp+98h+var_60]
0x180007713  mov     edx, 12h
0x180007718  mov     ebx, 80070057h
0x18000771d  mov     ecx, ebx
0x18000771f  call    cs:__imp_RoOriginateErrorW
0x180007725  mov     eax, ebx
0x180007727  mov     rcx, [rsp+98h+var_38]
0x18000772c  xor     rcx, rsp; StackCookie
0x18000772f  call    __security_check_cookie
0x180007734  mov     rbx, [rsp+98h+arg_8]
0x18000773c  add     rsp, 70h
0x180007740  pop     r15
0x180007742  pop     r14
0x180007744  pop     rdi
0x180007745  pop     rsi
0x180007746  pop     rbp
0x180007747  retn
```

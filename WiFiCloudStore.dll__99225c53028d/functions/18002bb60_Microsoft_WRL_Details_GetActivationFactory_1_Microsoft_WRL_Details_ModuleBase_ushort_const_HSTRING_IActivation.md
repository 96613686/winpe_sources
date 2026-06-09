# Microsoft::WRL::Details::GetActivationFactory<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,HSTRING__ *,IActivationFactory * *)

- ea: `0x18002bb60`
- end: `0x18002bcd0`
- name: `??$GetActivationFactory@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGPEAUHSTRING__@@PEAPEAUIActivationFactory@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details *this, __int64, HSTRING, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002cc60`

## callees

- `0x18001eb6c`
- `0x18002a030`
- `0x18002bb60`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bbce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bbce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002bb9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002bb9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18002bbb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18002bbb0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002bc68`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18002bc68`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18002bca7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18002bca7`

## string_xrefs

- `0x18002bc70`: `activatibleClassId`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18002bb60  mov     [rsp+arg_8], rbx
0x18002bb65  push    rbp
0x18002bb66  push    rsi
0x18002bb67  push    rdi
0x18002bb68  push    r14
0x18002bb6a  push    r15
0x18002bb6c  sub     rsp, 70h
0x18002bb70  mov     rax, cs:__security_cookie
0x18002bb77  xor     rax, rsp
0x18002bb7a  mov     [rsp+98h+var_38], rax
0x18002bb7f  mov     r14, r9
0x18002bb82  mov     rdi, r8
0x18002bb85  mov     rsi, rcx
0x18002bb88  mov     qword ptr [r9], 0
0x18002bb8f  mov     [rsp+98h+hasEmbedNull], 0
0x18002bb97  mov     rcx, r8; string
0x18002bb9a  call    cs:__imp_WindowsIsStringEmpty
0x18002bba0  test    eax, eax
0x18002bba2  jnz     loc_18002BC70
0x18002bba8  lea     rdx, [rsp+98h+hasEmbedNull]; hasEmbedNull
0x18002bbad  mov     rcx, rdi; string
0x18002bbb0  call    cs:__imp_WindowsStringHasEmbeddedNull
0x18002bbb6  test    eax, eax
0x18002bbb8  js      loc_18002BC70
0x18002bbbe  cmp     [rsp+98h+hasEmbedNull], 1
0x18002bbc3  jz      loc_18002BC70
0x18002bbc9  xor     edx, edx; length
0x18002bbcb  mov     rcx, rdi; string
0x18002bbce  call    cs:__imp_WindowsGetStringRawBuffer
0x18002bbd4  mov     r15, rax
0x18002bbd7  mov     rcx, [rsi]
0x18002bbda  mov     rax, [rcx+28h]
0x18002bbde  mov     rcx, rsi
0x18002bbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbe6  lea     rbx, [rax+8]
0x18002bbea  mov     rcx, [rsi]
0x18002bbed  mov     rax, [rcx+30h]
0x18002bbf1  mov     rcx, rsi
0x18002bbf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbf9  mov     rbp, rax
0x18002bbfc  cmp     rbx, rbp
0x18002bbff  jnb     short loc_18002BC5E
0x18002bc01  mov     rax, [rbx]
0x18002bc04  test    rax, rax
0x18002bc07  jz      short loc_18002BC32
0x18002bc09  mov     rax, [rax+8]
0x18002bc0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc12  mov     rcx, r15
0x18002bc15  sub     rax, r15
0x18002bc18  movzx   edx, word ptr [rcx]
0x18002bc1b  movzx   r8d, word ptr [rcx+rax]
0x18002bc20  sub     edx, r8d
0x18002bc23  jnz     short loc_18002BC2E
0x18002bc25  add     rcx, 2
0x18002bc29  test    r8d, r8d
0x18002bc2c  jnz     short loc_18002BC18
0x18002bc2e  test    edx, edx
0x18002bc30  jz      short loc_18002BC38
0x18002bc32  add     rbx, 8
0x18002bc36  jmp     short loc_18002BBFC
0x18002bc38  mov     [rsp+98h+var_64], 1
0x18002bc40  mov     [rsp+98h+Ptr], r14; Ptr
0x18002bc45  mov     r9, [rbx]; struct _GUID *
0x18002bc48  lea     r8, _GUID_00000035_0000_0000_c000_000000000046; unsigned int *
0x18002bc4f  lea     rdx, [rsp+98h+var_64]; struct Microsoft::WRL::Details::ModuleBase *
0x18002bc54  mov     rcx, rsi; this
0x18002bc57  call    ?GetCacheEntry@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEAIAEBU_GUID@@PEBUCreatorMap@123@PEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::GetCacheEntry(Microsoft::WRL::Details::ModuleBase *,uint *,_GUID const &,Microsoft::WRL::Details::CreatorMap const *,IUnknown * *)
0x18002bc5c  jmp     short loc_18002BCAF
0x18002bc5e  mov     rdx, rdi
0x18002bc61  mov     ebx, 80040111h
0x18002bc66  mov     ecx, ebx
0x18002bc68  call    cs:__imp_RoOriginateError
0x18002bc6e  jmp     short loc_18002BCAD
0x18002bc70  movups  xmm0, xmmword ptr cs:aActivatiblecla; "activatibleClassId"
0x18002bc77  movups  [rsp+98h+var_60], xmm0
0x18002bc7c  movups  xmm1, xmmword ptr cs:aActivatiblecla+10h; "bleClassId"
0x18002bc83  movups  xmmword ptr [rsp+98h+var_50], xmm1
0x18002bc88  movsd   xmm0, qword ptr cs:aActivatiblecla+1Eh; "sId"
0x18002bc90  movsd   qword ptr [rsp+98h+var_50+0Eh], xmm0
0x18002bc96  lea     r8, [rsp+98h+var_60]
0x18002bc9b  mov     edx, 12h
0x18002bca0  mov     ebx, 80070057h
0x18002bca5  mov     ecx, ebx
0x18002bca7  call    cs:__imp_RoOriginateErrorW
0x18002bcad  mov     eax, ebx
0x18002bcaf  mov     rcx, [rsp+98h+var_38]
0x18002bcb4  xor     rcx, rsp; StackCookie
0x18002bcb7  call    __security_check_cookie
0x18002bcbc  mov     rbx, [rsp+98h+arg_8]
0x18002bcc4  add     rsp, 70h
0x18002bcc8  pop     r15
0x18002bcca  pop     r14
0x18002bccc  pop     rdi
0x18002bccd  pop     rsi
0x18002bcce  pop     rbp
0x18002bccf  retn
```

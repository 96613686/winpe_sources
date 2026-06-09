# _anonymous_namespace_::RecolorSvgAttribute

- ea: `0x18002b9dc`
- end: `0x18002bb7a`
- name: `_anonymous_namespace_::RecolorSvgAttribute`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002bbf8`

## callees

- `0x180003980`
- `0x18000a6e0`
- `0x18000cf94`
- `0x18002b630`
- `0x18002b954`
- `0x18002b9dc`
- `0x180035010`

## string_xrefs

- `0x18002ba5d`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002bafb`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`
- `0x18002bb40`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\cursorutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::RecolorSvgAttribute(__int64 a1, __int64 a2, __int128 *a3)
{
  __int64 result; // rax
  int v7; // eax
  __int64 v8; // rbx
  int v9; // eax
  int v10; // eax
  int v11; // [rsp+20h] [rbp-29h]
  _QWORD v12[2]; // [rsp+30h] [rbp-19h] BYREF
  __int128 v13; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v14[16]; // [rsp+50h] [rbp+7h] BYREF
  __int128 v15; // [rsp+60h] [rbp+17h] BYREF
  __int128 v16; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  result = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)a1 + 152LL))(a1, a2, 0);
  if ( (_DWORD)result )
  {
    v12[0] = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v12);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, _QWORD *))(*(_QWORD *)a1 + 240LL))(
           a1,
           a2,
           &IID_ID2D1SvgPaint,
           v12);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB2,
        (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
        (const char *)(unsigned int)v7,
        v11);
    v15 = 0;
    (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v12[0] + 72LL))(v12[0], &v15);
    if ( *(float *)&v15 == 0.0
      && *((float *)&v15 + 1) == 0.0
      && *((float *)&v15 + 2) > 0.0
      && *((float *)&v15 + 2) < 0.1 )
    {
      v8 = v12[0];
      v13 = *a3;
      v16 = *(_OWORD *)anonymous_namespace_::GetBorderColor(v14, &v13);
      v9 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v8 + 64LL))(v8, &v16);
      if ( v9 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xBA,
          (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
          (const char *)(unsigned int)v9,
          v11);
    }
    else
    {
      v16 = v15;
      if ( (unsigned __int8)anonymous_namespace_::IsInteriorColor(&v16) )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v12[0] + 64LL))(v12[0], a3);
        if ( v10 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xBE,
            (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\cursorutils.cpp",
            (const char *)(unsigned int)v10,
            v11);
      }
    }
    return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v12);
  }
  return result;
}

```

## disassembly

```asm
0x18002b9dc  mov     [rsp-8+arg_18], rbx
0x18002b9e1  push    rbp
0x18002b9e2  push    rsi
0x18002b9e3  push    rdi
0x18002b9e4  lea     rbp, [rsp-47h]
0x18002b9e9  sub     rsp, 90h
0x18002b9f0  mov     rax, cs:__security_cookie
0x18002b9f7  xor     rax, rsp
0x18002b9fa  mov     [rbp+57h+var_20], rax
0x18002b9fe  mov     rsi, r8
0x18002ba01  mov     rdi, rdx
0x18002ba04  mov     rbx, rcx
0x18002ba07  mov     rax, [rcx]
0x18002ba0a  xor     r8d, r8d
0x18002ba0d  mov     rax, [rax+98h]
0x18002ba14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba19  test    eax, eax
0x18002ba1b  jz      loc_18002BB5B
0x18002ba21  mov     [rbp+57h+var_70], 0
0x18002ba29  lea     rcx, [rbp+57h+var_70]
0x18002ba2d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002ba32  mov     rax, [rbx]
0x18002ba35  lea     r9, [rbp+57h+var_70]
0x18002ba39  lea     r8, IID_ID2D1SvgPaint
0x18002ba40  mov     rdx, rdi
0x18002ba43  mov     rcx, rbx
0x18002ba46  mov     rax, [rax+0F0h]
0x18002ba4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba52  mov     rcx, [rbp+5Fh]; this
0x18002ba56  test    eax, eax
0x18002ba58  jns     short loc_18002BA6F
0x18002ba5a  mov     r9d, eax; char *
0x18002ba5d  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002ba64  mov     edx, 0B2h; void *
0x18002ba69  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002ba6f  xorps   xmm0, xmm0
0x18002ba72  movups  [rbp+57h+var_40], xmm0
0x18002ba76  mov     rcx, [rbp+57h+var_70]
0x18002ba7a  mov     rax, [rcx]
0x18002ba7d  lea     rdx, [rbp+57h+var_40]
0x18002ba81  mov     rax, [rax+48h]
0x18002ba85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba8a  xorps   xmm1, xmm1
0x18002ba8d  movss   xmm0, dword ptr [rbp+57h+var_40]
0x18002ba92  ucomiss xmm0, xmm1
0x18002ba95  jp      short loc_18002BB0D
0x18002ba97  jnz     short loc_18002BB0D
0x18002ba99  movss   xmm0, dword ptr [rbp+57h+var_40+4]
0x18002ba9e  ucomiss xmm0, xmm1
0x18002baa1  jp      short loc_18002BB0D
0x18002baa3  jnz     short loc_18002BB0D
0x18002baa5  movss   xmm2, dword ptr [rbp+57h+var_40+8]
0x18002baaa  comiss  xmm2, xmm1
0x18002baad  jbe     short loc_18002BB0D
0x18002baaf  movss   xmm0, cs:__real@3dcccccd
0x18002bab7  comiss  xmm0, xmm2
0x18002baba  jbe     short loc_18002BB0D
0x18002babc  mov     rbx, [rbp+57h+var_70]
0x18002bac0  movaps  xmm0, xmmword ptr [rsi]
0x18002bac3  movdqu  [rbp+57h+var_60], xmm0
0x18002bac8  lea     rdx, [rbp+57h+var_60]
0x18002bacc  lea     rcx, [rbp+57h+var_50]
0x18002bad0  call    _anonymous_namespace___GetBorderColor
0x18002bad5  movups  xmm0, xmmword ptr [rax]
0x18002bad8  movdqu  [rbp+57h+var_30], xmm0
0x18002badd  mov     rax, [rbx]
0x18002bae0  lea     rdx, [rbp+57h+var_30]
0x18002bae4  mov     rcx, rbx
0x18002bae7  mov     rax, [rax+40h]
0x18002baeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002baf0  mov     rcx, [rbp+5Fh]; this
0x18002baf4  test    eax, eax
0x18002baf6  jns     short loc_18002BB52
0x18002baf8  mov     r9d, eax; char *
0x18002bafb  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002bb02  mov     edx, 0BAh; void *
0x18002bb07  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002bb0d  movups  xmm0, [rbp+57h+var_40]
0x18002bb11  movups  [rbp+57h+var_30], xmm0
0x18002bb15  lea     rcx, [rbp+57h+var_30]
0x18002bb19  call    _anonymous_namespace___IsInteriorColor
0x18002bb1e  test    al, al
0x18002bb20  jz      short loc_18002BB52
0x18002bb22  mov     rcx, [rbp+57h+var_70]
0x18002bb26  mov     rax, [rcx]
0x18002bb29  mov     rdx, rsi
0x18002bb2c  mov     rax, [rax+40h]
0x18002bb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb35  mov     rcx, [rbp+5Fh]; this
0x18002bb39  test    eax, eax
0x18002bb3b  jns     short loc_18002BB52
0x18002bb3d  mov     r9d, eax; char *
0x18002bb40  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002bb47  mov     edx, 0BEh; void *
0x18002bb4c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002bb52  lea     rcx, [rbp+57h+var_70]
0x18002bb56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bb5b  mov     rcx, [rbp+57h+var_20]
0x18002bb5f  xor     rcx, rsp; StackCookie
0x18002bb62  call    __security_check_cookie
0x18002bb67  mov     rbx, [rsp+0A0h+arg_18]
0x18002bb6f  add     rsp, 90h
0x18002bb76  pop     rdi
0x18002bb77  pop     rsi
0x18002bb78  pop     rbp
0x18002bb79  retn
```

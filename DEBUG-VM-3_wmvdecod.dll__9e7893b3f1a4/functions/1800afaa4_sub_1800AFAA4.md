# sub_1800AFAA4

- ea: `0x1800afaa4`
- end: `0x1800afc07`
- name: `sub_1800AFAA4`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800b2a2c`

## callees

- `0x1800013a8`
- `0x1800019b0`
- `0x18008c580`
- `0x1800994a0`
- `0x1800afaa4`
- `0x18020cab0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800afbd4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x1800afbd4`

## string_xrefs

- `0x1800afb6f`: `CWMVDXVADecoderOTA::CreateInstance`

## pseudocode

```c
__int64 __fastcall sub_1800AFAA4(__int64 *a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v5; // rcx
  __int64 v6; // r8
  GUID *v7; // rax
  __int64 v8; // rcx
  int v9; // r8d
  int v10; // r9d
  int v12; // [rsp+50h] [rbp-21h] BYREF
  int v13; // [rsp+54h] [rbp-1Dh] BYREF
  __int64 v14; // [rsp+58h] [rbp-19h] BYREF
  GUID *v15; // [rsp+60h] [rbp-11h] BYREF
  const wchar_t *v16; // [rsp+68h] [rbp-9h] BYREF
  _QWORD v17[2]; // [rsp+70h] [rbp-1h] BYREF
  GUID v18; // [rsp+80h] [rbp+Fh] BYREF

  v3 = *a1;
  if ( !v3 || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 320LL))(v3, qword_18021C578) )
  {
    v5 = *a1;
    v6 = 0;
    v18 = Buf2;
    if ( v5 )
    {
      v7 = (GUID *)(*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD))(*(_QWORD *)v5 + 280LL))(v5, v17, 0);
      v8 = *a1;
      v18 = *v7;
      v6 = (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v8 + 296LL))(v8);
    }
    if ( (unsigned int)dword_180281118 > 5 && (unsigned __int8)sub_1800019B0(v5, 0x200000000000LL, v6) )
    {
      v14 = a2;
      v15 = &v18;
      v12 = v9;
      v17[0] = "CWMVDXVADecoderOTA::CreateInstance";
      v16 = L"CWMVDXVADecoderOTA creation failed, system ran out of memory";
      v13 = -2147024882;
      sub_1800013A8(
        (unsigned int)v17,
        (unsigned int)&unk_180277CA0,
        v9,
        v10,
        (__int64)v17,
        (__int64)&v13,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v12,
        (__int64)&v14);
    }
  }
  RoOriginateErrorW(2147942414LL, 60, L"CWMVDXVADecoderOTA creation failed, system ran out of memory");
  sub_18008C580(a1);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800afaa4  push    rbp
0x1800afaa6  push    rbx
0x1800afaa7  push    rdi
0x1800afaa8  push    r14
0x1800afaaa  lea     rbp, [rsp-37h]
0x1800afaaf  sub     rsp, 0A8h
0x1800afab6  mov     rax, cs:__security_cookie
0x1800afabd  xor     rax, rsp
0x1800afac0  mov     [rbp+4Fh+var_30], rax
0x1800afac4  mov     rbx, rcx
0x1800afac7  lea     r14, aCwmvdxvadecode_0; "CWMVDXVADecoderOTA creation failed, sys"...
0x1800aface  mov     rcx, [rcx]
0x1800afad1  mov     rdi, rdx
0x1800afad4  test    rcx, rcx
0x1800afad7  jz      short loc_1800AFAF8
0x1800afad9  mov     rax, [rcx]
0x1800afadc  lea     rdx, qword_18021C578
0x1800afae3  mov     rax, [rax+140h]
0x1800afaea  call    cs:__guard_dispatch_icall_fptr
0x1800afaf0  test    eax, eax
0x1800afaf2  jnz     loc_1800AFBC7
0x1800afaf8  movups  xmm0, xmmword ptr cs:Buf2.Data1
0x1800afaff  mov     rcx, [rbx]
0x1800afb02  xor     r8d, r8d
0x1800afb05  movdqu  [rbp+4Fh+var_40], xmm0
0x1800afb0a  test    rcx, rcx
0x1800afb0d  jz      short loc_1800AFB41
0x1800afb0f  mov     rax, [rcx]
0x1800afb12  lea     rdx, [rbp+4Fh+var_50]
0x1800afb16  mov     rax, [rax+118h]
0x1800afb1d  call    cs:__guard_dispatch_icall_fptr
0x1800afb23  mov     rcx, [rbx]
0x1800afb26  movups  xmm0, xmmword ptr [rax]
0x1800afb29  movdqu  [rbp+4Fh+var_40], xmm0
0x1800afb2e  mov     rax, [rcx]
0x1800afb31  mov     rax, [rax+128h]
0x1800afb38  call    cs:__guard_dispatch_icall_fptr
0x1800afb3e  mov     r8d, eax
0x1800afb41  mov     eax, cs:dword_180281118
0x1800afb47  cmp     eax, 5
0x1800afb4a  jbe     short loc_1800AFBC7
0x1800afb4c  mov     rdx, 200000000000h
0x1800afb56  call    sub_1800019B0
0x1800afb5b  test    al, al
0x1800afb5d  jz      short loc_1800AFBC7
0x1800afb5f  lea     rax, [rbp+4Fh+var_40]
0x1800afb63  mov     [rbp+4Fh+var_68], rdi
0x1800afb67  mov     [rbp+4Fh+var_60], rax
0x1800afb6b  lea     rcx, [rbp+4Fh+var_50]
0x1800afb6f  lea     rax, aCwmvdxvadecode_1; "CWMVDXVADecoderOTA::CreateInstance"
0x1800afb76  mov     [rbp+4Fh+var_70], r8d
0x1800afb7a  mov     [rbp+4Fh+var_50], rax
0x1800afb7e  lea     rdx, unk_180277CA0
0x1800afb85  lea     rax, [rbp+4Fh+var_68]
0x1800afb89  mov     [rbp+4Fh+var_58], r14
0x1800afb8d  mov     [rsp+0C0h+var_78], rax
0x1800afb92  lea     rax, [rbp+4Fh+var_70]
0x1800afb96  mov     [rsp+0C0h+var_80], rax
0x1800afb9b  lea     rax, [rbp+4Fh+var_60]
0x1800afb9f  mov     [rsp+0C0h+var_88], rax
0x1800afba4  lea     rax, [rbp+4Fh+var_58]
0x1800afba8  mov     [rsp+0C0h+var_90], rax
0x1800afbad  lea     rax, [rbp+4Fh+var_6C]
0x1800afbb1  mov     [rsp+0C0h+var_98], rax
0x1800afbb6  mov     [rsp+0C0h+var_A0], rcx
0x1800afbbb  mov     [rbp+4Fh+var_6C], 8007000Eh
0x1800afbc2  call    sub_1800013A8
0x1800afbc7  mov     r8, r14
0x1800afbca  mov     edx, 3Ch ; '<'
0x1800afbcf  mov     ecx, 8007000Eh
0x1800afbd4  call    cs:RoOriginateErrorW
0x1800afbdb  nop     dword ptr [rax+rax+00h]
0x1800afbe0  mov     rcx, rbx
0x1800afbe3  call    sub_18008C580
0x1800afbe8  mov     eax, 8007000Eh
0x1800afbed  mov     rcx, [rbp+4Fh+var_30]
0x1800afbf1  xor     rcx, rsp; StackCookie
0x1800afbf4  call    __security_check_cookie
0x1800afbf9  add     rsp, 0A8h
0x1800afc00  pop     r14
0x1800afc02  pop     rdi
0x1800afc03  pop     rbx
0x1800afc04  pop     rbp
0x1800afc05  retn
```

# CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(IMFMediaType *)

- ea: `0x18001e550`
- end: `0x18001e6bc`
- name: `?ConvertDMORGBFormatToMFRGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z`
- size: `364`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18001da00`
- `0x18001daf0`
- `0x1800280ac`
- `0x18002d190`
- `0x18002d360`

## callees

- `0x18001e550`
- `0x18002aac0`
- `0x1800457f9`
- `0x180046010`

## pseudocode

```c
void __fastcall CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(__int64 a1, __int64 a2)
{
  void (__fastcall *v3)(__int64, GUID *); // rax
  const GUID *v4; // r8
  GUID v5; // [rsp+20h] [rbp-38h] BYREF
  GUID Buf2; // [rsp+30h] [rbp-28h] BYREF

  if ( a2 )
  {
    v3 = *(void (__fastcall **)(__int64, GUID *))(*(_QWORD *)a2 + 264LL);
    Buf2 = GUID_00000000_0000_0000_0000_000000000000;
    v5 = GUID_00000000_0000_0000_0000_000000000000;
    v3(a2, &Buf2);
    if ( !memcmp_0(&MEDIATYPE_Video, &Buf2, 0x10u) )
    {
      (*(void (__fastcall **)(__int64, const GUID *, GUID *))(*(_QWORD *)a2 + 80LL))(a2, &MF_MT_SUBTYPE, &v5);
      if ( !memcmp_0(&MEDIASUBTYPE_ARGB32, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_ARGB32;
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_RGB24, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_RGB24;
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_RGB32, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_RGB32;
      }
      else if ( !memcmp_0(&MEDIASUBTYPE_RGB555, &v5, 0x10u) )
      {
        v4 = &MFVideoFormat_RGB555;
      }
      else
      {
        if ( memcmp_0(&MEDIASUBTYPE_RGB565, &v5, 0x10u) )
          return;
        v4 = &MFVideoFormat_RGB565;
      }
      (*(void (__fastcall **)(__int64, const GUID *, const GUID *))(*(_QWORD *)a2 + 192LL))(a2, &MF_MT_SUBTYPE, v4);
    }
  }
}

```

## disassembly

```asm
0x18001e550  test    rdx, rdx
0x18001e553  jz      locret_18001E6A0
0x18001e559  mov     [rsp+arg_0], rbx
0x18001e55e  mov     [rsp+arg_10], rsi
0x18001e563  push    rdi
0x18001e564  sub     rsp, 50h
0x18001e568  mov     rax, cs:__security_cookie
0x18001e56f  xor     rax, rsp
0x18001e572  mov     [rsp+58h+var_18], rax
0x18001e577  mov     rax, [rdx]
0x18001e57a  mov     rbx, rdx
0x18001e57d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001e584  lea     rdx, [rsp+58h+Buf2]
0x18001e589  mov     rcx, rbx
0x18001e58c  mov     rax, [rax+108h]
0x18001e593  movdqu  [rsp+58h+Buf2], xmm0
0x18001e599  movdqu  [rsp+58h+var_38], xmm0
0x18001e59f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5a4  mov     esi, 10h
0x18001e5a9  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18001e5ae  mov     r8d, esi; Size
0x18001e5b1  lea     rcx, MEDIATYPE_Video; Buf1
0x18001e5b8  call    memcmp_0
0x18001e5bd  test    eax, eax
0x18001e5bf  jnz     loc_18001E684
0x18001e5c5  mov     rax, [rbx]
0x18001e5c8  lea     rdi, MF_MT_SUBTYPE
0x18001e5cf  lea     r8, [rsp+58h+var_38]
0x18001e5d4  mov     rdx, rdi
0x18001e5d7  mov     rcx, rbx
0x18001e5da  mov     rax, [rax+50h]
0x18001e5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5e3  mov     r8d, esi; Size
0x18001e5e6  lea     rdx, [rsp+58h+var_38]; Buf2
0x18001e5eb  lea     rcx, MEDIASUBTYPE_ARGB32; Buf1
0x18001e5f2  call    memcmp_0
0x18001e5f7  test    eax, eax
0x18001e5f9  jz      short loc_18001E668
0x18001e5fb  mov     r8d, esi; Size
0x18001e5fe  lea     rdx, [rsp+58h+var_38]; Buf2
0x18001e603  lea     rcx, MEDIASUBTYPE_RGB24; Buf1
0x18001e60a  call    memcmp_0
0x18001e60f  test    eax, eax
0x18001e611  jz      loc_18001E6A1
0x18001e617  mov     r8d, esi; Size
0x18001e61a  lea     rdx, [rsp+58h+var_38]; Buf2
0x18001e61f  lea     rcx, MEDIASUBTYPE_RGB32; Buf1
0x18001e626  call    memcmp_0
0x18001e62b  test    eax, eax
0x18001e62d  jz      short loc_18001E6AA
0x18001e62f  mov     r8d, esi; Size
0x18001e632  lea     rdx, [rsp+58h+var_38]; Buf2
0x18001e637  lea     rcx, MEDIASUBTYPE_RGB555; Buf1
0x18001e63e  call    memcmp_0
0x18001e643  test    eax, eax
0x18001e645  jz      short loc_18001E6B3
0x18001e647  mov     r8d, esi; Size
0x18001e64a  lea     rdx, [rsp+58h+var_38]; Buf2
0x18001e64f  lea     rcx, MEDIASUBTYPE_RGB565; Buf1
0x18001e656  call    memcmp_0
0x18001e65b  test    eax, eax
0x18001e65d  jnz     short loc_18001E684
0x18001e65f  lea     r8, MFVideoFormat_RGB565
0x18001e666  jmp     short loc_18001E66F
0x18001e668  lea     r8, MFVideoFormat_ARGB32
0x18001e66f  mov     rax, [rbx]
0x18001e672  mov     rdx, rdi
0x18001e675  mov     rcx, rbx
0x18001e678  mov     rax, [rax+0C0h]
0x18001e67f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e684  mov     rcx, [rsp+58h+var_18]
0x18001e689  xor     rcx, rsp; StackCookie
0x18001e68c  call    __security_check_cookie
0x18001e691  mov     rbx, [rsp+58h+arg_0]
0x18001e696  mov     rsi, [rsp+58h+arg_10]
0x18001e69b  add     rsp, 50h
0x18001e69f  pop     rdi
0x18001e6a0  retn
0x18001e6a1  lea     r8, MFVideoFormat_RGB24
0x18001e6a8  jmp     short loc_18001E66F
0x18001e6aa  lea     r8, MFVideoFormat_RGB32
0x18001e6b1  jmp     short loc_18001E66F
0x18001e6b3  lea     r8, MFVideoFormat_RGB555
0x18001e6ba  jmp     short loc_18001E66F
```

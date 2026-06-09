# CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(IMFMediaType *)

- ea: `0x18000324c`
- end: `0x1800033b7`
- name: `?ConvertDMORGBFormatToMFRGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z`
- size: `363`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180005570`
- `0x180005680`
- `0x1800058d0`
- `0x1800059e0`
- `0x1800066ac`

## callees

- `0x180001880`
- `0x18000324c`
- `0x180020f39`
- `0x180022010`

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
0x18000324c  test    rdx, rdx
0x18000324f  jz      locret_1800033B6
0x180003255  mov     [rsp+arg_0], rbx
0x18000325a  mov     [rsp+arg_10], rsi
0x18000325f  push    rdi
0x180003260  sub     rsp, 50h
0x180003264  mov     rax, cs:__security_cookie
0x18000326b  xor     rax, rsp
0x18000326e  mov     [rsp+58h+var_18], rax
0x180003273  mov     rax, [rdx]
0x180003276  mov     rbx, rdx
0x180003279  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180003280  lea     rdx, [rsp+58h+Buf2]
0x180003285  mov     rcx, rbx
0x180003288  mov     rax, [rax+108h]
0x18000328f  movdqu  [rsp+58h+Buf2], xmm0
0x180003295  movdqu  [rsp+58h+var_38], xmm0
0x18000329b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032a0  mov     esi, 10h
0x1800032a5  lea     rdx, [rsp+58h+Buf2]; Buf2
0x1800032aa  mov     r8d, esi; Size
0x1800032ad  lea     rcx, MEDIATYPE_Video; Buf1
0x1800032b4  call    memcmp_0
0x1800032b9  test    eax, eax
0x1800032bb  jnz     loc_18000339A
0x1800032c1  mov     rax, [rbx]
0x1800032c4  lea     rdi, MF_MT_SUBTYPE
0x1800032cb  lea     r8, [rsp+58h+var_38]
0x1800032d0  mov     rdx, rdi
0x1800032d3  mov     rcx, rbx
0x1800032d6  mov     rax, [rax+50h]
0x1800032da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032df  mov     r8d, esi; Size
0x1800032e2  lea     rdx, [rsp+58h+var_38]; Buf2
0x1800032e7  lea     rcx, MEDIASUBTYPE_ARGB32; Buf1
0x1800032ee  call    memcmp_0
0x1800032f3  test    eax, eax
0x1800032f5  jnz     short loc_180003303
0x1800032f7  lea     r8, MFVideoFormat_ARGB32
0x1800032fe  jmp     loc_180003385
0x180003303  mov     r8, rsi; Size
0x180003306  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000330b  lea     rcx, MEDIASUBTYPE_RGB24; Buf1
0x180003312  call    memcmp_0
0x180003317  test    eax, eax
0x180003319  jnz     short loc_180003324
0x18000331b  lea     r8, MFVideoFormat_RGB24
0x180003322  jmp     short loc_180003385
0x180003324  mov     r8, rsi; Size
0x180003327  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000332c  lea     rcx, MEDIASUBTYPE_RGB32; Buf1
0x180003333  call    memcmp_0
0x180003338  test    eax, eax
0x18000333a  jnz     short loc_180003345
0x18000333c  lea     r8, MFVideoFormat_RGB32
0x180003343  jmp     short loc_180003385
0x180003345  mov     r8, rsi; Size
0x180003348  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000334d  lea     rcx, MEDIASUBTYPE_RGB555; Buf1
0x180003354  call    memcmp_0
0x180003359  test    eax, eax
0x18000335b  jnz     short loc_180003366
0x18000335d  lea     r8, MFVideoFormat_RGB555
0x180003364  jmp     short loc_180003385
0x180003366  mov     r8, rsi; Size
0x180003369  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000336e  lea     rcx, MEDIASUBTYPE_RGB565; Buf1
0x180003375  call    memcmp_0
0x18000337a  test    eax, eax
0x18000337c  jnz     short loc_18000339A
0x18000337e  lea     r8, MFVideoFormat_RGB565
0x180003385  mov     rax, [rbx]
0x180003388  mov     rdx, rdi
0x18000338b  mov     rcx, rbx
0x18000338e  mov     rax, [rax+0C0h]
0x180003395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000339a  mov     rcx, [rsp+58h+var_18]
0x18000339f  xor     rcx, rsp; StackCookie
0x1800033a2  call    __security_check_cookie
0x1800033a7  mov     rbx, [rsp+58h+arg_0]
0x1800033ac  mov     rsi, [rsp+58h+arg_10]
0x1800033b1  add     rsp, 50h
0x1800033b5  pop     rdi
0x1800033b6  retn
```

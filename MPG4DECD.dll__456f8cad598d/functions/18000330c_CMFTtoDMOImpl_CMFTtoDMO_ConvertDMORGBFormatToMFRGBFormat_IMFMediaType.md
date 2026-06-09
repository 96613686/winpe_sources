# CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(IMFMediaType *)

- ea: `0x18000330c`
- end: `0x180003477`
- name: `?ConvertDMORGBFormatToMFRGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z`
- size: `363`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180005630`
- `0x180005740`
- `0x180005990`
- `0x180005aa0`
- `0x18000676c`

## callees

- `0x1800018b0`
- `0x18000330c`
- `0x180020ff9`
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
0x18000330c  test    rdx, rdx
0x18000330f  jz      locret_180003476
0x180003315  mov     [rsp+arg_0], rbx
0x18000331a  mov     [rsp+arg_10], rsi
0x18000331f  push    rdi
0x180003320  sub     rsp, 50h
0x180003324  mov     rax, cs:__security_cookie
0x18000332b  xor     rax, rsp
0x18000332e  mov     [rsp+58h+var_18], rax
0x180003333  mov     rax, [rdx]
0x180003336  mov     rbx, rdx
0x180003339  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180003340  lea     rdx, [rsp+58h+Buf2]
0x180003345  mov     rcx, rbx
0x180003348  mov     rax, [rax+108h]
0x18000334f  movdqu  [rsp+58h+Buf2], xmm0
0x180003355  movdqu  [rsp+58h+var_38], xmm0
0x18000335b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003360  mov     esi, 10h
0x180003365  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18000336a  mov     r8d, esi; Size
0x18000336d  lea     rcx, MEDIATYPE_Video; Buf1
0x180003374  call    memcmp_0
0x180003379  test    eax, eax
0x18000337b  jnz     loc_18000345A
0x180003381  mov     rax, [rbx]
0x180003384  lea     rdi, MF_MT_SUBTYPE
0x18000338b  lea     r8, [rsp+58h+var_38]
0x180003390  mov     rdx, rdi
0x180003393  mov     rcx, rbx
0x180003396  mov     rax, [rax+50h]
0x18000339a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000339f  mov     r8d, esi; Size
0x1800033a2  lea     rdx, [rsp+58h+var_38]; Buf2
0x1800033a7  lea     rcx, MEDIASUBTYPE_ARGB32; Buf1
0x1800033ae  call    memcmp_0
0x1800033b3  test    eax, eax
0x1800033b5  jnz     short loc_1800033C3
0x1800033b7  lea     r8, MFVideoFormat_ARGB32
0x1800033be  jmp     loc_180003445
0x1800033c3  mov     r8, rsi; Size
0x1800033c6  lea     rdx, [rsp+58h+var_38]; Buf2
0x1800033cb  lea     rcx, MEDIASUBTYPE_RGB24; Buf1
0x1800033d2  call    memcmp_0
0x1800033d7  test    eax, eax
0x1800033d9  jnz     short loc_1800033E4
0x1800033db  lea     r8, MFVideoFormat_RGB24
0x1800033e2  jmp     short loc_180003445
0x1800033e4  mov     r8, rsi; Size
0x1800033e7  lea     rdx, [rsp+58h+var_38]; Buf2
0x1800033ec  lea     rcx, MEDIASUBTYPE_RGB32; Buf1
0x1800033f3  call    memcmp_0
0x1800033f8  test    eax, eax
0x1800033fa  jnz     short loc_180003405
0x1800033fc  lea     r8, MFVideoFormat_RGB32
0x180003403  jmp     short loc_180003445
0x180003405  mov     r8, rsi; Size
0x180003408  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000340d  lea     rcx, MEDIASUBTYPE_RGB555; Buf1
0x180003414  call    memcmp_0
0x180003419  test    eax, eax
0x18000341b  jnz     short loc_180003426
0x18000341d  lea     r8, MFVideoFormat_RGB555
0x180003424  jmp     short loc_180003445
0x180003426  mov     r8, rsi; Size
0x180003429  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000342e  lea     rcx, MEDIASUBTYPE_RGB565; Buf1
0x180003435  call    memcmp_0
0x18000343a  test    eax, eax
0x18000343c  jnz     short loc_18000345A
0x18000343e  lea     r8, MFVideoFormat_RGB565
0x180003445  mov     rax, [rbx]
0x180003448  mov     rdx, rdi
0x18000344b  mov     rcx, rbx
0x18000344e  mov     rax, [rax+0C0h]
0x180003455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000345a  mov     rcx, [rsp+58h+var_18]
0x18000345f  xor     rcx, rsp; StackCookie
0x180003462  call    __security_check_cookie
0x180003467  mov     rbx, [rsp+58h+arg_0]
0x18000346c  mov     rsi, [rsp+58h+arg_10]
0x180003471  add     rsp, 50h
0x180003475  pop     rdi
0x180003476  retn
```

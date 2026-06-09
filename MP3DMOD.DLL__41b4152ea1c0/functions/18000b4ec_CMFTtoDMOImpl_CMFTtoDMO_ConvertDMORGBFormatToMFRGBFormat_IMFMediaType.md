# CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(IMFMediaType *)

- ea: `0x18000b4ec`
- end: `0x18000b657`
- name: `?ConvertDMORGBFormatToMFRGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z`
- size: `363`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a900`
- `0x18000aa00`
- `0x18000aaf0`
- `0x18000d2dc`
- `0x18000f640`

## callees

- `0x18000b4ec`
- `0x18000e3a0`
- `0x1800114a5`
- `0x180012010`

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
    Buf2 = GUID_NULL;
    v5 = GUID_NULL;
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
0x18000b4ec  test    rdx, rdx
0x18000b4ef  jz      locret_18000B656
0x18000b4f5  mov     [rsp+arg_0], rbx
0x18000b4fa  mov     [rsp+arg_10], rsi
0x18000b4ff  push    rdi
0x18000b500  sub     rsp, 50h
0x18000b504  mov     rax, cs:__security_cookie
0x18000b50b  xor     rax, rsp
0x18000b50e  mov     [rsp+58h+var_18], rax
0x18000b513  mov     rax, [rdx]
0x18000b516  mov     rbx, rdx
0x18000b519  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000b520  lea     rdx, [rsp+58h+Buf2]
0x18000b525  mov     rcx, rbx
0x18000b528  mov     rax, [rax+108h]
0x18000b52f  movdqu  [rsp+58h+Buf2], xmm0
0x18000b535  movdqu  [rsp+58h+var_38], xmm0
0x18000b53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b540  mov     esi, 10h
0x18000b545  lea     rdx, [rsp+58h+Buf2]; Buf2
0x18000b54a  mov     r8d, esi; Size
0x18000b54d  lea     rcx, MEDIATYPE_Video; Buf1
0x18000b554  call    memcmp_0
0x18000b559  test    eax, eax
0x18000b55b  jnz     loc_18000B63A
0x18000b561  mov     rax, [rbx]
0x18000b564  lea     rdi, MF_MT_SUBTYPE
0x18000b56b  lea     r8, [rsp+58h+var_38]
0x18000b570  mov     rdx, rdi
0x18000b573  mov     rcx, rbx
0x18000b576  mov     rax, [rax+50h]
0x18000b57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b57f  mov     r8d, esi; Size
0x18000b582  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000b587  lea     rcx, MEDIASUBTYPE_ARGB32; Buf1
0x18000b58e  call    memcmp_0
0x18000b593  test    eax, eax
0x18000b595  jnz     short loc_18000B5A3
0x18000b597  lea     r8, MFVideoFormat_ARGB32
0x18000b59e  jmp     loc_18000B625
0x18000b5a3  mov     r8, rsi; Size
0x18000b5a6  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000b5ab  lea     rcx, MEDIASUBTYPE_RGB24; Buf1
0x18000b5b2  call    memcmp_0
0x18000b5b7  test    eax, eax
0x18000b5b9  jnz     short loc_18000B5C4
0x18000b5bb  lea     r8, MFVideoFormat_RGB24
0x18000b5c2  jmp     short loc_18000B625
0x18000b5c4  mov     r8, rsi; Size
0x18000b5c7  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000b5cc  lea     rcx, MEDIASUBTYPE_RGB32; Buf1
0x18000b5d3  call    memcmp_0
0x18000b5d8  test    eax, eax
0x18000b5da  jnz     short loc_18000B5E5
0x18000b5dc  lea     r8, MFVideoFormat_RGB32
0x18000b5e3  jmp     short loc_18000B625
0x18000b5e5  mov     r8, rsi; Size
0x18000b5e8  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000b5ed  lea     rcx, MEDIASUBTYPE_RGB555; Buf1
0x18000b5f4  call    memcmp_0
0x18000b5f9  test    eax, eax
0x18000b5fb  jnz     short loc_18000B606
0x18000b5fd  lea     r8, MFVideoFormat_RGB555
0x18000b604  jmp     short loc_18000B625
0x18000b606  mov     r8, rsi; Size
0x18000b609  lea     rdx, [rsp+58h+var_38]; Buf2
0x18000b60e  lea     rcx, MEDIASUBTYPE_RGB565; Buf1
0x18000b615  call    memcmp_0
0x18000b61a  test    eax, eax
0x18000b61c  jnz     short loc_18000B63A
0x18000b61e  lea     r8, MFVideoFormat_RGB565
0x18000b625  mov     rax, [rbx]
0x18000b628  mov     rdx, rdi
0x18000b62b  mov     rcx, rbx
0x18000b62e  mov     rax, [rax+0C0h]
0x18000b635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b63a  mov     rcx, [rsp+58h+var_18]
0x18000b63f  xor     rcx, rsp; StackCookie
0x18000b642  call    __security_check_cookie
0x18000b647  mov     rbx, [rsp+58h+arg_0]
0x18000b64c  mov     rsi, [rsp+58h+arg_10]
0x18000b651  add     rsp, 50h
0x18000b655  pop     rdi
0x18000b656  retn
```

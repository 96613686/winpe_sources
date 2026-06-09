# ConsoleToPipeRedirector::SendData(void const *,ulong)

- ea: `0x14001ca50`
- end: `0x14001cb62`
- name: `?SendData@ConsoleToPipeRedirector@@AEAAKPEBXK@Z`
- size: `274`
- prototype: `__int64 __fastcall(ConsoleToPipeRedirector *this, const void *, DWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001b160`
- `0x14001b984`
- `0x14001bad0`
- `0x14001bddc`
- `0x14001c60c`
- `0x14001cb68`

## callees

- `0x140002310`
- `0x14001c398`
- `0x14001ca50`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001cae3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001cb13`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001cb3b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001cae3`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001cb13`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001cb3b`

## pseudocode

```c
__int64 __fastcall ConsoleToPipeRedirector::SendData(ConsoleToPipeRedirector *this, const void *a2, DWORD a3)
{
  bool v6; // zf
  _OWORD *Csi; // rax
  void *v8; // rcx
  void *v9; // rcx
  _BYTE v11[32]; // [rsp+30h] [rbp-19h] BYREF
  int v12; // [rsp+50h] [rbp+7h] BYREF
  char v13; // [rsp+54h] [rbp+Bh]
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+Fh] BYREF
  _OWORD Buffer[2]; // [rsp+60h] [rbp+17h] BYREF

  if ( (unsigned __int64)(*((_QWORD *)this + 7) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v6 = *((_BYTE *)this + 376) == 0;
    NumberOfBytesWritten = 0;
    if ( v6 )
    {
LABEL_6:
      WriteFile(*((HANDLE *)this + 7), a2, a3, &NumberOfBytesWritten, 0);
      return 0;
    }
    Csi = (_OWORD *)MakeCsi((__int64)v11, 74, 2);
    v8 = (void *)*((_QWORD *)this + 7);
    Buffer[0] = *Csi;
    *(_OWORD *)((char *)Buffer + 12) = *(_OWORD *)((char *)Csi + 12);
    if ( WriteFile(
           v8,
           Buffer,
           (unsigned int)_mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)((char *)Buffer + 12), 12)) >> 24,
           &NumberOfBytesWritten,
           0) )
    {
      v9 = (void *)*((_QWORD *)this + 7);
      v12 = 4741915;
      v13 = 3;
      if ( WriteFile(v9, &v12, 3u, &NumberOfBytesWritten, 0) )
      {
        *((_BYTE *)this + 376) = 0;
        goto LABEL_6;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001ca50  mov     [rsp-8+arg_18], rbx
0x14001ca55  push    rbp
0x14001ca56  push    rsi
0x14001ca57  push    rdi
0x14001ca58  lea     rbp, [rsp-47h]
0x14001ca5d  sub     rsp, 90h
0x14001ca64  mov     rax, cs:__security_cookie
0x14001ca6b  xor     rax, rsp
0x14001ca6e  mov     [rbp+57h+var_20], rax
0x14001ca72  mov     rax, [rcx+38h]
0x14001ca76  mov     esi, r8d
0x14001ca79  dec     rax
0x14001ca7c  mov     rdi, rdx
0x14001ca7f  mov     rbx, rcx
0x14001ca82  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14001ca86  ja      loc_14001CB41
0x14001ca8c  cmp     byte ptr [rcx+178h], 0
0x14001ca93  mov     [rbp+57h+NumberOfBytesWritten], 0
0x14001ca9a  jz      loc_14001CB24
0x14001caa0  mov     r8d, 2
0x14001caa6  lea     rcx, [rbp+57h+var_70]
0x14001caaa  mov     dl, 4Ah ; 'J'
0x14001caac  call    ?MakeCsi@@YA?AUCsiCommand@@DK@Z; MakeCsi(char,ulong)
0x14001cab1  mov     rcx, [rbx+38h]; hFile
0x14001cab5  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001cab9  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x14001cabd  mov     [rsp+0A0h+lpOverlapped], 0; lpOverlapped
0x14001cac6  movups  xmm0, xmmword ptr [rax]
0x14001cac9  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x14001cacd  movups  xmm1, xmmword ptr [rax+0Ch]
0x14001cad1  movups  xmmword ptr [rbp+57h+Buffer+0Ch], xmm1
0x14001cad5  psrldq  xmm1, 0Ch
0x14001cada  movd    r8d, xmm1
0x14001cadf  shr     r8d, 18h; nNumberOfBytesToWrite
0x14001cae3  call    cs:__imp_WriteFile
0x14001cae9  test    eax, eax
0x14001caeb  jz      short loc_14001CB41
0x14001caed  mov     rcx, [rbx+38h]; hFile
0x14001caf1  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001caf5  mov     r8d, 3; nNumberOfBytesToWrite
0x14001cafb  mov     [rbp+57h+var_50], 485B1Bh
0x14001cb02  lea     rdx, [rbp+57h+var_50]; lpBuffer
0x14001cb06  mov     [rbp+57h+var_4C], 3
0x14001cb0a  mov     [rsp+0A0h+lpOverlapped], 0; lpOverlapped
0x14001cb13  call    cs:__imp_WriteFile
0x14001cb19  test    eax, eax
0x14001cb1b  jz      short loc_14001CB41
0x14001cb1d  mov     byte ptr [rbx+178h], 0
0x14001cb24  mov     rcx, [rbx+38h]; hFile
0x14001cb28  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001cb2c  mov     r8d, esi; nNumberOfBytesToWrite
0x14001cb2f  mov     [rsp+0A0h+lpOverlapped], 0; lpOverlapped
0x14001cb38  mov     rdx, rdi; lpBuffer
0x14001cb3b  call    cs:__imp_WriteFile
0x14001cb41  xor     eax, eax
0x14001cb43  mov     rcx, [rbp+57h+var_20]
0x14001cb47  xor     rcx, rsp; StackCookie
0x14001cb4a  call    __security_check_cookie
0x14001cb4f  mov     rbx, [rsp+0A0h+arg_18]
0x14001cb57  add     rsp, 90h
0x14001cb5e  pop     rdi
0x14001cb5f  pop     rsi
0x14001cb60  pop     rbp
0x14001cb61  retn
```

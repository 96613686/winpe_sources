# BufferWriter::CBufferWriter::CreateInstance(ushort *,BufferWriter::CBufferWriter * *)

- ea: `0x180013bb8`
- end: `0x180013d2b`
- name: `?CreateInstance@CBufferWriter@BufferWriter@@SAJPEAGPEAPEAV12@@Z`
- size: `371`
- prototype: `static int(unsigned __int16 *, struct BufferWriter::CBufferWriter **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800168c4`

## callees

- `0x180001460`
- `0x180013bb8`
- `0x180013d34`

## import_xrefs

- `ole32!StringFromGUID2` at `0x180013ce5`
- `ole32!StringFromGUID2` at `0x180013ce5`
- `ole32!CoCreateGuid` at `0x180013cce`
- `ole32!CoCreateGuid` at `0x180013cce`

## pseudocode

```c
__int64 __fastcall BufferWriter::CBufferWriter::CreateInstance(
        unsigned __int16 *a1,
        struct BufferWriter::CBufferWriter **a2)
{
  unsigned __int16 *v3; // r10
  int v4; // ebx
  unsigned __int16 *v5; // rax
  __int64 v6; // r9
  signed int Instance; // edx
  __int64 v8; // r8
  __int64 v9; // rax
  WCHAR *v10; // r11
  __int64 v11; // r9
  WCHAR *v12; // rcx
  WCHAR *v13; // rsi
  __int64 v14; // rdx
  GUID pguid; // [rsp+20h] [rbp-258h] BYREF
  WCHAR FileName[264]; // [rsp+30h] [rbp-248h] BYREF

  v3 = a1;
  pguid = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  v4 = 260;
  v5 = a1;
  v6 = 260;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  Instance = v6 == 0 ? 0x80070057 : 0;
  v8 = (260 - v6) & -(__int64)(v6 != 0);
  if ( v6 )
  {
    FileName[0] = 0;
    if ( !v8 )
    {
      v13 = FileName;
      goto LABEL_19;
    }
    v9 = 2147483646;
    v10 = FileName;
    v11 = 260;
    do
    {
      if ( !v9 )
        break;
      if ( !*v3 )
        break;
      *v10++ = *v3++;
      --v9;
      --v11;
    }
    while ( v11 );
    v12 = v10 - 1;
    Instance = v11 == 0 ? 0x8007007A : 0;
    if ( v11 )
      v12 = v10;
    *v12 = 0;
    if ( v11 )
    {
      if ( *(_WORD *)&pguid.Data4[2 * v8 + 6] != 92 )
      {
        if ( (unsigned __int64)(v8 + 2) > 0x104 )
          return (unsigned int)-2147024809;
        *(_DWORD *)&FileName[v8++] = 92;
      }
      v4 = 259 - v8;
      v13 = &FileName[v8];
LABEL_19:
      Instance = CoCreateGuid(&pguid);
      if ( Instance < 0 )
        return (unsigned int)Instance;
      if ( StringFromGUID2(&pguid, v13, v4) )
      {
        Instance = BufferWriter::CBufferWriter::CreateInstance(FileName, v14, a2);
        if ( Instance < 0 )
          *a2 = 0;
        return (unsigned int)Instance;
      }
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180013bb8  push    rbx
0x180013bba  push    rbp
0x180013bbb  push    rsi
0x180013bbc  push    r14
0x180013bbe  sub     rsp, 258h
0x180013bc5  mov     rax, cs:__security_cookie
0x180013bcc  xor     rax, rsp
0x180013bcf  mov     [rsp+278h+var_38], rax
0x180013bd7  xor     ebp, ebp
0x180013bd9  xorps   xmm0, xmm0
0x180013bdc  mov     r14, rdx
0x180013bdf  mov     r10, rcx
0x180013be2  movups  xmmword ptr [rsp+278h+pguid.Data1], xmm0
0x180013be7  test    rcx, rcx
0x180013bea  jz      loc_180013D07
0x180013bf0  mov     ebx, 104h
0x180013bf5  mov     rax, rcx
0x180013bf8  mov     r9d, ebx
0x180013bfb  cmp     [rax], bp
0x180013bfe  jz      short loc_180013C0A
0x180013c00  add     rax, 2
0x180013c04  sub     r9, 1
0x180013c08  jnz     short loc_180013BFB
0x180013c0a  mov     rax, r9
0x180013c0d  mov     rcx, rbx
0x180013c10  neg     rax
0x180013c13  mov     rax, r9
0x180013c16  sbb     edx, edx
0x180013c18  sub     rcx, r9
0x180013c1b  not     edx
0x180013c1d  and     edx, 80070057h
0x180013c23  neg     rax
0x180013c26  sbb     r8, r8
0x180013c29  and     r8, rcx
0x180013c2c  test    r9, r9
0x180013c2f  jz      loc_180013D0C
0x180013c35  mov     [rsp+278h+FileName], bp
0x180013c3a  test    r8, r8
0x180013c3d  jz      loc_180013CC4
0x180013c43  mov     eax, 7FFFFFFEh
0x180013c48  lea     r11, [rsp+278h+FileName]
0x180013c4d  mov     r9, rbx
0x180013c50  test    rax, rax
0x180013c53  jz      short loc_180013C73
0x180013c55  movzx   ecx, word ptr [r10]
0x180013c59  test    cx, cx
0x180013c5c  jz      short loc_180013C73
0x180013c5e  mov     [r11], cx
0x180013c62  add     r10, 2
0x180013c66  add     r11, 2
0x180013c6a  dec     rax
0x180013c6d  sub     r9, 1
0x180013c71  jnz     short loc_180013C50
0x180013c73  mov     rax, r9
0x180013c76  lea     rcx, [r11-2]
0x180013c7a  neg     rax
0x180013c7d  sbb     edx, edx
0x180013c7f  not     edx
0x180013c81  and     edx, 8007007Ah
0x180013c87  test    r9, r9
0x180013c8a  cmovnz  rcx, r11
0x180013c8e  mov     [rcx], bp
0x180013c91  jz      short loc_180013D0C
0x180013c93  mov     ecx, 5Ch ; '\'
0x180013c98  cmp     word ptr [rsp+r8*2+278h+pguid.Data4+6], cx
0x180013c9e  jz      short loc_180013CB1
0x180013ca0  lea     rax, [r8+2]
0x180013ca4  cmp     rax, rbx
0x180013ca7  ja      short loc_180013D07
0x180013ca9  mov     dword ptr [rsp+r8*2+278h+FileName], ecx
0x180013cae  inc     r8
0x180013cb1  mov     ebx, 103h
0x180013cb6  lea     rsi, [rsp+278h+FileName]
0x180013cbb  sub     rbx, r8
0x180013cbe  lea     rsi, [rsi+r8*2]
0x180013cc2  jmp     short loc_180013CC9
0x180013cc4  lea     rsi, [rsp+278h+FileName]
0x180013cc9  lea     rcx, [rsp+278h+pguid]; pguid
0x180013cce  call    cs:__imp_CoCreateGuid
0x180013cd4  mov     edx, eax
0x180013cd6  test    eax, eax
0x180013cd8  js      short loc_180013D0C
0x180013cda  mov     r8d, ebx; cchMax
0x180013cdd  lea     rcx, [rsp+278h+pguid]; rguid
0x180013ce2  mov     rdx, rsi; lpsz
0x180013ce5  call    cs:__imp_StringFromGUID2
0x180013ceb  test    eax, eax
0x180013ced  jz      short loc_180013D07
0x180013cef  mov     r8, r14; struct BufferWriter::CBufferWriter **
0x180013cf2  lea     rcx, [rsp+278h+FileName]; lpFileName
0x180013cf7  call    ?CreateInstance@CBufferWriter@BufferWriter@@SAJPEBGKPEAPEAV12@@Z; BufferWriter::CBufferWriter::CreateInstance(ushort const *,ulong,BufferWriter::CBufferWriter * *)
0x180013cfc  mov     edx, eax
0x180013cfe  test    eax, eax
0x180013d00  jns     short loc_180013D0C
0x180013d02  mov     [r14], rbp
0x180013d05  jmp     short loc_180013D0C
0x180013d07  mov     edx, 80070057h
0x180013d0c  mov     eax, edx
0x180013d0e  mov     rcx, [rsp+278h+var_38]
0x180013d16  xor     rcx, rsp; StackCookie
0x180013d19  call    __security_check_cookie
0x180013d1e  add     rsp, 258h
0x180013d25  pop     r14
0x180013d27  pop     rsi
0x180013d28  pop     rbp
0x180013d29  pop     rbx
0x180013d2a  retn
```

# CGpBmpDecoder::GenerateGdiBits(void)

- ea: `0x180086ce8`
- end: `0x180086fdd`
- name: `?GenerateGdiBits@CGpBmpDecoder@@AEAAJXZ`
- size: `757`
- prototype: `__int64 __fastcall(CGpBmpDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180086ba4`

## callees

- `0x1800759b0`
- `0x180075a80`
- `0x18007607c`
- `0x180086ce8`
- `0x1800bb784`
- `0x1800c9be8`
- `0x1800e2f90`
- `0x18017b044`
- `0x18017b148`
- `0x18017b528`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180086e7a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180086f73`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180086f7c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180086e7a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180086f73`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180086f7c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180086d43`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180086e3f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180086d43`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180086e3f`
- `ext-ms-win-gdi-draw-l1-1-0!SetDIBits` at `0x180086f68`
- `ext-ms-win-gdi-draw-l1-1-0!SetDIBits` at `0x180086f68`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180086e0d`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x180086e0d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180086e6c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180086fa4`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180086e6c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180086fa4`

## pseudocode

```c
__int64 __fastcall CGpBmpDecoder::GenerateGdiBits(CGpBmpDecoder *this)
{
  CStreamBase *v2; // rcx
  unsigned int v3; // eax
  unsigned int v4; // esi
  unsigned int v5; // r8d
  void *v6; // r14
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  LONG v11; // ecx
  HBITMAP v12; // rax
  unsigned int v13; // eax
  BITMAPINFO *v14; // rax
  BITMAPINFO *v15; // rsi
  DWORD v16; // ebx
  int v17; // eax
  int v18; // ecx
  DWORD v19; // eax
  int v20; // eax
  int v21; // ebx
  unsigned int v22; // [rsp+40h] [rbp-29h] BYREF
  BITMAPINFO pbmi; // [rsp+48h] [rbp-21h] BYREF

  v2 = (CStreamBase *)*((_QWORD *)this + 15);
  v22 = 0;
  if ( (int)CStreamBase::HrGetSize(v2, &v22) < 0 )
    return 2291674976LL;
  v3 = *(_DWORD *)((char *)this + 302);
  if ( v3 > v22 )
    return 2291674976LL;
  v4 = v22 - v3;
  v6 = malloc(v22 - v3);
  if ( !v6 )
    return 2147942414LL;
  v8 = CStreamBase::HrSeek(*((CStreamBase **)this + 15), *(_DWORD *)((char *)this + 302), v5);
  v9 = v8;
  if ( v8 < 0 || (v8 = CDecoderBase::HrRead(this, v6, v4, 0), v9 = v8, v8 < 0) )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v8);
    goto LABEL_22;
  }
  pbmi.bmiHeader.biWidth = *((_DWORD *)this + 78);
  v10 = *((_DWORD *)this + 79);
  v11 = -v10;
  *(_QWORD *)&pbmi.bmiHeader.biClrImportant = 0;
  pbmi.bmiHeader.biSize = 40;
  if ( v10 > 0 )
    v11 = v10;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  pbmi.bmiHeader.biXPelsPerMeter = *((_DWORD *)this + 83);
  pbmi.bmiHeader.biYPelsPerMeter = *((_DWORD *)this + 84);
  pbmi.bmiHeader.biHeight = v11;
  pbmi.bmiHeader.biSizeImage = 0;
  pbmi.bmiHeader.biClrUsed = 0;
  if ( !(unsigned __int8)IsSetDIBitsPresent() )
    return 2147500033LL;
  v12 = CreateDIBSection(0, &pbmi, 0, (void **)this + 183, 0, 0);
  *((_QWORD *)this + 182) = v12;
  if ( !v12 )
  {
    v9 = -2003292320;
LABEL_22:
    free(v6);
    return v9;
  }
  v13 = *((_DWORD *)this + 82);
  if ( !v13 || v13 > v4 )
    *((_DWORD *)this + 82) = v4;
  v14 = (BITMAPINFO *)malloc(0x428u);
  v15 = v14;
  if ( !v14 )
  {
    if ( (unsigned __int8)IsDeleteObjectPresent() )
    {
      DeleteObject(*((HGDIOBJ *)this + 182));
      v9 = -2147024882;
      goto LABEL_22;
    }
    goto LABEL_19;
  }
  v14->bmiHeader.biSize = 40;
  v16 = *((_DWORD *)this + 81);
  v14->bmiHeader.biWidth = *((_DWORD *)this + 78);
  v17 = *((_DWORD *)this + 79);
  v18 = -v17;
  v15->bmiHeader.biCompression = v16;
  if ( v17 > 0 )
    v18 = v17;
  v15->bmiHeader.biPlanes = *((_WORD *)this + 160);
  v15->bmiHeader.biBitCount = *((_WORD *)this + 161);
  v15->bmiHeader.biSizeImage = *((_DWORD *)this + 82);
  v15->bmiHeader.biXPelsPerMeter = *((_DWORD *)this + 83);
  v15->bmiHeader.biYPelsPerMeter = *((_DWORD *)this + 84);
  v15->bmiHeader.biClrUsed = *((_DWORD *)this + 85);
  v19 = *((_DWORD *)this + 86);
  v15->bmiHeader.biHeight = v18;
  v15->bmiHeader.biClrImportant = v19;
  memcpy_0(v15->bmiColors, (char *)this + 432, 0x400u);
  v20 = *((_DWORD *)this + 77);
  if ( (v20 == 56 || v20 == 108 || v20 == 124) && v16 == 3 )
  {
    v15->bmiColors[0] = (RGBQUAD)*((_DWORD *)this + 87);
    v15[1].bmiHeader.biSize = *((_DWORD *)this + 88);
    v15[1].bmiHeader.biWidth = *((_DWORD *)this + 89);
  }
  if ( !(unsigned __int8)IsSetDIBitsPresent() )
    return 2147500033LL;
  v21 = SetDIBits(0, *((HBITMAP *)this + 182), 0, *((_DWORD *)this + 45), v6, v15, 0);
  free(v15);
  free(v6);
  if ( v21 != *((_DWORD *)this + 45) )
  {
    if ( !(unsigned __int8)IsDeleteObjectPresent() )
    {
LABEL_19:
      MicrosoftTelemetryAssertTriggeredNoArgs();
      return 2147500033LL;
    }
    DeleteObject(*((HGDIOBJ *)this + 182));
    *((_QWORD *)this + 182) = 0;
    *((_QWORD *)this + 183) = 0;
    return 2291674976LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180086ce8  push    rbp
0x180086cea  push    rbx
0x180086ceb  push    rsi
0x180086cec  push    rdi
0x180086ced  push    r12
0x180086cef  push    r13
0x180086cf1  push    r14
0x180086cf3  push    r15
0x180086cf5  lea     rbp, [rsp-1Fh]
0x180086cfa  sub     rsp, 88h
0x180086d01  mov     rax, cs:__security_cookie
0x180086d08  xor     rax, rsp
0x180086d0b  mov     [rbp+57h+var_48], rax
0x180086d0f  mov     rdi, rcx
0x180086d12  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x180086d16  mov     rcx, [rcx+78h]; this
0x180086d1a  xor     r13d, r13d
0x180086d1d  mov     [rbp+57h+var_80], r13d
0x180086d21  call    ?HrGetSize@CStreamBase@@QEAAJPEAI@Z; CStreamBase::HrGetSize(uint *)
0x180086d26  test    eax, eax
0x180086d28  js      loc_180086FB4
0x180086d2e  mov     eax, [rdi+12Eh]
0x180086d34  mov     esi, [rbp+57h+var_80]
0x180086d37  cmp     eax, esi
0x180086d39  ja      loc_180086FB4
0x180086d3f  sub     esi, eax
0x180086d41  mov     ecx, esi; Size
0x180086d43  call    cs:__imp_malloc
0x180086d49  mov     r14, rax
0x180086d4c  test    rax, rax
0x180086d4f  jnz     short loc_180086D5B
0x180086d51  mov     eax, 8007000Eh
0x180086d56  jmp     loc_180086FB9
0x180086d5b  mov     edx, [rdi+12Eh]; unsigned int
0x180086d61  mov     rcx, [rdi+78h]; this
0x180086d65  call    ?HrSeek@CStreamBase@@QEAAJIK@Z; CStreamBase::HrSeek(uint,ulong)
0x180086d6a  mov     ebx, eax
0x180086d6c  test    eax, eax
0x180086d6e  js      short loc_180086D87
0x180086d70  xor     r9d, r9d; unsigned int *
0x180086d73  mov     r8d, esi; unsigned int
0x180086d76  mov     rdx, r14; void *
0x180086d79  mov     rcx, rdi; this
0x180086d7c  call    ?HrRead@CDecoderBase@@IEAAJPEAXIPEAI@Z; CDecoderBase::HrRead(void *,uint,uint *)
0x180086d81  mov     ebx, eax
0x180086d83  test    eax, eax
0x180086d85  jns     short loc_180086DA0
0x180086d87  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180086d8e  jz      loc_180086E77
0x180086d94  mov     ecx, eax; int
0x180086d96  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180086d9b  jmp     loc_180086E77
0x180086da0  mov     eax, [rdi+138h]
0x180086da6  mov     ebx, 28h ; '('
0x180086dab  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x180086dae  mov     eax, [rdi+13Ch]
0x180086db4  mov     ecx, eax
0x180086db6  neg     ecx
0x180086db8  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], r13
0x180086dbc  mov     [rbp+57h+pbmi.bmiHeader.biSize], ebx
0x180086dbf  cmovs   ecx, eax
0x180086dc2  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x180086dca  mov     eax, [rdi+14Ch]
0x180086dd0  mov     [rbp+57h+pbmi.bmiHeader.biXPelsPerMeter], eax
0x180086dd3  mov     eax, [rdi+150h]
0x180086dd9  mov     [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], eax
0x180086ddc  mov     [rbp+57h+pbmi.bmiHeader.biHeight], ecx
0x180086ddf  mov     [rbp+57h+pbmi.bmiHeader.biSizeImage], r13d
0x180086de3  mov     [rbp+57h+pbmi.bmiHeader.biClrUsed], r13d
0x180086de7  call    IsSetDIBitsPresent
0x180086dec  test    al, al
0x180086dee  jz      short loc_180086E5B
0x180086df0  lea     r15, [rdi+5B8h]
0x180086df7  mov     [rsp+0C0h+offset], r13d; offset
0x180086dfc  mov     r9, r15; ppvBits
0x180086dff  mov     [rsp+0C0h+hSection], r13; hSection
0x180086e04  xor     r8d, r8d; usage
0x180086e07  lea     rdx, [rbp+57h+pbmi]; pbmi
0x180086e0b  xor     ecx, ecx; hdc
0x180086e0d  call    cs:__imp_CreateDIBSection
0x180086e13  mov     [rdi+5B0h], rax
0x180086e1a  test    rax, rax
0x180086e1d  jnz     short loc_180086E26
0x180086e1f  mov     ebx, 88982F60h
0x180086e24  jmp     short loc_180086E77
0x180086e26  mov     eax, [rdi+148h]
0x180086e2c  test    eax, eax
0x180086e2e  jz      short loc_180086E34
0x180086e30  cmp     eax, esi
0x180086e32  jbe     short loc_180086E3A
0x180086e34  mov     [rdi+148h], esi
0x180086e3a  mov     ecx, 428h; Size
0x180086e3f  call    cs:__imp_malloc
0x180086e45  mov     rsi, rax
0x180086e48  test    rax, rax
0x180086e4b  jnz     short loc_180086E87
0x180086e4d  call    IsDeleteObjectPresent
0x180086e52  test    al, al
0x180086e54  jnz     short loc_180086E65
0x180086e56  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180086e5b  mov     eax, 80004001h
0x180086e60  jmp     loc_180086FB9
0x180086e65  mov     rcx, [rdi+5B0h]; ho
0x180086e6c  call    cs:__imp_DeleteObject
0x180086e72  mov     ebx, 8007000Eh
0x180086e77  mov     rcx, r14; Block
0x180086e7a  call    cs:__imp_free
0x180086e80  mov     eax, ebx
0x180086e82  jmp     loc_180086FB9
0x180086e87  mov     [rax], ebx
0x180086e89  lea     rdx, [rdi+1B0h]; Src
0x180086e90  mov     eax, [rdi+138h]
0x180086e96  mov     r8d, 400h; Size
0x180086e9c  mov     ebx, [rdi+144h]
0x180086ea2  mov     [rsi+4], eax
0x180086ea5  mov     eax, [rdi+13Ch]
0x180086eab  mov     ecx, eax
0x180086ead  neg     ecx
0x180086eaf  mov     [rsi+10h], ebx
0x180086eb2  cmovs   ecx, eax
0x180086eb5  movzx   eax, word ptr [rdi+140h]
0x180086ebc  mov     [rsi+0Ch], ax
0x180086ec0  movzx   eax, word ptr [rdi+142h]
0x180086ec7  mov     [rsi+0Eh], ax
0x180086ecb  mov     eax, [rdi+148h]
0x180086ed1  mov     [rsi+14h], eax
0x180086ed4  mov     eax, [rdi+14Ch]
0x180086eda  mov     [rsi+18h], eax
0x180086edd  mov     eax, [rdi+150h]
0x180086ee3  mov     [rsi+1Ch], eax
0x180086ee6  mov     eax, [rdi+154h]
0x180086eec  mov     [rsi+20h], eax
0x180086eef  mov     eax, [rdi+158h]
0x180086ef5  mov     [rsi+8], ecx
0x180086ef8  lea     rcx, [rsi+28h]; void *
0x180086efc  mov     [rsi+24h], eax
0x180086eff  call    memcpy_0
0x180086f04  mov     eax, [rdi+134h]
0x180086f0a  cmp     eax, 38h ; '8'
0x180086f0d  jz      short loc_180086F19
0x180086f0f  cmp     eax, 6Ch ; 'l'
0x180086f12  jz      short loc_180086F19
0x180086f14  cmp     eax, 7Ch ; '|'
0x180086f17  jnz     short loc_180086F39
0x180086f19  cmp     ebx, 3
0x180086f1c  jnz     short loc_180086F39
0x180086f1e  mov     eax, [rdi+15Ch]
0x180086f24  mov     [rsi+28h], eax
0x180086f27  mov     eax, [rdi+160h]
0x180086f2d  mov     [rsi+2Ch], eax
0x180086f30  mov     eax, [rdi+164h]
0x180086f36  mov     [rsi+30h], eax
0x180086f39  call    IsSetDIBitsPresent
0x180086f3e  test    al, al
0x180086f40  jz      loc_180086E5B
0x180086f46  mov     r9d, [rdi+0B4h]; cLines
0x180086f4d  xor     r8d, r8d; start
0x180086f50  mov     rdx, [rdi+5B0h]; hbm
0x180086f57  xor     ecx, ecx; hdc
0x180086f59  mov     [rsp+0C0h+ColorUse], r13d; ColorUse
0x180086f5e  mov     qword ptr [rsp+0C0h+offset], rsi; lpbmi
0x180086f63  mov     [rsp+0C0h+hSection], r14; lpBits
0x180086f68  call    cs:__imp_SetDIBits
0x180086f6e  mov     rcx, rsi; Block
0x180086f71  mov     ebx, eax
0x180086f73  call    cs:__imp_free
0x180086f79  mov     rcx, r14; Block
0x180086f7c  call    cs:__imp_free
0x180086f82  cmp     ebx, [rdi+0B4h]
0x180086f88  jz      short loc_180086FD9
0x180086f8a  call    IsDeleteObjectPresent
0x180086f8f  test    al, al
0x180086f91  jnz     short loc_180086F9D
0x180086f93  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180086f98  jmp     loc_180086E5B
0x180086f9d  mov     rcx, [rdi+5B0h]; ho
0x180086fa4  call    cs:__imp_DeleteObject
0x180086faa  mov     [rdi+5B0h], r13
0x180086fb1  mov     [r15], r13
0x180086fb4  mov     eax, 88982F60h
0x180086fb9  mov     rcx, [rbp+57h+var_48]
0x180086fbd  xor     rcx, rsp; StackCookie
0x180086fc0  call    __security_check_cookie
0x180086fc5  add     rsp, 88h
0x180086fcc  pop     r15
0x180086fce  pop     r14
0x180086fd0  pop     r13
0x180086fd2  pop     r12
0x180086fd4  pop     rdi
0x180086fd5  pop     rsi
0x180086fd6  pop     rbx
0x180086fd7  pop     rbp
0x180086fd8  retn
0x180086fd9  xor     eax, eax
0x180086fdb  jmp     short loc_180086FB9
```

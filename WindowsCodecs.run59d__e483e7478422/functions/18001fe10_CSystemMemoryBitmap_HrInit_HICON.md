# CSystemMemoryBitmap::HrInit(HICON__ *)

- ea: `0x18001fe10`
- end: `0x180020153`
- name: `?HrInit@CSystemMemoryBitmap@@QEAAJPEAUHICON__@@@Z`
- size: `835`
- prototype: `int(CSystemMemoryBitmap *__hidden this, HICON)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18001fba0`

## callees

- `0x18001e7b8`
- `0x18001fe10`
- `0x18002015c`
- `0x18002065c`
- `0x1800bd9d4`
- `0x1800c7f24`
- `0x1800cc0d4`
- `0x18017dacc`
- `0x18017dd80`
- `0x18017e058`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ffc6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ffd6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ffc6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001ffd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fe5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fe5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200c1`
- `ext-ms-win-ntuser-gui-l1-1-0!GetIconInfo` at `0x18001fe6e`
- `ext-ms-win-ntuser-gui-l1-1-0!GetIconInfo` at `0x18001fe6e`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18001fee9`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18001fee9`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18002000f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18002002a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18002000f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18002002a`

## pseudocode

```c
__int64 __fastcall CSystemMemoryBitmap::HrInit(CSystemMemoryBitmap *this, HICON a2)
{
  struct tagBITMAPINFO *v4; // rdi
  int BitmapData; // eax
  unsigned int v6; // ebx
  unsigned int v7; // eax
  void *v8; // rsi
  _BYTE *v9; // rcx
  int v10; // eax
  signed int LastError; // eax
  void *v13; // [rsp+38h] [rbp-19h] BYREF
  ICONINFO piconinfo; // [rsp+40h] [rbp-11h] BYREF
  __int128 pv; // [rsp+60h] [rbp+Fh] BYREF
  __int128 v16; // [rsp+70h] [rbp+1Fh]
  void *Block; // [rsp+C8h] [rbp+77h] BYREF
  void *v18; // [rsp+D0h] [rbp+7Fh] BYREF

  v4 = 0;
  Block = 0;
  v18 = 0;
  v13 = 0;
  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( !(unsigned __int8)IsGetIconInfoPresent() )
  {
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147467263);
    v6 = -2147467263;
    goto LABEL_18;
  }
  SetLastError(0);
  if ( !GetIconInfo(a2, &piconinfo) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (v6 & 0x80000000) == 0 )
      v6 = -2003292268;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v6);
    goto LABEL_18;
  }
  if ( piconinfo.hbmColor )
  {
    BitmapData = HrGetBitmapData(piconinfo.hbmColor, 0, 0x20u, (struct tagBITMAPINFO **)&Block, &v18, &v13);
    v6 = BitmapData;
    if ( BitmapData >= 0 )
    {
      pv = 0;
      v16 = 0;
      if ( !(unsigned __int8)IsGetObjectAPresent() )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(-2147467263);
        v4 = (struct tagBITMAPINFO *)Block;
        v6 = -2147467263;
        goto LABEL_18;
      }
      if ( GetObjectW(piconinfo.hbmColor, 32, &pv) && (_DWORD)v16 == 2097153 )
      {
        v4 = (struct tagBITMAPINFO *)Block;
        v7 = 0;
        v8 = v18;
        v9 = (char *)v18 + 3;
        while ( v7 < *((_DWORD *)Block + 1) * *((_DWORD *)Block + 2) )
        {
          if ( *v9 )
            goto LABEL_13;
          v9 += 4;
          ++v7;
        }
      }
      else
      {
        v4 = (struct tagBITMAPINFO *)Block;
        v8 = v18;
      }
      v10 = HrMaskIcon(piconinfo.hbmMask, v4, v8);
      v6 = v10;
      if ( v10 < 0 )
      {
        if ( !(_DWORD)g_doStackCaptures )
          goto LABEL_18;
LABEL_26:
        DoStackCapture(v10);
        goto LABEL_18;
      }
      goto LABEL_13;
    }
LABEL_15:
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(BitmapData);
    v4 = (struct tagBITMAPINFO *)Block;
    goto LABEL_18;
  }
  BitmapData = HrMaskMonochromeIcon(piconinfo.hbmMask, (struct tagBITMAPINFO **)&Block, &v18, &v13);
  v6 = BitmapData;
  if ( BitmapData < 0 )
    goto LABEL_15;
  v4 = (struct tagBITMAPINFO *)Block;
  v8 = v18;
LABEL_13:
  v10 = CSystemMemoryBitmap::HrInitFromBitmapInfo(this, v4, 2);
  v6 = v10;
  if ( v10 >= 0 )
  {
    *((_QWORD *)this + 30) = v13;
    *((_DWORD *)this + 32) = 15;
    *((_QWORD *)this + 29) = v8;
    v13 = 0;
    goto LABEL_18;
  }
  if ( (_DWORD)g_doStackCaptures )
    goto LABEL_26;
  while ( 1 )
  {
LABEL_18:
    free(v4);
    free(v13);
    if ( piconinfo.hbmMask )
    {
      if ( !(unsigned __int8)IsDeleteObjectPresent() )
        goto LABEL_27;
      DeleteObject(piconinfo.hbmMask);
    }
    if ( !piconinfo.hbmColor )
      return v6;
    if ( (unsigned __int8)IsDeleteObjectPresent() )
      break;
LABEL_27:
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147467263);
    v6 = -2147467263;
  }
  DeleteObject(piconinfo.hbmColor);
  return v6;
}

```

## disassembly

```asm
0x18001fe10  mov     rax, rsp
0x18001fe13  push    rbp
0x18001fe14  push    rbx
0x18001fe15  push    rdi
0x18001fe16  lea     rbp, [rax-5Fh]
0x18001fe1a  sub     rsp, 90h
0x18001fe21  mov     [rax-20h], r14
0x18001fe25  xorps   xmm0, xmm0
0x18001fe28  mov     [rax-28h], r15
0x18001fe2c  mov     rbx, rdx
0x18001fe2f  xor     r15d, r15d
0x18001fe32  mov     r14, rcx
0x18001fe35  mov     edi, r15d
0x18001fe38  mov     [rbp+57h+Block], r15
0x18001fe3c  mov     [rbp+57h+arg_18], r15
0x18001fe40  mov     [rbp+57h+var_70], r15
0x18001fe44  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x18001fe48  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x18001fe4c  call    IsGetIconInfoPresent
0x18001fe51  test    al, al
0x18001fe53  jz      loc_180020100
0x18001fe59  xor     ecx, ecx; dwErrCode
0x18001fe5b  call    cs:__imp_SetLastError
0x18001fe62  nop     dword ptr [rax+rax+00h]
0x18001fe67  lea     rdx, [rbp+57h+piconinfo]; piconinfo
0x18001fe6b  mov     rcx, rbx; hIcon
0x18001fe6e  call    cs:__imp_GetIconInfo
0x18001fe75  nop     dword ptr [rax+rax+00h]
0x18001fe7a  test    eax, eax
0x18001fe7c  jz      loc_1800200C1
0x18001fe82  mov     rcx, [rbp+57h+piconinfo.hbmColor]; HBITMAP
0x18001fe86  mov     [rsp+0A0h+arg_0], rsi
0x18001fe8e  test    rcx, rcx
0x18001fe91  jz      loc_180020095
0x18001fe97  lea     rax, [rbp+57h+var_70]
0x18001fe9b  mov     r8d, 20h ; ' '; unsigned __int16
0x18001fea1  mov     [rsp+28h], rax; void **
0x18001fea6  lea     r9, [rbp+57h+Block]; struct tagBITMAPINFO **
0x18001feaa  lea     rax, [rbp+57h+arg_18]
0x18001feae  xor     edx, edx; HPALETTE
0x18001feb0  mov     [rsp+0A0h+var_80], rax; void **
0x18001feb5  call    ?HrGetBitmapData@@YAJPEAUHBITMAP__@@PEAUHPALETTE__@@GPEAPEAUtagBITMAPINFO@@PEAPEAX3@Z; HrGetBitmapData(HBITMAP__ *,HPALETTE__ *,ushort,tagBITMAPINFO * *,void * *,void * *)
0x18001feba  mov     ebx, eax
0x18001febc  test    eax, eax
0x18001febe  js      loc_18001FF98
0x18001fec4  xorps   xmm0, xmm0
0x18001fec7  movups  [rbp+57h+pv], xmm0
0x18001fecb  movups  [rbp+57h+var_38], xmm0
0x18001fecf  call    IsGetObjectAPresent
0x18001fed4  test    al, al
0x18001fed6  jz      loc_18002011C
0x18001fedc  mov     rcx, [rbp+57h+piconinfo.hbmColor]; h
0x18001fee0  lea     r8, [rbp+57h+pv]; pv
0x18001fee4  mov     edx, 20h ; ' '; c
0x18001fee9  call    cs:__imp_GetObjectW
0x18001fef0  nop     dword ptr [rax+rax+00h]
0x18001fef5  test    eax, eax
0x18001fef7  jz      loc_18002013C
0x18001fefd  cmp     word ptr [rbp+57h+var_38+2], 20h ; ' '
0x18001ff02  jnz     loc_18002013C
0x18001ff08  cmp     word ptr [rbp+57h+var_38], 1
0x18001ff0d  jnz     loc_18002013C
0x18001ff13  mov     rdi, [rbp+57h+Block]
0x18001ff17  mov     eax, r15d
0x18001ff1a  mov     rsi, [rbp+57h+arg_18]
0x18001ff1e  mov     edx, [rdi+8]
0x18001ff21  imul    edx, [rdi+4]
0x18001ff25  lea     rcx, [rsi+3]
0x18001ff29  nop     dword ptr [rax+00000000h]
0x18001ff30  cmp     eax, edx
0x18001ff32  jnb     short loc_18001FF41
0x18001ff34  cmp     [rcx], r15b
0x18001ff37  jnz     short loc_18001FF5A
0x18001ff39  add     rcx, 4
0x18001ff3d  inc     eax
0x18001ff3f  jmp     short loc_18001FF30
0x18001ff41  mov     rcx, [rbp+57h+piconinfo.hbmMask]; HBITMAP
0x18001ff45  mov     r8, rsi; void *
0x18001ff48  mov     rdx, rdi; struct tagBITMAPINFO *
0x18001ff4b  call    ?HrMaskIcon@@YAJPEAUHBITMAP__@@PEAUtagBITMAPINFO@@PEAX@Z; HrMaskIcon(HBITMAP__ *,tagBITMAPINFO *,void *)
0x18001ff50  mov     ebx, eax
0x18001ff52  test    eax, eax
0x18001ff54  js      loc_18002007C
0x18001ff5a  mov     r8d, 2
0x18001ff60  mov     rdx, rdi
0x18001ff63  mov     rcx, r14
0x18001ff66  call    ?HrInitFromBitmapInfo@CSystemMemoryBitmap@@AEAAJPEAUtagBITMAPINFO@@W4Enum@MilBitmapAlphaChannelOption@@@Z; CSystemMemoryBitmap::HrInitFromBitmapInfo(tagBITMAPINFO *,MilBitmapAlphaChannelOption::Enum)
0x18001ff6b  mov     ebx, eax
0x18001ff6d  test    eax, eax
0x18001ff6f  js      loc_180020038
0x18001ff75  mov     rax, [rbp+57h+var_70]
0x18001ff79  mov     [r14+0F0h], rax
0x18001ff80  mov     dword ptr [r14+80h], 0Fh
0x18001ff8b  mov     [r14+0E8h], rsi
0x18001ff92  mov     [rbp+57h+var_70], r15
0x18001ff96  jmp     short loc_18001FFAB
0x18001ff98  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18001ff9e  jz      short loc_18001FFA7
0x18001ffa0  mov     ecx, eax; int
0x18001ffa2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001ffa7  mov     rdi, [rbp+57h+Block]
0x18001ffab  mov     rsi, [rsp+0A0h+arg_0]
0x18001ffb3  mov     r15, [rsp+0A0h+var_20]
0x18001ffbb  mov     r14, [rsp+88h]
0x18001ffc3  mov     rcx, rdi; Block
0x18001ffc6  call    cs:__imp_free
0x18001ffcd  nop     dword ptr [rax+rax+00h]
0x18001ffd2  mov     rcx, [rbp+57h+var_70]; Block
0x18001ffd6  call    cs:__imp_free
0x18001ffdd  nop     dword ptr [rax+rax+00h]
0x18001ffe2  cmp     [rbp+57h+piconinfo.hbmMask], 0
0x18001ffe7  jnz     short loc_18001FFFE
0x18001ffe9  cmp     [rbp+57h+piconinfo.hbmColor], 0
0x18001ffee  jnz     short loc_18002001D
0x18001fff0  mov     eax, ebx
0x18001fff2  add     rsp, 90h
0x18001fff9  pop     rdi
0x18001fffa  pop     rbx
0x18001fffb  pop     rbp
0x18001fffc  retn
0x18001fffe  call    IsDeleteObjectPresent
0x180020003  test    al, al
0x180020005  jz      loc_180020149
0x18002000b  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x18002000f  call    cs:__imp_DeleteObject
0x180020016  nop     dword ptr [rax+rax+00h]
0x18002001b  jmp     short loc_18001FFE9
0x18002001d  call    IsDeleteObjectPresent
0x180020022  test    al, al
0x180020024  jz      short loc_18002004D
0x180020026  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x18002002a  call    cs:__imp_DeleteObject
0x180020031  nop     dword ptr [rax+rax+00h]
0x180020036  jmp     short loc_18001FFF0
0x180020038  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18002003f  jz      short loc_18002006F
0x180020041  mov     ecx, eax; int
0x180020043  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020048  jmp     loc_18001FFAB
0x18002004d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020052  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180020059  jz      short loc_180020065
0x18002005b  mov     ecx, 80004001h; int
0x180020060  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020065  mov     ebx, 80004001h
0x18002006a  jmp     loc_18001FFC3
0x18002006f  test    eax, eax
0x180020071  js      loc_18001FFAB
0x180020077  jmp     loc_18001FF75
0x18002007c  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180020083  jz      loc_18001FFAB
0x180020089  mov     ecx, eax; int
0x18002008b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020090  jmp     loc_18001FFAB
0x180020095  mov     rcx, [rbp+57h+piconinfo.hbmMask]; HBITMAP
0x180020099  lea     r9, [rbp+57h+var_70]; void **
0x18002009d  lea     r8, [rbp+57h+arg_18]; void **
0x1800200a1  lea     rdx, [rbp+57h+Block]; struct tagBITMAPINFO **
0x1800200a5  call    ?HrMaskMonochromeIcon@@YAJPEAUHBITMAP__@@PEAPEAUtagBITMAPINFO@@PEAPEAX2@Z; HrMaskMonochromeIcon(HBITMAP__ *,tagBITMAPINFO * *,void * *,void * *)
0x1800200aa  mov     ebx, eax
0x1800200ac  test    eax, eax
0x1800200ae  js      loc_18001FF98
0x1800200b4  mov     rdi, [rbp+57h+Block]
0x1800200b8  mov     rsi, [rbp+57h+arg_18]
0x1800200bc  jmp     loc_18001FF5A
0x1800200c1  call    cs:__imp_GetLastError
0x1800200c8  nop     dword ptr [rax+rax+00h]
0x1800200cd  mov     ebx, eax
0x1800200cf  test    eax, eax
0x1800200d1  jg      short loc_1800200F5
0x1800200d3  test    ebx, ebx
0x1800200d5  mov     eax, 88982F94h
0x1800200da  cmovns  ebx, eax
0x1800200dd  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800200e3  jz      loc_18001FFB3
0x1800200e9  mov     ecx, ebx; int
0x1800200eb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800200f0  jmp     loc_18001FFB3
0x1800200f5  movzx   ebx, ax
0x1800200f8  or      ebx, 80070000h
0x1800200fe  jmp     short loc_1800200D3
0x180020100  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180020106  jz      short loc_180020112
0x180020108  mov     ecx, 80004001h; int
0x18002010d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180020112  mov     ebx, 80004001h
0x180020117  jmp     loc_18001FFB3
0x18002011c  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180020122  jz      short loc_18002012E
0x180020124  mov     ecx, 80004001h; int
0x180020129  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002012e  mov     rdi, [rbp+57h+Block]
0x180020132  mov     ebx, 80004001h
0x180020137  jmp     loc_18001FFAB
0x18002013c  mov     rdi, [rbp+57h+Block]
0x180020140  mov     rsi, [rbp+57h+arg_18]
0x180020144  jmp     loc_18001FF41
0x180020149  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002014e  jmp     loc_180020052
```

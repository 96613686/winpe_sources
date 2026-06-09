# CSystemMemoryBitmap::HrInit(HICON__ *)

- ea: `0x18007ffc0`
- end: `0x1800802cb`
- name: `?HrInit@CSystemMemoryBitmap@@QEAAJPEAUHICON__@@@Z`
- size: `779`
- prototype: `__int64 __fastcall(CSystemMemoryBitmap *this, HICON)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003e3ac`

## callees

- `0x18007fc2c`
- `0x18007ffc0`
- `0x1800802d4`
- `0x18008076c`
- `0x1800bb784`
- `0x1800c5adc`
- `0x1800c9be8`
- `0x18017abbc`
- `0x18017ae70`
- `0x18017b148`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008015d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180080167`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008015d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180080167`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008000b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18008000b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008023f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008023f`
- `ext-ms-win-ntuser-gui-l1-1-0!GetIconInfo` at `0x180080018`
- `ext-ms-win-ntuser-gui-l1-1-0!GetIconInfo` at `0x180080018`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18008008d`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x18008008d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180080199`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800801ae`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180080199`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800801ae`

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
  v10 = CSystemMemoryBitmap::HrInitFromBitmapInfo((__int64)this, (__int64)v4, 2);
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
0x18007ffc0  mov     rax, rsp
0x18007ffc3  push    rbp
0x18007ffc4  push    rbx
0x18007ffc5  push    rdi
0x18007ffc6  lea     rbp, [rax-5Fh]
0x18007ffca  sub     rsp, 90h
0x18007ffd1  mov     [rax-20h], r14
0x18007ffd5  xorps   xmm0, xmm0
0x18007ffd8  mov     [rax-28h], r15
0x18007ffdc  mov     rbx, rdx
0x18007ffdf  xor     r15d, r15d
0x18007ffe2  mov     r14, rcx
0x18007ffe5  mov     edi, r15d
0x18007ffe8  mov     [rbp+57h+Block], r15
0x18007ffec  mov     [rbp+57h+arg_18], r15
0x18007fff0  mov     [rbp+57h+var_70], r15
0x18007fff4  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x18007fff8  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x18007fffc  call    IsGetIconInfoPresent
0x180080001  test    al, al
0x180080003  jz      loc_180080278
0x180080009  xor     ecx, ecx; dwErrCode
0x18008000b  call    cs:__imp_SetLastError
0x180080011  lea     rdx, [rbp+57h+piconinfo]; piconinfo
0x180080015  mov     rcx, rbx; hIcon
0x180080018  call    cs:__imp_GetIconInfo
0x18008001e  test    eax, eax
0x180080020  jz      loc_18008023F
0x180080026  mov     rcx, [rbp+57h+piconinfo.hbmColor]; HBITMAP
0x18008002a  mov     [rsp+0A0h+arg_0], rsi
0x180080032  test    rcx, rcx
0x180080035  jz      loc_180080213
0x18008003b  lea     rax, [rbp+57h+var_70]
0x18008003f  mov     r8d, 20h ; ' '; unsigned __int16
0x180080045  mov     [rsp+28h], rax; void **
0x18008004a  lea     r9, [rbp+57h+Block]; struct tagBITMAPINFO **
0x18008004e  lea     rax, [rbp+57h+arg_18]
0x180080052  xor     edx, edx; HPALETTE
0x180080054  mov     [rsp+0A0h+var_80], rax; void **
0x180080059  call    ?HrGetBitmapData@@YAJPEAUHBITMAP__@@PEAUHPALETTE__@@GPEAPEAUtagBITMAPINFO@@PEAPEAX3@Z; HrGetBitmapData(HBITMAP__ *,HPALETTE__ *,ushort,tagBITMAPINFO * *,void * *,void * *)
0x18008005e  mov     ebx, eax
0x180080060  test    eax, eax
0x180080062  js      loc_18008012F
0x180080068  xorps   xmm0, xmm0
0x18008006b  movups  [rbp+57h+pv], xmm0
0x18008006f  movups  [rbp+57h+var_38], xmm0
0x180080073  call    IsGetObjectAPresent
0x180080078  test    al, al
0x18008007a  jz      loc_180080294
0x180080080  mov     rcx, [rbp+57h+piconinfo.hbmColor]; h
0x180080084  lea     r8, [rbp+57h+pv]; pv
0x180080088  mov     edx, 20h ; ' '; c
0x18008008d  call    cs:__imp_GetObjectW
0x180080093  test    eax, eax
0x180080095  jz      loc_1800802B4
0x18008009b  cmp     word ptr [rbp+57h+var_38+2], 20h ; ' '
0x1800800a0  jnz     loc_1800802B4
0x1800800a6  cmp     word ptr [rbp+57h+var_38], 1
0x1800800ab  jnz     loc_1800802B4
0x1800800b1  mov     rdi, [rbp+57h+Block]
0x1800800b5  mov     eax, r15d
0x1800800b8  mov     rsi, [rbp+57h+arg_18]
0x1800800bc  mov     edx, [rdi+8]
0x1800800bf  imul    edx, [rdi+4]
0x1800800c3  lea     rcx, [rsi+3]
0x1800800c7  cmp     eax, edx
0x1800800c9  jnb     short loc_1800800D8
0x1800800cb  cmp     [rcx], r15b
0x1800800ce  jnz     short loc_1800800F1
0x1800800d0  add     rcx, 4
0x1800800d4  inc     eax
0x1800800d6  jmp     short loc_1800800C7
0x1800800d8  mov     rcx, [rbp+57h+piconinfo.hbmMask]; HBITMAP
0x1800800dc  mov     r8, rsi; void *
0x1800800df  mov     rdx, rdi; struct tagBITMAPINFO *
0x1800800e2  call    ?HrMaskIcon@@YAJPEAUHBITMAP__@@PEAUtagBITMAPINFO@@PEAX@Z; HrMaskIcon(HBITMAP__ *,tagBITMAPINFO *,void *)
0x1800800e7  mov     ebx, eax
0x1800800e9  test    eax, eax
0x1800800eb  js      loc_1800801FA
0x1800800f1  mov     r8d, 2
0x1800800f7  mov     rdx, rdi
0x1800800fa  mov     rcx, r14
0x1800800fd  call    ?HrInitFromBitmapInfo@CSystemMemoryBitmap@@AEAAJPEAUtagBITMAPINFO@@W4Enum@MilBitmapAlphaChannelOption@@@Z; CSystemMemoryBitmap::HrInitFromBitmapInfo(tagBITMAPINFO *,MilBitmapAlphaChannelOption::Enum)
0x180080102  mov     ebx, eax
0x180080104  test    eax, eax
0x180080106  js      loc_1800801B6
0x18008010c  mov     rax, [rbp+57h+var_70]
0x180080110  mov     [r14+0F0h], rax
0x180080117  mov     dword ptr [r14+80h], 0Fh
0x180080122  mov     [r14+0E8h], rsi
0x180080129  mov     [rbp+57h+var_70], r15
0x18008012d  jmp     short loc_180080142
0x18008012f  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180080135  jz      short loc_18008013E
0x180080137  mov     ecx, eax; int
0x180080139  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008013e  mov     rdi, [rbp+57h+Block]
0x180080142  mov     rsi, [rsp+0A0h+arg_0]
0x18008014a  mov     r15, [rsp+0A0h+var_20]
0x180080152  mov     r14, [rsp+88h]
0x18008015a  mov     rcx, rdi; Block
0x18008015d  call    cs:__imp_free
0x180080163  mov     rcx, [rbp+57h+var_70]; Block
0x180080167  call    cs:__imp_free
0x18008016d  cmp     [rbp+57h+piconinfo.hbmMask], 0
0x180080172  jnz     short loc_180080188
0x180080174  cmp     [rbp+57h+piconinfo.hbmColor], 0
0x180080179  jnz     short loc_1800801A1
0x18008017b  mov     eax, ebx
0x18008017d  add     rsp, 90h
0x180080184  pop     rdi
0x180080185  pop     rbx
0x180080186  pop     rbp
0x180080187  retn
0x180080188  call    IsDeleteObjectPresent
0x18008018d  test    al, al
0x18008018f  jz      loc_1800802C1
0x180080195  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x180080199  call    cs:__imp_DeleteObject
0x18008019f  jmp     short loc_180080174
0x1800801a1  call    IsDeleteObjectPresent
0x1800801a6  test    al, al
0x1800801a8  jz      short loc_1800801CB
0x1800801aa  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x1800801ae  call    cs:__imp_DeleteObject
0x1800801b4  jmp     short loc_18008017B
0x1800801b6  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x1800801bd  jz      short loc_1800801ED
0x1800801bf  mov     ecx, eax; int
0x1800801c1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800801c6  jmp     loc_180080142
0x1800801cb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800801d0  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800801d7  jz      short loc_1800801E3
0x1800801d9  mov     ecx, 80004001h; int
0x1800801de  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800801e3  mov     ebx, 80004001h
0x1800801e8  jmp     loc_18008015A
0x1800801ed  test    eax, eax
0x1800801ef  js      loc_180080142
0x1800801f5  jmp     loc_18008010C
0x1800801fa  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x180080201  jz      loc_180080142
0x180080207  mov     ecx, eax; int
0x180080209  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008020e  jmp     loc_180080142
0x180080213  mov     rcx, [rbp+57h+piconinfo.hbmMask]; HBITMAP
0x180080217  lea     r9, [rbp+57h+var_70]; void **
0x18008021b  lea     r8, [rbp+57h+arg_18]; void **
0x18008021f  lea     rdx, [rbp+57h+Block]; struct tagBITMAPINFO **
0x180080223  call    ?HrMaskMonochromeIcon@@YAJPEAUHBITMAP__@@PEAPEAUtagBITMAPINFO@@PEAPEAX2@Z; HrMaskMonochromeIcon(HBITMAP__ *,tagBITMAPINFO * *,void * *,void * *)
0x180080228  mov     ebx, eax
0x18008022a  test    eax, eax
0x18008022c  js      loc_18008012F
0x180080232  mov     rdi, [rbp+57h+Block]
0x180080236  mov     rsi, [rbp+57h+arg_18]
0x18008023a  jmp     loc_1800800F1
0x18008023f  call    cs:__imp_GetLastError
0x180080245  mov     ebx, eax
0x180080247  test    eax, eax
0x180080249  jg      short loc_18008026D
0x18008024b  test    ebx, ebx
0x18008024d  mov     eax, 88982F94h
0x180080252  cmovns  ebx, eax
0x180080255  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18008025b  jz      loc_18008014A
0x180080261  mov     ecx, ebx; int
0x180080263  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180080268  jmp     loc_18008014A
0x18008026d  movzx   ebx, ax
0x180080270  or      ebx, 80070000h
0x180080276  jmp     short loc_18008024B
0x180080278  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18008027e  jz      short loc_18008028A
0x180080280  mov     ecx, 80004001h; int
0x180080285  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18008028a  mov     ebx, 80004001h
0x18008028f  jmp     loc_18008014A
0x180080294  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x18008029a  jz      short loc_1800802A6
0x18008029c  mov     ecx, 80004001h; int
0x1800802a1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800802a6  mov     rdi, [rbp+57h+Block]
0x1800802aa  mov     ebx, 80004001h
0x1800802af  jmp     loc_180080142
0x1800802b4  mov     rdi, [rbp+57h+Block]
0x1800802b8  mov     rsi, [rbp+57h+arg_18]
0x1800802bc  jmp     loc_1800800D8
0x1800802c1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800802c6  jmp     loc_1800801D0
```

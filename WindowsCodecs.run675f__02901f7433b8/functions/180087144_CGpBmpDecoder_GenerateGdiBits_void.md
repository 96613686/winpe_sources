# CGpBmpDecoder::GenerateGdiBits(void)

- ea: `0x180087144`
- end: `0x180087470`
- name: `?GenerateGdiBits@CGpBmpDecoder@@AEAAJXZ`
- size: `812`
- prototype: `__int64 __fastcall(CGpBmpDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180087000`

## callees

- `0x18006c790`
- `0x18006c860`
- `0x18006cdbc`
- `0x180087144`
- `0x1800bd9d4`
- `0x1800cc0d4`
- `0x1800e5e60`
- `0x18017df54`
- `0x18017e058`
- `0x18017e438`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800872ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800873f3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180087402`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800872ee`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800873f3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180087402`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18008719f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800872a7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18008719f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800872a7`
- `ext-ms-win-gdi-draw-l1-1-0!SetDIBits` at `0x1800873e2`
- `ext-ms-win-gdi-draw-l1-1-0!SetDIBits` at `0x1800873e2`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18008726f`
- `ext-ms-win-gdi-draw-l1-1-0!CreateDIBSection` at `0x18008726f`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800872da`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180087430`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800872da`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180087430`

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
0x180087144  push    rbp
0x180087146  push    rbx
0x180087147  push    rsi
0x180087148  push    rdi
0x180087149  push    r12
0x18008714b  push    r13
0x18008714d  push    r14
0x18008714f  push    r15
0x180087151  lea     rbp, [rsp-1Fh]
0x180087156  sub     rsp, 88h
0x18008715d  mov     rax, cs:__security_cookie
0x180087164  xor     rax, rsp
0x180087167  mov     [rbp+57h+var_48], rax
0x18008716b  mov     rdi, rcx
0x18008716e  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x180087172  mov     rcx, [rcx+78h]; this
0x180087176  xor     r13d, r13d
0x180087179  mov     [rbp+57h+var_80], r13d
0x18008717d  call    ?HrGetSize@CStreamBase@@QEAAJPEAI@Z; CStreamBase::HrGetSize(uint *)
0x180087182  test    eax, eax
0x180087184  js      loc_180087446
0x18008718a  mov     eax, [rdi+12Eh]
0x180087190  mov     esi, [rbp+57h+var_80]
0x180087193  cmp     eax, esi
0x180087195  ja      loc_180087446
0x18008719b  sub     esi, eax
0x18008719d  mov     ecx, esi; Size
0x18008719f  call    cs:__imp_malloc
0x1800871a6  nop     dword ptr [rax+rax+00h]
0x1800871ab  mov     r14, rax
0x1800871ae  test    rax, rax
0x1800871b1  jnz     short loc_1800871BD
0x1800871b3  mov     eax, 8007000Eh
0x1800871b8  jmp     loc_18008744B
0x1800871bd  mov     edx, [rdi+12Eh]; unsigned int
0x1800871c3  mov     rcx, [rdi+78h]; this
0x1800871c7  call    ?HrSeek@CStreamBase@@QEAAJIK@Z; CStreamBase::HrSeek(uint,ulong)
0x1800871cc  mov     ebx, eax
0x1800871ce  test    eax, eax
0x1800871d0  js      short loc_1800871E9
0x1800871d2  xor     r9d, r9d; unsigned int *
0x1800871d5  mov     r8d, esi; unsigned int
0x1800871d8  mov     rdx, r14; void *
0x1800871db  mov     rcx, rdi; this
0x1800871de  call    ?HrRead@CDecoderBase@@IEAAJPEAXIPEAI@Z; CDecoderBase::HrRead(void *,uint,uint *)
0x1800871e3  mov     ebx, eax
0x1800871e5  test    eax, eax
0x1800871e7  jns     short loc_180087202
0x1800871e9  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800871f0  jz      loc_1800872EB
0x1800871f6  mov     ecx, eax; int
0x1800871f8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800871fd  jmp     loc_1800872EB
0x180087202  mov     eax, [rdi+138h]
0x180087208  mov     ebx, 28h ; '('
0x18008720d  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x180087210  mov     eax, [rdi+13Ch]
0x180087216  mov     ecx, eax
0x180087218  neg     ecx
0x18008721a  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], r13
0x18008721e  mov     [rbp+57h+pbmi.bmiHeader.biSize], ebx
0x180087221  cmovs   ecx, eax
0x180087224  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18008722c  mov     eax, [rdi+14Ch]
0x180087232  mov     [rbp+57h+pbmi.bmiHeader.biXPelsPerMeter], eax
0x180087235  mov     eax, [rdi+150h]
0x18008723b  mov     [rbp+57h+pbmi.bmiHeader.biYPelsPerMeter], eax
0x18008723e  mov     [rbp+57h+pbmi.bmiHeader.biHeight], ecx
0x180087241  mov     [rbp+57h+pbmi.bmiHeader.biSizeImage], r13d
0x180087245  mov     [rbp+57h+pbmi.bmiHeader.biClrUsed], r13d
0x180087249  call    IsSetDIBitsPresent
0x18008724e  test    al, al
0x180087250  jz      short loc_1800872C9
0x180087252  lea     r15, [rdi+5B8h]
0x180087259  mov     [rsp+0C0h+offset], r13d; offset
0x18008725e  mov     r9, r15; ppvBits
0x180087261  mov     [rsp+0C0h+hSection], r13; hSection
0x180087266  xor     r8d, r8d; usage
0x180087269  lea     rdx, [rbp+57h+pbmi]; pbmi
0x18008726d  xor     ecx, ecx; hdc
0x18008726f  call    cs:__imp_CreateDIBSection
0x180087276  nop     dword ptr [rax+rax+00h]
0x18008727b  mov     [rdi+5B0h], rax
0x180087282  test    rax, rax
0x180087285  jnz     short loc_18008728E
0x180087287  mov     ebx, 88982F60h
0x18008728c  jmp     short loc_1800872EB
0x18008728e  mov     eax, [rdi+148h]
0x180087294  test    eax, eax
0x180087296  jz      short loc_18008729C
0x180087298  cmp     eax, esi
0x18008729a  jbe     short loc_1800872A2
0x18008729c  mov     [rdi+148h], esi
0x1800872a2  mov     ecx, 428h; Size
0x1800872a7  call    cs:__imp_malloc
0x1800872ae  nop     dword ptr [rax+rax+00h]
0x1800872b3  mov     rsi, rax
0x1800872b6  test    rax, rax
0x1800872b9  jnz     short loc_180087301
0x1800872bb  call    IsDeleteObjectPresent
0x1800872c0  test    al, al
0x1800872c2  jnz     short loc_1800872D3
0x1800872c4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800872c9  mov     eax, 80004001h
0x1800872ce  jmp     loc_18008744B
0x1800872d3  mov     rcx, [rdi+5B0h]; ho
0x1800872da  call    cs:__imp_DeleteObject
0x1800872e1  nop     dword ptr [rax+rax+00h]
0x1800872e6  mov     ebx, 8007000Eh
0x1800872eb  mov     rcx, r14; Block
0x1800872ee  call    cs:__imp_free
0x1800872f5  nop     dword ptr [rax+rax+00h]
0x1800872fa  mov     eax, ebx
0x1800872fc  jmp     loc_18008744B
0x180087301  mov     [rax], ebx
0x180087303  lea     rdx, [rdi+1B0h]; Src
0x18008730a  mov     eax, [rdi+138h]
0x180087310  mov     r8d, 400h; Size
0x180087316  mov     ebx, [rdi+144h]
0x18008731c  mov     [rsi+4], eax
0x18008731f  mov     eax, [rdi+13Ch]
0x180087325  mov     ecx, eax
0x180087327  neg     ecx
0x180087329  mov     [rsi+10h], ebx
0x18008732c  cmovs   ecx, eax
0x18008732f  movzx   eax, word ptr [rdi+140h]
0x180087336  mov     [rsi+0Ch], ax
0x18008733a  movzx   eax, word ptr [rdi+142h]
0x180087341  mov     [rsi+0Eh], ax
0x180087345  mov     eax, [rdi+148h]
0x18008734b  mov     [rsi+14h], eax
0x18008734e  mov     eax, [rdi+14Ch]
0x180087354  mov     [rsi+18h], eax
0x180087357  mov     eax, [rdi+150h]
0x18008735d  mov     [rsi+1Ch], eax
0x180087360  mov     eax, [rdi+154h]
0x180087366  mov     [rsi+20h], eax
0x180087369  mov     eax, [rdi+158h]
0x18008736f  mov     [rsi+8], ecx
0x180087372  lea     rcx, [rsi+28h]; void *
0x180087376  mov     [rsi+24h], eax
0x180087379  call    memcpy_0
0x18008737e  mov     eax, [rdi+134h]
0x180087384  cmp     eax, 38h ; '8'
0x180087387  jz      short loc_180087393
0x180087389  cmp     eax, 6Ch ; 'l'
0x18008738c  jz      short loc_180087393
0x18008738e  cmp     eax, 7Ch ; '|'
0x180087391  jnz     short loc_1800873B3
0x180087393  cmp     ebx, 3
0x180087396  jnz     short loc_1800873B3
0x180087398  mov     eax, [rdi+15Ch]
0x18008739e  mov     [rsi+28h], eax
0x1800873a1  mov     eax, [rdi+160h]
0x1800873a7  mov     [rsi+2Ch], eax
0x1800873aa  mov     eax, [rdi+164h]
0x1800873b0  mov     [rsi+30h], eax
0x1800873b3  call    IsSetDIBitsPresent
0x1800873b8  test    al, al
0x1800873ba  jz      loc_1800872C9
0x1800873c0  mov     r9d, [rdi+0B4h]; cLines
0x1800873c7  xor     r8d, r8d; start
0x1800873ca  mov     rdx, [rdi+5B0h]; hbm
0x1800873d1  xor     ecx, ecx; hdc
0x1800873d3  mov     [rsp+0C0h+ColorUse], r13d; ColorUse
0x1800873d8  mov     qword ptr [rsp+0C0h+offset], rsi; lpbmi
0x1800873dd  mov     [rsp+0C0h+hSection], r14; lpBits
0x1800873e2  call    cs:__imp_SetDIBits
0x1800873e9  nop     dword ptr [rax+rax+00h]
0x1800873ee  mov     rcx, rsi; Block
0x1800873f1  mov     ebx, eax
0x1800873f3  call    cs:__imp_free
0x1800873fa  nop     dword ptr [rax+rax+00h]
0x1800873ff  mov     rcx, r14; Block
0x180087402  call    cs:__imp_free
0x180087409  nop     dword ptr [rax+rax+00h]
0x18008740e  cmp     ebx, [rdi+0B4h]
0x180087414  jz      short loc_18008746C
0x180087416  call    IsDeleteObjectPresent
0x18008741b  test    al, al
0x18008741d  jnz     short loc_180087429
0x18008741f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180087424  jmp     loc_1800872C9
0x180087429  mov     rcx, [rdi+5B0h]; ho
0x180087430  call    cs:__imp_DeleteObject
0x180087437  nop     dword ptr [rax+rax+00h]
0x18008743c  mov     [rdi+5B0h], r13
0x180087443  mov     [r15], r13
0x180087446  mov     eax, 88982F60h
0x18008744b  mov     rcx, [rbp+57h+var_48]
0x18008744f  xor     rcx, rsp; StackCookie
0x180087452  call    __security_check_cookie
0x180087457  add     rsp, 88h
0x18008745e  pop     r15
0x180087460  pop     r14
0x180087462  pop     r13
0x180087464  pop     r12
0x180087466  pop     rdi
0x180087467  pop     rsi
0x180087468  pop     rbx
0x180087469  pop     rbp
0x18008746a  retn
0x18008746c  xor     eax, eax
0x18008746e  jmp     short loc_18008744B
```

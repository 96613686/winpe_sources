# CIcmColorTransform24bppBgr::CopyPixels(WICRect const *,uint,uint,uchar *)

- ea: `0x180005540`
- end: `0x180005792`
- name: `?CopyPixels@CIcmColorTransform24bppBgr@@UEAAJPEBUWICRect@@IIPEAE@Z`
- size: `594`
- prototype: `__int64 __fastcall(CIcmColorTransform24bppBgr *__hidden this, const struct WICRect *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005540`
- `0x180005c90`
- `0x180007410`
- `0x1800171c4`
- `0x180021a30`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005761`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005761`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000569d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000569d`

## pseudocode

```c
__int64 __fastcall CIcmColorTransform24bppBgr::CopyPixels(
        CIcmColorTransform24bppBgr *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  int v5; // eax
  int v7; // r10d
  __int64 v11; // r12
  INT X; // ecx
  INT Width; // r9d
  int v14; // edx
  INT v15; // eax
  int v16; // edx
  INT Y; // ecx
  INT Height; // r8d
  INT v19; // eax
  int v20; // r10d
  int v21; // eax
  unsigned int v22; // ebx
  int v23; // r14d
  int v24; // esi
  int v26; // r15d
  int v27; // ebx
  int v28; // ecx
  signed int LastError; // eax
  __int64 v30; // [rsp+20h] [rbp-51h]
  int v31; // [rsp+60h] [rbp-11h]
  unsigned int v32; // [rsp+64h] [rbp-Dh]
  __int64 v33; // [rsp+68h] [rbp-9h]
  __int64 v34; // [rsp+70h] [rbp-1h]
  __int128 v35; // [rsp+78h] [rbp+7h] BYREF

  v5 = *((_DWORD *)this + 12);
  v7 = *((_DWORD *)this + 13);
  *((_QWORD *)&v35 + 1) = __PAIR64__(v7, v5);
  v11 = a3;
  *(_QWORD *)&v35 = 0;
  if ( !a2 )
    goto LABEL_14;
  X = a2->X;
  Width = a2->Width;
  v14 = Width + a2->X;
  if ( v14 >= v5 )
    v14 = v5;
  v15 = 0;
  if ( X > 0 )
    v15 = X;
  v16 = v14 - v15;
  LODWORD(v35) = v15;
  DWORD2(v35) = v16;
  if ( v16 <= 0 )
    goto LABEL_27;
  Y = a2->Y;
  Height = a2->Height;
  if ( Height + Y < v7 )
    v7 = Height + Y;
  v19 = 0;
  if ( Y > 0 )
    v19 = a2->Y;
  v20 = v7 - v19;
  DWORD1(v35) = v19;
  HIDWORD(v35) = v20;
  if ( v20 <= 0 )
  {
LABEL_27:
    v35 = 0;
    goto LABEL_28;
  }
  if ( Width != v16 || Height != v20 )
  {
LABEL_28:
    v22 = -2147024809;
    if ( g_doStackCaptures )
    {
      v28 = -2147024809;
LABEL_31:
      DoStackCapture(v28);
      return v22;
    }
    return v22;
  }
LABEL_14:
  v21 = HrCheckBufferSize(12, (unsigned int)v11, &v35, a4);
  v22 = v21;
  if ( v21 < 0 )
  {
    if ( !g_doStackCaptures )
      return v22;
    goto LABEL_30;
  }
  v23 = HIDWORD(v35);
  v24 = 0;
  HIDWORD(v35) = 1;
  if ( v23 > 0 )
  {
    while ( 1 )
    {
      v21 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 56LL))(
              *((_QWORD *)this + 2),
              &v35,
              *((unsigned int *)this + 8),
              *((unsigned int *)this + 8),
              *((_QWORD *)this + 3));
      v22 = v21;
      if ( v21 < 0 )
        break;
      SetLastError(0);
      v26 = 0;
      v27 = *((_DWORD *)this + 8);
      v33 = *((_QWORD *)this + 3);
      v34 = *((_QWORD *)this + 1);
      v31 = HIDWORD(v35);
      v32 = DWORD2(v35);
      if ( (unsigned int)ICMModule::EnsureLoaded() )
      {
        LODWORD(v30) = v31;
        v26 = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64, int, unsigned __int8 *, int, _DWORD, _QWORD, _DWORD))ICMModule::s_pfnTranslateBitmapBits)(
                v34,
                v33,
                2,
                v32,
                v30,
                v27,
                a5,
                2,
                v11,
                0,
                0);
      }
      v22 = 0;
      if ( !v26 )
      {
        LastError = GetLastError();
        v22 = LastError;
        if ( LastError > 0 )
          v22 = (unsigned __int16)LastError | 0x80070000;
        if ( (v22 & 0x80000000) == 0 )
          v22 = -2003292268;
        if ( g_doStackCaptures )
          DoStackCapture(v22);
      }
      if ( (v22 & 0x80000000) == 0 )
      {
        ++DWORD1(v35);
        a5 += v11;
        if ( ++v24 < v23 )
          continue;
      }
      return v22;
    }
    if ( g_doStackCaptures )
    {
LABEL_30:
      v28 = v21;
      goto LABEL_31;
    }
  }
  return v22;
}

```

## disassembly

```asm
0x180005540  mov     [rsp-8+arg_8], rbx
0x180005545  push    rbp
0x180005546  push    rsi
0x180005547  push    rdi
0x180005548  push    r12
0x18000554a  push    r13
0x18000554c  push    r14
0x18000554e  push    r15
0x180005550  lea     rbp, [rsp-1Fh]
0x180005555  sub     rsp, 90h
0x18000555c  mov     rax, cs:__security_cookie
0x180005563  xor     rax, rsp
0x180005566  mov     [rbp+4Fh+var_38], rax
0x18000556a  mov     eax, [rcx+30h]
0x18000556d  mov     ebx, r9d
0x180005570  mov     r10d, [rcx+34h]
0x180005574  mov     r11, rdx
0x180005577  mov     r13, [rbp+4Fh+arg_20]
0x18000557b  mov     rdi, rcx
0x18000557e  mov     dword ptr [rbp+4Fh+var_48+8], eax
0x180005581  mov     dword ptr [rbp+4Fh+var_48+0Ch], r10d
0x180005585  mov     r12d, r8d
0x180005588  mov     qword ptr [rbp+4Fh+var_48], 0
0x180005590  test    rdx, rdx
0x180005593  jz      short loc_1800055FA
0x180005595  mov     ecx, [rdx]
0x180005597  mov     r9d, [rdx+8]
0x18000559b  lea     edx, [r9+rcx]
0x18000559f  cmp     edx, eax
0x1800055a1  cmovge  edx, eax
0x1800055a4  xor     eax, eax
0x1800055a6  test    ecx, ecx
0x1800055a8  cmovg   eax, ecx
0x1800055ab  sub     edx, eax
0x1800055ad  mov     dword ptr [rbp+4Fh+var_48], eax
0x1800055b0  mov     dword ptr [rbp+4Fh+var_48+8], edx
0x1800055b3  test    edx, edx
0x1800055b5  jle     loc_180005738
0x1800055bb  mov     ecx, [r11+4]
0x1800055bf  mov     r8d, [r11+0Ch]
0x1800055c3  lea     eax, [r8+rcx]
0x1800055c7  cmp     eax, r10d
0x1800055ca  cmovl   r10d, eax
0x1800055ce  xor     eax, eax
0x1800055d0  test    ecx, ecx
0x1800055d2  cmovg   eax, ecx
0x1800055d5  sub     r10d, eax
0x1800055d8  mov     dword ptr [rbp+4Fh+var_48+4], eax
0x1800055db  mov     dword ptr [rbp+4Fh+var_48+0Ch], r10d
0x1800055df  test    r10d, r10d
0x1800055e2  jle     loc_180005738
0x1800055e8  cmp     r9d, edx
0x1800055eb  jnz     loc_18000573F
0x1800055f1  cmp     r8d, r10d
0x1800055f4  jnz     loc_18000573F
0x1800055fa  mov     r9d, ebx
0x1800055fd  lea     r8, [rbp+4Fh+var_48]
0x180005601  mov     edx, r12d
0x180005604  mov     ecx, 0Ch
0x180005609  call    ?HrCheckBufferSize@@YAJW4Enum@MilPixelFormat@@IPEBUWICRect@@I@Z; HrCheckBufferSize(MilPixelFormat::Enum,uint,WICRect const *,uint)
0x18000560e  mov     ebx, eax
0x180005610  test    eax, eax
0x180005612  jns     short loc_180005625
0x180005614  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000561b  jnz     loc_180005755
0x180005621  test    eax, eax
0x180005623  js      short loc_180005672
0x180005625  mov     r14d, dword ptr [rbp+4Fh+var_48+0Ch]
0x180005629  xor     esi, esi
0x18000562b  mov     dword ptr [rbp+4Fh+var_48+0Ch], 1
0x180005632  test    r14d, r14d
0x180005635  jle     short loc_180005672
0x180005637  mov     rdx, [rdi+18h]
0x18000563b  mov     rcx, [rdi+10h]
0x18000563f  mov     r8d, [rdi+20h]
0x180005643  mov     r9d, r8d
0x180005646  mov     [rsp+0C0h+var_A0], rdx
0x18000564b  lea     rdx, [rbp+4Fh+var_48]
0x18000564f  mov     rax, [rcx]
0x180005652  mov     rax, [rax+38h]
0x180005656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000565b  mov     ebx, eax
0x18000565d  test    eax, eax
0x18000565f  jns     short loc_18000569B
0x180005661  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180005668  jnz     loc_180005755
0x18000566e  test    eax, eax
0x180005670  jns     short loc_18000569B
0x180005672  mov     eax, ebx
0x180005674  mov     rcx, [rbp+4Fh+var_38]
0x180005678  xor     rcx, rsp; StackCookie
0x18000567b  call    __security_check_cookie
0x180005680  mov     rbx, [rsp+0C0h+arg_8]
0x180005688  add     rsp, 90h
0x18000568f  pop     r15
0x180005691  pop     r14
0x180005693  pop     r13
0x180005695  pop     r12
0x180005697  pop     rdi
0x180005698  pop     rsi
0x180005699  pop     rbp
0x18000569a  retn
0x18000569b  xor     ecx, ecx; dwErrCode
0x18000569d  call    cs:__imp_SetLastError
0x1800056a3  mov     rax, [rdi+18h]
0x1800056a7  xor     r15d, r15d
0x1800056aa  mov     ebx, [rdi+20h]
0x1800056ad  mov     [rbp+4Fh+var_58], rax
0x1800056b1  mov     rax, [rdi+8]
0x1800056b5  mov     [rbp+4Fh+var_50], rax
0x1800056b9  mov     eax, dword ptr [rbp+4Fh+var_48+0Ch]
0x1800056bc  mov     [rbp+4Fh+var_60], eax
0x1800056bf  mov     eax, dword ptr [rbp+4Fh+var_48+8]
0x1800056c2  mov     [rbp+4Fh+var_5C], eax
0x1800056c5  call    ?EnsureLoaded@ICMModule@@SAHXZ; ICMModule::EnsureLoaded(void)
0x1800056ca  test    eax, eax
0x1800056cc  jz      short loc_180005713
0x1800056ce  mov     eax, [rbp+4Fh+var_60]
0x1800056d1  lea     ecx, [r15+2]
0x1800056d5  mov     r9d, [rbp+4Fh+var_5C]
0x1800056d9  mov     r8d, ecx
0x1800056dc  mov     rdx, [rbp+4Fh+var_58]
0x1800056e0  mov     [rsp+0C0h+var_70], r15d
0x1800056e5  mov     [rsp+0C0h+var_78], r15
0x1800056ea  mov     [rsp+0C0h+var_80], r12d
0x1800056ef  mov     [rsp+0C0h+var_88], ecx
0x1800056f3  mov     rcx, [rbp+4Fh+var_50]
0x1800056f7  mov     [rsp+0C0h+var_90], r13
0x1800056fc  mov     [rsp+0C0h+var_98], ebx
0x180005700  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180005704  mov     rax, cs:?s_pfnTranslateBitmapBits@ICMModule@@0P6AHPEAX0W4BMFORMAT@@KKK01KP6AHKK_J@ZK@ZEA; int (*ICMModule::s_pfnTranslateBitmapBits)(void *,void *,BMFORMAT,ulong,ulong,ulong,void *,BMFORMAT,ulong,int (*)(ulong,ulong,__int64),ulong)
0x18000570b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005710  mov     r15d, eax
0x180005713  xor     ebx, ebx
0x180005715  test    r15d, r15d
0x180005718  jz      short loc_180005761
0x18000571a  test    ebx, ebx
0x18000571c  js      loc_180005672
0x180005722  inc     dword ptr [rbp+4Fh+var_48+4]
0x180005725  add     r13, r12
0x180005728  inc     esi
0x18000572a  cmp     esi, r14d
0x18000572d  jge     loc_180005672
0x180005733  jmp     loc_180005637
0x180005738  xorps   xmm0, xmm0
0x18000573b  movups  [rbp+4Fh+var_48], xmm0
0x18000573f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180005746  mov     ebx, 80070057h
0x18000574b  jz      loc_180005672
0x180005751  mov     ecx, ebx
0x180005753  jmp     short loc_180005757
0x180005755  mov     ecx, eax; int
0x180005757  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000575c  jmp     loc_180005672
0x180005761  call    cs:__imp_GetLastError
0x180005767  mov     ebx, eax
0x180005769  test    eax, eax
0x18000576b  jle     short loc_180005776
0x18000576d  movzx   ebx, ax
0x180005770  or      ebx, 80070000h
0x180005776  test    ebx, ebx
0x180005778  mov     eax, 88982F94h
0x18000577d  cmovns  ebx, eax
0x180005780  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180005787  jz      short loc_18000571A
0x180005789  mov     ecx, ebx; int
0x18000578b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180005790  jmp     short loc_18000571A
```

# SensorProfileFilterSet::CreateSensorProfileFilterSetCollection(ulong,ushort const *,IMFCollection * *)

- ea: `0x18001fd08`
- end: `0x18002021d`
- name: `?CreateSensorProfileFilterSetCollection@SensorProfileFilterSet@@SAJKPEBGPEAPEAUIMFCollection@@@Z`
- size: `1301`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *, struct IMFCollection **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18001f940`
- `0x18005ce7c`

## callees

- `0x180005fa0`
- `0x18000d1f0`
- `0x180015e80`
- `0x18001fd08`
- `0x180020bb4`
- `0x1800217f4`
- `0x180044adc`
- `0x180044b1c`
- `0x180044b28`
- `0x180044f30`
- `0x180076274`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateCollection` at `0x18001fdb9`
- `MFPlat!MFCreateCollection` at `0x18001fdb9`

## pseudocode

```c
__int64 __fastcall SensorProfileFilterSet::CreateSensorProfileFilterSetCollection(
        unsigned int a1,
        unsigned __int16 *a2,
        struct IMFCollection **a3)
{
  unsigned int v5; // ebx
  unsigned int v6; // edi
  int v7; // eax
  __int64 v8; // rdx
  char v9; // r12
  char v10; // r13
  unsigned __int16 *v11; // rcx
  SensorProfileFilterSet *v12; // rax
  SensorProfileFilterSet *v13; // rbx
  int v14; // eax
  unsigned __int64 v15; // rdi
  void *v16; // rax
  SensorProfileFilterSet *v17; // rax
  SensorProfileFilterSet *v18; // rax
  __int64 v19; // rdx
  struct IMFCollection *v21; // [rsp+30h] [rbp-39h] BYREF
  void *Block; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v23; // [rsp+40h] [rbp-29h]
  unsigned __int16 *v24; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v25; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v26[40]; // [rsp+58h] [rbp-11h] BYREF

  v23 = a1;
  v24 = 0;
  v21 = 0;
  Block = 0;
  v5 = a1;
  if ( !a3 )
  {
    v6 = -2147467261;
    if ( g_wppLevels )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_c8770159fdd03d353e3d3063b6f4a6f2_Traceguids,
        0,
        -2147467261);
      goto LABEL_71;
    }
    return v6;
  }
  *a3 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    v6 = -2147024809;
    if ( g_wppLevels )
    {
      v8 = 17;
      goto LABEL_7;
    }
    return v6;
  }
  v7 = MFCreateCollection(&v21);
  v6 = v7;
  if ( v7 < 0 )
  {
    if ( g_wppLevels )
    {
      v8 = 18;
      goto LABEL_7;
    }
    goto LABEL_71;
  }
  v9 = 0;
  v10 = 0;
  v11 = a2;
  while ( 1 )
  {
    if ( !v11 || !*v11 )
    {
      *a3 = v21;
      v21 = 0;
      goto LABEL_71;
    }
    memset(v26, 0, sizeof(v26));
    v7 = ParseFilterSetString(
           v11,
           (const unsigned __int16 **)&v24,
           (struct MFSensorProfileFilterSet *)v26,
           (unsigned __int16 **)&Block);
    v6 = v7;
    if ( v7 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_71;
      v8 = 19;
      goto LABEL_7;
    }
    *(_WORD *)v26 |= (v5 >> 2) & 4;
    v12 = (SensorProfileFilterSet *)operator new(0x48u);
    if ( !v12 )
      break;
    v13 = SensorProfileFilterSet::SensorProfileFilterSet(v12, (const struct MFSensorProfileFilterSet *)v26);
    if ( !v13 )
      break;
    if ( !Block && (*(_WORD *)v26 & 0x8000) != 0 )
    {
      v25 = 0;
      v14 = StringCchLengthW(a2, 0x7FFFFFFFu, &v25);
      v6 = v14;
      if ( v14 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_65;
        v19 = 21;
        goto LABEL_64;
      }
      v15 = v25 + 1;
      v16 = operator new[](saturated_mul(v25 + 1, 2u));
      Block = v16;
      if ( !v16 )
      {
        v14 = -2147024882;
        v6 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_65;
        v19 = 22;
        goto LABEL_64;
      }
      v14 = StringCchCopyW((unsigned __int16 *)v16, v15, a2);
      v6 = v14;
      if ( v14 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_65;
        v19 = 23;
LABEL_64:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_c8770159fdd03d353e3d3063b6f4a6f2_Traceguids, 0, v14);
        goto LABEL_65;
      }
    }
    v14 = (*(__int64 (__fastcall **)(SensorProfileFilterSet *))(*(_QWORD *)v13 + 120LL))(v13);
    v6 = v14;
    if ( v14 < 0 )
    {
      if ( g_wppLevels )
      {
        v19 = 24;
        goto LABEL_64;
      }
      goto LABEL_65;
    }
    Block = 0;
    if ( (v26[0] & 1) != 0 )
    {
      if ( v10 )
      {
        v14 = -2147024809;
        v6 = -2147024809;
        if ( !g_wppLevels )
          goto LABEL_65;
        v19 = 25;
        goto LABEL_64;
      }
      v14 = ((__int64 (__fastcall *)(struct IMFCollection *, _QWORD, SensorProfileFilterSet *))v21->lpVtbl->InsertElementAt)(
              v21,
              0,
              v13);
      v6 = v14;
      if ( v14 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_65;
        v19 = 26;
        goto LABEL_64;
      }
      v9 = 1;
    }
    else if ( (v26[0] & 8) != 0 )
    {
      if ( v9 )
      {
        v14 = -2147024809;
        v6 = -2147024809;
        if ( !g_wppLevels )
          goto LABEL_65;
        v19 = 27;
        goto LABEL_64;
      }
      v14 = ((__int64 (__fastcall *)(struct IMFCollection *, _QWORD, SensorProfileFilterSet *))v21->lpVtbl->InsertElementAt)(
              v21,
              0,
              v13);
      v6 = v14;
      if ( v14 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_65;
        v19 = 28;
        goto LABEL_64;
      }
      v10 = 1;
    }
    else
    {
      v14 = ((__int64 (__fastcall *)(struct IMFCollection *, SensorProfileFilterSet *))v21->lpVtbl->AddElement)(
              v21,
              v13);
      v6 = v14;
      if ( v14 < 0 )
      {
        if ( g_wppLevels )
        {
          v19 = 29;
          goto LABEL_64;
        }
        goto LABEL_65;
      }
    }
    if ( (v26[0] & 9) == 0 && *(_WORD *)&v26[6] != 5 && !memcmp_0(&v26[24], &MFVideoFormat_MJPG, 0x10u) )
    {
      (*(void (__fastcall **)(SensorProfileFilterSet *))(*(_QWORD *)v13 + 16LL))(v13);
      *(GUID *)&v26[24] = MFVideoFormat_NV12;
      v17 = (SensorProfileFilterSet *)operator new(0x48u);
      if ( v17 )
      {
        v18 = SensorProfileFilterSet::SensorProfileFilterSet(v17, (const struct MFSensorProfileFilterSet *)v26);
        v13 = v18;
        if ( v18 )
        {
          v14 = (*(__int64 (__fastcall **)(SensorProfileFilterSet *))(*(_QWORD *)v18 + 128LL))(v18);
          v6 = v14;
          if ( v14 < 0 )
          {
            if ( g_wppLevels )
            {
              v19 = 31;
              goto LABEL_64;
            }
          }
          else
          {
            v14 = ((__int64 (__fastcall *)(struct IMFCollection *, SensorProfileFilterSet *))v21->lpVtbl->AddElement)(
                    v21,
                    v13);
            v6 = v14;
            if ( v14 >= 0 )
              goto LABEL_39;
            if ( g_wppLevels )
            {
              v19 = 32;
              goto LABEL_64;
            }
          }
LABEL_65:
          (*(void (__fastcall **)(SensorProfileFilterSet *))(*(_QWORD *)v13 + 16LL))(v13);
          goto LABEL_71;
        }
      }
      v7 = -2147024882;
      v6 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_71;
      v8 = 30;
LABEL_7:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_c8770159fdd03d353e3d3063b6f4a6f2_Traceguids, 0, v7);
      goto LABEL_71;
    }
LABEL_39:
    (*(void (__fastcall **)(SensorProfileFilterSet *))(*(_QWORD *)v13 + 16LL))(v13);
    v11 = v24;
    v5 = v23;
    v24 = 0;
  }
  v7 = -2147024882;
  v6 = -2147024882;
  if ( g_wppLevels )
  {
    v8 = 20;
    goto LABEL_7;
  }
LABEL_71:
  if ( Block )
  {
    operator delete(Block);
    Block = 0;
  }
  if ( v21 )
    ((void (__fastcall *)(struct IMFCollection *))v21->lpVtbl->Release)(v21);
  return v6;
}

```

## disassembly

```asm
0x18001fd08  mov     [rsp-8+arg_0], rbx
0x18001fd0d  push    rbp
0x18001fd0e  push    rsi
0x18001fd0f  push    rdi
0x18001fd10  push    r12
0x18001fd12  push    r13
0x18001fd14  push    r14
0x18001fd16  push    r15
0x18001fd18  lea     rbp, [rsp-27h]
0x18001fd1d  sub     rsp, 90h
0x18001fd24  mov     rax, cs:__security_cookie
0x18001fd2b  xor     rax, rsp
0x18001fd2e  mov     [rbp+57h+var_40], rax
0x18001fd32  xor     esi, esi
0x18001fd34  mov     [rbp+57h+var_80], ecx
0x18001fd37  mov     [rbp+57h+var_78], rsi
0x18001fd3b  mov     r15, r8
0x18001fd3e  mov     [rbp+57h+var_90], rsi
0x18001fd42  mov     r14, rdx
0x18001fd45  mov     [rbp+57h+Block], rsi
0x18001fd49  mov     ebx, ecx
0x18001fd4b  test    r8, r8
0x18001fd4e  jnz     short loc_18001FD8C
0x18001fd50  mov     edi, 80004003h
0x18001fd55  mov     sil, 1
0x18001fd58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18001fd5f  jb      loc_1800201F4
0x18001fd65  lea     edx, [r8+10h]
0x18001fd69  mov     [rsp+0C0h+var_A0], edi
0x18001fd6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd74  lea     r8, WPP_c8770159fdd03d353e3d3063b6f4a6f2_Traceguids
0x18001fd7b  xor     r9d, r9d
0x18001fd7e  mov     rcx, [rcx+10h]
0x18001fd82  call    WPP_SF_qD
0x18001fd87  jmp     loc_1800201CA
0x18001fd8c  mov     [r8], rsi
0x18001fd8f  test    r14, r14
0x18001fd92  jnz     short loc_18001FDB5
0x18001fd94  mov     eax, 80070057h
0x18001fd99  mov     edi, eax
0x18001fd9b  mov     sil, 1
0x18001fd9e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18001fda5  jb      loc_1800201F4
0x18001fdab  lea     edx, [r14+11h]
0x18001fdaf  mov     [rsp+0C0h+var_A0], eax
0x18001fdb3  jmp     short loc_18001FD6D
0x18001fdb5  lea     rcx, [rbp+57h+var_90]
0x18001fdb9  call    cs:__imp_MFCreateCollection
0x18001fdbf  mov     edi, eax
0x18001fdc1  test    eax, eax
0x18001fdc3  jns     short loc_18001FDDC
0x18001fdc5  mov     sil, 1
0x18001fdc8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18001fdcf  jb      loc_1800201CA
0x18001fdd5  mov     edx, 12h
0x18001fdda  jmp     short loc_18001FDAF
0x18001fddc  mov     r12b, sil
0x18001fddf  mov     r13b, sil
0x18001fde2  mov     sil, 1
0x18001fde5  mov     rcx, r14; unsigned __int16 *
0x18001fde8  xor     edx, edx
0x18001fdea  test    rcx, rcx
0x18001fded  jz      loc_1800201BF
0x18001fdf3  cmp     [rcx], dx
0x18001fdf6  jz      loc_1800201BF
0x18001fdfc  xorps   xmm0, xmm0
0x18001fdff  lea     r9, [rbp+57h+Block]; unsigned __int16 **
0x18001fe03  xor     eax, eax
0x18001fe05  lea     r8, [rbp+57h+var_68]; struct MFSensorProfileFilterSet *
0x18001fe09  lea     rdx, [rbp+57h+var_78]; unsigned __int16 **
0x18001fe0d  mov     [rbp+57h+var_48], rax
0x18001fe11  movups  [rbp+57h+var_68], xmm0
0x18001fe15  movups  [rbp+57h+Buf1], xmm0
0x18001fe19  call    ?ParseFilterSetString@@YAJPEBGPEAPEBGPEAUMFSensorProfileFilterSet@@PEAPEAG@Z; ParseFilterSetString(ushort const *,ushort const * *,MFSensorProfileFilterSet *,ushort * *)
0x18001fe1e  mov     edi, eax
0x18001fe20  test    eax, eax
0x18001fe22  js      loc_1800201AC
0x18001fe28  mov     eax, ebx
0x18001fe2a  mov     ecx, 48h ; 'H'; Size
0x18001fe2f  shr     eax, 2
0x18001fe32  and     ax, 4
0x18001fe36  or      word ptr [rbp+57h+var_68], ax
0x18001fe3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fe3f  xor     edi, edi
0x18001fe41  test    rax, rax
0x18001fe44  jz      loc_180020192
0x18001fe4a  lea     rdx, [rbp+57h+var_68]; struct MFSensorProfileFilterSet *
0x18001fe4e  mov     rcx, rax; this
0x18001fe51  call    ??0SensorProfileFilterSet@@IEAA@AEBUMFSensorProfileFilterSet@@@Z; SensorProfileFilterSet::SensorProfileFilterSet(MFSensorProfileFilterSet const &)
0x18001fe56  mov     rbx, rax
0x18001fe59  test    rax, rax
0x18001fe5c  jz      loc_180020192
0x18001fe62  mov     rdx, [rbp+57h+Block]
0x18001fe66  test    rdx, rdx
0x18001fe69  jnz     short loc_18001FEE6
0x18001fe6b  movzx   ecx, word ptr [rbp+57h+var_68]
0x18001fe6f  mov     eax, 8000h
0x18001fe74  and     cx, ax
0x18001fe77  cmp     di, cx
0x18001fe7a  jz      short loc_18001FEE6
0x18001fe7c  lea     r8, [rbp+57h+var_70]; unsigned __int64 *
0x18001fe80  mov     [rbp+57h+var_70], rdi
0x18001fe84  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001fe89  mov     rcx, r14; unsigned __int16 *
0x18001fe8c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001fe91  mov     edi, eax
0x18001fe93  test    eax, eax
0x18001fe95  js      loc_18002008C
0x18001fe9b  mov     rdi, [rbp+57h+var_70]
0x18001fe9f  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001fea6  inc     rdi
0x18001fea9  mov     eax, 2
0x18001feae  mul     rdi
0x18001feb1  cmovb   rax, rcx
0x18001feb5  mov     rcx, rax; unsigned __int64
0x18001feb8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001febd  mov     [rbp+57h+Block], rax
0x18001fec1  test    rax, rax
0x18001fec4  jz      loc_18002006E
0x18001feca  mov     r8, r14; unsigned __int16 *
0x18001fecd  mov     rdx, rdi; unsigned __int64
0x18001fed0  mov     rcx, rax; unsigned __int16 *
0x18001fed3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001fed8  mov     edi, eax
0x18001feda  test    eax, eax
0x18001fedc  js      loc_180020057
0x18001fee2  mov     rdx, [rbp+57h+Block]
0x18001fee6  mov     rax, [rbx]
0x18001fee9  mov     rcx, rbx
0x18001feec  mov     rax, [rax+78h]
0x18001fef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fef5  xor     ecx, ecx
0x18001fef7  mov     edi, eax
0x18001fef9  test    eax, eax
0x18001fefb  js      loc_180020155
0x18001ff01  mov     al, byte ptr [rbp+57h+var_68]
0x18001ff04  mov     [rbp+57h+Block], rcx
0x18001ff08  test    sil, al
0x18001ff0b  jz      short loc_18001FF3A
0x18001ff0d  test    r13b, r13b
0x18001ff10  jnz     loc_1800200BA
0x18001ff16  mov     rcx, [rbp+57h+var_90]
0x18001ff1a  mov     r8, rbx
0x18001ff1d  xor     edx, edx
0x18001ff1f  mov     rax, [rcx]
0x18001ff22  mov     rax, [rax+38h]
0x18001ff26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff2b  mov     edi, eax
0x18001ff2d  test    eax, eax
0x18001ff2f  js      loc_1800200A3
0x18001ff35  mov     r12b, sil
0x18001ff38  jmp     short loc_18001FF88
0x18001ff3a  test    al, 8
0x18001ff3c  jz      short loc_18001FF6B
0x18001ff3e  test    r12b, r12b
0x18001ff41  jnz     loc_1800200EC
0x18001ff47  mov     rcx, [rbp+57h+var_90]
0x18001ff4b  mov     r8, rbx
0x18001ff4e  xor     edx, edx
0x18001ff50  mov     rax, [rcx]
0x18001ff53  mov     rax, [rax+38h]
0x18001ff57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff5c  mov     edi, eax
0x18001ff5e  test    eax, eax
0x18001ff60  js      loc_1800200D8
0x18001ff66  mov     r13b, sil
0x18001ff69  jmp     short loc_18001FF88
0x18001ff6b  mov     rcx, [rbp+57h+var_90]
0x18001ff6f  mov     rdx, rbx
0x18001ff72  mov     rax, [rcx]
0x18001ff75  mov     rax, [rax+28h]
0x18001ff79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff7e  mov     edi, eax
0x18001ff80  test    eax, eax
0x18001ff82  js      loc_180020145
0x18001ff88  test    byte ptr [rbp+57h+var_68], 9
0x18001ff8c  jnz     loc_180020036
0x18001ff92  cmp     word ptr [rbp+57h+var_68+6], 5
0x18001ff97  jz      loc_180020036
0x18001ff9d  mov     r8d, 10h; Size
0x18001ffa3  lea     rdx, MFVideoFormat_MJPG; Buf2
0x18001ffaa  lea     rcx, [rbp+57h+Buf1+8]; Buf1
0x18001ffae  call    memcmp_0
0x18001ffb3  test    eax, eax
0x18001ffb5  jnz     short loc_180020036
0x18001ffb7  mov     rax, [rbx]
0x18001ffba  mov     rcx, rbx
0x18001ffbd  mov     rax, [rax+10h]
0x18001ffc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffc6  movups  xmm0, xmmword ptr cs:MFVideoFormat_NV12.Data1
0x18001ffcd  mov     ecx, 48h ; 'H'; Size
0x18001ffd2  movdqu  [rbp+57h+Buf1+8], xmm0
0x18001ffd7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ffdc  test    rax, rax
0x18001ffdf  jz      loc_180020127
0x18001ffe5  lea     rdx, [rbp+57h+var_68]; struct MFSensorProfileFilterSet *
0x18001ffe9  mov     rcx, rax; this
0x18001ffec  call    ??0SensorProfileFilterSet@@IEAA@AEBUMFSensorProfileFilterSet@@@Z; SensorProfileFilterSet::SensorProfileFilterSet(MFSensorProfileFilterSet const &)
0x18001fff1  mov     rbx, rax
0x18001fff4  test    rax, rax
0x18001fff7  jz      loc_180020127
0x18001fffd  mov     rax, [rax]
0x180020000  mov     rcx, rbx
0x180020003  mov     rax, [rax+80h]
0x18002000a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002000f  mov     edi, eax
0x180020011  test    eax, eax
0x180020013  js      loc_180020117
0x180020019  mov     rcx, [rbp+57h+var_90]
0x18002001d  mov     rdx, rbx
0x180020020  mov     rax, [rcx]
0x180020023  mov     rax, [rax+28h]
0x180020027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002002c  mov     edi, eax
0x18002002e  test    eax, eax
0x180020030  js      loc_180020107
0x180020036  mov     rax, [rbx]
0x180020039  mov     rcx, rbx
0x18002003c  mov     rax, [rax+10h]
0x180020040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020045  mov     rcx, [rbp+57h+var_78]
0x180020049  xor     edx, edx
0x18002004b  mov     ebx, [rbp+57h+var_80]
0x18002004e  mov     [rbp+57h+var_78], rdx
0x180020052  jmp     loc_18001FDEA
0x180020057  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18002005e  jb      loc_180020181
0x180020064  mov     edx, 17h
0x180020069  jmp     loc_180020163
0x18002006e  mov     eax, 8007000Eh
0x180020073  mov     edi, eax
0x180020075  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18002007c  jb      loc_180020181
0x180020082  mov     edx, 16h
0x180020087  jmp     loc_180020163
0x18002008c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180020093  jb      loc_180020181
0x180020099  mov     edx, 15h
0x18002009e  jmp     loc_180020163
0x1800200a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800200aa  jb      loc_180020181
0x1800200b0  mov     edx, 1Ah
0x1800200b5  jmp     loc_180020163
0x1800200ba  mov     eax, 80070057h
0x1800200bf  mov     edi, eax
0x1800200c1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800200c8  jb      loc_180020181
0x1800200ce  mov     edx, 19h
0x1800200d3  jmp     loc_180020163
0x1800200d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800200df  jb      loc_180020181
0x1800200e5  mov     edx, 1Ch
0x1800200ea  jmp     short loc_180020163
0x1800200ec  mov     eax, 80070057h
0x1800200f1  mov     edi, eax
0x1800200f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800200fa  jb      loc_180020181
0x180020100  mov     edx, 1Bh
0x180020105  jmp     short loc_180020163
0x180020107  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18002010e  jb      short loc_180020181
0x180020110  mov     edx, 20h ; ' '
0x180020115  jmp     short loc_180020163
0x180020117  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18002011e  jb      short loc_180020181
0x180020120  mov     edx, 1Fh
0x180020125  jmp     short loc_180020163
0x180020127  mov     eax, 8007000Eh
0x18002012c  mov     edi, eax
0x18002012e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180020135  jb      loc_1800201CA
0x18002013b  mov     edx, 1Eh
0x180020140  jmp     loc_18001FDAF
0x180020145  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18002014c  jb      short loc_180020181
0x18002014e  mov     edx, 1Dh
0x180020153  jmp     short loc_180020163
0x180020155  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18002015c  jb      short loc_180020181
0x18002015e  mov     edx, 18h
0x180020163  mov     rcx, cs:WPP_GLOBAL_Control
0x18002016a  lea     r8, WPP_c8770159fdd03d353e3d3063b6f4a6f2_Traceguids
0x180020171  xor     r9d, r9d
0x180020174  mov     [rsp+0C0h+var_A0], eax
0x180020178  mov     rcx, [rcx+10h]
0x18002017c  call    WPP_SF_qD
0x180020181  mov     rax, [rbx]
0x180020184  mov     rcx, rbx
0x180020187  mov     rax, [rax+10h]
0x18002018b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020190  jmp     short loc_1800201CA
0x180020192  mov     eax, 8007000Eh
0x180020197  mov     edi, eax
0x180020199  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800201a0  jb      short loc_1800201CA
0x1800201a2  mov     edx, 14h
0x1800201a7  jmp     loc_18001FDAF
0x1800201ac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800201b3  jb      short loc_1800201CA
0x1800201b5  mov     edx, 13h
  ... truncated ...
```

# sub_14003FBEC

- ea: `0x14003fbec`
- end: `0x14003ff6e`
- name: `sub_14003FBEC`
- size: `898`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update`

## callers

- `0x14003ff70`

## callees

- `0x14001bf00`
- `0x14001bf20`
- `0x14001bf28`
- `0x14001c0a4`
- `0x14001e2d0`
- `0x14001ee6c`
- `0x14003a808`
- `0x14003cc5c`
- `0x14003fa64`
- `0x14003fbec`
- `0x140040378`
- `0x140040a2c`
- `0x1400460a0`
- `0x1400462c8`
- `0x1400463e4`
- `0x140046474`
- `0x1400464a0`
- `0x1400a1f64`
- `0x1400a2114`
- `0x1400a2928`
- `0x1400a6b18`
- `0x1400a6bb4`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14003fea6`
- `KERNEL32!EnterCriticalSection` at `0x14003fea6`
- `KERNEL32!LeaveCriticalSection` at `0x14003feea`
- `KERNEL32!LeaveCriticalSection` at `0x14003feea`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14003fe85`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x14003fe85`
- `RPCRT4!UuidCreate` at `0x14003fc6f`
- `RPCRT4!UuidCreate` at `0x14003fc6f`

## string_xrefs

- `0x14003fc36`: `UpdateTelemetryCV`
- `0x14003ff4d`: `UpdateTelemetryCV`

## pseudocode

```c
__int64 __fastcall sub_14003FBEC(__int64 a1, __int64 a2)
{
  _BYTE *v4; // rbx
  bool v5; // al
  void *v6; // rcx
  unsigned __int64 v7; // rdx
  unsigned __int64 i; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // rbx
  void *v11; // rcx
  void *v12; // rdi
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  void *Block; // [rsp+48h] [rbp-C0h] BYREF
  void *Block_8[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v28; // [rsp+60h] [rbp-A8h]
  __int128 v29; // [rsp+70h] [rbp-98h]
  __int64 v30; // [rsp+80h] [rbp-88h]
  __int64 v31; // [rsp+88h] [rbp-80h]
  _BYTE pExceptionObject[24]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v33[32]; // [rsp+A8h] [rbp-60h] BYREF
  UUID Uuid; // [rsp+C8h] [rbp-40h] BYREF
  char Source[416]; // [rsp+D8h] [rbp-30h] BYREF

  *(_QWORD *)&Uuid.Data1 = 129;
  if ( (int)sub_1400A1F64(L"UpdateTelemetryCV") >= 0 )
  {
    v7 = *(_QWORD *)&Uuid.Data1;
    if ( (unsigned __int64)(*(_QWORD *)&Uuid.Data1 - 1LL) > 0x80 )
    {
      sub_14003CC5C(v33, "UpdateTelemetryCV");
      throw (std::invalid_argument *)v33;
    }
    for ( i = 0; i < v7; ++i )
      Source[i] = Source[2 * i + 144];
    v9 = v7 - 1;
    if ( v9 >= 0x81 )
      _report_rangecheckfailure(i);
    Source[v9] = 0;
    v4 = (_BYTE *)sub_140040A2C(Source);
    if ( !v4 )
    {
      sub_14003CC5C(pExceptionObject, Source);
      throw (std::invalid_argument *)pExceptionObject;
    }
  }
  else
  {
    v4 = operator new(0x90u);
    Uuid = 0;
    v4[130] = 65;
    UuidCreate(&Uuid);
    v4[129] = 17;
    *((_QWORD *)v4 + 17) = 0x1300000000LL;
    memset(v4, 0, 0x81u);
    sub_14003FA64(&Uuid, 12, v4);
    *((_WORD *)v4 + 8) = 46;
  }
  *(_QWORD *)a1 = v4;
  *(_DWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 8) = byte_1400BC14D;
  *(_QWORD *)(a1 + 16) = a2;
  v5 = sub_1400463E4();
  *(_DWORD *)(a1 + 32) = 0;
  *(_BYTE *)(a1 + 28) = v5;
  *(_QWORD *)&Uuid.Data1 = 0;
  *(_OWORD *)(a1 + 36) = 0;
  *(_QWORD *)(a1 + 52) = 0;
  if ( (int)sub_1400A2114(&Uuid) < 0 )
    goto LABEL_22;
  Block = 0;
  if ( (int)sub_1400A2928((__int64)&Block, *(__int64 *)&Uuid.Data1) < 0 )
  {
    v6 = Block;
    if ( Block )
      goto LABEL_21;
    goto LABEL_22;
  }
  v10 = Block;
  *(_QWORD *)&Uuid.Data1 = 0;
  if ( (int)sub_1400A6BB4(1, &Uuid, Block) >= 0 )
  {
    v12 = *(void **)&Uuid.Data1;
    LODWORD(v30) = 0;
    *(_OWORD *)Block_8 = 0;
    v28 = 0;
    v29 = 0;
    sub_1400A6B18(Block_8, *(_QWORD *)&Uuid.Data1);
    if ( !v12 )
      goto LABEL_19;
    v11 = v12;
  }
  else
  {
    v11 = *(void **)&Uuid.Data1;
    if ( !*(_QWORD *)&Uuid.Data1 )
      goto LABEL_19;
  }
  j_j_free(v11);
LABEL_19:
  if ( v10 )
  {
    v6 = v10;
LABEL_21:
    j_j_free(v6);
  }
LABEL_22:
  sub_14003A808((char *)(a1 + 36));
  v13 = lpCriticalSection;
  v30 = 0;
  v31 = 0;
  *(_OWORD *)Block_8 = 0;
  v28 = 0;
  v29 = 0;
  if ( lpCriticalSection
    || (InitializeCriticalSectionAndSpinCount(&stru_1400D7F60, 0xFA0u),
        lpCriticalSection = &stru_1400D7F60,
        sub_1400464A0(v15, v14, v16),
        (v13 = lpCriticalSection) != 0) )
  {
    EnterCriticalSection(v13);
    if ( qword_1400D7F00 )
    {
      sub_1400462C8(qword_1400D7F00, v17, v18);
      qword_1400D7F00 = 0;
      sub_140046474(v20, v19, v21);
      sub_1400464A0(v23, v22, v24);
    }
    qword_1400D7F00 = (__int64)sub_1400460A0(qword_1400D7F90, (__int64 *)Block_8);
    LeaveCriticalSection(v13);
  }
  sub_140040378(Block_8);
  return a1;
}

```

## disassembly

```asm
0x14003fbec  mov     rax, rsp
0x14003fbef  mov     [rax+10h], rbx
0x14003fbf3  mov     [rax+18h], rsi
0x14003fbf7  mov     [rax+20h], rdi
0x14003fbfb  push    rbp
0x14003fbfc  push    r14
0x14003fbfe  push    r15
0x14003fc00  lea     rbp, [rax-198h]
0x14003fc07  sub     rsp, 280h
0x14003fc0e  mov     rax, cs:__security_cookie
0x14003fc15  xor     rax, rsp
0x14003fc18  mov     [rbp+190h+var_20], rax
0x14003fc1f  mov     qword ptr [rbp+190h+Uuid.Data1], rcx
0x14003fc23  lea     r8, [rbp+190h+var_130]
0x14003fc27  mov     rdi, rdx
0x14003fc2a  mov     r14, rcx
0x14003fc2d  mov     esi, 81h
0x14003fc32  lea     rdx, [rbp+190h+Uuid]
0x14003fc36  lea     rcx, aUpdatetelemetr; "UpdateTelemetryCV"
0x14003fc3d  mov     qword ptr [rbp+190h+Uuid.Data1], rsi
0x14003fc41  call    sub_1400A1F64
0x14003fc46  test    eax, eax
0x14003fc48  jns     loc_14003FD2C
0x14003fc4e  lea     ecx, [rsi+0Fh]; Size
0x14003fc51  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003fc56  mov     qword ptr [rbp+190h+Uuid.Data1], rax
0x14003fc5a  lea     rcx, [rbp+190h+Uuid]; Uuid
0x14003fc5e  xorps   xmm0, xmm0
0x14003fc61  mov     rbx, rax
0x14003fc64  movups  xmmword ptr [rbp+190h+Uuid.Data1], xmm0
0x14003fc68  mov     byte ptr [rax+82h], 41h ; 'A'
0x14003fc6f  call    cs:UuidCreate
0x14003fc75  movaps  xmm0, xmmword ptr [rbp+190h+Uuid.Data1]
0x14003fc79  mov     rax, 1300000000h
0x14003fc83  movdqa  xmmword ptr [rbp+190h+Uuid.Data1], xmm0
0x14003fc88  mov     r8d, esi; Size
0x14003fc8b  mov     byte ptr [rbx+81h], 11h
0x14003fc92  xor     edx, edx; Val
0x14003fc94  mov     rcx, rbx; Dst
0x14003fc97  mov     [rbx+88h], rax
0x14003fc9e  call    memset
0x14003fca3  mov     r8, rbx
0x14003fca6  lea     edx, [rsi-75h]
0x14003fca9  lea     rcx, [rbp+190h+Uuid]
0x14003fcad  call    sub_14003FA64
0x14003fcb2  mov     word ptr [rbx+10h], 2Eh ; '.'
0x14003fcb8  mov     [r14], rbx
0x14003fcbb  lea     rax, byte_1400BC14D
0x14003fcc2  and     dword ptr [r14+18h], 0
0x14003fcc7  mov     [r14+8], rax
0x14003fccb  mov     [r14+10h], rdi
0x14003fccf  call    sub_1400463E4
0x14003fcd4  and     dword ptr [r14+20h], 0
0x14003fcd9  lea     rcx, [rbp+190h+Uuid]
0x14003fcdd  mov     [r14+1Ch], al
0x14003fce1  xorps   xmm0, xmm0
0x14003fce4  xor     eax, eax
0x14003fce6  xor     esi, esi
0x14003fce8  and     qword ptr [rbp+190h+Uuid.Data1], rax
0x14003fcec  movups  xmmword ptr [r14+24h], xmm0
0x14003fcf1  mov     [r14+34h], rax
0x14003fcf5  call    sub_1400A2114
0x14003fcfa  test    eax, eax
0x14003fcfc  js      loc_14003FE01
0x14003fd02  mov     rdx, qword ptr [rbp+190h+Uuid.Data1]
0x14003fd06  lea     rcx, [rsp+290h+Block]
0x14003fd0b  and     [rsp+290h+Block], rsi
0x14003fd10  call    sub_1400A2928
0x14003fd15  test    eax, eax
0x14003fd17  jns     short loc_14003FD82
0x14003fd19  mov     rcx, [rsp+290h+Block]
0x14003fd1e  test    rcx, rcx
0x14003fd21  jz      loc_14003FE01
0x14003fd27  jmp     loc_14003FDFC
0x14003fd2c  mov     rdx, qword ptr [rbp+190h+Uuid.Data1]
0x14003fd30  lea     rax, [rdx-1]
0x14003fd34  cmp     rax, 80h
0x14003fd3a  ja      loc_14003FF4D
0x14003fd40  xor     ecx, ecx
0x14003fd42  test    rdx, rdx
0x14003fd45  jz      short loc_14003FD57
0x14003fd47  mov     al, [rbp+rcx*2+190h+var_130]
0x14003fd4b  mov     [rbp+rcx+190h+Source], al
0x14003fd4f  inc     rcx
0x14003fd52  cmp     rcx, rdx
0x14003fd55  jb      short loc_14003FD47
0x14003fd57  dec     rdx
0x14003fd5a  cmp     rdx, rsi
0x14003fd5d  jnb     loc_14003FF29
0x14003fd63  lea     rcx, [rbp+190h+Source]; Source
0x14003fd67  mov     [rbp+rdx+190h+Source], 0
0x14003fd6c  call    sub_140040A2C
0x14003fd71  mov     rbx, rax
0x14003fd74  test    rax, rax
0x14003fd77  jz      loc_14003FF2F
0x14003fd7d  jmp     loc_14003FCB8
0x14003fd82  mov     rbx, [rsp+290h+Block]
0x14003fd87  lea     rdx, [rbp+190h+Uuid]
0x14003fd8b  and     qword ptr [rbp+190h+Uuid.Data1], rsi
0x14003fd8f  mov     r8, rbx
0x14003fd92  mov     ecx, 1
0x14003fd97  call    sub_1400A6BB4
0x14003fd9c  test    eax, eax
0x14003fd9e  jns     short loc_14003FDAB
0x14003fda0  mov     rcx, qword ptr [rbp+190h+Uuid.Data1]
0x14003fda4  test    rcx, rcx
0x14003fda7  jz      short loc_14003FDF4
0x14003fda9  jmp     short loc_14003FDEF
0x14003fdab  mov     rdi, qword ptr [rbp+190h+Uuid.Data1]
0x14003fdaf  lea     rcx, [rsp+290h+Block+8]
0x14003fdb4  xorps   xmm0, xmm0
0x14003fdb7  xor     eax, eax
0x14003fdb9  mov     rdx, rdi
0x14003fdbc  mov     dword ptr [rsp+290h+var_218], eax
0x14003fdc0  movups  xmmword ptr [rsp+290h+Block+8], xmm0
0x14003fdc5  movups  [rsp+290h+var_240+8], xmm0
0x14003fdca  movups  xmmword ptr [rsp+290h+var_230+8], xmm0
0x14003fdcf  call    sub_1400A6B18
0x14003fdd4  test    eax, eax
0x14003fdd6  js      short loc_14003FDE7
0x14003fdd8  mov     esi, dword ptr [rsp+290h+var_240]
0x14003fddc  mov     eax, dword ptr [rsp+290h+var_240+4]
0x14003fde0  shl     rsi, 20h
0x14003fde4  add     rsi, rax
0x14003fde7  test    rdi, rdi
0x14003fdea  jz      short loc_14003FDF4
0x14003fdec  mov     rcx, rdi; Block
0x14003fdef  call    j_j_free
0x14003fdf4  test    rbx, rbx
0x14003fdf7  jz      short loc_14003FE01
0x14003fdf9  mov     rcx, rbx; Block
0x14003fdfc  call    j_j_free
0x14003fe01  movzx   r10d, si
0x14003fe05  lea     rcx, [r14+24h]; Buffer
0x14003fe09  mov     [rsp+290h+var_260], r10d
0x14003fe0e  mov     rax, rsi
0x14003fe11  shr     rax, 10h
0x14003fe15  movzx   r8d, ax
0x14003fe19  mov     rax, rsi
0x14003fe1c  mov     [rsp+290h+var_268], r8d
0x14003fe21  lea     r8, aUUUU; "%u.%u.%u.%u"
0x14003fe28  shr     rax, 20h
0x14003fe2c  movzx   edx, ax
0x14003fe2f  mov     [rsp+290h+var_270], edx
0x14003fe33  mov     edx, 18h
0x14003fe38  shr     rsi, 30h
0x14003fe3c  mov     r9d, esi
0x14003fe3f  call    sub_14003A808
0x14003fe44  mov     rbx, cs:lpCriticalSection
0x14003fe4b  xor     eax, eax
0x14003fe4d  and     [rsp+290h+var_218], rax
0x14003fe52  xorps   xmm0, xmm0
0x14003fe55  mov     [rbp+190h+var_210], rax
0x14003fe59  xorps   xmm1, xmm1
0x14003fe5c  mov     dword ptr [rbp+190h+var_210+4], eax
0x14003fe5f  movdqu  xmmword ptr [rsp+290h+Block+8], xmm0
0x14003fe65  movdqu  [rsp+290h+var_240+8], xmm1
0x14003fe6b  movdqu  xmmword ptr [rsp+290h+var_230+8], xmm0
0x14003fe71  test    rbx, rbx
0x14003fe74  jnz     short loc_14003FEA3
0x14003fe76  lea     rbx, stru_1400D7F60
0x14003fe7d  mov     edx, 0FA0h; dwSpinCount
0x14003fe82  mov     rcx, rbx; lpCriticalSection
0x14003fe85  call    cs:InitializeCriticalSectionAndSpinCount
0x14003fe8b  mov     cs:lpCriticalSection, rbx
0x14003fe92  call    sub_1400464A0
0x14003fe97  mov     rbx, cs:lpCriticalSection
0x14003fe9e  test    rbx, rbx
0x14003fea1  jz      short loc_14003FEF0
0x14003fea3  mov     rcx, rbx; lpCriticalSection
0x14003fea6  call    cs:EnterCriticalSection
0x14003feac  mov     rcx, cs:qword_1400D7F00
0x14003feb3  test    rcx, rcx
0x14003feb6  jz      short loc_14003FECF
0x14003feb8  call    sub_1400462C8
0x14003febd  and     cs:qword_1400D7F00, 0
0x14003fec5  call    sub_140046474
0x14003feca  call    sub_1400464A0
0x14003fecf  lea     rdx, [rsp+290h+Block+8]
0x14003fed4  lea     rcx, qword_1400D7F90
0x14003fedb  call    sub_1400460A0
0x14003fee0  mov     rcx, rbx; lpCriticalSection
0x14003fee3  mov     cs:qword_1400D7F00, rax
0x14003feea  call    cs:LeaveCriticalSection
0x14003fef0  lea     rcx, [rsp+290h+Block+8]
0x14003fef5  call    sub_140040378
0x14003fefa  mov     rax, r14
0x14003fefd  mov     rcx, [rbp+190h+var_20]
0x14003ff04  xor     rcx, rsp; StackCookie
0x14003ff07  call    __security_check_cookie
0x14003ff0c  lea     r11, [rsp+290h+var_10]
0x14003ff14  mov     rbx, [r11+28h]
0x14003ff18  mov     rsi, [r11+30h]
0x14003ff1c  mov     rdi, [r11+38h]
0x14003ff20  mov     rsp, r11
0x14003ff23  pop     r15
0x14003ff25  pop     r14
0x14003ff27  pop     rbp
0x14003ff28  retn
0x14003ff29  call    __report_rangecheckfailure
0x14003ff2f  lea     rdx, [rbp+190h+Source]
0x14003ff33  lea     rcx, [rbp+190h+pExceptionObject]
0x14003ff37  call    sub_14003CC5C
0x14003ff3c  lea     rdx, __TI3?AVinvalid_argument@std@@; pThrowInfo
0x14003ff43  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x14003ff47  call    _CxxThrowException
0x14003ff4d  lea     rdx, aUpdatetelemetr_0; "UpdateTelemetryCV"
0x14003ff54  lea     rcx, [rbp+190h+var_1F0]
0x14003ff58  call    sub_14003CC5C
0x14003ff5d  lea     rdx, __TI3?AVinvalid_argument@std@@; pThrowInfo
0x14003ff64  lea     rcx, [rbp+190h+var_1F0]; pExceptionObject
0x14003ff68  call    _CxxThrowException
```

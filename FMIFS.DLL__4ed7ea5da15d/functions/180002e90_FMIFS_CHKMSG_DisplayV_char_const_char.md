# FMIFS_CHKMSG::DisplayV(char const *,char *)

- ea: `0x180002e90`
- end: `0x18000338f`
- name: `?DisplayV@FMIFS_CHKMSG@@UEAAEPEBDPEAD@Z`
- size: `1279`
- prototype: `unsigned __int8 __fastcall(FMIFS_CHKMSG *__hidden this, const char *, char *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180002e90`
- `0x180009752`
- `0x180009780`
- `0x18000a010`

## import_xrefs

- `ulib!?IsLoggingEnabled@MESSAGE@@QEAAEXZ` at `0x180002f5d`
- `ulib!?IsLoggingEnabled@MESSAGE@@QEAAEXZ` at `0x180002f5d`
- `ulib!?QueryResourceStringV@BASE_SYSTEM@@SAEPEAVWSTRING@@KPEBDPEAD@Z` at `0x180002f4c`
- `ulib!?QueryResourceStringV@BASE_SYSTEM@@SAEPEAVWSTRING@@KPEBDPEAD@Z` at `0x18000328c`
- `ulib!?QueryResourceStringV@BASE_SYSTEM@@SAEPEAVWSTRING@@KPEBDPEAD@Z` at `0x180002f4c`
- `ulib!?QueryResourceStringV@BASE_SYSTEM@@SAEPEAVWSTRING@@KPEBDPEAD@Z` at `0x18000328c`
- `ulib!?LogMessage@MESSAGE@@QEAAEPEBVWSTRING@@@Z` at `0x180002f84`
- `ulib!?LogMessage@MESSAGE@@QEAAEPEBVWSTRING@@@Z` at `0x180002f84`
- `ulib!?QuerySTR@WSTRING@@QEBAPEADKKPEADKE@Z` at `0x180002faa`
- `ulib!?QuerySTR@WSTRING@@QEBAPEADKKPEADKE@Z` at `0x180002faa`
- `ulib!?QueryWSTR@WSTRING@@QEBAPEAGKKPEAGKE@Z` at `0x1800032bd`
- `ulib!?QueryWSTR@WSTRING@@QEBAPEAGKKPEAGKE@Z` at `0x1800032bd`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002ec7`
- `ulib!??0DSTRING@@QEAA@XZ` at `0x180002ec7`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000307f`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000313c`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000307f`
- `ulib!??1DSTRING@@UEAA@XZ` at `0x18000313c`

## pseudocode

```c
bool __fastcall FMIFS_CHKMSG::DisplayV(FMIFS_CHKMSG *this, const char *a2, char *a3)
{
  bool v6; // zf
  unsigned int v7; // edx
  BOOL v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  __int128 *v11; // r8
  __int64 v12; // rdx
  unsigned __int8 (__fastcall *v13)(_QWORD, __int64, __int128 *); // rax
  char v14; // si
  int v16; // eax
  __int64 (__fastcall *v17)(__int64, __int64, unsigned __int8 *); // rax
  __int64 (__fastcall *v18)(__int64, __int64, unsigned __int8 *); // rax
  __int64 (__fastcall *v19)(_QWORD, __int64, __int128 *); // rax
  unsigned __int8 v20; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 v21[7]; // [rsp+31h] [rbp-CFh] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[48]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+80h] [rbp-80h] BYREF
  __int128 v26; // [rsp+90h] [rbp-70h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-60h]
  int v28; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v29[102]; // [rsp+B4h] [rbp-4Ch] BYREF
  char v30[400]; // [rsp+180h] [rbp+80h] BYREF

  DSTRING::DSTRING((DSTRING *)v24);
  v27 = 0;
  v21[0] = 0;
  v20 = 0;
  v25 = 0;
  v26 = 0;
  v23 = 0;
  memset_0(&v28, 0, 0xCCu);
  v6 = (*((_BYTE *)this + 100) & 2) == 0;
  v22 = 0;
  if ( !v6 )
  {
    v7 = *((_DWORD *)this + 17);
    v8 = 1;
    if ( v7 > 0x6F54 )
    {
      if ( v7 <= 0x7BF7 )
      {
        if ( v7 != 31735 )
        {
          switch ( v7 )
          {
            case 0x6F55u:
            case 0x6F56u:
            case 0x6F57u:
            case 0x6F58u:
            case 0x6F59u:
            case 0x6F5Cu:
            case 0x6F5Du:
            case 0x6F5Eu:
            case 0x6F5Fu:
            case 0x6F60u:
            case 0x6F61u:
            case 0x6FBEu:
            case 0x6FBFu:
              goto LABEL_49;
            default:
              goto LABEL_4;
          }
        }
        v10 = 0;
        if ( *((_DWORD *)this + 33) )
        {
          LODWORD(v27) = *(_DWORD *)a3;
          v11 = &v26;
          v12 = 24;
          LODWORD(v26) = *((_DWORD *)a3 + 2);
          HIDWORD(v27) = *((_DWORD *)a3 + 4);
          *((_QWORD *)&v26 + 1) = 0;
          goto LABEL_18;
        }
        LODWORD(v25) = *(_DWORD *)a3;
        v13 = (unsigned __int8 (__fastcall *)(_QWORD, __int64, __int128 *))*((_QWORD *)this + 13);
        *((_QWORD *)&v25 + 1) = 0;
        if ( v13(0, 16, &v25) )
        {
          v11 = (__int128 *)&v28;
          v28 = v25;
          v12 = 204;
          v29[0] = 0;
          v10 = 25;
          goto LABEL_18;
        }
        goto LABEL_51;
      }
LABEL_4:
      if ( BASE_SYSTEM::QueryResourceStringV((struct WSTRING *)v24, v7, a2, a3) )
      {
        if ( MESSAGE::IsLoggingEnabled((MESSAGE *)this)
          && !(*(unsigned __int8 (__fastcall **)(FMIFS_CHKMSG *, _QWORD))(*(_QWORD *)this + 24LL))(this, 0) )
        {
          MESSAGE::LogMessage((MESSAGE *)this, (const struct WSTRING *)v24);
        }
        WSTRING::QuerySTR((WSTRING *)v24, 0, 0xFFFFFFFF, v30, 0x190u, 1u);
        *((_QWORD *)&v23 + 1) = v30;
        v9 = *((_DWORD *)this + 17);
        if ( v9 == 26068 || (unsigned int)(v9 - 3035) < 2 )
          LODWORD(v23) = 2;
        else
          LODWORD(v23) = *((_DWORD *)this + 24) != 2;
        if ( !(*((unsigned __int8 (__fastcall **)(__int64, __int64, __int128 *))this + 13))(14, 16, &v23) )
          goto LABEL_53;
        if ( *((_DWORD *)this + 17) != 26068 )
        {
LABEL_20:
          v8 = 0;
LABEL_21:
          *((_DWORD *)this + 35) = v8;
          DSTRING::~DSTRING((DSTRING *)v24);
          return !v8;
        }
        v10 = 32;
        goto LABEL_13;
      }
LABEL_51:
      v8 = *((_DWORD *)this + 34) != 0;
      goto LABEL_21;
    }
    if ( v7 == 28500 )
    {
LABEL_49:
      LODWORD(v25) = *(_DWORD *)a3;
      v19 = (__int64 (__fastcall *)(_QWORD, __int64, __int128 *))*((_QWORD *)this + 13);
      *((_QWORD *)&v25 + 1) = 0;
      v14 = v19(0, 16, &v25);
      if ( BASE_SYSTEM::QueryResourceStringV((struct WSTRING *)v24, *((_DWORD *)this + 17) + 100, a2, a3 + 8) )
      {
        v28 = v25;
        WSTRING::QueryWSTR((WSTRING *)v24, 0, 0xFFFFFFFF, v29, 0x64u, 1u);
        v11 = (__int128 *)&v28;
        v12 = 204;
        v10 = 25;
        goto LABEL_18;
      }
    }
    else
    {
      if ( v7 <= 0xBD5 )
      {
        if ( v7 == 3029 )
        {
          v10 = 6;
          goto LABEL_13;
        }
        if ( v7 != 1004 )
        {
          if ( v7 != 1132 )
          {
            if ( v7 != 1133 )
            {
              if ( v7 == 2000 || v7 == 2004 )
              {
                v11 = &v25;
                LODWORD(v25) = *(_DWORD *)a3;
                v12 = 16;
                *((_QWORD *)&v25 + 1) = 0;
                v10 = 0;
                goto LABEL_18;
              }
              goto LABEL_4;
            }
            v10 = 22;
LABEL_13:
            v11 = 0;
            v12 = 0;
LABEL_18:
            v14 = (*((__int64 (__fastcall **)(__int64, __int64, __int128 *))this + 13))(v10, v12, v11);
            goto LABEL_19;
          }
LABEL_44:
          v10 = 7;
          goto LABEL_13;
        }
        v16 = *(_DWORD *)a3 >> 10;
        goto LABEL_37;
      }
      switch ( v7 )
      {
        case 0xBDAu:
          v18 = (__int64 (__fastcall *)(__int64, __int64, unsigned __int8 *))*((_QWORD *)this + 13);
          v21[0] = 2;
          v14 = v18(13, 1, v21);
          *((_DWORD *)this + 32) = v21[0];
          break;
        case 0xBE1u:
          v17 = (__int64 (__fastcall *)(__int64, __int64, unsigned __int8 *))*((_QWORD *)this + 13);
          v20 = 2;
          v14 = v17(33, 1, &v20);
          *((_DWORD *)this + 32) = v20;
          break;
        case 0x65B5u:
          v16 = *(_DWORD *)a3;
LABEL_37:
          LODWORD(v22) = v16;
          v11 = (__int128 *)&v22;
          BYTE4(v22) = 0;
          v12 = 8;
          v10 = 26;
          goto LABEL_18;
        case 0x663Cu:
          v11 = (__int128 *)&v22;
          LODWORD(v22) = *(_DWORD *)a3;
          v12 = 8;
          BYTE4(v22) = 1;
          v10 = 26;
          goto LABEL_18;
        case 0x6678u:
          goto LABEL_44;
        default:
          goto LABEL_4;
      }
    }
LABEL_19:
    if ( v14 )
      goto LABEL_20;
LABEL_53:
    if ( *((_DWORD *)this + 34) )
      goto LABEL_21;
    goto LABEL_20;
  }
  DSTRING::~DSTRING((DSTRING *)v24);
  return 1;
}

```

## disassembly

```asm
0x180002e90  push    rbp
0x180002e92  push    rdi
0x180002e93  push    r12
0x180002e95  push    r14
0x180002e97  push    r15
0x180002e99  lea     rbp, [rsp-230h]
0x180002ea1  sub     rsp, 330h
0x180002ea8  mov     rax, cs:__security_cookie
0x180002eaf  xor     rax, rsp
0x180002eb2  mov     [rbp+250h+var_40], rax
0x180002eb9  mov     rdi, rcx
0x180002ebc  mov     r14, r8
0x180002ebf  lea     rcx, [rsp+350h+var_300]
0x180002ec4  mov     r15, rdx
0x180002ec7  call    cs:__imp_??0DSTRING@@QEAA@XZ; DSTRING::DSTRING(void)
0x180002ecd  xor     eax, eax
0x180002ecf  lea     rcx, [rbp+250h+var_2A0]; void *
0x180002ed3  xorps   xmm0, xmm0
0x180002ed6  mov     [rbp+250h+var_2B0], rax
0x180002eda  xorps   xmm1, xmm1
0x180002edd  mov     [rsp+350h+var_31F], al
0x180002ee1  xor     edx, edx; Val
0x180002ee3  mov     [rsp+350h+var_320], al
0x180002ee7  mov     r8d, 0CCh; Size
0x180002eed  movups  [rbp+250h+var_2D0], xmm0
0x180002ef1  movups  [rbp+250h+var_2C0], xmm1
0x180002ef5  movups  [rsp+350h+var_310], xmm0
0x180002efa  call    memset_0
0x180002eff  xor     r12d, r12d
0x180002f02  test    byte ptr [rdi+64h], 2
0x180002f06  mov     [rsp+350h+var_318], r12
0x180002f0b  jz      loc_180003137
0x180002f11  mov     edx, [rdi+44h]
0x180002f14  mov     [rsp+350h+var_28], rbx
0x180002f1c  mov     ebx, 1
0x180002f21  mov     [rsp+350h+var_30], rsi
0x180002f29  cmp     edx, 6F54h
0x180002f2f  jbe     loc_1800030B7
0x180002f35  cmp     edx, 7BF7h
0x180002f3b  jbe     loc_180003007
0x180002f41  mov     r9, r14; jumptable 0000000180003257 default case, cases 28506,28507,28514-28605
0x180002f44  lea     rcx, [rsp+350h+var_300]
0x180002f49  mov     r8, r15
0x180002f4c  call    cs:__imp_?QueryResourceStringV@BASE_SYSTEM@@SAEPEAVWSTRING@@KPEBDPEAD@Z; BASE_SYSTEM::QueryResourceStringV(WSTRING *,ulong,char const *,char *)
0x180002f52  test    al, al
0x180002f54  jz      loc_1800032D6
0x180002f5a  mov     rcx, rdi
0x180002f5d  call    cs:__imp_?IsLoggingEnabled@MESSAGE@@QEAAEXZ; MESSAGE::IsLoggingEnabled(void)
0x180002f63  test    al, al
0x180002f65  jz      short loc_180002F8A
0x180002f67  mov     rax, [rdi]
0x180002f6a  xor     edx, edx
0x180002f6c  mov     rcx, rdi
0x180002f6f  mov     rax, [rax+18h]
0x180002f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f78  test    al, al
0x180002f7a  jnz     short loc_180002F8A
0x180002f7c  lea     rdx, [rsp+350h+var_300]
0x180002f81  mov     rcx, rdi
0x180002f84  call    cs:__imp_?LogMessage@MESSAGE@@QEAAEPEBVWSTRING@@@Z; MESSAGE::LogMessage(WSTRING const *)
0x180002f8a  mov     [rsp+350h+var_328], bl
0x180002f8e  lea     r9, [rbp+250h+var_1D0]
0x180002f95  xor     edx, edx
0x180002f97  mov     [rsp+350h+var_330], 190h
0x180002f9f  mov     r8d, 0FFFFFFFFh
0x180002fa5  lea     rcx, [rsp+350h+var_300]
0x180002faa  call    cs:__imp_?QuerySTR@WSTRING@@QEBAPEADKKPEADKE@Z; WSTRING::QuerySTR(ulong,ulong,char *,ulong,uchar)
0x180002fb0  lea     rax, [rbp+250h+var_1D0]
0x180002fb7  mov     qword ptr [rsp+350h+var_310+8], rax
0x180002fbc  mov     eax, [rdi+44h]
0x180002fbf  cmp     eax, 65D4h
0x180002fc4  jnz     loc_180003111
0x180002fca  mov     dword ptr [rsp+350h+var_310], 2
0x180002fd2  mov     rax, [rdi+68h]
0x180002fd6  lea     r8, [rsp+350h+var_310]
0x180002fdb  mov     edx, 10h
0x180002fe0  mov     ecx, 0Eh
0x180002fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fea  test    al, al
0x180002fec  jz      loc_18000330A
0x180002ff2  cmp     dword ptr [rdi+44h], 65D4h
0x180002ff9  jnz     short loc_18000306E
0x180002ffb  mov     ecx, 20h ; ' '
0x180003000  xor     r8d, r8d
0x180003003  xor     edx, edx
0x180003005  jmp     short loc_180003059
0x180003007  jnz     loc_18000322D
0x18000300d  mov     eax, [r14]
0x180003010  xor     ecx, ecx
0x180003012  cmp     [rdi+84h], r12d
0x180003019  jnz     loc_1800032E7
0x18000301f  mov     dword ptr [rbp+250h+var_2D0], eax
0x180003022  lea     r8, [rbp+250h+var_2D0]
0x180003026  mov     rax, [rdi+68h]
0x18000302a  mov     edx, 10h
0x18000302f  mov     qword ptr [rbp+250h+var_2D0+8], r12
0x180003033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003038  test    al, al
0x18000303a  jz      loc_1800032D6
0x180003040  mov     eax, dword ptr [rbp+250h+var_2D0]
0x180003043  lea     r8, [rbp+250h+var_2A0]
0x180003047  mov     [rbp+250h+var_2A0], eax
0x18000304a  mov     edx, 0CCh
0x18000304f  mov     [rbp+250h+var_29C], r12w
0x180003054  mov     ecx, 19h
0x180003059  mov     rax, [rdi+68h]
0x18000305d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003062  movzx   esi, al
0x180003065  test    sil, sil
0x180003068  jz      loc_18000330A
0x18000306e  mov     ebx, r12d
0x180003071  mov     [rdi+8Ch], ebx
0x180003077  lea     rcx, [rsp+350h+var_300]
0x18000307c  xor     bl, 1
0x18000307f  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180003085  mov     rsi, [rsp+350h+var_30]
0x18000308d  movzx   eax, bl
0x180003090  mov     rbx, [rsp+350h+var_28]
0x180003098  mov     rcx, [rbp+250h+var_40]
0x18000309f  xor     rcx, rsp; StackCookie
0x1800030a2  call    __security_check_cookie
0x1800030a7  add     rsp, 330h
0x1800030ae  pop     r15
0x1800030b0  pop     r14
0x1800030b2  pop     r12
0x1800030b4  pop     rdi
0x1800030b5  pop     rbp
0x1800030b6  retn
0x1800030b7  jz      loc_180003259; jumptable 0000000180003257 cases 28501-28505,28508-28513,28606,28607
0x1800030bd  cmp     edx, 0BD5h
0x1800030c3  ja      loc_180003185
0x1800030c9  jz      loc_18000317B
0x1800030cf  mov     eax, edx
0x1800030d1  sub     eax, 3ECh
0x1800030d6  jz      short loc_180003153
0x1800030d8  sub     eax, 80h
0x1800030dd  jz      loc_1800031AA
0x1800030e3  sub     eax, ebx
0x1800030e5  jz      short loc_180003149
0x1800030e7  sub     eax, 363h
0x1800030ec  jz      short loc_1800030F7
0x1800030ee  cmp     eax, 4
0x1800030f1  jnz     def_180003257; jumptable 0000000180003257 default case, cases 28506,28507,28514-28605
0x1800030f7  mov     eax, [r14]
0x1800030fa  lea     r8, [rbp+250h+var_2D0]
0x1800030fe  mov     dword ptr [rbp+250h+var_2D0], eax
0x180003101  mov     edx, 10h
0x180003106  mov     qword ptr [rbp+250h+var_2D0+8], r12
0x18000310a  xor     ecx, ecx
0x18000310c  jmp     loc_180003059
0x180003111  sub     eax, 0BDBh
0x180003116  jz      loc_180002FCA
0x18000311c  cmp     eax, ebx
0x18000311e  jz      loc_180002FCA
0x180003124  cmp     dword ptr [rdi+60h], 2
0x180003128  mov     eax, r12d
0x18000312b  setnz   al
0x18000312e  mov     dword ptr [rsp+350h+var_310], eax
0x180003132  jmp     loc_180002FD2
0x180003137  lea     rcx, [rsp+350h+var_300]
0x18000313c  call    cs:__imp_??1DSTRING@@UEAA@XZ; DSTRING::~DSTRING(void)
0x180003142  mov     al, 1
0x180003144  jmp     loc_180003098
0x180003149  mov     ecx, 16h
0x18000314e  jmp     loc_180003000
0x180003153  mov     eax, [r14]
0x180003156  shr     eax, 0Ah
0x180003159  jmp     short loc_18000315E
0x18000315b  mov     eax, [r14]
0x18000315e  mov     dword ptr [rsp+350h+var_318], eax
0x180003162  lea     r8, [rsp+350h+var_318]
0x180003167  mov     byte ptr [rsp+350h+var_318+4], r12b
0x18000316c  mov     edx, 8
0x180003171  mov     ecx, 1Ah
0x180003176  jmp     loc_180003059
0x18000317b  mov     ecx, 6
0x180003180  jmp     loc_180003000
0x180003185  mov     eax, edx
0x180003187  sub     eax, 0BDAh
0x18000318c  jz      short loc_180003200
0x18000318e  sub     eax, 7
0x180003191  jz      short loc_1800031D3
0x180003193  sub     eax, 59D4h
0x180003198  jz      short loc_18000315B
0x18000319a  sub     eax, 87h
0x18000319f  jz      short loc_1800031B4
0x1800031a1  cmp     eax, 3Ch ; '<'
0x1800031a4  jnz     def_180003257; jumptable 0000000180003257 default case, cases 28506,28507,28514-28605
0x1800031aa  mov     ecx, 7
0x1800031af  jmp     loc_180003000
0x1800031b4  mov     eax, [r14]
0x1800031b7  lea     r8, [rsp+350h+var_318]
0x1800031bc  mov     dword ptr [rsp+350h+var_318], eax
0x1800031c0  mov     edx, 8
0x1800031c5  mov     byte ptr [rsp+350h+var_318+4], bl
0x1800031c9  mov     ecx, 1Ah
0x1800031ce  jmp     loc_180003059
0x1800031d3  mov     rax, [rdi+68h]
0x1800031d7  lea     r8, [rsp+350h+var_320]
0x1800031dc  mov     edx, ebx
0x1800031de  mov     [rsp+350h+var_320], 2
0x1800031e3  mov     ecx, 21h ; '!'
0x1800031e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ed  movzx   esi, al
0x1800031f0  movzx   eax, [rsp+350h+var_320]
0x1800031f5  mov     [rdi+80h], eax
0x1800031fb  jmp     loc_180003065
0x180003200  mov     rax, [rdi+68h]
0x180003204  lea     r8, [rsp+350h+var_31F]
0x180003209  mov     edx, ebx
0x18000320b  mov     [rsp+350h+var_31F], 2
0x180003210  mov     ecx, 0Dh
0x180003215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000321a  movzx   esi, al
0x18000321d  movzx   eax, [rsp+350h+var_31F]
0x180003222  mov     [rdi+80h], eax
0x180003228  jmp     loc_180003065
0x18000322d  lea     eax, [rdx-6F55h]; switch 107 cases
0x180003233  cmp     eax, 6Ah
0x180003236  ja      def_180003257; jumptable 0000000180003257 default case, cases 28506,28507,28514-28605
0x18000323c  lea     r8, cs:180000000h
0x180003243  movzx   eax, ds:(byte_180003324 - 180000000h)[r8+rax]
0x18000324c  mov     ecx, ds:(jpt_180003257 - 180000000h)[r8+rax*4]
0x180003254  add     rcx, r8
0x180003257  jmp     rcx; switch jump
0x180003259  mov     eax, [r14]; jumptable 0000000180003257 cases 28501-28505,28508-28513,28606,28607
0x18000325c  lea     r8, [rbp+250h+var_2D0]
0x180003260  mov     dword ptr [rbp+250h+var_2D0], eax
0x180003263  mov     edx, 10h
0x180003268  mov     rax, [rdi+68h]
0x18000326c  xor     ecx, ecx
0x18000326e  mov     qword ptr [rbp+250h+var_2D0+8], r12
0x180003272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003277  mov     edx, [rdi+44h]
0x18000327a  lea     r9, [r14+8]
0x18000327e  add     edx, 64h ; 'd'
0x180003281  lea     rcx, [rsp+350h+var_300]
0x180003286  mov     r8, r15
0x180003289  movzx   esi, al
0x18000328c  call    cs:__imp_?QueryResourceStringV@BASE_SYSTEM@@SAEPEAVWSTRING@@KPEBDPEAD@Z; BASE_SYSTEM::QueryResourceStringV(WSTRING *,ulong,char const *,char *)
0x180003292  test    al, al
0x180003294  jz      loc_180003065
0x18000329a  mov     eax, dword ptr [rbp+250h+var_2D0]
0x18000329d  lea     r9, [rbp+250h+var_29C]
0x1800032a1  mov     [rsp+350h+var_328], bl
0x1800032a5  lea     rcx, [rsp+350h+var_300]
0x1800032aa  xor     edx, edx
0x1800032ac  mov     [rbp+250h+var_2A0], eax
0x1800032af  mov     r8d, 0FFFFFFFFh
0x1800032b5  mov     [rsp+350h+var_330], 64h ; 'd'
0x1800032bd  call    cs:__imp_?QueryWSTR@WSTRING@@QEBAPEAGKKPEAGKE@Z; WSTRING::QueryWSTR(ulong,ulong,ushort *,ulong,uchar)
0x1800032c3  lea     r8, [rbp+250h+var_2A0]
0x1800032c7  mov     edx, 0CCh
0x1800032cc  mov     ecx, 19h
0x1800032d1  jmp     loc_180003059
0x1800032d6  mov     ebx, r12d
0x1800032d9  cmp     [rdi+88h], ebx
0x1800032df  setnz   bl
0x1800032e2  jmp     loc_180003071
0x1800032e7  mov     dword ptr [rbp+250h+var_2B0], eax
0x1800032ea  lea     r8, [rbp+250h+var_2C0]
0x1800032ee  mov     eax, [r14+8]
0x1800032f2  mov     edx, 18h
0x1800032f7  mov     dword ptr [rbp+250h+var_2C0], eax
0x1800032fa  mov     eax, [r14+10h]
0x1800032fe  mov     dword ptr [rbp+250h+var_2B0+4], eax
0x180003301  mov     qword ptr [rbp+250h+var_2C0+8], r12
0x180003305  jmp     loc_180003059
0x18000330a  cmp     [rdi+88h], r12d
0x180003311  jnz     loc_180003071
0x180003317  jmp     loc_18000306E
```

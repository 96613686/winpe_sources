# write_double_translated_ansi_nolock(int,char const * const,uint,__crt_cached_ptd_host &)

- ea: `0x1400191f8`
- end: `0x140019670`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDIAEAV__crt_cached_ptd_host@@@Z`
- size: `1144`
- prototype: `__int64 __fastcall(__int64, int, _BYTE *, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x140019bc8`

## callees

- `0x14000ad70`
- `0x1400113dc`
- `0x140015164`
- `0x140015314`
- `0x1400191f8`
- `0x14001bf00`
- `0x14001db10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001963e`
- `KERNEL32!GetLastError` at `0x14001963e`
- `KERNEL32!WriteFile` at `0x140019542`
- `KERNEL32!WriteFile` at `0x140019588`
- `KERNEL32!WriteFile` at `0x140019542`
- `KERNEL32!WriteFile` at `0x140019588`
- `KERNEL32!GetConsoleOutputCP` at `0x140019277`
- `KERNEL32!GetConsoleOutputCP` at `0x140019277`

## pseudocode

```c
__int64 __fastcall write_double_translated_ansi_nolock(
        __int64 a1,
        int a2,
        _BYTE *a3,
        int a4,
        __crt_cached_ptd_host *a5)
{
  _BYTE *v5; // rsi
  __int64 v6; // r14
  __int64 v8; // r13
  __int64 v9; // r15
  unsigned __int64 v10; // r12
  int v11; // edi
  __crt_cached_ptd_host *v12; // r10
  int v13; // ecx
  __int64 v14; // r9
  int v15; // edx
  __int64 v16; // r12
  int v17; // edx
  __int64 v18; // r14
  _BYTE *v19; // rcx
  int v20; // r12d
  __int64 v21; // rdx
  signed __int64 v22; // r8
  __int64 v23; // rcx
  _BYTE *v24; // rdx
  __int64 i; // rdx
  __int64 v26; // r13
  __int64 v27; // r8
  unsigned int v28; // r14d
  __int64 v29; // r8
  char v30; // cl
  int v31; // r8d
  _BYTE *v32; // rdx
  __int64 v33; // r9
  DWORD v34; // eax
  DWORD v35; // r14d
  HANDLE v36; // r12
  _BYTE *v37; // rsi
  __int64 v38; // rdx
  __int64 v39; // r9
  __int16 v41[2]; // [rsp+48h] [rbp-71h] BYREF
  int v42; // [rsp+4Ch] [rbp-6Dh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 v44; // [rsp+58h] [rbp-61h]
  __crt_cached_ptd_host *v45; // [rsp+60h] [rbp-59h]
  __int64 v46; // [rsp+68h] [rbp-51h] BYREF
  UINT ConsoleOutputCP; // [rsp+70h] [rbp-49h]
  int v48; // [rsp+74h] [rbp-45h]
  _BYTE *v49; // [rsp+78h] [rbp-41h]
  __int64 v50; // [rsp+80h] [rbp-39h]
  __int64 v51; // [rsp+88h] [rbp-31h] BYREF
  _BYTE *v52; // [rsp+90h] [rbp-29h] BYREF
  _BYTE *v53; // [rsp+98h] [rbp-21h] BYREF
  HANDLE hFile; // [rsp+A0h] [rbp-19h]
  __int64 v55; // [rsp+A8h] [rbp-11h]
  __int64 v56; // [rsp+B0h] [rbp-9h]
  _BYTE v57[8]; // [rsp+B8h] [rbp-1h] BYREF
  _BYTE v58[8]; // [rsp+C0h] [rbp+7h] BYREF
  char Buffer[8]; // [rsp+C8h] [rbp+Fh] BYREF

  v56 = -2;
  v5 = a3;
  v49 = a3;
  v6 = a2;
  v45 = a5;
  v8 = (__int64)a2 >> 6;
  v50 = v8;
  v9 = 9LL * (a2 & 0x3F);
  hFile = *(HANDLE *)(qword_1400D69C0[v8] + 72LL * (a2 & 0x3F) + 40);
  v10 = (unsigned __int64)&a3[a4];
  v44 = v10;
  ConsoleOutputCP = GetConsoleOutputCP();
  v11 = 0;
  v12 = a5;
  if ( !*((_BYTE *)a5 + 40) )
  {
    __crt_cached_ptd_host::update_locale_slow(v45);
    v12 = v45;
  }
  v13 = *(_DWORD *)(*((_QWORD *)v12 + 3) + 12LL);
  v48 = v13;
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 8) = 0;
  if ( (unsigned __int64)v49 < v10 )
  {
    v14 = v6 >> 6;
    v55 = v6 >> 6;
    v15 = 0;
    while ( 1 )
    {
      LOBYTE(v41[0]) = *v5;
      v42 = 0;
      LODWORD(v16) = 1;
      if ( v13 == 65001 )
      {
        v17 = 0;
        v18 = 0;
        v19 = (_BYTE *)(qword_1400D69C0[v14] + 8 * v9 + 62);
        do
        {
          if ( !*v19 )
            break;
          ++v17;
          ++v18;
          ++v19;
        }
        while ( v18 < 5 );
        if ( v18 <= 0 )
        {
          v26 = *((char *)&qword_1400D67C8[1] + (unsigned __int8)*v5);
          v27 = v44 - (_QWORD)v5;
          if ( (int)v26 + 1 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v27 > 0 )
            {
              v38 = 0;
              v39 = v50;
              do
              {
                *(_BYTE *)(v38 + qword_1400D69C0[v39] + 8 * v9 + 62) = v5[v38];
                ++v11;
                ++v38;
              }
              while ( v11 < v27 );
            }
            *(_DWORD *)(a1 + 4) += v27;
            return a1;
          }
          v46 = 0;
          v53 = v5;
          v28 = ((_DWORD)v26 == 3) + 1;
          if ( sub_140015164(&v42, &v53, v28, &v46, v12) == -1 )
            return a1;
          v5 += v26;
          LODWORD(v16) = v28;
          v8 = v50;
        }
        else
        {
          v20 = *((char *)&qword_1400D67C8[1] + *(unsigned __int8 *)(qword_1400D69C0[v8] + 8 * v9 + 62)) + 1;
          LODWORD(v46) = v20 - v17;
          v21 = v44 - (_QWORD)v5;
          v22 = (int)v46;
          if ( (int)v46 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v21 > 0 )
            {
              v37 = &v5[-v18];
              do
              {
                *(_BYTE *)(v18 + qword_1400D69C0[v8] + 8 * v9 + 62) = v37[v18];
                ++v11;
                ++v18;
              }
              while ( v11 < v21 );
            }
            *(_DWORD *)(a1 + 4) += v21;
            return a1;
          }
          v23 = 0;
          v24 = (_BYTE *)(qword_1400D69C0[v14] + 8 * v9 + 62);
          do
            v57[v23++] = *v24++;
          while ( v23 < v18 );
          if ( v22 > 0 )
          {
            memmove(&v57[v18], v5, v22);
            v12 = v45;
          }
          for ( i = 0; i < v18; ++i )
            *(_BYTE *)(i + qword_1400D69C0[v8] + 8 * v9 + 62) = 0;
          v51 = 0;
          v52 = v57;
          v16 = (unsigned int)(v20 == 4) + 1;
          if ( sub_140015164(&v42, &v52, v16, &v51, v12) == -1 )
            return a1;
          v5 += (int)v46 - 1;
        }
      }
      else
      {
        v29 = qword_1400D69C0[v8];
        v30 = *(_BYTE *)(v29 + 8 * v9 + 61);
        if ( (v30 & 4) != 0 )
        {
          v58[0] = *(_BYTE *)(v29 + 8 * v9 + 62);
          v58[1] = *v5;
          *(_BYTE *)(v29 + 8 * v9 + 61) = v30 & 0xFB;
          v31 = 2;
          v32 = v58;
          goto LABEL_29;
        }
        v33 = (unsigned __int8)*v5;
        if ( *(__int16 *)(**((_QWORD **)v12 + 3) + 2 * v33) >= 0 )
        {
          v31 = 1;
          LODWORD(v32) = (_DWORD)v5;
LABEL_29:
          if ( (unsigned int)mbtowc_internal((int)&v42, (int)v32, v31, v12) == -1 )
            return a1;
          goto LABEL_30;
        }
        if ( (unsigned __int64)(v5 + 1) >= v44 )
        {
          *(_BYTE *)(v29 + 8 * v9 + 62) = v33;
          *(_BYTE *)(qword_1400D69C0[v8] + 8 * v9 + 61) |= 4u;
          *(_DWORD *)(a1 + 4) = v15 + 1;
          return a1;
        }
        if ( (unsigned int)mbtowc_internal((int)&v42, (int)v5, 2, v12) == -1 )
          return a1;
        ++v5;
      }
LABEL_30:
      ++v5;
      v34 = _acrt_WideCharToMultiByte(ConsoleOutputCP, 0, (unsigned int)&v42, v16, (unsigned int)Buffer, 5, 0, 0);
      v35 = v34;
      if ( !v34 )
        return a1;
      NumberOfBytesWritten = 0;
      v36 = hFile;
      if ( !WriteFile(hFile, Buffer, v34, &NumberOfBytesWritten, 0) )
      {
LABEL_48:
        *(_DWORD *)a1 = GetLastError();
        return a1;
      }
      v15 = *(_DWORD *)(a1 + 8) + (_DWORD)v5 - (_DWORD)v49;
      *(_DWORD *)(a1 + 4) = v15;
      if ( NumberOfBytesWritten < v35 )
        return a1;
      if ( LOBYTE(v41[0]) == 10 )
      {
        v41[0] = 13;
        if ( !WriteFile(v36, v41, 1u, &NumberOfBytesWritten, 0) )
          goto LABEL_48;
        if ( !NumberOfBytesWritten )
          return a1;
        ++*(_DWORD *)(a1 + 8);
        v15 = ++*(_DWORD *)(a1 + 4);
      }
      if ( (unsigned __int64)v5 >= v44 )
        return a1;
      v12 = v45;
      v14 = v55;
      v13 = v48;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1400191f8  mov     rax, rsp
0x1400191fb  push    rbp
0x1400191fc  push    rsi
0x1400191fd  push    rdi
0x1400191fe  push    r12
0x140019200  push    r13
0x140019202  push    r14
0x140019204  push    r15
0x140019206  lea     rbp, [rax-57h]
0x14001920a  sub     rsp, 0D0h
0x140019211  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x140019219  mov     [rax+8], rbx
0x14001921d  mov     rax, cs:__security_cookie
0x140019224  xor     rax, rsp
0x140019227  mov     [rbp+4Fh+var_38], rax
0x14001922b  mov     rsi, r8
0x14001922e  mov     [rbp+4Fh+var_90], r8
0x140019232  movsxd  r14, edx
0x140019235  mov     rbx, rcx
0x140019238  mov     rax, [rbp+4Fh+arg_20]
0x14001923c  mov     [rbp+4Fh+var_A8], rax
0x140019240  mov     rax, r14
0x140019243  mov     r13, r14
0x140019246  sar     r13, 6
0x14001924a  mov     [rbp+4Fh+var_88], r13
0x14001924e  lea     rcx, cs:140000000h
0x140019255  and     eax, 3Fh
0x140019258  lea     r15, [rax+rax*8]
0x14001925c  mov     rax, rva qword_1400D69C0[rcx+r13*8]
0x140019264  mov     rax, [rax+r15*8+28h]
0x140019269  mov     [rbp+4Fh+hFile], rax
0x14001926d  mov     r12d, r9d
0x140019270  add     r12, r8
0x140019273  mov     [rbp+4Fh+var_B0], r12
0x140019277  call    cs:GetConsoleOutputCP
0x14001927d  mov     [rbp+4Fh+var_98], eax
0x140019280  xor     edi, edi
0x140019282  mov     r10, [rbp+4Fh+var_A8]
0x140019286  cmp     [r10+28h], dil
0x14001928a  jnz     short loc_140019298
0x14001928c  mov     rcx, r10; this
0x14001928f  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x140019294  mov     r10, [rbp+4Fh+var_A8]
0x140019298  mov     rcx, [r10+18h]
0x14001929c  mov     ecx, [rcx+0Ch]
0x14001929f  mov     [rbp+4Fh+var_94], ecx
0x1400192a2  xor     eax, eax
0x1400192a4  mov     [rbx], rax
0x1400192a7  mov     [rbx+8], eax
0x1400192aa  cmp     [rbp+4Fh+var_90], r12
0x1400192ae  jnb     loc_140019646
0x1400192b4  mov     r9, r14
0x1400192b7  sar     r9, 6
0x1400192bb  mov     [rbp+4Fh+var_60], r9
0x1400192bf  mov     edx, edi
0x1400192c1  mov     al, [rsi]
0x1400192c3  mov     byte ptr [rbp+4Fh+var_C0], al
0x1400192c6  mov     [rbp+4Fh+var_BC], edi
0x1400192c9  mov     r12d, 1
0x1400192cf  lea     r11, cs:140000000h
0x1400192d6  cmp     ecx, 0FDE9h
0x1400192dc  jnz     loc_14001945D
0x1400192e2  mov     edx, edi
0x1400192e4  mov     r14, rdi
0x1400192e7  lea     rcx, ds:3Eh[r15*8]
0x1400192ef  add     rcx, rva qword_1400D69C0[r11+r9*8]
0x1400192f7  cmp     [rcx], dil
0x1400192fa  jz      short loc_14001930A
0x1400192fc  inc     edx
0x1400192fe  inc     r14
0x140019301  inc     rcx
0x140019304  cmp     r14, 5
0x140019308  jl      short loc_1400192F7
0x14001930a  test    r14, r14
0x14001930d  jle     loc_1400193F3
0x140019313  mov     rax, rva qword_1400D69C0[r11+r13*8]
0x14001931b  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x140019321  movsx   r12d, byte ptr [rcx+r11+0D67D0h]
0x14001932a  inc     r12d
0x14001932d  mov     eax, r12d
0x140019330  sub     eax, edx
0x140019332  mov     dword ptr [rbp+4Fh+var_A0], eax
0x140019335  mov     rdx, [rbp+4Fh+var_B0]
0x140019339  sub     rdx, rsi
0x14001933c  movsxd  r8, eax; MaxCount
0x14001933f  cmp     r8, rdx
0x140019342  jg      loc_1400195C3
0x140019348  mov     rcx, rdi
0x14001934b  lea     rdx, ds:3Eh[r15*8]
0x140019353  add     rdx, rva qword_1400D69C0[r11+r9*8]
0x14001935b  mov     al, [rdx]
0x14001935d  mov     [rbp+rcx+4Fh+var_50], al
0x140019361  inc     rcx
0x140019364  inc     rdx
0x140019367  cmp     rcx, r14
0x14001936a  jl      short loc_14001935B
0x14001936c  test    r8, r8
0x14001936f  jle     short loc_14001938B
0x140019371  lea     rcx, [rbp+4Fh+var_50]
0x140019375  add     rcx, r14; Dst
0x140019378  mov     rdx, rsi; Src
0x14001937b  call    memmove
0x140019380  mov     r10, [rbp+4Fh+var_A8]
0x140019384  lea     r11, cs:140000000h
0x14001938b  mov     rdx, rdi
0x14001938e  mov     rcx, rva qword_1400D69C0[r11+r13*8]
0x140019396  add     rcx, rdx
0x140019399  mov     [rcx+r15*8+3Eh], dil
0x14001939e  inc     rdx
0x1400193a1  cmp     rdx, r14
0x1400193a4  jl      short loc_14001938E
0x1400193a6  mov     [rbp+4Fh+var_80], rdi
0x1400193aa  lea     rax, [rbp+4Fh+var_50]
0x1400193ae  mov     [rbp+4Fh+var_78], rax
0x1400193b2  mov     eax, edi
0x1400193b4  cmp     r12d, 4
0x1400193b8  setz    al
0x1400193bb  inc     eax
0x1400193bd  mov     r12d, eax
0x1400193c0  mov     r8d, eax
0x1400193c3  mov     [rsp+100h+lpOverlapped], r10
0x1400193c8  lea     r9, [rbp+4Fh+var_80]
0x1400193cc  lea     rdx, [rbp+4Fh+var_78]
0x1400193d0  lea     rcx, [rbp+4Fh+var_BC]
0x1400193d4  call    sub_140015164
0x1400193d9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400193dd  jz      loc_140019646
0x1400193e3  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x1400193e6  dec     eax
0x1400193e8  movsxd  rcx, eax
0x1400193eb  add     rsi, rcx
0x1400193ee  jmp     loc_1400194EE
0x1400193f3  movzx   eax, byte ptr [rsi]
0x1400193f6  movsx   r13, byte ptr [rax+r11+0D67D0h]
0x1400193ff  lea     ecx, [r13+1]
0x140019403  mov     r8, [rbp+4Fh+var_B0]
0x140019407  sub     r8, rsi
0x14001940a  movsxd  rax, ecx
0x14001940d  cmp     rax, r8
0x140019410  jg      loc_1400195F1
0x140019416  mov     [rbp+4Fh+var_A0], rdi
0x14001941a  mov     [rbp+4Fh+var_70], rsi
0x14001941e  mov     eax, edi
0x140019420  cmp     ecx, 4
0x140019423  setz    al
0x140019426  inc     eax
0x140019428  mov     r14d, eax
0x14001942b  mov     r8d, eax
0x14001942e  mov     [rsp+100h+lpOverlapped], r10
0x140019433  lea     r9, [rbp+4Fh+var_A0]
0x140019437  lea     rdx, [rbp+4Fh+var_70]
0x14001943b  lea     rcx, [rbp+4Fh+var_BC]
0x14001943f  call    sub_140015164
0x140019444  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140019448  jz      loc_140019646
0x14001944e  add     rsi, r13
0x140019451  mov     r12d, r14d
0x140019454  mov     r13, [rbp+4Fh+var_88]
0x140019458  jmp     loc_1400194EE
0x14001945d  mov     r8, rva qword_1400D69C0[r11+r13*8]
0x140019465  mov     cl, [r8+r15*8+3Dh]
0x14001946a  test    cl, 4
0x14001946d  jz      short loc_140019490
0x14001946f  mov     al, [r8+r15*8+3Eh]
0x140019474  mov     [rbp+4Fh+var_48], al
0x140019477  mov     al, [rsi]
0x140019479  mov     [rbp+4Fh+var_47], al
0x14001947c  and     cl, 0FBh
0x14001947f  mov     [r8+r15*8+3Dh], cl
0x140019484  mov     r8d, 2
0x14001948a  lea     rdx, [rbp+4Fh+var_48]
0x14001948e  jmp     short loc_1400194D9
0x140019490  movzx   r9d, byte ptr [rsi]
0x140019494  mov     rax, [r10+18h]
0x140019498  mov     rcx, [rax]
0x14001949b  cmp     [rcx+r9*2], di
0x1400194a0  jge     short loc_1400194D3
0x1400194a2  lea     r14, [rsi+1]
0x1400194a6  cmp     r14, [rbp+4Fh+var_B0]
0x1400194aa  jnb     loc_140019623
0x1400194b0  mov     r9, r10; this
0x1400194b3  mov     r8d, 2; int
0x1400194b9  mov     rdx, rsi; int
0x1400194bc  lea     rcx, [rbp+4Fh+var_BC]; int
0x1400194c0  call    _mbtowc_internal
0x1400194c5  cmp     eax, 0FFFFFFFFh
0x1400194c8  jz      loc_140019646
0x1400194ce  mov     rsi, r14
0x1400194d1  jmp     short loc_1400194EE
0x1400194d3  mov     r8, r12; int
0x1400194d6  mov     rdx, rsi; int
0x1400194d9  mov     r9, r10; this
0x1400194dc  lea     rcx, [rbp+4Fh+var_BC]; int
0x1400194e0  call    _mbtowc_internal
0x1400194e5  cmp     eax, 0FFFFFFFFh
0x1400194e8  jz      loc_140019646
0x1400194ee  inc     rsi
0x1400194f1  mov     [rsp+38h], rdi
0x1400194f6  mov     [rsp+100h+var_D0], rdi
0x1400194fb  mov     dword ptr [rsp+100h+var_D8], 5
0x140019503  lea     rax, [rbp+4Fh+Buffer]
0x140019507  mov     [rsp+100h+lpOverlapped], rax
0x14001950c  mov     r9d, r12d
0x14001950f  lea     r8, [rbp+4Fh+var_BC]
0x140019513  xor     edx, edx
0x140019515  mov     ecx, [rbp+4Fh+var_98]
0x140019518  call    __acrt_WideCharToMultiByte
0x14001951d  mov     r14d, eax
0x140019520  test    eax, eax
0x140019522  jz      loc_140019646
0x140019528  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x14001952b  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x140019530  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140019534  mov     r8d, eax; nNumberOfBytesToWrite
0x140019537  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x14001953b  mov     r12, [rbp+4Fh+hFile]
0x14001953f  mov     rcx, r12; hFile
0x140019542  call    cs:WriteFile
0x140019548  test    eax, eax
0x14001954a  jz      loc_14001963E
0x140019550  mov     edx, esi
0x140019552  sub     edx, dword ptr [rbp+4Fh+var_90]
0x140019555  add     edx, [rbx+8]
0x140019558  mov     [rbx+4], edx
0x14001955b  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x14001955f  jb      loc_140019646
0x140019565  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x140019569  jnz     short loc_1400195A9
0x14001956b  mov     eax, 0Dh
0x140019570  mov     [rbp+4Fh+var_C0], ax
0x140019574  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x140019579  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001957d  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x140019581  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x140019585  mov     rcx, r12; hFile
0x140019588  call    cs:WriteFile
0x14001958e  test    eax, eax
0x140019590  jz      loc_14001963E
0x140019596  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x14001959a  jb      loc_140019646
0x1400195a0  inc     dword ptr [rbx+8]
0x1400195a3  inc     dword ptr [rbx+4]
0x1400195a6  mov     edx, [rbx+4]
0x1400195a9  cmp     rsi, [rbp+4Fh+var_B0]
0x1400195ad  jnb     loc_140019646
0x1400195b3  mov     r10, [rbp+4Fh+var_A8]
0x1400195b7  mov     r9, [rbp+4Fh+var_60]
0x1400195bb  mov     ecx, [rbp+4Fh+var_94]
0x1400195be  jmp     loc_1400192C1
0x1400195c3  test    rdx, rdx
0x1400195c6  jle     short loc_1400195EC
0x1400195c8  sub     rsi, r14
0x1400195cb  mov     rcx, rva qword_1400D69C0[r11+r13*8]
0x1400195d3  add     rcx, r14
0x1400195d6  mov     al, [rsi+r14]
0x1400195da  mov     [rcx+r15*8+3Eh], al
0x1400195df  inc     edi
0x1400195e1  inc     r14
0x1400195e4  movsxd  rax, edi
0x1400195e7  cmp     rax, rdx
0x1400195ea  jl      short loc_1400195CB
0x1400195ec  add     [rbx+4], edx
0x1400195ef  jmp     short loc_140019646
0x1400195f1  test    r8, r8
0x1400195f4  jle     short loc_14001961D
0x1400195f6  mov     rdx, rdi
0x1400195f9  mov     r9, [rbp+4Fh+var_88]
0x1400195fd  mov     rcx, rva qword_1400D69C0[r11+r9*8]
0x140019605  add     rcx, rdx
0x140019608  mov     al, [rdx+rsi]
0x14001960b  mov     [rcx+r15*8+3Eh], al
0x140019610  inc     edi
0x140019612  inc     rdx
0x140019615  movsxd  rax, edi
0x140019618  cmp     rax, r8
0x14001961b  jl      short loc_1400195FD
0x14001961d  add     [rbx+4], r8d
0x140019621  jmp     short loc_140019646
0x140019623  mov     [r8+r15*8+3Eh], r9b
0x140019628  mov     rax, rva qword_1400D69C0[r11+r13*8]
0x140019630  or      byte ptr [rax+r15*8+3Dh], 4
0x140019636  lea     eax, [rdx+1]
0x140019639  mov     [rbx+4], eax
0x14001963c  jmp     short loc_140019646
0x14001963e  call    cs:GetLastError
0x140019644  mov     [rbx], eax
0x140019646  mov     rax, rbx
0x140019649  mov     rcx, [rbp+4Fh+var_38]
0x14001964d  xor     rcx, rsp; StackCookie
0x140019650  call    __security_check_cookie
0x140019655  mov     rbx, [rsp+100h+arg_0]
0x14001965d  add     rsp, 0D0h
0x140019664  pop     r15
0x140019666  pop     r14
0x140019668  pop     r13
0x14001966a  pop     r12
0x14001966c  pop     rdi
0x14001966d  pop     rsi
0x14001966e  pop     rbp
0x14001966f  retn
  ... truncated ...
```

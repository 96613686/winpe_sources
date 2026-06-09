# write_double_translated_ansi_nolock(int,char const * const,uint,__crt_cached_ptd_host &)

- ea: `0x140020ed4`
- end: `0x140021367`
- name: `?write_double_translated_ansi_nolock@@YA?AUwrite_result@?A0x17268360@@HQEBDIAEAV__crt_cached_ptd_host@@@Z`
- size: `1171`
- prototype: `__int64 __fastcall(__int64, int, _BYTE *, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1400218b8`

## callees

- `0x14000a640`
- `0x140014130`
- `0x14001a998`
- `0x14001ae8c`
- `0x14001dca4`
- `0x140020ed4`
- `0x140029c50`

## import_xrefs

- `KERNEL32!WriteFile` at `0x140021230`
- `KERNEL32!WriteFile` at `0x140021276`
- `KERNEL32!WriteFile` at `0x140021230`
- `KERNEL32!WriteFile` at `0x140021276`
- `KERNEL32!GetLastError` at `0x140021335`
- `KERNEL32!GetLastError` at `0x140021335`
- `KERNEL32!GetConsoleOutputCP` at `0x140020f53`
- `KERNEL32!GetConsoleOutputCP` at `0x140020f53`

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
  __int64 v14; // r11
  int v15; // edx
  int v16; // r12d
  int v17; // edx
  __int64 v18; // r14
  _BYTE *v19; // rcx
  int v20; // r12d
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  _BYTE *v24; // rdx
  __int64 i; // rdx
  __int64 v26; // r13
  __int64 v27; // r9
  int v28; // r14d
  __int64 v29; // r8
  char v30; // cl
  __int64 v31; // r8
  _BYTE *v32; // rdx
  __int64 v33; // r9
  DWORD v34; // eax
  DWORD v35; // r14d
  HANDLE v36; // r12
  _BYTE *v37; // rsi
  __int64 v38; // r8
  __int64 v39; // r10
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
  hFile = *(HANDLE *)(qword_14003E600[v8] + 72LL * (a2 & 0x3F) + 40);
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
      v16 = 1;
      if ( v13 == 65001 )
      {
        v17 = 0;
        v18 = 0;
        v19 = (_BYTE *)(qword_14003E600[v14] + 8 * v9 + 62);
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
          v26 = (char)algn_14003CB31[(unsigned __int8)*v5 + 15];
          v27 = v44 - (_QWORD)v5;
          if ( (int)v26 + 1 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v27 > 0 )
            {
              v38 = 0;
              v39 = v50;
              do
              {
                *(_BYTE *)(v38 + 8 * v9 + qword_14003E600[v39] + 62) = v5[v38];
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
          if ( sub_14001AE8C((unsigned int)&v42, (unsigned int)&v53, v28, (unsigned int)&v46, (__int64)v12) == -1 )
            return a1;
          v5 += v26;
          v16 = v28;
          v8 = v50;
        }
        else
        {
          v20 = (char)algn_14003CB31[*(unsigned __int8 *)(qword_14003E600[v8] + 8 * v9 + 62) + 15] + 1;
          LODWORD(v46) = v20 - v17;
          v21 = v44 - (_QWORD)v5;
          v22 = v20 - v17;
          if ( v22 > (__int64)(v44 - (_QWORD)v5) )
          {
            if ( v21 > 0 )
            {
              v37 = &v5[-v18];
              do
              {
                *(_BYTE *)(v18 + 8 * v9 + qword_14003E600[v8] + 62) = v37[v18];
                ++v11;
                ++v18;
              }
              while ( v11 < v21 );
            }
            *(_DWORD *)(a1 + 4) += v21;
            return a1;
          }
          v23 = 0;
          v24 = (_BYTE *)(qword_14003E600[v14] + 8 * v9 + 62);
          do
            v57[v23++] = *v24++;
          while ( v23 < v18 );
          if ( v22 > 0 )
          {
            sub_140029C50(&v57[v18], v5, v22);
            v12 = v45;
          }
          for ( i = 0; i < v18; ++i )
            *(_BYTE *)(i + 8 * v9 + qword_14003E600[v8] + 62) = 0;
          v51 = 0;
          v52 = v57;
          v16 = (v20 == 4) + 1;
          if ( sub_14001AE8C((unsigned int)&v42, (unsigned int)&v52, v16, (unsigned int)&v51, (__int64)v12) == -1 )
            return a1;
          v5 += (int)v46 - 1;
        }
      }
      else
      {
        v29 = qword_14003E600[v8];
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
          v32 = v5;
LABEL_29:
          if ( (unsigned int)mbtowc_internal(&v42, v32, v31, v12) == -1 )
            return a1;
          goto LABEL_30;
        }
        if ( (unsigned __int64)(v5 + 1) >= v44 )
        {
          *(_BYTE *)(v29 + 8 * v9 + 62) = v33;
          *(_BYTE *)(qword_14003E600[v8] + 8 * v9 + 61) |= 4u;
          *(_DWORD *)(a1 + 4) = v15 + 1;
          return a1;
        }
        if ( (unsigned int)mbtowc_internal(&v42, v5, 2, v12) == -1 )
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
      v15 = (_DWORD)v5 + *(_DWORD *)(a1 + 8) - (_DWORD)v49;
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
0x140020ed4  mov     rax, rsp
0x140020ed7  push    rbp
0x140020ed8  push    rsi
0x140020ed9  push    rdi
0x140020eda  push    r12
0x140020edc  push    r13
0x140020ede  push    r14
0x140020ee0  push    r15
0x140020ee2  lea     rbp, [rax-57h]
0x140020ee6  sub     rsp, 0D0h
0x140020eed  mov     [rbp+4Fh+var_58], 0FFFFFFFFFFFFFFFEh
0x140020ef5  mov     [rax+8], rbx
0x140020ef9  mov     rax, cs:__security_cookie
0x140020f00  xor     rax, rsp
0x140020f03  mov     [rbp+4Fh+var_38], rax
0x140020f07  mov     rsi, r8
0x140020f0a  mov     [rbp+4Fh+var_90], r8
0x140020f0e  movsxd  r14, edx
0x140020f11  mov     rbx, rcx
0x140020f14  mov     rax, [rbp+4Fh+arg_20]
0x140020f18  mov     [rbp+4Fh+var_A8], rax
0x140020f1c  mov     rax, r14
0x140020f1f  mov     r13, r14
0x140020f22  sar     r13, 6
0x140020f26  mov     [rbp+4Fh+var_88], r13
0x140020f2a  lea     rcx, cs:140000000h
0x140020f31  and     eax, 3Fh
0x140020f34  lea     r15, [rax+rax*8]
0x140020f38  mov     rax, rva qword_14003E600[rcx+r13*8]
0x140020f40  mov     rax, [rax+r15*8+28h]
0x140020f45  mov     [rbp+4Fh+hFile], rax
0x140020f49  mov     r12d, r9d
0x140020f4c  add     r12, r8
0x140020f4f  mov     [rbp+4Fh+var_B0], r12
0x140020f53  call    cs:GetConsoleOutputCP
0x140020f59  mov     [rbp+4Fh+var_98], eax
0x140020f5c  xor     edi, edi
0x140020f5e  mov     r10, [rbp+4Fh+var_A8]
0x140020f62  cmp     [r10+28h], dil
0x140020f66  jnz     short loc_140020F74
0x140020f68  mov     rcx, r10; this
0x140020f6b  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x140020f70  mov     r10, [rbp+4Fh+var_A8]
0x140020f74  mov     rcx, [r10+18h]
0x140020f78  mov     ecx, [rcx+0Ch]
0x140020f7b  mov     [rbp+4Fh+var_94], ecx
0x140020f7e  xor     eax, eax
0x140020f80  mov     [rbx], rax
0x140020f83  mov     [rbx+8], eax
0x140020f86  cmp     [rbp+4Fh+var_90], r12
0x140020f8a  jnb     loc_14002133D
0x140020f90  mov     r11, r14
0x140020f93  sar     r11, 6
0x140020f97  mov     [rbp+4Fh+var_60], r11
0x140020f9b  mov     edx, edi
0x140020f9d  mov     al, [rsi]
0x140020f9f  mov     byte ptr [rbp+4Fh+var_C0], al
0x140020fa2  mov     [rbp+4Fh+var_BC], edi
0x140020fa5  mov     r12d, 1
0x140020fab  cmp     ecx, 0FDE9h
0x140020fb1  jnz     loc_140021144
0x140020fb7  mov     edx, edi
0x140020fb9  mov     r14, rdi
0x140020fbc  lea     r12, cs:140000000h
0x140020fc3  lea     rcx, ds:3Eh[r15*8]
0x140020fcb  add     rcx, rva qword_14003E600[r12+r11*8]
0x140020fd3  cmp     [rcx], dil
0x140020fd6  jz      short loc_140020FE6
0x140020fd8  inc     edx
0x140020fda  inc     r14
0x140020fdd  inc     rcx
0x140020fe0  cmp     r14, 5
0x140020fe4  jl      short loc_140020FD3
0x140020fe6  test    r14, r14
0x140020fe9  jle     loc_1400210DA
0x140020fef  mov     rax, rva qword_14003E600[r12+r13*8]
0x140020ff7  movzx   ecx, byte ptr [rax+r15*8+3Eh]
0x140020ffd  movsx   r12d, byte ptr [rcx+r12+3CB40h]
0x140021006  inc     r12d
0x140021009  mov     eax, r12d
0x14002100c  sub     eax, edx
0x14002100e  mov     dword ptr [rbp+4Fh+var_A0], eax
0x140021011  mov     r8, [rbp+4Fh+var_B0]
0x140021015  sub     r8, rsi
0x140021018  movsxd  r9, eax
0x14002101b  cmp     r9, r8
0x14002101e  jg      loc_1400212B1
0x140021024  mov     rcx, rdi
0x140021027  lea     r8, cs:140000000h
0x14002102e  lea     rdx, ds:3Eh[r15*8]
0x140021036  add     rdx, rva qword_14003E600[r8+r11*8]
0x14002103e  mov     al, [rdx]
0x140021040  mov     [rbp+rcx+4Fh+var_50], al
0x140021044  inc     rcx
0x140021047  inc     rdx
0x14002104a  cmp     rcx, r14
0x14002104d  jl      short loc_14002103E
0x14002104f  test    r9, r9
0x140021052  jle     short loc_140021071
0x140021054  lea     rcx, [rbp+4Fh+var_50]
0x140021058  add     rcx, r14
0x14002105b  mov     r8, r9
0x14002105e  mov     rdx, rsi
0x140021061  call    sub_140029C50
0x140021066  mov     r10, [rbp+4Fh+var_A8]
0x14002106a  lea     r8, cs:140000000h
0x140021071  mov     rdx, rdi
0x140021074  lea     rcx, [rdx+r15*8]
0x140021078  mov     rax, rva qword_14003E600[r8+r13*8]
0x140021080  mov     [rcx+rax+3Eh], dil
0x140021085  inc     rdx
0x140021088  cmp     rdx, r14
0x14002108b  jl      short loc_140021074
0x14002108d  mov     [rbp+4Fh+var_80], rdi
0x140021091  lea     rax, [rbp+4Fh+var_50]
0x140021095  mov     [rbp+4Fh+var_78], rax
0x140021099  mov     eax, edi
0x14002109b  cmp     r12d, 4
0x14002109f  setz    al
0x1400210a2  inc     eax
0x1400210a4  mov     r12d, eax
0x1400210a7  mov     r8d, eax
0x1400210aa  mov     [rsp+100h+lpOverlapped], r10
0x1400210af  lea     r9, [rbp+4Fh+var_80]
0x1400210b3  lea     rdx, [rbp+4Fh+var_78]
0x1400210b7  lea     rcx, [rbp+4Fh+var_BC]
0x1400210bb  call    sub_14001AE8C
0x1400210c0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400210c4  jz      loc_14002133D
0x1400210ca  mov     eax, dword ptr [rbp+4Fh+var_A0]
0x1400210cd  dec     eax
0x1400210cf  movsxd  rcx, eax
0x1400210d2  add     rsi, rcx
0x1400210d5  jmp     loc_1400211DC
0x1400210da  movzx   eax, byte ptr [rsi]
0x1400210dd  movsx   r13, byte ptr [rax+r12+3CB40h]
0x1400210e6  lea     ecx, [r13+1]
0x1400210ea  mov     r9, [rbp+4Fh+var_B0]
0x1400210ee  sub     r9, rsi
0x1400210f1  movsxd  rax, ecx
0x1400210f4  cmp     rax, r9
0x1400210f7  jg      loc_1400212E7
0x1400210fd  mov     [rbp+4Fh+var_A0], rdi
0x140021101  mov     [rbp+4Fh+var_70], rsi
0x140021105  mov     eax, edi
0x140021107  cmp     ecx, 4
0x14002110a  setz    al
0x14002110d  inc     eax
0x14002110f  mov     r14d, eax
0x140021112  mov     r8d, eax
0x140021115  mov     [rsp+100h+lpOverlapped], r10
0x14002111a  lea     r9, [rbp+4Fh+var_A0]
0x14002111e  lea     rdx, [rbp+4Fh+var_70]
0x140021122  lea     rcx, [rbp+4Fh+var_BC]
0x140021126  call    sub_14001AE8C
0x14002112b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002112f  jz      loc_14002133D
0x140021135  add     rsi, r13
0x140021138  mov     r12d, r14d
0x14002113b  mov     r13, [rbp+4Fh+var_88]
0x14002113f  jmp     loc_1400211DC
0x140021144  lea     r11, cs:140000000h
0x14002114b  mov     r8, rva qword_14003E600[r11+r13*8]
0x140021153  mov     cl, [r8+r15*8+3Dh]
0x140021158  test    cl, 4
0x14002115b  jz      short loc_14002117E
0x14002115d  mov     al, [r8+r15*8+3Eh]
0x140021162  mov     [rbp+4Fh+var_48], al
0x140021165  mov     al, [rsi]
0x140021167  mov     [rbp+4Fh+var_47], al
0x14002116a  and     cl, 0FBh
0x14002116d  mov     [r8+r15*8+3Dh], cl
0x140021172  mov     r8d, 2
0x140021178  lea     rdx, [rbp+4Fh+var_48]
0x14002117c  jmp     short loc_1400211C7
0x14002117e  movzx   r9d, byte ptr [rsi]
0x140021182  mov     rax, [r10+18h]
0x140021186  mov     rcx, [rax]
0x140021189  cmp     [rcx+r9*2], di
0x14002118e  jge     short loc_1400211C1
0x140021190  lea     r14, [rsi+1]
0x140021194  cmp     r14, [rbp+4Fh+var_B0]
0x140021198  jnb     loc_14002131A
0x14002119e  mov     r9, r10
0x1400211a1  mov     r8d, 2
0x1400211a7  mov     rdx, rsi
0x1400211aa  lea     rcx, [rbp+4Fh+var_BC]
0x1400211ae  call    _mbtowc_internal
0x1400211b3  cmp     eax, 0FFFFFFFFh
0x1400211b6  jz      loc_14002133D
0x1400211bc  mov     rsi, r14
0x1400211bf  jmp     short loc_1400211DC
0x1400211c1  mov     r8, r12
0x1400211c4  mov     rdx, rsi
0x1400211c7  mov     r9, r10
0x1400211ca  lea     rcx, [rbp+4Fh+var_BC]
0x1400211ce  call    _mbtowc_internal
0x1400211d3  cmp     eax, 0FFFFFFFFh
0x1400211d6  jz      loc_14002133D
0x1400211dc  inc     rsi
0x1400211df  mov     [rsp+38h], rdi
0x1400211e4  mov     [rsp+100h+var_D0], rdi
0x1400211e9  mov     dword ptr [rsp+100h+var_D8], 5
0x1400211f1  lea     rax, [rbp+4Fh+Buffer]
0x1400211f5  mov     [rsp+100h+lpOverlapped], rax
0x1400211fa  mov     r9d, r12d
0x1400211fd  lea     r8, [rbp+4Fh+var_BC]
0x140021201  xor     edx, edx
0x140021203  mov     ecx, [rbp+4Fh+var_98]
0x140021206  call    __acrt_WideCharToMultiByte
0x14002120b  mov     r14d, eax
0x14002120e  test    eax, eax
0x140021210  jz      loc_14002133D
0x140021216  mov     [rbp+4Fh+NumberOfBytesWritten], edi
0x140021219  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x14002121e  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140021222  mov     r8d, eax; nNumberOfBytesToWrite
0x140021225  lea     rdx, [rbp+4Fh+Buffer]; lpBuffer
0x140021229  mov     r12, [rbp+4Fh+hFile]
0x14002122d  mov     rcx, r12; hFile
0x140021230  call    cs:WriteFile
0x140021236  test    eax, eax
0x140021238  jz      loc_140021335
0x14002123e  mov     edx, [rbx+8]
0x140021241  sub     edx, dword ptr [rbp+4Fh+var_90]
0x140021244  add     edx, esi
0x140021246  mov     [rbx+4], edx
0x140021249  cmp     [rbp+4Fh+NumberOfBytesWritten], r14d
0x14002124d  jb      loc_14002133D
0x140021253  cmp     byte ptr [rbp+4Fh+var_C0], 0Ah
0x140021257  jnz     short loc_140021297
0x140021259  mov     eax, 0Dh
0x14002125e  mov     [rbp+4Fh+var_C0], ax
0x140021262  mov     [rsp+100h+lpOverlapped], rdi; lpOverlapped
0x140021267  lea     r9, [rbp+4Fh+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14002126b  lea     r8d, [rax-0Ch]; nNumberOfBytesToWrite
0x14002126f  lea     rdx, [rbp+4Fh+var_C0]; lpBuffer
0x140021273  mov     rcx, r12; hFile
0x140021276  call    cs:WriteFile
0x14002127c  test    eax, eax
0x14002127e  jz      loc_140021335
0x140021284  cmp     [rbp+4Fh+NumberOfBytesWritten], 1
0x140021288  jb      loc_14002133D
0x14002128e  inc     dword ptr [rbx+8]
0x140021291  inc     dword ptr [rbx+4]
0x140021294  mov     edx, [rbx+4]
0x140021297  cmp     rsi, [rbp+4Fh+var_B0]
0x14002129b  jnb     loc_14002133D
0x1400212a1  mov     r10, [rbp+4Fh+var_A8]
0x1400212a5  mov     r11, [rbp+4Fh+var_60]
0x1400212a9  mov     ecx, [rbp+4Fh+var_94]
0x1400212ac  jmp     loc_140020F9D
0x1400212b1  test    r8, r8
0x1400212b4  jle     short loc_1400212E1
0x1400212b6  sub     rsi, r14
0x1400212b9  lea     r9, cs:140000000h
0x1400212c0  lea     rdx, [r14+r15*8]
0x1400212c4  mov     rcx, rva qword_14003E600[r9+r13*8]
0x1400212cc  mov     al, [rsi+r14]
0x1400212d0  mov     [rdx+rcx+3Eh], al
0x1400212d4  inc     edi
0x1400212d6  inc     r14
0x1400212d9  movsxd  rax, edi
0x1400212dc  cmp     rax, r8
0x1400212df  jl      short loc_1400212C0
0x1400212e1  add     [rbx+4], r8d
0x1400212e5  jmp     short loc_14002133D
0x1400212e7  test    r9, r9
0x1400212ea  jle     short loc_140021314
0x1400212ec  mov     r8, rdi
0x1400212ef  mov     r10, [rbp+4Fh+var_88]
0x1400212f3  lea     rdx, [r8+r15*8]
0x1400212f7  mov     rcx, rva qword_14003E600[r12+r10*8]
0x1400212ff  mov     al, [r8+rsi]
0x140021303  mov     [rdx+rcx+3Eh], al
0x140021307  inc     edi
0x140021309  inc     r8
0x14002130c  movsxd  rax, edi
0x14002130f  cmp     rax, r9
0x140021312  jl      short loc_1400212F3
0x140021314  add     [rbx+4], r9d
0x140021318  jmp     short loc_14002133D
0x14002131a  mov     [r8+r15*8+3Eh], r9b
0x14002131f  mov     rax, rva qword_14003E600[r11+r13*8]
0x140021327  or      byte ptr [rax+r15*8+3Dh], 4
0x14002132d  lea     eax, [rdx+1]
0x140021330  mov     [rbx+4], eax
0x140021333  jmp     short loc_14002133D
0x140021335  call    cs:GetLastError
0x14002133b  mov     [rbx], eax
0x14002133d  mov     rax, rbx
0x140021340  mov     rcx, [rbp+4Fh+var_38]
0x140021344  xor     rcx, rsp; StackCookie
0x140021347  call    __security_check_cookie
0x14002134c  mov     rbx, [rsp+100h+arg_0]
0x140021354  add     rsp, 0D0h
0x14002135b  pop     r15
0x14002135d  pop     r14
0x14002135f  pop     r13
0x140021361  pop     r12
  ... truncated ...
```

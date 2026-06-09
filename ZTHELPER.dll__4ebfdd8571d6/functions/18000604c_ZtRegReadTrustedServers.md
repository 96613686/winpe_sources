# ZtRegReadTrustedServers

- ea: `0x18000604c`
- end: `0x1800064a3`
- name: `ZtRegReadTrustedServers`
- size: `1111`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180006f9c`

## callees

- `0x1800014b0`
- `0x18000206a`
- `0x180005d90`
- `0x18000604c`
- `0x180009eac`
- `0x18000c750`
- `0x180012564`
- `0x1800125d4`
- `0x180015008`
- `0x180015618`
- `0x1800157fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800061fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800061fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006478`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006478`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180006294`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180006294`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18000618c`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x18000618c`

## pseudocode

```c
__int64 __fastcall ZtRegReadTrustedServers(__int64 a1, __int64 a2, unsigned int *a3, _QWORD *a4)
{
  DWORD v7; // r13d
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  char *v12; // rsi
  signed int v13; // ebx
  signed int v14; // eax
  LSTATUS v15; // eax
  unsigned int v16; // edi
  LSTATUS v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  __int128 *v21; // rax
  unsigned __int64 v22; // r14
  __int64 *v23; // rax
  unsigned __int64 v24; // r14
  __int64 v25; // rcx
  ULONG v26; // eax
  ULONG v27; // ebx
  unsigned __int64 v29; // [rsp+60h] [rbp-A0h]
  DWORD cSubKeys; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-94h] BYREF
  int v32; // [rsp+70h] [rbp-90h] BYREF
  int hKey[3]; // [rsp+74h] [rbp-8Ch] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v35[3]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v36[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v37[3]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Name[72]; // [rsp+100h] [rbp+0h] BYREF

  v7 = 0;
  memset_0(Name, 0, 0x82u);
  cSubKeys = 0;
  cchName = 0;
  v32 = 0;
  memset(hKey, 0, sizeof(hKey));
  memset_0(&v34, 0, 0x40u);
  memset_0(v36, 0, 0x40u);
  v12 = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qqqq(v10, v9, v11, a1, a2, a3, a4);
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        if ( a4 )
        {
          v13 = 0;
          v14 = RegOpenKeyExInternalW(a1, L"ZtTrustedServers", 0, 131097, &hKey[1], a2);
          if ( v14 != 2 )
          {
            v13 = v14 > 0 ? (unsigned __int16)v14 | 0x80070000 : v14;
            if ( v13 >= 0 )
            {
              v15 = RegQueryInfoKeyW(*(HKEY *)&hKey[1], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
              v13 = v15;
              if ( v15 > 0 )
                v13 = (unsigned __int16)v15 | 0x80070000;
              if ( v13 >= 0 && cSubKeys )
              {
                v29 = 2 * cSubKeys;
                v12 = (char *)Dns_Allocate((unsigned __int64)(unsigned int)v29 << 6);
                if ( v12 )
                {
                  v16 = 0;
                  v13 = 0;
                  if ( cSubKeys )
                  {
                    while ( 1 )
                    {
                      cchName = 65;
                      v17 = RegEnumKeyExW(*(HKEY *)&hKey[1], v7, Name, &cchName, 0, 0, 0, 0);
                      v13 = v17;
                      if ( v17 > 0 )
                        v13 = (unsigned __int16)v17 | 0x80070000;
                      if ( v13 < 0 )
                        break;
                      v18 = ZtReadTrustedServer(*(HKEY *)&hKey[1], Name, &v32, &v34, hKey, v36);
                      v13 = v18;
                      if ( v18 > 0 )
                        v13 = (unsigned __int16)v18 | 0x80070000;
                      if ( v13 < 0 )
                        break;
                      if ( v32 )
                      {
                        if ( v16 >= v29 )
                        {
                          v13 = -2147024809;
                          break;
                        }
                        v13 = 0;
                        if ( (xmmword_18001F260 & 4) != 0 )
                          WPP_SF__SOCKADDR_(v19, 74, v20, v35);
                        v21 = &v34;
                        v22 = (unsigned __int64)v16 << 6;
                        v19 = 64;
                        *(_OWORD *)&v12[v22] = v34;
                        *(_OWORD *)&v12[v22 + 16] = v35[0];
                        *(_OWORD *)&v12[v22 + 32] = v35[1];
                        *(_OWORD *)&v12[v22 + 48] = v35[2];
                        do
                        {
                          *(_BYTE *)v21 = 0;
                          v21 = (__int128 *)((char *)v21 + 1);
                          --v19;
                        }
                        while ( v19 );
                        ++v16;
                      }
                      if ( hKey[0] )
                      {
                        if ( v16 >= v29 )
                        {
                          v13 = -2147024809;
                          break;
                        }
                        v13 = 0;
                        if ( (xmmword_18001F260 & 4) != 0 )
                          WPP_SF__SOCKADDR_(v19, 75, v20, v37);
                        v23 = v36;
                        v24 = (unsigned __int64)v16 << 6;
                        v25 = 64;
                        *(_OWORD *)&v12[v24] = *(_OWORD *)v36;
                        *(_OWORD *)&v12[v24 + 16] = v37[0];
                        *(_OWORD *)&v12[v24 + 32] = v37[1];
                        *(_OWORD *)&v12[v24 + 48] = v37[2];
                        do
                        {
                          *(_BYTE *)v23 = 0;
                          v23 = (__int64 *)((char *)v23 + 1);
                          --v25;
                        }
                        while ( v25 );
                        ++v16;
                      }
                      if ( ++v7 >= cSubKeys )
                        goto LABEL_53;
                    }
                  }
                  else
                  {
LABEL_53:
                    *a4 = v12;
                    v12 = 0;
                    *a3 = v16;
                  }
                }
                else
                {
                  v13 = -2147024809;
                }
              }
            }
          }
        }
        else
        {
          v13 = -2147024809;
        }
      }
      else
      {
        v13 = -2147024809;
      }
    }
    else
    {
      v13 = -2147024809;
    }
  }
  else
  {
    v13 = -2147024809;
  }
  DnsFreeZtTrustedServerMembers((__int64)&v34);
  DnsFreeZtTrustedServerMembers((__int64)v36);
  Dns_Free(v12);
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    v26 = WX_WIN32_FROM_HR(v13);
    WPP_SF_d(1026, 0x4Cu, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v26);
  }
  v27 = WX_WIN32_FROM_HR(v13);
  if ( *(_QWORD *)&hKey[1] )
    RegCloseKey(*(HKEY *)&hKey[1]);
  return v27;
}

```

## disassembly

```asm
0x18000604c  push    rbp
0x18000604e  push    rbx
0x18000604f  push    rsi
0x180006050  push    rdi
0x180006051  push    r12
0x180006053  push    r13
0x180006055  push    r14
0x180006057  push    r15
0x180006059  lea     rbp, [rsp-0A8h]
0x180006061  sub     rsp, 1A8h
0x180006068  mov     rax, cs:__security_cookie
0x18000606f  xor     rax, rsp
0x180006072  mov     [rbp+0E0h+var_50], rax
0x180006079  mov     r15, r8
0x18000607c  mov     r14, rdx
0x18000607f  mov     rdi, rcx
0x180006082  xor     r13d, r13d
0x180006085  xor     edx, edx; Val
0x180006087  mov     [rsp+1E0h+var_17C], r13d
0x18000608c  mov     r8d, 82h; Size
0x180006092  mov     qword ptr [rsp+1E0h+hKey+4], r13
0x180006097  lea     rcx, [rbp+0E0h+Name]; void *
0x18000609b  mov     r12, r9
0x18000609e  call    memset_0
0x1800060a3  lea     ebx, [r13+40h]
0x1800060a7  mov     [rsp+1E0h+cSubKeys], r13d
0x1800060ac  mov     r8d, ebx; Size
0x1800060af  mov     [rsp+1E0h+cchName], r13d
0x1800060b4  xor     edx, edx; Val
0x1800060b6  mov     [rsp+1E0h+var_170], r13d
0x1800060bb  lea     rcx, [rbp+0E0h+var_160]; void *
0x1800060bf  mov     dword ptr [rsp+1E0h+hKey], r13d
0x1800060c4  call    memset_0
0x1800060c9  mov     r8d, ebx; Size
0x1800060cc  lea     rcx, [rbp+0E0h+var_120]; void *
0x1800060d0  xor     edx, edx; Val
0x1800060d2  call    memset_0
0x1800060d7  mov     esi, r13d
0x1800060da  test    byte ptr cs:xmmword_18001F260, 4
0x1800060e1  jz      short loc_1800060FA
0x1800060e3  mov     [rsp+1E0h+lpcbMaxClassLen], r12
0x1800060e8  mov     r9, rdi
0x1800060eb  mov     [rsp+1E0h+lpcbMaxSubKeyLen], r15
0x1800060f0  mov     [rsp+1E0h+lpcSubKeys], r14
0x1800060f5  call    WPP_SF_qqqq
0x1800060fa  test    r15, r15
0x1800060fd  jz      short loc_180006102
0x1800060ff  mov     [r15], r13d
0x180006102  test    r12, r12
0x180006105  jz      short loc_18000610B
0x180006107  mov     [r12], r13
0x18000610b  test    rdi, rdi
0x18000610e  jnz     short loc_180006122
0x180006110  mov     ebx, 80070057h
0x180006115  mov     [rsp+1E0h+var_17C], 3DEh
0x18000611d  jmp     loc_180006422
0x180006122  test    r14, r14
0x180006125  jnz     short loc_180006139
0x180006127  mov     ebx, 80070057h
0x18000612c  mov     [rsp+1E0h+var_17C], 3DFh
0x180006134  jmp     loc_180006422
0x180006139  test    r15, r15
0x18000613c  jnz     short loc_180006150
0x18000613e  mov     ebx, 80070057h
0x180006143  mov     [rsp+1E0h+var_17C], 3E0h
0x18000614b  jmp     loc_180006422
0x180006150  test    r12, r12
0x180006153  jnz     short loc_180006167
0x180006155  mov     ebx, 80070057h
0x18000615a  mov     [rsp+1E0h+var_17C], 3E1h
0x180006162  jmp     loc_180006422
0x180006167  lea     rax, [rsp+1E0h+hKey+4]
0x18000616c  mov     [rsp+1E0h+lpcbMaxSubKeyLen], r14
0x180006171  mov     r9d, 20019h
0x180006177  mov     [rsp+1E0h+lpcSubKeys], rax
0x18000617c  xor     r8d, r8d
0x18000617f  lea     rdx, aZttrustedserve; "ZtTrustedServers"
0x180006186  mov     rcx, rdi
0x180006189  mov     ebx, r13d
0x18000618c  call    cs:__imp_RegOpenKeyExInternalW
0x180006192  cmp     eax, 2
0x180006195  jz      loc_180006422
0x18000619b  mov     r14d, 80070000h
0x1800061a1  test    eax, eax
0x1800061a3  jg      short loc_1800061A9
0x1800061a5  mov     ebx, eax
0x1800061a7  jmp     short loc_1800061AF
0x1800061a9  movzx   ebx, ax
0x1800061ac  or      ebx, r14d
0x1800061af  test    ebx, ebx
0x1800061b1  jns     short loc_1800061C0
0x1800061b3  mov     [rsp+1E0h+var_17C], 3EEh
0x1800061bb  jmp     loc_180006422
0x1800061c0  mov     rcx, qword ptr [rsp+1E0h+hKey+4]; hKey
0x1800061c5  lea     rax, [rsp+1E0h+cSubKeys]
0x1800061ca  mov     [rsp+1E0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800061cf  xor     r9d, r9d; lpReserved
0x1800061d2  mov     [rsp+1E0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800061d7  xor     r8d, r8d; lpcchClass
0x1800061da  mov     [rsp+1E0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1800061df  xor     edx, edx; lpClass
0x1800061e1  mov     [rsp+1E0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1800061e6  mov     [rsp+1E0h+lpcValues], r13; lpcValues
0x1800061eb  mov     [rsp+1E0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800061f0  mov     [rsp+1E0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1800061f5  mov     [rsp+1E0h+lpcSubKeys], rax; lpcSubKeys
0x1800061fa  call    cs:__imp_RegQueryInfoKeyW
0x180006200  mov     ebx, eax
0x180006202  test    eax, eax
0x180006204  jle     short loc_18000620C
0x180006206  movzx   ebx, ax
0x180006209  or      ebx, r14d
0x18000620c  test    ebx, ebx
0x18000620e  jns     short loc_18000621D
0x180006210  mov     [rsp+1E0h+var_17C], 3FFh
0x180006218  jmp     loc_180006422
0x18000621d  mov     eax, [rsp+1E0h+cSubKeys]
0x180006221  test    eax, eax
0x180006223  jz      loc_180006422
0x180006229  add     eax, eax
0x18000622b  mov     ecx, eax
0x18000622d  mov     [rsp+60h], rax
0x180006232  shl     rcx, 6
0x180006236  call    Dns_Allocate
0x18000623b  mov     rsi, rax
0x18000623e  test    rax, rax
0x180006241  jnz     short loc_180006255
0x180006243  mov     ebx, 80070057h
0x180006248  mov     [rsp+1E0h+var_17C], 410h
0x180006250  jmp     loc_180006422
0x180006255  xor     edx, edx
0x180006257  mov     edi, r13d
0x18000625a  mov     ebx, r13d
0x18000625d  cmp     [rsp+1E0h+cSubKeys], edx
0x180006261  jbe     loc_180006415
0x180006267  mov     rcx, qword ptr [rsp+1E0h+hKey+4]; hKey
0x18000626c  lea     r9, [rsp+1E0h+cchName]; lpcchName
0x180006271  mov     [rsp+1E0h+lpcValues], rdx; lpftLastWriteTime
0x180006276  lea     r8, [rbp+0E0h+Name]; lpName
0x18000627a  mov     [rsp+1E0h+lpcbMaxClassLen], rdx; lpcchClass
0x18000627f  mov     [rsp+1E0h+lpcbMaxSubKeyLen], rdx; lpClass
0x180006284  mov     [rsp+1E0h+lpcSubKeys], rdx; lpReserved
0x180006289  mov     edx, r13d; dwIndex
0x18000628c  mov     [rsp+1E0h+cchName], 41h ; 'A'
0x180006294  call    cs:__imp_RegEnumKeyExW
0x18000629a  mov     ebx, eax
0x18000629c  test    eax, eax
0x18000629e  jle     short loc_1800062A6
0x1800062a0  movzx   ebx, ax
0x1800062a3  or      ebx, r14d
0x1800062a6  test    ebx, ebx
0x1800062a8  js      loc_18000640B
0x1800062ae  mov     rcx, qword ptr [rsp+1E0h+hKey+4]; hKey
0x1800062b3  lea     rax, [rbp+0E0h+var_120]
0x1800062b7  mov     [rsp+1E0h+lpcbMaxSubKeyLen], rax; __int64
0x1800062bc  lea     r9, [rbp+0E0h+var_160]
0x1800062c0  lea     rax, [rsp+1E0h+hKey]
0x1800062c5  lea     r8, [rsp+1E0h+var_170]
0x1800062ca  mov     [rsp+1E0h+lpcSubKeys], rax; __int64
0x1800062cf  lea     rdx, [rbp+0E0h+Name]; lpSubKey
0x1800062d3  call    ZtReadTrustedServer
0x1800062d8  xor     edx, edx
0x1800062da  mov     ebx, eax
0x1800062dc  test    eax, eax
0x1800062de  jle     short loc_1800062E6
0x1800062e0  movzx   ebx, ax
0x1800062e3  or      ebx, r14d
0x1800062e6  test    ebx, ebx
0x1800062e8  js      loc_180006401
0x1800062ee  cmp     [rsp+1E0h+var_170], edx
0x1800062f2  jz      short loc_18000635E
0x1800062f4  mov     r14d, edi
0x1800062f7  cmp     r14, [rsp+60h]
0x1800062fc  jnb     loc_1800063E3
0x180006302  mov     ebx, edx
0x180006304  test    byte ptr cs:xmmword_18001F260, 4
0x18000630b  jz      short loc_18000631D
0x18000630d  mov     edx, 4Ah ; 'J'
0x180006312  lea     r9, [rbp+0E0h+var_150]
0x180006316  call    WPP_SF__SOCKADDR_
0x18000631b  xor     edx, edx
0x18000631d  movaps  xmm0, [rbp+0E0h+var_160]
0x180006321  lea     rax, [rbp+0E0h+var_160]
0x180006325  shl     r14, 6
0x180006329  mov     ecx, 40h ; '@'
0x18000632e  movups  xmmword ptr [r14+rsi], xmm0
0x180006333  movaps  xmm1, [rbp+0E0h+var_150]
0x180006337  movups  xmmword ptr [r14+rsi+10h], xmm1
0x18000633d  movaps  xmm0, [rbp+0E0h+var_140]
0x180006341  movups  xmmword ptr [r14+rsi+20h], xmm0
0x180006347  movaps  xmm1, [rbp+0E0h+var_130]
0x18000634b  movups  xmmword ptr [r14+rsi+30h], xmm1
0x180006351  mov     [rax], dl
0x180006353  inc     rax
0x180006356  sub     rcx, 1
0x18000635a  jnz     short loc_180006351
0x18000635c  inc     edi
0x18000635e  cmp     dword ptr [rsp+1E0h+hKey], edx
0x180006362  jz      short loc_1800063CE
0x180006364  mov     r14d, edi
0x180006367  cmp     r14, [rsp+60h]
0x18000636c  jnb     loc_1800063F2
0x180006372  mov     ebx, edx
0x180006374  test    byte ptr cs:xmmword_18001F260, 4
0x18000637b  jz      short loc_18000638D
0x18000637d  mov     edx, 4Bh ; 'K'
0x180006382  lea     r9, [rbp+0E0h+var_110]
0x180006386  call    WPP_SF__SOCKADDR_
0x18000638b  xor     edx, edx
0x18000638d  movaps  xmm0, xmmword ptr [rbp+0E0h+var_120]
0x180006391  lea     rax, [rbp+0E0h+var_120]
0x180006395  shl     r14, 6
0x180006399  mov     ecx, 40h ; '@'
0x18000639e  movups  xmmword ptr [r14+rsi], xmm0
0x1800063a3  movaps  xmm1, [rbp+0E0h+var_110]
0x1800063a7  movups  xmmword ptr [r14+rsi+10h], xmm1
0x1800063ad  movaps  xmm0, [rbp+0E0h+var_100]
0x1800063b1  movups  xmmword ptr [r14+rsi+20h], xmm0
0x1800063b7  movaps  xmm1, [rbp+0E0h+var_F0]
0x1800063bb  movups  xmmword ptr [r14+rsi+30h], xmm1
0x1800063c1  mov     [rax], dl
0x1800063c3  inc     rax
0x1800063c6  sub     rcx, 1
0x1800063ca  jnz     short loc_1800063C1
0x1800063cc  inc     edi
0x1800063ce  inc     r13d
0x1800063d1  cmp     r13d, [rsp+1E0h+cSubKeys]
0x1800063d6  jnb     short loc_180006415
0x1800063d8  mov     r14d, 80070000h
0x1800063de  jmp     loc_180006267
0x1800063e3  mov     ebx, 80070057h
0x1800063e8  mov     [rsp+1E0h+var_17C], 435h
0x1800063f0  jmp     short loc_180006422
0x1800063f2  mov     ebx, 80070057h
0x1800063f7  mov     [rsp+1E0h+var_17C], 440h
0x1800063ff  jmp     short loc_180006422
0x180006401  mov     [rsp+1E0h+var_17C], 42Dh
0x180006409  jmp     short loc_180006422
0x18000640b  mov     [rsp+1E0h+var_17C], 422h
0x180006413  jmp     short loc_180006422
0x180006415  mov     [r12], rsi
0x180006419  xor     r13d, r13d
0x18000641c  mov     esi, r13d
0x18000641f  mov     [r15], edi
0x180006422  lea     rcx, [rbp+0E0h+var_160]
0x180006426  call    DnsFreeZtTrustedServerMembers
0x18000642b  lea     rcx, [rbp+0E0h+var_120]
0x18000642f  call    DnsFreeZtTrustedServerMembers
0x180006434  mov     rcx, rsi; lpMem
0x180006437  call    Dns_Free
0x18000643c  test    byte ptr cs:xmmword_18001F260, 4
0x180006443  jz      short loc_180006465
0x180006445  mov     ecx, ebx
0x180006447  call    WX_WIN32_FROM_HR
0x18000644c  mov     r9d, eax
0x18000644f  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180006456  mov     edx, 4Ch ; 'L'
0x18000645b  mov     ecx, 402h
0x180006460  call    WPP_SF_d
0x180006465  mov     ecx, ebx
0x180006467  call    WX_WIN32_FROM_HR
0x18000646c  mov     rcx, qword ptr [rsp+1E0h+hKey+4]; hKey
0x180006471  mov     ebx, eax
0x180006473  test    rcx, rcx
0x180006476  jz      short loc_18000647E
0x180006478  call    cs:__imp_RegCloseKey
0x18000647e  mov     eax, ebx
0x180006480  mov     rcx, [rbp+0E0h+var_50]
0x180006487  xor     rcx, rsp; StackCookie
0x18000648a  call    __security_check_cookie
0x18000648f  add     rsp, 1A8h
0x180006496  pop     r15
0x180006498  pop     r14
0x18000649a  pop     r13
0x18000649c  pop     r12
0x18000649e  pop     rdi
0x18000649f  pop     rsi
0x1800064a0  pop     rbx
0x1800064a1  pop     rbp
0x1800064a2  retn
```

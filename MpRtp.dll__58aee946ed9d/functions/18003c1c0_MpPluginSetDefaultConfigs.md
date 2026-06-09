# MpPluginSetDefaultConfigs

- ea: `0x18003c1c0`
- end: `0x18003c6af`
- name: `MpPluginSetDefaultConfigs`
- size: `1263`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callees

- `0x1800115a0`
- `0x180011990`
- `0x1800119f0`
- `0x180011a60`
- `0x180011c24`
- `0x18003a1e8`
- `0x18003a39c`
- `0x18003a424`
- `0x18003c1c0`
- `0x18003d7ac`
- `0x18003d810`
- `0x18003d86c`
- `0x1800767e0`
- `0x180077138`
- `0x180086494`
- `0x18009c84c`
- `0x18009cc20`
- `0x1800ae318`
- `0x1800d4220`

## import_xrefs

- `ADVAPI32!RegDeleteKeyValueW` at `0x18003c4f3`
- `ADVAPI32!RegDeleteKeyValueW` at `0x18003c4f3`

## pseudocode

```c
__int64 __fastcall MpPluginSetDefaultConfigs(int a1)
{
  _QWORD *v2; // rdi
  int v3; // eax
  unsigned int v4; // edi
  __int64 v5; // rcx
  int v6; // r15d
  int v7; // eax
  __int64 **v8; // r13
  int v9; // r14d
  __int64 *v10; // rax
  __int64 *v11; // rsi
  volatile signed __int32 *v12; // rdi
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 *v15; // rcx
  LPCWSTR *v16; // rax
  _QWORD *v17; // rax
  __int64 *v18; // r9
  const WCHAR *v19; // r14
  const WCHAR *v20; // r8
  const WCHAR *v21; // rdx
  LSTATUS v22; // eax
  __int128 *v23; // rax
  bool v24; // cc
  const WCHAR *v25; // rax
  __int64 *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // r8
  __int64 v29; // [rsp+38h] [rbp-99h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-91h] BYREF
  __int64 **v31; // [rsp+48h] [rbp-89h]
  _QWORD v32[2]; // [rsp+50h] [rbp-81h] BYREF
  _QWORD v33[2]; // [rsp+60h] [rbp-71h] BYREF
  _QWORD v34[2]; // [rsp+70h] [rbp-61h] BYREF
  _QWORD v35[2]; // [rsp+80h] [rbp-51h] BYREF
  _QWORD v36[2]; // [rsp+90h] [rbp-41h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-21h]
  unsigned __int64 v39; // [rsp+B8h] [rbp-19h]
  __int128 v40; // [rsp+C0h] [rbp-11h] BYREF
  __int64 v41; // [rsp+D0h] [rbp-1h]
  unsigned __int64 v42; // [rsp+D8h] [rbp+7h]
  __int128 v43; // [rsp+E0h] [rbp+Fh] BYREF
  __int64 v44; // [rsp+F0h] [rbp+1Fh]

  LODWORD(v29) = a1;
  if ( !a1 )
    return 2147942487LL;
  v2 = (_QWORD *)*((_QWORD *)lpMem + 7);
  if ( !v2 )
    return 2147500037LL;
  sub_180011C24(*v2, 480, 0);
  v44 = 0;
  v43 = 0;
  v3 = sub_1800AE318(v2, &v29, &v43);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = (unsigned int)TlsIndex;
    if ( dword_1801200A8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)TlsIndex)
                                     + 4LL) )
    {
      sub_180011A60(&dword_1801200A8);
      if ( dword_1801200A8 == -1 )
      {
        sub_1800767E0(qword_1801200B0);
        atexit(sub_1800DA050);
        sub_1800119F0(&dword_1801200A8);
      }
    }
    v6 = 0;
    v7 = sub_180086494(v5, 86);
    v8 = (__int64 **)v43;
    v9 = v7;
    LODWORD(v29) = v7;
    v31 = (__int64 **)*((_QWORD *)&v43 + 1);
    if ( (_QWORD)v43 == *((_QWORD *)&v43 + 1) )
    {
LABEL_71:
      sub_18003A1E8(&v43);
      return v6 != 0 ? 0x80004005 : 0;
    }
    while ( 1 )
    {
      v10 = v8[1];
      if ( v10 )
        _InterlockedIncrement((volatile signed __int32 *)v10 + 2);
      v11 = *v8;
      v12 = (volatile signed __int32 *)v8[1];
      hKey = 0;
      *(_OWORD *)lpSubKey = 0;
      LOWORD(lpSubKey[0]) = 0;
      v38 = 0;
      v39 = 7;
      if ( (unsigned __int8)sub_180077138(qword_1801200B0, v11, &hKey, lpSubKey) )
      {
        if ( v11[6] )
        {
          v41 = 0;
          v42 = 7;
          v40 = 0;
          LOWORD(v40) = 0;
          if ( !v9 )
          {
            v15 = v11 + 4;
            if ( (unsigned __int64)v11[7] > 7 )
              v15 = (__int64 *)v11[4];
            v32[1] = v11[6];
            v32[0] = v15;
            v16 = lpSubKey;
            if ( v39 > 7 )
              v16 = (LPCWSTR *)lpSubKey[0];
            v33[0] = v16;
            v33[1] = v38;
            if ( (int)sub_18009C84C(hKey, v33, v32, &v40) < 0 )
              sub_18003A424(&v40, L"N/A", 3);
          }
          if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 2) != 0 )
          {
            v17 = v11 + 4;
            if ( (unsigned __int64)v11[7] > 7 )
              v17 = (_QWORD *)*v17;
            LODWORD(v18) = (_DWORD)v11;
            if ( (unsigned __int64)v11[3] > 7 )
              v18 = (__int64 *)*v11;
            sub_18003D86C(*((_QWORD *)off_180119DF0 + 2), 35, (unsigned int)&MessageGuid, (_DWORD)v18, (__int64)v17);
          }
          v19 = (const WCHAR *)(v11 + 4);
          v20 = (const WCHAR *)(v11 + 4);
          if ( (unsigned __int64)v11[7] > 7 )
            v20 = *(const WCHAR **)v19;
          v21 = (const WCHAR *)lpSubKey;
          if ( v39 > 7 )
            v21 = lpSubKey[0];
          v22 = RegDeleteKeyValueW(hKey, v21, v20);
          if ( v22 )
          {
            if ( v22 != 2 )
            {
              ++v6;
              if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
              {
                if ( (unsigned __int64)v11[7] > 7 )
                  v19 = *(const WCHAR **)v19;
                if ( (unsigned __int64)v11[3] > 7 )
                  v11 = (__int64 *)*v11;
                sub_18003D86C(*((_QWORD *)off_180119DF0 + 2), 36, (unsigned int)&MessageGuid, (_DWORD)v11, (__int64)v19);
              }
            }
          }
          else if ( !(_DWORD)v29 )
          {
            v23 = &v40;
            if ( v42 > 7 )
              v23 = (__int128 *)v40;
            v24 = (unsigned __int64)v11[7] <= 7;
            v34[0] = v23;
            v34[1] = v41;
            v25 = (const WCHAR *)(v11 + 4);
            if ( !v24 )
              v25 = *(const WCHAR **)v19;
            v24 = (unsigned __int64)v11[12] <= 7;
            v26 = v11 + 9;
            v35[0] = v25;
            v35[1] = v11[6];
            if ( !v24 )
              v26 = (__int64 *)v11[9];
            v27 = v11[11];
            v28 = *((unsigned int *)v11 + 17);
            v36[0] = v26;
            v36[1] = v27;
            sub_18009CC20(v36, v35, v28, v34);
          }
          sub_18003A39C(&v40);
          sub_18003A39C(lpSubKey);
          if ( v12 )
          {
            if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
              if ( !_InterlockedDecrement(v12 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
            }
          }
          v9 = v29;
          goto LABEL_70;
        }
        ++v6;
        v13 = off_180119DF0;
        if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 2) != 0 )
        {
          if ( (unsigned __int64)v11[3] > 7 )
            v11 = (__int64 *)*v11;
          v14 = 34;
          goto LABEL_19;
        }
      }
      else
      {
        ++v6;
        v13 = off_180119DF0;
        if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
        {
          if ( (unsigned __int64)v11[3] > 7 )
            v11 = (__int64 *)*v11;
          v14 = 33;
LABEL_19:
          sub_18003D810(v13[2], v14, &MessageGuid, v11);
        }
      }
      sub_18003A39C(lpSubKey);
      if ( v12 )
      {
        if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( !_InterlockedDecrement(v12 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
LABEL_70:
      v8 += 2;
      if ( v8 == v31 )
        goto LABEL_71;
    }
  }
  if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
    sub_18003D7AC(*((_QWORD *)off_180119DF0 + 2), 32, &MessageGuid, (unsigned int)v29, v3);
  sub_18003A1E8(&v43);
  return v4;
}

```

## disassembly

```asm
0x18003c1c0  mov     rax, rsp
0x18003c1c3  mov     [rax+10h], rbx
0x18003c1c7  mov     [rax+18h], rsi
0x18003c1cb  mov     [rax+20h], rdi
0x18003c1cf  push    rbp
0x18003c1d0  push    r12
0x18003c1d2  push    r13
0x18003c1d4  push    r14
0x18003c1d6  push    r15
0x18003c1d8  lea     rbp, [rax-5Fh]
0x18003c1dc  sub     rsp, 100h
0x18003c1e3  mov     rax, cs:__security_cookie
0x18003c1ea  xor     rax, rsp
0x18003c1ed  mov     [rbp+57h+var_30], rax
0x18003c1f1  xor     ebx, ebx
0x18003c1f3  mov     dword ptr [rsp+120h+var_F0], ecx
0x18003c1f7  test    ecx, ecx
0x18003c1f9  jnz     short loc_18003C205
0x18003c1fb  mov     eax, 80070057h
0x18003c200  jmp     loc_18003C641
0x18003c205  mov     rax, cs:lpMem
0x18003c20c  mov     rdi, [rax+38h]
0x18003c210  test    rdi, rdi
0x18003c213  jz      loc_18003C63C
0x18003c219  mov     rcx, [rdi]
0x18003c21c  xor     r8d, r8d
0x18003c21f  mov     edx, 1E0h
0x18003c224  call    sub_180011C24
0x18003c229  test    rdi, rdi
0x18003c22c  jz      loc_18003C63C
0x18003c232  xorps   xmm0, xmm0
0x18003c235  mov     [rbp+57h+var_38], rbx
0x18003c239  lea     r8, [rbp+57h+var_48]
0x18003c23d  mov     rcx, rdi
0x18003c240  lea     rdx, [rsp+120h+var_F0]
0x18003c245  movdqu  [rbp+57h+var_48], xmm0
0x18003c24a  call    sub_1800AE318
0x18003c24f  mov     edi, eax
0x18003c251  test    eax, eax
0x18003c253  jns     short loc_18003C29C
0x18003c255  mov     rcx, cs:off_180119DF0
0x18003c25c  lea     r12, off_180119DF0
0x18003c263  cmp     rcx, r12
0x18003c266  jz      short loc_18003C28C
0x18003c268  test    byte ptr [rcx+1Ch], 1
0x18003c26c  jz      short loc_18003C28C
0x18003c26e  mov     r9d, dword ptr [rsp+120h+var_F0]
0x18003c273  lea     r8, MessageGuid
0x18003c27a  mov     rcx, [rcx+10h]
0x18003c27e  mov     edx, 20h ; ' '
0x18003c283  mov     dword ptr [rsp+120h+var_100], eax
0x18003c287  call    sub_18003D7AC
0x18003c28c  lea     rcx, [rbp+57h+var_48]
0x18003c290  call    sub_18003A1E8
0x18003c295  mov     eax, edi
0x18003c297  jmp     loc_18003C641
0x18003c29c  mov     ecx, cs:TlsIndex
0x18003c2a2  or      esi, 0FFFFFFFFh
0x18003c2a5  mov     rax, gs:58h
0x18003c2ae  mov     edx, 4
0x18003c2b3  mov     rax, [rax+rcx*8]
0x18003c2b7  mov     eax, [rdx+rax]
0x18003c2ba  cmp     cs:dword_1801200A8, eax
0x18003c2c0  jg      loc_18003C66E
0x18003c2c6  mov     edx, 56h ; 'V'
0x18003c2cb  mov     r15d, ebx
0x18003c2ce  call    sub_180086494
0x18003c2d3  mov     r13, qword ptr [rbp+57h+var_48]
0x18003c2d7  mov     r14d, eax
0x18003c2da  mov     dword ptr [rsp+120h+var_F0], eax
0x18003c2de  mov     rax, qword ptr [rbp+57h+var_48+8]
0x18003c2e2  mov     [rsp+120h+var_E0], rax
0x18003c2e7  cmp     r13, rax
0x18003c2ea  jz      loc_18003C622
0x18003c2f0  lea     r12, off_180119DF0
0x18003c2f7  mov     rax, [r13+8]
0x18003c2fb  test    rax, rax
0x18003c2fe  jz      short loc_18003C304
0x18003c300  lock inc dword ptr [rax+8]
0x18003c304  mov     rsi, [r13+0]
0x18003c308  lea     r9, [rbp+57h+lpSubKey]
0x18003c30c  mov     rdi, [r13+8]
0x18003c310  lea     r8, [rsp+120h+hKey]
0x18003c315  xorps   xmm0, xmm0
0x18003c318  mov     [rsp+120h+hKey], rbx
0x18003c31d  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18003c321  mov     rdx, rsi
0x18003c324  mov     word ptr [rbp+57h+lpSubKey], bx
0x18003c328  lea     rcx, qword_1801200B0
0x18003c32f  mov     [rbp+57h+var_78], rbx
0x18003c333  mov     [rbp+57h+var_70], 7
0x18003c33b  call    sub_180077138
0x18003c340  test    al, al
0x18003c342  jnz     loc_18003C3D6
0x18003c348  inc     r15d
0x18003c34b  mov     rcx, cs:off_180119DF0
0x18003c352  cmp     rcx, r12
0x18003c355  jz      short loc_18003C37F
0x18003c357  test    byte ptr [rcx+1Ch], 1
0x18003c35b  jz      short loc_18003C37F
0x18003c35d  cmp     qword ptr [rsi+18h], 7
0x18003c362  jbe     short loc_18003C367
0x18003c364  mov     rsi, [rsi]
0x18003c367  mov     edx, 21h ; '!'
0x18003c36c  mov     rcx, [rcx+10h]
0x18003c370  lea     r8, MessageGuid
0x18003c377  mov     r9, rsi
0x18003c37a  call    sub_18003D810
0x18003c37f  lea     rcx, [rbp+57h+lpSubKey]
0x18003c383  call    sub_18003A39C
0x18003c388  test    rdi, rdi
0x18003c38b  jz      loc_18003C613
0x18003c391  or      esi, 0FFFFFFFFh
0x18003c394  mov     eax, esi
0x18003c396  lock xadd [rdi+8], eax
0x18003c39b  add     eax, esi
0x18003c39d  jnz     loc_18003C613
0x18003c3a3  mov     rax, [rdi]
0x18003c3a6  mov     rcx, rdi
0x18003c3a9  mov     rax, [rax]
0x18003c3ac  call    cs:__guard_dispatch_icall_fptr
0x18003c3b2  mov     eax, esi
0x18003c3b4  lock xadd [rdi+0Ch], eax
0x18003c3b9  add     eax, esi
0x18003c3bb  jnz     loc_18003C613
0x18003c3c1  mov     rax, [rdi]
0x18003c3c4  mov     rcx, rdi
0x18003c3c7  mov     rax, [rax+8]
0x18003c3cb  call    cs:__guard_dispatch_icall_fptr
0x18003c3d1  jmp     loc_18003C613
0x18003c3d6  cmp     [rsi+30h], rbx
0x18003c3da  jnz     short loc_18003C405
0x18003c3dc  inc     r15d
0x18003c3df  mov     rcx, cs:off_180119DF0
0x18003c3e6  cmp     rcx, r12
0x18003c3e9  jz      short loc_18003C37F
0x18003c3eb  test    byte ptr [rcx+1Ch], 2
0x18003c3ef  jz      short loc_18003C37F
0x18003c3f1  cmp     qword ptr [rsi+18h], 7
0x18003c3f6  jbe     short loc_18003C3FB
0x18003c3f8  mov     rsi, [rsi]
0x18003c3fb  mov     edx, 22h ; '"'
0x18003c400  jmp     loc_18003C36C
0x18003c405  mov     [rbp+57h+var_58], rbx
0x18003c409  xorps   xmm0, xmm0
0x18003c40c  mov     [rbp+57h+var_50], 7
0x18003c414  movups  [rbp+57h+var_68], xmm0
0x18003c418  mov     word ptr [rbp+57h+var_68], bx
0x18003c41c  test    r14d, r14d
0x18003c41f  jnz     short loc_18003C488
0x18003c421  cmp     qword ptr [rsi+38h], 7
0x18003c426  lea     rcx, [rsi+20h]
0x18003c42a  jbe     short loc_18003C430
0x18003c42c  mov     rcx, [rsi+20h]
0x18003c430  mov     rax, [rsi+30h]
0x18003c434  lea     r9, [rbp+57h+var_68]
0x18003c438  cmp     [rbp+57h+var_70], 7
0x18003c43d  lea     r8, [rsp+120h+var_D8]
0x18003c442  mov     [rbp+57h+var_D0], rax
0x18003c446  lea     rdx, [rbp+57h+var_C8]
0x18003c44a  mov     [rsp+120h+var_D8], rcx
0x18003c44f  lea     rax, [rbp+57h+lpSubKey]
0x18003c453  cmova   rax, [rbp+57h+lpSubKey]
0x18003c458  mov     rcx, [rsp+120h+hKey]
0x18003c45d  mov     [rbp+57h+var_C8], rax
0x18003c461  mov     rax, [rbp+57h+var_78]
0x18003c465  mov     [rbp+57h+var_C0], rax
0x18003c469  call    sub_18009C84C
0x18003c46e  test    eax, eax
0x18003c470  jns     short loc_18003C488
0x18003c472  mov     r8d, 3
0x18003c478  lea     rdx, aNA; "N/A"
0x18003c47f  lea     rcx, [rbp+57h+var_68]
0x18003c483  call    sub_18003A424
0x18003c488  mov     rcx, cs:off_180119DF0
0x18003c48f  cmp     rcx, r12
0x18003c492  jz      short loc_18003C4CF
0x18003c494  test    byte ptr [rcx+1Ch], 2
0x18003c498  jz      short loc_18003C4CF
0x18003c49a  lea     rax, [rsi+20h]
0x18003c49e  cmp     qword ptr [rax+18h], 7
0x18003c4a3  jbe     short loc_18003C4A8
0x18003c4a5  mov     rax, [rax]
0x18003c4a8  cmp     qword ptr [rsi+18h], 7
0x18003c4ad  mov     r9, rsi
0x18003c4b0  jbe     short loc_18003C4B5
0x18003c4b2  mov     r9, [rsi]
0x18003c4b5  mov     rcx, [rcx+10h]
0x18003c4b9  lea     r8, MessageGuid
0x18003c4c0  mov     edx, 23h ; '#'
0x18003c4c5  mov     [rsp+120h+var_100], rax
0x18003c4ca  call    sub_18003D86C
0x18003c4cf  lea     r14, [rsi+20h]
0x18003c4d3  cmp     qword ptr [r14+18h], 7
0x18003c4d8  mov     r8, r14
0x18003c4db  jbe     short loc_18003C4E0
0x18003c4dd  mov     r8, [r14]; lpValueName
0x18003c4e0  cmp     [rbp+57h+var_70], 7
0x18003c4e5  lea     rdx, [rbp+57h+lpSubKey]
0x18003c4e9  mov     rcx, [rsp+120h+hKey]; hKey
0x18003c4ee  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18003c4f3  call    cs:RegDeleteKeyValueW
0x18003c4f9  test    eax, eax
0x18003c4fb  jz      short loc_18003C556
0x18003c4fd  cmp     eax, 2
0x18003c500  jz      loc_18003C5BF
0x18003c506  inc     r15d
0x18003c509  mov     rcx, cs:off_180119DF0
0x18003c510  cmp     rcx, r12
0x18003c513  jz      loc_18003C5BF
0x18003c519  test    byte ptr [rcx+1Ch], 1
0x18003c51d  jz      loc_18003C5BF
0x18003c523  cmp     qword ptr [r14+18h], 7
0x18003c528  jbe     short loc_18003C52D
0x18003c52a  mov     r14, [r14]
0x18003c52d  cmp     qword ptr [rsi+18h], 7
0x18003c532  jbe     short loc_18003C537
0x18003c534  mov     rsi, [rsi]
0x18003c537  mov     rcx, [rcx+10h]
0x18003c53b  lea     r8, MessageGuid
0x18003c542  mov     edx, 24h ; '$'
0x18003c547  mov     [rsp+120h+var_100], r14
0x18003c54c  mov     r9, rsi
0x18003c54f  call    sub_18003D86C
0x18003c554  jmp     short loc_18003C5BF
0x18003c556  cmp     dword ptr [rsp+120h+var_F0], ebx
0x18003c55a  jnz     short loc_18003C5BF
0x18003c55c  cmp     [rbp+57h+var_50], 7
0x18003c561  lea     rax, [rbp+57h+var_68]
0x18003c565  cmova   rax, qword ptr [rbp+57h+var_68]
0x18003c56a  cmp     qword ptr [r14+18h], 7
0x18003c56f  mov     [rbp+57h+var_B8], rax
0x18003c573  mov     rax, [rbp+57h+var_58]
0x18003c577  mov     [rbp+57h+var_B0], rax
0x18003c57b  mov     rax, r14
0x18003c57e  jbe     short loc_18003C583
0x18003c580  mov     rax, [r14]
0x18003c583  cmp     qword ptr [rsi+60h], 7
0x18003c588  lea     rcx, [rsi+48h]
0x18003c58c  mov     [rbp+57h+var_A8], rax
0x18003c590  mov     rax, [r14+10h]
0x18003c594  mov     [rbp+57h+var_A0], rax
0x18003c598  jbe     short loc_18003C59E
0x18003c59a  mov     rcx, [rsi+48h]
0x18003c59e  mov     rax, [rsi+58h]
0x18003c5a2  lea     r9, [rbp+57h+var_B8]
0x18003c5a6  mov     r8d, [rsi+44h]
0x18003c5aa  lea     rdx, [rbp+57h+var_A8]
0x18003c5ae  mov     [rbp+57h+var_98], rcx
0x18003c5b2  lea     rcx, [rbp+57h+var_98]
0x18003c5b6  mov     [rbp+57h+var_90], rax
0x18003c5ba  call    sub_18009CC20
0x18003c5bf  lea     rcx, [rbp+57h+var_68]
0x18003c5c3  call    sub_18003A39C
0x18003c5c8  lea     rcx, [rbp+57h+lpSubKey]
0x18003c5cc  call    sub_18003A39C
0x18003c5d1  test    rdi, rdi
0x18003c5d4  jz      short loc_18003C60E
0x18003c5d6  or      esi, 0FFFFFFFFh
0x18003c5d9  mov     eax, esi
0x18003c5db  lock xadd [rdi+8], eax
0x18003c5e0  add     eax, esi
0x18003c5e2  jnz     short loc_18003C60E
0x18003c5e4  mov     rax, [rdi]
0x18003c5e7  mov     rcx, rdi
0x18003c5ea  mov     rax, [rax]
0x18003c5ed  call    cs:__guard_dispatch_icall_fptr
0x18003c5f3  mov     eax, esi
0x18003c5f5  lock xadd [rdi+0Ch], eax
0x18003c5fa  add     eax, esi
0x18003c5fc  jnz     short loc_18003C60E
0x18003c5fe  mov     rax, [rdi]
0x18003c601  mov     rcx, rdi
0x18003c604  mov     rax, [rax+8]
0x18003c608  call    cs:__guard_dispatch_icall_fptr
0x18003c60e  mov     r14d, dword ptr [rsp+120h+var_F0]
0x18003c613  add     r13, 10h
0x18003c617  cmp     r13, [rsp+120h+var_E0]
0x18003c61c  jnz     loc_18003C2F7
0x18003c622  sub     ebx, r15d
0x18003c625  lea     rcx, [rbp+57h+var_48]
0x18003c629  neg     ebx
0x18003c62b  sbb     ebx, ebx
0x18003c62d  and     ebx, 80004005h
0x18003c633  call    sub_18003A1E8
0x18003c638  mov     eax, ebx
0x18003c63a  jmp     short loc_18003C641
0x18003c63c  mov     eax, 80004005h
0x18003c641  mov     rcx, [rbp+57h+var_30]
0x18003c645  xor     rcx, rsp; StackCookie
0x18003c648  call    __security_check_cookie
0x18003c64d  lea     r11, [rsp+120h+var_20]
0x18003c655  mov     rbx, [r11+38h]
0x18003c659  mov     rsi, [r11+40h]
0x18003c65d  mov     rdi, [r11+48h]
0x18003c661  mov     rsp, r11
0x18003c664  pop     r15
0x18003c666  pop     r14
0x18003c668  pop     r13
0x18003c66a  pop     r12
  ... truncated ...
```

# sub_181FE7BB4

- ea: `0x181fe7bb4`
- end: `0x181fe84e9`
- name: `sub_181FE7BB4`
- size: `2357`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180ca1730`

## callees

- `0x1800580e0`
- `0x180086f40`
- `0x180088d28`
- `0x1800a774c`
- `0x180112b70`
- `0x1801172d4`
- `0x180227960`
- `0x18022ab58`
- `0x18032f53c`
- `0x180441ffc`
- `0x180599580`
- `0x180612480`
- `0x180636fb8`
- `0x180908e78`
- `0x18090a640`
- `0x180945a1c`
- `0x180945c0c`
- `0x1809d2a9c`
- `0x1809d2ac8`
- `0x1809d34e8`
- `0x1809d35e4`
- `0x180e192ec`
- `0x180eaee28`
- `0x1810eff0c`
- `0x18145a390`
- `0x18176d588`
- `0x181ddc0e8`
- `0x181ddd27c`
- `0x181dde1fc`
- `0x181fe7bb4`
- `0x181fe84ec`
- `0x181fe8cdc`
- `0x181febca4`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x181fe8104`
- `KERNEL32!TlsGetValue` at `0x181fe8128`
- `KERNEL32!TlsGetValue` at `0x181fe8138`
- `KERNEL32!TlsGetValue` at `0x181fe8167`
- `KERNEL32!TlsGetValue` at `0x181fe8187`
- `KERNEL32!TlsGetValue` at `0x181fe81a1`
- `KERNEL32!TlsGetValue` at `0x181fe81d6`
- `KERNEL32!TlsGetValue` at `0x181fe81eb`
- `KERNEL32!TlsGetValue` at `0x181fe8220`
- `KERNEL32!TlsGetValue` at `0x181fe8237`
- `KERNEL32!TlsGetValue` at `0x181fe8260`
- `KERNEL32!TlsGetValue` at `0x181fe8275`
- `KERNEL32!TlsGetValue` at `0x181fe829e`
- `KERNEL32!TlsGetValue` at `0x181fe82b3`
- `KERNEL32!TlsGetValue` at `0x181fe82dc`
- `KERNEL32!TlsGetValue` at `0x181fe82f1`
- `KERNEL32!TlsGetValue` at `0x181fe8104`
- `KERNEL32!TlsGetValue` at `0x181fe8128`
- `KERNEL32!TlsGetValue` at `0x181fe8138`
- `KERNEL32!TlsGetValue` at `0x181fe8167`
- `KERNEL32!TlsGetValue` at `0x181fe8187`
- `KERNEL32!TlsGetValue` at `0x181fe81a1`
- `KERNEL32!TlsGetValue` at `0x181fe81d6`
- `KERNEL32!TlsGetValue` at `0x181fe81eb`
- `KERNEL32!TlsGetValue` at `0x181fe8220`
- `KERNEL32!TlsGetValue` at `0x181fe8237`
- `KERNEL32!TlsGetValue` at `0x181fe8260`
- `KERNEL32!TlsGetValue` at `0x181fe8275`
- `KERNEL32!TlsGetValue` at `0x181fe829e`
- `KERNEL32!TlsGetValue` at `0x181fe82b3`
- `KERNEL32!TlsGetValue` at `0x181fe82dc`
- `KERNEL32!TlsGetValue` at `0x181fe82f1`
- `MSVCP140!?_Xout_of_range@std@@YAXPEBD@Z` at `0x181fe7d6b`
- `MSVCP140!?_Xout_of_range@std@@YAXPEBD@Z` at `0x181fe7dd0`
- `MSVCP140!?_Xout_of_range@std@@YAXPEBD@Z` at `0x181fe83de`
- `MSVCP140!?_Xout_of_range@std@@YAXPEBD@Z` at `0x181fe7d6b`
- `MSVCP140!?_Xout_of_range@std@@YAXPEBD@Z` at `0x181fe7dd0`
- `MSVCP140!?_Xout_of_range@std@@YAXPEBD@Z` at `0x181fe83de`
- `Mso30Win32Client!Mso30Win32Client_991` at `0x181fe7fa0`
- `Mso30Win32Client!Mso30Win32Client_991` at `0x181fe7fa0`
- `Mso20Win32Client!Mso20Win32Client_14081` at `0x181fe7f98`
- `Mso20Win32Client!Mso20Win32Client_14081` at `0x181fe7f98`
- `ole32!WriteClassStg` at `0x181fe846f`
- `ole32!WriteClassStg` at `0x181fe84b3`
- `ole32!WriteClassStg` at `0x181fe846f`
- `ole32!WriteClassStg` at `0x181fe84b3`
- `ole32!StringFromGUID2` at `0x181fe8409`
- `ole32!StringFromGUID2` at `0x181fe8409`
- `ole32!ReadClassStg` at `0x181fe83f1`
- `ole32!ReadClassStg` at `0x181fe83f1`

## pseudocode

```c
char __fastcall sub_181FE7BB4(__int64 a1, unsigned int a2, unsigned int a3, __int64 a4)
{
  int v8; // r13d
  OLECHAR *p_sz; // r14
  OLECHAR v10; // ax
  OLECHAR v11; // ax
  OLECHAR *v12; // rcx
  unsigned __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r10
  unsigned __int64 v16; // rax
  __int64 v17; // rax
  __int16 v18; // ax
  __int64 v20; // r8
  __int64 v21; // rdx
  unsigned int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  unsigned int v29; // r11d
  unsigned int v30; // r10d
  unsigned int v31; // ebx
  unsigned int v32; // r9d
  __int64 v33; // rax
  char *Value; // rax
  char *v35; // rbx
  unsigned int v36; // eax
  char *v37; // rax
  unsigned __int16 *v38; // rax
  unsigned __int16 *v39; // rax
  __int16 *v40; // rax
  __int16 *v41; // rax
  __int16 *v42; // rax
  __int16 *v43; // rax
  __int64 v44; // r15
  _QWORD *v45; // rbx
  __int64 v46; // r8
  char v47[8]; // [rsp+30h] [rbp-D0h] BYREF
  int v48; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v49; // [rsp+40h] [rbp-C0h] BYREF
  int v50; // [rsp+48h] [rbp-B8h]
  __int128 v51; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v52; // [rsp+60h] [rbp-A0h]
  __int64 v53; // [rsp+70h] [rbp-90h]
  unsigned int v54; // [rsp+78h] [rbp-88h] BYREF
  __int64 v55; // [rsp+80h] [rbp-80h]
  _DWORD v56[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v57; // [rsp+90h] [rbp-70h]
  CLSID pclsid; // [rsp+98h] [rbp-68h] BYREF
  __int128 v59; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v60; // [rsp+B8h] [rbp-48h]
  __int128 v61; // [rsp+C8h] [rbp-38h]
  __int16 v62; // [rsp+D8h] [rbp-28h]
  char v63; // [rsp+DAh] [rbp-26h]
  _WORD v64[1000]; // [rsp+E0h] [rbp-20h] BYREF
  OLECHAR sz; // [rsp+8B0h] [rbp+7B0h] BYREF
  __int16 v66; // [rsp+8B2h] [rbp+7B2h] BYREF

  v51 = 0;
  v52 = 0;
  v53 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v48 = 0;
  LODWORD(v49) = 0;
  v8 = 0;
  p_sz = 0;
  pclsid = 0;
  v50 = 0;
  sub_180227960(*(_QWORD *)(a1 + 280), a3, &v59);
  if ( (unsigned __int8)sub_180612480(a1, a2, (unsigned int)&v59, (unsigned int)&sz, 255) )
  {
    p_sz = &sz;
    if ( sz )
    {
      p_sz = (OLECHAR *)&v66;
      if ( v66 == 32 )
      {
        do
          ++p_sz;
        while ( *p_sz == 32 );
      }
      v10 = *p_sz;
      do
      {
        if ( !v10 )
          break;
        v10 = *++p_sz;
      }
      while ( *p_sz != 32 );
      while ( 1 )
      {
        v11 = *p_sz;
        if ( *p_sz != 32 )
          break;
        ++p_sz;
      }
      v12 = p_sz;
      do
      {
        if ( !v11 )
          break;
        if ( v11 == 20 )
          break;
        v11 = *++v12;
      }
      while ( *v12 != 32 );
      *v12 = 0;
    }
  }
  if ( DWORD2(v60) == 82 )
  {
    if ( (*(_DWORD *)(a4 + 24) & 0x400) != 0 )
      return 0;
    v8 = 1;
    goto LABEL_38;
  }
  if ( (unsigned __int8)sub_180636FB8(a1, a3, &v51, 1) )
  {
    if ( (__int64)(*(_QWORD *)(qword_182A0F5E8 + 8) - *(_QWORD *)qword_182A0F5E8) >> 3 <= (unsigned __int64)(unsigned int)v51 )
    {
      std::_Xout_of_range("invalid vector subscript");
      __debugbreak();
    }
    if ( !*(_QWORD *)(*(_QWORD *)qword_182A0F5E8 + 8LL * (unsigned int)v51) )
      return 0;
    if ( (unsigned __int8)sub_1800A774C(a1) && (*(_DWORD *)(a4 + 24) & 0x1000) != 0 && *(_BYTE *)(a1 + 208) )
    {
      if ( (*(_WORD *)(v15 + 156) & 0x1000) == 0 )
      {
        v16 = *(unsigned int *)(v15 + 168);
        if ( !(_DWORD)v16 )
          goto LABEL_107;
        if ( v13 <= v16 )
        {
          std::_Xout_of_range("invalid vector subscript");
          __debugbreak();
        }
        v17 = *(_QWORD *)(v14 + 8 * v16);
        if ( (*(_BYTE *)(v17 + 156) & 0x10) == 0
          || (v18 = *(_WORD *)(v17 + 112), v18 == HIWORD(dword_182A305F4))
          || v18 == word_182A30602 )
        {
LABEL_107:
          if ( (unsigned __int8)sub_18176D588(v15, a1, a2, a3) )
          {
            v47[0] = 123;
            sub_180945A1C(a4, v47, 1);
            sub_1809D34E8(a4, 755, 13);
            v47[0] = 32;
            goto LABEL_19;
          }
        }
      }
      return 0;
    }
LABEL_38:
    sub_1809D34E8(a4, 212, 5);
    if ( v8 )
    {
      sub_1809D35E4(a4, 223);
    }
    else
    {
      if ( (WORD2(v51) & 0x1000) != 0 )
      {
        v21 = 986;
      }
      else if ( (WORD2(v51) & 0x800) != 0 )
      {
        v21 = 985;
      }
      else if ( (BYTE4(v51) & 1) != 0 )
      {
        v21 = (BYTE4(v51) & 2) != 0 ? 205 : 216;
      }
      else
      {
        v21 = 213;
      }
      sub_1809D35E4(a4, v21);
      if ( (WORD2(v51) & 0x1000) != 0 || (WORD2(v51) & 0x800) != 0 )
      {
        memset(v64, 0, sizeof(v64));
        sub_18032F53C(v64, 0, 0);
        v22 = Mso20Win32Client_14081();
        if ( (unsigned int)Mso30Win32Client_991(v22) )
          sub_180112B70(v64, 1);
        sub_1809D2A9C(a4, 115, v64[3]);
      }
    }
    if ( (BYTE12(v61) & 0x10) != 0 )
      sub_1809D35E4(a4, 217);
    sub_180945C0C(a4);
    if ( (unsigned __int8)sub_18145A390(a3, a1) )
    {
      sub_1809D35E4(a4, 323);
      sub_180945C0C(a4);
    }
    if ( !v8 && (BYTE4(v51) & 1) == 0 )
    {
      if ( (unsigned int)sub_180EAEE28(a1, a3, v20) )
      {
        sub_1809D35E4(a4, 222);
        sub_180945C0C(a4);
      }
      goto LABEL_73;
    }
    v23 = sub_181FEBCA4(a3, a1) - 1;
    if ( v23 )
    {
      v24 = v23 - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( v26 && (v27 = v26 - 1) != 0 )
          {
            if ( v27 != 5 )
              goto LABEL_72;
            v28 = 326;
          }
          else
          {
            v28 = 322;
          }
        }
        else
        {
          v28 = 324;
        }
      }
      else
      {
        v28 = 327;
      }
    }
    else
    {
      v28 = 325;
    }
    sub_1809D35E4(a4, v28);
    sub_180945C0C(a4);
LABEL_72:
    if ( v8 )
    {
LABEL_77:
      v57 = a1;
      v56[0] = v59 + DWORD1(v59);
      v56[1] = v59 + DWORD1(v59) + 1;
      v33 = sub_18022AB58(a1, 0, 8);
      if ( (unsigned __int8)sub_1801172D4(v56, v33, 1, &v54) )
      {
        Value = (char *)TlsGetValue(dwTlsIndex);
        sub_180086F40(Value + 8, v55, v54, 5);
        v35 = (char *)TlsGetValue(dwTlsIndex) + 8;
        v36 = (unsigned int)TlsGetValue(dwTlsIndex);
        sub_180088D28(0, a1, v54, v36 + 19776, (__int64)v35, 128);
        v37 = (char *)TlsGetValue(dwTlsIndex);
        sub_180441FFC(v37 + 19800, a1, v54);
        if ( *((_WORD *)TlsGetValue(dwTlsIndex) + 19001) != 1000 )
        {
          v38 = (unsigned __int16 *)TlsGetValue(dwTlsIndex);
          sub_1809D2A9C(a4, 220, v38[19001] / 0xAu);
          sub_180945C0C(a4);
        }
        if ( *((_WORD *)TlsGetValue(dwTlsIndex) + 19002) != 1000 )
        {
          v39 = (unsigned __int16 *)TlsGetValue(dwTlsIndex);
          sub_1809D2A9C(a4, 221, v39[19002] / 0xAu);
          sub_180945C0C(a4);
        }
        if ( *((_WORD *)TlsGetValue(dwTlsIndex) + 19004) )
        {
          v40 = (__int16 *)TlsGetValue(dwTlsIndex);
          sub_1809D2A9C(a4, 210, (unsigned int)v40[19004]);
          sub_180945C0C(a4);
        }
        if ( *((_WORD *)TlsGetValue(dwTlsIndex) + 19006) )
        {
          v41 = (__int16 *)TlsGetValue(dwTlsIndex);
          sub_1809D2A9C(a4, 207, (unsigned int)v41[19006]);
          sub_180945C0C(a4);
        }
        if ( *((_WORD *)TlsGetValue(dwTlsIndex) + 19003) )
        {
          v42 = (__int16 *)TlsGetValue(dwTlsIndex);
          sub_1809D2A9C(a4, 208, (unsigned int)v42[19003]);
          sub_180945C0C(a4);
        }
        if ( *((_WORD *)TlsGetValue(dwTlsIndex) + 19005) )
        {
          v43 = (__int16 *)TlsGetValue(dwTlsIndex);
          sub_1809D2A9C(a4, 209, (unsigned int)v43[19005]);
          sub_180945C0C(a4);
        }
      }
      if ( v8 )
      {
        sub_181FE8CDC(a1, a3, a4);
      }
      else
      {
        sub_181DDC0E8(&v49);
        v44 = 0;
        v45 = v49;
        *v49 = &qword_182ACA388;
        sub_1809D34E8(a4, 206, 15);
        sub_181FE84EC(a4, &v51, p_sz);
        v47[0] = 125;
        sub_180945A1C(a4, v47, 1);
        sub_180945C0C(a4);
        if ( !(unsigned __int8)sub_1810EFF0C((unsigned int)v51, &sz, 255) || !sz )
        {
          if ( (__int64)(*(_QWORD *)(qword_182A0F5E8 + 8) - *(_QWORD *)qword_182A0F5E8) >> 3 <= (unsigned __int64)(unsigned int)v51 )
          {
            std::_Xout_of_range("invalid vector subscript");
            __debugbreak();
          }
          v44 = *(_QWORD *)(*(_QWORD *)qword_182A0F5E8 + 8LL * (unsigned int)v51);
          if ( ReadClassStg(*(LPSTORAGE *)(v44 + 88), &pclsid) >= 0 && StringFromGUID2(&pclsid, &sz, 255) > 0 )
          {
            sub_1809D34E8(a4, 1759, 15);
            v46 = -1;
            do
              ++v46;
            while ( *(&sz + v46) );
            sub_1809D2AC8(a4, &sz);
            v47[0] = 125;
            sub_180945A1C(a4, v47, 1);
            sub_180945C0C(a4);
            WriteClassStg(*(LPSTORAGE *)(v44 + 88), &stru_18252A218);
            v50 = 1;
          }
        }
        sub_1809D34E8(a4, 211, 15);
        v45[2] = a4;
        *((_DWORD *)v45 + 2) = 1;
        sub_181DDE1FC((unsigned int)v51, v45);
        sub_180945C0C(a4);
        if ( v50 )
          WriteClassStg(*(LPSTORAGE *)(v44 + 88), &pclsid);
        sub_1800580E0(&v49);
      }
      return 1;
    }
LABEL_73:
    if ( (_DWORD)v52 )
    {
      sub_1809D2A9C(a4, 224, (unsigned int)v52);
      sub_180945C0C(a4);
    }
    if ( (unsigned __int8)sub_181DDD27C((unsigned int)v51, &v48, &v49) )
    {
      sub_180599580((unsigned __int16)v48, 567, 1000);
      v31 = sub_180599580((unsigned __int16)v49, v30, v29);
      sub_1809D2A9C(a4, 225, v32);
      sub_1809D2A9C(a4, 214, v31);
      sub_180945C0C(a4);
    }
    goto LABEL_77;
  }
  sub_180E192EC(693, 0, 0, 1, 588866650);
  sub_1809D34E8(a4, 212, 13);
  v47[0] = 123;
LABEL_19:
  sub_180945A1C(a4, v47, 1);
  sub_180945C0C(a4);
  return 1;
}

```

## disassembly

```asm
0x181fe7bb4  push    rbp
0x181fe7bb6  push    rbx
0x181fe7bb7  push    rsi
0x181fe7bb8  push    rdi
0x181fe7bb9  push    r12
0x181fe7bbb  push    r13
0x181fe7bbd  push    r14
0x181fe7bbf  push    r15
0x181fe7bc1  lea     rbp, [rsp-9C8h]
0x181fe7bc9  sub     rsp, 0AC8h
0x181fe7bd0  mov     rax, cs:__security_cookie
0x181fe7bd7  xor     rax, rsp
0x181fe7bda  mov     [rbp+0A00h+var_50], rax
0x181fe7be1  mov     rdi, r9
0x181fe7be4  mov     r12d, r8d
0x181fe7be7  mov     ebx, edx
0x181fe7be9  mov     r15, rcx
0x181fe7bec  xorps   xmm0, xmm0
0x181fe7bef  xor     eax, eax
0x181fe7bf1  movups  [rsp+0B00h+var_AB0], xmm0
0x181fe7bf6  movups  [rsp+0B00h+var_AA0], xmm0
0x181fe7bfb  mov     [rsp+0B00h+var_A90], rax
0x181fe7c00  xorps   xmm1, xmm1
0x181fe7c03  movups  [rbp+0A00h+var_A58], xmm1
0x181fe7c07  movups  [rbp+0A00h+var_A48], xmm1
0x181fe7c0b  movups  [rbp+0A00h+var_A38], xmm1
0x181fe7c0f  mov     [rbp+0A00h+var_A28], ax
0x181fe7c13  mov     [rbp+0A00h+var_A26], al
0x181fe7c16  xor     esi, esi
0x181fe7c18  mov     [rsp+0B00h+var_AC8], esi
0x181fe7c1c  mov     dword ptr [rsp+0B00h+var_AC0], esi
0x181fe7c20  mov     r13d, esi
0x181fe7c23  mov     r14d, esi
0x181fe7c26  movups  xmmword ptr [rbp+0A00h+pclsid.Data1], xmm0
0x181fe7c2a  mov     [rsp+0B00h+var_AB8], esi
0x181fe7c2e  lea     r8, [rbp+0A00h+var_A58]
0x181fe7c32  mov     edx, r12d
0x181fe7c35  mov     rcx, [rcx+118h]
0x181fe7c3c  call    sub_180227960
0x181fe7c41  mov     dword ptr [rsp+0B00h+var_AE0], 0FFh
0x181fe7c49  lea     r9, [rbp+0A00h+sz]
0x181fe7c50  lea     r8, [rbp+0A00h+var_A58]
0x181fe7c54  mov     edx, ebx
0x181fe7c56  mov     rcx, r15
0x181fe7c59  call    sub_180612480
0x181fe7c5e  mov     dx, 20h ; ' '
0x181fe7c62  test    al, al
0x181fe7c64  jz      short loc_181FE7CD2
0x181fe7c66  lea     r14, [rbp+0A00h+sz]
0x181fe7c6d  cmp     [rbp+0A00h+sz], si
0x181fe7c74  jz      short loc_181FE7CD2
0x181fe7c76  lea     r14, [rbp+0A00h+var_24E]
0x181fe7c7d  cmp     [rbp+0A00h+var_24E], dx
0x181fe7c84  jnz     short loc_181FE7C90
0x181fe7c86  add     r14, 2
0x181fe7c8a  cmp     [r14], dx
0x181fe7c8e  jz      short loc_181FE7C86
0x181fe7c90  movzx   eax, word ptr [r14]
0x181fe7c94  test    ax, ax
0x181fe7c97  jz      short loc_181FE7CAC
0x181fe7c99  add     r14, 2
0x181fe7c9d  movzx   eax, word ptr [r14]
0x181fe7ca1  cmp     ax, dx
0x181fe7ca4  jnz     short loc_181FE7C94
0x181fe7ca6  jmp     short loc_181FE7CAC
0x181fe7ca8  add     r14, 2
0x181fe7cac  movzx   eax, word ptr [r14]
0x181fe7cb0  cmp     ax, dx
0x181fe7cb3  jz      short loc_181FE7CA8
0x181fe7cb5  mov     rcx, r14
0x181fe7cb8  test    ax, ax
0x181fe7cbb  jz      short loc_181FE7CCF
0x181fe7cbd  cmp     ax, 14h
0x181fe7cc1  jz      short loc_181FE7CCF
0x181fe7cc3  add     rcx, 2
0x181fe7cc7  movzx   eax, word ptr [rcx]
0x181fe7cca  cmp     ax, dx
0x181fe7ccd  jnz     short loc_181FE7CB8
0x181fe7ccf  mov     [rcx], si
0x181fe7cd2  cmp     dword ptr [rbp+0A00h+var_A48+8], 52h ; 'R'
0x181fe7cd6  jz      loc_181FE7E41
0x181fe7cdc  mov     esi, 1
0x181fe7ce1  mov     r9d, esi
0x181fe7ce4  lea     r8, [rsp+0B00h+var_AB0]
0x181fe7ce9  mov     edx, r12d
0x181fe7cec  mov     rcx, r15
0x181fe7cef  call    sub_180636FB8
0x181fe7cf4  test    al, al
0x181fe7cf6  jnz     short loc_181FE7D45
0x181fe7cf8  mov     dword ptr [rsp+0B00h+var_AE0], 2319645Ah
0x181fe7d00  mov     r9d, esi
0x181fe7d03  xor     r8d, r8d
0x181fe7d06  xor     edx, edx
0x181fe7d08  mov     ecx, 2B5h
0x181fe7d0d  call    sub_180E192EC
0x181fe7d12  mov     edx, 0D4h
0x181fe7d17  lea     r8d, [rsi+0Ch]
0x181fe7d1b  mov     rcx, rdi
0x181fe7d1e  call    sub_1809D34E8
0x181fe7d23  mov     [rsp+0B00h+var_AD0], 7Bh ; '{'
0x181fe7d28  mov     r8d, esi
0x181fe7d2b  lea     rdx, [rsp+0B00h+var_AD0]
0x181fe7d30  mov     rcx, rdi
0x181fe7d33  call    sub_180945A1C
0x181fe7d38  mov     rcx, rdi
0x181fe7d3b  call    sub_180945C0C
0x181fe7d40  jmp     loc_181FE84C3
0x181fe7d45  mov     rax, cs:qword_182A0F5E8
0x181fe7d4c  mov     r8, [rax]
0x181fe7d4f  mov     rdx, [rax+8]
0x181fe7d53  sub     rdx, r8
0x181fe7d56  sar     rdx, 3
0x181fe7d5a  mov     r10d, dword ptr [rsp+0B00h+var_AB0]
0x181fe7d5f  cmp     rdx, r10
0x181fe7d62  ja      short loc_181FE7D72
0x181fe7d64  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x181fe7d6b  call    cs:?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x181fe7d71  int     3; Trap to Debugger
0x181fe7d72  mov     r10, [r8+r10*8]
0x181fe7d76  test    r10, r10
0x181fe7d79  jz      loc_181FE7E4A
0x181fe7d7f  mov     rcx, r15
0x181fe7d82  call    sub_1800A774C
0x181fe7d87  test    al, al
0x181fe7d89  jz      loc_181FE7E59
0x181fe7d8f  mov     eax, 1000h
0x181fe7d94  test    [rdi+18h], eax
0x181fe7d97  jz      loc_181FE7E59
0x181fe7d9d  cmp     byte ptr [r15+0D0h], 0
0x181fe7da5  jz      loc_181FE7E59
0x181fe7dab  test    [r10+9Ch], ax
0x181fe7db3  jnz     loc_181FE7E4A
0x181fe7db9  mov     eax, [r10+0A8h]
0x181fe7dc0  test    eax, eax
0x181fe7dc2  jz      short loc_181FE7DFA
0x181fe7dc4  cmp     rdx, rax
0x181fe7dc7  ja      short loc_181FE7DD7
0x181fe7dc9  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x181fe7dd0  call    cs:?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x181fe7dd6  int     3; Trap to Debugger
0x181fe7dd7  mov     rax, [r8+rax*8]
0x181fe7ddb  test    byte ptr [rax+9Ch], 10h
0x181fe7de2  jz      short loc_181FE7DFA
0x181fe7de4  movzx   eax, word ptr [rax+70h]
0x181fe7de8  cmp     ax, word ptr cs:dword_182A305F4+2
0x181fe7def  jz      short loc_181FE7DFA
0x181fe7df1  cmp     ax, cs:word_182A30602
0x181fe7df8  jnz     short loc_181FE7E4A
0x181fe7dfa  mov     r9d, r12d
0x181fe7dfd  mov     r8d, ebx
0x181fe7e00  mov     rdx, r15
0x181fe7e03  mov     rcx, r10
0x181fe7e06  call    sub_18176D588
0x181fe7e0b  test    al, al
0x181fe7e0d  jz      short loc_181FE7E4A
0x181fe7e0f  mov     [rsp+0B00h+var_AD0], 7Bh ; '{'
0x181fe7e14  mov     r8d, esi
0x181fe7e17  lea     rdx, [rsp+0B00h+var_AD0]
0x181fe7e1c  mov     rcx, rdi
0x181fe7e1f  call    sub_180945A1C
0x181fe7e24  mov     edx, 2F3h
0x181fe7e29  mov     r8d, 0Dh
0x181fe7e2f  mov     rcx, rdi
0x181fe7e32  call    sub_1809D34E8
0x181fe7e37  mov     [rsp+0B00h+var_AD0], 20h ; ' '
0x181fe7e3c  jmp     loc_181FE7D28
0x181fe7e41  test    dword ptr [rdi+18h], 400h
0x181fe7e48  jz      short loc_181FE7E51
0x181fe7e4a  xor     al, al
0x181fe7e4c  jmp     loc_181FE84C6
0x181fe7e51  mov     esi, 1
0x181fe7e56  mov     r13d, esi
0x181fe7e59  mov     edx, 0D4h
0x181fe7e5e  mov     r8d, 5
0x181fe7e64  mov     rcx, rdi
0x181fe7e67  call    sub_1809D34E8
0x181fe7e6c  test    r13d, r13d
0x181fe7e6f  jz      loc_181FE7F04
0x181fe7e75  mov     edx, 0DFh
0x181fe7e7a  mov     rcx, rdi
0x181fe7e7d  call    sub_1809D35E4
0x181fe7e82  xor     ebx, ebx
0x181fe7e84  test    byte ptr [rbp+0A00h+var_A38+0Ch], 10h
0x181fe7e88  jz      short loc_181FE7E97
0x181fe7e8a  mov     edx, 0D9h
0x181fe7e8f  mov     rcx, rdi
0x181fe7e92  call    sub_1809D35E4
0x181fe7e97  mov     rcx, rdi
0x181fe7e9a  call    sub_180945C0C
0x181fe7e9f  mov     rdx, r15
0x181fe7ea2  mov     ecx, r12d
0x181fe7ea5  call    sub_18145A390
0x181fe7eaa  test    al, al
0x181fe7eac  jz      short loc_181FE7EC3
0x181fe7eae  mov     edx, 143h
0x181fe7eb3  mov     rcx, rdi
0x181fe7eb6  call    sub_1809D35E4
0x181fe7ebb  mov     rcx, rdi
0x181fe7ebe  call    sub_180945C0C
0x181fe7ec3  test    r13d, r13d
0x181fe7ec6  jnz     loc_181FE7FCE
0x181fe7ecc  test    byte ptr [rsp+0B00h+var_AB0+4], sil
0x181fe7ed1  jnz     loc_181FE7FCE
0x181fe7ed7  mov     edx, r12d
0x181fe7eda  mov     rcx, r15
0x181fe7edd  call    sub_180EAEE28
0x181fe7ee2  test    eax, eax
0x181fe7ee4  jz      loc_181FE8031
0x181fe7eea  mov     edx, 0DEh
0x181fe7eef  mov     rcx, rdi
0x181fe7ef2  call    sub_1809D35E4
0x181fe7ef7  mov     rcx, rdi
0x181fe7efa  call    sub_180945C0C
0x181fe7eff  jmp     loc_181FE8031
0x181fe7f04  movzx   eax, word ptr [rsp+0B00h+var_AB0+4]
0x181fe7f09  bt      ax, 0Ch
0x181fe7f0e  jnb     short loc_181FE7F17
0x181fe7f10  mov     edx, 3DAh
0x181fe7f15  jmp     short loc_181FE7F40
0x181fe7f17  bt      ax, 0Bh
0x181fe7f1c  jnb     short loc_181FE7F25
0x181fe7f1e  mov     edx, 3D9h
0x181fe7f23  jmp     short loc_181FE7F40
0x181fe7f25  test    sil, al
0x181fe7f28  jz      short loc_181FE7F3B
0x181fe7f2a  and     al, 2
0x181fe7f2c  neg     al
0x181fe7f2e  sbb     edx, edx
0x181fe7f30  and     edx, 0FFFFFFF5h
0x181fe7f33  add     edx, 0D8h
0x181fe7f39  jmp     short loc_181FE7F40
0x181fe7f3b  mov     edx, 0D5h
0x181fe7f40  mov     rcx, rdi
0x181fe7f43  call    sub_1809D35E4
0x181fe7f48  mov     eax, 1000h
0x181fe7f4d  test    word ptr [rsp+0B00h+var_AB0+4], ax
0x181fe7f52  jnz     short loc_181FE7F64
0x181fe7f54  mov     eax, 800h
0x181fe7f59  test    word ptr [rsp+0B00h+var_AB0+4], ax
0x181fe7f5e  jz      loc_181FE7E82
0x181fe7f64  xor     edx, edx; Val
0x181fe7f66  mov     r8d, 7D0h; Size
0x181fe7f6c  lea     rcx, [rbp+0A00h+var_A20]; void *
0x181fe7f70  call    memset
0x181fe7f75  mov     [rsp+0B00h+var_AD8], 0; int
0x181fe7f7d  mov     [rsp+0B00h+var_AE0], 0; __int64
0x181fe7f86  xor     r9d, r9d
0x181fe7f89  mov     r8d, ebx
0x181fe7f8c  mov     rdx, r15
0x181fe7f8f  lea     rcx, [rbp+0A00h+var_A20]; void *
0x181fe7f93  call    sub_18032F53C
0x181fe7f98  call    cs:Mso20Win32Client_14081
0x181fe7f9e  mov     ecx, eax
0x181fe7fa0  call    cs:Mso30Win32Client_991
0x181fe7fa6  xor     ebx, ebx
0x181fe7fa8  test    eax, eax
0x181fe7faa  jz      short loc_181FE7FB7
0x181fe7fac  mov     edx, esi
0x181fe7fae  lea     rcx, [rbp+0A00h+var_A20]
0x181fe7fb2  call    sub_180112B70
0x181fe7fb7  movsx   r8d, [rbp+0A00h+var_A1A]
0x181fe7fbc  mov     edx, 73h ; 's'
0x181fe7fc1  mov     rcx, rdi
0x181fe7fc4  call    sub_1809D2A9C
0x181fe7fc9  jmp     loc_181FE7E84
0x181fe7fce  mov     rdx, r15
0x181fe7fd1  mov     ecx, r12d
0x181fe7fd4  call    sub_181FEBCA4
0x181fe7fd9  sub     eax, 1
0x181fe7fdc  jz      short loc_181FE8013
0x181fe7fde  sub     eax, 1
0x181fe7fe1  jz      short loc_181FE800C
0x181fe7fe3  sub     eax, 1
0x181fe7fe6  jz      short loc_181FE8005
0x181fe7fe8  sub     eax, 1
0x181fe7feb  jz      short loc_181FE7FFE
0x181fe7fed  sub     eax, 1
0x181fe7ff0  jz      short loc_181FE7FFE
0x181fe7ff2  cmp     eax, 5
0x181fe7ff5  jnz     short loc_181FE8028
0x181fe7ff7  mov     edx, 146h
0x181fe7ffc  jmp     short loc_181FE8018
0x181fe7ffe  mov     edx, 142h
0x181fe8003  jmp     short loc_181FE8018
0x181fe8005  mov     edx, 144h
0x181fe800a  jmp     short loc_181FE8018
0x181fe800c  mov     edx, 147h
0x181fe8011  jmp     short loc_181FE8018
0x181fe8013  mov     edx, 145h
0x181fe8018  mov     rcx, rdi
0x181fe801b  call    sub_1809D35E4
0x181fe8020  mov     rcx, rdi
0x181fe8023  call    sub_180945C0C
0x181fe8028  test    r13d, r13d
0x181fe802b  jnz     loc_181FE80C2
0x181fe8031  mov     r8d, dword ptr [rsp+0B00h+var_AA0]
0x181fe8036  test    r8d, r8d
0x181fe8039  jz      short loc_181FE8050
0x181fe803b  mov     edx, 0E0h
0x181fe8040  mov     rcx, rdi
  ... truncated ...
```

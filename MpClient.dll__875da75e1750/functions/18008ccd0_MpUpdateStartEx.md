# MpUpdateStartEx

- ea: `0x18008ccd0`
- end: `0x18008d630`
- name: `MpUpdateStartEx`
- size: `2400`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `installer_update`

## callers

- `0x18008ccb0`
- `0x1800af17c`

## callees

- `0x18001b270`
- `0x18003b830`
- `0x180073384`
- `0x1800733a8`
- `0x18007aee8`
- `0x18007b188`
- `0x180089b18`
- `0x180089d74`
- `0x18008afac`
- `0x18008b3b8`
- `0x18008b958`
- `0x18008bafc`
- `0x18008c824`
- `0x18008ccd0`
- `0x18008d630`
- `0x18008d98c`
- `0x1800af024`
- `0x1800b07ac`
- `0x1800ca400`
- `0x1800cb1b4`
- `0x1800d8afc`
- `0x1800de950`
- `0x180112ee0`
- `0x180125920`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x18008cd6a`
- `KERNEL32!DebugBreak` at `0x18008cd6a`
- `KERNEL32!HeapFree` at `0x18008ce38`
- `KERNEL32!HeapFree` at `0x18008cf2d`
- `KERNEL32!HeapFree` at `0x18008cfae`
- `KERNEL32!HeapFree` at `0x18008d0be`
- `KERNEL32!HeapFree` at `0x18008d1ca`
- `KERNEL32!HeapFree` at `0x18008d2b2`
- `KERNEL32!HeapFree` at `0x18008d38e`
- `KERNEL32!HeapFree` at `0x18008d466`
- `KERNEL32!HeapFree` at `0x18008d5a6`
- `KERNEL32!HeapFree` at `0x18008ce38`
- `KERNEL32!HeapFree` at `0x18008cf2d`
- `KERNEL32!HeapFree` at `0x18008cfae`
- `KERNEL32!HeapFree` at `0x18008d0be`
- `KERNEL32!HeapFree` at `0x18008d1ca`
- `KERNEL32!HeapFree` at `0x18008d2b2`
- `KERNEL32!HeapFree` at `0x18008d38e`
- `KERNEL32!HeapFree` at `0x18008d466`
- `KERNEL32!HeapFree` at `0x18008d5a6`

## string_xrefs

- `0x18008cd4b`: `MpClient_MpUpdateStartExDebug`

## pseudocode

```c
__int64 __fastcall MpUpdateStartEx(_DWORD *a1, unsigned int a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 v7; // r9
  int v8; // eax
  int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // edi
  int v13; // r14d
  LPVOID v14; // rdi
  __int64 v15; // rcx
  int v16; // eax
  _QWORD *v17; // rcx
  bool v18; // zf
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  _QWORD *v22; // rcx
  unsigned int v23; // r15d
  unsigned int v24; // edi
  int v25; // eax
  int v26; // eax
  int v27; // eax
  _QWORD *v28; // rcx
  int v29; // eax
  LPVOID v30; // rdi
  __int64 v31; // rcx
  int v32; // eax
  void (__fastcall ***v33)(_QWORD, __int64); // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int v36; // eax
  void (__fastcall ***v37)(_QWORD, __int64); // rcx
  __int64 v38; // rcx
  int v39; // r14d
  int v40; // r14d
  int v41; // r14d
  int v42; // r14d
  int v43; // r14d
  int v44; // r14d
  void (__fastcall ***v45)(_QWORD, __int64); // rcx
  _QWORD *v46; // rax
  __int64 v47; // [rsp+30h] [rbp-41h] BYREF
  __int64 v48; // [rsp+38h] [rbp-39h] BYREF
  _QWORD *v49; // [rsp+40h] [rbp-31h]
  unsigned int v50; // [rsp+48h] [rbp-29h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-21h] BYREF
  _OWORD v52[2]; // [rsp+58h] [rbp-19h] BYREF

  v48 = a3;
  v50 = a2;
  v49 = a5;
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 2) != 0 )
    sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 78, &stru_180146770, a2);
  LODWORD(lpMem) = 0;
  if ( (int)sub_180112EE0(L"MpClient_MpUpdateStartExDebug", 0, &lpMem) >= 0 )
  {
    v8 = (int)lpMem;
  }
  else
  {
    v8 = 0;
    LODWORD(lpMem) = 0;
  }
  if ( v8 )
    DebugBreak();
  if ( !a1 || !a5 || !a4 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_180073384(*((_QWORD *)off_18019DE80 + 2), 79, &stru_180146770, v7);
    return 2147942487LL;
  }
  if ( *a1 != 1 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_180073384(*((_QWORD *)off_18019DE80 + 2), 80, &stru_180146770, v7);
    return 2147942406LL;
  }
  v10 = sub_180089D74(&v50);
  v12 = v10;
  if ( v10 >= 0 )
  {
    lpMem = 0;
    LOBYTE(v11) = 1;
    v13 = sub_1800CA400(&lpMem, 16, v11);
    if ( v13 < 0 )
    {
      v14 = lpMem;
      if ( !lpMem || !qword_1801A9738 || HeapFree(qword_1801A9738, 0, lpMem) )
        return (unsigned int)v13;
      goto LABEL_26;
    }
    v47 = 0;
    if ( (unsigned int)sub_1800DE950() )
    {
      v22 = off_18019DE80;
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      {
        sub_180073384(*((_QWORD *)off_18019DE80 + 2), 82, &stru_180146770, v21);
        v22 = off_18019DE80;
      }
      v13 = 7;
      v23 = 1;
LABEL_133:
      if ( v22 != &off_18019DE80 && (*((_BYTE *)v22 + 28) & 2) != 0 )
        sub_1800733A8(v22[2], 85, &stru_180146770, (unsigned int)v13);
      v38 = 0;
      v39 = v13 - 1;
      if ( v39 )
      {
        v40 = v39 - 1;
        if ( v40 )
        {
          v41 = v40 - 1;
          if ( v41 )
          {
            v42 = v41 - 1;
            if ( v42 )
            {
              v43 = v42 - 1;
              if ( v43 )
              {
                v44 = v43 - 1;
                if ( v44 )
                {
                  if ( v44 == 1 )
                    v38 = 7;
                }
                else
                {
                  v38 = 6;
                }
              }
              else
              {
                v38 = 5;
              }
            }
            else
            {
              v38 = 4;
            }
          }
          else
          {
            v38 = 3;
          }
        }
        else
        {
          v38 = 2;
        }
      }
      else
      {
        v38 = 1;
      }
      sub_18008C824(v38);
      if ( *(_QWORD *)a4 )
      {
        memset(v52, 0, sizeof(v52));
        sub_1800D8AFC(v52, 6, 32781, v23);
        (*(void (__fastcall **)(_QWORD, _OWORD *))a4)(*(_QWORD *)(a4 + 8), v52);
      }
      v47 = 0;
      v13 = sub_180089B18(&v47);
      if ( v13 < 0 )
      {
        v45 = (void (__fastcall ***)(_QWORD, __int64))v47;
        if ( v47 && _InterlockedExchangeAdd((volatile signed __int32 *)(v47 + 8), 0xFFFFFFFF) <= 1 )
        {
          _mm_lfence();
          (**v45)(v45, 1);
        }
        v14 = lpMem;
        if ( !lpMem || !qword_1801A9738 || HeapFree(qword_1801A9738, 0, lpMem) )
          return (unsigned int)v13;
        goto LABEL_159;
      }
      goto LABEL_160;
    }
    v24 = v50;
    if ( (v50 & 4) == 0 )
      goto LABEL_46;
    v25 = sub_18008AFAC(v50);
    v13 = v25;
    if ( v25 < 0 )
    {
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
        sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 83, &stru_180146770, (unsigned int)v25);
      v14 = lpMem;
      if ( !lpMem || !qword_1801A9738 || HeapFree(qword_1801A9738, 0, lpMem) )
        return (unsigned int)v13;
      goto LABEL_26;
    }
    if ( !v25 )
    {
LABEL_46:
      v26 = sub_18008B3B8(v24, v19, v20, v21);
      v13 = v26;
      if ( v26 < 0 )
      {
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 84, &stru_180146770, (unsigned int)v26);
        v14 = lpMem;
        if ( !lpMem || !qword_1801A9738 || HeapFree(qword_1801A9738, 0, lpMem) )
          return (unsigned int)v13;
LABEL_26:
        v16 = sub_18001B270(v15);
        v17 = off_18019DE80;
        v18 = off_18019DE80 == (_UNKNOWN *)&off_18019DE80;
LABEL_27:
        if ( !v18 && (*((_BYTE *)v17 + 28) & 1) != 0 )
          sub_18007B188(v17[2], 11, qword_180146138, v14, v16);
        return (unsigned int)v13;
      }
    }
    v23 = 1;
    v50 = 1;
    if ( !v13 )
    {
      v13 = sub_18008B958(&v50);
      if ( !v13 )
      {
        v27 = sub_1800CB1B4(0, 0);
        if ( v27 < 0 )
        {
          v28 = off_18019DE80;
          if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 2) == 0 )
          {
LABEL_61:
            v29 = v24 & 0x1D0;
            if ( (v24 & 0x1D0) != 0 )
            {
              if ( v29 != 64 && v29 != 16 && v29 != 128 && v29 != 256 )
              {
                if ( v28 != &off_18019DE80 && (*((_BYTE *)v28 + 28) & 1) != 0 )
                  sub_18007AEE8(v28[2], 87, &stru_180146770, v24, v24 & 0x1D0);
                v30 = lpMem;
                if ( lpMem )
                {
                  if ( qword_1801A9738 )
                  {
                    if ( !HeapFree(qword_1801A9738, 0, lpMem) )
                    {
                      v32 = sub_18001B270(v31);
                      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
                        sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v30, v32);
                    }
                  }
                }
                return 2147942487LL;
              }
              if ( v28 != &off_18019DE80 && (*((_BYTE *)v28 + 28) & 2) != 0 )
                sub_18007AEE8(v28[2], 88, &stru_180146770, v24, v24);
              v13 = sub_18008BAFC(&v47, a1, a4, v24);
              if ( v13 < 0 )
              {
                if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
                  sub_18008D630(*((_QWORD *)off_18019DE80 + 2), 89, &stru_180146770);
                v33 = (void (__fastcall ***)(_QWORD, __int64))v47;
                if ( v47 && _InterlockedExchangeAdd((volatile signed __int32 *)(v47 + 8), 0xFFFFFFFF) <= 1 )
                {
                  _mm_lfence();
                  (**v33)(v33, 1);
                }
                v14 = lpMem;
                if ( !lpMem || !qword_1801A9738 || HeapFree(qword_1801A9738, 0, lpMem) )
                  return (unsigned int)v13;
                goto LABEL_159;
              }
LABEL_160:
              v35 = v47;
LABEL_161:
              v46 = lpMem;
              *(_DWORD *)lpMem = 4;
              v46[1] = v35;
              *v49 = v46;
              return 0;
            }
            if ( (v24 & 0x20) != 0 )
            {
              if ( v28 != &off_18019DE80 && (*((_BYTE *)v28 + 28) & 2) != 0 )
                sub_1800733A8(v28[2], 90, &stru_180146770, v24);
              v50 = v24;
              v47 = 0;
              v13 = sub_1800B07AC(&v47, a4, &v50, &v48);
              v35 = v47;
              if ( v13 >= 0 )
                goto LABEL_161;
              if ( v47 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)(v47 + 16) + 8LL))(v47 + 16);
              if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
                sub_18007AEE8(*((_QWORD *)off_18019DE80 + 2), 91, &stru_180146770, v24, v13);
              v14 = lpMem;
              if ( !lpMem || !qword_1801A9738 || HeapFree(qword_1801A9738, 0, lpMem) )
                return (unsigned int)v13;
            }
            else if ( (v24 & 8) != 0 )
            {
              if ( v28 != &off_18019DE80 && (*((_BYTE *)v28 + 28) & 2) != 0 )
                sub_1800733A8(v28[2], 92, &stru_180146770, v24);
              v50 = v24;
              v47 = 0;
              v13 = sub_18008D98C(&v47, a4, &v50);
              v35 = v47;
              if ( v13 >= 0 )
                goto LABEL_161;
              if ( v47 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)(v47 + 16) + 8LL))(v47 + 16);
              if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
                sub_18007AEE8(*((_QWORD *)off_18019DE80 + 2), 93, &stru_180146770, v24, v13);
              v14 = lpMem;
              if ( !lpMem || !qword_1801A9738 || HeapFree(qword_1801A9738, 0, lpMem) )
                return (unsigned int)v13;
            }
            else
            {
              if ( v28 != &off_18019DE80 && (*((_BYTE *)v28 + 28) & 2) != 0 )
                sub_1800733A8(v28[2], 94, &stru_180146770, v24);
              v36 = sub_1800AF024(&v47, a1, a4, v24);
              v13 = v36;
              if ( v36 >= 0 )
                goto LABEL_160;
              if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
                sub_18007AEE8(*((_QWORD *)off_18019DE80 + 2), 95, &stru_180146770, v24, v36);
              v37 = (void (__fastcall ***)(_QWORD, __int64))v47;
              if ( v47 && _InterlockedExchangeAdd((volatile signed __int32 *)(v47 + 8), 0xFFFFFFFF) <= 1 )
              {
                _mm_lfence();
                (**v37)(v37, 1);
              }
              v14 = lpMem;
              if ( !lpMem || !qword_1801A9738 || HeapFree(qword_1801A9738, 0, lpMem) )
                return (unsigned int)v13;
            }
LABEL_159:
            v16 = sub_18001B270(v34);
            v17 = off_18019DE80;
            v18 = off_18019DE80 == (_UNKNOWN *)&off_18019DE80;
            goto LABEL_27;
          }
          sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 86, &stru_180146770, (unsigned int)v27);
        }
        v28 = off_18019DE80;
        goto LABEL_61;
      }
      v23 = v50;
    }
    v22 = off_18019DE80;
    goto LABEL_133;
  }
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    sub_18007AEE8(*((_QWORD *)off_18019DE80 + 2), 81, &stru_180146770, v50, v10);
  return v12;
}

```

## disassembly

```asm
0x18008ccd0  push    rbp
0x18008ccd2  push    rbx
0x18008ccd3  push    rsi
0x18008ccd4  push    rdi
0x18008ccd5  push    r12
0x18008ccd7  push    r13
0x18008ccd9  push    r14
0x18008ccdb  push    r15
0x18008ccdd  lea     rbp, [rsp-17h]
0x18008cce2  sub     rsp, 88h
0x18008cce9  mov     rax, cs:__security_cookie
0x18008ccf0  xor     rax, rsp
0x18008ccf3  mov     [rbp+4Fh+var_48], rax
0x18008ccf7  mov     r13, r9
0x18008ccfa  mov     [rbp+4Fh+var_88], r8
0x18008ccfe  mov     r9d, edx
0x18008cd01  mov     r12, rcx
0x18008cd04  mov     [rbp+4Fh+var_78], edx
0x18008cd07  mov     rdi, [rbp+4Fh+arg_20]
0x18008cd0b  mov     [rbp+4Fh+var_80], rdi
0x18008cd0f  lea     r15, off_18019DE80
0x18008cd16  lea     r14, stru_180146770
0x18008cd1d  mov     rcx, cs:off_18019DE80
0x18008cd24  cmp     rcx, r15
0x18008cd27  jz      short loc_18008CD40
0x18008cd29  test    byte ptr [rcx+1Ch], 2
0x18008cd2d  jz      short loc_18008CD40
0x18008cd2f  mov     edx, 4Eh ; 'N'
0x18008cd34  mov     r8, r14
0x18008cd37  mov     rcx, [rcx+10h]
0x18008cd3b  call    sub_1800733A8
0x18008cd40  xor     ebx, ebx
0x18008cd42  mov     dword ptr [rbp+4Fh+lpMem], ebx
0x18008cd45  lea     r8, [rbp+4Fh+lpMem]
0x18008cd49  xor     edx, edx
0x18008cd4b  lea     rcx, aMpclientMpupda; "MpClient_MpUpdateStartExDebug"
0x18008cd52  call    sub_180112EE0
0x18008cd57  nop
0x18008cd58  test    eax, eax
0x18008cd5a  jns     short loc_18008CD63
0x18008cd5c  mov     eax, ebx
0x18008cd5e  mov     dword ptr [rbp+4Fh+lpMem], ebx
0x18008cd61  jmp     short loc_18008CD66
0x18008cd63  mov     eax, dword ptr [rbp+4Fh+lpMem]
0x18008cd66  test    eax, eax
0x18008cd68  jz      short loc_18008CD70
0x18008cd6a  call    cs:__imp_DebugBreak
0x18008cd70  test    r12, r12
0x18008cd73  jz      loc_18008D5E5
0x18008cd79  test    rdi, rdi
0x18008cd7c  jz      loc_18008D5E5
0x18008cd82  test    r13, r13
0x18008cd85  jz      loc_18008D5E5
0x18008cd8b  mov     esi, 1
0x18008cd90  cmp     [r12], esi
0x18008cd94  jz      short loc_18008CDC1
0x18008cd96  mov     rcx, cs:off_18019DE80
0x18008cd9d  cmp     rcx, r15
0x18008cda0  jz      short loc_18008CDB7
0x18008cda2  test    [rcx+1Ch], sil
0x18008cda6  jz      short loc_18008CDB7
0x18008cda8  lea     edx, [rsi+4Fh]
0x18008cdab  mov     r8, r14
0x18008cdae  mov     rcx, [rcx+10h]
0x18008cdb2  call    sub_180073384
0x18008cdb7  mov     eax, 80070006h
0x18008cdbc  jmp     loc_18008D610
0x18008cdc1  lea     rcx, [rbp+4Fh+var_78]
0x18008cdc5  call    sub_180089D74
0x18008cdca  mov     edi, eax
0x18008cdcc  test    eax, eax
0x18008cdce  jns     short loc_18008CE02
0x18008cdd0  mov     rcx, cs:off_18019DE80
0x18008cdd7  cmp     rcx, r15
0x18008cdda  jz      short loc_18008CDFB
0x18008cddc  test    [rcx+1Ch], sil
0x18008cde0  jz      short loc_18008CDFB
0x18008cde2  mov     edx, 51h ; 'Q'
0x18008cde7  mov     [rsp+0C0h+var_A0], eax
0x18008cdeb  mov     r9d, [rbp+4Fh+var_78]
0x18008cdef  mov     r8, r14
0x18008cdf2  mov     rcx, [rcx+10h]
0x18008cdf6  call    sub_18007AEE8
0x18008cdfb  mov     eax, edi
0x18008cdfd  jmp     loc_18008D610
0x18008ce02  mov     [rbp+4Fh+lpMem], rbx
0x18008ce06  mov     r8b, sil
0x18008ce09  mov     edx, 10h
0x18008ce0e  lea     rcx, [rbp+4Fh+lpMem]
0x18008ce12  call    sub_1800CA400
0x18008ce17  mov     r14d, eax
0x18008ce1a  test    eax, eax
0x18008ce1c  jns     short loc_18008CE7D
0x18008ce1e  mov     rdi, [rbp+4Fh+lpMem]
0x18008ce22  test    rdi, rdi
0x18008ce25  jz      short loc_18008CE75
0x18008ce27  mov     rcx, cs:qword_1801A9738; hHeap
0x18008ce2e  test    rcx, rcx
0x18008ce31  jz      short loc_18008CE75
0x18008ce33  mov     r8, rdi; lpMem
0x18008ce36  xor     edx, edx; dwFlags
0x18008ce38  call    cs:HeapFree
0x18008ce3e  test    eax, eax
0x18008ce40  jnz     short loc_18008CE75
0x18008ce42  call    sub_18001B270
0x18008ce47  mov     rcx, cs:off_18019DE80
0x18008ce4e  cmp     rcx, r15
0x18008ce51  jz      short loc_18008CE75
0x18008ce53  test    [rcx+1Ch], sil
0x18008ce57  jz      short loc_18008CE75
0x18008ce59  lea     r8, qword_180146138
0x18008ce60  mov     r9, rdi
0x18008ce63  mov     [rsp+0C0h+var_A0], eax
0x18008ce67  mov     edx, 0Bh
0x18008ce6c  mov     rcx, [rcx+10h]
0x18008ce70  call    sub_18007B188
0x18008ce75  mov     eax, r14d
0x18008ce78  jmp     loc_18008D610
0x18008ce7d  mov     [rbp+4Fh+var_90], rbx
0x18008ce81  call    sub_1800DE950
0x18008ce86  test    eax, eax
0x18008ce88  jz      short loc_18008CEC6
0x18008ce8a  mov     rcx, cs:off_18019DE80
0x18008ce91  cmp     rcx, r15
0x18008ce94  jz      short loc_18008CEB8
0x18008ce96  test    [rcx+1Ch], sil
0x18008ce9a  jz      short loc_18008CEB8
0x18008ce9c  mov     edx, 52h ; 'R'
0x18008cea1  lea     r8, stru_180146770
0x18008cea8  mov     rcx, [rcx+10h]
0x18008ceac  call    sub_180073384
0x18008ceb1  mov     rcx, cs:off_18019DE80
0x18008ceb8  mov     r14d, 7
0x18008cebe  mov     r15d, esi
0x18008cec1  jmp     loc_18008D493
0x18008cec6  mov     edi, [rbp+4Fh+var_78]
0x18008cec9  test    dil, 4
0x18008cecd  jz      loc_18008CF54
0x18008ced3  mov     ecx, edi
0x18008ced5  call    sub_18008AFAC
0x18008ceda  mov     r14d, eax
0x18008cedd  test    eax, eax
0x18008cedf  jns     short loc_18008CF4F
0x18008cee1  mov     rcx, cs:off_18019DE80
0x18008cee8  cmp     rcx, r15
0x18008ceeb  jz      short loc_18008CF0B
0x18008ceed  test    [rcx+1Ch], sil
0x18008cef1  jz      short loc_18008CF0B
0x18008cef3  mov     edx, 53h ; 'S'
0x18008cef8  mov     r9d, eax
0x18008cefb  lea     r8, stru_180146770
0x18008cf02  mov     rcx, [rcx+10h]
0x18008cf06  call    sub_1800733A8
0x18008cf0b  mov     rdi, [rbp+4Fh+lpMem]
0x18008cf0f  test    rdi, rdi
0x18008cf12  jz      loc_18008CE75
0x18008cf18  mov     rcx, cs:qword_1801A9738; hHeap
0x18008cf1f  test    rcx, rcx
0x18008cf22  jz      loc_18008CE75
0x18008cf28  mov     r8, rdi; lpMem
0x18008cf2b  xor     edx, edx; dwFlags
0x18008cf2d  call    cs:HeapFree
0x18008cf33  test    eax, eax
0x18008cf35  jnz     loc_18008CE75
0x18008cf3b  call    sub_18001B270
0x18008cf40  mov     rcx, cs:off_18019DE80
0x18008cf47  cmp     rcx, r15
0x18008cf4a  jmp     loc_18008CE51
0x18008cf4f  test    r14d, r14d
0x18008cf52  jnz     short loc_18008CFD0
0x18008cf54  mov     ecx, edi
0x18008cf56  call    sub_18008B3B8
0x18008cf5b  mov     r14d, eax
0x18008cf5e  test    eax, eax
0x18008cf60  jns     short loc_18008CFD0
0x18008cf62  mov     rcx, cs:off_18019DE80
0x18008cf69  cmp     rcx, r15
0x18008cf6c  jz      short loc_18008CF8C
0x18008cf6e  test    [rcx+1Ch], sil
0x18008cf72  jz      short loc_18008CF8C
0x18008cf74  mov     edx, 54h ; 'T'
0x18008cf79  mov     r9d, eax
0x18008cf7c  lea     r8, stru_180146770
0x18008cf83  mov     rcx, [rcx+10h]
0x18008cf87  call    sub_1800733A8
0x18008cf8c  mov     rdi, [rbp+4Fh+lpMem]
0x18008cf90  test    rdi, rdi
0x18008cf93  jz      loc_18008CE75
0x18008cf99  mov     rcx, cs:qword_1801A9738; hHeap
0x18008cfa0  test    rcx, rcx
0x18008cfa3  jz      loc_18008CE75
0x18008cfa9  mov     r8, rdi; lpMem
0x18008cfac  xor     edx, edx; dwFlags
0x18008cfae  call    cs:HeapFree
0x18008cfb4  test    eax, eax
0x18008cfb6  jnz     loc_18008CE75
0x18008cfbc  call    sub_18001B270
0x18008cfc1  mov     rcx, cs:off_18019DE80
0x18008cfc8  cmp     rcx, r15
0x18008cfcb  jmp     loc_18008CE51
0x18008cfd0  mov     r15d, esi
0x18008cfd3  mov     [rbp+4Fh+var_78], esi
0x18008cfd6  test    r14d, r14d
0x18008cfd9  jnz     loc_18008D48C
0x18008cfdf  lea     rcx, [rbp+4Fh+var_78]
0x18008cfe3  call    sub_18008B958
0x18008cfe8  mov     r14d, eax
0x18008cfeb  test    eax, eax
0x18008cfed  jnz     loc_18008D488
0x18008cff3  xor     edx, edx
0x18008cff5  xor     ecx, ecx
0x18008cff7  call    sub_1800CB1B4
0x18008cffc  test    eax, eax
0x18008cffe  jns     short loc_18008D032
0x18008d000  mov     rcx, cs:off_18019DE80
0x18008d007  lea     r15, off_18019DE80
0x18008d00e  cmp     rcx, r15
0x18008d011  jz      short loc_18008D040
0x18008d013  test    byte ptr [rcx+1Ch], 2
0x18008d017  jz      short loc_18008D040
0x18008d019  lea     edx, [r14+56h]
0x18008d01d  mov     r9d, eax
0x18008d020  lea     r8, stru_180146770
0x18008d027  mov     rcx, [rcx+10h]
0x18008d02b  call    sub_1800733A8
0x18008d030  jmp     short loc_18008D039
0x18008d032  lea     r15, off_18019DE80
0x18008d039  mov     rcx, cs:off_18019DE80
0x18008d040  mov     eax, edi
0x18008d042  and     eax, 1D0h
0x18008d047  jz      loc_18008D1EC
0x18008d04d  cmp     eax, 40h ; '@'
0x18008d050  jz      loc_18008D10C
0x18008d056  cmp     eax, 10h
0x18008d059  jz      loc_18008D10C
0x18008d05f  cmp     eax, 80h
0x18008d064  jz      loc_18008D10C
0x18008d06a  cmp     eax, 100h
0x18008d06f  jz      loc_18008D10C
0x18008d075  cmp     rcx, r15
0x18008d078  jz      short loc_18008D09C
0x18008d07a  test    [rcx+1Ch], sil
0x18008d07e  jz      short loc_18008D09C
0x18008d080  mov     edx, 57h ; 'W'
0x18008d085  mov     [rsp+0C0h+var_A0], eax
0x18008d089  mov     r9d, edi
0x18008d08c  lea     r8, stru_180146770
0x18008d093  mov     rcx, [rcx+10h]
0x18008d097  call    sub_18007AEE8
0x18008d09c  mov     rdi, [rbp+4Fh+lpMem]
0x18008d0a0  test    rdi, rdi
0x18008d0a3  jz      loc_18008D60B
0x18008d0a9  mov     rcx, cs:qword_1801A9738; hHeap
0x18008d0b0  test    rcx, rcx
0x18008d0b3  jz      loc_18008D60B
0x18008d0b9  mov     r8, rdi; lpMem
0x18008d0bc  xor     edx, edx; dwFlags
0x18008d0be  call    cs:HeapFree
0x18008d0c4  test    eax, eax
0x18008d0c6  jnz     loc_18008D60B
0x18008d0cc  call    sub_18001B270
0x18008d0d1  mov     rcx, cs:off_18019DE80
0x18008d0d8  cmp     rcx, r15
0x18008d0db  jz      loc_18008D60B
0x18008d0e1  test    [rcx+1Ch], sil
0x18008d0e5  jz      loc_18008D60B
0x18008d0eb  mov     edx, 0Bh
0x18008d0f0  mov     [rsp+0C0h+var_A0], eax
0x18008d0f4  mov     r9, rdi
0x18008d0f7  lea     r8, qword_180146138
0x18008d0fe  mov     rcx, [rcx+10h]
0x18008d102  call    sub_18007B188
0x18008d107  jmp     loc_18008D60B
0x18008d10c  cmp     rcx, r15
0x18008d10f  jz      short loc_18008D133
0x18008d111  test    byte ptr [rcx+1Ch], 2
0x18008d115  jz      short loc_18008D133
0x18008d117  mov     edx, 58h ; 'X'
0x18008d11c  mov     [rsp+0C0h+var_A0], edi
0x18008d120  mov     r9d, edi
0x18008d123  lea     r8, stru_180146770
0x18008d12a  mov     rcx, [rcx+10h]
0x18008d12e  call    sub_18007AEE8
0x18008d133  mov     r9d, edi
0x18008d136  mov     r8, r13
0x18008d139  mov     rdx, r12
0x18008d13c  lea     rcx, [rbp+4Fh+var_90]
0x18008d140  call    sub_18008BAFC
0x18008d145  mov     r14d, eax
0x18008d148  test    eax, eax
0x18008d14a  jns     loc_18008D5C8
0x18008d150  mov     rcx, cs:off_18019DE80
0x18008d157  cmp     rcx, r15
0x18008d15a  jz      short loc_18008D182
0x18008d15c  test    [rcx+1Ch], sil
0x18008d160  jz      short loc_18008D182
0x18008d162  mov     edx, 59h ; 'Y'
0x18008d167  mov     [rsp+0C0h+var_98], eax
0x18008d16b  mov     [rsp+0C0h+var_A0], edi
0x18008d16f  mov     r9d, edi
  ... truncated ...
```

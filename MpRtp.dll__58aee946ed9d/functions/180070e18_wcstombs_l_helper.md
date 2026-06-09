# _wcstombs_l_helper

- ea: `0x180070e18`
- end: `0x180071298`
- name: `_wcstombs_l_helper`
- size: `1152`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x180069c28`

## callees

- `0x18000ace4`
- `0x18000b4c8`
- `0x18000be88`
- `0x1800115a0`
- `0x18003d734`
- `0x18003d758`
- `0x18003d810`
- `0x1800408dc`
- `0x18005fefc`
- `0x180070e18`
- `0x180073928`
- `0x18007c110`
- `0x18009dcb8`
- `0x1800c572c`
- `0x1800d4220`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x180070fcb`
- `MpClient!MpFreeMemory` at `0x1800710ef`
- `MpClient!MpFreeMemory` at `0x1800711d2`
- `MpClient!MpFreeMemory` at `0x180070fcb`
- `MpClient!MpFreeMemory` at `0x1800710ef`
- `MpClient!MpFreeMemory` at `0x1800711d2`
- `KERNEL32!GetTickCount` at `0x180070e9a`
- `KERNEL32!GetTickCount` at `0x180070e9a`
- `KERNEL32!CloseHandle` at `0x180071158`
- `KERNEL32!CloseHandle` at `0x180071158`
- `ADVAPI32!SetThreadToken` at `0x1800710d4`
- `ADVAPI32!SetThreadToken` at `0x1800710d4`
- `ADVAPI32!RevertToSelf` at `0x18007111b`
- `ADVAPI32!RevertToSelf` at `0x18007116f`
- `ADVAPI32!RevertToSelf` at `0x18007111b`
- `ADVAPI32!RevertToSelf` at `0x18007116f`

## pseudocode

```c
__int64 __fastcall wcstombs_l_helper(__int64 a1, wchar_t **a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  int v6; // esi
  DWORD TickCount; // esi
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdi
  unsigned int v11; // ecx
  _BYTE *v12; // rax
  unsigned int v13; // esi
  unsigned int v14; // r13d
  wchar_t **v15; // rbx
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // r13
  __int64 v19; // rcx
  int v20; // eax
  HANDLE v21; // rbx
  bool v22; // r13
  _QWORD *v23; // rcx
  unsigned int v24; // eax
  __int64 v26; // [rsp+30h] [rbp-50h] BYREF
  __int64 v27; // [rsp+38h] [rbp-48h] BYREF
  __int64 v28; // [rsp+40h] [rbp-40h]
  HANDLE Token; // [rsp+48h] [rbp-38h] BYREF
  wchar_t **v30; // [rsp+50h] [rbp-30h]
  void **v31; // [rsp+58h] [rbp-28h] BYREF
  int v32; // [rsp+60h] [rbp-20h]
  char v33; // [rsp+68h] [rbp-18h]

  v30 = a2;
  v5 = 1000;
  v28 = a1;
  v27 = 0;
  v26 = 0;
  if ( !*a2 )
  {
    if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 1) != 0 )
      sub_18003D734(*((_QWORD *)off_180119DF0 + 2), 95, &stru_1800F0588);
    return (unsigned int)-2147467259;
  }
  TickCount = GetTickCount();
  sub_18007C110(lpMem, &v26);
  v10 = v26;
  if ( v26 )
    v5 = *(_DWORD *)(v26 + 44);
  v11 = *(_DWORD *)(a1 + 520);
  if ( TickCount < v11 )
  {
    v14 = -1;
    v12 = off_180119DF0;
    if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 2) != 0 )
    {
      sub_180073928(*((_QWORD *)off_180119DF0 + 2), v8, v9, TickCount, v11, -2147024362);
      v12 = off_180119DF0;
    }
  }
  else
  {
    v12 = off_180119DF0;
    v13 = TickCount - v11;
    v14 = v13;
    if ( v13 >= v5 )
    {
LABEL_11:
      if ( v12 != (_BYTE *)&off_180119DF0 && (v12[28] & 0x10) != 0 )
      {
        _mm_lfence();
        sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 99, &stru_1800F0588, v14);
      }
LABEL_14:
      v15 = v30;
      v33 = 0;
      v16 = sub_18000BE88(*v30);
      if ( v16 < 0 )
      {
        v17 = off_180119DF0;
        if ( off_180119DF0 == (_UNKNOWN *)&off_180119DF0 || (*((_BYTE *)off_180119DF0 + 28) & 1) == 0 )
        {
LABEL_19:
          LODWORD(v26) = 0;
          if ( !v33 )
          {
            if ( v17 != &off_180119DF0 && (*((_BYTE *)v17 + 28) & 0x10) != 0 )
              sub_18003D810(v17[2], 103, &stru_1800F0588, *v15);
            if ( *a3 )
            {
              MpFreeMemory(*a3);
              *a3 = 0;
            }
            v6 = sub_18005FEFC(*v15, a3, &v27, &v26);
            goto LABEL_67;
          }
          if ( v17 != &off_180119DF0 && (*((_BYTE *)v17 + 28) & 0x10) != 0 )
            sub_18003D810(v17[2], 101, &stru_1800F0588, *v15);
          v18 = v28;
          v31 = &RealtimeProtection::CThreadImpersonation::`vftable';
          v32 = 0;
          v6 = sub_18009DCB8(&v31, *(unsigned int *)(v28 + 20), *(unsigned int *)(v28 + 28));
          if ( v6 >= 0 )
          {
            if ( *a3 )
            {
              MpFreeMemory(*a3);
              *a3 = 0;
            }
            v6 = sub_18005FEFC(*v15, a3, &v27, &v26);
            goto LABEL_55;
          }
          v19 = *(unsigned int *)(v18 + 24);
          if ( !(_DWORD)v19 )
          {
LABEL_55:
            v23 = off_180119DF0;
LABEL_56:
            if ( !v32 )
              goto LABEL_68;
            if ( !RevertToSelf() )
            {
              v24 = sub_18000B4C8();
              v23 = off_180119DF0;
              if ( off_180119DF0 == (_UNKNOWN *)&off_180119DF0 || (*((_BYTE *)off_180119DF0 + 28) & 2) == 0 )
              {
LABEL_68:
                if ( v6 < 0 )
                {
                  if ( v6 == -2147024894 )
                  {
                    if ( v23 != &off_180119DF0 && (*((_BYTE *)v23 + 28) & 0x10) != 0 )
                      sub_1800408DC(v23[2], 104, (unsigned int)&stru_1800F0588, *(_QWORD *)(v28 + 480), 2);
                  }
                  else if ( v23 != &off_180119DF0 && (*((_BYTE *)v23 + 28) & 1) != 0 )
                  {
                    sub_1800408DC(v23[2], 105, (unsigned int)&stru_1800F0588, *(_QWORD *)(v28 + 480), v6);
                  }
                }
                goto LABEL_76;
              }
              sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 34, qword_1800F71A8, v24);
            }
LABEL_67:
            v23 = off_180119DF0;
            goto LABEL_68;
          }
          Token = 0;
          v20 = sub_1800C572C(v19, &Token);
          v21 = Token;
          v6 = v20;
          if ( v20 < 0 )
          {
            v23 = off_180119DF0;
            if ( off_180119DF0 == (_UNKNOWN *)&off_180119DF0 || (*((_BYTE *)off_180119DF0 + 28) & 2) == 0 )
              goto LABEL_53;
            sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 102, &stru_1800F0588, (unsigned int)v20);
          }
          else
          {
            v22 = Token && SetThreadToken(0, Token);
            if ( *a3 )
            {
              MpFreeMemory(*a3);
              *a3 = 0;
            }
            v6 = sub_18005FEFC(*v30, a3, &v27, &v26);
            if ( v22 )
              RevertToSelf();
          }
          v23 = off_180119DF0;
LABEL_53:
          if ( !v21 )
            goto LABEL_56;
          CloseHandle(v21);
          goto LABEL_55;
        }
        sub_1800408DC(*((_QWORD *)off_180119DF0 + 2), 100, (unsigned int)&stru_1800F0588, (unsigned int)*v15, v16);
      }
      v17 = off_180119DF0;
      goto LABEL_19;
    }
    v5 -= v13;
  }
  if ( !v5 )
    goto LABEL_11;
  _mm_lfence();
  if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 0x10) != 0 )
    sub_18003D758(*((_QWORD *)off_180119DF0 + 2), 97, &stru_1800F0588, v5);
  if ( (unsigned __int8)sub_18000ACE4(*((_QWORD *)lpMem + 290), v5) )
    goto LABEL_14;
  if ( off_180119DF0 != (_UNKNOWN *)&off_180119DF0 && (*((_BYTE *)off_180119DF0 + 28) & 2) != 0 )
    sub_18003D734(*((_QWORD *)off_180119DF0 + 2), 98, &stru_1800F0588);
  v6 = -2147467260;
LABEL_76:
  if ( v10 && _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 8), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180070e18  mov     [rsp-38h+arg_18], rbx
0x180070e1d  push    rbp
0x180070e1e  push    rsi
0x180070e1f  push    rdi
0x180070e20  push    r12
0x180070e22  push    r13
0x180070e24  push    r14
0x180070e26  push    r15
0x180070e28  mov     rbp, rsp
0x180070e2b  sub     rsp, 80h
0x180070e32  mov     rax, cs:__security_cookie
0x180070e39  xor     rax, rsp
0x180070e3c  mov     [rbp+var_10], rax
0x180070e40  xor     r15d, r15d
0x180070e43  mov     [rbp+var_30], rdx
0x180070e47  mov     r12, r8
0x180070e4a  mov     r14, rcx
0x180070e4d  mov     ebx, 3E8h
0x180070e52  mov     [rbp+var_40], rcx
0x180070e56  mov     [rbp+var_48], r15
0x180070e5a  mov     [rbp+var_50], r15
0x180070e5e  cmp     [rdx], r15
0x180070e61  jnz     short loc_180070E9A
0x180070e63  mov     rcx, cs:off_180119DF0
0x180070e6a  lea     r14, off_180119DF0
0x180070e71  cmp     rcx, r14
0x180070e74  jz      short loc_180070E90
0x180070e76  test    byte ptr [rcx+1Ch], 1
0x180070e7a  jz      short loc_180070E90
0x180070e7c  mov     rcx, [rcx+10h]
0x180070e80  lea     edx, [r15+5Fh]
0x180070e84  lea     r8, stru_1800F0588
0x180070e8b  call    sub_18003D734
0x180070e90  mov     esi, 80004005h
0x180070e95  jmp     loc_18007126F
0x180070e9a  call    cs:GetTickCount
0x180070ea0  mov     rcx, cs:lpMem
0x180070ea7  lea     rdx, [rbp+var_50]
0x180070eab  mov     esi, eax
0x180070ead  call    sub_18007C110
0x180070eb2  mov     rdi, [rbp+var_50]
0x180070eb6  test    rdi, rdi
0x180070eb9  jz      short loc_180070EBE
0x180070ebb  mov     ebx, [rdi+2Ch]
0x180070ebe  mov     ecx, [r14+208h]
0x180070ec5  lea     r15, stru_1800F0588
0x180070ecc  lea     r14, off_180119DF0
0x180070ed3  cmp     esi, ecx
0x180070ed5  jb      loc_180070FF3
0x180070edb  mov     rax, cs:off_180119DF0
0x180070ee2  sub     esi, ecx
0x180070ee4  mov     r13d, esi
0x180070ee7  cmp     esi, ebx
0x180070ee9  jnb     short loc_180070EF2
0x180070eeb  sub     ebx, esi
0x180070eed  jmp     loc_180071028
0x180070ef2  xor     esi, esi
0x180070ef4  cmp     rax, r14
0x180070ef7  jz      short loc_180070F1D
0x180070ef9  test    byte ptr [rax+1Ch], 10h
0x180070efd  jz      short loc_180070F1D
0x180070eff  lfence
0x180070f02  mov     rcx, cs:off_180119DF0
0x180070f09  mov     edx, 63h ; 'c'
0x180070f0e  mov     r9d, r13d
0x180070f11  mov     r8, r15
0x180070f14  mov     rcx, [rcx+10h]
0x180070f18  call    sub_18003D758
0x180070f1d  mov     rbx, [rbp+var_30]
0x180070f21  lea     rdx, [rbp+var_18]
0x180070f25  xor     r8d, r8d
0x180070f28  mov     [rbp+var_18], sil
0x180070f2c  mov     rcx, [rbx]; Str1
0x180070f2f  call    sub_18000BE88
0x180070f34  test    eax, eax
0x180070f36  jns     short loc_180070F62
0x180070f38  mov     rcx, cs:off_180119DF0
0x180070f3f  cmp     rcx, r14
0x180070f42  jz      short loc_180070F69
0x180070f44  test    byte ptr [rcx+1Ch], 1
0x180070f48  jz      short loc_180070F69
0x180070f4a  mov     r9, [rbx]
0x180070f4d  mov     edx, 64h ; 'd'
0x180070f52  mov     rcx, [rcx+10h]
0x180070f56  mov     r8, r15
0x180070f59  mov     [rsp+80h+var_60], eax
0x180070f5d  call    sub_1800408DC
0x180070f62  mov     rcx, cs:off_180119DF0
0x180070f69  mov     dword ptr [rbp+var_50], esi
0x180070f6c  cmp     [rbp+var_18], sil
0x180070f70  jz      loc_1800711AA
0x180070f76  cmp     rcx, r14
0x180070f79  jz      short loc_180070F95
0x180070f7b  test    byte ptr [rcx+1Ch], 10h
0x180070f7f  jz      short loc_180070F95
0x180070f81  mov     r9, [rbx]
0x180070f84  mov     edx, 65h ; 'e'
0x180070f89  mov     rcx, [rcx+10h]
0x180070f8d  mov     r8, r15
0x180070f90  call    sub_18003D810
0x180070f95  mov     r13, [rbp+var_40]
0x180070f99  lea     rax, ??_7CThreadImpersonation@RealtimeProtection@@6B@
0x180070fa0  lea     rcx, [rbp+var_28]
0x180070fa4  mov     [rbp+var_28], rax
0x180070fa8  mov     [rbp+var_20], esi
0x180070fab  mov     r8d, [r13+1Ch]
0x180070faf  mov     edx, [r13+14h]
0x180070fb3  call    sub_18009DCB8
0x180070fb8  mov     esi, eax
0x180070fba  test    eax, eax
0x180070fbc  js      loc_1800710A3
0x180070fc2  mov     rcx, [r12]
0x180070fc6  test    rcx, rcx
0x180070fc9  jz      short loc_180070FD9
0x180070fcb  call    cs:MpFreeMemory
0x180070fd1  mov     qword ptr [r12], 0
0x180070fd9  mov     rcx, [rbx]
0x180070fdc  lea     r9, [rbp+var_50]
0x180070fe0  lea     r8, [rbp+var_48]
0x180070fe4  mov     rdx, r12
0x180070fe7  call    sub_18005FEFC
0x180070fec  mov     esi, eax
0x180070fee  jmp     loc_18007115E
0x180070ff3  or      r13d, 0FFFFFFFFh
0x180070ff7  mov     rax, cs:off_180119DF0
0x180070ffe  cmp     rax, r14
0x180071001  jz      short loc_180071028
0x180071003  test    byte ptr [rax+1Ch], 2
0x180071007  jz      short loc_180071028
0x180071009  mov     [rsp+80h+var_58], 80070216h
0x180071011  mov     r9d, esi
0x180071014  mov     [rsp+80h+var_60], ecx
0x180071018  mov     rcx, [rax+10h]
0x18007101c  call    sub_180073928
0x180071021  mov     rax, cs:off_180119DF0
0x180071028  xor     esi, esi
0x18007102a  test    ebx, ebx
0x18007102c  jz      loc_180070EF4
0x180071032  lfence
0x180071035  mov     rcx, cs:off_180119DF0
0x18007103c  cmp     rcx, r14
0x18007103f  jz      short loc_180071059
0x180071041  test    byte ptr [rcx+1Ch], 10h
0x180071045  jz      short loc_180071059
0x180071047  mov     rcx, [rcx+10h]
0x18007104b  lea     edx, [rsi+61h]
0x18007104e  mov     r9d, ebx
0x180071051  mov     r8, r15
0x180071054  call    sub_18003D758
0x180071059  mov     rcx, cs:lpMem
0x180071060  mov     edx, ebx
0x180071062  mov     rcx, [rcx+910h]
0x180071069  call    sub_18000ACE4
0x18007106e  test    al, al
0x180071070  jnz     loc_180070F1D
0x180071076  mov     rcx, cs:off_180119DF0
0x18007107d  cmp     rcx, r14
0x180071080  jz      short loc_180071099
0x180071082  test    byte ptr [rcx+1Ch], 2
0x180071086  jz      short loc_180071099
0x180071088  mov     rcx, [rcx+10h]
0x18007108c  mov     edx, 62h ; 'b'
0x180071091  mov     r8, r15
0x180071094  call    sub_18003D734
0x180071099  mov     esi, 80004004h
0x18007109e  jmp     loc_180071246
0x1800710a3  mov     ecx, [r13+18h]
0x1800710a7  test    ecx, ecx
0x1800710a9  jz      loc_18007115E
0x1800710af  lea     rdx, [rbp+Token]
0x1800710b3  mov     [rbp+Token], 0
0x1800710bb  call    sub_1800C572C
0x1800710c0  mov     rbx, [rbp+Token]
0x1800710c4  mov     esi, eax
0x1800710c6  test    eax, eax
0x1800710c8  js      short loc_180071123
0x1800710ca  test    rbx, rbx
0x1800710cd  jz      short loc_1800710E3
0x1800710cf  mov     rdx, rbx; Token
0x1800710d2  xor     ecx, ecx; Thread
0x1800710d4  call    cs:SetThreadToken
0x1800710da  test    eax, eax
0x1800710dc  jz      short loc_1800710E3
0x1800710de  mov     r13b, 1
0x1800710e1  jmp     short loc_1800710E6
0x1800710e3  xor     r13b, r13b
0x1800710e6  mov     rcx, [r12]
0x1800710ea  test    rcx, rcx
0x1800710ed  jz      short loc_1800710FD
0x1800710ef  call    cs:MpFreeMemory
0x1800710f5  mov     qword ptr [r12], 0
0x1800710fd  mov     rax, [rbp+var_30]
0x180071101  lea     r9, [rbp+var_50]
0x180071105  lea     r8, [rbp+var_48]
0x180071109  mov     rdx, r12
0x18007110c  mov     rcx, [rax]
0x18007110f  call    sub_18005FEFC
0x180071114  mov     esi, eax
0x180071116  test    r13b, r13b
0x180071119  jz      short loc_180071149
0x18007111b  call    cs:RevertToSelf
0x180071121  jmp     short loc_180071149
0x180071123  mov     rcx, cs:off_180119DF0
0x18007112a  cmp     rcx, r14
0x18007112d  jz      short loc_180071150
0x18007112f  test    byte ptr [rcx+1Ch], 2
0x180071133  jz      short loc_180071150
0x180071135  mov     rcx, [rcx+10h]
0x180071139  mov     edx, 66h ; 'f'
0x18007113e  mov     r9d, eax
0x180071141  mov     r8, r15
0x180071144  call    sub_18003D758
0x180071149  mov     rcx, cs:off_180119DF0
0x180071150  test    rbx, rbx
0x180071153  jz      short loc_180071165
0x180071155  mov     rcx, rbx; hObject
0x180071158  call    cs:CloseHandle
0x18007115e  mov     rcx, cs:off_180119DF0
0x180071165  cmp     [rbp+var_20], 0
0x180071169  jz      loc_1800711F8
0x18007116f  call    cs:RevertToSelf
0x180071175  test    eax, eax
0x180071177  jnz     short loc_1800711F1
0x180071179  call    sub_18000B4C8
0x18007117e  mov     rcx, cs:off_180119DF0
0x180071185  cmp     rcx, r14
0x180071188  jz      short loc_1800711F8
0x18007118a  test    byte ptr [rcx+1Ch], 2
0x18007118e  jz      short loc_1800711F8
0x180071190  mov     rcx, [rcx+10h]
0x180071194  lea     r8, qword_1800F71A8
0x18007119b  mov     edx, 22h ; '"'
0x1800711a0  mov     r9d, eax
0x1800711a3  call    sub_18003D758
0x1800711a8  jmp     short loc_1800711F1
0x1800711aa  cmp     rcx, r14
0x1800711ad  jz      short loc_1800711C9
0x1800711af  test    byte ptr [rcx+1Ch], 10h
0x1800711b3  jz      short loc_1800711C9
0x1800711b5  mov     r9, [rbx]
0x1800711b8  mov     edx, 67h ; 'g'
0x1800711bd  mov     rcx, [rcx+10h]
0x1800711c1  mov     r8, r15
0x1800711c4  call    sub_18003D810
0x1800711c9  mov     rcx, [r12]
0x1800711cd  test    rcx, rcx
0x1800711d0  jz      short loc_1800711DC
0x1800711d2  call    cs:MpFreeMemory
0x1800711d8  mov     [r12], rsi
0x1800711dc  mov     rcx, [rbx]
0x1800711df  lea     r9, [rbp+var_50]
0x1800711e3  lea     r8, [rbp+var_48]
0x1800711e7  mov     rdx, r12
0x1800711ea  call    sub_18005FEFC
0x1800711ef  mov     esi, eax
0x1800711f1  mov     rcx, cs:off_180119DF0
0x1800711f8  test    esi, esi
0x1800711fa  jns     short loc_180071246
0x1800711fc  mov     eax, 80070002h
0x180071201  cmp     esi, eax
0x180071203  jnz     short loc_18007121B
0x180071205  cmp     rcx, r14
0x180071208  jz      short loc_180071246
0x18007120a  test    byte ptr [rcx+1Ch], 10h
0x18007120e  jz      short loc_180071246
0x180071210  mov     edx, 68h ; 'h'
0x180071215  mov     [rsp+80h+var_60], eax
0x180071219  jmp     short loc_18007122F
0x18007121b  cmp     rcx, r14
0x18007121e  jz      short loc_180071246
0x180071220  test    byte ptr [rcx+1Ch], 1
0x180071224  jz      short loc_180071246
0x180071226  mov     edx, 69h ; 'i'
0x18007122b  mov     [rsp+80h+var_60], esi
0x18007122f  mov     r9, [rbp+var_40]
0x180071233  mov     r8, r15
0x180071236  mov     rcx, [rcx+10h]
0x18007123a  mov     r9, [r9+1E0h]
0x180071241  call    sub_1800408DC
0x180071246  test    rdi, rdi
0x180071249  jz      short loc_18007126F
0x18007124b  or      eax, 0FFFFFFFFh
0x18007124e  lock xadd [rdi+8], eax
0x180071253  sub     eax, 1
0x180071256  jg      short loc_18007126F
0x180071258  lfence
0x18007125b  mov     rax, [rdi]
0x18007125e  mov     edx, 1
0x180071263  mov     rcx, rdi
0x180071266  mov     rax, [rax]
0x180071269  call    cs:__guard_dispatch_icall_fptr
0x18007126f  mov     eax, esi
0x180071271  mov     rcx, [rbp+var_10]
0x180071275  xor     rcx, rsp; StackCookie
0x180071278  call    __security_check_cookie
0x18007127d  mov     rbx, [rsp+80h+arg_18]
0x180071285  add     rsp, 80h
0x18007128c  pop     r15
0x18007128e  pop     r14
0x180071290  pop     r13
  ... truncated ...
```

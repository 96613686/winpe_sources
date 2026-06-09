# sub_1800DAAD0

- ea: `0x1800daad0`
- end: `0x1800db46c`
- name: `sub_1800DAAD0`
- size: `2460`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callees

- `0x18001b270`
- `0x18003b830`
- `0x18003bcb0`
- `0x18003c020`
- `0x18003c090`
- `0x180056720`
- `0x1800720a4`
- `0x180073384`
- `0x1800733a8`
- `0x18007b188`
- `0x180089530`
- `0x1800ca400`
- `0x1800daad0`
- `0x1800dcd58`
- `0x180125d60`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800dacb3`
- `KERNEL32!HeapFree` at `0x1800dadd9`
- `KERNEL32!HeapFree` at `0x1800dae25`
- `KERNEL32!HeapFree` at `0x1800daec6`
- `KERNEL32!HeapFree` at `0x1800daf16`
- `KERNEL32!HeapFree` at `0x1800daf92`
- `KERNEL32!HeapFree` at `0x1800dafde`
- `KERNEL32!HeapFree` at `0x1800db077`
- `KERNEL32!HeapFree` at `0x1800db0c3`
- `KERNEL32!HeapFree` at `0x1800db134`
- `KERNEL32!HeapFree` at `0x1800db180`
- `KERNEL32!HeapFree` at `0x1800db1f3`
- `KERNEL32!HeapFree` at `0x1800db23f`
- `KERNEL32!HeapFree` at `0x1800dacb3`
- `KERNEL32!HeapFree` at `0x1800dadd9`
- `KERNEL32!HeapFree` at `0x1800dae25`
- `KERNEL32!HeapFree` at `0x1800daec6`
- `KERNEL32!HeapFree` at `0x1800daf16`
- `KERNEL32!HeapFree` at `0x1800daf92`
- `KERNEL32!HeapFree` at `0x1800dafde`
- `KERNEL32!HeapFree` at `0x1800db077`
- `KERNEL32!HeapFree` at `0x1800db0c3`
- `KERNEL32!HeapFree` at `0x1800db134`
- `KERNEL32!HeapFree` at `0x1800db180`
- `KERNEL32!HeapFree` at `0x1800db1f3`
- `KERNEL32!HeapFree` at `0x1800db23f`

## string_xrefs

- `0x1800db420`: `PlatformLastUpdated`
- `0x1800dab80`: `Signature Updates`
- `0x1800db3f4`: `Signature Updates`
- `0x1800db3cf`: `InstallLocation`
- `0x1800db374`: `Miscellaneous Configuration`
- `0x1800db398`: `MpConfig_FastMiscConfig`

## pseudocode

```c
__int64 __fastcall sub_1800DAAD0(__int64 a1, int a2, unsigned int *a3, __int64 a4, int *a5)
{
  unsigned int *v5; // rbx
  __int64 v7; // rdi
  _QWORD *i; // rbx
  _QWORD *v9; // rsi
  unsigned __int64 v10; // rdi
  unsigned int v11; // edi
  unsigned int v12; // r12d
  int v13; // eax
  unsigned int v14; // r13d
  LPVOID v15; // rbx
  int v16; // eax
  _DWORD *v18; // rbx
  int v19; // eax
  int v20; // eax
  unsigned int v21; // r12d
  LPVOID v22; // r14
  int v23; // eax
  int v24; // eax
  _DWORD *v25; // r14
  int v26; // eax
  int v27; // eax
  int v28; // eax
  unsigned int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  unsigned int v38; // [rsp+30h] [rbp-D0h]
  unsigned int *v40; // [rsp+38h] [rbp-C8h]
  LPVOID lpMem[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h]
  _QWORD v43[18]; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+F0h] [rbp-10h] BYREF
  LPVOID v45; // [rsp+F8h] [rbp-8h] BYREF
  _DWORD v46[4]; // [rsp+100h] [rbp+0h] BYREF

  v42 = a4;
  v5 = a3;
  v40 = a3;
  if ( !a1 || a2 >= 2 || !a3 || !a4 && *a3 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 66, &stru_18014B088, 2147942487LL);
    return 2147942487LL;
  }
  v7 = -1;
  if ( !a5
    || *a5 != 5
    || (unsigned int)sub_180056720(a1, L".")
    && (unsigned int)sub_180056720(a1, L"Features")
    && (unsigned int)sub_180056720(a1, L"Signature Updates") )
  {
    if ( dword_1801A99A0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)TlsIndex)
                                     + 16LL) )
    {
      sub_18003C090(&dword_1801A99A0);
      if ( dword_1801A99A0 == -1 )
      {
        xmmword_1801A9988 = 0;
        qword_1801A9998 = 0;
        v43[0] = L".";
        v43[1] = L"Miscellaneous Configuration";
        v43[2] = L"ProductFeature";
        v43[3] = L"ProductGUID";
        v43[4] = L"MpConfig_FastMiscConfig";
        v43[5] = L"BetaPlatform";
        v43[6] = L"PartnerGUID";
        v43[7] = L"ManagedDefenderProductType";
        v43[8] = L"PassiveMode";
        v43[9] = L"InstallLocation";
        v43[10] = L"Features";
        v43[11] = L"SenseOrgId";
        v43[12] = L"ForcePassiveMode";
        v43[13] = L"Signature Updates";
        v43[14] = L"EngineVersion";
        v43[15] = L"AVSignatureVersion";
        v43[16] = L"ASSignatureVersion";
        v43[17] = L"PlatformLastUpdated";
        lpMem[0] = v43;
        lpMem[1] = &v44;
        sub_1800720A4(&xmmword_1801A9988, lpMem);
        atexit(sub_18012F9A0);
        sub_18003C020(&dword_1801A99A0);
      }
    }
    v9 = (_QWORD *)*((_QWORD *)&xmmword_1801A9988 + 1);
    for ( i = (_QWORD *)xmmword_1801A9988; ; ++i )
    {
      if ( i == v9 )
      {
        v5 = v40;
        goto LABEL_18;
      }
      if ( *i == a1 || !(unsigned int)sub_180056720(*i, a1) )
        break;
    }
    return 2147500033LL;
  }
LABEL_18:
  v46[0] = -780278114;
  v46[1] = 1333519253;
  v46[2] = -139157869;
  v46[3] = 554002858;
  do
    ++v7;
  while ( *(_WORD *)(a1 + 2 * v7) );
  v10 = 2LL * (unsigned int)v7;
  if ( v10 > 0xFFFFFFFF )
  {
    v36 = off_18019DE80;
    if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
      return 2147942934LL;
    v37 = 67;
    goto LABEL_127;
  }
  v11 = v10 + 2;
  v12 = v11 + 36;
  if ( v11 >= 0xFFFFFFDC )
  {
    v36 = off_18019DE80;
    if ( off_18019DE80 == (_UNKNOWN *)&off_18019DE80 || (*((_BYTE *)off_18019DE80 + 28) & 1) == 0 )
      return 2147942934LL;
    v37 = 68;
LABEL_127:
    sub_1800733A8(v36[2], v37, &stru_18014B088, 2147942934LL);
    return 2147942934LL;
  }
  v38 = *v5;
  lpMem[0] = 0;
  LOBYTE(a3) = 1;
  v13 = sub_1800CA400(lpMem, v12, a3, a4);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 69, &stru_18014B088, (unsigned int)v13);
    v15 = lpMem[0];
    if ( lpMem[0] )
    {
      if ( qword_1801A9738 )
      {
        if ( !HeapFree(qword_1801A9738, 0, lpMem[0]) )
        {
          v16 = sub_18001B270();
          if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
            sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v15, v16);
        }
      }
    }
    return v14;
  }
  v18 = lpMem[0];
  *(_DWORD *)lpMem[0] = v12;
  v18[7] = v38;
  v18[8] = v11;
  v18[5] = a5 != 0;
  if ( a5 )
    v19 = *a5;
  else
    v19 = 0;
  v18[6] = v19;
  v18[4] = a2;
  sub_180125D60(v18 + 9, a1, v11);
  *((_QWORD *)v18 + 1) = 36;
  v44 = 0;
  v45 = 0;
  v20 = sub_180089530((unsigned int)v46, v12, (_DWORD)v18, (unsigned int)&v44, (__int64)&v45);
  v21 = v20;
  if ( v20 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 70, &stru_18014B088, (unsigned int)v20);
    v22 = v45;
    if ( v45 )
    {
      if ( !qword_1801A9738 )
        return v21;
      if ( !HeapFree(qword_1801A9738, 0, v45) )
      {
        v23 = sub_18001B270();
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v22, v23);
      }
    }
    if ( qword_1801A9738 )
    {
      if ( !HeapFree(qword_1801A9738, 0, v18) )
      {
        v24 = sub_18001B270();
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v18, v24);
      }
    }
    return v21;
  }
  v25 = v45;
  if ( !v45 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    {
      sub_180073384(*((_QWORD *)off_18019DE80 + 2), (unsigned int)((_DWORD)v45 + 71), &stru_18014B088);
      v25 = v45;
    }
    if ( v25 )
    {
      if ( !qword_1801A9738 )
        return 2147549183LL;
      if ( !HeapFree(qword_1801A9738, 0, v25) )
      {
        v26 = sub_18001B270();
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v25, v26);
      }
    }
    if ( qword_1801A9738 && !HeapFree(qword_1801A9738, 0, v18) )
      goto LABEL_78;
    return 2147549183LL;
  }
  if ( v44 != *(_DWORD *)v45 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
    {
      sub_1800DCD58(*((_QWORD *)off_18019DE80 + 2));
      v25 = v45;
    }
    if ( v25 )
    {
      if ( !qword_1801A9738 )
        return 2147549183LL;
      if ( !HeapFree(qword_1801A9738, 0, v25) )
      {
        v27 = sub_18001B270();
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v25, v27);
      }
    }
    if ( qword_1801A9738 && !HeapFree(qword_1801A9738, 0, v18) )
    {
LABEL_78:
      v28 = sub_18001B270();
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
        sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v18, v28);
      return 2147549183LL;
    }
    return 2147549183LL;
  }
  if ( a5 )
    *a5 = *((_DWORD *)v45 + 1);
  *v40 = v25[2];
  if ( v42 )
  {
    v29 = v25[2];
    if ( v38 < v29 )
    {
      if ( qword_1801A9738 )
      {
        if ( !HeapFree(qword_1801A9738, 0, v25) )
        {
          v30 = sub_18001B270();
          if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
            sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v25, v30);
        }
        if ( qword_1801A9738 )
        {
          if ( !HeapFree(qword_1801A9738, 0, v18) )
          {
            v31 = sub_18001B270();
            if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
              sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v18, v31);
          }
        }
      }
      return 2147942634LL;
    }
    if ( v29 > v25[3] )
    {
      if ( qword_1801A9738 )
      {
        if ( !HeapFree(qword_1801A9738, 0, v25) )
        {
          v32 = sub_18001B270();
          if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
            sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v25, v32);
        }
        if ( qword_1801A9738 )
        {
          if ( !HeapFree(qword_1801A9738, 0, v18) )
          {
            v33 = sub_18001B270();
            if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
              sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v18, v33);
          }
        }
      }
      return 2147942413LL;
    }
    sub_180125D60(v42, v25 + 4, (unsigned int)v25[2]);
  }
  if ( qword_1801A9738 )
  {
    if ( !HeapFree(qword_1801A9738, 0, v25) )
    {
      v34 = sub_18001B270();
      if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
        sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v25, v34);
    }
    if ( qword_1801A9738 )
    {
      if ( !HeapFree(qword_1801A9738, 0, v18) )
      {
        v35 = sub_18001B270();
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_18007B188(*((_QWORD *)off_18019DE80 + 2), 11, qword_180146138, v18, v35);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800daad0  mov     [rsp-8+arg_8], rbx
0x1800daad5  push    rbp
0x1800daad6  push    rsi
0x1800daad7  push    rdi
0x1800daad8  push    r12
0x1800daada  push    r13
0x1800daadc  push    r14
0x1800daade  push    r15
0x1800daae0  lea     rbp, [rsp-20h]
0x1800daae5  sub     rsp, 120h
0x1800daaec  mov     rax, cs:__security_cookie
0x1800daaf3  xor     rax, rsp
0x1800daaf6  mov     [rbp+50h+var_40], rax
0x1800daafa  mov     rax, r9
0x1800daafd  mov     [rsp+150h+var_100], rax
0x1800dab02  mov     rbx, r8
0x1800dab05  mov     [rsp+150h+var_118], rbx
0x1800dab0a  mov     [rsp+150h+var_11C], edx
0x1800dab0e  mov     r14, rcx
0x1800dab11  mov     r15, [rbp+50h+arg_20]
0x1800dab18  xor     r13d, r13d
0x1800dab1b  test    rcx, rcx
0x1800dab1e  jz      loc_1800DB2E2
0x1800dab24  cmp     edx, 2
0x1800dab27  jge     loc_1800DB2E2
0x1800dab2d  test    rbx, rbx
0x1800dab30  jz      loc_1800DB2E2
0x1800dab36  test    rax, rax
0x1800dab39  jnz     short loc_1800DAB44
0x1800dab3b  cmp     [r8], r13d
0x1800dab3e  jnz     loc_1800DB2E2
0x1800dab44  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800dab48  lea     rsi, asc_1801457FC; "."
0x1800dab4f  lea     r12, aFeatures; "Features"
0x1800dab56  test    r15, r15
0x1800dab59  jz      short loc_1800DAB93
0x1800dab5b  cmp     dword ptr [r15], 5
0x1800dab5f  jnz     short loc_1800DAB93
0x1800dab61  mov     rdx, rsi
0x1800dab64  call    sub_180056720
0x1800dab69  test    eax, eax
0x1800dab6b  jz      loc_1800DABF4
0x1800dab71  mov     rdx, r12
0x1800dab74  mov     rcx, r14
0x1800dab77  call    sub_180056720
0x1800dab7c  test    eax, eax
0x1800dab7e  jz      short loc_1800DABF4
0x1800dab80  lea     rdx, aSignatureUpdat; "Signature Updates"
0x1800dab87  mov     rcx, r14
0x1800dab8a  call    sub_180056720
0x1800dab8f  test    eax, eax
0x1800dab91  jz      short loc_1800DABF4
0x1800dab93  mov     ecx, cs:TlsIndex
0x1800dab99  mov     rax, gs:58h
0x1800daba2  mov     edx, 10h
0x1800daba7  mov     rax, [rax+rcx*8]
0x1800dabab  mov     ecx, [rdx+rax]
0x1800dabae  cmp     cs:dword_1801A99A0, ecx
0x1800dabb4  jg      loc_1800DB344
0x1800dabba  mov     rbx, qword ptr cs:xmmword_1801A9988
0x1800dabc1  mov     rsi, qword ptr cs:xmmword_1801A9988+8
0x1800dabc8  jmp     short loc_1800DABEA
0x1800dabca  cmp     [rbx], r14
0x1800dabcd  jz      loc_1800DACF8
0x1800dabd3  mov     rdx, r14
0x1800dabd6  mov     rcx, [rbx]
0x1800dabd9  call    sub_180056720
0x1800dabde  test    eax, eax
0x1800dabe0  jz      loc_1800DACF8
0x1800dabe6  add     rbx, 8
0x1800dabea  cmp     rbx, rsi
0x1800dabed  jnz     short loc_1800DABCA
0x1800dabef  mov     rbx, [rsp+150h+var_118]
0x1800dabf4  mov     [rbp+50h+var_50], 0D17DE69Eh
0x1800dabfb  mov     [rbp+50h+var_4C], 4F7BE395h
0x1800dac02  mov     [rbp+50h+var_48], 0F7B49E93h
0x1800dac09  mov     [rbp+50h+var_44], 210569AAh
0x1800dac10  inc     rdi
0x1800dac13  cmp     [r14+rdi*2], r13w
0x1800dac18  jnz     short loc_1800DAC10
0x1800dac1a  mov     edi, edi
0x1800dac1c  add     rdi, rdi
0x1800dac1f  mov     eax, 0FFFFFFFFh
0x1800dac24  cmp     rdi, rax
0x1800dac27  ja      loc_1800DB2A4
0x1800dac2d  add     edi, 2
0x1800dac30  lea     r12d, [rdi+24h]
0x1800dac34  cmp     r12d, 24h ; '$'
0x1800dac38  jb      loc_1800DB281
0x1800dac3e  mov     eax, [rbx]
0x1800dac40  mov     [rsp+150h+var_120], eax
0x1800dac44  mov     [rsp+150h+lpMem], r13
0x1800dac49  mov     edx, r12d
0x1800dac4c  mov     sil, 1
0x1800dac4f  mov     r8b, sil
0x1800dac52  lea     rcx, [rsp+150h+lpMem]
0x1800dac57  call    sub_1800CA400
0x1800dac5c  mov     r13d, eax
0x1800dac5f  test    eax, eax
0x1800dac61  jns     loc_1800DAD02
0x1800dac67  lea     rdi, off_18019DE80
0x1800dac6e  mov     rcx, cs:off_18019DE80
0x1800dac75  cmp     rcx, rdi
0x1800dac78  jz      short loc_1800DAC98
0x1800dac7a  test    [rcx+1Ch], sil
0x1800dac7e  jz      short loc_1800DAC98
0x1800dac80  mov     edx, 45h ; 'E'
0x1800dac85  mov     r9d, eax
0x1800dac88  lea     r8, stru_18014B088
0x1800dac8f  mov     rcx, [rcx+10h]
0x1800dac93  call    sub_1800733A8
0x1800dac98  mov     rbx, [rsp+150h+lpMem]
0x1800dac9d  test    rbx, rbx
0x1800daca0  jz      short loc_1800DACF0
0x1800daca2  mov     rcx, cs:qword_1801A9738; hHeap
0x1800daca9  test    rcx, rcx
0x1800dacac  jz      short loc_1800DACF0
0x1800dacae  mov     r8, rbx; lpMem
0x1800dacb1  xor     edx, edx; dwFlags
0x1800dacb3  call    cs:HeapFree
0x1800dacb9  test    eax, eax
0x1800dacbb  jnz     short loc_1800DACF0
0x1800dacbd  call    sub_18001B270
0x1800dacc2  mov     rcx, cs:off_18019DE80
0x1800dacc9  cmp     rcx, rdi
0x1800daccc  jz      short loc_1800DACF0
0x1800dacce  test    [rcx+1Ch], sil
0x1800dacd2  jz      short loc_1800DACF0
0x1800dacd4  mov     edx, 0Bh
0x1800dacd9  mov     dword ptr [rsp+150h+var_130], eax
0x1800dacdd  mov     r9, rbx
0x1800dace0  lea     r8, qword_180146138
0x1800dace7  mov     rcx, [rcx+10h]
0x1800daceb  call    sub_18007B188
0x1800dacf0  mov     eax, r13d
0x1800dacf3  jmp     loc_1800DB31D
0x1800dacf8  mov     eax, 80004001h
0x1800dacfd  jmp     loc_1800DB31D
0x1800dad02  mov     rbx, [rsp+150h+lpMem]
0x1800dad07  mov     [rbx], r12d
0x1800dad0a  mov     r13d, [rsp+150h+var_120]
0x1800dad0f  mov     [rbx+1Ch], r13d
0x1800dad13  mov     [rbx+20h], edi
0x1800dad16  xor     eax, eax
0x1800dad18  test    r15, r15
0x1800dad1b  setnz   al
0x1800dad1e  mov     [rbx+14h], eax
0x1800dad21  test    r15, r15
0x1800dad24  jz      short loc_1800DAD2B
0x1800dad26  mov     eax, [r15]
0x1800dad29  jmp     short loc_1800DAD2D
0x1800dad2b  xor     eax, eax
0x1800dad2d  mov     [rbx+18h], eax
0x1800dad30  mov     eax, [rsp+150h+var_11C]
0x1800dad34  mov     [rbx+10h], eax
0x1800dad37  mov     r8d, edi
0x1800dad3a  lea     rcx, [rbx+24h]
0x1800dad3e  mov     rdx, r14
0x1800dad41  call    sub_180125D60
0x1800dad46  mov     qword ptr [rbx+8], 24h ; '$'
0x1800dad4e  mov     [rbp+50h+var_60], 0
0x1800dad55  mov     [rbp+50h+var_58], 0
0x1800dad5d  lea     rax, [rbp+50h+var_58]
0x1800dad61  mov     [rsp+150h+var_130], rax
0x1800dad66  lea     r9, [rbp+50h+var_60]
0x1800dad6a  mov     r8, rbx
0x1800dad6d  mov     edx, r12d
0x1800dad70  lea     rcx, [rbp+50h+var_50]
0x1800dad74  call    sub_180089530
0x1800dad79  mov     r12d, eax
0x1800dad7c  test    eax, eax
0x1800dad7e  jns     loc_1800DAE68
0x1800dad84  lea     rdi, off_18019DE80
0x1800dad8b  mov     rcx, cs:off_18019DE80
0x1800dad92  cmp     rcx, rdi
0x1800dad95  jz      short loc_1800DADB5
0x1800dad97  test    [rcx+1Ch], sil
0x1800dad9b  jz      short loc_1800DADB5
0x1800dad9d  mov     edx, 46h ; 'F'
0x1800dada2  mov     r9d, eax
0x1800dada5  lea     r8, stru_18014B088
0x1800dadac  mov     rcx, [rcx+10h]
0x1800dadb0  call    sub_1800733A8
0x1800dadb5  mov     r15d, 0Bh
0x1800dadbb  mov     r14, [rbp+50h+var_58]
0x1800dadbf  test    r14, r14
0x1800dadc2  jz      short loc_1800DAE14
0x1800dadc4  mov     rcx, cs:qword_1801A9738; hHeap
0x1800dadcb  test    rcx, rcx
0x1800dadce  jz      loc_1800DAE60
0x1800dadd4  mov     r8, r14; lpMem
0x1800dadd7  xor     edx, edx; dwFlags
0x1800dadd9  call    cs:HeapFree
0x1800daddf  test    eax, eax
0x1800dade1  jnz     short loc_1800DAE14
0x1800dade3  call    sub_18001B270
0x1800dade8  mov     rcx, cs:off_18019DE80
0x1800dadef  cmp     rcx, rdi
0x1800dadf2  jz      short loc_1800DAE14
0x1800dadf4  test    [rcx+1Ch], sil
0x1800dadf8  jz      short loc_1800DAE14
0x1800dadfa  mov     edx, r15d
0x1800dadfd  mov     dword ptr [rsp+150h+var_130], eax
0x1800dae01  mov     r9, r14
0x1800dae04  lea     r8, qword_180146138
0x1800dae0b  mov     rcx, [rcx+10h]
0x1800dae0f  call    sub_18007B188
0x1800dae14  mov     rcx, cs:qword_1801A9738; hHeap
0x1800dae1b  test    rcx, rcx
0x1800dae1e  jz      short loc_1800DAE60
0x1800dae20  mov     r8, rbx; lpMem
0x1800dae23  xor     edx, edx; dwFlags
0x1800dae25  call    cs:HeapFree
0x1800dae2b  test    eax, eax
0x1800dae2d  jnz     short loc_1800DAE60
0x1800dae2f  call    sub_18001B270
0x1800dae34  mov     rcx, cs:off_18019DE80
0x1800dae3b  cmp     rcx, rdi
0x1800dae3e  jz      short loc_1800DAE60
0x1800dae40  test    [rcx+1Ch], sil
0x1800dae44  jz      short loc_1800DAE60
0x1800dae46  mov     edx, r15d
0x1800dae49  mov     dword ptr [rsp+150h+var_130], eax
0x1800dae4d  mov     r9, rbx
0x1800dae50  lea     r8, qword_180146138
0x1800dae57  mov     rcx, [rcx+10h]
0x1800dae5b  call    sub_18007B188
0x1800dae60  mov     eax, r12d
0x1800dae63  jmp     loc_1800DB31D
0x1800dae68  mov     r14, [rbp+50h+var_58]
0x1800dae6c  test    r14, r14
0x1800dae6f  jnz     loc_1800DAF38
0x1800dae75  lea     rdi, off_18019DE80
0x1800dae7c  mov     rcx, cs:off_18019DE80
0x1800dae83  cmp     rcx, rdi
0x1800dae86  jz      short loc_1800DAEA6
0x1800dae88  test    [rcx+1Ch], sil
0x1800dae8c  jz      short loc_1800DAEA6
0x1800dae8e  lea     edx, [r14+47h]
0x1800dae92  lea     r8, stru_18014B088
0x1800dae99  mov     rcx, [rcx+10h]
0x1800dae9d  call    sub_180073384
0x1800daea2  mov     r14, [rbp+50h+var_58]
0x1800daea6  mov     r15d, 0Bh
0x1800daeac  test    r14, r14
0x1800daeaf  jz      short loc_1800DAF01
0x1800daeb1  mov     rcx, cs:qword_1801A9738; hHeap
0x1800daeb8  test    rcx, rcx
0x1800daebb  jz      loc_1800DB019
0x1800daec1  mov     r8, r14; lpMem
0x1800daec4  xor     edx, edx; dwFlags
0x1800daec6  call    cs:HeapFree
0x1800daecc  test    eax, eax
0x1800daece  jnz     short loc_1800DAF01
0x1800daed0  call    sub_18001B270
0x1800daed5  mov     rcx, cs:off_18019DE80
0x1800daedc  cmp     rcx, rdi
0x1800daedf  jz      short loc_1800DAF01
0x1800daee1  test    [rcx+1Ch], sil
0x1800daee5  jz      short loc_1800DAF01
0x1800daee7  mov     edx, r15d
0x1800daeea  mov     dword ptr [rsp+150h+var_130], eax
0x1800daeee  mov     r9, r14
0x1800daef1  lea     r8, qword_180146138
0x1800daef8  mov     rcx, [rcx+10h]
0x1800daefc  call    sub_18007B188
0x1800daf01  mov     rcx, cs:qword_1801A9738; hHeap
0x1800daf08  test    rcx, rcx
0x1800daf0b  jz      loc_1800DB019
0x1800daf11  mov     r8, rbx; lpMem
0x1800daf14  xor     edx, edx; dwFlags
0x1800daf16  call    cs:HeapFree
0x1800daf1c  test    eax, eax
0x1800daf1e  jnz     loc_1800DB019
0x1800daf24  call    sub_18001B270
0x1800daf29  mov     rcx, cs:off_18019DE80
0x1800daf30  cmp     rcx, rdi
0x1800daf33  jmp     loc_1800DAFF7
0x1800daf38  mov     eax, [r14]
0x1800daf3b  mov     r9d, [rbp+50h+var_60]
0x1800daf3f  cmp     r9d, eax
0x1800daf42  jz      loc_1800DB023
0x1800daf48  lea     rdi, off_18019DE80
0x1800daf4f  mov     rcx, cs:off_18019DE80
0x1800daf56  cmp     rcx, rdi
0x1800daf59  jz      short loc_1800DAF72
0x1800daf5b  test    [rcx+1Ch], sil
0x1800daf5f  jz      short loc_1800DAF72
0x1800daf61  mov     dword ptr [rsp+150h+var_130], eax
0x1800daf65  mov     rcx, [rcx+10h]
0x1800daf69  call    sub_1800DCD58
0x1800daf6e  mov     r14, [rbp+50h+var_58]
0x1800daf72  mov     r15d, 0Bh
0x1800daf78  test    r14, r14
0x1800daf7b  jz      short loc_1800DAFCD
0x1800daf7d  mov     rcx, cs:qword_1801A9738; hHeap
0x1800daf84  test    rcx, rcx
0x1800daf87  jz      loc_1800DB019
0x1800daf8d  mov     r8, r14; lpMem
0x1800daf90  xor     edx, edx; dwFlags
  ... truncated ...
```

# sub_1800DEBD0

- ea: `0x1800debd0`
- end: `0x1800df1fd`
- name: `sub_1800DEBD0`
- size: `1581`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800df200`

## callees

- `0x180021050`
- `0x18003b830`
- `0x180056720`
- `0x1800733a8`
- `0x18008d630`
- `0x1800debd0`
- `0x1800df430`
- `0x1800df528`
- `0x180125920`

## import_xrefs

- `OLEAUT32!SysFreeString` at `0x1800def71`
- `OLEAUT32!SysFreeString` at `0x1800def81`
- `OLEAUT32!SysFreeString` at `0x1800df069`
- `OLEAUT32!SysFreeString` at `0x1800df079`
- `OLEAUT32!SysFreeString` at `0x1800df0e7`
- `OLEAUT32!SysFreeString` at `0x1800df0f7`
- `OLEAUT32!SysFreeString` at `0x1800df165`
- `OLEAUT32!SysFreeString` at `0x1800def71`
- `OLEAUT32!SysFreeString` at `0x1800def81`
- `OLEAUT32!SysFreeString` at `0x1800df069`
- `OLEAUT32!SysFreeString` at `0x1800df079`
- `OLEAUT32!SysFreeString` at `0x1800df0e7`
- `OLEAUT32!SysFreeString` at `0x1800df0f7`
- `OLEAUT32!SysFreeString` at `0x1800df165`

## string_xrefs

- `0x1800def3d`: `WSC_SECURITY_PRODUCT_STATE_OFF`
- `0x1800dee81`: `WSC_SECURITY_PRODUCT_STATE_ON`
- `0x1800dee8f`: `WSC_SECURITY_PRODUCT_STATE_SNOOZED`
- `0x1800dee98`: `WSC_SECURITY_PRODUCT_STATE_EXPIRED`

## pseudocode

```c
__int64 __fastcall sub_1800DEBD0(unsigned int a1, _DWORD *a2, _DWORD *a3)
{
  int v5; // r15d
  int v6; // r14d
  unsigned __int8 v7; // si
  int v8; // eax
  unsigned int v9; // edi
  int v11; // eax
  int v12; // eax
  int v13; // esi
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  _UNKNOWN **v19; // rcx
  const char *v20; // r8
  char v21; // [rsp+40h] [rbp-40h]
  int v22; // [rsp+44h] [rbp-3Ch]
  LPVOID ppv; // [rsp+50h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-28h] BYREF
  __int64 v26; // [rsp+60h] [rbp-20h] BYREF
  BSTR v27; // [rsp+68h] [rbp-18h] BYREF
  int v28; // [rsp+70h] [rbp-10h] BYREF
  int v29; // [rsp+74h] [rbp-Ch] BYREF

  v5 = 0;
  v6 = 0;
  *a2 = 0;
  *a3 = 0;
  v7 = 0;
  v21 = 0;
  ppv = 0;
  v8 = sub_180021050(&ppv, (IID *)&stru_18014B850, (IID *)&stru_18014B870, 1u, 0);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 10, &stru_18014B860, (unsigned int)v8);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v9;
  }
  v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, a1);
  v9 = v11;
  if ( v11 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 11, &stru_18014B860, (unsigned int)v11);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v9;
  }
  v29 = 0;
  v12 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 64LL))(ppv, &v29);
  v9 = v12;
  if ( v12 < 0 )
  {
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 12, &stru_18014B860, (unsigned int)v12);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v9;
  }
  if ( v29 > 0 )
  {
    v13 = 1;
    while ( 1 )
    {
      v22 = v13;
      v26 = 0;
      v14 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 72LL))(
              ppv,
              (unsigned int)(v13 - 1),
              &v26);
      v9 = v14;
      if ( v14 < 0 )
        break;
      v27 = 0;
      v15 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v26 + 56LL))(v26, &v27);
      v9 = v15;
      if ( v15 < 0 )
      {
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 14, &stru_18014B860, (unsigned int)v15);
        if ( v27 )
          SysFreeString(v27);
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return v9;
      }
      bstrString = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v26 + 80LL))(v26, &bstrString);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 15, &stru_18014B860, (unsigned int)v16);
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v27 )
          SysFreeString(v27);
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return v9;
      }
      v28 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 64LL))(v26, &v28);
      v9 = v17;
      if ( v17 < 0 )
      {
        if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
          sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 16, &stru_18014B860, (unsigned int)v17);
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v27 )
          SysFreeString(v27);
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        return v9;
      }
      if ( (unsigned int)sub_180056720(bstrString, L"%ProgramFiles%\\Windows Defender\\MSASCui.exe")
        && (unsigned int)sub_180056720(bstrString, L"%ProgramFiles%\\Microsoft Defender for Endpoint\\MSASCui.exe")
        && (unsigned int)sub_180056720(bstrString, L"windowsdefender://") )
      {
        v18 = v28;
        if ( v28 == 1 )
        {
          if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
            sub_1800DF528(
              *((_QWORD *)off_18019DE80 + 2),
              v13,
              (__int64)v27,
              (__int64)"WSC_SECURITY_PRODUCT_STATE_OFF",
              (__int64)bstrString);
        }
        else
        {
          v19 = (_UNKNOWN **)off_18019DE80;
          if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
          {
            if ( v28 )
            {
              if ( v28 == 2 )
              {
                v20 = "WSC_SECURITY_PRODUCT_STATE_SNOOZED";
              }
              else
              {
                v20 = "WSC_SECURITY_PRODUCT_STATE_EXPIRED";
                if ( v28 != 3 )
                  v20 = "Unknown";
              }
            }
            else
            {
              v20 = "WSC_SECURITY_PRODUCT_STATE_ON";
            }
            sub_1800DF528(*((_QWORD *)off_18019DE80 + 2), v13, (__int64)v27, (__int64)v20, (__int64)bstrString);
            v18 = v28;
            v19 = (_UNKNOWN **)off_18019DE80;
          }
          ++v5;
          if ( v18 == 3 )
          {
            if ( v19 != &off_18019DE80 && (*((_BYTE *)v19 + 28) & 4) != 0 )
              sub_1800DF430((TRACEHANDLE)v19[2], v13, (__int64)v27, (__int64)bstrString);
            ++v6;
          }
        }
      }
      else
      {
        v21 = 1;
      }
      if ( bstrString )
        SysFreeString(bstrString);
      if ( v27 )
        SysFreeString(v27);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      ++v13;
      if ( v22 >= v29 )
      {
        v7 = v21;
        goto LABEL_58;
      }
    }
    if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 1) != 0 )
      sub_1800733A8(*((_QWORD *)off_18019DE80 + 2), 13, &stru_18014B860, (unsigned int)v14);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v9;
  }
LABEL_58:
  *a2 = v5;
  *a3 = v6;
  if ( off_18019DE80 != (_UNKNOWN *)&off_18019DE80 && (*((_BYTE *)off_18019DE80 + 28) & 4) != 0 )
    sub_18008D630(*((_QWORD *)off_18019DE80 + 2), 20, &stru_18014B860, (unsigned int)*a2, v6, v7);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x1800debd0  mov     [rsp-38h+arg_18], rbx
0x1800debd5  push    rbp
0x1800debd6  push    rsi
0x1800debd7  push    rdi
0x1800debd8  push    r12
0x1800debda  push    r13
0x1800debdc  push    r14
0x1800debde  push    r15
0x1800debe0  mov     rbp, rsp
0x1800debe3  sub     rsp, 80h
0x1800debea  mov     rax, cs:__security_cookie
0x1800debf1  xor     rax, rsp
0x1800debf4  mov     [rbp+var_8], rax
0x1800debf8  mov     [rbp+var_38], r8
0x1800debfc  mov     r13, rdx
0x1800debff  mov     r12d, ecx
0x1800dec02  xor     ebx, ebx
0x1800dec04  mov     r15d, ebx
0x1800dec07  mov     r14d, ebx
0x1800dec0a  mov     [rdx], ebx
0x1800dec0c  mov     [r8], ebx
0x1800dec0f  mov     sil, bl
0x1800dec12  mov     [rbp+var_40], bl
0x1800dec15  mov     [rbp+ppv], rbx
0x1800dec19  mov     [rsp+80h+pUnkOuter], rbx; pUnkOuter
0x1800dec1e  lea     r9d, [rbx+1]; dwClsContext
0x1800dec22  lea     r8, stru_18014B870; riid
0x1800dec29  lea     rdx, stru_18014B850; rclsid
0x1800dec30  lea     rcx, [rbp+ppv]; ppv
0x1800dec34  call    sub_180021050
0x1800dec39  mov     edi, eax
0x1800dec3b  test    eax, eax
0x1800dec3d  jns     short loc_1800DEC8F
0x1800dec3f  lea     rbx, off_18019DE80
0x1800dec46  mov     rcx, cs:off_18019DE80
0x1800dec4d  cmp     rcx, rbx
0x1800dec50  jz      short loc_1800DEC71
0x1800dec52  test    byte ptr [rcx+1Ch], 1
0x1800dec56  jz      short loc_1800DEC71
0x1800dec58  mov     edx, 0Ah
0x1800dec5d  mov     r9d, eax
0x1800dec60  lea     r8, stru_18014B860
0x1800dec67  mov     rcx, [rcx+10h]
0x1800dec6b  call    sub_1800733A8
0x1800dec70  nop
0x1800dec71  mov     rcx, [rbp+ppv]
0x1800dec75  test    rcx, rcx
0x1800dec78  jz      short loc_1800DEC88
0x1800dec7a  mov     rax, [rcx]
0x1800dec7d  mov     rax, [rax+10h]
0x1800dec81  call    cs:__guard_dispatch_icall_fptr
0x1800dec87  nop
0x1800dec88  mov     eax, edi
0x1800dec8a  jmp     loc_1800DF00E
0x1800dec8f  mov     rcx, [rbp+ppv]
0x1800dec93  mov     rax, [rcx]
0x1800dec96  mov     edx, r12d
0x1800dec99  mov     rax, [rax+38h]
0x1800dec9d  call    cs:__guard_dispatch_icall_fptr
0x1800deca3  mov     edi, eax
0x1800deca5  test    eax, eax
0x1800deca7  jns     short loc_1800DECF4
0x1800deca9  lea     rbx, off_18019DE80
0x1800decb0  mov     rcx, cs:off_18019DE80
0x1800decb7  cmp     rcx, rbx
0x1800decba  jz      short loc_1800DECDB
0x1800decbc  test    byte ptr [rcx+1Ch], 1
0x1800decc0  jz      short loc_1800DECDB
0x1800decc2  mov     edx, 0Bh
0x1800decc7  mov     r9d, eax
0x1800decca  lea     r8, stru_18014B860
0x1800decd1  mov     rcx, [rcx+10h]
0x1800decd5  call    sub_1800733A8
0x1800decda  nop
0x1800decdb  mov     rcx, [rbp+ppv]
0x1800decdf  test    rcx, rcx
0x1800dece2  jz      short loc_1800DECF2
0x1800dece4  mov     rax, [rcx]
0x1800dece7  mov     rax, [rax+10h]
0x1800deceb  call    cs:__guard_dispatch_icall_fptr
0x1800decf1  nop
0x1800decf2  jmp     short loc_1800DEC88
0x1800decf4  mov     [rbp+var_C], ebx
0x1800decf7  mov     rcx, [rbp+ppv]
0x1800decfb  mov     rax, [rcx]
0x1800decfe  lea     rdx, [rbp+var_C]
0x1800ded02  mov     rax, [rax+40h]
0x1800ded06  call    cs:__guard_dispatch_icall_fptr
0x1800ded0c  mov     edi, eax
0x1800ded0e  test    eax, eax
0x1800ded10  jns     short loc_1800DED60
0x1800ded12  lea     rbx, off_18019DE80
0x1800ded19  mov     rcx, cs:off_18019DE80
0x1800ded20  cmp     rcx, rbx
0x1800ded23  jz      short loc_1800DED44
0x1800ded25  test    byte ptr [rcx+1Ch], 1
0x1800ded29  jz      short loc_1800DED44
0x1800ded2b  mov     edx, 0Ch
0x1800ded30  mov     r9d, eax
0x1800ded33  lea     r8, stru_18014B860
0x1800ded3a  mov     rcx, [rcx+10h]
0x1800ded3e  call    sub_1800733A8
0x1800ded43  nop
0x1800ded44  mov     rcx, [rbp+ppv]
0x1800ded48  test    rcx, rcx
0x1800ded4b  jz      short loc_1800DED5B
0x1800ded4d  mov     rax, [rcx]
0x1800ded50  mov     rax, [rax+10h]
0x1800ded54  call    cs:__guard_dispatch_icall_fptr
0x1800ded5a  nop
0x1800ded5b  jmp     loc_1800DEC88
0x1800ded60  lea     rbx, off_18019DE80
0x1800ded67  cmp     [rbp+var_C], 0
0x1800ded6b  jle     loc_1800DEFB1
0x1800ded71  mov     esi, 1
0x1800ded76  mov     [rbp+var_3C], esi
0x1800ded79  mov     [rbp+var_20], 0
0x1800ded81  mov     rcx, [rbp+ppv]
0x1800ded85  mov     rax, [rcx]
0x1800ded88  lea     edx, [rsi-1]
0x1800ded8b  lea     r8, [rbp+var_20]
0x1800ded8f  mov     rax, [rax+48h]
0x1800ded93  call    cs:__guard_dispatch_icall_fptr
0x1800ded99  mov     edi, eax
0x1800ded9b  test    eax, eax
0x1800ded9d  js      loc_1800DF19F
0x1800deda3  mov     [rbp+var_18], 0
0x1800dedab  mov     rcx, [rbp+var_20]
0x1800dedaf  mov     rax, [rcx]
0x1800dedb2  lea     rdx, [rbp+var_18]
0x1800dedb6  mov     rax, [rax+38h]
0x1800dedba  call    cs:__guard_dispatch_icall_fptr
0x1800dedc0  mov     edi, eax
0x1800dedc2  test    eax, eax
0x1800dedc4  js      loc_1800DF131
0x1800dedca  mov     [rbp+bstrString], 0
0x1800dedd2  mov     rcx, [rbp+var_20]
0x1800dedd6  mov     rax, [rcx]
0x1800dedd9  lea     rdx, [rbp+bstrString]
0x1800deddd  mov     rax, [rax+50h]
0x1800dede1  call    cs:__guard_dispatch_icall_fptr
0x1800dede7  mov     edi, eax
0x1800dede9  test    eax, eax
0x1800dedeb  js      loc_1800DF0B3
0x1800dedf1  mov     [rbp+var_10], 0
0x1800dedf8  mov     rcx, [rbp+var_20]
0x1800dedfc  mov     rax, [rcx]
0x1800dedff  lea     rdx, [rbp+var_10]
0x1800dee03  mov     rax, [rax+40h]
0x1800dee07  call    cs:__guard_dispatch_icall_fptr
0x1800dee0d  mov     edi, eax
0x1800dee0f  test    eax, eax
0x1800dee11  js      loc_1800DF035
0x1800dee17  lea     rdx, aProgramfilesWi_0; "%ProgramFiles%\\Windows Defender\\MSASC"...
0x1800dee1e  mov     rcx, [rbp+bstrString]
0x1800dee22  call    sub_180056720
0x1800dee27  test    eax, eax
0x1800dee29  jz      loc_1800DEF64
0x1800dee2f  lea     rdx, aProgramfilesMi_1; "%ProgramFiles%\\Microsoft Defender for "...
0x1800dee36  mov     rcx, [rbp+bstrString]
0x1800dee3a  call    sub_180056720
0x1800dee3f  test    eax, eax
0x1800dee41  jz      loc_1800DEF64
0x1800dee47  lea     rdx, aWindowsdefende; "windowsdefender://"
0x1800dee4e  mov     rcx, [rbp+bstrString]
0x1800dee52  call    sub_180056720
0x1800dee57  test    eax, eax
0x1800dee59  jz      loc_1800DEF64
0x1800dee5f  mov     eax, [rbp+var_10]
0x1800dee62  cmp     eax, 1
0x1800dee65  jz      loc_1800DEF1D
0x1800dee6b  mov     rcx, cs:off_18019DE80
0x1800dee72  cmp     rcx, rbx
0x1800dee75  jz      short loc_1800DEEE3
0x1800dee77  test    byte ptr [rcx+1Ch], 4
0x1800dee7b  jz      short loc_1800DEEE3
0x1800dee7d  test    eax, eax
0x1800dee7f  jnz     short loc_1800DEE8A
0x1800dee81  lea     r8, aWscSecurityPro; "WSC_SECURITY_PRODUCT_STATE_ON"
0x1800dee88  jmp     short loc_1800DEEAD
0x1800dee8a  cmp     eax, 2
0x1800dee8d  jnz     short loc_1800DEE98
0x1800dee8f  lea     r8, aWscSecurityPro_0; "WSC_SECURITY_PRODUCT_STATE_SNOOZED"
0x1800dee96  jmp     short loc_1800DEEAD
0x1800dee98  lea     r8, aWscSecurityPro_1; "WSC_SECURITY_PRODUCT_STATE_EXPIRED"
0x1800dee9f  lea     rdx, aUnknown_3; "Unknown"
0x1800deea6  cmp     eax, 3
0x1800deea9  cmovnz  r8, rdx
0x1800deead  mov     edx, 11h
0x1800deeb2  mov     rax, [rbp+bstrString]
0x1800deeb6  mov     [rsp+80h+var_48], rax; __int64
0x1800deebb  mov     [rsp+80h+var_50], r8; __int64
0x1800deec0  mov     rax, [rbp+var_18]
0x1800deec4  mov     [rsp+80h+var_58], rax; __int64
0x1800deec9  mov     dword ptr [rsp+80h+pUnkOuter], esi; char
0x1800deecd  mov     r9d, r12d
0x1800deed0  mov     rcx, [rcx+10h]; LoggerHandle
0x1800deed4  call    sub_1800DF528
0x1800deed9  mov     eax, [rbp+var_10]
0x1800deedc  mov     rcx, cs:off_18019DE80
0x1800deee3  inc     r15d
0x1800deee6  cmp     eax, 3
0x1800deee9  jnz     short loc_1800DEF68
0x1800deeeb  cmp     rcx, rbx
0x1800deeee  jz      short loc_1800DEF18
0x1800deef0  test    byte ptr [rcx+1Ch], 4
0x1800deef4  jz      short loc_1800DEF18
0x1800deef6  mov     rax, [rbp+bstrString]
0x1800deefa  mov     [rsp+80h+var_50], rax; __int64
0x1800deeff  mov     rax, [rbp+var_18]
0x1800def03  mov     [rsp+80h+var_58], rax; __int64
0x1800def08  mov     dword ptr [rsp+80h+pUnkOuter], esi; char
0x1800def0c  mov     r9d, r12d
0x1800def0f  mov     rcx, [rcx+10h]; LoggerHandle
0x1800def13  call    sub_1800DF430
0x1800def18  inc     r14d
0x1800def1b  jmp     short loc_1800DEF68
0x1800def1d  mov     rcx, cs:off_18019DE80
0x1800def24  cmp     rcx, rbx
0x1800def27  jz      short loc_1800DEF68
0x1800def29  test    byte ptr [rcx+1Ch], 4
0x1800def2d  jz      short loc_1800DEF68
0x1800def2f  mov     edx, 13h
0x1800def34  mov     rax, [rbp+bstrString]
0x1800def38  mov     [rsp+80h+var_48], rax; __int64
0x1800def3d  lea     rax, aWscSecurityPro_2; "WSC_SECURITY_PRODUCT_STATE_OFF"
0x1800def44  mov     [rsp+80h+var_50], rax; __int64
0x1800def49  mov     rax, [rbp+var_18]
0x1800def4d  mov     [rsp+80h+var_58], rax; __int64
0x1800def52  mov     dword ptr [rsp+80h+pUnkOuter], esi; char
0x1800def56  mov     r9d, r12d
0x1800def59  mov     rcx, [rcx+10h]; LoggerHandle
0x1800def5d  call    sub_1800DF528
0x1800def62  jmp     short loc_1800DEF68
0x1800def64  mov     [rbp+var_40], 1
0x1800def68  mov     rcx, [rbp+bstrString]; bstrString
0x1800def6c  test    rcx, rcx
0x1800def6f  jz      short loc_1800DEF78
0x1800def71  call    cs:SysFreeString
0x1800def77  nop
0x1800def78  mov     rcx, [rbp+var_18]; bstrString
0x1800def7c  test    rcx, rcx
0x1800def7f  jz      short loc_1800DEF88
0x1800def81  call    cs:SysFreeString
0x1800def87  nop
0x1800def88  mov     rcx, [rbp+var_20]
0x1800def8c  test    rcx, rcx
0x1800def8f  jz      short loc_1800DEF9F
0x1800def91  mov     rax, [rcx]
0x1800def94  mov     rax, [rax+10h]
0x1800def98  call    cs:__guard_dispatch_icall_fptr
0x1800def9e  nop
0x1800def9f  inc     esi
0x1800defa1  mov     eax, [rbp+var_3C]
0x1800defa4  cmp     eax, [rbp+var_C]
0x1800defa7  jl      loc_1800DED76
0x1800defad  mov     sil, [rbp+var_40]
0x1800defb1  mov     [r13+0], r15d
0x1800defb5  mov     rax, [rbp+var_38]
0x1800defb9  mov     [rax], r14d
0x1800defbc  mov     rcx, cs:off_18019DE80
0x1800defc3  cmp     rcx, rbx
0x1800defc6  jz      short loc_1800DEFF5
0x1800defc8  test    byte ptr [rcx+1Ch], 4
0x1800defcc  jz      short loc_1800DEFF5
0x1800defce  movzx   eax, sil
0x1800defd2  mov     edx, 14h
0x1800defd7  mov     dword ptr [rsp+80h+var_58], eax
0x1800defdb  mov     dword ptr [rsp+80h+pUnkOuter], r14d
0x1800defe0  mov     r9d, [r13+0]
0x1800defe4  lea     r8, stru_18014B860
0x1800defeb  mov     rcx, [rcx+10h]
0x1800defef  call    sub_18008D630
0x1800deff4  nop
0x1800deff5  mov     rcx, [rbp+ppv]
0x1800deff9  test    rcx, rcx
0x1800deffc  jz      short loc_1800DF00C
0x1800deffe  mov     rax, [rcx]
0x1800df001  mov     rax, [rax+10h]
0x1800df005  call    cs:__guard_dispatch_icall_fptr
0x1800df00b  nop
0x1800df00c  xor     eax, eax
0x1800df00e  mov     rcx, [rbp+var_8]
0x1800df012  xor     rcx, rsp; StackCookie
0x1800df015  call    __security_check_cookie
0x1800df01a  mov     rbx, [rsp+80h+arg_18]
0x1800df022  add     rsp, 80h
0x1800df029  pop     r15
0x1800df02b  pop     r14
0x1800df02d  pop     r13
0x1800df02f  pop     r12
0x1800df031  pop     rdi
0x1800df032  pop     rsi
0x1800df033  pop     rbp
0x1800df034  retn
0x1800df035  mov     rcx, cs:off_18019DE80
0x1800df03c  cmp     rcx, rbx
0x1800df03f  jz      short loc_1800DF060
0x1800df041  test    byte ptr [rcx+1Ch], 1
0x1800df045  jz      short loc_1800DF060
  ... truncated ...
```

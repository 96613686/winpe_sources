# sub_1800A0EBC

- ea: `0x1800a0ebc`
- end: `0x1800a1505`
- name: `sub_1800A0EBC`
- size: `1609`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800a1508`

## callees

- `0x180004678`
- `0x180007f5c`
- `0x18000b710`
- `0x18000bc94`
- `0x180018d7c`
- `0x180097bfc`
- `0x180099e68`
- `0x1800a0ebc`
- `0x1800a4fac`
- `0x1800f3fb8`
- `0x1800f400c`
- `0x1800f4078`
- `0x1800f4270`
- `0x18013b830`
- `0x18013bf50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1308`

## string_xrefs

- `0x1800a0f0b`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`
- `0x1800a107a`: `C:\Users\ContainerAdministrator\ESP\ESP.Build\third_party\wp.client\msinternal\src\base\core\windows\online_auth.h`
- `0x1800a12f6`: `C:\Users\ContainerAdministrator\ESP\ESP.Build\third_party\wp.client\msinternal\src\base\core\windows\online_auth.h`
- `0x1800a1051`: `CombaseRoGetActivationFactoryFailed`
- `0x1800a12ce`: `CombaseRoGetActivationFactoryEmpty`

## pseudocode

```c
__int64 __fastcall sub_1800A0EBC(__int64 a1)
{
  __int64 v2; // rbx
  int v3; // esi
  unsigned int v4; // edx
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  signed int LastError; // eax
  unsigned int v9; // edx
  __int64 v10; // rax
  _BYTE v12[8]; // [rsp+40h] [rbp-C0h] BYREF
  union _RTL_RUN_ONCE *v13; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v14; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+60h] [rbp-A0h]
  __int128 v16; // [rsp+70h] [rbp-90h] BYREF
  __int128 v17; // [rsp+80h] [rbp-80h]
  __int128 v18; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v19[32]; // [rsp+B0h] [rbp-50h] BYREF
  char v20; // [rsp+D0h] [rbp-30h]
  _BYTE v21[72]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v22[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v23[40]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v24[32]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v25[40]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v26; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v27; // [rsp+1A8h] [rbp+A8h] BYREF
  _QWORD v28[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v29[40]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v30[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v31[32]; // [rsp+208h] [rbp+108h] BYREF
  char v32; // [rsp+228h] [rbp+128h]

  v27 = a1;
  sub_18013BF50(v28, 0, 128);
  sub_1800A4FAC(v28, L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest");
  if ( !v32 )
  {
    sub_18000BC94(a1, v28);
    *(_BYTE *)(a1 + 120) = 0;
    if ( v32 )
    {
      if ( v28[0] )
        sub_180099E68(v28, v28[0]);
      return a1;
    }
LABEL_39:
    sub_180007F5C(v31);
    sub_180007F5C(v30);
    sub_180007F5C(v29);
    return a1;
  }
  v2 = v28[0];
  v28[0] = 0;
  v27 = v2;
  if ( dword_18021C690 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)TlsIndex)
                                   + 4LL) )
  {
    sub_1800F4078(&dword_18021C690);
    if ( dword_18021C690 == -1 )
    {
      stru_18021C640.Ptr = 0;
      qword_18021C648 = (__int64)off_180152498;
      qword_18021C680 = (__int64)&qword_18021C648;
      byte_18021C688 = 0;
      atexit(sub_180146940);
      sub_1800F400C(&dword_18021C690);
    }
  }
  v13 = &stru_18021C640;
  sub_180097BFC(&stru_18021C640);
  if ( byte_18021C688 == 1 && byte_18021C660 )
  {
    v26 = 0;
    v18 = xmmword_180151398;
    v3 = ((__int64 (__fastcall *)(__int64, __int128 *, __int64 *))qword_18021C658)(v2, &v18, &v26);
    if ( v3 )
    {
      *(_QWORD *)&v18 = v21;
      LODWORD(v13) = 0;
      sub_18000B710(v21, &v13, v12);
      v13 = (union _RTL_RUN_ONCE *)v19;
      v20 = 0;
      v16 = 0;
      v17 = 0;
      sub_180004678(&v16, "CombaseRoGetActivationFactoryFailed", 35);
      v14 = 0;
      v15 = 0;
      sub_180004678(
        &v14,
        "C:\\Users\\ContainerAdministrator\\ESP\\ESP.Build\\third_party\\wp.client\\msinternal\\src\\base\\core\\windows\\online_auth.h",
        114);
      v4 = (unsigned __int16)v3 | 0x80070000;
      if ( v3 <= 0 )
        v4 = v3;
      v5 = sub_180018D7C((unsigned int)v22, v4, (unsigned int)&v14, 241, (__int64)&v16, 0, (__int64)v19, (__int64)v21);
      *(_OWORD *)a1 = *(_OWORD *)v5;
      *(_OWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 40) = 0;
      *(_OWORD *)(a1 + 16) = *(_OWORD *)(v5 + 16);
      *(_OWORD *)(a1 + 32) = *(_OWORD *)(v5 + 32);
      *(_QWORD *)(v5 + 32) = 0;
      *(_QWORD *)(v5 + 40) = 15;
      *(_BYTE *)(v5 + 16) = 0;
      *(_DWORD *)(a1 + 48) = *(_DWORD *)(v5 + 48);
      *(_OWORD *)(a1 + 56) = 0;
      *(_QWORD *)(a1 + 72) = 0;
      *(_QWORD *)(a1 + 80) = 0;
      *(_OWORD *)(a1 + 56) = *(_OWORD *)(v5 + 56);
      *(_OWORD *)(a1 + 72) = *(_OWORD *)(v5 + 72);
      *(_QWORD *)(v5 + 72) = 0;
      *(_QWORD *)(v5 + 80) = 15;
      *(_BYTE *)(v5 + 56) = 0;
      *(_OWORD *)(a1 + 88) = 0;
      *(_QWORD *)(a1 + 104) = 0;
      *(_QWORD *)(a1 + 112) = 0;
      *(_OWORD *)(a1 + 88) = *(_OWORD *)(v5 + 88);
      *(_OWORD *)(a1 + 104) = *(_OWORD *)(v5 + 104);
      *(_QWORD *)(v5 + 104) = 0;
      *(_QWORD *)(v5 + 112) = 15;
      *(_BYTE *)(v5 + 88) = 0;
      *(_BYTE *)(a1 + 120) = 0;
      sub_180007F5C(v25);
      sub_180007F5C(v24);
      sub_180007F5C(v23);
      sub_180007F5C(&v14);
      sub_180007F5C(&v16);
      v6 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      }
      if ( v2 )
        sub_180099E68(&v27, v2);
      if ( !v32 )
        goto LABEL_39;
      if ( v28[0] )
        sub_180099E68(v28, v28[0]);
    }
    else
    {
      *(_QWORD *)a1 = 0;
      if ( (__int64 *)a1 == &v26 )
      {
        v7 = v26;
      }
      else
      {
        *(_QWORD *)a1 = v26;
        v7 = 0;
        v26 = 0;
      }
      *(_BYTE *)(a1 + 120) = 1;
      if ( v7 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      }
      if ( v2 )
        sub_180099E68(&v27, v2);
      if ( !v32 )
        goto LABEL_39;
      if ( v28[0] )
        sub_180099E68(v28, v28[0]);
    }
  }
  else
  {
    *(_QWORD *)&v18 = v21;
    LODWORD(v13) = 0;
    sub_18000B710(v21, &v13, v12);
    v13 = (union _RTL_RUN_ONCE *)v19;
    v20 = 0;
    v14 = 0;
    v15 = 0;
    sub_180004678(&v14, "CombaseRoGetActivationFactoryEmpty", 34);
    v16 = 0;
    v17 = 0;
    sub_180004678(
      &v16,
      "C:\\Users\\ContainerAdministrator\\ESP\\ESP.Build\\third_party\\wp.client\\msinternal\\src\\base\\core\\windows\\online_auth.h",
      114);
    LastError = GetLastError();
    v9 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v9 = LastError;
    v10 = sub_180018D7C((unsigned int)v22, v9, (unsigned int)&v16, 245, (__int64)&v14, 0, (__int64)v19, (__int64)v21);
    *(_OWORD *)a1 = *(_OWORD *)v10;
    *(_OWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v10 + 16);
    *(_OWORD *)(a1 + 32) = *(_OWORD *)(v10 + 32);
    *(_QWORD *)(v10 + 32) = 0;
    *(_QWORD *)(v10 + 40) = 15;
    *(_BYTE *)(v10 + 16) = 0;
    *(_DWORD *)(a1 + 48) = *(_DWORD *)(v10 + 48);
    *(_OWORD *)(a1 + 56) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    *(_QWORD *)(a1 + 80) = 0;
    *(_OWORD *)(a1 + 56) = *(_OWORD *)(v10 + 56);
    *(_OWORD *)(a1 + 72) = *(_OWORD *)(v10 + 72);
    *(_QWORD *)(v10 + 72) = 0;
    *(_QWORD *)(v10 + 80) = 15;
    *(_BYTE *)(v10 + 56) = 0;
    *(_OWORD *)(a1 + 88) = 0;
    *(_QWORD *)(a1 + 104) = 0;
    *(_QWORD *)(a1 + 112) = 0;
    *(_OWORD *)(a1 + 88) = *(_OWORD *)(v10 + 88);
    *(_OWORD *)(a1 + 104) = *(_OWORD *)(v10 + 104);
    *(_QWORD *)(v10 + 104) = 0;
    *(_QWORD *)(v10 + 112) = 15;
    *(_BYTE *)(v10 + 88) = 0;
    *(_BYTE *)(a1 + 120) = 0;
    sub_180007F5C(v25);
    sub_180007F5C(v24);
    sub_180007F5C(v23);
    sub_180007F5C(&v16);
    sub_180007F5C(&v14);
    if ( v2 )
      sub_180099E68(&v27, v2);
    if ( !v32 )
      goto LABEL_39;
    if ( v28[0] )
      sub_180099E68(v28, v28[0]);
  }
  return a1;
}

```

## disassembly

```asm
0x1800a0ebc  mov     [rsp-8+arg_8], rbx
0x1800a0ec1  mov     [rsp-8+arg_10], rsi
0x1800a0ec6  push    rbp
0x1800a0ec7  push    rdi
0x1800a0ec8  push    r14
0x1800a0eca  lea     rbp, [rsp-140h]
0x1800a0ed2  sub     rsp, 240h
0x1800a0ed9  mov     rax, cs:__security_cookie
0x1800a0ee0  xor     rax, rsp
0x1800a0ee3  mov     [rbp+150h+var_20], rax
0x1800a0eea  mov     rdi, rcx
0x1800a0eed  mov     [rbp+150h+var_A8], rcx
0x1800a0ef4  xor     r14d, r14d
0x1800a0ef7  xor     edx, edx
0x1800a0ef9  mov     r8d, 80h
0x1800a0eff  lea     rcx, [rbp+150h+var_A0]
0x1800a0f06  call    sub_18013BF50
0x1800a0f0b  lea     rdx, aWindowsSecurit; "Windows.Security.Authentication.OnlineI"...
0x1800a0f12  lea     rcx, [rbp+150h+var_A0]
0x1800a0f19  call    sub_1800A4FAC
0x1800a0f1e  nop
0x1800a0f1f  cmp     [rbp+150h+var_28], r14b
0x1800a0f26  jnz     short loc_1800A0F66
0x1800a0f28  lea     rdx, [rbp+150h+var_A0]
0x1800a0f2f  mov     rcx, rdi
0x1800a0f32  call    sub_18000BC94
0x1800a0f37  mov     [rdi+78h], r14b
0x1800a0f3b  cmp     [rbp+150h+var_28], r14b
0x1800a0f42  jz      loc_1800A1456
0x1800a0f48  mov     rdx, [rbp+150h+var_A0]
0x1800a0f4f  test    rdx, rdx
0x1800a0f52  jz      short loc_1800A0F61
0x1800a0f54  lea     rcx, [rbp+150h+var_A0]
0x1800a0f5b  call    sub_180099E68
0x1800a0f60  nop
0x1800a0f61  jmp     loc_1800A147A
0x1800a0f66  mov     rbx, [rbp+150h+var_A0]
0x1800a0f6d  mov     [rbp+150h+var_A0], r14
0x1800a0f74  mov     [rbp+150h+var_A8], rbx
0x1800a0f7b  mov     ecx, cs:TlsIndex
0x1800a0f81  mov     rax, gs:58h
0x1800a0f8a  mov     edx, 4
0x1800a0f8f  mov     rax, [rax+rcx*8]
0x1800a0f93  mov     ecx, [rdx+rax]
0x1800a0f96  cmp     cs:dword_18021C690, ecx
0x1800a0f9c  jg      loc_1800A14A4
0x1800a0fa2  lea     rcx, stru_18021C640; lpInitOnce
0x1800a0fa9  mov     [rsp+250h+var_208], rcx
0x1800a0fae  lea     rdx, [rsp+250h+var_208]
0x1800a0fb3  call    sub_180097BFC
0x1800a0fb8  cmp     cs:byte_18021C688, 1
0x1800a0fbf  jnz     loc_1800A1286
0x1800a0fc5  cmp     cs:byte_18021C660, r14b
0x1800a0fcc  jz      loc_1800A1286
0x1800a0fd2  mov     [rbp+150h+var_B0], r14
0x1800a0fd9  movups  xmm0, cs:xmmword_180151398
0x1800a0fe0  movdqu  [rbp+150h+var_1B0], xmm0
0x1800a0fe5  lea     r8, [rbp+150h+var_B0]
0x1800a0fec  lea     rdx, [rbp+150h+var_1B0]
0x1800a0ff0  mov     rcx, rbx
0x1800a0ff3  mov     rax, cs:qword_18021C658
0x1800a0ffa  call    cs:__guard_dispatch_icall_fptr
0x1800a1000  mov     esi, eax
0x1800a1002  test    eax, eax
0x1800a1004  jz      loc_1800A11FC
0x1800a100a  lea     rax, [rbp+150h+var_178]
0x1800a100e  mov     qword ptr [rbp+150h+var_1B0], rax
0x1800a1012  mov     dword ptr [rsp+250h+var_208], 0
0x1800a101a  lea     r8, [rsp+250h+var_210]
0x1800a101f  lea     rdx, [rsp+250h+var_208]
0x1800a1024  lea     rcx, [rbp+150h+var_178]
0x1800a1028  call    sub_18000B710
0x1800a102d  nop
0x1800a102e  lea     rax, [rbp+150h+var_1A0]
0x1800a1032  mov     [rsp+250h+var_208], rax
0x1800a1037  mov     [rbp+150h+var_180], r14b
0x1800a103b  xorps   xmm0, xmm0
0x1800a103e  movups  [rsp+250h+var_1E0], xmm0
0x1800a1043  xorps   xmm1, xmm1
0x1800a1046  movdqu  [rbp+150h+var_1D0], xmm1
0x1800a104b  mov     r8d, 23h ; '#'
0x1800a1051  lea     rdx, aCombaserogetac; "CombaseRoGetActivationFactoryFailed"
0x1800a1058  lea     rcx, [rsp+250h+var_1E0]
0x1800a105d  call    sub_180004678
0x1800a1062  nop
0x1800a1063  xorps   xmm0, xmm0
0x1800a1066  movups  [rsp+250h+var_200], xmm0
0x1800a106b  xorps   xmm1, xmm1
0x1800a106e  movdqu  [rsp+250h+var_1F0], xmm1
0x1800a1074  mov     r8d, 72h ; 'r'
0x1800a107a  lea     rdx, aCUsersContaine_26; "C:\\Users\\ContainerAdministrator\\ESP"...
0x1800a1081  lea     rcx, [rsp+250h+var_200]
0x1800a1086  call    sub_180004678
0x1800a108b  nop
0x1800a108c  movzx   edx, si
0x1800a108f  or      edx, 80070000h
0x1800a1095  test    esi, esi
0x1800a1097  cmovle  edx, esi
0x1800a109a  lea     rax, [rbp+150h+var_178]
0x1800a109e  mov     [rsp+250h+var_218], rax
0x1800a10a3  lea     rax, [rbp+150h+var_1A0]
0x1800a10a7  mov     [rsp+250h+var_220], rax
0x1800a10ac  mov     [rsp+250h+var_228], r14
0x1800a10b1  lea     rax, [rsp+250h+var_1E0]
0x1800a10b6  mov     [rsp+250h+var_230], rax
0x1800a10bb  mov     r9d, 0F1h
0x1800a10c1  lea     r8, [rsp+250h+var_200]
0x1800a10c6  lea     rcx, [rbp+150h+var_130]
0x1800a10ca  call    sub_180018D7C
0x1800a10cf  mov     rcx, rax
0x1800a10d2  movups  xmm0, xmmword ptr [rax]
0x1800a10d5  movdqu  xmmword ptr [rdi], xmm0
0x1800a10d9  xorps   xmm0, xmm0
0x1800a10dc  movups  xmmword ptr [rdi+10h], xmm0
0x1800a10e0  mov     [rdi+20h], r14
0x1800a10e4  mov     [rdi+28h], r14
0x1800a10e8  movups  xmm0, xmmword ptr [rax+10h]
0x1800a10ec  movups  xmmword ptr [rdi+10h], xmm0
0x1800a10f0  movups  xmm1, xmmword ptr [rax+20h]
0x1800a10f4  movups  xmmword ptr [rdi+20h], xmm1
0x1800a10f8  mov     [rax+20h], r14
0x1800a10fc  mov     edx, 0Fh
0x1800a1101  mov     [rax+28h], rdx
0x1800a1105  mov     [rax+10h], r14b
0x1800a1109  mov     eax, [rax+30h]
0x1800a110c  mov     [rdi+30h], eax
0x1800a110f  xorps   xmm0, xmm0
0x1800a1112  movups  xmmword ptr [rdi+38h], xmm0
0x1800a1116  mov     [rdi+48h], r14
0x1800a111a  mov     [rdi+50h], r14
0x1800a111e  movups  xmm0, xmmword ptr [rcx+38h]
0x1800a1122  movups  xmmword ptr [rdi+38h], xmm0
0x1800a1126  movups  xmm1, xmmword ptr [rcx+48h]
0x1800a112a  movups  xmmword ptr [rdi+48h], xmm1
0x1800a112e  mov     [rcx+48h], r14
0x1800a1132  mov     [rcx+50h], rdx
0x1800a1136  mov     [rcx+38h], r14b
0x1800a113a  xorps   xmm0, xmm0
0x1800a113d  movups  xmmword ptr [rdi+58h], xmm0
0x1800a1141  mov     [rdi+68h], r14
0x1800a1145  mov     [rdi+70h], r14
0x1800a1149  movups  xmm0, xmmword ptr [rcx+58h]
0x1800a114d  movups  xmmword ptr [rdi+58h], xmm0
0x1800a1151  movups  xmm1, xmmword ptr [rcx+68h]
0x1800a1155  movups  xmmword ptr [rdi+68h], xmm1
0x1800a1159  mov     [rcx+68h], r14
0x1800a115d  mov     [rcx+70h], rdx
0x1800a1161  mov     [rcx+58h], r14b
0x1800a1165  mov     [rdi+78h], r14b
0x1800a1169  lea     rcx, [rbp+150h+var_D8]
0x1800a116d  call    sub_180007F5C
0x1800a1172  lea     rcx, [rbp+150h+var_F8]
0x1800a1176  call    sub_180007F5C
0x1800a117b  lea     rcx, [rbp+150h+var_120]
0x1800a117f  call    sub_180007F5C
0x1800a1184  nop
0x1800a1185  lea     rcx, [rsp+250h+var_200]
0x1800a118a  call    sub_180007F5C
0x1800a118f  nop
0x1800a1190  lea     rcx, [rsp+250h+var_1E0]
0x1800a1195  call    sub_180007F5C
0x1800a119a  nop
0x1800a119b  mov     rcx, [rbp+150h+var_B0]
0x1800a11a2  test    rcx, rcx
0x1800a11a5  jz      short loc_1800A11BC
0x1800a11a7  mov     [rbp+150h+var_B0], r14
0x1800a11ae  mov     rax, [rcx]
0x1800a11b1  mov     rax, [rax+10h]
0x1800a11b5  call    cs:__guard_dispatch_icall_fptr
0x1800a11bb  nop
0x1800a11bc  test    rbx, rbx
0x1800a11bf  jz      short loc_1800A11D1
0x1800a11c1  mov     rdx, rbx
0x1800a11c4  lea     rcx, [rbp+150h+var_A8]
0x1800a11cb  call    sub_180099E68
0x1800a11d0  nop
0x1800a11d1  cmp     [rbp+150h+var_28], r14b
0x1800a11d8  jz      loc_1800A1456
0x1800a11de  mov     rdx, [rbp+150h+var_A0]
0x1800a11e5  test    rdx, rdx
0x1800a11e8  jz      short loc_1800A11F7
0x1800a11ea  lea     rcx, [rbp+150h+var_A0]
0x1800a11f1  call    sub_180099E68
0x1800a11f6  nop
0x1800a11f7  jmp     loc_1800A147A
0x1800a11fc  mov     [rdi], r14
0x1800a11ff  lea     rax, [rbp+150h+var_B0]
0x1800a1206  cmp     rdi, rax
0x1800a1209  jz      short loc_1800A1221
0x1800a120b  mov     rax, [rbp+150h+var_B0]
0x1800a1212  mov     [rdi], rax
0x1800a1215  mov     rcx, r14
0x1800a1218  mov     [rbp+150h+var_B0], rcx
0x1800a121f  jmp     short loc_1800A1228
0x1800a1221  mov     rcx, [rbp+150h+var_B0]
0x1800a1228  mov     byte ptr [rdi+78h], 1
0x1800a122c  test    rcx, rcx
0x1800a122f  jz      short loc_1800A1246
0x1800a1231  mov     [rbp+150h+var_B0], r14
0x1800a1238  mov     rax, [rcx]
0x1800a123b  mov     rax, [rax+10h]
0x1800a123f  call    cs:__guard_dispatch_icall_fptr
0x1800a1245  nop
0x1800a1246  test    rbx, rbx
0x1800a1249  jz      short loc_1800A125B
0x1800a124b  mov     rdx, rbx
0x1800a124e  lea     rcx, [rbp+150h+var_A8]
0x1800a1255  call    sub_180099E68
0x1800a125a  nop
0x1800a125b  cmp     [rbp+150h+var_28], r14b
0x1800a1262  jz      loc_1800A1456
0x1800a1268  mov     rdx, [rbp+150h+var_A0]
0x1800a126f  test    rdx, rdx
0x1800a1272  jz      short loc_1800A1281
0x1800a1274  lea     rcx, [rbp+150h+var_A0]
0x1800a127b  call    sub_180099E68
0x1800a1280  nop
0x1800a1281  jmp     loc_1800A147A
0x1800a1286  lea     rax, [rbp+150h+var_178]
0x1800a128a  mov     qword ptr [rbp+150h+var_1B0], rax
0x1800a128e  mov     dword ptr [rsp+250h+var_208], 0
0x1800a1296  lea     r8, [rsp+250h+var_210]
0x1800a129b  lea     rdx, [rsp+250h+var_208]
0x1800a12a0  lea     rcx, [rbp+150h+var_178]
0x1800a12a4  call    sub_18000B710
0x1800a12a9  nop
0x1800a12aa  lea     rax, [rbp+150h+var_1A0]
0x1800a12ae  mov     [rsp+250h+var_208], rax
0x1800a12b3  mov     [rbp+150h+var_180], r14b
0x1800a12b7  xorps   xmm0, xmm0
0x1800a12ba  movups  [rsp+250h+var_200], xmm0
0x1800a12bf  xorps   xmm1, xmm1
0x1800a12c2  movdqu  [rsp+250h+var_1F0], xmm1
0x1800a12c8  mov     r8d, 22h ; '"'
0x1800a12ce  lea     rdx, aCombaserogetac_0; "CombaseRoGetActivationFactoryEmpty"
0x1800a12d5  lea     rcx, [rsp+250h+var_200]
0x1800a12da  call    sub_180004678
0x1800a12df  nop
0x1800a12e0  xorps   xmm0, xmm0
0x1800a12e3  movups  [rsp+250h+var_1E0], xmm0
0x1800a12e8  xorps   xmm1, xmm1
0x1800a12eb  movdqu  [rbp+150h+var_1D0], xmm1
0x1800a12f0  mov     r8d, 72h ; 'r'
0x1800a12f6  lea     rdx, aCUsersContaine_26; "C:\\Users\\ContainerAdministrator\\ESP"...
0x1800a12fd  lea     rcx, [rsp+250h+var_1E0]
0x1800a1302  call    sub_180004678
0x1800a1307  nop
0x1800a1308  call    cs:__imp_GetLastError
0x1800a130e  movzx   edx, ax
0x1800a1311  or      edx, 80070000h
0x1800a1317  test    eax, eax
0x1800a1319  cmovle  edx, eax
0x1800a131c  lea     rax, [rbp+150h+var_178]
0x1800a1320  mov     [rsp+250h+var_218], rax
0x1800a1325  lea     rax, [rbp+150h+var_1A0]
0x1800a1329  mov     [rsp+250h+var_220], rax
0x1800a132e  mov     [rsp+250h+var_228], r14
0x1800a1333  lea     rax, [rsp+250h+var_200]
0x1800a1338  mov     [rsp+250h+var_230], rax
0x1800a133d  mov     r9d, 0F5h
0x1800a1343  lea     r8, [rsp+250h+var_1E0]
0x1800a1348  lea     rcx, [rbp+150h+var_130]
0x1800a134c  call    sub_180018D7C
0x1800a1351  mov     rcx, rax
0x1800a1354  movups  xmm0, xmmword ptr [rax]
0x1800a1357  movdqu  xmmword ptr [rdi], xmm0
0x1800a135b  xorps   xmm0, xmm0
0x1800a135e  movups  xmmword ptr [rdi+10h], xmm0
0x1800a1362  mov     [rdi+20h], r14
0x1800a1366  mov     [rdi+28h], r14
0x1800a136a  movups  xmm0, xmmword ptr [rax+10h]
0x1800a136e  movups  xmmword ptr [rdi+10h], xmm0
0x1800a1372  movups  xmm1, xmmword ptr [rax+20h]
0x1800a1376  movups  xmmword ptr [rdi+20h], xmm1
0x1800a137a  mov     [rax+20h], r14
0x1800a137e  mov     edx, 0Fh
0x1800a1383  mov     [rax+28h], rdx
0x1800a1387  mov     [rax+10h], r14b
0x1800a138b  mov     eax, [rax+30h]
0x1800a138e  mov     [rdi+30h], eax
0x1800a1391  xorps   xmm0, xmm0
0x1800a1394  movups  xmmword ptr [rdi+38h], xmm0
0x1800a1398  mov     [rdi+48h], r14
0x1800a139c  mov     [rdi+50h], r14
0x1800a13a0  movups  xmm0, xmmword ptr [rcx+38h]
0x1800a13a4  movups  xmmword ptr [rdi+38h], xmm0
0x1800a13a8  movups  xmm1, xmmword ptr [rcx+48h]
0x1800a13ac  movups  xmmword ptr [rdi+48h], xmm1
0x1800a13b0  mov     [rcx+48h], r14
0x1800a13b4  mov     [rcx+50h], rdx
0x1800a13b8  mov     [rcx+38h], r14b
0x1800a13bc  xorps   xmm0, xmm0
0x1800a13bf  movups  xmmword ptr [rdi+58h], xmm0
0x1800a13c3  mov     [rdi+68h], r14
0x1800a13c7  mov     [rdi+70h], r14
0x1800a13cb  movups  xmm0, xmmword ptr [rcx+58h]
0x1800a13cf  movups  xmmword ptr [rdi+58h], xmm0
0x1800a13d3  movups  xmm1, xmmword ptr [rcx+68h]
0x1800a13d7  movups  xmmword ptr [rdi+68h], xmm1
0x1800a13db  mov     [rcx+68h], r14
  ... truncated ...
```

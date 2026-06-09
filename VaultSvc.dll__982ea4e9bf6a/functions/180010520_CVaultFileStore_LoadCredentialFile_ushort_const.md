# CVaultFileStore::LoadCredentialFile(ushort const *)

- ea: `0x180010520`
- end: `0x180010f10`
- name: `?LoadCredentialFile@CVaultFileStore@@AEAAKPEBG@Z`
- size: `2544`
- prototype: `__int64 __fastcall(const wchar_t **this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x18000f0d8`

## callees

- `0x180003140`
- `0x180006680`
- `0x180010520`
- `0x180011eb0`
- `0x180012210`
- `0x180024b08`
- `0x18003a580`
- `0x18003aef8`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003b9ac`
- `0x18004b430`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800106d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001066e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010762`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010a11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001066e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010762`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010a11`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001078f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001078f`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180010731`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180010731`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010709`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010709`

## pseudocode

```c
__int64 __fastcall CVaultFileStore::LoadCredentialFile(const wchar_t **this, const unsigned __int16 *a2)
{
  unsigned int v4; // r13d
  PVOID *v5; // r10
  const wchar_t *v6; // r14
  __int64 v7; // r15
  __int64 v8; // rbx
  __int64 v9; // rdi
  unsigned int v10; // eax
  wchar_t *v11; // rax
  const WCHAR *v12; // r12
  wchar_t *v13; // r9
  DWORD v14; // edi
  HANDLE FileW; // r14
  DWORD LowPart; // ebx
  CVaultCredential *v17; // rax
  CVaultCredential *v18; // rdi
  CVaultCredential *v19; // r12
  DWORD LastError; // edi
  __int64 v21; // r14
  DWORD v22; // edi
  unsigned int v23; // ebx
  CVaultCredential *v24; // r14
  __int64 v26; // rbx
  __int64 v27; // rax
  unsigned __int64 v28; // r14
  _WORD *v29; // rdi
  __int64 v30; // rax
  const unsigned __int16 *v31; // rdx
  unsigned __int16 *v32; // rcx
  int v33; // r12d
  unsigned __int16 v34; // r8
  struct IVaultCredential *QuadPart; // r14
  unsigned int v36; // eax
  unsigned int v37; // eax
  __int64 (__fastcall *v38)(_QWORD); // [rsp+40h] [rbp-C0h] BYREF
  CVaultCredential *v39; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+50h] [rbp-B0h]
  _LARGE_INTEGER FileSize[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  _WORD *v43; // [rsp+70h] [rbp-90h]
  int v44; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v45)(_QWORD); // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h] BYREF
  int v47; // [rsp+90h] [rbp-70h]
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  CVaultCredential *v49; // [rsp+A0h] [rbp-60h]
  int v50; // [rsp+A8h] [rbp-58h]
  __int64 v51; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v52; // [rsp+B8h] [rbp-48h]
  int v53; // [rsp+C0h] [rbp-40h]
  __int64 (__fastcall *v54)(_QWORD); // [rsp+C8h] [rbp-38h] BYREF
  CVaultCredential *v55; // [rsp+D0h] [rbp-30h]
  int v56; // [rsp+D8h] [rbp-28h]
  DWORD NumberOfBytesRead; // [rsp+E0h] [rbp-20h] BYREF
  CVaultMemoryStore *v58; // [rsp+E8h] [rbp-18h]
  BOOL (__stdcall *Buf1)(HANDLE); // [rsp+F0h] [rbp-10h] BYREF
  HANDLE v60; // [rsp+F8h] [rbp-8h]
  int v61; // [rsp+100h] [rbp+0h]
  __int128 v62; // [rsp+108h] [rbp+8h] BYREF

  v58 = (CVaultMemoryStore *)this;
  v54 = AutoDereference<IVaultKeyManager>;
  v55 = 0;
  v56 = 0;
  v52 = 0;
  v53 = 0;
  v51 = 0;
  v49 = 0;
  v50 = 0;
  v48 = 0;
  v45 = AutoDereference<IVaultKeyManager>;
  v46 = 0;
  v47 = 0;
  v62 = 0;
  v43 = 0;
  v44 = 0;
  v42 = 0;
  v4 = 14;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, a2);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = this[39];
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v6[v8] );
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = v9 + v8;
  if ( (int)v9 + (int)v8 < (unsigned int)v8 || v10 + 2 < v10 )
  {
    v4 = 534;
    goto LABEL_8;
  }
  v11 = (wchar_t *)LocalAlloc(0x40u, 2LL * (v10 + 2));
  v12 = v11;
  if ( !v11 )
  {
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    {
LABEL_11:
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v42);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v45);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v48);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v51);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v54);
      return v4;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_13ef719d6c39382471689e3834fa0ad3_Traceguids);
      v5 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_8:
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
      WPP_SF_d(v5[2], 15, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, v4);
    goto LABEL_11;
  }
  v52 = v11;
  wcscpy_s(v11, (unsigned int)(v8 + 1), v6);
  v13 = (wchar_t *)&v12[(unsigned int)v8];
  FileSize[0].QuadPart = (LONGLONG)v13;
  if ( (_DWORD)v8 && v6[(unsigned int)(v8 - 1)] != 92 )
  {
    wcscpy_s((wchar_t *)&v12[(unsigned int)v8], 2u, L"\\");
    v13 = (wchar_t *)(FileSize[0].QuadPart + 2);
  }
  wcscpy_s(v13, (unsigned int)(v9 + 1), a2);
  v14 = dword_18005F630;
  NumberOfBytesRead = 0;
  FileSize[0].QuadPart = 0;
  v39 = 0;
  v40 = 0;
  v38 = 0;
  Buf1 = CloseHandle;
  v60 = 0;
  v61 = 0;
  FileW = CreateFileW(v12, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&Buf1);
  v60 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&Buf1);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
  }
  else
  {
    if ( GetFileSizeEx(FileW, FileSize) )
    {
      if ( FileSize[0].HighPart || (LowPart = FileSize[0].LowPart, v14) && FileSize[0].LowPart > v14 )
      {
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&Buf1);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
        LastError = 223;
        goto LABEL_66;
      }
      v17 = (CVaultCredential *)LocalAlloc(0x40u, FileSize[0].LowPart);
      v18 = v17;
      v39 = v17;
      if ( !v17 )
      {
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&Buf1);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
        LastError = 14;
        goto LABEL_66;
      }
      if ( ReadFile(FileW, v17, LowPart, &NumberOfBytesRead, 0) )
      {
        v19 = v18;
        v49 = v18;
        v39 = 0;
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&Buf1);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
        goto LABEL_23;
      }
    }
    LastError = GetLastError();
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&Buf1);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
  }
  LowPart = 0;
  if ( LastError )
  {
LABEL_66:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, LastError);
    goto LABEL_67;
  }
  v19 = v49;
LABEL_23:
  if ( LowPart < 0x10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, 122);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v42);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v45);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v48);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v51);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v54);
    return 122;
  }
  v62 = *(_OWORD *)v19;
  LastError = (*(__int64 (__fastcall **)(CVaultMemoryStore *, __int128 *, __int64 *))(*(_QWORD *)v58 + 80LL))(
                v58,
                &v62,
                &v46);
  if ( LastError )
  {
LABEL_67:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v42);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v45);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v48);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v51);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v54);
    return LastError;
  }
  v21 = v46;
  (*(void (__fastcall **)(__int64, BOOL (__stdcall **)(HANDLE)))(*(_QWORD *)v46 + 24LL))(v46, &Buf1);
  v38 = AutoDereference<IVaultKeyManager>;
  v39 = 0;
  v40 = 0;
  *(_OWORD *)&FileSize[0].LowPart = *(_OWORD *)v19;
  if ( memcmp_0(&Buf1, FileSize, 0x10u) )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
    v23 = 87;
    goto LABEL_30;
  }
  v22 = LowPart - 16;
  if ( LowPart - 16 < 4 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
    v23 = 122;
    goto LABEL_30;
  }
  v23 = CVaultCredential::CreateNewCredential(v21, *((unsigned int *)v19 + 4), 1, &v39);
  if ( v23
    || (v24 = v39,
        FileSize[0].QuadPart = (LONGLONG)v39,
        (v23 = CVaultCredential::DeserializeCredential(v39, (unsigned __int8 *)v19 + 20, v22 - 4)) != 0) )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
LABEL_30:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, v23);
LABEL_94:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v42);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v45);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v48);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v51);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v54);
    return v23;
  }
  v39 = 0;
  v55 = v24;
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v38);
  v26 = -1;
  do
    ++v26;
  while ( a2[v26] );
  v27 = (unsigned int)(v26 + 1);
  if ( (unsigned int)v27 < (unsigned int)v26 )
  {
    v4 = 534;
LABEL_38:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v42);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v45);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v48);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v51);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v54);
    return v4;
  }
  v28 = (unsigned int)v27;
  v29 = LocalAlloc(0x40u, 2 * v27);
  v43 = v29;
  if ( !v29 )
    goto LABEL_38;
  if ( !v28 )
  {
    LOWORD(v33) = 87;
    goto LABEL_50;
  }
  if ( v28 > 0x7FFFFFFF )
  {
    LOWORD(v33) = 87;
    *v29 = 0;
LABEL_50:
    VaultFreeInternal(v29);
    v43 = 0;
    v4 = (unsigned __int16)v33;
    goto LABEL_38;
  }
  v30 = 2147483646;
  v31 = a2;
  v32 = v29;
  v33 = 0;
  while ( v30 )
  {
    v34 = *v31;
    if ( !*v31 )
      break;
    ++v31;
    *v32++ = v34;
    --v30;
    if ( !--v28 )
    {
      --v32;
      v33 = -2147024774;
      break;
    }
  }
  *v32 = 0;
  if ( v33 < 0 )
    goto LABEL_50;
  v29[(unsigned int)v26 - 5] = 0;
  QuadPart = (struct IVaultCredential *)FileSize[0].QuadPart;
  do
    ++v7;
  while ( v29[v7] );
  v36 = (*(__int64 (__fastcall **)(_LARGE_INTEGER, _WORD *, _QWORD))(*(_QWORD *)FileSize[0].QuadPart + 88LL))(
          FileSize[0],
          v29,
          (unsigned int)(2 * v7 + 2));
  v23 = v36;
  if ( v36 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, v36);
    goto LABEL_94;
  }
  v37 = CVaultMemoryStore::SubmitCredentialToStoreNoAlloc(v58, QuadPart, v29);
  v23 = v37;
  if ( v37 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, v37);
    goto LABEL_94;
  }
  v43 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids, a2);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v42);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v45);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v48);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v51);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v54);
  return 0;
}

```

## disassembly

```asm
0x180010520  mov     [rsp-8+arg_10], rbx
0x180010525  push    rbp
0x180010526  push    rsi
0x180010527  push    rdi
0x180010528  push    r12
0x18001052a  push    r13
0x18001052c  push    r14
0x18001052e  push    r15
0x180010530  lea     rbp, [rsp-20h]
0x180010535  sub     rsp, 120h
0x18001053c  mov     rax, cs:__security_cookie
0x180010543  xor     rax, rsp
0x180010546  mov     [rbp+50h+var_38], rax
0x18001054a  mov     rsi, rdx
0x18001054d  mov     rbx, rcx
0x180010550  mov     [rbp+50h+var_68], rcx
0x180010554  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x18001055b  mov     [rbp+50h+var_88], rax
0x18001055f  xor     ecx, ecx
0x180010561  mov     [rbp+50h+var_80], rcx
0x180010565  mov     [rbp+50h+var_78], ecx
0x180010568  mov     [rbp+50h+var_98], rcx
0x18001056c  mov     [rbp+50h+var_90], ecx
0x18001056f  mov     [rbp+50h+var_A0], rcx
0x180010573  mov     [rbp+50h+var_B0], rcx
0x180010577  mov     [rbp+50h+var_A8], ecx
0x18001057a  mov     [rbp+50h+var_B8], rcx
0x18001057e  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180010585  mov     [rbp+50h+var_D0], rax
0x180010589  mov     [rbp+50h+var_C8], rcx
0x18001058d  mov     [rbp+50h+var_C0], ecx
0x180010590  xorps   xmm0, xmm0
0x180010593  movups  [rbp+50h+var_48], xmm0
0x180010597  mov     [rsp+150h+var_E0], rcx
0x18001059c  mov     [rsp+150h+var_D8], ecx
0x1800105a0  mov     [rsp+150h+var_E8], rcx
0x1800105a5  lea     rax, WPP_GLOBAL_Control
0x1800105ac  mov     r13d, 0Eh
0x1800105b2  mov     r10, cs:WPP_GLOBAL_Control
0x1800105b9  cmp     r10, rax
0x1800105bc  jnz     loc_180010C57
0x1800105c2  mov     r14, [rbx+138h]
0x1800105c9  mov     r15, 0FFFFFFFFFFFFFFFFh
0x1800105d0  mov     rbx, r15
0x1800105d3  inc     rbx
0x1800105d6  cmp     word ptr [r14+rbx*2], 0
0x1800105dc  jnz     short loc_1800105D3
0x1800105de  mov     rdi, r15
0x1800105e1  lea     rdi, [rdi+1]
0x1800105e5  cmp     word ptr [rsi+rdi*2], 0
0x1800105ea  jnz     short loc_1800105E1
0x1800105ec  lea     eax, [rdi+rbx]
0x1800105ef  cmp     eax, ebx
0x1800105f1  jnb     short loc_18001065D
0x1800105f3  lea     r14, WPP_GLOBAL_Control
0x1800105fa  mov     r13d, 216h
0x180010600  cmp     r10, r14
0x180010603  jz      short loc_180010625
0x180010605  test    byte ptr [r10+1Ch], 8
0x18001060a  jz      short loc_180010625
0x18001060c  mov     edx, 0Fh
0x180010611  mov     r9d, r13d
0x180010614  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x18001061b  mov     rcx, [r10+10h]
0x18001061f  call    WPP_SF_d
0x180010624  nop
0x180010625  lea     rcx, [rsp+150h+var_E8]
0x18001062a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001062f  nop
0x180010630  lea     rcx, [rbp+50h+var_D0]
0x180010634  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010639  nop
0x18001063a  lea     rcx, [rbp+50h+var_B8]
0x18001063e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010643  nop
0x180010644  lea     rcx, [rbp+50h+var_A0]
0x180010648  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001064d  nop
0x18001064e  lea     rcx, [rbp+50h+var_88]
0x180010652  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010657  nop
0x180010658  jmp     loc_1800109A6
0x18001065d  lea     ecx, [rax+2]
0x180010660  cmp     ecx, eax
0x180010662  jb      short loc_1800105F3
0x180010664  mov     edx, ecx
0x180010666  add     rdx, rdx; uBytes
0x180010669  mov     ecx, 40h ; '@'; uFlags
0x18001066e  call    cs:__imp_LocalAlloc
0x180010674  mov     r12, rax
0x180010677  test    rax, rax
0x18001067a  jz      loc_180010C84
0x180010680  mov     [rbp+50h+var_98], rax
0x180010684  lea     edx, [rbx+1]; SizeInWords
0x180010687  mov     r8, r14; Source
0x18001068a  mov     rcx, rax; Destination
0x18001068d  call    wcscpy_s
0x180010692  mov     eax, ebx
0x180010694  lea     r9, [r12+rax*2]
0x180010698  mov     qword ptr [rsp+150h+FileSize], r9
0x18001069d  test    ebx, ebx
0x18001069f  jnz     loc_180010BA3
0x1800106a5  lea     edx, [rdi+1]; SizeInWords
0x1800106a8  mov     r8, rsi; Source
0x1800106ab  mov     rcx, r9; Destination
0x1800106ae  call    wcscpy_s
0x1800106b3  mov     edi, cs:dword_18005F630
0x1800106b9  xor     ecx, ecx
0x1800106bb  mov     [rbp+50h+NumberOfBytesRead], ecx
0x1800106be  mov     qword ptr [rsp+150h+FileSize], rcx
0x1800106c3  mov     [rsp+150h+var_108], rcx
0x1800106c8  mov     [rsp+150h+var_100], ecx
0x1800106cc  mov     [rsp+150h+var_110], rcx
0x1800106d1  mov     rax, cs:__imp_CloseHandle
0x1800106d8  mov     [rbp+50h+Buf1], rax
0x1800106dc  mov     [rbp+50h+var_58], rcx
0x1800106e0  mov     [rbp+50h+var_50], ecx
0x1800106e3  mov     [rsp+150h+hTemplateFile], rcx; hTemplateFile
0x1800106e8  mov     [rsp+150h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800106f0  mov     [rsp+150h+dwCreationDisposition], 3; dwCreationDisposition
0x1800106f8  xor     r9d, r9d; lpSecurityAttributes
0x1800106fb  mov     edx, 80000000h; dwDesiredAccess
0x180010700  mov     r8d, 1; dwShareMode
0x180010706  mov     rcx, r12; lpFileName
0x180010709  call    cs:__imp_CreateFileW
0x18001070f  mov     r14, rax
0x180010712  lea     rcx, [rbp+50h+Buf1]
0x180010716  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001071b  mov     [rbp+50h+var_58], r14
0x18001071f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180010723  jz      loc_180010CC7
0x180010729  lea     rdx, [rsp+150h+FileSize]; lpFileSize
0x18001072e  mov     rcx, r14; hFile
0x180010731  call    cs:__imp_GetFileSizeEx
0x180010737  test    eax, eax
0x180010739  jz      loc_180010CE9
0x18001073f  cmp     dword ptr [rsp+150h+FileSize+4], 0
0x180010744  jnz     loc_180010D0B
0x18001074a  mov     ebx, dword ptr [rsp+150h+FileSize]
0x18001074e  test    edi, edi
0x180010750  jz      short loc_18001075A
0x180010752  cmp     ebx, edi
0x180010754  ja      loc_180010D2A
0x18001075a  mov     rdx, rbx; uBytes
0x18001075d  mov     ecx, 40h ; '@'; uFlags
0x180010762  call    cs:__imp_LocalAlloc
0x180010768  mov     rdi, rax
0x18001076b  mov     [rsp+150h+var_108], rax
0x180010770  test    rax, rax
0x180010773  jz      loc_180010D49
0x180010779  mov     qword ptr [rsp+150h+dwCreationDisposition], 0; lpOverlapped
0x180010782  lea     r9, [rbp+50h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180010786  mov     r8d, ebx; nNumberOfBytesToRead
0x180010789  mov     rdx, rax; lpBuffer
0x18001078c  mov     rcx, r14; hFile
0x18001078f  call    cs:__imp_ReadFile
0x180010795  test    eax, eax
0x180010797  jz      loc_180010D66
0x18001079d  mov     r12, rdi
0x1800107a0  mov     [rbp+50h+var_B0], rdi
0x1800107a4  mov     [rsp+150h+var_108], 0
0x1800107ad  lea     rcx, [rbp+50h+Buf1]
0x1800107b1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800107b6  nop
0x1800107b7  lea     rcx, [rsp+150h+var_110]
0x1800107bc  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800107c1  nop
0x1800107c2  cmp     ebx, 10h
0x1800107c5  jb      loc_180010DB8
0x1800107cb  movups  xmm0, xmmword ptr [r12]
0x1800107d0  movups  [rbp+50h+var_48], xmm0
0x1800107d4  mov     rcx, [rbp+50h+var_68]
0x1800107d8  mov     rax, [rcx]
0x1800107db  lea     r8, [rbp+50h+var_C8]
0x1800107df  lea     rdx, [rbp+50h+var_48]
0x1800107e3  mov     rax, [rax+50h]
0x1800107e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107ec  mov     edi, eax
0x1800107ee  test    eax, eax
0x1800107f0  jnz     loc_180010936
0x1800107f6  mov     r14, [rbp+50h+var_C8]
0x1800107fa  mov     rax, [r14]
0x1800107fd  lea     rdx, [rbp+50h+Buf1]
0x180010801  mov     rcx, r14
0x180010804  mov     rax, [rax+18h]
0x180010808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080d  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180010814  mov     [rsp+150h+var_110], rax
0x180010819  xor     eax, eax
0x18001081b  mov     [rsp+150h+var_108], rax
0x180010820  mov     [rsp+150h+var_100], eax
0x180010824  movups  xmm0, xmmword ptr [r12]
0x180010829  movups  xmmword ptr [rsp+150h+FileSize], xmm0
0x18001082e  mov     r8d, 10h; Size
0x180010834  lea     rdx, [rsp+150h+FileSize]; Buf2
0x180010839  lea     rcx, [rbp+50h+Buf1]; Buf1
0x18001083d  call    memcmp_0
0x180010842  test    eax, eax
0x180010844  jnz     loc_180010914
0x18001084a  lea     edi, [rbx-10h]
0x18001084d  cmp     edi, 4
0x180010850  jb      loc_180010E29
0x180010856  lea     r9, [rsp+150h+var_108]
0x18001085b  mov     r8d, 1
0x180010861  mov     edx, [r12+10h]
0x180010866  mov     rcx, r14
0x180010869  call    ?CreateNewCredential@CVaultCredential@@SAKPEAUIVaultSchema@@KW4EVaultCredentialOrigin@@PEAPEAV1@@Z; CVaultCredential::CreateNewCredential(IVaultSchema *,ulong,EVaultCredentialOrigin,CVaultCredential * *)
0x18001086e  mov     ebx, eax
0x180010870  test    eax, eax
0x180010872  jnz     loc_180010926
0x180010878  mov     r14, [rsp+150h+var_108]
0x18001087d  mov     qword ptr [rsp+150h+FileSize], r14
0x180010882  lea     r8d, [rdi-4]; unsigned int
0x180010886  lea     rdx, [r12+14h]; unsigned __int8 *
0x18001088b  mov     rcx, r14; this
0x18001088e  call    ?DeserializeCredential@CVaultCredential@@AEAAKPEAEK@Z; CVaultCredential::DeserializeCredential(uchar *,ulong)
0x180010893  mov     ebx, eax
0x180010895  test    eax, eax
0x180010897  jz      loc_1800109D0
0x18001089d  lea     rcx, [rsp+150h+var_110]
0x1800108a2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800108a7  nop
0x1800108a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108af  lea     r14, WPP_GLOBAL_Control
0x1800108b6  cmp     rcx, r14
0x1800108b9  jz      short loc_1800108DA
0x1800108bb  test    byte ptr [rcx+1Ch], 8
0x1800108bf  jz      short loc_1800108DA
0x1800108c1  mov     edx, 12h
0x1800108c6  mov     r9d, ebx
0x1800108c9  lea     r8, WPP_c304bf9ddc9a325b3ef15398c2399f48_Traceguids
0x1800108d0  mov     rcx, [rcx+10h]
0x1800108d4  call    WPP_SF_d
0x1800108d9  nop
0x1800108da  lea     rcx, [rsp+150h+var_E8]
0x1800108df  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800108e4  nop
0x1800108e5  lea     rcx, [rbp+50h+var_D0]
0x1800108e9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800108ee  nop
0x1800108ef  lea     rcx, [rbp+50h+var_B8]
0x1800108f3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800108f8  nop
0x1800108f9  lea     rcx, [rbp+50h+var_A0]
0x1800108fd  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010902  nop
0x180010903  lea     rcx, [rbp+50h+var_88]
0x180010907  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001090c  nop
0x18001090d  mov     eax, ebx
0x18001090f  jmp     loc_1800109A9
0x180010914  lea     rcx, [rsp+150h+var_110]
0x180010919  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001091e  nop
0x18001091f  mov     ebx, 57h ; 'W'
0x180010924  jmp     short loc_1800108A8
0x180010926  lea     rcx, [rsp+150h+var_110]
0x18001092b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010930  nop
0x180010931  jmp     loc_1800108A8
0x180010936  lea     rcx, [rsp+150h+var_E8]
0x18001093b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010940  nop
0x180010941  lea     rcx, [rbp+50h+var_D0]
0x180010945  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001094a  nop
0x18001094b  lea     rcx, [rbp+50h+var_B8]
0x18001094f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010954  nop
0x180010955  lea     rcx, [rbp+50h+var_A0]
0x180010959  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001095e  nop
0x18001095f  lea     rcx, [rbp+50h+var_88]
0x180010963  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010968  nop
0x180010969  mov     eax, edi
0x18001096b  jmp     short loc_1800109A9
0x18001096d  mov     r13d, 216h
0x180010973  lea     rcx, [rsp+150h+var_E8]
0x180010978  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001097d  nop
0x18001097e  lea     rcx, [rbp+50h+var_D0]
0x180010982  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010987  nop
0x180010988  lea     rcx, [rbp+50h+var_B8]
0x18001098c  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010991  nop
0x180010992  lea     rcx, [rbp+50h+var_A0]
0x180010996  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001099b  nop
0x18001099c  lea     rcx, [rbp+50h+var_88]
0x1800109a0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800109a5  nop
0x1800109a6  mov     eax, r13d
0x1800109a9  mov     rcx, [rbp+50h+var_38]
0x1800109ad  xor     rcx, rsp; StackCookie
0x1800109b0  call    __security_check_cookie
0x1800109b5  mov     rbx, [rsp+150h+arg_10]
0x1800109bd  add     rsp, 120h
0x1800109c4  pop     r15
  ... truncated ...
```

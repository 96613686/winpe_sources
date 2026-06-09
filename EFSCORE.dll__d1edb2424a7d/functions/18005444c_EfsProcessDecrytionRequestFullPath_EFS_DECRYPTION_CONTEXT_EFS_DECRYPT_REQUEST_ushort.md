# EfsProcessDecrytionRequestFullPath(_EFS_DECRYPTION_CONTEXT *,_EFS_DECRYPT_REQUEST *,ushort *)

- ea: `0x18005444c`
- end: `0x180054d8b`
- name: `?EfsProcessDecrytionRequestFullPath@@YAXPEAU_EFS_DECRYPTION_CONTEXT@@PEAU_EFS_DECRYPT_REQUEST@@PEAG@Z`
- size: `2367`
- prototype: `void __fastcall(struct _EFS_DECRYPTION_CONTEXT *, struct _EFS_DECRYPT_REQUEST *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180054d94`

## callees

- `0x180005045`
- `0x18005444c`
- `0x1800612fc`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180080f58`
- `0x1800dddf0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180054803`
- `msvcrt!_wcsicmp` at `0x180054803`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180054ab9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180054ab9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054816`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054d0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054816`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180054d0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054824`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054d1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054824`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180054d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054c96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800547c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800548c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800549bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054ce1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800547c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800548c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800549bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054ce1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054d29`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180054ad2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180054ad2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800547e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800547e9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180054504`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180054504`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x180054548`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x180054548`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientQueryProtectors` at `0x18005472f`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientQueryProtectors` at `0x18005472f`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientGetEncryptedFileVersion` at `0x18005468f`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientGetEncryptedFileVersion` at `0x18005468f`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientFreeProtectorList` at `0x1800546f7`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientFreeProtectorList` at `0x180054cf9`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientFreeProtectorList` at `0x1800546f7`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientFreeProtectorList` at `0x180054cf9`

## pseudocode

```c
void __fastcall EfsProcessDecrytionRequestFullPath(HANDLE *a1, struct _EFS_DECRYPT_REQUEST *a2, unsigned __int16 *a3)
{
  HLOCAL v3; // rdi
  HANDLE v6; // rax
  unsigned int v7; // ebx
  unsigned int v8; // r12d
  int v9; // r15d
  void *v10; // r14
  int v11; // ecx
  DWORD v12; // eax
  int v13; // ecx
  int v14; // eax
  int v15; // ecx
  int v16; // r12d
  int v17; // ecx
  int EncryptedFileVersion; // eax
  int v19; // ecx
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rcx
  HANDLE *v23; // r15
  int v24; // ecx
  HANDLE ProcessHeap; // rax
  int v26; // ecx
  int v27; // eax
  int v28; // eax
  signed int v29; // eax
  int v30; // eax
  signed int LastError; // eax
  HANDLE v32; // rax
  bool v33; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v36; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v37; // [rsp+7Ch] [rbp-84h]
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  int v39; // [rsp+88h] [rbp-78h] BYREF
  int v40; // [rsp+8Ch] [rbp-74h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h] BYREF
  int v42; // [rsp+98h] [rbp-68h] BYREF
  HANDLE *v43; // [rsp+A0h] [rbp-60h]
  unsigned __int8 v44[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[108]; // [rsp+B4h] [rbp-4Ch] BYREF
  HANDLE Handles[3]; // [rsp+120h] [rbp+20h] BYREF

  v3 = 0;
  Handles[0] = hHandle;
  Handles[1] = a1[6];
  v6 = a1[5];
  v43 = a1;
  v7 = 0;
  Handles[2] = v6;
  v8 = 0;
  v39 = 0;
  v9 = 0;
  v42 = 0;
  v35 = 0;
  v10 = 0;
  hMem = 0;
  lpMem = 0;
  v40 = 0;
  memset_0(v44, 0, 0x6Cu);
  v34 = 0;
  v33 = 0;
  fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 45, 91);
  while ( 1 )
  {
    v12 = WaitForMultipleObjects(3u, Handles, 0, 0xFFFFFFFF);
    if ( v12 < 2 )
      break;
    if ( v12 != 2 )
    {
      if ( v12 == -1 )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 45, 109);
      }
      else
      {
        v7 = -2147418113;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 45, 111);
      }
      break;
    }
    fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 121);
    v14 = EfsClientDecryptFile(a3, 0);
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v7,
                45,
                121) >= 0 )
    {
      v30 = ++*((_DWORD *)a2 + 10);
      ++*((_DWORD *)a2 + 11);
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)L"Decrypted",
        v30,
        45,
        128);
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (_DWORD)a3,
        0,
        45,
        129);
      goto LABEL_63;
    }
    v37 = v8 + 1;
    v16 = 0;
    if ( v7 == -2147024864 )
    {
      v16 = 1;
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)L"Sharing violation while trying to decrypt",
        0,
        45,
        146);
    }
    if ( v37 > 3 )
      break;
    if ( !v9 )
    {
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_TRACE_EVENT,
        (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
        (unsigned int)L"Failed to decrypt",
        v7,
        45,
        166);
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (_DWORD)a3,
        0,
        45,
        167);
      fnEfsLogTrace1Strings(v17, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 171);
      EncryptedFileVersion = EfsClientGetEncryptedFileVersion(a3, &v39, &v42);
      v7 = EncryptedFileVersion;
      if ( EncryptedFileVersion > 0 )
        v7 = (unsigned __int16)EncryptedFileVersion | 0x80070000;
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v7,
                  45,
                  171) < 0 )
        break;
      if ( v39 != 5 )
      {
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"Non-NCrypt protector EFS version",
          v39,
          45,
          179);
        break;
      }
      v19 = v35;
      if ( v35 )
      {
        EfsClientFreeProtectorList();
        v35 = 0;
      }
      fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 192);
      v20 = EfsClientQueryProtectors(a3, &v35);
      v7 = v20;
      if ( v20 > 0 )
        v7 = (unsigned __int16)v20 | 0x80070000;
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v7,
                  45,
                  192) < 0 )
        break;
      v21 = v35;
      if ( !v35
        || !*(_DWORD *)v35
        || (v22 = *(_QWORD *)(v35 + 8)) == 0
        || !*(_QWORD *)(*(_QWORD *)v22 + 8LL)
        || !*(_QWORD *)(*(_QWORD *)v22 + 16LL) )
      {
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"No protectors found",
          0,
          45,
          204);
        break;
      }
      if ( hMem )
      {
        LocalFree(hMem);
        v21 = v35;
        hMem = 0;
      }
      if ( !ConvertSidToStringSidW(*(PSID *)(**(_QWORD **)(v21 + 8) + 8LL), (LPWSTR *)&hMem) )
      {
        v29 = GetLastError();
        v7 = v29;
        if ( v29 > 0 )
          v7 = (unsigned __int16)v29 | 0x80070000;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 45, 219);
        break;
      }
      v23 = v43;
      if ( _wcsicmp((const wchar_t *)hMem, (const wchar_t *)v43[4]) )
      {
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"Encrypted file belongs to other user",
          ++*((_DWORD *)a2 + 12),
          45,
          229);
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (_DWORD)hMem,
          0,
          45,
          230);
        break;
      }
      if ( v10 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v10);
        lpMem = 0;
      }
      fnEfsLogTrace1Strings(v24, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 244);
      v7 = EfsConvertProtectorToExternalId(
             *(const unsigned __int16 **)(**(_QWORD **)(v35 + 8) + 16LL),
             (unsigned __int16 **)&lpMem,
             &v33);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  v7,
                  45,
                  244) < 0 )
      {
        v10 = lpMem;
        goto LABEL_62;
      }
      v36 = 0;
      if ( v3 )
      {
        LocalFree(v3);
        v34 = 0;
      }
      memset_0(v45, 0, 0x68u);
      *(_DWORD *)v44 = 108;
      fnEfsLogTrace1Strings(v26, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 13);
      v10 = lpMem;
      v7 = EdpCredSvcControl(
             0,
             2u,
             (const unsigned __int16 *)v23[4],
             (const unsigned __int16 *)v23[4],
             (const unsigned __int16 *)lpMem,
             v44,
             *(unsigned int *)v44,
             0,
             0,
             (unsigned __int8 **)&v34,
             &v36);
      v27 = fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v7,
              45,
              13);
      v3 = v34;
      if ( v27 < 0 )
        goto LABEL_62;
      v40 = 1;
      v9 = 1;
      if ( v34 && !*((_DWORD *)v34 + 2) )
      {
        if ( !*((_DWORD *)v34 + 4) )
        {
          fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
            (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
            (unsigned int)L"Encrypted file is revoked",
            0,
            45,
            24);
          goto LABEL_63;
        }
        fnEfsLogTrace1String1Dword(
          g_hPublisher,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
          (unsigned int)L"Encrypted file is missing credentials",
          0,
          45,
          33);
        goto LABEL_62;
      }
    }
    v36 = 0;
    if ( v3 )
    {
      LocalFree(v3);
      v34 = 0;
    }
    fnEfsLogTrace1Strings(v15, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 61);
    v7 = EdpCredSvcControl(
           0,
           1u,
           (const unsigned __int16 *)v43[4],
           (const unsigned __int16 *)v43[4],
           (const unsigned __int16 *)v10,
           0,
           0,
           0,
           0,
           (unsigned __int8 **)&v34,
           &v36);
    v28 = fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
            (unsigned int)&sourceString,
            v7,
            45,
            61);
    v3 = v34;
    if ( v28 < 0 )
      break;
    if ( v34 && *((_DWORD *)v34 + 2) )
    {
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)EFS_TRACE_MSG_DWORD_EVENT,
        (unsigned int)L"Encrypted file keys are locked",
        0,
        45,
        72);
      ResetEvent(v43[5]);
    }
    else
    {
      Sleep(v16 != 0 ? 15000 : 500);
    }
    v8 = v37;
  }
  if ( !v40 )
    goto LABEL_63;
LABEL_62:
  ++*((_DWORD *)a2 + 11);
LABEL_63:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v35 )
  {
    EfsClientFreeProtectorList();
    v35 = 0;
  }
  if ( v10 )
  {
    v32 = GetProcessHeap();
    HeapFree(v32, 0, v10);
  }
  if ( v3 )
    LocalFree(v3);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v7,
    45,
    108);
}

```

## disassembly

```asm
0x18005444c  mov     [rsp-8+arg_18], rbx
0x180054451  push    rbp
0x180054452  push    rsi
0x180054453  push    rdi
0x180054454  push    r12
0x180054456  push    r13
0x180054458  push    r14
0x18005445a  push    r15
0x18005445c  lea     rbp, [rsp-40h]
0x180054461  sub     rsp, 140h
0x180054468  mov     rax, cs:__security_cookie
0x18005446f  xor     rax, rsp
0x180054472  mov     [rbp+70h+var_38], rax
0x180054476  mov     rax, cs:hHandle
0x18005447d  xor     edi, edi
0x18005447f  mov     [rbp+70h+Handles], rax
0x180054483  mov     r13, r8
0x180054486  mov     rax, [rcx+30h]
0x18005448a  mov     rsi, rdx
0x18005448d  mov     [rbp+70h+var_48], rax
0x180054491  xor     edx, edx; Val
0x180054493  mov     rax, [rcx+28h]
0x180054497  lea     r8d, [rdi+6Ch]; Size
0x18005449b  mov     [rbp+70h+var_D0], rcx
0x18005449f  mov     ebx, edi
0x1800544a1  lea     rcx, [rbp+70h+var_C0]; void *
0x1800544a5  mov     [rbp+70h+var_40], rax
0x1800544a9  mov     r12d, edi
0x1800544ac  mov     [rbp+70h+var_E8], edi
0x1800544af  mov     r15d, edi
0x1800544b2  mov     [rbp+70h+var_D8], edi
0x1800544b5  mov     [rsp+170h+var_100], rdi
0x1800544ba  mov     r14d, edi
0x1800544bd  mov     [rbp+70h+hMem], rdi
0x1800544c1  mov     [rbp+70h+lpMem], rdi
0x1800544c5  mov     [rbp+70h+var_E4], edi
0x1800544c8  call    memset_0
0x1800544cd  lea     r9d, [rdi+2Dh]
0x1800544d1  mov     [rsp+170h+var_108], rdi
0x1800544d6  lea     r8, sourceString
0x1800544dd  mov     [rsp+170h+var_110], bl
0x1800544e1  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800544e8  mov     dword ptr [rsp+170h+var_150], 65Bh
0x1800544f0  call    fnEfsLogTrace1Strings
0x1800544f5  xor     r8d, r8d; bWaitAll
0x1800544f8  lea     rdx, [rbp+70h+Handles]; lpHandles
0x1800544fc  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180054500  lea     ecx, [r8+3]; nCount
0x180054504  call    cs:__imp_WaitForMultipleObjects
0x18005450a  test    eax, eax
0x18005450c  jz      loc_180054CCF
0x180054512  cmp     eax, 1
0x180054515  jz      loc_180054CCF
0x18005451b  cmp     eax, 2
0x18005451e  jnz     loc_180054C7C
0x180054524  lea     r9d, [rax+2Bh]
0x180054528  mov     dword ptr [rsp+170h+var_150], 679h
0x180054530  lea     r8, sourceString
0x180054537  lea     rdx, EFS_TRACE_START_EVENT
0x18005453e  call    fnEfsLogTrace1Strings
0x180054543  xor     edx, edx
0x180054545  mov     rcx, r13
0x180054548  call    cs:__imp_EfsClientDecryptFile
0x18005454e  mov     ebx, eax
0x180054550  test    eax, eax
0x180054552  jle     short loc_18005455D
0x180054554  movzx   ebx, ax
0x180054557  or      ebx, 80070000h
0x18005455d  mov     rcx, cs:g_hPublisher
0x180054564  lea     r9, sourceString
0x18005456b  mov     [rsp+170h+var_140], 679h
0x180054573  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18005457a  mov     dword ptr [rsp+170h+var_148], 2Dh ; '-'
0x180054582  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180054589  mov     dword ptr [rsp+170h+var_150], ebx
0x18005458d  call    fnEfsLogTrace1String1Dword
0x180054592  test    eax, eax
0x180054594  jns     loc_180054C10
0x18005459a  inc     r12d
0x18005459d  mov     [rsp+170h+var_F4], r12d
0x1800545a2  xor     r12d, r12d
0x1800545a5  cmp     ebx, 80070020h
0x1800545ab  jnz     short loc_1800545EC
0x1800545ad  mov     rcx, cs:g_hPublisher
0x1800545b4  lea     r9, aSharingViolati; "Sharing violation while trying to decry"...
0x1800545bb  mov     [rsp+170h+var_140], 692h
0x1800545c3  lea     r8, EFS_TRACE_MSG_DWORD_EVENT
0x1800545ca  mov     dword ptr [rsp+170h+var_148], 2Dh ; '-'
0x1800545d2  lea     rdx, EFS_TRACE_MSG_DWORD_EVENT
0x1800545d9  mov     dword ptr [rsp+170h+var_150], 0
0x1800545e1  mov     r12d, 1
0x1800545e7  call    fnEfsLogTrace1String1Dword
0x1800545ec  cmp     [rsp+170h+var_F4], 3
0x1800545f1  ja      loc_180054CCF
0x1800545f7  test    r15d, r15d
0x1800545fa  jnz     loc_1800549B1
0x180054600  mov     rcx, cs:g_hPublisher
0x180054607  lea     r9, aFailedToDecryp; "Failed to decrypt"
0x18005460e  mov     [rsp+170h+var_140], 6A6h
0x180054616  lea     r8, EFS_TRACE_MSG_ERROR_EVENT
0x18005461d  mov     dword ptr [rsp+170h+var_148], 2Dh ; '-'
0x180054625  lea     rdx, EFS_TRACE_MSG_TRACE_EVENT
0x18005462c  mov     dword ptr [rsp+170h+var_150], ebx
0x180054630  call    fnEfsLogTrace1String1Dword
0x180054635  mov     rcx, cs:g_hPublisher
0x18005463c  lea     ebx, [r15+2Dh]
0x180054640  mov     [rsp+170h+var_140], 6A7h
0x180054648  mov     r9, r13
0x18005464b  mov     dword ptr [rsp+170h+var_148], ebx
0x18005464f  mov     dword ptr [rsp+170h+var_150], r15d
0x180054654  lea     r15, EFS_TRACE_MSG_DWORD_EVENT
0x18005465b  mov     r8, r15
0x18005465e  mov     rdx, r15
0x180054661  call    fnEfsLogTrace1String1Dword
0x180054666  mov     r9d, ebx
0x180054669  mov     dword ptr [rsp+170h+var_150], 6ABh
0x180054671  lea     r8, sourceString
0x180054678  lea     rdx, EFS_TRACE_START_EVENT
0x18005467f  call    fnEfsLogTrace1Strings
0x180054684  lea     r8, [rbp+70h+var_D8]
0x180054688  mov     rcx, r13
0x18005468b  lea     rdx, [rbp+70h+var_E8]
0x18005468f  call    cs:__imp_EfsClientGetEncryptedFileVersion
0x180054695  mov     ebx, eax
0x180054697  test    eax, eax
0x180054699  jle     short loc_1800546A4
0x18005469b  movzx   ebx, ax
0x18005469e  or      ebx, 80070000h
0x1800546a4  mov     rcx, cs:g_hPublisher
0x1800546ab  lea     r9, sourceString
0x1800546b2  mov     [rsp+170h+var_140], 6ABh
0x1800546ba  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800546c1  mov     dword ptr [rsp+170h+var_148], 2Dh ; '-'
0x1800546c9  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800546d0  mov     dword ptr [rsp+170h+var_150], ebx
0x1800546d4  call    fnEfsLogTrace1String1Dword
0x1800546d9  test    eax, eax
0x1800546db  js      loc_180054CCF
0x1800546e1  mov     eax, [rbp+70h+var_E8]
0x1800546e4  cmp     eax, 5
0x1800546e7  jnz     loc_180054BDE
0x1800546ed  mov     rcx, [rsp+170h+var_100]
0x1800546f2  test    rcx, rcx
0x1800546f5  jz      short loc_180054706
0x1800546f7  call    cs:__imp_EfsClientFreeProtectorList
0x1800546fd  mov     [rsp+170h+var_100], 0
0x180054706  mov     r9d, 2Dh ; '-'
0x18005470c  mov     dword ptr [rsp+170h+var_150], 6C0h
0x180054714  lea     r8, sourceString
0x18005471b  lea     rdx, EFS_TRACE_START_EVENT
0x180054722  call    fnEfsLogTrace1Strings
0x180054727  lea     rdx, [rsp+170h+var_100]
0x18005472c  mov     rcx, r13
0x18005472f  call    cs:__imp_EfsClientQueryProtectors
0x180054735  mov     ebx, eax
0x180054737  test    eax, eax
0x180054739  jle     short loc_180054744
0x18005473b  movzx   ebx, ax
0x18005473e  or      ebx, 80070000h
0x180054744  mov     rcx, cs:g_hPublisher
0x18005474b  lea     r9, sourceString
0x180054752  mov     [rsp+170h+var_140], 6C0h
0x18005475a  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180054761  mov     dword ptr [rsp+170h+var_148], 2Dh ; '-'
0x180054769  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180054770  mov     dword ptr [rsp+170h+var_150], ebx
0x180054774  call    fnEfsLogTrace1String1Dword
0x180054779  test    eax, eax
0x18005477b  js      loc_180054CCF
0x180054781  mov     rax, [rsp+170h+var_100]
0x180054786  test    rax, rax
0x180054789  jz      loc_180054BBD
0x18005478f  cmp     dword ptr [rax], 0
0x180054792  jz      loc_180054BBD
0x180054798  mov     rcx, [rax+8]
0x18005479c  test    rcx, rcx
0x18005479f  jz      loc_180054BBD
0x1800547a5  mov     rdx, [rcx]
0x1800547a8  cmp     qword ptr [rdx+8], 0
0x1800547ad  jz      loc_180054BBD
0x1800547b3  cmp     qword ptr [rdx+10h], 0
0x1800547b8  jz      loc_180054BBD
0x1800547be  mov     rcx, [rbp+70h+hMem]; hMem
0x1800547c2  test    rcx, rcx
0x1800547c5  jz      short loc_1800547DA
0x1800547c7  call    cs:__imp_LocalFree
0x1800547cd  mov     rax, [rsp+170h+var_100]
0x1800547d2  mov     [rbp+70h+hMem], 0
0x1800547da  mov     rax, [rax+8]
0x1800547de  lea     rdx, [rbp+70h+hMem]; StringSid
0x1800547e2  mov     rcx, [rax]
0x1800547e5  mov     rcx, [rcx+8]; Sid
0x1800547e9  call    cs:__imp_ConvertSidToStringSidW
0x1800547ef  test    eax, eax
0x1800547f1  jz      loc_180054B9B
0x1800547f7  mov     r15, [rbp+70h+var_D0]
0x1800547fb  mov     rcx, [rbp+70h+hMem]; String1
0x1800547ff  mov     rdx, [r15+20h]; String2
0x180054803  call    cs:__imp__wcsicmp
0x180054809  test    eax, eax
0x18005480b  jnz     loc_180054B43
0x180054811  test    r14, r14
0x180054814  jz      short loc_180054832
0x180054816  call    cs:__imp_GetProcessHeap
0x18005481c  mov     r8, r14; lpMem
0x18005481f  xor     edx, edx; dwFlags
0x180054821  mov     rcx, rax; hHeap
0x180054824  call    cs:__imp_HeapFree
0x18005482a  mov     [rbp+70h+lpMem], 0
0x180054832  mov     r14d, 2Dh ; '-'
0x180054838  mov     dword ptr [rsp+170h+var_150], 6F4h
0x180054840  mov     r9d, r14d
0x180054843  lea     r8, sourceString
0x18005484a  lea     rdx, EFS_TRACE_START_EVENT
0x180054851  call    fnEfsLogTrace1Strings
0x180054856  mov     rax, [rsp+170h+var_100]
0x18005485b  lea     r8, [rsp+170h+var_110]; bool *
0x180054860  lea     rdx, [rbp+70h+lpMem]; unsigned __int16 **
0x180054864  mov     rcx, [rax+8]
0x180054868  mov     rcx, [rcx]
0x18005486b  mov     rcx, [rcx+10h]; unsigned __int16 *
0x18005486f  call    ?EfsConvertProtectorToExternalId@@YAJPEBGPEAPEAGPEA_N@Z; EfsConvertProtectorToExternalId(ushort const *,ushort * *,bool *)
0x180054874  mov     rcx, cs:g_hPublisher
0x18005487b  lea     r9, sourceString
0x180054882  mov     [rsp+170h+var_140], 6F4h
0x18005488a  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180054891  mov     dword ptr [rsp+170h+var_148], r14d
0x180054896  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18005489d  mov     dword ptr [rsp+170h+var_150], eax
0x1800548a1  mov     ebx, eax
0x1800548a3  call    fnEfsLogTrace1String1Dword
0x1800548a8  test    eax, eax
0x1800548aa  js      loc_180054B3A
0x1800548b0  mov     [rsp+170h+var_F8], 0
0x1800548b8  test    rdi, rdi
0x1800548bb  jz      short loc_1800548CF
0x1800548bd  mov     rcx, rdi; hMem
0x1800548c0  call    cs:__imp_LocalFree
0x1800548c6  mov     [rsp+170h+var_108], 0
0x1800548cf  xor     edx, edx; Val
0x1800548d1  lea     rcx, [rbp+70h+var_BC]; void *
0x1800548d5  lea     r8d, [rdx+68h]; Size
0x1800548d9  call    memset_0
0x1800548de  mov     edi, 70Dh
0x1800548e3  mov     dword ptr [rbp+70h+var_C0], 6Ch ; 'l'
0x1800548ea  mov     r9d, r14d
0x1800548ed  mov     dword ptr [rsp+170h+var_150], edi
0x1800548f1  lea     r8, sourceString
0x1800548f8  lea     rdx, EFS_TRACE_START_EVENT
0x1800548ff  call    fnEfsLogTrace1Strings
0x180054904  mov     r8, [r15+20h]; unsigned __int16 *
0x180054908  lea     rax, [rsp+170h+var_F8]
0x18005490d  mov     r14, [rbp+70h+lpMem]
0x180054911  mov     r9, r8; unsigned __int16 *
0x180054914  mov     [rsp+170h+var_120], rax; unsigned int *
0x180054919  mov     edx, 2; unsigned int
0x18005491e  lea     rax, [rsp+170h+var_108]
0x180054923  xor     ecx, ecx; void *
0x180054925  mov     [rsp+170h+var_128], rax; unsigned __int8 **
0x18005492a  mov     eax, dword ptr [rbp+70h+var_C0]
0x18005492d  mov     [rsp+170h+var_130], 0; unsigned int
0x180054935  mov     [rsp+170h+var_138], 0; unsigned __int8 *
0x18005493e  mov     [rsp+170h+var_140], eax; unsigned int
0x180054942  lea     rax, [rbp+70h+var_C0]
0x180054946  mov     [rsp+170h+var_148], rax; unsigned __int8 *
0x18005494b  mov     [rsp+170h+var_150], r14; unsigned __int16 *
0x180054950  call    ?EdpCredSvcControl@@YAJPEAXKPEBG11PEBEK2KPEAPEAEPEAK@Z; EdpCredSvcControl(void *,ulong,ushort const *,ushort const *,ushort const *,uchar const *,ulong,uchar const *,ulong,uchar * *,ulong *)
0x180054955  mov     rcx, cs:g_hPublisher
0x18005495c  lea     r9, sourceString
0x180054963  mov     [rsp+170h+var_140], edi
0x180054967  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18005496e  mov     dword ptr [rsp+170h+var_148], 2Dh ; '-'
0x180054976  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18005497d  mov     dword ptr [rsp+170h+var_150], eax
0x180054981  mov     ebx, eax
0x180054983  call    fnEfsLogTrace1String1Dword
0x180054988  mov     rdi, [rsp+170h+var_108]
0x18005498d  test    eax, eax
0x18005498f  js      loc_180054CD5
0x180054995  mov     [rbp+70h+var_E4], 1
0x18005499c  mov     r15d, 1
0x1800549a2  test    rdi, rdi
0x1800549a5  jz      short loc_1800549B1
0x1800549a7  cmp     dword ptr [rdi+8], 0
0x1800549ab  jz      loc_180054AE2
0x1800549b1  xor     ebx, ebx
0x1800549b3  mov     [rsp+170h+var_F8], ebx
0x1800549b7  test    rdi, rdi
0x1800549ba  jz      short loc_1800549CA
0x1800549bc  mov     rcx, rdi; hMem
0x1800549bf  call    cs:__imp_LocalFree
0x1800549c5  mov     [rsp+170h+var_108], rbx
0x1800549ca  mov     edi, 2Dh ; '-'
0x1800549cf  mov     dword ptr [rsp+170h+var_150], 73Dh
0x1800549d7  mov     r9d, edi
0x1800549da  lea     r8, sourceString
0x1800549e1  lea     rdx, EFS_TRACE_START_EVENT
0x1800549e8  call    fnEfsLogTrace1Strings
0x1800549ed  mov     rax, [rbp+70h+var_D0]
0x1800549f1  lea     edx, [rdi-2Ch]; unsigned int
  ... truncated ...
```

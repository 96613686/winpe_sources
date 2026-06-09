# CContainerProps::CleanupSecureDirectories(void)

- ea: `0x1800b6594`
- end: `0x1800b6ab7`
- name: `?CleanupSecureDirectories@CContainerProps@@QEAAJXZ`
- size: `1315`
- prototype: `__int64 __fastcall(CContainerProps *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18012a078`

## callees

- `0x1800204f8`
- `0x180020fc4`
- `0x180025910`
- `0x180025980`
- `0x1800701d0`
- `0x18007ec9c`
- `0x18007ed10`
- `0x180083d00`
- `0x180083dc4`
- `0x1800acab8`
- `0x1800b6398`
- `0x1800b6594`
- `0x1800b6ac0`
- `0x1800d6e10`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e1b00`
- `0x1801e3c78`
- `0x1801e4988`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b665c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b665c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b68f8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b68f8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b68e9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b6a79`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b68e9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800b6a79`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b69aa`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b69aa`
- `ESENT!JetRollback` at `0x1800b6806`
- `ESENT!JetRollback` at `0x1800b6817`
- `ESENT!JetRollback` at `0x1800b6806`
- `ESENT!JetRollback` at `0x1800b6817`
- `ESENT!JetBeginTransaction` at `0x1800b6691`
- `ESENT!JetBeginTransaction` at `0x1800b6691`
- `ESENT!JetMove` at `0x1800b66c2`
- `ESENT!JetMove` at `0x1800b66c2`

## pseudocode

```c
__int64 __fastcall CContainerProps::CleanupSecureDirectories(CContainerProps *this)
{
  __int64 FirstFileW; // rbx
  signed int BasicColumn; // edi
  JET_SESID *v4; // rsi
  JET_ERR v5; // eax
  struct _FILETIME v6; // r12
  int i; // r8d
  JET_ERR v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdi
  unsigned __int8 *Heap; // rax
  unsigned __int8 *v13; // r14
  unsigned __int8 *v14; // r14
  unsigned int dwLowDateTime_low; // r9d
  unsigned int v16; // r8d
  int dwHighDateTime_low; // r10d
  unsigned __int16 v18; // ax
  unsigned int v19; // ecx
  __int64 v20; // rax
  __int64 j; // r8
  _DWORD *v22; // rdx
  __int64 v23; // rcx
  unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // r8
  __int64 v26; // rdx
  unsigned __int16 *v27; // rcx
  __int64 v28; // rcx
  BOOL k; // eax
  int IsMember; // eax
  __int64 v31; // rax
  const unsigned __int16 *v33; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v34; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v35; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v36; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v37; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v38; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v39; // [rsp+50h] [rbp-B0h]
  struct CJetContext *v40; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v42; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpPathName[3]; // [rsp+88h] [rbp-78h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 *v46[32]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v47[8]; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int16 v48; // [rsp+400h] [rbp+300h]

  SystemTimeAsFileTime.dwHighDateTime = 0;
  v40 = 0;
  lpPathName[0] = &Data;
  lpPathName[1] = 0;
  v42 = 0;
  memset_0(v46, 0, sizeof(v46));
  lpFileName[0] = &Data;
  lpFileName[1] = 0;
  v48 = 0;
  *(_OWORD *)v47 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = -1;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_(1036, 24, &WPP_b5c7e844a87d3fa49b467b888bebb474_Traceguids);
  if ( *((_QWORD *)this + 20) )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    BasicColumn = CJetContextList::AcquireContext(*((CJetContextList **)this + 19), &v40, 0);
    if ( BasicColumn >= 0 )
    {
      v4 = (JET_SESID *)v40;
      v5 = JetBeginTransaction(*((_QWORD *)v40 + 2));
      BasicColumn = HRESULTFromJET_ERR(v5, 1);
      if ( BasicColumn >= 0 )
      {
        v6 = SystemTimeAsFileTime;
        for ( i = 0x80000000; ; i = 1 )
        {
          v8 = JetMove(v4[2], v4[4], i, 0);
          if ( v8 == -1603 )
            break;
          BasicColumn = HRESULTFromJET_ERR(v8, 1);
          if ( BasicColumn < 0 )
            goto LABEL_22;
          BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v4, 6u, &v42, 4u);
          if ( BasicColumn < 0 )
          {
            SystemTimeAsFileTime.dwHighDateTime = 651;
            goto LABEL_22;
          }
          if ( v42 )
          {
            v10 = v42 - 1;
            v42 = v10;
            v11 = (unsigned int)v10;
            if ( !v46[v10] )
            {
              SystemTimeAsFileTime.dwHighDateTime = 0;
              v46[v10] = 0;
              Heap = (unsigned __int8 *)WxAllocateHeapEx(v9, 0x2000);
              v13 = Heap;
              if ( !Heap )
              {
                BasicColumn = -2147024882;
                SystemTimeAsFileTime.dwHighDateTime = 663;
LABEL_22:
                JetRollback(v4[2], 0);
                goto LABEL_57;
              }
              memset_0(Heap, 0, 0x2000u);
              v46[v11] = v13;
            }
            BasicColumn = CJetContext::GetStringColumn((CJetContext *)v4, 5u, (struct CWxString *)lpPathName);
            if ( BasicColumn < 0 )
            {
              SystemTimeAsFileTime.dwHighDateTime = 666;
              goto LABEL_22;
            }
            SystemTimeAsFileTime = 0;
            v14 = v46[v42];
            WxBloomFilterComputeMemberHashes(lpPathName[0], (struct WxBloomEntryHashes *)&SystemTimeAsFileTime);
            dwLowDateTime_low = LOWORD(SystemTimeAsFileTime.dwLowDateTime);
            v16 = 0;
            dwHighDateTime_low = LOWORD(SystemTimeAsFileTime.dwHighDateTime);
            do
            {
              v18 = dwHighDateTime_low + dwLowDateTime_low;
              v14[(unsigned __int64)dwLowDateTime_low >> 3] |= 1 << (dwLowDateTime_low & 7);
              dwHighDateTime_low += v16;
              dwLowDateTime_low = v18;
              ++v16;
            }
            while ( v16 < 4 );
          }
        }
        JetRollback(v4[2], 0);
        CContainerProps::ReleaseEntryContext(this, &v40);
        v19 = 0;
        v20 = 0;
        for ( j = 0; ; j = v19 )
        {
          v22 = (_DWORD *)*((_QWORD *)this + 20);
          v42 = v19;
          if ( (unsigned int)v20 >= *v22 )
            break;
          if ( v46[v20] )
          {
            v23 = 8;
            v24 = v47;
            v25 = (unsigned __int16 *)&v22[4 * j + 1];
            v26 = 9;
            do
            {
              if ( !v23 )
                break;
              if ( !*v25 )
                break;
              *v24++ = *v25++;
              --v23;
              --v26;
            }
            while ( v26 );
            v27 = v24 - 1;
            if ( v26 )
              v27 = v24;
            *v27 = 0;
            BasicColumn = v26 == 0 ? 0x8007007A : 0;
            if ( v26 )
            {
              BasicColumn = CWxString::SetPath(
                              (CWxString *)lpFileName,
                              *((const unsigned __int16 **)this + 13),
                              v47,
                              L"*",
                              v33,
                              v34,
                              v35,
                              v36,
                              v37,
                              v38,
                              v39);
              if ( BasicColumn < 0 )
              {
                SystemTimeAsFileTime.dwHighDateTime = 690;
              }
              else
              {
                if ( FirstFileW != -1 )
                  FindClose((HANDLE)FirstFileW);
                FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
                for ( k = FirstFileW != -1; k; k = FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
                {
                  if ( *(_QWORD *)&v6 - *(_QWORD *)&FindFileData.ftLastWriteTime >= 0x861C46800uLL )
                  {
                    IsMember = WxBloomFilterIsMember(FindFileData.cFileName, v46[v42], 0x2000u, 4u);
                    BasicColumn = IsMember;
                    if ( IsMember < 0 )
                    {
                      SystemTimeAsFileTime.dwHighDateTime = 713;
                      goto LABEL_57;
                    }
                    if ( IsMember )
                    {
                      BasicColumn = CWxString::SetPath(
                                      (CWxString *)lpPathName,
                                      *((const unsigned __int16 **)this + 13),
                                      v47,
                                      FindFileData.cFileName,
                                      v33,
                                      v34,
                                      v35,
                                      v36,
                                      v37,
                                      v38,
                                      v39);
                      if ( BasicColumn < 0 )
                      {
                        SystemTimeAsFileTime.dwHighDateTime = 719;
                        goto LABEL_57;
                      }
                      if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
                        WPP_SF_S(1036, 25, &WPP_b5c7e844a87d3fa49b467b888bebb474_Traceguids, lpPathName[0]);
                      WxDeleteFileOrDirectory(lpPathName[0], FindFileData.dwFileAttributes);
                    }
                  }
                }
                BasicColumn = WxGetLastError(v28);
                if ( ((BasicColumn - 2) & 0xFFFFFFEF) == 0 )
                {
                  v19 = v42;
                  BasicColumn = 0;
                  goto LABEL_48;
                }
                if ( BasicColumn > 0 )
                  BasicColumn = (unsigned __int16)BasicColumn | 0x80070000;
                SystemTimeAsFileTime.dwHighDateTime = 731;
              }
            }
            else
            {
              SystemTimeAsFileTime.dwHighDateTime = 688;
            }
            break;
          }
LABEL_48:
          v20 = ++v19;
        }
      }
    }
    else
    {
      SystemTimeAsFileTime.dwHighDateTime = 637;
    }
  }
  else
  {
    BasicColumn = 0;
  }
LABEL_57:
  CContainerProps::ReleaseEntryContext(this, &v40);
  v31 = 0;
  v42 = 0;
  do
  {
    WxHeapFree<_WX_AVL_TABLE>(&v46[v31]);
    v31 = v42 + 1;
    v42 = v31;
  }
  while ( (unsigned int)v31 < 0x20 );
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qD(1036, 26, &WPP_b5c7e844a87d3fa49b467b888bebb474_Traceguids, this, BasicColumn);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  CWxString::_Release((CWxString *)lpFileName);
  CWxString::_Release((CWxString *)lpPathName);
  return (unsigned int)BasicColumn;
}

```

## disassembly

```asm
0x1800b6594  push    rbp
0x1800b6596  push    rbx
0x1800b6597  push    rsi
0x1800b6598  push    rdi
0x1800b6599  push    r12
0x1800b659b  push    r13
0x1800b659d  push    r14
0x1800b659f  push    r15
0x1800b65a1  lea     rbp, [rsp-318h]
0x1800b65a9  sub     rsp, 418h
0x1800b65b0  mov     rax, cs:__security_cookie
0x1800b65b7  xor     rax, rsp
0x1800b65ba  mov     [rbp+350h+var_48], rax
0x1800b65c1  xor     r13d, r13d
0x1800b65c4  lea     rbx, Data
0x1800b65cb  mov     r15, rcx
0x1800b65ce  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], r13d
0x1800b65d2  lea     rcx, [rbp+350h+var_160]; void *
0x1800b65d9  mov     [rsp+450h+var_3F0], r13
0x1800b65de  xor     edx, edx; Val
0x1800b65e0  mov     [rbp+350h+lpPathName], rbx
0x1800b65e4  mov     r8d, 100h; Size
0x1800b65ea  mov     [rbp+350h+var_3C0], r13
0x1800b65ee  mov     [rsp+450h+var_3D8], r13d
0x1800b65f3  call    memset_0
0x1800b65f8  xorps   xmm0, xmm0
0x1800b65fb  mov     [rsp+450h+lpFileName], rbx
0x1800b6600  xor     eax, eax
0x1800b6602  mov     [rsp+450h+var_3E0], r13
0x1800b6607  xor     edx, edx; Val
0x1800b6609  mov     [rbp+350h+var_50], ax
0x1800b6610  mov     r8d, 250h; Size
0x1800b6616  lea     rcx, [rbp+350h+FindFileData]; void *
0x1800b661a  movups  xmmword ptr [rbp+350h+var_60], xmm0
0x1800b6621  call    memset_0
0x1800b6626  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b662a  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800b6631  jz      short loc_1800B6647
0x1800b6633  lea     edx, [rbx+19h]
0x1800b6636  mov     ecx, 40Ch
0x1800b663b  lea     r8, WPP_b5c7e844a87d3fa49b467b888bebb474_Traceguids
0x1800b6642  call    WPP_SF_
0x1800b6647  cmp     [r15+0A0h], r13
0x1800b664e  jz      loc_1800B6A13
0x1800b6654  lea     rcx, [rbp+350h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800b6658  mov     qword ptr [rbp+350h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800b665c  call    cs:__imp_GetSystemTimeAsFileTime
0x1800b6662  mov     rcx, [r15+98h]; this
0x1800b6669  lea     rdx, [rsp+450h+var_3F0]; struct CJetContext **
0x1800b666e  xor     r8d, r8d; int *
0x1800b6671  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800b6676  mov     edi, eax
0x1800b6678  test    eax, eax
0x1800b667a  jns     short loc_1800B6688
0x1800b667c  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], 27Dh
0x1800b6683  jmp     loc_1800B6A16
0x1800b6688  mov     rsi, [rsp+450h+var_3F0]
0x1800b668d  mov     rcx, [rsi+10h]; sesid
0x1800b6691  call    cs:__imp_JetBeginTransaction
0x1800b6697  mov     ecx, eax; int
0x1800b6699  mov     edx, 1; int
0x1800b669e  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b66a3  mov     edi, eax
0x1800b66a5  test    eax, eax
0x1800b66a7  js      loc_1800B6A16
0x1800b66ad  mov     r12, qword ptr [rbp+350h+SystemTimeAsFileTime.dwLowDateTime]
0x1800b66b1  mov     r8d, 80000000h; cRow
0x1800b66b7  mov     rdx, [rsi+20h]; tableid
0x1800b66bb  xor     r9d, r9d; grbit
0x1800b66be  mov     rcx, [rsi+10h]; sesid
0x1800b66c2  call    cs:__imp_JetMove
0x1800b66c8  cmp     eax, 0FFFFF9BDh
0x1800b66cd  jz      loc_1800B6811
0x1800b66d3  mov     edx, 1; int
0x1800b66d8  mov     ecx, eax; int
0x1800b66da  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800b66df  mov     edi, eax
0x1800b66e1  test    eax, eax
0x1800b66e3  js      loc_1800B6800
0x1800b66e9  mov     r9d, 4; unsigned int
0x1800b66ef  lea     r8, [rsp+450h+var_3D8]; void *
0x1800b66f4  mov     rcx, rsi; this
0x1800b66f7  lea     edx, [r9+2]; unsigned int
0x1800b66fb  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x1800b6700  mov     edi, eax
0x1800b6702  test    eax, eax
0x1800b6704  js      loc_1800B67F9
0x1800b670a  mov     eax, [rsp+450h+var_3D8]
0x1800b670e  test    eax, eax
0x1800b6710  jz      loc_1800B67D0
0x1800b6716  dec     eax
0x1800b6718  mov     [rsp+450h+var_3D8], eax
0x1800b671c  mov     edi, eax
0x1800b671e  cmp     [rbp+rax*8+350h+var_160], r13
0x1800b6726  jnz     short loc_1800B6762
0x1800b6728  mov     edx, 2000h
0x1800b672d  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], r13d
0x1800b6731  mov     [rbp+rax*8+350h+var_160], r13
0x1800b6739  call    WxAllocateHeapEx
0x1800b673e  mov     r14, rax
0x1800b6741  test    rax, rax
0x1800b6744  jz      loc_1800B67DB
0x1800b674a  xor     edx, edx; Val
0x1800b674c  mov     r8d, 2000h; Size
0x1800b6752  mov     rcx, rax; void *
0x1800b6755  call    memset_0
0x1800b675a  mov     [rbp+rdi*8+350h+var_160], r14
0x1800b6762  lea     r8, [rbp+350h+lpPathName]; struct CWxString *
0x1800b6766  mov     edx, 5; unsigned int
0x1800b676b  mov     rcx, rsi; this
0x1800b676e  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800b6773  mov     edi, eax
0x1800b6775  test    eax, eax
0x1800b6777  js      short loc_1800B67F0
0x1800b6779  mov     eax, [rsp+450h+var_3D8]
0x1800b677d  lea     rdx, [rbp+350h+SystemTimeAsFileTime]; struct WxBloomEntryHashes *
0x1800b6781  mov     rcx, [rbp+350h+lpPathName]; unsigned __int16 *
0x1800b6785  mov     qword ptr [rbp+350h+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800b6789  mov     r14, [rbp+rax*8+350h+var_160]
0x1800b6791  call    ?WxBloomFilterComputeMemberHashes@@YAXPEBGPEAUWxBloomEntryHashes@@@Z; WxBloomFilterComputeMemberHashes(ushort const *,WxBloomEntryHashes *)
0x1800b6796  movzx   r9d, word ptr [rbp+350h+SystemTimeAsFileTime.dwLowDateTime]
0x1800b679b  mov     r8d, r13d
0x1800b679e  movzx   r10d, word ptr [rbp+350h+SystemTimeAsFileTime.dwHighDateTime]
0x1800b67a3  mov     edx, r9d
0x1800b67a6  mov     eax, r9d
0x1800b67a9  shr     rdx, 3
0x1800b67ad  and     eax, 7
0x1800b67b0  movzx   ecx, byte ptr [rdx+r14]
0x1800b67b5  bts     ecx, eax
0x1800b67b8  lea     eax, [r10+r9]
0x1800b67bc  mov     [rdx+r14], cl
0x1800b67c0  add     r10d, r8d
0x1800b67c3  movzx   r9d, ax
0x1800b67c7  inc     r8d
0x1800b67ca  cmp     r8d, 4
0x1800b67ce  jb      short loc_1800B67A3
0x1800b67d0  mov     r8d, 1
0x1800b67d6  jmp     loc_1800B66B7
0x1800b67db  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], 4Ch ; 'L'
0x1800b67e2  mov     edi, 8007000Eh
0x1800b67e7  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], 297h
0x1800b67ee  jmp     short loc_1800B6800
0x1800b67f0  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], 29Ah
0x1800b67f7  jmp     short loc_1800B6800
0x1800b67f9  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], 28Bh
0x1800b6800  mov     rcx, [rsi+10h]; sesid
0x1800b6804  xor     edx, edx; grbit
0x1800b6806  call    cs:__imp_JetRollback
0x1800b680c  jmp     loc_1800B6A16
0x1800b6811  mov     rcx, [rsi+10h]; sesid
0x1800b6815  xor     edx, edx; grbit
0x1800b6817  call    cs:__imp_JetRollback
0x1800b681d  lea     rdx, [rsp+450h+var_3F0]; struct CJetContext **
0x1800b6822  mov     rcx, r15; this
0x1800b6825  call    ?ReleaseEntryContext@CContainerProps@@QEAAXPEAPEAVCJetContext@@@Z; CContainerProps::ReleaseEntryContext(CJetContext * *)
0x1800b682a  mov     ecx, r13d
0x1800b682d  mov     eax, r13d
0x1800b6830  mov     r8d, r13d
0x1800b6833  mov     rdx, [r15+0A0h]
0x1800b683a  mov     [rsp+450h+var_3D8], ecx
0x1800b683e  cmp     eax, [rdx]
0x1800b6840  jnb     loc_1800B6A16
0x1800b6846  cmp     [rbp+rax*8+350h+var_160], r13
0x1800b684e  jz      loc_1800B69CD
0x1800b6854  add     rdx, 4
0x1800b6858  shl     r8, 4
0x1800b685c  mov     ecx, 8
0x1800b6861  lea     rax, [rbp+350h+var_60]
0x1800b6868  add     r8, rdx
0x1800b686b  lea     edx, [rcx+1]
0x1800b686e  test    rcx, rcx
0x1800b6871  jz      short loc_1800B6892
0x1800b6873  movzx   r9d, word ptr [r8]
0x1800b6877  test    r9w, r9w
0x1800b687b  jz      short loc_1800B6892
0x1800b687d  mov     [rax], r9w
0x1800b6881  add     r8, 2
0x1800b6885  add     rax, 2
0x1800b6889  dec     rcx
0x1800b688c  sub     rdx, 1
0x1800b6890  jnz     short loc_1800B686E
0x1800b6892  test    rdx, rdx
0x1800b6895  lea     rcx, [rax-2]
0x1800b6899  cmovnz  rcx, rax
0x1800b689d  mov     rax, rdx
0x1800b68a0  neg     rax
0x1800b68a3  sbb     edi, edi
0x1800b68a5  not     edi
0x1800b68a7  mov     [rcx], r13w
0x1800b68ab  and     edi, 8007007Ah
0x1800b68b1  test    rdx, rdx
0x1800b68b4  jz      loc_1800B6A0A
0x1800b68ba  mov     rdx, [r15+68h]; unsigned __int16 *
0x1800b68be  lea     r9, asc_180226340; "*"
0x1800b68c5  lea     r8, [rbp+350h+var_60]; unsigned __int16 *
0x1800b68cc  lea     rcx, [rsp+450h+lpFileName]; this
0x1800b68d1  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800b68d6  mov     edi, eax
0x1800b68d8  test    eax, eax
0x1800b68da  js      loc_1800B6A01
0x1800b68e0  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b68e4  jz      short loc_1800B68EF
0x1800b68e6  mov     rcx, rbx; hFindFile
0x1800b68e9  call    cs:__imp_FindClose
0x1800b68ef  mov     rcx, [rsp+450h+lpFileName]; lpFileName
0x1800b68f4  lea     rdx, [rbp+350h+FindFileData]; lpFindFileData
0x1800b68f8  call    cs:__imp_FindFirstFileW
0x1800b68fe  mov     rbx, rax
0x1800b6901  mov     eax, r13d
0x1800b6904  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b6908  setnz   al
0x1800b690b  test    eax, eax
0x1800b690d  jz      loc_1800B69B5
0x1800b6913  mov     rax, r12
0x1800b6916  mov     rcx, 861C46800h
0x1800b6920  sub     rax, qword ptr [rbp+350h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x1800b6924  cmp     rax, rcx
0x1800b6927  jb      short loc_1800B69A3
0x1800b6929  mov     edx, [rsp+450h+var_3D8]
0x1800b692d  lea     rcx, [rbp+350h+FindFileData.cFileName]; unsigned __int16 *
0x1800b6931  mov     r9d, 4; unsigned int
0x1800b6937  mov     r8d, 2000h; unsigned int
0x1800b693d  mov     rdx, [rbp+rdx*8+350h+var_160]; unsigned __int8 *
0x1800b6945  call    ?WxBloomFilterIsMember@@YAJPEBGPEBEKK@Z; WxBloomFilterIsMember(ushort const *,uchar const *,ulong,ulong)
0x1800b694a  mov     edi, eax
0x1800b694c  test    eax, eax
0x1800b694e  js      loc_1800B69E2
0x1800b6954  jz      short loc_1800B69A3
0x1800b6956  mov     rdx, [r15+68h]; unsigned __int16 *
0x1800b695a  lea     r9, [rbp+350h+FindFileData.cFileName]; unsigned __int16 *
0x1800b695e  lea     r8, [rbp+350h+var_60]; unsigned __int16 *
0x1800b6965  lea     rcx, [rbp+350h+lpPathName]; this
0x1800b6969  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800b696e  mov     edi, eax
0x1800b6970  test    eax, eax
0x1800b6972  js      short loc_1800B69D9
0x1800b6974  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800b697b  jz      short loc_1800B6997
0x1800b697d  mov     r9, [rbp+350h+lpPathName]
0x1800b6981  lea     r8, WPP_b5c7e844a87d3fa49b467b888bebb474_Traceguids
0x1800b6988  mov     edx, 19h
0x1800b698d  mov     ecx, 40Ch
0x1800b6992  call    WPP_SF_S
0x1800b6997  mov     edx, [rbp+350h+FindFileData.dwFileAttributes]; unsigned int
0x1800b699a  mov     rcx, [rbp+350h+lpPathName]; lpPathName
0x1800b699e  call    ?WxDeleteFileOrDirectory@@YAJPEBGK@Z; WxDeleteFileOrDirectory(ushort const *,ulong)
0x1800b69a3  lea     rdx, [rbp+350h+FindFileData]; lpFindFileData
0x1800b69a7  mov     rcx, rbx; hFindFile
0x1800b69aa  call    cs:__imp_FindNextFileW
0x1800b69b0  jmp     loc_1800B690B
0x1800b69b5  call    WxGetLastError
0x1800b69ba  mov     edi, eax
0x1800b69bc  add     eax, 0FFFFFFFEh
0x1800b69bf  test    eax, 0FFFFFFEFh
0x1800b69c4  jnz     short loc_1800B69EB
0x1800b69c6  mov     ecx, [rsp+450h+var_3D8]
0x1800b69ca  mov     edi, r13d
0x1800b69cd  inc     ecx
0x1800b69cf  mov     eax, ecx
0x1800b69d1  mov     r8d, ecx
0x1800b69d4  jmp     loc_1800B6833
0x1800b69d9  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], 2CFh
0x1800b69e0  jmp     short loc_1800B6A16
0x1800b69e2  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], 2C9h
0x1800b69e9  jmp     short loc_1800B6A16
0x1800b69eb  test    edi, edi
0x1800b69ed  jle     short loc_1800B69F8
0x1800b69ef  movzx   edi, di
0x1800b69f2  or      edi, 80070000h
0x1800b69f8  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], 2DBh
0x1800b69ff  jmp     short loc_1800B6A16
0x1800b6a01  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], 2B2h
0x1800b6a08  jmp     short loc_1800B6A16
0x1800b6a0a  mov     [rbp+350h+SystemTimeAsFileTime.dwHighDateTime], 2B0h
0x1800b6a11  jmp     short loc_1800B6A16
0x1800b6a13  mov     edi, r13d
0x1800b6a16  lea     rdx, [rsp+450h+var_3F0]; struct CJetContext **
0x1800b6a1b  mov     rcx, r15; this
0x1800b6a1e  call    ?ReleaseEntryContext@CContainerProps@@QEAAXPEAPEAVCJetContext@@@Z; CContainerProps::ReleaseEntryContext(CJetContext * *)
0x1800b6a23  mov     eax, r13d
0x1800b6a26  mov     [rsp+450h+var_3D8], r13d
0x1800b6a2b  lea     rcx, [rbp+350h+var_160]
0x1800b6a32  lea     rcx, [rcx+rax*8]
0x1800b6a36  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1800b6a3b  mov     eax, [rsp+450h+var_3D8]
0x1800b6a3f  inc     eax
0x1800b6a41  mov     [rsp+450h+var_3D8], eax
0x1800b6a45  cmp     eax, 20h ; ' '
0x1800b6a48  jb      short loc_1800B6A2B
0x1800b6a4a  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800b6a51  jz      short loc_1800B6A70
0x1800b6a53  mov     edx, 1Ah
0x1800b6a58  mov     dword ptr [rsp+450h+var_430], edi
0x1800b6a5c  mov     ecx, 40Ch
0x1800b6a61  lea     r8, WPP_b5c7e844a87d3fa49b467b888bebb474_Traceguids
0x1800b6a68  mov     r9, r15
0x1800b6a6b  call    WPP_SF_qD
0x1800b6a70  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800b6a74  jz      short loc_1800B6A7F
0x1800b6a76  mov     rcx, rbx; hFindFile
  ... truncated ...
```

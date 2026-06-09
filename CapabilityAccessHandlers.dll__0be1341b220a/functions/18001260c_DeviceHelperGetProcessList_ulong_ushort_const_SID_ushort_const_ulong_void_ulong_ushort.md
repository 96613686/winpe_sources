# _DeviceHelperGetProcessList(ulong,ushort const *,_SID *,ushort const *,ulong *,void * * *,ulong * *,ushort * * *)

- ea: `0x18001260c`
- end: `0x180012bb6`
- name: `?_DeviceHelperGetProcessList@@YAJKPEBGPEAU_SID@@0PEAKPEAPEAPEAXPEAPEAKPEAPEAPEAG@Z`
- size: `1450`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, struct _SID *, const unsigned __int16 *, unsigned int *, void ***, unsigned int **, unsigned __int16 ***)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012bbc`

## callees

- `0x180004c70`
- `0x1800056e0`
- `0x18001260c`
- `0x1800135e0`
- `0x18001364c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001292b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800127ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001292b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180012829`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180012829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800129f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012852`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012925`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001296b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012852`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012925`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001296b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180012889`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180012889`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012984`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180012984`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012727`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012763`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001279d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012941`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012a29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012a48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012a6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012727`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012763`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001279d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012941`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012a29`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012a48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180012a6c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012aaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ac0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012af7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800129e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012aaa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ac0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ada`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012af7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b84`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001280c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001280c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800126ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800126ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001299a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001299a`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x180012704`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x180012704`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800128b6`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x1800128b6`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800128e5`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800128e5`

## pseudocode

```c
__int64 __fastcall _DeviceHelperGetProcessList(
        __int64 a1,
        const unsigned __int16 *a2,
        struct _SID *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        void ***a6,
        unsigned int **a7,
        unsigned __int16 ***a8)
{
  void **v8; // r13
  HLOCAL *v10; // rdi
  void *v11; // r14
  __int64 v12; // r12
  LPWSTR *v13; // r15
  signed int LastError; // eax
  __int64 v15; // rbx
  __int64 v16; // r12
  signed int v17; // eax
  signed int v18; // eax
  signed int v19; // eax
  __int64 v20; // r13
  DWORD v21; // r8d
  PSID *v22; // rdi
  HANDLE v23; // rax
  void *v24; // r14
  bool v25; // zf
  void **v26; // rax
  HLOCAL v27; // rax
  unsigned __int16 **v28; // rax
  signed int v29; // eax
  __int64 i; // rdi
  void *v31; // rcx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v34[4]; // [rsp+34h] [rbp-CCh] BYREF
  void **v35; // [rsp+38h] [rbp-C8h]
  void *v36; // [rsp+40h] [rbp-C0h]
  void *Src; // [rsp+48h] [rbp-B8h]
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbNeeded; // [rsp+58h] [rbp-A8h] BYREF
  int TokenInformation; // [rsp+5Ch] [rbp-A4h] BYREF
  int v41; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  int v43; // [rsp+70h] [rbp-90h]
  PSID Sid; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v45; // [rsp+80h] [rbp-80h]
  unsigned int *v46; // [rsp+88h] [rbp-78h]
  const unsigned __int16 *v47; // [rsp+90h] [rbp-70h]
  struct _SID *v48; // [rsp+98h] [rbp-68h]
  void ***v49; // [rsp+A0h] [rbp-60h]
  DWORD idProcess[2048]; // [rsp+B0h] [rbp-50h] BYREF

  v8 = (void **)a6;
  v10 = (HLOCAL *)a7;
  v48 = a3;
  v47 = a2;
  v45 = a4;
  v46 = a5;
  v49 = a6;
  v35 = (void **)a7;
  Sid = 0;
  memset_0(idProcess, 0, sizeof(idProcess));
  cbNeeded = 0;
  v11 = 0;
  Src = 0;
  LODWORD(v12) = 0;
  TokenInformationLength = 0;
  v13 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a4 && !ConvertStringSidToSidW(a4, &Sid) || !K32EnumProcesses(idProcess, 0x2000u, &cbNeeded) )
  {
    LastError = GetLastError();
    LODWORD(v15) = LastError;
    if ( LastError > 0 )
      LODWORD(v15) = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_61;
  }
  v16 = cbNeeded >> 2;
  Src = LocalAlloc(0x40u, 8 * v16);
  if ( !Src )
  {
    v17 = GetLastError();
    LODWORD(v15) = v17;
    if ( v17 > 0 )
      LODWORD(v15) = (unsigned __int16)v17 | 0x80070000;
    LODWORD(v12) = 0;
    goto LABEL_60;
  }
  v36 = LocalAlloc(0x40u, 4 * v16);
  v11 = v36;
  if ( !v36 )
  {
    v18 = GetLastError();
    LODWORD(v15) = v18;
    if ( v18 > 0 )
      LODWORD(v15) = (unsigned __int16)v18 | 0x80070000;
    LODWORD(v12) = 0;
    goto LABEL_60;
  }
  if ( a8 )
  {
    v13 = (LPWSTR *)LocalAlloc(0x40u, 8 * v16);
    if ( !v13 )
    {
      v19 = GetLastError();
      LODWORD(v15) = v19;
      if ( v19 > 0 )
        LODWORD(v15) = (unsigned __int16)v19 | 0x80070000;
      LODWORD(v12) = TokenInformationLength;
      goto LABEL_60;
    }
  }
  v15 = 0;
  v20 = 0;
  v43 = 0;
  if ( !(_DWORD)v16 )
    goto LABEL_77;
  do
  {
    v21 = idProcess[v20];
    TokenHandle = 0;
    hObject = 0;
    v22 = 0;
    TokenInformationLength = 0;
    TokenInformation = 0;
    v23 = OpenProcess(0x3000u, 0, v21);
    v24 = v23;
    if ( v23 )
    {
      if ( OpenProcessToken(v23, 0xAu, &TokenHandle) )
      {
        if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &TokenInformationLength) )
        {
          if ( TokenInformation )
          {
            if ( DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
            {
              if ( !v47
                || (v34[0] = 0, v41 = 0, (int)CapabilityCheck(hObject, v47, v34) >= 0)
                && (v34[0] || v48 && (unsigned int)CheckTokenCapability(hObject, v48, &v41) && v41) )
              {
                if ( !v45 && !a8
                  || (GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength), GetLastError() == 122)
                  && (v22 = (PSID *)LocalAlloc(0x40u, TokenInformationLength)) != 0
                  && GetTokenInformation(TokenHandle, TokenUser, v22, TokenInformationLength, &TokenInformationLength)
                  && (!v45 || EqualSid(Sid, *v22))
                  && (!a8 || ConvertSidToStringSidW(*v22, &v13[v15])) )
                {
                  *((_QWORD *)Src + v15) = v24;
                  v11 = v36;
                  *((_DWORD *)v36 + v15) = idProcess[v20];
                  v15 = (unsigned int)(v15 + 1);
                  goto LABEL_45;
                }
              }
            }
          }
        }
      }
      CloseHandle(v24);
    }
    v11 = v36;
LABEL_45:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( v22 )
      LocalFree(v22);
    if ( hObject )
      CloseHandle(hObject);
    v20 = (unsigned int)(v20 + 1);
  }
  while ( (unsigned int)v20 < (unsigned int)v16 );
  v12 = (unsigned int)v15;
  v25 = (_DWORD)v15 == 0;
  LODWORD(v15) = v43;
  if ( v25 )
  {
LABEL_77:
    v31 = Src;
    goto LABEL_78;
  }
  v26 = (void **)LocalAlloc(0x40u, 8 * v12);
  v8 = (void **)v49;
  *v49 = v26;
  if ( v26 )
  {
    v27 = LocalAlloc(0x40u, 4LL * (unsigned int)v12);
    *v35 = v27;
    if ( v27 )
    {
      if ( !a8 || (v28 = (unsigned __int16 **)LocalAlloc(0x40u, 8 * v12), (*a8 = v28) != 0) )
      {
        memcpy_0(*v8, Src, 8 * v12);
        v11 = v36;
        memcpy_0(*v35, v36, 4LL * (unsigned int)v12);
        if ( a8 )
          memcpy_0(*a8, v13, 8 * v12);
        *v46 = v12;
        goto LABEL_77;
      }
    }
  }
  v29 = GetLastError();
  LODWORD(v15) = v29;
  if ( v29 > 0 )
    LODWORD(v15) = (unsigned __int16)v29 | 0x80070000;
  v11 = v36;
LABEL_60:
  v10 = v35;
LABEL_61:
  if ( (_DWORD)v15 )
  {
    if ( *v8 )
    {
      LocalFree(*v8);
      *v8 = 0;
    }
    if ( *v10 )
    {
      LocalFree(*v10);
      *v10 = 0;
    }
    if ( a8 && *a8 )
    {
      LocalFree(*a8);
      *a8 = 0;
    }
    if ( v13 )
    {
      for ( i = 0; (unsigned int)i < (unsigned int)v12; i = (unsigned int)(i + 1) )
        LocalFree(v13[i]);
    }
  }
  v31 = Src;
  if ( Src )
LABEL_78:
    LocalFree(v31);
  if ( Sid )
    LocalFree(Sid);
  if ( v11 )
    LocalFree(v11);
  if ( v13 )
    LocalFree(v13);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001260c  mov     [rsp-8+arg_0], rbx
0x180012611  push    rbp
0x180012612  push    rsi
0x180012613  push    rdi
0x180012614  push    r12
0x180012616  push    r13
0x180012618  push    r14
0x18001261a  push    r15
0x18001261c  lea     rbp, [rsp-1FC0h]
0x180012624  mov     eax, 20C0h
0x180012629  call    _alloca_probe
0x18001262e  sub     rsp, rax
0x180012631  mov     rax, cs:__security_cookie
0x180012638  xor     rax, rsp
0x18001263b  mov     [rbp+1FF0h+var_40], rax
0x180012642  mov     rax, [rbp+1FF0h+arg_20]
0x180012649  lea     rcx, [rbp+1FF0h+idProcess]; void *
0x18001264d  mov     r13, [rbp+1FF0h+arg_28]
0x180012654  mov     rbx, r9
0x180012657  mov     rdi, [rbp+1FF0h+arg_30]
0x18001265e  mov     rsi, [rbp+1FF0h+arg_38]
0x180012665  mov     [rbp+1FF0h+var_2058], r8
0x180012669  mov     r8d, 2000h; Size
0x18001266f  mov     [rbp+1FF0h+var_2060], rdx
0x180012673  xor     edx, edx; Val
0x180012675  mov     [rbp+1FF0h+var_2070], rbx
0x180012679  mov     [rbp+1FF0h+var_2068], rax
0x18001267d  mov     [rbp+1FF0h+var_2050], r13
0x180012681  mov     [rsp+20F0h+var_20B8], rdi
0x180012686  mov     [rsp+20F0h+Sid], 0
0x18001268f  call    memset_0
0x180012694  mov     rax, [rbp+1FF0h+var_2068]
0x180012698  xor     ecx, ecx
0x18001269a  mov     [rsp+20F0h+cbNeeded], ecx
0x18001269e  mov     r14d, ecx
0x1800126a1  mov     [rsp+20F0h+Src], rcx
0x1800126a6  mov     r12d, ecx
0x1800126a9  mov     [rsp+20F0h+TokenInformationLength], ecx
0x1800126ad  mov     r15d, ecx
0x1800126b0  mov     [rax], ecx
0x1800126b2  mov     [r13+0], rcx
0x1800126b6  mov     [rdi], rcx
0x1800126b9  test    rsi, rsi
0x1800126bc  jz      short loc_1800126C1
0x1800126be  mov     [rsi], rcx
0x1800126c1  test    rbx, rbx
0x1800126c4  jz      short loc_1800126F6
0x1800126c6  lea     rdx, [rsp+20F0h+Sid]; Sid
0x1800126cb  mov     rcx, rbx; StringSid
0x1800126ce  call    cs:__imp_ConvertStringSidToSidW
0x1800126d4  test    eax, eax
0x1800126d6  jnz     short loc_1800126F6
0x1800126d8  call    cs:__imp_GetLastError
0x1800126de  mov     ebx, eax
0x1800126e0  test    eax, eax
0x1800126e2  jle     loc_180012A9D
0x1800126e8  movzx   ebx, ax
0x1800126eb  or      ebx, 80070000h
0x1800126f1  jmp     loc_180012A9D
0x1800126f6  lea     r8, [rsp+20F0h+cbNeeded]; lpcbNeeded
0x1800126fb  mov     edx, 2000h; cb
0x180012700  lea     rcx, [rbp+1FF0h+idProcess]; lpidProcess
0x180012704  call    cs:__imp_K32EnumProcesses
0x18001270a  test    eax, eax
0x18001270c  jz      short loc_1800126D8
0x18001270e  mov     r12d, [rsp+20F0h+cbNeeded]
0x180012713  mov     ecx, 40h ; '@'; uFlags
0x180012718  shr     r12d, 2
0x18001271c  lea     rdi, ds:0[r12*8]
0x180012724  mov     rdx, rdi; uBytes
0x180012727  call    cs:__imp_LocalAlloc
0x18001272d  mov     [rsp+20F0h+Src], rax
0x180012732  test    rax, rax
0x180012735  jnz     short loc_180012754
0x180012737  call    cs:__imp_GetLastError
0x18001273d  mov     ebx, eax
0x18001273f  test    eax, eax
0x180012741  jle     short loc_18001274C
0x180012743  movzx   ebx, ax
0x180012746  or      ebx, 80070000h
0x18001274c  mov     r12d, r14d
0x18001274f  jmp     loc_180012A98
0x180012754  mov     ebx, 40h ; '@'
0x180012759  lea     rdx, ds:0[r12*4]; uBytes
0x180012761  mov     ecx, ebx; uFlags
0x180012763  call    cs:__imp_LocalAlloc
0x180012769  mov     [rsp+20F0h+var_20B0], rax
0x18001276e  mov     r14, rax
0x180012771  test    rax, rax
0x180012774  jnz     short loc_180012793
0x180012776  call    cs:__imp_GetLastError
0x18001277c  mov     ebx, eax
0x18001277e  test    eax, eax
0x180012780  jle     short loc_18001278B
0x180012782  movzx   ebx, ax
0x180012785  or      ebx, 80070000h
0x18001278b  mov     r12d, r15d
0x18001278e  jmp     loc_180012A98
0x180012793  test    rsi, rsi
0x180012796  jz      short loc_1800127CA
0x180012798  mov     rdx, rdi; uBytes
0x18001279b  mov     ecx, ebx; uFlags
0x18001279d  call    cs:__imp_LocalAlloc
0x1800127a3  mov     r15, rax
0x1800127a6  test    rax, rax
0x1800127a9  jnz     short loc_1800127CA
0x1800127ab  call    cs:__imp_GetLastError
0x1800127b1  mov     ebx, eax
0x1800127b3  test    eax, eax
0x1800127b5  jle     short loc_1800127C0
0x1800127b7  movzx   ebx, ax
0x1800127ba  or      ebx, 80070000h
0x1800127c0  mov     r12d, [rsp+20F0h+TokenInformationLength]
0x1800127c5  jmp     loc_180012A98
0x1800127ca  xor     ebx, ebx
0x1800127cc  xor     r13d, r13d
0x1800127cf  mov     [rsp+20F0h+var_2080], ebx
0x1800127d3  test    r12d, r12d
0x1800127d6  jz      loc_180012B53
0x1800127dc  mov     r8d, [rbp+r13*4+1FF0h+idProcess]; dwProcessId
0x1800127e1  xor     edx, edx; bInheritHandle
0x1800127e3  mov     ecx, 3000h; dwDesiredAccess
0x1800127e8  mov     [rsp+20F0h+TokenHandle], 0
0x1800127f1  mov     [rsp+20F0h+hObject], 0
0x1800127fa  xor     edi, edi
0x1800127fc  mov     [rsp+20F0h+TokenInformationLength], 0
0x180012804  mov     [rsp+20F0h+TokenInformation], 0
0x18001280c  call    cs:__imp_OpenProcess
0x180012812  mov     r14, rax
0x180012815  test    rax, rax
0x180012818  jz      loc_1800129C8
0x18001281e  lea     r8, [rsp+20F0h+TokenHandle]; TokenHandle
0x180012823  mov     rcx, rax; ProcessHandle
0x180012826  lea     edx, [rdi+0Ah]; DesiredAccess
0x180012829  call    cs:__imp_OpenProcessToken
0x18001282f  test    eax, eax
0x180012831  jz      loc_1800129BF
0x180012837  mov     rcx, [rsp+20F0h+TokenHandle]; TokenHandle
0x18001283c  lea     rax, [rsp+20F0h+TokenInformationLength]
0x180012841  lea     r9d, [rdi+4]; TokenInformationLength
0x180012845  mov     [rsp+20F0h+ReturnLength], rax; ReturnLength
0x18001284a  lea     r8, [rsp+20F0h+TokenInformation]; TokenInformation
0x18001284f  lea     edx, [rdi+1Dh]; TokenInformationClass
0x180012852  call    cs:__imp_GetTokenInformation
0x180012858  test    eax, eax
0x18001285a  jz      loc_1800129BF
0x180012860  cmp     [rsp+20F0h+TokenInformation], edi
0x180012864  jz      loc_1800129BF
0x18001286a  mov     rcx, [rsp+20F0h+TokenHandle]; hExistingToken
0x18001286f  lea     rax, [rsp+20F0h+hObject]
0x180012874  mov     [rsp+20F0h+phNewToken], rax; phNewToken
0x180012879  lea     edx, [rdi+0Ch]; dwDesiredAccess
0x18001287c  lea     eax, [rdi+2]
0x18001287f  xor     r8d, r8d; lpTokenAttributes
0x180012882  mov     r9d, eax; ImpersonationLevel
0x180012885  mov     dword ptr [rsp+20F0h+ReturnLength], eax; TokenType
0x180012889  call    cs:__imp_DuplicateTokenEx
0x18001288f  test    eax, eax
0x180012891  jz      loc_1800129BF
0x180012897  mov     rax, [rbp+1FF0h+var_2060]
0x18001289b  test    rax, rax
0x18001289e  jz      short loc_1800128FD
0x1800128a0  mov     rcx, [rsp+20F0h+hObject]
0x1800128a5  lea     r8, [rsp+20F0h+var_20BC]
0x1800128aa  mov     rdx, rax
0x1800128ad  mov     [rsp+20F0h+var_20BC], dil
0x1800128b2  mov     [rsp+20F0h+var_2090], edi
0x1800128b6  call    cs:__imp_CapabilityCheck
0x1800128bc  test    eax, eax
0x1800128be  js      loc_1800129BF
0x1800128c4  cmp     [rsp+20F0h+var_20BC], dil
0x1800128c9  jnz     short loc_1800128FD
0x1800128cb  mov     rax, [rbp+1FF0h+var_2058]
0x1800128cf  test    rax, rax
0x1800128d2  jz      loc_1800129BF
0x1800128d8  mov     rcx, [rsp+20F0h+hObject]
0x1800128dd  lea     r8, [rsp+20F0h+var_2090]
0x1800128e2  mov     rdx, rax
0x1800128e5  call    cs:__imp_CheckTokenCapability
0x1800128eb  test    eax, eax
0x1800128ed  jz      loc_1800129BF
0x1800128f3  cmp     [rsp+20F0h+var_2090], edi
0x1800128f7  jz      loc_1800129BF
0x1800128fd  cmp     [rbp+1FF0h+var_2070], rdi
0x180012901  jnz     short loc_18001290C
0x180012903  test    rsi, rsi
0x180012906  jz      loc_1800129A4
0x18001290c  mov     rcx, [rsp+20F0h+TokenHandle]; TokenHandle
0x180012911  lea     rax, [rsp+20F0h+TokenInformationLength]
0x180012916  xor     r9d, r9d; TokenInformationLength
0x180012919  mov     [rsp+20F0h+ReturnLength], rax; ReturnLength
0x18001291e  xor     r8d, r8d; TokenInformation
0x180012921  lea     edx, [r9+1]; TokenInformationClass
0x180012925  call    cs:__imp_GetTokenInformation
0x18001292b  call    cs:__imp_GetLastError
0x180012931  cmp     eax, 7Ah ; 'z'
0x180012934  jnz     loc_1800129BF
0x18001293a  mov     edx, [rsp+20F0h+TokenInformationLength]; uBytes
0x18001293e  lea     ecx, [rax-3Ah]; uFlags
0x180012941  call    cs:__imp_LocalAlloc
0x180012947  mov     rdi, rax
0x18001294a  test    rax, rax
0x18001294d  jz      short loc_1800129BF
0x18001294f  mov     r9d, [rsp+20F0h+TokenInformationLength]; TokenInformationLength
0x180012954  lea     rax, [rsp+20F0h+TokenInformationLength]
0x180012959  mov     rcx, [rsp+20F0h+TokenHandle]; TokenHandle
0x18001295e  mov     r8, rdi; TokenInformation
0x180012961  mov     edx, 1; TokenInformationClass
0x180012966  mov     [rsp+20F0h+ReturnLength], rax; ReturnLength
0x18001296b  call    cs:__imp_GetTokenInformation
0x180012971  test    eax, eax
0x180012973  jz      short loc_1800129BF
0x180012975  cmp     [rbp+1FF0h+var_2070], 0
0x18001297a  jz      short loc_18001298E
0x18001297c  mov     rdx, [rdi]; pSid2
0x18001297f  mov     rcx, [rsp+20F0h+Sid]; pSid1
0x180012984  call    cs:__imp_EqualSid
0x18001298a  test    eax, eax
0x18001298c  jz      short loc_1800129BF
0x18001298e  test    rsi, rsi
0x180012991  jz      short loc_1800129A4
0x180012993  mov     rcx, [rdi]; Sid
0x180012996  lea     rdx, [r15+rbx*8]; StringSid
0x18001299a  call    cs:__imp_ConvertSidToStringSidW
0x1800129a0  test    eax, eax
0x1800129a2  jz      short loc_1800129BF
0x1800129a4  mov     rax, [rsp+20F0h+Src]
0x1800129a9  mov     [rax+rbx*8], r14
0x1800129ad  mov     r14, [rsp+20F0h+var_20B0]
0x1800129b2  mov     eax, [rbp+r13*4+1FF0h+idProcess]
0x1800129b7  mov     [r14+rbx*4], eax
0x1800129bb  inc     ebx
0x1800129bd  jmp     short loc_1800129CD
0x1800129bf  mov     rcx, r14; hObject
0x1800129c2  call    cs:__imp_CloseHandle
0x1800129c8  mov     r14, [rsp+20F0h+var_20B0]
0x1800129cd  mov     rcx, [rsp+20F0h+TokenHandle]; hObject
0x1800129d2  test    rcx, rcx
0x1800129d5  jz      short loc_1800129DD
0x1800129d7  call    cs:__imp_CloseHandle
0x1800129dd  test    rdi, rdi
0x1800129e0  jz      short loc_1800129EB
0x1800129e2  mov     rcx, rdi; hMem
0x1800129e5  call    cs:__imp_LocalFree
0x1800129eb  mov     rcx, [rsp+20F0h+hObject]; hObject
0x1800129f0  test    rcx, rcx
0x1800129f3  jz      short loc_1800129FB
0x1800129f5  call    cs:__imp_CloseHandle
0x1800129fb  inc     r13d
0x1800129fe  cmp     r13d, r12d
0x180012a01  jb      loc_1800127DC
0x180012a07  mov     r12d, ebx
0x180012a0a  test    ebx, ebx
0x180012a0c  mov     ebx, [rsp+20F0h+var_2080]
0x180012a10  jz      loc_180012B53
0x180012a16  lea     rdi, ds:0[r12*8]
0x180012a1e  mov     ecx, 40h ; '@'; uFlags
0x180012a23  mov     rdx, rdi; uBytes
0x180012a26  mov     r14d, r12d
0x180012a29  call    cs:__imp_LocalAlloc
0x180012a2f  mov     r13, [rbp+1FF0h+var_2050]
0x180012a33  mov     [r13+0], rax
0x180012a37  test    rax, rax
0x180012a3a  jz      short loc_180012A7E
0x180012a3c  shl     r14, 2
0x180012a40  mov     ecx, 40h ; '@'; uFlags
0x180012a45  mov     rdx, r14; uBytes
0x180012a48  call    cs:__imp_LocalAlloc
0x180012a4e  mov     rcx, [rsp+20F0h+var_20B8]
0x180012a53  mov     [rcx], rax
0x180012a56  test    rax, rax
0x180012a59  jz      short loc_180012A7E
0x180012a5b  test    rsi, rsi
0x180012a5e  jz      loc_180012B10
0x180012a64  mov     rdx, rdi; uBytes
0x180012a67  mov     ecx, 40h ; '@'; uFlags
0x180012a6c  call    cs:__imp_LocalAlloc
0x180012a72  mov     [rsi], rax
0x180012a75  test    rax, rax
0x180012a78  jnz     loc_180012B10
0x180012a7e  call    cs:__imp_GetLastError
0x180012a84  mov     ebx, eax
0x180012a86  test    eax, eax
0x180012a88  jle     short loc_180012A93
0x180012a8a  movzx   ebx, ax
0x180012a8d  or      ebx, 80070000h
0x180012a93  mov     r14, [rsp+20F0h+var_20B0]
0x180012a98  mov     rdi, [rsp+20F0h+var_20B8]
0x180012a9d  test    ebx, ebx
0x180012a9f  jz      short loc_180012B04
0x180012aa1  mov     rcx, [r13+0]; hMem
0x180012aa5  test    rcx, rcx
0x180012aa8  jz      short loc_180012AB8
0x180012aaa  call    cs:__imp_LocalFree
0x180012ab0  mov     qword ptr [r13+0], 0
0x180012ab8  mov     rcx, [rdi]; hMem
0x180012abb  test    rcx, rcx
0x180012abe  jz      short loc_180012ACD
0x180012ac0  call    cs:__imp_LocalFree
0x180012ac6  mov     qword ptr [rdi], 0
  ... truncated ...
```

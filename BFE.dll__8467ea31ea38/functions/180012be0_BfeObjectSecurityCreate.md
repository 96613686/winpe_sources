# BfeObjectSecurityCreate

- ea: `0x180012be0`
- end: `0x18001309c`
- name: `BfeObjectSecurityCreate`
- size: `1212`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR ParentDescriptor, PSECURITY_DESCRIPTOR CreatorDescriptor, BOOL IsContainerObject, HANDLE Token, __int64)`
- caller_count: `7`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000aef4`
- `0x180030180`
- `0x180038e90`
- `0x18003fa78`
- `0x18003fb08`
- `0x1800476a0`
- `0x180068ec8`

## callees

- `0x180008240`
- `0x18000f1a8`
- `0x180010ad0`
- `0x18001236c`
- `0x180012a30`
- `0x180012be0`
- `0x180022730`
- `0x18002aef0`
- `0x180058b30`
- `0x180087dc0`
- `0x180087dcc`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180012d2f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180012e68`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180012d2f`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180012e68`
- `ntdll!RtlLookupEntryHashTable` at `0x180012d7b`
- `ntdll!RtlLookupEntryHashTable` at `0x180012d7b`
- `ntdll!RtlGetNextEntryHashTable` at `0x180013085`
- `ntdll!RtlGetNextEntryHashTable` at `0x180013085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012c4a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012edb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012c4a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180012edb`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180012e4b`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180012ea8`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180012e4b`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180012ea8`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x180012d09`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x180012d09`

## string_xrefs

- `0x180012f6c`: `BfeObjectSecurityCreate`
- `0x180012f46`: `CreatePrivateObjectSecurityEx`
- `0x180012db8`: `BfeObjectSecurityCreateInternal`

## pseudocode

```c
__int64 __fastcall BfeObjectSecurityCreate(
        char *ParentDescriptor,
        PSECURITY_DESCRIPTOR CreatorDescriptor,
        BOOL IsContainerObject,
        HANDLE Token,
        _QWORD *a5)
{
  char *v9; // r12
  __int64 *Value; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r14
  char *v14; // rax
  __int64 result; // rax
  ULONG AutoInheritFlags; // eax
  unsigned __int8 *v17; // rdi
  ULONG v18; // eax
  size_t v19; // rsi
  __int64 v20; // rbx
  ULONG v21; // ecx
  __int64 v22; // rdx
  __int64 v23; // rdx
  _DWORD *NextEntryHashTable; // r15
  __int64 v25; // rax
  int v26; // r8d
  int v27; // r8d
  __int64 *v28; // rax
  __int64 v29; // rax
  __int64 v30; // rcx
  _DWORD *v31; // rax
  DWORD LastError; // eax
  __int64 v33; // rcx
  int v34; // [rsp+40h] [rbp-61h] BYREF
  _DWORD *v35; // [rsp+48h] [rbp-59h]
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+50h] [rbp-51h] BYREF
  __int128 v37; // [rsp+58h] [rbp-49h] BYREF
  __int64 v38; // [rsp+68h] [rbp-39h]
  _BYTE v39[16]; // [rsp+70h] [rbp-31h] BYREF
  const char *v40; // [rsp+80h] [rbp-21h]
  __int64 v41; // [rsp+88h] [rbp-19h]
  int *v42; // [rsp+90h] [rbp-11h]
  __int64 v43; // [rsp+98h] [rbp-9h]

  NewDescriptor = 0;
  if ( CreatorDescriptor || IsContainerObject )
  {
    v9 = 0;
    v34 = 0;
  }
  else
  {
    v34 = 1;
    if ( ParentDescriptor )
      v9 = ParentDescriptor - 28;
    else
      v9 = 0;
    Value = (__int64 *)TlsGetValue(gBfeContextComponent);
    if ( Value && (v11 = *Value) != 0 )
      v12 = *(_QWORD *)(v11 + 80);
    else
      v12 = 0;
    if ( qword_1800F2AE0 == v12 && lpMem == v9 )
    {
      v13 = 0;
      if ( qword_1800F2AF0 && (++*((_DWORD *)qword_1800F2AF0 + 6), qword_1800F2AF0) )
        v14 = (char *)qword_1800F2AF0 + 28;
      else
        v14 = 0;
LABEL_13:
      *a5 = v14;
      return v13;
    }
  }
  AutoInheritFlags = 123;
  if ( Token )
    AutoInheritFlags = 3;
  if ( CreatePrivateObjectSecurityEx(
         ParentDescriptor,
         CreatorDescriptor,
         &NewDescriptor,
         0,
         IsContainerObject,
         AutoInheritFlags,
         Token,
         (PGENERIC_MAPPING)&GenericMapping) )
  {
    v17 = (unsigned __int8 *)NewDescriptor;
    v35 = 0;
    v38 = 0;
    v37 = 0;
    v18 = RtlLengthSecurityDescriptor(NewDescriptor);
    v19 = v18;
    v20 = 0;
    if ( !v17 )
      goto LABEL_57;
    v21 = 0;
    if ( !v18 )
      goto LABEL_57;
    do
    {
      v22 = v21++;
      v20 = v17[v22] + 37 * v20;
    }
    while ( v21 < v18 );
    if ( v20 )
      v23 = v20;
    else
LABEL_57:
      v23 = -1;
    NextEntryHashTable = (_DWORD *)RtlLookupEntryHashTable(&qword_1800F2AB0, v23, &v37);
    if ( NextEntryHashTable )
    {
      while ( 1 )
      {
        v35 = NextEntryHashTable;
        if ( RtlLengthSecurityDescriptor(NextEntryHashTable + 7) == (_DWORD)v19
          && !memcmp_0(v17, NextEntryHashTable + 7, v19) )
        {
          break;
        }
        NextEntryHashTable = (_DWORD *)RtlGetNextEntryHashTable(&qword_1800F2AB0, &v37);
        if ( !NextEntryHashTable )
          goto LABEL_26;
      }
      v13 = 0;
    }
    else
    {
LABEL_26:
      v25 = WfpMemAlloc((unsigned int)(v19 + 28), 0);
      v13 = v25;
      if ( v25 )
      {
        NextEntryHashTable = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v26, 0, (__int64)"BfeObjectSecurityCreateInternal", v25);
        }
        if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
        {
          v34 = v13;
          v42 = &v34;
          v40 = "BfeObjectSecurityCreateInternal";
          v41 = 32;
          v43 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
            (unsigned int)WFP_USERMODE_ERROR,
            v26,
            3,
            (__int64)v39);
          DestroyPrivateObjectSecurity(&NewDescriptor);
          goto LABEL_50;
        }
        goto LABEL_38;
      }
      NextEntryHashTable = v35;
      *((_QWORD *)v35 + 2) = v20;
      NextEntryHashTable[6] = 0;
      memcpy_0(NextEntryHashTable + 7, v17, v19);
      WfpHashtableInsert(&qword_1800F2AB0, NextEntryHashTable);
      WfpRestructureHashtable(&qword_1800F2AB0);
      if ( !NextEntryHashTable )
      {
LABEL_38:
        DestroyPrivateObjectSecurity(&NewDescriptor);
        if ( !v13 )
        {
          if ( v34 )
          {
            BfeObjectSecurityRelease(lpMem);
            BfeObjectSecurityRelease(qword_1800F2AF0);
            v28 = (__int64 *)TlsGetValue(gBfeContextComponent);
            if ( v28 && (v29 = *v28) != 0 )
              v30 = *(_QWORD *)(v29 + 80);
            else
              v30 = 0;
            qword_1800F2AE0 = v30;
            v31 = NextEntryHashTable;
            qword_1800F2AF0 = NextEntryHashTable;
            lpMem = v9;
            if ( v9 )
            {
              ++*((_DWORD *)v9 + 6);
              v31 = qword_1800F2AF0;
            }
            if ( v31 )
              ++v31[6];
          }
          if ( NextEntryHashTable )
            v14 = (char *)(NextEntryHashTable + 7);
          else
            v14 = 0;
          goto LABEL_13;
        }
LABEL_50:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v27, 0, (__int64)"BfeObjectSecurityCreate", v13);
        }
        if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
        {
          v34 = v13;
          v42 = &v34;
          v40 = "BfeObjectSecurityCreate";
          v41 = 24;
          v43 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
            (unsigned int)WFP_USERMODE_ERROR,
            v27,
            3,
            (__int64)v39);
        }
        return v13;
      }
    }
    ++NextEntryHashTable[6];
    goto LABEL_38;
  }
  LastError = GetLastError();
  result = WfpReportSysErrorAsWinError(v33, "CreatePrivateObjectSecurityEx", LastError);
  v13 = result;
  if ( result )
    goto LABEL_50;
  return result;
}

```

## disassembly

```asm
0x180012be0  push    rbp
0x180012be2  push    rbx
0x180012be3  push    rsi
0x180012be4  push    rdi
0x180012be5  push    r12
0x180012be7  push    r13
0x180012be9  push    r14
0x180012beb  push    r15
0x180012bed  lea     rbp, [rsp-17h]
0x180012bf2  sub     rsp, 0B8h
0x180012bf9  mov     rax, cs:__security_cookie
0x180012c00  xor     rax, rsp
0x180012c03  mov     [rbp+4Fh+var_50], rax
0x180012c07  mov     r13, [rbp+4Fh+arg_20]
0x180012c0b  xor     r15d, r15d
0x180012c0e  mov     [rbp+4Fh+NewDescriptor], r15
0x180012c12  mov     r14, r9
0x180012c15  mov     esi, r8d
0x180012c18  mov     rbx, rdx
0x180012c1b  mov     rdi, rcx
0x180012c1e  test    rdx, rdx
0x180012c21  jnz     loc_180012CCC
0x180012c27  test    r8d, r8d
0x180012c2a  jnz     loc_180012CCC
0x180012c30  mov     [rbp+4Fh+var_B0], 1
0x180012c37  test    rcx, rcx
0x180012c3a  jz      loc_18001301C
0x180012c40  lea     r12, [rcx-1Ch]
0x180012c44  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180012c4a  call    cs:__imp_TlsGetValue
0x180012c50  test    rax, rax
0x180012c53  jz      loc_180013014
0x180012c59  mov     rax, [rax]
0x180012c5c  test    rax, rax
0x180012c5f  jz      loc_180013014
0x180012c65  mov     rcx, [rax+50h]
0x180012c69  cmp     cs:qword_1800F2AE0, rcx
0x180012c70  jnz     short loc_180012CD3
0x180012c72  cmp     cs:lpMem, r12
0x180012c79  jnz     short loc_180012CD3
0x180012c7b  mov     rax, cs:qword_1800F2AF0
0x180012c82  mov     r14, r15
0x180012c85  test    rax, rax
0x180012c88  jz      loc_18001300C
0x180012c8e  inc     dword ptr [rax+18h]
0x180012c91  mov     rax, cs:qword_1800F2AF0
0x180012c98  test    rax, rax
0x180012c9b  jz      loc_18001300C
0x180012ca1  add     rax, 1Ch
0x180012ca5  mov     [r13+0], rax
0x180012ca9  mov     rax, r14
0x180012cac  mov     rcx, [rbp+4Fh+var_50]
0x180012cb0  xor     rcx, rsp; StackCookie
0x180012cb3  call    __security_check_cookie
0x180012cb8  add     rsp, 0B8h
0x180012cbf  pop     r15
0x180012cc1  pop     r14
0x180012cc3  pop     r13
0x180012cc5  pop     r12
0x180012cc7  pop     rdi
0x180012cc8  pop     rsi
0x180012cc9  pop     rbx
0x180012cca  pop     rbp
0x180012ccb  retn
0x180012ccc  mov     r12, r15
0x180012ccf  mov     [rbp+4Fh+var_B0], r15d
0x180012cd3  mov     eax, 7Bh ; '{'
0x180012cd8  lea     r8, [rbp+4Fh+NewDescriptor]; NewDescriptor
0x180012cdc  mov     ecx, 3
0x180012ce1  test    r14, r14
0x180012ce4  mov     rdx, rbx; CreatorDescriptor
0x180012ce7  cmovnz  eax, ecx
0x180012cea  lea     rcx, GenericMapping
0x180012cf1  mov     [rsp+0F0h+GenericMapping], rcx; GenericMapping
0x180012cf6  xor     r9d, r9d; ObjectType
0x180012cf9  mov     [rsp+0F0h+Token], r14; Token
0x180012cfe  mov     rcx, rdi; ParentDescriptor
0x180012d01  mov     [rsp+0F0h+AutoInheritFlags], eax; AutoInheritFlags
0x180012d05  mov     [rsp+0F0h+IsContainerObject], esi; IsContainerObject
0x180012d09  call    cs:__imp_CreatePrivateObjectSecurityEx
0x180012d0f  test    eax, eax
0x180012d11  jz      loc_180012F3D
0x180012d17  mov     rdi, [rbp+4Fh+NewDescriptor]
0x180012d1b  xorps   xmm0, xmm0
0x180012d1e  xor     eax, eax
0x180012d20  mov     [rbp+4Fh+var_A8], r15
0x180012d24  mov     rcx, rdi; SecurityDescriptor
0x180012d27  mov     [rbp+4Fh+var_88], rax
0x180012d2b  movups  [rbp+4Fh+var_98], xmm0
0x180012d2f  call    cs:__imp_RtlLengthSecurityDescriptor
0x180012d35  mov     esi, eax
0x180012d37  mov     rbx, r15
0x180012d3a  test    rdi, rdi
0x180012d3d  jz      loc_180013000
0x180012d43  mov     ecx, r15d
0x180012d46  test    eax, eax
0x180012d48  jz      loc_180013000
0x180012d4e  xchg    ax, ax
0x180012d50  imul    rbx, 25h ; '%'
0x180012d54  mov     edx, ecx
0x180012d56  inc     ecx
0x180012d58  movzx   r8d, byte ptr [rdx+rdi]
0x180012d5d  add     rbx, r8
0x180012d60  cmp     ecx, esi
0x180012d62  jb      short loc_180012D50
0x180012d64  test    rbx, rbx
0x180012d67  jz      loc_180013000
0x180012d6d  mov     rdx, rbx
0x180012d70  lea     r8, [rbp+4Fh+var_98]
0x180012d74  lea     rcx, qword_1800F2AB0
0x180012d7b  call    cs:__imp_RtlLookupEntryHashTable
0x180012d81  mov     r15, rax
0x180012d84  test    rax, rax
0x180012d87  jnz     loc_180012E60
0x180012d8d  lea     ecx, [rsi+1Ch]; dwBytes
0x180012d90  xor     edx, edx; dwFlags
0x180012d92  lea     r8, [rbp+4Fh+var_A8]
0x180012d96  call    WfpMemAlloc
0x180012d9b  mov     r14, rax
0x180012d9e  test    rax, rax
0x180012da1  jz      loc_180013032
0x180012da7  xor     r15d, r15d
0x180012daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180012db1  lea     rdi, WPP_GLOBAL_Control
0x180012db8  lea     rbx, aBfeobjectsecur_4; "BfeObjectSecurityCreateInternal"
0x180012dbf  cmp     rcx, rdi
0x180012dc2  jz      short loc_180012DEB
0x180012dc4  cmp     byte ptr [rcx+19h], 2
0x180012dc8  jb      short loc_180012DEB
0x180012dca  test    byte ptr [rcx+1Ch], 1
0x180012dce  jz      short loc_180012DEB
0x180012dd0  mov     rcx, [rcx+10h]
0x180012dd4  mov     edx, 1Ah
0x180012dd9  mov     [rsp+0F0h+AutoInheritFlags], r14d
0x180012dde  xor     r9d, r9d
0x180012de1  mov     qword ptr [rsp+0F0h+IsContainerObject], rbx
0x180012de6  call    WPP_SF_Ssd
0x180012deb  cmp     cs:gWfpLogUserModeErrors, r15d
0x180012df2  jz      loc_180012EA4
0x180012df8  test    cs:byte_1800F30F5, 1
0x180012dff  jz      loc_180012EA4
0x180012e05  lea     rax, [rbp+4Fh+var_B0]
0x180012e09  mov     [rbp+4Fh+var_B0], r14d
0x180012e0d  mov     [rbp+4Fh+var_60], rax
0x180012e11  lea     rdx, WFP_USERMODE_ERROR
0x180012e18  lea     rax, [rbp+4Fh+var_80]
0x180012e1c  mov     [rbp+4Fh+var_70], rbx
0x180012e20  mov     r9d, 3
0x180012e26  mov     qword ptr [rsp+0F0h+IsContainerObject], rax
0x180012e2b  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180012e32  mov     [rbp+4Fh+var_68], 20h ; ' '
0x180012e3a  mov     [rbp+4Fh+var_58], 4
0x180012e42  call    McGenEventWrite_EtwEventWriteTransfer
0x180012e47  lea     rcx, [rbp+4Fh+NewDescriptor]; ObjectDescriptor
0x180012e4b  call    cs:__imp_DestroyPrivateObjectSecurity
0x180012e51  jmp     loc_180012F65
0x180012e60  lea     rcx, [r15+1Ch]; SecurityDescriptor
0x180012e64  mov     [rbp+4Fh+var_A8], r15
0x180012e68  call    cs:__imp_RtlLengthSecurityDescriptor
0x180012e6e  cmp     eax, esi
0x180012e70  jnz     loc_18001307A
0x180012e76  mov     r8, rsi; Size
0x180012e79  lea     rdx, [r15+1Ch]; Buf2
0x180012e7d  mov     rcx, rdi; Buf1
0x180012e80  call    memcmp_0
0x180012e85  test    eax, eax
0x180012e87  jnz     loc_18001307A
0x180012e8d  xor     r14d, r14d
0x180012e90  test    r15, r15
0x180012e93  jz      loc_180012D8D
0x180012e99  inc     dword ptr [r15+18h]
0x180012e9d  lea     rdi, WPP_GLOBAL_Control
0x180012ea4  lea     rcx, [rbp+4Fh+NewDescriptor]; ObjectDescriptor
0x180012ea8  call    cs:__imp_DestroyPrivateObjectSecurity
0x180012eae  test    r14, r14
0x180012eb1  jnz     loc_180012F65
0x180012eb7  cmp     [rbp+4Fh+var_B0], r14d
0x180012ebb  jz      short loc_180012F2B
0x180012ebd  mov     rcx, cs:lpMem; lpMem
0x180012ec4  call    BfeObjectSecurityRelease
0x180012ec9  mov     rcx, cs:qword_1800F2AF0; lpMem
0x180012ed0  call    BfeObjectSecurityRelease
0x180012ed5  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180012edb  call    cs:__imp_TlsGetValue
0x180012ee1  test    rax, rax
0x180012ee4  jz      loc_180013024
0x180012eea  mov     rax, [rax]
0x180012eed  test    rax, rax
0x180012ef0  jz      loc_180013024
0x180012ef6  mov     rcx, [rax+50h]
0x180012efa  mov     cs:qword_1800F2AE0, rcx
0x180012f01  mov     rax, r15
0x180012f04  mov     cs:qword_1800F2AF0, rax
0x180012f0b  mov     cs:lpMem, r12
0x180012f12  test    r12, r12
0x180012f15  jz      short loc_180012F23
0x180012f17  inc     dword ptr [r12+18h]
0x180012f1c  mov     rax, cs:qword_1800F2AF0
0x180012f23  test    rax, rax
0x180012f26  jz      short loc_180012F2B
0x180012f28  inc     dword ptr [rax+18h]
0x180012f2b  test    r15, r15
0x180012f2e  jz      loc_18001302B
0x180012f34  lea     rax, [r15+1Ch]
0x180012f38  jmp     loc_180012CA5
0x180012f3d  call    cs:__imp_GetLastError
0x180012f43  mov     r8d, eax
0x180012f46  lea     rdx, aCreateprivateo; "CreatePrivateObjectSecurityEx"
0x180012f4d  call    WfpReportSysErrorAsWinError
0x180012f52  mov     r14, rax
0x180012f55  test    rax, rax
0x180012f58  jz      loc_180012CAC
0x180012f5e  lea     rdi, WPP_GLOBAL_Control
0x180012f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180012f6c  lea     rbx, aBfeobjectsecur_9; "BfeObjectSecurityCreate"
0x180012f73  cmp     rcx, rdi
0x180012f76  jz      short loc_180012F9F
0x180012f78  cmp     byte ptr [rcx+19h], 2
0x180012f7c  jb      short loc_180012F9F
0x180012f7e  test    byte ptr [rcx+1Ch], 1
0x180012f82  jz      short loc_180012F9F
0x180012f84  mov     rcx, [rcx+10h]
0x180012f88  mov     edx, 1Ah
0x180012f8d  mov     [rsp+0F0h+AutoInheritFlags], r14d
0x180012f92  xor     r9d, r9d
0x180012f95  mov     qword ptr [rsp+0F0h+IsContainerObject], rbx
0x180012f9a  call    WPP_SF_Ssd
0x180012f9f  cmp     cs:gWfpLogUserModeErrors, 0
0x180012fa6  jz      loc_180012CA9
0x180012fac  test    cs:byte_1800F30F5, 1
0x180012fb3  jz      loc_180012CA9
0x180012fb9  lea     rax, [rbp+4Fh+var_B0]
0x180012fbd  mov     [rbp+4Fh+var_B0], r14d
0x180012fc1  mov     [rbp+4Fh+var_60], rax
0x180012fc5  lea     rdx, WFP_USERMODE_ERROR
0x180012fcc  lea     rax, [rbp+4Fh+var_80]
0x180012fd0  mov     [rbp+4Fh+var_70], rbx
0x180012fd4  mov     r9d, 3
0x180012fda  mov     qword ptr [rsp+0F0h+IsContainerObject], rax
0x180012fdf  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180012fe6  mov     [rbp+4Fh+var_68], 18h
0x180012fee  mov     [rbp+4Fh+var_58], 4
0x180012ff6  call    McGenEventWrite_EtwEventWriteTransfer
0x180012ffb  jmp     loc_180012CA9
0x180013000  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180013007  jmp     loc_180012D70
0x18001300c  mov     rax, r15
0x18001300f  jmp     loc_180012CA5
0x180013014  mov     rcx, r15
0x180013017  jmp     loc_180012C69
0x18001301c  mov     r12, r15
0x18001301f  jmp     loc_180012C44
0x180013024  xor     ecx, ecx
0x180013026  jmp     loc_180012EFA
0x18001302b  xor     eax, eax
0x18001302d  jmp     loc_180012CA5
0x180013032  mov     r15, [rbp+4Fh+var_A8]
0x180013036  mov     r8, rsi; Size
0x180013039  mov     rdx, rdi; Src
0x18001303c  mov     [r15+10h], rbx
0x180013040  lea     rcx, [r15+1Ch]; void *
0x180013044  mov     dword ptr [r15+18h], 0
0x18001304c  call    memcpy_0
0x180013051  mov     rdx, r15
0x180013054  lea     rcx, qword_1800F2AB0
0x18001305b  call    WfpHashtableInsert
0x180013060  lea     rcx, qword_1800F2AB0
0x180013067  call    WfpRestructureHashtable
0x18001306c  test    r15, r15
0x18001306f  jnz     loc_180012E99
0x180013075  jmp     loc_180012E9D
0x18001307a  lea     rdx, [rbp+4Fh+var_98]
0x18001307e  lea     rcx, qword_1800F2AB0
0x180013085  call    cs:__imp_RtlGetNextEntryHashTable
0x18001308b  mov     r15, rax
0x18001308e  test    rax, rax
0x180013091  jnz     loc_180012E60
0x180013097  jmp     loc_180012D8D
```

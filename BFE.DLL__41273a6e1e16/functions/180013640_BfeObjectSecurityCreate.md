# BfeObjectSecurityCreate

- ea: `0x180013640`
- end: `0x180013b3c`
- name: `BfeObjectSecurityCreate`
- size: `1276`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR ParentDescriptor, PSECURITY_DESCRIPTOR CreatorDescriptor, BOOL IsContainerObject, HANDLE Token, __int64)`
- caller_count: `7`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b5b4`
- `0x180031aa8`
- `0x180032274`
- `0x1800376d0`
- `0x180040dcc`
- `0x180040e5c`
- `0x18006b460`

## callees

- `0x1800087f0`
- `0x18000fb34`
- `0x180011510`
- `0x180012d8c`
- `0x180013480`
- `0x180013640`
- `0x180024e40`
- `0x18002c690`
- `0x18005aa60`
- `0x18008ad60`
- `0x18008ad6c`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x18001379c`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800138ea`
- `ntdll!RtlLengthSecurityDescriptor` at `0x18001379c`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800138ea`
- `ntdll!RtlLookupEntryHashTable` at `0x1800137fb`
- `ntdll!RtlLookupEntryHashTable` at `0x1800137fb`
- `ntdll!RtlGetNextEntryHashTable` at `0x180013b1f`
- `ntdll!RtlGetNextEntryHashTable` at `0x180013b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800139d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800136aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013969`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800136aa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013969`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800138d1`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180013930`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800138d1`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180013930`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x180013770`
- `api-ms-win-security-base-l1-1-0!CreatePrivateObjectSecurityEx` at `0x180013770`

## string_xrefs

- `0x180013a06`: `BfeObjectSecurityCreate`
- `0x1800139e0`: `CreatePrivateObjectSecurityEx`
- `0x18001383e`: `BfeObjectSecurityCreateInternal`

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
    if ( qword_1800F5B00 == v12 && lpMem == v9 )
    {
      v13 = 0;
      if ( qword_1800F5B10 && (++*((_DWORD *)qword_1800F5B10 + 6), qword_1800F5B10) )
        v14 = (char *)qword_1800F5B10 + 28;
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
    NextEntryHashTable = (_DWORD *)RtlLookupEntryHashTable(&qword_1800F5AD0, v23, &v37);
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
        NextEntryHashTable = (_DWORD *)RtlGetNextEntryHashTable(&qword_1800F5AD0, &v37);
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
        if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
      WfpHashtableInsert(&qword_1800F5AD0, NextEntryHashTable);
      WfpRestructureHashtable(&qword_1800F5AD0);
      if ( !NextEntryHashTable )
      {
LABEL_38:
        DestroyPrivateObjectSecurity(&NewDescriptor);
        if ( !v13 )
        {
          if ( v34 )
          {
            BfeObjectSecurityRelease(lpMem);
            BfeObjectSecurityRelease(qword_1800F5B10);
            v28 = (__int64 *)TlsGetValue(gBfeContextComponent);
            if ( v28 && (v29 = *v28) != 0 )
              v30 = *(_QWORD *)(v29 + 80);
            else
              v30 = 0;
            qword_1800F5B00 = v30;
            v31 = NextEntryHashTable;
            qword_1800F5B10 = NextEntryHashTable;
            lpMem = v9;
            if ( v9 )
            {
              ++*((_DWORD *)v9 + 6);
              v31 = qword_1800F5B10;
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
        if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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
0x180013640  push    rbp
0x180013642  push    rbx
0x180013643  push    rsi
0x180013644  push    rdi
0x180013645  push    r12
0x180013647  push    r13
0x180013649  push    r14
0x18001364b  push    r15
0x18001364d  lea     rbp, [rsp-17h]
0x180013652  sub     rsp, 0B8h
0x180013659  mov     rax, cs:__security_cookie
0x180013660  xor     rax, rsp
0x180013663  mov     [rbp+4Fh+var_50], rax
0x180013667  mov     r13, [rbp+4Fh+arg_20]
0x18001366b  xor     r15d, r15d
0x18001366e  mov     [rbp+4Fh+NewDescriptor], r15
0x180013672  mov     r14, r9
0x180013675  mov     esi, r8d
0x180013678  mov     rbx, rdx
0x18001367b  mov     rdi, rcx
0x18001367e  test    rdx, rdx
0x180013681  jnz     loc_180013733
0x180013687  test    r8d, r8d
0x18001368a  jnz     loc_180013733
0x180013690  mov     [rbp+4Fh+var_B0], 1
0x180013697  test    rcx, rcx
0x18001369a  jz      loc_180013AB6
0x1800136a0  lea     r12, [rcx-1Ch]
0x1800136a4  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x1800136aa  call    cs:__imp_TlsGetValue
0x1800136b1  nop     dword ptr [rax+rax+00h]
0x1800136b6  test    rax, rax
0x1800136b9  jz      loc_180013AAE
0x1800136bf  mov     rax, [rax]
0x1800136c2  test    rax, rax
0x1800136c5  jz      loc_180013AAE
0x1800136cb  mov     rcx, [rax+50h]
0x1800136cf  cmp     cs:qword_1800F5B00, rcx
0x1800136d6  jnz     short loc_18001373A
0x1800136d8  cmp     cs:lpMem, r12
0x1800136df  jnz     short loc_18001373A
0x1800136e1  mov     rax, cs:qword_1800F5B10
0x1800136e8  mov     r14, r15
0x1800136eb  test    rax, rax
0x1800136ee  jz      loc_180013AA6
0x1800136f4  inc     dword ptr [rax+18h]
0x1800136f7  mov     rax, cs:qword_1800F5B10
0x1800136fe  test    rax, rax
0x180013701  jz      loc_180013AA6
0x180013707  add     rax, 1Ch
0x18001370b  mov     [r13+0], rax
0x18001370f  mov     rax, r14
0x180013712  mov     rcx, [rbp+4Fh+var_50]
0x180013716  xor     rcx, rsp; StackCookie
0x180013719  call    __security_check_cookie
0x18001371e  add     rsp, 0B8h
0x180013725  pop     r15
0x180013727  pop     r14
0x180013729  pop     r13
0x18001372b  pop     r12
0x18001372d  pop     rdi
0x18001372e  pop     rsi
0x18001372f  pop     rbx
0x180013730  pop     rbp
0x180013731  retn
0x180013733  mov     r12, r15
0x180013736  mov     [rbp+4Fh+var_B0], r15d
0x18001373a  mov     eax, 7Bh ; '{'
0x18001373f  lea     r8, [rbp+4Fh+NewDescriptor]; NewDescriptor
0x180013743  mov     ecx, 3
0x180013748  test    r14, r14
0x18001374b  mov     rdx, rbx; CreatorDescriptor
0x18001374e  cmovnz  eax, ecx
0x180013751  lea     rcx, GenericMapping
0x180013758  mov     [rsp+0F0h+GenericMapping], rcx; GenericMapping
0x18001375d  xor     r9d, r9d; ObjectType
0x180013760  mov     [rsp+0F0h+Token], r14; Token
0x180013765  mov     rcx, rdi; ParentDescriptor
0x180013768  mov     [rsp+0F0h+AutoInheritFlags], eax; AutoInheritFlags
0x18001376c  mov     [rsp+0F0h+IsContainerObject], esi; IsContainerObject
0x180013770  call    cs:__imp_CreatePrivateObjectSecurityEx
0x180013777  nop     dword ptr [rax+rax+00h]
0x18001377c  test    eax, eax
0x18001377e  jz      loc_1800139D1
0x180013784  mov     rdi, [rbp+4Fh+NewDescriptor]
0x180013788  xorps   xmm0, xmm0
0x18001378b  xor     eax, eax
0x18001378d  mov     [rbp+4Fh+var_A8], r15
0x180013791  mov     rcx, rdi; SecurityDescriptor
0x180013794  mov     [rbp+4Fh+var_88], rax
0x180013798  movups  [rbp+4Fh+var_98], xmm0
0x18001379c  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800137a3  nop     dword ptr [rax+rax+00h]
0x1800137a8  mov     esi, eax
0x1800137aa  mov     rbx, r15
0x1800137ad  test    rdi, rdi
0x1800137b0  jz      loc_180013A9A
0x1800137b6  mov     ecx, r15d
0x1800137b9  test    eax, eax
0x1800137bb  jz      loc_180013A9A
0x1800137c1  nop     dword ptr [rax+00h]
0x1800137c5  nop     word ptr [rax+rax+00000000h]
0x1800137d0  imul    rbx, 25h ; '%'
0x1800137d4  mov     edx, ecx
0x1800137d6  inc     ecx
0x1800137d8  movzx   r8d, byte ptr [rdx+rdi]
0x1800137dd  add     rbx, r8
0x1800137e0  cmp     ecx, esi
0x1800137e2  jb      short loc_1800137D0
0x1800137e4  test    rbx, rbx
0x1800137e7  jz      loc_180013A9A
0x1800137ed  mov     rdx, rbx
0x1800137f0  lea     r8, [rbp+4Fh+var_98]
0x1800137f4  lea     rcx, qword_1800F5AD0
0x1800137fb  call    cs:__imp_RtlLookupEntryHashTable
0x180013802  nop     dword ptr [rax+rax+00h]
0x180013807  mov     r15, rax
0x18001380a  test    rax, rax
0x18001380d  jnz     loc_1800138E2
0x180013813  lea     ecx, [rsi+1Ch]; dwBytes
0x180013816  xor     edx, edx; dwFlags
0x180013818  lea     r8, [rbp+4Fh+var_A8]
0x18001381c  call    WfpMemAlloc
0x180013821  mov     r14, rax
0x180013824  test    rax, rax
0x180013827  jz      loc_180013ACC
0x18001382d  xor     r15d, r15d
0x180013830  mov     rcx, cs:WPP_GLOBAL_Control
0x180013837  lea     rdi, WPP_GLOBAL_Control
0x18001383e  lea     rbx, aBfeobjectsecur_4; "BfeObjectSecurityCreateInternal"
0x180013845  cmp     rcx, rdi
0x180013848  jz      short loc_180013871
0x18001384a  cmp     byte ptr [rcx+19h], 2
0x18001384e  jb      short loc_180013871
0x180013850  test    byte ptr [rcx+1Ch], 1
0x180013854  jz      short loc_180013871
0x180013856  mov     rcx, [rcx+10h]
0x18001385a  mov     edx, 1Ah
0x18001385f  mov     [rsp+0F0h+AutoInheritFlags], r14d
0x180013864  xor     r9d, r9d
0x180013867  mov     qword ptr [rsp+0F0h+IsContainerObject], rbx
0x18001386c  call    WPP_SF_Ssd
0x180013871  cmp     cs:gWfpLogUserModeErrors, r15d
0x180013878  jz      loc_18001392C
0x18001387e  test    cs:byte_1800F6115, 1
0x180013885  jz      loc_18001392C
0x18001388b  lea     rax, [rbp+4Fh+var_B0]
0x18001388f  mov     [rbp+4Fh+var_B0], r14d
0x180013893  mov     [rbp+4Fh+var_60], rax
0x180013897  lea     rdx, WFP_USERMODE_ERROR
0x18001389e  lea     rax, [rbp+4Fh+var_80]
0x1800138a2  mov     [rbp+4Fh+var_70], rbx
0x1800138a6  mov     r9d, 3
0x1800138ac  mov     qword ptr [rsp+0F0h+IsContainerObject], rax
0x1800138b1  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800138b8  mov     [rbp+4Fh+var_68], 20h ; ' '
0x1800138c0  mov     [rbp+4Fh+var_58], 4
0x1800138c8  call    McGenEventWrite_EtwEventWriteTransfer
0x1800138cd  lea     rcx, [rbp+4Fh+NewDescriptor]; ObjectDescriptor
0x1800138d1  call    cs:__imp_DestroyPrivateObjectSecurity
0x1800138d8  nop     dword ptr [rax+rax+00h]
0x1800138dd  jmp     loc_1800139FF
0x1800138e2  lea     rcx, [r15+1Ch]; SecurityDescriptor
0x1800138e6  mov     [rbp+4Fh+var_A8], r15
0x1800138ea  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800138f1  nop     dword ptr [rax+rax+00h]
0x1800138f6  cmp     eax, esi
0x1800138f8  jnz     loc_180013B14
0x1800138fe  mov     r8, rsi; Size
0x180013901  lea     rdx, [r15+1Ch]; Buf2
0x180013905  mov     rcx, rdi; Buf1
0x180013908  call    memcmp_0
0x18001390d  test    eax, eax
0x18001390f  jnz     loc_180013B14
0x180013915  xor     r14d, r14d
0x180013918  test    r15, r15
0x18001391b  jz      loc_180013813
0x180013921  inc     dword ptr [r15+18h]
0x180013925  lea     rdi, WPP_GLOBAL_Control
0x18001392c  lea     rcx, [rbp+4Fh+NewDescriptor]; ObjectDescriptor
0x180013930  call    cs:__imp_DestroyPrivateObjectSecurity
0x180013937  nop     dword ptr [rax+rax+00h]
0x18001393c  test    r14, r14
0x18001393f  jnz     loc_1800139FF
0x180013945  cmp     [rbp+4Fh+var_B0], r14d
0x180013949  jz      short loc_1800139BF
0x18001394b  mov     rcx, cs:lpMem; lpMem
0x180013952  call    BfeObjectSecurityRelease
0x180013957  mov     rcx, cs:qword_1800F5B10; lpMem
0x18001395e  call    BfeObjectSecurityRelease
0x180013963  mov     ecx, cs:gBfeContextComponent; dwTlsIndex
0x180013969  call    cs:__imp_TlsGetValue
0x180013970  nop     dword ptr [rax+rax+00h]
0x180013975  test    rax, rax
0x180013978  jz      loc_180013ABE
0x18001397e  mov     rax, [rax]
0x180013981  test    rax, rax
0x180013984  jz      loc_180013ABE
0x18001398a  mov     rcx, [rax+50h]
0x18001398e  mov     cs:qword_1800F5B00, rcx
0x180013995  mov     rax, r15
0x180013998  mov     cs:qword_1800F5B10, rax
0x18001399f  mov     cs:lpMem, r12
0x1800139a6  test    r12, r12
0x1800139a9  jz      short loc_1800139B7
0x1800139ab  inc     dword ptr [r12+18h]
0x1800139b0  mov     rax, cs:qword_1800F5B10
0x1800139b7  test    rax, rax
0x1800139ba  jz      short loc_1800139BF
0x1800139bc  inc     dword ptr [rax+18h]
0x1800139bf  test    r15, r15
0x1800139c2  jz      loc_180013AC5
0x1800139c8  lea     rax, [r15+1Ch]
0x1800139cc  jmp     loc_18001370B
0x1800139d1  call    cs:__imp_GetLastError
0x1800139d8  nop     dword ptr [rax+rax+00h]
0x1800139dd  mov     r8d, eax
0x1800139e0  lea     rdx, aCreateprivateo; "CreatePrivateObjectSecurityEx"
0x1800139e7  call    WfpReportSysErrorAsWinError
0x1800139ec  mov     r14, rax
0x1800139ef  test    rax, rax
0x1800139f2  jz      loc_180013712
0x1800139f8  lea     rdi, WPP_GLOBAL_Control
0x1800139ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a06  lea     rbx, aBfeobjectsecur_9; "BfeObjectSecurityCreate"
0x180013a0d  cmp     rcx, rdi
0x180013a10  jz      short loc_180013A39
0x180013a12  cmp     byte ptr [rcx+19h], 2
0x180013a16  jb      short loc_180013A39
0x180013a18  test    byte ptr [rcx+1Ch], 1
0x180013a1c  jz      short loc_180013A39
0x180013a1e  mov     rcx, [rcx+10h]
0x180013a22  mov     edx, 1Ah
0x180013a27  mov     [rsp+0F0h+AutoInheritFlags], r14d
0x180013a2c  xor     r9d, r9d
0x180013a2f  mov     qword ptr [rsp+0F0h+IsContainerObject], rbx
0x180013a34  call    WPP_SF_Ssd
0x180013a39  cmp     cs:gWfpLogUserModeErrors, 0
0x180013a40  jz      loc_18001370F
0x180013a46  test    cs:byte_1800F6115, 1
0x180013a4d  jz      loc_18001370F
0x180013a53  lea     rax, [rbp+4Fh+var_B0]
0x180013a57  mov     [rbp+4Fh+var_B0], r14d
0x180013a5b  mov     [rbp+4Fh+var_60], rax
0x180013a5f  lea     rdx, WFP_USERMODE_ERROR
0x180013a66  lea     rax, [rbp+4Fh+var_80]
0x180013a6a  mov     [rbp+4Fh+var_70], rbx
0x180013a6e  mov     r9d, 3
0x180013a74  mov     qword ptr [rsp+0F0h+IsContainerObject], rax
0x180013a79  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180013a80  mov     [rbp+4Fh+var_68], 18h
0x180013a88  mov     [rbp+4Fh+var_58], 4
0x180013a90  call    McGenEventWrite_EtwEventWriteTransfer
0x180013a95  jmp     loc_18001370F
0x180013a9a  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180013aa1  jmp     loc_1800137F0
0x180013aa6  mov     rax, r15
0x180013aa9  jmp     loc_18001370B
0x180013aae  mov     rcx, r15
0x180013ab1  jmp     loc_1800136CF
0x180013ab6  mov     r12, r15
0x180013ab9  jmp     loc_1800136A4
0x180013abe  xor     ecx, ecx
0x180013ac0  jmp     loc_18001398E
0x180013ac5  xor     eax, eax
0x180013ac7  jmp     loc_18001370B
0x180013acc  mov     r15, [rbp+4Fh+var_A8]
0x180013ad0  mov     r8, rsi; Size
0x180013ad3  mov     rdx, rdi; Src
0x180013ad6  mov     [r15+10h], rbx
0x180013ada  lea     rcx, [r15+1Ch]; void *
0x180013ade  mov     dword ptr [r15+18h], 0
0x180013ae6  call    memcpy_0
0x180013aeb  mov     rdx, r15
0x180013aee  lea     rcx, qword_1800F5AD0
0x180013af5  call    WfpHashtableInsert
0x180013afa  lea     rcx, qword_1800F5AD0
0x180013b01  call    WfpRestructureHashtable
0x180013b06  test    r15, r15
0x180013b09  jnz     loc_180013921
0x180013b0f  jmp     loc_180013925
0x180013b14  lea     rdx, [rbp+4Fh+var_98]
0x180013b18  lea     rcx, qword_1800F5AD0
0x180013b1f  call    cs:__imp_RtlGetNextEntryHashTable
0x180013b26  nop     dword ptr [rax+rax+00h]
0x180013b2b  mov     r15, rax
0x180013b2e  test    rax, rax
0x180013b31  jnz     loc_1800138E2
0x180013b37  jmp     loc_180013813
```

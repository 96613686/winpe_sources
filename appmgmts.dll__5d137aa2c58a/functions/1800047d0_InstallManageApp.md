# InstallManageApp

- ea: `0x1800047d0`
- end: `0x1800049ca`
- name: `InstallManageApp`
- size: `506`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800016d0`
- `0x1800047d0`
- `0x180005294`
- `0x180007410`
- `0x180007918`
- `0x18000d11c`
- `0x18000d734`
- `0x1800131d4`
- `0x18001b1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000483d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004855`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000483d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004855`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800049aa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800049aa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000482b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18000482b`

## pseudocode

```c
DWORD __fastcall InstallManageApp(__int64 *a1, const unsigned __int16 *a2, unsigned int a3, bool *a4)
{
  __int64 v7; // rcx
  DWORD LastError; // eax
  DWORD result; // eax
  CAppInfo *v10; // rcx
  unsigned int v11; // esi
  _QWORD *v12; // rcx
  __int64 v13; // rdi
  CAppInfo *v14; // rcx
  unsigned int v15; // eax
  struct _GUID v16; // [rsp+30h] [rbp-48h] BYREF

  *a4 = 0;
  v16 = 0;
  StringToGuid(a2, &v16);
  v7 = *a1;
  if ( *(_DWORD *)(*a1 + 396) == 1 || !*(_DWORD *)(v7 + 296) || ImpersonateLoggedOnUser(*(HANDLE *)(v7 + 264)) )
    goto LABEL_7;
  if ( *(_DWORD *)&gDebugLevel )
  {
    LastError = GetLastError();
    _DebugMsg(2, 0xBC4u, LastError);
  }
  result = GetLastError();
  if ( !result )
  {
LABEL_7:
    v10 = (CAppInfo *)a1[1];
    if ( *(_QWORD *)&v16.Data1 == *((_QWORD *)v10 + 3) && *(_QWORD *)v16.Data4 == *((_QWORD *)v10 + 4) )
    {
      *((_DWORD *)a1 + 4) = 1;
      v11 = CAppInfo::ProcessApplyActions(v10);
      if ( !v11 && *(_DWORD *)(*a1 + 392) && *(_DWORD *)(*a1 + 396) == 2 )
        v11 = CAppInfo::ProcessTransformConflicts((CAppInfo *)a1[1]);
    }
    else
    {
      v12 = (_QWORD *)*a1;
      v12[13] = *(_QWORD *)(*a1 + 96);
      v12[12] = v12[11];
      while ( 1 )
      {
        v13 = *(_QWORD *)(*a1 + 96);
        if ( v13 == *a1 + 80 || !v13 )
        {
          v11 = 1168;
          goto LABEL_24;
        }
        if ( *(_QWORD *)&v16.Data1 == *(_QWORD *)(v13 + 24) && *(_QWORD *)v16.Data4 == *(_QWORD *)(v13 + 32) )
          break;
        *(_QWORD *)(*a1 + 96) = *(_QWORD *)(v13 + 8);
      }
      v11 = 0;
      if ( *(_DWORD *)(v13 + 228) == 4 )
      {
        v14 = *(CAppInfo **)(*a1 + 96);
        *a4 = (*(_DWORD *)(v13 + 224) & 0x80) != 0;
        v15 = CAppInfo::Assign(v14, ((*(_DWORD *)(v13 + 224) & 1u) << 8) + 37, 1, 0);
        v11 = v15;
        if ( v15 )
          CEvents::Assign((CEvents *)(*a1 + 344), v15, (struct CAppInfo *)v13);
      }
      *(_DWORD *)(v13 + 300) = 1;
      CEvents::UpgradeAbort(
        (CEvents *)(*a1 + 344),
        a3,
        (struct CAppInfo *)a1[1],
        (struct CAppInfo *)v13,
        *((_DWORD *)a1 + 4) == 0);
    }
LABEL_24:
    if ( *(_DWORD *)(*a1 + 396) != 1 )
    {
      if ( *(_DWORD *)(*a1 + 296) )
        RevertToSelf();
    }
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x1800047d0  push    rbx
0x1800047d2  push    rbp
0x1800047d3  push    rsi
0x1800047d4  push    rdi
0x1800047d5  push    r14
0x1800047d7  sub     rsp, 50h
0x1800047db  mov     rax, cs:__security_cookie
0x1800047e2  xor     rax, rsp
0x1800047e5  mov     [rsp+78h+var_38], rax
0x1800047ea  mov     rax, rdx
0x1800047ed  mov     byte ptr [r9], 0
0x1800047f1  mov     rbx, rcx
0x1800047f4  lea     rdx, [rsp+78h+var_48]; struct _GUID *
0x1800047f9  xorps   xmm0, xmm0
0x1800047fc  mov     rcx, rax; unsigned __int16 *
0x1800047ff  mov     r14, r9
0x180004802  mov     ebp, r8d
0x180004805  movups  xmmword ptr [rsp+78h+var_48.Data1], xmm0
0x18000480a  call    ?StringToGuid@@YAXPEBGPEAU_GUID@@@Z; StringToGuid(ushort const *,_GUID *)
0x18000480f  mov     rcx, [rbx]
0x180004812  cmp     dword ptr [rcx+18Ch], 1
0x180004819  jz      short loc_180004863
0x18000481b  cmp     dword ptr [rcx+128h], 0
0x180004822  jz      short loc_180004863
0x180004824  mov     rcx, [rcx+108h]; hToken
0x18000482b  call    cs:__imp_ImpersonateLoggedOnUser
0x180004831  test    eax, eax
0x180004833  jnz     short loc_180004863
0x180004835  cmp     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x18000483b  jz      short loc_180004855
0x18000483d  call    cs:__imp_GetLastError
0x180004843  mov     edx, 0BC4h; unsigned int
0x180004848  mov     ecx, 2; unsigned int
0x18000484d  mov     r8d, eax
0x180004850  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180004855  call    cs:__imp_GetLastError
0x18000485b  test    eax, eax
0x18000485d  jnz     loc_1800049B2
0x180004863  mov     rcx, [rbx+8]; this
0x180004867  mov     rax, qword ptr [rsp+78h+var_48.Data1]
0x18000486c  cmp     rax, [rcx+18h]
0x180004870  jnz     short loc_1800048BF
0x180004872  mov     rax, qword ptr [rsp+78h+var_48.Data4]
0x180004877  cmp     rax, [rcx+20h]
0x18000487b  jnz     short loc_1800048BF
0x18000487d  mov     dword ptr [rbx+10h], 1
0x180004884  call    ?ProcessApplyActions@CAppInfo@@QEAAKXZ; CAppInfo::ProcessApplyActions(void)
0x180004889  mov     esi, eax
0x18000488b  test    eax, eax
0x18000488d  jnz     loc_180004995
0x180004893  mov     rax, [rbx]
0x180004896  cmp     [rax+188h], esi
0x18000489c  jz      loc_180004995
0x1800048a2  cmp     dword ptr [rax+18Ch], 2
0x1800048a9  jnz     loc_180004995
0x1800048af  mov     rcx, [rbx+8]; this
0x1800048b3  call    ?ProcessTransformConflicts@CAppInfo@@QEAAKXZ; CAppInfo::ProcessTransformConflicts(void)
0x1800048b8  mov     esi, eax
0x1800048ba  jmp     loc_180004995
0x1800048bf  mov     rcx, [rbx]
0x1800048c2  mov     rax, [rcx+60h]
0x1800048c6  mov     [rcx+68h], rax
0x1800048ca  mov     rax, [rcx+58h]
0x1800048ce  mov     [rcx+60h], rax
0x1800048d2  mov     rcx, [rbx]
0x1800048d5  add     rcx, 50h ; 'P'
0x1800048d9  mov     rdi, [rcx+10h]
0x1800048dd  cmp     rdi, rcx
0x1800048e0  jz      loc_180004990
0x1800048e6  test    rdi, rdi
0x1800048e9  jz      loc_180004990
0x1800048ef  mov     rax, qword ptr [rsp+78h+var_48.Data1]
0x1800048f4  cmp     rax, [rdi+18h]
0x1800048f8  jnz     short loc_180004905
0x1800048fa  mov     rax, qword ptr [rsp+78h+var_48.Data4]
0x1800048ff  cmp     rax, [rdi+20h]
0x180004903  jz      short loc_18000490F
0x180004905  mov     rax, [rdi+8]
0x180004909  mov     [rcx+10h], rax
0x18000490d  jmp     short loc_1800048D2
0x18000490f  xor     esi, esi
0x180004911  cmp     dword ptr [rdi+0E4h], 4
0x180004918  jnz     short loc_180004960
0x18000491a  mov     eax, [rdi+0E0h]
0x180004920  lea     r8d, [rsi+1]; int
0x180004924  shr     eax, 7
0x180004927  xor     r9d, r9d; int
0x18000492a  and     al, 1
0x18000492c  mov     rcx, rdi; this
0x18000492f  mov     [r14], al
0x180004932  mov     edx, [rdi+0E0h]
0x180004938  and     edx, 1
0x18000493b  shl     edx, 8
0x18000493e  add     edx, 25h ; '%'; unsigned int
0x180004941  call    ?Assign@CAppInfo@@QEAAKKHH@Z; CAppInfo::Assign(ulong,int,int)
0x180004946  mov     esi, eax
0x180004948  test    eax, eax
0x18000494a  jz      short loc_180004960
0x18000494c  mov     rcx, [rbx]
0x18000494f  mov     r8, rdi; struct CAppInfo *
0x180004952  add     rcx, 158h; this
0x180004959  mov     edx, eax; unsigned int
0x18000495b  call    ?Assign@CEvents@@QEAAXKPEAVCAppInfo@@@Z; CEvents::Assign(ulong,CAppInfo *)
0x180004960  xor     eax, eax
0x180004962  mov     dword ptr [rdi+12Ch], 1
0x18000496c  cmp     [rbx+10h], eax
0x18000496f  mov     r9, rdi; struct CAppInfo *
0x180004972  mov     rcx, [rbx]
0x180004975  mov     edx, ebp; unsigned int
0x180004977  mov     r8, [rbx+8]; struct CAppInfo *
0x18000497b  setz    al
0x18000497e  add     rcx, 158h; this
0x180004985  mov     [rsp+78h+var_58], eax; int
0x180004989  call    ?UpgradeAbort@CEvents@@QEAAXKPEAVCAppInfo@@0H@Z; CEvents::UpgradeAbort(ulong,CAppInfo *,CAppInfo *,int)
0x18000498e  jmp     short loc_180004995
0x180004990  mov     esi, 490h
0x180004995  mov     rax, [rbx]
0x180004998  cmp     dword ptr [rax+18Ch], 1
0x18000499f  jz      short loc_1800049B0
0x1800049a1  cmp     dword ptr [rax+128h], 0
0x1800049a8  jz      short loc_1800049B0
0x1800049aa  call    cs:__imp_RevertToSelf
0x1800049b0  mov     eax, esi
0x1800049b2  mov     rcx, [rsp+78h+var_38]
0x1800049b7  xor     rcx, rsp; StackCookie
0x1800049ba  call    __security_check_cookie
0x1800049bf  add     rsp, 50h
0x1800049c3  pop     r14
0x1800049c5  pop     rdi
0x1800049c6  pop     rsi
0x1800049c7  pop     rbp
0x1800049c8  pop     rbx
0x1800049c9  retn
```

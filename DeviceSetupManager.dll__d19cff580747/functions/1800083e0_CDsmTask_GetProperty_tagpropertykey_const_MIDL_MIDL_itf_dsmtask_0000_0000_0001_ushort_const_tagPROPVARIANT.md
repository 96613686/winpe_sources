# CDsmTask::GetProperty(_tagpropertykey const &,__MIDL___MIDL_itf_dsmtask_0000_0000_0001,ushort const *,tagPROPVARIANT *)

- ea: `0x1800083e0`
- end: `0x180008637`
- name: `?GetProperty@CDsmTask@@UEAAJAEBU_tagpropertykey@@W4__MIDL___MIDL_itf_dsmtask_0000_0000_0001@@PEBGPEAUtagPROPVARIANT@@@Z`
- size: `599`
- prototype: `int __high(const struct _tagpropertykey *, enum __MIDL___MIDL_itf_dsmtask_0000_0000_0001, const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800083e0`
- `0x180008640`
- `0x180008890`
- `0x18001af70`
- `0x18001b98a`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800084fd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800084fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008419`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180008419`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008608`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008608`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800084ba`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008540`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800084ba`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008540`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800084c7`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800084c7`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008462`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008462`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800085ca`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800085ca`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800085fe`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x1800085fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDsmTask::GetProperty(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3,
        const WCHAR *a4,
        struct tagPROPVARIANT *a5)
{
  _QWORD *v8; // rsi
  _QWORD *v9; // rbx
  __int64 v10; // rdi
  HRESULT ObjectProperties; // ebx
  __int64 v12; // rdi
  __int64 v13; // rax
  __int16 v14; // ax
  int v15; // edi
  RTL_SRWLOCK *Ptr; // rdx
  __int64 v17; // rcx
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-30h] BYREF
  BYTE *v20; // [rsp+60h] [rbp-20h]
  const WCHAR *v21; // [rsp+68h] [rbp-18h]

  AcquireSRWLockShared(a1 + 14);
  v8 = 0;
  v9 = *(PVOID *)((char *)&a1[15].Ptr + (a1[39].Ptr != 0 ? 0x30 : 0));
  while ( v9 )
  {
    v10 = v9[2];
    if ( a4 )
    {
      if ( !*(_QWORD *)v10 )
        goto LABEL_15;
      v9 = (_QWORD *)*v9;
      if ( !lstrcmpiW(a4, *(LPCWSTR *)v10) )
        goto LABEL_6;
    }
    else
    {
      if ( !*(_QWORD *)v10 )
      {
LABEL_6:
        v8 = *(_QWORD **)(v10 + 8);
        break;
      }
LABEL_15:
      v9 = (_QWORD *)*v9;
    }
  }
  ObjectProperties = -2147467259;
  while ( v8 )
  {
    v12 = v8[2];
    v13 = *(_QWORD *)a2 - *(_QWORD *)(v12 + 24);
    if ( *(_QWORD *)a2 == *(_QWORD *)(v12 + 24) )
      v13 = *(_QWORD *)(a2 + 8) - *(_QWORD *)(v12 + 32);
    if ( !v13 && *(_DWORD *)(a2 + 16) == *(_DWORD *)(v12 + 40) )
    {
      LOWORD(pvar[0]) = 0;
      PropVariantClear(pvar);
      ObjectProperties = PropVariantCopy(pvar, (const PROPVARIANT *)v12);
      if ( ObjectProperties >= 0 )
      {
        ObjectProperties = (HRESULT)pvar[1];
        v14 = (__int16)pvar[0];
      }
      else
      {
        v14 = 10;
        LOWORD(pvar[0]) = 10;
        LODWORD(pvar[1]) = ObjectProperties;
      }
      if ( v14 != 10 )
      {
        ObjectProperties = 0;
        goto LABEL_22;
      }
      if ( ObjectProperties >= 0 )
      {
LABEL_22:
        if ( a5 )
        {
          *(_OWORD *)&a5->vt = *(_OWORD *)pvar;
          a5->bstrblobVal.pData = v20;
          v15 = 0;
        }
        else
        {
          v15 = 22;
          *(_DWORD *)_o__errno(10) = 22;
          invalid_parameter_noinfo();
        }
        ATL::AtlCrtErrorCheck(v15);
        *(_OWORD *)pvar = 0;
        v20 = 0;
      }
      PropVariantClear(pvar);
      break;
    }
    v8 = (_QWORD *)*v8;
  }
  if ( ObjectProperties < 0 )
  {
    pvar[0] = 0;
    pvar[1] = 0;
    *(_OWORD *)pvar = *(_OWORD *)a2;
    v20 = (BYTE *)*(unsigned int *)(a2 + 16);
    v21 = a4;
    Ptr = (RTL_SRWLOCK *)a1[39].Ptr;
    if ( Ptr )
    {
      v17 = 3;
    }
    else
    {
      Ptr = a1 + 29;
      v17 = 2;
    }
    ObjectProperties = DevGetObjectProperties(v17, Ptr, 0);
  }
  ReleaseSRWLockShared(a1 + 14);
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x1800083e0  mov     [rsp-38h+arg_10], rbx
0x1800083e5  push    rbp
0x1800083e6  push    rsi
0x1800083e7  push    rdi
0x1800083e8  push    r12
0x1800083ea  push    r13
0x1800083ec  push    r14
0x1800083ee  push    r15
0x1800083f0  mov     rbp, rsp
0x1800083f3  sub     rsp, 80h
0x1800083fa  mov     rax, cs:__security_cookie
0x180008401  xor     rax, rsp
0x180008404  mov     [rbp+var_10], rax
0x180008408  mov     r15, r9
0x18000840b  mov     r14, rdx
0x18000840e  mov     r13, rcx
0x180008411  mov     r12, [rbp+arg_20]
0x180008415  add     rcx, 70h ; 'p'; SRWLock
0x180008419  call    cs:__imp_AcquireSRWLockShared
0x18000841f  xor     esi, esi
0x180008421  mov     rax, [r13+138h]
0x180008428  neg     rax
0x18000842b  sbb     rcx, rcx
0x18000842e  and     ecx, 30h
0x180008431  mov     rbx, [rcx+r13+78h]
0x180008436  test    rbx, rbx
0x180008439  jz      short loc_180008470
0x18000843b  mov     rax, [rbx]
0x18000843e  cmp     qword ptr [r13+138h], 0
0x180008446  jnz     short loc_18000844A
0x180008448  jmp     short $+2
0x18000844a  mov     rdi, [rbx+10h]
0x18000844e  test    r15, r15
0x180008451  jz      short loc_1800084A6
0x180008453  cmp     qword ptr [rdi], 0
0x180008457  jz      short loc_1800084AB
0x180008459  mov     rbx, rax
0x18000845c  mov     rdx, [rdi]; lpString2
0x18000845f  mov     rcx, r15; lpString1
0x180008462  call    cs:__imp_lstrcmpiW
0x180008468  test    eax, eax
0x18000846a  jnz     short loc_180008436
0x18000846c  mov     rsi, [rdi+8]
0x180008470  mov     ebx, 80004005h
0x180008475  test    rsi, rsi
0x180008478  jz      loc_180008546
0x18000847e  mov     rdi, [rsi+10h]
0x180008482  mov     rax, [r14]
0x180008485  sub     rax, [rdi+18h]
0x180008489  jnz     short loc_180008493
0x18000848b  mov     rax, [r14+8]
0x18000848f  sub     rax, [rdi+20h]
0x180008493  test    rax, rax
0x180008496  jnz     short loc_1800084A1
0x180008498  mov     eax, [rdi+28h]
0x18000849b  cmp     [r14+10h], eax
0x18000849f  jz      short loc_1800084B0
0x1800084a1  mov     rsi, [rsi]
0x1800084a4  jmp     short loc_180008475
0x1800084a6  cmp     r15, [rdi]
0x1800084a9  jz      short loc_18000846C
0x1800084ab  mov     rbx, rax
0x1800084ae  jmp     short loc_180008436
0x1800084b0  xor     eax, eax
0x1800084b2  mov     word ptr [rbp+pvar], ax
0x1800084b6  lea     rcx, [rbp+pvar]; pvar
0x1800084ba  call    cs:__imp_PropVariantClear
0x1800084c0  mov     rdx, rdi; pvarSrc
0x1800084c3  lea     rcx, [rbp+pvar]; pvarDest
0x1800084c7  call    cs:__imp_PropVariantCopy
0x1800084cd  mov     ebx, eax
0x1800084cf  mov     ecx, 0Ah
0x1800084d4  test    eax, eax
0x1800084d6  jns     short loc_1800084E4
0x1800084d8  movzx   eax, cx
0x1800084db  mov     word ptr [rbp+pvar], cx
0x1800084df  mov     dword ptr [rbp+pvar+8], ebx
0x1800084e2  jmp     short loc_1800084EB
0x1800084e4  mov     ebx, dword ptr [rbp+pvar+8]
0x1800084e7  movzx   eax, word ptr [rbp+pvar]
0x1800084eb  cmp     ax, cx
0x1800084ee  jz      short loc_1800084F4
0x1800084f0  xor     ebx, ebx
0x1800084f2  jmp     short loc_1800084F8
0x1800084f4  test    ebx, ebx
0x1800084f6  js      short loc_18000853C
0x1800084f8  test    r12, r12
0x1800084fb  jnz     short loc_180008511
0x1800084fd  call    cs:__imp__o__errno
0x180008503  lea     edi, [r12+16h]
0x180008508  mov     [rax], edi
0x18000850a  call    _invalid_parameter_noinfo
0x18000850f  jmp     short loc_180008528
0x180008511  movups  xmm0, xmmword ptr [rbp+pvar]
0x180008515  movups  xmmword ptr [r12], xmm0
0x18000851a  movsd   xmm1, [rbp+var_20]
0x18000851f  movsd   qword ptr [r12+10h], xmm1
0x180008526  xor     edi, edi
0x180008528  mov     ecx, edi; int
0x18000852a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000852f  xorps   xmm0, xmm0
0x180008532  xor     eax, eax
0x180008534  movups  xmmword ptr [rbp+pvar], xmm0
0x180008538  mov     [rbp+var_20], rax
0x18000853c  lea     rcx, [rbp+pvar]; pvar
0x180008540  call    cs:__imp_PropVariantClear
0x180008546  test    ebx, ebx
0x180008548  jns     loc_180008604
0x18000854e  mov     dword ptr [rbp+var_40], 0
0x180008555  mov     [rbp+var_38], 0
0x18000855d  mov     [rbp+pvar], 0
0x180008565  mov     [rbp+pvar+8], 0
0x18000856d  movups  xmm0, xmmword ptr [r14]
0x180008571  movdqu  xmmword ptr [rbp+pvar], xmm0
0x180008576  mov     eax, [r14+10h]
0x18000857a  mov     dword ptr [rbp+var_20], eax
0x18000857d  mov     dword ptr [rbp+var_20+4], 0
0x180008584  mov     [rbp+var_18], r15
0x180008588  mov     rdx, [r13+138h]
0x18000858f  lea     rax, [rbp+var_38]
0x180008593  mov     r9d, 1
0x180008599  xor     r8d, r8d
0x18000859c  mov     [rsp+80h+var_50], rax
0x1800085a1  lea     rax, [rbp+var_40]
0x1800085a5  mov     [rsp+80h+var_58], rax
0x1800085aa  lea     rax, [rbp+pvar]
0x1800085ae  mov     [rsp+80h+var_60], rax
0x1800085b3  test    rdx, rdx
0x1800085b6  jnz     short loc_1800085C5
0x1800085b8  lea     rdx, [r13+0E8h]
0x1800085bf  lea     ecx, [r9+1]
0x1800085c3  jmp     short loc_1800085CA
0x1800085c5  mov     ecx, 3
0x1800085ca  call    cs:__imp_DevGetObjectProperties
0x1800085d0  mov     ebx, eax
0x1800085d2  test    eax, eax
0x1800085d4  js      short loc_180008604
0x1800085d6  mov     ecx, dword ptr [rbp+var_40]; this
0x1800085d9  mov     rdx, [rbp+var_38]; struct _DEVPROPERTY *
0x1800085dd  cmp     ecx, 1
0x1800085e0  jnz     short loc_1800085F9
0x1800085e2  cmp     dword ptr [rdx+20h], 2
0x1800085e6  jb      short loc_1800085F9
0x1800085e8  mov     r8, r12; struct tagPROPVARIANT *
0x1800085eb  call    ?_DevPropToPropVariant@CDsmPropertyCache@@AEAAJPEBU_DEVPROPERTY@@PEAUtagPROPVARIANT@@@Z; CDsmPropertyCache::_DevPropToPropVariant(_DEVPROPERTY const *,tagPROPVARIANT *)
0x1800085f0  mov     ebx, eax
0x1800085f2  mov     ecx, dword ptr [rbp+var_40]
0x1800085f5  mov     rdx, [rbp+var_38]
0x1800085f9  test    rdx, rdx
0x1800085fc  jz      short loc_180008604
0x1800085fe  call    cs:__imp_DevFreeObjectProperties
0x180008604  lea     rcx, [r13+70h]; SRWLock
0x180008608  call    cs:__imp_ReleaseSRWLockShared
0x18000860e  mov     eax, ebx
0x180008610  mov     rcx, [rbp+var_10]
0x180008614  xor     rcx, rsp; StackCookie
0x180008617  call    __security_check_cookie
0x18000861c  mov     rbx, [rsp+80h+arg_10]
0x180008624  add     rsp, 80h
0x18000862b  pop     r15
0x18000862d  pop     r14
0x18000862f  pop     r13
0x180008631  pop     r12
0x180008633  pop     rdi
0x180008634  pop     rsi
0x180008635  pop     rbp
0x180008636  retn
```

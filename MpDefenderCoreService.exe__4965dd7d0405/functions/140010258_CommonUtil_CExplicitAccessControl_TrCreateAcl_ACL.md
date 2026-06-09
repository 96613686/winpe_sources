# CommonUtil::CExplicitAccessControl::TrCreateAcl(_ACL *)

- ea: `0x140010258`
- end: `0x1400103fc`
- name: `?TrCreateAcl@CExplicitAccessControl@CommonUtil@@QEAA?AV?$AutoRef@UIWinSecurityAcl@CommonUtil@@@2@PEAU_ACL@@@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400100c0`

## callees

- `0x14000bf54`
- `0x140010258`
- `0x140010648`
- `0x14003a0f4`
- `0x14003a5c0`
- `0x14007d210`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140010371`
- `KERNEL32!LocalFree` at `0x14001038c`
- `KERNEL32!LocalFree` at `0x140010371`
- `KERNEL32!LocalFree` at `0x14001038c`
- `ADVAPI32!SetEntriesInAclW` at `0x140010322`
- `ADVAPI32!SetEntriesInAclW` at `0x140010322`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct _ACL **__fastcall CommonUtil::CExplicitAccessControl::TrCreateAcl(__int64 a1, struct _ACL **a2, struct _ACL *a3)
{
  struct _EXPLICIT_ACCESS_W **v4; // rax
  struct _EXPLICIT_ACCESS_W *v5; // rcx
  int EmptyAcl; // eax
  int v7; // edx
  _OWORD *v8; // rax
  struct _EXPLICIT_ACCESS_W *v9; // r10
  unsigned __int64 v10; // rcx
  signed int v11; // eax
  int v12; // edx
  _QWORD *v13; // rbx
  PACL v14; // rsi
  PACL v15; // rcx
  unsigned int v17; // ebx
  struct _ACL **v18; // [rsp+20h] [rbp-48h] BYREF
  void *v19; // [rsp+30h] [rbp-38h]
  PACL NewAcl; // [rsp+38h] [rbp-30h] BYREF

  v18 = a2;
  v4 = (struct _EXPLICIT_ACCESS_W **)(a1 + 24);
  v5 = *(struct _EXPLICIT_ACCESS_W **)(a1 + 32);
  if ( *v4 != v5 || a3 )
  {
    NewAcl = 0;
    v9 = *v4;
    if ( *v4 == v5 )
      v9 = (struct _EXPLICIT_ACCESS_W *)v4;
    v10 = (__int64)((unsigned __int128)(((char *)v5 - (char *)*v4) * (__int128)0x2AAAAAAAAAAAAAABLL) >> 64) >> 3;
    v11 = SetEntriesInAclW((v10 >> 63) + v10, v9, a3, &NewAcl);
    if ( v11 )
    {
      v17 = (unsigned __int16)v11 | 0x80070000;
      if ( v11 <= 0 )
        v17 = v11;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids, v17);
      CommonUtil::CommonThrowHr((CommonUtil *)v17, v12);
    }
    v13 = operator new(0x18u);
    v19 = v13;
    *((_DWORD *)v13 + 2) = 0;
    *v13 = &CommonUtil::CWinSecurityAclAlloc<CommonUtil::CAutoLocalPtr<_ACL *>>::`vftable';
    v13[2] = 0;
    v14 = NewAcl;
    NewAcl = 0;
    v15 = (PACL)v13[2];
    if ( v15 != v14 )
    {
      if ( v15 )
        LocalFree(v15);
      v13[2] = v14;
    }
    _InterlockedIncrement((volatile signed __int32 *)v13 + 2);
    *a2 = (struct _ACL *)v13;
    if ( NewAcl )
      LocalFree(NewAcl);
  }
  else
  {
    v18 = 0;
    EmptyAcl = CommonUtil::UtilCreateEmptyAcl((CommonUtil *)&v18, a2);
    if ( EmptyAcl < 0 )
    {
      _mm_lfence();
      CommonUtil::CommonThrowHr((CommonUtil *)(unsigned int)EmptyAcl, v7);
    }
    v8 = operator new(0x18u);
    v19 = v8;
    *v8 = 0;
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &CommonUtil::CWinSecurityAclAlloc<CommonUtil::CAutoUniquePtr<_ACL,void>>::`vftable';
    *((_QWORD *)v8 + 2) = 0;
    if ( v18 )
      *((_QWORD *)v8 + 2) = v18;
    _InterlockedIncrement((volatile signed __int32 *)v8 + 2);
    *a2 = (struct _ACL *)v8;
  }
  return a2;
}

```

## disassembly

```asm
0x140010258  push    rbx
0x14001025a  push    rsi
0x14001025b  push    rdi
0x14001025c  sub     rsp, 50h
0x140010260  mov     rax, cs:__security_cookie
0x140010267  xor     rax, rsp
0x14001026a  mov     [rsp+68h+var_28], rax
0x14001026f  mov     rdi, rdx
0x140010272  mov     [rsp+68h+var_48], rdx
0x140010277  lea     rax, [rcx+18h]
0x14001027b  mov     rcx, [rax+8]
0x14001027f  cmp     [rax], rcx
0x140010282  jnz     short loc_1400102E6
0x140010284  test    r8, r8
0x140010287  jnz     short loc_1400102E6
0x140010289  mov     [rsp+68h+var_48], r8
0x14001028e  lea     rcx, [rsp+68h+var_48]; this
0x140010293  call    ?UtilCreateEmptyAcl@CommonUtil@@YAJPEAPEAU_ACL@@@Z; CommonUtil::UtilCreateEmptyAcl(_ACL * *)
0x140010298  test    eax, eax
0x14001029a  js      loc_1400103F1
0x1400102a0  mov     ecx, 18h; Size
0x1400102a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400102aa  mov     [rsp+68h+var_38], rax
0x1400102af  xorps   xmm0, xmm0
0x1400102b2  xor     ecx, ecx
0x1400102b4  movups  xmmword ptr [rax], xmm0
0x1400102b7  mov     [rax+8], ecx
0x1400102ba  lea     rcx, ??_7?$CWinSecurityAclAlloc@V?$CAutoUniquePtr@U_ACL@@X@CommonUtil@@@CommonUtil@@6B@; const CommonUtil::CWinSecurityAclAlloc<CommonUtil::CAutoUniquePtr<_ACL,void>>::`vftable'
0x1400102c1  mov     [rax], rcx
0x1400102c4  mov     qword ptr [rax+10h], 0
0x1400102cc  mov     rcx, [rsp+68h+var_48]
0x1400102d1  test    rcx, rcx
0x1400102d4  jz      short loc_1400102DA
0x1400102d6  mov     [rax+10h], rcx
0x1400102da  lock inc dword ptr [rax+8]
0x1400102de  mov     [rdi], rax
0x1400102e1  jmp     loc_140010392
0x1400102e6  mov     [rsp+68h+NewAcl], 0
0x1400102ef  mov     r10, [rax]
0x1400102f2  cmp     r10, rcx
0x1400102f5  cmovz   r10, rax
0x1400102f9  sub     rcx, [rax]
0x1400102fc  mov     rax, 2AAAAAAAAAAAAAABh
0x140010306  imul    rcx
0x140010309  mov     rcx, rdx
0x14001030c  sar     rcx, 3
0x140010310  mov     rax, rcx
0x140010313  shr     rax, 3Fh
0x140010317  add     rcx, rax; cCountOfExplicitEntries
0x14001031a  lea     r9, [rsp+68h+NewAcl]; NewAcl
0x14001031f  mov     rdx, r10; pListOfExplicitEntries
0x140010322  call    cs:__imp_SetEntriesInAclW
0x140010328  test    eax, eax
0x14001032a  jnz     short loc_1400103AA
0x14001032c  lea     ecx, [rax+18h]; Size
0x14001032f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010334  mov     rbx, rax
0x140010337  mov     [rsp+68h+var_38], rax
0x14001033c  mov     dword ptr [rax+8], 0
0x140010343  lea     rax, ??_7?$CWinSecurityAclAlloc@U?$CAutoLocalPtr@PEAU_ACL@@@CommonUtil@@@CommonUtil@@6B@; const CommonUtil::CWinSecurityAclAlloc<CommonUtil::CAutoLocalPtr<_ACL *>>::`vftable'
0x14001034a  mov     [rbx], rax
0x14001034d  mov     qword ptr [rbx+10h], 0
0x140010355  mov     rsi, [rsp+68h+NewAcl]
0x14001035a  mov     [rsp+68h+NewAcl], 0
0x140010363  mov     rcx, [rbx+10h]; hMem
0x140010367  cmp     rcx, rsi
0x14001036a  jz      short loc_14001037B
0x14001036c  test    rcx, rcx
0x14001036f  jz      short loc_140010377
0x140010371  call    cs:__imp_LocalFree
0x140010377  mov     [rbx+10h], rsi
0x14001037b  lock inc dword ptr [rbx+8]
0x14001037f  mov     [rdi], rbx
0x140010382  mov     rcx, [rsp+68h+NewAcl]; hMem
0x140010387  test    rcx, rcx
0x14001038a  jz      short loc_140010392
0x14001038c  call    cs:__imp_LocalFree
0x140010392  mov     rax, rdi
0x140010395  mov     rcx, [rsp+68h+var_28]
0x14001039a  xor     rcx, rsp; StackCookie
0x14001039d  call    __security_check_cookie
0x1400103a2  add     rsp, 50h
0x1400103a6  pop     rdi
0x1400103a7  pop     rsi
0x1400103a8  pop     rbx
0x1400103a9  retn
0x1400103aa  movzx   ebx, ax
0x1400103ad  or      ebx, 80070000h
0x1400103b3  test    eax, eax
0x1400103b5  cmovle  ebx, eax
0x1400103b8  lea     rax, WPP_GLOBAL_Control
0x1400103bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103c6  cmp     rcx, rax
0x1400103c9  jz      short loc_1400103E9
0x1400103cb  test    byte ptr [rcx+1Ch], 1
0x1400103cf  jz      short loc_1400103E9
0x1400103d1  mov     edx, 0Bh
0x1400103d6  mov     r9d, ebx
0x1400103d9  lea     r8, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids
0x1400103e0  mov     rcx, [rcx+10h]
0x1400103e4  call    WPP_SF_d
0x1400103e9  mov     ecx, ebx; this
0x1400103eb  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
0x1400103f1  lfence
0x1400103f4  mov     ecx, eax; this
0x1400103f6  call    ?CommonThrowHr@CommonUtil@@YAXJ@Z; CommonUtil::CommonThrowHr(long)
```

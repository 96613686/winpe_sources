# Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *)

- ea: `0x180014e44`
- end: `0x1800150e6`
- name: `?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBG@Z`
- size: `674`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014d00`

## callees

- `0x1800056c8`
- `0x18000d6e0`
- `0x1800130a8`
- `0x180013eb8`
- `0x180014e44`
- `0x1800150e8`
- `0x1800262c4`
- `0x1800268f4`
- `0x180027910`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180015015`
- `msvcrt!wcsrchr` at `0x180015026`
- `msvcrt!wcsrchr` at `0x180015015`
- `msvcrt!wcsrchr` at `0x180015026`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        XPerf::Internal *a2)
{
  void **v4; // r13
  unsigned int *v5; // r8
  void **v6; // r12
  union _CVDD *v7; // r9
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // ebx
  unsigned int v12; // edi
  unsigned int v14; // eax
  const struct _RSDS *v15; // r14
  unsigned int v16; // eax
  unsigned __int64 v17; // rcx
  _BYTE *v18; // rax
  unsigned int v19; // eax
  unsigned __int16 *v20; // rbx
  wchar_t *v21; // rdi
  wchar_t *v22; // rax
  unsigned __int16 *v23; // rbx
  unsigned __int16 *v24[2]; // [rsp+30h] [rbp-10h] BYREF
  bool v25; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v26; // [rsp+90h] [rbp+50h] BYREF
  unsigned int v27; // [rsp+98h] [rbp+58h]

  v24[1] = (unsigned __int16 *)-2LL;
  v26 = *((_DWORD *)this + 46);
  v4 = (void **)((char *)this + 192);
  v5 = (unsigned int *)*((_QWORD *)this + 24);
  if ( !v5 )
    return 2147942414LL;
  v6 = (void **)((char *)this + 200);
  v7 = (union _CVDD *)*((_QWORD *)this + 25);
  if ( !v7 )
    return 2147942414LL;
  v8 = CvDbgInfoFromImage(a2, &v26, v5, v7, (unsigned int)&v25);
  v11 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2146893023 )
      goto LABEL_8;
    *((_DWORD *)this + 46) = 0;
    operator delete(*v4);
    *v4 = 0;
    operator delete(*v6);
    *v6 = 0;
    v12 = v26;
    if ( ATL::CAutoVectorPtr<_CVDD>::Allocate(v4, v26) && ATL::CAutoVectorPtr<unsigned long>::Allocate(v6, v12) )
    {
      *((_DWORD *)this + 46) = v12;
      v11 = CvDbgInfoFromImage(a2, &v26, (unsigned int *)*v4, (union _CVDD *)*v6, (unsigned int)&v25);
LABEL_8:
      if ( v11 < 0 )
      {
        if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
          Template_zq(v10, v9, (const wchar_t *)a2, v11);
        return (unsigned int)v11;
      }
      goto LABEL_12;
    }
    return 2147942414LL;
  }
LABEL_12:
  v14 = 0;
  v27 = 0;
  if ( !v26 )
    return 0;
  while ( 1 )
  {
    v15 = (const struct _RSDS *)((char *)*v4 + 1576 * v14);
    v16 = *((_DWORD *)*v6 + v14);
    if ( v16 <= 0x18 || *(_DWORD *)v15 != 1396986706 )
      goto LABEL_29;
    v17 = v16 - 24;
    v18 = (char *)v15 + 24;
    if ( v15 == (const struct _RSDS *)-24LL || v17 > 0x7FFFFFFF )
    {
      v19 = -2147024809;
    }
    else
    {
      for ( ; v17; --v17 )
      {
        if ( !*v18 )
          break;
        ++v18;
      }
      v19 = v17 == 0 ? 0x80070057 : 0;
    }
    if ( v19
      || (int)Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
                this,
                *((char **)this + 8),
                (const unsigned __int16 *)a2,
                v15,
                v25) >= 0 )
    {
      goto LABEL_29;
    }
    v20 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
    v24[0] = v20;
    v21 = wcsrchr((const wchar_t *)a2, 0x2Fu);
    v22 = wcsrchr((const wchar_t *)a2, 0x5Cu);
    if ( v21 > v22 )
      v22 = v21;
    if ( !v22 )
      break;
    ATL::CSimpleStringT<unsigned short,0>::SetString((__int64 *)v24, a2, ((char *)v22 - (char *)a2) >> 1);
    v23 = v24[0];
    Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(
      this,
      (char *)v24[0],
      (const unsigned __int16 *)a2,
      v15,
      v25);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 - 3) + 8LL))(*((_QWORD *)v23 - 3));
LABEL_29:
    v14 = v27 + 1;
    v27 = v14;
    if ( v14 >= v26 )
      return 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v20 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v20 - 3) + 8LL))(*((_QWORD *)v20 - 3));
  return 1;
}

```

## disassembly

```asm
0x180014e44  mov     r11, rsp
0x180014e47  push    rbp
0x180014e48  push    rsi
0x180014e49  push    rdi
0x180014e4a  push    r12
0x180014e4c  push    r13
0x180014e4e  push    r14
0x180014e50  push    r15
0x180014e52  mov     rbp, rsp
0x180014e55  sub     rsp, 40h
0x180014e59  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x180014e61  mov     [r11+10h], rbx
0x180014e65  mov     r15, rdx
0x180014e68  mov     rsi, rcx
0x180014e6b  mov     eax, [rcx+0B8h]
0x180014e71  mov     [rbp+arg_10], eax
0x180014e74  lea     r13, [rcx+0C0h]
0x180014e7b  mov     r8, [r13+0]; unsigned int *
0x180014e7f  test    r8, r8
0x180014e82  jz      loc_1800150C9
0x180014e88  lea     r12, [rcx+0C8h]
0x180014e8f  mov     r9, [r12]; union _CVDD *
0x180014e93  test    r9, r9
0x180014e96  jz      loc_1800150C9
0x180014e9c  lea     rax, [rbp+arg_0]
0x180014ea0  mov     [r11-58h], rax
0x180014ea4  lea     rdx, [rbp+arg_10]; unsigned int *
0x180014ea8  mov     rcx, r15; this
0x180014eab  call    CvDbgInfoFromImage
0x180014eb0  mov     ebx, eax
0x180014eb2  test    eax, eax
0x180014eb4  jns     loc_180014F4F
0x180014eba  cmp     eax, 80090321h
0x180014ebf  jnz     short loc_180014F30
0x180014ec1  and     dword ptr [rsi+0B8h], 0
0x180014ec8  mov     rcx, [r13+0]; Block
0x180014ecc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014ed1  and     qword ptr [r13+0], 0
0x180014ed6  mov     rcx, [r12]; Block
0x180014eda  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014edf  and     qword ptr [r12], 0
0x180014ee4  mov     edi, [rbp+arg_10]
0x180014ee7  mov     edx, edi
0x180014ee9  mov     rcx, r13
0x180014eec  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x180014ef1  test    al, al
0x180014ef3  jz      loc_1800150C9
0x180014ef9  mov     edx, edi
0x180014efb  mov     rcx, r12
0x180014efe  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180014f03  test    al, al
0x180014f05  jz      loc_1800150C9
0x180014f0b  mov     [rsi+0B8h], edi
0x180014f11  lea     rax, [rbp+arg_0]
0x180014f15  mov     qword ptr [rsp+40h+var_20], rax; unsigned int
0x180014f1a  mov     r9, [r12]; union _CVDD *
0x180014f1e  mov     r8, [r13+0]; unsigned int *
0x180014f22  lea     rdx, [rbp+arg_10]; unsigned int *
0x180014f26  mov     rcx, r15; this
0x180014f29  call    CvDbgInfoFromImage
0x180014f2e  mov     ebx, eax
0x180014f30  test    ebx, ebx
0x180014f32  jns     short loc_180014F4F
0x180014f34  test    cs:Microsoft_Windows_XPerfCoreEnableBits, 1
0x180014f3b  jz      short loc_180014F48
0x180014f3d  mov     r9d, ebx
0x180014f40  mov     r8, r15
0x180014f43  call    Template_zq
0x180014f48  mov     eax, ebx
0x180014f4a  jmp     loc_1800150CE
0x180014f4f  xor     eax, eax
0x180014f51  mov     [rbp+arg_18], eax
0x180014f54  cmp     [rbp+arg_10], eax
0x180014f57  jbe     loc_1800150C5
0x180014f5d  mov     ecx, eax
0x180014f5f  imul    r14, rcx, 628h
0x180014f66  add     r14, [r13+0]
0x180014f6a  mov     rax, [r12]
0x180014f6e  mov     eax, [rax+rcx*4]
0x180014f71  cmp     eax, 18h
0x180014f74  jbe     loc_18001508B
0x180014f7a  cmp     dword ptr [r14], 53445352h
0x180014f81  jnz     loc_18001508B
0x180014f87  add     eax, 0FFFFFFE8h
0x180014f8a  mov     ecx, eax
0x180014f8c  lea     rax, [r14+18h]
0x180014f90  test    rax, rax
0x180014f93  jz      short loc_180014FBF
0x180014f95  cmp     rcx, 7FFFFFFFh
0x180014f9c  ja      short loc_180014FBF
0x180014f9e  test    rcx, rcx
0x180014fa1  jz      short loc_180014FB1
0x180014fa3  cmp     byte ptr [rax], 0
0x180014fa6  jz      short loc_180014FB1
0x180014fa8  inc     rax
0x180014fab  sub     rcx, 1
0x180014faf  jnz     short loc_180014FA3
0x180014fb1  neg     rcx
0x180014fb4  sbb     eax, eax
0x180014fb6  not     eax
0x180014fb8  and     eax, 80070057h
0x180014fbd  jmp     short loc_180014FC4
0x180014fbf  mov     eax, 80070057h
0x180014fc4  test    eax, eax
0x180014fc6  jnz     loc_18001508B
0x180014fcc  mov     al, [rbp+arg_0]
0x180014fcf  mov     [rsp+40h+var_20], al; bool
0x180014fd3  mov     r9, r14; struct _RSDS *
0x180014fd6  mov     r8, r15; unsigned __int16 *
0x180014fd9  mov     rdx, [rsi+40h]; unsigned __int16 *
0x180014fdd  mov     rcx, rsi; this
0x180014fe0  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x180014fe5  test    eax, eax
0x180014fe7  jns     loc_18001508B
0x180014fed  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014ff4  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180014ffb  mov     rax, [rax+18h]
0x180014fff  call    cs:__guard_dispatch_icall_fptr
0x180015005  lea     rbx, [rax+18h]
0x180015009  mov     [rbp+var_10], rbx
0x18001500d  mov     edx, 2Fh ; '/'; Ch
0x180015012  mov     rcx, r15; Str
0x180015015  call    cs:__imp_wcsrchr
0x18001501b  mov     rdi, rax
0x18001501e  mov     edx, 5Ch ; '\'; Ch
0x180015023  mov     rcx, r15; Str
0x180015026  call    cs:__imp_wcsrchr
0x18001502c  cmp     rdi, rax
0x18001502f  cmova   rax, rdi
0x180015033  test    rax, rax
0x180015036  jz      short loc_18001509D
0x180015038  sub     rax, r15
0x18001503b  sar     rax, 1
0x18001503e  mov     r8d, eax
0x180015041  mov     rdx, r15
0x180015044  lea     rcx, [rbp+var_10]
0x180015048  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001504d  mov     al, [rbp+arg_0]
0x180015050  mov     [rsp+40h+var_20], al; bool
0x180015054  mov     r9, r14; struct _RSDS *
0x180015057  mov     r8, r15; unsigned __int16 *
0x18001505a  mov     rbx, [rbp+var_10]
0x18001505e  mov     rdx, rbx; unsigned __int16 *
0x180015061  mov     rcx, rsi; this
0x180015064  call    ?CreateNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBG0AEBU_RSDS@@_N@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreateNGenPdb(ushort const *,ushort const *,_RSDS const &,bool)
0x180015069  nop
0x18001506a  lea     rdx, [rbx-18h]
0x18001506e  or      eax, 0FFFFFFFFh
0x180015071  lock xadd [rdx+10h], eax
0x180015076  sub     eax, 1
0x180015079  jg      short loc_18001508B
0x18001507b  mov     rcx, [rdx]
0x18001507e  mov     rax, [rcx]
0x180015081  mov     rax, [rax+8]
0x180015085  call    cs:__guard_dispatch_icall_fptr
0x18001508b  mov     eax, [rbp+arg_18]
0x18001508e  inc     eax
0x180015090  mov     [rbp+arg_18], eax
0x180015093  cmp     eax, [rbp+arg_10]
0x180015096  jnb     short loc_1800150C5
0x180015098  jmp     loc_180014F5D
0x18001509d  lea     rdx, [rbx-18h]
0x1800150a1  or      ecx, 0FFFFFFFFh
0x1800150a4  lock xadd [rdx+10h], ecx
0x1800150a9  sub     ecx, 1
0x1800150ac  jg      short loc_1800150BE
0x1800150ae  mov     rcx, [rdx]
0x1800150b1  mov     r8, [rcx]
0x1800150b4  mov     rax, [r8+8]
0x1800150b8  call    cs:__guard_dispatch_icall_fptr
0x1800150be  mov     eax, 1
0x1800150c3  jmp     short loc_1800150CE
0x1800150c5  xor     eax, eax
0x1800150c7  jmp     short loc_1800150CE
0x1800150c9  mov     eax, 8007000Eh
0x1800150ce  mov     rbx, [rsp+40h+arg_8]
0x1800150d6  add     rsp, 40h
0x1800150da  pop     r15
0x1800150dc  pop     r14
0x1800150de  pop     r13
0x1800150e0  pop     r12
0x1800150e2  pop     rdi
0x1800150e3  pop     rsi
0x1800150e4  pop     rbp
0x1800150e5  retn
```

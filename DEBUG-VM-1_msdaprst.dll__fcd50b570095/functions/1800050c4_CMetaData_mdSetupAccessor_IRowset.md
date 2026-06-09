# CMetaData::mdSetupAccessor(IRowset *)

- ea: `0x1800050c4`
- end: `0x180005467`
- name: `?mdSetupAccessor@CMetaData@@AEAA_KPEAUIRowset@@@Z`
- size: `931`
- prototype: `unsigned __int64 __fastcall(CMetaData *__hidden this, struct IRowset *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x1800030c4`

## callees

- `0x180001d94`
- `0x18000261c`
- `0x180002650`
- `0x18000266c`
- `0x1800027c0`
- `0x1800050c4`
- `0x180005470`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e060`
- `0x18002e120`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000541c`
- `ole32!CoTaskMemFree` at `0x180005427`
- `ole32!CoTaskMemFree` at `0x18000541c`
- `ole32!CoTaskMemFree` at `0x180005427`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMetaData::mdSetupAccessor(CMetaData *this, struct IRowset *a2)
{
  void *v3; // rcx
  __int64 v4; // rbx
  int v5; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // ebx
  unsigned __int64 v9; // rcx
  __int64 v10; // rax
  void *v11; // rsp
  LPVOID *v12; // r12
  unsigned int v13; // eax
  unsigned __int128 v14; // rax
  unsigned __int64 v15; // kr00_8
  __int64 v16; // rcx
  unsigned int v17; // r14d
  unsigned int v18; // r15d
  LPVOID *v19; // rbx
  int v20; // eax
  int v21; // ebx
  int v22; // eax
  int v23; // ebx
  LPVOID v25; // [rsp+40h] [rbp+0h] BYREF
  unsigned __int64 v26; // [rsp+48h] [rbp+8h] BYREF
  __int64 v27; // [rsp+50h] [rbp+10h] BYREF
  __int64 v28; // [rsp+58h] [rbp+18h] BYREF
  LPVOID *v29; // [rsp+60h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+28h] BYREF
  __int64 v31; // [rsp+70h] [rbp+30h] BYREF
  tagDBCOLUMNINFO v32; // [rsp+80h] [rbp+40h] BYREF

  v28 = 0;
  v27 = 0;
  v26 = 0;
  v25 = 0;
  v3 = 0;
  pv = 0;
  v4 = 0;
  v31 = 0;
  if ( a2 )
  {
    v5 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IColumnsInfo,
           &v28);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048438[0] )
          bidTraceW(off_1800481B8[0], 675840, off_180048438[0], (unsigned int)v5, 660);
      }
      ThrowHR(v6);
    }
    v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v28 + 24LL))(
           v28,
           &v26,
           &v25,
           &pv);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048430[0] )
        bidTraceW(off_1800481B8[0], 676864, off_180048430[0], (unsigned int)v7, 661);
      ThrowHR(v8);
    }
    v29 = 0;
    if ( (unsigned int)DownsizeToULONGThrow<unsigned __int64>(v26) > 0xB )
    {
      v13 = DownsizeToULONGThrow<unsigned __int64>(v26);
      v15 = v13;
      v14 = v13 * (unsigned __int128)0x58uLL;
      if ( !is_mul_ok(v15, 0x58u) )
        LODWORD(v14) = -1;
      v12 = (LPVOID *)MMMAlloc(v14, DWORD2(v14));
      v29 = v12;
    }
    else
    {
      v9 = 88LL * (unsigned int)DownsizeToULONGThrow<unsigned __int64>(v26);
      v10 = v9 + 15;
      if ( v9 + 15 < v9 )
        v10 = 0xFFFFFFFFFFFFFF0LL;
      v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
      v12 = &v25;
    }
    OnNullThrowOOM(v12);
    v17 = 0;
    v18 = 0;
    if ( v26 )
    {
      do
      {
        v32 = *(tagDBCOLUMNINFO *)((_BYTE *)v25 + v18);
        v19 = &v12[11 * v17];
        if ( (unsigned int)CMetaData::mdSetupColRSDataBuffer((CMetaData *)v16, (struct tagDBBINDING *)v19, &v32) )
        {
          *v19 = (LPVOID)*((_QWORD *)v25 + 10 * v18 + 2);
          v19[9] = (LPVOID)(*((_QWORD *)v25 + 10 * v18 + 4) + 1LL);
          v16 = 130;
          if ( *((_WORD *)v25 + 40 * v18 + 20) == 130 )
            v19[9] = (LPVOID)1028;
          v19[4] = 0;
          v19[5] = 0;
          v19[6] = 0;
          *(LPVOID *)((char *)v19 + 60) = 0;
          *((_DWORD *)v19 + 20) = 0;
          *((_BYTE *)v19 + 86) = *((_BYTE *)v25 + 80 * v18 + 42);
          LOBYTE(v16) = *((_BYTE *)v25 + 80 * v18 + 43);
          *((_BYTE *)v19 + 87) = v16;
          ++v17;
        }
        ++v18;
      }
      while ( v18 < v26 );
      if ( v17 )
      {
        v20 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
                a2,
                &IID_IAccessor,
                &v27);
        v21 = v20;
        if ( v20 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048428[0] )
            bidTraceW(off_1800481B8[0], 710656, off_180048428[0], (unsigned int)v20, 694);
          ThrowHR(v21);
        }
        v22 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPVOID *, __int64, __int64 *, _QWORD))(*(_QWORD *)v27 + 32LL))(
                v27,
                2,
                v17,
                v12,
                9648,
                &v31,
                0);
        v23 = v22;
        if ( v22 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048420[0] )
            bidTraceW(off_1800481B8[0], 711680, off_180048420[0], (unsigned int)v22, 695);
          ThrowHR(v23);
        }
      }
    }
    CAutoP<_GUID>::~CAutoP<_GUID>(&v29);
    v3 = pv;
    v4 = v31;
  }
  CoTaskMemFree(v3);
  CoTaskMemFree(v25);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v27);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v28);
  return v4;
}

```

## disassembly

```asm
0x1800050c4  push    rbp
0x1800050c6  push    rbx
0x1800050c7  push    rsi
0x1800050c8  push    rdi
0x1800050c9  push    r12
0x1800050cb  push    r13
0x1800050cd  push    r14
0x1800050cf  push    r15
0x1800050d1  sub     rsp, 0E8h
0x1800050d8  lea     rbp, [rsp+40h]
0x1800050dd  mov     rax, cs:__security_cookie
0x1800050e4  xor     rax, rbp
0x1800050e7  mov     [rbp+0E0h+var_50], rax
0x1800050ee  mov     rsi, rdx
0x1800050f1  xor     r13d, r13d
0x1800050f4  mov     [rbp+0E0h+var_C8], r13
0x1800050f8  mov     [rbp+0E0h+var_D0], r13
0x1800050fc  mov     [rbp+0E0h+var_D8], r13
0x180005100  mov     [rbp+0E0h+var_E0], r13
0x180005104  mov     ecx, r13d
0x180005107  mov     [rbp+0E0h+pv], rcx
0x18000510b  mov     ebx, r13d
0x18000510e  mov     [rbp+0E0h+var_B0], rbx
0x180005112  test    rdx, rdx
0x180005115  jz      loc_18000541C
0x18000511b  mov     rax, [rdx]
0x18000511e  lea     r8, [rbp+0E0h+var_C8]
0x180005122  lea     rdx, IID_IColumnsInfo
0x180005129  mov     rcx, rsi
0x18000512c  mov     rax, [rax]
0x18000512f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005134  mov     ebx, eax
0x180005136  test    eax, eax
0x180005138  jns     short loc_18000517A
0x18000513a  test    byte ptr cs:_bidGblFlags, 2
0x180005141  jz      short loc_180005172
0x180005143  mov     rcx, cs:off_180048438; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x18000514a  test    rcx, rcx
0x18000514d  jz      short loc_180005172
0x18000514f  mov     dword ptr [rsp+120h+var_100], 294h
0x180005157  mov     r9d, eax
0x18000515a  mov     r8, cs:off_180048438; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x180005161  mov     edx, 0A5000h
0x180005166  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000516d  call    _bidTraceW
0x180005172  mov     ecx, ebx; int
0x180005174  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000517a  mov     rcx, [rbp+0E0h+var_C8]
0x18000517e  mov     rax, [rcx]
0x180005181  lea     r9, [rbp+0E0h+pv]
0x180005185  lea     r8, [rbp+0E0h+var_E0]
0x180005189  lea     rdx, [rbp+0E0h+var_D8]
0x18000518d  mov     rax, [rax+18h]
0x180005191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005196  mov     ebx, eax
0x180005198  test    eax, eax
0x18000519a  jns     short loc_1800051DC
0x18000519c  test    byte ptr cs:_bidGblFlags, 2
0x1800051a3  jz      short loc_1800051D4
0x1800051a5  mov     rcx, cs:off_180048430; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x1800051ac  test    rcx, rcx
0x1800051af  jz      short loc_1800051D4
0x1800051b1  mov     dword ptr [rsp+120h+var_100], 295h
0x1800051b9  mov     r9d, eax
0x1800051bc  mov     r8, cs:off_180048430; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x1800051c3  mov     edx, 0A5400h
0x1800051c8  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800051cf  call    _bidTraceW
0x1800051d4  mov     ecx, ebx; int
0x1800051d6  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800051dc  mov     [rbp+0E0h+var_C0], r13
0x1800051e0  mov     rcx, [rbp+0E0h+var_D8]
0x1800051e4  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x1800051e9  mov     rcx, [rbp+0E0h+var_D8]
0x1800051ed  cmp     eax, 0Bh
0x1800051f0  ja      short loc_180005223
0x1800051f2  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x1800051f7  mov     eax, eax
0x1800051f9  imul    rcx, rax, 58h ; 'X'
0x1800051fd  lea     rax, [rcx+0Fh]
0x180005201  cmp     rax, rcx
0x180005204  ja      short loc_180005210
0x180005206  mov     rax, 0FFFFFFFFFFFFFF0h
0x180005210  and     rax, 0FFFFFFFFFFFFFFF0h
0x180005214  call    _alloca_probe
0x180005219  sub     rsp, rax
0x18000521c  lea     r12, [rsp+120h+var_E0]
0x180005221  jmp     short loc_18000524B
0x180005223  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x180005228  mov     ecx, eax
0x18000522a  mov     eax, 58h ; 'X'
0x18000522f  mul     rcx
0x180005232  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005239  cmovb   rax, rcx
0x18000523d  mov     ecx, eax; unsigned int
0x18000523f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180005244  mov     r12, rax
0x180005247  mov     [rbp+0E0h+var_C0], rax
0x18000524b  mov     rcx, r12; void *
0x18000524e  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180005253  mov     r14d, r13d
0x180005256  mov     r15d, r13d
0x180005259  cmp     [rbp+0E0h+var_D8], r13
0x18000525d  jbe     loc_18000540B
0x180005263  mov     eax, r15d
0x180005266  lea     rdi, [rax+rax*4]
0x18000526a  add     rdi, rdi
0x18000526d  mov     rax, [rbp+0E0h+var_E0]
0x180005271  movups  xmm0, xmmword ptr [rax+rdi*8]
0x180005275  movaps  xmmword ptr [rbp+0E0h+var_A0.pwszName], xmm0
0x180005279  movups  xmm1, xmmword ptr [rax+rdi*8+10h]
0x18000527e  movaps  xmmword ptr [rbp+0E0h+var_A0.iOrdinal], xmm1
0x180005282  movups  xmm0, xmmword ptr [rax+rdi*8+20h]
0x180005287  movaps  xmmword ptr [rbp+0E0h+var_A0.ulColumnSize], xmm0
0x18000528b  movups  xmm1, xmmword ptr [rax+rdi*8+30h]
0x180005290  movaps  xmmword ptr [rbp+0E0h+var_A0.columnid.uGuid], xmm1
0x180005294  movups  xmm0, xmmword ptr [rax+rdi*8+40h]
0x180005299  movaps  xmmword ptr [rbp+0E0h+var_A0.columnid.eKind], xmm0
0x1800052a0  mov     eax, r14d
0x1800052a3  imul    rbx, rax, 58h ; 'X'
0x1800052a7  add     rbx, r12
0x1800052aa  lea     r8, [rbp+0E0h+var_A0]; struct tagDBCOLUMNINFO
0x1800052ae  mov     rdx, rbx; struct tagDBBINDING *
0x1800052b1  call    ?mdSetupColRSDataBuffer@CMetaData@@AEAAHPEAUtagDBBINDING@@UtagDBCOLUMNINFO@@@Z; CMetaData::mdSetupColRSDataBuffer(tagDBBINDING *,tagDBCOLUMNINFO)
0x1800052b6  test    eax, eax
0x1800052b8  jz      short loc_18000531B
0x1800052ba  mov     rax, [rbp+0E0h+var_E0]
0x1800052be  mov     rcx, [rax+rdi*8+10h]
0x1800052c3  mov     [rbx], rcx
0x1800052c6  mov     rax, [rbp+0E0h+var_E0]
0x1800052ca  mov     rcx, [rax+rdi*8+20h]
0x1800052cf  inc     rcx
0x1800052d2  mov     [rbx+48h], rcx
0x1800052d6  mov     ecx, 82h
0x1800052db  mov     rax, [rbp+0E0h+var_E0]
0x1800052df  cmp     [rax+rdi*8+28h], cx
0x1800052e4  jnz     short loc_1800052EE
0x1800052e6  mov     qword ptr [rbx+48h], 404h
0x1800052ee  mov     [rbx+20h], r13
0x1800052f2  mov     [rbx+28h], r13
0x1800052f6  mov     [rbx+30h], r13
0x1800052fa  mov     [rbx+3Ch], r13
0x1800052fe  mov     [rbx+50h], r13d
0x180005302  mov     rax, [rbp+0E0h+var_E0]
0x180005306  mov     cl, [rax+rdi*8+2Ah]
0x18000530a  mov     [rbx+56h], cl
0x18000530d  mov     rax, [rbp+0E0h+var_E0]
0x180005311  mov     cl, [rax+rdi*8+2Bh]
0x180005315  mov     [rbx+57h], cl
0x180005318  inc     r14d
0x18000531b  inc     r15d
0x18000531e  mov     eax, r15d
0x180005321  cmp     rax, [rbp+0E0h+var_D8]
0x180005325  jb      loc_180005263
0x18000532b  test    r14d, r14d
0x18000532e  jz      loc_18000540B
0x180005334  mov     rax, [rsi]
0x180005337  lea     r8, [rbp+0E0h+var_D0]
0x18000533b  lea     rdx, IID_IAccessor
0x180005342  mov     rcx, rsi
0x180005345  mov     rax, [rax]
0x180005348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000534d  mov     ebx, eax
0x18000534f  test    eax, eax
0x180005351  jns     short loc_180005393
0x180005353  test    byte ptr cs:_bidGblFlags, 2
0x18000535a  jz      short loc_18000538B
0x18000535c  mov     rcx, cs:off_180048428; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x180005363  test    rcx, rcx
0x180005366  jz      short loc_18000538B
0x180005368  mov     dword ptr [rsp+120h+var_100], 2B6h
0x180005370  mov     r9d, eax
0x180005373  mov     r8, cs:off_180048428; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x18000537a  mov     edx, 0AD800h
0x18000537f  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180005386  call    _bidTraceW
0x18000538b  mov     ecx, ebx; int
0x18000538d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180005393  mov     rcx, [rbp+0E0h+var_D0]
0x180005397  mov     rax, [rcx]
0x18000539a  mov     r8d, r14d
0x18000539d  mov     [rsp+120h+var_F0], r13
0x1800053a2  lea     rdx, [rbp+0E0h+var_B0]
0x1800053a6  mov     [rsp+120h+var_F8], rdx
0x1800053ab  mov     [rsp+120h+var_100], 25B0h
0x1800053b4  mov     r9, r12
0x1800053b7  mov     edx, 2
0x1800053bc  mov     rax, [rax+20h]
0x1800053c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053c5  mov     ebx, eax
0x1800053c7  test    eax, eax
0x1800053c9  jns     short loc_18000540B
0x1800053cb  test    byte ptr cs:_bidGblFlags, 2
0x1800053d2  jz      short loc_180005403
0x1800053d4  mov     rcx, cs:off_180048420; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x1800053db  test    rcx, rcx
0x1800053de  jz      short loc_180005403
0x1800053e0  mov     dword ptr [rsp+120h+var_100], 2B7h
0x1800053e8  mov     r9d, eax
0x1800053eb  mov     r8, cs:off_180048420; "<CMetaData::mdSetupAccessor|ADO|ERR>  H"...
0x1800053f2  mov     edx, 0ADC00h
0x1800053f7  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800053fe  call    _bidTraceW
0x180005403  mov     ecx, ebx; int
0x180005405  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000540b  lea     rcx, [rbp+0E0h+var_C0]
0x18000540f  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180005414  mov     rcx, [rbp+0E0h+pv]; pv
0x180005418  mov     rbx, [rbp+0E0h+var_B0]
0x18000541c  call    cs:__imp_CoTaskMemFree
0x180005422  nop
0x180005423  mov     rcx, [rbp+0E0h+var_E0]; pv
0x180005427  call    cs:__imp_CoTaskMemFree
0x18000542d  nop
0x18000542e  lea     rcx, [rbp+0E0h+var_D0]
0x180005432  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180005437  nop
0x180005438  lea     rcx, [rbp+0E0h+var_C8]
0x18000543c  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180005441  mov     rax, rbx
0x180005444  mov     rcx, [rbp+0E0h+var_50]
0x18000544b  xor     rcx, rbp; StackCookie
0x18000544e  call    __security_check_cookie
0x180005453  lea     rsp, [rbp+0A8h]
0x18000545a  pop     r15
0x18000545c  pop     r14
0x18000545e  pop     r13
0x180005460  pop     r12
0x180005462  pop     rdi
0x180005463  pop     rsi
0x180005464  pop     rbx
0x180005465  pop     rbp
0x180005466  retn
```

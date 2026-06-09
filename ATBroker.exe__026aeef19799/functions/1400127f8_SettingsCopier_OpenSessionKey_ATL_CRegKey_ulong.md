# SettingsCopier::OpenSessionKey(ATL::CRegKey &,ulong)

- ea: `0x1400127f8`
- end: `0x140012a41`
- name: `?OpenSessionKey@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@K@Z`
- size: `585`
- prototype: `__int64 __fastcall(SettingsCopier *this, HKEY *, REGSAM)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140012640`
- `0x14001271c`

## callees

- `0x140009aa8`
- `0x14000be54`
- `0x1400127f8`
- `0x140015830`
- `0x140017010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14001293b`
- `ADVAPI32!RegOpenKeyExW` at `0x14001293b`
- `ADVAPI32!RegCloseKey` at `0x140012950`
- `ADVAPI32!RegCloseKey` at `0x140012950`
- `msvcrt!malloc` at `0x1400128d5`
- `msvcrt!malloc` at `0x1400128d5`
- `msvcrt!free` at `0x140012907`
- `msvcrt!free` at `0x14001299e`
- `msvcrt!free` at `0x1400129d0`
- `msvcrt!free` at `0x140012907`
- `msvcrt!free` at `0x14001299e`
- `msvcrt!free` at `0x1400129d0`

## string_xrefs

- `0x140012830`: `%s\ATConfig`
- `0x1400128ee`: `%s\ATConfig`

## pseudocode

```c
__int64 __fastcall SettingsCopier::OpenSessionKey(SettingsCopier *this, HKEY *a2, REGSAM a3)
{
  __int64 v5; // r9
  unsigned __int16 *v6; // rax
  unsigned __int64 v7; // rdx
  _WORD *v8; // rdi
  __int64 v9; // rcx
  _WORD *v10; // rax
  __int64 v11; // r8
  unsigned __int64 v12; // r14
  WCHAR *v13; // rbx
  size_t v14; // rcx
  unsigned __int16 *v15; // rax
  volatile signed __int32 *v16; // rdx
  unsigned __int16 *v17; // r9
  LSTATUS v18; // eax
  _QWORD *v19; // rdx
  _QWORD *v21; // rdx
  struct _SECURITY_ATTRIBUTES *v22; // [rsp+30h] [rbp-20h]
  HKEY phkResult; // [rsp+80h] [rbp+30h] BYREF
  _WORD *v24; // [rsp+98h] [rbp+48h] BYREF

  phkResult = (HKEY)this;
  CATUtils::SessionKeyString(&v24);
  v5 = 0x7FFFFFFF;
  v6 = SettingsCopier::_ATSessionConfigKeyString;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = (0x7FFFFFFF - v5) & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64);
  v8 = v24;
  if ( !v5 || !v24 )
    goto LABEL_30;
  v9 = 0x7FFFFFFF;
  v10 = v24;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = (0x7FFFFFFF - v9) & -(__int64)(v9 != 0);
  if ( !v9 || (v12 = v11 + v7, v11 + v7 < v7) )
  {
LABEL_30:
    v16 = (volatile signed __int32 *)(v24 - 12);
    goto LABEL_31;
  }
  v13 = 0;
  if ( v12 )
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
      goto LABEL_27;
    v14 = 2 * v12;
  }
  else
  {
    v14 = 0;
  }
  v15 = (unsigned __int16 *)malloc(v14);
  v13 = v15;
  if ( v15 )
  {
    if ( (int)StringCchPrintfW(v15, v12, SettingsCopier::_ATSessionConfigKeyString, v8) >= 0 )
    {
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v13, 0, a3, &phkResult) )
      {
        v18 = 0;
        if ( *a2 )
          v18 = RegCloseKey(*a2);
        *a2 = phkResult;
        if ( !v18 )
          goto LABEL_24;
      }
      if ( (a3 & 0x20006) == 0x20006
        && !ATL::CRegKey::Create(
              (ATL::CRegKey *)a2,
              HKEY_LOCAL_MACHINE,
              v13,
              v17,
              1u,
              a3,
              v22,
              (unsigned int *)&phkResult) )
      {
LABEL_24:
        free(v13);
        v19 = v24 - 12;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 - 2, 0xFFFFFFFF) <= 1 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 8LL))(*v19);
        return 0;
      }
    }
    free(v13);
    v16 = (volatile signed __int32 *)(v24 - 12);
LABEL_31:
    if ( _InterlockedExchangeAdd(v16 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 8LL))(*(_QWORD *)v16);
    return 2147500037LL;
  }
LABEL_27:
  free(v13);
  v21 = v24 - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v24 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 8LL))(*v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1400127f8  mov     [rsp-28h+arg_8], rbx
0x1400127fd  mov     [rsp-28h+arg_10], rdi
0x140012802  mov     [rsp-28h+arg_0], rcx
0x140012807  push    rbp
0x140012808  push    r12
0x14001280a  push    r13
0x14001280c  push    r14
0x14001280e  push    r15
0x140012810  mov     rbp, rsp
0x140012813  sub     rsp, 50h
0x140012817  mov     r12d, r8d
0x14001281a  mov     r15, rdx
0x14001281d  lea     rcx, [rbp+arg_18]
0x140012821  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x140012826  nop
0x140012827  mov     r10d, 7FFFFFFFh
0x14001282d  mov     r9d, r10d
0x140012830  lea     rax, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x140012837  xor     r13d, r13d
0x14001283a  cmp     [rax], r13w
0x14001283e  jz      short loc_14001284A
0x140012840  add     rax, 2
0x140012844  sub     r9, 1
0x140012848  jnz     short loc_14001283A
0x14001284a  mov     rax, r9
0x14001284d  mov     rcx, r10
0x140012850  sub     rcx, r9
0x140012853  neg     rax
0x140012856  sbb     rdx, rdx
0x140012859  and     rdx, rcx
0x14001285c  mov     rdi, [rbp+arg_18]
0x140012860  test    r9, r9
0x140012863  jz      loc_140012A02
0x140012869  test    rdi, rdi
0x14001286c  jz      loc_140012A02
0x140012872  mov     rcx, r10
0x140012875  mov     rax, rdi
0x140012878  cmp     [rax], r13w
0x14001287c  jz      short loc_140012888
0x14001287e  add     rax, 2
0x140012882  sub     rcx, 1
0x140012886  jnz     short loc_140012878
0x140012888  mov     rax, rcx
0x14001288b  sub     r10, rcx
0x14001288e  neg     rax
0x140012891  sbb     r8, r8
0x140012894  and     r8, r10
0x140012897  test    rcx, rcx
0x14001289a  jz      loc_140012A02
0x1400128a0  lea     r14, [r8+rdx]
0x1400128a4  cmp     r14, rdx
0x1400128a7  jb      loc_140012A02
0x1400128ad  mov     rbx, r13
0x1400128b0  mov     [rbp+var_10], rbx
0x1400128b4  test    r14, r14
0x1400128b7  jnz     short loc_1400128BE
0x1400128b9  mov     rcx, r13
0x1400128bc  jmp     short loc_1400128D5
0x1400128be  xor     edx, edx
0x1400128c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400128c4  div     r14
0x1400128c7  cmp     rax, 2
0x1400128cb  jb      loc_1400129CD
0x1400128d1  lea     rcx, [r14+r14]; Size
0x1400128d5  call    cs:__imp_malloc
0x1400128db  mov     rbx, rax
0x1400128de  mov     [rbp+var_10], rax
0x1400128e2  test    rax, rax
0x1400128e5  jz      loc_1400129CD
0x1400128eb  mov     r9, rdi
0x1400128ee  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x1400128f5  mov     rdx, r14; unsigned __int64
0x1400128f8  mov     rcx, rax; unsigned __int16 *
0x1400128fb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140012900  test    eax, eax
0x140012902  jns     short loc_14001291B
0x140012904  mov     rcx, rbx; Block
0x140012907  call    cs:__imp_free
0x14001290d  nop
0x14001290e  mov     rdx, [rbp+arg_18]
0x140012912  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140012916  jmp     loc_140012A06
0x14001291b  mov     [rbp+arg_0], r13
0x14001291f  lea     rax, [rbp+arg_0]
0x140012923  mov     [rsp+50h+phkResult], rax; phkResult
0x140012928  mov     r9d, r12d; samDesired
0x14001292b  xor     r8d, r8d; ulOptions
0x14001292e  mov     rdx, rbx; lpSubKey
0x140012931  mov     rdi, 0FFFFFFFF80000002h
0x140012938  mov     rcx, rdi; hKey
0x14001293b  call    cs:__imp_RegOpenKeyExW
0x140012941  test    eax, eax
0x140012943  jnz     short loc_140012961
0x140012945  mov     eax, r13d
0x140012948  mov     rcx, [r15]; hKey
0x14001294b  test    rcx, rcx
0x14001294e  jz      short loc_140012956
0x140012950  call    cs:__imp_RegCloseKey
0x140012956  mov     rcx, [rbp+arg_0]
0x14001295a  mov     [r15], rcx
0x14001295d  test    eax, eax
0x14001295f  jz      short loc_14001299B
0x140012961  mov     eax, r12d
0x140012964  mov     ecx, 20006h
0x140012969  and     eax, ecx
0x14001296b  cmp     eax, ecx
0x14001296d  jnz     short loc_140012904
0x14001296f  lea     rax, [rbp+arg_0]
0x140012973  mov     [rsp+50h+var_18], rax; unsigned int *
0x140012978  mov     [rsp+50h+var_28], r12d; unsigned int
0x14001297d  mov     dword ptr [rsp+50h+phkResult], 1; unsigned int
0x140012985  mov     r8, rbx; unsigned __int16 *
0x140012988  mov     rdx, rdi; HKEY
0x14001298b  mov     rcx, r15; this
0x14001298e  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x140012993  test    eax, eax
0x140012995  jnz     loc_140012904
0x14001299b  mov     rcx, rbx; Block
0x14001299e  call    cs:__imp_free
0x1400129a4  nop
0x1400129a5  mov     rdx, [rbp+arg_18]
0x1400129a9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400129ad  or      eax, 0FFFFFFFFh
0x1400129b0  lock xadd [rdx+10h], eax
0x1400129b5  sub     eax, 1
0x1400129b8  jg      short loc_1400129C9
0x1400129ba  mov     rcx, [rdx]
0x1400129bd  mov     rax, [rcx]
0x1400129c0  mov     rax, [rax+8]
0x1400129c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129c9  xor     eax, eax
0x1400129cb  jmp     short loc_140012A27
0x1400129cd  mov     rcx, rbx; Block
0x1400129d0  call    cs:__imp_free
0x1400129d6  nop
0x1400129d7  mov     rdx, [rbp+arg_18]
0x1400129db  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400129df  or      eax, 0FFFFFFFFh
0x1400129e2  lock xadd [rdx+10h], eax
0x1400129e7  sub     eax, 1
0x1400129ea  jg      short loc_1400129FB
0x1400129ec  mov     rcx, [rdx]
0x1400129ef  mov     rax, [rcx]
0x1400129f2  mov     rax, [rax+8]
0x1400129f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400129fb  mov     eax, 8007000Eh
0x140012a00  jmp     short loc_140012A27
0x140012a02  lea     rdx, [rdi-18h]
0x140012a06  or      eax, 0FFFFFFFFh
0x140012a09  lock xadd [rdx+10h], eax
0x140012a0e  sub     eax, 1
0x140012a11  jg      short loc_140012A22
0x140012a13  mov     rcx, [rdx]
0x140012a16  mov     rax, [rcx]
0x140012a19  mov     rax, [rax+8]
0x140012a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012a22  mov     eax, 80004005h
0x140012a27  lea     r11, [rsp+50h+var_s0]
0x140012a2c  mov     rbx, [r11+38h]
0x140012a30  mov     rdi, [r11+40h]
0x140012a34  mov     rsp, r11
0x140012a37  pop     r15
0x140012a39  pop     r14
0x140012a3b  pop     r13
0x140012a3d  pop     r12
0x140012a3f  pop     rbp
0x140012a40  retn
```

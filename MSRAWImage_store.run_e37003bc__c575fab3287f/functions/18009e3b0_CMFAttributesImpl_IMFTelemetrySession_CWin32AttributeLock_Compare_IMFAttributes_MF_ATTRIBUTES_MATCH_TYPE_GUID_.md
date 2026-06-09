# CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_Compare(IMFAttributes *,_MF_ATTRIBUTES_MATCH_TYPE,_GUID const *,uint,int *)

- ea: `0x18009e3b0`
- end: `0x18009e65d`
- name: `?_Compare@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@QEAAJPEAUIMFAttributes@@W4_MF_ATTRIBUTES_MATCH_TYPE@@PEBU_GUID@@IPEAH@Z`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180098dc0`

## callees

- `0x180002a00`
- `0x18009e3b0`
- `0x18009e6d0`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e62a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009e62a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e3fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009e3fd`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_Compare(
        __int64 a1,
        __int64 *a2,
        int a3,
        __int64 a4,
        int a5,
        _DWORD *a6)
{
  int v9; // ebx
  __int64 v10; // rax
  __int64 i; // r12
  __int64 v12; // rax
  __int64 j; // rsi
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int k; // esi
  __int64 v17; // rax
  __int64 Item; // r8
  __int64 v19; // rax
  int v21; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v22; // [rsp+34h] [rbp-1Ch] BYREF
  __int128 v23; // [rsp+38h] [rbp-18h] BYREF

  v9 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 224))(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( v9 >= 0 )
  {
    switch ( a3 )
    {
      case 4:
        v10 = *a2;
        v22 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v10 + 240))(a2, &v22);
        if ( v9 < 0 )
          goto LABEL_36;
        if ( v22 >= *(_DWORD *)(a1 + 60) )
        {
          a3 = 0;
          goto LABEL_6;
        }
        break;
      case 0:
LABEL_6:
        for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 60); i = (unsigned int)(i + 1) )
        {
          v12 = *(_QWORD *)(a1 + 48);
          v21 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, int *))(*a2 + 40))(
                 a2,
                 v12 + 40 * i,
                 v12 + 40 * i + 16,
                 &v21);
          if ( v9 < 0 )
            goto LABEL_36;
          if ( !v21 )
            goto LABEL_22;
        }
        if ( a3 != 2 )
          goto LABEL_35;
        v19 = *a2;
        v21 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(v19 + 240))(a2, &v21);
        if ( v9 >= 0 )
        {
          if ( v21 != *(_DWORD *)(a1 + 60) )
          {
LABEL_34:
            *a6 = 0;
            goto LABEL_36;
          }
LABEL_35:
          *a6 = 1;
        }
LABEL_36:
        (*(void (__fastcall **)(__int64 *))(*a2 + 232))(a2);
        goto LABEL_37;
      case 1:
        break;
      case 2:
        goto LABEL_6;
      case 3:
        for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 60); j = (unsigned int)(j + 1) )
        {
          v14 = *(_QWORD *)(a1 + 48);
          v22 = 0;
          if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD))(*a2 + 24))(a2, v14 + 40 * j, 0) >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, unsigned int *))(*a2 + 40))(
                   a2,
                   *(_QWORD *)(a1 + 48) + 40 * j,
                   *(_QWORD *)(a1 + 48) + 40 * j + 16,
                   &v22);
            if ( v9 < 0 )
              goto LABEL_36;
            if ( !v22 )
            {
LABEL_22:
              *a6 = 0;
              goto LABEL_36;
            }
          }
        }
        goto LABEL_35;
      default:
        v9 = -2147024809;
        goto LABEL_36;
    }
    v15 = *a2;
    v22 = 0;
    v23 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v15 + 240))(a2, &v22);
    if ( v9 >= 0 )
    {
      for ( k = 0; k < v22; ++k )
      {
        v17 = *a2;
        v21 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int128 *, _QWORD))(v17 + 248))(a2, k, &v23, 0);
        if ( v9 < 0 )
          goto LABEL_36;
        Item = CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(a1, &v23);
        if ( !Item )
          goto LABEL_34;
        v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64, int *))(*a2 + 40))(a2, &v23, Item, &v21);
        if ( v9 < 0 )
          goto LABEL_36;
        if ( !v21 )
          goto LABEL_34;
      }
      goto LABEL_35;
    }
    goto LABEL_36;
  }
LABEL_37:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18009e3b0  mov     [rsp-38h+arg_18], rbx
0x18009e3b5  push    rbp
0x18009e3b6  push    rsi
0x18009e3b7  push    rdi
0x18009e3b8  push    r12
0x18009e3ba  push    r13
0x18009e3bc  push    r14
0x18009e3be  push    r15
0x18009e3c0  mov     rbp, rsp
0x18009e3c3  sub     rsp, 50h
0x18009e3c7  mov     rax, cs:__security_cookie
0x18009e3ce  xor     rax, rsp
0x18009e3d1  mov     [rbp+var_8], rax
0x18009e3d5  mov     rax, [rdx]
0x18009e3d8  mov     r15, rcx
0x18009e3db  mov     r14, [rbp+arg_28]
0x18009e3df  mov     rcx, rdx
0x18009e3e2  mov     esi, r8d
0x18009e3e5  mov     rdi, rdx
0x18009e3e8  mov     rax, [rax+0E0h]
0x18009e3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e3f4  lea     rcx, [r15+8]; lpCriticalSection
0x18009e3f8  mov     ebx, eax
0x18009e3fa  mov     r12d, eax
0x18009e3fd  call    cs:__imp_EnterCriticalSection
0x18009e404  nop     dword ptr [rax+rax+00h]
0x18009e409  test    ebx, ebx
0x18009e40b  js      loc_18009E626
0x18009e411  cmp     esi, 4
0x18009e414  jnz     loc_18009E4A0
0x18009e41a  mov     rax, [rdi]
0x18009e41d  lea     rdx, [rbp+var_1C]
0x18009e421  mov     rcx, rdi
0x18009e424  mov     [rbp+var_1C], 0
0x18009e42b  mov     rax, [rax+0F0h]
0x18009e432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e437  mov     ebx, eax
0x18009e439  test    eax, eax
0x18009e43b  js      loc_18009E614
0x18009e441  mov     eax, [r15+3Ch]
0x18009e445  cmp     [rbp+var_1C], eax
0x18009e448  jb      loc_18009E537
0x18009e44e  xor     esi, esi
0x18009e450  xor     r12d, r12d
0x18009e453  cmp     r12d, [r15+3Ch]
0x18009e457  jnb     loc_18009E5D4
0x18009e45d  mov     rax, [r15+30h]
0x18009e461  lea     rcx, [r12+r12*4]
0x18009e465  lea     r9, [rbp+var_20]
0x18009e469  mov     [rbp+var_20], 0
0x18009e470  lea     rdx, [rax+rcx*8]
0x18009e474  mov     rax, [rdi]
0x18009e477  lea     r8, [rdx+10h]
0x18009e47b  mov     rcx, rdi
0x18009e47e  mov     rax, [rax+28h]
0x18009e482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e487  mov     ebx, eax
0x18009e489  test    eax, eax
0x18009e48b  js      loc_18009E614
0x18009e491  cmp     [rbp+var_20], 0
0x18009e495  jz      loc_18009E52B
0x18009e49b  inc     r12d
0x18009e49e  jmp     short loc_18009E453
0x18009e4a0  mov     ecx, esi
0x18009e4a2  test    esi, esi
0x18009e4a4  jz      short loc_18009E450
0x18009e4a6  sub     ecx, 1
0x18009e4a9  jz      loc_18009E537
0x18009e4af  sub     ecx, 1
0x18009e4b2  jz      short loc_18009E450
0x18009e4b4  cmp     ecx, 1
0x18009e4b7  jz      short loc_18009E4C3
0x18009e4b9  mov     ebx, 80070057h
0x18009e4be  jmp     loc_18009E614
0x18009e4c3  xor     esi, esi
0x18009e4c5  cmp     esi, [r15+3Ch]
0x18009e4c9  jnb     loc_18009E60D
0x18009e4cf  mov     rax, [r15+30h]
0x18009e4d3  lea     r12, [rsi+rsi*4]
0x18009e4d7  xor     r8d, r8d
0x18009e4da  mov     [rbp+var_1C], 0
0x18009e4e1  mov     rcx, rdi
0x18009e4e4  lea     rdx, [rax+r12*8]
0x18009e4e8  mov     rax, [rdi]
0x18009e4eb  mov     rax, [rax+18h]
0x18009e4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e4f4  test    eax, eax
0x18009e4f6  js      short loc_18009E527
0x18009e4f8  mov     rax, [r15+30h]
0x18009e4fc  lea     r9, [rbp+var_1C]
0x18009e500  mov     rcx, rdi
0x18009e503  lea     rdx, [rax+r12*8]
0x18009e507  mov     rax, [rdi]
0x18009e50a  lea     r8, [rdx+10h]
0x18009e50e  mov     rax, [rax+28h]
0x18009e512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e517  mov     ebx, eax
0x18009e519  test    eax, eax
0x18009e51b  js      loc_18009E614
0x18009e521  cmp     [rbp+var_1C], 0
0x18009e525  jz      short loc_18009E52B
0x18009e527  inc     esi
0x18009e529  jmp     short loc_18009E4C5
0x18009e52b  mov     dword ptr [r14], 0
0x18009e532  jmp     loc_18009E614
0x18009e537  mov     rax, [rdi]
0x18009e53a  lea     rdx, [rbp+var_1C]
0x18009e53e  xorps   xmm0, xmm0
0x18009e541  mov     [rbp+var_1C], 0
0x18009e548  mov     rcx, rdi
0x18009e54b  movups  [rbp+var_18], xmm0
0x18009e54f  mov     rax, [rax+0F0h]
0x18009e556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e55b  xor     r12d, r12d
0x18009e55e  mov     ebx, eax
0x18009e560  test    eax, eax
0x18009e562  js      loc_18009E614
0x18009e568  mov     esi, r12d
0x18009e56b  cmp     esi, [rbp+var_1C]
0x18009e56e  jnb     loc_18009E60D
0x18009e574  mov     rax, [rdi]
0x18009e577  lea     r8, [rbp+var_18]
0x18009e57b  xor     r9d, r9d
0x18009e57e  mov     [rbp+var_20], r12d
0x18009e582  mov     edx, esi
0x18009e584  mov     rcx, rdi
0x18009e587  mov     rax, [rax+0F8h]
0x18009e58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e593  mov     ebx, eax
0x18009e595  test    eax, eax
0x18009e597  js      short loc_18009E614
0x18009e599  lea     rdx, [rbp+var_18]
0x18009e59d  mov     rcx, r15
0x18009e5a0  call    ?_FindItem@?$CMFAttributesImpl@UIMFTelemetrySession@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFTelemetrySession,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18009e5a5  mov     r8, rax
0x18009e5a8  test    rax, rax
0x18009e5ab  jz      short loc_18009E608
0x18009e5ad  mov     rcx, [rdi]
0x18009e5b0  lea     r9, [rbp+var_20]
0x18009e5b4  lea     rdx, [rbp+var_18]
0x18009e5b8  mov     rax, [rcx+28h]
0x18009e5bc  mov     rcx, rdi
0x18009e5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e5c4  mov     ebx, eax
0x18009e5c6  test    eax, eax
0x18009e5c8  js      short loc_18009E614
0x18009e5ca  cmp     [rbp+var_20], r12d
0x18009e5ce  jz      short loc_18009E608
0x18009e5d0  inc     esi
0x18009e5d2  jmp     short loc_18009E56B
0x18009e5d4  cmp     esi, 2
0x18009e5d7  jnz     short loc_18009E60D
0x18009e5d9  mov     rax, [rdi]
0x18009e5dc  lea     rdx, [rbp+var_20]
0x18009e5e0  mov     rcx, rdi
0x18009e5e3  mov     [rbp+var_20], 0
0x18009e5ea  mov     rax, [rax+0F0h]
0x18009e5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e5f6  xor     r12d, r12d
0x18009e5f9  mov     ebx, eax
0x18009e5fb  test    eax, eax
0x18009e5fd  js      short loc_18009E614
0x18009e5ff  mov     eax, [r15+3Ch]
0x18009e603  cmp     [rbp+var_20], eax
0x18009e606  jz      short loc_18009E60D
0x18009e608  mov     [r14], r12d
0x18009e60b  jmp     short loc_18009E614
0x18009e60d  mov     dword ptr [r14], 1
0x18009e614  mov     rax, [rdi]
0x18009e617  mov     rcx, rdi
0x18009e61a  mov     rax, [rax+0E8h]
0x18009e621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e626  lea     rcx, [r15+8]; lpCriticalSection
0x18009e62a  call    cs:__imp_LeaveCriticalSection
0x18009e631  nop     dword ptr [rax+rax+00h]
0x18009e636  mov     eax, ebx
0x18009e638  mov     rcx, [rbp+var_8]
0x18009e63c  xor     rcx, rsp; StackCookie
0x18009e63f  call    __security_check_cookie
0x18009e644  mov     rbx, [rsp+50h+arg_18]
0x18009e64c  add     rsp, 50h
0x18009e650  pop     r15
0x18009e652  pop     r14
0x18009e654  pop     r13
0x18009e656  pop     r12
0x18009e658  pop     rdi
0x18009e659  pop     rsi
0x18009e65a  pop     rbp
0x18009e65b  retn
```

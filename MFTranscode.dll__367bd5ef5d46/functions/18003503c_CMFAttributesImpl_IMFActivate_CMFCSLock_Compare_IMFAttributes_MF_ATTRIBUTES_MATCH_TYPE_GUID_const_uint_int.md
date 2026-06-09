# CMFAttributesImpl<IMFActivate,CMFCSLock>::_Compare(IMFAttributes *,_MF_ATTRIBUTES_MATCH_TYPE,_GUID const *,uint,int *)

- ea: `0x18003503c`
- end: `0x1800352ea`
- name: `?_Compare@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@QEAAJPEAUIMFAttributes@@W4_MF_ATTRIBUTES_MATCH_TYPE@@PEBU_GUID@@IPEAH@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180031ac0`

## callees

- `0x1800088d0`
- `0x1800174c0`
- `0x18003503c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800352be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800352be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035086`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035086`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFActivate,CMFCSLock>::_Compare(
        __int64 a1,
        __int64 *a2,
        int a3,
        __int64 a4,
        int a5,
        _DWORD *a6)
{
  int v9; // ebx
  unsigned int v10; // r12d
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned int i; // r15d
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned int j; // r15d
  __int64 v18; // rax
  __int64 Item; // r8
  __int64 v20; // rax
  unsigned int v22; // [rsp+30h] [rbp-20h] BYREF
  int v23; // [rsp+34h] [rbp-1Ch] BYREF
  __int128 v24; // [rsp+38h] [rbp-18h] BYREF

  v9 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 224))(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v10 = 0;
  if ( v9 >= 0 )
  {
    if ( a3 == 4 )
    {
      v11 = *a2;
      v22 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v11 + 240))(a2, &v22);
      if ( v9 < 0 )
        goto LABEL_35;
      if ( v22 >= *(_DWORD *)(a1 + 60) )
      {
        a3 = 0;
        goto LABEL_6;
      }
    }
    else
    {
      if ( !a3 )
        goto LABEL_6;
      if ( a3 != 1 )
      {
        if ( a3 == 2 )
        {
LABEL_6:
          while ( v10 < *(_DWORD *)(a1 + 60) )
          {
            v23 = 0;
            v12 = *(_QWORD *)(a1 + 48) + 40LL * v10;
            v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, int *))(*a2 + 40))(a2, v12, v12 + 16, &v23);
            if ( v9 < 0 )
              goto LABEL_35;
            if ( !v23 )
              goto LABEL_30;
            ++v10;
          }
          if ( a3 != 2 )
            goto LABEL_34;
          v20 = *a2;
          v23 = 0;
          v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(v20 + 240))(a2, &v23);
          if ( v9 >= 0 )
          {
            if ( v23 != *(_DWORD *)(a1 + 60) )
            {
LABEL_30:
              *a6 = 0;
              goto LABEL_35;
            }
            goto LABEL_34;
          }
        }
        else
        {
          if ( a3 == 3 )
          {
            for ( i = 0; i < *(_DWORD *)(a1 + 60); ++i )
            {
              v14 = *a2;
              v22 = 0;
              if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD))(v14 + 24))(
                     a2,
                     *(_QWORD *)(a1 + 48) + 40LL * i,
                     0) >= 0 )
              {
                v15 = *(_QWORD *)(a1 + 48) + 40LL * i;
                v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64, unsigned int *))(*a2 + 40))(
                       a2,
                       v15,
                       v15 + 16,
                       &v22);
                if ( v9 < 0 )
                  goto LABEL_35;
                if ( !v22 )
                {
LABEL_20:
                  *a6 = 0;
                  goto LABEL_35;
                }
              }
            }
            goto LABEL_34;
          }
          v9 = -2147024809;
        }
LABEL_35:
        (*(void (__fastcall **)(__int64 *))(*a2 + 232))(a2);
        goto LABEL_36;
      }
    }
    v16 = *a2;
    v22 = 0;
    v24 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v16 + 240))(a2, &v22);
    if ( v9 >= 0 )
    {
      for ( j = 0; j < v22; ++j )
      {
        v18 = *a2;
        v23 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int128 *, _QWORD))(v18 + 248))(a2, j, &v24, 0);
        if ( v9 < 0 )
          goto LABEL_35;
        Item = CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(a1, &v24);
        if ( !Item )
          goto LABEL_20;
        v9 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64, int *))(*a2 + 40))(a2, &v24, Item, &v23);
        if ( v9 < 0 )
          goto LABEL_35;
        if ( !v23 )
          goto LABEL_20;
      }
LABEL_34:
      *a6 = 1;
      goto LABEL_35;
    }
    goto LABEL_35;
  }
LABEL_36:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003503c  mov     [rsp-38h+arg_10], rbx
0x180035041  push    rbp
0x180035042  push    rsi
0x180035043  push    rdi
0x180035044  push    r12
0x180035046  push    r13
0x180035048  push    r14
0x18003504a  push    r15
0x18003504c  mov     rbp, rsp
0x18003504f  sub     rsp, 50h
0x180035053  mov     rax, cs:__security_cookie
0x18003505a  xor     rax, rsp
0x18003505d  mov     [rbp+var_8], rax
0x180035061  mov     rax, [rdx]
0x180035064  mov     r14, rcx
0x180035067  mov     rsi, [rbp+arg_28]
0x18003506b  mov     rcx, rdx
0x18003506e  mov     r15d, r8d
0x180035071  mov     rdi, rdx
0x180035074  mov     rax, [rax+0E0h]
0x18003507b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035080  lea     rcx, [r14+8]; lpCriticalSection
0x180035084  mov     ebx, eax
0x180035086  call    cs:__imp_EnterCriticalSection
0x18003508c  xor     r12d, r12d
0x18003508f  test    ebx, ebx
0x180035091  js      loc_1800352BA
0x180035097  cmp     r15d, 4
0x18003509b  jnz     loc_180035125
0x1800350a1  mov     rax, [rdi]
0x1800350a4  lea     rdx, [rbp+var_20]
0x1800350a8  mov     rcx, rdi
0x1800350ab  mov     [rbp+var_20], r12d
0x1800350af  mov     rax, [rax+0F0h]
0x1800350b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800350bb  mov     ebx, eax
0x1800350bd  test    eax, eax
0x1800350bf  js      loc_1800352A8
0x1800350c5  mov     eax, [r14+3Ch]
0x1800350c9  cmp     [rbp+var_20], eax
0x1800350cc  jb      loc_1800351C2
0x1800350d2  mov     r15d, r12d
0x1800350d5  cmp     r12d, [r14+3Ch]
0x1800350d9  jnb     loc_180035270
0x1800350df  mov     eax, r12d
0x1800350e2  lea     r9, [rbp+var_1C]
0x1800350e6  mov     [rbp+var_1C], 0
0x1800350ed  lea     rcx, [rax+rax*4]
0x1800350f1  mov     rax, [r14+30h]
0x1800350f5  lea     rdx, [rax+rcx*8]
0x1800350f9  mov     rax, [rdi]
0x1800350fc  lea     r8, [rdx+10h]
0x180035100  mov     rcx, rdi
0x180035103  mov     rax, [rax+28h]
0x180035107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003510c  mov     ebx, eax
0x18003510e  test    eax, eax
0x180035110  js      loc_1800352A8
0x180035116  cmp     [rbp+var_1C], 0
0x18003511a  jz      loc_180035268
0x180035120  inc     r12d
0x180035123  jmp     short loc_1800350D5
0x180035125  mov     ecx, r15d
0x180035128  test    r15d, r15d
0x18003512b  jz      short loc_1800350D5
0x18003512d  sub     ecx, 1
0x180035130  jz      loc_1800351C2
0x180035136  sub     ecx, 1
0x180035139  jz      short loc_1800350D5
0x18003513b  cmp     ecx, 1
0x18003513e  jz      short loc_18003514A
0x180035140  mov     ebx, 80070057h
0x180035145  jmp     loc_1800352A8
0x18003514a  mov     r15d, r12d
0x18003514d  cmp     r15d, [r14+3Ch]
0x180035151  jnb     loc_1800352A2
0x180035157  mov     rcx, [rdi]
0x18003515a  xor     r8d, r8d
0x18003515d  mov     eax, r15d
0x180035160  mov     [rbp+var_20], r12d
0x180035164  lea     r12, [rax+rax*4]
0x180035168  mov     rax, [r14+30h]
0x18003516c  lea     rdx, [rax+r12*8]
0x180035170  mov     rax, [rcx+18h]
0x180035174  mov     rcx, rdi
0x180035177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003517c  test    eax, eax
0x18003517e  js      short loc_1800351BA
0x180035180  mov     rax, [r14+30h]
0x180035184  lea     r9, [rbp+var_20]
0x180035188  mov     rcx, rdi
0x18003518b  lea     rdx, [rax+r12*8]
0x18003518f  mov     rax, [rdi]
0x180035192  lea     r8, [rdx+10h]
0x180035196  mov     rax, [rax+28h]
0x18003519a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003519f  xor     r12d, r12d
0x1800351a2  mov     ebx, eax
0x1800351a4  test    eax, eax
0x1800351a6  js      loc_1800352A8
0x1800351ac  cmp     [rbp+var_20], r12d
0x1800351b0  jnz     short loc_1800351BD
0x1800351b2  mov     [rsi], r12d
0x1800351b5  jmp     loc_1800352A8
0x1800351ba  xor     r12d, r12d
0x1800351bd  inc     r15d
0x1800351c0  jmp     short loc_18003514D
0x1800351c2  mov     rax, [rdi]
0x1800351c5  lea     rdx, [rbp+var_20]
0x1800351c9  xorps   xmm0, xmm0
0x1800351cc  mov     [rbp+var_20], r12d
0x1800351d0  mov     rcx, rdi
0x1800351d3  movups  [rbp+var_18], xmm0
0x1800351d7  mov     rax, [rax+0F0h]
0x1800351de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351e3  mov     ebx, eax
0x1800351e5  test    eax, eax
0x1800351e7  js      loc_1800352A8
0x1800351ed  mov     r15d, r12d
0x1800351f0  cmp     r15d, [rbp+var_20]
0x1800351f4  jnb     loc_1800352A2
0x1800351fa  mov     rax, [rdi]
0x1800351fd  lea     r8, [rbp+var_18]
0x180035201  xor     r9d, r9d
0x180035204  mov     [rbp+var_1C], r12d
0x180035208  mov     edx, r15d
0x18003520b  mov     rcx, rdi
0x18003520e  mov     rax, [rax+0F8h]
0x180035215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003521a  mov     ebx, eax
0x18003521c  test    eax, eax
0x18003521e  js      loc_1800352A8
0x180035224  lea     rdx, [rbp+var_18]
0x180035228  mov     rcx, r14
0x18003522b  call    ?_FindItem@?$CMFAttributesImpl@UIMFActivate@@VCMFCSLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFActivate,CMFCSLock>::_FindItem(_GUID const &)
0x180035230  mov     r8, rax
0x180035233  test    rax, rax
0x180035236  jz      loc_1800351B2
0x18003523c  mov     rcx, [rdi]
0x18003523f  lea     r9, [rbp+var_1C]
0x180035243  lea     rdx, [rbp+var_18]
0x180035247  mov     rax, [rcx+28h]
0x18003524b  mov     rcx, rdi
0x18003524e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035253  mov     ebx, eax
0x180035255  test    eax, eax
0x180035257  js      short loc_1800352A8
0x180035259  cmp     [rbp+var_1C], r12d
0x18003525d  jz      loc_1800351B2
0x180035263  inc     r15d
0x180035266  jmp     short loc_1800351F0
0x180035268  mov     dword ptr [rsi], 0
0x18003526e  jmp     short loc_1800352A8
0x180035270  cmp     r15d, 2
0x180035274  jnz     short loc_1800352A2
0x180035276  mov     rax, [rdi]
0x180035279  lea     rdx, [rbp+var_1C]
0x18003527d  mov     rcx, rdi
0x180035280  mov     [rbp+var_1C], 0
0x180035287  mov     rax, [rax+0F0h]
0x18003528e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035293  mov     ebx, eax
0x180035295  test    eax, eax
0x180035297  js      short loc_1800352A8
0x180035299  mov     eax, [r14+3Ch]
0x18003529d  cmp     [rbp+var_1C], eax
0x1800352a0  jnz     short loc_180035268
0x1800352a2  mov     dword ptr [rsi], 1
0x1800352a8  mov     rax, [rdi]
0x1800352ab  mov     rcx, rdi
0x1800352ae  mov     rax, [rax+0E8h]
0x1800352b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800352ba  lea     rcx, [r14+8]; lpCriticalSection
0x1800352be  call    cs:__imp_LeaveCriticalSection
0x1800352c4  mov     eax, ebx
0x1800352c6  mov     rcx, [rbp+var_8]
0x1800352ca  xor     rcx, rsp; StackCookie
0x1800352cd  call    __security_check_cookie
0x1800352d2  mov     rbx, [rsp+50h+arg_10]
0x1800352da  add     rsp, 50h
0x1800352de  pop     r15
0x1800352e0  pop     r14
0x1800352e2  pop     r13
0x1800352e4  pop     r12
0x1800352e6  pop     rdi
0x1800352e7  pop     rsi
0x1800352e8  pop     rbp
0x1800352e9  retn
```

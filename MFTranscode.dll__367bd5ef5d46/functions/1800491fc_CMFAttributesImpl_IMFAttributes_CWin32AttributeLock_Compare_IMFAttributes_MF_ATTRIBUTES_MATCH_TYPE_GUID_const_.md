# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_Compare(IMFAttributes *,_MF_ATTRIBUTES_MATCH_TYPE,_GUID const *,uint,int *)

- ea: `0x1800491fc`
- end: `0x1800494aa`
- name: `?_Compare@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@QEAAJPEAUIMFAttributes@@W4_MF_ATTRIBUTES_MATCH_TYPE@@PEBU_GUID@@IPEAH@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180046a10`

## callees

- `0x1800076c0`
- `0x1800174c0`
- `0x1800491fc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004947e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004947e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049246`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049246`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_Compare(
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
        Item = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, &v24);
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
0x1800491fc  mov     [rsp-38h+arg_10], rbx
0x180049201  push    rbp
0x180049202  push    rsi
0x180049203  push    rdi
0x180049204  push    r12
0x180049206  push    r13
0x180049208  push    r14
0x18004920a  push    r15
0x18004920c  mov     rbp, rsp
0x18004920f  sub     rsp, 50h
0x180049213  mov     rax, cs:__security_cookie
0x18004921a  xor     rax, rsp
0x18004921d  mov     [rbp+var_8], rax
0x180049221  mov     rax, [rdx]
0x180049224  mov     r14, rcx
0x180049227  mov     rsi, [rbp+arg_28]
0x18004922b  mov     rcx, rdx
0x18004922e  mov     r15d, r8d
0x180049231  mov     rdi, rdx
0x180049234  mov     rax, [rax+0E0h]
0x18004923b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049240  lea     rcx, [r14+8]; lpCriticalSection
0x180049244  mov     ebx, eax
0x180049246  call    cs:__imp_EnterCriticalSection
0x18004924c  xor     r12d, r12d
0x18004924f  test    ebx, ebx
0x180049251  js      loc_18004947A
0x180049257  cmp     r15d, 4
0x18004925b  jnz     loc_1800492E5
0x180049261  mov     rax, [rdi]
0x180049264  lea     rdx, [rbp+var_20]
0x180049268  mov     rcx, rdi
0x18004926b  mov     [rbp+var_20], r12d
0x18004926f  mov     rax, [rax+0F0h]
0x180049276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004927b  mov     ebx, eax
0x18004927d  test    eax, eax
0x18004927f  js      loc_180049468
0x180049285  mov     eax, [r14+3Ch]
0x180049289  cmp     [rbp+var_20], eax
0x18004928c  jb      loc_180049382
0x180049292  mov     r15d, r12d
0x180049295  cmp     r12d, [r14+3Ch]
0x180049299  jnb     loc_180049430
0x18004929f  mov     eax, r12d
0x1800492a2  lea     r9, [rbp+var_1C]
0x1800492a6  mov     [rbp+var_1C], 0
0x1800492ad  lea     rcx, [rax+rax*4]
0x1800492b1  mov     rax, [r14+30h]
0x1800492b5  lea     rdx, [rax+rcx*8]
0x1800492b9  mov     rax, [rdi]
0x1800492bc  lea     r8, [rdx+10h]
0x1800492c0  mov     rcx, rdi
0x1800492c3  mov     rax, [rax+28h]
0x1800492c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800492cc  mov     ebx, eax
0x1800492ce  test    eax, eax
0x1800492d0  js      loc_180049468
0x1800492d6  cmp     [rbp+var_1C], 0
0x1800492da  jz      loc_180049428
0x1800492e0  inc     r12d
0x1800492e3  jmp     short loc_180049295
0x1800492e5  mov     ecx, r15d
0x1800492e8  test    r15d, r15d
0x1800492eb  jz      short loc_180049295
0x1800492ed  sub     ecx, 1
0x1800492f0  jz      loc_180049382
0x1800492f6  sub     ecx, 1
0x1800492f9  jz      short loc_180049295
0x1800492fb  cmp     ecx, 1
0x1800492fe  jz      short loc_18004930A
0x180049300  mov     ebx, 80070057h
0x180049305  jmp     loc_180049468
0x18004930a  mov     r15d, r12d
0x18004930d  cmp     r15d, [r14+3Ch]
0x180049311  jnb     loc_180049462
0x180049317  mov     rcx, [rdi]
0x18004931a  xor     r8d, r8d
0x18004931d  mov     eax, r15d
0x180049320  mov     [rbp+var_20], r12d
0x180049324  lea     r12, [rax+rax*4]
0x180049328  mov     rax, [r14+30h]
0x18004932c  lea     rdx, [rax+r12*8]
0x180049330  mov     rax, [rcx+18h]
0x180049334  mov     rcx, rdi
0x180049337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004933c  test    eax, eax
0x18004933e  js      short loc_18004937A
0x180049340  mov     rax, [r14+30h]
0x180049344  lea     r9, [rbp+var_20]
0x180049348  mov     rcx, rdi
0x18004934b  lea     rdx, [rax+r12*8]
0x18004934f  mov     rax, [rdi]
0x180049352  lea     r8, [rdx+10h]
0x180049356  mov     rax, [rax+28h]
0x18004935a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004935f  xor     r12d, r12d
0x180049362  mov     ebx, eax
0x180049364  test    eax, eax
0x180049366  js      loc_180049468
0x18004936c  cmp     [rbp+var_20], r12d
0x180049370  jnz     short loc_18004937D
0x180049372  mov     [rsi], r12d
0x180049375  jmp     loc_180049468
0x18004937a  xor     r12d, r12d
0x18004937d  inc     r15d
0x180049380  jmp     short loc_18004930D
0x180049382  mov     rax, [rdi]
0x180049385  lea     rdx, [rbp+var_20]
0x180049389  xorps   xmm0, xmm0
0x18004938c  mov     [rbp+var_20], r12d
0x180049390  mov     rcx, rdi
0x180049393  movups  [rbp+var_18], xmm0
0x180049397  mov     rax, [rax+0F0h]
0x18004939e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493a3  mov     ebx, eax
0x1800493a5  test    eax, eax
0x1800493a7  js      loc_180049468
0x1800493ad  mov     r15d, r12d
0x1800493b0  cmp     r15d, [rbp+var_20]
0x1800493b4  jnb     loc_180049462
0x1800493ba  mov     rax, [rdi]
0x1800493bd  lea     r8, [rbp+var_18]
0x1800493c1  xor     r9d, r9d
0x1800493c4  mov     [rbp+var_1C], r12d
0x1800493c8  mov     edx, r15d
0x1800493cb  mov     rcx, rdi
0x1800493ce  mov     rax, [rax+0F8h]
0x1800493d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800493da  mov     ebx, eax
0x1800493dc  test    eax, eax
0x1800493de  js      loc_180049468
0x1800493e4  lea     rdx, [rbp+var_18]
0x1800493e8  mov     rcx, r14
0x1800493eb  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x1800493f0  mov     r8, rax
0x1800493f3  test    rax, rax
0x1800493f6  jz      loc_180049372
0x1800493fc  mov     rcx, [rdi]
0x1800493ff  lea     r9, [rbp+var_1C]
0x180049403  lea     rdx, [rbp+var_18]
0x180049407  mov     rax, [rcx+28h]
0x18004940b  mov     rcx, rdi
0x18004940e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049413  mov     ebx, eax
0x180049415  test    eax, eax
0x180049417  js      short loc_180049468
0x180049419  cmp     [rbp+var_1C], r12d
0x18004941d  jz      loc_180049372
0x180049423  inc     r15d
0x180049426  jmp     short loc_1800493B0
0x180049428  mov     dword ptr [rsi], 0
0x18004942e  jmp     short loc_180049468
0x180049430  cmp     r15d, 2
0x180049434  jnz     short loc_180049462
0x180049436  mov     rax, [rdi]
0x180049439  lea     rdx, [rbp+var_1C]
0x18004943d  mov     rcx, rdi
0x180049440  mov     [rbp+var_1C], 0
0x180049447  mov     rax, [rax+0F0h]
0x18004944e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049453  mov     ebx, eax
0x180049455  test    eax, eax
0x180049457  js      short loc_180049468
0x180049459  mov     eax, [r14+3Ch]
0x18004945d  cmp     [rbp+var_1C], eax
0x180049460  jnz     short loc_180049428
0x180049462  mov     dword ptr [rsi], 1
0x180049468  mov     rax, [rdi]
0x18004946b  mov     rcx, rdi
0x18004946e  mov     rax, [rax+0E8h]
0x180049475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004947a  lea     rcx, [r14+8]; lpCriticalSection
0x18004947e  call    cs:__imp_LeaveCriticalSection
0x180049484  mov     eax, ebx
0x180049486  mov     rcx, [rbp+var_8]
0x18004948a  xor     rcx, rsp; StackCookie
0x18004948d  call    __security_check_cookie
0x180049492  mov     rbx, [rsp+50h+arg_10]
0x18004949a  add     rsp, 50h
0x18004949e  pop     r15
0x1800494a0  pop     r14
0x1800494a2  pop     r13
0x1800494a4  pop     r12
0x1800494a6  pop     rdi
0x1800494a7  pop     rsi
0x1800494a8  pop     rbp
0x1800494a9  retn
```

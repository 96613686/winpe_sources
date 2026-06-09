# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_Compare(IMFAttributes *,_MF_ATTRIBUTES_MATCH_TYPE,_GUID const *,uint,int *)

- ea: `0x18007048c`
- end: `0x180070751`
- name: `?_Compare@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@QEAAJPEAUIMFAttributes@@W4_MF_ATTRIBUTES_MATCH_TYPE@@PEBU_GUID@@IPEAH@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006c600`

## callees

- `0x1800445e4`
- `0x18004d320`
- `0x18007048c`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007071e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007071e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800704d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800704d7`

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
0x18007048c  mov     [rsp-38h+arg_10], rbx
0x180070491  push    rbp
0x180070492  push    rsi
0x180070493  push    rdi
0x180070494  push    r12
0x180070496  push    r13
0x180070498  push    r14
0x18007049a  push    r15
0x18007049c  mov     rbp, rsp
0x18007049f  sub     rsp, 50h
0x1800704a3  mov     rax, cs:__security_cookie
0x1800704aa  xor     rax, rsp
0x1800704ad  mov     [rbp+var_8], rax
0x1800704b1  mov     rax, [rdx]
0x1800704b4  mov     r14, rcx
0x1800704b7  mov     rsi, [rbp+arg_28]
0x1800704bb  mov     rcx, rdx
0x1800704be  mov     r15d, r8d
0x1800704c1  mov     rdi, rdx
0x1800704c4  mov     rax, [rax+0E0h]
0x1800704cb  call    cs:__guard_dispatch_icall_fptr
0x1800704d1  lea     rcx, [r14+8]; lpCriticalSection
0x1800704d5  mov     ebx, eax
0x1800704d7  call    cs:__imp_EnterCriticalSection
0x1800704de  nop     dword ptr [rax+rax+00h]
0x1800704e3  xor     r12d, r12d
0x1800704e6  test    ebx, ebx
0x1800704e8  js      loc_18007071A
0x1800704ee  cmp     r15d, 4
0x1800704f2  jnz     loc_18007057E
0x1800704f8  mov     rax, [rdi]
0x1800704fb  lea     rdx, [rbp+var_20]
0x1800704ff  mov     rcx, rdi
0x180070502  mov     [rbp+var_20], r12d
0x180070506  mov     rax, [rax+0F0h]
0x18007050d  call    cs:__guard_dispatch_icall_fptr
0x180070513  mov     ebx, eax
0x180070515  test    eax, eax
0x180070517  js      loc_180070707
0x18007051d  mov     eax, [r14+3Ch]
0x180070521  cmp     [rbp+var_20], eax
0x180070524  jb      loc_18007061D
0x18007052a  mov     r15d, r12d
0x18007052d  cmp     r12d, [r14+3Ch]
0x180070531  jnb     loc_1800706CE
0x180070537  mov     eax, r12d
0x18007053a  lea     r9, [rbp+var_1C]
0x18007053e  mov     [rbp+var_1C], 0
0x180070545  lea     rcx, [rax+rax*4]
0x180070549  mov     rax, [r14+30h]
0x18007054d  lea     rdx, [rax+rcx*8]
0x180070551  mov     rax, [rdi]
0x180070554  lea     r8, [rdx+10h]
0x180070558  mov     rcx, rdi
0x18007055b  mov     rax, [rax+28h]
0x18007055f  call    cs:__guard_dispatch_icall_fptr
0x180070565  mov     ebx, eax
0x180070567  test    eax, eax
0x180070569  js      loc_180070707
0x18007056f  cmp     [rbp+var_1C], 0
0x180070573  jz      loc_1800706C6
0x180070579  inc     r12d
0x18007057c  jmp     short loc_18007052D
0x18007057e  mov     ecx, r15d
0x180070581  test    r15d, r15d
0x180070584  jz      short loc_18007052D
0x180070586  sub     ecx, 1
0x180070589  jz      loc_18007061D
0x18007058f  sub     ecx, 1
0x180070592  jz      short loc_18007052D
0x180070594  cmp     ecx, 1
0x180070597  jz      short loc_1800705A3
0x180070599  mov     ebx, 80070057h
0x18007059e  jmp     loc_180070707
0x1800705a3  mov     r15d, r12d
0x1800705a6  cmp     r15d, [r14+3Ch]
0x1800705aa  jnb     loc_180070701
0x1800705b0  mov     rcx, [rdi]
0x1800705b3  xor     r8d, r8d
0x1800705b6  mov     eax, r15d
0x1800705b9  mov     [rbp+var_20], r12d
0x1800705bd  lea     r12, [rax+rax*4]
0x1800705c1  mov     rax, [r14+30h]
0x1800705c5  lea     rdx, [rax+r12*8]
0x1800705c9  mov     rax, [rcx+18h]
0x1800705cd  mov     rcx, rdi
0x1800705d0  call    cs:__guard_dispatch_icall_fptr
0x1800705d6  test    eax, eax
0x1800705d8  js      short loc_180070615
0x1800705da  mov     rax, [r14+30h]
0x1800705de  lea     r9, [rbp+var_20]
0x1800705e2  mov     rcx, rdi
0x1800705e5  lea     rdx, [rax+r12*8]
0x1800705e9  mov     rax, [rdi]
0x1800705ec  lea     r8, [rdx+10h]
0x1800705f0  mov     rax, [rax+28h]
0x1800705f4  call    cs:__guard_dispatch_icall_fptr
0x1800705fa  xor     r12d, r12d
0x1800705fd  mov     ebx, eax
0x1800705ff  test    eax, eax
0x180070601  js      loc_180070707
0x180070607  cmp     [rbp+var_20], r12d
0x18007060b  jnz     short loc_180070618
0x18007060d  mov     [rsi], r12d
0x180070610  jmp     loc_180070707
0x180070615  xor     r12d, r12d
0x180070618  inc     r15d
0x18007061b  jmp     short loc_1800705A6
0x18007061d  mov     rax, [rdi]
0x180070620  lea     rdx, [rbp+var_20]
0x180070624  xorps   xmm0, xmm0
0x180070627  mov     [rbp+var_20], r12d
0x18007062b  mov     rcx, rdi
0x18007062e  movups  [rbp+var_18], xmm0
0x180070632  mov     rax, [rax+0F0h]
0x180070639  call    cs:__guard_dispatch_icall_fptr
0x18007063f  mov     ebx, eax
0x180070641  test    eax, eax
0x180070643  js      loc_180070707
0x180070649  mov     r15d, r12d
0x18007064c  cmp     r15d, [rbp+var_20]
0x180070650  jnb     loc_180070701
0x180070656  mov     rax, [rdi]
0x180070659  lea     r8, [rbp+var_18]
0x18007065d  xor     r9d, r9d
0x180070660  mov     [rbp+var_1C], r12d
0x180070664  mov     edx, r15d
0x180070667  mov     rcx, rdi
0x18007066a  mov     rax, [rax+0F8h]
0x180070671  call    cs:__guard_dispatch_icall_fptr
0x180070677  mov     ebx, eax
0x180070679  test    eax, eax
0x18007067b  js      loc_180070707
0x180070681  lea     rdx, [rbp+var_18]
0x180070685  mov     rcx, r14
0x180070688  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18007068d  mov     r8, rax
0x180070690  test    rax, rax
0x180070693  jz      loc_18007060D
0x180070699  mov     rcx, [rdi]
0x18007069c  lea     r9, [rbp+var_1C]
0x1800706a0  lea     rdx, [rbp+var_18]
0x1800706a4  mov     rax, [rcx+28h]
0x1800706a8  mov     rcx, rdi
0x1800706ab  call    cs:__guard_dispatch_icall_fptr
0x1800706b1  mov     ebx, eax
0x1800706b3  test    eax, eax
0x1800706b5  js      short loc_180070707
0x1800706b7  cmp     [rbp+var_1C], r12d
0x1800706bb  jz      loc_18007060D
0x1800706c1  inc     r15d
0x1800706c4  jmp     short loc_18007064C
0x1800706c6  mov     dword ptr [rsi], 0
0x1800706cc  jmp     short loc_180070707
0x1800706ce  cmp     r15d, 2
0x1800706d2  jnz     short loc_180070701
0x1800706d4  mov     rax, [rdi]
0x1800706d7  lea     rdx, [rbp+var_1C]
0x1800706db  mov     rcx, rdi
0x1800706de  mov     [rbp+var_1C], 0
0x1800706e5  mov     rax, [rax+0F0h]
0x1800706ec  call    cs:__guard_dispatch_icall_fptr
0x1800706f2  mov     ebx, eax
0x1800706f4  test    eax, eax
0x1800706f6  js      short loc_180070707
0x1800706f8  mov     eax, [r14+3Ch]
0x1800706fc  cmp     [rbp+var_1C], eax
0x1800706ff  jnz     short loc_1800706C6
0x180070701  mov     dword ptr [rsi], 1
0x180070707  mov     rax, [rdi]
0x18007070a  mov     rcx, rdi
0x18007070d  mov     rax, [rax+0E8h]
0x180070714  call    cs:__guard_dispatch_icall_fptr
0x18007071a  lea     rcx, [r14+8]; lpCriticalSection
0x18007071e  call    cs:__imp_LeaveCriticalSection
0x180070725  nop     dword ptr [rax+rax+00h]
0x18007072a  mov     eax, ebx
0x18007072c  mov     rcx, [rbp+var_8]
0x180070730  xor     rcx, rsp; StackCookie
0x180070733  call    __security_check_cookie
0x180070738  mov     rbx, [rsp+50h+arg_10]
0x180070740  add     rsp, 50h
0x180070744  pop     r15
0x180070746  pop     r14
0x180070748  pop     r13
0x18007074a  pop     r12
0x18007074c  pop     rdi
0x18007074d  pop     rsi
0x18007074e  pop     rbp
0x18007074f  retn
```

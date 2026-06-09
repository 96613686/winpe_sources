# CApplicationManager::UpdateActiveMediaAppForSession(CApplication *,int)

- ea: `0x18001bf24`
- end: `0x18001c1a2`
- name: `?UpdateActiveMediaAppForSession@CApplicationManager@@QEAAXPEAVCApplication@@H@Z`
- size: `638`
- prototype: `void __fastcall(CApplicationManager *this, struct CApplication *, int)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18001bd40`
- `0x1800281f0`
- `0x18003c61c`
- `0x18003cadc`

## callees

- `0x180007610`
- `0x18000a384`
- `0x18001bf24`
- `0x18001c1a8`
- `0x18001c21c`
- `0x180031550`
- `0x1800327ec`
- `0x1800422b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c006`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c01f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf41`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bf9e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c006`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c01f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c09a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c0ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c0e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c125`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c133`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c141`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c09a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c0ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c0e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c125`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c133`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c141`

## pseudocode

```c
void __fastcall CApplicationManager::UpdateActiveMediaAppForSession(
        CApplicationManager *this,
        struct CApplication *a2,
        int a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // r14
  unsigned int v6; // ebp
  int v7; // edi
  _QWORD *i; // rax
  __int64 v9; // rcx
  int v10; // edi
  _QWORD *j; // rax
  __int64 v12; // rcx
  int v13; // ebx
  int HasPlayToStreams; // eax
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  __int64 v16; // rcx
  unsigned __int64 k; // rdx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdi
  struct TSSession *v21; // rdi
  __int64 trivial_8; // rax
  __int64 v23; // r8
  int v24; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v26; // [rsp+50h] [rbp+8h]
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+58h] [rbp+10h]
  struct _RTL_CRITICAL_SECTION *v28; // [rsp+68h] [rbp+20h]

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v27 = v5;
  v6 = *((_DWORD *)a2 + 53);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  v7 = 0;
  for ( i = (_QWORD *)*((_QWORD *)a2 + 9); i; i = (_QWORD *)*i )
  {
    v9 = i[2];
    if ( !*(_DWORD *)(v9 + 416) && *(_DWORD *)(v9 + 496) )
    {
      v7 = 1;
      break;
    }
  }
  if ( a2 != (struct CApplication *)-32LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  if ( v7 && *((_DWORD *)a2 + 52) )
    goto LABEL_46;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  v10 = 0;
  for ( j = (_QWORD *)*((_QWORD *)a2 + 9); j; j = (_QWORD *)*j )
  {
    v12 = j[2];
    if ( !*(_DWORD *)(v12 + 416) && *(_DWORD *)(v12 + 500) )
    {
      v10 = 1;
      break;
    }
  }
  if ( a2 != (struct CApplication *)-32LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 32));
  if ( v10 && (unsigned int)CApplication::IsBackgroundAudioCapable(a2) )
LABEL_46:
    v13 = 1;
  else
    v13 = 0;
  if ( a3 || (HasPlayToStreams = CApplication::HasPlayToStreams(a2)) != 0 )
    HasPlayToStreams = 1;
  if ( !v13 || HasPlayToStreams )
  {
    v15 = (struct _RTL_CRITICAL_SECTION *)((char *)g_ApplicationManager + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_ApplicationManager + 32));
    v28 = v15;
    v26 = v6;
    EnterCriticalSection(&stru_180064458);
    v16 = 0xCBF29CE484222325uLL;
    for ( k = 0; k < 4; ++k )
      v16 = 0x100000001B3LL * (*((unsigned __int8 *)&v26 + k) ^ (unsigned __int64)v16);
    v18 = 2 * (qword_1800644B0 & v16);
    v19 = *(_QWORD *)(qword_180064498 + 8 * v18 + 8);
    if ( v19 == qword_180064488 )
    {
LABEL_29:
      v19 = 0;
    }
    else
    {
      while ( v6 != *(_DWORD *)(v19 + 16) )
      {
        if ( v19 == *(_QWORD *)(qword_180064498 + 8 * v18) )
          goto LABEL_29;
        v19 = *(_QWORD *)(v19 + 8);
      }
    }
    v20 = qword_180064488;
    if ( v19 )
      v20 = v19;
    if ( v20 == qword_180064488 )
    {
      LeaveCriticalSection(&stru_180064458);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x530,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\ts.cpp",
        (const char *)0x80070490LL,
        v24);
    }
    else
    {
      v21 = *(struct TSSession **)(v20 + 24);
      LeaveCriticalSection(&stru_180064458);
      trivial_8 = _std_find_trivial_8(*((_QWORD *)v21 + 6), *((_QWORD *)v21 + 7), a2);
      v23 = *((_QWORD *)v21 + 7);
      if ( trivial_8 != v23 )
      {
        memmove_0((void *)trivial_8, (const void *)(trivial_8 + 8), v23 - (trivial_8 + 8));
        *((_QWORD *)v21 + 7) -= 8LL;
        TsSessionSendAppManagerNotification(v21);
      }
    }
    if ( v15 )
      LeaveCriticalSection(v15);
  }
  else
  {
    TsSessionIdAddActiveMediaApp(v6, a2);
  }
  if ( v5 )
    LeaveCriticalSection(v5);
}

```

## disassembly

```asm
0x18001bf24  mov     [rsp+arg_10], rbx
0x18001bf29  push    rbp
0x18001bf2a  push    rsi
0x18001bf2b  push    rdi
0x18001bf2c  push    r14
0x18001bf2e  push    r15; int
0x18001bf30  sub     rsp, 20h
0x18001bf34  mov     r15d, r8d
0x18001bf37  mov     rsi, rdx
0x18001bf3a  lea     r14, [rcx+20h]
0x18001bf3e  mov     rcx, r14; lpCriticalSection
0x18001bf41  call    cs:__imp_EnterCriticalSection
0x18001bf47  mov     [rsp+48h+arg_8], r14
0x18001bf4c  mov     ebp, [rsi+0D4h]
0x18001bf52  lea     rbx, [rsi+20h]
0x18001bf56  mov     rcx, rbx; lpCriticalSection
0x18001bf59  call    cs:__imp_EnterCriticalSection
0x18001bf5f  xor     edi, edi
0x18001bf61  mov     rax, [rsi+48h]
0x18001bf65  test    rax, rax
0x18001bf68  jz      short loc_18001BF8A
0x18001bf6a  mov     rcx, [rax+10h]
0x18001bf6e  cmp     dword ptr [rcx+1A0h], 0
0x18001bf75  jnz     short loc_18001BF80
0x18001bf77  cmp     dword ptr [rcx+1F0h], 1
0x18001bf7e  jnb     short loc_18001BF85
0x18001bf80  mov     rax, [rax]
0x18001bf83  jmp     short loc_18001BF65
0x18001bf85  mov     edi, 1
0x18001bf8a  test    rbx, rbx
0x18001bf8d  jnz     loc_18001C122
0x18001bf93  test    edi, edi
0x18001bf95  jnz     loc_18001C161
0x18001bf9b  mov     rcx, rbx; lpCriticalSection
0x18001bf9e  call    cs:__imp_EnterCriticalSection
0x18001bfa4  xor     edi, edi
0x18001bfa6  mov     rax, [rsi+48h]
0x18001bfaa  test    rax, rax
0x18001bfad  jz      short loc_18001BFCF
0x18001bfaf  mov     rcx, [rax+10h]
0x18001bfb3  cmp     dword ptr [rcx+1A0h], 0
0x18001bfba  jnz     short loc_18001BFC5
0x18001bfbc  cmp     dword ptr [rcx+1F4h], 1
0x18001bfc3  jnb     short loc_18001BFCA
0x18001bfc5  mov     rax, [rax]
0x18001bfc8  jmp     short loc_18001BFAA
0x18001bfca  mov     edi, 1
0x18001bfcf  test    rbx, rbx
0x18001bfd2  jnz     loc_18001C130
0x18001bfd8  test    edi, edi
0x18001bfda  jnz     loc_18001C170
0x18001bfe0  xor     ebx, ebx
0x18001bfe2  test    r15d, r15d
0x18001bfe5  jz      loc_18001C14C
0x18001bfeb  mov     eax, 1
0x18001bff0  test    ebx, ebx
0x18001bff2  jnz     loc_18001C18A
0x18001bff8  mov     rbx, cs:?g_ApplicationManager@@3PEAVCApplicationManager@@EA; CApplicationManager * g_ApplicationManager
0x18001bfff  add     rbx, 20h ; ' '
0x18001c003  mov     rcx, rbx; lpCriticalSection
0x18001c006  call    cs:__imp_EnterCriticalSection
0x18001c00c  mov     [rsp+48h+arg_18], rbx
0x18001c011  mov     [rsp+48h+arg_0], ebp
0x18001c015  lea     r15, stru_180064458
0x18001c01c  mov     rcx, r15; lpCriticalSection
0x18001c01f  call    cs:__imp_EnterCriticalSection
0x18001c025  mov     rcx, 0CBF29CE484222325h
0x18001c02f  xor     edx, edx
0x18001c031  movzx   eax, byte ptr [rsp+rdx+48h+arg_0]
0x18001c036  xor     rcx, rax
0x18001c039  mov     r8, 100000001B3h
0x18001c043  imul    rcx, r8
0x18001c047  inc     rdx
0x18001c04a  cmp     rdx, 4
0x18001c04e  jb      short loc_18001C031
0x18001c050  and     rcx, cs:qword_1800644B0
0x18001c057  add     rcx, rcx
0x18001c05a  mov     r8, cs:qword_180064498
0x18001c061  mov     rax, [r8+rcx*8+8]
0x18001c066  mov     rdx, cs:qword_180064488
0x18001c06d  cmp     rax, rdx
0x18001c070  jz      short loc_18001C086
0x18001c072  mov     r9, [r8+rcx*8]
0x18001c076  cmp     ebp, [rax+10h]
0x18001c079  jz      short loc_18001C088
0x18001c07b  cmp     rax, r9
0x18001c07e  jz      short loc_18001C086
0x18001c080  mov     rax, [rax+8]
0x18001c084  jmp     short loc_18001C076
0x18001c086  xor     eax, eax
0x18001c088  mov     rdi, rdx
0x18001c08b  test    rax, rax
0x18001c08e  cmovnz  rdi, rax
0x18001c092  mov     rcx, r15; lpCriticalSection
0x18001c095  cmp     rdi, rdx
0x18001c098  jnz     short loc_18001C0E1
0x18001c09a  call    cs:__imp_LeaveCriticalSection
0x18001c0a0  mov     rcx, [rsp+48h]; this
0x18001c0a5  mov     r9d, 80070490h; char *
0x18001c0ab  lea     r8, aClientcoreMult_10; "clientcore\\multimedia\\audiocore\\serv"...
0x18001c0b2  mov     edx, 530h; void *
0x18001c0b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c0bc  nop
0x18001c0bd  test    rbx, rbx
0x18001c0c0  jnz     short loc_18001C13E
0x18001c0c2  test    r14, r14
0x18001c0c5  jz      short loc_18001C0D0
0x18001c0c7  mov     rcx, r14; lpCriticalSection
0x18001c0ca  call    cs:__imp_LeaveCriticalSection
0x18001c0d0  mov     rbx, [rsp+48h+arg_10]
0x18001c0d5  add     rsp, 20h
0x18001c0d9  pop     r15
0x18001c0db  pop     r14
0x18001c0dd  pop     rdi
0x18001c0de  pop     rsi
0x18001c0df  pop     rbp
0x18001c0e0  retn
0x18001c0e1  mov     rdi, [rdi+18h]
0x18001c0e5  call    cs:__imp_LeaveCriticalSection
0x18001c0eb  mov     r8, rsi
0x18001c0ee  mov     rdx, [rdi+38h]
0x18001c0f2  mov     rcx, [rdi+30h]
0x18001c0f6  call    __std_find_trivial_8
0x18001c0fb  mov     r8, [rdi+38h]
0x18001c0ff  cmp     rax, r8
0x18001c102  jz      short loc_18001C0BD
0x18001c104  lea     rdx, [rax+8]; Src
0x18001c108  sub     r8, rdx; Size
0x18001c10b  mov     rcx, rax; void *
0x18001c10e  call    memmove_0
0x18001c113  add     qword ptr [rdi+38h], 0FFFFFFFFFFFFFFF8h
0x18001c118  mov     rcx, rdi; struct TSSession *
0x18001c11b  call    ?TsSessionSendAppManagerNotification@@YAJPEAVTSSession@@@Z; TsSessionSendAppManagerNotification(TSSession *)
0x18001c120  jmp     short loc_18001C0BD
0x18001c122  mov     rcx, rbx; lpCriticalSection
0x18001c125  call    cs:__imp_LeaveCriticalSection
0x18001c12b  jmp     loc_18001BF93
0x18001c130  mov     rcx, rbx; lpCriticalSection
0x18001c133  call    cs:__imp_LeaveCriticalSection
0x18001c139  jmp     loc_18001BFD8
0x18001c13e  mov     rcx, rbx; lpCriticalSection
0x18001c141  call    cs:__imp_LeaveCriticalSection
0x18001c147  jmp     loc_18001C0C2
0x18001c14c  mov     rcx, rsi; this
0x18001c14f  call    ?HasPlayToStreams@CApplication@@QEAAHXZ; CApplication::HasPlayToStreams(void)
0x18001c154  test    eax, eax
0x18001c156  jnz     loc_18001BFEB
0x18001c15c  jmp     loc_18001BFF0
0x18001c161  cmp     dword ptr [rsi+0D0h], 0
0x18001c168  jz      loc_18001BF9B
0x18001c16e  jmp     short loc_18001C180
0x18001c170  mov     rcx, rsi; this
0x18001c173  call    ?IsBackgroundAudioCapable@CApplication@@QEAAHXZ; CApplication::IsBackgroundAudioCapable(void)
0x18001c178  test    eax, eax
0x18001c17a  jz      loc_18001BFE0
0x18001c180  mov     ebx, 1
0x18001c185  jmp     loc_18001BFE2
0x18001c18a  test    eax, eax
0x18001c18c  jnz     loc_18001BFF8
0x18001c192  mov     rdx, rsi; struct CApplication *
0x18001c195  mov     ecx, ebp; unsigned int
0x18001c197  call    ?TsSessionIdAddActiveMediaApp@@YAJKPEAVCApplication@@@Z; TsSessionIdAddActiveMediaApp(ulong,CApplication *)
0x18001c19c  jmp     loc_18001C0C2
```

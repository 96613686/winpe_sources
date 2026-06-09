# UbpmpGetConsumerSids

- ea: `0x1800298c4`
- end: `0x180029bc9`
- name: `UbpmpGetConsumerSids`
- size: `773`
- prototype: `__int64 __usercall@<rax>(PSID pSid1@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f284`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x1800298c4`
- `0x18003eff0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800299ec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180029b0d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800299ec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180029b0d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180029a04`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180029a04`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002994b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180029a8d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180029abe`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002994b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180029a8d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180029abe`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800299b0`
- `ntdll!RtlReleaseSRWLockShared` at `0x180029b3b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180029b85`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800299b0`
- `ntdll!RtlReleaseSRWLockShared` at `0x180029b3b`
- `ntdll!RtlReleaseSRWLockShared` at `0x180029b85`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002990a`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002998d`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002990a`
- `ntdll!RtlAcquireSRWLockShared` at `0x18002998d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b26`

## pseudocode

```c
__int64 __fastcall UbpmpGetConsumerSids(PSID pSid1, int a2, _DWORD *a3, _QWORD *a4, _QWORD *a5)
{
  PSID v5; // rbx
  int v6; // r14d
  int v7; // ebp
  __int64 v8; // r15
  char *v9; // rsi
  unsigned int i; // r12d
  struct _LIST_ENTRY *j; // rdi
  _QWORD *v12; // rbx
  char v13; // r13
  DWORD LengthSid; // eax
  void *v15; // rdx
  __int64 v16; // rbp
  char *v17; // r14
  void *v18; // rcx
  __int64 k; // rbp
  char *v20; // rax
  DWORD LastError; // ebx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  int v26; // [rsp+30h] [rbp-58h]
  int v27; // [rsp+34h] [rbp-54h]
  char *v28; // [rsp+38h] [rbp-50h]

  v5 = pSid1;
  v6 = 0;
  v28 = 0;
  v7 = 0;
  v26 = 0;
  v27 = 0;
  v8 = 0;
  v9 = 0;
  RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
  for ( i = 0; ; ++i )
  {
    if ( i >= 2 )
    {
      *a4 = v9;
      v9 = 0;
      LastError = 0;
      *a3 = v8;
      goto LABEL_36;
    }
    if ( i == 1 )
      break;
LABEL_4:
    for ( j = g_leTaskHostHardeningListHead.Flink; j != &g_leTaskHostHardeningListHead; j = j->Flink )
    {
      if ( EqualSid(v5, j[1].Blink) && j[3].Flink )
      {
        v12 = g_leTaskHostContextListHead;
        v13 = 0;
        if ( g_leTaskHostContextListHead != (_UNKNOWN *)&g_leTaskHostContextListHead )
        {
          while ( 1 )
          {
            if ( (v12[12] & 0x54) == 0x10 )
            {
              RtlAcquireSRWLockShared(v12 + 7);
              if ( *((unsigned __int8 *)v12 + 424) == a2
                && *((char *)v12 + 96) >= 0
                && (v18 = (void *)v12[22]) != 0
                && EqualSid(v18, pSid1) )
              {
                for ( k = 0; (unsigned int)k < *((_DWORD *)v12 + 96); k = (unsigned int)(k + 1) )
                {
                  if ( EqualSid(*(PSID *)(v12[49] + 8 * k), j[3].Flink) )
                  {
                    v13 = 1;
                    break;
                  }
                }
                RtlReleaseSRWLockShared(v12 + 7);
                if ( v13 )
                {
                  v7 = v27;
                  goto LABEL_21;
                }
              }
              else
              {
                RtlReleaseSRWLockShared(v12 + 7);
              }
            }
            v12 = (_QWORD *)*v12;
            if ( v12 == &g_leTaskHostContextListHead )
            {
              v6 = v26;
              v7 = v27;
              break;
            }
          }
        }
        if ( i )
        {
          *(_QWORD *)&v9[8 * v7] = v28;
          LengthSid = GetLengthSid(j[3].Flink);
          v15 = *(void **)&v9[8 * v7];
          v16 = LengthSid;
          if ( !CopySid(LengthSid, v15, j[3].Flink) )
            goto LABEL_35;
          *a5 |= (unsigned __int64)j[2].Flink;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            WPP_SF_Si(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, *a5, j[1].Flink, *a5);
          v17 = &v28[v16];
          v7 = v27 + 1;
          v28 = v17;
          ++v27;
LABEL_21:
          v6 = v26;
        }
        else
        {
          v8 = (unsigned int)(v8 + 1);
          v6 += GetLengthSid(j[3].Flink);
          v26 = v6;
        }
        v5 = pSid1;
      }
    }
  }
  if ( (_DWORD)v8 )
  {
    v20 = (char *)UbpmAlloc((unsigned int)(v6 + 8 * v8));
    v9 = v20;
    if ( !v20 )
    {
LABEL_35:
      LastError = GetLastError();
      goto LABEL_36;
    }
    v28 = &v20[8 * v8];
    goto LABEL_4;
  }
  LastError = 13;
LABEL_36:
  RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
  UBPM_MIDL_user_free(v9, v22, v23, v24);
  return LastError;
}

```

## disassembly

```asm
0x1800298c4  mov     rax, rsp
0x1800298c7  mov     [rax+20h], r9
0x1800298cb  mov     [rax+18h], r8
0x1800298cf  mov     [rax+10h], edx
0x1800298d2  mov     [rax+8], rcx
0x1800298d6  push    rbx
0x1800298d7  push    rbp
0x1800298d8  push    rsi
0x1800298d9  push    rdi
0x1800298da  push    r12
0x1800298dc  push    r13
0x1800298de  push    r14
0x1800298e0  push    r15
0x1800298e2  sub     rsp, 48h
0x1800298e6  mov     rbx, rcx
0x1800298e9  xor     eax, eax
0x1800298eb  xor     r14d, r14d
0x1800298ee  mov     [rsp+88h+var_50], rax
0x1800298f3  xor     ebp, ebp
0x1800298f5  mov     [rsp+88h+var_58], r14d
0x1800298fa  lea     rcx, g_TaskHostContextListLock
0x180029901  mov     [rsp+88h+var_54], ebp
0x180029905  xor     r15d, r15d
0x180029908  xor     esi, esi
0x18002990a  call    cs:__imp_RtlAcquireSRWLockShared
0x180029911  nop     dword ptr [rax+rax+00h]
0x180029916  xor     r12d, r12d
0x180029919  cmp     r12d, 2
0x18002991d  jnb     loc_180029B63
0x180029923  cmp     r12d, 1
0x180029927  jz      loc_180029ADE
0x18002992d  mov     rdi, cs:?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x180029934  lea     rax, ?g_leTaskHostHardeningListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_leTaskHostHardeningListHead
0x18002993b  cmp     rdi, rax
0x18002993e  jz      loc_180029AD6
0x180029944  mov     rdx, [rdi+18h]; pSid2
0x180029948  mov     rcx, rbx; pSid1
0x18002994b  call    cs:__imp_EqualSid
0x180029952  nop     dword ptr [rax+rax+00h]
0x180029957  test    eax, eax
0x180029959  jnz     short loc_180029960
0x18002995b  mov     rdi, [rdi]
0x18002995e  jmp     short loc_180029934
0x180029960  cmp     qword ptr [rdi+30h], 0
0x180029965  jz      short loc_18002995B
0x180029967  mov     rbx, cs:g_leTaskHostContextListHead
0x18002996e  lea     rax, g_leTaskHostContextListHead
0x180029975  xor     r13b, r13b
0x180029978  cmp     rbx, rax
0x18002997b  jz      short loc_1800299D4
0x18002997d  mov     al, [rbx+60h]
0x180029980  and     al, 54h
0x180029982  cmp     al, 10h
0x180029984  jnz     short loc_1800299BC
0x180029986  lea     r14, [rbx+38h]
0x18002998a  mov     rcx, r14
0x18002998d  call    cs:__imp_RtlAcquireSRWLockShared
0x180029994  nop     dword ptr [rax+rax+00h]
0x180029999  movzx   eax, byte ptr [rbx+1A8h]
0x1800299a0  cmp     eax, [rsp+88h+arg_8]
0x1800299a7  jz      loc_180029A6B
0x1800299ad  mov     rcx, r14
0x1800299b0  call    cs:__imp_RtlReleaseSRWLockShared
0x1800299b7  nop     dword ptr [rax+rax+00h]
0x1800299bc  mov     rbx, [rbx]
0x1800299bf  lea     rax, g_leTaskHostContextListHead
0x1800299c6  cmp     rbx, rax
0x1800299c9  jnz     short loc_18002997D
0x1800299cb  mov     r14d, [rsp+88h+var_58]
0x1800299d0  mov     ebp, [rsp+88h+var_54]
0x1800299d4  test    r12d, r12d
0x1800299d7  jz      loc_180029B06
0x1800299dd  mov     r14, [rsp+88h+var_50]
0x1800299e2  mov     ebx, ebp
0x1800299e4  mov     [rsi+rbx*8], r14
0x1800299e8  mov     rcx, [rdi+30h]; pSid
0x1800299ec  call    cs:__imp_GetLengthSid
0x1800299f3  nop     dword ptr [rax+rax+00h]
0x1800299f8  mov     r8, [rdi+30h]; pSourceSid
0x1800299fc  mov     ecx, eax; nDestinationSidLength
0x1800299fe  mov     rdx, [rsi+rbx*8]; pDestinationSid
0x180029a02  mov     ebp, eax
0x180029a04  call    cs:__imp_CopySid
0x180029a0b  nop     dword ptr [rax+rax+00h]
0x180029a10  test    eax, eax
0x180029a12  jz      loc_180029B26
0x180029a18  mov     rax, [rsp+88h+arg_20]
0x180029a20  mov     rcx, [rdi+20h]
0x180029a24  or      [rax], rcx
0x180029a27  mov     r8, [rax]
0x180029a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180029a31  lea     rax, WPP_GLOBAL_Control
0x180029a38  cmp     rcx, rax
0x180029a3b  jz      short loc_180029A47
0x180029a3d  test    byte ptr [rcx+1Ch], 80h
0x180029a41  jnz     loc_180029BA3
0x180029a47  add     r14, rbp
0x180029a4a  mov     ebp, [rsp+88h+var_54]
0x180029a4e  inc     ebp
0x180029a50  mov     [rsp+88h+var_50], r14
0x180029a55  mov     [rsp+88h+var_54], ebp
0x180029a59  mov     r14d, [rsp+88h+var_58]
0x180029a5e  mov     rbx, [rsp+88h+pSid2]
0x180029a66  jmp     loc_18002995B
0x180029a6b  cmp     byte ptr [rbx+60h], 0
0x180029a6f  jl      loc_1800299AD
0x180029a75  mov     rcx, [rbx+0B0h]; pSid1
0x180029a7c  test    rcx, rcx
0x180029a7f  jz      loc_1800299AD
0x180029a85  mov     rdx, [rsp+88h+pSid2]; pSid2
0x180029a8d  call    cs:__imp_EqualSid
0x180029a94  nop     dword ptr [rax+rax+00h]
0x180029a99  test    eax, eax
0x180029a9b  jz      loc_1800299AD
0x180029aa1  xor     ebp, ebp
0x180029aa3  cmp     ebp, [rbx+180h]
0x180029aa9  jnb     loc_180029B82
0x180029aaf  mov     rcx, [rbx+188h]
0x180029ab6  mov     rdx, [rdi+30h]; pSid2
0x180029aba  mov     rcx, [rcx+rbp*8]; pSid1
0x180029abe  call    cs:__imp_EqualSid
0x180029ac5  nop     dword ptr [rax+rax+00h]
0x180029aca  test    eax, eax
0x180029acc  jnz     loc_180029B7F
0x180029ad2  inc     ebp
0x180029ad4  jmp     short loc_180029AA3
0x180029ad6  inc     r12d
0x180029ad9  jmp     loc_180029919
0x180029ade  test    r15d, r15d
0x180029ae1  jz      loc_180029BBF
0x180029ae7  lea     ecx, [r14+r15*8]; Size
0x180029aeb  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x180029af0  mov     rsi, rax
0x180029af3  test    rax, rax
0x180029af6  jz      short loc_180029B26
0x180029af8  lea     rax, [rax+r15*8]
0x180029afc  mov     [rsp+88h+var_50], rax
0x180029b01  jmp     loc_18002992D
0x180029b06  mov     rcx, [rdi+30h]; pSid
0x180029b0a  inc     r15d
0x180029b0d  call    cs:__imp_GetLengthSid
0x180029b14  nop     dword ptr [rax+rax+00h]
0x180029b19  add     r14d, eax
0x180029b1c  mov     [rsp+88h+var_58], r14d
0x180029b21  jmp     loc_180029A5E
0x180029b26  call    cs:__imp_GetLastError
0x180029b2d  nop     dword ptr [rax+rax+00h]
0x180029b32  mov     ebx, eax
0x180029b34  lea     rcx, g_TaskHostContextListLock
0x180029b3b  call    cs:__imp_RtlReleaseSRWLockShared
0x180029b42  nop     dword ptr [rax+rax+00h]
0x180029b47  mov     rcx, rsi
0x180029b4a  call    UBPM_MIDL_user_free
0x180029b4f  mov     eax, ebx
0x180029b51  add     rsp, 48h
0x180029b55  pop     r15
0x180029b57  pop     r14
0x180029b59  pop     r13
0x180029b5b  pop     r12
0x180029b5d  pop     rdi
0x180029b5e  pop     rsi
0x180029b5f  pop     rbp
0x180029b60  pop     rbx
0x180029b61  retn
0x180029b63  mov     rax, [rsp+88h+arg_18]
0x180029b6b  mov     [rax], rsi
0x180029b6e  xor     esi, esi
0x180029b70  mov     rax, [rsp+88h+arg_10]
0x180029b78  xor     ebx, ebx
0x180029b7a  mov     [rax], r15d
0x180029b7d  jmp     short loc_180029B34
0x180029b7f  mov     r13b, 1
0x180029b82  mov     rcx, r14
0x180029b85  call    cs:__imp_RtlReleaseSRWLockShared
0x180029b8c  nop     dword ptr [rax+rax+00h]
0x180029b91  test    r13b, r13b
0x180029b94  jz      loc_1800299BC
0x180029b9a  mov     ebp, [rsp+88h+var_54]
0x180029b9e  jmp     loc_180029A59
0x180029ba3  mov     r9, [rdi+10h]
0x180029ba7  mov     edx, 0E0h
0x180029bac  mov     rcx, [rcx+10h]
0x180029bb0  mov     [rsp+88h+var_68], r8
0x180029bb5  call    WPP_SF_Si
0x180029bba  jmp     loc_180029A47
0x180029bbf  mov     ebx, 0Dh
0x180029bc4  jmp     loc_180029B34
```

# BdeSvcEventTriggerImpersonate(_EVENT_TRIGGER_PARAMETERS *)

- ea: `0x180049204`
- end: `0x180049358`
- name: `?BdeSvcEventTriggerImpersonate@@YAJPEAU_EVENT_TRIGGER_PARAMETERS@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(struct _EVENT_TRIGGER_PARAMETERS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d020`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x180049204`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800492c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800492c3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800492b3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800492b3`

## pseudocode

```c
__int64 __fastcall BdeSvcEventTriggerImpersonate(struct _EVENT_TRIGGER_PARAMETERS *a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // rdx
  DWORD LastError; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    v3 = -2147024809;
    if ( v2 == &WPP_GLOBAL_Control )
      return v3;
    if ( (*((_BYTE *)v2 + 28) & 0x40) == 0 )
      goto LABEL_25;
    v4 = 54;
LABEL_8:
    WPP_SF_d(v2[2], v4, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v3);
LABEL_24:
    v2 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  if ( *((_DWORD *)a1 + 4) )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    {
      WPP_SF_(v2[2], 55, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = 1;
    goto LABEL_25;
  }
  if ( ImpersonateLoggedOnUser(*((HANDLE *)a1 + 1)) )
  {
    v3 = 0;
    *((_DWORD *)a1 + 4) = 1;
    goto LABEL_24;
  }
  LastError = GetLastError();
  v3 = LastError;
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, LastError);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (int)v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  if ( v2 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v2 + 28) & 0x40) == 0 )
    {
LABEL_25:
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
        WPP_SF_(v2[2], 58, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
      return v3;
    }
    v4 = 57;
    goto LABEL_8;
  }
  return v3;
}

```

## disassembly

```asm
0x180049204  push    rbx
0x180049206  push    rbp
0x180049207  push    rsi
0x180049208  push    rdi
0x180049209  sub     rsp, 28h
0x18004920d  mov     rdi, rcx
0x180049210  mov     rcx, cs:WPP_GLOBAL_Control
0x180049217  lea     rsi, WPP_GLOBAL_Control
0x18004921e  lea     rbp, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180049225  cmp     rcx, rsi
0x180049228  jz      short loc_180049248
0x18004922a  test    byte ptr [rcx+1Ch], 20h
0x18004922e  jz      short loc_180049248
0x180049230  mov     rcx, [rcx+10h]
0x180049234  mov     edx, 35h ; '5'
0x180049239  mov     r8, rbp
0x18004923c  call    WPP_SF_
0x180049241  mov     rcx, cs:WPP_GLOBAL_Control
0x180049248  test    rdi, rdi
0x18004924b  jnz     short loc_18004927C
0x18004924d  mov     ebx, 80070057h
0x180049252  cmp     rcx, rsi
0x180049255  jz      loc_18004934C
0x18004925b  test    byte ptr [rcx+1Ch], 40h
0x18004925f  jz      loc_180049330
0x180049265  lea     edx, [rdi+36h]
0x180049268  mov     rcx, [rcx+10h]
0x18004926c  mov     r9d, ebx
0x18004926f  mov     r8, rbp
0x180049272  call    WPP_SF_d
0x180049277  jmp     loc_180049329
0x18004927c  cmp     dword ptr [rdi+10h], 0
0x180049280  jz      short loc_1800492AF
0x180049282  cmp     rcx, rsi
0x180049285  jz      short loc_1800492A5
0x180049287  test    byte ptr [rcx+1Ch], 8
0x18004928b  jz      short loc_1800492A5
0x18004928d  mov     rcx, [rcx+10h]
0x180049291  mov     edx, 37h ; '7'
0x180049296  mov     r8, rbp
0x180049299  call    WPP_SF_
0x18004929e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800492a5  mov     ebx, 1
0x1800492aa  jmp     loc_180049330
0x1800492af  mov     rcx, [rdi+8]; hToken
0x1800492b3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800492ba  nop     dword ptr [rax+rax+00h]
0x1800492bf  test    eax, eax
0x1800492c1  jnz     short loc_180049320
0x1800492c3  call    cs:__imp_GetLastError
0x1800492ca  nop     dword ptr [rax+rax+00h]
0x1800492cf  mov     ebx, eax
0x1800492d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800492d8  cmp     rcx, rsi
0x1800492db  jz      short loc_1800492FE
0x1800492dd  test    byte ptr [rcx+1Ch], 2
0x1800492e1  jz      short loc_1800492FE
0x1800492e3  mov     rcx, [rcx+10h]
0x1800492e7  mov     edx, 38h ; '8'
0x1800492ec  mov     r9d, eax
0x1800492ef  mov     r8, rbp
0x1800492f2  call    WPP_SF_d
0x1800492f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800492fe  test    ebx, ebx
0x180049300  jle     short loc_18004930B
0x180049302  movzx   ebx, bx
0x180049305  or      ebx, 80070000h
0x18004930b  cmp     rcx, rsi
0x18004930e  jz      short loc_18004934C
0x180049310  test    byte ptr [rcx+1Ch], 40h
0x180049314  jz      short loc_180049330
0x180049316  mov     edx, 39h ; '9'
0x18004931b  jmp     loc_180049268
0x180049320  xor     ebx, ebx
0x180049322  mov     dword ptr [rdi+10h], 1
0x180049329  mov     rcx, cs:WPP_GLOBAL_Control
0x180049330  cmp     rcx, rsi
0x180049333  jz      short loc_18004934C
0x180049335  test    byte ptr [rcx+1Ch], 20h
0x180049339  jz      short loc_18004934C
0x18004933b  mov     rcx, [rcx+10h]
0x18004933f  mov     edx, 3Ah ; ':'
0x180049344  mov     r8, rbp
0x180049347  call    WPP_SF_
0x18004934c  mov     eax, ebx
0x18004934e  add     rsp, 28h
0x180049352  pop     rdi
0x180049353  pop     rsi
0x180049354  pop     rbp
0x180049355  pop     rbx
0x180049356  retn
```

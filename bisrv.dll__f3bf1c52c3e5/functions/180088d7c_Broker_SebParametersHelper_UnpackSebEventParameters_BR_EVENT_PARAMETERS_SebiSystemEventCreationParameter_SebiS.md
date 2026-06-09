# Broker::SebParametersHelper::UnpackSebEventParameters(_BR_EVENT_PARAMETERS *,_SebiSystemEventCreationParameter &,_SebiSystemEventFilterParameter &,ulong &)

- ea: `0x180088d7c`
- end: `0x18008902b`
- name: `?UnpackSebEventParameters@SebParametersHelper@Broker@@SAJPEAU_BR_EVENT_PARAMETERS@@AEAU_SebiSystemEventCreationParameter@@AEAU_SebiSystemEventFilterParameter@@AEAK@Z`
- size: `687`
- prototype: `__int64 __fastcall(struct _BR_EVENT_PARAMETERS *, struct _SebiSystemEventCreationParameter *, struct _SebiSystemEventFilterParameter *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180088cc0`

## callees

- `0x180088d7c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088dfe`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088e4f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088ea0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088ee8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088f40`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088f8d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088dfe`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088e4f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088ea0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088ee8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088f40`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180088f8d`

## pseudocode

```c
__int64 __fastcall Broker::SebParametersHelper::UnpackSebEventParameters(
        struct _BR_EVENT_PARAMETERS *a1,
        struct _SebiSystemEventCreationParameter *a2,
        struct _SebiSystemEventFilterParameter *a3,
        unsigned int *a4)
{
  unsigned int i; // ebp
  __int64 v10; // rbx
  const WCHAR *v11; // r8
  int v12; // eax
  __int64 v13; // r8
  unsigned int v14; // eax
  int v15; // eax
  __int64 v16; // r8
  unsigned int v17; // eax
  int v18; // eax
  __int64 v19; // r8
  int v20; // eax
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // r8
  unsigned int v24; // eax
  __int64 v25; // rcx

  if ( !*(_WORD *)a1 || *((_QWORD *)a1 + 1) )
  {
    for ( i = 0; i < *(unsigned __int16 *)a1; ++i )
    {
      v10 = 32LL * i;
      v11 = *(const WCHAR **)(v10 + *((_QWORD *)a1 + 1));
      if ( !v11 )
      {
        *a4 = 20;
        return 3221225485LL;
      }
      v12 = CompareStringW(0x7Fu, 1u, v11, -1, L"Type", -1);
      v13 = *((_QWORD *)a1 + 1);
      if ( v12 == 2 )
      {
        if ( *(_DWORD *)(v13 + v10 + 8) || (v14 = *(_DWORD *)(v13 + v10 + 16), v14 >= 0x4C) )
        {
          *a4 = 30;
          return 3221225485LL;
        }
        *((_DWORD *)a2 + 2) = v14;
      }
      else
      {
        v15 = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v13 + 32LL * i), -1, L"TriggerType", -1);
        v16 = *((_QWORD *)a1 + 1);
        if ( v15 == 2 )
        {
          if ( *(_DWORD *)(v10 + v16 + 8) || (v17 = *(_DWORD *)(v10 + v16 + 16), v17 > 3) )
          {
            *a4 = 40;
            return 3221225485LL;
          }
          *((_DWORD *)a2 + 3) = v17;
        }
        else
        {
          v18 = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v10 + v16), -1, L"OneShot", -1);
          v19 = *((_QWORD *)a1 + 1);
          if ( v18 == 2 )
          {
            if ( *(_DWORD *)(v10 + v19 + 8) )
            {
              *a4 = 50;
              return 3221225485LL;
            }
            *((_DWORD *)a2 + 4) = *(_DWORD *)(v10 + v19 + 16);
          }
          else
          {
            v20 = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v10 + v19), -1, L"EventName", -1);
            v21 = *((_QWORD *)a1 + 1);
            if ( v20 == 2 )
            {
              if ( *(_DWORD *)(v10 + v21 + 8) != 4 || *(_WORD *)(v10 + v21 + 16) != 8 )
              {
                *a4 = 60;
                return 3221225485LL;
              }
              *(_QWORD *)a2 = **(_QWORD **)(v10 + v21 + 24);
            }
            else
            {
              v22 = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v10 + v21), -1, L"FilterVersion", -1);
              v23 = *((_QWORD *)a1 + 1);
              if ( v22 == 2 )
              {
                if ( *(_DWORD *)(v10 + v23 + 8) || (v24 = *(_DWORD *)(v10 + v23 + 16), v24 >= 2) )
                {
                  *a4 = 70;
                  return 3221225485LL;
                }
                *(_DWORD *)a3 = v24;
              }
              else
              {
                if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v10 + v23), -1, L"FilterData", -1) != 2 )
                {
                  *a4 = 90;
                  return 3221225485LL;
                }
                v25 = *((_QWORD *)a1 + 1);
                if ( *(_DWORD *)(v25 + v10 + 8) != 4 )
                {
                  *a4 = 80;
                  return 3221225485LL;
                }
                *((_QWORD *)a3 + 1) = *(_QWORD *)(v25 + v10 + 24);
                *((_DWORD *)a3 + 1) = *(unsigned __int16 *)(v25 + v10 + 16);
              }
            }
          }
        }
      }
    }
    *a4 = 0;
    return 0;
  }
  else
  {
    *a4 = 10;
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180088d7c  push    rbx
0x180088d7e  push    rbp
0x180088d7f  push    rsi
0x180088d80  push    rdi
0x180088d81  push    r12
0x180088d83  push    r13
0x180088d85  push    r14
0x180088d87  push    r15
0x180088d89  sub     rsp, 38h
0x180088d8d  xor     r12d, r12d
0x180088d90  mov     rdi, r9
0x180088d93  mov     r15, r8
0x180088d96  mov     r14, rdx
0x180088d99  mov     rsi, rcx
0x180088d9c  cmp     [rcx], r12w
0x180088da0  jz      short loc_180088DB9
0x180088da2  cmp     [rcx+8], r12
0x180088da6  jnz     short loc_180088DB9
0x180088da8  mov     dword ptr [r9], 0Ah
0x180088daf  mov     eax, 0C000000Dh
0x180088db4  jmp     loc_18008901A
0x180088db9  mov     ebp, r12d
0x180088dbc  or      r13d, 0FFFFFFFFh
0x180088dc0  movzx   eax, word ptr [rsi]
0x180088dc3  cmp     ebp, eax
0x180088dc5  jnb     loc_180089014
0x180088dcb  mov     rax, [rsi+8]
0x180088dcf  mov     ebx, ebp
0x180088dd1  shl     rbx, 5
0x180088dd5  mov     r8, [rbx+rax]; lpString1
0x180088dd9  test    r8, r8
0x180088ddc  jz      loc_180089009
0x180088de2  mov     edx, 1; dwCmpFlags
0x180088de7  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x180088dec  lea     rax, aType; "Type"
0x180088df3  mov     r9d, r13d; cchCount1
0x180088df6  mov     [rsp+78h+lpString2], rax; lpString2
0x180088dfb  lea     ecx, [rdx+7Eh]; Locale
0x180088dfe  call    cs:__imp_CompareStringW
0x180088e04  mov     r8, [rsi+8]
0x180088e08  cmp     eax, 2
0x180088e0b  jnz     short loc_180088E2F
0x180088e0d  cmp     [r8+rbx+8], r12d
0x180088e12  jnz     loc_180088FBC
0x180088e18  mov     eax, [r8+rbx+10h]
0x180088e1d  cmp     eax, 4Ch ; 'L'
0x180088e20  jnb     loc_180088FBC
0x180088e26  mov     [r14+8], eax
0x180088e2a  jmp     loc_180088FB5
0x180088e2f  mov     r8, [r8+rbx]; lpString1
0x180088e33  lea     rax, aTriggertype; "TriggerType"
0x180088e3a  mov     edx, 1; dwCmpFlags
0x180088e3f  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x180088e44  mov     r9d, r13d; cchCount1
0x180088e47  mov     [rsp+78h+lpString2], rax; lpString2
0x180088e4c  lea     ecx, [rdx+7Eh]; Locale
0x180088e4f  call    cs:__imp_CompareStringW
0x180088e55  mov     r8, [rsi+8]
0x180088e59  cmp     eax, 2
0x180088e5c  jnz     short loc_180088E80
0x180088e5e  cmp     [rbx+r8+8], r12d
0x180088e63  jnz     loc_180088FC7
0x180088e69  mov     eax, [rbx+r8+10h]
0x180088e6e  cmp     eax, 3
0x180088e71  ja      loc_180088FC7
0x180088e77  mov     [r14+0Ch], eax
0x180088e7b  jmp     loc_180088FB5
0x180088e80  mov     r8, [rbx+r8]; lpString1
0x180088e84  lea     rax, aOneshot; "OneShot"
0x180088e8b  mov     edx, 1; dwCmpFlags
0x180088e90  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x180088e95  mov     r9d, r13d; cchCount1
0x180088e98  mov     [rsp+78h+lpString2], rax; lpString2
0x180088e9d  lea     ecx, [rdx+7Eh]; Locale
0x180088ea0  call    cs:__imp_CompareStringW
0x180088ea6  mov     r8, [rsi+8]
0x180088eaa  cmp     eax, 2
0x180088ead  jnz     short loc_180088EC8
0x180088eaf  cmp     [rbx+r8+8], r12d
0x180088eb4  jnz     loc_180088FD2
0x180088eba  mov     eax, [rbx+r8+10h]
0x180088ebf  mov     [r14+10h], eax
0x180088ec3  jmp     loc_180088FB5
0x180088ec8  mov     r8, [rbx+r8]; lpString1
0x180088ecc  lea     rax, aEventname; "EventName"
0x180088ed3  mov     edx, 1; dwCmpFlags
0x180088ed8  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x180088edd  mov     r9d, r13d; cchCount1
0x180088ee0  mov     [rsp+78h+lpString2], rax; lpString2
0x180088ee5  lea     ecx, [rdx+7Eh]; Locale
0x180088ee8  call    cs:__imp_CompareStringW
0x180088eee  mov     r8, [rsi+8]
0x180088ef2  cmp     eax, 2
0x180088ef5  jnz     short loc_180088F20
0x180088ef7  cmp     dword ptr [rbx+r8+8], 4
0x180088efd  jnz     loc_180088FDD
0x180088f03  cmp     word ptr [rbx+r8+10h], 8
0x180088f0a  jnz     loc_180088FDD
0x180088f10  mov     rax, [rbx+r8+18h]
0x180088f15  mov     rcx, [rax]
0x180088f18  mov     [r14], rcx
0x180088f1b  jmp     loc_180088FB5
0x180088f20  mov     r8, [rbx+r8]; lpString1
0x180088f24  lea     rax, aFilterversion; "FilterVersion"
0x180088f2b  mov     edx, 1; dwCmpFlags
0x180088f30  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x180088f35  mov     r9d, r13d; cchCount1
0x180088f38  mov     [rsp+78h+lpString2], rax; lpString2
0x180088f3d  lea     ecx, [rdx+7Eh]; Locale
0x180088f40  call    cs:__imp_CompareStringW
0x180088f46  mov     r8, [rsi+8]
0x180088f4a  cmp     eax, 2
0x180088f4d  jnz     short loc_180088F6D
0x180088f4f  cmp     [rbx+r8+8], r12d
0x180088f54  jnz     loc_180088FE8
0x180088f5a  mov     eax, [rbx+r8+10h]
0x180088f5f  cmp     eax, 2
0x180088f62  jnb     loc_180088FE8
0x180088f68  mov     [r15], eax
0x180088f6b  jmp     short loc_180088FB5
0x180088f6d  mov     r8, [rbx+r8]; lpString1
0x180088f71  lea     rax, aFilterdata; "FilterData"
0x180088f78  mov     edx, 1; dwCmpFlags
0x180088f7d  mov     [rsp+78h+cchCount2], r13d; cchCount2
0x180088f82  mov     r9d, r13d; cchCount1
0x180088f85  mov     [rsp+78h+lpString2], rax; lpString2
0x180088f8a  lea     ecx, [rdx+7Eh]; Locale
0x180088f8d  call    cs:__imp_CompareStringW
0x180088f93  cmp     eax, 2
0x180088f96  jnz     short loc_180088FFE
0x180088f98  mov     rcx, [rsi+8]
0x180088f9c  cmp     dword ptr [rcx+rbx+8], 4
0x180088fa1  jnz     short loc_180088FF3
0x180088fa3  mov     rax, [rcx+rbx+18h]
0x180088fa8  mov     [r15+8], rax
0x180088fac  movzx   eax, word ptr [rcx+rbx+10h]
0x180088fb1  mov     [r15+4], eax
0x180088fb5  inc     ebp
0x180088fb7  jmp     loc_180088DC0
0x180088fbc  mov     dword ptr [rdi], 1Eh
0x180088fc2  jmp     loc_180088DAF
0x180088fc7  mov     dword ptr [rdi], 28h ; '('
0x180088fcd  jmp     loc_180088DAF
0x180088fd2  mov     dword ptr [rdi], 32h ; '2'
0x180088fd8  jmp     loc_180088DAF
0x180088fdd  mov     dword ptr [rdi], 3Ch ; '<'
0x180088fe3  jmp     loc_180088DAF
0x180088fe8  mov     dword ptr [rdi], 46h ; 'F'
0x180088fee  jmp     loc_180088DAF
0x180088ff3  mov     dword ptr [rdi], 50h ; 'P'
0x180088ff9  jmp     loc_180088DAF
0x180088ffe  mov     dword ptr [rdi], 5Ah ; 'Z'
0x180089004  jmp     loc_180088DAF
0x180089009  mov     dword ptr [rdi], 14h
0x18008900f  jmp     loc_180088DAF
0x180089014  mov     [rdi], r12d
0x180089017  mov     eax, r12d
0x18008901a  add     rsp, 38h
0x18008901e  pop     r15
0x180089020  pop     r14
0x180089022  pop     r13
0x180089024  pop     r12
0x180089026  pop     rdi
0x180089027  pop     rsi
0x180089028  pop     rbp
0x180089029  pop     rbx
0x18008902a  retn
```

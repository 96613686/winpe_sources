# Broker::SebParametersHelper::UnpackSebEventParameters(_BR_EVENT_PARAMETERS *,_SebiSystemEventCreationParameter &,_SebiSystemEventFilterParameter &,ulong &)

- ea: `0x180013c40`
- end: `0x180013f55`
- name: `?UnpackSebEventParameters@SebParametersHelper@Broker@@SAJPEAU_BR_EVENT_PARAMETERS@@AEAU_SebiSystemEventCreationParameter@@AEAU_SebiSystemEventFilterParameter@@AEAK@Z`
- size: `789`
- prototype: `__int64 __fastcall(struct _BR_EVENT_PARAMETERS *, struct _SebiSystemEventCreationParameter *, struct _SebiSystemEventFilterParameter *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011190`

## callees

- `0x180013c40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013cd8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013d2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013d84`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013dd5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013e35`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013e8b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013cd8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013d2a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013d84`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013dd5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013e35`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013e8b`

## pseudocode

```c
__int64 __fastcall Broker::SebParametersHelper::UnpackSebEventParameters(
        struct _BR_EVENT_PARAMETERS *a1,
        struct _SebiSystemEventCreationParameter *a2,
        struct _SebiSystemEventFilterParameter *a3,
        unsigned int *a4)
{
  unsigned int v9; // edi
  __int64 v10; // rsi
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
  __int64 v25; // rax

  if ( !*(_WORD *)a1 || *((_QWORD *)a1 + 1) )
  {
    v9 = 0;
    while ( v9 < *(unsigned __int16 *)a1 )
    {
      v10 = 32LL * v9;
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
        ++v9;
      }
      else
      {
        v15 = CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v13 + 32LL * v9), -1, L"TriggerType", -1);
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
                *((_DWORD *)a3 + 1) = *(unsigned __int16 *)(*((_QWORD *)a1 + 1) + v10 + 16);
              }
            }
          }
        }
        ++v9;
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
0x180013c40  push    rbx
0x180013c42  push    rbp
0x180013c43  push    r14
0x180013c45  push    r15
0x180013c47  sub     rsp, 38h
0x180013c4b  cmp     word ptr [rcx], 0
0x180013c4f  mov     r14, r9
0x180013c52  mov     rbp, r8
0x180013c55  mov     r15, rdx
0x180013c58  mov     rbx, rcx
0x180013c5b  jz      short loc_180013C75
0x180013c5d  cmp     qword ptr [rcx+8], 0
0x180013c62  jnz     short loc_180013C75
0x180013c64  mov     dword ptr [r9], 0Ah
0x180013c6b  mov     eax, 0C000000Dh
0x180013c70  jmp     loc_180013F4A
0x180013c75  mov     [rsp+58h+arg_8], rdi
0x180013c7a  xor     edi, edi
0x180013c7c  mov     [rsp+58h+arg_10], r12
0x180013c81  lea     r12, aTriggertype_0; "TriggerType"
0x180013c88  mov     [rsp+58h+var_28], r13
0x180013c8d  lea     r13, aType_0; "Type"
0x180013c94  mov     [rsp+58h+arg_0], rsi
0x180013c99  movzx   eax, word ptr [rbx]
0x180013c9c  cmp     edi, eax
0x180013c9e  jnb     loc_180013F2D
0x180013ca4  mov     rax, [rbx+8]
0x180013ca8  mov     esi, edi
0x180013caa  shl     rsi, 5
0x180013cae  mov     r8, [rsi+rax]; lpString1
0x180013cb2  test    r8, r8
0x180013cb5  jz      loc_180013F1F
0x180013cbb  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180013cc3  mov     edx, 1; dwCmpFlags
0x180013cc8  mov     ecx, 7Fh; Locale
0x180013ccd  mov     [rsp+58h+lpString2], r13; lpString2
0x180013cd2  mov     r9d, 0FFFFFFFFh; cchCount1
0x180013cd8  call    cs:__imp_CompareStringW
0x180013cde  mov     r8, [rbx+8]
0x180013ce2  cmp     eax, 2
0x180013ce5  jnz     short loc_180013D09
0x180013ce7  cmp     dword ptr [r8+rsi+8], 0
0x180013ced  jnz     loc_180013EBD
0x180013cf3  mov     eax, [r8+rsi+10h]
0x180013cf8  cmp     eax, 4Ch ; 'L'
0x180013cfb  jnb     loc_180013EBD
0x180013d01  mov     [r15+8], eax
0x180013d05  inc     edi
0x180013d07  jmp     short loc_180013C99
0x180013d09  mov     r8, [r8+rsi]; lpString1
0x180013d0d  mov     r9d, 0FFFFFFFFh; cchCount1
0x180013d13  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180013d1b  mov     edx, 1; dwCmpFlags
0x180013d20  mov     ecx, 7Fh; Locale
0x180013d25  mov     [rsp+58h+lpString2], r12; lpString2
0x180013d2a  call    cs:__imp_CompareStringW
0x180013d30  mov     r8, [rbx+8]
0x180013d34  cmp     eax, 2
0x180013d37  jnz     short loc_180013D5C
0x180013d39  cmp     dword ptr [rsi+r8+8], 0
0x180013d3f  jnz     loc_180013ECB
0x180013d45  mov     eax, [rsi+r8+10h]
0x180013d4a  cmp     eax, 3
0x180013d4d  ja      loc_180013ECB
0x180013d53  mov     [r15+0Ch], eax
0x180013d57  jmp     loc_180013EB6
0x180013d5c  mov     r8, [rsi+r8]; lpString1
0x180013d60  lea     rax, aOneshot_0; "OneShot"
0x180013d67  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180013d6f  mov     r9d, 0FFFFFFFFh; cchCount1
0x180013d75  mov     edx, 1; dwCmpFlags
0x180013d7a  mov     [rsp+58h+lpString2], rax; lpString2
0x180013d7f  mov     ecx, 7Fh; Locale
0x180013d84  call    cs:__imp_CompareStringW
0x180013d8a  mov     r8, [rbx+8]
0x180013d8e  cmp     eax, 2
0x180013d91  jnz     short loc_180013DAD
0x180013d93  cmp     dword ptr [rsi+r8+8], 0
0x180013d99  jnz     loc_180013ED9
0x180013d9f  mov     eax, [rsi+r8+10h]
0x180013da4  mov     [r15+10h], eax
0x180013da8  jmp     loc_180013EB6
0x180013dad  mov     r8, [rsi+r8]; lpString1
0x180013db1  lea     rax, aEventname_0; "EventName"
0x180013db8  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180013dc0  mov     r9d, 0FFFFFFFFh; cchCount1
0x180013dc6  mov     edx, 1; dwCmpFlags
0x180013dcb  mov     [rsp+58h+lpString2], rax; lpString2
0x180013dd0  mov     ecx, 7Fh; Locale
0x180013dd5  call    cs:__imp_CompareStringW
0x180013ddb  mov     r8, [rbx+8]
0x180013ddf  cmp     eax, 2
0x180013de2  jnz     short loc_180013E0D
0x180013de4  cmp     dword ptr [rsi+r8+8], 4
0x180013dea  jnz     loc_180013EE7
0x180013df0  cmp     word ptr [rsi+r8+10h], 8
0x180013df7  jnz     loc_180013EE7
0x180013dfd  mov     rax, [rsi+r8+18h]
0x180013e02  mov     rcx, [rax]
0x180013e05  mov     [r15], rcx
0x180013e08  jmp     loc_180013EB6
0x180013e0d  mov     r8, [rsi+r8]; lpString1
0x180013e11  lea     rax, aFilterversion; "FilterVersion"
0x180013e18  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180013e20  mov     r9d, 0FFFFFFFFh; cchCount1
0x180013e26  mov     edx, 1; dwCmpFlags
0x180013e2b  mov     [rsp+58h+lpString2], rax; lpString2
0x180013e30  mov     ecx, 7Fh; Locale
0x180013e35  call    cs:__imp_CompareStringW
0x180013e3b  mov     r8, [rbx+8]
0x180013e3f  cmp     eax, 2
0x180013e42  jnz     short loc_180013E63
0x180013e44  cmp     dword ptr [rsi+r8+8], 0
0x180013e4a  jnz     loc_180013EF5
0x180013e50  mov     eax, [rsi+r8+10h]
0x180013e55  cmp     eax, 2
0x180013e58  jnb     loc_180013EF5
0x180013e5e  mov     [rbp+0], eax
0x180013e61  jmp     short loc_180013EB6
0x180013e63  mov     r8, [rsi+r8]; lpString1
0x180013e67  lea     rax, aFilterdata; "FilterData"
0x180013e6e  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180013e76  mov     r9d, 0FFFFFFFFh; cchCount1
0x180013e7c  mov     edx, 1; dwCmpFlags
0x180013e81  mov     [rsp+58h+lpString2], rax; lpString2
0x180013e86  mov     ecx, 7Fh; Locale
0x180013e8b  call    cs:__imp_CompareStringW
0x180013e91  cmp     eax, 2
0x180013e94  jnz     short loc_180013F11
0x180013e96  mov     rax, [rbx+8]
0x180013e9a  cmp     dword ptr [rax+rsi+8], 4
0x180013e9f  jnz     short loc_180013F03
0x180013ea1  mov     rax, [rax+rsi+18h]
0x180013ea6  mov     [rbp+8], rax
0x180013eaa  mov     rax, [rbx+8]
0x180013eae  movzx   ecx, word ptr [rax+rsi+10h]
0x180013eb3  mov     [rbp+4], ecx
0x180013eb6  inc     edi
0x180013eb8  jmp     loc_180013C99
0x180013ebd  mov     dword ptr [r14], 1Eh
0x180013ec4  mov     eax, 0C000000Dh
0x180013ec9  jmp     short loc_180013F36
0x180013ecb  mov     dword ptr [r14], 28h ; '('
0x180013ed2  mov     eax, 0C000000Dh
0x180013ed7  jmp     short loc_180013F36
0x180013ed9  mov     dword ptr [r14], 32h ; '2'
0x180013ee0  mov     eax, 0C000000Dh
0x180013ee5  jmp     short loc_180013F36
0x180013ee7  mov     dword ptr [r14], 3Ch ; '<'
0x180013eee  mov     eax, 0C000000Dh
0x180013ef3  jmp     short loc_180013F36
0x180013ef5  mov     dword ptr [r14], 46h ; 'F'
0x180013efc  mov     eax, 0C000000Dh
0x180013f01  jmp     short loc_180013F36
0x180013f03  mov     dword ptr [r14], 50h ; 'P'
0x180013f0a  mov     eax, 0C000000Dh
0x180013f0f  jmp     short loc_180013F36
0x180013f11  mov     dword ptr [r14], 5Ah ; 'Z'
0x180013f18  mov     eax, 0C000000Dh
0x180013f1d  jmp     short loc_180013F36
0x180013f1f  mov     dword ptr [r14], 14h
0x180013f26  mov     eax, 0C000000Dh
0x180013f2b  jmp     short loc_180013F36
0x180013f2d  mov     dword ptr [r14], 0
0x180013f34  xor     eax, eax
0x180013f36  mov     rsi, [rsp+58h+arg_0]
0x180013f3b  mov     rdi, [rsp+58h+arg_8]
0x180013f40  mov     r12, [rsp+58h+arg_10]
0x180013f45  mov     r13, [rsp+58h+var_28]
0x180013f4a  add     rsp, 38h
0x180013f4e  pop     r15
0x180013f50  pop     r14
0x180013f52  pop     rbp
0x180013f53  pop     rbx
0x180013f54  retn
```

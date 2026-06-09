# RegisterObject

- ea: `0x180002200`
- end: `0x18000248a`
- name: `RegisterObject`
- size: `650`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, int, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002200`
- `0x180002a40`
- `0x180002b20`
- `0x180002d10`
- `0x1800085b0`
- `0x180008ff0`
- `0x180009130`
- `0x18000b894`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000243b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000243b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000239b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000239b`

## pseudocode

```c
__int64 __fastcall RegisterObject(LPCWSTR lpSubKey, int a2, __int64 a3)
{
  unsigned int v6; // eax
  unsigned int SecurityDescriptorFromRegistry; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rax
  unsigned int v12; // eax
  __int64 v13; // r10
  DWORD LastError; // eax
  unsigned int v15; // eax
  int v17; // [rsp+40h] [rbp-28h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+48h] [rbp-20h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+88h] [rbp+20h] BYREF

  v17 = 0;
  StringSecurityDescriptor = 0;
  StringSecurityDescriptorLen = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
  v6 = AcquireLockSecurityObject(&v17);
  SecurityDescriptorFromRegistry = v6;
  if ( v6 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v9 = 91;
      v10 = v6;
LABEL_31:
      WPP_SF_L(v8[2], v9, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v10);
    }
  }
  else if ( lpSubKey
         && a3
         && (v11 = *(unsigned int *)(a3 + 8), (unsigned int)v11 < 0x14)
         && !*(_QWORD *)(*(_QWORD *)&g_pSecurity + 8 * v11 + 120) )
  {
    SecurityDescriptorFromRegistry = ReadSecurityDescriptorFromRegistry(
                                       lpSubKey,
                                       *(const WCHAR **)a3,
                                       *(unsigned int *)(a3 + 12),
                                       *(_QWORD *)&g_pSecurity + 120LL + 8 * v11);
    if ( SecurityDescriptorFromRegistry )
    {
      v12 = BuildLogicalSecurityDescriptor(
              *(_DWORD *)(a3 + 12),
              g_pSecurity,
              *(_DWORD *)(a3 + 16),
              *(_QWORD *)(a3 + 24),
              *(PSID *)(*(_QWORD *)&g_pSecurity + 416LL),
              *(PSID *)(*(_QWORD *)&g_pSecurity + 416LL),
              *(_QWORD *)&g_pSecurity + 8 * (*(unsigned int *)(a3 + 8) + 15LL));
      SecurityDescriptorFromRegistry = v12;
      if ( v12 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v9 = 93;
          v10 = v12;
          goto LABEL_31;
        }
      }
      else
      {
        v13 = *(_QWORD *)&g_pSecurity;
        *(_DWORD *)(*(_QWORD *)&g_pSecurity + 4LL * *(unsigned int *)(a3 + 8) + 280) = a2;
        if ( *(_QWORD *)a3 )
        {
          if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
                 *(PSECURITY_DESCRIPTOR *)(v13 + 8LL * *(unsigned int *)(a3 + 8) + 120),
                 1u,
                 7u,
                 &StringSecurityDescriptor,
                 &StringSecurityDescriptorLen)
            || (LastError = GetLastError(), (SecurityDescriptorFromRegistry = LastError) == 0) )
          {
            v15 = WriteSecurityDescriptorToRegistry(
                    lpSubKey,
                    *(LPCWSTR *)a3,
                    StringSecurityDescriptorLen,
                    (const BYTE *)StringSecurityDescriptor);
            SecurityDescriptorFromRegistry = v15;
            if ( v15 )
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                v9 = 95;
                v10 = v15;
                goto LABEL_31;
              }
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v9 = 94;
              v10 = LastError;
              goto LABEL_31;
            }
          }
        }
      }
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)&g_pSecurity + 4LL * *(unsigned int *)(a3 + 8) + 280) = a2;
    }
  }
  else
  {
    SecurityDescriptorFromRegistry = 87;
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v9 = 92;
      v10 = 87;
      goto LABEL_31;
    }
  }
  LocalFree(StringSecurityDescriptor);
  ReleaseLockSecurityObject(&v17);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      WPP_fd6184a389643c6486807174a58ed414_Traceguids,
      SecurityDescriptorFromRegistry);
  return SecurityDescriptorFromRegistry;
}

```

## disassembly

```asm
0x180002200  mov     [rsp+arg_0], rbx
0x180002205  mov     [rsp+arg_8], rbp
0x18000220a  push    rsi
0x18000220b  push    rdi
0x18000220c  push    r14
0x18000220e  sub     rsp, 50h
0x180002212  xor     eax, eax
0x180002214  mov     rdi, r8
0x180002217  mov     [rsp+68h+var_28], eax
0x18000221b  mov     ebp, edx
0x18000221d  mov     [rsp+68h+StringSecurityDescriptor], rax
0x180002222  mov     rsi, rcx
0x180002225  mov     [rsp+68h+arg_18], eax
0x18000222c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002233  lea     r14, WPP_GLOBAL_Control
0x18000223a  cmp     rcx, r14
0x18000223d  jz      short loc_18000225A
0x18000223f  test    byte ptr [rcx+1Ch], 8
0x180002243  jz      short loc_18000225A
0x180002245  mov     rcx, [rcx+10h]
0x180002249  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002250  mov     edx, 5Ah ; 'Z'
0x180002255  call    WPP_SF_
0x18000225a  lea     rcx, [rsp+68h+var_28]
0x18000225f  call    AcquireLockSecurityObject
0x180002264  mov     ebx, eax
0x180002266  test    eax, eax
0x180002268  jz      short loc_180002291
0x18000226a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002271  cmp     rcx, r14
0x180002274  jz      loc_180002436
0x18000227a  test    byte ptr [rcx+1Ch], 4
0x18000227e  jz      loc_180002436
0x180002284  mov     edx, 5Bh ; '['
0x180002289  mov     r9d, eax
0x18000228c  jmp     loc_180002426
0x180002291  test    rsi, rsi
0x180002294  jz      loc_180002407
0x18000229a  test    rdi, rdi
0x18000229d  jz      loc_180002407
0x1800022a3  mov     eax, [rdi+8]
0x1800022a6  cmp     eax, 14h
0x1800022a9  jnb     loc_180002407
0x1800022af  mov     rcx, cs:g_pSecurity
0x1800022b6  cmp     qword ptr [rcx+rax*8+78h], 0
0x1800022bc  jnz     loc_180002407
0x1800022c2  mov     r8d, [rdi+0Ch]
0x1800022c6  add     rcx, 78h ; 'x'
0x1800022ca  mov     rdx, [rdi]
0x1800022cd  lea     r9, [rcx+rax*8]
0x1800022d1  mov     rcx, rsi
0x1800022d4  call    ReadSecurityDescriptorFromRegistry
0x1800022d9  mov     ebx, eax
0x1800022db  test    eax, eax
0x1800022dd  jnz     short loc_1800022F5
0x1800022df  mov     ecx, [rdi+8]
0x1800022e2  mov     rax, cs:g_pSecurity
0x1800022e9  mov     [rax+rcx*4+118h], ebp
0x1800022f0  jmp     loc_180002436
0x1800022f5  mov     rdx, cs:g_pSecurity; int
0x1800022fc  mov     eax, [rdi+8]
0x1800022ff  mov     r9, [rdi+18h]; int
0x180002303  add     rax, 0Fh
0x180002307  mov     r8, [rdx+1A0h]
0x18000230e  lea     rcx, [rdx+rax*8]
0x180002312  mov     [rsp+68h+var_38], rcx; __int64
0x180002317  mov     ecx, [rdi+0Ch]; int
0x18000231a  mov     [rsp+68h+pGroup], r8; pGroup
0x18000231f  mov     [rsp+68h+StringSecurityDescriptorLen], r8; pOwner
0x180002324  mov     r8d, [rdi+10h]; int
0x180002328  call    BuildLogicalSecurityDescriptor
0x18000232d  mov     ebx, eax
0x18000232f  test    eax, eax
0x180002331  jz      short loc_18000235A
0x180002333  mov     rcx, cs:WPP_GLOBAL_Control
0x18000233a  cmp     rcx, r14
0x18000233d  jz      loc_180002436
0x180002343  test    byte ptr [rcx+1Ch], 4
0x180002347  jz      loc_180002436
0x18000234d  mov     edx, 5Dh ; ']'
0x180002352  mov     r9d, eax
0x180002355  jmp     loc_180002426
0x18000235a  mov     eax, [rdi+8]
0x18000235d  mov     r10, cs:g_pSecurity
0x180002364  mov     [r10+rax*4+118h], ebp
0x18000236c  cmp     qword ptr [rdi], 0
0x180002370  jz      loc_180002436
0x180002376  mov     ecx, [rdi+8]
0x180002379  lea     rax, [rsp+68h+arg_18]
0x180002381  lea     r9, [rsp+68h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180002386  mov     [rsp+68h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x18000238b  mov     edx, 1; RequestedStringSDRevision
0x180002390  mov     r8d, 7; SecurityInformation
0x180002396  mov     rcx, [r10+rcx*8+78h]; SecurityDescriptor
0x18000239b  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x1800023a1  test    eax, eax
0x1800023a3  jnz     short loc_1800023CD
0x1800023a5  call    cs:__imp_GetLastError
0x1800023ab  mov     ebx, eax
0x1800023ad  test    eax, eax
0x1800023af  jz      short loc_1800023CD
0x1800023b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023b8  cmp     rcx, r14
0x1800023bb  jz      short loc_180002436
0x1800023bd  test    byte ptr [rcx+1Ch], 4
0x1800023c1  jz      short loc_180002436
0x1800023c3  mov     edx, 5Eh ; '^'
0x1800023c8  mov     r9d, eax
0x1800023cb  jmp     short loc_180002426
0x1800023cd  mov     r9, [rsp+68h+StringSecurityDescriptor]
0x1800023d2  mov     rcx, rsi; lpSubKey
0x1800023d5  mov     r8d, [rsp+68h+arg_18]
0x1800023dd  mov     rdx, [rdi]; lpValueName
0x1800023e0  call    WriteSecurityDescriptorToRegistry
0x1800023e5  mov     ebx, eax
0x1800023e7  test    eax, eax
0x1800023e9  jz      short loc_180002436
0x1800023eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023f2  cmp     rcx, r14
0x1800023f5  jz      short loc_180002436
0x1800023f7  test    byte ptr [rcx+1Ch], 4
0x1800023fb  jz      short loc_180002436
0x1800023fd  mov     edx, 5Fh ; '_'
0x180002402  mov     r9d, eax
0x180002405  jmp     short loc_180002426
0x180002407  mov     ebx, 57h ; 'W'
0x18000240c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002413  cmp     rcx, r14
0x180002416  jz      short loc_180002436
0x180002418  test    byte ptr [rcx+1Ch], 4
0x18000241c  jz      short loc_180002436
0x18000241e  mov     edx, 5Ch ; '\'
0x180002423  mov     r9d, ebx
0x180002426  mov     rcx, [rcx+10h]
0x18000242a  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002431  call    WPP_SF_L
0x180002436  mov     rcx, [rsp+68h+StringSecurityDescriptor]; hMem
0x18000243b  call    cs:__imp_LocalFree
0x180002441  lea     rcx, [rsp+68h+var_28]
0x180002446  call    ReleaseLockSecurityObject
0x18000244b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002452  cmp     rcx, r14
0x180002455  jz      short loc_180002475
0x180002457  test    byte ptr [rcx+1Ch], 8
0x18000245b  jz      short loc_180002475
0x18000245d  mov     rcx, [rcx+10h]
0x180002461  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180002468  mov     edx, 61h ; 'a'
0x18000246d  mov     r9d, ebx
0x180002470  call    WPP_SF_L
0x180002475  mov     rbp, [rsp+68h+arg_8]
0x18000247a  mov     eax, ebx
0x18000247c  mov     rbx, [rsp+68h+arg_0]
0x180002481  add     rsp, 50h
0x180002485  pop     r14
0x180002487  pop     rdi
0x180002488  pop     rsi
0x180002489  retn
```

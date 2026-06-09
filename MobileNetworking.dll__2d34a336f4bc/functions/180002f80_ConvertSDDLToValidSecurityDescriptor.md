# ConvertSDDLToValidSecurityDescriptor

- ea: `0x180002f80`
- end: `0x1800031f6`
- name: `ConvertSDDLToValidSecurityDescriptor`
- size: `630`
- prototype: `__int64 __fastcall(LPCWSTR StringSecurityDescriptor, unsigned int, _DWORD *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001dc0`
- `0x180002d10`

## callees

- `0x180002f80`
- `0x180003200`
- `0x180004390`
- `0x180008ff0`
- `0x180009130`
- `0x1800118f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000300a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000300a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000302b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000302b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003000`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180003000`

## string_xrefs

- `0x180003081`: `ConvertSDDLToValidSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall ConvertSDDLToValidSecurityDescriptor(
        LPCWSTR StringSecurityDescriptor,
        unsigned int a2,
        _DWORD *a3,
        void **a4)
{
  PVOID *v8; // rcx
  __int64 v9; // rax
  DWORD LastError; // eax
  unsigned int v11; // ebx
  unsigned int v13; // eax
  unsigned int Memory; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-28h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+50h] [rbp+8h] BYREF

  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !StringSecurityDescriptor )
  {
    v11 = 87;
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 4) == 0 )
      goto LABEL_11;
    v15 = 30;
    goto LABEL_25;
  }
  v9 = -1;
  do
    ++v9;
  while ( StringSecurityDescriptor[v9] );
  if ( a3 )
  {
    *a3 = v9;
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (unsigned int)v9 > 0x7D0 )
  {
    v11 = 87;
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 4) == 0 )
      goto LABEL_11;
    v15 = 31;
    goto LABEL_25;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         StringSecurityDescriptor,
         1u,
         &SecurityDescriptor,
         &SecurityDescriptorSize)
    || (LastError = GetLastError(), (v11 = LastError) == 0) )
  {
    if ( SecurityDescriptorSize && SecurityDescriptor )
    {
      v13 = ValidateSecurityDescriptor(a2);
      v11 = v13;
      if ( v13 )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v15 = 34;
          v16 = v13;
          goto LABEL_26;
        }
      }
      else if ( a4 )
      {
        Memory = AllocateMemory(SecurityDescriptorSize, a4, (int)"ConvertSDDLToValidSecurityDescriptor", 18);
        v11 = Memory;
        if ( Memory )
        {
          v8 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            v15 = 35;
            v16 = Memory;
            goto LABEL_26;
          }
        }
        else
        {
          memcpy_0(*a4, SecurityDescriptor, SecurityDescriptorSize);
        }
      }
      goto LABEL_11;
    }
    v11 = 5023;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_11;
    v15 = 33;
LABEL_25:
    v16 = v11;
LABEL_26:
    WPP_SF_L(v8[2], v15, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v16);
    goto LABEL_11;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v15 = 32;
    v16 = LastError;
    goto LABEL_26;
  }
LABEL_11:
  LocalFree(SecurityDescriptor);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180002f80  mov     [rsp+arg_8], rbx
0x180002f85  mov     [rsp+arg_10], rbp
0x180002f8a  push    rsi
0x180002f8b  push    rdi
0x180002f8c  push    r14
0x180002f8e  sub     rsp, 30h
0x180002f92  xor     eax, eax
0x180002f94  mov     rsi, r9
0x180002f97  mov     [rsp+48h+SecurityDescriptor], rax
0x180002f9c  mov     rdi, r8
0x180002f9f  mov     [rsp+48h+SecurityDescriptorSize], eax
0x180002fa3  mov     ebp, edx
0x180002fa5  mov     rbx, rcx
0x180002fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180002faf  lea     r14, WPP_GLOBAL_Control
0x180002fb6  cmp     rcx, r14
0x180002fb9  jnz     loc_180003112
0x180002fbf  test    rbx, rbx
0x180002fc2  jz      loc_18000313D
0x180002fc8  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180002fcf  nop
0x180002fd0  inc     rax
0x180002fd3  cmp     word ptr [rbx+rax*2], 0
0x180002fd8  jnz     short loc_180002FD0
0x180002fda  test    rdi, rdi
0x180002fdd  jnz     loc_18000315C
0x180002fe3  cmp     eax, 7D0h
0x180002fe8  ja      loc_1800030B7
0x180002fee  lea     r9, [rsp+48h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180002ff3  mov     edx, 1; StringSDRevision
0x180002ff8  lea     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x180002ffd  mov     rcx, rbx; StringSecurityDescriptor
0x180003000  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180003006  test    eax, eax
0x180003008  jnz     short loc_180003056
0x18000300a  call    cs:__imp_GetLastError
0x180003010  mov     ebx, eax
0x180003012  test    eax, eax
0x180003014  jz      short loc_180003056
0x180003016  mov     rcx, cs:WPP_GLOBAL_Control
0x18000301d  cmp     rcx, r14
0x180003020  jnz     loc_18000316A
0x180003026  mov     rcx, [rsp+48h+SecurityDescriptor]; hMem
0x18000302b  call    cs:__imp_LocalFree
0x180003031  mov     rcx, cs:WPP_GLOBAL_Control
0x180003038  cmp     rcx, r14
0x18000303b  jnz     loc_1800031CF
0x180003041  mov     rbp, [rsp+48h+arg_10]
0x180003046  mov     eax, ebx
0x180003048  mov     rbx, [rsp+48h+arg_8]
0x18000304d  add     rsp, 30h
0x180003051  pop     r14
0x180003053  pop     rdi
0x180003054  pop     rsi
0x180003055  retn
0x180003056  cmp     [rsp+48h+SecurityDescriptorSize], 0
0x18000305b  jz      short loc_1800030D6
0x18000305d  mov     rdx, [rsp+48h+SecurityDescriptor]
0x180003062  test    rdx, rdx
0x180003065  jz      short loc_1800030D6
0x180003067  mov     ecx, ebp
0x180003069  call    ValidateSecurityDescriptor
0x18000306e  mov     ebx, eax
0x180003070  test    eax, eax
0x180003072  jnz     loc_180003181
0x180003078  test    rsi, rsi
0x18000307b  jz      short loc_180003026
0x18000307d  mov     ecx, [rsp+48h+SecurityDescriptorSize]; dwBytes
0x180003081  lea     r8, aConvertsddltov_0; "ConvertSDDLToValidSecurityDescriptor"
0x180003088  mov     r9d, 112h
0x18000308e  mov     rdx, rsi
0x180003091  call    AllocateMemory
0x180003096  mov     ebx, eax
0x180003098  test    eax, eax
0x18000309a  jnz     loc_1800031A8
0x1800030a0  mov     r8d, [rsp+48h+SecurityDescriptorSize]; Size
0x1800030a5  mov     rdx, [rsp+48h+SecurityDescriptor]; Src
0x1800030aa  mov     rcx, [rsi]; void *
0x1800030ad  call    memcpy_0
0x1800030b2  jmp     loc_180003026
0x1800030b7  mov     ebx, 57h ; 'W'
0x1800030bc  cmp     rcx, r14
0x1800030bf  jz      loc_180003026
0x1800030c5  test    byte ptr [rcx+1Ch], 4
0x1800030c9  jz      loc_180003026
0x1800030cf  mov     edx, 1Fh
0x1800030d4  jmp     short loc_1800030FA
0x1800030d6  mov     ebx, 139Fh
0x1800030db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030e2  cmp     rcx, r14
0x1800030e5  jz      loc_180003026
0x1800030eb  test    byte ptr [rcx+1Ch], 4
0x1800030ef  jz      loc_180003026
0x1800030f5  mov     edx, 21h ; '!'
0x1800030fa  mov     r9d, ebx
0x1800030fd  mov     rcx, [rcx+10h]
0x180003101  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180003108  call    WPP_SF_L
0x18000310d  jmp     loc_180003026
0x180003112  test    byte ptr [rcx+1Ch], 8
0x180003116  jz      loc_180002FBF
0x18000311c  mov     rcx, [rcx+10h]
0x180003120  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180003127  mov     edx, 1Dh
0x18000312c  call    WPP_SF_
0x180003131  mov     rcx, cs:WPP_GLOBAL_Control
0x180003138  jmp     loc_180002FBF
0x18000313d  mov     ebx, 57h ; 'W'
0x180003142  cmp     rcx, r14
0x180003145  jz      loc_180003026
0x18000314b  test    byte ptr [rcx+1Ch], 4
0x18000314f  jz      loc_180003026
0x180003155  mov     edx, 1Eh
0x18000315a  jmp     short loc_1800030FA
0x18000315c  mov     [rdi], eax
0x18000315e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003165  jmp     loc_180002FE3
0x18000316a  test    byte ptr [rcx+1Ch], 4
0x18000316e  jz      loc_180003026
0x180003174  mov     edx, 20h ; ' '
0x180003179  mov     r9d, eax
0x18000317c  jmp     loc_1800030FD
0x180003181  mov     rcx, cs:WPP_GLOBAL_Control
0x180003188  cmp     rcx, r14
0x18000318b  jz      loc_180003026
0x180003191  test    byte ptr [rcx+1Ch], 4
0x180003195  jz      loc_180003026
0x18000319b  mov     edx, 22h ; '"'
0x1800031a0  mov     r9d, eax
0x1800031a3  jmp     loc_1800030FD
0x1800031a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031af  cmp     rcx, r14
0x1800031b2  jz      loc_180003026
0x1800031b8  test    byte ptr [rcx+1Ch], 4
0x1800031bc  jz      loc_180003026
0x1800031c2  mov     edx, 23h ; '#'
0x1800031c7  mov     r9d, eax
0x1800031ca  jmp     loc_1800030FD
0x1800031cf  test    byte ptr [rcx+1Ch], 8
0x1800031d3  jz      loc_180003041
0x1800031d9  mov     rcx, [rcx+10h]
0x1800031dd  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x1800031e4  mov     edx, 24h ; '$'
0x1800031e9  mov     r9d, ebx
0x1800031ec  call    WPP_SF_L
0x1800031f1  jmp     loc_180003041
```
